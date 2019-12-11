---
title: Création d'un site de commerce électronique
description: Cette rubrique décrit les tâches associées à la création d'un site de commerce électronique dans Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fd87a51b73deae64867b0420c00db9fce7c79336
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697127"
---
# <a name="create-an-e-commerce-site"></a><span data-ttu-id="1e144-103">Création d'un site de commerce électronique</span><span class="sxs-lookup"><span data-stu-id="1e144-103">Create an e-Commerce site</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="1e144-104">Cette rubrique décrit les tâches associées à la création d'un site de commerce électronique dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1e144-104">This topic describes the tasks that are associated with the creation of a new e-Commerce site in Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="1e144-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="1e144-105">Overview</span></span>

<span data-ttu-id="1e144-106">Pour commencer à développer votre site de commerce électronique, vous devez d'abord créer un site dans l'environnement de création de site.</span><span class="sxs-lookup"><span data-stu-id="1e144-106">To start to develop your e-Commerce site, you must first establish a new site in the site authoring environment.</span></span> <span data-ttu-id="1e144-107">Avant de créer un site, au moins un magasin en ligne doit être créé dans Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="1e144-107">Before you can create a new site, at least one online store must be created in Dynamics 365 Retail.</span></span> 

## <a name="set-up-your-site"></a><span data-ttu-id="1e144-108">Configurer votre site</span><span class="sxs-lookup"><span data-stu-id="1e144-108">Set up your site</span></span>

<span data-ttu-id="1e144-109">Pour paramétrer votre site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="1e144-109">To set up your site, do the following.</span></span>

1. <span data-ttu-id="1e144-110">Dans Microsoft Lifecycle Services (LCS), sélectionnez le lien pour l'environnement de création de site.</span><span class="sxs-lookup"><span data-stu-id="1e144-110">In Microsoft Lifecycle Services (LCS), select the link for the site authoring environment.</span></span> 
1. <span data-ttu-id="1e144-111">Sur la page d'accueil de l'environnement de création de site, sélectionnez **Nouveau site**.</span><span class="sxs-lookup"><span data-stu-id="1e144-111">On the home page for the site authoring environment, select **New site**.</span></span>
1. <span data-ttu-id="1e144-112">Dans la boîte de dialogue **Nouveau site**, fournissez les informations suivantes.</span><span class="sxs-lookup"><span data-stu-id="1e144-112">In the **New site** dialog box, provide the following information.</span></span>

| <span data-ttu-id="1e144-113">Champ</span><span class="sxs-lookup"><span data-stu-id="1e144-113">Field</span></span>                               | <span data-ttu-id="1e144-114">Description</span><span class="sxs-lookup"><span data-stu-id="1e144-114">Description</span></span> |
|-------------------------------------|-------------|
| <span data-ttu-id="1e144-115">Nom du site</span><span class="sxs-lookup"><span data-stu-id="1e144-115">Site name</span></span>                           | <span data-ttu-id="1e144-116">Entrez le nom d'affichage qui doit être utilisé pour votre site dans l'environnement de création de site.</span><span class="sxs-lookup"><span data-stu-id="1e144-116">Enter the display name that should be used for your site in the site authoring environment.</span></span> <span data-ttu-id="1e144-117">Ce nom est visible uniquement dans l'environnement de création et n'est pas affiché aux clients.</span><span class="sxs-lookup"><span data-stu-id="1e144-117">This name is visible only in the authoring environment and will not be shown to customers.</span></span> |
| <span data-ttu-id="1e144-118">Groupe de sécurité de l'administrateur de site</span><span class="sxs-lookup"><span data-stu-id="1e144-118">Site administrator's security group</span></span> | <span data-ttu-id="1e144-119">Spécifiez le groupe de sécurité Microsoft Azure Active Directory (Azure AD) qui gère les utilisateurs qui disposent du rôle Administrateur de site dans ce site.</span><span class="sxs-lookup"><span data-stu-id="1e144-119">Specify the Microsoft Azure Active Directory (Azure AD) security group that manages users who have the site administrator role in this site.</span></span> |
| <span data-ttu-id="1e144-120">Canal par défaut (numéro d’unité opérationnelle)</span><span class="sxs-lookup"><span data-stu-id="1e144-120">Default channel (operating unit number)</span></span> | <span data-ttu-id="1e144-121">Sélectionnez le magasin en ligne auquel ce site sert de vitrine web.</span><span class="sxs-lookup"><span data-stu-id="1e144-121">Select the online store that this site will serve as the web storefront for.</span></span> <span data-ttu-id="1e144-122">Si vous souhaitez que votre site de commerce électronique prenne en charge des magasins en ligne, vous devez associer les magasins à votre site dans **Paramètres du site** une fois le site paramétré.</span><span class="sxs-lookup"><span data-stu-id="1e144-122">If you want your e-Commerce site to support multiple online stores, you must associate the stores with your site in **Site settings** after the site is set up.</span></span> |
| <span data-ttu-id="1e144-123">Langue par défaut</span><span class="sxs-lookup"><span data-stu-id="1e144-123">Default language</span></span>                            | <span data-ttu-id="1e144-124">Spécifiez la langue par défaut pour ces magasin et marché en ligne.</span><span class="sxs-lookup"><span data-stu-id="1e144-124">Specify the default language for this online store and market.</span></span> <span data-ttu-id="1e144-125">Un magasin en ligne peut prendre en charge plusieurs langues.</span><span class="sxs-lookup"><span data-stu-id="1e144-125">An online store can support multiple languages.</span></span> <span data-ttu-id="1e144-126">Si vous souhaitez prendre en charge plusieurs langues pour un ce magasin en ligne ou un magasin en ligne différent, vous pouvez configurer cette prise en charge dans **Paramètres du site** une fois le site paramétré.</span><span class="sxs-lookup"><span data-stu-id="1e144-126">If you want to support multiple languages for this online store or another online store, you can configure that support in **Site settings** after the site is set up.</span></span>  |
| <span data-ttu-id="1e144-127">Domaine</span><span class="sxs-lookup"><span data-stu-id="1e144-127">Domain</span></span>                              | <span data-ttu-id="1e144-128">Sélectionnez un nom de domaine qui servira de domaine à ce magasin enligne.</span><span class="sxs-lookup"><span data-stu-id="1e144-128">Select a domain name that will serve as the domain for this online store.</span></span> <span data-ttu-id="1e144-129">Si vous n'avez configuré aucun domaine dans LCS, vous pouvez laisser ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="1e144-129">If you haven't configured any domains in LCS, you can leave this field blank.</span></span> <span data-ttu-id="1e144-130">Une fois votre domaine configuré dans LCS, vous devez l'ajouter à votre magasin en ligne dans **Paramètres du site**.</span><span class="sxs-lookup"><span data-stu-id="1e144-130">After your domain is configured in LCS, you must add it to your online store in **Site settings**.</span></span>  |
| <span data-ttu-id="1e144-131">Chemin</span><span class="sxs-lookup"><span data-stu-id="1e144-131">Path</span></span>                              | <span data-ttu-id="1e144-132">Lorsque votre site prend en charge plusieurs langues pour un nom de domaine donné, utilisez le champ de chemin d'accès pour créer une seul URL de site pour cette combinaison de domaine et de langue.</span><span class="sxs-lookup"><span data-stu-id="1e144-132">When your site supports more than one language for a given domain name, use the path field to create a unique site URL for that domain and language combination.</span></span> <span data-ttu-id="1e144-133">Si la langue spécifiée dans le champ **Langue par défaut** est la seule langue vous avez prise en charge pour ce domaine, ou reste la langue par défaut après avoir localisé votre site dans des langues supplémentaires, nous recommandons de laisser ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="1e144-133">If the language you specified in the **Default language** field is the only language you will support for this domain, or will continue to be the default language after you have localized your site into additional languages, we recommend that you leave this field empty.</span></span> |


<span data-ttu-id="1e144-134">Lorsque votre site est créé, vous pouvez vérifier qu'il est associé à votre magasin en ligne en sélectionnant l'onglet **Produits**. Vous devez voir l'assortiment des produits affecté au magasin en ligne.</span><span class="sxs-lookup"><span data-stu-id="1e144-134">After your site is created, you can verify that it is associated with your online store by selecting the **Products** tab. You should see the assortment of products that has been allocated to the online store.</span></span> <span data-ttu-id="1e144-135">Vous pouvez également utiliser le menu déroulant situé dans la partie supérieure gauche de la page pour accéder aux produits alloués par catégorie.</span><span class="sxs-lookup"><span data-stu-id="1e144-135">You can also use the drop-down menu in the upper left of the page to access the allocated products by category.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1e144-136">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="1e144-136">Additional resources</span></span>

[<span data-ttu-id="1e144-137">Vue d'ensemble du magasin en ligne</span><span class="sxs-lookup"><span data-stu-id="1e144-137">Online store overview</span></span>](online-store-overview.md)

[<span data-ttu-id="1e144-138">Déploiement d'un nouveau site de commerce électronique</span><span class="sxs-lookup"><span data-stu-id="1e144-138">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="1e144-139">Association d'un site en ligne avec un canal</span><span class="sxs-lookup"><span data-stu-id="1e144-139">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="1e144-140">Configuration du nom de domaine</span><span class="sxs-lookup"><span data-stu-id="1e144-140">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="1e144-141">Ajouter la prise en charge d'un réseau de diffusion de contenu (CDN)</span><span class="sxs-lookup"><span data-stu-id="1e144-141">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="1e144-142">Activation de la détection du magasin selon l’emplacement</span><span class="sxs-lookup"><span data-stu-id="1e144-142">Enable location-based store detection</span></span>](enable-store-detection.md)

[<span data-ttu-id="1e144-143">Paramétrer des pages personnalisées pour les ouvertures de session utilisateur</span><span class="sxs-lookup"><span data-stu-id="1e144-143">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="1e144-144">Vue d'ensemble de la page d'accueil de création</span><span class="sxs-lookup"><span data-stu-id="1e144-144">Authoring home page overview</span></span>](authoring-home-overview.md)

[<span data-ttu-id="1e144-145">Ajouter une nouvelle page de site</span><span class="sxs-lookup"><span data-stu-id="1e144-145">Add a new site page</span></span>](add-new-page.md)
