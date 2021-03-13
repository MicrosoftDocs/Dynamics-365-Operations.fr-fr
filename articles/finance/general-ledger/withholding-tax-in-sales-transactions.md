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
ms.openlocfilehash: c50f6df1c63c91107da65f463934565f786d6ccd
ms.sourcegitcommit: 630a0b3f800f36ced49b79156dd52132904fef75
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2021
ms.locfileid: "5060736"
---
# <a name="withholding-tax-in-sales-transactions"></a><span data-ttu-id="51dab-104">Retenue à la source dans les transactions de vente</span><span class="sxs-lookup"><span data-stu-id="51dab-104">Withholding tax in sales transactions</span></span>

<span data-ttu-id="51dab-105">Cette rubrique répertorie les étapes permettant d'éviter le calcul de la retenue à la source pour les clients sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="51dab-105">This topic lists the steps for avoiding the calculation of withholding tax for selected customers.</span></span> <span data-ttu-id="51dab-106">Pour les clients qui spécifient une retenue à la source dans leurs paiements, vous pouvez affecter le **Groupe de retenue à la source** sur la page **Clients**.</span><span class="sxs-lookup"><span data-stu-id="51dab-106">For customers who specify withholding tax in their payments to you, you can assign the default **Withholding tax group** on the **Customers** page.</span></span> 

1. <span data-ttu-id="51dab-107">Allez dans **Volet de navigation > Modules > Comptabilité client > Clients > Tous les clients**.</span><span class="sxs-lookup"><span data-stu-id="51dab-107">Go to **Navigation pane > Modules > Accounts receivable > Customers > All customers**.</span></span>

2. <span data-ttu-id="51dab-108">Cliquez sur le compte client concerné, puis sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="51dab-108">Click the respective customer account, click **Edit**.</span></span>

3. <span data-ttu-id="51dab-109">Dans l'onglet **Facturation et livraison**, définissez le champ **Calcul de la retenue à la source** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="51dab-109">In the **Invoice and delivery** tab, set the **Calculate withholding tax** field to **Yes**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="51dab-110">La retenue à la source ne sera pas calculée si le champ **Calcul de la retenue à la source** n'est pas activé pour ce client dans les données principales.</span><span class="sxs-lookup"><span data-stu-id="51dab-110">Withholding tax will not be calculated if **Calculate withholding tax** is not switched on for this customer in the master data.</span></span>

4. <span data-ttu-id="51dab-111">Sélectionnez un groupe de retenue à la source dans le **Groupe de retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="51dab-111">Select a withholding tax group in **Withholding tax group**.</span></span>

5. <span data-ttu-id="51dab-112">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="51dab-112">Click **Save**.</span></span>

<span data-ttu-id="51dab-113">Pour les articles/services soumis à une retenue à la source, vous pouvez attribuer la valeur par défaut du **Groupe de retenue à la source d'articles** dans **Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="51dab-113">For items/services, which are liable to withholding tax, you can assign the default **Item withholding tax group** in **Released Products**.</span></span>

1. <span data-ttu-id="51dab-114">Accédez à **Volet de navigation > Modules > Gestion d'informations sur les produits > Produits > Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="51dab-114">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>

2. <span data-ttu-id="51dab-115">Cliquez sur le numéro d’article concerné, puis sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="51dab-115">Click the respective Item number, click **Edit**.</span></span>

3. <span data-ttu-id="51dab-116">Dans l'onglet **Vente**, cliquez sur **Calcul de la retenue à la source**.</span><span class="sxs-lookup"><span data-stu-id="51dab-116">In the **Sell** tab, click **Calculate withholding tax**.</span></span>

   > [!NOTE] 
   > <span data-ttu-id="51dab-117">La retenue à la source ne sera pas calculée si le champ **Calcul de la retenue à la source** n'est pas défini sur **Oui** pour cet article dans l'onglet **Vente** sur la page **Produit lancé**.</span><span class="sxs-lookup"><span data-stu-id="51dab-117">Withholding tax will not be calculated if **Calculate withholding tax** is not set to **Yes** for this Item in the **Sell** tab on the **Released product** page.</span></span>

4. <span data-ttu-id="51dab-118">Sélectionnez un groupe de retenue à la source d'articles dans la liste **Groupe de retenue à la source d'articles**.</span><span class="sxs-lookup"><span data-stu-id="51dab-118">Select an Item withholding tax group in **Item withholding tax group** list.</span></span>

5. <span data-ttu-id="51dab-119">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="51dab-119">Click **Save**.</span></span>

<span data-ttu-id="51dab-120">Les groupes de retenue à la source et les groupes de retenue à la source d'articles peuvent être attribués à l'aide de la page **Commande client**.</span><span class="sxs-lookup"><span data-stu-id="51dab-120">Withholding tax groups and Item withholding tax groups can be assigned using the **Sales order** page.</span></span> 

<span data-ttu-id="51dab-121">Le groupe de retenue à la source par défaut et le groupe de retenue à la source d'articles seront utilisés comme entrées par défaut sur les lignes de commande client lorsque vous créez une nouvelle commande client.</span><span class="sxs-lookup"><span data-stu-id="51dab-121">The default Withholding tax group and Item withholding tax group will be used as default entries on sales order lines when you create a new sales order.</span></span>

<span data-ttu-id="51dab-122">La retenue à la source est calculée et comptabilisée avec le **Journal des paiements client**.</span><span class="sxs-lookup"><span data-stu-id="51dab-122">Withholding tax is calculated and posted with **Customer payment journal**.</span></span> <span data-ttu-id="51dab-123">Vous pouvez ajuster manuellement le code de retenue à la source applicable, ainsi que le montant réel de la retenue à la source dans l'onglet **Retenue à la source** sur la page **Régler des transactions**.</span><span class="sxs-lookup"><span data-stu-id="51dab-123">You can manually adjust the applicable withholding tax code, as well as the actual withholding tax amount in the **Withholding tax** tab on the **Settle transactions** page.</span></span>

<span data-ttu-id="51dab-124">Le montant de la retenue à la source calculé sera déduit du paiement du client et imputé au compte **Compensation de la retenue à la source** dans un justificatif associé.</span><span class="sxs-lookup"><span data-stu-id="51dab-124">The calculated withholding tax amount will be deducted from the customer payment and posted to the **Withholding tax offset** account in a related voucher.</span></span>
