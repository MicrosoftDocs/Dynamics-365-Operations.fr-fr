---
title: Vue d'ensemble d'un environnement d'évaluation Dynamics 365 Commerce
description: Cette rubrique fournit une vue d'ensemble de l'environnement d'évaluation Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 07/16/2020
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
ms.openlocfilehash: 25c0574e8d4502bcb846fba0ddf913d81eded87b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412162"
---
# <a name="dynamics-365-commerce-evaluation-environment-overview"></a><span data-ttu-id="3d0fd-103">Vue d'ensemble d'un environnement d'évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="3d0fd-103">Dynamics 365 Commerce evaluation environment overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3d0fd-104">Cette rubrique fournit une vue d'ensemble de l'environnement d'évaluation Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3d0fd-104">This topic gives an overview of the Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

> [!NOTE]
> <span data-ttu-id="3d0fd-105">Les environnements d'évaluation de Commerce ne sont pas en disponibilité générale et sont accordés aux partenaires et aux clients sur demande.</span><span class="sxs-lookup"><span data-stu-id="3d0fd-105">Commerce evaluation environments aren't generally available, and are granted to partners and customers on a per-request basis.</span></span> <span data-ttu-id="3d0fd-106">Pour plus d'informations, contactez votre partenaire Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d0fd-106">For more information, reach out to your Microsoft partner contact.</span></span>

## <a name="overview"></a><span data-ttu-id="3d0fd-107">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="3d0fd-107">Overview</span></span>

<span data-ttu-id="3d0fd-108">L'environnement d'évaluation de Commerce est un environnement facultatif de bout en bout de Dynamics 365 Commerce qui permet aux partenaires et aux clients potentiels d'essayer le produit Commerce.</span><span class="sxs-lookup"><span data-stu-id="3d0fd-108">The Commerce evaluation environment is an optional end-to-end environment of Dynamics 365 Commerce that lets partners and potential customers try out the Commerce product.</span></span>

<span data-ttu-id="3d0fd-109">Les environnements d'évaluation sont partiellement préconfigurés pour réduire les étapes post-mise en service requises.</span><span class="sxs-lookup"><span data-stu-id="3d0fd-109">Evaluation environments are partially preconfigured to reduce the required post-provisioning steps.</span></span>

<span data-ttu-id="3d0fd-110">Mis à part quelques limitations mineures qui n'affectent pas les fonctionnalités, l'environnement d'évaluation Commerce fournit l'expérience Commerce complète et peut être utilisé par les clients et les partenaires de mise en œuvre pour évaluer le produit, fournir des commentaires et effectuer une analyse d'ajustement/des écarts.</span><span class="sxs-lookup"><span data-stu-id="3d0fd-110">Aside from some minor limitations that don't affect features or functionality, the Commerce evaluation environment provides the complete Commerce experience, and can be used by customers and implementation partners to evaluate the product, provide feedback, and do fit/gap analysis.</span></span>

## <a name="limitations-of-the-commerce-evaluation-environment"></a><span data-ttu-id="3d0fd-111">Limitations de l'environnement d'évaluation de Commerce</span><span class="sxs-lookup"><span data-stu-id="3d0fd-111">Limitations of the Commerce evaluation environment</span></span>

<span data-ttu-id="3d0fd-112">Bien que l'environnement d'évaluation de Commerce fournisse l'ensemble complet des fonctionnalités de Commerce, il existe quelques limitations mineures :</span><span class="sxs-lookup"><span data-stu-id="3d0fd-112">Although the Commerce evaluation environment provides the full set of Commerce features and functionality, there are some minor limitations:</span></span>

- <span data-ttu-id="3d0fd-113">Bien que l'environnement d'évaluation Commerce lui-même n'ait aucune limitation géographique, des composants de l'environnement, tels que Retail Cloud Scale Unit (RCSU) et les applications de commerce électronique, ne peuvent être fournies qu'aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="3d0fd-113">Although the Commerce evaluation environment itself has no geographical limitations, components of the environment, such as the Retail Cloud Scale Unit (RCSU) and e-Commerce applications, should be provisioned only in the United States.</span></span>
- <span data-ttu-id="3d0fd-114">L'utilisation de l'environnement d'évaluation Commerce est limitée à 30 jours à compter de la date de mise en service du commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="3d0fd-114">Use of the Commerce evaluation environment is limited to 30 days from the date when e-Commerce is provisioned.</span></span>
- <span data-ttu-id="3d0fd-115">L'environnement d'évaluation de Commerce ne peut être déployé et initialisé avec succès que dans un environnement qui utilise la topologie de démonstration, où tous les composants d'un environnement sont déployés sur une seule machine virtuelle hébergée dans le cloud.</span><span class="sxs-lookup"><span data-stu-id="3d0fd-115">The Commerce evaluation environment can be successfully deployed and initialized only in an environment that uses the demo topology, where all components of an environment are deployed on a single cloud-hosted virtual machine (VM).</span></span> <span data-ttu-id="3d0fd-116">La principale limitation de cette topologie est le nombre d'utilisateurs simultanés que l'environnement d'évaluation peut prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="3d0fd-116">The main limitation of this topology is the number of concurrent users that the environment can support.</span></span>

## <a name="get-started"></a><span data-ttu-id="3d0fd-117">Prise en main</span><span class="sxs-lookup"><span data-stu-id="3d0fd-117">Get started</span></span>

<span data-ttu-id="3d0fd-118">Pour mettre en service l'environnement d'évaluation de Commerce, voir [Mise en service d'un environnement d'évaluation de Commerce](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="3d0fd-118">To provision the Commerce evaluation environment, see [Provision a Commerce evaluation environment](provisioning-guide.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3d0fd-119">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="3d0fd-119">Additional resources</span></span>

[<span data-ttu-id="3d0fd-120">Mettre en service un environnement d'évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="3d0fd-120">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="3d0fd-121">Configurer un environnement d'évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="3d0fd-121">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="3d0fd-122">Configurer le BOPIS dans un environnement d'évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="3d0fd-122">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="3d0fd-123">Configurer des fonctionnalités facultatives pour un environnement d'évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="3d0fd-123">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="3d0fd-124">FAQ des environnements d'évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="3d0fd-124">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)
