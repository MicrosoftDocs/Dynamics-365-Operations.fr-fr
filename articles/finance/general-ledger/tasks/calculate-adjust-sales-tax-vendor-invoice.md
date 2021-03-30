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
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f4d01fe7587e01c04af28be934a235d955455216
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204735"
---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a><span data-ttu-id="d9956-103">Calculer et ajuster la taxe sur une facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="d9956-103">Calculate and adjust sales tax on a vendor invoice</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d9956-104">Cette rubrique explique comment ajuster la taxe sur une facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="d9956-104">This topic explains how to adjust sales tax on a vendor invoice.</span></span> <span data-ttu-id="d9956-105">Si le document source d’origine affiche différents montants de taxe calculés, vous pouvez régler ces montants avant la validation.</span><span class="sxs-lookup"><span data-stu-id="d9956-105">If the original source document displays different tax amounts as calculated, you can adjust those amounts before posting.</span></span> <span data-ttu-id="d9956-106">La société fictive DEMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="d9956-106">This task uses the DEMF demo company.</span></span>

1. <span data-ttu-id="d9956-107">Dans le volet de navigation, accédez **Modules > Comptabilité fournisseur > Factures > Journal des factures**.</span><span class="sxs-lookup"><span data-stu-id="d9956-107">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice journal**.</span></span>
2. <span data-ttu-id="d9956-108">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="d9956-108">Select **New**.</span></span>
3. <span data-ttu-id="d9956-109">Dans le champ **Nom** de la nouvelle ligne, sélectionnez une option du menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="d9956-109">In the **Name** field of the new row, select an option in the drop-down menu.</span></span>
4. <span data-ttu-id="d9956-110">Dans le volet Actions, sélectionnez **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="d9956-110">In the Action Pane, select **Lines**.</span></span>
5. <span data-ttu-id="d9956-111">Dans le champ **Compte**, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="d9956-111">In the **Account** field, specify the desired values.</span></span>
6. <span data-ttu-id="d9956-112">Dans le champ **Facture**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="d9956-112">In the **Invoice** field, type a value.</span></span>
7. <span data-ttu-id="d9956-113">Dans le champ **Crédit**, entrez un numéro.</span><span class="sxs-lookup"><span data-stu-id="d9956-113">In the **Credit** field, enter a number.</span></span>
8. <span data-ttu-id="d9956-114">Dans le champ **Compte de contrepartie**, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="d9956-114">In the **Offset account** field, specify the desired values.</span></span>
9. <span data-ttu-id="d9956-115">Sélectionnez **Taxe**.</span><span class="sxs-lookup"><span data-stu-id="d9956-115">Select **Sales tax**.</span></span>
10. <span data-ttu-id="d9956-116">Dans le champ **Montant réel de taxe total**, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="d9956-116">In the **Total actual sales tax amount** field, enter a number.</span></span>
11. <span data-ttu-id="d9956-117">Sous l’onglet **Ajustement**, les montants de taxe peuvent être ajustés par code taxe.</span><span class="sxs-lookup"><span data-stu-id="d9956-117">On the **Adjustment** tab, the sales tax amounts can be adjusted per sales tax code.</span></span>
12. <span data-ttu-id="d9956-118">Sélectionnez **Réinitialiser les montants réels des montants calculés**.</span><span class="sxs-lookup"><span data-stu-id="d9956-118">Select **Reset actual from calculated amounts**.</span></span>
13. <span data-ttu-id="d9956-119">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d9956-119">Select **OK**.</span></span>
14. <span data-ttu-id="d9956-120">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d9956-120">Select **Save**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]