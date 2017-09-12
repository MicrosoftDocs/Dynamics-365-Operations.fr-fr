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
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 12314
ms.assetid: 3b77d6f3-fd07-41a7-9ddb-1b22d1ae33fc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 6405599186c8d07ac5ade19d3b7d27ae83b036ff
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---

# <a name="trial-balance-financial-reports"></a><span data-ttu-id="13499-104">États financiers de balance comptable</span><span class="sxs-lookup"><span data-stu-id="13499-104">Trial balance financial reports</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="13499-105">Cet article décrit les états par défaut des balances comptables.</span><span class="sxs-lookup"><span data-stu-id="13499-105">This article describes the default reports for trial balances.</span></span> <span data-ttu-id="13499-106">Il décrit également les blocs élémentaires associés à ces états et comment il est possible de modifier ces états pour les adapter à vos exigences métier.</span><span class="sxs-lookup"><span data-stu-id="13499-106">It also describes the building blocks that are associated with these reports and how you can modify the reports to fit your business requirements.</span></span> 

<a name="default-trial-balance-reports"></a><span data-ttu-id="13499-107">États de la balance comptable par défaut</span><span class="sxs-lookup"><span data-stu-id="13499-107">Default trial balance reports</span></span>
-----------------------------

<span data-ttu-id="13499-108">Trois états de balance comptable sont disponibles dans les états financiers dans Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="13499-108">Three trial balance reports are available in Financial reporting in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span>

| <span data-ttu-id="13499-109">État par défaut</span><span class="sxs-lookup"><span data-stu-id="13499-109">Default report</span></span>                                 | <span data-ttu-id="13499-110">Fonction</span><span class="sxs-lookup"><span data-stu-id="13499-110">What it does</span></span>                                                                                                                                                                                        |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="13499-111">Balance comptable détaillée – Par défaut</span><span class="sxs-lookup"><span data-stu-id="13499-111">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="13499-112">Fournit les informations de solde pour tous les comptes, et comprend les soldes de débit et de crédit, et le net de ces soldes, avec la date de la transaction, le N° document et la description de journal.</span><span class="sxs-lookup"><span data-stu-id="13499-112">Provides balance information for all accounts, and includes debit and credit balances, and the net of these, together with the transaction date, voucher, and journal description.</span></span>                  |
| <span data-ttu-id="13499-113">Synthèse de balance comptable– Par défaut</span><span class="sxs-lookup"><span data-stu-id="13499-113">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="13499-114">Fournit les informations du solde pour tous les comptes et comprend les soldes d'ouverture et de clôture, et les soldes de débit et de crédit avec leur différence nette.</span><span class="sxs-lookup"><span data-stu-id="13499-114">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference.</span></span>                                        |
| <span data-ttu-id="13499-115">Synthèse de balance comptable d'une année à l'autre – Par défaut</span><span class="sxs-lookup"><span data-stu-id="13499-115">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="13499-116">Fournit les informations du solde pour tous les comptes, et comprend des soldes d'ouverture et de clôture, et les soldes de débit et de crédit avec leur différence nette pour l'année en cours et l'année passée.</span><span class="sxs-lookup"><span data-stu-id="13499-116">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference for the current year and the past year.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="13499-117">Éléments constitutifs</span><span class="sxs-lookup"><span data-stu-id="13499-117">Building blocks</span></span>
<span data-ttu-id="13499-118">Les états financiers de balance comptable utilisent les éléments constitutifs suivants.</span><span class="sxs-lookup"><span data-stu-id="13499-118">The trial balance financial reports use the following building blocks.</span></span>

| <span data-ttu-id="13499-119">État par défaut</span><span class="sxs-lookup"><span data-stu-id="13499-119">Default report</span></span>                                 | <span data-ttu-id="13499-120">Définition de ligne</span><span class="sxs-lookup"><span data-stu-id="13499-120">Row definition</span></span>          | <span data-ttu-id="13499-121">Définition de colonne</span><span class="sxs-lookup"><span data-stu-id="13499-121">Column definition</span></span>                              |
|------------------------------------------------|-------------------------|------------------------------------------------|
| <span data-ttu-id="13499-122">Balance comptable détaillée – Par défaut</span><span class="sxs-lookup"><span data-stu-id="13499-122">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="13499-123">Balance comptable - Par défaut</span><span class="sxs-lookup"><span data-stu-id="13499-123">Trial Balance - Default</span></span> | <span data-ttu-id="13499-124">Balance comptable détaillée – Par défaut</span><span class="sxs-lookup"><span data-stu-id="13499-124">Detailed Trial Balance - Default</span></span>               |
| <span data-ttu-id="13499-125">Synthèse de balance comptable– Par défaut</span><span class="sxs-lookup"><span data-stu-id="13499-125">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="13499-126">Balance comptable - Par défaut</span><span class="sxs-lookup"><span data-stu-id="13499-126">Trial Balance - Default</span></span> | <span data-ttu-id="13499-127">Synthèse de balance comptable - Par défaut</span><span class="sxs-lookup"><span data-stu-id="13499-127">Summary Trial Balance - Default</span></span>                |
| <span data-ttu-id="13499-128">Synthèse de balance comptable d'une année à l'autre – Par défaut</span><span class="sxs-lookup"><span data-stu-id="13499-128">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="13499-129">Balance comptable - Par défaut</span><span class="sxs-lookup"><span data-stu-id="13499-129">Trial Balance - Default</span></span> | <span data-ttu-id="13499-130">Synthèse de balance comptable d'une année à l'autre - Par défaut</span><span class="sxs-lookup"><span data-stu-id="13499-130">Summary Trial Balance Year Over Year - Default</span></span> |

### <a name="row-definition"></a><span data-ttu-id="13499-131">Définition de ligne</span><span class="sxs-lookup"><span data-stu-id="13499-131">Row definition</span></span>

<span data-ttu-id="13499-132">La définition de ligne, balance comptable – Par défaut, contient une seule ligne qui rassemble tous les comptes principaux.</span><span class="sxs-lookup"><span data-stu-id="13499-132">The row definition, Trial Balance – Default, contains a single row that pulls in all main accounts.</span></span> <span data-ttu-id="13499-133">Par conséquent, n'importe qui peut générer le rapport sans avoir à apporter de modifications.</span><span class="sxs-lookup"><span data-stu-id="13499-133">Therefore, anyone can generate the report without having to make any modifications.</span></span> <span data-ttu-id="13499-134">Lorsque vous affichez l'état, vous explorez la ligne unique pour afficher les détails de chaque compte.</span><span class="sxs-lookup"><span data-stu-id="13499-134">When you view the report, you drill into the single row to see details about each account.</span></span> <span data-ttu-id="13499-135">Vous pouvez modifier la définition de ligne afin qu'elle comprenne plus de détails.</span><span class="sxs-lookup"><span data-stu-id="13499-135">You can modify the row definition so that it includes more detail.</span></span> <span data-ttu-id="13499-136">Pour modifier la définition de ligne Balance comptable - Par défaut afin qu'elle inclue les lignes pour tous les comptes, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="13499-136">To modify the Trial Balance – Default row definition so that it includes rows for all accounts, follow these steps.</span></span>

1.  <span data-ttu-id="13499-137">Cliquez sur **Modifier**, puis sur **Insérer des lignes à partir des dimensions**.</span><span class="sxs-lookup"><span data-stu-id="13499-137">Click **Edit**, and then click **Insert Rows from Dimensions**.</span></span> <span data-ttu-id="13499-138">La commande **Insérer des lignes à partir des dimensions** permet de sélectionner les dimensions que vous voulez avoir dans votre définition de ligne.</span><span class="sxs-lookup"><span data-stu-id="13499-138">The **Insert Rows from Dimensions** command lets you choose the dimensions that you want to have in your row definition.</span></span> <span data-ttu-id="13499-139">Pour cette définition de ligne, vous allez utiliser **Compte principal**.</span><span class="sxs-lookup"><span data-stu-id="13499-139">For this row definition, you're going to use **Main Account**.</span></span>
2.  <span data-ttu-id="13499-140">Vérifiez que **Compte principal** contient toutes les esperluettes (&) et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="13499-140">Make sure that **Main Account** contains all ampersands (&), and then click **OK**.</span></span>

<span data-ttu-id="13499-141">La définition de ligne contient désormais tous les comptes principaux pour votre entité juridique par défaut.</span><span class="sxs-lookup"><span data-stu-id="13499-141">The row definition now contains all the main accounts for your default legal entity.</span></span>

### <a name="column-definition"></a><span data-ttu-id="13499-142">Définition de colonne</span><span class="sxs-lookup"><span data-stu-id="13499-142">Column definition</span></span>

<span data-ttu-id="13499-143">Chaque état de balance comptable utilise une définition de colonne différente.</span><span class="sxs-lookup"><span data-stu-id="13499-143">Each trial balance report uses a different column definition.</span></span> <span data-ttu-id="13499-144">Ces définitions de colonne contiennent différents types de colonnes afin d'offrir différents niveaux de détails et de données financières.</span><span class="sxs-lookup"><span data-stu-id="13499-144">These column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="13499-145">**Balance comptable détaillée – Types de colonne par défaut :**</span><span class="sxs-lookup"><span data-stu-id="13499-145">**Detailed Trial Balance – Default column types:**</span></span>
    -   <span data-ttu-id="13499-146">**DESC** : Description de la définition de ligne.</span><span class="sxs-lookup"><span data-stu-id="13499-146">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="13499-147">**ACCT** : Codes compte</span><span class="sxs-lookup"><span data-stu-id="13499-147">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="13499-148">**ATTR (3)** : Attributs :</span><span class="sxs-lookup"><span data-stu-id="13499-148">**ATTR (3)** – Attributes:</span></span>
        -   <span data-ttu-id="13499-149">Date de transaction</span><span class="sxs-lookup"><span data-stu-id="13499-149">Transaction Date</span></span>
        -   <span data-ttu-id="13499-150">N° document</span><span class="sxs-lookup"><span data-stu-id="13499-150">Voucher</span></span>
        -   <span data-ttu-id="13499-151">Description du journal</span><span class="sxs-lookup"><span data-stu-id="13499-151">Journal Description</span></span>
    -   <span data-ttu-id="13499-152">**FD** : Données financières qui contiennent uniquement des débits</span><span class="sxs-lookup"><span data-stu-id="13499-152">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="13499-153">**FD** : Données financières qui contiennent uniquement des crédits</span><span class="sxs-lookup"><span data-stu-id="13499-153">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="13499-154">**CALC** : Différence nette</span><span class="sxs-lookup"><span data-stu-id="13499-154">**CALC** – The net difference</span></span>
-   <span data-ttu-id="13499-155">**Synthèse de balance comptable – Types de colonne par défaut :**</span><span class="sxs-lookup"><span data-stu-id="13499-155">**Summary Trial Balance – Default columns types:**</span></span>
    -   <span data-ttu-id="13499-156">**ACCT** : Codes compte</span><span class="sxs-lookup"><span data-stu-id="13499-156">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="13499-157">**DESC** : Description de la définition de ligne.</span><span class="sxs-lookup"><span data-stu-id="13499-157">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="13499-158">**ATTR** : Attribut :</span><span class="sxs-lookup"><span data-stu-id="13499-158">**ATTR** – An attribute:</span></span>
        -   <span data-ttu-id="13499-159">N° document</span><span class="sxs-lookup"><span data-stu-id="13499-159">Voucher</span></span>
    -   <span data-ttu-id="13499-160">**FD** : Données financières de solde d'ouverture</span><span class="sxs-lookup"><span data-stu-id="13499-160">**FD** – The beginning balance financial data</span></span>
    -   <span data-ttu-id="13499-161">**FD** : Données financières qui contiennent uniquement des débits</span><span class="sxs-lookup"><span data-stu-id="13499-161">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="13499-162">**FD** : Données financières qui contiennent uniquement des crédits</span><span class="sxs-lookup"><span data-stu-id="13499-162">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="13499-163">**CALC** : Différence nette</span><span class="sxs-lookup"><span data-stu-id="13499-163">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="13499-164">**CALC** : Solde de clôture</span><span class="sxs-lookup"><span data-stu-id="13499-164">**CALC** – The closing balance</span></span>
-   <span data-ttu-id="13499-165">**Synthèse de balance comptable d'une année à l'autre - Par défaut :**</span><span class="sxs-lookup"><span data-stu-id="13499-165">**Summary Trial Balance Year Over Year – Default:**</span></span>
    -   <span data-ttu-id="13499-166">**ACCT** : Codes compte</span><span class="sxs-lookup"><span data-stu-id="13499-166">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="13499-167">**DESC** : Description de la définition de ligne.</span><span class="sxs-lookup"><span data-stu-id="13499-167">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="13499-168">**ATTR** : Attribut</span><span class="sxs-lookup"><span data-stu-id="13499-168">**ATTR** – An attribute</span></span>
        -   <span data-ttu-id="13499-169">N° document</span><span class="sxs-lookup"><span data-stu-id="13499-169">Voucher</span></span>
    -   <span data-ttu-id="13499-170">**FD** – Données financières de solde d'ouverture pour l'année actuelle</span><span class="sxs-lookup"><span data-stu-id="13499-170">**FD** – The beginning balance financial data for the current year</span></span>
    -   <span data-ttu-id="13499-171">**FD** : Données financières qui contiennent uniquement des débits pour l'année en cours</span><span class="sxs-lookup"><span data-stu-id="13499-171">**FD** – Financial data that contains only debits for the current year</span></span>
    -   <span data-ttu-id="13499-172">**FD** : Données financières qui contiennent uniquement des crédits pour l'année en cours</span><span class="sxs-lookup"><span data-stu-id="13499-172">**FD** – Financial data that contains only credits for the current year</span></span>
    -   <span data-ttu-id="13499-173">**CALC** : Différence nette</span><span class="sxs-lookup"><span data-stu-id="13499-173">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="13499-174">**CALC** : Solde de clôture</span><span class="sxs-lookup"><span data-stu-id="13499-174">**CALC** – The closing balance</span></span>
    -   <span data-ttu-id="13499-175">**FD** : Données financières qui contiennent uniquement des débits pour l'année dernière</span><span class="sxs-lookup"><span data-stu-id="13499-175">**FD** – Financial data that contains only debits for the last year</span></span>
    -   <span data-ttu-id="13499-176">**FD** : Données financières qui contiennent uniquement des crédits pour l'année dernière</span><span class="sxs-lookup"><span data-stu-id="13499-176">**FD** – Financial data that contains only credits for the last year</span></span>

 

<a name="see-also"></a><span data-ttu-id="13499-177">Voir également :</span><span class="sxs-lookup"><span data-stu-id="13499-177">See also</span></span>
--------

[<span data-ttu-id="13499-178">États financiers</span><span class="sxs-lookup"><span data-stu-id="13499-178">Financial reporting</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="13499-179">Afficher les états financiers</span><span class="sxs-lookup"><span data-stu-id="13499-179">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="13499-180">États financiers Dynamics (blog)</span><span class="sxs-lookup"><span data-stu-id="13499-180">Dynamics Financial Reporting Blog</span></span>](http://blogs.msdn.com/b/dynamics_financial_reporting/)




