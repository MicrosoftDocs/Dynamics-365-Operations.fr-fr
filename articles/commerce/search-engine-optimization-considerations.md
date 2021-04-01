---
title: Considérations relatives à l'optimisation de moteur de recherche (SEO) pour le site
description: Cette rubrique couvre des considérations sur l'optimisation du moteur de recherche (SEO) pour votre site du développement à la production.
author: psimolin
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c4d1a4a1b14f7af1db1c53bd9ee1993cc9187609
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254791"
---
# <a name="search-engine-optimization-seo-considerations-for-your-site"></a><span data-ttu-id="00591-103">Considérations relatives à l'optimisation de moteur de recherche (SEO) pour le site</span><span class="sxs-lookup"><span data-stu-id="00591-103">Search engine optimization (SEO) considerations for your site</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="00591-104">Cette rubrique couvre les considérations sur l'optimisation du moteur de recherche (SEO) pour votre site du développement à la production.</span><span class="sxs-lookup"><span data-stu-id="00591-104">This topic covers earch engine optimization (SEO) considerations for your site from development to production.</span></span>

## <a name="a-site-that-is-under-development"></a><span data-ttu-id="00591-105">Site en cours de développement</span><span class="sxs-lookup"><span data-stu-id="00591-105">A site that is under development</span></span>

<span data-ttu-id="00591-106">Lorsqu'un site est cours de développement, toutes les pages du site doivent avoir des métabalises **NOINDEX** et **NOFOLLOW**, de sorte que les moteurs de recherche n'indexent pas les pages ni ne stockent les versions de développement de votre site dans leur cache.</span><span class="sxs-lookup"><span data-stu-id="00591-106">While a site is under development, all site pages should have the **NOINDEX** and **NOFOLLOW** meta tags, so that search engines don't index the pages and store development versions of your site in their cache.</span></span> <span data-ttu-id="00591-107">Pour effectuer cette configuration, vous devez ajouter le module par défaut de métabalises au modèle de page du site.</span><span class="sxs-lookup"><span data-stu-id="00591-107">To do this configuration, you must add the default meta tags module to the site page template.</span></span> <span data-ttu-id="00591-108">Les propriétés par défaut de métabalises sont alors disponibles dans la section des propriétés SEO dans l'éditeur de page.</span><span class="sxs-lookup"><span data-stu-id="00591-108">The default meta tags properties will then be available in the SEO properties section in the page editor.</span></span> <span data-ttu-id="00591-109">Vous pouvez utiliser ces propriétés pour gérer les métabalises.</span><span class="sxs-lookup"><span data-stu-id="00591-109">You can use these properties to manage the meta tags.</span></span>

## <a name="soft-launch-of-a-site"></a><span data-ttu-id="00591-110">Lancement provisoire un site</span><span class="sxs-lookup"><span data-stu-id="00591-110">Soft launch of a site</span></span>

<span data-ttu-id="00591-111">Pendant « un lancement provisoire », un site web est rendu disponible à une audience ou à un marché limité avant que le lancement complet se produise.</span><span class="sxs-lookup"><span data-stu-id="00591-111">During a "soft launch," a website is made available to a limited audience or market before the full launch occurs.</span></span> <span data-ttu-id="00591-112">Si vous effectuez un lancement provisoire de votre site web, vous devez envisager de laisser les métabalises **NOINDEX** en place.</span><span class="sxs-lookup"><span data-stu-id="00591-112">If you do a soft launch of your website, you should consider leaving the **NOINDEX** meta tags in place.</span></span> <span data-ttu-id="00591-113">Ainsi, vous garantissez que le lancement provisoire reste limité à l'audience limitée que vous souhaitez atteindre.</span><span class="sxs-lookup"><span data-stu-id="00591-113">In this way, you help guarantee that the soft launch remains restricted to the limited audience that you want to reach.</span></span>

## <a name="a-site-that-is-in-production"></a><span data-ttu-id="00591-114">Un site qui est en production</span><span class="sxs-lookup"><span data-stu-id="00591-114">A site that is in production</span></span>

<span data-ttu-id="00591-115">Lorsqu'un site est en production, vous devez vous assurer que toutes les pages du site sont correctement référencées.</span><span class="sxs-lookup"><span data-stu-id="00591-115">When a site is in production, you should make sure that all site pages are correctly tagged.</span></span> <span data-ttu-id="00591-116">Microsoft Dynamics 365 Commerce utilise les informations entrées pour une page pour afficher toutes les informations SEO dans cette page.</span><span class="sxs-lookup"><span data-stu-id="00591-116">Microsoft Dynamics 365 Commerce uses the information that is entered for a page to render all the SEO information on that page.</span></span> <span data-ttu-id="00591-117">Les modules suivants fournissent cette fonctionnalité : synthèse de page de catégorie, synthèse de la page de liste, et synthèse de la page de produit.</span><span class="sxs-lookup"><span data-stu-id="00591-117">The following modules provide this functionality: category page summary, list page summary, and product page summary.</span></span>

<span data-ttu-id="00591-118">Pour optimiser l'indexation du moteur de recherche, la zone de rendu utilise les informations des propriétés SEO configurées dans Dynamics 365 Commerce et les informations spécifiques au module.</span><span class="sxs-lookup"><span data-stu-id="00591-118">To optimize search engine indexing, the rendering framework uses both information from the SEO properties that are configured in Dynamics 365 Commerce and module-specific information.</span></span> <span data-ttu-id="00591-119">Pour un site qui est en production, vous devez vous assurer que le fichier robots.txt permet l'indexation du site entier, et qu'il contient des liens vers votre document de plan de site publié.</span><span class="sxs-lookup"><span data-stu-id="00591-119">For a site that is in production, you should make sure that the robots.txt file allows for indexing of your whole site, and that it contains links to your published site map document.</span></span> <span data-ttu-id="00591-120">Vous devez activer la fonctionnalité de génération de plan de site dans **Paramètres du site \> Plans de site activés**.</span><span class="sxs-lookup"><span data-stu-id="00591-120">You should turn on the site map generation functionality at **Site Settings \> Site maps enabled**.</span></span>

### <a name="page-seo-settings-for-internal-preview-limited-audiences-and-all-audiences"></a><span data-ttu-id="00591-121">Paramètres SEO de la page pour un aperçu interne, audiences limitées, toutes les audiences</span><span class="sxs-lookup"><span data-stu-id="00591-121">Page SEO settings for internal preview, limited audiences, and all audiences</span></span>

<span data-ttu-id="00591-122">Comme Dynamics 365 Commerce prend en charge des aperçus authentifiés « Tel écrit, tel écran » dans le générateur de page visuel, les auteurs peuvent préparer leur contenu de page sans devoir s'inquiéter que les informations deviennent visibles par les visiteurs du site.</span><span class="sxs-lookup"><span data-stu-id="00591-122">Because Dynamics 365 Commerce supports "what you see is what you get" (WYSIWYG) authenticated previews in visual page builder, authors can prepare their page content without having to worry that the information will become visible to site visitors.</span></span> <span data-ttu-id="00591-123">Si une page doit être publiée, mais que son exposition doit être limitée, elle doit avoir la métabalise **NOINDEX**, afin qu'elle ne soit pas indexée par les moteurs de recherche.</span><span class="sxs-lookup"><span data-stu-id="00591-123">If a page must be published, but its exposure must be limited, it should have the **NOINDEX** meta tag, so that it won't be indexed by search engines.</span></span> <span data-ttu-id="00591-124">Puis, lorsque la page est prête pour toutes les audiences, toutes les métadonnées SEO de base doivent être présentes, afin d'optimiser l'efficacité de l'indexation du moteur de recherche.</span><span class="sxs-lookup"><span data-stu-id="00591-124">Then, when the page is ready for all audiences, all the basic SEO metadata should be present, to maximize the efficiency of search engine indexing.</span></span> <span data-ttu-id="00591-125">En outre, la métabalise **NOLIMIT** doit être supprimée.</span><span class="sxs-lookup"><span data-stu-id="00591-125">Additionally, the **NOLIMIT** meta tag should be removed.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="00591-126">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="00591-126">Additional resources</span></span>

[<span data-ttu-id="00591-127">Gestion des utilisateurs et des rôles de commerce électronique</span><span class="sxs-lookup"><span data-stu-id="00591-127">Manage e-Commerce users and roles</span></span>](manage-ecommerce-users-roles.md)

[<span data-ttu-id="00591-128">Ajout d'un code de script aux pages de site pour prendre en charge la télémétrie</span><span class="sxs-lookup"><span data-stu-id="00591-128">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

[<span data-ttu-id="00591-129">Gérer la stratégie de sécurité de contenu (CSP)</span><span class="sxs-lookup"><span data-stu-id="00591-129">Manage Content Security Policy (CSP)</span></span>](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]