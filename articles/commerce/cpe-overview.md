---
title: Vue d'ensemble de l'environnement d'aperçu dans Dynamics 365 Commerce
description: Cette rubrique fournit une vue d'ensemble de l'environnement d'aperçu Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-chgri
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1ff96aeb5963df9ddee56783a089dad129bbb71c
ms.sourcegitcommit: 4ed1d8ad8a0206a4172dbb41cc43f7d95073059c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024681"
---
# <a name="dynamics-365-commerce-preview-environment-overview"></a><span data-ttu-id="995e2-103">Vue d'ensemble de l'environnement d'aperçu dans Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="995e2-103">Dynamics 365 Commerce preview environment overview</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="995e2-104">Cette rubrique fournit une vue d'ensemble de l'environnement d'aperçu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="995e2-104">This topic gives an overview of the Microsoft Dynamics 365 Commerce preview environment.</span></span>

## <a name="overview"></a><span data-ttu-id="995e2-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="995e2-105">Overview</span></span>

<span data-ttu-id="995e2-106">L'environnement de prévisualisation Commerce est un environnement de prévisualisation de bout en bout facultatif de Dynamics 365 Commerce qui permet aux clients potentiels d'essayer le produit Commerce avant sa sortie générale.</span><span class="sxs-lookup"><span data-stu-id="995e2-106">The Commerce preview environment is an optional end-to-end preview environment of Dynamics 365 Commerce that lets potential customers try out the Commerce product before its general release to the public.</span></span>

<span data-ttu-id="995e2-107">Mis à part quelques limitations mineures qui n'affectent pas les fonctionnalités, l'environnement de prévisualisation Commerce fournit l'expérience Commerce complète et peut être utilisé par les clients et les partenaires de mise en œuvre pour évaluer le produit, fournir des commentaires et effectuer une analyse d'ajustement/des écarts.</span><span class="sxs-lookup"><span data-stu-id="995e2-107">Aside from some minor limitations that don't affect features or functionality, the Commerce preview environment provides the complete Commerce experience, and can be used by customers and implementation partners to evaluate the product, provide feedback, and do fit/gap analysis.</span></span>

## <a name="limitations-of-the-commerce-preview-environment"></a><span data-ttu-id="995e2-108">Limitations de l'environnement d'aperçu de Commerce</span><span class="sxs-lookup"><span data-stu-id="995e2-108">Limitations of the Commerce preview environment</span></span>

<span data-ttu-id="995e2-109">Bien que l'environnement d'aperçu de Commerce fournisse l'ensemble complet des fonctionnalités de Commerce, il existe quelques limitations mineures :</span><span class="sxs-lookup"><span data-stu-id="995e2-109">Although the Commerce preview environment provides the full set of Commerce features and functionality, there are some minor limitations:</span></span>

- <span data-ttu-id="995e2-110">Bien que l'environnement de prévisualisation Commerce lui-même n'ait aucune limitation géographique, des composants de l'environnement, tels que Retail Cloud Scale Unit (RCSU) et les applications de commerce électronique, ne peuvent être fournies qu'aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="995e2-110">Although the Commerce preview environment itself has no geographical limitations, components of the environment, such as the Retail Cloud Scale Unit (RCSU) and e-Commerce applications, can be provisioned only in the United States.</span></span>
- <span data-ttu-id="995e2-111">L'utilisation de l'environnement de prévisualisation Commerce est limitée à 30 jours à compter de la date de mise en service du commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="995e2-111">Use of the Commerce preview environment is limited to 30 days from the date when e-Commerce is provisioned.</span></span>
- <span data-ttu-id="995e2-112">L'environnement de prévisualisation Commerce ne peut être déployé et initialisé avec succès que dans un environnement qui utilise la topologie de démonstration, où tous les composants d'un environnement sont déployés sur une seule machine virtuelle.</span><span class="sxs-lookup"><span data-stu-id="995e2-112">The Commerce preview environment can be successfully deployed and initialized only in an environment that uses the demo topology, where all components of an environment are deployed in a single virtual machine (VM).</span></span> <span data-ttu-id="995e2-113">La principale limitation de cette topologie de machine virtuelle OneBox est le nombre d'utilisateurs simultanés que l'environnement d'aperçu peut prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="995e2-113">The main limitation of this OneBox VM topology is the number of concurrent users that the preview environment can support.</span></span>
- <span data-ttu-id="995e2-114">L'environnement de prévisualisation Commerce ne peut être évalué que jusqu'à la disponibilité générale (DG) du produit Commerce.</span><span class="sxs-lookup"><span data-stu-id="995e2-114">The Commerce preview environment can be evaluated only until the general availability (GA) of the Commerce product.</span></span> <span data-ttu-id="995e2-115">De nouveaux environnements de démonstration seront disponibles après la DG.</span><span class="sxs-lookup"><span data-stu-id="995e2-115">New demo environments will be available after GA.</span></span>

## <a name="get-started"></a><span data-ttu-id="995e2-116">Mise en route</span><span class="sxs-lookup"><span data-stu-id="995e2-116">Get started</span></span>

<span data-ttu-id="995e2-117">Pour mettre en service l'environnement d'aperçu Commerce, voir [Mise en service d'un environnement d'aperçu Commerce](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="995e2-117">To provision the Commerce preview environment, see [Provision a Commerce preview environment](provisioning-guide.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="995e2-118">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="995e2-118">Additional resources</span></span>

[<span data-ttu-id="995e2-119">Mettre en service un environnement d'aperçu dans Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="995e2-119">Provision a Dynamics 365 Commerce preview environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="995e2-120">Configurer un environnement d'aperçu dans Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="995e2-120">Configure a Dynamics 365 Commerce preview environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="995e2-121">Configurer les fonctionnalités facultatives pour un environnement d'aperçu dans Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="995e2-121">Configure optional features for a Dynamics 365 Commerce preview environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="995e2-122">FAQ sur l'environnement d'aperçu dans Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="995e2-122">Dynamics 365 Commerce preview environment FAQ</span></span>](cpe-faq.md)
