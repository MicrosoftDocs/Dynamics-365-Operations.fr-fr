---
title: Retenue à la source dans les transactions de vente
description: Cette rubrique répertorie les étapes permettant d'éviter le calcul de la retenue à la source pour les clients sélectionnés. Pour les clients qui spécifient une retenue à la source dans leurs paiements, vous pouvez affecter le groupe de retenue à la source par défaut.
author: roschlom
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: c839df1b54cdb60beefa6dc6c3fc6e945a6eac85
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5256641"
---
# <a name="withholding-tax-in-sales-transactions"></a><span data-ttu-id="c498e-104">Retenue à la source dans les transactions de vente</span><span class="sxs-lookup"><span data-stu-id="c498e-104">Withholding tax in sales transactions</span></span>

<span data-ttu-id="c498e-105">Cette rubrique répertorie les étapes permettant d'éviter le calcul de la retenue à la source pour les clients sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="c498e-105">This topic lists the steps for avoiding the calculation of withholding tax for selected customers.</span></span> <span data-ttu-id="c498e-106">Pour les clients qui spécifient une retenue à la source dans leurs paiements, vous pouvez affecter le **Groupe de retenue à la source** sur la page **Clients**.</span><span class="sxs-lookup"><span data-stu-id="c498e-106">For customers who specify withholding tax in their payments to you, you can assign the default **Withholding tax group** on the **Customers** page.</span></span> 

1. <span data-ttu-id="c498e-107">Allez dans **Volet de navigation > Modules > Comptabilité client > Clients > Tous les clients**.</span><span class="sxs-lookup"><span data-stu-id="c498e-107">Go to **Navigation pane > Modules > Accounts receivable > Customers > All customers**.</span></span>

2. <span data-ttu-id="c498e-108">Cliquez sur le compte client concerné, puis sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="c498e-108">Click the respective customer account, click **Edit**.</span></span>

3. <span data-ttu-id="c498e-109">Dans l'onglet **Facturation et livraison**, définissez le champ **Calcul de la retenue à la source** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="c498e-109">In the **Invoice and delivery** tab, set the **Calculate withholding tax** field to **Yes**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="c498e-110">La retenue à la source ne sera pas calculée si le champ **Calcul de la retenue à la source** n'est pas activé pour ce client dans les données principales.</span><span class="sxs-lookup"><span data-stu-id="c498e-110">Withholding tax will not be calculated if **Calculate withholding tax** is not switched on for this customer in the master data.</span></span>

4. <span data-ttu-id="c498e-111">Sélectionnez un groupe de retenue à la source dans le **Groupe de retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="c498e-111">Select a withholding tax group in **Withholding tax group**.</span></span>

5. <span data-ttu-id="c498e-112">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c498e-112">Click **Save**.</span></span>

<span data-ttu-id="c498e-113">Pour les articles/services soumis à une retenue à la source, vous pouvez attribuer la valeur par défaut du **Groupe de retenue à la source d'articles** dans **Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="c498e-113">For items/services, which are liable to withholding tax, you can assign the default **Item withholding tax group** in **Released Products**.</span></span>

1. <span data-ttu-id="c498e-114">Accédez à **Volet de navigation > Modules > Gestion d'informations sur les produits > Produits > Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="c498e-114">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>

2. <span data-ttu-id="c498e-115">Cliquez sur le numéro d’article concerné, puis sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="c498e-115">Click the respective Item number, click **Edit**.</span></span>

3. <span data-ttu-id="c498e-116">Dans l'onglet **Vente**, cliquez sur **Calcul de la retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="c498e-116">In the **Sell** tab, click **Calculate withholding tax**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="c498e-117">La retenue à la source ne sera pas calculée si le champ **Calcul de la retenue à la source** n'est pas défini sur **Oui** pour cet article dans l'onglet **Vente** sur la page **Produit lancé**.</span><span class="sxs-lookup"><span data-stu-id="c498e-117">Withholding tax will not be calculated if **Calculate withholding tax** is not set to **Yes** for this Item in the **Sell** tab on the **Released product** page.</span></span>

4. <span data-ttu-id="c498e-118">Sélectionnez un groupe de retenue à la source d'articles dans la liste **Groupe de retenue à la source d'articles**.</span><span class="sxs-lookup"><span data-stu-id="c498e-118">Select an Item withholding tax group in **Item withholding tax group** list.</span></span>

5. <span data-ttu-id="c498e-119">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c498e-119">Click **Save**.</span></span>

<span data-ttu-id="c498e-120">Les groupes de retenue à la source et les groupes de retenue à la source d'articles peuvent être attribués à l'aide de la page **Commande client**.</span><span class="sxs-lookup"><span data-stu-id="c498e-120">Withholding tax groups and Item withholding tax groups can be assigned using the **Sales order** page.</span></span> 

<span data-ttu-id="c498e-121">Le groupe de retenue à la source par défaut et le groupe de retenue à la source d'articles seront utilisés comme entrées par défaut sur les lignes de commande client lorsque vous créez une nouvelle commande client.</span><span class="sxs-lookup"><span data-stu-id="c498e-121">The default Withholding tax group and Item withholding tax group will be used as default entries on sales order lines when you create a new sales order.</span></span>

<span data-ttu-id="c498e-122">La retenue à la source est calculée et comptabilisée avec le **Journal des paiements client**.</span><span class="sxs-lookup"><span data-stu-id="c498e-122">Withholding tax is calculated and posted with **Customer payment journal**.</span></span> <span data-ttu-id="c498e-123">Vous pouvez ajuster manuellement le code de retenue à la source applicable, ainsi que le montant réel de la retenue à la source dans l'onglet **Retenue à la source** sur la page **Régler des transactions**.</span><span class="sxs-lookup"><span data-stu-id="c498e-123">You can manually adjust the applicable withholding tax code, as well as the actual withholding tax amount in the **Withholding tax** tab on the **Settle transactions** page.</span></span>

<span data-ttu-id="c498e-124">Le montant de la retenue à la source calculé sera déduit du paiement du client et imputé au compte **Compensation de la retenue à la source** dans un justificatif associé.</span><span class="sxs-lookup"><span data-stu-id="c498e-124">The calculated withholding tax amount will be deducted from the customer payment and posted to the **Withholding tax offset** account in a related voucher.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]