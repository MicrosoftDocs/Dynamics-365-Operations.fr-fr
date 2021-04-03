---
title: Règlement d’un chèque postdaté pour un fournisseur
description: Réglez un chèque postdaté remis à un fournisseur dès que la banque a compensé la transaction de chèque après le chèque a été en retard et compensé par la banque.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPostDatedChecks, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d66caa83df693445c1b1d40ffdc11e8d10cf7426
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5239625"
---
# <a name="settle-a-postdated-check-for-a-vendor"></a><span data-ttu-id="7ebdf-103">Règlement d’un chèque postdaté pour un fournisseur</span><span class="sxs-lookup"><span data-stu-id="7ebdf-103">Settle a postdated check for a vendor</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7ebdf-104">Réglez un chèque postdaté remis à un fournisseur dès que la banque a compensé la transaction de chèque après le chèque a été en retard et compensé par la banque.</span><span class="sxs-lookup"><span data-stu-id="7ebdf-104">Settle a postdated check issued to a vendor when the bank has cleared the check transaction after the check has been overdue and cleared by the bank.</span></span> 

<span data-ttu-id="7ebdf-105">Avant de commencer cette procédure, exécutez les procédures suivantes.</span><span class="sxs-lookup"><span data-stu-id="7ebdf-105">Complete the following procedures before you start this one.</span></span>

1) <span data-ttu-id="7ebdf-106">Paramétrage de chèques postdatés</span><span class="sxs-lookup"><span data-stu-id="7ebdf-106">Set up postdated checks</span></span>

2) <span data-ttu-id="7ebdf-107">Enregistrement et validation d’un chèque postdaté pour un fournisseur</span><span class="sxs-lookup"><span data-stu-id="7ebdf-107">Register and post a postdated check for a vendor</span></span>



<span data-ttu-id="7ebdf-108">Le rôle de cette procédure Trésorier.</span><span class="sxs-lookup"><span data-stu-id="7ebdf-108">The role of this procedure is Treasurer.</span></span> <span data-ttu-id="7ebdf-109">La société fictive USMF sert d’exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="7ebdf-109">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="7ebdf-110">Accédez à Comptabilité fournisseur > Paiements > Chèques fournisseur postdatés.</span><span class="sxs-lookup"><span data-stu-id="7ebdf-110">Go to Accounts payable > Payments > Vendor postdated checks.</span></span>
2. <span data-ttu-id="7ebdf-111">Cliquez sur Régler.</span><span class="sxs-lookup"><span data-stu-id="7ebdf-111">Click Settle.</span></span>
3. <span data-ttu-id="7ebdf-112">Cliquez sur Régler les lignes de compensation.</span><span class="sxs-lookup"><span data-stu-id="7ebdf-112">Click Settle clearing entries.</span></span>
    * <span data-ttu-id="7ebdf-113">Réglez le compte fournisseur pour la transaction par chèque.</span><span class="sxs-lookup"><span data-stu-id="7ebdf-113">Settle the vendor account for the check transaction.</span></span>  
4. <span data-ttu-id="7ebdf-114">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="7ebdf-114">Close the page.</span></span>
5. <span data-ttu-id="7ebdf-115">Accédez à Comptabilité > Entrées de journal > Journaux des opérations diverses.</span><span class="sxs-lookup"><span data-stu-id="7ebdf-115">Go to General ledger > Journal entries > General journals.</span></span>
6. <span data-ttu-id="7ebdf-116">Dans le champ Afficher, sélectionnez « Tout ».</span><span class="sxs-lookup"><span data-stu-id="7ebdf-116">In the Show field, select 'All'.</span></span>
7. <span data-ttu-id="7ebdf-117">Activez ou désactivez la case à cocher Afficher uniquement les journaux créés par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7ebdf-117">Select or clear the Show user-created only check box.</span></span>
8. <span data-ttu-id="7ebdf-118">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7ebdf-118">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="7ebdf-119">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="7ebdf-119">Click Lines.</span></span>
10. <span data-ttu-id="7ebdf-120">Cliquez Document.</span><span class="sxs-lookup"><span data-stu-id="7ebdf-120">Click Voucher.</span></span>
11. <span data-ttu-id="7ebdf-121">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="7ebdf-121">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]