---
title: Utilisation des mises en page prédéfinies
description: Cette rubrique décrit l'utilisation des dispositions prédéfinies dans Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c8149c6e443c77dabfa641a698c931176bedbc98
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002634"
---
# <a name="work-with-preset-layouts"></a><span data-ttu-id="3b377-103">Utilisation des mises en page prédéfinies</span><span class="sxs-lookup"><span data-stu-id="3b377-103">Work with preset layouts</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="3b377-104">Cette rubrique décrit l'utilisation des dispositions prédéfinies dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3b377-104">This topic describes how to work with preset layouts in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="3b377-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="3b377-105">Overview</span></span>

<span data-ttu-id="3b377-106">Avant d'exécuter les procédures décrites dans cette rubrique, assurez-vous de lire [Dispositions prédéfinies et personnalisées](templates-layouts-overview.md#preset-and-custom-layouts).</span><span class="sxs-lookup"><span data-stu-id="3b377-106">Before you complete the procedures in this topic, be sure to read [Preset and custom layouts](templates-layouts-overview.md#preset-and-custom-layouts).</span></span> <span data-ttu-id="3b377-107">Pour obtenir une vue d'ensemble générale, voir [Vue d'ensemble des modèles et dispositions](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3b377-107">For a general overview, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

## <a name="create-a-new-preset-layout"></a><span data-ttu-id="3b377-108">Créer une dispositions prédéfinie</span><span class="sxs-lookup"><span data-stu-id="3b377-108">Create a new preset layout</span></span>

<span data-ttu-id="3b377-109">Il existe deux méthodes pour créer une dispositions prédéfinie.</span><span class="sxs-lookup"><span data-stu-id="3b377-109">There are two methods for creating a preset layout.</span></span> <span data-ttu-id="3b377-110">Vous pouvez enregistrer une disposition personnalisée existante comme nouvelle disposition prédéfinie, ou créer une disposition prédéfinie créée de toutes pièces.</span><span class="sxs-lookup"><span data-stu-id="3b377-110">You can save an existing custom layout as a new preset layout, or you can create a preset layout from scratch.</span></span>

### <a name="create-a-preset-layout-from-an-existing-custom-layout"></a><span data-ttu-id="3b377-111">Créer une disposition prédéfinie à partir d'une disposition personnalisée existante</span><span class="sxs-lookup"><span data-stu-id="3b377-111">Create a preset layout from an existing custom layout</span></span>

<span data-ttu-id="3b377-112">Pour créer une disposition prédéfinie à partir d'une disposition personnalisée existante; procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3b377-112">To create a preset layout from an existing custom layout, follow these steps.</span></span>

1. <span data-ttu-id="3b377-113">Ouvrez une page existante qui n'utilise pas actuellement de disposition prédéfinie, et qui a une structure de module que vous souhaitez réutiliser pour d'autres pages sur votre site.</span><span class="sxs-lookup"><span data-stu-id="3b377-113">Open an existing page that doesn't currently use a preset layout, and that has a module structure that you want to reuse for other pages on your site.</span></span>
1. <span data-ttu-id="3b377-114">Sélectionnez **Caisse**.</span><span class="sxs-lookup"><span data-stu-id="3b377-114">Select **Check out**.</span></span>
1. <span data-ttu-id="3b377-115">Sélectionnez **Enregistrer comme nouvelle disposition**.</span><span class="sxs-lookup"><span data-stu-id="3b377-115">Select **Save as new layout**.</span></span> <span data-ttu-id="3b377-116">La boîte de dialogue **Enregistrer comme nouvelle disposition** apparaît.</span><span class="sxs-lookup"><span data-stu-id="3b377-116">The **Save as new layout** dialog box appears.</span></span>
1. <span data-ttu-id="3b377-117">Entrez un nom et une description pour la disposition prédéfinie.</span><span class="sxs-lookup"><span data-stu-id="3b377-117">Enter a name and description for your preset layout.</span></span> <span data-ttu-id="3b377-118">Les valeurs entrées sont affichées à d'autres auteurs lorsqu'ils créent des pages dans votre disposition ou passent à celle-ci.</span><span class="sxs-lookup"><span data-stu-id="3b377-118">The values that you enter will be shown to other authors when they create new pages from your layout or switch to it.</span></span> <span data-ttu-id="3b377-119">Entrez donc des valeurs qui sont utiles pour les auteurs de pages.</span><span class="sxs-lookup"><span data-stu-id="3b377-119">Therefore, enter values that will be useful to page authors.</span></span>
1. <span data-ttu-id="3b377-120">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3b377-120">Select **OK**.</span></span>

<span data-ttu-id="3b377-121">La disposition prédéfinie sera désormais disponible lorsque vous créez des pages ou sélectionnez une disposition différente pour une page dans la même hiérarchie de modèle.</span><span class="sxs-lookup"><span data-stu-id="3b377-121">The preset layout will now be available when you create new pages or select a different layout for a page in the same template hierarchy.</span></span>

> [!TIP]
> <span data-ttu-id="3b377-122">Pour afficher rapidement si une page spécifique est actuellement associée à une disposition prédéfinie, sélectionnez la page dans la vue de liste de page, et inspectez les métadonnées de mise en page dans le volet de propriété à droite.</span><span class="sxs-lookup"><span data-stu-id="3b377-122">To quickly see whether a specific page is currently bound to a preset layout, select the page in the pages list view, and inspect the layout metadata in the property pane on the right.</span></span>

### <a name="create-a-new-preset-layout"></a><span data-ttu-id="3b377-123">Créer une dispositions prédéfinie</span><span class="sxs-lookup"><span data-stu-id="3b377-123">Create a new preset layout</span></span>

<span data-ttu-id="3b377-124">Pour créer une disposition prédéfinie de zéro, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3b377-124">To create a preset layout from scratch, follow these steps.</span></span>

1. <span data-ttu-id="3b377-125">Dans le volet de navigation sur la gauche, sélectionnez **Dispositions**.</span><span class="sxs-lookup"><span data-stu-id="3b377-125">In the navigation pane on the left, select **Layouts**.</span></span>
1. <span data-ttu-id="3b377-126">Sélectionner **Nouvelle disposition**.</span><span class="sxs-lookup"><span data-stu-id="3b377-126">Select **New Layout**.</span></span> <span data-ttu-id="3b377-127">La boîte de dialogue **Nouvelle disposition** apparaît.</span><span class="sxs-lookup"><span data-stu-id="3b377-127">The **New layout** dialog box appears.</span></span>
1. <span data-ttu-id="3b377-128">Sélectionnez le modèle à utiliser pour une disposition prédéfinie.</span><span class="sxs-lookup"><span data-stu-id="3b377-128">Select the template to use for your preset layout.</span></span>
1. <span data-ttu-id="3b377-129">Entrez un nom et une description pour la disposition prédéfinie.</span><span class="sxs-lookup"><span data-stu-id="3b377-129">Enter a name and description for your preset layout.</span></span> <span data-ttu-id="3b377-130">Les valeurs entrées sont affichées à d'autres auteurs lorsqu'ils créent des pages dans votre disposition ou passent à celle-ci.</span><span class="sxs-lookup"><span data-stu-id="3b377-130">The values that you enter will be shown to other authors when they create new pages from your layout or switch to it.</span></span> <span data-ttu-id="3b377-131">Entrez donc des valeurs qui sont utiles pour les auteurs de pages.</span><span class="sxs-lookup"><span data-stu-id="3b377-131">Therefore, enter values that will be useful to page authors.</span></span>
1. <span data-ttu-id="3b377-132">Sélectionnez **OK** pour créer une disposition prédéfinie et ouvrir l'éditeur de disposition.</span><span class="sxs-lookup"><span data-stu-id="3b377-132">Select **OK** to create the new preset layout and open the layout editor.</span></span>
1. <span data-ttu-id="3b377-133">Dans l'éditeur de disposition, ajoutez et configurez les modules à l'aide de l'arborescence de contour à gauche et du volet de propriété à droite.</span><span class="sxs-lookup"><span data-stu-id="3b377-133">In the layout editor, add and configure modules by using the outline tree on the left and the property pane on the right.</span></span> <span data-ttu-id="3b377-134">(Le processus est semblable à celui pour ajouter et configurer des modules pour un modèle dans l'éditeur de modèle.) L'organisation des modules et de tous les paramètres par défaut verrouillés devient la configuration de module centralisée pour toutes les pages qui utilisent cette disposition prédéfinie.</span><span class="sxs-lookup"><span data-stu-id="3b377-134">(The process resembles the process for adding and configuring modules for a template in the template editor.) The arrangement of modules and any locked default settings become the centralized module configuration for any pages that use this preset layout.</span></span>

## <a name="modify-a-preset-layout"></a><span data-ttu-id="3b377-135">Modification d'une disposition prédéfinie</span><span class="sxs-lookup"><span data-stu-id="3b377-135">Modify a preset layout</span></span>

<span data-ttu-id="3b377-136">Pour modifier une disposition prédéfinie, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3b377-136">To modify a preset layout, follow these steps.</span></span>

1. <span data-ttu-id="3b377-137">Dans le volet de navigation sur la gauche, sélectionnez **Dispositions**.</span><span class="sxs-lookup"><span data-stu-id="3b377-137">In the navigation pane on the left, select **Layouts**.</span></span>
1. <span data-ttu-id="3b377-138">Dans l'éditeur de disposition, dans l'arborescence de contour à gauche, sélectionnez le module à modifier.</span><span class="sxs-lookup"><span data-stu-id="3b377-138">In the layout editor, in the outline tree on the left, select the module to modify.</span></span> <span data-ttu-id="3b377-139">Suivez ensuite l'une des procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="3b377-139">Then follow any of these steps:</span></span>

    - <span data-ttu-id="3b377-140">Pour déplacer un module vers le haut ou vers le bas à l'intérieur de son parent, sélectionnez le bouton représentant des points de suspension (**...**) pour le module, puis sélectionnez **Déplacer vers le haut** ou **Déplacer vers le bas**.</span><span class="sxs-lookup"><span data-stu-id="3b377-140">To move a module up or down inside its parent, select the ellipsis button (**...**) for the module, and then select **Move up** or **Move down**.</span></span>
    - <span data-ttu-id="3b377-141">Pour modifier les paramètres par défaut d'un module, utilisez le volet de propriété pour entrer des valeurs par défaut et les verrouiller (facultatif) pour toutes les pages en aval.</span><span class="sxs-lookup"><span data-stu-id="3b377-141">To change a module's default settings, use the property pane to enter default values and optionally lock them for all downstream pages.</span></span>
    - <span data-ttu-id="3b377-142">Pour ajouter de nouveaux modules ou fragments aux modules de conteneur, sélectionnez le bouton représentant des points de suspension, puis sélectionnez **Ajouter un module** ou **Ajouter un fragment**.</span><span class="sxs-lookup"><span data-stu-id="3b377-142">To add new modules or fragments to container modules, select the ellipsis button, and then select **Add module** or **Add fragment**.</span></span>
    - <span data-ttu-id="3b377-143">Pour supprimer un module de la disposition, sélectionnez le bouton représentant des points de suspension, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="3b377-143">To remove a module from the layout, select the ellipsis button, and then select **Delete**.</span></span>

## <a name="change-a-preset-layout-theme"></a><span data-ttu-id="3b377-144">Modification d'un thème de disposition prédéfinie</span><span class="sxs-lookup"><span data-stu-id="3b377-144">Change a preset layout theme</span></span>

<span data-ttu-id="3b377-145">Une pratique typique consiste à définir un thème par défaut pour toutes les pages qui utilisent une disposition prédéfinie.</span><span class="sxs-lookup"><span data-stu-id="3b377-145">A typical practice is to set a default theme for all pages that use a preset layout.</span></span>

<span data-ttu-id="3b377-146">Pour définir ou modifier le thème pour toutes les pages enfants qui utilisent une disposition prédéfinie, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3b377-146">To set or change the theme for all child pages that use your preset layout, follow these steps.</span></span>

1. <span data-ttu-id="3b377-147">Dans l'éditeur de disposition, dans l'arborescence de contour à gauche, sélectionnez le module de conteneur de page.</span><span class="sxs-lookup"><span data-stu-id="3b377-147">In the layout editor, in the outline tree on the left, select the page container module.</span></span> <span data-ttu-id="3b377-148">(Généralement, ce module est le deuxième nœud et est appelé **Page par défaut**.)</span><span class="sxs-lookup"><span data-stu-id="3b377-148">(Typically, this module is the second node and is named **Default page**.)</span></span>
1. <span data-ttu-id="3b377-149">Dans le volet de propriété de droite, dans le champ **Thème**, sélectionnez un thème.</span><span class="sxs-lookup"><span data-stu-id="3b377-149">In the property pane on the right, in the **Theme** field, select a theme.</span></span>

## <a name="save-check-in-preview-and-publish-a-preset-layout"></a><span data-ttu-id="3b377-150">Enregistrer, archiver, afficher un aperçu et publier une disposition prédéfinie</span><span class="sxs-lookup"><span data-stu-id="3b377-150">Save, check in, preview, and publish a preset layout</span></span>

<span data-ttu-id="3b377-151">Pour enregistrer et archiver dans votre disposition prédéfinie, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3b377-151">To save and check in your preset layout, follow these steps.</span></span>

1. <span data-ttu-id="3b377-152">Sélectionnez **Enregistrer** en haut de l'éditeur de disposition.</span><span class="sxs-lookup"><span data-stu-id="3b377-152">Select **Save** at the top of the layout editor.</span></span> <span data-ttu-id="3b377-153">Les modifications enregistrées n'affectent pas les pages en aval tant qu'elles ne sont pas archivées.</span><span class="sxs-lookup"><span data-stu-id="3b377-153">Saved changes don't affect downstream pages until they are checked in.</span></span>
1. <span data-ttu-id="3b377-154">Sélectionnez **Archiver**.</span><span class="sxs-lookup"><span data-stu-id="3b377-154">Select **Check In**.</span></span> <span data-ttu-id="3b377-155">Vos modifications sont désormais découvrables pour les workflows en aval.</span><span class="sxs-lookup"><span data-stu-id="3b377-155">Your changes are now discoverable for downstream workflows.</span></span>

<span data-ttu-id="3b377-156">Pour afficher les modifications en aperçu, ouvrez une page existante qui utilise la disposition prédéfinie ou créez une page à partir de la disposition.</span><span class="sxs-lookup"><span data-stu-id="3b377-156">To preview your changes, either open an existing page that uses the preset layout or create a new page from the layout.</span></span>

<span data-ttu-id="3b377-157">Après avoir prévisualisé les modifications de votre disposition prédéfinie, suivez l'une de ces étapes pour publier la disposition sur votre site en direct :</span><span class="sxs-lookup"><span data-stu-id="3b377-157">After you've previewed the changes to your preset layout, follow one of these steps to publish the layout to your live site:</span></span>

* <span data-ttu-id="3b377-158">Accédez à **Dispositions**, sélectionnez la disposition, puis sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="3b377-158">Go to **Layouts**, select the layout, and then select **Publish**.</span></span>
* <span data-ttu-id="3b377-159">Dans l'éditeur de disposition, sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="3b377-159">In the layout editor, select **Publish**.</span></span>
* <span data-ttu-id="3b377-160">Publiez une page qui référence la disposition non publiée.</span><span class="sxs-lookup"><span data-stu-id="3b377-160">Publish a page that references the unpublished layout.</span></span> <span data-ttu-id="3b377-161">La disposition est automatiquement publiée.</span><span class="sxs-lookup"><span data-stu-id="3b377-161">The layout will automatically be published.</span></span>

> [!WARNING]
> <span data-ttu-id="3b377-162">Les dispositions prédéfinies peuvent être référencées par plusieurs pages.</span><span class="sxs-lookup"><span data-stu-id="3b377-162">Preset layouts can be referenced by multiple pages.</span></span> <span data-ttu-id="3b377-163">Lorsque vous publiez une disposition prédéfinie, notez que vous pouvez affecter la disposition de plusieurs pages.</span><span class="sxs-lookup"><span data-stu-id="3b377-163">When you publish a preset layout, be aware that you might affect the layout of multiple pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3b377-164">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="3b377-164">Additional resources</span></span>

[<span data-ttu-id="3b377-165">Vue d'ensemble des modèles et dispositions</span><span class="sxs-lookup"><span data-stu-id="3b377-165">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="3b377-166">Utiliser des modèles</span><span class="sxs-lookup"><span data-stu-id="3b377-166">Work with templates</span></span>](work-with-templates.md)
