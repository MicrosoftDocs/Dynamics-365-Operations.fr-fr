---
title: Module Partage social
description: Cette rubrique couvre les modules de partage social et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
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
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: c34410a8c817de9fed350bf2cd2dd918a37c230f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795355"
---
# <a name="social-share-module"></a><span data-ttu-id="32829-103">Module Partage social</span><span class="sxs-lookup"><span data-stu-id="32829-103">Social share module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="32829-104">Cette rubrique couvre les modules de partage social et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="32829-104">This topic covers social share modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="32829-105">Les modules de partage social permettent aux utilisateurs de partager des URL de page de site d’e-commerce sur les médias sociaux, tels que Facebook, Twitter, Pinterest et LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="32829-105">Social share modules allow users to share e-Commerce site page URLs on social media such as Facebook, Twitter, Pinterest, and LinkedIn.</span></span> <span data-ttu-id="32829-106">Les URL des pages du site peuvent également être partagées par e-mail.</span><span class="sxs-lookup"><span data-stu-id="32829-106">Site page URLs can also be shared via email.</span></span> <span data-ttu-id="32829-107">Les modules de partage social sont couramment utilisés sur les pages de détails sur les produits (PDP) pour aider les utilisateurs à partager des informations sur les produits.</span><span class="sxs-lookup"><span data-stu-id="32829-107">Social share modules are commonly used on product details pages (PDPs) to help users share product information.</span></span>

<span data-ttu-id="32829-108">Chaque module de partage social est un conteneur pour les modules d’éléments de partage social.</span><span class="sxs-lookup"><span data-stu-id="32829-108">Each social share module is a container for social share item modules.</span></span> <span data-ttu-id="32829-109">Chaque module d’élément de partage social peut être configuré pour pointer vers un média social spécifique.</span><span class="sxs-lookup"><span data-stu-id="32829-109">Each social share item module can be configured to point to a specific social media site.</span></span> <span data-ttu-id="32829-110">Intégration avec Facebook, Twitter, Pinterest, LinkedIn et les e-mails sont pris en charge par défaut.</span><span class="sxs-lookup"><span data-stu-id="32829-110">Integration with Facebook, Twitter, Pinterest, LinkedIn, and email is supported out of the box.</span></span> <span data-ttu-id="32829-111">Lorsqu’un utilisateur du site sélectionne un symbole de réseau social, un iframe HTML est lancé pour le site de réseau social respectif.</span><span class="sxs-lookup"><span data-stu-id="32829-111">When a site user selects a social media symbol, an HTML iframe is launched for the respective social media site.</span></span> <span data-ttu-id="32829-112">Dans l’iframe, l’utilisateur peut se connecter et publier le contenu de la page qu’il consultait.</span><span class="sxs-lookup"><span data-stu-id="32829-112">Within the iframe, the user can sign in and post the page content that they were viewing.</span></span>

<span data-ttu-id="32829-113">Chaque plateforme de média social peut suivre les cookies, ce module oblige donc les utilisateurs du site à accepter le message de notification de consentement aux cookies.</span><span class="sxs-lookup"><span data-stu-id="32829-113">Each social media platform may track cookies, so this module requires site users to accept the cookie consent notification message.</span></span> <span data-ttu-id="32829-114">Lorsque le consentement aux cookies n’est pas accepté, le module est masqué sur la page.</span><span class="sxs-lookup"><span data-stu-id="32829-114">When cookie consent is not accepted, the module will be hidden on the page.</span></span> <span data-ttu-id="32829-115">Pour plus d’informations, voir [Conformité des cookies](cookie-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="32829-115">For more information, see [Cookie compliance](cookie-compliance.md).</span></span>

<span data-ttu-id="32829-116">L’illustration suivante met en évidence un exemple de module de partage social utilisé sur une page de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="32829-116">The following illustration highlights an example of a social share module used on a product details page.</span></span>

![Exemple de module de partage social](./media/ecommerce-socialshare.png)

## <a name="social-share-module-properties"></a><span data-ttu-id="32829-118">Propriétés du module Partage social</span><span class="sxs-lookup"><span data-stu-id="32829-118">Social share module properties</span></span>

| <span data-ttu-id="32829-119">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="32829-119">Property name</span></span>             | <span data-ttu-id="32829-120">Valeur</span><span class="sxs-lookup"><span data-stu-id="32829-120">Value</span></span>                 | <span data-ttu-id="32829-121">Description</span><span class="sxs-lookup"><span data-stu-id="32829-121">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="32829-122">Légende</span><span class="sxs-lookup"><span data-stu-id="32829-122">Caption</span></span>                  | <span data-ttu-id="32829-123">Détails</span><span class="sxs-lookup"><span data-stu-id="32829-123">Text</span></span> | <span data-ttu-id="32829-124">Cette propriété spécifie une légende pour le module.</span><span class="sxs-lookup"><span data-stu-id="32829-124">This property specifies a caption for the module.</span></span> |
| <span data-ttu-id="32829-125">Orientation</span><span class="sxs-lookup"><span data-stu-id="32829-125">Orientation</span></span> | <span data-ttu-id="32829-126">**Horizontal** ou **Vertical**</span><span class="sxs-lookup"><span data-stu-id="32829-126">**Horizontal** or **Vertical**</span></span>  | <span data-ttu-id="32829-127">Cette propriété définit l’orientation de la mise en page des éléments de médias sociaux.</span><span class="sxs-lookup"><span data-stu-id="32829-127">This property defines the layout orientation for the social media items.</span></span> |

## <a name="social-share-item-module-properties"></a><span data-ttu-id="32829-128">Propriétés du module d’élément Partage social</span><span class="sxs-lookup"><span data-stu-id="32829-128">Social share item module properties</span></span>
| <span data-ttu-id="32829-129">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="32829-129">Property name</span></span>             | <span data-ttu-id="32829-130">Valeur</span><span class="sxs-lookup"><span data-stu-id="32829-130">Value</span></span>                 | <span data-ttu-id="32829-131">Description</span><span class="sxs-lookup"><span data-stu-id="32829-131">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="32829-132">Réseaux sociaux</span><span class="sxs-lookup"><span data-stu-id="32829-132">Social media</span></span>              | <span data-ttu-id="32829-133">**Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **E-mail**</span><span class="sxs-lookup"><span data-stu-id="32829-133">**Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **Mail**</span></span> | <span data-ttu-id="32829-134">Un menu déroulant avec une liste de plateformes de médias sociaux.</span><span class="sxs-lookup"><span data-stu-id="32829-134">A drop-down menu with a list of social media platforms.</span></span> |
| <span data-ttu-id="32829-135">Icône</span><span class="sxs-lookup"><span data-stu-id="32829-135">Icon</span></span> |<span data-ttu-id="32829-136">Image</span><span class="sxs-lookup"><span data-stu-id="32829-136">Image</span></span>    | <span data-ttu-id="32829-137">Ce sera l’image qui sera affichée pour les médias sociaux respectifs.</span><span class="sxs-lookup"><span data-stu-id="32829-137">This will be the image that will be shown for the respective social media.</span></span> <span data-ttu-id="32829-138">En tant que meilleure pratique, reportez-vous au Kit de développement logiciel (SDK) de la plateforme de médias sociaux pour obtenir l’image recommandée à utiliser pour chaque plateforme.</span><span class="sxs-lookup"><span data-stu-id="32829-138">As a best practice, refer to the social media platform's SDK for the recommended image to use for each platform.</span></span> |

## <a name="add-a-social-share-module-to-a-buy-box-module"></a><span data-ttu-id="32829-139">Ajouter un module de partage social à un module de zone d’achat</span><span class="sxs-lookup"><span data-stu-id="32829-139">Add a social share module to a buy box module</span></span>

<span data-ttu-id="32829-140">Pour ajouter un module de partage social à un module de zone d’achat, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="32829-140">To add a social share module to a buy box module, follow these steps.</span></span>

1. <span data-ttu-id="32829-141">Dans le site Fabrikam, sélectionnez **Pages**, puis la page **DefaultPDP** pour ouvrir la page des détails du produit.</span><span class="sxs-lookup"><span data-stu-id="32829-141">In the Fabrikam site, select **Pages**, and then select the **DefaultPDP** page to open the product details page.</span></span> 
1. <span data-ttu-id="32829-142">Dans l’emplacement **Zone d’achat (obligatoire)**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="32829-142">In the **Buybox (required)** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="32829-143">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Partage social**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="32829-143">In the **Add Module** dialog box, select the **Social Share** module, and then select **OK**.</span></span>
1. <span data-ttu-id="32829-144">Dans l’emplacement **Partage social**, sélectionnez le bouton (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="32829-144">In the **Social Share** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="32829-145">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **SocialShare**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="32829-145">In the **Add Module** dialog box, select the **SocialShare** module, and then select **OK**.</span></span>
1. <span data-ttu-id="32829-146">Dans le volet des propriétés du module **SocialShare**, sous **Orientation**, sélectionnez **Horizontal**.</span><span class="sxs-lookup"><span data-stu-id="32829-146">In the properties pane of the **SocialShare** module, under **Orientation**, select **Horizontal**.</span></span> <span data-ttu-id="32829-147">Ajoutez une légende si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="32829-147">Add a caption as needed.</span></span>
1. <span data-ttu-id="32829-148">Dans l’emplacement **SocialShare**, sélectionnez le bouton (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="32829-148">In the **SocialShare** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="32829-149">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **SocialShareItem**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="32829-149">In the **Add Module** dialog box, select the **SocialShareItem** module, and then select **OK**.</span></span>
1. <span data-ttu-id="32829-150">Dans le volet des propriétés du module **SocialShareItem**, sous **Réseau social**, sélectionnez **Facebook**.</span><span class="sxs-lookup"><span data-stu-id="32829-150">In the properties pane of the **SocialShareItem** module, under **Social Media**, select **Facebook**.</span></span>
1. <span data-ttu-id="32829-151">Dans le volet des propriétés du module **SocialShareItem**, sous **Icône**, sélectionnez **+ Ajouter une image**.</span><span class="sxs-lookup"><span data-stu-id="32829-151">In the properties pane of the **SocialShareItem** module, under **Icon**, select **+ Add an image**.</span></span>
1. <span data-ttu-id="32829-152">Dans la boîte de dialogue **Sélecteur multimédia**, sélectionnez l’image du logo Facebook, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="32829-152">In the **Media Picker** dialog box, select the Facebook logo image, and then select **OK**.</span></span> <span data-ttu-id="32829-153">Si aucune image du logo Facebook n’est présente, sélectionnez **Importer un nouvel élément multimédia** pour en charger une.</span><span class="sxs-lookup"><span data-stu-id="32829-153">If no Facebook logo image is present, select **Upload new media item** to upload one.</span></span>
1. <span data-ttu-id="32829-154">Ajoutez et configurez des modules **SocialShareItem** selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="32829-154">Add and configure additional **SocialShareItem** modules as needed.</span></span>
1. <span data-ttu-id="32829-155">Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.</span><span class="sxs-lookup"><span data-stu-id="32829-155">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="32829-156">La page affichera le module de partage social.</span><span class="sxs-lookup"><span data-stu-id="32829-156">The page will show the social share module.</span></span>
1. <span data-ttu-id="32829-157">Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.</span><span class="sxs-lookup"><span data-stu-id="32829-157">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="32829-158">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="32829-158">Additional resources</span></span>

[<span data-ttu-id="32829-159">Présentation de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="32829-159">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="32829-160">Module Zone d’achat</span><span class="sxs-lookup"><span data-stu-id="32829-160">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="32829-161">Conformité des cookies</span><span class="sxs-lookup"><span data-stu-id="32829-161">Cookie compliance</span></span>](cookie-compliance.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]