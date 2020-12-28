---
title: Module Partage social
description: Cette rubrique couvre les modules de partage social et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 82a8795360f453cdee19fa6e9e376a42e8276849
ms.sourcegitcommit: 510ca8b14d8b5334e50aca1b15d636c65fcc9888
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4412398"
---
# <a name="social-share-module"></a><span data-ttu-id="3f3c2-103">Module Partage social</span><span class="sxs-lookup"><span data-stu-id="3f3c2-103">Social share module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3f3c2-104">Cette rubrique couvre les modules de partage social et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-104">This topic covers social share modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="3f3c2-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="3f3c2-105">Overview</span></span>

<span data-ttu-id="3f3c2-106">Les modules de partage social permettent aux utilisateurs de partager des URL de page de site d’e-commerce sur les médias sociaux, tels que Facebook, Twitter, Pinterest et LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-106">Social share modules allow users to share e-Commerce site page URLs on social media such as Facebook, Twitter, Pinterest, and LinkedIn.</span></span> <span data-ttu-id="3f3c2-107">Les URL des pages du site peuvent également être partagées par e-mail.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-107">Site page URLs can also be shared via email.</span></span> <span data-ttu-id="3f3c2-108">Les modules de partage social sont couramment utilisés sur les pages de détails sur les produits (PDP) pour aider les utilisateurs à partager des informations sur les produits.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-108">Social share modules are commonly used on product details pages (PDPs) to help users share product information.</span></span>

<span data-ttu-id="3f3c2-109">Chaque module de partage social est un conteneur pour les modules d’éléments de partage social.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-109">Each social share module is a container for social share item modules.</span></span> <span data-ttu-id="3f3c2-110">Chaque module d’élément de partage social peut être configuré pour pointer vers un média social spécifique.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-110">Each social share item module can be configured to point to a specific social media site.</span></span> <span data-ttu-id="3f3c2-111">Intégration avec Facebook, Twitter, Pinterest, LinkedIn et les e-mails sont pris en charge par défaut.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-111">Integration with Facebook, Twitter, Pinterest, LinkedIn, and email is supported out of the box.</span></span> <span data-ttu-id="3f3c2-112">Lorsqu’un utilisateur du site sélectionne un symbole de réseau social, un iframe HTML est lancé pour le site de réseau social respectif.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-112">When a site user selects a social media symbol, an HTML iframe is launched for the respective social media site.</span></span> <span data-ttu-id="3f3c2-113">Dans l’iframe, l’utilisateur peut se connecter et publier le contenu de la page qu’il consultait.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-113">Within the iframe, the user can sign in and post the page content that they were viewing.</span></span>

<span data-ttu-id="3f3c2-114">Chaque plateforme de média social peut suivre les cookies, ce module oblige donc les utilisateurs du site à accepter le message de notification de consentement aux cookies.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-114">Each social media platform may track cookies, so this module requires site users to accept the cookie consent notification message.</span></span> <span data-ttu-id="3f3c2-115">Lorsque le consentement aux cookies n’est pas accepté, le module est masqué sur la page.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-115">When cookie consent is not accepted, the module will be hidden on the page.</span></span> <span data-ttu-id="3f3c2-116">Pour plus d’informations, voir [Conformité des cookies](cookie-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="3f3c2-116">For more information, see [Cookie compliance](cookie-compliance.md).</span></span>

<span data-ttu-id="3f3c2-117">L’illustration suivante met en évidence un exemple de module de partage social utilisé sur une page de détails de produit.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-117">The following illustration highlights an example of a social share module used on a product details page.</span></span>

![Exemple de module de partage social](./media/ecommerce-socialshare.png)

## <a name="social-share-module-properties"></a><span data-ttu-id="3f3c2-119">Propriétés du module Partage social</span><span class="sxs-lookup"><span data-stu-id="3f3c2-119">Social share module properties</span></span>

| <span data-ttu-id="3f3c2-120">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="3f3c2-120">Property name</span></span>             | <span data-ttu-id="3f3c2-121">Valeur</span><span class="sxs-lookup"><span data-stu-id="3f3c2-121">Value</span></span>                 | <span data-ttu-id="3f3c2-122">Description</span><span class="sxs-lookup"><span data-stu-id="3f3c2-122">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="3f3c2-123">Légende</span><span class="sxs-lookup"><span data-stu-id="3f3c2-123">Caption</span></span>                  | <span data-ttu-id="3f3c2-124">Détails</span><span class="sxs-lookup"><span data-stu-id="3f3c2-124">Text</span></span> | <span data-ttu-id="3f3c2-125">Cette propriété spécifie une légende pour le module.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-125">This property specifies a caption for the module.</span></span> |
| <span data-ttu-id="3f3c2-126">Orientation</span><span class="sxs-lookup"><span data-stu-id="3f3c2-126">Orientation</span></span> | <span data-ttu-id="3f3c2-127">**Horizontal** ou **Vertical**</span><span class="sxs-lookup"><span data-stu-id="3f3c2-127">**Horizontal** or **Vertical**</span></span>  | <span data-ttu-id="3f3c2-128">Cette propriété définit l’orientation de la mise en page des éléments de médias sociaux.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-128">This property defines the layout orientation for the social media items.</span></span> |

## <a name="social-share-item-module-properties"></a><span data-ttu-id="3f3c2-129">Propriétés du module d’élément Partage social</span><span class="sxs-lookup"><span data-stu-id="3f3c2-129">Social share item module properties</span></span>
| <span data-ttu-id="3f3c2-130">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="3f3c2-130">Property name</span></span>             | <span data-ttu-id="3f3c2-131">Valeur</span><span class="sxs-lookup"><span data-stu-id="3f3c2-131">Value</span></span>                 | <span data-ttu-id="3f3c2-132">Description</span><span class="sxs-lookup"><span data-stu-id="3f3c2-132">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="3f3c2-133">Réseaux sociaux</span><span class="sxs-lookup"><span data-stu-id="3f3c2-133">Social media</span></span>              | <span data-ttu-id="3f3c2-134">**Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **E-mail**</span><span class="sxs-lookup"><span data-stu-id="3f3c2-134">**Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **Mail**</span></span> | <span data-ttu-id="3f3c2-135">Un menu déroulant avec une liste de plateformes de médias sociaux.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-135">A drop-down menu with a list of social media platforms.</span></span> |
| <span data-ttu-id="3f3c2-136">Icône</span><span class="sxs-lookup"><span data-stu-id="3f3c2-136">Icon</span></span> |<span data-ttu-id="3f3c2-137">Image</span><span class="sxs-lookup"><span data-stu-id="3f3c2-137">Image</span></span>    | <span data-ttu-id="3f3c2-138">Ce sera l’image qui sera affichée pour les médias sociaux respectifs.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-138">This will be the image that will be shown for the respective social media.</span></span> <span data-ttu-id="3f3c2-139">En tant que meilleure pratique, reportez-vous au Kit de développement logiciel (SDK) de la plateforme de médias sociaux pour obtenir l’image recommandée à utiliser pour chaque plateforme.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-139">As a best practice, refer to the social media platform's SDK for the recommended image to use for each platform.</span></span> |

## <a name="add-a-social-share-module-to-a-buy-box-module"></a><span data-ttu-id="3f3c2-140">Ajouter un module de partage social à un module de zone d’achat</span><span class="sxs-lookup"><span data-stu-id="3f3c2-140">Add a social share module to a buy box module</span></span>

<span data-ttu-id="3f3c2-141">Pour ajouter un module de partage social à un module de zone d’achat, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-141">To add a social share module to a buy box module, follow these steps.</span></span>

1. <span data-ttu-id="3f3c2-142">Dans le site Fabrikam, sélectionnez **Pages**, puis la page **DefaultPDP** pour ouvrir la page des détails du produit.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-142">In the Fabrikam site, select **Pages**, and then select the **DefaultPDP** page to open the product details page.</span></span> 
1. <span data-ttu-id="3f3c2-143">Dans l’emplacement **Zone d’achat (obligatoire)**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-143">In the **Buybox (required)** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3f3c2-144">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **Partage social**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-144">In the **Add Module** dialog box, select the **Social Share** module, and then select **OK**.</span></span>
1. <span data-ttu-id="3f3c2-145">Dans l’emplacement **Partage social**, sélectionnez le bouton (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-145">In the **Social Share** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3f3c2-146">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **SocialShare**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-146">In the **Add Module** dialog box, select the **SocialShare** module, and then select **OK**.</span></span>
1. <span data-ttu-id="3f3c2-147">Dans le volet des propriétés du module **SocialShare**, sous **Orientation**, sélectionnez **Horizontal**.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-147">In the properties pane of the **SocialShare** module, under **Orientation**, select **Horizontal**.</span></span> <span data-ttu-id="3f3c2-148">Ajoutez une légende si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-148">Add a caption as needed.</span></span>
1. <span data-ttu-id="3f3c2-149">Dans l’emplacement **SocialShare**, sélectionnez le bouton (**...**), puis sélectionnez **Ajouter un module**.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-149">In the **SocialShare** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3f3c2-150">Dans la boîte de dialogue **Ajouter un module**, sélectionnez le module **SocialShareItem**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-150">In the **Add Module** dialog box, select the **SocialShareItem** module, and then select **OK**.</span></span>
1. <span data-ttu-id="3f3c2-151">Dans le volet des propriétés du module **SocialShareItem**, sous **Réseau social**, sélectionnez **Facebook**.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-151">In the properties pane of the **SocialShareItem** module, under **Social Media**, select **Facebook**.</span></span>
1. <span data-ttu-id="3f3c2-152">Dans le volet des propriétés du module **SocialShareItem**, sous **Icône**, sélectionnez **+ Ajouter une image**.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-152">In the properties pane of the **SocialShareItem** module, under **Icon**, select **+ Add an image**.</span></span>
1. <span data-ttu-id="3f3c2-153">Dans la boîte de dialogue **Sélecteur multimédia**, sélectionnez l’image du logo Facebook, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-153">In the **Media Picker** dialog box, select the Facebook logo image, and then select **OK**.</span></span> <span data-ttu-id="3f3c2-154">Si aucune image du logo Facebook n’est présente, sélectionnez **Importer un nouvel élément multimédia** pour en charger une.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-154">If no Facebook logo image is present, select **Upload new media item** to upload one.</span></span>
1. <span data-ttu-id="3f3c2-155">Ajoutez et configurez des modules **SocialShareItem** selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-155">Add and configure additional **SocialShareItem** modules as needed.</span></span>
1. <span data-ttu-id="3f3c2-156">Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-156">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="3f3c2-157">La page affichera le module de partage social.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-157">The page will show the social share module.</span></span>
1. <span data-ttu-id="3f3c2-158">Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.</span><span class="sxs-lookup"><span data-stu-id="3f3c2-158">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3f3c2-159">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="3f3c2-159">Additional resources</span></span>

[<span data-ttu-id="3f3c2-160">Présentation de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="3f3c2-160">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="3f3c2-161">Module Zone d’achat</span><span class="sxs-lookup"><span data-stu-id="3f3c2-161">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="3f3c2-162">Conformité des cookies</span><span class="sxs-lookup"><span data-stu-id="3f3c2-162">Cookie compliance</span></span>](cookie-compliance.md)
