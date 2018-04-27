---
title: "Créer des règles pour le Conseiller en optimisation"
description: "Cette rubrique décrit comment ajouter de nouvelles règles au Conseiller en optimisation."
author: roxanadiaconu
manager: AnnBe
ms.date: 02/04/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SelfHealingWorkspace
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Operations, Core
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: roxanad
ms.search.validFrom: 2017-12-01
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 943239c7d57b4a438c405f1ad0551db29d7a8145
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="create-rules-for-optimization-advisor"></a>Créer des règles pour le Conseiller en optimisation

[!INCLUDE [banner](../includes/banner.md)]

Cette rubrique explique comment créer des règles pour le **Conseiller en optimisation**. Par exemple, vous pouvez créer une règle qui identifie les dossiers d'appels d'offre qui ont un titre vide. L'attribution de titres aux dossiers facilite leur identification et leur recherche. Tout en étant relativement simple, cet exemple montre ce qu'il est possible de réaliser avec les règles d'optimisation. 

Une *règle* est une vérification des données d'application. Si la condition évaluée par la règle est remplie, les opportunités d'optimisation des processus ou d'amélioration des données sont créées. Les opportunités peuvent être mises en œuvre et, éventuellement, l'impact des actions peut être mesuré. 

Pour créer une règle pour le **Conseiller en optimisation**, ajoutez une nouvelle classe qui étend la classe abstraite **SelfHealingRule**, implémente l'interface **IDiagnosticsRule** et est décorée par l'attribut **DiagnosticRule**. La classe doit également avoir une méthode décorée avec l'attribut **DiagnosticsRuleSubscription**. Par convention, on utilise la méthode **opportunityTitle**, qui sera présentée ultérieurement. Cette nouvelle classe peut être ajoutée à un modèle personnalisé avec une dépendance sur le modèle **SelfHealingRules**. Dans l'exemple suivant, la règle implémentée est appelée **RFQTitleSelfHealingRule**.

```
[DiagnosticsRule] 
public final class RFQTitleSelfHealingRule extends SelfHealingRule implements IDiagnosticsRule 
{ 
… 
} 
```

La classe abstraite **SelfHealingRule** a des méthodes abstraites qui doivent être implémentées dans les classes héritantes. Le noyau est la méthode **evaluate**, qui retourne la liste des opportunités identifiées par la règle. Les opportunités peuvent être créées par entité juridique ou peuvent s'appliquer à l'ensemble du système.

```
protected List evaluate() 
{ 
    List results = new List(Types::Record); 
    
    DataArea dataArea; 

    while select id from dataArea 
        where !dataArea.isVirtual 
    { 
        changecompany(dataArea.id) 
        { 
            container result = this.findRFQCasesWithEmptyTitle(); 

            if (conLen(result) > 0) 
            { 
                SelfHealingOpportunity opportunity = this.getOpportunityForCompany(dataArea.Id); 
                opportunity.EvaluationState = SelfHealingEvaluationState::Evaluated; 
                opportunity.Data = result; 
                opportunity.OpportunityDate = DateTimeUtil::utcNow(); 
                
                results.addEnd(opportunity); 
            } 
        } 
    } 
    
    return results; 
} 
```

La méthode indiquée ci-dessus parcourt les sociétés et sélectionne les dossiers d'appel d'offre avec des titres vides dans la méthode **findRFQCasesWithEmptyTitle**. Si au moins un dossier est trouvé, une opportunité spécifique à la société est créée avec la méthode **getOpportunityForCompany**. Notez que le champ **Données** de la table **SelfHealingOpportunity** est de type **Conteneur**, et peut donc contenir des données se rapportant à la logique spécifique à cette règle. Le paramètre **OpportunityDate** avec l'horodatage actuel enregistre l'heure de la dernière évaluation de l'opportunité.  

Les opportunités peuvent également être créées entre des sociétés. Dans ce cas, il n'est pas nécessaire de parcourir les sociétés et l'opportunité doit être créée avec la méthode **getOpportunityAcrossCompanies**. 

Le code suivant affiche la méthode **findRFQCasesWithEmptyTitle**, qui retourne les ID des dossiers d'appel d'offre qui ont des titres vides.

```
private container findRFQCasesWithEmptyTitle() 
{ 
    container result; 

    PurchRFQCaseTable rfqCase; 
    while select RFQCaseId from rfqCase 
        where rfqCase.Name == '' 
    { 
        result += rfqCase.RFQCaseId; 
    } 
    
    return result; 
} 
```

Les deux autres méthodes devant être implémentées sont **opportunityTitle** et **opportunityDetails**. La première retourne un titre court pour l'opportunité, la dernière retourne une description détaillée de l'opportunité, qui peut également inclure des données.

Le titre retourné par la méthode **opportunityTitle** s'affiche sous la colonne **Opportunité d'optimisation** dans l'espace de travail **Conseiller en optimisation**. Il s'affiche également comme en-tête du volet latéral et donne des informations supplémentaires sur l'opportunité. Par convention, cette méthode est décorée avec l'attribut **DiagnosticRuleSubscription**, qui accepte les arguments suivants : 

* **Zone de diagnostic** – Énumération de type **DiagnosticArea** qui décrit la zone de l'application à laquelle la règle appartient, par exemple **DiagnosticArea::SCM**. 

* **Nom de la règle** – Chaîne contenant le nom de la règle. Elle s'affiche sous la colonne **Nom de la règle** de l'écran **Règle de validation de diagnostic** (**DiagnosticsValidationRuleMaintain**). 

* **Fréquence d'exécution** – Énumération de type **DiagnosticRunFrequency** qui décrit la fréquence d'exécution de la règle, par exemple **DiagnosticRunFrequency::Daily**. 

* **Description de la règle** – Chaîne contenant une description plus détaillée de la règle. Elle s'affiche sous la colonne **Description de la règle** de l'écran **Règle de validation de diagnostic** (**DiagnosticsValidationRuleMaintain**). 

> [!NOTE]
> L'attribut **DiagnosticRuleSubscription** est requis pour le bon fonctionnement de la règle. Généralement, il est utilisé dans la méthode **opportunityTitle**, mais il peut décorer n'importe quelle méthode de la classe.

Vous trouverez ci-dessous un exemple d'implémentation. Les chaînes brutes sont utilisées pour des raisons de simplicité, mais une implémentation correcte nécessite des étiquettes. 

```
[DiagnosticsRuleSubscription(DiagnosticsArea::SCM, 
                             'Assign titles to Request for Quotation cases', 
                             DiagnosticsRunFrequency::Daily,  
                             'This rule detects Requests for Quotation with empty titles.')] 
public str opportunityTitle() 
{ 
    return 'Assign titles to Request for Quotation cases'; 
} 
```

La description retournée par la méthode **opportunityDetails** s'affiche dans le volet latéral et donne des informations supplémentaires sur l'opportunité. Elle accepte l'argument **SelfHealingOpportunity**, qui correspond au champ **Données** permettant de fournir d'autres détails sur l'opportunité. Dans l'exemple, la méthode retourne les ID des dossiers d'appel d'offre qui ont un titre vide. 

```
public str opportunityDetails(SelfHealingOpportunity _opportunity) 
{ 
    str details = ''; 
    container opportunityData = _opportunity.Data; 
    int affectedRFQCasesCount = conLen(opportunityData); 

    if (affectedRFQCasesCount != 0) 
    { 
        details = 'The following Request for Quotation cases have an empty title:\n'; 
        for (int i = 1; i <= affectedRFQCasesCount ; i++) 
        { 
            PurchRFQCaseId rfqCaseId = conPeek(opportunityData, i); 
            details += rfqCaseId + '\n'; 
        } 
    } 

    return details; 
}
```

Les deux méthodes abstraites restantes à implémenter sont **provideHealingAction** et **securityMenuItem**. 

La méthode **provideHealingAction** retourne true si une action corrective est indiquée ; sinon, elle retourne false. Si la valeur true est retournée, la méthode **performAction** doit être implémentée, ou une erreur est générée. La méthode **performAction** accepte un argument **SelfHealingOpportunity**, dans lequel les données peuvent être utilisées pour l'action. Dans l'exemple, l'action ouvre **PurchRFQCaseTableListPage** pour la correction manuelle. 

```
public boolean providesHealingAction() 
{ 
    return true; 
} 

protected void performAction(SelfHealingOpportunity _opportunity) 
{ 
    new MenuFunction(menuItemDisplayStr(PurchRFQCaseTableListPage), MenuItemType::Display).run(); 
} 
```

Selon les détails de la règle, il est possible d'effectuer une action automatique à l'aide des données de l'opportunité. Dans cet exemple, le système peut générer automatiquement des titres pour les dossiers d'appel d'offre. 

La méthode **securityMenuItem** retourne le nom d'une option du menu Action de sorte que la règle n'est visible que par les utilisateurs qui peuvent accéder à l'option du menu Action. La sécurité peut nécessiter que des règles et opportunités spécifiques ne soient accessibles qu'aux utilisateurs autorisés. Dans l'exemple, seuls les utilisateurs qui ont accès à **PurchRFQCaseTitleAction** peuvent afficher l'opportunité. Notez que cette option du menu Action a été créée pour cet exemple, et a été ajoutée comme point d'entrée pour le privilège de sécurité **PurchRFQCaseTableMaintain**. 

> [!NOTE]
> L'option de menu doit être une option de menu Actions pour que la sécurité fonctionne correctement. Les autres types d'option de menu, tels que **Options de menu d'affichage** ne fonctionneront pas correctement.

```
public MenuName securityMenuItem() 
{ 
    return menuItemActionStr(PurchRFQCaseTitleAction); 
}
```

Une fois que la règle a été compilée, exécutez la tâche suivante pour la faire apparaître dans l'interface utilisateur.

```
class ScanNewRulesJob 
{         
    public static void main(Args _args) 
    {         
        SysExtensionCache::clearAllScopes(); 
        var controller = new DiagnosticsRuleController(); 
        controller.runOperation(); 
    } 
} 
```

La règle s'affiche dans l'écran **Règle de validation de diagnostic**, accessible sous **Administration du système** > **Tâches périodiques** > **Mettre à jour la règle de validation de diagnostic**. Pour la faire évaluer, accédez à **Administration du système** > **Tâches périodiques** > **Planifier la règle de validation de diagnostic**, sélectionnez la fréquence de la règle, par exemple **Quotidien**. Cliquez sur **OK**. Accédez à **Administration du système** > **Conseiller en optimisation** pour afficher la nouvelle opportunité. 

L'exemple ci-dessous est un extrait de code avec le squelette d'une règle incluant les méthodes et attributs exigés. Il vous permettra de commencer à écrire de nouvelles règles. Les étiquettes et options de menu Actions utilisées dans l'exemple sont uniquement utilisées à des fins de démonstration.

```
[DiagnosticsRuleAttribute]
public final class SkeletonSelfHealingRule extends SelfHealingRule implements IDiagnosticsRule
{
    [DiagnosticsRuleSubscription(DiagnosticsArea::SCM,
                                 "@SkeletonRuleLabels:SkeletonRuleTitle", // Label with the title of the rule
                                 DiagnosticsRunFrequency::Monthly,
                                 "@SkeletonRuleLabels:SkeletonRuleDescription")] // Label with a description of the rule
    public str opportunityTitle()
    {
        // Return a label with the title of the opportunity
        return "@SkeletonRuleLabels:SkeletonOpportunityTitle";
    }

    public str opportunityDetails(SelfHealingOpportunity _opportunity)
    {
        str details = "";

        // Use _opportunity.data to provide details on the opportunity

        return details;
    }

    protected List evaluate()
    {
        List results = new List(Types::Record);

        // Write here the core logic of the rule

        // When creating an opportunity, use:
        //     * this.getOpportunityForCompany() for company specific opportunities
        //     * this.getOpportunityAcrossCompanies() for cross-company opportunities

        return results;
    }

    public boolean providesHealingAction()
    {
        return true;
    }

    protected void performAction(SelfHealingOpportunity _opportunity)
    {
        // Place here the code that performs the healing action

        // To open a form, use the following:
        // new MenuFunction(menuItemDisplayStr(SkeletonRuleDisplayMenuItem), MenuItemType::Display).run();
    }

    public MenuName securityMenuItem()
    {
        return menuItemActionStr(SkeletonRuleActionMenuItem);
    }

}
```

Pour plus d'informations, visionnez la courte vidéo YouTube :

> [!Video https://www.youtube.com/embed/MRsAzgFCUSQ]

