---
title: "Contenu Power BI Comparatif Réel/Budget"
description: "Cette rubrique décrit le contenu Power BI Comparatif Réel/Budget. Elle explique également comment accéder aux états inclus dans le contenu, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu."
author: ryansandness
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application user, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 6e64337f19600b18320550d91c134949c33af7b0
ms.openlocfilehash: 2a0ad5af4e4d7da09690331dc9d1a51d2e97a664
ms.contentlocale: fr-fr
ms.lasthandoff: 12/01/2017

---

# <a name="actual-vs-budget-power-bi-content"></a><span data-ttu-id="35d6f-104">Contenu Power BI Comparatif Réel/Budget</span><span class="sxs-lookup"><span data-stu-id="35d6f-104">Actual vs budget Power BI content</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="35d6f-105">Cette rubrique décrit le contenu Power BI **Comparatif Réel/Budget**.</span><span class="sxs-lookup"><span data-stu-id="35d6f-105">This topic describes the **Actual vs budget** Microsoft Power BI content.</span></span> <span data-ttu-id="35d6f-106">Elle explique également comment accéder aux états Power BI, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.</span><span class="sxs-lookup"><span data-stu-id="35d6f-106">It explains how to access the Power BI reports, and provides information about the data model and entities that were used to build the content.</span></span> 

# <a name="overview"></a><span data-ttu-id="35d6f-107">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="35d6f-107">Overview</span></span>

<span data-ttu-id="35d6f-108">Le contenu Power BI **Comparatif Réel/Budget** a été créé pour les personnes chargées de surveiller le comparatif des performances de budget dans leur organisation.</span><span class="sxs-lookup"><span data-stu-id="35d6f-108">The **Actual vs budget** Power BI content was created for individuals who are responsible for monitoring actual versus budget performance in their organization.</span></span> <span data-ttu-id="35d6f-109">Le contenu Power BI **Comparatif Réel/Budget** fournit une visibilité dans les écarts de budget.</span><span class="sxs-lookup"><span data-stu-id="35d6f-109">The **Actual vs budget** Power BI content provides visibility into your budget variances.</span></span> <span data-ttu-id="35d6f-110">Vous pouvez analyser le budget de l'année en cours par catégorie de compte, code budgétaire, compte principal, description de compte principal ou période fiscale pour obtenir une meilleure compréhension de la cause de tous les écarts.</span><span class="sxs-lookup"><span data-stu-id="35d6f-110">You can analyze budget for the current year by account category, budget code, main account, main account descriptions, or fiscal period to get a better understanding of the cause of any variances.</span></span> 

# <a name="accessing-the-power-bi-content"></a><span data-ttu-id="35d6f-111">Accès au contenu Power BI</span><span class="sxs-lookup"><span data-stu-id="35d6f-111">Accessing the Power BI content</span></span>
<span data-ttu-id="35d6f-112">Les états du contenu Power BI **Comparatif Réel/Budget** s'affichent dans les espaces de travail **Budget comptable et prévisions** et **CFO**.</span><span class="sxs-lookup"><span data-stu-id="35d6f-112">Reports from the **Actual vs budget** Power BI content are shown in the **Ledger budget and forecasts** and **CFO** workspaces.</span></span>

# <a name="reports-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="35d6f-113">États inclus dans le contenu Power BI</span><span class="sxs-lookup"><span data-stu-id="35d6f-113">Reports that are included in the Power BI content</span></span>
<span data-ttu-id="35d6f-114">Le tableau suivant fournit des détails sur les mesures disponibles sur chaque page d'état du contenu Power BI **Comparatif Réel/Budget**.</span><span class="sxs-lookup"><span data-stu-id="35d6f-114">The following table provides details about the metrics that are found on each report page in the **Actual vs budget** Power BI content.</span></span>

| <span data-ttu-id="35d6f-115">Etat</span><span class="sxs-lookup"><span data-stu-id="35d6f-115">Report</span></span>                      | <span data-ttu-id="35d6f-116">Métriques</span><span class="sxs-lookup"><span data-stu-id="35d6f-116">Metrics</span></span> |
|-----------------------------|---------|
| <span data-ttu-id="35d6f-117">Dépenses - comparatif Réel/Budget</span><span class="sxs-lookup"><span data-stu-id="35d6f-117">Expenses - Actual vs budget</span></span> | <ul><li><span data-ttu-id="35d6f-118">Dépenses totales de cette année</span><span class="sxs-lookup"><span data-stu-id="35d6f-118">Total expenses this year</span></span></li><li><span data-ttu-id="35d6f-119">Dépenses totales de cette année</span><span class="sxs-lookup"><span data-stu-id="35d6f-119">Budget total expenses this year</span></span></li></ul> |
| <span data-ttu-id="35d6f-120">Produit - Comparatif Réel/Budget</span><span class="sxs-lookup"><span data-stu-id="35d6f-120">Revenue - Actual vs budget</span></span>  | <ul><li><span data-ttu-id="35d6f-121">Produit total de cette année</span><span class="sxs-lookup"><span data-stu-id="35d6f-121">Total revenue this year</span></span></li><li><span data-ttu-id="35d6f-122">Produit total basé sur le budget de cette année</span><span class="sxs-lookup"><span data-stu-id="35d6f-122">Budget total revenue this year</span></span></li><ul> |
| <span data-ttu-id="35d6f-123">Dépense</span><span class="sxs-lookup"><span data-stu-id="35d6f-123">Expense</span></span>                     | <ul><li><span data-ttu-id="35d6f-124">Dépenses totales de cette année</span><span class="sxs-lookup"><span data-stu-id="35d6f-124">Total expenses this year</span></span></li><li><span data-ttu-id="35d6f-125">Objectif des dépenses basées sur le budget</span><span class="sxs-lookup"><span data-stu-id="35d6f-125">Goal for expenses based on budget</span></span> </li><ul> |
| <span data-ttu-id="35d6f-126">Produit</span><span class="sxs-lookup"><span data-stu-id="35d6f-126">Revenue</span></span>                     | <ul><li><span data-ttu-id="35d6f-127">Produit total de cette année</span><span class="sxs-lookup"><span data-stu-id="35d6f-127">Total revenue this year</span></span></li><li><span data-ttu-id="35d6f-128">Objectif des produits basés sur le budget</span><span class="sxs-lookup"><span data-stu-id="35d6f-128">Goal for revenue based on budget</span></span> </li><ul> |
| <span data-ttu-id="35d6f-129">Revenu net</span><span class="sxs-lookup"><span data-stu-id="35d6f-129">Net income</span></span>                  | <ul><li><span data-ttu-id="35d6f-130">Revenu net de cette année</span><span class="sxs-lookup"><span data-stu-id="35d6f-130">Net income this year</span></span></li><li><span data-ttu-id="35d6f-131">Objectif du revenu net basé sur le budget</span><span class="sxs-lookup"><span data-stu-id="35d6f-131">Goal for net income based on budget</span></span> </li><ul> |

## <a name="extending-the-power-bi-content"></a><span data-ttu-id="35d6f-132">Extension du contenu Power BI</span><span class="sxs-lookup"><span data-stu-id="35d6f-132">Extending the Power BI content</span></span>
<span data-ttu-id="35d6f-133">Grâce aux packs de contenu disponibles dans Microsoft Dynamics Lifecycle Services (LCS), vous pouvez fournir une analyse approfondie aux personnes qui ne se connectent pas à Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="35d6f-133">By using the content packs that are available in Microsoft Dynamics Lifecycle Services (LCS), you can provide great analytics to people who don't sign in to Microsoft Dynamics 365.</span></span> <span data-ttu-id="35d6f-134">Vous pouvez modifier ces packs de contenu pour qu'ils permettent d'inclure d'autres rapports ou visuels, et de publier les packs de contenu via votre locataire Power BI.com pour analyse.</span><span class="sxs-lookup"><span data-stu-id="35d6f-134">You can modify these content packs so that they include other reports or visuals, and then publish the content packs to your Power BI.com tenant for analysis.</span></span> 

<span data-ttu-id="35d6f-135">Le contenu Power BI **Comparatif Réel/Budget** se trouve dans la bibliothèque de ressources partagées dans LCS.</span><span class="sxs-lookup"><span data-stu-id="35d6f-135">You can find the **Actual vs budget** Power BI content in the Shared assets library in LCS.</span></span> <span data-ttu-id="35d6f-136">Pour savoir comment télécharger le contenu et l'implémenter dans votre organisation, voir [Contenu Power BI dans LCS de Microsoft et de vos partenaires](power-bi-content-microsoft-partners.md).</span><span class="sxs-lookup"><span data-stu-id="35d6f-136">For more information about how to download the content and implement it in your organization, see [Power BI content in LCS from Microsoft and your partners](power-bi-content-microsoft-partners.md).</span></span> <span data-ttu-id="35d6f-137">Pour visionner une démonstration sur l'implémentation du contenu Power BI, voir la présentation Office Mix [Contenu Power BI de Microsoft et de vos partenaires dans Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office Mix.</span><span class="sxs-lookup"><span data-stu-id="35d6f-137">To watch a demo that shows how to implement the Power BI content, see the [Power BI content from Microsoft and your partners in Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office Mix.</span></span>

# <a name="understanding-the-data-model-and-entities"></a><span data-ttu-id="35d6f-138">Compréhension du modèle de données et des entités</span><span class="sxs-lookup"><span data-stu-id="35d6f-138">Understanding the data model and entities</span></span>

| <span data-ttu-id="35d6f-139">Entité</span><span class="sxs-lookup"><span data-stu-id="35d6f-139">Entity</span></span>                    | <span data-ttu-id="35d6f-140">Sommaire</span><span class="sxs-lookup"><span data-stu-id="35d6f-140">Contents</span></span> |
|---------------------------|----------|
| <span data-ttu-id="35d6f-141">Activités liées à la comptabilité</span><span class="sxs-lookup"><span data-stu-id="35d6f-141">General Ledger Activities</span></span> | <span data-ttu-id="35d6f-142">Montants des transactions pour la comptabilité</span><span class="sxs-lookup"><span data-stu-id="35d6f-142">Transaction amounts for the general ledger</span></span> |
| <span data-ttu-id="35d6f-143">Activités liées au budget</span><span class="sxs-lookup"><span data-stu-id="35d6f-143">Budget Activities</span></span>         | <span data-ttu-id="35d6f-144">Montants des transactions pour le registre budgétaire</span><span class="sxs-lookup"><span data-stu-id="35d6f-144">Transaction amounts for the budget register</span></span> |
| <span data-ttu-id="35d6f-145">Comptes principaux</span><span class="sxs-lookup"><span data-stu-id="35d6f-145">Main Accounts</span></span>             | <span data-ttu-id="35d6f-146">Comptes principaux en fonction desquels filtrer les états</span><span class="sxs-lookup"><span data-stu-id="35d6f-146">Main accounts to filter reports by</span></span> |
| <span data-ttu-id="35d6f-147">Calendriers fiscaux</span><span class="sxs-lookup"><span data-stu-id="35d6f-147">Fiscal Calendars</span></span>          | <span data-ttu-id="35d6f-148">Calendriers fiscaux en fonction desquels filtrer les états</span><span class="sxs-lookup"><span data-stu-id="35d6f-148">Fiscal calendars to filter reports by</span></span> |
| <span data-ttu-id="35d6f-149">Comptabilités</span><span class="sxs-lookup"><span data-stu-id="35d6f-149">Ledgers</span></span>                   | <span data-ttu-id="35d6f-150">Comptabilité permettant de filtrer l'état dans la comptabilité actuelle</span><span class="sxs-lookup"><span data-stu-id="35d6f-150">Ledgers that can be used to filter the report to the current ledger</span></span> |
| <span data-ttu-id="35d6f-151">Codes budgétaires</span><span class="sxs-lookup"><span data-stu-id="35d6f-151">Budget Codes</span></span>              | <span data-ttu-id="35d6f-152">Codes budgétaires selon lesquels filtrer les états</span><span class="sxs-lookup"><span data-stu-id="35d6f-152">Budget codes to filter reports by</span></span> |
| <span data-ttu-id="35d6f-153">Entités juridiques</span><span class="sxs-lookup"><span data-stu-id="35d6f-153">Legal Entities</span></span>            | <span data-ttu-id="35d6f-154">Les entités juridiques permettant de filtrer l'état dans l'entité juridique actuelle</span><span class="sxs-lookup"><span data-stu-id="35d6f-154">Legal entities that can be used to filter the report to the current legal entity</span></span> |

