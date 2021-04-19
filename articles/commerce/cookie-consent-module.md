---
title: Module de consentement aux cookies
description: Cette rubrique couvre les modules de consentement aux cookies et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 2f0118b197f465113bb894e3e57b3e682e04ef36
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796001"
---
# <a name="cookie-consent-module"></a><span data-ttu-id="dd676-103">Module de consentement aux cookies</span><span class="sxs-lookup"><span data-stu-id="dd676-103">Cookie consent module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="dd676-104">Cette rubrique couvre les modules de consentement aux cookies et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="dd676-104">This topic covers cookie consent modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="dd676-105">Le module de consentement des cookies invite les utilisateurs du site à donner explicitement leur consentement pour autoriser les cookies pour toute fonctionnalité ou module qui suit les cookies du navigateur.</span><span class="sxs-lookup"><span data-stu-id="dd676-105">The cookie consent module prompts site users to explicitly provide consent to allow cookies for any feature or module that tracks browser cookies.</span></span> <span data-ttu-id="dd676-106">Le consentement est requis la première fois qu’un utilisateur du site navigue sur un site dans une nouvelle session de navigateur.</span><span class="sxs-lookup"><span data-stu-id="dd676-106">The consent is required the first time a site user browses a site in a new browser session.</span></span> <span data-ttu-id="dd676-107">Lorsque le consentement est reçu, il est suivi et l’utilisateur du site ne sera plus invité à donner son consentement.</span><span class="sxs-lookup"><span data-stu-id="dd676-107">When consent is received, it is tracked and the site user will not be prompted for consent again.</span></span> <span data-ttu-id="dd676-108">Pour plus d’informations, voir [Conformité des cookies](cookie-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="dd676-108">For more information, see [Cookie compliance](cookie-compliance.md).</span></span>

<span data-ttu-id="dd676-109">Si le consentement aux cookies de l’utilisateur du site n’est pas obtenu, les fonctionnalités ou modules qui nécessitent le consentement aux cookies ne seront pas affichés sur la page.</span><span class="sxs-lookup"><span data-stu-id="dd676-109">If site user cookie consent is not received, any features or modules that require cookie consent will not be rendered on the page.</span></span> <span data-ttu-id="dd676-110">Par exemple, le module de paiement, le module de partage social et la fonctionnalité de magasin préféré nécessitent tous le consentement aux cookies et ne seront pas affichés si le consentement de l’utilisateur du site n’est pas obtenu.</span><span class="sxs-lookup"><span data-stu-id="dd676-110">For example, the checkout module, social share module, and preferred store feature all require cookie consent and will not be rendered if site user consent is not received.</span></span> 

<span data-ttu-id="dd676-111">Un module de consentement aux cookies peut être configuré sur le fragment d’en-tête d’une page afin qu’il puisse être appliqué lors du chargement de la page.</span><span class="sxs-lookup"><span data-stu-id="dd676-111">A cookie consent module can be configured on a page's header fragment so that it can be enforced when the page loads.</span></span> <span data-ttu-id="dd676-112">Le module de consentement aux cookies doit comporter un message clair informant l’utilisateur du site de l’utilisation des cookies sur le site et doit fournir un lien vers la page de protection des données personnelles du site.</span><span class="sxs-lookup"><span data-stu-id="dd676-112">The cookie consent module should have a clear message informing the site user about cookie usage on the site and should provide a link to the site's privacy page.</span></span>

<span data-ttu-id="dd676-113">L’illustration suivante met en évidence un exemple de message de consentement aux cookies avec un lien vers la page de politique de protection des données personnelles du site affiché sur l’en-tête d’une page de site.</span><span class="sxs-lookup"><span data-stu-id="dd676-113">The following illustration highlights an example of a cookie consent message with a link to the site's privacy policy page displayed on the header of a site page.</span></span>
<span data-ttu-id="dd676-114">![Exemple de module de consentement aux cookies](./media/ecommerce-cookieconsent.png)</span><span class="sxs-lookup"><span data-stu-id="dd676-114">![Example of a cookie consent module](./media/ecommerce-cookieconsent.png)</span></span>

## <a name="cookie-consent-module-properties"></a><span data-ttu-id="dd676-115">Propriétés du module de consentement aux cookies</span><span class="sxs-lookup"><span data-stu-id="dd676-115">Cookie consent module properties</span></span>

| <span data-ttu-id="dd676-116">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="dd676-116">Property name</span></span>             | <span data-ttu-id="dd676-117">Valeur</span><span class="sxs-lookup"><span data-stu-id="dd676-117">Value</span></span>                 | <span data-ttu-id="dd676-118">Description</span><span class="sxs-lookup"><span data-stu-id="dd676-118">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="dd676-119">Texte enrichi</span><span class="sxs-lookup"><span data-stu-id="dd676-119">Rich Text</span></span>                  | <span data-ttu-id="dd676-120">Texte enrichi</span><span class="sxs-lookup"><span data-stu-id="dd676-120">Rich Text</span></span> | <span data-ttu-id="dd676-121">Spécifie une notification de texte enrichi aux utilisateurs du site indiquant que le site utilise des cookies de navigateur et que les utilisateurs doivent accepter l’utilisation de cookies pour que le site soit pleinement fonctionnel.</span><span class="sxs-lookup"><span data-stu-id="dd676-121">Specifies a Rich Text notification to site users that the site uses browser cookies and that users should accept the use of cookies for the site to be fully functional.</span></span> |
| <span data-ttu-id="dd676-122">Liens</span><span class="sxs-lookup"><span data-stu-id="dd676-122">Links</span></span> | <span data-ttu-id="dd676-123">URL</span><span class="sxs-lookup"><span data-stu-id="dd676-123">URL</span></span> | <span data-ttu-id="dd676-124">Un ou plusieurs liens peuvent être ajoutés à la page de protection des données personnelles d’un site qui décrit les types de cookies suivis sur le site.</span><span class="sxs-lookup"><span data-stu-id="dd676-124">One or more links can be added to a site's privacy page that describes the types of cookies that are tracked on the site.</span></span> |

## <a name="add-a-cookie-consent-module-to-site-pages"></a><span data-ttu-id="dd676-125">Ajouter un module de consentement aux cookies aux pages du site</span><span class="sxs-lookup"><span data-stu-id="dd676-125">Add a cookie consent module to site pages</span></span>

<span data-ttu-id="dd676-126">Pour ajouter efficacement un module de consentement aux cookies à plusieurs pages du site, il peut être ajouté à un fragment d’en-tête de page partagé.</span><span class="sxs-lookup"><span data-stu-id="dd676-126">To efficiently add a cookie consent module to multiple site pages, it can be added to a shared page header fragment.</span></span> <span data-ttu-id="dd676-127">Une fois le fragment d’en-tête ajouté à toutes les pages du site, une notification de consentement aux cookies sera automatiquement affichée la première fois qu’un utilisateur du site accède à une page du site.</span><span class="sxs-lookup"><span data-stu-id="dd676-127">After the header fragment is added to all site pages, a cookie consent notification will automatically be rendered the first time a site user navigates to any site page.</span></span>

<span data-ttu-id="dd676-128">Pour plus d’informations sur les fragments d’en-tête et les modules, voir [Module En-tête](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="dd676-128">For more information about header fragments and modules, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dd676-129">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="dd676-129">Additional resources</span></span>

[<span data-ttu-id="dd676-130">Présentation de la bibliothèque de modules</span><span class="sxs-lookup"><span data-stu-id="dd676-130">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="dd676-131">Module En-tête</span><span class="sxs-lookup"><span data-stu-id="dd676-131">Header module</span></span>](author-header-module.md) 

[<span data-ttu-id="dd676-132">Conformité des cookies</span><span class="sxs-lookup"><span data-stu-id="dd676-132">Cookie compliance</span></span>](cookie-compliance.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]