---
title: Module d’onglet
description: Cette rubrique couvre les modules d’onglet et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: c865d5e055e3fadf2dda225b49f13a163974768f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797453"
---
# <a name="tab-module"></a><span data-ttu-id="3f39a-103">Module Onglet</span><span class="sxs-lookup"><span data-stu-id="3f39a-103">Tab module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3f39a-104">Cette rubrique couvre les modules d’onglet et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3f39a-104">This topic covers tab modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="3f39a-105">Les modules d’onglets sont des modules de type conteneur utilisés pour organiser les informations d’une page de site dans des onglets.</span><span class="sxs-lookup"><span data-stu-id="3f39a-105">Tab modules are container-like modules that are used to organize the information on a site page on tabs.</span></span> <span data-ttu-id="3f39a-106">Ils peuvent être utilisés sur n’importe quelle page où les informations doivent être présentées dans des onglets.</span><span class="sxs-lookup"><span data-stu-id="3f39a-106">They can be used on any page where information must be presented on tabs.</span></span>

<span data-ttu-id="3f39a-107">Dans chaque module d’onglet, un ou plusieurs modules d’élément d’onglet peuvent être ajoutés.</span><span class="sxs-lookup"><span data-stu-id="3f39a-107">In every tab module, one or more tab item modules can be added.</span></span> <span data-ttu-id="3f39a-108">Chaque module d’élément d’onglet représente un onglet unique. Dans chaque module d’élément d’onglet, un ou plusieurs modules peuvent être ajoutés.</span><span class="sxs-lookup"><span data-stu-id="3f39a-108">Each tab item module represents a single tab. In each tab item module, one or more modules can be added.</span></span> <span data-ttu-id="3f39a-109">Il n’y a aucune restriction quant aux types de modules qui peuvent être ajoutés à un module d’élément d’onglet.</span><span class="sxs-lookup"><span data-stu-id="3f39a-109">There are no restrictions on the types of modules that can be added to a tab item module.</span></span>

<span data-ttu-id="3f39a-110">L’image suivante montre un exemple de module d’onglet sur une page de site.</span><span class="sxs-lookup"><span data-stu-id="3f39a-110">The following image shows an example of a tab module on a site page.</span></span> <span data-ttu-id="3f39a-111">Dans cet exemple, l’onglet **Livraison** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="3f39a-111">In this example, the **Shipping** tab selected.</span></span>

![Exemple d’un module d’onglet](./media/ecommerce-tab.PNG)

## <a name="tab-module-properties"></a><span data-ttu-id="3f39a-113">Propriétés du module d’onglet</span><span class="sxs-lookup"><span data-stu-id="3f39a-113">Tab module properties</span></span>

| <span data-ttu-id="3f39a-114">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="3f39a-114">Property name</span></span> | <span data-ttu-id="3f39a-115">Valeurs</span><span class="sxs-lookup"><span data-stu-id="3f39a-115">Values</span></span> | <span data-ttu-id="3f39a-116">Description</span><span class="sxs-lookup"><span data-stu-id="3f39a-116">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="3f39a-117">En-tête</span><span class="sxs-lookup"><span data-stu-id="3f39a-117">Heading</span></span> | <span data-ttu-id="3f39a-118">Détails</span><span class="sxs-lookup"><span data-stu-id="3f39a-118">Text</span></span> | <span data-ttu-id="3f39a-119">Cette propriété spécifie un en-tête de texte facultatif pour le module d’onglet.</span><span class="sxs-lookup"><span data-stu-id="3f39a-119">This property specifies an optional text heading for the tab module.</span></span> |
| <span data-ttu-id="3f39a-120">Index des onglets actifs</span><span class="sxs-lookup"><span data-stu-id="3f39a-120">Active Tab Index</span></span> | <span data-ttu-id="3f39a-121">Nombre</span><span class="sxs-lookup"><span data-stu-id="3f39a-121">Number</span></span> | <span data-ttu-id="3f39a-122">Cette propriété spécifie l’onglet qui doit être actif par défaut au chargement d’une page.</span><span class="sxs-lookup"><span data-stu-id="3f39a-122">This property specifies the tab that should be active by default when a page is loaded.</span></span> <span data-ttu-id="3f39a-123">Si aucune valeur n’est fournie, le premier élément d’onglet est activé par défaut.</span><span class="sxs-lookup"><span data-stu-id="3f39a-123">If no value is provided, the first tab item is active by default.</span></span> |

## <a name="tab-item-module-properties"></a><span data-ttu-id="3f39a-124">Propriétés du module d’élément d’onglet</span><span class="sxs-lookup"><span data-stu-id="3f39a-124">Tab item module properties</span></span>

| <span data-ttu-id="3f39a-125">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="3f39a-125">Property name</span></span> | <span data-ttu-id="3f39a-126">Valeurs</span><span class="sxs-lookup"><span data-stu-id="3f39a-126">Values</span></span> | <span data-ttu-id="3f39a-127">Description</span><span class="sxs-lookup"><span data-stu-id="3f39a-127">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="3f39a-128">Titre</span><span class="sxs-lookup"><span data-stu-id="3f39a-128">Title</span></span> | <span data-ttu-id="3f39a-129">Détails</span><span class="sxs-lookup"><span data-stu-id="3f39a-129">Text</span></span> | <span data-ttu-id="3f39a-130">Cette propriété spécifie le texte du titre du module d’élément d’onglet.</span><span class="sxs-lookup"><span data-stu-id="3f39a-130">This property specifies the title text for the tab item module.</span></span> |

## <a name="add-a-tab-module-to-a-page"></a><span data-ttu-id="3f39a-131">Ajouter un module d’onglet à une page</span><span class="sxs-lookup"><span data-stu-id="3f39a-131">Add a tab module to a page</span></span>

<span data-ttu-id="3f39a-132">Pour ajouter un module d’onglet à une page et définir les propriétés requises, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3f39a-132">To add a tab module to a page and set the properties, follow these steps.</span></span>

1. <span data-ttu-id="3f39a-133">Utilisez le modèle de marketing Fabrikam (ou tout modèle dénué de restriction) pour créer une nouvelle page nommée **Page des politiques du magasin**.</span><span class="sxs-lookup"><span data-stu-id="3f39a-133">Use the Fabrikam marketing template (or any template that has no restrictions) to create a new page that is named **Store policies page**.</span></span>
1. <span data-ttu-id="3f39a-134">Dans l’emplacement **Principal** de la **Page par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="3f39a-134">In the **Main** slot of the **Default page**, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3f39a-135">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f39a-135">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="3f39a-136">Dans l’emplacement **Conteneur**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="3f39a-136">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3f39a-137">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Onglet**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f39a-137">In the **Add Module** dialog box, select the **Tab** module, and then select **OK**.</span></span>
1. <span data-ttu-id="3f39a-138">Dans le volet des propriétés du module d’onglet, sélectionnez **En-tête** à côté du symbole du crayon.</span><span class="sxs-lookup"><span data-stu-id="3f39a-138">In the property pane of the tab module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="3f39a-139">Dans la boîte de dialogue **En-tête**, sous **Texte d’en-tête**, saisissez le texte de l’en-tête (par exemple, **Politiques**).</span><span class="sxs-lookup"><span data-stu-id="3f39a-139">In the **Heading** dialog box, under **Heading Text**, enter heading text (for example, **Policies**).</span></span> <span data-ttu-id="3f39a-140">Puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f39a-140">Then select **OK**.</span></span>
1. <span data-ttu-id="3f39a-141">Dans l’emplacement **Onglet**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="3f39a-141">In the **Tab** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3f39a-142">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Élément d’onglet**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f39a-142">In the **Add Module** dialog box, select the **Tab item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="3f39a-143">Dans le volet des propriétés du module d’élément d’onglet, sous **Titre**, saisissez le texte du titre (par exemple, **Livraison**).</span><span class="sxs-lookup"><span data-stu-id="3f39a-143">In the property pane of the tab item module, under **Title**, enter title text (for example, **Delivery**).</span></span>
1. <span data-ttu-id="3f39a-144">Dans l’emplacement **Élément d’onglet**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="3f39a-144">In the **Tab item** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3f39a-145">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Bloc de texte**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f39a-145">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span>
1. <span data-ttu-id="3f39a-146">Dans le volet des propriétés du module de bloc de texte, sous **Texte enrichi**, entrez un paragraphe de texte.</span><span class="sxs-lookup"><span data-stu-id="3f39a-146">In the property pane of the text block module, under **Rich text**, enter a paragraph of text.</span></span>
1. <span data-ttu-id="3f39a-147">Dans l’emplacement **Onglet**, ajoutez quelques autres modules d’élément d’onglet portant un titre.</span><span class="sxs-lookup"><span data-stu-id="3f39a-147">In the **Tab** slot, add a few more tab item modules that have titles.</span></span> <span data-ttu-id="3f39a-148">Dans chaque module d’élément d’onglet, ajoutez un module de bloc de texte portant du contenu.</span><span class="sxs-lookup"><span data-stu-id="3f39a-148">In each tab item module, add a text block module that has content.</span></span>
1. <span data-ttu-id="3f39a-149">Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.</span><span class="sxs-lookup"><span data-stu-id="3f39a-149">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="3f39a-150">La page affichera un module d’onglet contenant les modules d’élément d’onglet ayant le contenu que vous avez ajouté.</span><span class="sxs-lookup"><span data-stu-id="3f39a-150">The page will show a tab module that contains tab item modules have the content that you added.</span></span>
1. <span data-ttu-id="3f39a-151">Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.</span><span class="sxs-lookup"><span data-stu-id="3f39a-151">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3f39a-152">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="3f39a-152">Additional resources</span></span>

[<span data-ttu-id="3f39a-153">Présentation de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="3f39a-153">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="3f39a-154">Module Conteneur</span><span class="sxs-lookup"><span data-stu-id="3f39a-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="3f39a-155">Module Accordéon</span><span class="sxs-lookup"><span data-stu-id="3f39a-155">Accordion module</span></span>](add-accordion.md)

[<span data-ttu-id="3f39a-156">Module de bloc de texte</span><span class="sxs-lookup"><span data-stu-id="3f39a-156">Text block module</span></span>](add-content-rich-block.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]