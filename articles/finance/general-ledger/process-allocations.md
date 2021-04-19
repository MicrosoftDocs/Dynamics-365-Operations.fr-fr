---
title: Traiter les répartitions
description: Cet article fournit des informations sur les répartitions, les options pour les traiter dans Microsoft Dynamics 365 Finance, et comment elles peuvent être utilisées dans la planification budgétaire. Les répartitions sont utilisées pour répartir les montants entre plusieurs combinaisons de compte général. Elles permettent de garantir que les dépenses sont facturées pour l’objet approprié dans la comptabilité.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount
audience: Application User
ms.reviewer: roschlom
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 30f445698eddba8bdbb2ac9a257142458fb5990f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815426"
---
# <a name="process-allocations"></a><span data-ttu-id="9035a-105">Traiter les répartitions</span><span class="sxs-lookup"><span data-stu-id="9035a-105">Process allocations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9035a-106">Cet article fournit des informations sur les répartitions, les options pour les traiter, et comment elles peuvent être utilisées dans la planification budgétaire.</span><span class="sxs-lookup"><span data-stu-id="9035a-106">This article provides information about allocations, the options for processing them, and how they can be used in budget planning.</span></span> <span data-ttu-id="9035a-107">Les répartitions sont utilisées pour répartir les montants entre plusieurs combinaisons de compte général.</span><span class="sxs-lookup"><span data-stu-id="9035a-107">Allocations are used to distribute amounts across multiple ledger account combinations.</span></span> <span data-ttu-id="9035a-108">Elles permettent de garantir que les dépenses sont facturées pour l’objet approprié dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="9035a-108">They help ensure that expenses or revenues are charged to the correct object in accounting.</span></span>

<span data-ttu-id="9035a-109">Les fonctionnalités suivantes prennent en charge le processus suivant :</span><span class="sxs-lookup"><span data-stu-id="9035a-109">The following capabilities support this process:</span></span>

-   <span data-ttu-id="9035a-110">Répartir manuellement les montants de transaction à l’aide de l’action Fractionnement dans les répartitions comptables, ou en appliquant les modèles par défaut de dimension financière à un document.</span><span class="sxs-lookup"><span data-stu-id="9035a-110">Manually allocate transaction amounts by using the Split action in accounting distributions, or by applying financial dimension default templates to a document.</span></span> <span data-ttu-id="9035a-111">Pour plus d’informations, consultez [Répartitions comptables](../accounts-payable/accounting-distributions.md).</span><span class="sxs-lookup"><span data-stu-id="9035a-111">For more information, see [Accounting distributions](../accounts-payable/accounting-distributions.md).</span></span>
-   <span data-ttu-id="9035a-112">Répartir automatiquement les montants des transactions selon des conditions de répartition définies sur le compte principal individuel.</span><span class="sxs-lookup"><span data-stu-id="9035a-112">Automatically allocate transactions amounts based on allocation terms defined on individual main account.</span></span> <span data-ttu-id="9035a-113">Les écritures de compte de répartition seront générées pour chaque journal en fonction du pourcentage et du compte général de destination à chaque fois qu’une écriture comptable répond aux critères définis comme compte général source.</span><span class="sxs-lookup"><span data-stu-id="9035a-113">Allocation account entries will be generated for each journal based on the percentage and destination ledger account whenever an accounting entry meets the criteria defined as the source ledger account.</span></span> <span data-ttu-id="9035a-114">Pour plus d’informations, voir [Conditions de répartition sur un compte principal](../general-ledger/main-account-allocation-terms.md)</span><span class="sxs-lookup"><span data-stu-id="9035a-114">For more information, see [Main account allocation terms](../general-ledger/main-account-allocation-terms.md)</span></span>
-   <span data-ttu-id="9035a-115">Répartir automatiquement les soldes de comptabilité ou les montants fixes en fonction des règles de répartition comptable.</span><span class="sxs-lookup"><span data-stu-id="9035a-115">Automatically allocate ledger balances or fixed amounts based on ledger allocation rules.</span></span> <span data-ttu-id="9035a-116">Les règles de répartition comptable sont traitées sur une base périodique à l’aide des journaux de répartition.</span><span class="sxs-lookup"><span data-stu-id="9035a-116">The ledger allocation rules are processed on a periodic basis using allocation journals.</span></span> <span data-ttu-id="9035a-117">Pour plus d’informations, voir la rubrique [Règles de répartition](../general-ledger/ledger-allocation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="9035a-117">For more information, see [Allocation rules](../general-ledger/ledger-allocation-rules.md).</span></span>

###  <a name="allocations-in-budget-planning"></a><span data-ttu-id="9035a-118">Répartitions dans la planification budgétaire</span><span class="sxs-lookup"><span data-stu-id="9035a-118">Allocations in budget planning</span></span>

<span data-ttu-id="9035a-119">Les règles de répartition comptable peuvent être utilisées pour les plans budgétaires.</span><span class="sxs-lookup"><span data-stu-id="9035a-119">Ledger allocation rules can be used for budget plans.</span></span> <span data-ttu-id="9035a-120">Lorsque vous utilisez des règles de répartition comptable dans la planification budgétaire, les règles de répartition fonctionnent de la même manière que dans la comptabilité, mais les données sources et les données de destination proviennent du plan budgétaire.</span><span class="sxs-lookup"><span data-stu-id="9035a-120">When you use ledger allocation rules in budget planning, the allocation rules work the same way they would in the ledger, but the source data and destination data comes from the budget plan.</span></span> <span data-ttu-id="9035a-121">Vous pouvez sélectionner manuellement les règles de répartition comptable à utiliser pour les plans budgétaires.</span><span class="sxs-lookup"><span data-stu-id="9035a-121">You can manually select ledger allocation rules to use for budget plans.</span></span> <span data-ttu-id="9035a-122">Sinon, vous pouvez utiliser un programme de répartition qui s’exécute dans le cadre d’un processus de workflow.</span><span class="sxs-lookup"><span data-stu-id="9035a-122">Alternatively, you can use an allocation schedule that runs as part of a workflow process.</span></span>

> [!NOTE]
> <span data-ttu-id="9035a-123">Vous ne pouvez pas utiliser les règles de répartition comptable intersociétés pour la planification budgétaire.</span><span class="sxs-lookup"><span data-stu-id="9035a-123">You can’t use intercompany ledger allocation rules for budget planning.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]