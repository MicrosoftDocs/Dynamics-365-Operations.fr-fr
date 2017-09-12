--- 
title: "Règlement d'un chèque postdaté pour un fournisseur"
description: "Réglez un chèque postdaté remis à un fournisseur dès que la banque a compensé la transaction de chèque après le chèque a été en retard et compensé par la banque."
author: kweekley
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: ac3fcad40e2d71dbde5fab8d1aa77cbfa879cdb1
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="settle-a-postdated-check-for-a-vendor"></a><span data-ttu-id="a0ed9-103">Règlement d'un chèque postdaté pour un fournisseur</span><span class="sxs-lookup"><span data-stu-id="a0ed9-103">Settle a postdated check for a vendor</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a0ed9-104">Réglez un chèque postdaté remis à un fournisseur dès que la banque a compensé la transaction de chèque après le chèque a été en retard et compensé par la banque.</span><span class="sxs-lookup"><span data-stu-id="a0ed9-104">Settle a postdated check issued to a vendor when the bank has cleared the check transaction after the check has been overdue and cleared by the bank.</span></span> 

<span data-ttu-id="a0ed9-105">Avant de commencer cette procédure, exécutez les procédures suivantes.</span><span class="sxs-lookup"><span data-stu-id="a0ed9-105">Complete the following procedures before you start this one.</span></span>

1) <span data-ttu-id="a0ed9-106">Paramétrage de chèques postdatés</span><span class="sxs-lookup"><span data-stu-id="a0ed9-106">Set up postdated checks</span></span>

2) <span data-ttu-id="a0ed9-107">Enregistrement et validation d'un chèque postdaté pour un fournisseur</span><span class="sxs-lookup"><span data-stu-id="a0ed9-107">Register and post a postdated check for a vendor</span></span>



<span data-ttu-id="a0ed9-108">Le rôle de cette procédure Trésorier.</span><span class="sxs-lookup"><span data-stu-id="a0ed9-108">The role of this procedure is Treasurer.</span></span> <span data-ttu-id="a0ed9-109">La société fictive USMF sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="a0ed9-109">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="a0ed9-110">Accédez à Comptabilité fournisseur > Paiements > Chèques fournisseur postdatés.</span><span class="sxs-lookup"><span data-stu-id="a0ed9-110">Go to Accounts payable > Payments > Vendor postdated checks.</span></span>
2. <span data-ttu-id="a0ed9-111">Cliquez sur Régler.</span><span class="sxs-lookup"><span data-stu-id="a0ed9-111">Click Settle.</span></span>
3. <span data-ttu-id="a0ed9-112">Cliquez sur Régler les lignes de compensation.</span><span class="sxs-lookup"><span data-stu-id="a0ed9-112">Click Settle clearing entries.</span></span>
    * <span data-ttu-id="a0ed9-113">Réglez le compte fournisseur pour la transaction par chèque.</span><span class="sxs-lookup"><span data-stu-id="a0ed9-113">Settle the vendor account for the check transaction.</span></span>  
4. <span data-ttu-id="a0ed9-114">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="a0ed9-114">Close the page.</span></span>
5. <span data-ttu-id="a0ed9-115">Accédez à Comptabilité > Entrées de journal > Journaux des opérations diverses.</span><span class="sxs-lookup"><span data-stu-id="a0ed9-115">Go to General ledger > Journal entries > General journals.</span></span>
6. <span data-ttu-id="a0ed9-116">Dans le champ Afficher, sélectionnez « Tout ».</span><span class="sxs-lookup"><span data-stu-id="a0ed9-116">In the Show field, select 'All'.</span></span>
7. <span data-ttu-id="a0ed9-117">Activez ou désactivez la case à cocher Afficher uniquement les journaux créés par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a0ed9-117">Select or clear the Show user-created only check box.</span></span>
8. <span data-ttu-id="a0ed9-118">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a0ed9-118">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="a0ed9-119">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="a0ed9-119">Click Lines.</span></span>
10. <span data-ttu-id="a0ed9-120">Cliquez Document.</span><span class="sxs-lookup"><span data-stu-id="a0ed9-120">Click Voucher.</span></span>
11. <span data-ttu-id="a0ed9-121">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="a0ed9-121">Close the page.</span></span>


