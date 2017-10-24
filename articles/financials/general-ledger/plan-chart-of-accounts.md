---
title: Planifier votre plan de comptes
description: Cet article fournit des informations vous permettant de planifier le plan de comptes de votre organisation.
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: robinr
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 848da7ec8f4a7915f3b78945b808b564f4510434
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="plan-your-chart-of-accounts"></a><span data-ttu-id="3e373-103">Planifier votre plan de comptes</span><span class="sxs-lookup"><span data-stu-id="3e373-103">Plan your chart of accounts</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="3e373-104">Cet article fournit des informations vous permettant de planifier le plan de comptes de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3e373-104">This article provides information that will help you plan the chart of accounts for your organization.</span></span>

<span data-ttu-id="3e373-105">Pour suivre et tenir à jour les informations financières dans une organisation, vous pouvez paramétrer un plan de comptes.</span><span class="sxs-lookup"><span data-stu-id="3e373-105">To track and maintain financial information in an organization, you can set up a chart of accounts.</span></span> <span data-ttu-id="3e373-106">Un plan de comptes est un ensemble de comptes qui définit une structure financière.</span><span class="sxs-lookup"><span data-stu-id="3e373-106">A chart of accounts is a collection of accounts that define a financial framework.</span></span> <span data-ttu-id="3e373-107">Pour suivre de façon plus approfondie les transactions dans ces comptes, vous pouvez ajouter des segments (appelés dimensions financières).</span><span class="sxs-lookup"><span data-stu-id="3e373-107">To further track the transactions in these accounts, you can add segments, which are known as financial dimensions.</span></span> <span data-ttu-id="3e373-108">Par exemple, un compte de dépenses peut inclure les dimensions financières nommées Département, Centre de coûts et Objectif.</span><span class="sxs-lookup"><span data-stu-id="3e373-108">For example, an expense account might include financial dimensions that are named Department, Cost center, and Purpose.</span></span> <span data-ttu-id="3e373-109">Des règles définies par l'utilisateur (appelées structures de compte et règles avancées), déterminent l'association des dimensions financières aux comptes principaux et aux autres dimensions financières, ainsi que les modalités de saisie des transactions.</span><span class="sxs-lookup"><span data-stu-id="3e373-109">User-defined rules, which are known as account structures and advanced rules, determine how financial dimensions are attached to the main accounts and other financial dimensions, and also how transactions are entered.</span></span> 

<span data-ttu-id="3e373-110">Le plan de comptes est une liste structurée des comptes généraux d'une entité juridique.</span><span class="sxs-lookup"><span data-stu-id="3e373-110">The chart of accounts is a structured list of a legal entity’s general ledger accounts.</span></span> <span data-ttu-id="3e373-111">La liste permet de préparer les états financiers pour les administrations et les propriétaires.</span><span class="sxs-lookup"><span data-stu-id="3e373-111">The list is used to prepare financial reports for authorities and owners.</span></span> <span data-ttu-id="3e373-112">Les comptes sont regroupés en types de comptes, puis rassemblés dans de plus grandes catégories.</span><span class="sxs-lookup"><span data-stu-id="3e373-112">The accounts are grouped into types of accounts and then further aggregated into larger categories.</span></span> <span data-ttu-id="3e373-113">Au niveau le plus général, les comptes sont regroupés par coûts et produits (comptes d'exploitation) et actifs et passifs (comptes de bilan).</span><span class="sxs-lookup"><span data-stu-id="3e373-113">At the most general level, the accounts are grouped as revenues and costs (operating accounts), and assets and liabilities (balance accounts).</span></span> 

<span data-ttu-id="3e373-114">Un plan de comptes peut être partagé et utilisé par les entités juridiques d'une organisation.</span><span class="sxs-lookup"><span data-stu-id="3e373-114">A chart of accounts can be shared and used by any legal entity in an organization.</span></span> <span data-ttu-id="3e373-115">Le plan de comptes qui est utilisé par une entité juridique est défini sur la page **Comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="3e373-115">The chart of accounts that is used by a legal entity is defined on the **Ledger** page.</span></span> 

<span data-ttu-id="3e373-116">Voici des facteurs dont vous devez tenir compte lorsque vous planifiez la structure du plan de comptes pour votre organisation :</span><span class="sxs-lookup"><span data-stu-id="3e373-116">Here are some of the factors that you must consider when you plan the structure of the chart of accounts for your organization:</span></span>

-   <span data-ttu-id="3e373-117">les conditions de génération d'états du pays ou de la région où est basée la société ;</span><span class="sxs-lookup"><span data-stu-id="3e373-117">The reporting requirements of the country/region where your organization is based</span></span>
-   <span data-ttu-id="3e373-118">les conditions de génération d'états de votre entité juridique ;</span><span class="sxs-lookup"><span data-stu-id="3e373-118">The reporting requirements of your legal entity</span></span>
-   <span data-ttu-id="3e373-119">le degré de spécification requis, à la fois pour les organisations externes et votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3e373-119">The degree of specification that is required, both for both external organizations and for your organization</span></span>

<span data-ttu-id="3e373-120">Créez le plan de comptes dans la page **Plan de comptes**.</span><span class="sxs-lookup"><span data-stu-id="3e373-120">Create the chart of accounts on the **Chart of accounts** page.</span></span> <span data-ttu-id="3e373-121">Les comptes principaux peuvent être créés à partir de la page **Plan de comptes** ou de la page **Comptes principaux**.</span><span class="sxs-lookup"><span data-stu-id="3e373-121">Main accounts can be created from the **Chart of accounts** page or the **Main accounts** page.</span></span> <span data-ttu-id="3e373-122">Vos comptes principaux ne doivent pas utiliser de caractères spéciaux utilisés comme séparateurs de plan de comptes.</span><span class="sxs-lookup"><span data-stu-id="3e373-122">Your main accounts shouldn't use any special characters that are used as chart of accounts delimiters.</span></span> <span data-ttu-id="3e373-123">Si vous avez un caractère spécial qui est identique à votre séparateur de plan de comptes, il peut y avoir une instabilité, ou la nécessité de toujours utiliser des recherches ou le menu volant pour saisir le compte et les combinaisons de dimensions.</span><span class="sxs-lookup"><span data-stu-id="3e373-123">If you do have a special character that is the same as your chart of accounts delimiter, you may experience instability, or the need to always use lookups or the flyout when entering account and dimension combinations.</span></span> <span data-ttu-id="3e373-124">Pour plus d'informations, voir [Créer un compte principal](tasks/create-account-structures.md).</span><span class="sxs-lookup"><span data-stu-id="3e373-124">For more information, see [Create a main account](tasks/create-account-structures.md).</span></span>


<span data-ttu-id="3e373-125">Il est préférable de lier les comptes principaux aux catégories de compte principal, afin de pouvoir tirer profit des états financiers par défaut sans devoir apporter des modifications.</span><span class="sxs-lookup"><span data-stu-id="3e373-125">It's a good idea to link the main accounts to main account categories, so that you can take advantage of the default financial reports without having to make any modifications.</span></span> <span data-ttu-id="3e373-126">Par conséquent, vous pouvez concevoir et tenir à jour les états plus rapidement et plus facilement.</span><span class="sxs-lookup"><span data-stu-id="3e373-126">Therefore, you can more quickly and easily design and maintain reports.</span></span> 

<span data-ttu-id="3e373-127">Utilisez la page **Configurer les structures de compte** pour créer des structures de compte.</span><span class="sxs-lookup"><span data-stu-id="3e373-127">Use the **Configure account structures** page to create account structures.</span></span> <span data-ttu-id="3e373-128">Les structures de compte définissent les combinaisons valides.</span><span class="sxs-lookup"><span data-stu-id="3e373-128">Account structures define valid combinations.</span></span> <span data-ttu-id="3e373-129">Les combinaisons, associées aux comptes principaux, forment un plan de comptes.</span><span class="sxs-lookup"><span data-stu-id="3e373-129">The combinations, together with main accounts, form a chart of accounts.</span></span>  <span data-ttu-id="3e373-130">Pour plus d'informations, voir [Créer des structures de compte](tasks/create-main-account.md).</span><span class="sxs-lookup"><span data-stu-id="3e373-130">For more information, see [Create account structures](tasks/create-main-account.md).</span></span>

<span data-ttu-id="3e373-131">**Remplacements des entités juridiques**</span><span class="sxs-lookup"><span data-stu-id="3e373-131">**Legal entity overrides**</span></span> 

<span data-ttu-id="3e373-132">Seuls certains comptes principaux sont valides pour toutes les entités juridiques et certaines peuvent être appropriées uniquement pour une période spécifique.</span><span class="sxs-lookup"><span data-stu-id="3e373-132">Not all main accounts are valid for all legal entities and some may only be relevant for a specific time period.</span></span> <span data-ttu-id="3e373-133">Dans ce scénario, la section Remplacements des entités juridiques peut être utilisée pour identifier les sociétés pour lesquelles le compte principal doit être suspendu, le propriétaire et la période d'activité de la dimension.</span><span class="sxs-lookup"><span data-stu-id="3e373-133">In this scenario the Legal entity overrides section can be used to identify which companies the main account should be suspended for, who the owner is and the time period the dimension is active.</span></span> <span data-ttu-id="3e373-134">Les remplacements au niveau partagé ne peuvent pas être plus restrictifs que les remplacements au niveau de l'entité juridique.</span><span class="sxs-lookup"><span data-stu-id="3e373-134">The overrides at the shared level cannot be more restrictive than the overrides at the legal entity level.</span></span>

<span data-ttu-id="3e373-135">Pour plus d'informations, voir les rubriques suivantes : [Dimensions financières](financial-dimensions.md)
[Créer et affecter des structures de règle avancées](tasks/create-assign-advanced-rule-structures.md)</span><span class="sxs-lookup"><span data-stu-id="3e373-135">For more information, see the following topics: [Financial dimensions](financial-dimensions.md)
[Create and assign advanced rule structures](tasks/create-assign-advanced-rule-structures.md)</span></span>




