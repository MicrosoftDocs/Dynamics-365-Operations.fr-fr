---
title: Module de consentement aux cookies
description: Cette rubrique couvre les modules de consentement aux cookies et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 60ce530575841c22355e4a14e8b0bbec6c0e35ab
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817280"
---
# <a name="cookie-consent-module"></a><span data-ttu-id="dee08-103">Module de consentement aux cookies</span><span class="sxs-lookup"><span data-stu-id="dee08-103">Cookie consent module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="dee08-104">Cette rubrique couvre les modules de consentement aux cookies et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="dee08-104">This topic covers cookie consent modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="dee08-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="dee08-105">Overview</span></span>

<span data-ttu-id="dee08-106">Le module de consentement des cookies invite les utilisateurs du site à donner explicitement leur consentement pour autoriser les cookies pour toute fonctionnalité ou module qui suit les cookies du navigateur.</span><span class="sxs-lookup"><span data-stu-id="dee08-106">The cookie consent module prompts site users to explicitly provide consent to allow cookies for any feature or module that tracks browser cookies.</span></span> <span data-ttu-id="dee08-107">Le consentement est requis la première fois qu’un utilisateur du site navigue sur un site dans une nouvelle session de navigateur.</span><span class="sxs-lookup"><span data-stu-id="dee08-107">The consent is required the first time a site user browses a site in a new browser session.</span></span> <span data-ttu-id="dee08-108">Lorsque le consentement est reçu, il est suivi et l’utilisateur du site ne sera plus invité à donner son consentement.</span><span class="sxs-lookup"><span data-stu-id="dee08-108">When consent is received, it is tracked and the site user will not be prompted for consent again.</span></span> <span data-ttu-id="dee08-109">Pour plus d’informations, voir [Conformité des cookies](cookie-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="dee08-109">For more information, see [Cookie compliance](cookie-compliance.md).</span></span>

<span data-ttu-id="dee08-110">Si le consentement aux cookies de l’utilisateur du site n’est pas obtenu, les fonctionnalités ou modules qui nécessitent le consentement aux cookies ne seront pas affichés sur la page.</span><span class="sxs-lookup"><span data-stu-id="dee08-110">If site user cookie consent is not received, any features or modules that require cookie consent will not be rendered on the page.</span></span> <span data-ttu-id="dee08-111">Par exemple, le module de paiement, le module de partage social et la fonctionnalité de magasin préféré nécessitent tous le consentement aux cookies et ne seront pas affichés si le consentement de l’utilisateur du site n’est pas obtenu.</span><span class="sxs-lookup"><span data-stu-id="dee08-111">For example, the checkout module, social share module, and preferred store feature all require cookie consent and will not be rendered if site user consent is not received.</span></span> 

<span data-ttu-id="dee08-112">Un module de consentement aux cookies peut être configuré sur le fragment d’en-tête d’une page afin qu’il puisse être appliqué lors du chargement de la page.</span><span class="sxs-lookup"><span data-stu-id="dee08-112">A cookie consent module can be configured on a page's header fragment so that it can be enforced when the page loads.</span></span> <span data-ttu-id="dee08-113">Le module de consentement aux cookies doit comporter un message clair informant l’utilisateur du site de l’utilisation des cookies sur le site et doit fournir un lien vers la page de protection des données personnelles du site.</span><span class="sxs-lookup"><span data-stu-id="dee08-113">The cookie consent module should have a clear message informing the site user about cookie usage on the site and should provide a link to the site's privacy page.</span></span>

<span data-ttu-id="dee08-114">L’illustration suivante met en évidence un exemple de message de consentement aux cookies avec un lien vers la page de politique de protection des données personnelles du site affiché sur l’en-tête d’une page de site.</span><span class="sxs-lookup"><span data-stu-id="dee08-114">The following illustration highlights an example of a cookie consent message with a link to the site's privacy policy page displayed on the header of a site page.</span></span>
<span data-ttu-id="dee08-115">![Exemple de module de consentement aux cookies](./media/ecommerce-cookieconsent.png)</span><span class="sxs-lookup"><span data-stu-id="dee08-115">![Example of a cookie consent module](./media/ecommerce-cookieconsent.png)</span></span>

## <a name="cookie-consent-module-properties"></a><span data-ttu-id="dee08-116">Propriétés du module de consentement aux cookies</span><span class="sxs-lookup"><span data-stu-id="dee08-116">Cookie consent module properties</span></span>

| <span data-ttu-id="dee08-117">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="dee08-117">Property name</span></span>             | <span data-ttu-id="dee08-118">Valeur</span><span class="sxs-lookup"><span data-stu-id="dee08-118">Value</span></span>                 | <span data-ttu-id="dee08-119">Description</span><span class="sxs-lookup"><span data-stu-id="dee08-119">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="dee08-120">Texte enrichi</span><span class="sxs-lookup"><span data-stu-id="dee08-120">Rich Text</span></span>                  | <span data-ttu-id="dee08-121">Texte enrichi</span><span class="sxs-lookup"><span data-stu-id="dee08-121">Rich Text</span></span> | <span data-ttu-id="dee08-122">Spécifie une notification de texte enrichi aux utilisateurs du site indiquant que le site utilise des cookies de navigateur et que les utilisateurs doivent accepter l’utilisation de cookies pour que le site soit pleinement fonctionnel.</span><span class="sxs-lookup"><span data-stu-id="dee08-122">Specifies a Rich Text notification to site users that the site uses browser cookies and that users should accept the use of cookies for the site to be fully functional.</span></span> |
| <span data-ttu-id="dee08-123">Liens</span><span class="sxs-lookup"><span data-stu-id="dee08-123">Links</span></span> | <span data-ttu-id="dee08-124">URL</span><span class="sxs-lookup"><span data-stu-id="dee08-124">URL</span></span> | <span data-ttu-id="dee08-125">Un ou plusieurs liens peuvent être ajoutés à la page de protection des données personnelles d’un site qui décrit les types de cookies suivis sur le site.</span><span class="sxs-lookup"><span data-stu-id="dee08-125">One or more links can be added to a site's privacy page that describes the types of cookies that are tracked on the site.</span></span> |

## <a name="add-a-cookie-consent-module-to-site-pages"></a><span data-ttu-id="dee08-126">Ajouter un module de consentement aux cookies aux pages du site</span><span class="sxs-lookup"><span data-stu-id="dee08-126">Add a cookie consent module to site pages</span></span>

<span data-ttu-id="dee08-127">Pour ajouter efficacement un module de consentement aux cookies à plusieurs pages du site, il peut être ajouté à un fragment d’en-tête de page partagé.</span><span class="sxs-lookup"><span data-stu-id="dee08-127">To efficiently add a cookie consent module to multiple site pages, it can be added to a shared page header fragment.</span></span> <span data-ttu-id="dee08-128">Une fois le fragment d’en-tête ajouté à toutes les pages du site, une notification de consentement aux cookies sera automatiquement affichée la première fois qu’un utilisateur du site accède à une page du site.</span><span class="sxs-lookup"><span data-stu-id="dee08-128">After the header fragment is added to all site pages, a cookie consent notification will automatically be rendered the first time a site user navigates to any site page.</span></span>

<span data-ttu-id="dee08-129">Pour plus d’informations sur les fragments d’en-tête et les modules, voir [Module En-tête](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="dee08-129">For more information about header fragments and modules, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dee08-130">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="dee08-130">Additional resources</span></span>

[<span data-ttu-id="dee08-131">Présentation de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="dee08-131">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="dee08-132">Module En-tête</span><span class="sxs-lookup"><span data-stu-id="dee08-132">Header module</span></span>](author-header-module.md) 

[<span data-ttu-id="dee08-133">Conformité des cookies</span><span class="sxs-lookup"><span data-stu-id="dee08-133">Cookie compliance</span></span>](cookie-compliance.md)
