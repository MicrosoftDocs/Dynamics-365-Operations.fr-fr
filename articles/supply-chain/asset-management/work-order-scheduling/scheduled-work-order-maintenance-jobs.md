---
title: Tâches de maintenance de l'ordre de travail planifiées
description: Cette rubrique explique les tâches de maintenance de l'ordre de travail planifiées dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4b3cc32d6ff263967c1ee843702c28968219ac33
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887180"
---
# <a name="scheduled-work-order-maintenance-jobs"></a><span data-ttu-id="c9f92-103">Tâches de maintenance de l'ordre de travail planifiées</span><span class="sxs-lookup"><span data-stu-id="c9f92-103">Scheduled work order maintenance jobs</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="c9f92-104">La page **Tâches de maintenance de l'ordre de travail planifiées** permet d'obtenir une vue d'ensemble des ordres de travail affectés à une ressource.</span><span class="sxs-lookup"><span data-stu-id="c9f92-104">The **Scheduled work order maintenance jobs** page is used to get an overview of the work orders allocated to a resource.</span></span> <span data-ttu-id="c9f92-105">Les ordres de travail qui utilisent les ressources de type « Ressources humaines » , « Outil » et « Ordinateur » sont affichés dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c9f92-105">Work orders using resource types "Human resources", "Tool", and "Machine" are shown in the list.</span></span> <span data-ttu-id="c9f92-106">La liste permet d'obtenir une vue d'ensemble des ordres de travail alloués à une ressource spécifique.</span><span class="sxs-lookup"><span data-stu-id="c9f92-106">The list can be used to get an overview of work orders allocated to a specific resource.</span></span> <span data-ttu-id="c9f92-107">Vous pouvez également l'utiliser pour trouver rapidement un ordre de travail affecté à un agent de maintenance qui, par exemple, était malade ce matin, et affecter rapidement un autre agent de maintenance à la tâche.</span><span class="sxs-lookup"><span data-stu-id="c9f92-107">You can also use it to quickly find a work order allocated to a maintenance worker who, for example, called in sick this morning, and then quickly allocate another maintenance worker to the job.</span></span>

## <a name="view-scheduled-work-order-maintenance-jobs"></a><span data-ttu-id="c9f92-108">Afficher les tâches de maintenance de l'ordre de travail planifiées</span><span class="sxs-lookup"><span data-stu-id="c9f92-108">View scheduled work order maintenance jobs</span></span>

1. <span data-ttu-id="c9f92-109">Cliquez sur **Gestion des actifs** > **Commun** > **Ordres de travail** > **Tâches de maintenance de l'ordre de travail planifiées**.</span><span class="sxs-lookup"><span data-stu-id="c9f92-109">Click **Asset management** > **Common** > **Work orders** > **Scheduled work order maintenance jobs**.</span></span> <span data-ttu-id="c9f92-110">Vous voyez une liste de tous les ordres de travail définis sur l'état du cycle de vie « Planifié » ou « En cours ».</span><span class="sxs-lookup"><span data-stu-id="c9f92-110">You see a list of all work orders set to work order lifecycle state "Scheduled" or "In progress".</span></span>

2. <span data-ttu-id="c9f92-111">Vous pouvez trier la liste, par exemple, par agent de maintenance.</span><span class="sxs-lookup"><span data-stu-id="c9f92-111">You can sort the list, for example, by maintenance worker.</span></span> <span data-ttu-id="c9f92-112">Vous pouvez également utiliser le filtre pour limiter la liste pour afficher les ordres de travail alloués à une ressource ou à un agent de maintenance spécifique.</span><span class="sxs-lookup"><span data-stu-id="c9f92-112">You can also use the filter to limit the list to display work orders allocated to a specific resource or maintenance worker.</span></span>

3. <span data-ttu-id="c9f92-113">Vous pouvez voir des notes sur l'ordre de travail et, le cas échéant, ajouter de nouvelles notes en sélectionnant la tâche de l'ordre de travail dans la liste et en cliquant sur **Notes**.</span><span class="sxs-lookup"><span data-stu-id="c9f92-113">You can see notes on the work order and, if required, add new notes by selecting the work order job in the list and clicking **Notes**.</span></span>

4. <span data-ttu-id="c9f92-114">Si vous souhaitez affecter un agent de maintenance à un ordre de travail, sélectionnez l'ordre de travail dans la liste, puis cliquez sur **Ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="c9f92-114">If you want to allocate one maintenance worker to a work order, select the work order in the list, and click **Work order**.</span></span>

5. <span data-ttu-id="c9f92-115">La page **Ordre de travail** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="c9f92-115">The **Work order** page opens.</span></span> <span data-ttu-id="c9f92-116">Cliquez sur **Répartir** pour planifier l'ordre de travail à un agent de maintenance spécifique.</span><span class="sxs-lookup"><span data-stu-id="c9f92-116">Click **Dispatch** to schedule the work order to a specific maintenance worker.</span></span>

>[!NOTE]
><span data-ttu-id="c9f92-117">Découvrez-en davantage sur la planification de plusieurs ordres de travail ou d'un ordre de travail dans [Planifier les ordres de travail](../work-order-scheduling/schedule-work-orders.md) et [Répartir l'ordre de travail](../work-order-scheduling/dispatch-work-order.md).</span><span class="sxs-lookup"><span data-stu-id="c9f92-117">Read more about scheduling several work orders or one work order in [Schedule work orders](../work-order-scheduling/schedule-work-orders.md) and [Dispatch work order](../work-order-scheduling/dispatch-work-order.md).</span></span>

<span data-ttu-id="c9f92-118">La figure ci-dessous présente un exemple de la page **Tâches de maintenance de l'ordre de travail planifiées**.</span><span class="sxs-lookup"><span data-stu-id="c9f92-118">The figure below shows an example of the **Scheduled work order maintenance jobs** page.</span></span>

![Figure 1](media/07-work-order-scheduling.png)

