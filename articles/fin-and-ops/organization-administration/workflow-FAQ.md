---
title: FAQ Workflow
description: Cette rubrique répond à des questions fréquentes sur le système de workflow dans Microsoft Dynamics 365 for Finance and Operations.
author: ChrisGarty
manager: AnnBe
ms.date: 05/07/2019
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
ms.openlocfilehash: f6240b1b5136937aa47f455547fed6f0c7c08e2c
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1509289"
---
# <a name="workflow-system"></a><span data-ttu-id="64e55-103">Système de workflow</span><span class="sxs-lookup"><span data-stu-id="64e55-103">Workflow system</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="64e55-104">Cette rubrique répond à des questions fréquentes sur le système de workflow dans Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="64e55-104">This topic answers frequently asked questions about the workflow system in Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="notifications"></a><span data-ttu-id="64e55-105">Notifications</span><span class="sxs-lookup"><span data-stu-id="64e55-105">Notifications</span></span>

### <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a><span data-ttu-id="64e55-106">Pourquoi plusieurs notifications sont-elles reçues lorsqu'un élément de travail est rejeté ?</span><span class="sxs-lookup"><span data-stu-id="64e55-106">Why are multiple notifications received when a work item is rejected?</span></span>
<span data-ttu-id="64e55-107">Lors du rejet d'un élément de travail, ce dernier est défini comme rejeté.</span><span class="sxs-lookup"><span data-stu-id="64e55-107">When a work item is rejected, that work item is completed as rejected.</span></span> <span data-ttu-id="64e55-108">Un autre élément de travail est créé et attribué à l'expéditeur.</span><span class="sxs-lookup"><span data-stu-id="64e55-108">Another work item is created and assigned to the originator.</span></span> <span data-ttu-id="64e55-109">Autrement dit, une notification est envoyée à l'expéditeur concernant le rejet de l'élément de travail et une notification distincte est envoyée à l'utilisateur assigné au nouvel élément de travail « Modification requise ».</span><span class="sxs-lookup"><span data-stu-id="64e55-109">This means that there is a notification to the originator for the rejected work item, and a separate notification to the user assigned to the new "change requested" work item.</span></span> 

<span data-ttu-id="64e55-110">Chaque notification correspond à un élément de travail différent, mais la similarité peut générer une confusion.</span><span class="sxs-lookup"><span data-stu-id="64e55-110">Each notification is for a different work item, but the similarity can cause confusion.</span></span> <span data-ttu-id="64e55-111">Nous étudions des façons d'améliorer cela dans une prochaine version.</span><span class="sxs-lookup"><span data-stu-id="64e55-111">We are looking at ways to improve this in a future release.</span></span>

### <a name="why-are-my-workflow-exports-failing"></a><span data-ttu-id="64e55-112">Pourquoi mes exportations de workflows échouent-elles ?</span><span class="sxs-lookup"><span data-stu-id="64e55-112">Why are my workflow exports failing?</span></span>
<span data-ttu-id="64e55-113">Il existe actuellement une limitation de la fonctionnalité d'exportation de workflows qui empêche les noms des workflows de dépasser 48 caractères.</span><span class="sxs-lookup"><span data-stu-id="64e55-113">There is currently a limitation in the workflow export feature that prevents workflow names from exceeding 48 characters.</span></span> <span data-ttu-id="64e55-114">L'utilisation d'un nom de plus de 48 caractères peut entraîner une erreur « Échec du serveur à authentifier la demande » et/ou pour empêcher qu'un fichier soit exporté sans type de fichier.</span><span class="sxs-lookup"><span data-stu-id="64e55-114">Using a name that is longer than 48 characters can result in a "Server failed to authenticate the request" error and/or prevent a file to be exported  without a file type.</span></span> <span data-ttu-id="64e55-115">La publication de blog suivante fournit davantage de détails [Dépannage de l'exportation de workflows](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="64e55-115">The following blog post provides more details [Workflow Export Troubleshooting](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).</span></span>
