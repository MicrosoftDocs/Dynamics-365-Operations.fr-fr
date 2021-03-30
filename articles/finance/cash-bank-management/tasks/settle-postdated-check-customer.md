---
title: Règlement d’un chèque postdaté provenant d’un client
description: Vous pouvez régler un chèque postdaté après que celui-ci ait été compensé par la banque.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPostDatedChecks, SystemDate, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: abcd6532c294223e768d1a01d97309e35c30edbe
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5217408"
---
# <a name="settle-a-postdated-check-from-a-customer"></a><span data-ttu-id="53c53-103">Règlement d’un chèque postdaté provenant d’un client</span><span class="sxs-lookup"><span data-stu-id="53c53-103">Settle a postdated check from a customer</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="53c53-104">Vous pouvez régler un chèque postdaté après que celui-ci ait été compensé par la banque.</span><span class="sxs-lookup"><span data-stu-id="53c53-104">You can settle a postdated check after the check has been cleared by the bank.</span></span> <span data-ttu-id="53c53-105">Cette transaction financière permet également d’effacer la transaction de compte d’attente pour le chèque postdaté.</span><span class="sxs-lookup"><span data-stu-id="53c53-105">This financial transaction also clears the bridge account transaction for the postdated check.</span></span> 

<span data-ttu-id="53c53-106">Les tâches suivantes doivent être terminées avant de commencer celui-ci.</span><span class="sxs-lookup"><span data-stu-id="53c53-106">The following tasks must be complete before you start this one.</span></span>

1) <span data-ttu-id="53c53-107">Paramétrage de chèques postdatés</span><span class="sxs-lookup"><span data-stu-id="53c53-107">Set up postdated checks</span></span>

2) <span data-ttu-id="53c53-108">Enregistrer et valider un chèque postdaté pour un client</span><span class="sxs-lookup"><span data-stu-id="53c53-108">Register and post a postdated check for a customer</span></span> 



<span data-ttu-id="53c53-109">Le rôle de ces guides de tâches est Trésorier.</span><span class="sxs-lookup"><span data-stu-id="53c53-109">The role of this task guides is Treasurer.</span></span>



<span data-ttu-id="53c53-110">La société fictive USMF sert d’exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="53c53-110">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="53c53-111">Accédez à Crédit et relances > Recherches et états > Paiements > Chèques client postdatés.</span><span class="sxs-lookup"><span data-stu-id="53c53-111">Go to Credit and collections > Inquiries and reports > Payments > Customer postdated checks.</span></span>
2. <span data-ttu-id="53c53-112">Cliquez sur Régler.</span><span class="sxs-lookup"><span data-stu-id="53c53-112">Click Settle.</span></span>
3. <span data-ttu-id="53c53-113">Cliquez sur Régler les lignes de compensation.</span><span class="sxs-lookup"><span data-stu-id="53c53-113">Click Settle clearing entries.</span></span>
    * <span data-ttu-id="53c53-114">Réglez le compte client pour la transaction par chèque.</span><span class="sxs-lookup"><span data-stu-id="53c53-114">Settle the customer account for the check transaction.</span></span>  
4. <span data-ttu-id="53c53-115">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="53c53-115">Close the page.</span></span>
5. <span data-ttu-id="53c53-116">Accédez à Comptabilité > Entrées de journal > Journaux des opérations diverses.</span><span class="sxs-lookup"><span data-stu-id="53c53-116">Go to General ledger > Journal entries > General journals.</span></span>
6. <span data-ttu-id="53c53-117">Dans le champ Afficher, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="53c53-117">In the Show field, select an option.</span></span>
7. <span data-ttu-id="53c53-118">Activez ou désactivez la case à cocher Afficher uniquement les journaux créés par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="53c53-118">Select or clear the Show user-created only check box.</span></span>
8. <span data-ttu-id="53c53-119">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="53c53-119">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="53c53-120">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="53c53-120">Click Lines.</span></span>
10. <span data-ttu-id="53c53-121">Cliquez Document.</span><span class="sxs-lookup"><span data-stu-id="53c53-121">Click Voucher.</span></span>
11. <span data-ttu-id="53c53-122">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="53c53-122">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]