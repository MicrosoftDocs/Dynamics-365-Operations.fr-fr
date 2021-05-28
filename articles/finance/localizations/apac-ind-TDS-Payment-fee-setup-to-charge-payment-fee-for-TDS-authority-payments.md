---
title: Paramétrer des frais de paiement pour les paiements à l'administration TDS
description: Cette rubrique explique comment configurer les frais de paiement qui sont facturés pour les paiements d'autorisation de retenue de la taxe à la source (TDS).
author: kailiang
ms.date: 02/12/2021
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
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: b52331bb1c7a1bc2c764008112f3df9cc0385995
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023253"
---
# <a name="set-up-payment-fees-for-tds-authority-payments"></a><span data-ttu-id="0e88e-103">Paramétrer des frais de paiement pour les paiements à l'administration TDS</span><span class="sxs-lookup"><span data-stu-id="0e88e-103">Set up payment fees for TDS authority payments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0e88e-104">Cette rubrique explique comment configurer les frais de paiement qui sont facturés pour les paiements d'autorisation de retenue de la taxe à la source (TDS).</span><span class="sxs-lookup"><span data-stu-id="0e88e-104">This topic explains how to set up payment fees that are charged for Tax Deducted at Source (TDS) authority payments.</span></span>

1. <span data-ttu-id="0e88e-105">Accédez à **Comptabilité fournisseur \> Paramétrage des paiements \> Frais de paiement**.</span><span class="sxs-lookup"><span data-stu-id="0e88e-105">Go to **Accounts payable \> Payment setup \> Payment fee**.</span></span>

    <span data-ttu-id="0e88e-106">[![Page Frais de paiement](./media/apac-ind-TDS-28.png)](./media/apac-ind-TDS-28.png)</span><span class="sxs-lookup"><span data-stu-id="0e88e-106">[![Payment fee page](./media/apac-ind-TDS-28.png)](./media/apac-ind-TDS-28.png)</span></span>

2. <span data-ttu-id="0e88e-107">Sélectionnez **Nouveau** pour créer des frais de paiement, puis entrez les informations requises.</span><span class="sxs-lookup"><span data-stu-id="0e88e-107">Select **New** to create a payment fee, and enter the required details.</span></span>
3. <span data-ttu-id="0e88e-108">Dans le champ **Type de frais**, sélectionnez le type de frais de paiement :</span><span class="sxs-lookup"><span data-stu-id="0e88e-108">In the **Fee type** field, select the type of payment fee:</span></span>

    - <span data-ttu-id="0e88e-109">**None**</span><span class="sxs-lookup"><span data-stu-id="0e88e-109">**None**</span></span>
    - <span data-ttu-id="0e88e-110">**Intérêt** - Des intérêts sont facturés sur les paiements en retard qui sont effectués au fournisseur de l'autorité TDS.</span><span class="sxs-lookup"><span data-stu-id="0e88e-110">**Interest** – Interest is charged on late payments that are made to the TDS authority vendor.</span></span>
    - <span data-ttu-id="0e88e-111">**Autres** - D'autres frais sont facturés sur les paiements en retard qui sont effectués au fournisseur de l'autorité TDS.</span><span class="sxs-lookup"><span data-stu-id="0e88e-111">**Others** – Other charges are charged on late payments that are made to the TDS authority vendor.</span></span>

    <span data-ttu-id="0e88e-112">Si vous sélectionnez **Intérêt** ou **Autres**, le champ **Frais** est automatiquement défini sur **Registre**.</span><span class="sxs-lookup"><span data-stu-id="0e88e-112">If you select **Interest** or **Others**, the **Charge** field is automatically set to **Ledger**.</span></span>

4. <span data-ttu-id="0e88e-113">Si vous avez sélectionné **Intérêt** ou **Autres** dans le champ **Type de champ**, dans le champ **Compte principal**, sélectionnez le compte général sur lequel imputer les intérêts ou autres frais.</span><span class="sxs-lookup"><span data-stu-id="0e88e-113">If you selected **Interest** or **Others** in the **Field type** field, in the **Main account** field, select the ledger account to post the interest or other charges to.</span></span>
5. <span data-ttu-id="0e88e-114">Renseignez les informations demandées.</span><span class="sxs-lookup"><span data-stu-id="0e88e-114">Enter the other required details.</span></span>
6. <span data-ttu-id="0e88e-115">Dans le volet Actions, sélectionnez **Configuration des frais de paiement** pour ouvrir la page **Configuration des frais de paiement**, où vous pouvez configurer les frais de paiement pour diverses combinaisons de banques, modes de paiement, spécifications de paiement, devises et intervalles de dates.</span><span class="sxs-lookup"><span data-stu-id="0e88e-115">On the Action Pane, select **Payment fee setup** to open the **Payment fee setup** page, where you can set up payment fees for various combinations of banks, methods of payment, payment specifications, currencies, and date intervals.</span></span>

    <span data-ttu-id="0e88e-116">[![Page Paramétrage des frais de paiement](./media/apac-ind-TDS-21.png)](./media/apac-ind-TDS-21.png)</span><span class="sxs-lookup"><span data-stu-id="0e88e-116">[![Payment fee setup page](./media/apac-ind-TDS-21.png)](./media/apac-ind-TDS-21.png)</span></span>

7. <span data-ttu-id="0e88e-117">Dans l'onglet **Aperçu**, dans le champ **Groupements**, spécifiez les banques pour lesquelles vous configurez les frais de paiement :</span><span class="sxs-lookup"><span data-stu-id="0e88e-117">On the **Overview** tab, in the **Groupings** field, specify which banks you're setting up the payment fee for:</span></span>

    - <span data-ttu-id="0e88e-118">**Tableau** - Les frais sont valables pour un compte bancaire spécifique.</span><span class="sxs-lookup"><span data-stu-id="0e88e-118">**Table** – The fee is valid for a specific bank account.</span></span>
    - <span data-ttu-id="0e88e-119">**Groupe** - Les frais sont valables pour un groupe bancaire spécifique.</span><span class="sxs-lookup"><span data-stu-id="0e88e-119">**Group** – The fee is valid for a specific bank group.</span></span>
    - <span data-ttu-id="0e88e-120">**Tous** : Les frais sont valides pour tous les comptes bancaires.</span><span class="sxs-lookup"><span data-stu-id="0e88e-120">**All** – The fee is valid for all the bank accounts.</span></span>

8. <span data-ttu-id="0e88e-121">Si vous avez sélectionné **Tableau** ou **Groupe** dans le champ **Regroupements**, dans le champ **Relation bancaire**, sélectionnez le compte bancaire ou le groupe bancaire pour lequel vous configurez les frais de paiement.</span><span class="sxs-lookup"><span data-stu-id="0e88e-121">If you selected **Table** or **Group** in the **Groupings** field, in the **Bank relation** field, select the specific bank account or bank group that you're setting up the payment fee for.</span></span>
9. <span data-ttu-id="0e88e-122">Dans le champ **Mode de paiement**, sélectionnez le mode de paiement des frais.</span><span class="sxs-lookup"><span data-stu-id="0e88e-122">In the **Method of payment** field, select the method of payment for the payment of fees.</span></span>
10. <span data-ttu-id="0e88e-123">Dans le champ **Spécification de paiement**, sélectionnez ou entrez le code de spécification de paiement qui a été généré sur la page **Spécification de paiement**.</span><span class="sxs-lookup"><span data-stu-id="0e88e-123">In the **Payment specification** field, select or enter the payment specification code that was generated on the **Payment specification** page.</span></span>
    - <span data-ttu-id="0e88e-124">La spécification de paiement est utilisée avec des modes de paiement électroniques.</span><span class="sxs-lookup"><span data-stu-id="0e88e-124">The Payment specification is used with electronic fund transfer methods of payment.</span></span>
12. <span data-ttu-id="0e88e-125">Dans le champ **Devise de paiement**, sélectionnez la devise qui active les frais.</span><span class="sxs-lookup"><span data-stu-id="0e88e-125">In the **Payment currency** field, select the currency that activates the fee.</span></span> <span data-ttu-id="0e88e-126">Seules les transactions utilisant la devise sélectionnée peuvent activer les frais.</span><span class="sxs-lookup"><span data-stu-id="0e88e-126">Only transactions that use the selected currency can activate the fee.</span></span> <span data-ttu-id="0e88e-127">Si vous laissez ce champ vide, toutes les devises activent les frais.</span><span class="sxs-lookup"><span data-stu-id="0e88e-127">If you leave this field blank, all currencies activate the fee.</span></span>
13. <span data-ttu-id="0e88e-128">Dans le champ **Pourcentage/montant**, sélectionnez la méthode de calcul.</span><span class="sxs-lookup"><span data-stu-id="0e88e-128">In the **Percentage/Amount** field, select the calculation method.</span></span> <span data-ttu-id="0e88e-129">Les options sont **Montant**, **Pourcentage** et **Intervalle**.</span><span class="sxs-lookup"><span data-stu-id="0e88e-129">The options are **Amount**, **Percent**, and **Interval**.</span></span>
14. <span data-ttu-id="0e88e-130">Dans le champ **Montant des frais**, indiquez le montant des frais en pourcentage du paiement ou en montant pour un paiement.</span><span class="sxs-lookup"><span data-stu-id="0e88e-130">In the **Fee amount** field, specify the fee amount as either a percentage of the payment or the amount for one payment.</span></span>
15. <span data-ttu-id="0e88e-131">Dans le champ **Devise des frais**, spécifiez le code devise pour les frais.</span><span class="sxs-lookup"><span data-stu-id="0e88e-131">In the **Fee currency** field, specify the currency code for the fee.</span></span>
16. <span data-ttu-id="0e88e-132">Sélectionnez l'onglet **Général** pour afficher ou modifier les détails du compte bancaire sélectionné.</span><span class="sxs-lookup"><span data-stu-id="0e88e-132">Select the **General** tab to view or modify the details for the selected bank account.</span></span>

    <span data-ttu-id="0e88e-133">[![Onglet Général](./media/apac-ind-TDS-22.png)](./media/apac-ind-TDS-22.png)</span><span class="sxs-lookup"><span data-stu-id="0e88e-133">[![General tab](./media/apac-ind-TDS-22.png)](./media/apac-ind-TDS-22.png)</span></span>

16. <span data-ttu-id="0e88e-134">Dans le champ **Minimum**, saisissez le montant minimum de la transaction qui active les frais.</span><span class="sxs-lookup"><span data-stu-id="0e88e-134">In the **Minimum** field, enter the minimum transaction amount that activates the fee.</span></span>
17. <span data-ttu-id="0e88e-135">Dans le champ **Maximum**, saisissez le montant maximum de la transaction qui active les frais.</span><span class="sxs-lookup"><span data-stu-id="0e88e-135">In the **Maximum** field, enter the maximum transaction amount that activates the fee.</span></span>
18. <span data-ttu-id="0e88e-136">Dans les champs **Date de début** et **Date de fin**, définissez une plage de dates pour le calcul des frais.</span><span class="sxs-lookup"><span data-stu-id="0e88e-136">In the **From date** and **To date** fields, define a date range for calculating fees.</span></span>
19. <span data-ttu-id="0e88e-137">Dans le champ **Frais minimum**, indiquez le montant des frais en pourcentage du paiement ou en montant pour un paiement.</span><span class="sxs-lookup"><span data-stu-id="0e88e-137">In the **Minimum fee** field, specify the amount of the fee as either a percentage of the payment or the amount for one payment.</span></span>
20. <span data-ttu-id="0e88e-138">Dans le champ **Groupe de taxe de vente**, sélectionnez le groupe de taxe de vente à utiliser pour calculer la taxe de vente pour le montant des frais.</span><span class="sxs-lookup"><span data-stu-id="0e88e-138">In the **Sales tax group** field, select the sales tax group to use to calculate the sales tax for the fee amount.</span></span>
21. <span data-ttu-id="0e88e-139">Dans le champ **Groupe de taxe de vente**, sélectionnez le groupe de taxe d'article à utiliser pour calculer la taxe de vente des articles pour le montant des frais.</span><span class="sxs-lookup"><span data-stu-id="0e88e-139">In the **Item sales tax group** field, select the item sales tax group to use to calculate the item sales tax for the fee amount.</span></span>
22. <span data-ttu-id="0e88e-140">Sélectionnez l’onglet **Intervalle**.</span><span class="sxs-lookup"><span data-stu-id="0e88e-140">Select the **Interval** tab.</span></span> 

    <span data-ttu-id="0e88e-141">[![Onglet Intervalle](./media/apac-ind-TDS-23.png)](./media/apac-ind-TDS-23.png)</span><span class="sxs-lookup"><span data-stu-id="0e88e-141">[![Interval tab](./media/apac-ind-TDS-23.png)](./media/apac-ind-TDS-23.png)</span></span>

23. <span data-ttu-id="0e88e-142">Dans le champ **Jours**, entrez le nombre de jours qui séparent la date de validation (date d'escompte) du paiement et la date d'échéance du billet à ordre.</span><span class="sxs-lookup"><span data-stu-id="0e88e-142">In the **Days** field, enter the number of days between the posting date (discounting date) of the payment and the due date of the promissory note.</span></span>
24. <span data-ttu-id="0e88e-143">Dans le champ **Pourcentage/Montant**, indiquez si la spécification est un pourcentage ou un montant défini.</span><span class="sxs-lookup"><span data-stu-id="0e88e-143">In the **Percentage/Amount** field, select whether the specification is a percentage or a set amount.</span></span>
25. <span data-ttu-id="0e88e-144">Dans le champ **Montant des frais**, saisissez le montant des frais en pourcentage du paiement ou en montant pour un paiement.</span><span class="sxs-lookup"><span data-stu-id="0e88e-144">In the **Fee amount** field, enter the amount of the fee as either a percentage of the payment or the amount for one payment.</span></span>
26. <span data-ttu-id="0e88e-145">Fermez la page **Configuration des frais de paiement**.</span><span class="sxs-lookup"><span data-stu-id="0e88e-145">Close the **Payment fee setup** page.</span></span>
27. <span data-ttu-id="0e88e-146">Fermez la page **Frais de paiement**.</span><span class="sxs-lookup"><span data-stu-id="0e88e-146">Close the **Payment fee** page.</span></span>
