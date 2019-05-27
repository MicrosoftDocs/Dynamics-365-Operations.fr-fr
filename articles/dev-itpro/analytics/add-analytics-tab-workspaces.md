---
title: Ajouter des analyses aux espaces de travail à l'aide de Power BI Embedded
description: Cette rubrique explique comment inclure un état Power BI sous l'onglet Analyses d'un espace de travail.
author: tjvass
manager: AnnBe
ms.date: 06/21/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user, IT Pro
ms.reviewer: robinr
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: a190e15dc304f60739c80d75222830ee737c5a32
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1548183"
---
# <a name="add-analytics-to-workspaces-by-using-power-bi-embedded"></a>Ajouter des analyses aux espaces de travail à l'aide de Power BI Embedded

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Cette fonction est prise en charge dans Dynamics 365 for Finance and Operations (version 7.2 et ultérieure).

## <a name="introduction"></a>Introduction
Cette rubrique explique comment inclure un état Microsoft Power BI sous l'onglet **Analyses** d'un espace de travail. Pour l'exemple qui est indiqué ici, nous étendrons l'espace de travail **Gestion des réservations** dans l'application Gestion de flotte pour inclure un espace de travail analytique sur un onglet **Analyses**.

## <a name="prerequisites"></a>Conditions préalables
+ Accédez à un environnement de développeur qui exécute la plateforme mise à jour 8 ou ultérieure.
+ Un état analytique (fichier .pbix) qui a été créé à l'aide de Microsoft Power BI Desktop, et un autre disposant d'un modèle de données qui est originaire de la base de données du magasin d'entités.

## <a name="overview"></a>Vue d'ensemble
Si vous étendez un espace de travail d'application existant ou que vous introduisez un nouvel espace de travail personnalisé, vous pouvez utiliser les vues analytiques intégrées pour fournir des vues pertinentes et interactives de vos données commerciales. Le processus pour ajouter un onglet d'espace de travail analytique se compose de quatre étapes.

1. Ajoutez un fichier .pbix comme ressource Dynamics 365.
2. Définissez un onglet d'espace de travail analytique.
3. Intégrez la ressource .pbix sous l'onglet de l'espace de travail.
4. Facultatif : ajoutez des extensions pour personnaliser la vue.

> [!NOTE]
> Pour plus d'informations sur la création des états analytiques, voir [Mise en route de Power BI Desktop](https://powerbi.microsoft.com/en-us/documentation/powerbi-desktop-getting-started/). Cette page est une grande source pour des informations qui vous permettent de créer des solutions de génération d'états analytiques attractifs.

## <a name="add-a-pbix-file-as-a-resource"></a>Ajoutez un fichier .pbix comme ressource
Avant de commencer, vous devez créer ou obtenir l'état Power BI que vous inclurez de l'espace de travail. Pour plus d'informations sur la création des états analytiques, voir [Mise en route de Power BI Desktop](https://powerbi.microsoft.com/en-us/documentation/powerbi-desktop-getting-started/).

Procédez comme suit pour ajouter un fichier .pbix comme artefact de projet Visual Studio.

1. Créez un projet dans le modèle approprié.
2. Dans l'Explorateur de solution, sélectionnez le projet, cliquez avec le bouton droit, puis sélectionnez **Ajouter** \> **Nouvel article**.
3. Dans la boîte de dialogue **Ajouter le nouvel article**, sous **Artefacts d'opérations**, sélectionnez le modèle **Ressource**.
4. Entrez un nom qui sera utilisé pour référencer l'état dans des métadonnées X++, puis cliquez sur **Ajouter**.

    ![Ajoutez la boîte de dialogue Nouvel article](media/analytical-workspace-add.png)

5. Cherchez le fichier .pbix contenant la définition de l'état analytique, puis cliquez sur **Ouvrir**.

    ![Sélectionnez une boîte de dialogue Fichier de ressource](media/analytical-workspace-select-resource.png)

Maintenant que vous avez ajouté le fichier .pbix comme ressource Dynamics 365, vous pouvez inclure les états dans des espaces de travail et ajouter des liens directs à l'aide des options de menu.

## <a name="add-a-tab-control-to-an-application-workspace"></a>Ajoutez un contrôle d'onglet à un espace de travail d'application
Dans cet exemple, nous étendrons l'espace de travail **Gestion des réservations** dans le modèle de gestion de flotte en ajoutant l'onglet **Analytises** à la définition de l'écran **FMClerkWorkspace**.

L'illustration suivante indique à quoi ressemble l'écran **FMClerkWorkspace** dans le concepteur de Microsoft Visual Studio.

![Écran FMClerkWorkspace avant les modifications](media/analytical-workspace-definition-before.png)

Procédez comme suit pour prolonger la définition d'écran pour l'espace de travail **Gestion des réservations**.

1. Ouvrez le concepteur d'écran pour étendre la définition de conception.
2. Dans la définition de conception, sélectionnez l'élément supérieur qui est libellé **Mise en page | Modèle : Workspace Operational**.
3. Cliquez avec le bouton droit, puis sélectionnez **Nouveau** \> **Onglet** pour ajouter un nouveau contrôle nommé **FormTabControl1**.
4. Dans le concepteur d'écrans, sélectionnez **FormTabControl1**.
5. Cliquez avec le bouton droit, puis sélectionnez la page **Nouvel onglet** pour ajouter un nouvel onglet.
6. Renommez la page de l'onglet avec un nom évocatrice, tel qu'**Espace de travail**.
7. Dans le concepteur d'écrans, sélectionnez **FormTabControl1**.
8. Cliquez avec le bouton droit et sélectionnez la page **Nouvel onglet**.
9. Renommez la page de l'onglet avec un nom évocateur, tel qu'**Analyses**.
10. Dans le concepteur d'écrans, sélectionnez **Analyses (page d'onglet)**.
11. Définissez la propriété **Légende** sur **Analyses**.
12. Cliquez avec le bouton droit sur le contrôle, puis sélectionnez **Nouveau** \> **Groupe** pour ajouter un nouveau contrôle de groupe d'écrans.
13. Renommez le groupe d'écrans avec un nom évocateur, tel que **powerBIReportGroup**.
14. Dans le concepteur d'écrans, sélectionnez **PanoramaBody (onglet)**, puis faites glisser le contrôle dans l'onglet **Espace de travail**.
15. Dans la définition de conception, sélectionnez l'élément supérieur qui est libellé **Mise en page | Modèle : Workspace Operational**.
16. Cliquez avec le bouton droit et sélectionnez la page **Supprimer le modèle**.
17. Cliquez avec le bouton droit de nouveau, puis sélectionnez **Ajouter un modèle** \> **Espace de travail à onglets**.
18. Créez un build pour vérifier vos modifications.

L'illustration suivante présente ce à quoi la conception ressemble une fois ces modifications appliquées.

![FMClerkWorkspace après des modifications](media/analytical-workspace-definition-after.png)

Maintenant que vous avez ajouté des contrôles d'écrans qui seront utilisés pour inclure l'état de l'espace de travail, vous devez définir la taille du contrôle parent de sorte qu'il s'adapte à la mise en page. Par défaut, la page **Volet de filtres** et la page **Onglet** sont visibles sur l'état. Toutefois, vous pouvez modifier la visibilité de ces contrôles en fonction du client cible de l'état.

> [!NOTE]
> Pour les espaces de travail intégrés, nous vous recommandons d'utiliser des extensions pour masquer les pages **Volet de filtres** et **Onglet**, pour des raisons de cohérence.

Vous avez terminé la tâche d'extension de la définition d'écran d'application. Pour plus d'informations sur l'utilisation d'extensions pour effectuer des personnalisations, voir [Personnalisation : superposition de couches et extensions](../extensibility/customization-overlayering-extensions.md).

## <a name="add-x-business-logic-to-embed-a-viewer-control"></a>Ajoutez la logique métier X++ pour inclure un contrôle de la visionneuse
Procédez comme suit pour ajouter une logique métier qui initialise le contrôle de la visionneuse de rapports qui est intégrée à l'espace de travail **Gestion des réservations**.

1. Ouvrez le concepteur d'écran **FMClerkWorkspace** pour étendre la définition de conception.
2. Appuyez sur F7 pour accéder au code derrière la définition du code.
3. Ajoutez le code X++ suivant :

    ```
    [Form] 
    public class FMClerkWorkspace extends FormRun
    {
        private boolean initReportControl = true;
        protected void initAnalyticalReport()
        {
            if (!initReportControl)
            {
                return;
            }
            // Note: secure entry point into the Workspace's Analytics report
            if (Global::hasMenuItemAccess(menuItemDisplayStr(FMClerkWorkspace), MenuItemType::Display))
            {
                // initialize the PBI report control using shared helper
                PBIReportHelper::initializeReportControl('FMPBIWorkspaces', powerBIReportGroup);
            }
            initReportControl = false;
        }
        /// <summary>
        /// Initializes the form.
        /// </summary>
        public void init()
        {
            super();
            this.initAnalyticalReport();
        }
    }
    ```

4. Créez un build pour vérifier vos modifications.

Vous avez terminé la tâche d'ajouter une logique métier pour initialiser le contrôle de la visionneuse de rapports intégrée. L'illustration suivante présente ce à quoi l'espace de travail ressemble une fois ces modifications appliquées.

![État intégré à l'espace de travail](media/analytical-workspace-final.png)

> [!NOTE]
> Vous pouvez accéder à la vue opérationnelle existante à l'aide des onglets de l'espace de travail sous le titre de la page.

## <a name="reference"></a>Référence

### <a name="pbireporthelperinitializereportcontrol-method"></a>Méthode PBIReportHelper.initializeReportControl
Cette section fournit des informations sur la classe d'aide utilisée pour inclure un état Power BI (ressource .pbix) à un contrôle de groupe d'écrans.

#### <a name="syntax"></a>Syntaxe
```
public static void initializeReportControl(
    str                 _resourceName,
    FormGroupControl    _formGroupControl,
    str                 _defaultPageName = '',
    boolean             _showFilterPane = false,
    boolean             _showNavPane = false,
    List                _defaultFilters = new List(Types::Class))
```

#### <a name="parameters"></a>Paramètres

| Nom             | Description                                                                                                  |
|------------------|--------------------------------------------------------------------------------------------------------------|
| resourceName     | Nom de la ressource .pbix                                                                              |
| formGroupControl | Contrôle de groupe d'écrans auquel appliquer le contrôle de l'état Power BI.                                              |
| defaultPageName  | Nom de la page par défaut                                                                                       |
| showFilterPane   | Valeur booléenne qui indique si le volet de filtre doit être affiché (**vrai**) ou masqué (**faux**).     |
| showNavPane      | Valeur booléenne qui indique si le volet de navigation doit être affiché (**vrai**) ou masqué (**faux**). |
| defaultFilters   | Filtres par défaut pour l'état Power BI.                                                                 |
