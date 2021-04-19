---
title: Programmer un ordre de fabrication
description: Cette procédure indique comment planifier un ordre de fabrication.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdSchedule, ProdRouteJob, WrkCtrCapResSum, ProdRouteJobSched, ProductionOrderScheduleDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0a52e2ee3bf0c5dadeda375882d16de60b31d658
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831888"
---
# <a name="schedule-a-production-order"></a><span data-ttu-id="f6a5e-103">Programmer un ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="f6a5e-103">Schedule a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f6a5e-104">Cette procédure indique comment planifier un ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-104">This procedure shows how to schedule a production order.</span></span> <span data-ttu-id="f6a5e-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="f6a5e-106">Il s’agit de la troisième des sept procédures expliquant le cycle de vie de l’ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-106">This is the third procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="schedule-a-production-order"></a><span data-ttu-id="f6a5e-107">Programmer un ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="f6a5e-107">Schedule a production order</span></span>
1. <span data-ttu-id="f6a5e-108">Accédez à Contrôle de la production > Ordres de fabrication > Tous les ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="f6a5e-109">Sélectionnez un ordre de fabrication ayant le statut Estimé.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-109">Select a production order that has the Estimated status.</span></span>  
2. <span data-ttu-id="f6a5e-110">Dans le volet Actions, cliquez sur Planification.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-110">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="f6a5e-111">Cliquez sur Planifier les tâches.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-111">Click Schedule jobs.</span></span>
    * <span data-ttu-id="f6a5e-112">Les paramètres de planification sont configurés sur cette page.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-112">The parameters for scheduling are set up on this page.</span></span> <span data-ttu-id="f6a5e-113">Vous pouvez configurer les paramètres pour des utilisateurs spécifiques ou pour tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-113">You can set up the parameters for specific users or all users.</span></span>  
4. <span data-ttu-id="f6a5e-114">Dans le champ Direction de la planification, sélectionnez « En avant à partir d’aujourd’hui ».</span><span class="sxs-lookup"><span data-stu-id="f6a5e-114">In the Scheduling direction field, select 'Forward from today'.</span></span>
5. <span data-ttu-id="f6a5e-115">Dans le champ Date de planification, entrez une date.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-115">In the Scheduling date field, enter a date.</span></span>
6. <span data-ttu-id="f6a5e-116">Cochez ou décochez la case Capacité finie.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-116">Select or clear the Finite capacity check box.</span></span>
7. <span data-ttu-id="f6a5e-117">Cochez ou décochez la case Matières limitées.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-117">Select or clear the Finite material check box.</span></span>
8. <span data-ttu-id="f6a5e-118">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-118">Click OK.</span></span>

## <a name="view-the-scheduling-results"></a><span data-ttu-id="f6a5e-119">Afficher les résultats de la planification</span><span class="sxs-lookup"><span data-stu-id="f6a5e-119">View the scheduling results</span></span>
1. <span data-ttu-id="f6a5e-120">Cliquez sur Ordre de fabrication dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-120">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="f6a5e-121">Cliquez sur Toutes les tâches.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-121">Click All jobs.</span></span>
    * <span data-ttu-id="f6a5e-122">Cette page affiche les tâches planifiées que vous venez de générer.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-122">This page displays the scheduled jobs that you have just generated.</span></span>  
3. <span data-ttu-id="f6a5e-123">Développez ou réduisez la section Planification.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-123">Expand or collapse the Scheduling section.</span></span>
    * <span data-ttu-id="f6a5e-124">Dans l’organisateur Planification, vous pouvez afficher la date et l’heure planifiées.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-124">On the Scheduling FastTab, you can view the scheduled date and time.</span></span>  
4. <span data-ttu-id="f6a5e-125">Cliquez sur Recherches.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-125">Click Inquiries.</span></span>
5. <span data-ttu-id="f6a5e-126">Cliquez sur Charge de la capacité.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-126">Click Capacity load.</span></span>
    * <span data-ttu-id="f6a5e-127">La page Charge de la capacité affiche la capacité réservée via la planification des tâches, le nombre total d’heures qui sont actuellement réservées pour la ressource, et le nombre d’heures encore disponibles pour la planification des tâches de la ressource.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-127">The Capacity load page displays the capacity that is reserved through job scheduling, the total number of hours that are currently reserved on the resource, and the number of hours that remain available for job scheduling on the resource.</span></span>  
6. <span data-ttu-id="f6a5e-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-128">Close the page.</span></span>
7. <span data-ttu-id="f6a5e-129">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-129">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]