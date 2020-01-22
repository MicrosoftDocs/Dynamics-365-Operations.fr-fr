---
title: Annuler une tâche de planification
description: Cette rubrique explique comment annuler une tâche active de planification qui utilise la fonctionnalité de planification intégrée.
author: ChristianRytt
manager: AnnBe
ms.date: 01/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-12-16
ms.dyn365.ops.version: ''
ms.openlocfilehash: 66d5b10e1471b98274d4049df18a2e53873f789a
ms.sourcegitcommit: 92cd55028be556a0bd41b6972c9c6d14b695dfa0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/10/2020
ms.locfileid: "2947478"
---
# <a name="cancel-a-master-planning-job"></a><span data-ttu-id="0e32e-103">Annuler une tâche de planification</span><span class="sxs-lookup"><span data-stu-id="0e32e-103">Cancel a master planning job</span></span>

<span data-ttu-id="0e32e-104">Dans Microsoft Dynamics 365 Supply Chain Management, il existe plusieurs options pour annuler un travail de planification.</span><span class="sxs-lookup"><span data-stu-id="0e32e-104">In Microsoft Dynamics 365 Supply Chain Management, there are multiple options for canceling a master planning job.</span></span> <span data-ttu-id="0e32e-105">Par exemple, vous souhaiterez peut-être annuler une tâche de planification si elle a été démarrée par erreur ou s’exécute plus longtemps que prévu et que vous souhaitez y mettre fin.</span><span class="sxs-lookup"><span data-stu-id="0e32e-105">For example, you may want to cancel a master planning job if it was started by mistake or is running longer than expected and you want to end it.</span></span> <span data-ttu-id="0e32e-106">La meilleure façon d'annuler un travail de planification se trouve sur la page **Processus de planification inachevés**.</span><span class="sxs-lookup"><span data-stu-id="0e32e-106">The best way to cancel a planning job is from  the **Unfinished planning processes** page.</span></span> <span data-ttu-id="0e32e-107">Les options alternatives aux pages **Traitement par lots** et **Traitement par lots améliorés** ne doivent être utilisées que si l'annulation de la tâche de planification de la page **Processus de planification inachevés** ne s'est pas terminée en quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="0e32e-107">Alternative options from the **Batch jobs** and **Batch jobs enhanced** pages should only be used if canceling the master planning job from the **Unfinished planning processes** page did not complete within a few minutes.</span></span>

## <a name="preferred-cancel-option"></a><span data-ttu-id="0e32e-108">Option d'annulation préférée</span><span class="sxs-lookup"><span data-stu-id="0e32e-108">Preferred cancel option</span></span>
### <a name="cancel-master-planning-job-from-unfinished-planning-processes-page"></a><span data-ttu-id="0e32e-109">Annuler le travail de planification de la page **Processus de planification inachevés**</span><span class="sxs-lookup"><span data-stu-id="0e32e-109">Cancel master planning job from **Unfinished planning processes** page</span></span>
1. <span data-ttu-id="0e32e-110">Allez dans **Planification > Recherches et états > Planification > Processus de planification non terminés**.</span><span class="sxs-lookup"><span data-stu-id="0e32e-110">Go to **Master planning > Inquiries and reports > Master planning > Unfinished planning processes**.</span></span>
2. <span data-ttu-id="0e32e-111">Sélectionnez la ligne du processus de planification à annuler.</span><span class="sxs-lookup"><span data-stu-id="0e32e-111">Select the line with the planning process that you want to cancel.</span></span>
3. <span data-ttu-id="0e32e-112">Cliquez sur **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="0e32e-112">Click **Cancel**.</span></span>

## <a name="additional-cancel-options"></a><span data-ttu-id="0e32e-113">Options d'annulation supplémentaires</span><span class="sxs-lookup"><span data-stu-id="0e32e-113">Additional cancel options</span></span>
<span data-ttu-id="0e32e-114">Celles-ci ne doivent être utilisées que si l'annulation du travail de planification sur la page **Processus de planification non terminés** ne s'est pas terminée en quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="0e32e-114">These should only be used iif cancelin the master planning job from the **Unfinished planning processes** page did not complete within a few minutes.</span></span>

### <a name="delete-master-planning-job-from-the-batch-jobs-page"></a><span data-ttu-id="0e32e-115">Suppression du travail de planification de la page **Traitement par lots**</span><span class="sxs-lookup"><span data-stu-id="0e32e-115">Delete master planning job from the **Batch jobs** page</span></span>
1. <span data-ttu-id="0e32e-116">Accédez à **Administration du système > Recherches > Traitements par lots**.</span><span class="sxs-lookup"><span data-stu-id="0e32e-116">Go to **System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="0e32e-117">Sélectionnez la ligne de la tâche de planification à supprimer.</span><span class="sxs-lookup"><span data-stu-id="0e32e-117">Select the line with the planning job that you want to delete.</span></span>
3. <span data-ttu-id="0e32e-118">Cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="0e32e-118">Click **Delete**.</span></span>

### <a name="abort-master-planning-job-task-from-the-batch-jobs-enhanced-page"></a><span data-ttu-id="0e32e-119">Abandon de la tâche du travail de planification de la page **Traitement par lots améliorés**</span><span class="sxs-lookup"><span data-stu-id="0e32e-119">Abort master planning job task from the **Batch jobs enhanced** page</span></span>
1. <span data-ttu-id="0e32e-120">Accédez à **Administration du système > Recherches > Traitements par lots**.</span><span class="sxs-lookup"><span data-stu-id="0e32e-120">Go to **System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="0e32e-121">Si l'ID de tâche n'apparaît pas dans la liste, cliquez sur **Basculer vers le formulaire amélioré**, sinon passez à l'étape suivante.</span><span class="sxs-lookup"><span data-stu-id="0e32e-121">If the job ID is not shown in the list, click **Switch to enhanced form**, otherwise proceed with the next step.</span></span>
3. <span data-ttu-id="0e32e-122">Ouvrez le traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="0e32e-122">Open the batch job.</span></span> <span data-ttu-id="0e32e-123">Cliquez sur l'**ID de tâche** du traitement par lots avec les tâches à terminer.</span><span class="sxs-lookup"><span data-stu-id="0e32e-123">Click the **Job ID** for the batch job with tasks that you want to end.</span></span>
4. <span data-ttu-id="0e32e-124">Dans **Tâches des traitements par lots**, sélectionnez les tâches à terminer.</span><span class="sxs-lookup"><span data-stu-id="0e32e-124">In **Batch tasks**, select the tasks to end.</span></span>
5. <span data-ttu-id="0e32e-125">Sur l'organisateur **Tâches des traitements par lots**, cliquez sur **Abandonner**.</span><span class="sxs-lookup"><span data-stu-id="0e32e-125">On the **Batch tasks** FastTab, click **Abort**.</span></span>