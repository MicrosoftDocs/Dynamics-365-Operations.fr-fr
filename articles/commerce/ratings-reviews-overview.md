---
title: Vue d'ensemble des évaluations et avis
description: Cette rubrique couvre les classements et les évaluations dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
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
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 45a6710a10fe3d33457c1327c8fc339c9ad0082a
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698186"
---
# <a name="ratings-and-reviews-overview"></a><span data-ttu-id="538bb-103">Vue d'ensemble des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="538bb-103">Ratings and reviews overview</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="538bb-104">Cette rubrique couvre les classements et les évaluations dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="538bb-104">This topic covers ratings and reviews in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="538bb-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="538bb-105">Overview</span></span>

<span data-ttu-id="538bb-106">Les classements et les évaluations sont cruciaux pour les clients du commerce électronique qui souhaitent savoir comment d'autres clients perçoivent un produit.</span><span class="sxs-lookup"><span data-stu-id="538bb-106">Ratings and reviews are crucial for e-Commerce customers who want to know how other customers perceive a product.</span></span> <span data-ttu-id="538bb-107">Ils peuvent également aider les consommateurs à prendre des décisions d'achat.</span><span class="sxs-lookup"><span data-stu-id="538bb-107">They can also help consumers make purchase decisions.</span></span> <span data-ttu-id="538bb-108">Dans Dynamics 365 Commerce, la solution de classements et d'évaluations permet aux détaillants de capturer des évaluations et des classements du produit par les clients.</span><span class="sxs-lookup"><span data-stu-id="538bb-108">In Dynamics 365 Commerce, the ratings and reviews solution lets retailers capture product reviews and ratings from customers.</span></span> <span data-ttu-id="538bb-109">Les détaillants peuvent ensuite afficher des informations sur les classements et les évaluations moyens sur son site web de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="538bb-109">Retailers can then show average ratings and review information across their e-Commerce website.</span></span>

<span data-ttu-id="538bb-110">Les informations de classement moyen sont affichées dans le point de vente (PDV) et les canaux de centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="538bb-110">Average rating information is shown in point of sale (POS) and call center channels.</span></span> <span data-ttu-id="538bb-111">Par conséquent, les vendeurs peuvent les utiliser à prendre des décisions.</span><span class="sxs-lookup"><span data-stu-id="538bb-111">Therefore, sales associates can use it to help users make decisions.</span></span> <span data-ttu-id="538bb-112">Les classements et les évaluations peuvent également servir de mécanisme de rétroaction que les détaillants peuvent utiliser pour améliorer la qualité d'un produit et donc pour augmenter des ventes.</span><span class="sxs-lookup"><span data-stu-id="538bb-112">Ratings and reviews can also serve as a feedback mechanism that retailers can use to improve the quality of a product and therefore increase sales.</span></span>

<span data-ttu-id="538bb-113">La fonctionnalité de classements et d'évaluations dans Dynamics 365 Commerce est une solution omnicanale et est disponible en mode natif dans le cadre de la plateforme.</span><span class="sxs-lookup"><span data-stu-id="538bb-113">Ratings and reviews functionality in Dynamics 365 Commerce is an omnichannel solution and is natively available as part of the platform.</span></span> <span data-ttu-id="538bb-114">La solution de classements et d'évaluations s'appuie sur Microsoft Azure, qui fournit une évolutivité et une fiabilité élevées.</span><span class="sxs-lookup"><span data-stu-id="538bb-114">The ratings and reviews solution is built on top of Microsoft Azure, which provides high scalability and reliability.</span></span>

<span data-ttu-id="538bb-115">L'illustration ci-dessous indique comment la solution de classements et d'évaluations fonctionne dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="538bb-115">The following illustration shows how the ratings and reviews solution works in Dynamics 365 Commerce.</span></span>

![Classements et évaluations dans Dynamics 365 for Commerce](media/Dynamics-365-Commerce-Ratings-and-Reviews-Overview.jpg)

<span data-ttu-id="538bb-117">La solution de classements et d'évaluations dans Dynamics 365 Commerce utilise Azure Cognitive Services pour offrir la modération automatique des mots grossiers dans 40 langues.</span><span class="sxs-lookup"><span data-stu-id="538bb-117">The ratings and reviews solution in Dynamics 365 Commerce uses Azure Cognitive Services to offer automatic moderation of profane words in 40 languages.</span></span> <span data-ttu-id="538bb-118">Comme l'approbation humaine n'est pas nécessaire, les coûts de modération sont réduits.</span><span class="sxs-lookup"><span data-stu-id="538bb-118">Because human approval isn't required, moderation costs are reduced.</span></span> <span data-ttu-id="538bb-119">Le système propose également des outils de modérateur qui peuvent être utilisés pour répondre aux préoccupations de vos clients, aux commentaires, et aux demandes de retrait, et traiter les demandes de données des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="538bb-119">The system also offers moderator tools that can be used to respond to customer concerns, feedback, and take-down requests, and to address data requests from users.</span></span>

<span data-ttu-id="538bb-120">La solution de classements et d'évaluations révisions fournit des widgets qui affichent des synthèses de classement dans les listes de produits, dans les résultats de la recherche, sur la page de détails des produits, et à d'autres endroits.</span><span class="sxs-lookup"><span data-stu-id="538bb-120">The ratings and reviews solution provides widgets that show rating summaries in product lists, in search results, on product details page, and in other places.</span></span> <span data-ttu-id="538bb-121">Les widgets affichent des listes d'évaluation complètes et fournissent également des options de tri et de filtre.</span><span class="sxs-lookup"><span data-stu-id="538bb-121">The widgets show complete review lists, and they also provide sorting and filtering options.</span></span>

<span data-ttu-id="538bb-122">La solution de classement et d'évaluations fournit également un modèle de Business Intelligence (BI) qui comprend un ensemble de mesures pour fournir des analyses sur les classements et les évaluations.</span><span class="sxs-lookup"><span data-stu-id="538bb-122">The ratings and reviews solution also provides a business intelligence (BI) template that includes a set of metrics to provide insights into ratings and reviews.</span></span> <span data-ttu-id="538bb-123">Les données de classements et d'évaluations peuvent être exportés pour une analyse approfondie.</span><span class="sxs-lookup"><span data-stu-id="538bb-123">Ratings and reviews data can be exported for further analysis.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="538bb-124">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="538bb-124">Additional resources</span></span>

[<span data-ttu-id="538bb-125">Choix d'utilisation des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="538bb-125">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="538bb-126">Gestion des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="538bb-126">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="538bb-127">Configuration des évaluations et avis</span><span class="sxs-lookup"><span data-stu-id="538bb-127">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="538bb-128">Synchronisation des évaluations de produit dans Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="538bb-128">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
