---
title: Vue d’ensemble du cycle de vie de l’ordre de fabrication
description: Lors de la création d’un ordre de fabrication, une demande de lancement de fabrication d’un article est effectuée. L’ordre de fabrication contient des informations sur l’article à fabriquer, la quantité à fabriquer, ainsi que la date de fin de fabrication prévue. Il inclut également des informations sur les matières à consommer et quel processus suivre pour produire l’article.
author: johanhoffmann
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTable, ProdTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19741
ms.assetid: bbb6e69d-479c-45fc-a0a8-66da5df16c7f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: df773cf13b8ccd9ee4f861955b1a4321af38a150
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811796"
---
# <a name="production-order-lifecycle-overview"></a><span data-ttu-id="5ef9b-105">Vue d’ensemble du cycle de vie de l’ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="5ef9b-105">Production order lifecycle overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5ef9b-106">Lors de la création d’un ordre de fabrication, une demande de lancement de fabrication d’un article est effectuée.</span><span class="sxs-lookup"><span data-stu-id="5ef9b-106">When a production order is created, a request is initiated to start producing an item.</span></span> <span data-ttu-id="5ef9b-107">L’ordre de fabrication contient des informations sur l’article à fabriquer, la quantité à fabriquer, ainsi que la date de fin de fabrication prévue.</span><span class="sxs-lookup"><span data-stu-id="5ef9b-107">The production order contains information about what will be produced, the quantity to produce, and the planned finish date.</span></span> <span data-ttu-id="5ef9b-108">Il inclut également des informations sur les matières à consommer et quel processus suivre pour produire l’article.</span><span class="sxs-lookup"><span data-stu-id="5ef9b-108">It also contains information about which materials to consume and which process to follow to produce the item.</span></span>

<span data-ttu-id="5ef9b-109">Un ordre de fabrication traverse les stades du cycle de vie de la production.</span><span class="sxs-lookup"><span data-stu-id="5ef9b-109">A production order passes through stages of the production life cycle.</span></span> <span data-ttu-id="5ef9b-110">Lorsqu’un ordre est créé, le statut **Créé** lui est affecté.</span><span class="sxs-lookup"><span data-stu-id="5ef9b-110">When an order is created, it is assigned the status **Created**.</span></span> <span data-ttu-id="5ef9b-111">Lorsqu’un ordre est terminé, le statut **Terminé** lui est affecté.</span><span class="sxs-lookup"><span data-stu-id="5ef9b-111">When an order is finished, it is assigned the status **Ended**.</span></span> <span data-ttu-id="5ef9b-112">Le paramétrage de chaque stade permet à un utilisateur de configurer chaque étape.</span><span class="sxs-lookup"><span data-stu-id="5ef9b-112">A parameter setting in each stage allows a user to configure each step.</span></span> <span data-ttu-id="5ef9b-113">Ce paramétrage peut être paramétré pour un seul utilisateur ou pour tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="5ef9b-113">The setting can be set up for a single user or for all users.</span></span>

<span data-ttu-id="5ef9b-114">Les nomenclatures de production et la gamme de production sont les entités principales de l’ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="5ef9b-114">The production bill of material and the production route are the main entities of the production order.</span></span> <span data-ttu-id="5ef9b-115">Elles sont copiées dans l’ordre de fabrication selon l’article sélectionné et la quantité qui vont être produits.</span><span class="sxs-lookup"><span data-stu-id="5ef9b-115">They are copied to the production order based on the selected item and quantity that are going to be produced.</span></span> <span data-ttu-id="5ef9b-116">La nomenclature de production et la gamme peuvent être modifiées avant le début de l’ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="5ef9b-116">Before the production order is started, the production bill of material and route can be edited.</span></span>

<span data-ttu-id="5ef9b-117">Un ordre de fabrication peut être créé dans les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="5ef9b-117">A production order can be created in the following scenarios:</span></span>

-   <span data-ttu-id="5ef9b-118">Créé par l’exécution de planification principale selon les besoins en matériel.</span><span class="sxs-lookup"><span data-stu-id="5ef9b-118">Created by master planning execution based on material demand.</span></span>
-   <span data-ttu-id="5ef9b-119">Créé directement à partir d’une ligne de commande client ou lorsqu’un ordre de fabrication de niveau supérieur est créé et estimé (approvisionnement invariable).</span><span class="sxs-lookup"><span data-stu-id="5ef9b-119">Created directly from a sales order line or when a higher-level production order is created and estimated (pegged supply).</span></span>
-   <span data-ttu-id="5ef9b-120">Créé manuellement.</span><span class="sxs-lookup"><span data-stu-id="5ef9b-120">Created manually.</span></span>






[!INCLUDE[footer-include](../../includes/footer-banner.md)]