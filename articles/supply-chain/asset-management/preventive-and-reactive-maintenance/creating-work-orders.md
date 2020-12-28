---
title: Création d'ordres de travail
description: Cette rubrique explique comment créer des ordres de travail dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f94f8bc20753e38ce1cb6eccdfbc85c2e491ffad
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427928"
---
# <a name="creating-work-orders"></a><span data-ttu-id="930fb-103">Création d'ordres de travail</span><span class="sxs-lookup"><span data-stu-id="930fb-103">Creating work orders</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="930fb-104">Lorsque vous avez planifié des tâches de maintenance préventive, l'étape suivante consiste à créer des ordres de travail pour ces tâches.</span><span class="sxs-lookup"><span data-stu-id="930fb-104">When you have scheduled preventive maintenance jobs, next step is to create work orders for the jobs.</span></span> <span data-ttu-id="930fb-105">Cette opération peut être effectuée dans l'un des programmes de maintenance.</span><span class="sxs-lookup"><span data-stu-id="930fb-105">This is done in one of the maintenance schedules.</span></span> <span data-ttu-id="930fb-106">Les tâches prévues dans un programme de maintenance peuvent avoir des types de références différents :</span><span class="sxs-lookup"><span data-stu-id="930fb-106">The scheduled jobs in a maintenance schedule can have different reference types:</span></span>

| <span data-ttu-id="930fb-107">Type de référence</span><span class="sxs-lookup"><span data-stu-id="930fb-107">Reference type</span></span> | <span data-ttu-id="930fb-108">Description</span><span class="sxs-lookup"><span data-stu-id="930fb-108">Description</span></span>                    |
|-----------------------|------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="930fb-109">Plans de maintenance</span><span class="sxs-lookup"><span data-stu-id="930fb-109">Maintenance plans</span></span>     | <span data-ttu-id="930fb-110">Des tâches de maintenance préventive basées sur des types de plan de maintenance « Heure » ou « Compteur ».</span><span class="sxs-lookup"><span data-stu-id="930fb-110">Preventive maintenance jobs based on maintenance plan types "Time" or "Counter".</span></span>                       |
| <span data-ttu-id="930fb-111">Visites de maintenance</span><span class="sxs-lookup"><span data-stu-id="930fb-111">Maintenance rounds</span></span>    | <span data-ttu-id="930fb-112">Des tâches de maintenance préventive contenant plusieurs actifs nécessitant un type de maintenance similaire.</span><span class="sxs-lookup"><span data-stu-id="930fb-112">Preventive maintenance jobs containing several assets that require a similar type of maintenance.</span></span>           |
| <span data-ttu-id="930fb-113">Demande de maintenance</span><span class="sxs-lookup"><span data-stu-id="930fb-113">Maintenance request</span></span>   | <span data-ttu-id="930fb-114">Une demande de maintenance ou de réparation d'un actif créée manuellement, qui peut être convertie en un bon de travail.</span><span class="sxs-lookup"><span data-stu-id="930fb-114">Manually created request for maintenance or repair of an asset, which can be converted into a work order.</span></span> |


1. <span data-ttu-id="930fb-115">Cliquez sur **Gestion des actifs** > **Commun** > **Tout le programme de maintenance** ou **Ouvrir les lignes de programme de maintenance** ou **Ouvrir le regroupement de programme de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="930fb-115">Click **Asset management** > **Common** > **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools**.</span></span>

2. <span data-ttu-id="930fb-116">Sélectionnez les tâches de maintenance prévues pour lesquelles vous souhaitez créer un ordre de travail et cliquez sur **Ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="930fb-116">Select the scheduled maintenance jobs for which you want to create a work order and click **Work order**.</span></span> <span data-ttu-id="930fb-117">Dans la boîte de dialogue **Créer des ordres de travail**, le nombre total d'heures prévues pour les lignes sélectionnées s'affiche dans le champ **Heures de prévision en matière de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="930fb-117">In the **Create work orders** dialog, the total number of forecast hours for the selected lines is shown in the **Maintenance forecast hours** field.</span></span>

3. <span data-ttu-id="930fb-118">Dans la section **Paramètres**, sélectionnez le nombre d'ordres de travail qui doivent être créés.</span><span class="sxs-lookup"><span data-stu-id="930fb-118">In the **Parameters** section, select how many work orders should be created.</span></span> <span data-ttu-id="930fb-119">Vous pouvez créer un ordre de travail par ligne de programme de maintenance, ou un certain nombre d'ordres de travail en fonction de vos sélections dans la section **Un bon de travail par**.</span><span class="sxs-lookup"><span data-stu-id="930fb-119">You can create one work order per maintenance schedule line, or a number of work orders based on your selections in the **One work order per** section.</span></span>

4. <span data-ttu-id="930fb-120">Sélectionnez un **Type d'ordre de travail** qui sera utilisé dans tous les ordres de travail que vous créez.</span><span class="sxs-lookup"><span data-stu-id="930fb-120">Select a **Work order type** that will be used on all the work orders you create.</span></span> <span data-ttu-id="930fb-121">L'illustration suivante présente un exemple de la boîte de dialogue **Créer des ordres de travail**.</span><span class="sxs-lookup"><span data-stu-id="930fb-121">The illustration below shows an example of the **Create work orders** dialog.</span></span>

![Figure 1](media/18-preventive-maintenance.png)

5. <span data-ttu-id="930fb-123">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="930fb-123">Click **OK**.</span></span> <span data-ttu-id="930fb-124">Un ou plusieurs ordres de travail sont alors créés.</span><span class="sxs-lookup"><span data-stu-id="930fb-124">One or more work orders are created.</span></span>

