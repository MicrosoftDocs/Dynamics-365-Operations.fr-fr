---
title: Le numéro de lot est effacé lorsqu'un nouvel ID de lot est sélectionné
description: Lorsque vous consultez une ligne de journal de liste de prélèvement, la valeur du champ Numéro de lot est effacée si vous sélectionnez une nouvelle valeur dans le champ ID de lot.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdJournalTransBOM
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: datra
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 71977a04adb066a8b51c9bf7b8c5a4e752ca902e
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026492"
---
# <a name="batch-number-is-cleared-when-a-new-lot-id-is-selected"></a><span data-ttu-id="ed9a3-103">Le numéro de lot est effacé lorsqu'un nouvel ID de lot est sélectionné</span><span class="sxs-lookup"><span data-stu-id="ed9a3-103">Batch number is cleared when a new lot ID is selected</span></span>

<span data-ttu-id="ed9a3-104">Numéro de la base de connaissances : 4613107</span><span class="sxs-lookup"><span data-stu-id="ed9a3-104">KB number: 4613107</span></span>

## <a name="symptoms"></a><span data-ttu-id="ed9a3-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="ed9a3-105">Symptoms</span></span>

<span data-ttu-id="ed9a3-106">Lorsque vous consultez une ligne de journal de liste de prélèvement, la valeur du champ **Numéro de lot** est effacée si vous sélectionnez une nouvelle valeur dans le champ **ID de lot**.</span><span class="sxs-lookup"><span data-stu-id="ed9a3-106">When you're reviewing a picking list journal line, the value in the **Batch number** field is cleared if you select a new value in the **Lot ID** field.</span></span>

## <a name="resolution"></a><span data-ttu-id="ed9a3-107">Résolution</span><span class="sxs-lookup"><span data-stu-id="ed9a3-107">Resolution</span></span>

<span data-ttu-id="ed9a3-108">Le système se comporte comme prévu.</span><span class="sxs-lookup"><span data-stu-id="ed9a3-108">The system is behaving as designed.</span></span> <span data-ttu-id="ed9a3-109">Si vous modifiez l'ID de lot, vous modifiez le contexte de l'article.</span><span class="sxs-lookup"><span data-stu-id="ed9a3-109">If you change the lot ID, you change the item context.</span></span> <span data-ttu-id="ed9a3-110">Par conséquent, le numéro de lot est réinitialisé.</span><span class="sxs-lookup"><span data-stu-id="ed9a3-110">Therefore, the batch number is reset.</span></span>

<span data-ttu-id="ed9a3-111">Pour associer le numéro de lot à un ID de lot, vous devez d'abord définir l'ID de lot.</span><span class="sxs-lookup"><span data-stu-id="ed9a3-111">To associate the batch number with a lot ID, you must set the lot ID first.</span></span>
