---
title: Création d’un site d'e-commerce
description: Cette rubrique décrit les étapes et les informations requises pour créer un site d'e-commerce dans le générateur de site de Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cf084f90d203d84c91ddf7c0d963780b895ef23d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963033"
---
# <a name="create-an-e-commerce-site"></a><span data-ttu-id="1172f-103">Création d’un site d'e-commerce</span><span class="sxs-lookup"><span data-stu-id="1172f-103">Create an e-commerce site</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1172f-104">Cette rubrique décrit les étapes et les informations requises pour créer un site d'e-commerce dans le générateur de site de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1172f-104">This topic describes the steps and information required to create a new e-commerce site in Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="1172f-105">Lorsque vous utilisez sous licence les fonctionnalités Dynamics 365 Commerce, le générateur de site sera configuré avec un site de démarrage que vous pouvez utiliser comme base pour votre propre site.</span><span class="sxs-lookup"><span data-stu-id="1172f-105">When you license the Dynamics 365 Commerce capabilities, site builder will be provisioned with a starter site that you can use as a basis for your own site.</span></span> <span data-ttu-id="1172f-106">Toutefois, si vous souhaitez partir de zéro ou si vous souhaitez créer un deuxième site, vous devrez créer un nouveau site dans l'environnement de création de site.</span><span class="sxs-lookup"><span data-stu-id="1172f-106">However, if you want to start from scratch or if you want to establish a second site, you will need to establish a new site in the site authoring environment.</span></span> 

## <a name="set-up-your-site"></a><span data-ttu-id="1172f-107">Configurer votre site</span><span class="sxs-lookup"><span data-stu-id="1172f-107">Set up your site</span></span>

<span data-ttu-id="1172f-108">Pour paramétrer votre site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="1172f-108">To set up your site, do the following.</span></span>

1. <span data-ttu-id="1172f-109">Ouvrez l'environnement du générateur de site.</span><span class="sxs-lookup"><span data-stu-id="1172f-109">Open the site builder environment.</span></span> <span data-ttu-id="1172f-110">Vous pouvez trouver un lien vers le générateur de site dans Microsoft Lifecycle Services (LCS) sur la page des fonctionnalités d'environnement pour Commerce.</span><span class="sxs-lookup"><span data-stu-id="1172f-110">You can find a link to site builder in Microsoft Lifecycle Services (LCS) in the environment features page for Commerce.</span></span>
1. <span data-ttu-id="1172f-111">Sur la page d'accueil de l'environnement de création de site, sélectionnez **Nouveau site**.</span><span class="sxs-lookup"><span data-stu-id="1172f-111">On the home page for the site authoring environment, select **New site**.</span></span>
1. <span data-ttu-id="1172f-112">Dans la boîte de dialogue **Nouveau site**, fournissez les informations suivantes.</span><span class="sxs-lookup"><span data-stu-id="1172f-112">In the **New site** dialog box, provide the following information.</span></span>

| <span data-ttu-id="1172f-113">Champ</span><span class="sxs-lookup"><span data-stu-id="1172f-113">Field</span></span>                               | <span data-ttu-id="1172f-114">Description</span><span class="sxs-lookup"><span data-stu-id="1172f-114">Description</span></span> |
|-------------------------------------|-------------|
| <span data-ttu-id="1172f-115">Nom du site</span><span class="sxs-lookup"><span data-stu-id="1172f-115">Site name</span></span>                           | <span data-ttu-id="1172f-116">Entrez le nom d'affichage qui doit être utilisé pour votre site dans l'environnement de création de site.</span><span class="sxs-lookup"><span data-stu-id="1172f-116">Enter the display name that should be used for your site in the site authoring environment.</span></span> <span data-ttu-id="1172f-117">Ce nom est visible uniquement dans l'environnement de création et n'est pas affiché aux clients.</span><span class="sxs-lookup"><span data-stu-id="1172f-117">This name is visible only in the authoring environment and will not be shown to customers.</span></span> |
| <span data-ttu-id="1172f-118">Groupe de sécurité de l'administrateur de site</span><span class="sxs-lookup"><span data-stu-id="1172f-118">Site administrator's security group</span></span> | <span data-ttu-id="1172f-119">Spécifiez le groupe de sécurité Microsoft Azure Active Directory (Azure AD) qui gère les utilisateurs qui disposent du rôle Administrateur de site dans ce site.</span><span class="sxs-lookup"><span data-stu-id="1172f-119">Specify the Microsoft Azure Active Directory (Azure AD) security group that manages users who have the site administrator role in this site.</span></span> |
| <span data-ttu-id="1172f-120">Canal par défaut (numéro d’unité opérationnelle)</span><span class="sxs-lookup"><span data-stu-id="1172f-120">Default channel (operating unit number)</span></span> | <span data-ttu-id="1172f-121">Sélectionnez le magasin en ligne auquel ce site sert de vitrine web.</span><span class="sxs-lookup"><span data-stu-id="1172f-121">Select the online store that this site will serve as the web storefront for.</span></span> <span data-ttu-id="1172f-122">Si vous souhaitez que votre site d'e-commerce prenne en charge des magasins en ligne, vous devez associer les magasins à votre site dans **Paramètres du site** une fois le site paramétré.</span><span class="sxs-lookup"><span data-stu-id="1172f-122">If you want your e-commerce site to support multiple online stores, you must associate the stores with your site in **Site settings** after the site is set up.</span></span> |
| <span data-ttu-id="1172f-123">Langue par défaut</span><span class="sxs-lookup"><span data-stu-id="1172f-123">Default language</span></span>                            | <span data-ttu-id="1172f-124">Spécifiez la langue par défaut pour ces magasin et marché en ligne.</span><span class="sxs-lookup"><span data-stu-id="1172f-124">Specify the default language for this online store and market.</span></span> <span data-ttu-id="1172f-125">Un magasin en ligne peut prendre en charge plusieurs langues.</span><span class="sxs-lookup"><span data-stu-id="1172f-125">An online store can support multiple languages.</span></span> <span data-ttu-id="1172f-126">Si vous souhaitez prendre en charge plusieurs langues pour un ce magasin en ligne ou un magasin en ligne différent, vous pouvez configurer cette prise en charge dans **Paramètres du site** une fois le site paramétré.</span><span class="sxs-lookup"><span data-stu-id="1172f-126">If you want to support multiple languages for this online store or another online store, you can configure that support in **Site settings** after the site is set up.</span></span>  |
| <span data-ttu-id="1172f-127">Domaine</span><span class="sxs-lookup"><span data-stu-id="1172f-127">Domain</span></span>                              | <span data-ttu-id="1172f-128">Sélectionnez un nom de domaine qui servira de domaine à ce magasin enligne.</span><span class="sxs-lookup"><span data-stu-id="1172f-128">Select a domain name that will serve as the domain for this online store.</span></span> <span data-ttu-id="1172f-129">Si vous n'avez configuré aucun domaine dans LCS, vous pouvez laisser ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="1172f-129">If you haven't configured any domains in LCS, you can leave this field blank.</span></span> <span data-ttu-id="1172f-130">Une fois votre domaine configuré dans LCS, vous devez l'ajouter à votre magasin en ligne dans **Paramètres du site**.</span><span class="sxs-lookup"><span data-stu-id="1172f-130">After your domain is configured in LCS, you must add it to your online store in **Site settings**.</span></span>  |
| <span data-ttu-id="1172f-131">Chemin</span><span class="sxs-lookup"><span data-stu-id="1172f-131">Path</span></span>                              | <span data-ttu-id="1172f-132">Lorsque votre site prend en charge plusieurs langues pour un nom de domaine donné, utilisez le champ de chemin d'accès pour créer une seul URL de site pour cette combinaison de domaine et de langue.</span><span class="sxs-lookup"><span data-stu-id="1172f-132">When your site supports more than one language for a given domain name, use the path field to create a unique site URL for that domain and language combination.</span></span> <span data-ttu-id="1172f-133">Si la langue spécifiée dans le champ **Langue par défaut** est la seule langue vous avez prise en charge pour ce domaine, ou reste la langue par défaut après avoir localisé votre site dans des langues supplémentaires, nous recommandons de laisser ce champ vide.</span><span class="sxs-lookup"><span data-stu-id="1172f-133">If the language you specified in the **Default language** field is the only language you will support for this domain, or will continue to be the default language after you have localized your site into additional languages, we recommend that you leave this field empty.</span></span> |


<span data-ttu-id="1172f-134">Lorsque votre site est créé, vous pouvez vérifier qu'il est associé à votre magasin en ligne en sélectionnant l'onglet **Produits**. Vous devez voir l'assortiment des produits affecté au magasin en ligne.</span><span class="sxs-lookup"><span data-stu-id="1172f-134">After your site is created, you can verify that it is associated with your online store by selecting the **Products** tab. You should see the assortment of products that has been allocated to the online store.</span></span> <span data-ttu-id="1172f-135">Vous pouvez également utiliser le menu déroulant situé dans la partie supérieure gauche de la page pour accéder aux produits alloués par catégorie.</span><span class="sxs-lookup"><span data-stu-id="1172f-135">You can also use the drop-down menu in the upper left of the page to access the allocated products by category.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1172f-136">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="1172f-136">Additional resources</span></span>

[<span data-ttu-id="1172f-137">Configuration du nom de domaine</span><span class="sxs-lookup"><span data-stu-id="1172f-137">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="1172f-138">Déployer un nouveau client e-commerce</span><span class="sxs-lookup"><span data-stu-id="1172f-138">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="1172f-139">Associer un site Dynamics 365 Commerce avec un canal en ligne</span><span class="sxs-lookup"><span data-stu-id="1172f-139">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="1172f-140">Gérer les fichiers robots.txt</span><span class="sxs-lookup"><span data-stu-id="1172f-140">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="1172f-141">Importer des redirections d’URL en bloc</span><span class="sxs-lookup"><span data-stu-id="1172f-141">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="1172f-142">Configurer un client B2C dans Commerce</span><span class="sxs-lookup"><span data-stu-id="1172f-142">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="1172f-143">Paramétrer des pages personnalisées pour les ouvertures de session utilisateur</span><span class="sxs-lookup"><span data-stu-id="1172f-143">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="1172f-144">Configurer plusieurs locataires B2C dans un environnement Commerce</span><span class="sxs-lookup"><span data-stu-id="1172f-144">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="1172f-145">Ajouter la prise en charge d’un réseau de diffusion de contenu (CDN)</span><span class="sxs-lookup"><span data-stu-id="1172f-145">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="1172f-146">Activation de la détection du magasin selon l’emplacement</span><span class="sxs-lookup"><span data-stu-id="1172f-146">Enable location-based store detection</span></span>](enable-store-detection.md)
