---
title: Calculer et ajuster la taxe sur une facture fournisseur
description: Cette rubrique explique comment ajuster la taxe sur une facture fournisseur dans Dynamics 365 Finance.
author: twheeloc
manager: AnnBe
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendInvoice, VendTableLookup, TaxTmpWorkTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2f3521f7bc56659fc6f7a6d47f581ddbfea16523
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3139965"
---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a><span data-ttu-id="b9c7a-103">Calculer et ajuster la taxe sur une facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="b9c7a-103">Calculate and adjust sales tax on a vendor invoice</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b9c7a-104">Cette rubrique explique comment ajuster la taxe sur une facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b9c7a-104">This topic explains how to adjust sales tax on a vendor invoice.</span></span> <span data-ttu-id="b9c7a-105">Si le document source d'origine affiche différents montants de taxe calculés, vous pouvez régler ces montants avant la validation.</span><span class="sxs-lookup"><span data-stu-id="b9c7a-105">If the original source document displays different tax amounts as calculated, you can adjust those amounts before posting.</span></span> <span data-ttu-id="b9c7a-106">La société fictive DEMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="b9c7a-106">This task uses the DEMF demo company.</span></span>

1. <span data-ttu-id="b9c7a-107">Dans le volet de navigation, accédez **Modules > Comptabilité fournisseur > Factures > Journal des factures**.</span><span class="sxs-lookup"><span data-stu-id="b9c7a-107">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice journal**.</span></span>
2. <span data-ttu-id="b9c7a-108">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="b9c7a-108">Select **New**.</span></span>
3. <span data-ttu-id="b9c7a-109">Dans le champ **Nom** de la nouvelle ligne, sélectionnez une option du menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="b9c7a-109">In the **Name** field of the new row, select an option in the drop-down menu.</span></span>
4. <span data-ttu-id="b9c7a-110">Dans le volet Actions, sélectionnez **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="b9c7a-110">In the Action Pane, select **Lines**.</span></span>
5. <span data-ttu-id="b9c7a-111">Dans le champ **Compte**, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="b9c7a-111">In the **Account** field, specify the desired values.</span></span>
6. <span data-ttu-id="b9c7a-112">Dans le champ **Facture**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="b9c7a-112">In the **Invoice** field, type a value.</span></span>
7. <span data-ttu-id="b9c7a-113">Dans le champ **Crédit**, entrez un numéro.</span><span class="sxs-lookup"><span data-stu-id="b9c7a-113">In the **Credit** field, enter a number.</span></span>
8. <span data-ttu-id="b9c7a-114">Dans le champ **Compte de contrepartie**, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="b9c7a-114">In the **Offset account** field, specify the desired values.</span></span>
9. <span data-ttu-id="b9c7a-115">Sélectionnez **Taxe**.</span><span class="sxs-lookup"><span data-stu-id="b9c7a-115">Select **Sales tax**.</span></span>
10. <span data-ttu-id="b9c7a-116">Dans le champ **Montant réel de taxe total**, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="b9c7a-116">In the **Total actual sales tax amount** field, enter a number.</span></span>
11. <span data-ttu-id="b9c7a-117">Sous l'onglet **Ajustement**, les montants de taxe peuvent être ajustés par code taxe.</span><span class="sxs-lookup"><span data-stu-id="b9c7a-117">On the **Adjustment** tab, the sales tax amounts can be adjusted per sales tax code.</span></span>
12. <span data-ttu-id="b9c7a-118">Sélectionnez **Réinitialiser les montants réels des montants calculés**.</span><span class="sxs-lookup"><span data-stu-id="b9c7a-118">Select **Reset actual from calculated amounts**.</span></span>
13. <span data-ttu-id="b9c7a-119">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b9c7a-119">Select **OK**.</span></span>
14. <span data-ttu-id="b9c7a-120">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b9c7a-120">Select **Save**.</span></span>

