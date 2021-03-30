---
title: Clôture de la comptabilité en fin de période
description: Cette rubrique décrit les tâches qui sont généralement effectuées lors de l’exécution d’une clôture de période pour la comptabilité.
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerPeriodCloseWorkspace
audience: Application User
ms.reviewer: roschlom
ms.custom: 14111
ms.assetid: cec9e039-c1a2-482c-bea6-e11d896eea9d
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fe90e29e5ae71492519d9ab0d4cab2d12765cf4b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5212371"
---
# <a name="close-the-general-ledger-at-period-end"></a><span data-ttu-id="7e5e7-103">Clôture de la comptabilité en fin de période</span><span class="sxs-lookup"><span data-stu-id="7e5e7-103">Close the general ledger at period end</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7e5e7-104">Cette rubrique décrit les tâches qui sont généralement effectuées lors de l’exécution d’une clôture de période pour la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="7e5e7-104">This topic describes the tasks that are typically completed when performing a period closing for General ledger.</span></span> 

<span data-ttu-id="7e5e7-105">Dans la comptabilité, vous pouvez exécuter les procédures de clôture pour une période ou année.</span><span class="sxs-lookup"><span data-stu-id="7e5e7-105">In General ledger, you can complete closing procedures for a period or a year.</span></span> <span data-ttu-id="7e5e7-106">Les procédures de clôture préparent le système pour une nouvelle période.</span><span class="sxs-lookup"><span data-stu-id="7e5e7-106">Closing processes prepare the system for a new period.</span></span> <span data-ttu-id="7e5e7-107">Pour préparer le système pour une année, vous devez exécuter le processus de clôture de fin d’exercice.</span><span class="sxs-lookup"><span data-stu-id="7e5e7-107">To prepare the system for a new year, you must run the year end close process.</span></span> <span data-ttu-id="7e5e7-108">Chaque organisation a différents processus et étapes qu’elle effectue pour la fin d’une période.</span><span class="sxs-lookup"><span data-stu-id="7e5e7-108">Each organization has different processes and steps that it performs for the end of a period.</span></span> <span data-ttu-id="7e5e7-109">Voici quelques étapes facultatives pour les fins de période :</span><span class="sxs-lookup"><span data-stu-id="7e5e7-109">Here are some optional steps for period ends:</span></span>

-   <span data-ttu-id="7e5e7-110">Complétez toutes les tâches de tous les autres modules, tels que Comptabilité client Comptabilité fournisseur et Stock.</span><span class="sxs-lookup"><span data-stu-id="7e5e7-110">Complete all the tasks for all other modules, such as Accounts receivable, Accounts payable, and Inventory.</span></span>
-   <span data-ttu-id="7e5e7-111">Vérifiez que tous les journaux sont validés.</span><span class="sxs-lookup"><span data-stu-id="7e5e7-111">Verify that all journals are posted.</span></span>
-   <span data-ttu-id="7e5e7-112">Exécutez la réévaluation des comptes en devises pour générer tous les montants de profit non réalisé ou de perte.</span><span class="sxs-lookup"><span data-stu-id="7e5e7-112">Run foreign currency revaluation to generate any unrealized gain or loss amounts.</span></span>
-   <span data-ttu-id="7e5e7-113">Réglez les transactions pour chaque compte général.</span><span class="sxs-lookup"><span data-stu-id="7e5e7-113">Settle transactions for each ledger account.</span></span>
-   <span data-ttu-id="7e5e7-114">Traitez toutes les répartitions demandées.</span><span class="sxs-lookup"><span data-stu-id="7e5e7-114">Process any required allocations.</span></span>
-   <span data-ttu-id="7e5e7-115">Validez manuellement les ajustements de fin de période.</span><span class="sxs-lookup"><span data-stu-id="7e5e7-115">Manually post period-end adjustments.</span></span>
-   <span data-ttu-id="7e5e7-116">Journalisez les transactions, et examinez l’état **Journal comptable**.</span><span class="sxs-lookup"><span data-stu-id="7e5e7-116">Journalize transactions, and review the **Ledger journal** report.</span></span>
-   <span data-ttu-id="7e5e7-117">Exécutez une consolidation à l’aide d’une société de consolidation ou des états financiers.</span><span class="sxs-lookup"><span data-stu-id="7e5e7-117">Perform a consolidation by using a consolidation company or Financial reporting.</span></span>
-   <span data-ttu-id="7e5e7-118">Générez des tableaux d’analyse de période de fin à l’aide des états financiers.</span><span class="sxs-lookup"><span data-stu-id="7e5e7-118">Generate period-end financial statements by using Financial reporting.</span></span>
-   <span data-ttu-id="7e5e7-119">Définissez les périodes comptables sur **En attente**, afin qu’aucune autre validation ne se produise.</span><span class="sxs-lookup"><span data-stu-id="7e5e7-119">Set ledger periods to **On hold**, so that no further posting occurs.</span></span> <span data-ttu-id="7e5e7-120">Vous pouvez également limiter une période à un groupe d’utilisateurs spécifique pendant que les activités de période de fin ont lieu, pour un meilleur contrôle.</span><span class="sxs-lookup"><span data-stu-id="7e5e7-120">You can also restrict a period to a specific user group while period-end activities are occurring, for better control.</span></span> <span data-ttu-id="7e5e7-121">Il n’est pas recommandé de définir des périodes sur **Clôturé définitivement**, car vous ne pouvez pas rouvrir une période clôturée.</span><span class="sxs-lookup"><span data-stu-id="7e5e7-121">It's not a good idea to set periods to **Permanently closed**, because you can't reopen a period that has been closed.</span></span>

<span data-ttu-id="7e5e7-122">L’espace de travail Clôture de période comptable peut être utilisé pour organiser et suivre les tâches requises pour différents processus de fin de période.</span><span class="sxs-lookup"><span data-stu-id="7e5e7-122">The Financial period close workspace can be used to organize and track the tasks required for various period end processes.</span></span> 


<span data-ttu-id="7e5e7-123">Pour plus d’informations, voir les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="7e5e7-123">For more information, see the following topics for more information:</span></span>
- [<span data-ttu-id="7e5e7-124">Espace de travail de clôture de période comptable</span><span class="sxs-lookup"><span data-stu-id="7e5e7-124">Financial period close workspace</span></span>](financial-period-close-workspace.md) 
- [<span data-ttu-id="7e5e7-125">Clôture de fin d’exercice</span><span class="sxs-lookup"><span data-stu-id="7e5e7-125">Year-end close</span></span>](Year-end-close.md)  
- [<span data-ttu-id="7e5e7-126">Secteur de clôture de période comptable</span><span class="sxs-lookup"><span data-stu-id="7e5e7-126">Mass financial period close</span></span>](tasks/mass-financial-period-close.md)






[!INCLUDE[footer-include](../../includes/footer-banner.md)]