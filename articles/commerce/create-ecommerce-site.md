---
title: Création d'un site de commerce électronique
description: Cette rubrique décrit les étapes et les informations requises pour créer un site de commerce électronique dans le générateur de site de Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 03/02/2020
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
ms.openlocfilehash: 7177bae911dfa91a645b40581bf23b3ed76562a3
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096772"
---
# <a name="create-an-e-commerce-site"></a><span data-ttu-id="11865-103">Création d'un site de commerce électronique</span><span class="sxs-lookup"><span data-stu-id="11865-103">Create an e-Commerce site</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="11865-104">Cette rubrique décrit les étapes et les informations requises pour créer un site de commerce électronique dans le générateur de site de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="11865-104">This topic describes the steps and information required to create a new e-Commerce site in Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="11865-105">Avant de pouvoir commencer à développer votre site de commerce électronique, vous devez d'abord créer un site dans le générateur de site.</span><span class="sxs-lookup"><span data-stu-id="11865-105">Before you can start developing your e-Commerce site, you must first establish a new site in site builder.</span></span> 


<span data-ttu-id="11865-106">Pour commencer à développer votre site de commerce électronique, vous devez d'abord créer un site dans l'environnement de création de site.</span><span class="sxs-lookup"><span data-stu-id="11865-106">To start to develop your e-Commerce site, you must first establish a new site in the site authoring environment.</span></span> <span data-ttu-id="11865-107">Avant de pouvoir créer un site, au moins un magasin en ligne doit être créé dans Commerce.</span><span class="sxs-lookup"><span data-stu-id="11865-107">Before you can create a new site, at least one online store must be created in Commerce.</span></span> 


## <a name="set-up-your-site"></a><span data-ttu-id="11865-108">Configurer votre site</span><span class="sxs-lookup"><span data-stu-id="11865-108">Set up your site</span></span>

<span data-ttu-id="11865-109">Pour paramétrer votre site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="11865-109">To set up your site, do the following.</span></span>

1. <span data-ttu-id="11865-110">Ouvrez l'environnement du générateur de site.</span><span class="sxs-lookup"><span data-stu-id="11865-110">Open the site builder environment.</span></span> <span data-ttu-id="11865-111">Vous pouvez trouver un lien vers le générateur de site dans Microsoft Lifecycle Services (LCS) sur la page des fonctionnalités d'environnement pour Commerce.</span><span class="sxs-lookup"><span data-stu-id="11865-111">You can find a link to site builder in Microsoft Lifecycle Services (LCS) in the environment features page for Commerce.</span></span>
1. <span data-ttu-id="11865-112">Sur la page d'accueil de l'environnement de création de site, sélectionnez **Nouveau site**.</span><span class="sxs-lookup"><span data-stu-id="11865-112">On the home page for the site authoring environment, select **New site**.</span></span>
1. <span data-ttu-id="11865-113">Dans la boîte de dialogue **Nouveau site**, fournissez les informations suivantes.</span><span class="sxs-lookup"><span data-stu-id="11865-113">In the **New site** dialog box, provide the following information.</span></span>

| <span data-ttu-id="11865-114">Champ</span><span class="sxs-lookup"><span data-stu-id="11865-114">Field</span></span>                               | <span data-ttu-id="11865-115">Description</span><span class="sxs-lookup"><span data-stu-id="11865-115">Description</span></span> |
|-------------------------------------|-------------|
| <span data-ttu-id="11865-116">Nom du site</span><span class="sxs-lookup"><span data-stu-id="11865-116">Site name</span></span>                           | <span data-ttu-id="11865-117">Entrez le nom d'affichage qui doit être utilisé pour votre site dans l'environnement de création de site.</span><span class="sxs-lookup"><span data-stu-id="11865-117">Enter the display name that should be used for your site in the site authoring environment.</span></span> <span data-ttu-id="11865-118">Ce nom est visible uniquement dans l'environnement de création et n'est pas affiché aux clients.</span><span class="sxs-lookup"><span data-stu-id="11865-118">This name is visible only in the authoring environment and will not be shown to customers.</span></span> |
| <span data-ttu-id="11865-119">Groupe de sécurité de l'administrateur de site</span><span class="sxs-lookup"><span data-stu-id="11865-119">Site administrator's security group</span></span> | <span data-ttu-id="11865-120">Spécifiez le groupe de sécurité Microsoft Azure Active Directory (Azure AD) qui gère les utilisateurs qui disposent du rôle Administrateur de site dans ce site.</span><span class="sxs-lookup"><span data-stu-id="11865-120">Specify the Microsoft Azure Active Directory (Azure AD) security group that manages users who have the site administrator role in this site.</span></span> |
| <span data-ttu-id="11865-121">Canal par défaut (numéro d’unité opérationnelle)</span><span class="sxs-lookup"><span data-stu-id="11865-121">Default channel (operating unit number)</span></span> | <span data-ttu-id="11865-122">Sélectionnez le magasin en ligne auquel ce site sert de vitrine web.</span><span class="sxs-lookup"><span data-stu-id="11865-122">Select the online store that this site will serve as the web storefront for.</span></span> <span data-ttu-id="11865-123">Si vous souhaitez que votre site de commerce électronique prenne en charge des magasins en ligne, vous devez associer les magasins à votre site dans **Paramètres du site** une fois le site paramétré.</span><span class="sxs-lookup"><span data-stu-id="11865-123">If you want your e-Commerce site to support multiple online stores, you must associate the stores with your site in **Site settings** after the site is set up.</span></span> |
| <span data-ttu-id="11865-124">Langue par défaut</span><span class="sxs-lookup"><span data-stu-id="11865-124">Default language</span></span>                            | <span data-ttu-id="11865-125">Spécifiez la langue par défaut pour ces magasin et marché en ligne.</span><span class="sxs-lookup"><span data-stu-id="11865-125">Specify the default language for this online store and market.</span></span> <span data-ttu-id="11865-126">Un magasin en ligne peut prendre en charge plusieurs langues.</span><span class="sxs-lookup"><span data-stu-id="11865-126">An online store can support multiple languages.</span></span> <span data-ttu-id="11865-127">Si vous souhaitez prendre en charge plusieurs langues pour un ce magasin en ligne ou un magasin en ligne différent, vous pouvez configurer cette prise en charge dans **Paramètres du site** une fois le site paramétré.</span><span class="sxs-lookup"><span data-stu-id="11865-127">If you want to support multiple languages for this online store or another online store, you can configure that support in **Site settings** after the site is set up.</span></span>  |
| <span data-ttu-id="11865-128">Domaine</span><span class="sxs-lookup"><span data-stu-id="11865-128">Domain</span></span>                              | <span data-ttu-id="11865-129">Sélectionnez un nom de domaine qui servira de domaine à ce magasin enligne.</span><span class="sxs-lookup"><span data-stu-id="11865-129">Select a domain name that will serve as the domain for this online store.</span></span> <span data-ttu-id="11865-130">Si vous n'avez configuré aucun domaine dans LCS, vous pouvez laisser ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="11865-130">If you haven't configured any domains in LCS, you can leave this field blank.</span></span> <span data-ttu-id="11865-131">Une fois votre domaine configuré dans LCS, vous devez l'ajouter à votre magasin en ligne dans **Paramètres du site**.</span><span class="sxs-lookup"><span data-stu-id="11865-131">After your domain is configured in LCS, you must add it to your online store in **Site settings**.</span></span>  |
| <span data-ttu-id="11865-132">Chemin</span><span class="sxs-lookup"><span data-stu-id="11865-132">Path</span></span>                              | <span data-ttu-id="11865-133">Lorsque votre site prend en charge plusieurs langues pour un nom de domaine donné, utilisez le champ de chemin d'accès pour créer une seul URL de site pour cette combinaison de domaine et de langue.</span><span class="sxs-lookup"><span data-stu-id="11865-133">When your site supports more than one language for a given domain name, use the path field to create a unique site URL for that domain and language combination.</span></span> <span data-ttu-id="11865-134">Si la langue spécifiée dans le champ **Langue par défaut** est la seule langue vous avez prise en charge pour ce domaine, ou reste la langue par défaut après avoir localisé votre site dans des langues supplémentaires, nous recommandons de laisser ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="11865-134">If the language you specified in the **Default language** field is the only language you will support for this domain, or will continue to be the default language after you have localized your site into additional languages, we recommend that you leave this field empty.</span></span> |


<span data-ttu-id="11865-135">Lorsque votre site est créé, vous pouvez vérifier qu'il est associé à votre magasin en ligne en sélectionnant l'onglet **Produits**. Vous devez voir l'assortiment des produits affecté au magasin en ligne.</span><span class="sxs-lookup"><span data-stu-id="11865-135">After your site is created, you can verify that it is associated with your online store by selecting the **Products** tab. You should see the assortment of products that has been allocated to the online store.</span></span> <span data-ttu-id="11865-136">Vous pouvez également utiliser le menu déroulant situé dans la partie supérieure gauche de la page pour accéder aux produits alloués par catégorie.</span><span class="sxs-lookup"><span data-stu-id="11865-136">You can also use the drop-down menu in the upper left of the page to access the allocated products by category.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="11865-137">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="11865-137">Additional resources</span></span>

[<span data-ttu-id="11865-138">Configuration du nom de domaine</span><span class="sxs-lookup"><span data-stu-id="11865-138">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="11865-139">Déploiement d'un nouveau site de commerce électronique</span><span class="sxs-lookup"><span data-stu-id="11865-139">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="11865-140">Paramétrer un canal de magasin en ligne</span><span class="sxs-lookup"><span data-stu-id="11865-140">Set up an online store channel</span></span>](online-stores.md)

[<span data-ttu-id="11865-141">Association d'un site en ligne avec un canal</span><span class="sxs-lookup"><span data-stu-id="11865-141">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="11865-142">Gérer les fichiers robots.txt</span><span class="sxs-lookup"><span data-stu-id="11865-142">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="11865-143">Importer des redirections d'URL en bloc</span><span class="sxs-lookup"><span data-stu-id="11865-143">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="11865-144">Configurer un client B2C dans Commerce</span><span class="sxs-lookup"><span data-stu-id="11865-144">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="11865-145">Paramétrer des pages personnalisées pour les ouvertures de session utilisateur</span><span class="sxs-lookup"><span data-stu-id="11865-145">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="11865-146">Configurer plusieurs locataires B2C dans un environnement Commerce</span><span class="sxs-lookup"><span data-stu-id="11865-146">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="11865-147">Ajouter la prise en charge d'un réseau de diffusion de contenu (CDN)</span><span class="sxs-lookup"><span data-stu-id="11865-147">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="11865-148">Activation de la détection du magasin selon l’emplacement</span><span class="sxs-lookup"><span data-stu-id="11865-148">Enable location-based store detection</span></span>](enable-store-detection.md)
