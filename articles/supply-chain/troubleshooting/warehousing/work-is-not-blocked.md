---
title: Le travail n'est pas bloqué
description: Le travail n'est pas bloqué
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d64ab282972e46e8857581b59e5705dd15667328
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924202"
---
# <a name="work-isnt-blocked"></a><span data-ttu-id="7f427-103">Le travail n'est pas bloqué</span><span class="sxs-lookup"><span data-stu-id="7f427-103">Work isn't blocked</span></span>

<span data-ttu-id="7f427-104">Code d'erreur : WHSUnblockNotBlockedWorkErrorMessage</span><span class="sxs-lookup"><span data-stu-id="7f427-104">Error code: WHSUnblockNotBlockedWorkErrorMessage</span></span>

## <a name="symptoms"></a><span data-ttu-id="7f427-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="7f427-105">Symptoms</span></span>

<span data-ttu-id="7f427-106">Le système affiche le message d'erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="7f427-106">The system shows the following error message:</span></span>

> <span data-ttu-id="7f427-107">Le travail avec l'ID %1 n'est pas bloqué.</span><span class="sxs-lookup"><span data-stu-id="7f427-107">Work with Id %1 is not blocked.</span></span>

## <a name="cause"></a><span data-ttu-id="7f427-108">Cause</span><span class="sxs-lookup"><span data-stu-id="7f427-108">Cause</span></span>

<span data-ttu-id="7f427-109">L'option **Vague bloquée** sur la vague est définie sur *Non*.</span><span class="sxs-lookup"><span data-stu-id="7f427-109">The **Blocked wave** option on the wave is set to *No*.</span></span> <span data-ttu-id="7f427-110">Le travail ne peut pas être débloqué car il n'est actuellement pas bloqué.</span><span class="sxs-lookup"><span data-stu-id="7f427-110">The work can't be unblocked because it isn't currently blocked.</span></span>

## <a name="resolution"></a><span data-ttu-id="7f427-111">Résolution</span><span class="sxs-lookup"><span data-stu-id="7f427-111">Resolution</span></span>

 <span data-ttu-id="7f427-112">Seul un travail pour lequel l'option **Vague bloquée** est définie sur *Oui* peut être débloqué.</span><span class="sxs-lookup"><span data-stu-id="7f427-112">Only work where the **Blocked wave** option is set to *Yes* can be unblocked.</span></span>
