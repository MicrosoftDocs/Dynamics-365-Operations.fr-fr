---
title: Règlement des transactions entre des comptes généraux
description: Cette procédure montre comment régler les transactions entre les comptes généraux et annuler un règlement comptable.
author: aprilolson
manager: AnnBe
ms.date: 10/03/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransSettlement, LedgerTrialBalanceListPage, LedgerTrialBalanceListPageBalanceParms, LedgerTransAccount, LedgerTransSettled
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4aff64fa1c017f295752e913de7fb320f0662ef8
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568118"
---
# <a name="settle-transactions-between-ledger-accounts"></a><span data-ttu-id="3fdb2-103">Règlement des transactions entre des comptes généraux</span><span class="sxs-lookup"><span data-stu-id="3fdb2-103">Settle transactions between ledger accounts</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3fdb2-104">Cette procédure montre comment régler les transactions entre les comptes généraux et annuler un règlement comptable.</span><span class="sxs-lookup"><span data-stu-id="3fdb2-104">This procedure shows how to settle transactions between ledger accounts and cancel a ledger settlement.</span></span> <span data-ttu-id="3fdb2-105">La société fictive USMF sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="3fdb2-105">This procedure uses the USMF demo data company.</span></span>


## <a name="settle-transaction-between-ledger-accounts"></a><span data-ttu-id="3fdb2-106">Régler une transaction entre des comptes généraux</span><span class="sxs-lookup"><span data-stu-id="3fdb2-106">Settle transaction between ledger accounts</span></span>
1. <span data-ttu-id="3fdb2-107">Accédez à Comptabilité > Tâches périodiques > Règlements comptables.</span><span class="sxs-lookup"><span data-stu-id="3fdb2-107">Go to General ledger > Periodic tasks > Ledger settlements.</span></span>
2. <span data-ttu-id="3fdb2-108">Dans la liste, cherchez la transaction que vous souhaitez régler.</span><span class="sxs-lookup"><span data-stu-id="3fdb2-108">In the list, find the transaction that you want to settle.</span></span>
   > [!NOTE]
   > <span data-ttu-id="3fdb2-109">Le solde du montant doit être nul.</span><span class="sxs-lookup"><span data-stu-id="3fdb2-109">The amount balance must be zero.</span></span>  
3. <span data-ttu-id="3fdb2-110">Cliquez sur Inclure.</span><span class="sxs-lookup"><span data-stu-id="3fdb2-110">Click Include.</span></span>
4. <span data-ttu-id="3fdb2-111">Cliquez sur Accepter.</span><span class="sxs-lookup"><span data-stu-id="3fdb2-111">Click Accept.</span></span>

## <a name="cancel-a-ledger-settlement"></a><span data-ttu-id="3fdb2-112">Annulation d'un règlement comptable</span><span class="sxs-lookup"><span data-stu-id="3fdb2-112">Cancel a ledger settlement</span></span>

1. <span data-ttu-id="3fdb2-113">Accédez à Comptabilité > Recherches et états > Balance comptable.</span><span class="sxs-lookup"><span data-stu-id="3fdb2-113">Go to General ledger > Inquiries and reports > Trial balance.</span></span>
2. <span data-ttu-id="3fdb2-114">Cliquez sur Paramètres pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="3fdb2-114">Click Parameters to open the drop dialog.</span></span>
3. <span data-ttu-id="3fdb2-115">Cliquez sur Mise à jour.</span><span class="sxs-lookup"><span data-stu-id="3fdb2-115">Click Update.</span></span>
4. <span data-ttu-id="3fdb2-116">Dans la liste, cherchez le compte qui présente la transaction réglée.</span><span class="sxs-lookup"><span data-stu-id="3fdb2-116">In the list, find the account that has the settled transaction.</span></span>
5. <span data-ttu-id="3fdb2-117">Cliquez sur Toutes les transactions.</span><span class="sxs-lookup"><span data-stu-id="3fdb2-117">Click All transactions.</span></span>
6. <span data-ttu-id="3fdb2-118">Utilisez un filtre pour rechercher facilement la transaction dans la liste.</span><span class="sxs-lookup"><span data-stu-id="3fdb2-118">Use a filter to easily find the transaction in the list.</span></span>
7. <span data-ttu-id="3fdb2-119">Cliquez sur Règlements comptables.</span><span class="sxs-lookup"><span data-stu-id="3fdb2-119">Click Ledger settlements.</span></span>
8. <span data-ttu-id="3fdb2-120">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3fdb2-120">In the list, mark the selected row.</span></span>

