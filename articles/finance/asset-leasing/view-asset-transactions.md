---
title: Afficher les transactions de passif, d’actifs et de dépenses
description: Cette rubrique explique comment afficher les transactions pour un actif loué. Ces transactions comprennent les transactions de passif locatif et les transactions de frais exécutoires qui ont été comptabilisées.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 17753087adb835b4632e929451e2cf3e2d772ed4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249531"
---
# <a name="view-liability-asset-and-expense-transactions"></a><span data-ttu-id="92f69-104">Afficher les transactions de passif, d’actifs et de dépenses</span><span class="sxs-lookup"><span data-stu-id="92f69-104">View liability, asset, and expense transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="92f69-105">Cette rubrique explique comment afficher les transactions pour un actif loué.</span><span class="sxs-lookup"><span data-stu-id="92f69-105">This topic explains how to view transactions for a leased asset.</span></span> <span data-ttu-id="92f69-106">Ces transactions comprennent les transactions de passif locatif et les transactions de frais exécutoires qui ont été comptabilisées.</span><span class="sxs-lookup"><span data-stu-id="92f69-106">These transactions include lease liability transactions and executory expense transactions that have been posted.</span></span> <span data-ttu-id="92f69-107">Les valeurs comptables du passif et droit d’utilisation de l’actif sont utilisées dans plusieurs rapports.</span><span class="sxs-lookup"><span data-stu-id="92f69-107">The carrying values of the liability and right-of-use (ROU) asset are used on several reports.</span></span> <span data-ttu-id="92f69-108">Ils sont également utilisés pour calculer les valeurs d’ajustement.</span><span class="sxs-lookup"><span data-stu-id="92f69-108">They are also used to calculate adjustment values.</span></span>

## <a name="liability-transactions"></a><span data-ttu-id="92f69-109">Opérations de passif</span><span class="sxs-lookup"><span data-stu-id="92f69-109">Liability transactions</span></span>

<span data-ttu-id="92f69-110">Pour afficher les transactions de passif de location, sélectionnez un contrat de location dans la page **Résumé du bail**, puis sélectionnez **Registres** pour ouvrir les registres joints à l’enregistrement de bail.</span><span class="sxs-lookup"><span data-stu-id="92f69-110">To view the lease liability transactions, select a lease on the **Lease summary** page, and then select **Books** to open the books that are attached to the lease record.</span></span> <span data-ttu-id="92f69-111">Après une reconnaissance initiale, une facture ou un journal des intérêts a été validée, sélectionnez **transactions de passif**.</span><span class="sxs-lookup"><span data-stu-id="92f69-111">After an initial recognition, an invoice, or an interest journal has been posted, select **Liability transactions**.</span></span>

<span data-ttu-id="92f69-112">La page **transactions de passif** montre les transactions qui augmentent ou diminuent le passif locatif.</span><span class="sxs-lookup"><span data-stu-id="92f69-112">The **Liability transactions** page shows the transactions that either increase or decrease the lease liability.</span></span> <span data-ttu-id="92f69-113">Les montants négatifs sur cette page représentent les transactions de crédit dans l’application standard.</span><span class="sxs-lookup"><span data-stu-id="92f69-113">Negative amounts on this page represent credit transactions in the standard application.</span></span> <span data-ttu-id="92f69-114">Tous les intérêts courus sont présentés comme des valeurs négatives et augmentent le total du passif locatif.</span><span class="sxs-lookup"><span data-stu-id="92f69-114">Any interest accruals are shown as negative values and increase the total lease liability.</span></span> <span data-ttu-id="92f69-115">Les éventuels ajustements de location sont présentés sous forme de valeurs positives ou négatives, selon la nature et l’impact du registre de location.</span><span class="sxs-lookup"><span data-stu-id="92f69-115">Any lease adjustments are shown as positive or negative values, depending on the nature and impact of the lease book.</span></span> <span data-ttu-id="92f69-116">Le solde total net actuel du passif locatif pour le bail sélectionné est affiché en bas à gauche de la page.</span><span class="sxs-lookup"><span data-stu-id="92f69-116">The current net total balance of the lease liability for the selected lease is shown at the bottom left of the page.</span></span>

## <a name="asset-transactions"></a><span data-ttu-id="92f69-117">Transactions d’actifs</span><span class="sxs-lookup"><span data-stu-id="92f69-117">Asset transactions</span></span>

<span data-ttu-id="92f69-118">Pour afficher les transactions d’actif de location, sélectionnez un contrat de location dans la page **Résumé du bail**, puis sélectionnez **Registres** pour ouvrir les registres de locations joints à l’enregistrement de bail.</span><span class="sxs-lookup"><span data-stu-id="92f69-118">To view the lease asset transactions, select a lease on the **Lease summary** page, and then select **Books** to open the lease books that are attached to the lease record.</span></span> <span data-ttu-id="92f69-119">Sélectionnez ensuite **Transactions d’actifs**.</span><span class="sxs-lookup"><span data-stu-id="92f69-119">Then select **Asset transactions**.</span></span>

<span data-ttu-id="92f69-120">La page **Transaction d’actifs** affiche les transactions qui augmentent ou diminuent l’actif de location et les comptes d’amortissement cumulé.</span><span class="sxs-lookup"><span data-stu-id="92f69-120">The **Asset transaction** page shows the transactions that either increase or decrease the lease asset and accumulated depreciation accounts.</span></span> <span data-ttu-id="92f69-121">Les débits sont affichés sous forme de valeurs positives et les crédits sont affichés sous forme de valeurs négatives, comme sur la page **Transactions de passif**.</span><span class="sxs-lookup"><span data-stu-id="92f69-121">Debits are shown as positive values, and credits are shown as negative values, as on the **Liability transactions** page.</span></span> <span data-ttu-id="92f69-122">La reconnaissance initiale enregistrée et la suivante de l’amortissement cumulé sont affichées en bas à gauche de la page en tant que solde de l’actif.</span><span class="sxs-lookup"><span data-stu-id="92f69-122">The posted initial recognition and the next of accumulated depreciation are shown at the bottom left of the page as the asset balance.</span></span> 

## <a name="expenses-transactions"></a><span data-ttu-id="92f69-123">Transactions de dépenses</span><span class="sxs-lookup"><span data-stu-id="92f69-123">Expenses transactions</span></span>

<span data-ttu-id="92f69-124">Pour afficher les transactions de dépenses de location, sélectionnez un contrat de location dans la page **Résumé du bail**, puis sélectionnez **Registres** pour ouvrir les registres de locations joints à l’enregistrement de bail.</span><span class="sxs-lookup"><span data-stu-id="92f69-124">To view the lease expense transactions, select a lease on the **Lease summary** page, and then select **Books** to open the lease books that are attached to the lease record.</span></span> <span data-ttu-id="92f69-125">Sélectionnez ensuite **Transactions de dépenses**.</span><span class="sxs-lookup"><span data-stu-id="92f69-125">Then select **Expense transactions**.</span></span>

<span data-ttu-id="92f69-126">La page **Transactions de dépenses** affiche toutes les dépenses qui ont été imputées au contrat de location, telles que les frais d’intérêt, les frais d’amortissement et les frais exécutoires.</span><span class="sxs-lookup"><span data-stu-id="92f69-126">The **Expense transactions** page shows all the expenses that have been posted against the lease, such as interest expenses, depreciation expenses, and any executory costs.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]