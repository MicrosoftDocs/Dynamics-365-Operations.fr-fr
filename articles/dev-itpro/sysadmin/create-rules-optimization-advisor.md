---
title: Créer des règles pour le Conseiller en optimisation
description: Cette rubrique décrit comment ajouter de nouvelles règles au Conseiller en optimisation.
author: roxanadiaconu
manager: AnnBe
ms.date: 02/04/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SelfHealingWorkspace
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Operations, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: roxanad
ms.search.validFrom: 2017-12-01
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: ca73120a5a0da4dc348c2d16dca8e7654876af5d
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570289"
---
# <a name="create-rules-for-optimization-advisor"></a><span data-ttu-id="2b63e-103">Créer des règles pour le Conseiller en optimisation</span><span class="sxs-lookup"><span data-stu-id="2b63e-103">Create rules for Optimization advisor</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2b63e-104">Cette rubrique explique comment créer des règles pour le **Conseiller en optimisation**.</span><span class="sxs-lookup"><span data-stu-id="2b63e-104">This topic explains how to create new rules for **Optimization advisor**.</span></span> <span data-ttu-id="2b63e-105">Par exemple, vous pouvez créer une règle qui identifie les dossiers d'appels d'offre qui ont un titre vide.</span><span class="sxs-lookup"><span data-stu-id="2b63e-105">For example, you can create a new rule that identifies which Request for Quotations (RFQ) cases have an empty title.</span></span> <span data-ttu-id="2b63e-106">L'attribution de titres aux dossiers facilite leur identification et leur recherche.</span><span class="sxs-lookup"><span data-stu-id="2b63e-106">Using titles on cases makes them easily identifiable and searchable.</span></span> <span data-ttu-id="2b63e-107">Tout en étant relativement simple, cet exemple montre ce qu'il est possible de réaliser avec les règles d'optimisation.</span><span class="sxs-lookup"><span data-stu-id="2b63e-107">While quite simple, this example shows what can be achieved with optimization rules.</span></span> 

<span data-ttu-id="2b63e-108">Une *règle* est une vérification des données d'application.</span><span class="sxs-lookup"><span data-stu-id="2b63e-108">A *rule* is a check on application data.</span></span> <span data-ttu-id="2b63e-109">Si la condition évaluée par la règle est remplie, les opportunités d'optimisation des processus ou d'amélioration des données sont créées.</span><span class="sxs-lookup"><span data-stu-id="2b63e-109">If the condition that the rule evaluates is met, opportunities to optimize processes or improve data are created.</span></span> <span data-ttu-id="2b63e-110">Les opportunités peuvent être mises en œuvre et, éventuellement, l'impact des actions peut être mesuré.</span><span class="sxs-lookup"><span data-stu-id="2b63e-110">The opportunities can be acted upon and, optionally, the impact of the actions can be measured.</span></span> 

<span data-ttu-id="2b63e-111">Pour créer une règle pour le **Conseiller en optimisation**, ajoutez une nouvelle classe qui étend la classe abstraite **SelfHealingRule**, implémente l'interface **IDiagnosticsRule** et est décorée par l'attribut **DiagnosticRule**.</span><span class="sxs-lookup"><span data-stu-id="2b63e-111">To create a new rule for the **Optimization advisor**, add a new class that extends the **SelfHealingRule** abstract class, implements the **IDiagnosticsRule** interface, and is decorated by the **DiagnosticRule** attribute.</span></span> <span data-ttu-id="2b63e-112">La classe doit également avoir une méthode décorée avec l'attribut **DiagnosticsRuleSubscription**.</span><span class="sxs-lookup"><span data-stu-id="2b63e-112">The class must also have a method decorated with the **DiagnosticsRuleSubscription** attribute.</span></span> <span data-ttu-id="2b63e-113">Par convention, on utilise la méthode **opportunityTitle**, qui sera présentée ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="2b63e-113">By convention, that is done on the **opportunityTitle** method, which will be discussed later.</span></span> <span data-ttu-id="2b63e-114">Cette nouvelle classe peut être ajoutée à un modèle personnalisé avec une dépendance sur le modèle **SelfHealingRules**.</span><span class="sxs-lookup"><span data-stu-id="2b63e-114">This new class can be added to a custom model with a dependency on the **SelfHealingRules** model.</span></span> <span data-ttu-id="2b63e-115">Dans l'exemple suivant, la règle implémentée est appelée **RFQTitleSelfHealingRule**.</span><span class="sxs-lookup"><span data-stu-id="2b63e-115">In the following example, the rule being implemented is called **RFQTitleSelfHealingRule**.</span></span>

```
[DiagnosticsRule] 
public final class RFQTitleSelfHealingRule extends SelfHealingRule implements IDiagnosticsRule 
{ 
… 
} 
```

<span data-ttu-id="2b63e-116">La classe abstraite **SelfHealingRule** a des méthodes abstraites qui doivent être implémentées dans les classes héritantes.</span><span class="sxs-lookup"><span data-stu-id="2b63e-116">The **SelfHealingRule** abstract class has abstract methods that must be implemented in inheriting classes.</span></span> <span data-ttu-id="2b63e-117">Le noyau est la méthode **evaluate**, qui retourne la liste des opportunités identifiées par la règle.</span><span class="sxs-lookup"><span data-stu-id="2b63e-117">The core is the **evaluate** method, which returns a list of the opportunities identified by the rule.</span></span> <span data-ttu-id="2b63e-118">Les opportunités peuvent être créées par entité juridique ou peuvent s'appliquer à l'ensemble du système.</span><span class="sxs-lookup"><span data-stu-id="2b63e-118">Opportunities can be per legal entity or can apply to the whole system.</span></span>

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

<span data-ttu-id="2b63e-119">La méthode indiquée ci-dessus parcourt les sociétés et sélectionne les dossiers d'appel d'offre avec des titres vides dans la méthode **findRFQCasesWithEmptyTitle**.</span><span class="sxs-lookup"><span data-stu-id="2b63e-119">The method shown above loops over companies and selects RFQ cases with empty titles in the **findRFQCasesWithEmptyTitle** method.</span></span> <span data-ttu-id="2b63e-120">Si au moins un dossier est trouvé, une opportunité spécifique à la société est créée avec la méthode **getOpportunityForCompany**.</span><span class="sxs-lookup"><span data-stu-id="2b63e-120">If at least one such case is found, then a company-specific opportunity is created with the **getOpportunityForCompany** method.</span></span> <span data-ttu-id="2b63e-121">Notez que le champ **Données** de la table **SelfHealingOpportunity** est de type **Conteneur**, et peut donc contenir des données se rapportant à la logique spécifique à cette règle.</span><span class="sxs-lookup"><span data-stu-id="2b63e-121">Notice that the field **Data** in the **SelfHealingOpportunity** table is of type **Container**, and can therefore contain any data relevant to the logic specific to this rule.</span></span> <span data-ttu-id="2b63e-122">Le paramètre **OpportunityDate** avec l'horodatage actuel enregistre l'heure de la dernière évaluation de l'opportunité.</span><span class="sxs-lookup"><span data-stu-id="2b63e-122">Setting **OpportunityDate** with the current timestamp registers the time of the latest evaluation of the opportunity.</span></span>  

<span data-ttu-id="2b63e-123">Les opportunités peuvent également être créées entre des sociétés.</span><span class="sxs-lookup"><span data-stu-id="2b63e-123">Opportunities can also be cross-company.</span></span> <span data-ttu-id="2b63e-124">Dans ce cas, il n'est pas nécessaire de parcourir les sociétés et l'opportunité doit être créée avec la méthode **getOpportunityAcrossCompanies**.</span><span class="sxs-lookup"><span data-stu-id="2b63e-124">In this case, the loop over companies is not necessary and the opportunity must be created with the **getOpportunityAcrossCompanies** method.</span></span> 

<span data-ttu-id="2b63e-125">Le code suivant affiche la méthode **findRFQCasesWithEmptyTitle**, qui retourne les ID des dossiers d'appel d'offre qui ont des titres vides.</span><span class="sxs-lookup"><span data-stu-id="2b63e-125">The following code shows the **findRFQCasesWithEmptyTitle** method, which returns the IDs of the RFQ cases that have empty titles.</span></span>

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

<span data-ttu-id="2b63e-126">Les deux autres méthodes devant être implémentées sont **opportunityTitle** et **opportunityDetails**.</span><span class="sxs-lookup"><span data-stu-id="2b63e-126">Two more methods that must be implemented are **opportunityTitle** and **opportunityDetails**.</span></span> <span data-ttu-id="2b63e-127">La première retourne un titre court pour l'opportunité, la dernière retourne une description détaillée de l'opportunité, qui peut également inclure des données.</span><span class="sxs-lookup"><span data-stu-id="2b63e-127">The former returns a short title for the opportunity, the latter returns a detailed description of the opportunity, which can also include data.</span></span>

<span data-ttu-id="2b63e-128">Le titre retourné par la méthode **opportunityTitle** s'affiche sous la colonne **Opportunité d'optimisation** dans l'espace de travail **Conseiller en optimisation**.</span><span class="sxs-lookup"><span data-stu-id="2b63e-128">The title returned by **opportunityTitle** appears under the **Optimization opportunity** column in the **Optimization advisor** workspace.</span></span> <span data-ttu-id="2b63e-129">Il s'affiche également comme en-tête du volet latéral et donne des informations supplémentaires sur l'opportunité.</span><span class="sxs-lookup"><span data-stu-id="2b63e-129">It also appears as the header of the side pane showing more information about the opportunity.</span></span> <span data-ttu-id="2b63e-130">Par convention, cette méthode est décorée avec l'attribut **DiagnosticRuleSubscription**, qui accepte les arguments suivants :</span><span class="sxs-lookup"><span data-stu-id="2b63e-130">By convention, this method is decorated with the **DiagnosticRuleSubscription** attribute, which takes the following arguments:</span></span> 

* <span data-ttu-id="2b63e-131">**Zone de diagnostic** – Énumération de type **DiagnosticArea** qui décrit la zone de l'application à laquelle la règle appartient, par exemple **DiagnosticArea::SCM**.</span><span class="sxs-lookup"><span data-stu-id="2b63e-131">**Diagnostic area** – An enum of type **DiagnosticArea** that describes what area of the application the rule belongs to, such as **DiagnosticArea::SCM**.</span></span> 

* <span data-ttu-id="2b63e-132">**Nom de la règle** – Chaîne contenant le nom de la règle.</span><span class="sxs-lookup"><span data-stu-id="2b63e-132">**Rule name** – A string with the rule name.</span></span> <span data-ttu-id="2b63e-133">Elle s'affiche sous la colonne **Nom de la règle** de l'écran **Règle de validation de diagnostic** (**DiagnosticsValidationRuleMaintain**).</span><span class="sxs-lookup"><span data-stu-id="2b63e-133">This will appear under the **Rule name** column in the **Dianostics validation rule** form (**DiagnosticsValidationRuleMaintain**).</span></span> 

* <span data-ttu-id="2b63e-134">**Fréquence d'exécution** – Énumération de type **DiagnosticRunFrequency** qui décrit la fréquence d'exécution de la règle, par exemple **DiagnosticRunFrequency::Daily**.</span><span class="sxs-lookup"><span data-stu-id="2b63e-134">**Run frequency** – An enum of type **DiagnosticRunFrequency** that describes how often the rule should be run, such as **DiagnosticRunFrequency::Daily**.</span></span> 

* <span data-ttu-id="2b63e-135">**Description de la règle** – Chaîne contenant une description plus détaillée de la règle.</span><span class="sxs-lookup"><span data-stu-id="2b63e-135">**Rule description** – A string with a more detailed description of the rule.</span></span> <span data-ttu-id="2b63e-136">Elle s'affiche sous la colonne **Description de la règle** de l'écran **Règle de validation de diagnostic** (**DiagnosticsValidationRuleMaintain**).</span><span class="sxs-lookup"><span data-stu-id="2b63e-136">This will appear under the **Rule description** column in the **Dianostics validation rule** form (**DiagnosticsValidationRuleMaintain**).</span></span> 

> [!NOTE]
> <span data-ttu-id="2b63e-137">L'attribut **DiagnosticRuleSubscription** est requis pour le bon fonctionnement de la règle.</span><span class="sxs-lookup"><span data-stu-id="2b63e-137">The **DiagnosticRuleSubscription** attribute is required for the rule to work.</span></span> <span data-ttu-id="2b63e-138">Généralement, il est utilisé dans la méthode **opportunityTitle**, mais il peut décorer n'importe quelle méthode de la classe.</span><span class="sxs-lookup"><span data-stu-id="2b63e-138">Typically, it is used on **opportunityTitle**, but it can decorate any method of the class.</span></span>

<span data-ttu-id="2b63e-139">Vous trouverez ci-dessous un exemple d'implémentation.</span><span class="sxs-lookup"><span data-stu-id="2b63e-139">The following is an example implementation.</span></span> <span data-ttu-id="2b63e-140">Les chaînes brutes sont utilisées pour des raisons de simplicité, mais une implémentation correcte nécessite des étiquettes.</span><span class="sxs-lookup"><span data-stu-id="2b63e-140">Raw strings are used for simplicity, but a correct implementation requires labels.</span></span> 

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

<span data-ttu-id="2b63e-141">La description retournée par la méthode **opportunityDetails** s'affiche dans le volet latéral et donne des informations supplémentaires sur l'opportunité.</span><span class="sxs-lookup"><span data-stu-id="2b63e-141">The description returned by **opportunityDetails** appears on the side pane showing more information about the opportunity.</span></span> <span data-ttu-id="2b63e-142">Elle accepte l'argument **SelfHealingOpportunity**, qui correspond au champ **Données** permettant de fournir d'autres détails sur l'opportunité.</span><span class="sxs-lookup"><span data-stu-id="2b63e-142">This takes the **SelfHealingOpportunity** argument, which is **Data** field that can be used to provide more details about the opportunity.</span></span> <span data-ttu-id="2b63e-143">Dans l'exemple, la méthode retourne les ID des dossiers d'appel d'offre qui ont un titre vide.</span><span class="sxs-lookup"><span data-stu-id="2b63e-143">In the example, the method returns the IDs of the RFQ cases with an empty title.</span></span> 

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

<span data-ttu-id="2b63e-144">Les deux méthodes abstraites restantes à implémenter sont **provideHealingAction** et **securityMenuItem**.</span><span class="sxs-lookup"><span data-stu-id="2b63e-144">The two remaining abstract methods to implement are **provideHealingAction** and **securityMenuItem**.</span></span> 

<span data-ttu-id="2b63e-145">La méthode **provideHealingAction** retourne true si une action corrective est indiquée ; sinon, elle retourne false.</span><span class="sxs-lookup"><span data-stu-id="2b63e-145">**provideHealingAction** returns true if a healing action is provided, otherwise, it returns false.</span></span> <span data-ttu-id="2b63e-146">Si la valeur true est retournée, la méthode **performAction** doit être implémentée, ou une erreur est générée.</span><span class="sxs-lookup"><span data-stu-id="2b63e-146">If true is returned, the method **performAction** must be implemented, or an error will be thrown.</span></span> <span data-ttu-id="2b63e-147">La méthode **performAction** accepte un argument **SelfHealingOpportunity**, dans lequel les données peuvent être utilisées pour l'action.</span><span class="sxs-lookup"><span data-stu-id="2b63e-147">The **performAction** method takes a **SelfHealingOpportunity** argument, in which the data can be used for the action.</span></span> <span data-ttu-id="2b63e-148">Dans l'exemple, l'action ouvre **PurchRFQCaseTableListPage** pour la correction manuelle.</span><span class="sxs-lookup"><span data-stu-id="2b63e-148">In the example, the action opens the **PurchRFQCaseTableListPage**, for manual correction.</span></span> 

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

<span data-ttu-id="2b63e-149">Selon les détails de la règle, il est possible d'effectuer une action automatique à l'aide des données de l'opportunité.</span><span class="sxs-lookup"><span data-stu-id="2b63e-149">Depending on the specifics of the rule, it might be possible to take an automatic action using the opportunity data.</span></span> <span data-ttu-id="2b63e-150">Dans cet exemple, le système peut générer automatiquement des titres pour les dossiers d'appel d'offre.</span><span class="sxs-lookup"><span data-stu-id="2b63e-150">In this example, the system could generate titles for RFQ cases automatically.</span></span> 

<span data-ttu-id="2b63e-151">La méthode **securityMenuItem** retourne le nom d'une option du menu Action de sorte que la règle n'est visible que par les utilisateurs qui peuvent accéder à l'option du menu Action.</span><span class="sxs-lookup"><span data-stu-id="2b63e-151">**securityMenuItem** returns the name of an action menu item such that the rule is only visible to users who can access the action menu item.</span></span> <span data-ttu-id="2b63e-152">La sécurité peut nécessiter que des règles et opportunités spécifiques ne soient accessibles qu'aux utilisateurs autorisés.</span><span class="sxs-lookup"><span data-stu-id="2b63e-152">Security might require that specific rules and opportunities are accessible only to authorized users.</span></span> <span data-ttu-id="2b63e-153">Dans l'exemple, seuls les utilisateurs qui ont accès à **PurchRFQCaseTitleAction** peuvent afficher l'opportunité.</span><span class="sxs-lookup"><span data-stu-id="2b63e-153">In the example, only users with access to **PurchRFQCaseTitleAction** can view the opportunity.</span></span> <span data-ttu-id="2b63e-154">Notez que cette option du menu Action a été créée pour cet exemple, et a été ajoutée comme point d'entrée pour le privilège de sécurité **PurchRFQCaseTableMaintain**.</span><span class="sxs-lookup"><span data-stu-id="2b63e-154">Notice that this action menu item was created for this example, and was added as an entry point for the **PurchRFQCaseTableMaintain** security privilege.</span></span> 

> [!NOTE]
> <span data-ttu-id="2b63e-155">L'option de menu doit être une option de menu Actions pour que la sécurité fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="2b63e-155">The menu item must be an action menu item for security to work correctly.</span></span> <span data-ttu-id="2b63e-156">Les autres types d'option de menu, tels que **Options de menu d'affichage** ne fonctionneront pas correctement.</span><span class="sxs-lookup"><span data-stu-id="2b63e-156">Other menu item types, such as **Display menu items** will not work correctly.</span></span>

```
public MenuName securityMenuItem() 
{ 
    return menuItemActionStr(PurchRFQCaseTitleAction); 
}
```

<span data-ttu-id="2b63e-157">Une fois que la règle a été compilée, exécutez la tâche suivante pour la faire apparaître dans l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2b63e-157">After the rule has compiled, execute the following job to have it display in the user interface (UI).</span></span>

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

<span data-ttu-id="2b63e-158">La règle s'affiche dans l'écran **Règle de validation de diagnostic**, accessible sous **Administration du système** > **Tâches périodiques** > **Mettre à jour la règle de validation de diagnostic**.</span><span class="sxs-lookup"><span data-stu-id="2b63e-158">The rule will display in the **Diagnostics validation rule** form, available from **System administration** > **Periodic tasks** > **Maintain diagnostics validation rule**.</span></span> <span data-ttu-id="2b63e-159">Pour la faire évaluer, accédez à **Administration du système** > **Tâches périodiques** > **Planifier la règle de validation de diagnostic**, sélectionnez la fréquence de la règle, par exemple **Quotidien**.</span><span class="sxs-lookup"><span data-stu-id="2b63e-159">To have it evaluated, go to **System administration** > **Periodic tasks** > **Schedule diagnostics validation rule**, select the frequency of the rule, such as **Daily**.</span></span> <span data-ttu-id="2b63e-160">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b63e-160">Click **OK**.</span></span> <span data-ttu-id="2b63e-161">Accédez à **Administration du système** > **Conseiller en optimisation** pour afficher la nouvelle opportunité.</span><span class="sxs-lookup"><span data-stu-id="2b63e-161">Go to **System administration** > **Optimization advisor** to view the new opportunity.</span></span> 

<span data-ttu-id="2b63e-162">L'exemple ci-dessous est un extrait de code avec le squelette d'une règle incluant les méthodes et attributs exigés.</span><span class="sxs-lookup"><span data-stu-id="2b63e-162">The following example is a code snippet with the skeleton of a rule including all the required methods and attributes.</span></span> <span data-ttu-id="2b63e-163">Il vous permettra de commencer à écrire de nouvelles règles.</span><span class="sxs-lookup"><span data-stu-id="2b63e-163">It helps you get started with writing new rules.</span></span><span data-ttu-id="2b63e-164"> Les étiquettes et options de menu Actions utilisées dans l'exemple sont uniquement utilisées à des fins de démonstration.</span><span class="sxs-lookup"><span data-stu-id="2b63e-164"> The labels and action menu items that are used in the example are only used for demonstration purpose.</span></span>

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

<span data-ttu-id="2b63e-165">Pour plus d'informations, consultez la brève vidéo YouTube : [Conseiller en optimisation dans Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=MRsAzgFCUSQ)</span><span class="sxs-lookup"><span data-stu-id="2b63e-165">For more information, watch the short YouTube video: [Optimization advisor in Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=MRsAzgFCUSQ)</span></span>
