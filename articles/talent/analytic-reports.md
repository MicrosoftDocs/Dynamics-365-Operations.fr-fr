---
title: Utiliser les états analytiques dans Attract
description: Cette rubrique décrit les états analytiques pour obtenir des informations sur le processus de recrutement dans Microsoft Dynamics 365 Talent - Attract
author: fewatson
manager: AnnBe
ms.date: 04/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: fewatson
ms.search.validFrom: 2019-04-30
ms.dyn365.ops.version: Talent April 2019 update
ms.openlocfilehash: 4ae608bbca111313d8c77e63f6a7a95813f6e5cd
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2019
ms.locfileid: "2833229"
---
# <a name="use-analytic-reports-in-attract"></a><span data-ttu-id="4baf4-103">Utiliser les états analytiques dans Attract</span><span class="sxs-lookup"><span data-stu-id="4baf4-103">Use analytic reports in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4baf4-104">Les états analytiques dans Microsoft Dynamics 365 Talent: Attract fournissent une solution prête à l'emploi pour obtenir des informations sur le processus de recrutement.</span><span class="sxs-lookup"><span data-stu-id="4baf4-104">Analytic reports in Microsoft Dynamics 365 Talent: Attract provide an out-of-the-box (OOTB) solution for hiring process insights.</span></span> <span data-ttu-id="4baf4-105">Les fonctionnalités disponibles comprennent :</span><span class="sxs-lookup"><span data-stu-id="4baf4-105">Availabe features include:</span></span>

- <span data-ttu-id="4baf4-106">**Analyses du poste :** Cliquez sur l'onglet **Analyses** d'un poste pour obtenir des mesures sur le candidat à un poste.</span><span class="sxs-lookup"><span data-stu-id="4baf4-106">**Job analytics:** Click the **Analytics** tab within a job for metrics on the job's applicants.</span></span>
- <span data-ttu-id="4baf4-107">**Concentrateur d'analyses :** Cliquez sur **Analyses** sur la navigation de gauche pour obtenir des mesures globales pour tous les postes.</span><span class="sxs-lookup"><span data-stu-id="4baf4-107">**Analytics hub:** Click **Analytics** on the left navigation for aggregated metrics across jobs.</span></span>
- <span data-ttu-id="4baf4-108">**Sécurité spécifique à l'utilisateur :** L'accès aux états est contrôlé par le [rôle](security-attract.md) Attract et le rôle de participant à la mission.</span><span class="sxs-lookup"><span data-stu-id="4baf4-108">**User-specific security:** Access to reports is controlled by Attract [role](security-attract.md) and job participant role.</span></span>
- <span data-ttu-id="4baf4-109">**Filtrage croisé :** Cliquez sur les visuels d'un état pour afficher d'autres mesures filtrées par des données sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="4baf4-109">**Cross-filtering:** Click visuals within a report to view other metrics filtered by selected data.</span></span>

>[!NOTE] 
>- <span data-ttu-id="4baf4-110">Cette fonctionnalité est actuellement en [mode aperçu](access-preview-feature.md).</span><span class="sxs-lookup"><span data-stu-id="4baf4-110">This feature is currently in [preview](access-preview-feature.md).</span></span> <span data-ttu-id="4baf4-111">Pour l'essayer, vous devez disposer du [**Module complémentaire Recrutement complet**](attract-comprehensive-hiring.md).</span><span class="sxs-lookup"><span data-stu-id="4baf4-111">To try it, you must have the [**Comprehensive Hiring Add-On**](attract-comprehensive-hiring.md).</span></span>
>- <span data-ttu-id="4baf4-112">Tous les états en aperçu public sont affichés en anglais.</span><span class="sxs-lookup"><span data-stu-id="4baf4-112">All public preview reports are displayed in English.</span></span>
>- <span data-ttu-id="4baf4-113">Les états sont actualisés toutes les 3 heures.</span><span class="sxs-lookup"><span data-stu-id="4baf4-113">Reports refresh every 3 hours.</span></span> <span data-ttu-id="4baf4-114">La dernière heure d'actualisation (dans le fuseau horaire local) est située en haut de l'état.</span><span class="sxs-lookup"><span data-stu-id="4baf4-114">The last refresh time (in the local timezone) is located at the top of the report.</span></span> <span data-ttu-id="4baf4-115">Les heures d'actualisation sont approximatives et varient en fonction du volume de données et de la charge des ressources dans votre région.</span><span class="sxs-lookup"><span data-stu-id="4baf4-115">Refresh times are an approximation and vary based on data volume and resource load in your region.</span></span>

## <a name="job-analytics"></a><span data-ttu-id="4baf4-116">Analyse du poste</span><span class="sxs-lookup"><span data-stu-id="4baf4-116">Job Analytics</span></span>

<span data-ttu-id="4baf4-117">Les états Analyses du poste sont un instantané du processus d'embauche pour une mission.</span><span class="sxs-lookup"><span data-stu-id="4baf4-117">Job Analytics reports are a snapshot of the hiring process for a job.</span></span>  <span data-ttu-id="4baf4-118">Les mesures clés sont :</span><span class="sxs-lookup"><span data-stu-id="4baf4-118">Key metrics include:</span></span>

- <span data-ttu-id="4baf4-119">Candidats actifs par stade</span><span class="sxs-lookup"><span data-stu-id="4baf4-119">Active applicants by stage</span></span>
- <span data-ttu-id="4baf4-120">Source de candidat</span><span class="sxs-lookup"><span data-stu-id="4baf4-120">Applicant source</span></span>
- <span data-ttu-id="4baf4-121">Type de candidat (interne ou externe)</span><span class="sxs-lookup"><span data-stu-id="4baf4-121">Applicant type (internal or external)</span></span>

## <a name="analytics-hub"></a><span data-ttu-id="4baf4-122">Concentrateur d'analyses</span><span class="sxs-lookup"><span data-stu-id="4baf4-122">Analytics Hub</span></span>

<span data-ttu-id="4baf4-123">Les états du Concentrateur d'analyses regroupent des données entre les postes pour fournit des tendances dans le processus de recrutement.</span><span class="sxs-lookup"><span data-stu-id="4baf4-123">Analytics Hub reports aggregate data across jobs to surface trends in the hiring process.</span></span> <span data-ttu-id="4baf4-124">Attract inclut deux états prêts à l'emploi : Récapitulatif des opportunités et Analyse en entonnoir.</span><span class="sxs-lookup"><span data-stu-id="4baf4-124">Attract includes two OOTB reports: Pipeline Summary and Funnel Analysis.</span></span>

### <a name="pipeline-summary"></a><span data-ttu-id="4baf4-125">Récapitulatif des opportunités</span><span class="sxs-lookup"><span data-stu-id="4baf4-125">Pipeline Summary</span></span>

<span data-ttu-id="4baf4-126">L'état Récapitulatif des opportunités regroupe les données des postes à pourvoir.</span><span class="sxs-lookup"><span data-stu-id="4baf4-126">The Pipeline Summary report aggregates data for open jobs.</span></span> <span data-ttu-id="4baf4-127">Les mesures clés sont :</span><span class="sxs-lookup"><span data-stu-id="4baf4-127">Key metrics include:</span></span>

- <span data-ttu-id="4baf4-128">Candidats à tous les postes par stade</span><span class="sxs-lookup"><span data-stu-id="4baf4-128">Applicants across all jobs by stage</span></span>
- <span data-ttu-id="4baf4-129">Source de candidat</span><span class="sxs-lookup"><span data-stu-id="4baf4-129">Applicant source</span></span>
- <span data-ttu-id="4baf4-130">Postes à pourvoir par niveau d'ancienneté</span><span class="sxs-lookup"><span data-stu-id="4baf4-130">Open jobs by seniority level</span></span>

### <a name="funnel-analysis"></a><span data-ttu-id="4baf4-131">Analyse en entonnoir</span><span class="sxs-lookup"><span data-stu-id="4baf4-131">Funnel Analysis</span></span>

<span data-ttu-id="4baf4-132">L'état Analyse en entonnoir regroupe des données pour des postes Fermés comme pourvus.</span><span class="sxs-lookup"><span data-stu-id="4baf4-132">The Funnel Analysis report aggregates data for jobs that have been closed as filled.</span></span> <span data-ttu-id="4baf4-133">Les mesures clés sont :</span><span class="sxs-lookup"><span data-stu-id="4baf4-133">Key metrics include:</span></span>

- <span data-ttu-id="4baf4-134">Délai du recrutement</span><span class="sxs-lookup"><span data-stu-id="4baf4-134">Time to hire</span></span>
- <span data-ttu-id="4baf4-135">Mesures de conversion (avec pointeur)</span><span class="sxs-lookup"><span data-stu-id="4baf4-135">Conversion metrics (on hover)</span></span>
- <span data-ttu-id="4baf4-136">Taux d'acceptation d'offre</span><span class="sxs-lookup"><span data-stu-id="4baf4-136">Offer acceptance rate</span></span>

<span data-ttu-id="4baf4-137">Remarque : Pour obtenir des états sur les délais de recrutement les plus précis, il est conseillé d'utiliser [Gestion des offres](offer-setup.md), fonctionnalité disponible dans le cadre du Module complémentaire Recrutement complet.</span><span class="sxs-lookup"><span data-stu-id="4baf4-137">Note: For the most accurate time to hire reporting, it is recommended that you use [Offer management](offer-setup.md), a feature available as part of the Comprehensive Hiring Add-On.</span></span>

>[!TIP] 
><span data-ttu-id="4baf4-138">Essayez de passer le pointeur de votre souris sur des visuels pour obtenir des informations supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="4baf4-138">Try hovering over visuals for additional information.</span></span> <span data-ttu-id="4baf4-139">Par exemple, si vous passez votre pointeur sur **Candidats actifs**, les visuels affichent le nombre moyen de jours dans ce stade.</span><span class="sxs-lookup"><span data-stu-id="4baf4-139">For example, hovering over **Active applicants** visuals will display the average days in stage.</span></span> <span data-ttu-id="4baf4-140">L'analyse de ces informations peut fournir des informations critiques permettant de réduire le délai du recrutement et permettre aux recruteurs de se concentrer sur des façons de réduire le temps passé à chaque stade.</span><span class="sxs-lookup"><span data-stu-id="4baf4-140">Analyzing this information can provide insights critical to reducing time to hire and enable recruiters to focus on ways to reduce the time spent in each stage.</span></span>

## <a name="user-specific-security"></a><span data-ttu-id="4baf4-141">Sécurité spécifique à l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="4baf4-141">User-specific security</span></span>

<span data-ttu-id="4baf4-142">Les états Attract sont accessibles par les [rôles](security-attract.md) Administrateur, Tout lire, Recruteur et Responsable du recrutement.</span><span class="sxs-lookup"><span data-stu-id="4baf4-142">Attract reports are accessible for Admin, Read All, Recruiter, and Hiring Manager [roles](security-attract.md).</span></span> <span data-ttu-id="4baf4-143">Les utilisateurs non affectés n'ont pas accès aux pages des états d'analyses (Analyses du poste ou Concentrateur d'analyses).</span><span class="sxs-lookup"><span data-stu-id="4baf4-143">Unassigned users do not have access to either of the analytic report pages (Job Analytics or Analytics Hub).</span></span>

<span data-ttu-id="4baf4-144">Les états Analyses du poste affichent des données sur le poste sélectionné.</span><span class="sxs-lookup"><span data-stu-id="4baf4-144">Job Analytics reports display data for the selected job.</span></span> <span data-ttu-id="4baf4-145">Les états du Concentrateur d'analyses regroupent des données sur tous les postes qu'un utilisateur peut afficher.</span><span class="sxs-lookup"><span data-stu-id="4baf4-145">Analytics Hub reports aggregate data across all jobs a user can view.</span></span> <span data-ttu-id="4baf4-146">Les utilisateurs qui peuvent afficher Mes postes et Tous les postes sur la page Postes ont les vues disponibles dans le Concentrateur d'analyses.</span><span class="sxs-lookup"><span data-stu-id="4baf4-146">Users that can view both My jobs and All jobs on the Jobs page have the same views available in the Analytics Hub.</span></span>

## <a name="cross-filter"></a><span data-ttu-id="4baf4-147">Filtrage croisé</span><span class="sxs-lookup"><span data-stu-id="4baf4-147">Cross-filter</span></span>

<span data-ttu-id="4baf4-148">L'une des fonctionnalités importantes de Power BI est la façon dont tous les visuels sur une page d'état sont interconnectés.</span><span class="sxs-lookup"><span data-stu-id="4baf4-148">One of the great features of Power BI is the way all visuals on a report page are interconnected.</span></span> <span data-ttu-id="4baf4-149">Si vous sélectionnez un point de données sur l'un des visuels, tous les autres visuels de la page qui contiennent ces données changent, selon cette sélection.</span><span class="sxs-lookup"><span data-stu-id="4baf4-149">If you select a data point on one of the visuals, all the other visuals on the page that contain that data change, based on that selection.</span></span> <span data-ttu-id="4baf4-150">Pour en savoir plus et voir un exemple dans [Filtrage croisé des visuels dans un état Power BI](https://docs.microsoft.com/power-bi/consumer/end-user-interactions).</span><span class="sxs-lookup"><span data-stu-id="4baf4-150">Find out more and see an example in [How visuals cross-filter each other in a Power BI report](https://docs.microsoft.com/power-bi/consumer/end-user-interactions).</span></span>

## <a name="export-to-excel"></a><span data-ttu-id="4baf4-151">Exporter vers Excel</span><span class="sxs-lookup"><span data-stu-id="4baf4-151">Export to Excel</span></span>

<span data-ttu-id="4baf4-152">Pour afficher les données d'un état dans Excel, vous pouvez cliquer sur le menu Options (trois points) d'un visuel et sélectionner **Exporter les données sous-jacentes**.</span><span class="sxs-lookup"><span data-stu-id="4baf4-152">To view report data in Excel, you can click the options menu (three dots) on a visual and select **Export underlying data**.</span></span> <span data-ttu-id="4baf4-153">Les données exportées s'exporteront filtrées, en fonction des autorisations de l'utilisateur dans Attract.</span><span class="sxs-lookup"><span data-stu-id="4baf4-153">Exported data will export as filtered, respecting user permissions in Attract.</span></span> <span data-ttu-id="4baf4-154">Pour plus d'informations, voir [Exporter à partir des visualisations](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data).</span><span class="sxs-lookup"><span data-stu-id="4baf4-154">For more information, see [Export data from visualizations](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data).</span></span>
