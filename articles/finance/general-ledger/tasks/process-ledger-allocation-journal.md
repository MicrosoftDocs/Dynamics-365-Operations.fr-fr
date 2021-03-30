---
title: Traiter le journal de répartition comptable
description: Cette rubrique explique comment traiter une demande de répartition dans Dynamics 365 Finance.
author: aprilolson
manager: AnnBe
ms.date: 07/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a52a5ce2d789757a11c9e443c7f25058bd9d8a91
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222333"
---
# <a name="process-ledger-allocation-journal"></a><span data-ttu-id="0dbba-103">Traiter le journal de répartition comptable</span><span class="sxs-lookup"><span data-stu-id="0dbba-103">Process ledger allocation journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0dbba-104">Cette rubrique explique comment traiter une demande de répartition.</span><span class="sxs-lookup"><span data-stu-id="0dbba-104">This topic explains how to process an allocation request.</span></span> <span data-ttu-id="0dbba-105">Utilisez la page Traiter la demande de répartition pour créer un journal de répartition qui puisse être consulté et approuvé avant la validation dans la comptabilité ou être validé directement dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="0dbba-105">Use the Process allocation request page to create an allocation journal that can be reviewed and approved before posting to General ledger, or posted directly to General ledger.</span></span> <span data-ttu-id="0dbba-106">Avant de créer un journal de répartition, il doit exister au moins une règle de répartition de comptabilité active.</span><span class="sxs-lookup"><span data-stu-id="0dbba-106">Before you can create an allocations journal, there must be least one active Ledger allocation rule.</span></span> <span data-ttu-id="0dbba-107">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="0dbba-107">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="0dbba-108">Dans le volet de navigation, accédez à **Modules > Comptabilité > Répartitions > Traiter la demande de répartition**.</span><span class="sxs-lookup"><span data-stu-id="0dbba-108">In the navigation pane, go to **Modules > General ledger > Allocations > Process allocation request**.</span></span>
2. <span data-ttu-id="0dbba-109">Dans le champ **Règle**, sélectionnez l’enregistrement souhaité dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="0dbba-109">In the **Rule** field, select the desired record in the drop-down menu.</span></span>
3. <span data-ttu-id="0dbba-110">Dans le champ **À partir du**, saisissez une date.</span><span class="sxs-lookup"><span data-stu-id="0dbba-110">In the **As of date** field, enter a date.</span></span>

    - <span data-ttu-id="0dbba-111">Le champ **À partir du** est très important lorsque la comptabilité est la source de données de la règle.</span><span class="sxs-lookup"><span data-stu-id="0dbba-111">The **As of Date** is very important when the Ledger is the Data source for the rule.</span></span> <span data-ttu-id="0dbba-112">Cette date contrôle les soldes comptables à inclure dans la répartition.</span><span class="sxs-lookup"><span data-stu-id="0dbba-112">This date controls which ledger balances to include for allocation.</span></span>  
    - <span data-ttu-id="0dbba-113">Dans le champ **Aucune origine**, sélectionnez **Arrêter**.</span><span class="sxs-lookup"><span data-stu-id="0dbba-113">In the **Zero source** field select **Stop**.</span></span> <span data-ttu-id="0dbba-114">Cela arrête le processus de répartition et affiche un message qui indique qu’un montant source nul est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="0dbba-114">This will stop the allocation process and display a message that states that a zero source amount is selected.</span></span>  

4. <span data-ttu-id="0dbba-115">Dans le champ **Options de proposition**, sélectionnez **Proposition uniquement**.</span><span class="sxs-lookup"><span data-stu-id="0dbba-115">In the **Proposal options** field, select **Proposal only**.</span></span> <span data-ttu-id="0dbba-116">Sélectionnez **Proposition uniquement** pour consulter uniquement et éventuellement approuver le résultat dans les journaux de répartition avant de valider la répartition dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="0dbba-116">Select **Proposal only** to review and optionally approve the result in Allocation journals prior to posting the allocation to General ledger.</span></span>  
5. <span data-ttu-id="0dbba-117">Entrez une date dans le champ Date de validation dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="0dbba-117">In the GL posting date field, enter a date.</span></span>
6. <span data-ttu-id="0dbba-118">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0dbba-118">Select **OK**.</span></span>
7. <span data-ttu-id="0dbba-119">Dans le volet de navigation, accédez à **Modules > Comptabilité > Répartitions > Journaux de répartition**.</span><span class="sxs-lookup"><span data-stu-id="0dbba-119">In the navigation pane, go to **Modules > General ledger > Allocations > Allocation journals**.</span></span>
8. <span data-ttu-id="0dbba-120">Sélectionnez **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="0dbba-120">Select **Lines**.</span></span>
9. <span data-ttu-id="0dbba-121">Sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="0dbba-121">Select **Post**.</span></span>
10. <span data-ttu-id="0dbba-122">Sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="0dbba-122">Select **Post**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]