---
title: Utiliser des modules
description: Cette rubrique décrit quand et comment utiliser des modules dans Microsoft Dynamics 365 Commerce.
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
ms.search.industry: ''
ms.author: phinneyridge
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 06a26e5dfd35bf229e67ed27213210d0da726bdf
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698071"
---
# <a name="work-with-modules"></a><span data-ttu-id="db6a4-103">Utiliser des modules</span><span class="sxs-lookup"><span data-stu-id="db6a4-103">Work with modules</span></span>

<span data-ttu-id="db6a4-104">Cette rubrique décrit quand et comment utiliser des modules dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="db6a4-104">This topic describes how and when to use modules in Microsoft Dynamics 365 Commerce.</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

## <a name="overview"></a><span data-ttu-id="db6a4-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="db6a4-105">Overview</span></span>

<span data-ttu-id="db6a4-106">Les modules sont des blocs élémentaires logiques qui constituent la structure de la page, et ils ont différentes fins et étendues.</span><span class="sxs-lookup"><span data-stu-id="db6a4-106">Modules are logical building blocks that make up your page structure, and they have various purposes and scopes.</span></span> <span data-ttu-id="db6a4-107">Certains modules sont des conteneurs de haut niveau, et leur seul objectif est de garder à jour et d'organiser les autres modules (modules enfants).</span><span class="sxs-lookup"><span data-stu-id="db6a4-107">Some modules are high-level containers, and their only purpose is to hold and organize other modules (child modules).</span></span> <span data-ttu-id="db6a4-108">D'autres modules, tels qu'un module de placement d'une image simple, à un objet très spécifique.</span><span class="sxs-lookup"><span data-stu-id="db6a4-108">Other modules, such as a simple image placement module, have a very specific purpose.</span></span> <span data-ttu-id="db6a4-109">D'autres modules, tels qu'un module de carrousel, se situe entre ces deux catégories.</span><span class="sxs-lookup"><span data-stu-id="db6a4-109">Other modules, such as a carousel module, fall somewhere between those two categories.</span></span>

<span data-ttu-id="db6a4-110">Par défaut, votre site Dynamics 365 Commerce inclut une bibliothèque de modules du kit de démarrage qui vous permet de réaliser la plupart des scénarios de base de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="db6a4-110">By default, your Dynamics 365 Commerce site includes a starter kit module library that lets you achieve most basic e-Commerce scenarios.</span></span> <span data-ttu-id="db6a4-111">Vous devez pouvoir construire un site de bout en bout de commerce électronique juste à l'aide de ces modules.</span><span class="sxs-lookup"><span data-stu-id="db6a4-111">You should be able to construct an end-to-end e-Commerce site just by using these modules.</span></span> <span data-ttu-id="db6a4-112">Toutefois, vous pouvez également souhaiter personnaliser ces modules ou générer de nouveaux modules, personnalisés pour les besoins spécifiques.</span><span class="sxs-lookup"><span data-stu-id="db6a4-112">However, you might also want to customize these modules or build new, custom modules for specific needs.</span></span> <span data-ttu-id="db6a4-113">Si vous souhaitez générer les modules personnalisés, un kit de développement logiciel (SDK) de conception de module est disponible pour créer une bibliothèque de modules personnalisée.</span><span class="sxs-lookup"><span data-stu-id="db6a4-113">If you want to build custom modules, a module design software development kit (SDK) is available to help you create a custom module library.</span></span>

## <a name="container-modules-and-slots"></a><span data-ttu-id="db6a4-114">Modules et emplacement de conteneur</span><span class="sxs-lookup"><span data-stu-id="db6a4-114">Container modules and slots</span></span>

<span data-ttu-id="db6a4-115">Comme précédemment évoqué, certains modules sont conçus pour mettre à jour les modules enfants.</span><span class="sxs-lookup"><span data-stu-id="db6a4-115">As was mentioned earlier, some modules are designed to hold child modules.</span></span> <span data-ttu-id="db6a4-116">Ces modules sont appelés *conteneurs*, et ils permettent des hiérarchies de modules imbriqués.</span><span class="sxs-lookup"><span data-stu-id="db6a4-116">These modules are known as *containers*, and they allow for hierarchies of nested modules.</span></span> <span data-ttu-id="db6a4-117">Les modules de conteneur incluent des *emplacements*.</span><span class="sxs-lookup"><span data-stu-id="db6a4-117">Container modules include *slots*.</span></span> <span data-ttu-id="db6a4-118">Les emplacements sont utilisés pour gérer la disposition et l'objectif des modules enfants dans le conteneur.</span><span class="sxs-lookup"><span data-stu-id="db6a4-118">Slots are used to handle the layout and purpose of child modules in the container.</span></span> <span data-ttu-id="db6a4-119">Un exemple est un module de conteneur de page de base (module de niveau supérieur pour toute page) qui définit plusieurs emplacements importantes :</span><span class="sxs-lookup"><span data-stu-id="db6a4-119">An example is a basic page container module (a top-level module for any page) that defines several important slots:</span></span>

- <span data-ttu-id="db6a4-120">Un emplacement d'en-tête</span><span class="sxs-lookup"><span data-stu-id="db6a4-120">A header slot</span></span>
- <span data-ttu-id="db6a4-121">Un emplacement de corps</span><span class="sxs-lookup"><span data-stu-id="db6a4-121">A body slot</span></span>
- <span data-ttu-id="db6a4-122">Un emplacement de pied de page</span><span class="sxs-lookup"><span data-stu-id="db6a4-122">A footer slot</span></span>

<span data-ttu-id="db6a4-123">Le développeur du module définit ces emplacements, et détermine quels modules enfants et combien de modules enfants peuvent être placés directement à l'intérieur de celui-ci.</span><span class="sxs-lookup"><span data-stu-id="db6a4-123">The module's developer defines these slots, and determines which child modules and how many child modules can be put directly inside it.</span></span> <span data-ttu-id="db6a4-124">Par exemple, l'emplacement d'en-tête ne peut prendre en charge qu'un module de type **Module d'en-tête**, alors que l'emplacement du corps peut prendre en charge un nombre illimité de modules de tous types (sauf d'autres modules de conteneur de page).</span><span class="sxs-lookup"><span data-stu-id="db6a4-124">For example, the header slot might support only one module of the **Header Module** type, whereas the body slot might support an unlimited number of modules of any type (except other page container modules).</span></span>

<span data-ttu-id="db6a4-125">Dans les outils de création, les auteurs de page ne doivent pas savoir à l'avance quels modules peuvent et ne peuvent pas être placés dans chaque emplacement.</span><span class="sxs-lookup"><span data-stu-id="db6a4-125">In the authoring tools, page authors don't have to know in advance which modules can and can't be put in each slot.</span></span> <span data-ttu-id="db6a4-126">Lorsque des auteurs de page sélectionnent un emplacement puis essayent de sélectionner un module à ajouter à celui-ci, ils peuvent afficher une vue filtrée des types de modules pris en charge pour cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="db6a4-126">When page authors select a slot and then try to select a module to add to it, they see a filtered view of module types that are supported for that slot.</span></span>

## <a name="content-modules"></a><span data-ttu-id="db6a4-127">Modules de contenu</span><span class="sxs-lookup"><span data-stu-id="db6a4-127">Content modules</span></span>

<span data-ttu-id="db6a4-128">Les modules de contenus contiennent des éléments de contenu et multimédias, tels que le texte (par exemple, des titres, des paragraphes, ainsi que des liens) ou des références d'actifs (par exemple, des images, des vidéos, et des PDF).</span><span class="sxs-lookup"><span data-stu-id="db6a4-128">Content modules contain content and media elements, such as text (for example, headlines, paragraphs, and links) or asset references (for example, images, video, and PDFs).</span></span> <span data-ttu-id="db6a4-129">Les exemples de types de modules de contenu habituels sont **Bannière**, **Fonctionnalité**, et **Bannière**.</span><span class="sxs-lookup"><span data-stu-id="db6a4-129">Examples of typical content module types are **Hero**, **Feature**, and **Banner**.</span></span> <span data-ttu-id="db6a4-130">Les modules de ces trois types peuvent contenir du texte ou du multimédia, et ils n'exigent pas de module enfant pour rendre un événement visible dans une page.</span><span class="sxs-lookup"><span data-stu-id="db6a4-130">Modules of these three types can contain text or media, and they don't require any child modules to make something visible on a page.</span></span>

<span data-ttu-id="db6a4-131">La plupart des activités de création de page et de contenu standard et quotidiennes impliquent des modules de contenu, principalement car ces modules définissent le contenu réel qui s'affiche dans leurs modules parents de conteneur.</span><span class="sxs-lookup"><span data-stu-id="db6a4-131">The majority of typical, day-to-day page and content authoring activities involve content modules, primarily because these modules define the actual content that is rendered in their parent container modules.</span></span> <span data-ttu-id="db6a4-132">De nombreux modules de contenu sont disponibles, et ces modules sont généralement les dernières pièces que vous ajoutez à la hiérarchie d'une page de modules imbriqués.</span><span class="sxs-lookup"><span data-stu-id="db6a4-132">Many content modules are available, and these modules are typically the last pieces that you will add to a page's hierarchy of nested modules.</span></span>

<span data-ttu-id="db6a4-133">L'illustration ci-dessous indique comment les modules sont imbriqués dans des emplacements parents des modules de conteneur.</span><span class="sxs-lookup"><span data-stu-id="db6a4-133">The following illustration shows how modules are nested inside parent container module slots.</span></span>

![Imbrication de modules](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a><span data-ttu-id="db6a4-135">Ajouter ou supprimer des modules</span><span class="sxs-lookup"><span data-stu-id="db6a4-135">Add or remove modules</span></span>

<span data-ttu-id="db6a4-136">Les procédures suivantes expliquent comment ajouter, supprimer des modules.</span><span class="sxs-lookup"><span data-stu-id="db6a4-136">The following procedures describe how to add and remove modules.</span></span>

### <a name="add-a-module"></a><span data-ttu-id="db6a4-137">Ajouter un module</span><span class="sxs-lookup"><span data-stu-id="db6a4-137">Add a module</span></span>

<span data-ttu-id="db6a4-138">Pour ajouter un module à un emplacement ou à un conteneur sur une page, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="db6a4-138">To add a module to a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="db6a4-139">Dans le volet de contour à gauche, sélectionnez un conteneur ou un emplacement auquel un module enfant peut être ajouté.</span><span class="sxs-lookup"><span data-stu-id="db6a4-139">In the outline pane on the left, select a container or slot that a child module can be added to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="db6a4-140">Le concepteur de module définit la liste des types de modules qui peuvent être ajoutés à un emplacement spécifique du module.</span><span class="sxs-lookup"><span data-stu-id="db6a4-140">The module designer defines the list of modules types that can be added to a specific module slot.</span></span> <span data-ttu-id="db6a4-141">Les auteurs de modèles peuvent ensuite affiner les options autorisées de module pour assurer un optimisation de moteur de recherche (SEO) cohérente et un rendement de création pour toutes les pages qui sont créées à partir d'un modèle spécifique.</span><span class="sxs-lookup"><span data-stu-id="db6a4-141">Template authors can then refine the allowed module options to help guarantee consistent search engine optimization (SEO) and authoring efficiency for all the pages pages that are built from a specific template.</span></span>

1. <span data-ttu-id="db6a4-142">Sélectionnez le bouton représentant des points de suspension (**...**) pour le module, et sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="db6a4-142">Select the ellipsis button (**...**) for the module, and then select **Add Module**.</span></span> <span data-ttu-id="db6a4-143">La boîte de dialogue **Ajoutez le module** apparaît.</span><span class="sxs-lookup"><span data-stu-id="db6a4-143">The **Add Module** dialog box appears.</span></span> <span data-ttu-id="db6a4-144">Cette boîte de dialogue est automatiquement filtrée afin d'afficher uniquement les modules pris en charge dans le conteneur ou l'emplacement sélectionné.</span><span class="sxs-lookup"><span data-stu-id="db6a4-144">This dialog box is automatically filtered so that it shows only modules that are supported in the selected container or slot.</span></span> <span data-ttu-id="db6a4-145">La liste des modules est déterminée par le modèle de la page ou la définition du module de conteneur.</span><span class="sxs-lookup"><span data-stu-id="db6a4-145">The list of modules is determined by the page's template or the container module definition.</span></span>

    > [!NOTE]
    > <span data-ttu-id="db6a4-146">Si le conteneur ou l'emplacement ne prend pas en charge de nouveaux modules enfants, l'option **Ajouter un module** n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="db6a4-146">If a container or slot doesn't support new child modules, the **Add Module** option is unavailable.</span></span>

1. <span data-ttu-id="db6a4-147">Dans la boîte de dialogue, recherchez et sélectionnez un module à ajouter à votre page.</span><span class="sxs-lookup"><span data-stu-id="db6a4-147">In the dialog box, search for and select a module to add to your page.</span></span>

    > [!TIP]
    > <span data-ttu-id="db6a4-148">**Fonctionnalité** et **Bannière** sont de bons types de modules pour les débutants.</span><span class="sxs-lookup"><span data-stu-id="db6a4-148">**Feature** and **Hero** are good module types for beginners to work with.</span></span>

1. <span data-ttu-id="db6a4-149">Sélectionnez **OK** pour ajouter le module sélectionné au conteneur ou à l'emplacement sélectionné sur la page.</span><span class="sxs-lookup"><span data-stu-id="db6a4-149">Select **OK** to add the selected module to the selected container or slot on your page.</span></span>

### <a name="remove-a-module"></a><span data-ttu-id="db6a4-150">Supprimer un module</span><span class="sxs-lookup"><span data-stu-id="db6a4-150">Remove a module</span></span>

<span data-ttu-id="db6a4-151">Pour supprimer un module d'un emplacement ou d'un conteneur sur une page, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="db6a4-151">To remove a module from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="db6a4-152">Dans le volet de contour à gauche, sélectionnez le bouton représentant des points de suspension en regard du nom du module à supprimer, puis sélectionnez le bouton de corbeille.</span><span class="sxs-lookup"><span data-stu-id="db6a4-152">In the outline pane on the left, select the ellipsis button next to the name of the module to remove, and then select the trash can button.</span></span>
1. <span data-ttu-id="db6a4-153">Lorsque vous êtes invité à confirmer la suppression du module, sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="db6a4-153">When you're prompted to confirm that you want to remove the module, select **OK**.</span></span>

## <a name="configure-modules"></a><span data-ttu-id="db6a4-154">Configuration des modules</span><span class="sxs-lookup"><span data-stu-id="db6a4-154">Configure modules</span></span>

<span data-ttu-id="db6a4-155">Les procédures suivantes expliquent comment configurer des modules de contenu et de conteneur.</span><span class="sxs-lookup"><span data-stu-id="db6a4-155">The following procedures describe how to configure content and container modules.</span></span>

### <a name="configure-a-content-module"></a><span data-ttu-id="db6a4-156">Configuration d'un module de contenu</span><span class="sxs-lookup"><span data-stu-id="db6a4-156">Configure a content module</span></span>

<span data-ttu-id="db6a4-157">Pour configurer un module de contenu sur une page, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="db6a4-157">To configure a content module on a page, follow these steps.</span></span>

1. <span data-ttu-id="db6a4-158">Dans le volet d'ensemble à gauche, sélectionnez un type de module de contenu (par exemple, **Fonctionnalité**, **Bannière**, ou **Bannière**).</span><span class="sxs-lookup"><span data-stu-id="db6a4-158">In the outline pane on the left, select a content module type (for example, **Feature**, **Hero**, or **Banner**).</span></span>
1. <span data-ttu-id="db6a4-159">Dans le volet de propriétés de droite, développez les contrôles imbriqués en sélectionnant les en-têtes, puis définissez toutes les valeurs requises de contrôle.</span><span class="sxs-lookup"><span data-stu-id="db6a4-159">In the properties pane on the right, expand the nested controls by selecting the headers, and set any required control values.</span></span>
1. <span data-ttu-id="db6a4-160">Si le volet de propriétés a une section **Configuration de données**, sélectionnez-la pour le développer.</span><span class="sxs-lookup"><span data-stu-id="db6a4-160">If the properties pane has a **Data Configuration** section, select it to expand it.</span></span> <span data-ttu-id="db6a4-161">Sinon, passez à l'étape 5.</span><span class="sxs-lookup"><span data-stu-id="db6a4-161">Otherwise, go to step 5.</span></span>
1. <span data-ttu-id="db6a4-162">S'il existe un bouton **Ajouter une source de données**, sélectionnez-la, puis sélectionnez les articles de contenu à ajouter.</span><span class="sxs-lookup"><span data-stu-id="db6a4-162">If there is a **Add Data Source** button, select it, and then select the content items to add.</span></span>
1. <span data-ttu-id="db6a4-163">Entrez les paramètres de tous les contrôles du module requis ou souhaités.</span><span class="sxs-lookup"><span data-stu-id="db6a4-163">Enter settings for any required or desired module controls.</span></span>
1. <span data-ttu-id="db6a4-164">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="db6a4-164">Select **Save**.</span></span>

### <a name="configure-a-container-module"></a><span data-ttu-id="db6a4-165">Configurer un module de conteneur</span><span class="sxs-lookup"><span data-stu-id="db6a4-165">Configure a container module</span></span>

<span data-ttu-id="db6a4-166">Pour configurer un module de conteneur sur une page, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="db6a4-166">To configure a container module on a page, follow these steps.</span></span>

1. <span data-ttu-id="db6a4-167">Sélectionnez un module de conteneur sur la page (par exemple, un module de carrousel ou de conteneur fluide).</span><span class="sxs-lookup"><span data-stu-id="db6a4-167">Select a container module on your page (for example, a carousel or fluid container module).</span></span>
1. <span data-ttu-id="db6a4-168">Dans le volet de propriétés de droite, développez les contrôles imbriqués en sélectionnant les en-têtes, puis définissez toutes les valeurs requises de contrôle.</span><span class="sxs-lookup"><span data-stu-id="db6a4-168">In the properties pane on the right, expand the nested controls by selecting the headers, and set any required control values.</span></span>
1. <span data-ttu-id="db6a4-169">Dans le volet de contour à gauche, sélectionnez le bouton représentant des points de suspension en regard du nom du conteneur ou des emplacements à l'intérieur du conteneur, puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="db6a4-169">In the outline pane on the left, select the ellipsis button next to the name of either the container or any slots inside the container, and then select **Add Module**.</span></span> <span data-ttu-id="db6a4-170">Ajoutez ensuite les modules enfants au conteneur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="db6a4-170">Then add child modules to the selected container.</span></span> <span data-ttu-id="db6a4-171">Pour plus d'informations, voir la procédure [Ajouter un module](#add-a-module) décrite plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="db6a4-171">For more information, see the [Add a module](#add-a-module) procedure earlier in this topic.</span></span>
1. <span data-ttu-id="db6a4-172">Si plusieurs modules enfants existent en tant que jumeaux dans un conteneur parent, vous pouvez changer l'ordre d'affichage du conteneur parent.</span><span class="sxs-lookup"><span data-stu-id="db6a4-172">If multiple child modules exist as siblings in a parent container, you can change their display order in the parent container.</span></span> <span data-ttu-id="db6a4-173">Sélectionnez le bouton représentant des points de suspension d'un module, puis utilisez les boutons de flèche vers le bas ou vers le haut.</span><span class="sxs-lookup"><span data-stu-id="db6a4-173">Select the ellipsis button for a module, and then use the up arrow and down arrow buttons.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="db6a4-174">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="db6a4-174">Additional resources</span></span>

[<span data-ttu-id="db6a4-175">Vue d'ensemble des modèles et dispositions</span><span class="sxs-lookup"><span data-stu-id="db6a4-175">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="db6a4-176">Utiliser des modèles</span><span class="sxs-lookup"><span data-stu-id="db6a4-176">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="db6a4-177">Utilisation des mises en page prédéfinies</span><span class="sxs-lookup"><span data-stu-id="db6a4-177">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="db6a4-178">Utiliser des fragments</span><span class="sxs-lookup"><span data-stu-id="db6a4-178">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="db6a4-179">Ajouter un module de conteneur à une page</span><span class="sxs-lookup"><span data-stu-id="db6a4-179">Add a container module to a page</span></span>](add-container-module.md)

[<span data-ttu-id="db6a4-180">Ajouter des modules de placement à une page</span><span class="sxs-lookup"><span data-stu-id="db6a4-180">Add content placement modules to a page</span></span>](add-content-placement-modules.md)

