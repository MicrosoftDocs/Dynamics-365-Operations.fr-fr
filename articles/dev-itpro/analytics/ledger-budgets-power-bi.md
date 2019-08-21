---
title: Contenu Power BI Comparatif Réel/Budget
description: Cette rubrique décrit le contenu Power BI Comparatif Réel/Budget. Elle explique également comment accéder aux états inclus dans le contenu, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.
author: ryansandness
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetTrackingWorkspace
audience: Application user, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: a577ab24aaf86c1f7a22953e03f397a2e8213c78
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1849429"
---
# <a name="actual-vs-budget-power-bi-content"></a><span data-ttu-id="345c1-104">Contenu Power BI Comparatif Réel/Budget</span><span class="sxs-lookup"><span data-stu-id="345c1-104">Actual vs budget Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="345c1-105">Cette rubrique décrit le contenu Power BI **Comparatif Réel/Budget**.</span><span class="sxs-lookup"><span data-stu-id="345c1-105">This topic describes the **Actual vs budget** Microsoft Power BI content.</span></span> <span data-ttu-id="345c1-106">Elle explique également comment accéder aux états Power BI, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.</span><span class="sxs-lookup"><span data-stu-id="345c1-106">It explains how to access the Power BI reports, and provides information about the data model and entities that were used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="345c1-107">Présentation</span><span class="sxs-lookup"><span data-stu-id="345c1-107">Overview</span></span>

<span data-ttu-id="345c1-108">Le contenu Power BI **Comparatif Réel/Budget** a été créé pour les personnes chargées de surveiller le comparatif des performances de budget dans leur organisation.</span><span class="sxs-lookup"><span data-stu-id="345c1-108">The **Actual vs budget** Power BI content was created for individuals who are responsible for monitoring actual versus budget performance in their organization.</span></span> <span data-ttu-id="345c1-109">Le contenu Power BI **Comparatif Réel/Budget** fournit une visibilité dans les écarts de budget.</span><span class="sxs-lookup"><span data-stu-id="345c1-109">The **Actual vs budget** Power BI content provides visibility into your budget variances.</span></span> <span data-ttu-id="345c1-110">Vous pouvez analyser le budget de l'année en cours par catégorie de compte, code budgétaire, compte principal, description de compte principal ou période fiscale pour obtenir une meilleure compréhension de la cause de tous les écarts.</span><span class="sxs-lookup"><span data-stu-id="345c1-110">You can analyze budget for the current year by account category, budget code, main account, main account descriptions, or fiscal period to get a better understanding of the cause of any variances.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="345c1-111">Accès au contenu Power BI</span><span class="sxs-lookup"><span data-stu-id="345c1-111">Accessing the Power BI content</span></span>
<span data-ttu-id="345c1-112">Les états du contenu Power BI **Comparatif Réel/Budget** s'affichent dans les espaces de travail **Budget comptable et prévisions** et **CFO**.</span><span class="sxs-lookup"><span data-stu-id="345c1-112">Reports from the **Actual vs budget** Power BI content are shown in the **Ledger budget and forecasts** and **CFO** workspaces.</span></span>

## <a name="reports-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="345c1-113">États inclus dans le pack de contenu Power BI</span><span class="sxs-lookup"><span data-stu-id="345c1-113">Reports that are included in the Power BI content</span></span>
<span data-ttu-id="345c1-114">Le tableau suivant fournit des détails sur les mesures disponibles sur chaque page d'état du contenu Power BI **Comparatif Réel/Budget**.</span><span class="sxs-lookup"><span data-stu-id="345c1-114">The following table provides details about the metrics that are found on each report page in the **Actual vs budget** Power BI content.</span></span>

| <span data-ttu-id="345c1-115">Etat</span><span class="sxs-lookup"><span data-stu-id="345c1-115">Report</span></span>                      | <span data-ttu-id="345c1-116">Métriques</span><span class="sxs-lookup"><span data-stu-id="345c1-116">Metrics</span></span>                                                                             |
|-----------------------------|-------------------------------------------------------------------------------------|
| <span data-ttu-id="345c1-117">Dépenses - comparatif Réel/Budget</span><span class="sxs-lookup"><span data-stu-id="345c1-117">Expenses - Actual vs budget</span></span> | <ul><li><span data-ttu-id="345c1-118">Dépenses totales de cette année</span><span class="sxs-lookup"><span data-stu-id="345c1-118">Total expenses this year</span></span></li><li><span data-ttu-id="345c1-119">Dépenses totales de cette année</span><span class="sxs-lookup"><span data-stu-id="345c1-119">Budget total expenses this year</span></span></li></ul>  |
| <span data-ttu-id="345c1-120">Produit - Comparatif Réel/Budget</span><span class="sxs-lookup"><span data-stu-id="345c1-120">Revenue - Actual vs budget</span></span>  | <ul><li><span data-ttu-id="345c1-121">Produit total de cette année</span><span class="sxs-lookup"><span data-stu-id="345c1-121">Total revenue this year</span></span></li><li><span data-ttu-id="345c1-122">Produit total basé sur le budget de cette année</span><span class="sxs-lookup"><span data-stu-id="345c1-122">Budget total revenue this year</span></span></li><ul>     |
| <span data-ttu-id="345c1-123">Dépense</span><span class="sxs-lookup"><span data-stu-id="345c1-123">Expense</span></span>                     | <ul><li><span data-ttu-id="345c1-124">Dépenses totales de cette année</span><span class="sxs-lookup"><span data-stu-id="345c1-124">Total expenses this year</span></span></li><li><span data-ttu-id="345c1-125">Objectif des dépenses basées sur le budget</span><span class="sxs-lookup"><span data-stu-id="345c1-125">Goal for expenses based on budget</span></span></li><ul> |
| <span data-ttu-id="345c1-126">Produit</span><span class="sxs-lookup"><span data-stu-id="345c1-126">Revenue</span></span>                     | <ul><li><span data-ttu-id="345c1-127">Produit total de cette année</span><span class="sxs-lookup"><span data-stu-id="345c1-127">Total revenue this year</span></span></li><li><span data-ttu-id="345c1-128">Objectif des produits basés sur le budget</span><span class="sxs-lookup"><span data-stu-id="345c1-128">Goal for revenue based on budget</span></span></li><ul>   |
| <span data-ttu-id="345c1-129">Revenu net</span><span class="sxs-lookup"><span data-stu-id="345c1-129">Net income</span></span>                  | <ul><li><span data-ttu-id="345c1-130">Revenu net de cette année</span><span class="sxs-lookup"><span data-stu-id="345c1-130">Net income this year</span></span></li><li><span data-ttu-id="345c1-131">Objectif du revenu net basé sur le budget</span><span class="sxs-lookup"><span data-stu-id="345c1-131">Goal for net income based on budget</span></span></li><ul>   |

## <a name="understanding-the-data-model-and-entities"></a><span data-ttu-id="345c1-132">Compréhension du modèle de données et des entités</span><span class="sxs-lookup"><span data-stu-id="345c1-132">Understanding the data model and entities</span></span>

| <span data-ttu-id="345c1-133">Entité</span><span class="sxs-lookup"><span data-stu-id="345c1-133">Entity</span></span>                    | <span data-ttu-id="345c1-134">Sommaire</span><span class="sxs-lookup"><span data-stu-id="345c1-134">Contents</span></span>                                                                         |
|---------------------------|----------------------------------------------------------------------------------|
| <span data-ttu-id="345c1-135">Activités liées à la comptabilité</span><span class="sxs-lookup"><span data-stu-id="345c1-135">General Ledger Activities</span></span> | <span data-ttu-id="345c1-136">Montants des transactions pour la comptabilité</span><span class="sxs-lookup"><span data-stu-id="345c1-136">Transaction amounts for the general ledger</span></span>                                       |
| <span data-ttu-id="345c1-137">Activités liées au budget</span><span class="sxs-lookup"><span data-stu-id="345c1-137">Budget Activities</span></span>         | <span data-ttu-id="345c1-138">Montants des transactions pour le registre budgétaire</span><span class="sxs-lookup"><span data-stu-id="345c1-138">Transaction amounts for the budget register</span></span>                                      |
| <span data-ttu-id="345c1-139">Comptes principaux</span><span class="sxs-lookup"><span data-stu-id="345c1-139">Main Accounts</span></span>             | <span data-ttu-id="345c1-140">Comptes principaux en fonction desquels filtrer les états</span><span class="sxs-lookup"><span data-stu-id="345c1-140">Main accounts to filter reports by</span></span>                                               |
| <span data-ttu-id="345c1-141">Calendriers fiscaux</span><span class="sxs-lookup"><span data-stu-id="345c1-141">Fiscal Calendars</span></span>          | <span data-ttu-id="345c1-142">Calendriers fiscaux en fonction desquels filtrer les états</span><span class="sxs-lookup"><span data-stu-id="345c1-142">Fiscal calendars to filter reports by</span></span>                                            |
| <span data-ttu-id="345c1-143">Comptabilités</span><span class="sxs-lookup"><span data-stu-id="345c1-143">Ledgers</span></span>                   | <span data-ttu-id="345c1-144">Comptabilité permettant de filtrer l'état dans la comptabilité actuelle</span><span class="sxs-lookup"><span data-stu-id="345c1-144">Ledgers that can be used to filter the report to the current ledger</span></span>              |
| <span data-ttu-id="345c1-145">Codes budgétaires</span><span class="sxs-lookup"><span data-stu-id="345c1-145">Budget Codes</span></span>              | <span data-ttu-id="345c1-146">Codes budgétaires selon lesquels filtrer les états</span><span class="sxs-lookup"><span data-stu-id="345c1-146">Budget codes to filter reports by</span></span>                                                |
| <span data-ttu-id="345c1-147">Entités juridiques</span><span class="sxs-lookup"><span data-stu-id="345c1-147">Legal Entities</span></span>            | <span data-ttu-id="345c1-148">Les entités juridiques permettant de filtrer l'état dans l'entité juridique actuelle</span><span class="sxs-lookup"><span data-stu-id="345c1-148">Legal entities that can be used to filter the report to the current legal entity</span></span> |
