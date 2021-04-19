---
title: Actifs et postes techniques
description: Cette rubrique décrit les postes techniques et les actifs dans Gestion des actifs. Gestion des actifs est un module avancé de gestion des actifs et des tâches de maintenance dans Dynamics 365 Supply Chain Management.
author: johanhoffmann
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1e626daa89eecf838d7cda0663d00c1c2dbecb76
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816747"
---
# <a name="functional-locations-and-assets"></a><span data-ttu-id="28d8b-104">Actifs et postes techniques</span><span class="sxs-lookup"><span data-stu-id="28d8b-104">Functional locations and assets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="28d8b-105">Cette rubrique décrit les postes techniques et les actifs dans Gestion des actifs.</span><span class="sxs-lookup"><span data-stu-id="28d8b-105">This topic describes functional locations and assets in Asset Management.</span></span> <span data-ttu-id="28d8b-106">Gestion des actifs est un module avancé de gestion des actifs et des tâches de maintenance dans Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="28d8b-106">Asset Management is an advanced module for managing assets and maintenance jobs in Dynamics 365 Supply Chain Management.</span></span>

## <a name="overview"></a><span data-ttu-id="28d8b-107">Présentation</span><span class="sxs-lookup"><span data-stu-id="28d8b-107">Overview</span></span>

<span data-ttu-id="28d8b-108">Gestion des actifs est intégré de façon transparente à plusieurs modules avec d’autres applications Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="28d8b-108">Asset Management is integrated seamlessly with several modules with other Finance and Operations apps.</span></span> <span data-ttu-id="28d8b-109">L’illustration suivante présente les interfaces avec d’autres modules.</span><span class="sxs-lookup"><span data-stu-id="28d8b-109">The following illustration shows the interfaces with other modules.</span></span>

![Diagramme affichant comment le module Gestion d’actifs se connecte par interface aux autres modules](media/01-overview-image.png)

<span data-ttu-id="28d8b-111">Gestion des actifs vous permet de gérer et d’exécuter plus efficacement toutes les tâches relatives à la gestion et à la maintenance de nombreux types d’équipements de votre société.</span><span class="sxs-lookup"><span data-stu-id="28d8b-111">Asset Management lets you efficiently manage and perform all tasks that are related to managing and servicing many types of equipment in your company.</span></span> <span data-ttu-id="28d8b-112">Cet équipement inclut les machines, l’équipement de production et les véhicules.</span><span class="sxs-lookup"><span data-stu-id="28d8b-112">This equipment includes machines, production equipment, and vehicles.</span></span> <span data-ttu-id="28d8b-113">Gestion des actifs prend également en charge les solutions de nombreux secteurs.</span><span class="sxs-lookup"><span data-stu-id="28d8b-113">Asset Management also supports solutions across numerous industries.</span></span>

<span data-ttu-id="28d8b-114">L’illustration suivante présente une vue d’ensemble de la fonctionnalité principale couverte par Gestion des actifs.</span><span class="sxs-lookup"><span data-stu-id="28d8b-114">The following illustration shows an overview of the main functionality that is covered by Asset Management.</span></span>

![Diagramme affichant la fonctionnalité principale du module Gestion des actifs](media/02-overview-image.png)

## <a name="functional-locations-and-assets"></a><span data-ttu-id="28d8b-116">Actifs et emplacements fonctionnels</span><span class="sxs-lookup"><span data-stu-id="28d8b-116">Functional locations and assets</span></span>

<span data-ttu-id="28d8b-117">Les postes techniques permettent de gérer des actifs à des postes.</span><span class="sxs-lookup"><span data-stu-id="28d8b-117">Functional locations are used to manage assets on locations.</span></span> <span data-ttu-id="28d8b-118">Cette gestion inclut le suivi des coûts d’actif à des postes techniques.</span><span class="sxs-lookup"><span data-stu-id="28d8b-118">This management includes tracking of asset costs on functional locations.</span></span> <span data-ttu-id="28d8b-119">Les postes techniques sont structurés hiérarchiquement, et les postes peuvent avoir des sous-postes.</span><span class="sxs-lookup"><span data-stu-id="28d8b-119">Functional locations are structured hierarchically, and locations can have sub-locations.</span></span> <span data-ttu-id="28d8b-120">La structure des postes techniques est statique.</span><span class="sxs-lookup"><span data-stu-id="28d8b-120">The structure of functional locations is static.</span></span> <span data-ttu-id="28d8b-121">Autrement dit, les postes ne peuvent pas changer d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="28d8b-121">In other words, locations can't change place.</span></span> <span data-ttu-id="28d8b-122">Les actifs peuvent être installés à des postes techniques et, au besoin, être installés à d’autres postes techniques ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="28d8b-122">Assets can be installed on functional locations and, as required, can be installed on other functional locations later.</span></span>

<span data-ttu-id="28d8b-123">Les coûts d’actifs suivent toujours le poste de l’actif.</span><span class="sxs-lookup"><span data-stu-id="28d8b-123">Asset costs always follow the location of the asset.</span></span> <span data-ttu-id="28d8b-124">En d’autres termes, si vous installez un actif à un nouveau poste technique, l’actif utilise automatiquement les dimensions financières associées au nouveau poste technique.</span><span class="sxs-lookup"><span data-stu-id="28d8b-124">In other words, if you install an asset on a new functional location, the asset automatically uses the financial dimensions that are related to the new functional location.</span></span> <span data-ttu-id="28d8b-125">Par conséquent, les coûts d’actif sont toujours liés au poste technique sur lequel l’actif est actuellement installé.</span><span class="sxs-lookup"><span data-stu-id="28d8b-125">Therefore, asset costs are always related to the functional location that the asset is  currently installed on.</span></span> <span data-ttu-id="28d8b-126">Ce traitement automatique des dimensions financières garantit le suivi complet des coûts lorsque votre société fait le projet de contrôler et de générer des états sur les postes techniques.</span><span class="sxs-lookup"><span data-stu-id="28d8b-126">This automatic handling of financial dimensions helps guarantee complete tracking of costs when your company does project controlling and reporting on functional locations.</span></span>

<span data-ttu-id="28d8b-127">La façon dont vous établissez votre hiérarchie des postes techniques dépend des exigences de votre société pour la maintenance de l’équipement interne ou l’entretien de l’équipement du client.</span><span class="sxs-lookup"><span data-stu-id="28d8b-127">The way that you build your hierarchy of functional locations depends on your company's requirements for maintaining internal equipment or servicing customer equipment.</span></span> <span data-ttu-id="28d8b-128">La figure suivante présente un exemple des postes techniques basés sur des emplacements géographiques.</span><span class="sxs-lookup"><span data-stu-id="28d8b-128">The following figure shows an example of functional locations that are based on geographical locations.</span></span>

![Diagramme affichant des postes techniques basés sur des emplacements géographiques](media/03-overview-image.png)

<span data-ttu-id="28d8b-130">La figure suivante présente un exemple des postes techniques basés sur les clients.</span><span class="sxs-lookup"><span data-stu-id="28d8b-130">The following figure shows an example of functional locations that are based on customers.</span></span>

![Diagramme affichant des postes techniques basés sur des clients](media/04-overview-image.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]