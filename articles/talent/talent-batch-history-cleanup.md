---
title: Optimiser les performances avec des tâches de nettoyage automatique
description: Cette rubrique décrit la procédure de résolution des problèmes de performances avec Microsoft Dynamics 365 Talent en nettoyant l'historique des traitements par lots.
author: andreabichsel
manager: AnnBe
ms.date: 09/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-09-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: fe536ace5c25765bd9c573f9303bd92f834765f7
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897970"
---
# <a name="optimize-performance-with-auto-cleanup-tasks"></a><span data-ttu-id="65b57-103">Optimiser les performances avec des tâches de nettoyage automatique</span><span class="sxs-lookup"><span data-stu-id="65b57-103">Optimize performance with auto cleanup tasks</span></span>

<span data-ttu-id="65b57-104">**Sortie**</span><span class="sxs-lookup"><span data-stu-id="65b57-104">**Issue**</span></span>

<span data-ttu-id="65b57-105">Microsoft Dynamics 365 Talent peut faire l'expérience de problèmes de performances si l'historique des traitements par lots se développe de trop.</span><span class="sxs-lookup"><span data-stu-id="65b57-105">Microsoft Dynamics 365 Talent can experience performance issues if the batch job history grows too large.</span></span>

<span data-ttu-id="65b57-106">**Cause**</span><span class="sxs-lookup"><span data-stu-id="65b57-106">**Cause**</span></span>

<span data-ttu-id="65b57-107">Les traitements par lots qui fonctionnent souvent peuvent entraîner la croissance insoutenable de l'historique des traitements par lots.</span><span class="sxs-lookup"><span data-stu-id="65b57-107">Batch jobs that run frequently can lead to unsustainable growth of the batch job history.</span></span> <span data-ttu-id="65b57-108">Cela peut entraîner des problèmes de performances.</span><span class="sxs-lookup"><span data-stu-id="65b57-108">This can cause performance issues.</span></span> 

<span data-ttu-id="65b57-109">**Résolution**</span><span class="sxs-lookup"><span data-stu-id="65b57-109">**Resolution**</span></span>

<span data-ttu-id="65b57-110">Planifiez une tâche automatique pour nettoyer votre historique des traitements par lots.</span><span class="sxs-lookup"><span data-stu-id="65b57-110">Schedule an automatic task to clean up your batch job history.</span></span> <span data-ttu-id="65b57-111">Nous vous recommandons de paramétrer la tâche à exécuter chaque semaine, mais vous devez exécuter le nettoyage plus ou moins souvent, selon votre environnement.</span><span class="sxs-lookup"><span data-stu-id="65b57-111">We recommend setting up the task to run weekly, but you might need to run the cleanup more or less frequently, depending on your environment.</span></span> <span data-ttu-id="65b57-112">La procédure suivante contient nos paramètres recommandés, mais vous pouvez les modifier selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="65b57-112">The following procedure contains our recommended settings, but you can change these according to your needs.</span></span>

1. <span data-ttu-id="65b57-113">Dans Talent, sélectionnez **Administration système**.</span><span class="sxs-lookup"><span data-stu-id="65b57-113">In Talent, select **System administration**.</span></span>

2. <span data-ttu-id="65b57-114">Dans la barre **Recherche**, entrez **Nettoyage de l'historique des traitements par lots**.</span><span class="sxs-lookup"><span data-stu-id="65b57-114">In the **Search** bar, enter **Batch job history clean-up**.</span></span>

   ![Rechercher le nettoyage de l'historique des traitements par lots](media/talent-batch-history-cleanup-search-bar.png)

3. <span data-ttu-id="65b57-116">Dans **Limite de l'historique (jours)**, saisissez **30**.</span><span class="sxs-lookup"><span data-stu-id="65b57-116">In **History limit (days)**, enter **30**.</span></span>

   ![Définir la limite de l'historique sur 30](media/talent-batch-history-cleanup-history-limit.png)

4. <span data-ttu-id="65b57-118">Sélectionnez **Exécuter en arrière-plan**, puis sélectionnez **Récurrence**.</span><span class="sxs-lookup"><span data-stu-id="65b57-118">Select **Run in the background** and then select **Recurrence**.</span></span>

   ![Définir la récurrence](media/talent-batch-history-cleanup-recurrence.png)

5. <span data-ttu-id="65b57-120">Sous **Définir la récurrence**, définissez **Date de début** et **Heure de début** pour qu'elles se produisent pendant les heures creuses ou le week-end, puis sélectionnez **PAS DE DATE DE FIN**.</span><span class="sxs-lookup"><span data-stu-id="65b57-120">Under **Define recurrence**, set the **Start date** and **Start time** to occur during off-hours or the weekend, and then select **NO END DATE**.</span></span> 

   ![Définir la date et heure de début de la récurrence](media/talent-batch-history-cleanup-define-recurrence.png)

6. <span data-ttu-id="65b57-122">Sous **PÉRIODICITÉ**, sélectionnez **Jours** et définissez **RÉPÉTER APRÈS L'INTERVALLE SPÉCIFIÉ** sur **7**.</span><span class="sxs-lookup"><span data-stu-id="65b57-122">Under **RECURRENCE PATTERN**, select **Days** and set **REPEAT AFTER SPECIFIED INTERVAL** to **7**.</span></span>

   ![Définir le nettoyage afin qu'il se répète de manière hebdomadaire](media/talent-batch-history-cleanup-recurrence-pattern.png)

7. <span data-ttu-id="65b57-124">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="65b57-124">Select **OK**.</span></span>

8. <span data-ttu-id="65b57-125">Modifiez les autres paramètres sous **Exécuter en arrière-plan** au besoin, et sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="65b57-125">Change any other parameters under **Run in the background** as necessary, and then select **OK**.</span></span>

