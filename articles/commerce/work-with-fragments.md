---
title: Utiliser des fragments
description: Cette rubrique décrit le pourquoi, quand et comment utiliser des fragments dans Microsoft Dynamics 365 Commerce.
author: v-chgri
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
ms.search.industry: retail
ms.author: phinneyridge
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d92b9077f8584bfa0710bbaacbc7caa3220baa4a
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698094"
---
# <a name="work-with-fragments"></a><span data-ttu-id="921b3-103">Utiliser des fragments</span><span class="sxs-lookup"><span data-stu-id="921b3-103">Work with fragments</span></span> 

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="921b3-104">Cette rubrique décrit le pourquoi, quand et comment utiliser des fragments dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="921b3-104">This topic describes why, when, and how to use fragments in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="921b3-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="921b3-105">Overview</span></span>

<span data-ttu-id="921b3-106">Les fragments permettent une expérience de création centralisée pour les configurations du module qui doivent être réutilisées dans tout votre site.</span><span class="sxs-lookup"><span data-stu-id="921b3-106">Fragments allow for a centralized authoring experience for module configurations that must be reused throughout your site.</span></span> <span data-ttu-id="921b3-107">Par exemple, les en-têtes, les pieds de page, et les bannières sont souvent configurés comme fragments, car ils sont partagés entre la plupart des pages.</span><span class="sxs-lookup"><span data-stu-id="921b3-107">For example, headers, footers, and banners are often configured as fragments, because they are shared across many pages.</span></span> <span data-ttu-id="921b3-108">Vous pouvez imaginer les fragments comme des pages web miniatures pouvant être insérées dans d'autres pages sur votre site.</span><span class="sxs-lookup"><span data-stu-id="921b3-108">You can think of fragments as miniature webpages that can be inserted into other pages on your site.</span></span> <span data-ttu-id="921b3-109">Les fragments ont leur propre cycle de vie.</span><span class="sxs-lookup"><span data-stu-id="921b3-109">Fragments have their own lifecycle.</span></span> <span data-ttu-id="921b3-110">En d'autres termes, ils sont créés, référencés, mis à jour et supprimés comme des entités indépendantes dans les outils de création.</span><span class="sxs-lookup"><span data-stu-id="921b3-110">In other words, they are created, referenced, updated, and deleted as independent entities in the authoring tools.</span></span>

<span data-ttu-id="921b3-111">Une fois les fragments configurés, ils peuvent être utilisés chaque fois que des modules peuvent être utilisés dans votre structure de site.</span><span class="sxs-lookup"><span data-stu-id="921b3-111">After fragments are configured, they can be used wherever modules can be used in your site structure.</span></span> <span data-ttu-id="921b3-112">Les fragments peuvent être référencés dans les pages, dans les dispositions, dans les modèles, et dans d'autres fragments.</span><span class="sxs-lookup"><span data-stu-id="921b3-112">Fragments can be referenced on pages, in layouts, in templates, and in other fragments.</span></span>

> [!NOTE]
> <span data-ttu-id="921b3-113">Les fragments peuvent être imbriqués jusqu'à sept niveaux de profondeur à l'intérieur d'autres fragments.</span><span class="sxs-lookup"><span data-stu-id="921b3-113">Fragments can be nested up to seven levels deep inside other fragments.</span></span>

<span data-ttu-id="921b3-114">Par exemple, si vous souhaitez promouvoir un événement saisonnier entre de nombreux pages de notre site, vous pouvez utiliser un fragment.</span><span class="sxs-lookup"><span data-stu-id="921b3-114">For example, if you want to promote a seasonal event cross many pages on our site, you can use a fragment.</span></span> <span data-ttu-id="921b3-115">La première étape du processus de création d'un fragment est de sélectionner le type du module à partir duquel démarrer.</span><span class="sxs-lookup"><span data-stu-id="921b3-115">The first step in the process of creating a new fragment is to select the type of module that you want to start from.</span></span> <span data-ttu-id="921b3-116">Par exemple, vous pouvez créer le fragment à partir d'un module de bannière.</span><span class="sxs-lookup"><span data-stu-id="921b3-116">For this example, you can build the fragment from a hero module.</span></span>

> [!NOTE]
> <span data-ttu-id="921b3-117">Les fragments peuvent être établis à partir de n'importe quel type de module.</span><span class="sxs-lookup"><span data-stu-id="921b3-117">Fragments can be built from any module type.</span></span>

<span data-ttu-id="921b3-118">Vous pouvez ensuite configurer le fragment de bannière avec votre contenu promotionnel spécifique.</span><span class="sxs-lookup"><span data-stu-id="921b3-118">You can then configure the hero fragment with your specific promotional content.</span></span> <span data-ttu-id="921b3-119">Vous pouvez également le localiser au besoin.</span><span class="sxs-lookup"><span data-stu-id="921b3-119">You can also localize it as you require.</span></span> <span data-ttu-id="921b3-120">Le nouveau fragment de bannière autonome peut ensuite être utilisé comme module préconfiguré dans tout votre site.</span><span class="sxs-lookup"><span data-stu-id="921b3-120">The new stand-alone hero fragment can then be consumed as a preconfigured module throughout your site.</span></span> <span data-ttu-id="921b3-121">Vous pouvez facilement l'ajouter aux modèles, à des pages spécifiques, ou à d'autres fragments qui peuvent contenir des modules de bannière.</span><span class="sxs-lookup"><span data-stu-id="921b3-121">You can easily add it to templates, to specific pages, or to other fragments that can contain hero modules.</span></span>

<span data-ttu-id="921b3-122">Tous les emplacements où le fragment est ajouté sont des références au fragment central de bannière que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="921b3-122">All the places where the fragment is added are references to the central hero fragment that you created.</span></span> <span data-ttu-id="921b3-123">Si vous sortez des modifications dans le fragment, ces modifications sont immédiatement répercutées à tous les emplacements où le fragment est mentionné dans le site.</span><span class="sxs-lookup"><span data-stu-id="921b3-123">If you publish changes to the fragment, those changes are immediately reflected in all the places where the fragment is referenced across the site.</span></span> <span data-ttu-id="921b3-124">Par conséquent, les fragments sont un moyen puissant et efficace de réutiliser et de gérer centralement des configurations de module dans un site.</span><span class="sxs-lookup"><span data-stu-id="921b3-124">Therefore, fragments provide a powerful and efficient way to reuse and centrally manage module configurations on a site.</span></span> <span data-ttu-id="921b3-125">En les utilisant efficacement, vous pouvez augmenter de façon importante l'agilité et minimiser le coût associé à la gestion du contenu du site.</span><span class="sxs-lookup"><span data-stu-id="921b3-125">By effectively using them, you can significantly increase agility and help reduce the cost that is associated with managing site content.</span></span>

<span data-ttu-id="921b3-126">L'illustration ci-dessous indique comment des fragments peuvent être utilisés pour centraliser la création de configurations de module partagées dans un site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="921b3-126">The following illustration shows how fragments can be used to centralize authoring of shared module configurations across an e-Commerce site.</span></span>

![Une illustration affichant comment des fragments peuvent être utilisés pour centraliser la création de configurations de module partagées dans un site de commerce électronique](./media/fragment-figure1.png)

## <a name="create-a-fragment"></a><span data-ttu-id="921b3-128">Créer un fragment</span><span class="sxs-lookup"><span data-stu-id="921b3-128">Create a fragment</span></span>

<span data-ttu-id="921b3-129">Vous pouvez créer un fragment ou enregistrer une configuration de module existante comme fragment.</span><span class="sxs-lookup"><span data-stu-id="921b3-129">You can either create a new fragment or save an existing module configuration as a fragment.</span></span>

### <a name="create-a-new-fragment"></a><span data-ttu-id="921b3-130">Créer un fragment</span><span class="sxs-lookup"><span data-stu-id="921b3-130">Create a new fragment</span></span>

<span data-ttu-id="921b3-131">Pour créer un fragment, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="921b3-131">To create a new fragment, follow these steps.</span></span>

1. <span data-ttu-id="921b3-132">Dans le volet de navigation sur la gauche, sélectionnez **Fragments**.</span><span class="sxs-lookup"><span data-stu-id="921b3-132">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="921b3-133">Sélectionnez **Nouveau fragment de page**.</span><span class="sxs-lookup"><span data-stu-id="921b3-133">Select **New Page Fragment**.</span></span> <span data-ttu-id="921b3-134">Une boîte de dialogue apparaît qui indique tous les types de modules disponibles.</span><span class="sxs-lookup"><span data-stu-id="921b3-134">A dialog box appears that shows all the available module types.</span></span> <span data-ttu-id="921b3-135">Comme mentionné précédemment, les fragments peuvent être créés à partir de n'importe quel type de module.</span><span class="sxs-lookup"><span data-stu-id="921b3-135">As was mentioned earlier, fragments can be created from any module type.</span></span>
1. <span data-ttu-id="921b3-136">Sélectionnez un type de module pour votre fragment, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="921b3-136">Select a module type for your fragment, and then select **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="921b3-137">Si vous sélectionnez le type générique de module de conteneur, vous obtenez la plus grande flexibilité lorsque vous devez mettre à jour et configurer votre fragment ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="921b3-137">By selecting a generic container module type, you get the most flexibility when you must update and configure your fragment later.</span></span>

### <a name="save-an-existing-module-configuration-as-a-fragment"></a><span data-ttu-id="921b3-138">Enregistrez une configuration de module existante comme fragment</span><span class="sxs-lookup"><span data-stu-id="921b3-138">Save an existing module configuration as a fragment</span></span>

<span data-ttu-id="921b3-139">Pour convertir un module précédemment configuré en un fragment réutilisable, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="921b3-139">To convert a previously configured module to a reusable fragment, follow these steps.</span></span>

1. <span data-ttu-id="921b3-140">Ouvrez une page ou un modèle contenant le module que vous souhaitez convertir en un fragment.</span><span class="sxs-lookup"><span data-stu-id="921b3-140">Open a page or template that contains the module that you want to convert to a fragment.</span></span>
1. <span data-ttu-id="921b3-141">Dans le volet de contour à gauche, sélectionnez le bouton représentant des points de suspension (**...**) en regard du nom du module, puis sélectionnez **Enregistrer comme fragment**.</span><span class="sxs-lookup"><span data-stu-id="921b3-141">In the outline pane on the left, select the ellipsis button (**...**) next to the name of the module, and then select **Save as Fragment**.</span></span> <span data-ttu-id="921b3-142">Une boîte de dialogue s'affiche.</span><span class="sxs-lookup"><span data-stu-id="921b3-142">A dialog box appears.</span></span>
1. <span data-ttu-id="921b3-143">Entrez un nom et les métadonnées du fragment.</span><span class="sxs-lookup"><span data-stu-id="921b3-143">Enter a name and metadata for the fragment.</span></span>
1. <span data-ttu-id="921b3-144">Sélectionnez **OK** pour enregistrer la configuration du module comme fragment qui peut être ajouté à d'autres pages.</span><span class="sxs-lookup"><span data-stu-id="921b3-144">Select **OK** to save the module configuration as a fragment that can be added to other pages.</span></span>

## <a name="add-remove-or-edit-fragments-on-a-page"></a><span data-ttu-id="921b3-145">Ajouter, supprimer ou modifier des fragments sur une page</span><span class="sxs-lookup"><span data-stu-id="921b3-145">Add, remove, or edit fragments on a page</span></span>

<span data-ttu-id="921b3-146">Les procédures suivantes expliquent comment ajouter, supprimer, et modifier des fragments.</span><span class="sxs-lookup"><span data-stu-id="921b3-146">The following procedures describe how to add, remove, and edit fragments.</span></span>

### <a name="add-a-fragment"></a><span data-ttu-id="921b3-147">Ajouter un fragment</span><span class="sxs-lookup"><span data-stu-id="921b3-147">Add a fragment</span></span>

<span data-ttu-id="921b3-148">Pour ajouter un fragment à une page, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="921b3-148">To add a fragment to a page, follow these steps.</span></span>

1. <span data-ttu-id="921b3-149">Dans le volet de contour à gauche, sélectionnez un conteneur ou un emplacement auquel les modules enfants peuvent être ajoutés.</span><span class="sxs-lookup"><span data-stu-id="921b3-149">In the outline pane on the left, select a container or slot that child modules can be added to.</span></span>
1. <span data-ttu-id="921b3-150">Sélectionnez le bouton représentant des points de suspension en regard du nom du conteneur ou de l'emplacement, et sélectionnez **Ajouter un fragment**.</span><span class="sxs-lookup"><span data-stu-id="921b3-150">Select the ellipsis button next to the name of the container or slot, and then select **Add Fragment**.</span></span> <span data-ttu-id="921b3-151">Une boîte de dialogue s'affiche.</span><span class="sxs-lookup"><span data-stu-id="921b3-151">A dialog box appears.</span></span>

    > [!NOTE]
    > <span data-ttu-id="921b3-152">Si le conteneur ou l'emplacement ne prend pas en charge de nouveaux modules enfants, l'option **Ajouter un fragment** n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="921b3-152">If the container or slot doesn't support new child modules, the **Add Fragment** option is unavailable.</span></span>

1. <span data-ttu-id="921b3-153">Dans la boîte de dialogue, recherchez et sélectionnez un fragment à ajouter.</span><span class="sxs-lookup"><span data-stu-id="921b3-153">In the dialog box, search for and select a fragment to add.</span></span> <span data-ttu-id="921b3-154">Si aucun fragment disponible n'est répertorié, vous pouvez d'abord peut-être créer un fragment d'un type de module que le conteneur ou l'emplacement sélectionné prend en charge.</span><span class="sxs-lookup"><span data-stu-id="921b3-154">If no available fragments are listed, you might first have to create a fragment from a module type that the selected container or slot supports.</span></span>
1. <span data-ttu-id="921b3-155">Sélectionnez **OK** pour ajouter le fragment sélectionné au conteneur ou à l'emplacement sélectionné sur la page.</span><span class="sxs-lookup"><span data-stu-id="921b3-155">Select **OK** to add the selected fragment to the selected container or slot on your page.</span></span>

> [!NOTE]
> <span data-ttu-id="921b3-156">Les modules autorisés dans un conteneur ou un emplacement sont définis par le modèle de la page ou les propres définitions des modules.</span><span class="sxs-lookup"><span data-stu-id="921b3-156">The modules that are allowed in a container or slot are defined by the page's template or the modules' own definitions.</span></span>

### <a name="remove-a-fragment"></a><span data-ttu-id="921b3-157">Suppression d'un fragment</span><span class="sxs-lookup"><span data-stu-id="921b3-157">Remove a fragment</span></span>

<span data-ttu-id="921b3-158">Pour supprimer un fragment d'un emplacement ou d'un conteneur sur une page, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="921b3-158">To remove a fragment from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="921b3-159">Dans le volet de contour à gauche, sélectionnez le bouton représentant des points de suspension en regard du nom du fragment à supprimer, puis sélectionnez le bouton de corbeille.</span><span class="sxs-lookup"><span data-stu-id="921b3-159">In the outline pane on the left, select the ellipsis button next to the name of the fragment to remove, and then select the trash can button.</span></span>
1. <span data-ttu-id="921b3-160">Lorsque vous êtes invité à confirmer la suppression du fragment, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="921b3-160">When you're prompted to confirm that you want to remove the fragment, select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="921b3-161">Lorsque vous supprimez un fragment d'une page, vous en supprimez immédiatement la référence sur cette page.</span><span class="sxs-lookup"><span data-stu-id="921b3-161">When you remove a fragment from a page, you just remove the reference to it from that page.</span></span> <span data-ttu-id="921b3-162">Vous ne supprimez **pas** le fragment de votre site.</span><span class="sxs-lookup"><span data-stu-id="921b3-162">You do **not** delete the fragment from your site.</span></span> <span data-ttu-id="921b3-163">Pour supprimer des fragments de votre site, vous devez utiliser l'interface utilisateur (UI) de l'inspecteur de fragment.</span><span class="sxs-lookup"><span data-stu-id="921b3-163">To delete fragments from your site, you must use the fragment inspector user interface (UI).</span></span> <span data-ttu-id="921b3-164">Vous pouvez supprimer des fragments d'un site que si ils ne sont actuellement référencés par des pages, modèles, ou d'autres fragments.</span><span class="sxs-lookup"><span data-stu-id="921b3-164">You can delete fragments from a site only if they aren't currently referenced by any pages, templates, or other fragments.</span></span>

### <a name="edit-a-fragment"></a><span data-ttu-id="921b3-165">Modifier un fragment</span><span class="sxs-lookup"><span data-stu-id="921b3-165">Edit a fragment</span></span>

<span data-ttu-id="921b3-166">Pour modifier des fragments, vous devez utiliser l'interface utilisateur de l'éditeur de fragment.</span><span class="sxs-lookup"><span data-stu-id="921b3-166">To edit fragments, you must use the fragment editor UI.</span></span> <span data-ttu-id="921b3-167">Cette restriction est faite exprès.</span><span class="sxs-lookup"><span data-stu-id="921b3-167">This restriction is by design.</span></span> <span data-ttu-id="921b3-168">Elle permet de garantir que les auteurs ne confondent pas le processus de modifier les modules pour une page spécifique avec le processus de modification des fragments qui peuvent être partagés entre plusieurs de pages.</span><span class="sxs-lookup"><span data-stu-id="921b3-168">It helps guarantee that authors don't confuse the process of editing the modules for a specific page with the process of editing fragments that might be shared across many pages.</span></span>

<span data-ttu-id="921b3-169">Pour modifier un fragment, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="921b3-169">To edit a fragment, follow these steps.</span></span>

1. <span data-ttu-id="921b3-170">Dans le volet de navigation sur la gauche, sélectionnez **Fragments**.</span><span class="sxs-lookup"><span data-stu-id="921b3-170">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="921b3-171">Sous **Fragments**, sélectionnez le fragment à modifier.</span><span class="sxs-lookup"><span data-stu-id="921b3-171">Under **Fragments**, select the fragment to edit.</span></span>
1. <span data-ttu-id="921b3-172">Modifiez les propriétés et la structure du module du fragment comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="921b3-172">Edit the fragment's module properties and structure as you require.</span></span> <span data-ttu-id="921b3-173">Le processus est semblable au processus de modification des modules sont modifiés dans la vue d'éditeur de page.</span><span class="sxs-lookup"><span data-stu-id="921b3-173">The process resembles the process for editing modules are edited in the page editor view.</span></span>

<span data-ttu-id="921b3-174">Vous pouvez également modifier un fragment en le sélectionnant dans une page, dans un modèle, ou un fragment parent, puis en sélectionnant **Modifier le fragment** dans le volet de propriétés à droite.</span><span class="sxs-lookup"><span data-stu-id="921b3-174">You can also edit a fragment by selecting it on a page, in a template, or in a parent fragment, and then selecting **Edit Fragment** in the properties pane on the right.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="921b3-175">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="921b3-175">Additional resources</span></span>

[<span data-ttu-id="921b3-176">Vue d'ensemble des modèles et dispositions</span><span class="sxs-lookup"><span data-stu-id="921b3-176">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="921b3-177">Utiliser des modèles</span><span class="sxs-lookup"><span data-stu-id="921b3-177">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="921b3-178">Utilisation des mises en page prédéfinies</span><span class="sxs-lookup"><span data-stu-id="921b3-178">Work with preset layouts</span></span>](work-with-layouts.md)
