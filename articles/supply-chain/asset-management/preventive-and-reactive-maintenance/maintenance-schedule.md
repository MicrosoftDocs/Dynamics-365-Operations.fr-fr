---
title: Programme de maintenance
description: Cette rubrique explique le programme de maintenance dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
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
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 780b633af04c38705f8321d19924f3802b2d5c67
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875651"
---
# <a name="maintenance-schedule"></a><span data-ttu-id="41b57-103">Programme de maintenance</span><span class="sxs-lookup"><span data-stu-id="41b57-103">Maintenance schedule</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="41b57-104">Le programme de maintenance contient une liste de tous les plans de maintenance préventive prévus, des demandes de maintenance et des visites de maintenance à effectuer. Quelques lignes de programme peuvent avoir été converties en ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="41b57-104">The maintenance schedule contains a list of all the expected preventive maintenance plans, maintenance requests, and maintenance rounds to be carried out. Some schedule lines may have been converted to work orders.</span></span>

<span data-ttu-id="41b57-105">Les quatre vues du programme de maintenance sont légèrement différentes, selon les lignes du programme de maintenance que vous souhaitez voir.</span><span class="sxs-lookup"><span data-stu-id="41b57-105">The four maintenance schedule views are slightly different, depending on which maintenance schedule lines you want to see.</span></span>

| <span data-ttu-id="41b57-106">Option de menu</span><span class="sxs-lookup"><span data-stu-id="41b57-106">Menu item</span></span>                  | <span data-ttu-id="41b57-107">Description du contenu</span><span class="sxs-lookup"><span data-stu-id="41b57-107">Description of contents</span></span>                                                                                                                                             |
|----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="41b57-108">Tout le programme de maintenance</span><span class="sxs-lookup"><span data-stu-id="41b57-108">All maintenance schedule</span></span>       | <span data-ttu-id="41b57-109">Toutes les lignes du programme de maintenance sont affichées.</span><span class="sxs-lookup"><span data-stu-id="41b57-109">All maintenance schedule lines are shown.</span></span>     |
| <span data-ttu-id="41b57-110">Mon programme d'actifs</span><span class="sxs-lookup"><span data-stu-id="41b57-110">My asset schedule</span></span>        | <span data-ttu-id="41b57-111">Toutes les lignes du programme de maintenance contenant les actifs installés sur les postes techniques auxquels vous êtes associé en tant qu'agent (configuré dans [Groupes d'agents et agents de maintenance](../setup-for-objects/workers-and-worker-groups.md)) sont affichées dans cette liste.</span><span class="sxs-lookup"><span data-stu-id="41b57-111">All maintenance schedule lines containing assets installed on functional locations to which you are related as a worker (set up in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md)) are shown in this list.</span></span> |
| <span data-ttu-id="41b57-112">Ouvrir des lignes du programme de maintenance</span><span class="sxs-lookup"><span data-stu-id="41b57-112">Open maintenance schedule lines</span></span> | <span data-ttu-id="41b57-113">Les lignes du programme de maintenance avec le statut « Créé », signifiant qu'elles n'ont pas encore été converties en ordre de travail ou qu'elles ont été ignorées, sont affichées dans cette ligne.</span><span class="sxs-lookup"><span data-stu-id="41b57-113">Maintenance schedule lines with status "Created" - meaning they have not yet been converted to a work order or discarded - are shown in this list.</span></span>                                            |
| <span data-ttu-id="41b57-114">Ouvrir les regroupements de programmes de maintenance</span><span class="sxs-lookup"><span data-stu-id="41b57-114">Open maintenance schedule pools</span></span> | <span data-ttu-id="41b57-115">Les lignes du programme de maintenance associées à un regroupement d'ordres de travail sont affichées dans cette liste.</span><span class="sxs-lookup"><span data-stu-id="41b57-115">Maintenance schedule lines related to a work order pool are shown in this list.</span></span>                                                                                                                  |

>[!NOTE]
><span data-ttu-id="41b57-116">Si une ligne du programme de maintenance est incluse dans plusieurs regroupements d'ordres de travail (consultez [Regroupements des ordres de travail](../work-orders/work-order-pools.md)), un enregistrement est indiqué pour chaque regroupement dans **Ouvrir les regroupements du programme de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="41b57-116">If a maintenance schedule line is included in several work order pools (refer to [Work order pools](../work-orders/work-order-pools.md)), one record is shown for each pool in **Open maintenance schedule pools**.</span></span> <span data-ttu-id="41b57-117">Cela permet d'optimiser les options de filtrage sur les regroupements des ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="41b57-117">This is done to optimize filtering options on work order pools.</span></span>

<span data-ttu-id="41b57-118">Pour ouvrir un programme de maintenance :</span><span class="sxs-lookup"><span data-stu-id="41b57-118">To open a maintenance schedule:</span></span>

1. <span data-ttu-id="41b57-119">Cliquez sur **Gestion des actifs** > **Commun** > **Programme de maintenance** > **Tout le programme de maintenance** ou **Ouvrir les lignes de programme de maintenance** ou **Ouvrir le regroupement de programme de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="41b57-119">Click **Asset management** > **Common** > **Maintenance schedule** > **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools**.</span></span>

2. <span data-ttu-id="41b57-120">Pour mettre le programme de maintenance à jour, cliquez sur **Plan de maintenance** ou **Visites de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="41b57-120">To update the maintenance schedule, click **Maintenance plan** or **Maintenance rounds**.</span></span> 

3. <span data-ttu-id="41b57-121">Vous pouvez modifier une ligne du programme de mise à jour en la sélectionnant et en cliquant sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="41b57-121">You can edit a maintenance schedule line by selecting it and clicking **Edit**.</span></span> <span data-ttu-id="41b57-122">Par exemple, vous pouvez facilement mettre à jour le niveau de service ou l'agent responsable de la tâche.</span><span class="sxs-lookup"><span data-stu-id="41b57-122">For example, you can easily update the service level or the worker responsible for the job.</span></span> <span data-ttu-id="41b57-123">Vous pouvez modifier uniquement les lignes du programme de maintenance qui n'ont pas encore été connectées à un ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="41b57-123">You can only edit maintenance schedule lines that have not yet been connected to a work order.</span></span>

4. <span data-ttu-id="41b57-124">Vous pouvez supprimer une ligne du programme de maintenance en la sélectionnant dans la page de liste et en cliquant sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="41b57-124">You can delete a maintenance schedule line by selecting it in the list page and clicking **Delete**.</span></span>

5. <span data-ttu-id="41b57-125">Vous pouvez ignorer une ligne du programme de maintenance en la sélectionnant dans la page de liste et en cliquant sur **Ignorer**.</span><span class="sxs-lookup"><span data-stu-id="41b57-125">You can discard a maintenance schedule line by selecting it in the list page and clicking **Discard**.</span></span> <span data-ttu-id="41b57-126">Cette fonction est utile, par exemple, un actif a un plan de maintenance de 2 000 km et un plan de maintenance de 10 000 km.</span><span class="sxs-lookup"><span data-stu-id="41b57-126">This function is useful if, for example, an asset has a 2,000 km maintenance plan and a 10,000 km maintenance plan.</span></span> <span data-ttu-id="41b57-127">Puis, vous pouvez ignorer la ligne créée depuis le plan de maintenance de 2 000 km lorsque cela coïncide avec 10 000 km, 20 000 km, 30 000 km, etc.</span><span class="sxs-lookup"><span data-stu-id="41b57-127">Then, you may want to discard the line created from the 2,000 km maintenance plan when it coincides with 10,000 km, 20,000 km, 30,000 km, and so on.</span></span> <span data-ttu-id="41b57-128">Si vous ignorez une ligne du programme de maintenance associée à un plan de maintenance, cette ligne n'apparaîtra jamais une fois le plan de maintenance planifié.</span><span class="sxs-lookup"><span data-stu-id="41b57-128">If you discard a maintenance schedule line related to a maintenance plan, that line will never again appear when that maintenance plan is scheduled.</span></span>

6. <span data-ttu-id="41b57-129">Vous pouvez sélectionner plusieurs lignes du programme de maintenance dans **Tout le programme de maintenance** et cliquez sur **Regroupement des ordres de travail**, si vous souhaitez que toutes les lignes sélectionnées soient incluses dans le même regroupement des ordres de travail.</span><span class="sxs-lookup"><span data-stu-id="41b57-129">You can select a number of maintenance schedule lines in **All maintenance schedule** and click **Work order pool**, if you want all selected lines to be included in the same work order pool.</span></span>

7. <span data-ttu-id="41b57-130">Vous pouvez sélectionner plusieurs lignes du programme de maintenance dans **Tout le programme de maintenance** ou **Ouvrir les lignes du programme de maintenance** ou **Ouvrir les regroupements de programmes de maintenance** et cliquez sur **Ajuster un programme** si vous souhaitez apporter les mêmes ajustements à plusieurs lignes.</span><span class="sxs-lookup"><span data-stu-id="41b57-130">You can select a number of maintenance schedule lines in **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools** and click **Adjust schedule** if you want to make the same adjustments on several lines.</span></span> <span data-ttu-id="41b57-131">Vous pouvez modifier les dates de début et de fin prévues, le niveau de service, et le groupe d'agents de maintenance responsable ou l'agent de maintenance responsable associé aux lignes du programme de maintenance sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="41b57-131">You can change expected start and end dates, service level, and the responsible maintenance worker group or responsible maintenance worker related to the selected maintenance schedule lines.</span></span>

- <span data-ttu-id="41b57-132">Lorsqu'une ligne du programme de maintenance a été associée à un ordre de travail, l'ID de l'ordre de travail sera affiché dans le champ **Ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="41b57-132">When a maintenance schedule line has been related to a work order, the work order ID will be displayed in the **Work order** field.</span></span>  
- <span data-ttu-id="41b57-133">Dans la vue détaillée **Tous les actifs** > organisateur **Plans de maintenance des actifs**, vous pouvez sélectionner les plans de maintenance pour l'actif.</span><span class="sxs-lookup"><span data-stu-id="41b57-133">In **All assets** details view > **Asset maintenance plans** FastTab, you can select maintenance plans for the asset.</span></span> <span data-ttu-id="41b57-134">Ultérieurement, si vous supprimez une ligne de plan de maintenance ou une visite de maintenance à un actif dans **Tous les actifs**, vous supprimez également automatiquement toutes les lignes du programme de maintenance avec le statut « Créé » ayant été créés en fonction de ce plan de maintenance ou de cette visite de maintenance.</span><span class="sxs-lookup"><span data-stu-id="41b57-134">Later, if you delete a maintenance plan line related to an asset in **All assets**, you also automatically delete all maintenance schedule lines with status "Created" that have been created based on that maintenance plan.</span></span> <span data-ttu-id="41b57-135">Consultez également [Créer un actif](../objects/create-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="41b57-135">See also [Create an asset](../objects/create-an-object.md).</span></span>

<span data-ttu-id="41b57-136">L'illustration ci-dessous présente la page de liste **Tout le programme de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="41b57-136">The figure below shows the **All maintenance schedule** list page.</span></span>

![Figure 1](media/16-preventive-maintenance.png)

