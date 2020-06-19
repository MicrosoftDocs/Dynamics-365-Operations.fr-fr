---
title: Module d'onglet
description: Cette rubrique couvre les modules d'onglet et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 60af9b74f7e647e83229e352a03c09d63d0c7902
ms.sourcegitcommit: 2683aacb426bfb3b541637edf1f8ec2d6cb5a745
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/01/2020
ms.locfileid: "3417367"
---
# <a name="tab-module"></a><span data-ttu-id="c1c5c-103">Module d'onglet</span><span class="sxs-lookup"><span data-stu-id="c1c5c-103">Tab module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="c1c5c-104">Cette rubrique couvre les modules d'onglet et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-104">This topic covers tab modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c1c5c-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="c1c5c-105">Overview</span></span>

<span data-ttu-id="c1c5c-106">Les modules d'onglets sont des modules de type conteneur utilisés pour organiser les informations d'une page de site dans des onglets.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-106">Tab modules are container-like modules that are used to organize the information on a site page on tabs.</span></span> <span data-ttu-id="c1c5c-107">Ils peuvent être utilisés sur n'importe quelle page où les informations doivent être présentées dans des onglets.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-107">They can be used on any page where information must be presented on tabs.</span></span>

<span data-ttu-id="c1c5c-108">Dans chaque module d'onglet, un ou plusieurs modules d'élément d'onglet peuvent être ajoutés.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-108">In every tab module, one or more tab item modules can be added.</span></span> <span data-ttu-id="c1c5c-109">Chaque module d'élément d'onglet représente un onglet unique. Dans chaque module d'élément d'onglet, un ou plusieurs modules peuvent être ajoutés.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-109">Each tab item module represents a single tab. In each tab item module, one or more modules can be added.</span></span> <span data-ttu-id="c1c5c-110">Il n'y a aucune restriction quant aux types de modules qui peuvent être ajoutés à un module d'élément d'onglet.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-110">There are no restrictions on the types of modules that can be added to a tab item module.</span></span>

<span data-ttu-id="c1c5c-111">L'image suivante montre un exemple de module d'onglet sur une page de site.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-111">The following image shows an example of a tab module on a site page.</span></span> <span data-ttu-id="c1c5c-112">Dans cet exemple, l'onglet **Livraison** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-112">In this example, the **Shipping** tab selected.</span></span>

![Exemple d'un module d'onglet](./media/ecommerce-tab.PNG)

## <a name="tab-module-properties"></a><span data-ttu-id="c1c5c-114">Propriétés du module d'onglet</span><span class="sxs-lookup"><span data-stu-id="c1c5c-114">Tab module properties</span></span>

| <span data-ttu-id="c1c5c-115">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="c1c5c-115">Property name</span></span> | <span data-ttu-id="c1c5c-116">Valeurs</span><span class="sxs-lookup"><span data-stu-id="c1c5c-116">Values</span></span> | <span data-ttu-id="c1c5c-117">Description</span><span class="sxs-lookup"><span data-stu-id="c1c5c-117">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="c1c5c-118">En-tête</span><span class="sxs-lookup"><span data-stu-id="c1c5c-118">Heading</span></span> | <span data-ttu-id="c1c5c-119">Détails</span><span class="sxs-lookup"><span data-stu-id="c1c5c-119">Text</span></span> | <span data-ttu-id="c1c5c-120">Cette propriété spécifie un en-tête de texte facultatif pour le module d'onglet.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-120">This property specifies an optional text heading for the tab module.</span></span> |
| <span data-ttu-id="c1c5c-121">Index des onglets actifs</span><span class="sxs-lookup"><span data-stu-id="c1c5c-121">Active Tab Index</span></span> | <span data-ttu-id="c1c5c-122">Nombre</span><span class="sxs-lookup"><span data-stu-id="c1c5c-122">Number</span></span> | <span data-ttu-id="c1c5c-123">Cette propriété spécifie l'onglet qui doit être actif par défaut au chargement d'une page.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-123">This property specifies the tab that should be active by default when a page is loaded.</span></span> <span data-ttu-id="c1c5c-124">Si aucune valeur n'est fournie, le premier élément d'onglet est activé par défaut.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-124">If no value is provided, the first tab item is active by default.</span></span> |

## <a name="tab-item-module-properties"></a><span data-ttu-id="c1c5c-125">Propriétés du module d'élément d'onglet</span><span class="sxs-lookup"><span data-stu-id="c1c5c-125">Tab item module properties</span></span>

| <span data-ttu-id="c1c5c-126">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="c1c5c-126">Property name</span></span> | <span data-ttu-id="c1c5c-127">Valeurs</span><span class="sxs-lookup"><span data-stu-id="c1c5c-127">Values</span></span> | <span data-ttu-id="c1c5c-128">Description</span><span class="sxs-lookup"><span data-stu-id="c1c5c-128">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="c1c5c-129">Titre</span><span class="sxs-lookup"><span data-stu-id="c1c5c-129">Title</span></span> | <span data-ttu-id="c1c5c-130">Détails</span><span class="sxs-lookup"><span data-stu-id="c1c5c-130">Text</span></span> | <span data-ttu-id="c1c5c-131">Cette propriété spécifie le texte du titre du module d'élément d'onglet.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-131">This property specifies the title text for the tab item module.</span></span> |

## <a name="add-a-tab-module-to-a-page"></a><span data-ttu-id="c1c5c-132">Ajouter un module d'onglet à une page</span><span class="sxs-lookup"><span data-stu-id="c1c5c-132">Add a tab module to a page</span></span>

<span data-ttu-id="c1c5c-133">Pour ajouter un module d'onglet à une page et définir les propriétés requises, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-133">To add a tab module to a page and set the properties, follow these steps.</span></span>

1. <span data-ttu-id="c1c5c-134">Utilisez le modèle de marketing Fabrikam (ou tout modèle dénué de restriction) pour créer une nouvelle page nommée **Page des politiques du magasin**.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-134">Use the Fabrikam marketing template (or any template that has no restrictions) to create a new page that is named **Store policies page**.</span></span>
1. <span data-ttu-id="c1c5c-135">Dans l'emplacement **Principal** de la **Page par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-135">In the **Main** slot of the **Default page**, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c1c5c-136">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-136">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c1c5c-137">Dans l'emplacement **Conteneur**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-137">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c1c5c-138">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Onglet**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-138">In the **Add Module** dialog box, select the **Tab** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c1c5c-139">Dans le volet des propriétés du module d'onglet, sélectionnez **En-tête** à côté du symbole du crayon.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-139">In the property pane of the tab module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="c1c5c-140">Dans la boîte de dialogue **En-tête**, sous **Texte d'en-tête**, saisissez le texte de l'en-tête (par exemple, **Politiques**).</span><span class="sxs-lookup"><span data-stu-id="c1c5c-140">In the **Heading** dialog box, under **Heading Text**, enter heading text (for example, **Policies**).</span></span> <span data-ttu-id="c1c5c-141">Puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-141">Then select **OK**.</span></span>
1. <span data-ttu-id="c1c5c-142">Dans l'emplacement **Onglet**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-142">In the **Tab** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c1c5c-143">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Élément d'onglet**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-143">In the **Add Module** dialog box, select the **Tab item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c1c5c-144">Dans le volet des propriétés du module d'élément d'onglet, sous **Titre**, saisissez le texte du titre (par exemple, **Livraison**).</span><span class="sxs-lookup"><span data-stu-id="c1c5c-144">In the property pane of the tab item module, under **Title**, enter title text (for example, **Delivery**).</span></span>
1. <span data-ttu-id="c1c5c-145">Dans l'emplacement **Élément d'onglet**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-145">In the **Tab item** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c1c5c-146">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Bloc de texte**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-146">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c1c5c-147">Dans le volet des propriétés du module de bloc de texte, sous **Texte enrichi**, entrez un paragraphe de texte.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-147">In the property pane of the text block module, under **Rich text**, enter a paragraph of text.</span></span>
1. <span data-ttu-id="c1c5c-148">Dans l'emplacement **Onglet**, ajoutez quelques autres modules d'élément d'onglet portant un titre.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-148">In the **Tab** slot, add a few more tab item modules that have titles.</span></span> <span data-ttu-id="c1c5c-149">Dans chaque module d'élément d'onglet, ajoutez un module de bloc de texte portant du contenu.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-149">In each tab item module, add a text block module that has content.</span></span>
1. <span data-ttu-id="c1c5c-150">Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-150">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="c1c5c-151">La page affichera un module d'onglet contenant les modules d'élément d'onglet ayant le contenu que vous avez ajouté.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-151">The page will show a tab module that contains tab item modules have the content that you added.</span></span>
1. <span data-ttu-id="c1c5c-152">Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.</span><span class="sxs-lookup"><span data-stu-id="c1c5c-152">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c1c5c-153">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c1c5c-153">Additional resources</span></span>

[<span data-ttu-id="c1c5c-154">Vue d'ensemble du kit de démarrage</span><span class="sxs-lookup"><span data-stu-id="c1c5c-154">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="c1c5c-155">Module Conteneur</span><span class="sxs-lookup"><span data-stu-id="c1c5c-155">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="c1c5c-156">Module d'accordéon</span><span class="sxs-lookup"><span data-stu-id="c1c5c-156">Accordion module</span></span>](add-accordion.md)

[<span data-ttu-id="c1c5c-157">Module de bloc de texte</span><span class="sxs-lookup"><span data-stu-id="c1c5c-157">Text block module</span></span>](add-content-rich-block.md)
