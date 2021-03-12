---
title: Utiliser des modules
description: Cette rubrique décrit quand et comment utiliser des modules dans Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 89d95814e892e3afcb6514ab0d0219f7b08b9c63
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000457"
---
# <a name="work-with-modules"></a><span data-ttu-id="33076-103">Utiliser des modules</span><span class="sxs-lookup"><span data-stu-id="33076-103">Work with modules</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="33076-104">Cette rubrique décrit quand et comment utiliser des modules dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="33076-104">This topic describes how and when to use modules in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="33076-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="33076-105">Overview</span></span>

<span data-ttu-id="33076-106">Les modules sont des blocs élémentaires logiques qui constituent la structure de la page, et ils ont différentes fins et étendues.</span><span class="sxs-lookup"><span data-stu-id="33076-106">Modules are logical building blocks that make up your page structure, and they have various purposes and scopes.</span></span> <span data-ttu-id="33076-107">Certains modules sont des conteneurs de haut niveau, et leur seul objectif est de garder à jour et d’organiser les autres modules (modules enfants).</span><span class="sxs-lookup"><span data-stu-id="33076-107">Some modules are high-level containers, and their only purpose is to hold and organize other modules (child modules).</span></span> <span data-ttu-id="33076-108">D’autres modules, tels qu’un module de placement d’une image simple, à un objet très spécifique.</span><span class="sxs-lookup"><span data-stu-id="33076-108">Other modules, such as a simple image placement module, have a very specific purpose.</span></span> <span data-ttu-id="33076-109">D’autres modules, tels qu’un module de carrousel, se situe entre ces deux catégories.</span><span class="sxs-lookup"><span data-stu-id="33076-109">Other modules, such as a carousel module, fall somewhere between those two categories.</span></span>

<span data-ttu-id="33076-110">Par défaut, votre site Dynamics 365 Commerce inclut une bibliothèque de modules qui vous permet de réaliser la plupart des scénarios de base de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="33076-110">By default, your Dynamics 365 Commerce site includes a module library that lets you achieve most basic e-Commerce scenarios.</span></span> <span data-ttu-id="33076-111">Vous devez pouvoir construire un site de bout en bout de commerce électronique juste à l’aide de ces modules.</span><span class="sxs-lookup"><span data-stu-id="33076-111">You should be able to construct an end-to-end e-Commerce site just by using these modules.</span></span> <span data-ttu-id="33076-112">Toutefois, vous pouvez également souhaiter personnaliser ces modules ou générer de nouveaux modules, personnalisés pour les besoins spécifiques.</span><span class="sxs-lookup"><span data-stu-id="33076-112">However, you might also want to customize these modules or build new, custom modules for specific needs.</span></span> <span data-ttu-id="33076-113">Si vous souhaitez générer les modules personnalisés, un kit de développement logiciel (SDK) de conception de module est disponible pour créer une bibliothèque de modules personnalisée.</span><span class="sxs-lookup"><span data-stu-id="33076-113">If you want to build custom modules, a module design software development kit (SDK) is available to help you create a custom module library.</span></span>

## <a name="container-modules-and-slots"></a><span data-ttu-id="33076-114">Modules et emplacement de conteneur</span><span class="sxs-lookup"><span data-stu-id="33076-114">Container modules and slots</span></span>

<span data-ttu-id="33076-115">Comme précédemment évoqué, certains modules sont conçus pour mettre à jour les modules enfants.</span><span class="sxs-lookup"><span data-stu-id="33076-115">As was mentioned earlier, some modules are designed to hold child modules.</span></span> <span data-ttu-id="33076-116">Ces modules sont appelés *conteneurs*, et ils permettent des hiérarchies de modules imbriqués.</span><span class="sxs-lookup"><span data-stu-id="33076-116">These modules are known as *containers*, and they allow for hierarchies of nested modules.</span></span> <span data-ttu-id="33076-117">Les modules de conteneur incluent des *emplacements*.</span><span class="sxs-lookup"><span data-stu-id="33076-117">Container modules include *slots*.</span></span> <span data-ttu-id="33076-118">Les emplacements sont utilisés pour gérer la disposition et l’objectif des modules enfants dans le conteneur.</span><span class="sxs-lookup"><span data-stu-id="33076-118">Slots are used to handle the layout and purpose of child modules in the container.</span></span> <span data-ttu-id="33076-119">Un exemple est un module de conteneur de page de base (module de niveau supérieur pour toute page) qui définit plusieurs emplacements importantes :</span><span class="sxs-lookup"><span data-stu-id="33076-119">An example is a basic page container module (a top-level module for any page) that defines several important slots:</span></span>

- <span data-ttu-id="33076-120">Un emplacement d’en-tête</span><span class="sxs-lookup"><span data-stu-id="33076-120">A header slot</span></span>
- <span data-ttu-id="33076-121">Emplacement de sous-en-tête</span><span class="sxs-lookup"><span data-stu-id="33076-121">A sub-header slot</span></span>
- <span data-ttu-id="33076-122">Emplacement principal</span><span class="sxs-lookup"><span data-stu-id="33076-122">A main slot</span></span>
- <span data-ttu-id="33076-123">Un emplacement de pied de page</span><span class="sxs-lookup"><span data-stu-id="33076-123">A footer slot</span></span>
- <span data-ttu-id="33076-124">Emplacement de sous-pied de page</span><span class="sxs-lookup"><span data-stu-id="33076-124">A sub-footer slot</span></span>

<span data-ttu-id="33076-125">Le développeur du module définit ces emplacements, et détermine quels modules enfants et combien de modules enfants peuvent être placés directement à l’intérieur de celui-ci.</span><span class="sxs-lookup"><span data-stu-id="33076-125">The module's developer defines these slots, and determines which child modules and how many child modules can be put directly inside it.</span></span> <span data-ttu-id="33076-126">Par exemple, l’emplacement d’en-tête ne peut prendre en charge qu’un module de type **Module d’en-tête**, alors que l’emplacement du corps peut prendre en charge un nombre illimité de modules de tous types (sauf d’autres modules de conteneur de page).</span><span class="sxs-lookup"><span data-stu-id="33076-126">For example, the header slot might support only one module of the **Header Module** type, whereas the body slot might support an unlimited number of modules of any type (except other page container modules).</span></span>

<span data-ttu-id="33076-127">Dans les outils de création, les auteurs de page ne doivent pas savoir à l’avance quels modules peuvent et ne peuvent pas être placés dans chaque emplacement.</span><span class="sxs-lookup"><span data-stu-id="33076-127">In the authoring tools, page authors don't have to know in advance which modules can and can't be put in each slot.</span></span> <span data-ttu-id="33076-128">Lorsque des auteurs de page sélectionnent un emplacement puis essayent de sélectionner un module à ajouter à celui-ci, ils peuvent afficher une vue filtrée des types de modules pris en charge pour cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="33076-128">When page authors select a slot and then try to select a module to add to it, they see a filtered view of module types that are supported for that slot.</span></span>

## <a name="content-modules"></a><span data-ttu-id="33076-129">Modules de contenu</span><span class="sxs-lookup"><span data-stu-id="33076-129">Content modules</span></span>

<span data-ttu-id="33076-130">Les modules de contenus contiennent des éléments de contenu et multimédias, tels que le texte (par exemple, des titres, des paragraphes, ainsi que des liens) ou des références d’actifs (par exemple, des images, des vidéos, et des PDF).</span><span class="sxs-lookup"><span data-stu-id="33076-130">Content modules contain content and media elements, such as text (for example, headlines, paragraphs, and links) or asset references (for example, images, video, and PDFs).</span></span> <span data-ttu-id="33076-131">Les types de modules de contenu typiques incluent les modules de bloc de contenu, de bloc de texte et de bannière promotionnelle.</span><span class="sxs-lookup"><span data-stu-id="33076-131">Typical content module types include content block, text block, and promo banner modules.</span></span> <span data-ttu-id="33076-132">Les modules de ces trois types peuvent contenir du texte ou du multimédia, et ils n’exigent pas de module enfant pour rendre un événement visible dans une page.</span><span class="sxs-lookup"><span data-stu-id="33076-132">Modules of these three types can contain text or media, and they don't require any child modules to make something visible on a page.</span></span>

<span data-ttu-id="33076-133">La plupart des activités de création de page et de contenu standard et quotidiennes impliquent des modules de contenu, principalement car ces modules définissent le contenu réel qui s’affiche dans leurs modules parents de conteneur.</span><span class="sxs-lookup"><span data-stu-id="33076-133">The majority of typical, day-to-day page and content authoring activities involve content modules, primarily because these modules define the actual content that is rendered in their parent container modules.</span></span> <span data-ttu-id="33076-134">De nombreux modules de contenu sont disponibles, et ces modules sont généralement les dernières pièces que vous ajoutez à la hiérarchie d’une page de modules imbriqués.</span><span class="sxs-lookup"><span data-stu-id="33076-134">Many content modules are available, and these modules are typically the last pieces that you will add to a page's hierarchy of nested modules.</span></span>

<span data-ttu-id="33076-135">L’illustration ci-dessous indique comment les modules sont imbriqués dans des emplacements parents des modules de conteneur.</span><span class="sxs-lookup"><span data-stu-id="33076-135">The following illustration shows how modules are nested inside parent container module slots.</span></span>

![Imbrication de modules](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a><span data-ttu-id="33076-137">Ajouter ou supprimer des modules</span><span class="sxs-lookup"><span data-stu-id="33076-137">Add or remove modules</span></span>

<span data-ttu-id="33076-138">Les procédures suivantes expliquent comment ajouter, supprimer des modules.</span><span class="sxs-lookup"><span data-stu-id="33076-138">The following procedures describe how to add and remove modules.</span></span>

### <a name="add-a-module"></a><span data-ttu-id="33076-139">Ajouter un module</span><span class="sxs-lookup"><span data-stu-id="33076-139">Add a module</span></span>

<span data-ttu-id="33076-140">Pour ajouter un module à un emplacement ou à un conteneur sur une page, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="33076-140">To add a module to a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="33076-141">Dans le volet de contour à gauche ou directement dans le canevas principal, sélectionnez un conteneur ou un emplacement auquel un module enfant peut être ajouté.</span><span class="sxs-lookup"><span data-stu-id="33076-141">In the outline pane on the left or directly in the main canvas, select a container or slot to which a child module can be added.</span></span>

    > [!NOTE]
    > <span data-ttu-id="33076-142">Le concepteur de module définit la liste des types de modules qui peuvent être ajoutés à un emplacement spécifique du module.</span><span class="sxs-lookup"><span data-stu-id="33076-142">The module designer defines the list of modules types that can be added to a specific module slot.</span></span> <span data-ttu-id="33076-143">Les auteurs de modèles peuvent ensuite affiner les options autorisées de module pour assurer un optimisation de moteur de recherche (SEO) cohérente et un rendement de création pour toutes les pages qui sont créées à partir d’un modèle spécifique.</span><span class="sxs-lookup"><span data-stu-id="33076-143">Template authors can then refine the allowed module options to help guarantee consistent search engine optimization (SEO) and authoring efficiency for all the pages that are built from a specific template.</span></span> <span data-ttu-id="33076-144">Lors de l’ajout d’un module à un emplacement, la boîte de dialogue **Ajouter un module** est automatiquement filtrée afin d’afficher uniquement les modules pris en charge dans le conteneur ou l’emplacement sélectionné.</span><span class="sxs-lookup"><span data-stu-id="33076-144">When adding a module to a slot, the **Add Module** dialog box is automatically filtered so that it shows only modules that are supported in the selected container or slot.</span></span> <span data-ttu-id="33076-145">Cette liste des modules autorisés est déterminée par le modèle de la page ou la définition du module de conteneur.</span><span class="sxs-lookup"><span data-stu-id="33076-145">This list of allowed modules is determined by the page's template or the container's module definition.</span></span>

1. <span data-ttu-id="33076-146">Si vous utilisez le volet de contour, sélectionnez les points de suspension (**...**) à côté du nom du module, puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="33076-146">If using the outline pane, select the ellipsis (**...**) next to the module name, and then select **Add Module**.</span></span> <span data-ttu-id="33076-147">Si vous utilisez les contrôles directement dans le canevas, sélectionnez le symbole plus (**+**) dans un emplacement vide ou adjacent au module actuellement sélectionné, puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="33076-147">If using the controls directly within the canvas, select the plus symbol (**+**) in an empty slot or adjacent to the currently selected module, and then select **Add Module**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="33076-148">Si le conteneur ou l’emplacement ne prend pas en charge de nouveaux modules enfants, l’option **Ajouter un module** n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="33076-148">If a container or slot doesn't support new child modules, the **Add Module** option is unavailable.</span></span>

1. <span data-ttu-id="33076-149">Dans la boîte de dialogue **Ajouter un module**, sélectionnez un module à ajouter à votre page.</span><span class="sxs-lookup"><span data-stu-id="33076-149">In the **Add Module** dialog box, select a module to add to your page.</span></span>

    > [!TIP]
    > <span data-ttu-id="33076-150">**Bloc de contenu** est un bon type de module pour les débutants.</span><span class="sxs-lookup"><span data-stu-id="33076-150">**Content block** is a good module type for beginners to work with.</span></span>

1. <span data-ttu-id="33076-151">Sélectionnez **OK** pour ajouter le module sélectionné au conteneur ou à l’emplacement sélectionné sur la page.</span><span class="sxs-lookup"><span data-stu-id="33076-151">Select **OK** to add the selected module to the selected container or slot on your page.</span></span>

### <a name="remove-a-module"></a><span data-ttu-id="33076-152">Supprimer un module</span><span class="sxs-lookup"><span data-stu-id="33076-152">Remove a module</span></span>

<span data-ttu-id="33076-153">Pour supprimer un module d’un emplacement ou d’un conteneur sur une page, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="33076-153">To remove a module from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="33076-154">Dans le volet de contour à gauche, sélectionnez le bouton représentant des points de suspension (**...**) en regard du nom du module à supprimer, puis sélectionnez le symbole de corbeille.</span><span class="sxs-lookup"><span data-stu-id="33076-154">In the outline pane on the left, select the ellipsis (**...**) next to the name of the module to be removed, and then select the trash can symbol.</span></span> <span data-ttu-id="33076-155">Sinon, dans le canevas principal, vous pouvez sélectionner le symbole de corbeille dans la barre d’outils d’un module sélectionné.</span><span class="sxs-lookup"><span data-stu-id="33076-155">Alternately, in the main canvas you can select the trash can symbol on a selected module's toolbar.</span></span>
1. <span data-ttu-id="33076-156">Lorsque vous êtes invité à confirmer la suppression du module, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="33076-156">When prompted to confirm that you want to remove the module, select **OK**.</span></span>

## <a name="move-a-module-to-a-new-position"></a><span data-ttu-id="33076-157">Déplacer un module vers une nouvelle position</span><span class="sxs-lookup"><span data-stu-id="33076-157">Move a module to a new position</span></span>

<span data-ttu-id="33076-158">Pour déplacer un module vers une nouvelle position sur votre page, appliquez l’une des méthodes suivantes.</span><span class="sxs-lookup"><span data-stu-id="33076-158">To move a module to a new position within your page, use any of the following methods.</span></span>

### <a name="move-a-module-using-the-outline-pane"></a><span data-ttu-id="33076-159">Déplacer un module à l’aide du volet de contour</span><span class="sxs-lookup"><span data-stu-id="33076-159">Move a module using the outline pane</span></span>

<span data-ttu-id="33076-160">Pour déplacer un module à l’aide du volet de contour, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="33076-160">To move a module using the outline pane, follow these steps.</span></span>

1. <span data-ttu-id="33076-161">Sélectionnez et maintenez le module que vous souhaitez déplacer dans le volet de contour, puis faites glisser le module vers une nouvelle position dans le contour.</span><span class="sxs-lookup"><span data-stu-id="33076-161">Select and hold the module you want to move in the outline pane, then drag the module to a new position in the outline.</span></span> <span data-ttu-id="33076-162">La ligne bleue dans le contour et sur le canevas indique où le module peut être placé.</span><span class="sxs-lookup"><span data-stu-id="33076-162">The blue line in the outline and on the canvas indicates where the module can be placed.</span></span>
1. <span data-ttu-id="33076-163">Relâchez le module pour le déposer dans la nouvelle position.</span><span class="sxs-lookup"><span data-stu-id="33076-163">Release the module to drop it into the new position.</span></span>

### <a name="move-a-module-directly-within-the-canvas"></a><span data-ttu-id="33076-164">Déplacer un module directement dans le canevas</span><span class="sxs-lookup"><span data-stu-id="33076-164">Move a module directly within the canvas</span></span>

<span data-ttu-id="33076-165">Pour déplacer un module directement dans le canevas, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="33076-165">To move a module directly within the canvas, follow these steps.</span></span>

1. <span data-ttu-id="33076-166">Sélectionnez le module à déplacer dans le canevas.</span><span class="sxs-lookup"><span data-stu-id="33076-166">Select the module you want to move in the canvas.</span></span> 
1. <span data-ttu-id="33076-167">Sélectionnez une flèche pointant vers le haut ou vers le bas dans la barre d’outils du module, puis faites glisser la flèche vers une nouvelle position sur la page.</span><span class="sxs-lookup"><span data-stu-id="33076-167">Select either an upward or downward pointing arrow symbol in the module's toolbar, and then drag the arrow to a new position on the page.</span></span> <span data-ttu-id="33076-168">La ligne bleue sur le canevas et dans le contour indique où le module peut être placé.</span><span class="sxs-lookup"><span data-stu-id="33076-168">The blue line in the canvas and outline indicates where the module can be placed.</span></span> <span data-ttu-id="33076-169">Si un module ne peut pas être déplacé vers le haut ou vers le bas, ce symbole de flèche sera grisé.</span><span class="sxs-lookup"><span data-stu-id="33076-169">If a module cannot be moved up or down, that arrow symbol will be grayed out.</span></span> 
1. <span data-ttu-id="33076-170">Relâchez le module pour le déposer dans la nouvelle position.</span><span class="sxs-lookup"><span data-stu-id="33076-170">Release the module to drop it into the new position.</span></span>

### <a name="move-a-module-using-the-ellipsis-menu"></a><span data-ttu-id="33076-171">Déplacer un module à l’aide du menu de points de suspension</span><span class="sxs-lookup"><span data-stu-id="33076-171">Move a module using the ellipsis menu</span></span>

<span data-ttu-id="33076-172">Pour déplacer un module à l’aide du menu de points de suspension, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="33076-172">To move a module using the ellipsis menu, follow these steps.</span></span>

1. <span data-ttu-id="33076-173">Sélectionnez un module dans le contour ou sur le canevas.</span><span class="sxs-lookup"><span data-stu-id="33076-173">Select a module in either the outline or the canvas.</span></span>
1. <span data-ttu-id="33076-174">Sélectionnez les points de suspension (**...**) à côté du nom du module dans le volet de contour ou dans la barre d’outils du module sur le canevas.</span><span class="sxs-lookup"><span data-stu-id="33076-174">Select the ellipsis (**...**) next to the module's name in the outline pane, or in the module's toolbar in the canvas.</span></span>
1. <span data-ttu-id="33076-175">Si le module peut être déplacé vers le haut ou vers le bas dans le conteneur ou l’emplacement, vous verrez des options pour **Déplacer vers le haut** ou **Déplacer vers le bas**.</span><span class="sxs-lookup"><span data-stu-id="33076-175">If the module can be moved up or down within the container or slot, you will see options for **Move up** or **Move down**.</span></span> <span data-ttu-id="33076-176">Sélectionnez l’option de déplacement souhaitée pour déplacer le module vers le haut ou vers le bas par rapport à ses frères et sœurs.</span><span class="sxs-lookup"><span data-stu-id="33076-176">Select the desired move option to move the module up or down relative to its siblings.</span></span>

## <a name="configure-modules"></a><span data-ttu-id="33076-177">Configuration des modules</span><span class="sxs-lookup"><span data-stu-id="33076-177">Configure modules</span></span>

<span data-ttu-id="33076-178">Les procédures suivantes expliquent comment configurer des modules de contenu et de conteneur.</span><span class="sxs-lookup"><span data-stu-id="33076-178">The following procedures describe how to configure content and container modules.</span></span>

### <a name="configure-a-content-module"></a><span data-ttu-id="33076-179">Configuration d’un module de contenu</span><span class="sxs-lookup"><span data-stu-id="33076-179">Configure a content module</span></span>

<span data-ttu-id="33076-180">Pour configurer un module de contenu sur une page, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="33076-180">To configure a content module on a page, follow these steps.</span></span>

1. <span data-ttu-id="33076-181">Dans le volet de contour à gauche, développez l’arborescence et sélectionnez un type de module de contenu (par exemple, **Bloc de contenu**).</span><span class="sxs-lookup"><span data-stu-id="33076-181">In the outline pane on the left, expand the tree and select any content module (for example, **Content block**).</span></span> <span data-ttu-id="33076-182">Sinon, vous pouvez sélectionner le module dans le canevas principal.</span><span class="sxs-lookup"><span data-stu-id="33076-182">Alternately, you can select the module in the main canvas.</span></span>
1. <span data-ttu-id="33076-183">Dans le volet des propriétés du module sur la droite, entrez les propriétés des contrôles de module souhaités.</span><span class="sxs-lookup"><span data-stu-id="33076-183">In the module properties pane on the right, enter properties for any desired module controls.</span></span>
1. <span data-ttu-id="33076-184">Sur la barre de commande, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="33076-184">On the command bar, select **Save**.</span></span> <span data-ttu-id="33076-185">Le canevas d’aperçu est également actualisé.</span><span class="sxs-lookup"><span data-stu-id="33076-185">This will also refresh the preview canvas.</span></span>

### <a name="edit-module-text-properties"></a><span data-ttu-id="33076-186">Modifier les propriétés du texte du module</span><span class="sxs-lookup"><span data-stu-id="33076-186">Edit module text properties</span></span>

<span data-ttu-id="33076-187">Les propriétés du texte du module qui ne sont pas en lecture seule peuvent être modifiées directement dans le canevas.</span><span class="sxs-lookup"><span data-stu-id="33076-187">Module text properties that are not read-only can be edited directly in the canvas.</span></span>

<span data-ttu-id="33076-188">Pour modifier les propriétés du texte du module, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="33076-188">To edit module text properties, follow these steps.</span></span>

1. <span data-ttu-id="33076-189">Sélectionnez le contrôle de texte dans le canevas, puis placez votre curseur à l’endroit où vous souhaitez modifier le texte.</span><span class="sxs-lookup"><span data-stu-id="33076-189">Select the text control in the canvas, then place your cursor where you wish to edit text.</span></span>
1. <span data-ttu-id="33076-190">Entrez le contenu du texte.</span><span class="sxs-lookup"><span data-stu-id="33076-190">Enter your text content.</span></span>
1. <span data-ttu-id="33076-191">Sélectionnez n’importe où en dehors du contenu du texte pour continuer à modifier d’autres contenus.</span><span class="sxs-lookup"><span data-stu-id="33076-191">Select anywhere outside the text content to continue editing other content.</span></span>

### <a name="inline-image-selection"></a><span data-ttu-id="33076-192">Sélection d’images en ligne</span><span class="sxs-lookup"><span data-stu-id="33076-192">Inline image selection</span></span>

<span data-ttu-id="33076-193">Les images du module qui ne sont pas en lecture seule peuvent être modifiées directement dans le canevas.</span><span class="sxs-lookup"><span data-stu-id="33076-193">Module images that are not read-only can be changed directly from the canvas.</span></span>

<span data-ttu-id="33076-194">Pour choisir une image pour un module de contenu, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="33076-194">To choose a new image for a content module, follow these steps.</span></span>

1. <span data-ttu-id="33076-195">Dans le canevas, double-cliquez sur l’image.</span><span class="sxs-lookup"><span data-stu-id="33076-195">In the canvas, double-click the image.</span></span> <span data-ttu-id="33076-196">Cela fera apparaître la fenêtre du sélecteur de média.</span><span class="sxs-lookup"><span data-stu-id="33076-196">This will bring up the media picker window.</span></span>
1. <span data-ttu-id="33076-197">Recherchez et sélectionnez une nouvelle image à utiliser, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="33076-197">Find and select a new image you want to use, and then select **OK**.</span></span> <span data-ttu-id="33076-198">La nouvelle image est maintenant affichée dans le canevas.</span><span class="sxs-lookup"><span data-stu-id="33076-198">The new image is now rendered in the canvas.</span></span>

### <a name="configure-a-container-module"></a><span data-ttu-id="33076-199">Configurer un module de conteneur</span><span class="sxs-lookup"><span data-stu-id="33076-199">Configure a container module</span></span>

<span data-ttu-id="33076-200">Pour configurer un module de conteneur sur une page, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="33076-200">To configure a container module on a page, follow these steps.</span></span>

1. <span data-ttu-id="33076-201">Sélectionnez un module de conteneur sur la page (par exemple, un module de carrousel ou de conteneur fluide).</span><span class="sxs-lookup"><span data-stu-id="33076-201">Select a container module on your page (for example, a carousel or fluid container module).</span></span>
1. <span data-ttu-id="33076-202">Dans le volet de propriétés de droite, développez les contrôles imbriqués en sélectionnant les en-têtes, puis définissez toutes les valeurs requises de contrôle.</span><span class="sxs-lookup"><span data-stu-id="33076-202">In the properties pane on the right, expand the nested controls by selecting the headers, and set any required control values.</span></span>
1. <span data-ttu-id="33076-203">Dans le volet de contour à gauche, sélectionnez le bouton représentant des points de suspension en regard du nom du conteneur ou des emplacements à l’intérieur du conteneur, puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="33076-203">In the outline pane on the left, select the ellipsis button next to the name of either the container or any slots inside the container, and then select **Add Module**.</span></span> <span data-ttu-id="33076-204">Ajoutez ensuite les modules enfants au conteneur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="33076-204">Then, add child modules to the selected container.</span></span> <span data-ttu-id="33076-205">Pour plus d’informations, voir la section [Utiliser les modules](#add-a-module) plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="33076-205">For more information, see the [Work with modules](#add-a-module) section earlier in this topic.</span></span>
1. <span data-ttu-id="33076-206">Si plusieurs modules enfants existent en tant que jumeaux dans un conteneur parent, vous pouvez changer l’ordre d’affichage du conteneur parent.</span><span class="sxs-lookup"><span data-stu-id="33076-206">If multiple child modules exist as siblings in a parent container, you can change their display order in the parent container.</span></span> <span data-ttu-id="33076-207">Sélectionnez le bouton représentant des points de suspension d’un module, puis utilisez les boutons de flèche vers le bas ou vers le haut.</span><span class="sxs-lookup"><span data-stu-id="33076-207">Select the ellipsis button for a module, and then use the up arrow and down arrow buttons.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="33076-208">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="33076-208">Additional resources</span></span>

[<span data-ttu-id="33076-209">Vue d’ensemble des modèles et dispositions</span><span class="sxs-lookup"><span data-stu-id="33076-209">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="33076-210">Utiliser des modèles</span><span class="sxs-lookup"><span data-stu-id="33076-210">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="33076-211">Utilisation des mises en page prédéfinies</span><span class="sxs-lookup"><span data-stu-id="33076-211">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="33076-212">Utiliser des fragments</span><span class="sxs-lookup"><span data-stu-id="33076-212">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="33076-213">Ajouter un module de conteneur à une page</span><span class="sxs-lookup"><span data-stu-id="33076-213">Add a container module to a page</span></span>](add-container-module.md)

[<span data-ttu-id="33076-214">Utilisation de groupes de publication</span><span class="sxs-lookup"><span data-stu-id="33076-214">Work with publish groups</span></span>](publish-groups.md)

