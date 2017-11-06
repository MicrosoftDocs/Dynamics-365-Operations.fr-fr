---
title: "Réserver le même lot pour une commande client"
description: "Cet article explique comment paramétrer un produit pour autoriser la réservation du stock par rapport à un lot de stock unique."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, EcoResStorageDimensionGroup, EcoResTrackingDimensionGroup, InventBatch, InventModelGroup, PdsAskSameLotForm, PdsCustSellableDays
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 28911
ms.assetid: 5823d75e-f839-46dd-beb3-e09b79fc8aa4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: aef3a52f4cb2d5af47a8c25a67e6c2076fa1ff03
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="reserve-the-same-batch-for-a-sales-order"></a><span data-ttu-id="de853-103">Réserver le même lot pour une commande client</span><span class="sxs-lookup"><span data-stu-id="de853-103">Reserve the same batch for a sales order</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="de853-104">Cet article explique comment paramétrer un produit pour autoriser la réservation du stock par rapport à un lot de stock unique.</span><span class="sxs-lookup"><span data-stu-id="de853-104">This article explains how to set up a product to allow reservation of inventory against a single batch of inventory.</span></span>

<span data-ttu-id="de853-105">Une réservation de lots identiques vous permet de réserver du stock pour une ligne de commande client par rapport à un lot de stock unique.</span><span class="sxs-lookup"><span data-stu-id="de853-105">Same batch reservation lets you reserve inventory for a sales order line against a single batch of inventory.</span></span> <span data-ttu-id="de853-106">Par exemple, un client qui commande du papier peint peut demander que toute la commande soit honorée à partir du même lot pour éviter les éventuelles différences entre les rouleaux de papier peint.</span><span class="sxs-lookup"><span data-stu-id="de853-106">For example, a customer who orders wallpaper can request that the whole order be filled from the same batch or lot, to avoid inconsistencies among the rolls.</span></span> <span data-ttu-id="de853-107">Pour paramétrer un produit de manière à utiliser la réservation de lots identiques, les paramètres suivants doivent être activés dans les Groupes de modèles d'article, Groupe de dimension de suivi et Groupe de dimension de stockage que vous affectez au produit.</span><span class="sxs-lookup"><span data-stu-id="de853-107">To set up a product to use same batch reservation, the following settings must be active in the item model group, tracking dimension group, and storage dimension group that you assign to the product:</span></span>

-   <span data-ttu-id="de853-108">**Groupes de modèles d'article** – Pour le groupe de modèles d'article, les champs **Même sélection de lot** et **Consolider le besoin** doivent être sélectionnés dans le groupe de champs **Réservation** pour les stratégies de stock.</span><span class="sxs-lookup"><span data-stu-id="de853-108">**Item model groups** – The item model group must have the **Same batch selection** and **Consolidate requirement** fields selected in the **Reservation** field group for inventory policies.</span></span>
-   <span data-ttu-id="de853-109">**Groupes de dimension de suivi** – Pour le groupe de dimension de suivi, le champ **Plan de couverture par dimension** doit être sélectionné pour le numéro du lot.</span><span class="sxs-lookup"><span data-stu-id="de853-109">**Tracking dimensions groups** – The tracking dimension group must have the **Coverage plan by dimension** field selected for the batch number.</span></span>
-   <span data-ttu-id="de853-110">**Groupe de dimension de stockage** – Pour le groupe de dimension de stockage, le champ **Plan de couverture par dimension** doit être sélectionné pour le **Site** et l'**Entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="de853-110">**Storage dimensions groups** – The storage dimension group must have the **Coverage plan by dimension** field selected for **Site** and **Warehouse**.</span></span>

<span data-ttu-id="de853-111">Lorsque vous réservez du stock pour un produit sur une ligne de commande client paramétrée pour la sélection du même lot, Microsoft Dynamics 365 for Finance and Operations tente de réserver la quantité commandée à partir d'un seul lot de stock.</span><span class="sxs-lookup"><span data-stu-id="de853-111">When you reserve inventory for a product on a sales order line that is set up for same batch selection, Microsoft Dynamics 365 for Finance and Operations tries to reserve the ordered quantity from a single inventory batch.</span></span> <span data-ttu-id="de853-112">Il prend également en considération toute demande d'attribut de lot spécifique.</span><span class="sxs-lookup"><span data-stu-id="de853-112">Any specific batch attribute requirements are also considered.</span></span> <span data-ttu-id="de853-113">Si la quantité ne peut pas être remplie à partir d'un seul lot, la page **Conflit de réservation du même lot** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="de853-113">If the quantity can't be filled from a single batch, the **Same batch reservation conflict** page appears.</span></span> <span data-ttu-id="de853-114">Cette page décrit les problèmes et également les actions que vous pouvez entreprendre pour poursuivre la réservation.</span><span class="sxs-lookup"><span data-stu-id="de853-114">This page describes the issues and also the actions that you can take to continue with the reservation.</span></span> <span data-ttu-id="de853-115">Les conditions suivantes peuvent empêcher le lot d'être réservé :</span><span class="sxs-lookup"><span data-stu-id="de853-115">The following conditions might prevent the batch from being reserved:</span></span>

-   <span data-ttu-id="de853-116">Pour le code disposition de lot, **Bloquer la réservation** pour les ventes est marqué comme **Bloqué**.</span><span class="sxs-lookup"><span data-stu-id="de853-116">The batch disposition code has **Block reservation** for sales flagged as **Blocked**.</span></span>
-   <span data-ttu-id="de853-117">Le lot a expiré, d'après la date d'expiration et des jours de vente applicables au client.</span><span class="sxs-lookup"><span data-stu-id="de853-117">The batch has expired, based on the expiration date and any applicable customer sellable days.</span></span> <span data-ttu-id="de853-118">L'article peut toujours être pris en compte pour la réservation si le Groupe de modèles d'article pour l'article est contrôlé par la date FEFO (première date d'expiration, premier sorti) et si la DLUO est sélectionnée dans les critères de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="de853-118">The item can still be considered for reservation if the item model group for the item is First Expiry First Out (FEFO) date–controlled, and if the best-before date is selected as the pick criterion.</span></span>
-   <span data-ttu-id="de853-119">Le lot a une durée de conservation en jours insuffisante, selon la date d'expiration/DLUO, plus les jours de vente du client.</span><span class="sxs-lookup"><span data-stu-id="de853-119">The batch doesn't have enough shelf-life days remaining, based on the expiration date and best-before date, plus any customer sellable days.</span></span>





