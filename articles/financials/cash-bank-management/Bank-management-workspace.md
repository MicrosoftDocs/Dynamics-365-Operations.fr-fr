---
title: Espace de travail de la gestion des banques
description: "Cette rubrique fournit des informations sur l'espace de travail Gestion des banques. Cet espace de travail affiche les informations concernant les comptes bancaires de la société, et inclut une vue de synthèse et une page Analyses. La vue Synthèse affiche des vignettes de synthèse, des informations sur les comptes bancaires, un graphique du solde et des informations associées. La page Analyses utilise les fonctionnalités de Microsoft Power BI pour afficher les éléments visuels associés aux soldes de comptes bancaires."
author: saraschi2
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankTreasurerWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: 421dc85a3f8ccd490993412c12f8766f46d3242a
ms.contentlocale: fr-fr
ms.lasthandoff: 01/17/2018

---
# <a name="bank-management-workspace"></a><span data-ttu-id="c1c17-106">Espace de travail de la gestion des banques</span><span class="sxs-lookup"><span data-stu-id="c1c17-106">Bank management workspace</span></span>

<span data-ttu-id="c1c17-107">L'espace de travail **Gestion des banques** affichent des informations concernant les comptes bancaires de la société.</span><span class="sxs-lookup"><span data-stu-id="c1c17-107">The **Bank management** workspace shows information that is related to company bank accounts.</span></span> <span data-ttu-id="c1c17-108">Cet espace de travail contient une vue **Synthèse** et une page **Analyses**.</span><span class="sxs-lookup"><span data-stu-id="c1c17-108">This workspace includes a **Summary** view and an **Analytics** page.</span></span> <span data-ttu-id="c1c17-109">La vue **Synthèse** affiche des vignettes de synthèse, des informations sur les comptes bancaires, un graphique du solde et des informations associées.</span><span class="sxs-lookup"><span data-stu-id="c1c17-109">The **Summary** view shows summary tiles, bank account information, a balance chart, and related information.</span></span> <span data-ttu-id="c1c17-110">La page **Analyses** utilise les fonctionnalités de Microsoft Power BI pour afficher les éléments visuels associés aux soldes de comptes bancaires.</span><span class="sxs-lookup"><span data-stu-id="c1c17-110">The **Analytics** page uses the capabilities of Microsoft Power BI to show visuals that are related to bank account balances.</span></span>

## <a name="summary-view"></a><span data-ttu-id="c1c17-111">Vue Synthèse</span><span class="sxs-lookup"><span data-stu-id="c1c17-111">Summary view</span></span>

### <a name="summary"></a><span data-ttu-id="c1c17-112">Synthèse</span><span class="sxs-lookup"><span data-stu-id="c1c17-112">Summary</span></span>

<span data-ttu-id="c1c17-113">Les vignettes dans la section **Synthèse** fournissent une vue d'ensemble de vos comptes bancaires et fournissent un accès rapide aux pages que vous devez utiliser le plus souvent.</span><span class="sxs-lookup"><span data-stu-id="c1c17-113">The tiles in the **Summary** section give an overview of your bank accounts and provide quick access to the pages that you most often have to use.</span></span> <span data-ttu-id="c1c17-114">Les informations de rapprochement bancaire sont spécifiques à la fonction de rapprochement bancaire avancée.</span><span class="sxs-lookup"><span data-stu-id="c1c17-114">The bank reconciliation information is specific to the Advanced bank reconciliation functionality.</span></span> <span data-ttu-id="c1c17-115">Les informations ne concernent que les comptes bancaires dont l'option **Rapprochement bancaire avancé** est définie sur **Oui** sur la page **Compte bancaire**.</span><span class="sxs-lookup"><span data-stu-id="c1c17-115">Information is included only for those bank accounts that have the **Advanced bank reconciliation** option set to **Yes** on the **Bank account** page.</span></span> <span data-ttu-id="c1c17-116">Dans la section **Synthèse**, vous pouvez importer les fichiers bancaires électroniques des comptes bancaires de toutes les entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="c1c17-116">From the **Summary** section, you can import electronic bank files for bank accounts across all legal entities.</span></span>

### <a name="bank-accounts"></a><span data-ttu-id="c1c17-117">Comptes bancaires</span><span class="sxs-lookup"><span data-stu-id="c1c17-117">Bank accounts</span></span>

<span data-ttu-id="c1c17-118">Chaque compte bancaire de l'entité juridique est représenté par une carte dans la section **Comptes bancaires**.</span><span class="sxs-lookup"><span data-stu-id="c1c17-118">Each bank account in the legal entity is represented by a card in the **Bank accounts** section.</span></span> <span data-ttu-id="c1c17-119">Le solde actuel est affiché, et vous pouvez accéder aux transactions composant ce montant du solde de synthèse.</span><span class="sxs-lookup"><span data-stu-id="c1c17-119">The current balance is shown, and you can drill down to the transactions that make up that summary balance amount.</span></span> <span data-ttu-id="c1c17-120">Le montant **Transactions d'attente** permet également d'accéder aux transactions composant ce montant de synthèse.</span><span class="sxs-lookup"><span data-stu-id="c1c17-120">The **Bridged transactions** amount also lets you drill down to the transactions that make up that summary amount.</span></span> <span data-ttu-id="c1c17-121">Les transactions d'attente sont toutes les transactions en attente qui ont été validées à l'aide de la fonctionnalité Transition, mais qui n'ont pas encore été effacées.</span><span class="sxs-lookup"><span data-stu-id="c1c17-121">Bridged transactions are any pending transactions that have been posted by using bridging functionality, but that haven't yet been cleared.</span></span> <span data-ttu-id="c1c17-122">Le montant **Solde en suspens** est le solde actuel moins les transactions en transition ou en attente.</span><span class="sxs-lookup"><span data-stu-id="c1c17-122">The **Pending balance** amount is the current balance minus the bridged, or pending, transactions.</span></span>

<span data-ttu-id="c1c17-123">La carte indique également le moment où le compte bancaire a fait l'objet d'un rapprochement pour la dernière fois.</span><span class="sxs-lookup"><span data-stu-id="c1c17-123">The card also shows when the bank account was last reconciled.</span></span> <span data-ttu-id="c1c17-124">Ces informations ne sont affichées que si le rapprochement bancaire avancé est activé pour le compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="c1c17-124">This information is shown only if Advanced bank reconciliation is enabled for the bank account.</span></span>

### <a name="balance"></a><span data-ttu-id="c1c17-125">Bilan</span><span class="sxs-lookup"><span data-stu-id="c1c17-125">Balance</span></span>

<span data-ttu-id="c1c17-126">Le graphique **Solde** affiche, soit les informations sur l'historique du solde du compte bancaire sélectionné dans la section **Comptes bancaires**, soit une synthèse de l'historique du solde de tous les comptes bancaires de l'entité juridique.</span><span class="sxs-lookup"><span data-stu-id="c1c17-126">The **Balance** chart shows either historic balance information for the bank account that is selected in the **Bank accounts** section or a summary of historic balance information for all bank accounts in the legal entity.</span></span> <span data-ttu-id="c1c17-127">Ces informations sont disponibles pour des périodes différentes : la semaine en cours, le mois en cours, l'année en cours, les cinq dernières années, et toutes les périodes (historique complet du compte bancaire).</span><span class="sxs-lookup"><span data-stu-id="c1c17-127">This information is available for various periods: the current week, the current month, the current year, the last five years, and all periods (the full history of the bank account).</span></span> 

<span data-ttu-id="c1c17-128">Si vous consultez le graphique **Solde** d'un seul compte bancaire, l'historique des soldes est affiché dans la devise du compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="c1c17-128">If you're viewing the **Balance** chart for a single bank account, the historic balances are shown in the bank account currency.</span></span> <span data-ttu-id="c1c17-129">Si vous consultez le graphique de tous les comptes de l'entité juridique, l'historique des soldes est affiché dans la devise comptable.</span><span class="sxs-lookup"><span data-stu-id="c1c17-129">If you're viewing the chart for all bank accounts in the legal entity, the historic balances are shown in the accounting currency.</span></span>

<span data-ttu-id="c1c17-130">Les informations relatives au moment où les données ont été mises à jour pour la dernière fois s'affichent en haut du graphique.</span><span class="sxs-lookup"><span data-stu-id="c1c17-130">Information about when the data was last updated appears at the top of the chart.</span></span> <span data-ttu-id="c1c17-131">Vous pouvez mettre à jour les données comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="c1c17-131">You can update the data as you require.</span></span>

### <a name="related-information"></a><span data-ttu-id="c1c17-132">Informations associées</span><span class="sxs-lookup"><span data-stu-id="c1c17-132">Related information</span></span>

<span data-ttu-id="c1c17-133">Dans la section **Informations associées**, vous pouvez ouvrir la page **Journal des opérations diverses** pour effectuer des transferts bancaires.</span><span class="sxs-lookup"><span data-stu-id="c1c17-133">From the **Related information** section, you can open the **General journal** page to complete bank transfers.</span></span> <span data-ttu-id="c1c17-134">Vous pouvez également ouvrir rapidement les pages **Transactions bancaires** et **Transactions d'attente**.</span><span class="sxs-lookup"><span data-stu-id="c1c17-134">You can also quickly open the **Bank transactions** and **Bridged transactions** pages.</span></span>

## <a name="analytics-view"></a><span data-ttu-id="c1c17-135">Vue Analyses</span><span class="sxs-lookup"><span data-stu-id="c1c17-135">Analytics view</span></span>

<span data-ttu-id="c1c17-136">La page **Analyses** fournit des mesures importantes sur les comptes bancaires de la société actuelle.</span><span class="sxs-lookup"><span data-stu-id="c1c17-136">The **Analytics** page provides important metrics about the bank accounts in the current company.</span></span> <span data-ttu-id="c1c17-137">Les visualisation suivantes sont disponibles dans la page :</span><span class="sxs-lookup"><span data-stu-id="c1c17-137">The following visualizations are available on the page:</span></span>

-   <span data-ttu-id="c1c17-138">Solde bancaire total dans la devise du système</span><span class="sxs-lookup"><span data-stu-id="c1c17-138">Total bank balance in system currency</span></span>
-   <span data-ttu-id="c1c17-139">Solde par entité juridique</span><span class="sxs-lookup"><span data-stu-id="c1c17-139">Balance by legal entity</span></span>
-   <span data-ttu-id="c1c17-140">Le solde actuel par rapport au solde prévisionnel dans la devise du compte bancaire</span><span class="sxs-lookup"><span data-stu-id="c1c17-140">Today’s actual vs forecasted balance in bank account currency</span></span>
-   <span data-ttu-id="c1c17-141">Solde par compte bancaire</span><span class="sxs-lookup"><span data-stu-id="c1c17-141">Balance by bank account</span></span>
-   <span data-ttu-id="c1c17-142">Solde par devise</span><span class="sxs-lookup"><span data-stu-id="c1c17-142">Balance by currency</span></span>

<span data-ttu-id="c1c17-143">Vous pouvez afficher les analyses bancaires de toutes les sociétés à partir de l'espace de travail **Aperçu de la trésorerie - toutes les sociétés**.</span><span class="sxs-lookup"><span data-stu-id="c1c17-143">You can view bank analytics across all companies from the **Cash overview – all companies** workspace.</span></span>

