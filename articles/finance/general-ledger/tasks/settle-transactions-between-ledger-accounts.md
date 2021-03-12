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
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8220bacc8d683163e97956ec59a5af929b04319c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994413"
---
# <a name="settle-transactions-between-ledger-accounts"></a><span data-ttu-id="f7f32-103">Règlement des transactions entre des comptes généraux</span><span class="sxs-lookup"><span data-stu-id="f7f32-103">Settle transactions between ledger accounts</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f7f32-104">Cette procédure montre comment régler les transactions entre les comptes généraux et annuler un règlement comptable.</span><span class="sxs-lookup"><span data-stu-id="f7f32-104">This procedure shows how to settle transactions between ledger accounts and cancel a ledger settlement.</span></span> <span data-ttu-id="f7f32-105">La société fictive USMF sert d’exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="f7f32-105">This procedure uses the USMF demo data company.</span></span>


## <a name="settle-transaction-between-ledger-accounts"></a><span data-ttu-id="f7f32-106">Régler une transaction entre des comptes généraux</span><span class="sxs-lookup"><span data-stu-id="f7f32-106">Settle transaction between ledger accounts</span></span>
1. <span data-ttu-id="f7f32-107">Accédez à Comptabilité > Tâches périodiques > Règlements comptables.</span><span class="sxs-lookup"><span data-stu-id="f7f32-107">Go to General ledger > Periodic tasks > Ledger settlements.</span></span>
2. <span data-ttu-id="f7f32-108">Dans la liste, cherchez la transaction que vous souhaitez régler.</span><span class="sxs-lookup"><span data-stu-id="f7f32-108">In the list, find the transaction that you want to settle.</span></span>
   > [!NOTE]
   > <span data-ttu-id="f7f32-109">Le solde du montant doit être nul.</span><span class="sxs-lookup"><span data-stu-id="f7f32-109">The amount balance must be zero.</span></span>  
3. <span data-ttu-id="f7f32-110">Cliquez sur Inclure.</span><span class="sxs-lookup"><span data-stu-id="f7f32-110">Click Include.</span></span>
4. <span data-ttu-id="f7f32-111">Cliquez sur Accepter.</span><span class="sxs-lookup"><span data-stu-id="f7f32-111">Click Accept.</span></span>

## <a name="cancel-a-ledger-settlement"></a><span data-ttu-id="f7f32-112">Annulation d’un règlement comptable</span><span class="sxs-lookup"><span data-stu-id="f7f32-112">Cancel a ledger settlement</span></span>

1. <span data-ttu-id="f7f32-113">Accédez à Comptabilité > Recherches et états > Balance comptable.</span><span class="sxs-lookup"><span data-stu-id="f7f32-113">Go to General ledger > Inquiries and reports > Trial balance.</span></span>
2. <span data-ttu-id="f7f32-114">Cliquez sur Paramètres pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="f7f32-114">Click Parameters to open the drop dialog.</span></span>
3. <span data-ttu-id="f7f32-115">Cliquez sur Mise à jour.</span><span class="sxs-lookup"><span data-stu-id="f7f32-115">Click Update.</span></span>
4. <span data-ttu-id="f7f32-116">Dans la liste, cherchez le compte qui présente la transaction réglée.</span><span class="sxs-lookup"><span data-stu-id="f7f32-116">In the list, find the account that has the settled transaction.</span></span>
5. <span data-ttu-id="f7f32-117">Cliquez sur Toutes les transactions.</span><span class="sxs-lookup"><span data-stu-id="f7f32-117">Click All transactions.</span></span>
6. <span data-ttu-id="f7f32-118">Utilisez un filtre pour rechercher facilement la transaction dans la liste.</span><span class="sxs-lookup"><span data-stu-id="f7f32-118">Use a filter to easily find the transaction in the list.</span></span>
7. <span data-ttu-id="f7f32-119">Cliquez sur Règlements comptables.</span><span class="sxs-lookup"><span data-stu-id="f7f32-119">Click Ledger settlements.</span></span>
8. <span data-ttu-id="f7f32-120">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f7f32-120">In the list, mark the selected row.</span></span>

