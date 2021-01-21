---
title: Résoudre les problèmes de réapprovisionnement de l’entrepôt
description: Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors du travail de réapprovisionnement en entrepôts dans Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: e4d87e85520c2b6f2346fddf3b985d4e17fe35cb
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644871"
---
# <a name="troubleshoot-warehouse-replenishment"></a><span data-ttu-id="43199-103">Résoudre les problèmes de réapprovisionnement de l’entrepôt</span><span class="sxs-lookup"><span data-stu-id="43199-103">Troubleshoot warehouse replenishment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="43199-104">Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors du travail de réapprovisionnement en entrepôts dans Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="43199-104">This topic describes how to fix common issues that you might encounter while you work with warehouse replenishment in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-work-1-cannot-be-unblocked-because-it-has-unfinished-replenishment-work"></a><span data-ttu-id="43199-105">Je reçois le message d’erreur suivant : « Le travail %1 ne peut pas être débloqué, car le travail de réapprovisionnement n’est pas terminé. »</span><span class="sxs-lookup"><span data-stu-id="43199-105">I receive the following error message: "Work %1 cannot be unblocked because it has unfinished replenishment work."</span></span>

### <a name="issue-description"></a><span data-ttu-id="43199-106">Description du problème</span><span class="sxs-lookup"><span data-stu-id="43199-106">Issue description</span></span>

<span data-ttu-id="43199-107">Le travail de prélèvement est bloqué en raison du travail de réapprovisionnement dépendant.</span><span class="sxs-lookup"><span data-stu-id="43199-107">Picking work is blocked because of dependent replenishment work.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="43199-108">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="43199-108">Issue resolution</span></span>

<span data-ttu-id="43199-109">Lorsque vous utilisez le réapprovisionnement de la demande de vague, si un site de prélèvement doit être réapprovisionné pour répondre à la demande de commande d'origine, le système crée à la fois le travail de réapprovisionnement et le travail de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="43199-109">When you use wave demand replenishment, if a picking location must be replenished to fulfill the source order demand, the system creates both the replenishment work and the picking work.</span></span> <span data-ttu-id="43199-110">Cependant, il bloque le travail de prélèvement jusqu'à ce que le travail de réapprovisionnement soit terminé.</span><span class="sxs-lookup"><span data-stu-id="43199-110">However, it blocks the picking work until the replenishment work is completed.</span></span> <span data-ttu-id="43199-111">Ce comportement est intentionnel, car l'emplacement de prélèvement n'aura pas suffisamment de stock tant que le travail de réapprovisionnement n'est pas terminé.</span><span class="sxs-lookup"><span data-stu-id="43199-111">This behavior is intentional, because the picking location won't have enough inventory unless the replenishment work is completed.</span></span> <span data-ttu-id="43199-112">Terminez le travail de réapprovisionnement, puis traitez le travail de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="43199-112">Complete the replenishment work, and then process the picking work.</span></span>