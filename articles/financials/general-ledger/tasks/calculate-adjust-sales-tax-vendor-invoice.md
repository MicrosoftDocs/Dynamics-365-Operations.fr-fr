--- 
title: Calculer et ajuster la taxe sur une facture fournisseur
description: "Si le document source d'origine affiche différents montants de taxe calculés, vous pouvez régler ces montants avant la validation."
author: twheeloc
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTable, LedgerJournalTransVendInvoice, VendTableLookup, TaxTmpWorkTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 2c120eeed18a1ae05bcdda1d1ae285232d68c6ed
ms.contentlocale: fr-fr
ms.lasthandoff: 09/11/2018

---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a><span data-ttu-id="c99e0-103">Calculer et ajuster la taxe sur une facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="c99e0-103">Calculate and adjust sales tax on a vendor invoice</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c99e0-104">Si le document source d'origine affiche différents montants de taxe calculés, vous pouvez régler ces montants avant la validation.</span><span class="sxs-lookup"><span data-stu-id="c99e0-104">If the original source document displays different tax amounts as calculated, you can adjust those amounts before posting.</span></span> <span data-ttu-id="c99e0-105">La société fictive DEMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="c99e0-105">This task uses the DEMF demo company.</span></span>

1. <span data-ttu-id="c99e0-106">Accédez à Comptabilité fournisseur > Factures > Journal des factures.</span><span class="sxs-lookup"><span data-stu-id="c99e0-106">Go to Accounts payable > Invoices > Invoice journal.</span></span>
2. <span data-ttu-id="c99e0-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="c99e0-107">Click New.</span></span>
3. <span data-ttu-id="c99e0-108">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c99e0-108">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="c99e0-109">Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="c99e0-109">In the Name field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="c99e0-110">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c99e0-110">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="c99e0-111">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="c99e0-111">Click Lines.</span></span>
7. <span data-ttu-id="c99e0-112">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c99e0-112">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="c99e0-113">Dans le champ Compte, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="c99e0-113">In the Account field, specify the desired values.</span></span>
9. <span data-ttu-id="c99e0-114">Tapez une valeur dans le champ Facture.</span><span class="sxs-lookup"><span data-stu-id="c99e0-114">In the Invoice field, type a value.</span></span>
10. <span data-ttu-id="c99e0-115">Entrez un numéro dans le champ Crédit.</span><span class="sxs-lookup"><span data-stu-id="c99e0-115">In the Credit field, enter a number.</span></span>
11. <span data-ttu-id="c99e0-116">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="c99e0-116">In the Offset account field, specify the desired values.</span></span>
12. <span data-ttu-id="c99e0-117">Cliquez sur Taxe.</span><span class="sxs-lookup"><span data-stu-id="c99e0-117">Click Sales tax.</span></span>
13. <span data-ttu-id="c99e0-118">Entrez un nombre dans le champ Montant réel de taxe total.</span><span class="sxs-lookup"><span data-stu-id="c99e0-118">In the Total actual sales tax amount field, enter a number.</span></span>
14. <span data-ttu-id="c99e0-119">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c99e0-119">Click OK.</span></span>
15. <span data-ttu-id="c99e0-120">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="c99e0-120">Click Save.</span></span>
16. <span data-ttu-id="c99e0-121">Cliquez sur Taxe.</span><span class="sxs-lookup"><span data-stu-id="c99e0-121">Click Sales tax.</span></span>
17. <span data-ttu-id="c99e0-122">Sous l'onglet Ajustement, les montants de taxe peuvent être ajustés par code taxe.</span><span class="sxs-lookup"><span data-stu-id="c99e0-122">On the Adjustment tab, the sales tax amounts can be adjusted per sales tax code.</span></span>
18. <span data-ttu-id="c99e0-123">Cliquez sur Réinitialiser les montants réels des montants calculés.</span><span class="sxs-lookup"><span data-stu-id="c99e0-123">Click Reset actual from calculated amounts.</span></span>
19. <span data-ttu-id="c99e0-124">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c99e0-124">Click OK.</span></span>
20. <span data-ttu-id="c99e0-125">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="c99e0-125">Click Save.</span></span>


