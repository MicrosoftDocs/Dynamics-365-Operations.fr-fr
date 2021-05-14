---
title: L'enregistrement TaxTrans n'est pas généré
description: Cette rubrique fournit des informations de dépannage qui peuvent vous aider lorsque l'enregistrement TaxTrans n'est pas généré.
author: qire
manager: beya
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 0c7414cc39198ff4d5be9b4c41ca62f9c78c9250
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947637"
---
# <a name="taxtrans-record-isnt-generated"></a><span data-ttu-id="3e27b-103">L'enregistrement TaxTrans n'est pas généré</span><span class="sxs-lookup"><span data-stu-id="3e27b-103">TaxTrans record isn't generated</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3e27b-104">Si vous sélectionnez **Taxe validée** pour une transaction, mais que la page **Taxe validée** n'affiche aucune ligne de taxe ou s'il manque une ligne de taxe, l'enregistrement **TaxTrans** risque de ne pas été généré.</span><span class="sxs-lookup"><span data-stu-id="3e27b-104">If you select **Posted sales tax** for a transaction, but the **Posted sales tax** page either shows no tax lines or is missing a tax line, the **TaxTrans** record might not have been generated.</span></span>

<span data-ttu-id="3e27b-105">[![Page Taxe validée sans éléments de ligne](./media/taxtrans-is-not-generated-Picture1.png)](./media/taxtrans-is-not-generated-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="3e27b-105">[![Posted sales tax page that has no line items](./media/taxtrans-is-not-generated-Picture1.png)](./media/taxtrans-is-not-generated-Picture1.png)</span></span>

<span data-ttu-id="3e27b-106">Pour résoudre ce problème, suivez les étapes des sections suivantes selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="3e27b-106">To troubleshoot this issue, follow the steps in the following sections as required.</span></span>

## <a name="check-the-sales-tax-before-you-post-the-transaction"></a><span data-ttu-id="3e27b-107">Vérifier la taxe de vente avant de valider la transaction</span><span class="sxs-lookup"><span data-stu-id="3e27b-107">Check the sales tax before you post the transaction</span></span>

1. <span data-ttu-id="3e27b-108">Avant de valider la transaction, sur la page **Validation de la facture**, sélectionnez **Taxe de vente** pour vérifier le calcul.</span><span class="sxs-lookup"><span data-stu-id="3e27b-108">Before you post the transaction, on the **Posting invoice** page, select **Sales tax** to check the calculation.</span></span>

    <span data-ttu-id="3e27b-109">[![Bouton Taxe sur la page Validation de la facture](./media/taxtrans-is-not-generated-Picture2.png)](./media/taxtrans-is-not-generated-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="3e27b-109">[![Sales tax button on the Posting invoice page](./media/taxtrans-is-not-generated-Picture2.png)](./media/taxtrans-is-not-generated-Picture2.png)</span></span>

2. <span data-ttu-id="3e27b-110">Sur la page **Transactions de taxe temporaires**, examinez le résultat du calcul.</span><span class="sxs-lookup"><span data-stu-id="3e27b-110">On the **Temporary sales tax transactions** page, review the result of the calculation.</span></span> <span data-ttu-id="3e27b-111">Si aucune taxe n'est calculée, voir [La taxe n'est pas calculée ou le montant de la taxe est égal à zéro](sales-tax-troubleshooting-tax-not-calculated-amount-zero.md).</span><span class="sxs-lookup"><span data-stu-id="3e27b-111">If no tax is calculated, see [Tax isn't calculated or the tax amount is zero](sales-tax-troubleshooting-tax-not-calculated-amount-zero.md).</span></span>

## <a name="find-the-taxtrans-record-in-all-posted-sales-tax"></a><span data-ttu-id="3e27b-112">Rechercher l'enregistrement TaxTrans dans toutes les taxes de vente affichées</span><span class="sxs-lookup"><span data-stu-id="3e27b-112">Find the TaxTrans record in all posted sales tax</span></span>

1. <span data-ttu-id="3e27b-113">Allez dans **Taxe** \> **Recherches et états** \> **Taxe (recherches)** > **Taxe validée**.</span><span class="sxs-lookup"><span data-stu-id="3e27b-113">Go to **Tax** \> **Inquiries and reports** \> **Sales tax inquiries** > **Posted sales tax**.</span></span>
2. <span data-ttu-id="3e27b-114">Dans l'en-tête de colonne **Justificatif**, sélectionnez le symbole de filtre pour trouver l'enregistrement **TaxTrans**.</span><span class="sxs-lookup"><span data-stu-id="3e27b-114">In the **Voucher** column heading, select the filter symbol to find the **TaxTrans** record.</span></span>
3. <span data-ttu-id="3e27b-115">Si vous trouvez les enregistrements de taxe de vente que vous recherchez, vérifiez la date.</span><span class="sxs-lookup"><span data-stu-id="3e27b-115">If you find the sales tax records that you're looking for, check the date.</span></span> <span data-ttu-id="3e27b-116">Si la date diffère de celle de l'en-tête du journal, créez une demande de service Microsoft pour une prise en charge supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="3e27b-116">If the date differs from the date of the journal header, create a Microsoft service request for additional support.</span></span>

    <span data-ttu-id="3e27b-117">[![Page de la taxe validée](./media/taxtrans-is-not-generated-Picture4.png)](./media/taxtrans-is-not-generated-Picture4.png)</span><span class="sxs-lookup"><span data-stu-id="3e27b-117">[![Posted sales tax page](./media/taxtrans-is-not-generated-Picture4.png)](./media/taxtrans-is-not-generated-Picture4.png)</span></span>

## <a name="debug-to-check-details"></a><span data-ttu-id="3e27b-118">Déboguer pour vérifier les détails</span><span class="sxs-lookup"><span data-stu-id="3e27b-118">Debug to check details</span></span>

1. <span data-ttu-id="3e27b-119">Pour plus d'informations sur la façon de déboguer et de déterminer si **TmpTaxWorkTrans** et **Taxe non engagée** sont correctement générés, voir [La valeur du champ dans TaxTrans est incorrecte](sales-tax-troubleshooting-field-value-taxtrans-incorrect.md).</span><span class="sxs-lookup"><span data-stu-id="3e27b-119">For information about how to debug and determine whether **TmpTaxWorkTrans** and **TaxUncommitted** are correctly generated, see [Field value in TaxTrans is incorrect](sales-tax-troubleshooting-field-value-taxtrans-incorrect.md).</span></span>
2. <span data-ttu-id="3e27b-120">Si **TaxTmpWorkTrans** ou **TaxUncommitted** est correctement généré, ajoutez un point d'arrêt à **TaxPost::SaveAndPost()** et **Tax::SaveAndPost** pour déboguer la raison pour laquelle **TaxTrans** n'est pas inséré.</span><span class="sxs-lookup"><span data-stu-id="3e27b-120">If **TaxTmpWorkTrans** or **TaxUncommitted** is correctly generated, add a breakpoint at **TaxPost::SaveAndPost()** and **Tax::SaveAndPost** to debug the reason why **TaxTrans** isn't inserted.</span></span>

    <span data-ttu-id="3e27b-121">[![Points d'arrêt ajoutés dans le code](./media/taxtrans-is-not-generated-Picture5.png)](./media/taxtrans-is-not-generated-Picture5.png)</span><span class="sxs-lookup"><span data-stu-id="3e27b-121">[![Breakpoints added in code](./media/taxtrans-is-not-generated-Picture5.png)](./media/taxtrans-is-not-generated-Picture5.png)</span></span>

    <span data-ttu-id="3e27b-122">[![Résultats des points d'arrêt ajoutés](./media/taxtrans-is-not-generated-Picture6.png)](./media/taxtrans-is-not-generated-Picture6.png)</span><span class="sxs-lookup"><span data-stu-id="3e27b-122">[![Results of added breakpoints](./media/taxtrans-is-not-generated-Picture6.png)](./media/taxtrans-is-not-generated-Picture6.png)</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="3e27b-123">Déterminer si la personnalisation existe</span><span class="sxs-lookup"><span data-stu-id="3e27b-123">Determine whether customization exists</span></span>

<span data-ttu-id="3e27b-124">Si vous avez terminé les étapes des sections précédentes mais que vous n'avez trouvé aucun problème, déterminez s'il existe une personnalisation.</span><span class="sxs-lookup"><span data-stu-id="3e27b-124">If you've completed the steps in the previous sections but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="3e27b-125">Si aucune personnalisation n'existe, créez une demande de service Microsoft pour une assistance supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="3e27b-125">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
