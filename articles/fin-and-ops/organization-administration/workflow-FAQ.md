---
title: FAQ Workflow
description: Cette rubrique répond à des questions fréquentes sur le système de workflow dans Microsoft Dynamics 365 for Finance and Operations.
author: ChrisGarty
manager: AnnBe
ms.date: 02/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f058a450eb18e688efbc5306a42b4efef6aa91e7
ms.sourcegitcommit: 9a723737565ac78c884e40f7129d0f5aad747524
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/01/2019
ms.locfileid: "773209"
---
# <a name="workflow-system"></a><span data-ttu-id="571c3-103">Système de workflow</span><span class="sxs-lookup"><span data-stu-id="571c3-103">Workflow system</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="571c3-104">Cette rubrique répond à des questions fréquentes sur le système de workflow dans Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="571c3-104">This topic answers frequently asked questions about the workflow system in Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="notifications"></a><span data-ttu-id="571c3-105">Notifications</span><span class="sxs-lookup"><span data-stu-id="571c3-105">Notifications</span></span>

### <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a><span data-ttu-id="571c3-106">Pourquoi plusieurs notifications sont-elles reçues lorsqu'un élément de travail est rejeté ?</span><span class="sxs-lookup"><span data-stu-id="571c3-106">Why are multiple notifications received when a work item is rejected?</span></span>
<span data-ttu-id="571c3-107">Lors du rejet d'un élément de travail, ce dernier est défini comme rejeté.</span><span class="sxs-lookup"><span data-stu-id="571c3-107">When a work item is rejected, that work item is completed as rejected.</span></span> <span data-ttu-id="571c3-108">Un autre élément de travail est créé et attribué à l'expéditeur.</span><span class="sxs-lookup"><span data-stu-id="571c3-108">Another work item is created and assigned to the originator.</span></span> <span data-ttu-id="571c3-109">Autrement dit, une notification est envoyée à l'expéditeur concernant le rejet de l'élément de travail et une notification distincte est envoyée à l'utilisateur assigné au nouvel élément de travail « Modification requise ».</span><span class="sxs-lookup"><span data-stu-id="571c3-109">This means that there is a notification to the originator for the rejected work item, and a separate notification to the user assigned to the new "change requested" work item.</span></span> 

<span data-ttu-id="571c3-110">Chaque notification correspond à un élément de travail différent, mais la similarité peut générer une confusion.</span><span class="sxs-lookup"><span data-stu-id="571c3-110">Each notification is for a different work item, but the similarity can cause confusion.</span></span> <span data-ttu-id="571c3-111">Nous étudions des façons d'améliorer cela dans une prochaine version.</span><span class="sxs-lookup"><span data-stu-id="571c3-111">We are looking at ways to improve this in a future release.</span></span>
