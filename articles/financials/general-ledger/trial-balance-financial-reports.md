---
title: "États financiers de balance comptable"
description: "Cet article décrit les états par défaut des balances comptables. Il décrit également les blocs élémentaires associés à ces états et comment il est possible de modifier ces états pour les adapter à vos exigences métier."
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 12314
ms.assetid: 3b77d6f3-fd07-41a7-9ddb-1b22d1ae33fc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: c9e8c16724364df4dd62150056299e818470aa63
ms.contentlocale: fr-fr
ms.lasthandoff: 08/07/2018

---

# <a name="trial-balance-financial-reports"></a><span data-ttu-id="fa108-104">États financiers de balance comptable</span><span class="sxs-lookup"><span data-stu-id="fa108-104">Trial balance financial reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fa108-105">Cet article décrit les états par défaut des balances comptables.</span><span class="sxs-lookup"><span data-stu-id="fa108-105">This article describes the default reports for trial balances.</span></span> <span data-ttu-id="fa108-106">Il décrit également les blocs élémentaires associés à ces états et comment il est possible de modifier ces états pour les adapter à vos exigences métier.</span><span class="sxs-lookup"><span data-stu-id="fa108-106">It also describes the building blocks that are associated with these reports and how you can modify the reports to fit your business requirements.</span></span> 

<a name="default-trial-balance-reports"></a><span data-ttu-id="fa108-107">États de la balance comptable par défaut</span><span class="sxs-lookup"><span data-stu-id="fa108-107">Default trial balance reports</span></span>
-----------------------------

<span data-ttu-id="fa108-108">Trois états de balance comptable sont disponibles dans les états financiers dans Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fa108-108">Three trial balance reports are available in Financial reporting in Microsoft Dynamics 365 for Finance and Operations.</span></span>

| <span data-ttu-id="fa108-109">État par défaut</span><span class="sxs-lookup"><span data-stu-id="fa108-109">Default report</span></span>                                 | <span data-ttu-id="fa108-110">Fonction</span><span class="sxs-lookup"><span data-stu-id="fa108-110">What it does</span></span>                                                                                                                                                                                        |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="fa108-111">Balance comptable détaillée – Par défaut</span><span class="sxs-lookup"><span data-stu-id="fa108-111">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="fa108-112">Fournit les informations de solde pour tous les comptes, et comprend les soldes de débit et de crédit, et le net de ces soldes, avec la date de la transaction, le N° document et la description de journal.</span><span class="sxs-lookup"><span data-stu-id="fa108-112">Provides balance information for all accounts, and includes debit and credit balances, and the net of these, together with the transaction date, voucher, and journal description.</span></span>                  |
| <span data-ttu-id="fa108-113">Synthèse de balance comptable– Par défaut</span><span class="sxs-lookup"><span data-stu-id="fa108-113">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="fa108-114">Fournit les informations du solde pour tous les comptes et comprend les soldes d'ouverture et de clôture, et les soldes de débit et de crédit avec leur différence nette.</span><span class="sxs-lookup"><span data-stu-id="fa108-114">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference.</span></span>                                        |
| <span data-ttu-id="fa108-115">Synthèse de balance comptable d'une année à l'autre – Par défaut</span><span class="sxs-lookup"><span data-stu-id="fa108-115">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="fa108-116">Fournit les informations du solde pour tous les comptes, et comprend des soldes d'ouverture et de clôture, et les soldes de débit et de crédit avec leur différence nette pour l'année en cours et l'année passée.</span><span class="sxs-lookup"><span data-stu-id="fa108-116">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference for the current year and the past year.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="fa108-117">Éléments constitutifs</span><span class="sxs-lookup"><span data-stu-id="fa108-117">Building blocks</span></span>
<span data-ttu-id="fa108-118">Les états financiers de balance comptable utilisent les éléments constitutifs suivants.</span><span class="sxs-lookup"><span data-stu-id="fa108-118">The trial balance financial reports use the following building blocks.</span></span>

| <span data-ttu-id="fa108-119">État par défaut</span><span class="sxs-lookup"><span data-stu-id="fa108-119">Default report</span></span>                                 | <span data-ttu-id="fa108-120">Définition de ligne</span><span class="sxs-lookup"><span data-stu-id="fa108-120">Row definition</span></span>          | <span data-ttu-id="fa108-121">Définition de colonne</span><span class="sxs-lookup"><span data-stu-id="fa108-121">Column definition</span></span>                              |
|------------------------------------------------|-------------------------|------------------------------------------------|
| <span data-ttu-id="fa108-122">Balance comptable détaillée – Par défaut</span><span class="sxs-lookup"><span data-stu-id="fa108-122">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="fa108-123">Balance comptable - Par défaut</span><span class="sxs-lookup"><span data-stu-id="fa108-123">Trial Balance - Default</span></span> | <span data-ttu-id="fa108-124">Balance comptable détaillée – Par défaut</span><span class="sxs-lookup"><span data-stu-id="fa108-124">Detailed Trial Balance - Default</span></span>               |
| <span data-ttu-id="fa108-125">Synthèse de balance comptable– Par défaut</span><span class="sxs-lookup"><span data-stu-id="fa108-125">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="fa108-126">Balance comptable - Par défaut</span><span class="sxs-lookup"><span data-stu-id="fa108-126">Trial Balance - Default</span></span> | <span data-ttu-id="fa108-127">Synthèse de balance comptable - Par défaut</span><span class="sxs-lookup"><span data-stu-id="fa108-127">Summary Trial Balance - Default</span></span>                |
| <span data-ttu-id="fa108-128">Synthèse de balance comptable d'une année à l'autre – Par défaut</span><span class="sxs-lookup"><span data-stu-id="fa108-128">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="fa108-129">Balance comptable - Par défaut</span><span class="sxs-lookup"><span data-stu-id="fa108-129">Trial Balance - Default</span></span> | <span data-ttu-id="fa108-130">Synthèse de balance comptable d'une année à l'autre - Par défaut</span><span class="sxs-lookup"><span data-stu-id="fa108-130">Summary Trial Balance Year Over Year - Default</span></span> |

### <a name="row-definition"></a><span data-ttu-id="fa108-131">Définition de ligne</span><span class="sxs-lookup"><span data-stu-id="fa108-131">Row definition</span></span>

<span data-ttu-id="fa108-132">La définition de ligne, balance comptable – Par défaut, contient une seule ligne qui rassemble tous les comptes principaux.</span><span class="sxs-lookup"><span data-stu-id="fa108-132">The row definition, Trial Balance – Default, contains a single row that pulls in all main accounts.</span></span> <span data-ttu-id="fa108-133">Par conséquent, n'importe qui peut générer le rapport sans avoir à apporter de modifications.</span><span class="sxs-lookup"><span data-stu-id="fa108-133">Therefore, anyone can generate the report without having to make any modifications.</span></span> <span data-ttu-id="fa108-134">Lorsque vous affichez l'état, vous explorez la ligne unique pour afficher les détails de chaque compte.</span><span class="sxs-lookup"><span data-stu-id="fa108-134">When you view the report, you drill into the single row to see details about each account.</span></span> <span data-ttu-id="fa108-135">Vous pouvez modifier la définition de ligne afin qu'elle comprenne plus de détails.</span><span class="sxs-lookup"><span data-stu-id="fa108-135">You can modify the row definition so that it includes more detail.</span></span> <span data-ttu-id="fa108-136">Pour modifier la définition de ligne Balance comptable - Par défaut afin qu'elle inclue les lignes pour tous les comptes, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="fa108-136">To modify the Trial Balance – Default row definition so that it includes rows for all accounts, follow these steps.</span></span>

1.  <span data-ttu-id="fa108-137">Cliquez sur **Modifier**, puis sur **Insérer des lignes à partir des dimensions**.</span><span class="sxs-lookup"><span data-stu-id="fa108-137">Click **Edit**, and then click **Insert Rows from Dimensions**.</span></span> <span data-ttu-id="fa108-138">La commande **Insérer des lignes à partir des dimensions** permet de sélectionner les dimensions que vous voulez avoir dans votre définition de ligne.</span><span class="sxs-lookup"><span data-stu-id="fa108-138">The **Insert Rows from Dimensions** command lets you choose the dimensions that you want to have in your row definition.</span></span> <span data-ttu-id="fa108-139">Pour cette définition de ligne, vous allez utiliser **Compte principal**.</span><span class="sxs-lookup"><span data-stu-id="fa108-139">For this row definition, you're going to use **Main Account**.</span></span>
2.  <span data-ttu-id="fa108-140">Vérifiez que **Compte principal** contient toutes les esperluettes (&) et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fa108-140">Make sure that **Main Account** contains all ampersands (&), and then click **OK**.</span></span>

<span data-ttu-id="fa108-141">La définition de ligne contient désormais tous les comptes principaux pour votre entité juridique par défaut.</span><span class="sxs-lookup"><span data-stu-id="fa108-141">The row definition now contains all the main accounts for your default legal entity.</span></span>

### <a name="column-definition"></a><span data-ttu-id="fa108-142">Définition de colonne</span><span class="sxs-lookup"><span data-stu-id="fa108-142">Column definition</span></span>

<span data-ttu-id="fa108-143">Chaque état de balance comptable utilise une définition de colonne différente.</span><span class="sxs-lookup"><span data-stu-id="fa108-143">Each trial balance report uses a different column definition.</span></span> <span data-ttu-id="fa108-144">Ces définitions de colonne contiennent différents types de colonnes afin d'offrir différents niveaux de détails et de données financières.</span><span class="sxs-lookup"><span data-stu-id="fa108-144">These column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="fa108-145">**Balance comptable détaillée – Types de colonne par défaut :**</span><span class="sxs-lookup"><span data-stu-id="fa108-145">**Detailed Trial Balance – Default column types:**</span></span>
    -   <span data-ttu-id="fa108-146">**DESC** : Description de la définition de ligne.</span><span class="sxs-lookup"><span data-stu-id="fa108-146">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="fa108-147">**ACCT** : Codes compte</span><span class="sxs-lookup"><span data-stu-id="fa108-147">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="fa108-148">**ATTR (3)** : Attributs :</span><span class="sxs-lookup"><span data-stu-id="fa108-148">**ATTR (3)** – Attributes:</span></span>
        -   <span data-ttu-id="fa108-149">Date de transaction</span><span class="sxs-lookup"><span data-stu-id="fa108-149">Transaction Date</span></span>
        -   <span data-ttu-id="fa108-150">N° document</span><span class="sxs-lookup"><span data-stu-id="fa108-150">Voucher</span></span>
        -   <span data-ttu-id="fa108-151">Description du journal</span><span class="sxs-lookup"><span data-stu-id="fa108-151">Journal Description</span></span>
    -   <span data-ttu-id="fa108-152">**FD** : Données financières qui contiennent uniquement des débits</span><span class="sxs-lookup"><span data-stu-id="fa108-152">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="fa108-153">**FD** : Données financières qui contiennent uniquement des crédits</span><span class="sxs-lookup"><span data-stu-id="fa108-153">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="fa108-154">**CALC** : Différence nette</span><span class="sxs-lookup"><span data-stu-id="fa108-154">**CALC** – The net difference</span></span>
-   <span data-ttu-id="fa108-155">**Synthèse de balance comptable – Types de colonne par défaut :**</span><span class="sxs-lookup"><span data-stu-id="fa108-155">**Summary Trial Balance – Default columns types:**</span></span>
    -   <span data-ttu-id="fa108-156">**ACCT** : Codes compte</span><span class="sxs-lookup"><span data-stu-id="fa108-156">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="fa108-157">**DESC** : Description de la définition de ligne.</span><span class="sxs-lookup"><span data-stu-id="fa108-157">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="fa108-158">**ATTR** : Attribut :</span><span class="sxs-lookup"><span data-stu-id="fa108-158">**ATTR** – An attribute:</span></span>
        -   <span data-ttu-id="fa108-159">N° document</span><span class="sxs-lookup"><span data-stu-id="fa108-159">Voucher</span></span>
    -   <span data-ttu-id="fa108-160">**FD** : Données financières de solde d'ouverture</span><span class="sxs-lookup"><span data-stu-id="fa108-160">**FD** – The beginning balance financial data</span></span>
    -   <span data-ttu-id="fa108-161">**FD** : Données financières qui contiennent uniquement des débits</span><span class="sxs-lookup"><span data-stu-id="fa108-161">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="fa108-162">**FD** : Données financières qui contiennent uniquement des crédits</span><span class="sxs-lookup"><span data-stu-id="fa108-162">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="fa108-163">**CALC** : Différence nette</span><span class="sxs-lookup"><span data-stu-id="fa108-163">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="fa108-164">**CALC** : Solde de clôture</span><span class="sxs-lookup"><span data-stu-id="fa108-164">**CALC** – The closing balance</span></span>
-   <span data-ttu-id="fa108-165">**Synthèse de balance comptable d'une année à l'autre - Par défaut :**</span><span class="sxs-lookup"><span data-stu-id="fa108-165">**Summary Trial Balance Year Over Year – Default:**</span></span>
    -   <span data-ttu-id="fa108-166">**ACCT** : Codes compte</span><span class="sxs-lookup"><span data-stu-id="fa108-166">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="fa108-167">**DESC** : Description de la définition de ligne.</span><span class="sxs-lookup"><span data-stu-id="fa108-167">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="fa108-168">**ATTR** : Attribut</span><span class="sxs-lookup"><span data-stu-id="fa108-168">**ATTR** – An attribute</span></span>
        -   <span data-ttu-id="fa108-169">N° document</span><span class="sxs-lookup"><span data-stu-id="fa108-169">Voucher</span></span>
    -   <span data-ttu-id="fa108-170">**FD** – Données financières de solde d'ouverture pour l'année actuelle</span><span class="sxs-lookup"><span data-stu-id="fa108-170">**FD** – The beginning balance financial data for the current year</span></span>
    -   <span data-ttu-id="fa108-171">**FD** : Données financières qui contiennent uniquement des débits pour l'année en cours</span><span class="sxs-lookup"><span data-stu-id="fa108-171">**FD** – Financial data that contains only debits for the current year</span></span>
    -   <span data-ttu-id="fa108-172">**FD** : Données financières qui contiennent uniquement des crédits pour l'année en cours</span><span class="sxs-lookup"><span data-stu-id="fa108-172">**FD** – Financial data that contains only credits for the current year</span></span>
    -   <span data-ttu-id="fa108-173">**CALC** : Différence nette</span><span class="sxs-lookup"><span data-stu-id="fa108-173">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="fa108-174">**CALC** : Solde de clôture</span><span class="sxs-lookup"><span data-stu-id="fa108-174">**CALC** – The closing balance</span></span>
    -   <span data-ttu-id="fa108-175">**FD** : Données financières qui contiennent uniquement des débits pour l'année dernière</span><span class="sxs-lookup"><span data-stu-id="fa108-175">**FD** – Financial data that contains only debits for the last year</span></span>
    -   <span data-ttu-id="fa108-176">**FD** : Données financières qui contiennent uniquement des crédits pour l'année dernière</span><span class="sxs-lookup"><span data-stu-id="fa108-176">**FD** – Financial data that contains only credits for the last year</span></span>



<a name="additional-resources"></a><span data-ttu-id="fa108-177">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="fa108-177">Additional resources</span></span>
--------

[<span data-ttu-id="fa108-178">États financiers</span><span class="sxs-lookup"><span data-stu-id="fa108-178">Financial reporting</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="fa108-179">Afficher les états financiers</span><span class="sxs-lookup"><span data-stu-id="fa108-179">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="fa108-180">États financiers Dynamics (blog)</span><span class="sxs-lookup"><span data-stu-id="fa108-180">Dynamics Financial Reporting Blog</span></span>](http://blogs.msdn.com/b/dynamics_financial_reporting/)




