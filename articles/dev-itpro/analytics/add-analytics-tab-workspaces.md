---
title: "Ajouter des analyses aux espaces de travail à l'aide de Power BI Embedded"
description: "Cette rubrique explique comment inclure un état Power BI sous l'onglet Analyses d'un espace de travail."
author: tjvass
manager: AnnBe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application user, IT Pro
ms.reviewer: robinr
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 8075abccdcdde21df967dcc9948a738895f35cef
ms.openlocfilehash: 9447b0d9eedbdd56f1e221a48f687a94a19d31c4
ms.contentlocale: fr-fr
ms.lasthandoff: 01/25/2018

---

# <a name="add-analytics-to-workspaces-by-using-power-bi-embedded"></a><span data-ttu-id="41050-103">Ajouter des analyses aux espaces de travail à l'aide de Power BI Embedded</span><span class="sxs-lookup"><span data-stu-id="41050-103">Add analytics to workspaces by using Power BI Embedded</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="41050-104">Cette fonction est prise en charge dans Dynamics 365 for Finance and Operations (version 7.2 et ultérieure).</span><span class="sxs-lookup"><span data-stu-id="41050-104">This feature is supported in Dynamics 365 for Finance and Operations (version 7.2 and later).</span></span>

## <a name="introduction"></a><span data-ttu-id="41050-105">Introduction</span><span class="sxs-lookup"><span data-stu-id="41050-105">Introduction</span></span>
<span data-ttu-id="41050-106">Cette rubrique explique comment inclure un état Microsoft Power BI sous l'onglet **Analyses** d'un espace de travail.</span><span class="sxs-lookup"><span data-stu-id="41050-106">This topic shows how to embed a Microsoft Power BI report on the **Analytics** tab of a workspace.</span></span> <span data-ttu-id="41050-107">Pour l'exemple qui est indiqué ici, nous étendrons l'espace de travail **Gestion des réservations** dans l'application Gestion de flotte pour inclure un espace de travail analytique sur un onglet **Analyses**.</span><span class="sxs-lookup"><span data-stu-id="41050-107">For the example that is given here, we will extend the **Reservation management** workspace in the Fleet Management application to embed an analytical workspace on an **Analytics** tab.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="41050-108">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="41050-108">Prerequisites</span></span>
+ <span data-ttu-id="41050-109">Accédez à un environnement de développeur qui exécute la plateforme mise à jour 8 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="41050-109">Access to a developer environment that runs Platform update 8 or later.</span></span>
+ <span data-ttu-id="41050-110">Un état analytique (fichier .pbix) qui a été créé à l'aide de Microsoft Power BI Desktop, et un autre disposant d'un modèle de données qui est originaire de la base de données du magasin d'entités.</span><span class="sxs-lookup"><span data-stu-id="41050-110">An analytical report (.pbix file) that was created by using Microsoft Power BI Desktop, and that has a data model that is sourced from the Entity store database.</span></span>

## <a name="overview"></a><span data-ttu-id="41050-111">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="41050-111">Overview</span></span>
<span data-ttu-id="41050-112">Si vous étendez un espace de travail d'application existant ou que vous introduisez un nouvel espace de travail personnalisé, vous pouvez utiliser les vues analytiques intégrées pour fournir des vues pertinentes et interactives de vos données commerciales.</span><span class="sxs-lookup"><span data-stu-id="41050-112">Whether you extend an existing application workspace or introduce a new workspace of your own, you can use embedded analytical views to deliver insightful and interactive views of your business data.</span></span> <span data-ttu-id="41050-113">Le processus pour ajouter un onglet d'espace de travail analytique se compose de quatre étapes.</span><span class="sxs-lookup"><span data-stu-id="41050-113">The process for adding an analytical workspace tab has four steps.</span></span>

1. <span data-ttu-id="41050-114">Ajoutez un fichier .pbix comme ressource Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="41050-114">Add a .pbix file as a Dynamics 365 resource.</span></span>
2. <span data-ttu-id="41050-115">Définissez un onglet d'espace de travail analytique.</span><span class="sxs-lookup"><span data-stu-id="41050-115">Define an analytical workspace tab.</span></span>
3. <span data-ttu-id="41050-116">Intégrez la ressource .pbix sous l'onglet de l'espace de travail.</span><span class="sxs-lookup"><span data-stu-id="41050-116">Embed the .pbix resource on the workspace tab.</span></span>
4. <span data-ttu-id="41050-117">Facultatif : ajoutez des extensions pour personnaliser la vue.</span><span class="sxs-lookup"><span data-stu-id="41050-117">Optional: Add extensions to customize the view.</span></span>

> [!NOTE]
> <span data-ttu-id="41050-118">Pour plus d'informations sur la création des états analytiques, voir [Mise en route de Power BI Desktop](https://powerbi.microsoft.com/en-us/documentation/powerbi-desktop-getting-started/).</span><span class="sxs-lookup"><span data-stu-id="41050-118">For more information about how to create analytical reports, see [Getting started with Power BI Desktop](https://powerbi.microsoft.com/en-us/documentation/powerbi-desktop-getting-started/).</span></span> <span data-ttu-id="41050-119">Cette page est une grande source pour des informations qui vous permettent de créer des solutions de génération d'états analytiques attractifs.</span><span class="sxs-lookup"><span data-stu-id="41050-119">This page is a great source for insights that can help you create compelling analytical reporting solutions.</span></span>

## <a name="add-a-pbix-file-as-a-resource"></a><span data-ttu-id="41050-120">Ajoutez un fichier .pbix comme ressource</span><span class="sxs-lookup"><span data-stu-id="41050-120">Add a .pbix file as a resource</span></span>
<span data-ttu-id="41050-121">Avant de commencer, vous devez créer ou obtenir l'état Power BI que vous inclurez de l'espace de travail.</span><span class="sxs-lookup"><span data-stu-id="41050-121">Before you begin, you must create or obtain the Power BI report that you will embed in the workspace.</span></span> <span data-ttu-id="41050-122">Pour plus d'informations sur la création des états analytiques, voir [Mise en route de Power BI Desktop](https://powerbi.microsoft.com/en-us/documentation/powerbi-desktop-getting-started/).</span><span class="sxs-lookup"><span data-stu-id="41050-122">For more information about how to create analytical reports, see [Getting started with Power BI Desktop](https://powerbi.microsoft.com/en-us/documentation/powerbi-desktop-getting-started/).</span></span>
 
<span data-ttu-id="41050-123">Procédez comme suit pour ajouter un fichier .pbix comme artefact de projet Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="41050-123">Follow these steps to add a .pbix file as a Visual Studio project artifact.</span></span>

1. <span data-ttu-id="41050-124">Créez un projet dans le modèle approprié.</span><span class="sxs-lookup"><span data-stu-id="41050-124">Create a new project in the appropriate model.</span></span>
2. <span data-ttu-id="41050-125">Dans l'Explorateur de solution, sélectionnez le projet, cliquez avec le bouton droit, puis sélectionnez **Ajouter** > **Nouvel article**.</span><span class="sxs-lookup"><span data-stu-id="41050-125">In Solution Explorer, select the project, right-click, and then select **Add** > **New Item**.</span></span>
3. <span data-ttu-id="41050-126">Dans la boîte de dialogue **Ajouter le nouvel article**, sous **Artefacts d'opérations**, sélectionnez le modèle **Ressource**.</span><span class="sxs-lookup"><span data-stu-id="41050-126">In the **Add New Item** dialog box, under **Operations Artifacts**, select the **Resource** template.</span></span>
4. <span data-ttu-id="41050-127">Entrez un nom qui sera utilisé pour référencer l'état dans des métadonnées X++, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="41050-127">Enter a name that will be used to reference the report in X++ metadata, and then click **Add**.</span></span>

    ![Ajoutez la boîte de dialogue Nouvel article](media/analytical-workspace-add.png)

5. <span data-ttu-id="41050-129">Cherchez le fichier .pbix contenant la définition de l'état analytique, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="41050-129">Find the .pbix file that contains the definition of the analytical report, and then click **Open**.</span></span>

    ![Sélectionnez une boîte de dialogue Fichier de ressource](media/analytical-workspace-select-resource.png)
  
<span data-ttu-id="41050-131">Maintenant que vous avez ajouté le fichier .pbix comme ressource Dynamics 365, vous pouvez inclure les états dans des espaces de travail et ajouter des liens directs à l'aide des options de menu.</span><span class="sxs-lookup"><span data-stu-id="41050-131">Now that you've added the .pbix file as a Dynamics 365 resource, you can embed the reports in workspaces and add direct links by using menu items.</span></span>

## <a name="add-a-tab-control-to-an-application-workspace"></a><span data-ttu-id="41050-132">Ajoutez un contrôle d'onglet à un espace de travail d'application</span><span class="sxs-lookup"><span data-stu-id="41050-132">Add a tab control to an application workspace</span></span>
<span data-ttu-id="41050-133">Dans cet exemple, nous étendrons l'espace de travail **Gestion des réservations** dans le modèle de gestion de flotte en ajoutant l'onglet **Analytises** à la définition de l'écran **FMClerkWorkspace**.</span><span class="sxs-lookup"><span data-stu-id="41050-133">In this example, we will extend the **Reservation management** workspace in the Fleet Management model by adding the **Analytics** tab to the definition of the **FMClerkWorkspace** form.</span></span>
 
<span data-ttu-id="41050-134">L'illustration suivante indique à quoi ressemble l'écran **FMClerkWorkspace** dans le concepteur de Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="41050-134">The following illustration shows what the **FMClerkWorkspace** form looks like in the designer in Microsoft Visual Studio.</span></span>

![Écran FMClerkWorkspace avant les modifications](media/analytical-workspace-definition-before.png)

<span data-ttu-id="41050-136">Procédez comme suit pour prolonger la définition d'écran pour l'espace de travail **Gestion des réservations**.</span><span class="sxs-lookup"><span data-stu-id="41050-136">Follow these steps to extend the form definition for the **Reservation management** workspace.</span></span>

1. <span data-ttu-id="41050-137">Ouvrez le concepteur d'écran pour étendre la définition de conception.</span><span class="sxs-lookup"><span data-stu-id="41050-137">Open the form designer to extend the design definition.</span></span>
2. <span data-ttu-id="41050-138">Dans la définition de conception, sélectionnez l'élément supérieur qui est libellé **Mise en page | Modèle : Workspace Operational**.</span><span class="sxs-lookup"><span data-stu-id="41050-138">In the design definition, select the top element that is labeled **Design | Pattern: Workspace Operational**.</span></span>
3. <span data-ttu-id="41050-139">Cliquez avec le bouton droit, puis sélectionnez **Nouveau** > **Onglet** pour ajouter un nouveau contrôle nommé **FormTabControl1**.</span><span class="sxs-lookup"><span data-stu-id="41050-139">Right-click, and then select **New** > **Tab** to add a new control that is named **FormTabControl1**.</span></span>
4. <span data-ttu-id="41050-140">Dans le concepteur d'écrans, sélectionnez **FormTabControl1**.</span><span class="sxs-lookup"><span data-stu-id="41050-140">In the form designer, select **FormTabControl1**.</span></span>
5. <span data-ttu-id="41050-141">Cliquez avec le bouton droit, puis sélectionnez la page **Nouvel onglet** pour ajouter un nouvel onglet.</span><span class="sxs-lookup"><span data-stu-id="41050-141">Right-click, and then select **New Tab Page** to add a new tab page.</span></span>
6. <span data-ttu-id="41050-142">Renommez la page de l'onglet avec un nom évocatrice, tel qu'**Espace de travail**.</span><span class="sxs-lookup"><span data-stu-id="41050-142">Rename the tab page to something meaningful, such as **Workspace**.</span></span>
7. <span data-ttu-id="41050-143">Dans le concepteur d'écrans, sélectionnez **FormTabControl1**.</span><span class="sxs-lookup"><span data-stu-id="41050-143">In the form designer, select **FormTabControl1**.</span></span>
8. <span data-ttu-id="41050-144">Cliquez avec le bouton droit et sélectionnez la page **Nouvel onglet**.</span><span class="sxs-lookup"><span data-stu-id="41050-144">Right-click, and then select **New Tab Page**.</span></span>
9. <span data-ttu-id="41050-145">Renommez la page de l'onglet avec un nom évocateur, tel qu'**Analyses**.</span><span class="sxs-lookup"><span data-stu-id="41050-145">Rename the tab page to something meaningful, such as **Analytics**.</span></span>
10. <span data-ttu-id="41050-146">Dans le concepteur d'écrans, sélectionnez **Analyses (page d'onglet)**.</span><span class="sxs-lookup"><span data-stu-id="41050-146">In the form designer, select **Analytics (Tab Page)**.</span></span>
11. <span data-ttu-id="41050-147">Définissez la propriété **Légende** sur **Analyses**.</span><span class="sxs-lookup"><span data-stu-id="41050-147">Set the **Caption** property to **Analytics**.</span></span>
12. <span data-ttu-id="41050-148">Cliquez avec le bouton droit sur le contrôle, puis sélectionnez **Nouveau** > **Groupe** pour ajouter un nouveau contrôle de groupe d'écrans.</span><span class="sxs-lookup"><span data-stu-id="41050-148">Right-click the control, and then select **New** > **Group** to add a new form group control.</span></span>
13. <span data-ttu-id="41050-149">Renommez le groupe d'écrans avec un nom évocateur, tel que **powerBIReportGroup**.</span><span class="sxs-lookup"><span data-stu-id="41050-149">Rename the form group to something meaningful, such as **powerBIReportGroup**.</span></span>
14. <span data-ttu-id="41050-150">Dans le concepteur d'écrans, sélectionnez **PanoramaBody (onglet)**, puis faites glisser le contrôle dans l'onglet **Espace de travail**.</span><span class="sxs-lookup"><span data-stu-id="41050-150">In the form designer, select **PanoramaBody (Tab)**, and then drag the control onto the **Workspace** tab.</span></span>
15. <span data-ttu-id="41050-151">Dans la définition de conception, sélectionnez l'élément supérieur qui est libellé **Mise en page | Modèle : Workspace Operational**.</span><span class="sxs-lookup"><span data-stu-id="41050-151">In the design definition, select the top element that is labeled **Design | Pattern: Workspace Operational**.</span></span>
16. <span data-ttu-id="41050-152">Cliquez avec le bouton droit et sélectionnez la page **Supprimer le modèle**.</span><span class="sxs-lookup"><span data-stu-id="41050-152">Right-click, and then select **Remove pattern**.</span></span>
17. <span data-ttu-id="41050-153">Cliquez avec le bouton droit de nouveau, puis sélectionnez **Ajouter un modèle** > **Espace de travail tabulé**.</span><span class="sxs-lookup"><span data-stu-id="41050-153">Right-click again, and then select **Add pattern** > **Workspace Tabbed**.</span></span>
18. <span data-ttu-id="41050-154">Créez un build pour vérifier vos modifications.</span><span class="sxs-lookup"><span data-stu-id="41050-154">Perform a build to verify your changes.</span></span>
 
<span data-ttu-id="41050-155">L'illustration suivante présente ce à quoi la conception ressemble une fois ces modifications appliquées.</span><span class="sxs-lookup"><span data-stu-id="41050-155">The following illustration shows what the design looks like after these changes are applied.</span></span>

![FMClerkWorkspace après des modifications](media/analytical-workspace-definition-after.png)

<span data-ttu-id="41050-157">Maintenant que vous avez ajouté des contrôles d'écrans qui seront utilisés pour inclure l'état de l'espace de travail, vous devez définir la taille du contrôle parent de sorte qu'il s'adapte à la mise en page.</span><span class="sxs-lookup"><span data-stu-id="41050-157">Now that you've added the form controls that will be used to embed the workspace report, you must define the size of the parent control so that it accommodates the layout.</span></span> <span data-ttu-id="41050-158">Par défaut, la page **Volet de filtres** et la page **Onglet** sont visibles sur l'état.</span><span class="sxs-lookup"><span data-stu-id="41050-158">By default, both the **Filters Pane** page and the **Tab** page will be visible on the report.</span></span> <span data-ttu-id="41050-159">Toutefois, vous pouvez modifier la visibilité de ces contrôles en fonction du client cible de l'état.</span><span class="sxs-lookup"><span data-stu-id="41050-159">However, you can change the visibility of these controls as appropriate for the target consumer of the report.</span></span>
 
> [!NOTE]
> <span data-ttu-id="41050-160">Pour les espaces de travail intégrés, nous vous recommandons d'utiliser des extensions pour masquer les pages **Volet de filtres** et **Onglet**, pour des raisons de cohérence.</span><span class="sxs-lookup"><span data-stu-id="41050-160">For embedded workspaces, we recommend that you use extensions to hide both the **Filters Pane** and **Tab** pages, for consistency.</span></span>
 
<span data-ttu-id="41050-161">Vous avez terminé la tâche d'extension de la définition d'écran d'application.</span><span class="sxs-lookup"><span data-stu-id="41050-161">You've now completed the task of extending the application form definition.</span></span> <span data-ttu-id="41050-162">Pour plus d'informations sur l'utilisation d'extensions pour effectuer des personnalisations, voir [Personnalisation : superposition de couches et extensions](../extensibility/customization-overlayering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="41050-162">For more information about how to use extensions to do customizations, see  [Customization: Overlayering and extensions](../extensibility/customization-overlayering-extensions.md).</span></span>

## <a name="add-x-business-logic-to-embed-a-viewer-control"></a><span data-ttu-id="41050-163">Ajoutez la logique métier X++ pour inclure un contrôle de la visionneuse</span><span class="sxs-lookup"><span data-stu-id="41050-163">Add X++ business logic to embed a viewer control</span></span>
<span data-ttu-id="41050-164">Procédez comme suit pour ajouter une logique métier qui initialise le contrôle de la visionneuse de rapports qui est intégrée à l'espace de travail **Gestion des réservations**.</span><span class="sxs-lookup"><span data-stu-id="41050-164">Follow these steps to add business logic that initializes the report viewer control that is embedded in the **Reservation management** workspace.</span></span>

1. <span data-ttu-id="41050-165">Ouvrez le concepteur d'écran **FMClerkWorkspace** pour étendre la définition de conception.</span><span class="sxs-lookup"><span data-stu-id="41050-165">Open the **FMClerkWorkspace** form designer to extend the design definition.</span></span>
2. <span data-ttu-id="41050-166">Appuyez sur F7 pour accéder au code derrière la définition du code.</span><span class="sxs-lookup"><span data-stu-id="41050-166">Press F7 to access the code behind the code definition.</span></span>
3. <span data-ttu-id="41050-167">Ajoutez le code X++ suivant :</span><span class="sxs-lookup"><span data-stu-id="41050-167">Add the following X++ code.</span></span>

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
                FMPBIWorkspaceController controller = new FMPBIWorkspaceController();
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

4. <span data-ttu-id="41050-168">Créez un build pour vérifier vos modifications.</span><span class="sxs-lookup"><span data-stu-id="41050-168">Perform a build to verify your changes.</span></span>

<span data-ttu-id="41050-169">Vous avez terminé la tâche d'ajouter une logique métier pour initialiser le contrôle de la visionneuse de rapports intégrée.</span><span class="sxs-lookup"><span data-stu-id="41050-169">You've now completed the task of adding business logic to initialize the embedded report viewer control.</span></span> <span data-ttu-id="41050-170">L'illustration suivante présente ce à quoi l'espace de travail ressemble une fois ces modifications appliquées.</span><span class="sxs-lookup"><span data-stu-id="41050-170">The following illustration shows what the workspace looks like after these changes are applied.</span></span>

![État intégré à l'espace de travail](media/analytical-workspace-final.png)

> [!NOTE]
> <span data-ttu-id="41050-172">Vous pouvez accéder à la vue opérationnelle existante à l'aide des onglets de l'espace de travail sous le titre de la page.</span><span class="sxs-lookup"><span data-stu-id="41050-172">You can access the existing operational view by using the workspace tabs below the page title.</span></span>

## <a name="reference"></a><span data-ttu-id="41050-173">Référence</span><span class="sxs-lookup"><span data-stu-id="41050-173">Reference</span></span>

### <a name="pbireporthelperinitializereportcontrol-method"></a><span data-ttu-id="41050-174">Méthode PBIReportHelper.initializeReportControl</span><span class="sxs-lookup"><span data-stu-id="41050-174">PBIReportHelper.initializeReportControl method</span></span>
<span data-ttu-id="41050-175">Cette section fournit des informations sur la classe d'aide utilisée pour inclure un état Power BI (ressource .pbix) à un contrôle de groupe d'écrans.</span><span class="sxs-lookup"><span data-stu-id="41050-175">This section provides information about the helper class that is used to embed a Power BI report (.pbix resource) in a form group control.</span></span>

#### <a name="syntax"></a><span data-ttu-id="41050-176">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="41050-176">Syntax</span></span>
```
public static void initializeReportControl(
     str                 _resourceName,
     FormGroupControl    _formGroupControl,
     str                 _defaultPageName = '',
     boolean             _showFilterPane = false,
     boolean             _showNavPane = false,
     List                _defaultFilters = new List(Types::Class))
```

#### <a name="parameters"></a><span data-ttu-id="41050-177">Paramètres</span><span class="sxs-lookup"><span data-stu-id="41050-177">Parameters</span></span>

| <span data-ttu-id="41050-178">Nom</span><span class="sxs-lookup"><span data-stu-id="41050-178">Name</span></span> | <span data-ttu-id="41050-179">Description</span><span class="sxs-lookup"><span data-stu-id="41050-179">Description</span></span> |
|---|---|
| <span data-ttu-id="41050-180">resourceName</span><span class="sxs-lookup"><span data-stu-id="41050-180">resourceName</span></span> | <span data-ttu-id="41050-181">Nom de la ressource .pbix</span><span class="sxs-lookup"><span data-stu-id="41050-181">The name of the .pbix resource.</span></span> |
| <span data-ttu-id="41050-182">formGroupControl</span><span class="sxs-lookup"><span data-stu-id="41050-182">formGroupControl</span></span> | <span data-ttu-id="41050-183">Contrôle de groupe d'écrans auquel appliquer le contrôle de l'état Power BI.</span><span class="sxs-lookup"><span data-stu-id="41050-183">The form group control to apply the Power BI report control to.</span></span> |
| <span data-ttu-id="41050-184">defaultPageName</span><span class="sxs-lookup"><span data-stu-id="41050-184">defaultPageName</span></span> | <span data-ttu-id="41050-185">Nom de la page par défaut</span><span class="sxs-lookup"><span data-stu-id="41050-185">The default page name.</span></span> |
| <span data-ttu-id="41050-186">showFilterPane</span><span class="sxs-lookup"><span data-stu-id="41050-186">showFilterPane</span></span> | <span data-ttu-id="41050-187">Valeur booléenne qui indique si le volet de filtre doit être affiché (**vrai**) ou masqué (**faux**).</span><span class="sxs-lookup"><span data-stu-id="41050-187">A Boolean value that indicates whether the filter pane should be shown (**true**) or hidden (**false**).</span></span> |
| <span data-ttu-id="41050-188">showNavPane</span><span class="sxs-lookup"><span data-stu-id="41050-188">showNavPane</span></span> | <span data-ttu-id="41050-189">Valeur booléenne qui indique si le volet de navigation doit être affiché (**vrai**) ou masqué (**faux**).</span><span class="sxs-lookup"><span data-stu-id="41050-189">A Boolean value that indicates whether the navigation pane should be shown (**true**) or hidden (**false**).</span></span> |
| <span data-ttu-id="41050-190">defaultFilters</span><span class="sxs-lookup"><span data-stu-id="41050-190">defaultFilters</span></span> | <span data-ttu-id="41050-191">Filtres par défaut pour l'état Power BI.</span><span class="sxs-lookup"><span data-stu-id="41050-191">The default filters for the Power BI report.</span></span> |

