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
ms.openlocfilehash: 2536e87953267eae13cf3b42c2bd5476fc647c22
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994713"
---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a><span data-ttu-id="affa7-103">Calculer et ajuster la taxe sur une facture fournisseur</span><span class="sxs-lookup"><span data-stu-id="affa7-103">Calculate and adjust sales tax on a vendor invoice</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="affa7-104">Cette rubrique explique comment ajuster la taxe sur une facture fournisseur.</span><span class="sxs-lookup"><span data-stu-id="affa7-104">This topic explains how to adjust sales tax on a vendor invoice.</span></span> <span data-ttu-id="affa7-105">Si le document source d’origine affiche différents montants de taxe calculés, vous pouvez régler ces montants avant la validation.</span><span class="sxs-lookup"><span data-stu-id="affa7-105">If the original source document displays different tax amounts as calculated, you can adjust those amounts before posting.</span></span> <span data-ttu-id="affa7-106">La société fictive DEMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="affa7-106">This task uses the DEMF demo company.</span></span>

1. <span data-ttu-id="affa7-107">Dans le volet de navigation, accédez **Modules > Comptabilité fournisseur > Factures > Journal des factures**.</span><span class="sxs-lookup"><span data-stu-id="affa7-107">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice journal**.</span></span>
2. <span data-ttu-id="affa7-108">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="affa7-108">Select **New**.</span></span>
3. <span data-ttu-id="affa7-109">Dans le champ **Nom** de la nouvelle ligne, sélectionnez une option du menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="affa7-109">In the **Name** field of the new row, select an option in the drop-down menu.</span></span>
4. <span data-ttu-id="affa7-110">Dans le volet Actions, sélectionnez **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="affa7-110">In the Action Pane, select **Lines**.</span></span>
5. <span data-ttu-id="affa7-111">Dans le champ **Compte**, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="affa7-111">In the **Account** field, specify the desired values.</span></span>
6. <span data-ttu-id="affa7-112">Dans le champ **Facture**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="affa7-112">In the **Invoice** field, type a value.</span></span>
7. <span data-ttu-id="affa7-113">Dans le champ **Crédit**, entrez un numéro.</span><span class="sxs-lookup"><span data-stu-id="affa7-113">In the **Credit** field, enter a number.</span></span>
8. <span data-ttu-id="affa7-114">Dans le champ **Compte de contrepartie**, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="affa7-114">In the **Offset account** field, specify the desired values.</span></span>
9. <span data-ttu-id="affa7-115">Sélectionnez **Taxe**.</span><span class="sxs-lookup"><span data-stu-id="affa7-115">Select **Sales tax**.</span></span>
10. <span data-ttu-id="affa7-116">Dans le champ **Montant réel de taxe total**, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="affa7-116">In the **Total actual sales tax amount** field, enter a number.</span></span>
11. <span data-ttu-id="affa7-117">Sous l’onglet **Ajustement**, les montants de taxe peuvent être ajustés par code taxe.</span><span class="sxs-lookup"><span data-stu-id="affa7-117">On the **Adjustment** tab, the sales tax amounts can be adjusted per sales tax code.</span></span>
12. <span data-ttu-id="affa7-118">Sélectionnez **Réinitialiser les montants réels des montants calculés**.</span><span class="sxs-lookup"><span data-stu-id="affa7-118">Select **Reset actual from calculated amounts**.</span></span>
13. <span data-ttu-id="affa7-119">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="affa7-119">Select **OK**.</span></span>
14. <span data-ttu-id="affa7-120">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="affa7-120">Select **Save**.</span></span>

