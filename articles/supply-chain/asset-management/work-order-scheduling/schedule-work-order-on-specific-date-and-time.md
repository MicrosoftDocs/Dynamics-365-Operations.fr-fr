---
title: Planifier un ordre de travail à une date et une heure spécifiques
description: Cette rubrique explique comment planifier un ordre de travail à une date et une heure spécifiques dans le module Gestion des actifs.
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
ms.openlocfilehash: 0f818c4c3b669cc94e37cba1e3571c57b5c0dd1b
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887363"
---
# <a name="schedule-work-order-on-specific-date-and-time"></a><span data-ttu-id="3bc98-103">Planifier un ordre de travail à une date et une heure spécifiques</span><span class="sxs-lookup"><span data-stu-id="3bc98-103">Schedule work order on specific date and time</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="3bc98-104">Si un ordre de travail doit être programmé à une date *et* à une heure spécifiques, vous pouvez remplacer le processus de planification standard dans le module Gestion des actifs et créer un programme spécifique pour un ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="3bc98-104">If a work order must be scheduled on a specific date *and* time, you can override the standard scheduling process in Asset Management and create a specific schedule for a work order.</span></span>

1. <span data-ttu-id="3bc98-105">Cliquez sur **Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**.</span><span class="sxs-lookup"><span data-stu-id="3bc98-105">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="3bc98-106">Dans la liste des ordres de travail, cliquez sur l'ID de l'ordre de travail dans la colonne **Ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="3bc98-106">In the work order list, click on the Work order ID in the **Work order** column.</span></span>

3. <span data-ttu-id="3bc98-107">Cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="3bc98-107">Click **Edit**.</span></span>

4. <span data-ttu-id="3bc98-108">Dans l'organisateur **En-tête de l'ordre de travail**, saisissez les dates et heures de début et de fin dans les champs **Début prévu** et **Fin prévue**.</span><span class="sxs-lookup"><span data-stu-id="3bc98-108">On the **Work order header** FastTab, insert start and end dates and times in the **Expected start** and **Expected end** fields.</span></span>

![Figure 1](media/05-work-order-scheduling.png)

5. <span data-ttu-id="3bc98-110">Dans l'onglet **Général**, cliquez sur **Planifier** pour utiliser le processus de planification standard, ou cliquez sur **Répartir** si vous souhaitez planifier l'ordre de travail à un agent spécifique.</span><span class="sxs-lookup"><span data-stu-id="3bc98-110">On the **General** tab, click **Schedule** to use the standard scheduling process, or click **Dispatch** if you want to schedule the work order to a specific worker.</span></span>

6. <span data-ttu-id="3bc98-111">Afin de remplacer les réservations de capacité existantes pour vous assurer que l'ordre de travail est planifié dans la période prévue, effectuez vos sélections comme illustré sur la figure ci-dessous dans la boîte de dialogue **Planifier un ordre de travail** > section **Capacité finie**.</span><span class="sxs-lookup"><span data-stu-id="3bc98-111">In order to override any existing capacity reservations to ensure that the work order is scheduled in the expected period, make the selections as shown in the figure below in the **Schedule work order** dialog > **Finite capacity** section.</span></span> <span data-ttu-id="3bc98-112">Cela signifie que le processus de planification ignorera les réservations de capacité existantes, car l'ordre de travail doit démarrer à l'heure de début prévue.</span><span class="sxs-lookup"><span data-stu-id="3bc98-112">This means that the scheduling process will ignore existing capacity reservations because the work order must start on the expected start time.</span></span>

![Figure 2](media/06-work-order-scheduling.png)

7. <span data-ttu-id="3bc98-114">Cliquez sur **OK** pour démarrer la planification.</span><span class="sxs-lookup"><span data-stu-id="3bc98-114">Click **OK** to start scheduling.</span></span>

8. <span data-ttu-id="3bc98-115">Si le processus de planification génère un doublon en matière de réservation, un message apparaît à l'écran, et vous pouvez ajuster les ordres de travail associés.</span><span class="sxs-lookup"><span data-stu-id="3bc98-115">If the scheduling process results in double bookings, you will see a message on the screen, and you can adjust the related work orders.</span></span>

>[!NOTE]
><span data-ttu-id="3bc98-116">Afin de planifier un agent de maintenance pour l'ordre de travail, cet agent de maintenance doit être disponible aux dates de début et de fin prévues.</span><span class="sxs-lookup"><span data-stu-id="3bc98-116">In order to schedule a maintenance worker for the work order, that maintenance worker must be available at the expected start date and time.</span></span> <span data-ttu-id="3bc98-117">La disponibilité de l'agent est paramétrée dans [calendrier de l'agent](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md).</span><span class="sxs-lookup"><span data-stu-id="3bc98-117">Worker availability is set up in the [worker calendar](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md).</span></span> 

