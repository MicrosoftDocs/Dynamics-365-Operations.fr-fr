---
title: Le travail reste bloqué
description: Le travail reste bloqué
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTableListPage_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f85364d1ecfadc36b26c3395ab4402d3cb3b1603
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924128"
---
# <a name="work-remains-blocked"></a><span data-ttu-id="8df62-103">Le travail reste bloqué</span><span class="sxs-lookup"><span data-stu-id="8df62-103">Work remains blocked</span></span>

<span data-ttu-id="8df62-104">Code d'erreur : WHSWorkBlockingExecutingWaveReason_ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="8df62-104">Error code: WHSWorkBlockingExecutingWaveReason_ErrorMessage</span></span>

## <a name="symptoms"></a><span data-ttu-id="8df62-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="8df62-105">Symptoms</span></span>

<span data-ttu-id="8df62-106">Le système affiche le message d'erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="8df62-106">The system shows the following error message:</span></span>

> <span data-ttu-id="8df62-107">Le travail %1 reste bloqué, car la vague associée %2 présente le statut %3.</span><span class="sxs-lookup"><span data-stu-id="8df62-107">Work %1 remains blocked because the related wave %2 has status %3.</span></span>

## <a name="cause"></a><span data-ttu-id="8df62-108">Cause</span><span class="sxs-lookup"><span data-stu-id="8df62-108">Cause</span></span>

<span data-ttu-id="8df62-109">Le travail est en cours de traitement dans une vague et ne peut pas être débloqué, comme l'indique l'une des conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="8df62-109">The work is currently being processed on a wave and can't be unblocked, as indicated by one of the following conditions:</span></span>

- <span data-ttu-id="8df62-110">Dans l'onglet **Motifs de blocage**, le champ **Motif de blocage de travail** pour une ou plusieurs lignes est défini sur *Traitement de la vague*.</span><span class="sxs-lookup"><span data-stu-id="8df62-110">On the **Blocking reasons** tab, the **Work blocking reason** field for one or more lines is set to *Processing wave*.</span></span>
- <span data-ttu-id="8df62-111">Lorsque vous sélectionnez **Vague** dans le groupe **Informations associées** de l'onglet **Informations associées** du volet Actions, le champ **Statut de la vague** est défini sur *Traitement*.</span><span class="sxs-lookup"><span data-stu-id="8df62-111">When you select **Wave** in the **Related information** group on the **Related information** tab of the Action Pane, the **Wave status** field is set to *Processing*.</span></span>

## <a name="resolution"></a><span data-ttu-id="8df62-112">Résolution</span><span class="sxs-lookup"><span data-stu-id="8df62-112">Resolution</span></span>

<span data-ttu-id="8df62-113">Dans le volet Actions, sous l’onglet **Informations associées**, dans le groupe **Informations associées**, cliquez sur **Vague**.</span><span class="sxs-lookup"><span data-stu-id="8df62-113">On the Action Pane, on the **Related information** tab, in the **Related information** group, select **Wave**.</span></span> <span data-ttu-id="8df62-114">Puis, sur la page **Vagues**, dans le volet Actions, sous l’onglet **Vague**, dans le groupe **Vague**, sélectionnez **Nettoyage des données de vague**.</span><span class="sxs-lookup"><span data-stu-id="8df62-114">Then, on the **Waves** page, on the Action Pane, on the **Wave** tab, in the **Wave** group, select **Cleanup wave data**.</span></span>

## <a name="workaround"></a><span data-ttu-id="8df62-115">Solution de contournement</span><span class="sxs-lookup"><span data-stu-id="8df62-115">Workaround</span></span>

<span data-ttu-id="8df62-116">Si les étapes précédentes n'ont pas résolu le problème, vous pouvez annuler le travail en suivant ces étapes.</span><span class="sxs-lookup"><span data-stu-id="8df62-116">If the previous steps didn't fix the issue, you can cancel the work by following these steps.</span></span>

1. <span data-ttu-id="8df62-117">Allez dans **Gestion des entrepôts \> Tâches périodiques \> Nettoyer \> Annuler le travail**.</span><span class="sxs-lookup"><span data-stu-id="8df62-117">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="8df62-118">Dans le champ **ID de travail**, spécifiez l'ID de travail que vous souhaitez annuler et dont le **Statut de travail** est actuellement *Ouvert*, *En cours*, *Annulé*, *Combiné* ou *Fermé*.</span><span class="sxs-lookup"><span data-stu-id="8df62-118">In the **Work ID** field, specify the ID of the work that you want to cancel, and that currently has a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="8df62-119">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8df62-119">Select **OK**.</span></span>
1. <span data-ttu-id="8df62-120">Sélectionnez **Oui** pour confirmer que vous souhaitez annuler le travail.</span><span class="sxs-lookup"><span data-stu-id="8df62-120">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="8df62-121">Pour en savoir plus, voir [Annuler le travail en entrepôt pour la gestion des exceptions](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="8df62-121">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
