---
title: "Tenir à jour les ordres prévisionnels"
description: "Cet article fournit des informations sur la gestion des ordres prévisionnels. Il décrit la manière dont vous pouvez mettre à jour le statut des ordres prévisionnels, les confirmer et filtrer les ordres prévisionnels ayant le même statut qu'un ordre prévisionnel sélectionné."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 8931908fbf643a8154da70d2ad065ea47d2aa4e6
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="maintain-planned-orders"></a><span data-ttu-id="8d5a2-104">Tenir à jour les ordres prévisionnels</span><span class="sxs-lookup"><span data-stu-id="8d5a2-104">Maintain planned orders</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="8d5a2-105">Cet article fournit des informations sur la gestion des ordres prévisionnels.</span><span class="sxs-lookup"><span data-stu-id="8d5a2-105">This article provides information about how to manage planned orders.</span></span> <span data-ttu-id="8d5a2-106">Il décrit la manière dont vous pouvez mettre à jour le statut des ordres prévisionnels, les confirmer et filtrer les ordres prévisionnels ayant le même statut qu'un ordre prévisionnel sélectionné.</span><span class="sxs-lookup"><span data-stu-id="8d5a2-106">It describes how you can update the status of planned orders, firm them, and filter for planned orders that have the same status as a selected planned order.</span></span>

<span data-ttu-id="8d5a2-107">Vous pouvez gérer les ordres prévisionnels à partir de l'espace de travail **Planification**, de la liste **Ordre prévisionnel** ou des listes **Ordres de fabrication prévisionnels**, **Commandes fournisseur prévisionnelles** et **Transfert prévisionnel**.</span><span class="sxs-lookup"><span data-stu-id="8d5a2-107">You can manage planned orders from the **Master planning** workspace, the **Planned order** list, or the **Planned production orders**, **Planned purchase orders**, and **Planned transfer** lists.</span></span> <span data-ttu-id="8d5a2-108">Vous pouvez utiliser le champ **Statut** pour aider à suivre la progression.</span><span class="sxs-lookup"><span data-stu-id="8d5a2-108">You can use the **Status** field to help track your progress.</span></span> <span data-ttu-id="8d5a2-109">Les valeurs suivantes sont utilisées :</span><span class="sxs-lookup"><span data-stu-id="8d5a2-109">The following values are used:</span></span>

-   <span data-ttu-id="8d5a2-110">Lorsque la planification génère des ordres prévisionnels, leur statut est **Non traité**.</span><span class="sxs-lookup"><span data-stu-id="8d5a2-110">When master planning generates planned orders, the planned orders have a status of **Unprocessed**.</span></span>
-   <span data-ttu-id="8d5a2-111">Si vous décidez de ne pas confirmer un ordre prévisionnel, vous pouvez lui attribuer le statut **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="8d5a2-111">If you decide not to firm a planned order, you can give it a status of **Completed**.</span></span>
-   <span data-ttu-id="8d5a2-112">Si vous décidez de confirmer un ordre prévisionnel, vous pouvez lui attribuer le statut **Approuvé**.</span><span class="sxs-lookup"><span data-stu-id="8d5a2-112">When you decide to firm a planned order, you can give it a status of **Approved**.</span></span> <span data-ttu-id="8d5a2-113">Ce statut indique que vous approuvez la confirmation de l'ordre prévisionnel, mais que celui-ci n'est pas encore confirmé.</span><span class="sxs-lookup"><span data-stu-id="8d5a2-113">This status indicates that you approve firming of the planned order, but it isn't firmed yet.</span></span>

<span data-ttu-id="8d5a2-114">**Remarque :** un ordre prévisionnel approuvé est transféré dans son état actuel vers le calcul de planification suivant.</span><span class="sxs-lookup"><span data-stu-id="8d5a2-114">**Note:** An approved planned order is transferred, in its current state, to the next master planning calculation.</span></span> <span data-ttu-id="8d5a2-115">Vous pouvez confirmer les ordres prévisionnels en cliquant sur **Confirmer**.</span><span class="sxs-lookup"><span data-stu-id="8d5a2-115">You can firm planned orders by clicking **Firm**.</span></span> <span data-ttu-id="8d5a2-116">Vous pouvez confirmer les ordres prévisionnels suivants :</span><span class="sxs-lookup"><span data-stu-id="8d5a2-116">You can firm the following planned orders:</span></span>

-   <span data-ttu-id="8d5a2-117">Ordre prévisionnel sélectionné.</span><span class="sxs-lookup"><span data-stu-id="8d5a2-117">The planned order that is selected.</span></span>
-   <span data-ttu-id="8d5a2-118">Plusieurs ordres prévisionnels.</span><span class="sxs-lookup"><span data-stu-id="8d5a2-118">Multiple planned orders.</span></span>
-   <span data-ttu-id="8d5a2-119">Ordres prévisionnels générés par un éclatement dans la page **Éclatement**.</span><span class="sxs-lookup"><span data-stu-id="8d5a2-119">Planned orders that are generated by an explosion from the **Explosion** page.</span></span> <span data-ttu-id="8d5a2-120">Cliquez sur **Ordres prévisionnels**, sélectionnez l'ordre prévisionnel, puis cliquez sur **Confirmer**.</span><span class="sxs-lookup"><span data-stu-id="8d5a2-120">Click **Planned orders**, select the planned order, and then click **Firm**.</span></span>

<span data-ttu-id="8d5a2-121">Après confirmation, l'ordre prévisionnel est déplacé vers la section Commandes du module approprié.</span><span class="sxs-lookup"><span data-stu-id="8d5a2-121">When a planned order is firmed, it's moved to the orders section of the relevant module.</span></span> <span data-ttu-id="8d5a2-122">**Remarque :** vous pouvez cliquer avec le bouton droit sur un ordre prévisionnel ayant un statut particulier et effectuer un filtrage afin de trouver d'autres ordres prévisionnels avec le même statut.</span><span class="sxs-lookup"><span data-stu-id="8d5a2-122">**Note:** You can right-click a planned order that has a particular status and filter for other planned orders that have the same status.</span></span> <span data-ttu-id="8d5a2-123">Cette fonctionnalité est utile si, par exemple, vous souhaitez filtrer tous les ordres prévisionnels ayant le statut **Approuvé**, afin de les confirmer.</span><span class="sxs-lookup"><span data-stu-id="8d5a2-123">This functionality is useful if, for example, you want to filter for all planned orders that have a status of **Approved**, so that you can then firm them.</span></span>

<a name="see-also"></a><span data-ttu-id="8d5a2-124">Voir également :</span><span class="sxs-lookup"><span data-stu-id="8d5a2-124">See also</span></span>
--------

[<span data-ttu-id="8d5a2-125">Plans généraux</span><span class="sxs-lookup"><span data-stu-id="8d5a2-125">Master plans</span></span>](master-plans.md)




