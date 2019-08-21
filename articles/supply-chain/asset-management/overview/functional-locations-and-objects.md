---
title: Actifs et postes techniques
description: Cette rubrique décrit les postes techniques et les actifs dans Gestion des actifs. Gestion des actifs est un module avancé de gestion des actifs et des tâches de maintenance dans Microsoft Dynamics 365 for Finance and Operations.
author: josaw1
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 351e27dfbbd5227a9642f14a48afe194c447a0f3
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783278"
---
# <a name="functional-locations-and-assets"></a><span data-ttu-id="f61f8-104">Actifs et postes techniques</span><span class="sxs-lookup"><span data-stu-id="f61f8-104">Functional locations and assets</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="f61f8-105">Cette rubrique décrit les postes techniques et les actifs dans Gestion des actifs.</span><span class="sxs-lookup"><span data-stu-id="f61f8-105">This topic describes functional locations and assets in Asset Management.</span></span> <span data-ttu-id="f61f8-106">Gestion des actifs est un module avancé de gestion des actifs et des tâches de maintenance dans Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f61f8-106">Asset Management is an advanced module for managing assets and maintenance jobs in Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="overview"></a><span data-ttu-id="f61f8-107">Présentation</span><span class="sxs-lookup"><span data-stu-id="f61f8-107">Overview</span></span>

<span data-ttu-id="f61f8-108">Gestion des actifs est intégré de façon transparente à plusieurs modules de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f61f8-108">Asset Management is integrated seamlessly with several modules in Finance and Operations.</span></span> <span data-ttu-id="f61f8-109">L'illustration suivante présente les interfaces avec d'autres modules.</span><span class="sxs-lookup"><span data-stu-id="f61f8-109">The following illustration shows the interfaces with other modules.</span></span>

![Figure 1](media/01-overview-image.png)

<span data-ttu-id="f61f8-111">Gestion des actifs vous permet de gérer et d'exécuter plus efficacement toutes les tâches relatives à la gestion et à la maintenance de nombreux types d'équipements de votre société.</span><span class="sxs-lookup"><span data-stu-id="f61f8-111">Asset Management lets you efficiently manage and perform all tasks that are related to managing and servicing many types of equipment in your company.</span></span> <span data-ttu-id="f61f8-112">Cet équipement inclut les machines, l'équipement de production et les véhicules.</span><span class="sxs-lookup"><span data-stu-id="f61f8-112">This equipment includes machines, production equipment, and vehicles.</span></span> <span data-ttu-id="f61f8-113">Gestion des actifs prend également en charge les solutions de nombreux secteurs.</span><span class="sxs-lookup"><span data-stu-id="f61f8-113">Asset Management also supports solutions across numerous industries.</span></span>

<span data-ttu-id="f61f8-114">L'illustration suivante présente une vue d'ensemble de la fonctionnalité principale couverte par Gestion des actifs.</span><span class="sxs-lookup"><span data-stu-id="f61f8-114">The following illustration shows an overview of the main functionality that is covered by Asset Management.</span></span>

![Figure 2](media/02-overview-image.png)

## <a name="functional-locations-and-assets"></a><span data-ttu-id="f61f8-116">Actifs et postes techniques</span><span class="sxs-lookup"><span data-stu-id="f61f8-116">Functional locations and assets</span></span>

<span data-ttu-id="f61f8-117">Les postes techniques permettent de gérer des actifs à des postes.</span><span class="sxs-lookup"><span data-stu-id="f61f8-117">Functional locations are used to manage assets on locations.</span></span> <span data-ttu-id="f61f8-118">Cette gestion inclut le suivi des coûts d'actif à des postes techniques.</span><span class="sxs-lookup"><span data-stu-id="f61f8-118">This management includes tracking of asset costs on functional locations.</span></span> <span data-ttu-id="f61f8-119">Les postes techniques sont structurés hiérarchiquement, et les postes peuvent avoir des sous-postes.</span><span class="sxs-lookup"><span data-stu-id="f61f8-119">Functional locations are structured hierarchically, and locations can have sub-locations.</span></span> <span data-ttu-id="f61f8-120">La structure des postes techniques est statique.</span><span class="sxs-lookup"><span data-stu-id="f61f8-120">The structure of functional locations is static.</span></span> <span data-ttu-id="f61f8-121">Autrement dit, les postes ne peuvent pas changer d'emplacement.</span><span class="sxs-lookup"><span data-stu-id="f61f8-121">In other words, locations can't change place.</span></span> <span data-ttu-id="f61f8-122">Les actifs peuvent être installés à des postes techniques et, au besoin, être installés à d'autres postes techniques ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="f61f8-122">Assets can be installed on functional locations and, as required, can be installed on other functional locations later.</span></span>

<span data-ttu-id="f61f8-123">Les coûts d'actifs suivent toujours le poste de l'actif.</span><span class="sxs-lookup"><span data-stu-id="f61f8-123">Asset costs always follow the location of the asset.</span></span> <span data-ttu-id="f61f8-124">En d'autres termes, si vous installez un actif à un nouveau poste technique, l'actif utilise automatiquement les dimensions financières associées au nouveau poste technique.</span><span class="sxs-lookup"><span data-stu-id="f61f8-124">In other words, if you install an asset on a new functional location, the asset automatically uses the financial dimensions that are related to the new functional location.</span></span> <span data-ttu-id="f61f8-125">Par conséquent, les coûts d'actif sont toujours liés au poste technique sur lequel l'actif est actuellement installé.</span><span class="sxs-lookup"><span data-stu-id="f61f8-125">Therefore, asset costs are always related to the functional location that the asset is  currently installed on.</span></span> <span data-ttu-id="f61f8-126">Ce traitement automatique des dimensions financières garantit le suivi complet des coûts lorsque votre société fait le projet de contrôler et de générer des états sur les postes techniques.</span><span class="sxs-lookup"><span data-stu-id="f61f8-126">This automatic handling of financial dimensions helps guarantee complete tracking of costs when your company does project controlling and reporting on functional locations.</span></span>

<span data-ttu-id="f61f8-127">La façon dont vous établissez votre hiérarchie des postes techniques dépend des exigences de votre société pour la maintenance de l'équipement interne ou l'entretien de l'équipement du client.</span><span class="sxs-lookup"><span data-stu-id="f61f8-127">The way that you build your hierarchy of functional locations depends on your company's requirements for maintaining internal equipment or servicing customer equipment.</span></span> <span data-ttu-id="f61f8-128">La figure suivante présente un exemple des postes techniques basés sur des emplacements géographiques.</span><span class="sxs-lookup"><span data-stu-id="f61f8-128">The following figure shows an example of functional locations that are based on geographical locations.</span></span>

![Figure 3](media/03-overview-image.png)

<span data-ttu-id="f61f8-130">La figure suivante présente un exemple des postes techniques basés sur les clients.</span><span class="sxs-lookup"><span data-stu-id="f61f8-130">The following figure shows an example of functional locations that are based on customers.</span></span>

![Figure 4](media/04-overview-image.png)
