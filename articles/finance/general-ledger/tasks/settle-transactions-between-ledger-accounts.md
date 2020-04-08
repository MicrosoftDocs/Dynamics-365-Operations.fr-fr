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
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bb53e9fee35712343f034389f00f3d4539cc652d
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144672"
---
# <a name="settle-transactions-between-ledger-accounts"></a><span data-ttu-id="27886-103">Règlement des transactions entre des comptes généraux</span><span class="sxs-lookup"><span data-stu-id="27886-103">Settle transactions between ledger accounts</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="27886-104">Cette procédure montre comment régler les transactions entre les comptes généraux et annuler un règlement comptable.</span><span class="sxs-lookup"><span data-stu-id="27886-104">This procedure shows how to settle transactions between ledger accounts and cancel a ledger settlement.</span></span> <span data-ttu-id="27886-105">La société fictive USMF sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="27886-105">This procedure uses the USMF demo data company.</span></span>


## <a name="settle-transaction-between-ledger-accounts"></a><span data-ttu-id="27886-106">Régler une transaction entre des comptes généraux</span><span class="sxs-lookup"><span data-stu-id="27886-106">Settle transaction between ledger accounts</span></span>
1. <span data-ttu-id="27886-107">Accédez à Comptabilité > Tâches périodiques > Règlements comptables.</span><span class="sxs-lookup"><span data-stu-id="27886-107">Go to General ledger > Periodic tasks > Ledger settlements.</span></span>
2. <span data-ttu-id="27886-108">Dans la liste, cherchez la transaction que vous souhaitez régler.</span><span class="sxs-lookup"><span data-stu-id="27886-108">In the list, find the transaction that you want to settle.</span></span>
   > [!NOTE]
   > <span data-ttu-id="27886-109">Le solde du montant doit être nul.</span><span class="sxs-lookup"><span data-stu-id="27886-109">The amount balance must be zero.</span></span>  
3. <span data-ttu-id="27886-110">Cliquez sur Inclure.</span><span class="sxs-lookup"><span data-stu-id="27886-110">Click Include.</span></span>
4. <span data-ttu-id="27886-111">Cliquez sur Accepter.</span><span class="sxs-lookup"><span data-stu-id="27886-111">Click Accept.</span></span>

## <a name="cancel-a-ledger-settlement"></a><span data-ttu-id="27886-112">Annulation d'un règlement comptable</span><span class="sxs-lookup"><span data-stu-id="27886-112">Cancel a ledger settlement</span></span>

1. <span data-ttu-id="27886-113">Accédez à Comptabilité > Recherches et états > Balance comptable.</span><span class="sxs-lookup"><span data-stu-id="27886-113">Go to General ledger > Inquiries and reports > Trial balance.</span></span>
2. <span data-ttu-id="27886-114">Cliquez sur Paramètres pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="27886-114">Click Parameters to open the drop dialog.</span></span>
3. <span data-ttu-id="27886-115">Cliquez sur Mise à jour.</span><span class="sxs-lookup"><span data-stu-id="27886-115">Click Update.</span></span>
4. <span data-ttu-id="27886-116">Dans la liste, cherchez le compte qui présente la transaction réglée.</span><span class="sxs-lookup"><span data-stu-id="27886-116">In the list, find the account that has the settled transaction.</span></span>
5. <span data-ttu-id="27886-117">Cliquez sur Toutes les transactions.</span><span class="sxs-lookup"><span data-stu-id="27886-117">Click All transactions.</span></span>
6. <span data-ttu-id="27886-118">Utilisez un filtre pour rechercher facilement la transaction dans la liste.</span><span class="sxs-lookup"><span data-stu-id="27886-118">Use a filter to easily find the transaction in the list.</span></span>
7. <span data-ttu-id="27886-119">Cliquez sur Règlements comptables.</span><span class="sxs-lookup"><span data-stu-id="27886-119">Click Ledger settlements.</span></span>
8. <span data-ttu-id="27886-120">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="27886-120">In the list, mark the selected row.</span></span>

