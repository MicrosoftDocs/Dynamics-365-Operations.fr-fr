---
title: L’ordre de fabrication prévisionnel doit être planifié avant de pouvoir être confirmé
description: Lorsque vous essayez de confirmer une commande planifiée, vous recevez un message d’erreur indiquant que la commande doit être planifiée avant de pouvoir être confirmée.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a360cb3cbd26e1bc1ebb1baf1a6a4d8282c28c5c
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294078"
---
# <a name="planned-production-order-must-be-scheduled-before-it-can-be-firmed"></a><span data-ttu-id="d0ffe-103">L’ordre de fabrication prévisionnel doit être planifié avant de pouvoir être confirmé</span><span class="sxs-lookup"><span data-stu-id="d0ffe-103">Planned production order must be scheduled before it can be firmed</span></span>

<span data-ttu-id="d0ffe-104">Code d’erreur : SYS309802</span><span class="sxs-lookup"><span data-stu-id="d0ffe-104">Error code: SYS309802</span></span>

## <a name="symptoms"></a><span data-ttu-id="d0ffe-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="d0ffe-105">Symptoms</span></span>

<span data-ttu-id="d0ffe-106">Lorsque vous essayez de confirmer une commande planifiée, vous recevez le message d’erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="d0ffe-106">When you try to firm a planned order, you receive the following error message:</span></span>

> <span data-ttu-id="d0ffe-107">L’ordre de fabrication prévisionnel doit être planifié avant de pouvoir être confirmé.</span><span class="sxs-lookup"><span data-stu-id="d0ffe-107">The planned production order must be scheduled before it can be firmed.</span></span>

## <a name="cause"></a><span data-ttu-id="d0ffe-108">Cause</span><span class="sxs-lookup"><span data-stu-id="d0ffe-108">Cause</span></span>

<span data-ttu-id="d0ffe-109">Les dates de début et de fin planifiées ne peuvent pas être vides.</span><span class="sxs-lookup"><span data-stu-id="d0ffe-109">The scheduled start and end dates can't be blank.</span></span>

## <a name="resolution"></a><span data-ttu-id="d0ffe-110">Résolution</span><span class="sxs-lookup"><span data-stu-id="d0ffe-110">Resolution</span></span>

<span data-ttu-id="d0ffe-111">Pour spécifier les dates de début et de fin de la commande planifiée, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d0ffe-111">To specify start and end dates for the planned order, follow these steps.</span></span>

1. <span data-ttu-id="d0ffe-112">Accédez à **Planification \> Planification \> Ordres prévisionnels**.</span><span class="sxs-lookup"><span data-stu-id="d0ffe-112">Go to **Master planning \> Master planning \> Planned orders**.</span></span>
1. <span data-ttu-id="d0ffe-113">Ouvrez la commande planifiée concernée.</span><span class="sxs-lookup"><span data-stu-id="d0ffe-113">Open the relevant planned order.</span></span>
1. <span data-ttu-id="d0ffe-114">Dans le raccourci **Général**, dans la section **Planifié**, précisez les dates dans les champs **Date de début** et **Date de fin**.</span><span class="sxs-lookup"><span data-stu-id="d0ffe-114">On the **General** FastTab, in the **Scheduled** section, specify dates in the **Start date** and **End date** fields.</span></span>
