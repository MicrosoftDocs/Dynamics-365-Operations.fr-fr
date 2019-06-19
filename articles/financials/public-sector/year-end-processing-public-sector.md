---
title: Traitement de fin d'exercice dans le secteur public
description: Cet article fournit des informations sur le processus de fin d'exercice pour des organisations du secteur public.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchYearEndClose
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 19601
ms.assetid: ba9a7abc-bd18-47c2-b745-96cdcec8ac98
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b9a89bd38feac2e580c3d1511d3bee8eca04115d
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1557121"
---
# <a name="year-end-processing-in-the-public-sector"></a><span data-ttu-id="8c16c-103">Traitement de fin d'exercice dans le secteur public</span><span class="sxs-lookup"><span data-stu-id="8c16c-103">Year-end processing in the public sector</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8c16c-104">Cet article fournit des informations sur le processus de fin d'exercice pour des organisations du secteur public.</span><span class="sxs-lookup"><span data-stu-id="8c16c-104">This article provides information about year-end processing for a public sector organizations.</span></span>

<span data-ttu-id="8c16c-105">Cette rubrique décrit la fonctionnalité de fin d'exercice disponible pour le secteur public.</span><span class="sxs-lookup"><span data-stu-id="8c16c-105">This topic describes the year-end functionality available for the public sector.</span></span> <span data-ttu-id="8c16c-106">À la fin d'un exercice, vous devez générer des transactions de clôture et préparer vos comptes pour l'exercice suivant.</span><span class="sxs-lookup"><span data-stu-id="8c16c-106">At the end of a fiscal year, you must generate closing transactions and prepare your accounts for the next fiscal year.</span></span>  <span data-ttu-id="8c16c-107">Les clients du secteur public ont les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="8c16c-107">Public sector clients have the following capabilities:</span></span>

-   <span data-ttu-id="8c16c-108">Sélectionner des comptes par fonds pour la clôture de fin d'exercice.</span><span class="sxs-lookup"><span data-stu-id="8c16c-108">Select accounts by fund for year-end closing.</span></span>
-   <span data-ttu-id="8c16c-109">Fermer les fonds à différents comptes.</span><span class="sxs-lookup"><span data-stu-id="8c16c-109">Close funds to different accounts.</span></span> <span data-ttu-id="8c16c-110">Par exemple, vous pouvez clôturer les comptes de gestion associés aux fonds gouvernementaux pour financer les soldes.</span><span class="sxs-lookup"><span data-stu-id="8c16c-110">For example, you can close nominal accounts that are associated with governmental funds to fund balances.</span></span> <span data-ttu-id="8c16c-111">Vous pouvez également clôturer les comptes de gestion associés aux fonds propriétaires aux bénéfices non répartis.</span><span class="sxs-lookup"><span data-stu-id="8c16c-111">You can also close nominal accounts that are associated with proprietary funds to retained earnings.</span></span>
-   <span data-ttu-id="8c16c-112">Paramétrer clôture de fin d'exercice pour tous les fonds et non-fonds.</span><span class="sxs-lookup"><span data-stu-id="8c16c-112">Set up year-end closing for all funds and non-funds.</span></span> <span data-ttu-id="8c16c-113">Les non-fonds ne disposent pas de dimension de fonds dans la structure de compte.</span><span class="sxs-lookup"><span data-stu-id="8c16c-113">Non-funds don't have a fund dimension in the account structure.</span></span>
-   <span data-ttu-id="8c16c-114">Paramétrer plusieurs périodes de clôture pour séparer différents types d'entrées de clôture, telles qu'une clôture générale de fin d'exercice et des ajustements d'audit.</span><span class="sxs-lookup"><span data-stu-id="8c16c-114">Set up multiple closing periods to segregate different types of closing entries, such as general year-end closing and audit adjustments.</span></span>

## <a name="can-the-year-end-process-be-run-more-than-one-time-on-the-same-data"></a><span data-ttu-id="8c16c-115">Le processus de fin d'exercice peut-il être exécuté plusieurs fois sur les mêmes données ?</span><span class="sxs-lookup"><span data-stu-id="8c16c-115">Can the year-end process be run more than one time on the same data?</span></span>
<span data-ttu-id="8c16c-116">Oui, le processus de fin d'exercice peut être exécuté plusieurs fois pour le même ensemble de données.</span><span class="sxs-lookup"><span data-stu-id="8c16c-116">Yes, the year-end process can be run multiple times for the same set of data.</span></span> <span data-ttu-id="8c16c-117">Généralement, si des transactions supplémentaires doivent être traitées après l'exécution d'un processus de fin d'exercice comptable, le processus de fin d'exercice peut être exécuté de nouveau pour clôturer les comptes de gestion et pour paramétrer correctement les soldes d'ouverture dans la nouvelle année.</span><span class="sxs-lookup"><span data-stu-id="8c16c-117">Typically, if additional transactions must be processed after a general ledger year-end process is run, the year-end process can be run again to close out the nominal accounts and correctly set the opening balances in the new year.</span></span>

## <a name="how-do-i-set-up-funds-for-year-end-processing"></a><span data-ttu-id="8c16c-118">Comment paramétrer des fonds pour le traitement de fin d'exercice ?</span><span class="sxs-lookup"><span data-stu-id="8c16c-118">How do I set up funds for year-end processing?</span></span>
<span data-ttu-id="8c16c-119">Le traitement de fin d'exercice des soldes comptables est contrôlé par les paramètres de configuration de fonds dans deux endroits :</span><span class="sxs-lookup"><span data-stu-id="8c16c-119">Year-end processing of general ledger balances is controlled by fund configuration settings in two places:</span></span>

-   <span data-ttu-id="8c16c-120">Le processus de fin d'exercice visant la clôture des soldes comptables de l'année passée et le paramétrage des soldes d'ouverture dans la nouvelle année est effectué par l'intermédiaire de la page **Transactions d'ouverture**.</span><span class="sxs-lookup"><span data-stu-id="8c16c-120">The year-end process of closing ledger balances in the old year and establishing opening balances in the new year is done by using the **Opening transactions** page.</span></span> <span data-ttu-id="8c16c-121">Un fonds unique ou une plage des fonds est requis pour le traitement.</span><span class="sxs-lookup"><span data-stu-id="8c16c-121">A single fund or range of funds is required for processing.</span></span>
-   <span data-ttu-id="8c16c-122">L'option de traitement de fin d'exercice pour les engagements de commande fournisseur est définie sur la page **Processus de fin d'exercice de commande fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="8c16c-122">The year-end processing option for purchase order encumbrances is set on the **Purchase order year-end process** page.</span></span> <span data-ttu-id="8c16c-123">Vous pouvez remplacer l'option sur un fonds spécifique, à condition que les paramètres de comptabilité aient été définis pour autoriser les remplacements.</span><span class="sxs-lookup"><span data-stu-id="8c16c-123">You can override the option on a specific fund, provided that the general ledger parameters have been set to allow for overrides.</span></span> <span data-ttu-id="8c16c-124">Pour plus d'informations sur ces paramètres, voir [Comptabilité dans le secteur public](general-ledger-public-sector.md).</span><span class="sxs-lookup"><span data-stu-id="8c16c-124">To learn more about the parameter settings, see [General ledger in the public sector](general-ledger-public-sector.md).</span></span>

## <a name="how-do-i-set-up-main-accounts-for-year-end-processing"></a><span data-ttu-id="8c16c-125">Comment paramétrer des comptes principaux pour le traitement de fin d'exercice ?</span><span class="sxs-lookup"><span data-stu-id="8c16c-125">How do I set up main accounts for year-end processing?</span></span>
<span data-ttu-id="8c16c-126">Vous devez sélectionner un type de clôture pour chaque compte dans votre plan de comptes.</span><span class="sxs-lookup"><span data-stu-id="8c16c-126">You must select a close type for every account in your chart of accounts.</span></span> <span data-ttu-id="8c16c-127">Le type de clôture détermine la manière dont le processus de fin d'exercice traite ce compte principal.</span><span class="sxs-lookup"><span data-stu-id="8c16c-127">The close type determines how the year-end process handles that main account.</span></span> <span data-ttu-id="8c16c-128">Il existe quatre types de clôture :</span><span class="sxs-lookup"><span data-stu-id="8c16c-128">There are four close types:</span></span>

-   <span data-ttu-id="8c16c-129">**Réel** – Le solde est utilisé pour établir des soldes d'ouverture dans la nouvelle année.</span><span class="sxs-lookup"><span data-stu-id="8c16c-129">**Real** – The balance is used to establish opening balances in the new year.</span></span>
-   <span data-ttu-id="8c16c-130">**Nominal** – Le compte est clôturé par le processus de fin d'exercice.</span><span class="sxs-lookup"><span data-stu-id="8c16c-130">**Nominal** – The account is closed by the year-end process.</span></span>
-   <span data-ttu-id="8c16c-131">**Nominal - pas de clôture** – Le compte est géré par d'autres processus de clôture, comme les comptes d'engagement pour la clôture de commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="8c16c-131">**Nominal – no close** – The account is managed by other closing processes, such as encumbrance accounts for purchase order close.</span></span>
-   <span data-ttu-id="8c16c-132">**Non applicable** – Le compte n'est pas inclus dans le traitement de fin d'exercice.</span><span class="sxs-lookup"><span data-stu-id="8c16c-132">**Not applicable** – The account isn't included in year-end processing.</span></span>

<span data-ttu-id="8c16c-133">Les définitions de validation régissent la comptabilité qui concerne les entrées de clôture, et elles permettent également de créer des transactions d'ouverture pour la nouvelle année.</span><span class="sxs-lookup"><span data-stu-id="8c16c-133">Posting definitions govern the accounting that occurs on the closing entries, and they also help create the opening transactions for the new year.</span></span> <span data-ttu-id="8c16c-134">Pour plus d'informations, voir [Définitions de validation dans le secteur public](posting-definitions-public-sector.md).</span><span class="sxs-lookup"><span data-stu-id="8c16c-134">To learn more, see [Posting definitions in the public sector](posting-definitions-public-sector.md).</span></span>



