---
title: Contenu Power BI de gestion des dépenses
description: Cette rubrique décrit les données incluses dans le pack de contenu Power BI Gestion des dépenses.
author: RyanSand
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: TrvExpenseWorkspace, ExpenseWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 0dcb6114544b3817d8b80122a32759e67ad8dc94
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181701"
---
# <a name="expense-management-power-bi-content"></a><span data-ttu-id="e6f19-103">Contenu Power BI de gestion des dépenses</span><span class="sxs-lookup"><span data-stu-id="e6f19-103">Expense management Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e6f19-104">Cette rubrique décrit les données incluses dans le contenu Power BI Gestion des dépenses.</span><span class="sxs-lookup"><span data-stu-id="e6f19-104">This topic describes what is included in the Expense management Power BI content.</span></span> 

## <a name="overview"></a><span data-ttu-id="e6f19-105">Présentation</span><span class="sxs-lookup"><span data-stu-id="e6f19-105">Overview</span></span>
<span data-ttu-id="e6f19-106">Deux packs de contenu Power BI sont disponibles pour être utilisés avec la Gestion des dépenses dans la version 8.1 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="e6f19-106">Two Power BI content packs are available for use with Expense management in version 8.1 and later.</span></span> 
- <span data-ttu-id="e6f19-107">Il existe un tableau de bord personnel conçu pour les employés qui soumettent des états de dépenses.</span><span class="sxs-lookup"><span data-stu-id="e6f19-107">There is a personal dashboard designed for employees who submit expense reports.</span></span> 

  <span data-ttu-id="e6f19-108">Ce tableau de bord est personnalisé pour fournir des informations importantes sur les montants qui ont été soumis et ne l'ont pas été, ainsi que l'historique et une analyse de l'historique des transactions de dépense.</span><span class="sxs-lookup"><span data-stu-id="e6f19-108">The dashboard is tailored to provide key information to individuals about unsubmitted and submitted amounts, as well as history and insights into expense transaction history.</span></span> <span data-ttu-id="e6f19-109">Le tableau de bord personnel est une seule page contenant les principales informations pour l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e6f19-109">The personal dashboard is a single page containing the most important information for the user.</span></span>

- <span data-ttu-id="e6f19-110">Il existe un concepteur de tableau de bord Administrateur conçu pour les employés et les responsables de la comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e6f19-110">There is an admin dashboard designed for accounts payable clerks and managers.</span></span> <span data-ttu-id="e6f19-111">Ce tableau de bord est adapté au suivi et à la génération d'états sur les dépenses générales des employés.</span><span class="sxs-lookup"><span data-stu-id="e6f19-111">The dashboard is tailored toward tracking and reporting on overall employee expenses.</span></span> <span data-ttu-id="e6f19-112">Il fournit des éléments de mesure des dépense, telles que les dépenses qui n'ont pas été soumises, le kilométrage, et les montants moyens des états de dépenses.</span><span class="sxs-lookup"><span data-stu-id="e6f19-112">It provides key expense metrics, such as unsubmitted expenses, mileage, and average expense report amounts.</span></span> <span data-ttu-id="e6f19-113">Il utilise des données transactionnelles et fournit une vue agrégée de la gestion des dépenses dans toutes les sociétés.</span><span class="sxs-lookup"><span data-stu-id="e6f19-113">It uses transactional data and provides aggregate views of expense management across all companies.</span></span> <span data-ttu-id="e6f19-114">Il fournit également une répartition par employé, avec la possibilité d'ajouter des données de dimension financière.</span><span class="sxs-lookup"><span data-stu-id="e6f19-114">It also provides a breakdown per employee, with the option to add financial dimension data.</span></span> <span data-ttu-id="e6f19-115">Le contenu d'analyses de dépense Administrateur contient :</span><span class="sxs-lookup"><span data-stu-id="e6f19-115">The Admin expense analytics content contains:</span></span> 
  - <span data-ttu-id="e6f19-116">Une page de vue d'ensemble avec les mesures principales sur les montants des dépenses et des aperçus des états des dépenses à l'état de brouillon, en cours, et terminés.</span><span class="sxs-lookup"><span data-stu-id="e6f19-116">An overview page with key metrics about expense amounts and insights into draft, in process, and completed expense reports.</span></span> 
  - <span data-ttu-id="e6f19-117">Une page de statistiques d'employé pour examiner les détails concernant un employé par horaire, type de coût et groupe de statistiques.</span><span class="sxs-lookup"><span data-stu-id="e6f19-117">An employee statistics page to review individual details about an employee by time, cost type, and statistics group.</span></span> 
  - <span data-ttu-id="e6f19-118">Une page de comparaison des employés pour comparer plusieurs employés au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="e6f19-118">An employee comparison page to compare multiple employees over time.</span></span> 

<span data-ttu-id="e6f19-119">Tous les montants sont indiqués dans la devise de la société.</span><span class="sxs-lookup"><span data-stu-id="e6f19-119">All the amounts are shown in the company currency.</span></span> <span data-ttu-id="e6f19-120">Les données de toutes les sociétés sont affichées, mais si nécessaire vous pouvez ajouter un filtre de société.</span><span class="sxs-lookup"><span data-stu-id="e6f19-120">Data for all companies are shown, but if needed you can add a company filter.</span></span> 

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="e6f19-121">Accès au contenu Power BI</span><span class="sxs-lookup"><span data-stu-id="e6f19-121">Accessing the Power BI content</span></span>
<span data-ttu-id="e6f19-122">Vous pouvez trouver le contenu Power BI Expense Admin Dashboard.pbix et Expense Personal Dashboard.pbix dans la bibliothèque des actifs partagés dans Microsoft Dynamics LCS (Lifecycle Services).</span><span class="sxs-lookup"><span data-stu-id="e6f19-122">You can find the Expense Admin Dashboard.pbix and Expense Personal Dashboard.pbix Power BI content in the Shared assets library in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="e6f19-123">Pour savoir comment télécharger le contenu et l'implémenter dans votre organisation, voir [Contenu Power BI dans LCS de Microsoft et de vos partenaires](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/12/12/power-bi-content-from-microsoft-and-your-partners/).</span><span class="sxs-lookup"><span data-stu-id="e6f19-123">For more information about how to download the content and implement it in your organization, see [Power BI content in LCS from Microsoft and your partners](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/12/12/power-bi-content-from-microsoft-and-your-partners/).</span></span>
<span data-ttu-id="e6f19-124">Le contenu est disponible dans l'espace de travail Gestion des dépenses comme contenu intégré de Power BI.</span><span class="sxs-lookup"><span data-stu-id="e6f19-124">The content is available from the Expense Management workspace as embedded Power Bi content.</span></span> <span data-ttu-id="e6f19-125">Tout propriétaire de dépenses peut accéder à ses propres dépenses personnelles, tandis que seuls les employé et les responsables de la comptabilité fournisseur ont accès au contenu Administrateur pour afficher les données de dépenses de tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e6f19-125">Any expense owner can access personal expenses for themselves, while only Accounts Payable clerks and managers have access to the Admin content to view all user's expense data.</span></span>

## <a name="refreshing-the-power-bi-content"></a><span data-ttu-id="e6f19-126">Actualisation du contenu Power BI</span><span class="sxs-lookup"><span data-stu-id="e6f19-126">Refreshing the Power BI content</span></span>
<span data-ttu-id="e6f19-127">Le contenu Power BI Gestion des dépenses nécessite que les mesures TrvBiExpenseMeasurement et BudgetActivityMeasure soient actualisées à partir du magasin des entités.</span><span class="sxs-lookup"><span data-stu-id="e6f19-127">The Expense management Power BI content requires the TrvBiExpenseMeasurement measure and the BudgetActivityMeasure to be refreshed from the Entity Store.</span></span> 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="e6f19-128">Mesures incluses dans le pack de contenu Power BI</span><span class="sxs-lookup"><span data-stu-id="e6f19-128">Metrics that are included in the Power BI content</span></span>
<span data-ttu-id="e6f19-129">Le contenu comprend un ensemble de pages d'état.</span><span class="sxs-lookup"><span data-stu-id="e6f19-129">The content includes a set of report pages.</span></span> <span data-ttu-id="e6f19-130">Chaque page contient un ensemble de mesures visualisées sous forme de graphiques, de vignettes et de tables.</span><span class="sxs-lookup"><span data-stu-id="e6f19-130">Each page consists of a set of metrics that are visualized as charts, tiles, and tables.</span></span> <span data-ttu-id="e6f19-131">Le tableau suivant offre une vue d'ensemble des visualisations proposées dans le contenu Power BI.</span><span class="sxs-lookup"><span data-stu-id="e6f19-131">The following table provides an overview of the visualizations in the Power BI content.</span></span>

<span data-ttu-id="e6f19-132">**Analyses des dépenses personnelles**</span><span class="sxs-lookup"><span data-stu-id="e6f19-132">**Personal expenses analytics**</span></span>

| <span data-ttu-id="e6f19-133">Page d'état</span><span class="sxs-lookup"><span data-stu-id="e6f19-133">Report page</span></span> | <span data-ttu-id="e6f19-134">Visualisation</span><span class="sxs-lookup"><span data-stu-id="e6f19-134">Visualization</span></span>                             |
|-------------|-------------------------------------------|
| <span data-ttu-id="e6f19-135">Mes dépenses</span><span class="sxs-lookup"><span data-stu-id="e6f19-135">My expenses</span></span> | <span data-ttu-id="e6f19-136">Montant du kilométrage</span><span class="sxs-lookup"><span data-stu-id="e6f19-136">Amount of mileage</span></span>                         |
|             | <span data-ttu-id="e6f19-137">États des dépenses en cours</span><span class="sxs-lookup"><span data-stu-id="e6f19-137">In process expense reports</span></span>                |
|             | <span data-ttu-id="e6f19-138">N°</span><span class="sxs-lookup"><span data-stu-id="e6f19-138">No.</span></span> <span data-ttu-id="e6f19-139">des dépenses non soumises</span><span class="sxs-lookup"><span data-stu-id="e6f19-139">of Unsubmitted expenses</span></span>               |
|             | <span data-ttu-id="e6f19-140">Dépenses personnelles à payer</span><span class="sxs-lookup"><span data-stu-id="e6f19-140">Personal expenses to be paid</span></span>              |
|             | <span data-ttu-id="e6f19-141">Montant non soumis</span><span class="sxs-lookup"><span data-stu-id="e6f19-141">Amount unsubmitted</span></span>                        |
|             | <span data-ttu-id="e6f19-142">Montant soumis</span><span class="sxs-lookup"><span data-stu-id="e6f19-142">Amount submitted</span></span>                          |
|             | <span data-ttu-id="e6f19-143">Montant en attente de remboursement</span><span class="sxs-lookup"><span data-stu-id="e6f19-143">Amount awaiting reimbursement</span></span>             |
|             | <span data-ttu-id="e6f19-144">États des dépenses avec les montants et le statut</span><span class="sxs-lookup"><span data-stu-id="e6f19-144">Expense reports with amounts and status</span></span>   |
|             | <span data-ttu-id="e6f19-145">États des dépenses soumises mais non approuvées</span><span class="sxs-lookup"><span data-stu-id="e6f19-145">Submitted but unapproved expense reports</span></span>  |
|             | <span data-ttu-id="e6f19-146">Dépenses par type de coût</span><span class="sxs-lookup"><span data-stu-id="e6f19-146">Expenses by cost type</span></span>                     |
|             | <span data-ttu-id="e6f19-147">Dépenses par marchand</span><span class="sxs-lookup"><span data-stu-id="e6f19-147">Expenses by merchant</span></span>                      |
|             | <span data-ttu-id="e6f19-148">Dépenses par dépenses traitées</span><span class="sxs-lookup"><span data-stu-id="e6f19-148">Expenses by processed expenses</span></span>            |
|             | <span data-ttu-id="e6f19-149">Dépenses par projet</span><span class="sxs-lookup"><span data-stu-id="e6f19-149">Expenses by project</span></span>                       |
|             | <span data-ttu-id="e6f19-150">Montant total des transactions au fil du temps</span><span class="sxs-lookup"><span data-stu-id="e6f19-150">Total transaction amount over time</span></span>        |

<span data-ttu-id="e6f19-151">**Analyses des dépenses de l'administrateur**</span><span class="sxs-lookup"><span data-stu-id="e6f19-151">**Admin expenses analytics**</span></span>

| <span data-ttu-id="e6f19-152">Page d'état</span><span class="sxs-lookup"><span data-stu-id="e6f19-152">Report page</span></span>         | <span data-ttu-id="e6f19-153">Visualisation</span><span class="sxs-lookup"><span data-stu-id="e6f19-153">Visualization</span></span>                           |           
|---------------------|-----------------------------------------|
| <span data-ttu-id="e6f19-154">Vue d'ensemble des dépenses</span><span class="sxs-lookup"><span data-stu-id="e6f19-154">Expense Overview</span></span>    | <span data-ttu-id="e6f19-155">Montant de dépense - brouillon</span><span class="sxs-lookup"><span data-stu-id="e6f19-155">Draft expenses amount</span></span>                   |
|                     | <span data-ttu-id="e6f19-156">Nombre de lignes de dépense - brouillon</span><span class="sxs-lookup"><span data-stu-id="e6f19-156">Number of draft expense lines</span></span>           |
|                     | <span data-ttu-id="e6f19-157">Lignes de dépense - brouillon</span><span class="sxs-lookup"><span data-stu-id="e6f19-157">Draft expense lines</span></span>                     |
|                     | <span data-ttu-id="e6f19-158">Violations de stratégie pour l'état des dépenses</span><span class="sxs-lookup"><span data-stu-id="e6f19-158">Expense report policy violations</span></span>        |
|                     | <span data-ttu-id="e6f19-159">Montant restant</span><span class="sxs-lookup"><span data-stu-id="e6f19-159">Amount outstanding</span></span>                      |
|                     | <span data-ttu-id="e6f19-160">Dépenses soumises mais non approuvées</span><span class="sxs-lookup"><span data-stu-id="e6f19-160">Submitted but unapproved expenses</span></span>       |
|                     | <span data-ttu-id="e6f19-161">Dépenses approuvées</span><span class="sxs-lookup"><span data-stu-id="e6f19-161">Approved expenses</span></span>                       |
|                     | <span data-ttu-id="e6f19-162">Montant total des dépenses</span><span class="sxs-lookup"><span data-stu-id="e6f19-162">Total expense amount</span></span>                    |
|                     | <span data-ttu-id="e6f19-163">Synthèses de l'état des dépenses</span><span class="sxs-lookup"><span data-stu-id="e6f19-163">Expense report summaries</span></span>                |
|                     | <span data-ttu-id="e6f19-164">Dépenses par type de coût</span><span class="sxs-lookup"><span data-stu-id="e6f19-164">Expenses by cost type</span></span>                   |
|                     | <span data-ttu-id="e6f19-165">Dépenses par marchand</span><span class="sxs-lookup"><span data-stu-id="e6f19-165">Expenses by merchant</span></span>                    |
|                     | <span data-ttu-id="e6f19-166">Dépenses par employé</span><span class="sxs-lookup"><span data-stu-id="e6f19-166">Expenses by employees</span></span>                   |
|                     | <span data-ttu-id="e6f19-167">Dépenses par projet</span><span class="sxs-lookup"><span data-stu-id="e6f19-167">Expenses vs project</span></span>                     |
| <span data-ttu-id="e6f19-168">Comparaison des employés</span><span class="sxs-lookup"><span data-stu-id="e6f19-168">Employee Comparison</span></span> | <span data-ttu-id="e6f19-169">Montants des dépenses</span><span class="sxs-lookup"><span data-stu-id="e6f19-169">Expense amounts</span></span>                         |
|                     | <span data-ttu-id="e6f19-170">Montants des dépenses au fil du temps par employé</span><span class="sxs-lookup"><span data-stu-id="e6f19-170">Expense amounts over time by employee</span></span>   |
| <span data-ttu-id="e6f19-171">Statistiques d'employé</span><span class="sxs-lookup"><span data-stu-id="e6f19-171">Employee Statistics</span></span> | <span data-ttu-id="e6f19-172">États des dépenses par type de coût</span><span class="sxs-lookup"><span data-stu-id="e6f19-172">Expense reports by cost type</span></span>            |
|                     | <span data-ttu-id="e6f19-173">Dépenses personnelles</span><span class="sxs-lookup"><span data-stu-id="e6f19-173">Personal expenses</span></span>                       |
|                     | <span data-ttu-id="e6f19-174">États des dépenses de groupe de statistiques</span><span class="sxs-lookup"><span data-stu-id="e6f19-174">Expense reports by statistics group</span></span>     |
