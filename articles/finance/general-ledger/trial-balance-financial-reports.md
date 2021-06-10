---
title: États financiers de balance comptable
description: Cet article décrit les états par défaut des balances comptables. Il décrit également les blocs élémentaires associés à ces états et comment il est possible de modifier ces états pour les adapter à vos exigences métier.
author: jinniew
ms.date: 05/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 12314
ms.assetid: 3b77d6f3-fd07-41a7-9ddb-1b22d1ae33fc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 26ec03422315a280f7e779f992cf694eb5f845ea
ms.sourcegitcommit: 365092f735310990e82516110141d42aaf04e654
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2021
ms.locfileid: "6103656"
---
# <a name="trial-balance-financial-reports"></a><span data-ttu-id="90763-104">États financiers de balance comptable</span><span class="sxs-lookup"><span data-stu-id="90763-104">Trial balance financial reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="90763-105">Cet article décrit les états par défaut des balances comptables.</span><span class="sxs-lookup"><span data-stu-id="90763-105">This article describes the default reports for trial balances.</span></span> <span data-ttu-id="90763-106">Il décrit également les blocs élémentaires associés à ces états et comment il est possible de modifier ces états pour les adapter à vos exigences métier.</span><span class="sxs-lookup"><span data-stu-id="90763-106">It also describes the building blocks that are associated with these reports and how you can modify the reports to fit your business requirements.</span></span> 

## <a name="default-trial-balance-reports"></a><span data-ttu-id="90763-107">États de la balance comptable par défaut</span><span class="sxs-lookup"><span data-stu-id="90763-107">Default trial balance reports</span></span>

<span data-ttu-id="90763-108">Trois états de balance comptable sont disponibles dans les états financiers.</span><span class="sxs-lookup"><span data-stu-id="90763-108">Three trial balance reports are available in Financial reporting.</span></span>

| <span data-ttu-id="90763-109">Rapport par défaut</span><span class="sxs-lookup"><span data-stu-id="90763-109">Default report</span></span>                                 | <span data-ttu-id="90763-110">Fonction</span><span class="sxs-lookup"><span data-stu-id="90763-110">What it does</span></span>                                                                                                                                                                                        |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="90763-111">Balance comptable détaillée – Par défaut</span><span class="sxs-lookup"><span data-stu-id="90763-111">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="90763-112">Fournit les informations de solde pour tous les comptes, et comprend les soldes de débit et de crédit, et le net de ces soldes, avec la date de la transaction, le N° document et la description de journal.</span><span class="sxs-lookup"><span data-stu-id="90763-112">Provides balance information for all accounts, and includes debit and credit balances, and the net of these, together with the transaction date, voucher, and journal description.</span></span>                  |
| <span data-ttu-id="90763-113">Synthèse de balance comptable– Par défaut</span><span class="sxs-lookup"><span data-stu-id="90763-113">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="90763-114">Fournit les informations du solde pour tous les comptes et comprend les soldes d’ouverture et de clôture, et les soldes de débit et de crédit avec leur différence nette.</span><span class="sxs-lookup"><span data-stu-id="90763-114">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference.</span></span>                                        |
| <span data-ttu-id="90763-115">Synthèse de balance comptable d’une année à l’autre – Par défaut</span><span class="sxs-lookup"><span data-stu-id="90763-115">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="90763-116">Fournit les informations du solde pour tous les comptes, et comprend des soldes d’ouverture et de clôture, et les soldes de débit et de crédit avec leur différence nette pour l’année en cours et l’année passée.</span><span class="sxs-lookup"><span data-stu-id="90763-116">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference for the current year and the past year.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="90763-117">Éléments constitutifs</span><span class="sxs-lookup"><span data-stu-id="90763-117">Building blocks</span></span>
<span data-ttu-id="90763-118">Les états financiers de balance comptable utilisent les éléments constitutifs suivants.</span><span class="sxs-lookup"><span data-stu-id="90763-118">The trial balance financial reports use the following building blocks.</span></span>

| <span data-ttu-id="90763-119">État par défaut</span><span class="sxs-lookup"><span data-stu-id="90763-119">Default report</span></span>                                 | <span data-ttu-id="90763-120">Définition de ligne</span><span class="sxs-lookup"><span data-stu-id="90763-120">Row definition</span></span>          | <span data-ttu-id="90763-121">Définition de colonne</span><span class="sxs-lookup"><span data-stu-id="90763-121">Column definition</span></span>                              |
|------------------------------------------------|-------------------------|------------------------------------------------|
| <span data-ttu-id="90763-122">Balance comptable détaillée – Par défaut</span><span class="sxs-lookup"><span data-stu-id="90763-122">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="90763-123">Balance comptable – Par défaut</span><span class="sxs-lookup"><span data-stu-id="90763-123">Trial Balance - Default</span></span> | <span data-ttu-id="90763-124">Balance comptable détaillée – Par défaut</span><span class="sxs-lookup"><span data-stu-id="90763-124">Detailed Trial Balance - Default</span></span>               |
| <span data-ttu-id="90763-125">Synthèse de balance comptable– Par défaut</span><span class="sxs-lookup"><span data-stu-id="90763-125">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="90763-126">Balance comptable – Par défaut</span><span class="sxs-lookup"><span data-stu-id="90763-126">Trial Balance - Default</span></span> | <span data-ttu-id="90763-127">Synthèse de balance comptable – Par défaut</span><span class="sxs-lookup"><span data-stu-id="90763-127">Summary Trial Balance - Default</span></span>                |
| <span data-ttu-id="90763-128">Synthèse de balance comptable d’une année à l’autre – Par défaut</span><span class="sxs-lookup"><span data-stu-id="90763-128">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="90763-129">Balance comptable – Par défaut</span><span class="sxs-lookup"><span data-stu-id="90763-129">Trial Balance - Default</span></span> | <span data-ttu-id="90763-130">Synthèse de balance comptable d’une année à l’autre – Par défaut</span><span class="sxs-lookup"><span data-stu-id="90763-130">Summary Trial Balance Year Over Year - Default</span></span> |

> [!NOTE] 
> <span data-ttu-id="90763-131">Lors de l’exécution du rapport **Balance comptable** dans Financial Reporting, assurez-vous de cocher les cases pour **Afficher les lignes sans montants** et **Afficher les rapports ne contenant pas de lignes actives** dans l’onglet **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="90763-131">When running the **Trial Balance** report in Financial reporting, be sure to select the check boxes for **Display rows with no amounts** and **Display reports with no active rows** on the **Settings** tab.</span></span>

### <a name="row-definition"></a><span data-ttu-id="90763-132">Définition de ligne</span><span class="sxs-lookup"><span data-stu-id="90763-132">Row definition</span></span>

<span data-ttu-id="90763-133">La définition de ligne, balance comptable – Par défaut, contient une seule ligne qui rassemble tous les comptes principaux.</span><span class="sxs-lookup"><span data-stu-id="90763-133">The row definition, Trial Balance – Default, contains a single row that pulls in all main accounts.</span></span> <span data-ttu-id="90763-134">Par conséquent, n’importe qui peut générer le rapport sans avoir à apporter de modifications.</span><span class="sxs-lookup"><span data-stu-id="90763-134">Therefore, anyone can generate the report without having to make any modifications.</span></span> <span data-ttu-id="90763-135">Lorsque vous affichez l’état, vous explorez la ligne unique pour afficher les détails de chaque compte.</span><span class="sxs-lookup"><span data-stu-id="90763-135">When you view the report, you drill into the single row to see details about each account.</span></span> <span data-ttu-id="90763-136">Vous pouvez modifier la définition de ligne afin qu’elle comprenne plus de détails.</span><span class="sxs-lookup"><span data-stu-id="90763-136">You can modify the row definition so that it includes more detail.</span></span> <span data-ttu-id="90763-137">Pour modifier la définition de ligne Balance comptable – Par défaut afin qu’elle inclue les lignes pour tous les comptes, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="90763-137">To modify the Trial Balance – Default row definition so that it includes rows for all accounts, follow these steps.</span></span>

1.  <span data-ttu-id="90763-138">Cliquez sur **Modifier**, puis sur **Insérer des lignes à partir des dimensions**.</span><span class="sxs-lookup"><span data-stu-id="90763-138">Click **Edit**, and then click **Insert Rows from Dimensions**.</span></span> <span data-ttu-id="90763-139">La commande **Insérer des lignes à partir des dimensions** permet de sélectionner les dimensions que vous voulez avoir dans votre définition de ligne.</span><span class="sxs-lookup"><span data-stu-id="90763-139">The **Insert Rows from Dimensions** command lets you choose the dimensions that you want to have in your row definition.</span></span> <span data-ttu-id="90763-140">Pour cette définition de ligne, vous allez utiliser **Compte principal**.</span><span class="sxs-lookup"><span data-stu-id="90763-140">For this row definition, you're going to use **Main Account**.</span></span>
2.  <span data-ttu-id="90763-141">Vérifiez que **Compte principal** contient toutes les esperluettes (&) et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="90763-141">Make sure that **Main Account** contains all ampersands (&), and then click **OK**.</span></span>

<span data-ttu-id="90763-142">La définition de ligne contient désormais tous les comptes principaux pour votre entité juridique par défaut.</span><span class="sxs-lookup"><span data-stu-id="90763-142">The row definition now contains all the main accounts for your default legal entity.</span></span>

### <a name="column-definition"></a><span data-ttu-id="90763-143">Définition de colonne</span><span class="sxs-lookup"><span data-stu-id="90763-143">Column definition</span></span>

<span data-ttu-id="90763-144">Chaque état de balance comptable utilise une définition de colonne différente.</span><span class="sxs-lookup"><span data-stu-id="90763-144">Each trial balance report uses a different column definition.</span></span> <span data-ttu-id="90763-145">Ces définitions de colonne contiennent différents types de colonnes afin d’offrir différents niveaux de détails et de données financières.</span><span class="sxs-lookup"><span data-stu-id="90763-145">These column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="90763-146">**Balance comptable détaillée – Types de colonne par défaut :**</span><span class="sxs-lookup"><span data-stu-id="90763-146">**Detailed Trial Balance – Default column types:**</span></span>
    -   <span data-ttu-id="90763-147">**DESC** : Description de la définition de ligne.</span><span class="sxs-lookup"><span data-stu-id="90763-147">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="90763-148">**ACCT** : Codes compte</span><span class="sxs-lookup"><span data-stu-id="90763-148">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="90763-149">**ATTR (3)** : Attributs :</span><span class="sxs-lookup"><span data-stu-id="90763-149">**ATTR (3)** – Attributes:</span></span>
        -   <span data-ttu-id="90763-150">Date de transaction</span><span class="sxs-lookup"><span data-stu-id="90763-150">Transaction Date</span></span>
        -   <span data-ttu-id="90763-151">N° document</span><span class="sxs-lookup"><span data-stu-id="90763-151">Voucher</span></span>
        -   <span data-ttu-id="90763-152">Description du journal</span><span class="sxs-lookup"><span data-stu-id="90763-152">Journal Description</span></span>
    -   <span data-ttu-id="90763-153">**FD** : Données financières qui contiennent uniquement des débits</span><span class="sxs-lookup"><span data-stu-id="90763-153">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="90763-154">**FD** : Données financières qui contiennent uniquement des crédits</span><span class="sxs-lookup"><span data-stu-id="90763-154">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="90763-155">**CALC** : Différence nette</span><span class="sxs-lookup"><span data-stu-id="90763-155">**CALC** – The net difference</span></span>
-   <span data-ttu-id="90763-156">**Synthèse de balance comptable – Types de colonne par défaut :**</span><span class="sxs-lookup"><span data-stu-id="90763-156">**Summary Trial Balance – Default columns types:**</span></span>
    -   <span data-ttu-id="90763-157">**ACCT** : Codes compte</span><span class="sxs-lookup"><span data-stu-id="90763-157">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="90763-158">**DESC** : Description de la définition de ligne.</span><span class="sxs-lookup"><span data-stu-id="90763-158">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="90763-159">**ATTR** : Attribut :</span><span class="sxs-lookup"><span data-stu-id="90763-159">**ATTR** – An attribute:</span></span>
        -   <span data-ttu-id="90763-160">N° document</span><span class="sxs-lookup"><span data-stu-id="90763-160">Voucher</span></span>
    -   <span data-ttu-id="90763-161">**FD** : Données financières de solde d’ouverture</span><span class="sxs-lookup"><span data-stu-id="90763-161">**FD** – The beginning balance financial data</span></span>
    -   <span data-ttu-id="90763-162">**FD** : Données financières qui contiennent uniquement des débits</span><span class="sxs-lookup"><span data-stu-id="90763-162">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="90763-163">**FD** : Données financières qui contiennent uniquement des crédits</span><span class="sxs-lookup"><span data-stu-id="90763-163">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="90763-164">**CALC** : Différence nette</span><span class="sxs-lookup"><span data-stu-id="90763-164">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="90763-165">**CALC** : Solde de clôture</span><span class="sxs-lookup"><span data-stu-id="90763-165">**CALC** – The closing balance</span></span>
-   <span data-ttu-id="90763-166">**Synthèse de balance comptable d’une année à l’autre – Par défaut :**</span><span class="sxs-lookup"><span data-stu-id="90763-166">**Summary Trial Balance Year Over Year – Default:**</span></span>
    -   <span data-ttu-id="90763-167">**ACCT** : Codes compte</span><span class="sxs-lookup"><span data-stu-id="90763-167">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="90763-168">**DESC** : Description de la définition de ligne.</span><span class="sxs-lookup"><span data-stu-id="90763-168">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="90763-169">**ATTR** : Attribut</span><span class="sxs-lookup"><span data-stu-id="90763-169">**ATTR** – An attribute</span></span>
        -   <span data-ttu-id="90763-170">N° document</span><span class="sxs-lookup"><span data-stu-id="90763-170">Voucher</span></span>
    -   <span data-ttu-id="90763-171">**FD** – Données financières de solde d’ouverture pour l’année actuelle</span><span class="sxs-lookup"><span data-stu-id="90763-171">**FD** – The beginning balance financial data for the current year</span></span>
    -   <span data-ttu-id="90763-172">**FD** : Données financières qui contiennent uniquement des débits pour l’année en cours</span><span class="sxs-lookup"><span data-stu-id="90763-172">**FD** – Financial data that contains only debits for the current year</span></span>
    -   <span data-ttu-id="90763-173">**FD** : Données financières qui contiennent uniquement des crédits pour l’année en cours</span><span class="sxs-lookup"><span data-stu-id="90763-173">**FD** – Financial data that contains only credits for the current year</span></span>
    -   <span data-ttu-id="90763-174">**CALC** : Différence nette</span><span class="sxs-lookup"><span data-stu-id="90763-174">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="90763-175">**CALC** : Solde de clôture</span><span class="sxs-lookup"><span data-stu-id="90763-175">**CALC** – The closing balance</span></span>
    -   <span data-ttu-id="90763-176">**FD** : Données financières qui contiennent uniquement des débits pour l’année dernière</span><span class="sxs-lookup"><span data-stu-id="90763-176">**FD** – Financial data that contains only debits for the last year</span></span>
    -   <span data-ttu-id="90763-177">**FD** : Données financières qui contiennent uniquement des crédits pour l’année dernière</span><span class="sxs-lookup"><span data-stu-id="90763-177">**FD** – Financial data that contains only credits for the last year</span></span>

## <a name="additional-resources"></a><span data-ttu-id="90763-178">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="90763-178">Additional resources</span></span>

[<span data-ttu-id="90763-179">Vue d’ensemble des états financiers</span><span class="sxs-lookup"><span data-stu-id="90763-179">Financial reporting overview</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="90763-180">Afficher les états financiers</span><span class="sxs-lookup"><span data-stu-id="90763-180">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="90763-181">États financiers Dynamics (blog)</span><span class="sxs-lookup"><span data-stu-id="90763-181">Dynamics Financial Reporting Blog</span></span>](https://blogs.msdn.com/b/dynamics_financial_reporting/)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
