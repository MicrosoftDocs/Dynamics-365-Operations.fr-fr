---
title: La dernière ligne de travail clôturée doit être un placement.
description: La dernière ligne de travail clôturée doit être un placement.
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel, WHSWorkTableListPage_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a5b78154b51252b3ac96ba28c254e823caf87019
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924373"
---
# <a name="the-last-closed-work-line-must-be-a-put"></a><span data-ttu-id="2bb23-103">La dernière ligne de travail clôturée doit être un placement.</span><span class="sxs-lookup"><span data-stu-id="2bb23-103">The last closed work line must be a put</span></span>

<span data-ttu-id="2bb23-104">Code d’erreur : WAX1285</span><span class="sxs-lookup"><span data-stu-id="2bb23-104">Error code: WAX1285</span></span>

## <a name="symptoms"></a><span data-ttu-id="2bb23-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="2bb23-105">Symptoms</span></span>

<span data-ttu-id="2bb23-106">Le système affiche le message d'erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="2bb23-106">The system shows the following error message:</span></span>

> <span data-ttu-id="2bb23-107">La dernière ligne de travail clôturée doit être un placement.</span><span class="sxs-lookup"><span data-stu-id="2bb23-107">The last closed work line must be a put.</span></span>

## <a name="cause"></a><span data-ttu-id="2bb23-108">Cause</span><span class="sxs-lookup"><span data-stu-id="2bb23-108">Cause</span></span>

<span data-ttu-id="2bb23-109">Le travail ne peut pas être annulé dans son état actuel.</span><span class="sxs-lookup"><span data-stu-id="2bb23-109">The work can't be canceled in its current state.</span></span>

<span data-ttu-id="2bb23-110">Sur la dernière ligne de travail, le champ **Statut de travail** est défini sur *Clôturé*, mais le champ **Type de travail** n'est pas défini sur *Placement*.</span><span class="sxs-lookup"><span data-stu-id="2bb23-110">On the last work line, the **Work status** field is set to *Closed*, but the **Work type** field isn't set to *Put*.</span></span>

## <a name="resolution"></a><span data-ttu-id="2bb23-111">Résolution</span><span class="sxs-lookup"><span data-stu-id="2bb23-111">Resolution</span></span>

<span data-ttu-id="2bb23-112">Pour annuler le travail, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="2bb23-112">To cancel the work, follow these steps.</span></span>

1. <span data-ttu-id="2bb23-113">Allez dans **Gestion des entrepôts \> Tâches périodiques \> Nettoyer \> Annuler le travail**.</span><span class="sxs-lookup"><span data-stu-id="2bb23-113">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="2bb23-114">Dans le champ **ID de travail**, spécifiez l'ID du travail que vous souhaitez annuler.</span><span class="sxs-lookup"><span data-stu-id="2bb23-114">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span>
1. <span data-ttu-id="2bb23-115">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2bb23-115">Select **OK**.</span></span>
1. <span data-ttu-id="2bb23-116">Sélectionnez **Oui** pour confirmer que vous souhaitez annuler le travail.</span><span class="sxs-lookup"><span data-stu-id="2bb23-116">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="2bb23-117">Pour en savoir plus, voir [Annuler le travail en entrepôt pour la gestion des exceptions](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="2bb23-117">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
