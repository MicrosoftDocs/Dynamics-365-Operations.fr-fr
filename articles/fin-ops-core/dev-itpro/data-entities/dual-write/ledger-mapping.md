---
title: Comptabilité intégrée
description: Cette rubrique décrit l’intégration des données de comptabilité entre Finance and Operations et d’autres applications Dynamics 365 à l’aide de Dataverse.
author: robinarh
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: rhaertle
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: f8095b0a755e40e5665d951d33ea4ce60e749165
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567694"
---
# <a name="integrated-ledger"></a><span data-ttu-id="2d2ab-103">Comptabilité intégrée</span><span class="sxs-lookup"><span data-stu-id="2d2ab-103">Integrated ledger</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="2d2ab-104">Dans une application d’entreprise, les données de comptabilité définissent la configuration de base pour le mode de fonctionnement d’une entreprise.</span><span class="sxs-lookup"><span data-stu-id="2d2ab-104">In a business application, ledger data defines the core set up for how a company does business.</span></span> <span data-ttu-id="2d2ab-105">Par exemple, les données de comptabilité décrivent l’exercice que suit la société, les devises qu’elle traite et les comptes qu’elle utilise.</span><span class="sxs-lookup"><span data-stu-id="2d2ab-105">For example, ledger data describes the fiscal year the company follows, the currencies it transacts in, and the accounts it uses.</span></span> <span data-ttu-id="2d2ab-106">Cette rubrique décrit l’intégration de ces données financières de base.</span><span class="sxs-lookup"><span data-stu-id="2d2ab-106">This topic describes the integration of this core financial data.</span></span>

## <a name="templates"></a><span data-ttu-id="2d2ab-107">Modèles</span><span class="sxs-lookup"><span data-stu-id="2d2ab-107">Templates</span></span>

<span data-ttu-id="2d2ab-108">Les données comptables comprennent un ensemble de mappages de tables financières de base qui fonctionnent ensemble pendant l’interaction des données client, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="2d2ab-108">Ledger data includes a collection of core financial table maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="2d2ab-109">Applications Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="2d2ab-109">Finance and Operations apps</span></span>      | <span data-ttu-id="2d2ab-110">Application pilotée par modèle dans Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="2d2ab-110">Model-driven app in Dynamics 365</span></span> | <span data-ttu-id="2d2ab-111">Description</span><span class="sxs-lookup"><span data-stu-id="2d2ab-111">Description</span></span>
---------------------------------|----------------------------------|------------
<span data-ttu-id="2d2ab-112">Devises</span><span class="sxs-lookup"><span data-stu-id="2d2ab-112">Currencies</span></span>                       | <span data-ttu-id="2d2ab-113">transactioncurrencies</span><span class="sxs-lookup"><span data-stu-id="2d2ab-113">transactioncurrencies</span></span>            |
<span data-ttu-id="2d2ab-114">FiscalCalendar</span><span class="sxs-lookup"><span data-stu-id="2d2ab-114">FiscalCalendar</span></span>                   | <span data-ttu-id="2d2ab-115">msdyn\_fiscalcalendars</span><span class="sxs-lookup"><span data-stu-id="2d2ab-115">msdyn\_fiscalcalendars</span></span>        |
<span data-ttu-id="2d2ab-116">FiscalCalendarYear</span><span class="sxs-lookup"><span data-stu-id="2d2ab-116">FiscalCalendarYear</span></span>               | <span data-ttu-id="2d2ab-117">msdyn\_fiscalcalendaryears</span><span class="sxs-lookup"><span data-stu-id="2d2ab-117">msdyn\_fiscalcalendaryears</span></span>        |
<span data-ttu-id="2d2ab-118">ExchRateType</span><span class="sxs-lookup"><span data-stu-id="2d2ab-118">ExchRateType</span></span>                     | <span data-ttu-id="2d2ab-119">msdyn\_exchangeratetypes</span><span class="sxs-lookup"><span data-stu-id="2d2ab-119">msdyn\_exchangeratetypes</span></span>        |
<span data-ttu-id="2d2ab-120">ExchangeRateCurrencyPair</span><span class="sxs-lookup"><span data-stu-id="2d2ab-120">ExchangeRateCurrencyPair</span></span>         | <span data-ttu-id="2d2ab-121">msdyn\_currencyexchangeratepairs</span><span class="sxs-lookup"><span data-stu-id="2d2ab-121">msdyn\_currencyexchangeratepairs</span></span>        |
<span data-ttu-id="2d2ab-122">FiscalPeriodEntity</span><span class="sxs-lookup"><span data-stu-id="2d2ab-122">FiscalPeriodEntity</span></span>               | <span data-ttu-id="2d2ab-123">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="2d2ab-123">msdyn\_fiscalcalendarperiods</span></span>        |
<span data-ttu-id="2d2ab-124">MainAccountCategory</span><span class="sxs-lookup"><span data-stu-id="2d2ab-124">MainAccountCategory</span></span>              | <span data-ttu-id="2d2ab-125">msdyn\_mainaccountcategory</span><span class="sxs-lookup"><span data-stu-id="2d2ab-125">msdyn\_mainaccountcategory</span></span>        |
<span data-ttu-id="2d2ab-126">MainAccount</span><span class="sxs-lookup"><span data-stu-id="2d2ab-126">MainAccount</span></span>                      | <span data-ttu-id="2d2ab-127">msdyn\_mainaccounts</span><span class="sxs-lookup"><span data-stu-id="2d2ab-127">msdyn\_mainaccounts</span></span>        |
<span data-ttu-id="2d2ab-128">Comptabilité</span><span class="sxs-lookup"><span data-stu-id="2d2ab-128">Ledger</span></span>                           | <span data-ttu-id="2d2ab-129">msdyn\_ledgers</span><span class="sxs-lookup"><span data-stu-id="2d2ab-129">msdyn\_ledgers</span></span>        |
<span data-ttu-id="2d2ab-130">ExchangeRates</span><span class="sxs-lookup"><span data-stu-id="2d2ab-130">ExchangeRates</span></span>                    | <span data-ttu-id="2d2ab-131">msdyn\_currencyexchangerates</span><span class="sxs-lookup"><span data-stu-id="2d2ab-131">msdyn\_currencyexchangerates</span></span>        |
<span data-ttu-id="2d2ab-132">FinancialCalendarPeriod</span><span class="sxs-lookup"><span data-stu-id="2d2ab-132">FinancialCalendarPeriod</span></span>          | <span data-ttu-id="2d2ab-133">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="2d2ab-133">msdyn\_fiscalcalendarperiods</span></span>        |
<span data-ttu-id="2d2ab-134">DimensionAttributeEntity</span><span class="sxs-lookup"><span data-stu-id="2d2ab-134">DimensionAttributeEntity</span></span>         | <span data-ttu-id="2d2ab-135">msdyn\_dimensionattributes</span><span class="sxs-lookup"><span data-stu-id="2d2ab-135">msdyn\_dimensionattributes</span></span>        |
<span data-ttu-id="2d2ab-136">DimensionIntegrationFormatEntity</span><span class="sxs-lookup"><span data-stu-id="2d2ab-136">DimensionIntegrationFormatEntity</span></span> | <span data-ttu-id="2d2ab-137">msdyn\_financialdimensionformats</span><span class="sxs-lookup"><span data-stu-id="2d2ab-137">msdyn\_financialdimensionformats</span></span>        |
<span data-ttu-id="2d2ab-138">LedgerChartOfAccounts</span><span class="sxs-lookup"><span data-stu-id="2d2ab-138">LedgerChartOfAccounts</span></span>            | <span data-ttu-id="2d2ab-139">msdyn\_chartofaccounts</span><span class="sxs-lookup"><span data-stu-id="2d2ab-139">msdyn\_chartofaccounts</span></span>        |


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Currency](includes/Currencies-transactioncurrencies.md)]

[!include [Fiscal calendar](includes/FiscalCalendar-msdyn-fiscalcalendars.md)]

[!include [Fiscal calendar year](includes/FiscalCalendarYear-msdyn-fiscalcalendaryears.md)]

[!include [Exchange rate types](includes/ExchRateType-msdyn-exchangeratetypes.md)]

[!include [Exchange rate pair](includes/ExchangeRateCurrencyPair-msdyn-currencyexchangeratepairs.md)]

[!include [Main account category](includes/MainAccountCategory-msdyn-mainaccountcategory.md)]

[!include [Main account](includes/MainAccount-msdyn-mainaccounts.md)]

[!include [Ledger](includes/Ledger-msdyn-ledgers.md)]

[!include [Exchange rates](includes/ExchangeRates-msdyn-currencyexchangerates.md)]

[!include [Financial Calendar Period](includes/FiscalPeriodEntity-msdyn-fiscalcalendarperiods.md)]

[!include [Dimension attribute](includes/DimensionAttributeEntity-msdyn-dimensionattributes.md)]

[!include [Dimension integration format](includes/DimensionIntegrationFormatEntity-msdyn-financialdimensionformats.md)]

[!include [Chart Of Account](includes/LedgerChartOfAccounts-msdyn-chartofaccounts.md)]






[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]