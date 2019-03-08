---
title: Traiter le journal de répartition comptable
description: Utilisez la page Traiter la demande de répartition pour créer un journal de répartition qui puisse être consulté et approuvé avant la validation dans la comptabilité ou être validé directement dans la comptabilité.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d2046e25719c9023bee99736488a4ee6f22723fe
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "335644"
---
# <a name="process-ledger-allocation-journal"></a><span data-ttu-id="04a40-103">Traiter le journal de répartition comptable</span><span class="sxs-lookup"><span data-stu-id="04a40-103">Process ledger allocation journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="04a40-104">Utilisez la page Traiter la demande de répartition pour créer un journal de répartition qui puisse être consulté et approuvé avant la validation dans la comptabilité ou être validé directement dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="04a40-104">Use the Process allocation request page to create an allocation journal that can be reviewed and approved before posting to General ledger, or posted directly to General ledger.</span></span> <span data-ttu-id="04a40-105">Avant de créer un journal de répartition, il doit exister au moins une règle de répartition de comptabilité active.</span><span class="sxs-lookup"><span data-stu-id="04a40-105">Before you can create an allocations journal, there must be least one active Ledger allocation rule.</span></span> <span data-ttu-id="04a40-106">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="04a40-106">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="04a40-107">Accédez à Comptabilité > Répartition > Traiter la demande de répartition.</span><span class="sxs-lookup"><span data-stu-id="04a40-107">Go to General ledger > Allocations > Process allocation request.</span></span>
2. <span data-ttu-id="04a40-108">Dans le champ Règle, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="04a40-108">In the Rule field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="04a40-109">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="04a40-109">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="04a40-110">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="04a40-110">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="04a40-111">Entrez une date dans le champ À partir de.</span><span class="sxs-lookup"><span data-stu-id="04a40-111">In the As of date field, enter a date.</span></span>
    * <span data-ttu-id="04a40-112">Le champ À partir du est très important lorsque la comptabilité est la source de données de la règle.</span><span class="sxs-lookup"><span data-stu-id="04a40-112">The As of Date is very important when the Ledger is the Data source for the rule.</span></span> <span data-ttu-id="04a40-113">Cette date contrôle les soldes comptables à inclure dans la répartition.</span><span class="sxs-lookup"><span data-stu-id="04a40-113">This date controls which ledger balances to include for allocation.</span></span>     <span data-ttu-id="04a40-114">Dans le champ Aucune origine, sélectionnez Arrêter.</span><span class="sxs-lookup"><span data-stu-id="04a40-114">In the Zero source field select Stop.</span></span> <span data-ttu-id="04a40-115">Cela arrête le processus de répartition et affiche un message qui indique qu'un montant source nul est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="04a40-115">This will  Stop the allocation process and display a message that states that a zero source amount is selected.</span></span>  
6. <span data-ttu-id="04a40-116">Dans le champ Options de proposition, sélectionnez « Proposition uniquement ».</span><span class="sxs-lookup"><span data-stu-id="04a40-116">In the Proposal options field, select 'Proposal only'.</span></span>
    * <span data-ttu-id="04a40-117">Sélectionnez Proposition uniquement pour consulter uniquement et éventuellement approuver le résultat dans les journaux de répartition avant de valider la répartition dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="04a40-117">Select Proposal only to review and optionally approve the result in Allocation journals prior to posting the allocation to General ledger.</span></span>  
7. <span data-ttu-id="04a40-118">Entrez une date dans le champ Date de validation dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="04a40-118">In the GL posting date field, enter a date.</span></span>
8. <span data-ttu-id="04a40-119">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="04a40-119">Click OK.</span></span>
9. <span data-ttu-id="04a40-120">Accédez à Comptabilité > Répartition > Journaux de répartition.</span><span class="sxs-lookup"><span data-stu-id="04a40-120">Go to General ledger > Allocations > Allocation journals.</span></span>
10. <span data-ttu-id="04a40-121">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="04a40-121">Click Lines.</span></span>
11. <span data-ttu-id="04a40-122">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="04a40-122">Click Post.</span></span>
12. <span data-ttu-id="04a40-123">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="04a40-123">Click Post.</span></span>

