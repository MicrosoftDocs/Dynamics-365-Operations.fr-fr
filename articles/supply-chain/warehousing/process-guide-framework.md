---
title: Structure du guide de traitement
description: Cet article fournit des informations sur le framework de guide de processus pour les développeurs qui étendent nos processus mobiles d'entrepôt dans X++.
author: Mirzaab
ms.date: 11/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: e88f32e0347a808d03615cf85e50b1592d691670
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860433"
---
# <a name="process-guide-framework"></a>Structure du guide de traitement

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur le framework de guide de processus pour les développeurs qui étendent les processus mobiles d'entrepôt dans X++. Les processus mobiles de l'entrepôt sont extensibles car les processus sont divisés en petites étapes. La logique métier et la création de l'interface utilisateur de chaque étape ont été extraites en classes individuelles, ce qui permet une extensibilité.

## <a name="overview-of-the-existing-design"></a>Aperçu de la conception existante

Les flux d'exécution mobiles de l'entrepôt sont exposés via un seul point de terminaison de service personnalisé. La requête arrive de l'application mobile sous la forme d'une chaîne XML, qui contient les métadonnées de l'interface utilisateur présentées dans l'application mobile, ainsi que les valeurs saisies par l'utilisateur.

Lorsque la demande est reçue, la première étape consiste à désérialiser ce XML. La classe **WHSMobileAppServiceXMLTranslator** convertit le XML en un conteneur, qui contient à la fois des informations de contrôle et des informations de session.

Ensuite, les informations contenues dans le conteneur sont utilisées pour déduire sur quel processus d'entrepôt l'utilisateur travaille ou est sur le point de démarrer (représenté par l'énumération **WHSWorkExecuteMode**), et en conséquence instancier une classe dérivée de **WHSWorkExecuteDisplay**. La méthode **displayform()** est invoquée, qui effectue ensuite les opérations suivantes :

-   Traite les données de l'utilisateur (déléguées à la classe **WHSRFControlData**, mais certains processus implémentent une logique spécifique en remplaçant la méthode **processControl()**).

-   Exécute la logique métier.

-   Incrémente l'étape.

-   Crée le conteneur représentant la nouvelle interface utilisateur (généralement dans une méthode **build…()**).

Le conteneur est ensuite renvoyé au traducteur, qui sérialise ensuite le XML et le renvoie en réponse à l'appareil mobile.

Le diagramme de séquence suivant montre une vue d'ensemble du flux d'exécution. Notez que le diagramme est plus une vue d'ensemble schématique et n'est pas une représentation 1:1 du code réel.

![Vue d’ensemble schématique du processus.](media/schematic-overview.png) 

### <a name="reason-for-the-redesign"></a>Motif de reconception

La conception ci-dessus offre un cadre très simple pour la création de processus utilisés dans les flux mobiles. Cependant, comme on le voit ci-dessus, les méthodes **displayform()** assument de multiples responsabilités. Il les délègue à d'autres méthodes et classes, mais en l'absence de responsabilités de classe concrètes, cela se fait de manière incohérente entre les classes. De plus, à mesure que le nombre de scénarios pris en charge augmente de manière organique, certaines de ces classes peuvent devenir assez complexes. Pour rendre les choses plus intéressantes, certaines de ces classes/méthodes sont remplacées et réutilisées dans plusieurs modes. Le résultat est des méthodes extrêmement longues avec une complexité cyclomatique élevée. Ceux-ci ont posé des problèmes de maintenance dans le passé. La correction des bogues dans ces méthodes a été risquée et sujette à la régression.
Par exemple, la méthode **processWorkLine()** dans la classe **WhsWorkExecuteDisplay** est référencée à partir de plusieurs processus (essentiellement, partout où l'exécution du travail est effectuée).

Pour les rendre extensibles, l'une des options serait de diviser les méthodes **displayForm** en méthodes plus petites et d'introduire des points d'extensibilité. Cependant, en raison de la matrice de scénario, il serait difficile pour les partenaires d'écrire des extensions et de valider par rapport aux régressions. Non seulement cela, en raison de l'absence de répartition structurée des responsabilités mentionnée ci-dessus, le code continuerait de croître de manière imprévisible au fil du temps, ce qui poserait des défis dans la construction d'extensions de qualité.

En conséquence, la refonte est l'option durable, dans le but d'avoir des classes clairement définies ayant des responsabilités indépendantes. Une classe devrait avoir une responsabilité, une raison de changer et une raison d'être prolongée.

## <a name="design-overview"></a>Aperçu de la conception

Dans le cadre repensé, la stratégie de base s'articule autour de deux principes : diviser le flux d'exécution en composants individuels avec des responsabilités bien définies et avoir des points d'extension bien définis dans chacun des composants.

Le nom du nouveau cadre est "ProcessGuide". En effet, le but de ces classes est de guider un utilisateur à travers un processus métier (par opposition au client riche qui est une expérience basée sur un formulaire où l'utilisateur a plus de flexibilité dans la façon dont il interagit avec les données ou dans quel ordre il effectue les tâches).

> [!NOTE]
> Un détail notable est l'omission délibérée du préfixe "WHS". Alors que les processus mobiles ont été initialement introduits pour l'entreposage, ils ont par la suite transcendé les frontières pour prendre en charge divers processus de production et de gestion des stocks. De ce fait, la référence entrepôt a été exclue au nom du framework.

Pour identifier les composants, la première étape consiste à examiner le processus de démarrage de la production (classe **WhsWorkExecuteDisplayProdStart**). Voici un schéma du processus.

![Image d'un processus schématique.](media/production-start-process-schematic.png)

En ce qui concerne le flux de contrôle, les composants suivants sont nécessaires :

-   Un contrôleur pour coudre l'ensemble du processus métier.
-   Une étape responsable de l'exécution d'une étape du processus.
-   Un processeur de données pour traiter les données en une étape.
-   Un générateur de pages chargé de créer l'interface utilisateur d'une étape.
-   Un agent de navigation responsable de la transition d'étape.
-   Une classe responsable de l'exécution du processus métier.

Dans le diagramme de flux de processus ci-dessus, si vous commencez à l'étape 1 et commencez à traiter les données de l'étape précédente, puis terminez par la création d'une interface utilisateur, les données continueront à être traitées à l'étape suivante. Cela introduit un couplage étroit entre les étapes consécutives, par conséquent, notre nouveau schéma de haut niveau ressemblerait à ce qui suit :

![Image d'un processus schématique de haut niveau.](media/high-level-schematic.png)

Voici les éléments clés du processus repensé :

-   **ProcessGuideController** - Ce cours orchestre l'exécution globale du processus métier. Il définit les usines qui instancient l'étape et l'agent de navigation, qui constituent par la suite l'exécution du processus, ainsi que la logique de nettoyage pour l'annulation ou la sortie du processus.

-   **ProcessGuideStep** - Cette classe représente une seule étape du processus métier. Cette classe contient une définition des usines qui instancient un générateur de page, des actions et des processeurs de données et est chargée de les appeler dans le bon ordre.

-   **ProcessGuideNavigationAgent** - Cette classe est responsable de la navigation entre les étapes. Lorsqu'une étape est terminée, l'agent de navigation est chargé de définir l'étape suivante et passe tous les paramètres que l'étape précédente peut avoir besoin de communiquer à la suivante.

-   **ProcessGuidePageBuilder** - Cette classe est responsable de l'instanciation de l'interface utilisateur.

-   **ProcessGuideAction** - Cette classe représente une action, affichée sous forme de bouton pour l'utilisateur.

-   **ProcessGuideDataProcessor** - Cette classe est responsable du traitement des données saisies par l'utilisateur dans un champ.

## <a name="execution-flow"></a>Flux d’exécution

Le point de départ du flux d'exécution reste inchangé. Ainsi, la demande arrive toujours via les mêmes points de terminaison, suivie de la désérialisation du XML dans le conteneur. Ce conteneur est ensuite transmis à **getNextFormState()**.

Il y a trois classes importantes à noter :

-  **ProcessGuideSessionState** – Il contient les informations sur l'état de la session – mode, réussite, contrôleur et étape en cours d'exécution, etc.

-  **ProcessGuidePage** – Il contient une représentation fortement typée des métadonnées de l'interface utilisateur.

-  **ProcessGuideRequest** – Cela contient les deux ci-dessus en tant que membres et est une représentation fortement typée de la demande reçue de l'appareil mobile.

Ces classes sont créées à l'aide des informations du conteneur (données de contrôle saisies par l'état et par l'utilisateur). Cela fournit un moyen sûr d'accéder aux valeurs et de les manipuler. Par rapport aux accès répétés du conteneur au cours du processus, cela offre un avantage à la fois en termes de lisibilité et de performances.

Les informations sur l'état de la session sont utilisées pour instancier la classe **ProcessGuideController** correcte. Une fois instanciée, la méthode **createResponse()** dans la classe **ProcessGuideController** est invoquée. Cette méthode est le point d'entrée de la logique du guide de processus, et après exécution, revient avec la réponse (représentée dans la classe **ProcessGuideResponse**). La réponse est ensuite reconvertie dans le conteneur et remise à la logique héritée, qui la sérialise ensuite dans le XML et renvoie la réponse à l'appareil mobile.

Ensuite, le contrôleur doit trouver la prochaine étape à exécuter. S'il s'agit du début d'un nouveau processus, le contrôleur appellera **initialStep()** pour obtenir la première étape du processus. Après cela, il appellerait la méthode **execute()** dans **ProcessGuideStep**. Cette méthode instancierait alors une classe **ProcessGuidePageBuilder** et appellerait **buildPage()**, qui reviendrait avec un objet **ProcessGuidePage**, qui est une représentation virtuelle de l'interface utilisateur à présenter à l'utilisateur. L'étape renverrait ensuite le résultat au contrôleur, qui enregistrerait ensuite l'état de la session en cours, puis renverrait le résultat à **getNextFormState()** sous la forme de la classe **ProcessGuideResponse**. Par la suite, la réponse est reconvertie dans le conteneur, puis sérialisée en XML et renvoie la réponse à l'appareil mobile.

Le diagramme de séquence suivant explique ce flux de contrôle. Notez qu'il s'agit du flux de contrôle le plus courant, simplifié pour expliquer la conception.

![Flux de contrôle simplifié.](media/control-flow.png)

Lorsque l'utilisateur effectue une action sur l'appareil mobile en cliquant sur un bouton (ou en scannant une valeur - ce qui déclenche généralement l'action par défaut) - la demande arrive à la méthode **createResponse()** dans la classe **ProcessGuideController** par le même itinéraire. Cette fois, cependant, le contrôleur sait à partir des informations d'état de session dans quelle étape se trouve l'utilisateur. En conséquence, il instancie la classe **ProcessGuideStep** et invoque la méthode execute. **ProcessGuideStep**, à son tour, lit le nom de l'action invoquée par l'utilisateur, puis instancie la classe **ProcessGuideAction** et appelle **execute()**.

La classe **ProcessGuideAction** est responsable de l'exécution de l'action spécifique, mais il existe deux exceptions notables.

La première est la classe **ProcessGuideOKAction**. Cette action implique que l'utilisateur souhaite confirmer et avancer dans le processus. Conformément à cela - cette méthode fait en fait un rappel à la classe ProcessGuideStep, ce qui signifie que l'étape appelle **processData()** dans **ProcessGuideDataProcessor**. Cela traite les données que l'utilisateur a saisies, puis met à jour l'état de l'étape et renvoie le résultat au contrôleur. Selon le résultat du processeur, l'étape appelle le générateur de page pour créer l'interface utilisateur appropriée ou définit le statut de l'étape comme terminé. Cela se reflète dans la moitié supérieure du diagramme de séquence ci-dessous.

L'autre exception est l'action d'annulation, mise en œuvre dans les classes **ProcessGuideCancelResetProcessAction** et **ProcessGuideCancelExitProcessAction**. Ces actions représentent une intention d'annuler le processus et de revenir au début du processus ou de quitter complètement le processus. Semblable à l'action **OK**, ces actions effectuent également un rappel à l'étape, qui signale l'intention au **ProcessGuideController**. Le contrôleur effectue ensuite le nettoyage nécessaire des variables d'état et déplace le contrôle à l'étape initiale du processus ou termine complètement le processus.

Une fois l'étape terminée, si le statut de l'étape est défini sur **Terminé**, alors le contrôleur instancie le **ProcessGuideNavigationAgent**, qui renvoie le nom de l'étape suivante. Le contrôleur instancie ensuite cette étape et invoque la méthode **execute()** – et le cycle continue. Le plus souvent, la nouvelle étape invoque le **ProcessGuidePageBuilder** pour créer l'interface utilisateur pour le prochain écran à présenter à l'utilisateur, qui est ensuite renvoyé. Ce flux est représenté dans la moitié inférieure du diagramme de séquence ci-dessous.

![diagramme de séquence.](media/sequence-diagram.png)

## <a name="building-a-new-process-using-the-processguide-framework"></a>Créer un nouveau processus à l'aide du framework ProcessGuide

La meilleure façon d'expliquer le flux de contrôle consiste à utiliser un exemple existant dans l'application : le processus de démarrage de la production.

## <a name="overview-of-the-production-start-process"></a>Vue d'ensemble du processus de démarrage

Commençons par comprendre le flux de processus. Dans la première étape, l'utilisateur est invité à saisir l'ID de l'ordre de fabrication.

![Demander l'ID de production.](media/production-id-prompt.png)

Lorsque l'utilisateur saisit l'ID de l'ordre de fabrication, le numéro de commande est validé. Certaines des validations exécutées dépendent du fait que la commande se trouve dans le même entrepôt que celui auquel l'utilisateur est connecté et du statut de la commande. Si la validation échoue, l'utilisateur reçoit un message d'erreur. Si la validation réussit, l'utilisateur voit les détails de l'ordre de fabrication et de l'article.

L'utilisateur peut soit annuler pour revenir au début du processus, soit cliquer sur **OK** pour confirmer. Dans ce dernier cas, l'ordre de fabrication est défini sur le statut **Démarré**, les journaux correspondants sont affichés, le contrôle revient à la première étape et le message "Travail terminé" est affiché à l'utilisateur.


## <a name="creating-the-controller"></a>Création du contrôleur

La première étape de la construction du processus métier consiste à créer la classe de contrôleur, qui s'étend de la classe abstraite **ProcessGuideController** qui implémente les comportements par défaut d'un contrôleur. Le nouveau nom de classe est **ProdProcessGuideProductionStartController** et décoré de la valeur **WHSWorkExecuteMode** de **StartProdOrder**. La même instanciation **SysExtension** basée qui a été utilisée dans les classes **WHSWorkExecuteDisplay** est utilisée, ce qui permet d'instancier le contrôleur lorsque l'utilisateur exécute une option de menu pour ce mode.

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode::StartProdOrder)]
public class ProdProcessGuideProductionStartController extends ProcessGuideController
```

> [!NOTE]
> Le modèle de nommage de la classe est **\<FunctionalArea\>ProcessGuide\<Businessprocessname\>Controller**. C'est le modèle qui est utilisé pour les classes de contrôleurs et pour s'étendre à d'autres classes.


## <a name="building-the-first-step"></a>Créer la première étape

Ensuite, pour définir la première étape, vous créez la classe **ProdProcessGuidePromptProductionIdStep**, s'étendant à partir de **ProcessGuideStep**.

La tâche d'instanciation de la classe est déléguée à une fabrique d'étapes, qui est invoquée par la classe de base **ProcessGuideController**. L'implémentation par défaut de la fabrique instancie l'étape en fonction du nom. Par conséquent, pour instancier **ProdProcessGuidePromptProductionIdStep** comme première étape dans le contrôleur, vous devez faire deux choses :

-   Décorez la classe **ProdProcessGuidePromptProductionIdStep** avec un attribut **ProcessGuideStepName**.

    ```xpp
    [ProcessGuideStepName(classStr(ProdProcessGuidePromptProductionIdStep))] public class ProdProcessGuidePromptProductionIdStep extends ProcessGuideStep
    ```

-   Dans la classe du contrôleur, implémentez la méthode abstraite **initialStepName()** pour renvoyer le nom de l'étape.

    ```xpp
    protected final ProcessGuideStepName initialStepName()
    {
        return classStr(ProdProcessGuidePromptProductionIdStep);
    }
    ````   
    
> [!NOTE]
> La valeur dans l'attribut **ProcessGuideStepName** n'a pas besoin de correspondre exactement au nom de la classe comme indiqué ci-dessus. Cependant, l'implémentation de ceci permet une uniformité et une sécurité de type autour des références croisées lors de l'utilisation de la classe. L'utilisation de cette convention de nommage est recommandée.
>
> L'instanciation **ProcessGuideStepName** basée sur l'étape est implémentée dans la classe **ProcessGuideStepDefaultFactory**. Dans les rares cas où vous souhaitez une stratégie différente pour instancier l'étape, vous devez procéder comme suit :
> -   Créer une nouvelle classe de fabrique héritant de **ProcessGuidStepAbstractFactory**.
> -   Facultativement, créez une nouvelle classe de paramètres implémentant l'interface **ProcessGuideIStepCreationParameters**, contenant les paramètres dont la fabrique aurait besoin.
> -   Dans votre classe de contrôleur, remplacez les méthodes **stepFactory()** et **stepCreationParameters()** pour renvoyer les paramètres de fabrique et ceux ci-dessus.

L'étape suivante consiste à implémenter la fonctionnalité de la classe **ProdProcessGuidePromptProductionIdStep**. Vous devez implémenter la logique pour créer l'interface utilisateur, traiter les données saisies par l'utilisateur et déterminer quand l'étape est terminée.

### <a name="building-the-user-interface-for-the-first-step"></a>Créer l'interface utilisateur pour la première étape

L'interface utilisateur est créée à l'aide d'une classe héritant de la classe abstraite **ProcessGuidePageBuilder**. Pour cette étape, nommez la classe pour représenter ce qu'elle fait -**ProdProcessGuidePromptProductionIdPageBuilder**.

Le mécanisme d'instanciation de la classe est similaire à la façon dont l'étape a été instanciée à partir du contrôleur. 

-   Décorez la classe **ProdProcessGuidePromptProductionIdPageBuilder** avec un attribut **ProcessGuidePageBuilderName**.

    ```xpp
    [ProcessGuidePageBuilderName(classStr(ProdProcessGuidePromptProductionIdPageBuilder))] public class ProdProcessGuidePromptProductionIdPageBuilder extends ProcessGuidePageBuilder
    ```

-   Dans la classe **ProdProcessGuidePromptProductionIdStep**, implémentez la méthode abstraite **pageBuilderName()** pour renvoyer ce nom.

    ```xpp
    protected final ProcessGuidePageBuilderName pageBuilderName()
    {
        return classStr(ProdProcessGuidePromptProductionIdPageBuilder);
    }
    ```    

> [!TIP]
> Semblable à la fabrique d'étapes, il existe également un modèle de fabrique abstraite implémenté pour la fabrique de création de pages. De ce fait, dans les rares cas où vous souhaitez une stratégie différente pour instancier le générateur de pages, vous pouvez procéder comme suit :
> - Créer une nouvelle classe de fabrique héritant de **ProcessGuidePageBuilderAbstractFactory**.
> - Facultativement, créez une nouvelle classe de paramètres implémentant l'interface **ProcessGuideIPageBuilderCreationParameters**, contenant les paramètres dont la fabrique aurait besoin.
> - Dans votre classe d'étape, remplacez les méthodes **pageBuilderFactory()** et **pageBuilderCreationParameters()** pour renvoyer les paramètres de fabrique et ceux ci-dessus.

Pour implémenter l'interface utilisateur, vous avez besoin d'une page avec une zone de texte pour saisir l'ID de l'ordre de fabrication, plus un bouton **OK** et un bouton **Annuler**. Le bouton **Annuler** devrait quitter le processus.

Pour implémenter cela, vous devez remplacer deux méthodes dans la classe **ProdProcessGuidePromptProductionIdPageBuilder** :

-   Utilisez la méthode **addDataControls()** pour ajouter la zone de texte.

    ```xpp
    protected final void addDataControls(ProcessGuidePage _page)
    {
        _page.addTextBox(ProcessGuideDataTypeNames::ProdId, "@SYS4398", extendedTypeNum(ProdId));
    }
    ```   

-   Utilisez la méthode **addActionControls()** pour ajouter les boutons **OK** et **Annuler**.

    ```xpp
    protected final void addActionControls(ProcessGuidePage _page)
    {
        #ProcessGuideActionNames
        _page.addButton(step.createAction(#ActionOK), true);
        _page.addButton(step.createAction(#ActionCancelExitProcess));
    }
    ``` 

Cela ajoute les contrôles de données, suivis des boutons. Cependant, si vous souhaitez créer un écran avec des commandes et des boutons de données intercalés, vous pouvez remplacer la méthode **addControls()** à la place pour la flexibilité.

Un scénario supplémentaire à considérer est de savoir comment recréer la page en cas d'échec de validation, par exemple si l'utilisateur entre un ID d'ordre de fabrication incorrect. La classe de base **ProcessGuidePageBuilder** implémente le comportement par défaut, qui recrée l'interface utilisateur, efface la valeur analysée et ajoute le contrôle d'erreur avec le message d'erreur. Comme il s'agit du comportement par défaut que vous souhaitez utiliser, vous n'avez pas besoin d'ajouter de code pour gérer les erreurs.

> [!TIP]
> Si vous souhaitez implémenter un comportement d'interface utilisateur personnalisé pour les situations d'erreur, vous pouvez remplacer une ou plusieurs des méthodes **rebuildFromRequestPage()**, **isErrorState()** et **reuseRequestPageOnError()**.

### <a name="processing-the-user-entered-data-in-the-first-step"></a>Traitement des données saisies par l'utilisateur dans la première étape

Le traitement des données se fait dans la classe **ProcessGuideDataProcessorDefault**, qui à son tour invoque la classe **WhsRfControlData** héritée. Aucune modification n'est nécessaire à ce comportement par défaut, et **WhsRfControlData** a déjà une logique pour valider le champ **ProdId**, vous n'avez donc pas besoin d'écrire de logique pour gérer cela. En cas d'extensions requises pour la logique de validation, pensez à utiliser le mécanisme d'extension basé **WhsControl**.

### <a name="determine-if-the-first-step-is-complete"></a>Déterminer si la première étape est terminée

Lorsque la validation est réussie, il est temps de marquer l'étape comme terminée. Cela se fait dans la classe de base, cependant, vous devez implémenter la condition pour déterminer l'achèvement de l'étape. La méthode remplacée suivante fait cela.

```xpp
protected final boolean isComplete()
{
    WhsrfPassthrough pass = controller.parmSessionState().parmPass();
    ProdId prodId = pass.lookup(ProcessGuideDataTypeNames::ProdId);
        return (prodId != '');
}
```   

### <a name="step-two-view-order-details-and-confirm"></a>Deuxième étape : afficher les détails de la commande et confirmer

Dans la deuxième étape du processus, l'utilisateur voit apparaître un écran avec des détails sur la commande. L'utilisateur peut soit cliquer sur **OK** pour confirmer le démarrage de l'ordre de fabrication, ou cliquez sur **Annuler** pour revenir au début du processus. Pour cet exemple, nommez l'étape **ProdProcessGuideConfirmProductionOrderStep** et la classe de générateur de pages **ProdProcessGuideConfirmProductionOrderPageBuilder**.

La classe ProdProcessGuideConfirmProductionOrderStep ressemble à ce qui suit.

```xpp
[ProcessGuideStepName(classStr(ProdProcessGuideConfirmProductionOrderStep))]
public class ProdProcessGuideConfirmProductionOrderStep extends ProcessGuideStep
{
    protected final ProcessGuidePageBuilderName pageBuilderName()
    {
        return classStr(ProdProcessGuideConfirmProductionOrderPageBuilder);
     }
}
```     

Étant donné que l'utilisateur n'entre aucune valeur ici, vous n'avez pas besoin de remplacer la méthode **isComplete()**. L'étape est terminée lorsque l'utilisateur clique sur **OK**.

La classe de générateur de pages remplace la méthode **addDataControls()** pour ajouter trois étiquettes. La première étiquette indique l'ID de l'ordre de fabrication, la seconde contient des informations sur l'article (telles que l'ID de l'article, les dimensions ou la description) et la troisième contient la quantité et l'unité de mesure.

**addActionControls()** est alors remplacé pour ajouter 2 boutons - le bouton **OK** et le bouton **Annuler** pour annuler le processus et revenir au début du processus.

```xpp
/// <summary>
/// The <c>ProdProcessGuideConfirmProductionOrderPageBuilder</c> builds a page that allows the user to see details of a production order
/// and then confirm.
/// </summary>
[ProcessGuidePageBuilderName(classStr(ProdProcessGuideConfirmProductionOrderPageBuilder))]
public class ProdProcessGuideConfirmProductionOrderPageBuilder extends ProcessGuidePageBuilder
{
    protected void addDataControls(ProcessGuidePage _page)
    {
        WhsrfPassthrough pass = controller.parmSessionState().parmPass();
        ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
        UnitOfMeasureSymbol inventUOM = InventTableModule::find(prodTable.ItemId, ModuleInventPurchSales::Invent).UnitId;
        
        _page.addLabel(ProcessGuideDataTypeNames::ProdIdLabelName, strFmt("@WAX1684", prodTable.ProdId), extendedTypeNum(ProdId));
        _page.addLabel(ProcessGuideDataTypeNames::ItemInfo, this.generateItemInfoForProdId(pass.lookup(ProcessGuideDataTypeNames::ProdId)), extendedTypeNum(WHSRFUndefinedDataType));
        _page.addLabel(ProcessGuideDataTypeNames::QtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId)), inventUOM), extendedTypeNum(WHSRFQuantityAndUOM));

        if (PdsGlobal::pdsIsCWItem(prodTable.ItemId))
        {
            _page.addLabel(ProcessGuideDataTypeNames::InventQtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::pdsCWProposalStartupQty(prodTable.ProdId)), PdsCatchWeightItem::pdsCWUnitId(prodTable.ItemId)), extendedTypeNum(WHSRFQuantityAndUOM));
        }
    }

    protected void addActionControls(ProcessGuidePage _page)
    {
        #ProcessGuideActionNames
        _page.addButton(step.createAction(#ActionOK), true);
        _page.addButton(step.createAction(#ActionCancelResetProcess));
    }
```

> [!NOTE]
> Vous pouvez trouver le même code source pour les méthodes X++ dans cet article en utilisant l'Explorateur d'applications. Filtrez sur le nom de la classe, puis cliquez avec le bouton droit sur le nom de la classe et sélectionnez **Voir le code**.

### <a name="step-3-start-the-production-order"></a>Étape 3 : Démarrer l'ordre de fabrication

La troisième étape est celle où la logique métier de démarrage de l'ordre de fabrication est exécutée. Cette étape est quelque peu différente des étapes précédentes, en ce sens qu'elle n'a pas d'interface utilisateur. Cette étape est exécutée silencieusement lorsque l'utilisateur clique sur **OK** à l'étape précédente.

La classe abstraite **ProcessGuideStepWithoutPrompt** implémente le comportement par défaut pour de telles étapes. L'étape actuelle devrait donc étendre la classe **ProcessGuideStepWithoutPrompt** et remplace la méthode **doExecute()**.

L'exemple de code suivant montre la classe et la mise en oeuvre de la méthode **doExecute()**. La méthode récupère simplement l'ID de commande et l'ID utilisateur de l'état de la session et appelle la méthode pour démarrer cet ordre de fabrication.

```xpp
/// <summary>
/// The <c>ProdProcessGuideStartProductionOrderStep</c> represents a step that starts a production order.
/// </summary>
[ProcessGuideStepName(classStr(ProdProcessGuideStartProductionOrderStep))]
public class ProdProcessGuideStartProductionOrderStep extends ProcessGuideStepWithoutPrompt
{
    protected final void doExecute()
    {
        WhsrfPassthrough pass = controller.parmSessionState().parmPass();
        WHSUserId userId = pass.lookup(ProcessGuideDataTypeNames::UserId);
        ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
        WhsWorkExecute workExecute = WhsWorkExecute::construct();
        workExecute.prodStartUp(prodTable.ProdId, ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId), userId);

        this.addProcessCompletionMessage();

        super();
    }

}
```

En cas d'exception, la logique de gestion des exceptions du framework garantit que le processus est restauré à l'étape précédente.

> [!NOTE]
> L'invocation à **addProcessCompletionMessage()** ajoute le message "Travail terminé" aux paramètres de navigation. L'étape suivante (en supposant qu'elle dispose d'une interface utilisateur) affichera ce message. Les classes de base gèrent cette logique et aucun code spécifique n'a besoin d'être ajouté aux classes de processus pour obtenir ce comportement.


### <a name="building-the-navigation-through-the-steps"></a>Créer la navigation à travers les étapes

La classe de base **ProcessGuideController** instancie la classe **ProcessGuideNavigationAgentDefault**, qui repose sur un itinéraire de navigation prédéfini, qui est une simple carte des étapes source et destination. Pour le scénario de démarrage de la production, comme il n'y a pas de branchement conditionnel, cette implémentation suffirait. Par conséquent, il vous suffit de remplacer la méthode **initializeNavigationRoute()** pour définir l'itinéraire de navigation.

```xpp
    protected ProcessGuideNavigationRoute initializeNavigationRoute()
    {
        ProcessGuideNavigationRoute navigationRoute = new ProcessGuideNavigationRoute();
        navigationRoute.addFollowingStep(classStr(ProdProcessGuidePromptProductionIdStep), classStr(ProdProcessGuideConfirmProductionOrderStep));
        navigationRoute.addFollowingStep(classStr(ProdProcessGuideConfirmProductionOrderStep), classStr(ProdProcessGuideStartProductionOrderStep));
        navigationRoute.addFollowingStep(classStr(ProdProcessGuideStartProductionOrderStep), classStr(ProdProcessGuidePromptProductionIdStep));

        return navigationRoute;
    }
```

Il existe des processus pour lesquels il y aura un branchement conditionnel (basé sur les actions de l'utilisateur ou toute autre condition). De tels processus doivent effectuer les opérations suivantes :

-   Implémenter des agents de navigation spécifiques hérités de la classe **ProcessGuideNavigationAgent** classer.

-   Implémenter la fabrique d'agents de navigation spécifique héritée de la classe **ProcessGuideNavigationAgentAbstractFactory**, contenant une logique pour instancier l'agent de navigation correct en fonction de l'étape actuelle, de l'état de la session, de l'action de l'utilisateur ou d'une autre logique.

-   En option, remplacez **navigationAgentCreationParameters()** dans la classe du contrôleur pour transmettre les paramètres appropriés.

-   Ignorez **navigationAgentFactory()** dans le contrôleur pour instancier la fabrique d'agents de navigation créée ci-dessus.

### <a name="action-classes"></a>Classes d'action

Les classes d'action représentent les actions de l'utilisateur, donc cet exemple utilise l'action **OK** pour montrer comment les actions sont créées.

```xpp
[ProcessGuideActionName(#ActionOK)]
public class ProcessGuideOKAction extends ProcessGuideAction
{
    public final str label()
    {
        return "@SYS5473";
     }
     protected final void doExecute()
     {
        step.executeOKAction();
      }
}
```    

La classe doit implémenter 2 méthodes abstraites :

-   **label()**, qui renvoie le libellé à afficher dans un champ bouton lié à cette action.

-   **doExecute()**, qui exécute l'action. Comme mentionné précédemment, le bouton **OK** effectue simplement un rappel à l'étape. Cependant, d'autres actions pourraient avoir une logique plus complexe ici.

Les actions sont instanciées à l'aide du cadre **SysExtension** basé sur l'attribut **ProcessGuideActionName**. Semblable à l'instanciation des générateurs de pages, la classe step implémente la fabrique d'actions par défaut, et il est possible de la remplacer. Le générateur de page ajoute un contrôle de bouton comme celui-ci.

```xpp
_page.addButton(step.createAction(#ActionOK), true);
```

Ce faisant, il demande à l'étape de créer une classe d'action pour le nom transmis et lie cette action au bouton.

### <a name="summary"></a>Résumé

Pour résumer tout ce qui a été expliqué dans ce sujet, voici un résumé complet du code nécessaire au processus :

1.  **ProdProcessGuideProductionStartController**

    1.  Ignorez **initialStepName()** pour fournir le nom de la première étape.
    2.  Ignorez **initializeNavigationRoute()** pour construire la carte de navigation.

        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideProductionStartController</c> class is the controller class for the production order start process guide.
        /// </summary>
        [WHSWorkExecuteMode(WHSWorkExecuteMode::StartProdOrder)]
        public class ProdProcessGuideProductionStartController extends ProcessGuideController
        {
            protected ProcessGuideStepName initialStepName()
            {
                return classStr(ProdProcessGuidePromptProductionIdStep);
            }

            protected ProcessGuideNavigationRoute initializeNavigationRoute()
            {
                ProcessGuideNavigationRoute navigationRoute = new ProcessGuideNavigationRoute();
                navigationRoute.addFollowingStep(classStr(ProdProcessGuidePromptProductionIdStep), classStr(ProdProcessGuideConfirmProductionOrderStep));
                navigationRoute.addFollowingStep(classStr(ProdProcessGuideConfirmProductionOrderStep), classStr(ProdProcessGuideStartProductionOrderStep));
                navigationRoute.addFollowingStep(classStr(ProdProcessGuideStartProductionOrderStep), classStr(ProdProcessGuidePromptProductionIdStep));

                return navigationRoute;
            }

        }
        ```

2.  **ProdProcessGuidePromptProductionIdStep**

    1.  Ignorez **isComplete()** pour spécifier quand l'étape est considérée comme terminée.
    2.  Ignorez **pageBuilderName()** pour spécifier le générateur de page à utiliser.

        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuidePromptProductionIdStep</c> represents a step that 
        /// that prompts the user for a production order id.
        /// </summary>
        [ProcessGuideStepName(classStr(ProdProcessGuidePromptProductionIdStep))]
        public class ProdProcessGuidePromptProductionIdStep extends ProcessGuideStep
        {
            protected boolean isComplete()
            {
                WhsrfPassthrough pass = controller.parmSessionState().parmPass();
                ProdId prodId = pass.lookup(ProcessGuideDataTypeNames::ProdId);

                return (prodId != '');
            }

            protected ProcessGuidePageBuilderName pageBuilderName()
            {
                return classStr(ProdProcessGuidePromptProductionIdPageBuilder);
            }

        }
        ```

3.  **ProdProcessGuidePromptProductionIdPageBuilder**

    1.  Ignorez **addDataControls()** pour ajouter la zone de texte **Prod ID**.
    2.  Ignorez **addActionControls()** pour ajouter les boutons **OK** et **Annuler**.
        
        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuidePromptProductionIdPageBuilder</c> class builds a page 
        /// that prompts the user for a production order id.
        /// </summary>
        [ProcessGuidePageBuilderName(classStr(ProdProcessGuidePromptProductionIdPageBuilder))]
        public class ProdProcessGuidePromptProductionIdPageBuilder extends ProcessGuidePageBuilder
        {
            protected void addDataControls(ProcessGuidePage _page)
            {
                _page.addTextBox(ProcessGuideDataTypeNames::ProdId, "@SYS4398", extendedTypeNum(ProdId));
            }

            protected void addActionControls(ProcessGuidePage _page)
            {
                #ProcessGuideActionNames
                _page.addButton(step.createAction(#ActionOK), true);
                _page.addButton(step.createAction(#ActionCancelExitProcess));
            }

        }
        ```

4.  **ProdProcessGuideConfirmProductionOrderStep**

    1.  Ignorez **pageBuilderName()** pour spécifier le générateur de page à utiliser.
        
        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideConfirmProductionOrderStep</c> class represents the step for viewing production order
        /// details and confirming the same.
        /// </summary>
        [ProcessGuideStepName(classStr(ProdProcessGuideConfirmProductionOrderStep))]
        public class ProdProcessGuideConfirmProductionOrderStep extends ProcessGuideStep
        {    
            protected ProcessGuidePageBuilderName pageBuilderName()
            {
                return classStr(ProdProcessGuideConfirmProductionOrderPageBuilder);
            }

        }
        ```

3.  **ProdProcessGuideConfirmProductionOrderPageBuilder**

    1.  Ignorez **addDataControls()** pour ajouter les étiquettes d'informations sur la commande, l'article et la quantité.

    2.  Ignorez **addActionControls()** pour ajouter les boutons **OK** et **Annuler**.
        
        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideConfirmProductionOrderPageBuilder</c> builds a page that allows the user to see details of a production order
        /// and then confirm.
        /// </summary>
        [ProcessGuidePageBuilderName(classStr(ProdProcessGuideConfirmProductionOrderPageBuilder))]
        public class ProdProcessGuideConfirmProductionOrderPageBuilder extends ProcessGuidePageBuilder
        {
            protected void addDataControls(ProcessGuidePage _page)
            {
                WhsrfPassthrough pass = controller.parmSessionState().parmPass();
                ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
                UnitOfMeasureSymbol inventUOM = InventTableModule::find(prodTable.ItemId, ModuleInventPurchSales::Invent).UnitId;

                _page.addLabel(ProcessGuideDataTypeNames::ProdIdLabelName, strFmt("@WAX1684", prodTable.ProdId), extendedTypeNum(ProdId));
                _page.addLabel(ProcessGuideDataTypeNames::ItemInfo, this.generateItemInfoForProdId(pass.lookup(ProcessGuideDataTypeNames::ProdId)), extendedTypeNum(WHSRFUndefinedDataType));
                _page.addLabel(ProcessGuideDataTypeNames::QtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId)), inventUOM), extendedTypeNum(WHSRFQuantityAndUOM));

                if (PdsGlobal::pdsIsCWItem(prodTable.ItemId))
                {
                    _page.addLabel(ProcessGuideDataTypeNames::InventQtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::pdsCWProposalStartupQty(prodTable.ProdId)), PdsCatchWeightItem::pdsCWUnitId(prodTable.ItemId)), extendedTypeNum(WHSRFQuantityAndUOM));
                }
            }

            protected void addActionControls(ProcessGuidePage _page)
            {
                #ProcessGuideActionNames
                _page.addButton(step.createAction(#ActionOK), true);
                _page.addButton(step.createAction(#ActionCancelResetProcess));
            }

        ```

        > [!NOTE]
        > La méthode **generateItemInfoForProdId()** utilisée pour générer les étiquettes d'informations sur les articles est exclue de cet article. Cette méthode interroge quelques tables pour obtenir l'ID, la description et les dimensions de l'article. Si vous voulez mieux comprendre **generateItemInfoForProdId()**, regardez le code source.

4.  **ProdProcessGuideStartProductionOrderStep**

    1.  Ignorez **doExecute()** pour exécuter le processus de démarrage de la production et ajouter le message d'achèvement du processus.

        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideStartProductionOrderStep</c> represents a step that starts a production order.
        /// </summary>
        [ProcessGuideStepName(classStr(ProdProcessGuideStartProductionOrderStep))]
        public class ProdProcessGuideStartProductionOrderStep extends ProcessGuideStepWithoutPrompt
        {
            protected final void doExecute()
            {
                WhsrfPassthrough pass = controller.parmSessionState().parmPass();
                WHSUserId userId = pass.lookup(ProcessGuideDataTypeNames::UserId);
                ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
                WhsWorkExecute workExecute = WhsWorkExecute::construct();
                workExecute.prodStartUp(prodTable.ProdId, ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId), userId);

                this.addProcessCompletionMessage();

                super();
            }

        }
        ```

> [!NOTE]
> Notez que de nombreux modèles courants (régénération de l'interface utilisateur en cas d'erreur, message d'achèvement du processus de configuration, comportement des boutons **OK** et **Annuler**) ont été déplacés vers le framework, évitant ainsi au développeur d'applications d'écrire du code passe-partout à la fois sujet aux erreurs et présentant un risque de comportement incohérent entre les processus. Lorsque le scénario doit s'écarter du chemin commun, cependant, le développeur de l'application a la possibilité de remplacer les méthodes appropriées - mais il s'agit alors d'un écart intentionnel à la fois explicite et traçable.


### <a name="extending-a-business-process"></a>Extension d'un processus d'entreprise

Jusqu'à présent, ce sujet a mis en évidence comment construire un nouveau processus en utilisant le cadre **ProcessGuide**. Dans cette dernière section, vous trouverez quelques exemples de la façon dont ce processus métier peut être étendu.

### <a name="add-a-step-in-a-flow-using-processguidenavigationagentdefault"></a>Ajouter une étape dans un flux (à l'aide de ProcessGuideNavigationAgentDefault)

Où effectuer l'extension :

-   Enfant de la classe **ProcessGuideController** pour le processus.

Comment effectuer l'extension :

-   Étendez la méthode **initializeNavigationRoute()** dans la classe du contrôleur, et invoquez **addFollowingStep()** dans la classe **ProcessGuideNavigationRoute**.

### <a name="add-a-step-in-a-flow-using-custom-navigation-agent"></a>Ajouter une étape dans un flux (à l'aide de l'agent de navigation personnalisée)

Où effectuer l'extension :

-   Enfant de **ProdProcessGuideNavigationAgentFactory/ProdProcessGuideNavigationAgent**.

Comment effectuer l'extension :

-   Créer une nouvelle classe enfant de **ProcessGuideNavigationAgent** qui renvoie le nom de l'étape souhaitée.

-   Créer une nouvelle classe à partir de **ProcessGuideNavigationAgentFactory** qui renvoie conditionnellement l'agent de navigation créé ci-dessus.

-   Étendez la méthode **navigationAgentFactory()** dans la classe du contrôleur pour renvoyer la fabrique créée ci-dessus.

### <a name="add-a-new-control-in-the-ui-of-an-existing-step"></a>Ajouter un nouveau contrôle dans l'interface utilisateur d'une étape existante 

Où effectuer l'extension :

-   Enfant de **ProdProcessGuidePageBuilder** pour l'étape.

Comment effectuer l'extension :

-   Étendez la méthode **addDataControls()** et ajoutez le contrôle supplémentaire.

### <a name="complete-overhaul-of-the-user-interface-in-an-existing-step"></a>Refonte complète de l'interface utilisateur dans une étape existante

Où effectuer l'extension :

-   Enfant de **ProdProcessGuideStep**.

Comment effectuer l'extension :

-   Créez une nouvelle classe enfant de la classe **ProdProcessGuidePageBuilder** et implémentez l'interface utilisateur souhaitée.

-   Étendez la méthode **pageBuildeName()** dans la classe step pour retourner **ProcessGuidePageBuilderNameAttribute** pour la classe créée ci-dessus.

### <a name="alter-logic-when-a-step-is-considered-complete"></a>Modifier la logique lorsqu'une étape est considérée comme terminée

Où effectuer l'extension :

-   Enfant de **ProdProcessGuideStep**.

Comment effectuer l'extension :

-   Étendez la méthode **isComplete** pour créer la logique supplémentaire.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]