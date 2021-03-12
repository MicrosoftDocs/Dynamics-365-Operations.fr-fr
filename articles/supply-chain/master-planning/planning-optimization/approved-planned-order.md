---
title: Approuver les ordres prévisionnels
description: Cette rubrique décrit l’approbation des ordres prévisionnels pris en charge dans l’Optimisation de la planification.
author: ChristianRytt
manager: tfehr
ms.date: 08/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: c29ede7ad8916a97b4a04b68f41961f79810e0c8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983567"
---
# <a name="approve-planned-orders"></a><span data-ttu-id="69cfd-103">Approuver les ordres prévisionnels</span><span class="sxs-lookup"><span data-stu-id="69cfd-103">Approve planned orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="69cfd-104">Cette rubrique fournit des informations sur la mise à jour du statut des ordres prévisionnels dans l’Optimisation de la planification.</span><span class="sxs-lookup"><span data-stu-id="69cfd-104">This topic provides information about how to update the status of planned orders in Planning Optimization.</span></span>

<span data-ttu-id="69cfd-105">Notez que l’approbation des ordres prévisionnels est une étape facultative, sur la façon de créer un ordre confirmé à partir d’un ordre prévisionnel.</span><span class="sxs-lookup"><span data-stu-id="69cfd-105">Note that approval of planned orders is an optional step, on the way to create a firmed order from a planned order.</span></span> <span data-ttu-id="69cfd-106">Il est recommandé d’approuver les ordres prévisionnels modifiés, sinon les modifications seront ignorées et écrasées lors du prochain cycle de planification.</span><span class="sxs-lookup"><span data-stu-id="69cfd-106">It is recommended to approve modified planned orders, otherwise the edits will be ignored and overwritten by the next planning run.</span></span>

![Flux d’ordre prévisionnel](media/approved-planned-orders-1.png)

<span data-ttu-id="69cfd-108">Le champ **Statut** vous aide à suivre votre progression en utilisant les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="69cfd-108">The **Status** field helps you tack your progress using the following values:</span></span>

- <span data-ttu-id="69cfd-109">**Non traité :** Lorsque la planification génère des ordres prévisionnels, leur statut est *Non traité*.</span><span class="sxs-lookup"><span data-stu-id="69cfd-109">**Unprocessed:** When master planning generates planned orders, the planned orders have a status of *Unprocessed*.</span></span> <span data-ttu-id="69cfd-110">Les ordres prévisionnels avec ce statut seront supprimés lors du prochain cycle de planification.</span><span class="sxs-lookup"><span data-stu-id="69cfd-110">Planned orders with this status will be deleted during the next planning run.</span></span>
- <span data-ttu-id="69cfd-111">**Terminé :** Si vous décidez de ne pas confirmer un ordre prévisionnel, vous pouvez modifier le statut sur *Terminé* pour indiquer que vous avez terminé l’évaluation de cet ordre prévisionnel.</span><span class="sxs-lookup"><span data-stu-id="69cfd-111">**Completed:** If you decide not to firm a planned order, you can change the status to *Completed* to indicate that you completed evaluating this planned order.</span></span> <span data-ttu-id="69cfd-112">Notez qu’un statut de *Non traité* et *Terminé* sont traités de la même manière par le système.</span><span class="sxs-lookup"><span data-stu-id="69cfd-112">Note that a status of *Unprocessed* and *Completed* are treated the same by the system.</span></span>
- <span data-ttu-id="69cfd-113">**Approuvé :** Si vous souhaitez conserver les modifications ou prévoyez de confirmer un ordre prévisionnel, changez le statut sur *Approuvé*.</span><span class="sxs-lookup"><span data-stu-id="69cfd-113">**Approved:** If you want to keep edits or are planning to firm a planned order, change the status to *Approved*.</span></span> <span data-ttu-id="69cfd-114">Les ordres prévisionnels avec le statut *Approuvé* sont considérés comme un approvisionnement fixe et prévu par la planification, de sorte qu’ils ne sont pas modifiés ou supprimés pendant une exécution ultérieure de la planification.</span><span class="sxs-lookup"><span data-stu-id="69cfd-114">Planned orders with *Approved* status are considered as fixed and expected supply by master planning, so they are not modified or deleted during later master planning runs.</span></span> <span data-ttu-id="69cfd-115">Pour ce faire, la logique de planification copie les ordres prévisionnels *Approuvés* de l’ancienne version de plan vers la nouvelle version de plan lors de la planification.</span><span class="sxs-lookup"><span data-stu-id="69cfd-115">To achieve this, the planning logic copies the *Approved* planned orders from the old plan version to the new plan version during master planning.</span></span> <span data-ttu-id="69cfd-116">Notez que les ordres prévisionnels *Approuvés* ne sont considérés comme des approvisionnements que dans le cadre du plan spécifique.</span><span class="sxs-lookup"><span data-stu-id="69cfd-116">Note that *Approved* planned orders are only considered supply within the specific master plan.</span></span>

<span data-ttu-id="69cfd-117">Vous pouvez gérer les ordres prévisionnels à partir de l’espace de travail **Planification**, de la liste **Ordre prévisionnel** ou des listes **Ordres de fabrication prévisionnels**, **Commandes fournisseur prévisionnelles** et **Transfert prévisionnel**.</span><span class="sxs-lookup"><span data-stu-id="69cfd-117">You can manage planned orders from the  **Master planning**  workspace, the  **Planned order**  list, or the  **Planned production orders**,  **Planned purchase orders**, and  **Planned transfer**  lists.</span></span>
