---
title: Description et niveau de service
description: Cette rubrique explique le niveau de service et la description dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectServiceLevel, EntAssetWorkOrderStandardDescription, EntAssetWorkOrderServiceLevel, EntAssetServiceLevelLookup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8bb56e5103bd9e18e88c164cd308e55d48e64823
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019377"
---
# <a name="service-level-and-description"></a><span data-ttu-id="63358-103">Description et niveau de service</span><span class="sxs-lookup"><span data-stu-id="63358-103">Service level and description</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="63358-104">Lorsque vous créez un ordre de travail, vous pouvez définir les niveaux de service pour celui-ci et y ajouter une description générale.</span><span class="sxs-lookup"><span data-stu-id="63358-104">When you create a work order, you might want to define the service levels for it and add a general description to it.</span></span> <span data-ttu-id="63358-105">Vous pouvez créer des niveaux de service de l'ordre de travail sur la page **Niveaux de service de l'ordre de travail** et les descriptions sur la page **Description de l'ordre de travail**.</span><span class="sxs-lookup"><span data-stu-id="63358-105">You can create work order service levels on the **Work order service levels** page and descriptions on the **Work order description** page.</span></span>

## <a name="create-a-service-level"></a><span data-ttu-id="63358-106">Créer un niveau de service</span><span class="sxs-lookup"><span data-stu-id="63358-106">Create a service level</span></span>

1. <span data-ttu-id="63358-107">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Ordres de travail** \> **Niveau de service**.</span><span class="sxs-lookup"><span data-stu-id="63358-107">Select **Asset management** \> **Setup** \> **Work orders** \> **Service level**.</span></span>
2. <span data-ttu-id="63358-108">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="63358-108">Select **New**.</span></span>
3. <span data-ttu-id="63358-109">Dans le champ **Niveau de service**, entrez le niveau de service (par exemple, un numéro).</span><span class="sxs-lookup"><span data-stu-id="63358-109">In the **Service level** field, enter the service level (for example, a number).</span></span>
4. <span data-ttu-id="63358-110">Dans le champ **Nom**, entrez un nom.</span><span class="sxs-lookup"><span data-stu-id="63358-110">In the **Name** field, enter a name.</span></span>

    <span data-ttu-id="63358-111">Dans l'organisateur **Ordres de travail**, vous pouvez définir les dates et heures de début et de fin prévues.</span><span class="sxs-lookup"><span data-stu-id="63358-111">On the **Work orders** FastTab, you can define expected start and end dates and times.</span></span> <span data-ttu-id="63358-112">Les champs de cet organisateur définissent la période au cours de laquelle les ordres de travail doivent être démarrés et terminés.</span><span class="sxs-lookup"><span data-stu-id="63358-112">The fields on this FastTab define the period that work orders should be started and ended during.</span></span> <span data-ttu-id="63358-113">Ils sont utilisés pour les ordres de travail créés manuellement et les ordres de travail créés selon les demandes de maintenance.</span><span class="sxs-lookup"><span data-stu-id="63358-113">They are used for work orders that are manually created and work orders that are created based on maintenance requests.</span></span> 

5. <span data-ttu-id="63358-114">Dans le champ **Jour de début**, entrez un nombre de jours pour définir la période au cours de laquelle l'ordre de travail doit commencer.</span><span class="sxs-lookup"><span data-stu-id="63358-114">In the **Start day** field, enter a number of days to define the period that the work order should start during.</span></span> <span data-ttu-id="63358-115">Le nombre de jours est calculé depuis la date de création de l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="63358-115">The number of days is calculated from the creation date of the work order.</span></span> <span data-ttu-id="63358-116">Par exemple, si l'ordre de travail doit commencer à sa création, entrez **0**.</span><span class="sxs-lookup"><span data-stu-id="63358-116">For example, if the work order should start when it's created, enter **0**.</span></span> <span data-ttu-id="63358-117">Si l'ordre de travail doit commencer sous une semaine après sa création, entrez **7**.</span><span class="sxs-lookup"><span data-stu-id="63358-117">If the work order should start within one week after it's created, enter **7**.</span></span>
6. <span data-ttu-id="63358-118">Pour définir une heure de début pour l'ordre de travail, en plus d'une date de début, définissez l'option **Définir l'heure de début** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="63358-118">To set a start time for the work order, in addition to a start date, set the **Set start time** option to **Yes**.</span></span> <span data-ttu-id="63358-119">Puis saisissez l'heure de début dans le champ **Heure de début**.</span><span class="sxs-lookup"><span data-stu-id="63358-119">Then enter the start time in the **Start time** field.</span></span> <span data-ttu-id="63358-120">Si vous définissez l'option sur **Non**, l'heure actuelle de la journée est utilisée.</span><span class="sxs-lookup"><span data-stu-id="63358-120">If you set the option to **No**, the current time of day is used.</span></span>
7. <span data-ttu-id="63358-121">Dans le champ **Jour de fin**, entrez un nombre de jours pour définir la période au cours de laquelle l'ordre de travail doit se terminer.</span><span class="sxs-lookup"><span data-stu-id="63358-121">In the **End day** field, enter a number of days to define the period that the work order should end during.</span></span> <span data-ttu-id="63358-122">Le nombre de jours est calculé depuis la date de début de l'ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="63358-122">The number of days is calculated from the start date of the work order.</span></span> <span data-ttu-id="63358-123">Par exemple, si l'ordre de travail se termine au cours d'une semaine à compter de sa date de début, entrez **7**.</span><span class="sxs-lookup"><span data-stu-id="63358-123">For example, if the work order should end within one week of its start date, enter **7**.</span></span>
8. <span data-ttu-id="63358-124">Pour définir une heure de fin pour l'ordre de travail, en plus d'une date de fin, définissez l'option **Définir l'heure de fin** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="63358-124">To set an end time for the work order, in addition to an end date, set the **Set end time** option to **Yes**.</span></span> <span data-ttu-id="63358-125">Puis saisissez l'heure de fin dans le champ **Heure de fin**.</span><span class="sxs-lookup"><span data-stu-id="63358-125">Then enter the end time in the **End time** field.</span></span> <span data-ttu-id="63358-126">Si vous définissez l'option sur **Non**, l'heure actuelle de la journée est utilisée.</span><span class="sxs-lookup"><span data-stu-id="63358-126">If you set the option to **No**, the current time of day is used.</span></span>
9. <span data-ttu-id="63358-127">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="63358-127">Select **Save**.</span></span>

![Page Niveau de service des ordres de travail](media/19-setup-for-work-orders.png)

## <a name="create-a-description"></a><span data-ttu-id="63358-129">Créer une description</span><span class="sxs-lookup"><span data-stu-id="63358-129">Create a description</span></span>

1. <span data-ttu-id="63358-130">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Ordres de travail** \> **Descriptions**.</span><span class="sxs-lookup"><span data-stu-id="63358-130">Select **Asset management** \> **Setup** \> **Work orders** \> **Descriptions**.</span></span>
2. <span data-ttu-id="63358-131">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="63358-131">Select **New**.</span></span>
3. <span data-ttu-id="63358-132">Entrez la description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="63358-132">In the **Description** field, enter the description.</span></span>
4. <span data-ttu-id="63358-133">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="63358-133">Select **Save**.</span></span>
