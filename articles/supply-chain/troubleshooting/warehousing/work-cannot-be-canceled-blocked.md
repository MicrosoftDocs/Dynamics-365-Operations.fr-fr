---
title: Le travail ne peut pas être annulé car il est bloqué
description: Le travail ne peut pas être annulé car il est bloqué
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a7ab4c7263947767164702fb7dd6da7573175253
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924277"
---
# <a name="work-cant-be-canceled-because-its-blocked"></a><span data-ttu-id="6ee84-103">Le travail ne peut pas être annulé car il est bloqué</span><span class="sxs-lookup"><span data-stu-id="6ee84-103">Work can't be canceled because it's blocked</span></span>

<span data-ttu-id="6ee84-104">Code d'erreur : WHSCancellationOfWorkBlockedByExecutingWave_ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="6ee84-104">Error code: WHSCancellationOfWorkBlockedByExecutingWave_ErrorMessage</span></span>

## <a name="symptoms"></a><span data-ttu-id="6ee84-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="6ee84-105">Symptoms</span></span>

<span data-ttu-id="6ee84-106">Le système affiche le message d'erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="6ee84-106">The system shows the following error message:</span></span>

> <span data-ttu-id="6ee84-107">Le travail %1 ne peut pas être annulé car il est bloqué par le type de motif %2.</span><span class="sxs-lookup"><span data-stu-id="6ee84-107">Work %1 cannot be cancelled because it is blocked by reason type %2.</span></span> <span data-ttu-id="6ee84-108">Le travail doit être débloqué avant de pouvoir être annulé.</span><span class="sxs-lookup"><span data-stu-id="6ee84-108">The work must be unblocked before it can be cancelled.</span></span>

## <a name="cause"></a><span data-ttu-id="6ee84-109">Cause</span><span class="sxs-lookup"><span data-stu-id="6ee84-109">Cause</span></span>

<span data-ttu-id="6ee84-110">Le travail est bloqué par un utilisateur et ne peut pas être annulé.</span><span class="sxs-lookup"><span data-stu-id="6ee84-110">The work is blocked and can't be canceled.</span></span>

<span data-ttu-id="6ee84-111">Sur la page **Travail**, sur l'onglet **Général**, l'option **Bloqué** est définie sur *Oui*.</span><span class="sxs-lookup"><span data-stu-id="6ee84-111">On the **Work** page, on the **General** tab, the **Blocked** option is set to *Yes*.</span></span> <span data-ttu-id="6ee84-112">Ce paramètre indique que le travail est bloqué.</span><span class="sxs-lookup"><span data-stu-id="6ee84-112">This setting indicates that the work is blocked.</span></span> <span data-ttu-id="6ee84-113">L'onglet **Motifs de blocage** montre pourquoi le travail a été bloqué.</span><span class="sxs-lookup"><span data-stu-id="6ee84-113">The **Blocking reasons** tab shows why the work was blocked.</span></span>

## <a name="resolution"></a><span data-ttu-id="6ee84-114">Résolution</span><span class="sxs-lookup"><span data-stu-id="6ee84-114">Resolution</span></span>

<span data-ttu-id="6ee84-115">Pour débloquer le travail, sélectionnez l'onglet **Motifs de blocage**, puis suivez l'une de ces étapes :</span><span class="sxs-lookup"><span data-stu-id="6ee84-115">To unblock the work, select the **Blocking reasons** tab, and then follow one of these steps:</span></span>

- <span data-ttu-id="6ee84-116">Si le champ **Motif de blocage de travail** est défini sur *Raison indéfinie* : Dans le volet Actions, sur l'onglet **Travail**, dans le groupe **Travail**, sélectionnez **Débloquer le travail**.</span><span class="sxs-lookup"><span data-stu-id="6ee84-116">If the **Work blocking reason** field is set to *Undefined reason*: On the Action Pane, on the **Work** tab, in the **Work** group, select **Unblock work**.</span></span>
- <span data-ttu-id="6ee84-117">Si le champ **Motif de blocage de travail** est défini sur *Traitement de la vague* : Dans le volet Actions, sous l’onglet **Informations associées**, dans le groupe **Informations associées**, sélectionnez **Vague**.</span><span class="sxs-lookup"><span data-stu-id="6ee84-117">If the **Work blocking reason** field is set to *Processing wave*: On the Action Pane, on the **Related information** tab, in the **Related information** group, select **Wave**.</span></span> <span data-ttu-id="6ee84-118">Puis, sur la page **Vagues**, dans le volet Actions, sous l’onglet **Vague**, dans le groupe **Vague**, sélectionnez **Nettoyage des données de vague**.</span><span class="sxs-lookup"><span data-stu-id="6ee84-118">Then, on the **Waves** page, on the Action Pane, on the **Wave** tab, in the **Wave** group, select **Cleanup wave data**.</span></span>

## <a name="workaround"></a><span data-ttu-id="6ee84-119">Solution de contournement</span><span class="sxs-lookup"><span data-stu-id="6ee84-119">Workaround</span></span>

<span data-ttu-id="6ee84-120">Si les étapes précédentes n'ont pas résolu le problème, vous pouvez annuler le travail en suivant ces étapes.</span><span class="sxs-lookup"><span data-stu-id="6ee84-120">If the previous steps didn't fix the issue, you can cancel the work by following these steps.</span></span>

1. <span data-ttu-id="6ee84-121">Allez dans **Gestion des entrepôts \> Tâches périodiques \> Nettoyer \> Annuler le travail**.</span><span class="sxs-lookup"><span data-stu-id="6ee84-121">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="6ee84-122">Dans le champ **ID de travail**, spécifiez l'ID de travail que vous souhaitez annuler et dont le **Statut de travail** est actuellement *Ouvert*, *En cours*, *Annulé*, *Combiné* ou *Fermé*.</span><span class="sxs-lookup"><span data-stu-id="6ee84-122">In the **Work ID** field, specify the ID of the work that you want to cancel, and that currently has a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="6ee84-123">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6ee84-123">Select **OK**.</span></span>
1. <span data-ttu-id="6ee84-124">Sélectionnez **Oui** pour confirmer que vous souhaitez annuler le travail.</span><span class="sxs-lookup"><span data-stu-id="6ee84-124">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="6ee84-125">Pour en savoir plus, voir [Annuler le travail en entrepôt pour la gestion des exceptions](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="6ee84-125">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
