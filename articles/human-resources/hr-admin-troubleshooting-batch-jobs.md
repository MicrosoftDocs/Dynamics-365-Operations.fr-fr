---
title: Optimiser les performances en planifiant des traitements par lots après les heures de travail
description: Cette rubrique explique comment résoudre les problèmes de performances avec Microsoft Dynamics 365 Human Resources en planifiant des traitements par lots de longue durée après les heures de travail.
author: andreabichsel
manager: tfehr
ms.date: 06/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 0b13853598bbdec239bce98029e534991a53876b
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467215"
---
# <a name="optimize-performance-by-scheduling-batch-jobs-after-hours"></a><span data-ttu-id="949e9-103">Optimiser les performances en planifiant des traitements par lots après les heures de travail</span><span class="sxs-lookup"><span data-stu-id="949e9-103">Optimize performance by scheduling batch jobs after hours</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="issue"></a><span data-ttu-id="949e9-104">Sortie</span><span class="sxs-lookup"><span data-stu-id="949e9-104">Issue</span></span>

<span data-ttu-id="949e9-105">Microsoft Dynamics 365 Human Resources peut rencontrer des problèmes de performances si des traitements par lots de longue durée s’exécutent pendant les heures de bureau normales.</span><span class="sxs-lookup"><span data-stu-id="949e9-105">Microsoft Dynamics 365 Human Resources can experience performance issues if long-running batch jobs run during typical business hours.</span></span>

## <a name="resolution"></a><span data-ttu-id="949e9-106">Résolution</span><span class="sxs-lookup"><span data-stu-id="949e9-106">Resolution</span></span>

<span data-ttu-id="949e9-107">Planifiez les traitements par lots suivants pendant les heures creuses.</span><span class="sxs-lookup"><span data-stu-id="949e9-107">Schedule the following batch jobs during off hours.</span></span> <span data-ttu-id="949e9-108">Nous vous recommandons également de revoir la fréquence des traitements par lots qui s’exécutent souvent.</span><span class="sxs-lookup"><span data-stu-id="949e9-108">We also recommend reviewing the frequency of batch jobs that run frequently.</span></span> <span data-ttu-id="949e9-109">Si possible, réduisez la périodicité du traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="949e9-109">If possible, reduce the recurrence of the batch job.</span></span> <span data-ttu-id="949e9-110">Dans de nombreux cas, la fréquence par défaut est suffisante.</span><span class="sxs-lookup"><span data-stu-id="949e9-110">In many cases, the default frequency is sufficient.</span></span>

<span data-ttu-id="949e9-111">Les traitements par lots suivants doivent s’exécuter la nuit ou après les heures de travail.</span><span class="sxs-lookup"><span data-stu-id="949e9-111">The following batch jobs should run at night or after hours.</span></span> <span data-ttu-id="949e9-112">Assurez-vous de vérifier le fuseau horaire de ces traitements par lots périodiques.</span><span class="sxs-lookup"><span data-stu-id="949e9-112">Be sure to check the time zone for these recurring batch jobs.</span></span> <span data-ttu-id="949e9-113">Certains traitements par lots peuvent utiliser l’heure standard du Pacifique (PST).</span><span class="sxs-lookup"><span data-stu-id="949e9-113">Some batch jobs might use Pacific Standard Time (PST).</span></span>

| <span data-ttu-id="949e9-114">Traitement par lots</span><span class="sxs-lookup"><span data-stu-id="949e9-114">Batch job</span></span> | <span data-ttu-id="949e9-115">Occurrence par défaut</span><span class="sxs-lookup"><span data-stu-id="949e9-115">Default occurrence</span></span> |
| --- | --- |
| <span data-ttu-id="949e9-116">Nettoyage de l’historique des traitements par lots</span><span class="sxs-lookup"><span data-stu-id="949e9-116">Batch job history cleanup</span></span> | <span data-ttu-id="949e9-117">1 fois par mois</span><span class="sxs-lookup"><span data-stu-id="949e9-117">1 time per month</span></span> |
| <span data-ttu-id="949e9-118">Exporter le nettoyage intermédiaire</span><span class="sxs-lookup"><span data-stu-id="949e9-118">Export staging cleanup</span></span> | <span data-ttu-id="949e9-119">1 fois par jour</span><span class="sxs-lookup"><span data-stu-id="949e9-119">1 time per day</span></span> |
| <span data-ttu-id="949e9-120">Sync de demande d’intégration manquée Common Data Service</span><span class="sxs-lookup"><span data-stu-id="949e9-120">Common Data Service integration missed request sync</span></span> | <span data-ttu-id="949e9-121">1 fois par jour</span><span class="sxs-lookup"><span data-stu-id="949e9-121">1 time per day</span></span> |
| <span data-ttu-id="949e9-122">Tâche système de compression de la base de données qui doit s’exécuter régulièrement pendant les heures creuses</span><span class="sxs-lookup"><span data-stu-id="949e9-122">Database compression system job that needs to run regularly during off hours</span></span> | <span data-ttu-id="949e9-123">1 fois par jour</span><span class="sxs-lookup"><span data-stu-id="949e9-123">1 time per day</span></span> |
| <span data-ttu-id="949e9-124">Tâche système de recréation de l’index de la base de données qui doit s’exécuter régulièrement pendant les heures creuses</span><span class="sxs-lookup"><span data-stu-id="949e9-124">Database index rebuild system job that needs to run regularly during off hours</span></span> | <span data-ttu-id="949e9-125">1 fois par jour</span><span class="sxs-lookup"><span data-stu-id="949e9-125">1 time per day</span></span> |

1. <span data-ttu-id="949e9-126">Dans Human Resources, sélectionnez **Administration du système**.</span><span class="sxs-lookup"><span data-stu-id="949e9-126">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="949e9-127">Dans la barre de **Recherche**, recherchez l’un des traitements par lots ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="949e9-127">In the **Search** bar, search for one of the above batch jobs.</span></span>

3. <span data-ttu-id="949e9-128">Sélectionnez **Exécuter à l’arrière-plan**, puis sélectionnez **Récurrence**.</span><span class="sxs-lookup"><span data-stu-id="949e9-128">Select **Run in the background**, and then select **Recurrence**.</span></span>

   ![Définir la récurrence](media/talent-batch-history-cleanup-recurrence.png)

4. <span data-ttu-id="949e9-130">Sous **Définir la récurrence**, définissez **Date de début** et **Heure de début** pour qu’elles se produisent pendant les heures creuses ou le week-end.</span><span class="sxs-lookup"><span data-stu-id="949e9-130">Under **Define recurrence**, set the **Start date** and **Start time** to occur during off hours or the weekend.</span></span> <span data-ttu-id="949e9-131">Sélectionnez **Aucune date de fin**.</span><span class="sxs-lookup"><span data-stu-id="949e9-131">Select **No end date**.</span></span> 

   ![Définir la date et heure de début de la récurrence](media/talent-batch-history-cleanup-define-recurrence.png)

5. <span data-ttu-id="949e9-133">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="949e9-133">Select **OK**.</span></span>

6. <span data-ttu-id="949e9-134">Si nécessaire, modifiez les autres paramètres sous **Exécuter à l’arrière-plan**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="949e9-134">If needed, change any other parameters under **Run in the background**, and then select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="949e9-135">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="949e9-135">Additional resources</span></span>

[<span data-ttu-id="949e9-136">Optimiser les performances grâce aux tâches automatiques de nettoyage</span><span class="sxs-lookup"><span data-stu-id="949e9-136">Optimize performance with auto cleanup tasks</span></span>](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]