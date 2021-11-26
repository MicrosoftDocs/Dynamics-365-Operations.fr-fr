---
title: Personnaliser l’interface d’exécution de l’atelier de production
description: Cette rubrique explique comment étendre les formulaires actuels ou créer des formulaires et boutons pour l’interface d’exécution de l’atelier de production.
author: johanhoffmann
ms.date: 11/08/2021
ms.topic: article
ms.search.form: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-11-08
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 414fe5d6e16ad125bc2b9bb7ed427e5db5180ec9
ms.sourcegitcommit: bc9e75c38e192664cde226ed3a94df5a0b304369
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2021
ms.locfileid: "7790970"
---
# <a name="customize-the-production-floor-execution-interface"></a>Personnaliser l’interface d’exécution de l’atelier de production

[!include [banner](../includes/banner.md)]

Les développeurs peuvent étendre les formulaires actuels ou créer leurs propres formulaires et boutons pour l’interface d’exécution de l’atelier de production. Une fois que vous avez ajouté le code de ces nouveaux éléments, les administrateurs ou les chefs d’atelier peuvent facilement les ajouter à l’interface en utilisant les contrôles de configuration standard.

Par exemple, voici quelques-unes des solutions possibles si de nouvelles colonnes sont nécessaires dans un formulaire principal :

- Étendez le formulaire `JmgProductionFloorExecutionMainGrid` et ajoutez les champs souhaités.
- Créez un formulaire et ajoutez-le en tant que nouvelle vue principale (onglet).

## <a name="add-a-new-button-action"></a>Ajouter un nouveau bouton (action)

Pour ajouter un nouveau bouton (action), suivez ces étapes pour créer une classe qui implémente votre action personnalisée.

1. Créez une classe nommée `<ExtensionPrefix>_JmgProductionFloorExecution<ActionName>Action`, où :

    - `<ExtensionPrefix>` identifie de manière unique votre solution, généralement en utilisant le nom de votre entreprise.
    - `<ActionName>` est un nom unique pour la classe. Il identifie généralement le type d’action.

1. La nouvelle classe doit étendre la classe `JmgProductionFloorExecutionAction`.
1. Remplacez toutes les méthodes nécessaires.

Pour des exemples, regardez le code des classes suivantes :

- `JmgProductionFloorExecutionBreakAction` – Une classe pour une action simple qui ne nécessite aucun enregistrement.
- `JmgProductionFloorExecutionReportFeedbackAction` – Une classe qui fournit des fonctionnalités plus complexes.

Lorsque vous avez terminé, le nouveau bouton (action) sera automatiquement répertorié sur la page **Onglets de conception** dans Microsoft Dynamics 365 Supply Chain Management. De là, vous (ou un administrateur ou un chef d’atelier) pouvez facilement l’ajouter à la barre d’outils principale ou secondaire, tout comme vous pouvez ajouter les boutons standard. Pour obtenir des instructions, voir [Concevoir l’interface d’exécution de l’atelier de production](production-floor-execution-tabs.md).

## <a name="add-a-new-main-view"></a>Ajouter une nouvelle vue principale

1. Créez un formulaire contenant les éléments et les fonctionnalités souhaités. Notez que ce formulaire est un nouveau formulaire, pas une extension. Nommez le formulaire `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>`, où :

    - `<ExtensionPrefix>` identifie de manière unique votre solution, généralement en utilisant le nom de votre entreprise.
    - `<FormName>` est un nom unique pour le formulaire.

1. Créer un élément de menu nommé `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>`.
1. Créer une extension nommée `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>_Extension`, où la méthode `getMainMenuItemsList` est étendue en ajoutant le nouvel élément de menu à la liste. Le code suivant présente un exemple.

    ```xpp
    [ExtensionOf(classStr(JmgProductionFloorExecutionForm))]
    public final class <ExtensionPrefix>_JmgProductionFloorExecutionForm<FormName>_Extension{
        static public List getMainMenuItemsList()
        {
            List menuItemList = next getMainMenuItemsList();
            menuItemList.addEnd(menuItemDisplayStr(<ExtensionPrefix>_JmgProductionFloorExecutionForm<FormName>));
            return menuItemList;
        }
    ```

Lorsque vous avez terminé, la nouvelle vue principale sera automatiquement répertoriée dans la zone de liste déroulante **Vue principale** sur la page **Onglets de conception** dans Supply Chain Management. De là, vous (ou un administrateur ou un chef d’atelier) pouvez facilement l’ajouter des onglets nouveaux ou existants, tout comme vous pouvez ajouter les vues principales standard. Pour obtenir des instructions, voir [Concevoir l’interface d’exécution de l’atelier de production](production-floor-execution-tabs.md).

## <a name="add-a-details-view"></a>Ajouter une vue des détails

1. Créez un formulaire contenant les éléments et les fonctionnalités souhaités. Notez que ce formulaire est nouveau, pas une extension. Nommez le formulaire `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>Detail`, où : 

    - `<ExtensionPrefix>` identifie de manière unique votre solution, généralement en utilisant le nom de votre entreprise.
    - `<FormName>` est un nom unique pour le formulaire.

1. Créer un élément de menu nommé `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>Detail`.
1. Créer une extension nommée `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>_Extension`, où la méthode `getDetailsMenuItemList` est étendue en ajoutant le nouvel élément de menu à la liste.

Lorsque vous avez terminé, la nouvelle vue de détails sera automatiquement répertoriée dans la zone de liste déroulante **Vue de détails** sur la page **Onglets de conception** dans Supply Chain Management. De là, vous (ou un administrateur ou un chef d’atelier) pouvez facilement l’ajouter des onglets nouveaux ou existants, tout comme vous pouvez ajouter les vues de détails standard. Pour obtenir des instructions, voir [Concevoir l’interface d’exécution de l’atelier de production](production-floor-execution-tabs.md).

## <a name="add-a-numeric-keypad-to-a-form-or-dialog"></a>Ajouter un pavé numérique à un formulaire ou une boîte de dialogue

L’exemple suivant montre comment ajouter des pavés numériques à un formulaire.

1. Le nombre de contrôleurs de pavé numérique que contient chaque formulaire doit être égal au nombre de pavés numériques de ce formulaire.

    ```xpp
    private JmgProductionFloorExecutionNumpadController   numpadController1;
    private JmgProductionFloorExecutionNumpadController   numpadController2;
    private JmgProductionFloorExecutionNumpadController   numpadController3;
    ```

1. Configurez le comportement de chaque contrôleur de clavier numérique et connectez chaque contrôleur de clavier numérique à un élément de formulaire de clavier numérique.

    ```xpp
    /// <summary>
    /// Initializes all numpad controllers, defines their behavior and connects them with numpad form parts.
    /// </summary>
    public void initializeNumpadController()
    {
        numpadController1 = new JmgProductionFloorExecutionNumpadController();
        numpadController1.getValueFromNumpadDelegate += eventhandler(this.setQuanityValueFromNumpad_1);
        QuantityNumpad1.getPartFormRun().setNumpadController(numpadController1);
    
        numpadController2 = new JmgProductionFloorExecutionNumpadController();
        numpadController2.parmNumpadEnabled(false);
        numpadController2.parmNumpadValue(333.56);
        numpadController2.getValueFromNumpadDelegate += eventhandler(this.setQuanityValueFromNumpad_2);
        QuantityNumpad2.getPartFormRun().setNumpadController(numpadController2);
    }
    ```

## <a name="use-a-numeric-keypad-as-a-pop-up-dialog"></a>Utiliser un pavé numérique comme boîte de dialogue contextuelle

L’exemple suivant montre une façon de configurer un contrôleur de clavier numérique pour une boîte de dialogue contextuelle.

```xpp
private void setupNumpadController()
{
    numpadController = new JmgProductionFloorExecutionNumpadController();
    numpadController.parmShouldNumpadShowOkCancelButtons(true);
    numpadController.setNumpadValueToParentFormDelegate += eventhandler(this.setQtyValueFromNumpad);
}
```

L’exemple suivant montre une façon d’appeler la boîte de dialogue contextuelle de clavier numérique.

```xpp
Args args = new Args();
args.name(formstr(JmgProductionFloorExecutionNumpad));
args.menuItemName(menuItemDisplayStr(JmgProductionFloorExecutionNumpad));
args.caller(element);
Object formRun = classfactory.formRunClass(args);
formRun.init();
formRun.setNumpadController(numpadController);
numpadController.setValueToNumpad(333.56);
formRun.run();
```

## <a name="additional-resources"></a>Ressources supplémentaires

- [Appliquer un style à l’interface d’exécution de l’atelier de production](production-floor-execution-styles.md)
- [Concevoir l’interface d’exécution de l’atelier de production](production-floor-execution-tabs.md)
