---
title: Retenue à la source dans les transactions d’achat
description: Pour les fournisseurs qui sont soumis à une retenue à la source, vous pouvez attribuer le **Groupe de retenue à la source** sur la page **Tous les fournisseurs**.
author: roschlom
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: faeaf0746532875d3517a208c9c338c112bf2c77
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816881"
---
# <a name="withholding-tax-in-purchase-transactions"></a><span data-ttu-id="7e7fa-103">Retenue à la source dans les transactions d’achat</span><span class="sxs-lookup"><span data-stu-id="7e7fa-103">Withholding tax in purchase transactions</span></span>

<span data-ttu-id="7e7fa-104">Pour les fournisseurs qui sont soumis à une retenue à la source, vous pouvez attribuer le **Groupe de retenue à la source** sur la page **Tous les fournisseurs**.</span><span class="sxs-lookup"><span data-stu-id="7e7fa-104">For vendors who are liable to withholding tax, you can assign the default **Withholding tax group** on the **All vendors** page.</span></span>

1. <span data-ttu-id="7e7fa-105">Allez dans **Volet de navigation > Modules > Comptabilité fournisseur > Fournisseur > Tous les fournisseurs**.</span><span class="sxs-lookup"><span data-stu-id="7e7fa-105">Go to **Navigation pane > Modules > Accounts payable > Vendors > All vendors**.</span></span>

2. <span data-ttu-id="7e7fa-106">Cliquez sur le compte fournisseur concerné, puis sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="7e7fa-106">Click the respective Vendor account, click **Edit**.</span></span>

3. <span data-ttu-id="7e7fa-107">Dans l’onglet **Facturation et livraison**, définissez le champ **Calcul de la retenue à la source** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="7e7fa-107">In **Invoice and delivery** tab, set the **Calculate withholding tax** field to **Yes**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="7e7fa-108">La retenue à la source ne sera pas calculée si le champ **Calcul de la retenue à la source** n’est pas activé pour ce fournisseur dans les données principales.</span><span class="sxs-lookup"><span data-stu-id="7e7fa-108">Withholding tax will not be calculated if **Calculate withholding tax** is not switched on for this vendor in the data.</span></span>

4. <span data-ttu-id="7e7fa-109">Sélectionnez un groupe de retenue à la source dans le **Groupe de retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="7e7fa-109">Select a withholding tax group in **Withholding tax group**.</span></span>

5. <span data-ttu-id="7e7fa-110">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="7e7fa-110">Click **Save**.</span></span>

<span data-ttu-id="7e7fa-111">Pour les articles/services soumis à une retenue à la source, vous pouvez attribuer la valeur par défaut du **Groupe de retenue à la source d’articles** dans **Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="7e7fa-111">For items/services which are liable to withholding tax, you can assign the default **Item withholding tax group** in **Released Products**.</span></span>

1. <span data-ttu-id="7e7fa-112">Accédez à **Volet de navigation > Modules > Gestion d’informations sur les produits > Produits > Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="7e7fa-112">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>

2. <span data-ttu-id="7e7fa-113">Cliquez sur le numéro d’article concerné, puis sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="7e7fa-113">Click the respective Item number, click **Edit**.</span></span>

3. <span data-ttu-id="7e7fa-114">Dans l’onglet **Achat**, cliquez sur **Calcul de la retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="7e7fa-114">In **Purchase** tab, click **Calculate withholding tax**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="7e7fa-115">La retenue à la source ne sera pas calculée si le champ **Calcul de la retenue à la source** n’est pas défini sur **Oui** pour cet article dans l’onglet **Achat** sur la page **Produit lancé**.</span><span class="sxs-lookup"><span data-stu-id="7e7fa-115">Withholding tax will not be calculated if **Calculate withholding tax** isn't set to **Yes** for this Item in the **Purchase** tab on the **Released product** page.</span></span>

4. <span data-ttu-id="7e7fa-116">Sélectionnez un groupe de retenue à la source d’articles dans la liste **Groupe de retenue à la source d’articles**.</span><span class="sxs-lookup"><span data-stu-id="7e7fa-116">Select an item withholding tax group in **Item withholding tax group** list.</span></span>

5. <span data-ttu-id="7e7fa-117">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="7e7fa-117">Click **Save**.</span></span>

<span data-ttu-id="7e7fa-118">Les groupes de retenue à la source et les groupes de retenue à la source d’articles peuvent être attribués dans les pages :</span><span class="sxs-lookup"><span data-stu-id="7e7fa-118">Withholding tax groups and Item withholding tax groups can be assigned in pages:</span></span> 

- <span data-ttu-id="7e7fa-119">**Commande fournisseur**</span><span class="sxs-lookup"><span data-stu-id="7e7fa-119">**Purchase order**</span></span>
- <span data-ttu-id="7e7fa-120">**Facture fournisseur**</span><span class="sxs-lookup"><span data-stu-id="7e7fa-120">**Vendor invoice**</span></span>
- <span data-ttu-id="7e7fa-121">**Journal des factures**</span><span class="sxs-lookup"><span data-stu-id="7e7fa-121">**Invoice journal**</span></span>

<span data-ttu-id="7e7fa-122">Le groupe de retenue à la source et le groupe de retenue à la source d’articles par défaut seront reportés dans les lignes lors de la création des **Commandes fournisseur** et/ou des **Factures fournisseur en attente**.</span><span class="sxs-lookup"><span data-stu-id="7e7fa-122">The default Withholding tax group and Item withholding tax group will be carried into the lines when creating **Purchase orders** and/or **Pending Vendor invoices**.</span></span> <span data-ttu-id="7e7fa-123">Pour le **Journal des factures fournisseur**, vous pouvez activer **Calcul de la retenue à la source** et sélectionner **Groupe de retenue à la source d’articles** dans l’onglet **Général** du journal.</span><span class="sxs-lookup"><span data-stu-id="7e7fa-123">For **Vendor invoice journal**, you can switch on **Calculate withholding tax** and select **Item withholding tax group** in the **General** tab in the journal.</span></span>

<span data-ttu-id="7e7fa-124">Le montant temporaire de la retenue à la source est disponible dans le champ **Retenue à la source ajustée** de l’onglet **Totaux** sur la page **Bon de commande**.</span><span class="sxs-lookup"><span data-stu-id="7e7fa-124">The temporary amount of withholding tax is available in the field **Adjusted withholding tax** of the **Totals** tab on the **Purchase order** page.</span></span>

![La retenue à la source est incluse dans le bon de commande](media/withholding-tax-adjusted.png)

<span data-ttu-id="7e7fa-126">La retenue à la source est calculée dans le **Journal des paiements fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="7e7fa-126">Withholding tax is calculated on **Vendor payment journal**.</span></span> <span data-ttu-id="7e7fa-127">Vous pouvez ajuster manuellement les codes de retenue à la source applicables, ainsi que les montants réels de la retenue à la source dans l’onglet **Retenue à la source** sur la page **Régler des transactions**.</span><span class="sxs-lookup"><span data-stu-id="7e7fa-127">You can manually adjust the applicable withholding tax codes as well as the actual withholding tax amounts in the **Withholding tax** tab on the **Settle transactions** page.</span></span>

![La retenue peut être ajustée manuellement sur la page Règlement des transactions](media/withholding-tax-vendor-payment-tab.png)

<span data-ttu-id="7e7fa-129">Le montant de la retenue à la source dérivé sera déduit du paiement du fournisseur et imputé au compte **Compte de retenue à la source** dans un justificatif associé.</span><span class="sxs-lookup"><span data-stu-id="7e7fa-129">The derived withholding tax amount will be deducted from the vendor payment and posted to the **Withholding tax account** in a related voucher.</span></span>

![Compte de retenue à la source montrant un justificatif associé](media/withholding-tax-adjusted.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]