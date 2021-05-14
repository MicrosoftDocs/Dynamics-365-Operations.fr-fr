---
title: Vous ne pouvez pas confirmer une expédition car il n'y a aucune quantité
description: Vous ne pouvez pas confirmer une expédition car il n'y a aucune quantité
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
ms.openlocfilehash: 7a06f0651db741a867e1e9fe7dbab841a928c22b
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938468"
---
# <a name="you-cant-confirm-a-shipment-because-there-is-zero-quantity"></a><span data-ttu-id="31f16-103">Vous ne pouvez pas confirmer une expédition car il n'y a aucune quantité</span><span class="sxs-lookup"><span data-stu-id="31f16-103">You can't confirm a shipment because there is zero quantity</span></span>

<span data-ttu-id="31f16-104">Code d'erreur : LoadLineWarningUpdatedToZero</span><span class="sxs-lookup"><span data-stu-id="31f16-104">Error code: LoadLineWarningUpdatedToZero</span></span>

## <a name="symptoms"></a><span data-ttu-id="31f16-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="31f16-105">Symptoms</span></span>

<span data-ttu-id="31f16-106">Lorsque vous essayez de confirmer une expédition, le système affiche le message d'erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="31f16-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="31f16-107">La ligne de chargement de l’article %1 et de l’expédition %2 a été mise à jour pour avoir une quantité nulle en raison d’un paramétrage de livraisons incomplètes qui permet de rien expédier pour cet article.</span><span class="sxs-lookup"><span data-stu-id="31f16-107">Load line for item %1 and shipment %2 has been updated to have zero quantity due to underdelivery setup allowing not to ship any quantities for this item.</span></span>

<span data-ttu-id="31f16-108">Par conséquent, vous ne pouvez pas confirmer l'expédition pour le chargement.</span><span class="sxs-lookup"><span data-stu-id="31f16-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="31f16-109">Cause</span><span class="sxs-lookup"><span data-stu-id="31f16-109">Cause</span></span>

<span data-ttu-id="31f16-110">Le système évalue si la quantité prélevée est dans les limites attendues, en fonction de la quantité prélevée, de la quantité de la ligne de chargement et du pourcentage de livraisons incomplètes.</span><span class="sxs-lookup"><span data-stu-id="31f16-110">The system evaluates whether the picked quantity is within the expected limits, based on the picked quantity, load line quantity, and underdelivery percentage.</span></span> <span data-ttu-id="31f16-111">Si le système constate que la quantité prélevée sur la ligne de chargement est 0 (zéro), vous ne pouvez pas confirmer l'expédition.</span><span class="sxs-lookup"><span data-stu-id="31f16-111">If the system finds that the picked quantity on the load line is 0 (zero), you can't confirm the shipment.</span></span> <span data-ttu-id="31f16-112">Par exemple, ce problème peut se produire si le travail a été annulé et que le pourcentage de livraisons incomplètes sur la ligne de chargement est de 100 %.</span><span class="sxs-lookup"><span data-stu-id="31f16-112">For example, this issue might occur if work has been canceled, and the underdelivery percentage on the load line is 100 percent.</span></span>

## <a name="resolution"></a><span data-ttu-id="31f16-113">Résolution</span><span class="sxs-lookup"><span data-stu-id="31f16-113">Resolution</span></span>

<span data-ttu-id="31f16-114">Vérifiez vos lignes de chargement pour vous assurer que le pourcentage et les quantités de livraisons incomplètes sont alignés sur le travail sélectionné.</span><span class="sxs-lookup"><span data-stu-id="31f16-114">Check your load lines to make sure that the underdelivery percentage and quantities are aligned with the picked work.</span></span>

1. <span data-ttu-id="31f16-115">Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.</span><span class="sxs-lookup"><span data-stu-id="31f16-115">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="31f16-116">Sélectionnez le chargement pour lequel l'expédition ne peut pas être confirmée.</span><span class="sxs-lookup"><span data-stu-id="31f16-116">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="31f16-117">Sur l'organisateur **Lignes de chargement**, sélectionnez la ligne de chargement de l'article qui dépasse le pourcentage de livraison incomplète.</span><span class="sxs-lookup"><span data-stu-id="31f16-117">On the **Load lines** FastTab, select the load line for the item that exceeds the underdelivery percentage.</span></span>
1. <span data-ttu-id="31f16-118">Modifiez la valeur du champ **Livraison incomplète** ou du champ **Quantité** si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="31f16-118">Adjust the value of the **Underdelivery** field or the **Quantity** field as required.</span></span>

> [!TIP]
> <span data-ttu-id="31f16-119">Si le problème n'est toujours pas résolu, vous devrez peut-être effectuer plus de tâches de retrait pour les commandes client associées ou les commandes de transfert jusqu'à ce que la quantité disponible soit alignée sur le chargement ou l'expédition.</span><span class="sxs-lookup"><span data-stu-id="31f16-119">If the issue still isn't fixed, you might have to complete more picking work for the related sales orders or transfer orders until the available quantity is aligned with the load or shipment.</span></span>
