---
title: Vous ne pouvez pas confirmer une expédition car les articles n'ont pas été retirés
description: Vous ne pouvez pas confirmer une expédition car les articles n'ont pas été retirés
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
ms.openlocfilehash: 23a517e7769dc86ebec30e4f17c62172a6ad8801
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938469"
---
# <a name="you-cant-confirm-a-shipment-because-items-havent-been-picked"></a><span data-ttu-id="4a3ed-103">Vous ne pouvez pas confirmer une expédition car les articles n'ont pas été retirés</span><span class="sxs-lookup"><span data-stu-id="4a3ed-103">You can't confirm a shipment because items haven't been picked</span></span>

<span data-ttu-id="4a3ed-104">Code d'erreur : LoadNotPickedAndMovedToFinalShippingLocation</span><span class="sxs-lookup"><span data-stu-id="4a3ed-104">Error code: LoadNotPickedAndMovedToFinalShippingLocation</span></span>

## <a name="symptoms"></a><span data-ttu-id="4a3ed-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="4a3ed-105">Symptoms</span></span>

<span data-ttu-id="4a3ed-106">Lorsque vous essayez de confirmer une expédition, le système affiche le message d'erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="4a3ed-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="4a3ed-107">Certains des articles nécessaires pour le chargement %1 n'ont pas encore été prélevés et ont été déplacés vers l'emplacement d'expédition final.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-107">Some of the items that are needed for load %1 have not yet been picked and moved to the final shipping location.</span></span>

<span data-ttu-id="4a3ed-108">Par conséquent, vous ne pouvez pas confirmer l'expédition pour le chargement.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="4a3ed-109">Cause</span><span class="sxs-lookup"><span data-stu-id="4a3ed-109">Cause</span></span>

<span data-ttu-id="4a3ed-110">Le chargement ou l'expédition ne peut pas être confirmé dans son état actuel car l'une des conditions suivantes peut exister :</span><span class="sxs-lookup"><span data-stu-id="4a3ed-110">The load or shipment can't be confirmed in its current state because one of the following conditions might exist:</span></span>

- <span data-ttu-id="4a3ed-111">Le travail associé n'a pas encore été sélectionné et déplacé vers le lieu d'expédition final.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-111">The related work hasn't yet been picked and moved to the final shipping location.</span></span>
- <span data-ttu-id="4a3ed-112">La quantité retirée ne correspond pas à celle créée sur la ligne de chargement.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-112">The picked work quantity doesn't match the created work quantity on the load line.</span></span>

## <a name="resolution"></a><span data-ttu-id="4a3ed-113">Résolution</span><span class="sxs-lookup"><span data-stu-id="4a3ed-113">Resolution</span></span>

<span data-ttu-id="4a3ed-114">Vérifiez les commandes client associées ou les commandes de transfert pour le chargement ou l'expédition.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-114">Check the related sales orders or transfer orders for the load or shipment.</span></span> <span data-ttu-id="4a3ed-115">Assurez-vous que tous les travaux connexes ont été effectués à l'emplacement d'expédition finale et que les quantités correspondent.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-115">Make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="4a3ed-116">Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-116">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="4a3ed-117">Sélectionnez le chargement pour lequel l'expédition ne peut pas être confirmée.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-117">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="4a3ed-118">Dans l’organisateur **Lignes de chargement**, sélectionnez la ligne de chargement.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-118">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="4a3ed-119">Notez la valeur du champ **Quantité créée**.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-119">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="4a3ed-120">Dans le volet Actions, sous l’onglet **Chargements**, dans le groupe **Informations associées**, cliquez sur **Travail**.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-120">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="4a3ed-121">Vérifiez que le travail a été terminé à l'emplacement d'expédition finale et que la quantité retirée correspond à celle créée sur la ligne de chargement.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-121">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="4a3ed-122">Répétez cette procédure pour toutes les lignes de chargement afin de vous assurer que tous les critères sont remplis.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-122">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>
