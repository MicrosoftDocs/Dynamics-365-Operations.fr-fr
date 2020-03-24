---
title: Comptabilité intégrée
description: Cette rubrique décrit l'intégration des données de comptabilité entre Finance and Operations et d'autres applications Dynamics 365 à l'aide de Common Data Service.
author: robinarh
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ''
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: d9bcec1d4bb0207a2c3e0d46f7661b666fea3736
ms.sourcegitcommit: 48c39c0c0949fe48b3536d9d2d0e451d561ff5c6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2020
ms.locfileid: "3112212"
---
# <a name="integrated-ledger"></a><span data-ttu-id="c8a94-103">Comptabilité intégrée</span><span class="sxs-lookup"><span data-stu-id="c8a94-103">Integrated ledger</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="c8a94-104">Dans une application d'entreprise, les données de comptabilité définissent la configuration de base pour le mode de fonctionnement d'une entreprise.</span><span class="sxs-lookup"><span data-stu-id="c8a94-104">In a business application, ledger data defines the core set up for how a company does business.</span></span> <span data-ttu-id="c8a94-105">Par exemple, les données de comptabilité décrivent l'exercice que suit la société, les devises qu'elle traite et les comptes qu'elle utilise.</span><span class="sxs-lookup"><span data-stu-id="c8a94-105">For example, ledger data describes the fiscal year the company follows, the currencies it transacts in, and the accounts it uses.</span></span> <span data-ttu-id="c8a94-106">Cette rubrique décrit l'intégration de ces données financières de base.</span><span class="sxs-lookup"><span data-stu-id="c8a94-106">This topic describes the integration of this core financial data.</span></span>

## <a name="templates"></a><span data-ttu-id="c8a94-107">Modèles</span><span class="sxs-lookup"><span data-stu-id="c8a94-107">Templates</span></span>

<span data-ttu-id="c8a94-108">Les données comptables comprennent un ensemble de mappages d'entités financières de base qui fonctionnent ensemble pendant l'interaction des données client, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="c8a94-108">Ledger data includes a collection of core financial entity maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="c8a94-109">Applications Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c8a94-109">Finance and Operations apps</span></span>      | <span data-ttu-id="c8a94-110">Application pilotée par modèle dans Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c8a94-110">Model-driven app in Dynamics 365</span></span> | <span data-ttu-id="c8a94-111">Description </span><span class="sxs-lookup"><span data-stu-id="c8a94-111">Description</span></span>
---------------------------------|----------------------------------|------------
<span data-ttu-id="c8a94-112">Devises</span><span class="sxs-lookup"><span data-stu-id="c8a94-112">Currencies</span></span>                       | <span data-ttu-id="c8a94-113">transactioncurrencies</span><span class="sxs-lookup"><span data-stu-id="c8a94-113">transactioncurrencies</span></span>            |
<span data-ttu-id="c8a94-114">FiscalCalendar</span><span class="sxs-lookup"><span data-stu-id="c8a94-114">FiscalCalendar</span></span>                   | <span data-ttu-id="c8a94-115">msdyn\_fiscalcalendars</span><span class="sxs-lookup"><span data-stu-id="c8a94-115">msdyn\_fiscalcalendars</span></span>        |
<span data-ttu-id="c8a94-116">FiscalCalendarYear</span><span class="sxs-lookup"><span data-stu-id="c8a94-116">FiscalCalendarYear</span></span>               | <span data-ttu-id="c8a94-117">msdyn\_fiscalcalendaryears</span><span class="sxs-lookup"><span data-stu-id="c8a94-117">msdyn\_fiscalcalendaryears</span></span>        |
<span data-ttu-id="c8a94-118">ExchRateType</span><span class="sxs-lookup"><span data-stu-id="c8a94-118">ExchRateType</span></span>                     | <span data-ttu-id="c8a94-119">msdyn\_exchangeratetypes</span><span class="sxs-lookup"><span data-stu-id="c8a94-119">msdyn\_exchangeratetypes</span></span>        |
<span data-ttu-id="c8a94-120">ExchangeRateCurrencyPair</span><span class="sxs-lookup"><span data-stu-id="c8a94-120">ExchangeRateCurrencyPair</span></span>         | <span data-ttu-id="c8a94-121">msdyn\_currencyexchangeratepairs</span><span class="sxs-lookup"><span data-stu-id="c8a94-121">msdyn\_currencyexchangeratepairs</span></span>        |
<span data-ttu-id="c8a94-122">FiscalPeriodEntity</span><span class="sxs-lookup"><span data-stu-id="c8a94-122">FiscalPeriodEntity</span></span>               | <span data-ttu-id="c8a94-123">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="c8a94-123">msdyn\_fiscalcalendarperiods</span></span>        |
<span data-ttu-id="c8a94-124">MainAccountCategory</span><span class="sxs-lookup"><span data-stu-id="c8a94-124">MainAccountCategory</span></span>              | <span data-ttu-id="c8a94-125">msdyn\_mainaccountcategory</span><span class="sxs-lookup"><span data-stu-id="c8a94-125">msdyn\_mainaccountcategory</span></span>        |
<span data-ttu-id="c8a94-126">MainAccount</span><span class="sxs-lookup"><span data-stu-id="c8a94-126">MainAccount</span></span>                      | <span data-ttu-id="c8a94-127">msdyn\_mainaccounts</span><span class="sxs-lookup"><span data-stu-id="c8a94-127">msdyn\_mainaccounts</span></span>        |
<span data-ttu-id="c8a94-128">Comptabilité</span><span class="sxs-lookup"><span data-stu-id="c8a94-128">Ledger</span></span>                           | <span data-ttu-id="c8a94-129">msdyn\_ledgers</span><span class="sxs-lookup"><span data-stu-id="c8a94-129">msdyn\_ledgers</span></span>        |
<span data-ttu-id="c8a94-130">ExchangeRates</span><span class="sxs-lookup"><span data-stu-id="c8a94-130">ExchangeRates</span></span>                    | <span data-ttu-id="c8a94-131">msdyn\_currencyexchangerates</span><span class="sxs-lookup"><span data-stu-id="c8a94-131">msdyn\_currencyexchangerates</span></span>        |
<span data-ttu-id="c8a94-132">FinancialCalendarPeriod</span><span class="sxs-lookup"><span data-stu-id="c8a94-132">FinancialCalendarPeriod</span></span>          | <span data-ttu-id="c8a94-133">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="c8a94-133">msdyn\_fiscalcalendarperiods</span></span>        |
<span data-ttu-id="c8a94-134">DimensionAttributeEntity</span><span class="sxs-lookup"><span data-stu-id="c8a94-134">DimensionAttributeEntity</span></span>         | <span data-ttu-id="c8a94-135">msdyn\_dimensionattributes</span><span class="sxs-lookup"><span data-stu-id="c8a94-135">msdyn\_dimensionattributes</span></span>        |
<span data-ttu-id="c8a94-136">DimensionIntegrationFormatEntity</span><span class="sxs-lookup"><span data-stu-id="c8a94-136">DimensionIntegrationFormatEntity</span></span> | <span data-ttu-id="c8a94-137">msdyn\_financialdimensionformats</span><span class="sxs-lookup"><span data-stu-id="c8a94-137">msdyn\_financialdimensionformats</span></span>        |
<span data-ttu-id="c8a94-138">LedgerChartOfAccounts</span><span class="sxs-lookup"><span data-stu-id="c8a94-138">LedgerChartOfAccounts</span></span>            | <span data-ttu-id="c8a94-139">msdyn\_chartofaccounts</span><span class="sxs-lookup"><span data-stu-id="c8a94-139">msdyn\_chartofaccounts</span></span>        |


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Currency](includes/Currencies-transactioncurrencies.md)]

[!include [Fiscal calendar](includes/FiscalCalendar-msdyn-fiscalcalendars.md)]

[!include [Fiscal calendar year](includes/FiscalCalendarYear-msdyn-fiscalcalendaryears.md)]

[!include [Exchange rate types](includes/ExchRateType-msdyn-exchangeratetypes.md)]

[!include [Exchange rate pair](includes/ExchangeRateCurrencyPair-msdyn-currencyexchangeratepairs.md)]

[!include [Ledger fiscal periods](includes/FiscalPeriodEntity-msdyn-fiscalcalendarperiods.md)]

[!include [Main account category](includes/MainAccountCategory-msdyn-mainaccountcategory.md)]

[!include [Main account](includes/MainAccount-msdyn-mainaccounts.md)]

[!include [Ledger](includes/Ledger-msdyn-ledgers.md)]

[!include [Exchange rates](includes/ExchangeRates-msdyn-currencyexchangerates.md)]

[!include [Financial Calendar Period](includes/FiscalPeriodEntity-msdyn-fiscalcalendarperiods.md)]

[!include [Dimension attribute](includes/DimensionAttributeEntity-msdyn-dimensionattributes.md)]

[!include [Dimension integration format](includes/DimensionIntegrationFormatEntity-msdyn-financialdimensionformats.md)]

[!include [Chart Of Account](includes/LedgerChartOfAccounts-msdyn-chartofaccounts.md)]




