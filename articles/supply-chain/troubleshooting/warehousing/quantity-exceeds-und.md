---
title: Vous ne pouvez pas confirmer une expédition car la quantité dépasse le pourcentage de livraison incomplète
description: Vous ne pouvez pas confirmer une expédition car la quantité dépasse le pourcentage de livraison incomplète
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 5339b9d800f7454e2a00c230a8d5deca3979c074
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938467"
---
# <a name="you-cant-confirm-a-shipment-because-the-quantity-exceeds-the-underdelivery-percentage"></a><span data-ttu-id="e08ef-103">Vous ne pouvez pas confirmer une expédition car la quantité dépasse le pourcentage de livraison incomplète</span><span class="sxs-lookup"><span data-stu-id="e08ef-103">You can't confirm a shipment because the quantity exceeds the underdelivery percentage</span></span>

<span data-ttu-id="e08ef-104">Code d’erreur : WAX1687</span><span class="sxs-lookup"><span data-stu-id="e08ef-104">Error code: WAX1687</span></span>

## <a name="symptoms"></a><span data-ttu-id="e08ef-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="e08ef-105">Symptoms</span></span>

<span data-ttu-id="e08ef-106">Lorsque vous essayez de confirmer une expédition, le système affiche le message d'erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="e08ef-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="e08ef-107">L'expédition pour le chargement %1 n'a pas pu être confirmée car la quantité pour l'article %2 dépasse le pourcentage défini pour la livraison incomplète.</span><span class="sxs-lookup"><span data-stu-id="e08ef-107">The shipment for load %1 could not be confirmed because the quantity for item %2 exceeds the percentage that is defined for underdelivery.</span></span>

<span data-ttu-id="e08ef-108">Par conséquent, vous ne pouvez pas confirmer l'expédition pour le chargement.</span><span class="sxs-lookup"><span data-stu-id="e08ef-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="e08ef-109">Cause</span><span class="sxs-lookup"><span data-stu-id="e08ef-109">Cause</span></span>

<span data-ttu-id="e08ef-110">La quantité du chargement ou de l'expédition n'a été que partiellement prélevée.</span><span class="sxs-lookup"><span data-stu-id="e08ef-110">The quantity of the load or shipment has been only partially picked.</span></span> <span data-ttu-id="e08ef-111">La quantité est actuellement inférieure à la quantité prélevée d'un pourcentage qui est en dehors du pourcentage de livraison incomplète autorisé.</span><span class="sxs-lookup"><span data-stu-id="e08ef-111">The quantity is currently less than the picked quantity by a percentage that is outside the allowed underdelivery percentage.</span></span>

## <a name="resolution"></a><span data-ttu-id="e08ef-112">Résolution</span><span class="sxs-lookup"><span data-stu-id="e08ef-112">Resolution</span></span>

<span data-ttu-id="e08ef-113">Pour résoudre ce problème, effectuez une ou plusieurs des tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="e08ef-113">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="e08ef-114">Définissez la quantité de ligne de charge.</span><span class="sxs-lookup"><span data-stu-id="e08ef-114">Set the load line quantity.</span></span>
- <span data-ttu-id="e08ef-115">Définissez le pourcentage de livraison incomplète.</span><span class="sxs-lookup"><span data-stu-id="e08ef-115">Set the underdelivery percentage.</span></span>

### <a name="set-the-load-line-quantity"></a><span data-ttu-id="e08ef-116">Définir la quantité de ligne de chargement</span><span class="sxs-lookup"><span data-stu-id="e08ef-116">Set the load line quantity</span></span>

<span data-ttu-id="e08ef-117">Pour définir la quantité de ligne de chargement, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e08ef-117">To set the load line quantity, follow these steps.</span></span>

1. <span data-ttu-id="e08ef-118">Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.</span><span class="sxs-lookup"><span data-stu-id="e08ef-118">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="e08ef-119">Sélectionnez le chargement pour lequel l'expédition ne peut pas être confirmée.</span><span class="sxs-lookup"><span data-stu-id="e08ef-119">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="e08ef-120">Sur l'organisateur **Lignes de chargement**, sélectionnez la ligne de chargement de l'article qui dépasse le pourcentage de livraison incomplète.</span><span class="sxs-lookup"><span data-stu-id="e08ef-120">On the **Load lines** FastTab, select the load line for the item that exceeds the underdelivery percentage.</span></span>
1. <span data-ttu-id="e08ef-121">Dans l’organisateur **Détails de ligne**, sélectionnez **Ordre**.</span><span class="sxs-lookup"><span data-stu-id="e08ef-121">On the **Line details** FastTab, select **Order**.</span></span>
1. <span data-ttu-id="e08ef-122">Dans le champ **Quantité**, définissez la valeur sur la quantité prélevée (c'est-à-dire sur la valeur **Quantité créée par le travail**), afin que la confirmation d'expédition puisse avoir lieu.</span><span class="sxs-lookup"><span data-stu-id="e08ef-122">In the **Quantity** field, set the value to the picked quantity (that is, to the **Work created quantity** value), so that shipment confirmation can occur.</span></span>

### <a name="set-the-underdelivery-percentage"></a><span data-ttu-id="e08ef-123">Définir le pourcentage de livraison incomplète</span><span class="sxs-lookup"><span data-stu-id="e08ef-123">Set the underdelivery percentage</span></span>

<span data-ttu-id="e08ef-124">Pour définir le pourcentage de livraison incomplète, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e08ef-124">To set the underdelivery percentage, follow these steps.</span></span>

1. <span data-ttu-id="e08ef-125">Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.</span><span class="sxs-lookup"><span data-stu-id="e08ef-125">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="e08ef-126">Sélectionnez le chargement pour lequel l'expédition ne peut pas être confirmée.</span><span class="sxs-lookup"><span data-stu-id="e08ef-126">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="e08ef-127">Sur l'organisateur **Lignes de chargement**, sélectionnez la ligne de chargement de l'article qui dépasse le pourcentage de livraison incomplète.</span><span class="sxs-lookup"><span data-stu-id="e08ef-127">On the **Load lines** FastTab, select the load line for the item that exceeds the underdelivery percentage.</span></span>
1. <span data-ttu-id="e08ef-128">Dans l’organisateur **Détails de ligne**, sélectionnez **Général**.</span><span class="sxs-lookup"><span data-stu-id="e08ef-128">On the **Line details** FastTab, select **General**.</span></span>
1. <span data-ttu-id="e08ef-129">Dans le champ **Livraison incomplète**, définissez la valeur sur un pourcentage plus élevé qui tient compte de la quantité prélevée par rapport à la quantité de chargement, afin que la confirmation d'expédition puisse avoir lieu.</span><span class="sxs-lookup"><span data-stu-id="e08ef-129">In the **Underdelivery** field, set the value to a larger percentage that accommodates the quantity that has been picked against the load quantity, so that shipment confirmation can occur.</span></span>
