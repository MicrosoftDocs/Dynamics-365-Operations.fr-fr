---
title: Double déclaration
description: Cette rubrique vous guide à travers un exemple qui montre comment vous pouvez remplir les exigences à la fois pour le reporting des normes internationales d’information financière (IFRS) et le reporting statutaire dans le bail d’actifs.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: c9f2bae330e688e1e941277d46ddcbd38916f8c8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815978"
---
# <a name="dual-reporting"></a><span data-ttu-id="57608-103">Double déclaration</span><span class="sxs-lookup"><span data-stu-id="57608-103">Dual reporting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="57608-104">Cette rubrique vous guide à travers un exemple qui montre comment vous pouvez remplir les exigences à la fois pour le reporting des normes internationales d’information financière (IFRS) et le reporting statutaire dans le bail d’actifs.</span><span class="sxs-lookup"><span data-stu-id="57608-104">This topic guides you through an example that shows how you can fulfill the requirements for both International Financial Reporting Standard (IFRS) reporting and statutory reporting in Asset leasing.</span></span> <span data-ttu-id="57608-105">Il est nécessaire d’être familiarisé avec les couches de validation dans Microsoft Dynamics 365 Finance, ce qui rendra l’exemple plus facile à comprendre.</span><span class="sxs-lookup"><span data-stu-id="57608-105">Familiarity with posting layers in Microsoft Dynamics 365 Finance is required and will make the example easier to understand.</span></span>

## <a name="example"></a><span data-ttu-id="57608-106">Exemple</span><span class="sxs-lookup"><span data-stu-id="57608-106">Example</span></span>

<span data-ttu-id="57608-107">L’exemple suivant rend compte d’un contrat de location selon le reporting statutaire italien en utilisant à la fois la méthode de la comptabilité de caisse et les méthodes de reporting IFRS.</span><span class="sxs-lookup"><span data-stu-id="57608-107">The following example accounts for a lease under Italian statutory reporting by using both the cash-basis method and IFRS reporting methods.</span></span> <span data-ttu-id="57608-108">L’entreprise doit établir trois registres pour tenir compte à la fois des exigences légales italiennes et des exigences d’IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="57608-108">The company must establish three books to account for both the Italian statutory requirements and the IFRS 16 requirements.</span></span> <span data-ttu-id="57608-109">Un registre est requis pour IFRS 16, un registre est requis pour les exigences statutaires et un registre est requis pour annuler automatiquement les écritures statutaires.</span><span class="sxs-lookup"><span data-stu-id="57608-109">One book is required for IFRS 16, one book is required for statutory requirements, and one book is required to automatically reverse statutory postings.</span></span> <span data-ttu-id="57608-110">Les registres sont configurés comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="57608-110">The books are set up as shown in the following tables.</span></span>

<span data-ttu-id="57608-111">**Registre IFRS 16**</span><span class="sxs-lookup"><span data-stu-id="57608-111">**IFRS 16 book**</span></span>

<span data-ttu-id="57608-112">Le registre IFRS 16 est mis en place de manière à être conforme à la norme comptable IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="57608-112">The IFRS 16 book is set up so that it complies with the IFRS 16 accounting standard.</span></span> <span data-ttu-id="57608-113">Toutes les entrées publiées dans ce livre seront publiées sur une couche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="57608-113">All entries that are posted in this book will be posted to a custom layer.</span></span>

| <span data-ttu-id="57608-114">Nom</span><span class="sxs-lookup"><span data-stu-id="57608-114">Name</span></span>                                    | <span data-ttu-id="57608-115">Description</span><span class="sxs-lookup"><span data-stu-id="57608-115">Description</span></span>    |
|-----------------------------------------|----------------|
| <span data-ttu-id="57608-116">Type de registre</span><span class="sxs-lookup"><span data-stu-id="57608-116">Book type</span></span>                               | <span data-ttu-id="57608-117">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="57608-117">IFRS 16</span></span>        |
| <span data-ttu-id="57608-118">Description du registre</span><span class="sxs-lookup"><span data-stu-id="57608-118">Book description</span></span>                        | <span data-ttu-id="57608-119">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="57608-119">IFRS 16</span></span>        |
| <span data-ttu-id="57608-120">Couche de comptabilisation</span><span class="sxs-lookup"><span data-stu-id="57608-120">Posting Layer</span></span>                           | <span data-ttu-id="57608-121">Couche personnalisée 1</span><span class="sxs-lookup"><span data-stu-id="57608-121">Custom layer 1</span></span> |
| <span data-ttu-id="57608-122">Type de bail</span><span class="sxs-lookup"><span data-stu-id="57608-122">Lease Type</span></span>                              | <span data-ttu-id="57608-123">Finances</span><span class="sxs-lookup"><span data-stu-id="57608-123">Finance</span></span>        |
| <span data-ttu-id="57608-124">Structure comptable</span><span class="sxs-lookup"><span data-stu-id="57608-124">Accounting Framework</span></span>                    | <span data-ttu-id="57608-125">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="57608-125">IFRS 16</span></span>        |
| <span data-ttu-id="57608-126">Configuration Durée du bail/Durée de vie utile</span><span class="sxs-lookup"><span data-stu-id="57608-126">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="57608-127">0,00</span><span class="sxs-lookup"><span data-stu-id="57608-127">0.00</span></span>           |
| <span data-ttu-id="57608-128">Configuration Valeur actuelle/Juste valeur de l’actif</span><span class="sxs-lookup"><span data-stu-id="57608-128">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="57608-129">0,00</span><span class="sxs-lookup"><span data-stu-id="57608-129">0.00</span></span>           |
| <span data-ttu-id="57608-130">Seuil à court terme</span><span class="sxs-lookup"><span data-stu-id="57608-130">Short-term threshold</span></span>                    | <span data-ttu-id="57608-131">12</span><span class="sxs-lookup"><span data-stu-id="57608-131">12</span></span>             |
| <span data-ttu-id="57608-132">Seuil de faible valeur</span><span class="sxs-lookup"><span data-stu-id="57608-132">Low Value Threshold</span></span>                     | <span data-ttu-id="57608-133">5,000.00</span><span class="sxs-lookup"><span data-stu-id="57608-133">5,000.00</span></span>       |
| <span data-ttu-id="57608-134">Payer au fournisseur</span><span class="sxs-lookup"><span data-stu-id="57608-134">Pay to Vendor</span></span>                           | <span data-ttu-id="57608-135">N°</span><span class="sxs-lookup"><span data-stu-id="57608-135">No</span></span>             |

<span data-ttu-id="57608-136">**Registre statutaire**</span><span class="sxs-lookup"><span data-stu-id="57608-136">**Statutory book**</span></span>

<span data-ttu-id="57608-137">Le registre statutaire est un registre de comptabilité de caisse dans lequel la société comptabilise les frais de location comme le montant en espèces payé chaque mois pour le loyer.</span><span class="sxs-lookup"><span data-stu-id="57608-137">The statutory book is a cash-basis book where the company will account for the lease expense as the amount of cash that is paid each month for rent.</span></span> <span data-ttu-id="57608-138">Ce registre ne produira pas de droit d’utilisation de l’actif (ROU) ni de passif locatif.</span><span class="sxs-lookup"><span data-stu-id="57608-138">This book won't produce a right-of-use (ROU) asset or lease liability.</span></span>

| <span data-ttu-id="57608-139">Nom</span><span class="sxs-lookup"><span data-stu-id="57608-139">Name</span></span>                                    | <span data-ttu-id="57608-140">Description</span><span class="sxs-lookup"><span data-stu-id="57608-140">Description</span></span> |
|-----------------------------------------|-------------|
| <span data-ttu-id="57608-141">Type de registre</span><span class="sxs-lookup"><span data-stu-id="57608-141">Book type</span></span>                               | <span data-ttu-id="57608-142">Statutaire</span><span class="sxs-lookup"><span data-stu-id="57608-142">Statutory</span></span>   |
| <span data-ttu-id="57608-143">Description du registre</span><span class="sxs-lookup"><span data-stu-id="57608-143">Book description</span></span>                        | <span data-ttu-id="57608-144">GAAP local</span><span class="sxs-lookup"><span data-stu-id="57608-144">Local GAAP</span></span>  |
| <span data-ttu-id="57608-145">Couche de comptabilisation</span><span class="sxs-lookup"><span data-stu-id="57608-145">Posting Layer</span></span>                           | <span data-ttu-id="57608-146">Actuelle</span><span class="sxs-lookup"><span data-stu-id="57608-146">Current</span></span>     |
| <span data-ttu-id="57608-147">Type de bail</span><span class="sxs-lookup"><span data-stu-id="57608-147">Lease Type</span></span>                              | <span data-ttu-id="57608-148">Automatique</span><span class="sxs-lookup"><span data-stu-id="57608-148">Automatic</span></span>   |
| <span data-ttu-id="57608-149">Structure comptable</span><span class="sxs-lookup"><span data-stu-id="57608-149">Accounting Framework</span></span>                    | <span data-ttu-id="57608-150">Base de trésorerie</span><span class="sxs-lookup"><span data-stu-id="57608-150">Cash basis</span></span>  |
| <span data-ttu-id="57608-151">Configuration Durée du bail/Durée de vie utile</span><span class="sxs-lookup"><span data-stu-id="57608-151">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="57608-152">0,00</span><span class="sxs-lookup"><span data-stu-id="57608-152">0.00</span></span>        |
| <span data-ttu-id="57608-153">Configuration Valeur actuelle/Juste valeur de l’actif</span><span class="sxs-lookup"><span data-stu-id="57608-153">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="57608-154">0,00</span><span class="sxs-lookup"><span data-stu-id="57608-154">0.00</span></span>        |
| <span data-ttu-id="57608-155">Seuil à court terme</span><span class="sxs-lookup"><span data-stu-id="57608-155">Short-term threshold</span></span>                    | <span data-ttu-id="57608-156">0</span><span class="sxs-lookup"><span data-stu-id="57608-156">0</span></span>           |
| <span data-ttu-id="57608-157">Seuil de faible valeur</span><span class="sxs-lookup"><span data-stu-id="57608-157">Low Value Threshold</span></span>                     | <span data-ttu-id="57608-158">0</span><span class="sxs-lookup"><span data-stu-id="57608-158">0</span></span>           |
| <span data-ttu-id="57608-159">Payer au fournisseur</span><span class="sxs-lookup"><span data-stu-id="57608-159">Pay to Vendor</span></span>                           | <span data-ttu-id="57608-160">N°</span><span class="sxs-lookup"><span data-stu-id="57608-160">No</span></span>          |

<span data-ttu-id="57608-161">**Registre de contrepassation statutaire**</span><span class="sxs-lookup"><span data-stu-id="57608-161">**Statutory reversal book**</span></span>

<span data-ttu-id="57608-162">Le registre de contrepassation statutaire est constitué de la même manière que le registre statutaire.</span><span class="sxs-lookup"><span data-stu-id="57608-162">The statutory reversal book is set up in the same way as the statutory book.</span></span>

| <span data-ttu-id="57608-163">Nom</span><span class="sxs-lookup"><span data-stu-id="57608-163">Name</span></span>                                    | <span data-ttu-id="57608-164">Description</span><span class="sxs-lookup"><span data-stu-id="57608-164">Description</span></span>                    |
|-----------------------------------------|--------------------------------|
| <span data-ttu-id="57608-165">Type de registre</span><span class="sxs-lookup"><span data-stu-id="57608-165">Book type</span></span>                               | <span data-ttu-id="57608-166">Statutaire – contrepassation</span><span class="sxs-lookup"><span data-stu-id="57608-166">Statutory – Reversal</span></span>           |
| <span data-ttu-id="57608-167">Description du registre</span><span class="sxs-lookup"><span data-stu-id="57608-167">Book description</span></span>                        | <span data-ttu-id="57608-168">Registre pour contrepasser le registre statutaire</span><span class="sxs-lookup"><span data-stu-id="57608-168">Book to reverse statutory book</span></span> |
| <span data-ttu-id="57608-169">Couche de comptabilisation</span><span class="sxs-lookup"><span data-stu-id="57608-169">Posting Layer</span></span>                           | <span data-ttu-id="57608-170">Couche personnalisée 1</span><span class="sxs-lookup"><span data-stu-id="57608-170">Custom layer 1</span></span>                 |
| <span data-ttu-id="57608-171">Type de bail</span><span class="sxs-lookup"><span data-stu-id="57608-171">Lease Type</span></span>                              | <span data-ttu-id="57608-172">Automatique</span><span class="sxs-lookup"><span data-stu-id="57608-172">Automatic</span></span>                      |
| <span data-ttu-id="57608-173">Structure comptable</span><span class="sxs-lookup"><span data-stu-id="57608-173">Accounting Framework</span></span>                    | <span data-ttu-id="57608-174">Base de trésorerie</span><span class="sxs-lookup"><span data-stu-id="57608-174">Cash basis</span></span>                     |
| <span data-ttu-id="57608-175">Configuration Durée du bail/Durée de vie utile</span><span class="sxs-lookup"><span data-stu-id="57608-175">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="57608-176">0,00</span><span class="sxs-lookup"><span data-stu-id="57608-176">0.00</span></span>                           |
| <span data-ttu-id="57608-177">Configuration Valeur actuelle/Juste valeur de l’actif</span><span class="sxs-lookup"><span data-stu-id="57608-177">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="57608-178">0,00</span><span class="sxs-lookup"><span data-stu-id="57608-178">0.00</span></span>                           |
| <span data-ttu-id="57608-179">Seuil à court terme</span><span class="sxs-lookup"><span data-stu-id="57608-179">Short-term threshold</span></span>                    | <span data-ttu-id="57608-180">0</span><span class="sxs-lookup"><span data-stu-id="57608-180">0</span></span>                              |
| <span data-ttu-id="57608-181">Seuil de faible valeur</span><span class="sxs-lookup"><span data-stu-id="57608-181">Low Value Threshold</span></span>                     | <span data-ttu-id="57608-182">0</span><span class="sxs-lookup"><span data-stu-id="57608-182">0</span></span>                              |
| <span data-ttu-id="57608-183">Payer au fournisseur</span><span class="sxs-lookup"><span data-stu-id="57608-183">Pay to Vendor</span></span>                           | <span data-ttu-id="57608-184">N°</span><span class="sxs-lookup"><span data-stu-id="57608-184">No</span></span>                             |

<span data-ttu-id="57608-185">Pour cet exemple, un bail a été créé avec les paramètres suivants sur les onglets **Général** et **Lignes d’échéancier de paiement**.</span><span class="sxs-lookup"><span data-stu-id="57608-185">For this example, a lease has been created that has the following settings on the **General** and **Payment schedule lines** tabs.</span></span>

<span data-ttu-id="57608-186">**Onglet Général**</span><span class="sxs-lookup"><span data-stu-id="57608-186">**General tab**</span></span>

| <span data-ttu-id="57608-187">Champ</span><span class="sxs-lookup"><span data-stu-id="57608-187">Field</span></span>                      | <span data-ttu-id="57608-188">Valeur</span><span class="sxs-lookup"><span data-stu-id="57608-188">Value</span></span>            |
|----------------------------|------------------|
| <span data-ttu-id="57608-189">Taux d’emprunt marginal</span><span class="sxs-lookup"><span data-stu-id="57608-189">Incremental borrowing rate</span></span> | <span data-ttu-id="57608-190">5 %</span><span class="sxs-lookup"><span data-stu-id="57608-190">5%</span></span>               |
| <span data-ttu-id="57608-191">Date d’entrée en vigueur</span><span class="sxs-lookup"><span data-stu-id="57608-191">Commencement date</span></span>          | <span data-ttu-id="57608-192">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="57608-192">1/1/2020</span></span>         |
| <span data-ttu-id="57608-193">Groupe de baux</span><span class="sxs-lookup"><span data-stu-id="57608-193">Lease group</span></span>                | <span data-ttu-id="57608-194">Bâtiments</span><span class="sxs-lookup"><span data-stu-id="57608-194">Buildings</span></span>        |
| <span data-ttu-id="57608-195">Fournisseur</span><span class="sxs-lookup"><span data-stu-id="57608-195">Vendor</span></span>                     | <span data-ttu-id="57608-196">1001</span><span class="sxs-lookup"><span data-stu-id="57608-196">1001</span></span>             |
| <span data-ttu-id="57608-197">Juste valeur de l’actif</span><span class="sxs-lookup"><span data-stu-id="57608-197">Fair value of the asset</span></span>    | <span data-ttu-id="57608-198">245,000</span><span class="sxs-lookup"><span data-stu-id="57608-198">245,000</span></span>          |
| <span data-ttu-id="57608-199">Durée de vie utile de l’actif</span><span class="sxs-lookup"><span data-stu-id="57608-199">Asset useful life</span></span>          | <span data-ttu-id="57608-200">120</span><span class="sxs-lookup"><span data-stu-id="57608-200">120</span></span>              |
| <span data-ttu-id="57608-201">Type d’annuité</span><span class="sxs-lookup"><span data-stu-id="57608-201">Annuity type</span></span>               | <span data-ttu-id="57608-202">Annuité ordinaire</span><span class="sxs-lookup"><span data-stu-id="57608-202">Ordinary annuity</span></span> |
| <span data-ttu-id="57608-203">Intervalle de composition</span><span class="sxs-lookup"><span data-stu-id="57608-203">Compounding interval</span></span>       | <span data-ttu-id="57608-204">Tous les mois</span><span class="sxs-lookup"><span data-stu-id="57608-204">Monthly</span></span>          |

<span data-ttu-id="57608-205">**Onglet Lignes d’échéancier de paiement**</span><span class="sxs-lookup"><span data-stu-id="57608-205">**Payment schedule lines tab**</span></span>

| <span data-ttu-id="57608-206">Champ</span><span class="sxs-lookup"><span data-stu-id="57608-206">Field</span></span>             | <span data-ttu-id="57608-207">Valeur</span><span class="sxs-lookup"><span data-stu-id="57608-207">Value</span></span>      |
|-------------------|------------|
| <span data-ttu-id="57608-208">Date de début</span><span class="sxs-lookup"><span data-stu-id="57608-208">Start date</span></span>        | <span data-ttu-id="57608-209">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="57608-209">1/1/2020</span></span>   |
| <span data-ttu-id="57608-210">Intervalle de périodes</span><span class="sxs-lookup"><span data-stu-id="57608-210">Period interval</span></span>   | <span data-ttu-id="57608-211">Mois</span><span class="sxs-lookup"><span data-stu-id="57608-211">Months</span></span>     |
| <span data-ttu-id="57608-212">Périodes</span><span class="sxs-lookup"><span data-stu-id="57608-212">Periods</span></span>           | <span data-ttu-id="57608-213">24</span><span class="sxs-lookup"><span data-stu-id="57608-213">24</span></span>         |
| <span data-ttu-id="57608-214">Date de fin</span><span class="sxs-lookup"><span data-stu-id="57608-214">End date</span></span>          | <span data-ttu-id="57608-215">31/12/2020</span><span class="sxs-lookup"><span data-stu-id="57608-215">12/31/2020</span></span> |
| <span data-ttu-id="57608-216">Fréquence de paiement</span><span class="sxs-lookup"><span data-stu-id="57608-216">Payment frequency</span></span> | <span data-ttu-id="57608-217">Tous les mois</span><span class="sxs-lookup"><span data-stu-id="57608-217">Monthly</span></span>    |
| <span data-ttu-id="57608-218">Montant du paiement</span><span class="sxs-lookup"><span data-stu-id="57608-218">Payment amount</span></span>    | <span data-ttu-id="57608-219">1 000</span><span class="sxs-lookup"><span data-stu-id="57608-219">1,000</span></span>      |

<span data-ttu-id="57608-220">Pour tenir compte de ce bail sous deux structures, vous utilisez une couche de validation actuelle et une couche de validation personnalisée.</span><span class="sxs-lookup"><span data-stu-id="57608-220">To account for this lease under two frameworks, you use a current posting layer and a custom posting layer.</span></span> <span data-ttu-id="57608-221">Le tableau suivant montre un exemple de chaque écriture de journal nécessaire pour représenter fidèlement les données financières selon chaque norme de reporting.</span><span class="sxs-lookup"><span data-stu-id="57608-221">The following table shows an example of every journal entry that required to fairly represent the financials under each reporting standard.</span></span> <span data-ttu-id="57608-222">Une description détaillée de chaque écriture de journal pour le premier mois du bail est fournie par la suite.</span><span class="sxs-lookup"><span data-stu-id="57608-222">A detailed description of each journal entry for the first month of the lease is provided afterward.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="57608-223">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="57608-223">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="57608-224">Description</span><span class="sxs-lookup"><span data-stu-id="57608-224">Description</span></span></th>
<th colspan='3'><span data-ttu-id="57608-225">Registre statutaire (couche actuelle)</span><span class="sxs-lookup"><span data-stu-id="57608-225">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="57608-226">Total de la couche actuelle</span><span class="sxs-lookup"><span data-stu-id="57608-226">Current layer total</span></span></th>
<th><span data-ttu-id="57608-227">Registre de contrepassation (couche personnalisée)</span><span class="sxs-lookup"><span data-stu-id="57608-227">Reversal book (custom layer)</span></span></th>
<th colspan='4'><span data-ttu-id="57608-228">Registre IFRS 16 (couche personnalisée)</span><span class="sxs-lookup"><span data-stu-id="57608-228">IFRS 16 book (custom layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="57608-229">Couche actuelle + total de la couche personnalisée</span><span class="sxs-lookup"><span data-stu-id="57608-229">Current layer + custom layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="57608-230">JE-100</span><span class="sxs-lookup"><span data-stu-id="57608-230">JE-100</span></span></th>
<th><span data-ttu-id="57608-231">JE-110</span><span class="sxs-lookup"><span data-stu-id="57608-231">JE-110</span></span></th>
<th><span data-ttu-id="57608-232">JE-120</span><span class="sxs-lookup"><span data-stu-id="57608-232">JE-120</span></span></th>
<th><span data-ttu-id="57608-233">JE-130</span><span class="sxs-lookup"><span data-stu-id="57608-233">JE-130</span></span></th>
<th><span data-ttu-id="57608-234">JE-140</span><span class="sxs-lookup"><span data-stu-id="57608-234">JE-140</span></span></th>
<th><span data-ttu-id="57608-235">JE-150</span><span class="sxs-lookup"><span data-stu-id="57608-235">JE-150</span></span></th>
<th><span data-ttu-id="57608-236">JE-160</span><span class="sxs-lookup"><span data-stu-id="57608-236">JE-160</span></span></th>
<th><span data-ttu-id="57608-237">JE-170</span><span class="sxs-lookup"><span data-stu-id="57608-237">JE-170</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="57608-238">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="57608-238">Dr (Cr)</span></span></th>
<th><span data-ttu-id="57608-239">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="57608-239">Dr (Cr)</span></span></th>
<th><span data-ttu-id="57608-240">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="57608-240">Dr (Cr)</span></span></th>
<th><span data-ttu-id="57608-241">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="57608-241">Dr (Cr)</span></span></th>
<th><span data-ttu-id="57608-242">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="57608-242">Dr (Cr)</span></span></th>
<th><span data-ttu-id="57608-243">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="57608-243">Dr (Cr)</span></span></th>
<th><span data-ttu-id="57608-244">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="57608-244">Dr (Cr)</span></span></th>
<th><span data-ttu-id="57608-245">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="57608-245">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57608-246">1</span><span class="sxs-lookup"><span data-stu-id="57608-246">1</span></span></td>
<td><span data-ttu-id="57608-247">Dépense de bail</span><span class="sxs-lookup"><span data-stu-id="57608-247">Lease expense</span></span></td>
<td><span data-ttu-id="57608-248">1,000.00</span><span class="sxs-lookup"><span data-stu-id="57608-248">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="57608-249">1,000.00</span><span class="sxs-lookup"><span data-stu-id="57608-249">1,000.00</span></span></td>
<td><span data-ttu-id="57608-250">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="57608-250">-1,000.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="57608-251">0,00</span><span class="sxs-lookup"><span data-stu-id="57608-251">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57608-252">2</span><span class="sxs-lookup"><span data-stu-id="57608-252">2</span></span></td>
<td><span data-ttu-id="57608-253">Frais bancaires</span><span class="sxs-lookup"><span data-stu-id="57608-253">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="57608-254">3.00</span><span class="sxs-lookup"><span data-stu-id="57608-254">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="57608-255">3.00</span><span class="sxs-lookup"><span data-stu-id="57608-255">3.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="57608-256">3.00</span><span class="sxs-lookup"><span data-stu-id="57608-256">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57608-257">3</span><span class="sxs-lookup"><span data-stu-id="57608-257">3</span></span></td>
<td><span data-ttu-id="57608-258">Dépenses de TVA</span><span class="sxs-lookup"><span data-stu-id="57608-258">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="57608-259">5.00</span><span class="sxs-lookup"><span data-stu-id="57608-259">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="57608-260">5.00</span><span class="sxs-lookup"><span data-stu-id="57608-260">5.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="57608-261">5.00</span><span class="sxs-lookup"><span data-stu-id="57608-261">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57608-262">4</span><span class="sxs-lookup"><span data-stu-id="57608-262">4</span></span></td>
<td><span data-ttu-id="57608-263">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="57608-263">Clearing account</span></span></td>
<td><span data-ttu-id="57608-264">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="57608-264">-1,000.00</span></span></td>
<td><span data-ttu-id="57608-265">1,000.00</span><span class="sxs-lookup"><span data-stu-id="57608-265">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="57608-266">0,00</span><span class="sxs-lookup"><span data-stu-id="57608-266">0.00</span></span></td>
<td><span data-ttu-id="57608-267">1,000.00</span><span class="sxs-lookup"><span data-stu-id="57608-267">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="57608-268">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="57608-268">-1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="57608-269">0,00</span><span class="sxs-lookup"><span data-stu-id="57608-269">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57608-270">5</span><span class="sxs-lookup"><span data-stu-id="57608-270">5</span></span></td>
<td><span data-ttu-id="57608-271">Module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="57608-271">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="57608-272">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="57608-272">-1,008.00</span></span></td>
<td><span data-ttu-id="57608-273">1,008.00</span><span class="sxs-lookup"><span data-stu-id="57608-273">1,008.00</span></span></td>
<td><span data-ttu-id="57608-274">0,00</span><span class="sxs-lookup"><span data-stu-id="57608-274">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="57608-275">0,00</span><span class="sxs-lookup"><span data-stu-id="57608-275">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57608-276">6</span><span class="sxs-lookup"><span data-stu-id="57608-276">6</span></span></td>
<td><span data-ttu-id="57608-277">Droit d’utilisation de l’actif</span><span class="sxs-lookup"><span data-stu-id="57608-277">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="57608-278">0,00</span><span class="sxs-lookup"><span data-stu-id="57608-278">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="57608-279">22,794.00</span><span class="sxs-lookup"><span data-stu-id="57608-279">22,794.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="57608-280">22,793.90</span><span class="sxs-lookup"><span data-stu-id="57608-280">22,793.90</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57608-281">7</span><span class="sxs-lookup"><span data-stu-id="57608-281">7</span></span></td>
<td><span data-ttu-id="57608-282">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="57608-282">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="57608-283">0,00</span><span class="sxs-lookup"><span data-stu-id="57608-283">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="57608-284">-22 794,00</span><span class="sxs-lookup"><span data-stu-id="57608-284">-22,794.00</span></span></td>
<td><span data-ttu-id="57608-285">1,000.00</span><span class="sxs-lookup"><span data-stu-id="57608-285">1,000.00</span></span></td>
<td><span data-ttu-id="57608-286">-94,97</span><span class="sxs-lookup"><span data-stu-id="57608-286">-94.97</span></span></td>
<td></td>
<td><span data-ttu-id="57608-287">-21 888,87</span><span class="sxs-lookup"><span data-stu-id="57608-287">-21,888.87</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57608-288">8</span><span class="sxs-lookup"><span data-stu-id="57608-288">8</span></span></td>
<td><span data-ttu-id="57608-289">Dépenses d’intérêts</span><span class="sxs-lookup"><span data-stu-id="57608-289">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="57608-290">0,00</span><span class="sxs-lookup"><span data-stu-id="57608-290">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="57608-291">94.97</span><span class="sxs-lookup"><span data-stu-id="57608-291">94.97</span></span></td>
<td></td>
<td><span data-ttu-id="57608-292">94.97</span><span class="sxs-lookup"><span data-stu-id="57608-292">94.97</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57608-293">9</span><span class="sxs-lookup"><span data-stu-id="57608-293">9</span></span></td>
<td><span data-ttu-id="57608-294">Monétaire</span><span class="sxs-lookup"><span data-stu-id="57608-294">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="57608-295">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="57608-295">-1,008.00</span></span></td>
<td><span data-ttu-id="57608-296">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="57608-296">-1,008.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="57608-297">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="57608-297">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57608-298">10</span><span class="sxs-lookup"><span data-stu-id="57608-298">10</span></span></td>
<td><span data-ttu-id="57608-299">Dépenses d’amortissement</span><span class="sxs-lookup"><span data-stu-id="57608-299">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="57608-300">0,00</span><span class="sxs-lookup"><span data-stu-id="57608-300">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="57608-301">949.75</span><span class="sxs-lookup"><span data-stu-id="57608-301">949.75</span></span></td>
<td><span data-ttu-id="57608-302">949.75</span><span class="sxs-lookup"><span data-stu-id="57608-302">949.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57608-303">11</span><span class="sxs-lookup"><span data-stu-id="57608-303">11</span></span></td>
<td><span data-ttu-id="57608-304">Amortissement cumulé</span><span class="sxs-lookup"><span data-stu-id="57608-304">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="57608-305">0,00</span><span class="sxs-lookup"><span data-stu-id="57608-305">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="57608-306">-949,75</span><span class="sxs-lookup"><span data-stu-id="57608-306">-949.75</span></span></td>
<td><span data-ttu-id="57608-307">-949,75</span><span class="sxs-lookup"><span data-stu-id="57608-307">-949.75</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="57608-308">Comme le montre le tableau précédent, trois registres sont tenus pour déclarer à la fois le reporting statutaire et le reporting IFRS.</span><span class="sxs-lookup"><span data-stu-id="57608-308">As the preceding table shows, three books are required to report under both statutory reporting and IFRS reporting.</span></span>

- <span data-ttu-id="57608-309">Le registre statutaire enregistre le paiement de location selon les règles de comptabilité de caisse sous la couche actuelle.</span><span class="sxs-lookup"><span data-stu-id="57608-309">The statutory book records the lease payment according to the rules for cash-basis accounting under the current layer.</span></span>
- <span data-ttu-id="57608-310">Le registre de contrepassation statutaire annule les écritures au journal statutaire.</span><span class="sxs-lookup"><span data-stu-id="57608-310">The statutory reversal book reverses the statutory journal entries.</span></span>
- <span data-ttu-id="57608-311">Le registre IFRS 16 crée les écritures de journal requises en vertu d’IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="57608-311">The IFRS 16 book creates the journal entries that are required under IFRS 16.</span></span>

<span data-ttu-id="57608-312">Vous ne devez saisir un bail qu’une seule fois.</span><span class="sxs-lookup"><span data-stu-id="57608-312">You must enter a lease only one time.</span></span> <span data-ttu-id="57608-313">Vous pouvez ensuite ouvrir la page **Registres** pour voir tous les registres associés au bail.</span><span class="sxs-lookup"><span data-stu-id="57608-313">You can then open the **Books** page to see all the books that are associated with the lease.</span></span>

> [!NOTE]
> <span data-ttu-id="57608-314">Lorsque vous créez les registres, tous les trois doivent être associés au même enregistrement de bail.</span><span class="sxs-lookup"><span data-stu-id="57608-314">When you create the books, all three of them must be associated with the same lease record.</span></span>

<span data-ttu-id="57608-315">La première écriture de journal enregistre les frais de location dans le registre statutaire.</span><span class="sxs-lookup"><span data-stu-id="57608-315">The first journal entry records the lease expense under the statutory book.</span></span> <span data-ttu-id="57608-316">Vous pouvez créer les paiements soit par lots, soit en sélectionnant l’échéancier de paiement dans le registre statutaire.</span><span class="sxs-lookup"><span data-stu-id="57608-316">You can create the payments either in a batch or by selecting the payment schedule in the statutory book.</span></span>

<span data-ttu-id="57608-317">Pour cet exemple, l’écriture de journal suivante est produite pour le registre statutaire à partir de l’échéancier de paiement.</span><span class="sxs-lookup"><span data-stu-id="57608-317">For this example, the following journal entry is produced for the statutory book from the payment schedule.</span></span>

### <a name="lease-payment--1312020--je-100"></a><span data-ttu-id="57608-318">Paiement de location – 31/01/2020 – JE 100</span><span class="sxs-lookup"><span data-stu-id="57608-318">Lease payment – 1/31/2020 – JE 100</span></span>

| <span data-ttu-id="57608-319">Type de compte</span><span class="sxs-lookup"><span data-stu-id="57608-319">Account type</span></span> | <span data-ttu-id="57608-320">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="57608-320">Account number</span></span> | <span data-ttu-id="57608-321">Couche</span><span class="sxs-lookup"><span data-stu-id="57608-321">Layer</span></span>   | <span data-ttu-id="57608-322">Description du compte</span><span class="sxs-lookup"><span data-stu-id="57608-322">Account description</span></span> | <span data-ttu-id="57608-323">Débit</span><span class="sxs-lookup"><span data-stu-id="57608-323">Debit</span></span>    | <span data-ttu-id="57608-324">Crédit</span><span class="sxs-lookup"><span data-stu-id="57608-324">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="57608-325">Registre</span><span class="sxs-lookup"><span data-stu-id="57608-325">Ledger</span></span>       | <span data-ttu-id="57608-326">1</span><span class="sxs-lookup"><span data-stu-id="57608-326">1</span></span>              | <span data-ttu-id="57608-327">Actuelle</span><span class="sxs-lookup"><span data-stu-id="57608-327">Current</span></span> | <span data-ttu-id="57608-328">Dépense de bail</span><span class="sxs-lookup"><span data-stu-id="57608-328">Lease expense</span></span>       | <span data-ttu-id="57608-329">1,000.00</span><span class="sxs-lookup"><span data-stu-id="57608-329">1,000.00</span></span> |          |
| <span data-ttu-id="57608-330">Registre</span><span class="sxs-lookup"><span data-stu-id="57608-330">Ledger</span></span>       | <span data-ttu-id="57608-331">4</span><span class="sxs-lookup"><span data-stu-id="57608-331">4</span></span>              | <span data-ttu-id="57608-332">Actuelle</span><span class="sxs-lookup"><span data-stu-id="57608-332">Current</span></span> | <span data-ttu-id="57608-333">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="57608-333">Clearing account</span></span>    |          | <span data-ttu-id="57608-334">1,000.00</span><span class="sxs-lookup"><span data-stu-id="57608-334">1,000.00</span></span> |

<span data-ttu-id="57608-335">Un commis aux comptes fournisseurs utilise la fonctionnalité standard de Dynamics 365 pour créer une facture pour payer le bail en dehors de la location d’actifs.</span><span class="sxs-lookup"><span data-stu-id="57608-335">An Accounts payable clerk uses standard Dynamics 365 functionality to create an invoice to pay for the lease outside Asset leasing.</span></span> <span data-ttu-id="57608-336">Cependant, au lieu de sélectionner **Frais de location** comme compte de débit, le commis aux comptes fournisseurs sélectionne un compte de compensation pour générer l’écriture suivante.</span><span class="sxs-lookup"><span data-stu-id="57608-336">However, instead of selecting **Lease expense** as the debit account, the Accounts payable clerk selects a clearing account to generate the following entry.</span></span>

### <a name="ap-process--1312020--je-110"></a><span data-ttu-id="57608-337">Processus AP – 31/01/2020 – JE 110</span><span class="sxs-lookup"><span data-stu-id="57608-337">AP process – 1/31/2020 – JE 110</span></span>

| <span data-ttu-id="57608-338">Type de compte</span><span class="sxs-lookup"><span data-stu-id="57608-338">Account type</span></span> | <span data-ttu-id="57608-339">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="57608-339">Account number</span></span> | <span data-ttu-id="57608-340">Couche</span><span class="sxs-lookup"><span data-stu-id="57608-340">Layer</span></span>   | <span data-ttu-id="57608-341">Description du compte</span><span class="sxs-lookup"><span data-stu-id="57608-341">Account description</span></span> | <span data-ttu-id="57608-342">Débit</span><span class="sxs-lookup"><span data-stu-id="57608-342">Debit</span></span>    | <span data-ttu-id="57608-343">Crédit</span><span class="sxs-lookup"><span data-stu-id="57608-343">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="57608-344">Registre</span><span class="sxs-lookup"><span data-stu-id="57608-344">Ledger</span></span>       | <span data-ttu-id="57608-345">4</span><span class="sxs-lookup"><span data-stu-id="57608-345">4</span></span>              | <span data-ttu-id="57608-346">Actuelle</span><span class="sxs-lookup"><span data-stu-id="57608-346">Current</span></span> | <span data-ttu-id="57608-347">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="57608-347">Clearing account</span></span>    | <span data-ttu-id="57608-348">1,000.00</span><span class="sxs-lookup"><span data-stu-id="57608-348">1,000.00</span></span> |          |
| <span data-ttu-id="57608-349">Registre</span><span class="sxs-lookup"><span data-stu-id="57608-349">Ledger</span></span>       | <span data-ttu-id="57608-350">2</span><span class="sxs-lookup"><span data-stu-id="57608-350">2</span></span>              | <span data-ttu-id="57608-351">Actuelle</span><span class="sxs-lookup"><span data-stu-id="57608-351">Current</span></span> | <span data-ttu-id="57608-352">Frais bancaires</span><span class="sxs-lookup"><span data-stu-id="57608-352">Bank fee</span></span>            | <span data-ttu-id="57608-353">3.00</span><span class="sxs-lookup"><span data-stu-id="57608-353">3.00</span></span>     |          |
| <span data-ttu-id="57608-354">Registre</span><span class="sxs-lookup"><span data-stu-id="57608-354">Ledger</span></span>       | <span data-ttu-id="57608-355">3</span><span class="sxs-lookup"><span data-stu-id="57608-355">3</span></span>              | <span data-ttu-id="57608-356">Actuelle</span><span class="sxs-lookup"><span data-stu-id="57608-356">Current</span></span> | <span data-ttu-id="57608-357">Dépenses de TVA</span><span class="sxs-lookup"><span data-stu-id="57608-357">VAT expense</span></span>         | <span data-ttu-id="57608-358">5.00</span><span class="sxs-lookup"><span data-stu-id="57608-358">5.00</span></span>     |          |
| <span data-ttu-id="57608-359">Fournisseur</span><span class="sxs-lookup"><span data-stu-id="57608-359">Vendor</span></span>       | <span data-ttu-id="57608-360">5</span><span class="sxs-lookup"><span data-stu-id="57608-360">5</span></span>              | <span data-ttu-id="57608-361">Actuelle</span><span class="sxs-lookup"><span data-stu-id="57608-361">Current</span></span> | <span data-ttu-id="57608-362">Module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="57608-362">Accounts payable</span></span>    |          | <span data-ttu-id="57608-363">1,008.00</span><span class="sxs-lookup"><span data-stu-id="57608-363">1,008.00</span></span> |

<span data-ttu-id="57608-364">Lorsque la déclaration est délivrée au fournisseur, vous suivez le processus de paiement régulier.</span><span class="sxs-lookup"><span data-stu-id="57608-364">When the statement is issued to the vendor, you follow the regular payment process.</span></span> <span data-ttu-id="57608-365">Au cours de ce processus, l’écriture de journal suivante est générée.</span><span class="sxs-lookup"><span data-stu-id="57608-365">During this process, the following journal entry is generated.</span></span>

### <a name="cash-payment--1312020--je-120"></a><span data-ttu-id="57608-366">Paiement en espèces – 31/01/2020 – JE 120</span><span class="sxs-lookup"><span data-stu-id="57608-366">Cash payment – 1/31/2020 – JE 120</span></span>

| <span data-ttu-id="57608-367">Type de compte</span><span class="sxs-lookup"><span data-stu-id="57608-367">Account type</span></span> | <span data-ttu-id="57608-368">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="57608-368">Account number</span></span> | <span data-ttu-id="57608-369">Couche</span><span class="sxs-lookup"><span data-stu-id="57608-369">Layer</span></span>   | <span data-ttu-id="57608-370">Description du compte</span><span class="sxs-lookup"><span data-stu-id="57608-370">Account description</span></span> | <span data-ttu-id="57608-371">Débit</span><span class="sxs-lookup"><span data-stu-id="57608-371">Debit</span></span>    | <span data-ttu-id="57608-372">Crédit</span><span class="sxs-lookup"><span data-stu-id="57608-372">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="57608-373">Fournisseur</span><span class="sxs-lookup"><span data-stu-id="57608-373">Vendor</span></span>       | <span data-ttu-id="57608-374">5</span><span class="sxs-lookup"><span data-stu-id="57608-374">5</span></span>              | <span data-ttu-id="57608-375">Actuelle</span><span class="sxs-lookup"><span data-stu-id="57608-375">Current</span></span> | <span data-ttu-id="57608-376">Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="57608-376">Accounts Payable</span></span>    | <span data-ttu-id="57608-377">1,008.00</span><span class="sxs-lookup"><span data-stu-id="57608-377">1,008.00</span></span> |          |
| <span data-ttu-id="57608-378">Banque</span><span class="sxs-lookup"><span data-stu-id="57608-378">Bank</span></span>         | <span data-ttu-id="57608-379">9</span><span class="sxs-lookup"><span data-stu-id="57608-379">9</span></span>              | <span data-ttu-id="57608-380">Actuelle</span><span class="sxs-lookup"><span data-stu-id="57608-380">Current</span></span> | <span data-ttu-id="57608-381">Monétaire</span><span class="sxs-lookup"><span data-stu-id="57608-381">Cash</span></span>                |          | <span data-ttu-id="57608-382">1,008.00</span><span class="sxs-lookup"><span data-stu-id="57608-382">1,008.00</span></span> |

<span data-ttu-id="57608-383">À ce stade, vous avez pleinement pris en compte ce bail conformément aux exigences légales en matière de rapports et pouvez générer une balance comptable en utilisant la couche actuelle.</span><span class="sxs-lookup"><span data-stu-id="57608-383">At this point, you've fully accounted for this lease under statutory reporting requirements and can generate a trial balance by using the current layer.</span></span> <span data-ttu-id="57608-384">Le système renvoie une balance comptable qui a les chiffres suivants.</span><span class="sxs-lookup"><span data-stu-id="57608-384">The system returns a trial balance that has the following figures.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="57608-385">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="57608-385">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="57608-386">Description</span><span class="sxs-lookup"><span data-stu-id="57608-386">Description</span></span></th>
<th colspan='3'><span data-ttu-id="57608-387">Registre statutaire (couche actuelle)</span><span class="sxs-lookup"><span data-stu-id="57608-387">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="57608-388">Total de la couche actuelle</span><span class="sxs-lookup"><span data-stu-id="57608-388">Current layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="57608-389">JE-100</span><span class="sxs-lookup"><span data-stu-id="57608-389">JE-100</span></span></th>
<th><span data-ttu-id="57608-390">JE-110</span><span class="sxs-lookup"><span data-stu-id="57608-390">JE-110</span></span></th>
<th><span data-ttu-id="57608-391">JE-120</span><span class="sxs-lookup"><span data-stu-id="57608-391">JE-120</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="57608-392">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="57608-392">Dr (Cr)</span></span></th>
<th><span data-ttu-id="57608-393">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="57608-393">Dr (Cr)</span></span></th>
<th><span data-ttu-id="57608-394">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="57608-394">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="57608-395">1</span><span class="sxs-lookup"><span data-stu-id="57608-395">1</span></span></td>
<td><span data-ttu-id="57608-396">Dépense de bail</span><span class="sxs-lookup"><span data-stu-id="57608-396">Lease expense</span></span></td>
<td><span data-ttu-id="57608-397">1,000.00</span><span class="sxs-lookup"><span data-stu-id="57608-397">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="57608-398">1,000.00</span><span class="sxs-lookup"><span data-stu-id="57608-398">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57608-399">2</span><span class="sxs-lookup"><span data-stu-id="57608-399">2</span></span></td>
<td><span data-ttu-id="57608-400">Frais bancaires</span><span class="sxs-lookup"><span data-stu-id="57608-400">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="57608-401">3.00</span><span class="sxs-lookup"><span data-stu-id="57608-401">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="57608-402">3.00</span><span class="sxs-lookup"><span data-stu-id="57608-402">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57608-403">3</span><span class="sxs-lookup"><span data-stu-id="57608-403">3</span></span></td>
<td><span data-ttu-id="57608-404">Dépenses de TVA</span><span class="sxs-lookup"><span data-stu-id="57608-404">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="57608-405">5.00</span><span class="sxs-lookup"><span data-stu-id="57608-405">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="57608-406">5.00</span><span class="sxs-lookup"><span data-stu-id="57608-406">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57608-407">4</span><span class="sxs-lookup"><span data-stu-id="57608-407">4</span></span></td>
<td><span data-ttu-id="57608-408">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="57608-408">Clearing account</span></span></td>
<td><span data-ttu-id="57608-409">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="57608-409">-1,000.00</span></span></td>
<td><span data-ttu-id="57608-410">1,000.00</span><span class="sxs-lookup"><span data-stu-id="57608-410">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="57608-411">0,00</span><span class="sxs-lookup"><span data-stu-id="57608-411">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57608-412">5</span><span class="sxs-lookup"><span data-stu-id="57608-412">5</span></span></td>
<td><span data-ttu-id="57608-413">Module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="57608-413">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="57608-414">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="57608-414">-1,008.00</span></span></td>
<td><span data-ttu-id="57608-415">1,008.00</span><span class="sxs-lookup"><span data-stu-id="57608-415">1,008.00</span></span></td>
<td><span data-ttu-id="57608-416">0,00</span><span class="sxs-lookup"><span data-stu-id="57608-416">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57608-417">6</span><span class="sxs-lookup"><span data-stu-id="57608-417">6</span></span></td>
<td><span data-ttu-id="57608-418">Droit d’utilisation de l’actif</span><span class="sxs-lookup"><span data-stu-id="57608-418">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="57608-419">0,00</span><span class="sxs-lookup"><span data-stu-id="57608-419">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57608-420">7</span><span class="sxs-lookup"><span data-stu-id="57608-420">7</span></span></td>
<td><span data-ttu-id="57608-421">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="57608-421">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="57608-422">0,00</span><span class="sxs-lookup"><span data-stu-id="57608-422">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57608-423">8</span><span class="sxs-lookup"><span data-stu-id="57608-423">8</span></span></td>
<td><span data-ttu-id="57608-424">Dépenses d’intérêts</span><span class="sxs-lookup"><span data-stu-id="57608-424">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="57608-425">0,00</span><span class="sxs-lookup"><span data-stu-id="57608-425">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57608-426">9</span><span class="sxs-lookup"><span data-stu-id="57608-426">9</span></span></td>
<td><span data-ttu-id="57608-427">Monétaire</span><span class="sxs-lookup"><span data-stu-id="57608-427">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="57608-428">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="57608-428">-1,008.00</span></span></td>
<td><span data-ttu-id="57608-429">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="57608-429">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57608-430">10</span><span class="sxs-lookup"><span data-stu-id="57608-430">10</span></span></td>
<td><span data-ttu-id="57608-431">Dépenses d’amortissement</span><span class="sxs-lookup"><span data-stu-id="57608-431">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="57608-432">0,00</span><span class="sxs-lookup"><span data-stu-id="57608-432">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="57608-433">11</span><span class="sxs-lookup"><span data-stu-id="57608-433">11</span></span></td>
<td><span data-ttu-id="57608-434">Amortissement cumulé</span><span class="sxs-lookup"><span data-stu-id="57608-434">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="57608-435">0,00</span><span class="sxs-lookup"><span data-stu-id="57608-435">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="57608-436">Si vous souhaitez utiliser les chiffres IFRS 16 pour exécuter la même balance comptable, les écritures comptables statutaires doivent être contrepassées et les écritures comptables IFRS 16 doivent être enregistrées.</span><span class="sxs-lookup"><span data-stu-id="57608-436">If you want to use the IFRS 16 figures to run the same trial balance, the statutory accounting journal entries must be reversed, and the IFRS 16 journal entries must be posted.</span></span> <span data-ttu-id="57608-437">Pour contrepasser les écritures statutaires, cet exemple inclut un registre de contrepassation statutaire qui a la même configuration que le registre statutaire mais un profil de validation opposé.</span><span class="sxs-lookup"><span data-stu-id="57608-437">To reverse the statutory journal entries, this example includes a statutory reversal book that has the same setup as the statutory book but an opposite posting profile.</span></span> <span data-ttu-id="57608-438">Par exemple, le registre statutaire *a débité* un compte de charges de location, mais le registre de contrepassation va *créditer* ce compte.</span><span class="sxs-lookup"><span data-stu-id="57608-438">For example, the statutory book *debited* a lease expense account, but the reversal book will *credit* this account.</span></span> <span data-ttu-id="57608-439">Ces relations sont facilement définies dans les comptes de comptabilisation de la location d’actifs sur la page **Paramètres de location d’actifs** (**Location d’actifs \> Configurer \> Paramètres de location d’actifs**).</span><span class="sxs-lookup"><span data-stu-id="57608-439">These relationships are easily defined in the Asset leasing posting accounts on the **Asset leasing parameters** page (**Asset leasing \> Setup \> Asset leasing parameters**).</span></span>

<span data-ttu-id="57608-440">Lorsque le même processus que celui utilisé pour le registre statutaire est utilisé pour le registre de contrepassation, l’écriture de journal suivante est produite.</span><span class="sxs-lookup"><span data-stu-id="57608-440">When the same process that was used for the statutory book is used for the reversal book, the following journal entry is produced.</span></span> <span data-ttu-id="57608-441">La différence est que le registre de contrepassation comptabilise les écritures de contrepassation du registre statutaire.</span><span class="sxs-lookup"><span data-stu-id="57608-441">The difference is that the reversal book books the reversing entries from the statutory book.</span></span> <span data-ttu-id="57608-442">Les écritures de contrepassation sont également apportées à la couche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="57608-442">The reversing entries are also made to the custom layer.</span></span> <span data-ttu-id="57608-443">Lorsqu’une balance comptable est exécutée au niveau de la couche actuelle, les écritures de journal de contrepassation ne sont pas incluses.</span><span class="sxs-lookup"><span data-stu-id="57608-443">When a trial balance is run at the current layer, the reversing journal entries aren't included.</span></span>

### <a name="lease-payment--1312020--je-130"></a><span data-ttu-id="57608-444">Paiement de location – 31/01/2020 – JE 130</span><span class="sxs-lookup"><span data-stu-id="57608-444">Lease payment – 1/31/2020 – JE 130</span></span>

| <span data-ttu-id="57608-445">Type de compte</span><span class="sxs-lookup"><span data-stu-id="57608-445">Account type</span></span> | <span data-ttu-id="57608-446">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="57608-446">Account number</span></span> | <span data-ttu-id="57608-447">Couche</span><span class="sxs-lookup"><span data-stu-id="57608-447">Layer</span></span>  | <span data-ttu-id="57608-448">Description du compte</span><span class="sxs-lookup"><span data-stu-id="57608-448">Account description</span></span> | <span data-ttu-id="57608-449">Débit</span><span class="sxs-lookup"><span data-stu-id="57608-449">Debit</span></span>    | <span data-ttu-id="57608-450">Crédit</span><span class="sxs-lookup"><span data-stu-id="57608-450">Credit</span></span>   |
|--------------|----------------|--------|---------------------|----------|----------|
| <span data-ttu-id="57608-451">Registre</span><span class="sxs-lookup"><span data-stu-id="57608-451">Ledger</span></span>       | <span data-ttu-id="57608-452">4</span><span class="sxs-lookup"><span data-stu-id="57608-452">4</span></span>              | <span data-ttu-id="57608-453">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="57608-453">Custom</span></span> | <span data-ttu-id="57608-454">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="57608-454">Clearing account</span></span>    | <span data-ttu-id="57608-455">1,000.00</span><span class="sxs-lookup"><span data-stu-id="57608-455">1,000.00</span></span> |          |
| <span data-ttu-id="57608-456">Registre</span><span class="sxs-lookup"><span data-stu-id="57608-456">Ledger</span></span>       | <span data-ttu-id="57608-457">1</span><span class="sxs-lookup"><span data-stu-id="57608-457">1</span></span>              | <span data-ttu-id="57608-458">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="57608-458">Custom</span></span> | <span data-ttu-id="57608-459">Dépense de bail</span><span class="sxs-lookup"><span data-stu-id="57608-459">Lease expense</span></span>       |          | <span data-ttu-id="57608-460">1,000.00</span><span class="sxs-lookup"><span data-stu-id="57608-460">1,000.00</span></span> |

<span data-ttu-id="57608-461">Maintenant que vous avez éliminé les écritures de journal statutaires, vous allez enregistrer toutes les écritures de journal requises par IFRS 16 dans le livre IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="57608-461">Now that you've eliminated the statutory journal entries, you will book all the journal entries that IFRS 16 requires in the IFRS 16 book.</span></span> <span data-ttu-id="57608-462">Ces écritures comprennent la reconnaissance initiale du droit d’utilisation de l’actif et du passif, ainsi que l’enregistrement des intérêts et des amortissements.</span><span class="sxs-lookup"><span data-stu-id="57608-462">These entries include the initial recognition of the ROU asset and the liability, and the record of interest and depreciation.</span></span>

### <a name="initial-recognition--112020--je-140"></a><span data-ttu-id="57608-463">Reconnaissance initiale – 1/1/2020 – JE 140</span><span class="sxs-lookup"><span data-stu-id="57608-463">Initial recognition – 1/1/2020 – JE 140</span></span>

| <span data-ttu-id="57608-464">Type de compte</span><span class="sxs-lookup"><span data-stu-id="57608-464">Account type</span></span> | <span data-ttu-id="57608-465">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="57608-465">Account number</span></span> | <span data-ttu-id="57608-466">Couche</span><span class="sxs-lookup"><span data-stu-id="57608-466">Layer</span></span>  | <span data-ttu-id="57608-467">Description du compte</span><span class="sxs-lookup"><span data-stu-id="57608-467">Account description</span></span>      | <span data-ttu-id="57608-468">Débit</span><span class="sxs-lookup"><span data-stu-id="57608-468">Debit</span></span>     | <span data-ttu-id="57608-469">Crédit</span><span class="sxs-lookup"><span data-stu-id="57608-469">Credit</span></span>    |
|--------------|----------------|--------|--------------------------|-----------|-----------|
| <span data-ttu-id="57608-470">Registre</span><span class="sxs-lookup"><span data-stu-id="57608-470">Ledger</span></span>       | <span data-ttu-id="57608-471">6</span><span class="sxs-lookup"><span data-stu-id="57608-471">6</span></span>              | <span data-ttu-id="57608-472">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="57608-472">Custom</span></span> | <span data-ttu-id="57608-473">Droit d’utilisation de l’actif</span><span class="sxs-lookup"><span data-stu-id="57608-473">ROU Asset</span></span>                | <span data-ttu-id="57608-474">22,793.90</span><span class="sxs-lookup"><span data-stu-id="57608-474">22,793.90</span></span> |           |
| <span data-ttu-id="57608-475">Registre</span><span class="sxs-lookup"><span data-stu-id="57608-475">Ledger</span></span>       | <span data-ttu-id="57608-476">7</span><span class="sxs-lookup"><span data-stu-id="57608-476">7</span></span>              | <span data-ttu-id="57608-477">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="57608-477">Custom</span></span> | <span data-ttu-id="57608-478">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="57608-478">Finance lease obligation</span></span> |           | <span data-ttu-id="57608-479">22,793.90</span><span class="sxs-lookup"><span data-stu-id="57608-479">22,793.90</span></span> |

<span data-ttu-id="57608-480">Le paiement de location est comptabilisé comme les autres paiements de location.</span><span class="sxs-lookup"><span data-stu-id="57608-480">The lease payment is posted like the other lease payments.</span></span> <span data-ttu-id="57608-481">La raison de l’utilisation du compte de compensation est de s’assurer que les espèces ne sont créditées qu’une seule fois.</span><span class="sxs-lookup"><span data-stu-id="57608-481">The reason for using the clearing account is to ensure that cash is credited only one time.</span></span>

### <a name="lease-payment--1312020--je-150"></a><span data-ttu-id="57608-482">Paiement de location – 31/01/2020 – JE 150</span><span class="sxs-lookup"><span data-stu-id="57608-482">Lease payment – 1/31/2020 – JE 150</span></span>

| <span data-ttu-id="57608-483">Type de compte</span><span class="sxs-lookup"><span data-stu-id="57608-483">Account type</span></span> | <span data-ttu-id="57608-484">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="57608-484">Account number</span></span> | <span data-ttu-id="57608-485">Couche</span><span class="sxs-lookup"><span data-stu-id="57608-485">Layer</span></span>  | <span data-ttu-id="57608-486">Description du compte</span><span class="sxs-lookup"><span data-stu-id="57608-486">Account description</span></span>      | <span data-ttu-id="57608-487">Débit</span><span class="sxs-lookup"><span data-stu-id="57608-487">Debit</span></span>    | <span data-ttu-id="57608-488">Crédit</span><span class="sxs-lookup"><span data-stu-id="57608-488">Credit</span></span>   |
|--------------|----------------|--------|--------------------------|----------|----------|
| <span data-ttu-id="57608-489">Registre</span><span class="sxs-lookup"><span data-stu-id="57608-489">Ledger</span></span>       | <span data-ttu-id="57608-490">7</span><span class="sxs-lookup"><span data-stu-id="57608-490">7</span></span>              | <span data-ttu-id="57608-491">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="57608-491">Custom</span></span> | <span data-ttu-id="57608-492">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="57608-492">Finance lease obligation</span></span> | <span data-ttu-id="57608-493">1,000.00</span><span class="sxs-lookup"><span data-stu-id="57608-493">1,000.00</span></span> |          |
| <span data-ttu-id="57608-494">Registre</span><span class="sxs-lookup"><span data-stu-id="57608-494">Ledger</span></span>       | <span data-ttu-id="57608-495">4</span><span class="sxs-lookup"><span data-stu-id="57608-495">4</span></span>              | <span data-ttu-id="57608-496">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="57608-496">Custom</span></span> | <span data-ttu-id="57608-497">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="57608-497">Clearing account</span></span>         |          | <span data-ttu-id="57608-498">1,000.00</span><span class="sxs-lookup"><span data-stu-id="57608-498">1,000.00</span></span> |

<span data-ttu-id="57608-499">L’écriture de journal des charges d’intérêts est générée à partir du calendrier d’amortissement du passif.</span><span class="sxs-lookup"><span data-stu-id="57608-499">The interest expense journal entry is generated from the liability amortization schedule.</span></span>

### <a name="interest-expense--1312020--je-160"></a><span data-ttu-id="57608-500">Dépenses d’intérêts – 31/1/2020 – JE 160</span><span class="sxs-lookup"><span data-stu-id="57608-500">Interest expense – 1/31/2020 – JE 160</span></span>

| <span data-ttu-id="57608-501">Type de compte</span><span class="sxs-lookup"><span data-stu-id="57608-501">Account type</span></span> | <span data-ttu-id="57608-502">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="57608-502">Account number</span></span> | <span data-ttu-id="57608-503">Couche</span><span class="sxs-lookup"><span data-stu-id="57608-503">Layer</span></span>  | <span data-ttu-id="57608-504">Description du compte</span><span class="sxs-lookup"><span data-stu-id="57608-504">Account description</span></span>      | <span data-ttu-id="57608-505">Débit</span><span class="sxs-lookup"><span data-stu-id="57608-505">Debit</span></span> | <span data-ttu-id="57608-506">Crédit</span><span class="sxs-lookup"><span data-stu-id="57608-506">Credit</span></span> |
|--------------|----------------|--------|--------------------------|-------|--------|
| <span data-ttu-id="57608-507">Registre</span><span class="sxs-lookup"><span data-stu-id="57608-507">Ledger</span></span>       | <span data-ttu-id="57608-508">8</span><span class="sxs-lookup"><span data-stu-id="57608-508">8</span></span>              | <span data-ttu-id="57608-509">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="57608-509">Custom</span></span> | <span data-ttu-id="57608-510">Dépenses d’intérêts</span><span class="sxs-lookup"><span data-stu-id="57608-510">Interest expense</span></span>         | <span data-ttu-id="57608-511">94.97</span><span class="sxs-lookup"><span data-stu-id="57608-511">94.97</span></span> |        |
| <span data-ttu-id="57608-512">Registre</span><span class="sxs-lookup"><span data-stu-id="57608-512">Ledger</span></span>       | <span data-ttu-id="57608-513">7</span><span class="sxs-lookup"><span data-stu-id="57608-513">7</span></span>              | <span data-ttu-id="57608-514">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="57608-514">Custom</span></span> | <span data-ttu-id="57608-515">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="57608-515">Finance lease obligation</span></span> |       | <span data-ttu-id="57608-516">94.97</span><span class="sxs-lookup"><span data-stu-id="57608-516">94.97</span></span>  |

<span data-ttu-id="57608-517">L’écriture de journal de dépense d’amortissement est générée à partir du programme d’amortissement du passif.</span><span class="sxs-lookup"><span data-stu-id="57608-517">The depreciation expense journal entry is generated from the asset depreciation schedule.</span></span>

### <a name="depreciation-expense--1312020--je-170"></a><span data-ttu-id="57608-518">Dépenses d’amortissement – 1/31/2020 – JE 170</span><span class="sxs-lookup"><span data-stu-id="57608-518">Depreciation expense – 1/31/2020 – JE 170</span></span>

| <span data-ttu-id="57608-519">Type de compte</span><span class="sxs-lookup"><span data-stu-id="57608-519">Account type</span></span> | <span data-ttu-id="57608-520">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="57608-520">Account number</span></span> | <span data-ttu-id="57608-521">Couche</span><span class="sxs-lookup"><span data-stu-id="57608-521">Layer</span></span>  | <span data-ttu-id="57608-522">Description du compte</span><span class="sxs-lookup"><span data-stu-id="57608-522">Account description</span></span>      | <span data-ttu-id="57608-523">Débit</span><span class="sxs-lookup"><span data-stu-id="57608-523">Debit</span></span>  | <span data-ttu-id="57608-524">Crédit</span><span class="sxs-lookup"><span data-stu-id="57608-524">Credit</span></span> |
|--------------|----------------|--------|--------------------------|--------|--------|
| <span data-ttu-id="57608-525">Registre</span><span class="sxs-lookup"><span data-stu-id="57608-525">Ledger</span></span>       | <span data-ttu-id="57608-526">10</span><span class="sxs-lookup"><span data-stu-id="57608-526">10</span></span>             | <span data-ttu-id="57608-527">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="57608-527">Custom</span></span> | <span data-ttu-id="57608-528">Dépenses d’amortissement</span><span class="sxs-lookup"><span data-stu-id="57608-528">Depreciation expense</span></span>     | <span data-ttu-id="57608-529">949.75</span><span class="sxs-lookup"><span data-stu-id="57608-529">949.75</span></span> |        |
| <span data-ttu-id="57608-530">Registre</span><span class="sxs-lookup"><span data-stu-id="57608-530">Ledger</span></span>       | <span data-ttu-id="57608-531">11</span><span class="sxs-lookup"><span data-stu-id="57608-531">11</span></span>             | <span data-ttu-id="57608-532">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="57608-532">Custom</span></span> | <span data-ttu-id="57608-533">Amortissement cumulé</span><span class="sxs-lookup"><span data-stu-id="57608-533">Accumulated depreciation</span></span> |        | <span data-ttu-id="57608-534">949.75</span><span class="sxs-lookup"><span data-stu-id="57608-534">949.75</span></span> |

<span data-ttu-id="57608-535">Une fois toutes ces entrées de journal créées et validées, vous verrez les valeurs de « couche personnalisée 1 » suivantes.</span><span class="sxs-lookup"><span data-stu-id="57608-535">After all these journal entries are created and posted, you will see the following "custom layer 1" values.</span></span> <span data-ttu-id="57608-536">Notez que la dernière colonne comprend les frais bancaires, les frais de taxe sur la valeur ajoutée (TVA) et la réduction des liquidités de la couche précédente, mais elle n’inclut pas les écritures de reporting statutaires.</span><span class="sxs-lookup"><span data-stu-id="57608-536">Note that the last column includes the bank fee, the value-added tax (VAT) expense, and the reduction of cash from the previous layer, but it doesn't include the statutory reporting journal entries.</span></span> <span data-ttu-id="57608-537">Par conséquent, vous obtenez de véritables capacités de double reporting.</span><span class="sxs-lookup"><span data-stu-id="57608-537">Therefore, you achieve true dual-reporting capabilities.</span></span> <span data-ttu-id="57608-538">À ce stade, l’entreprise doit simplement exécuter sa balance comptable et combiner la couche actuelle et la couche personnalisée pour créer une balance comptable IFRS.</span><span class="sxs-lookup"><span data-stu-id="57608-538">At this point, the company just has to run its trial balance, and combine the current layer and the custom layer to create an IFRS trial balance.</span></span>

| <span data-ttu-id="57608-539">N° de compte</span><span class="sxs-lookup"><span data-stu-id="57608-539">Account No</span></span> | <span data-ttu-id="57608-540">Description</span><span class="sxs-lookup"><span data-stu-id="57608-540">Description</span></span>              | <span data-ttu-id="57608-541">Registre statutaire\-Couche actuelle\-JE\-100\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="57608-541">Statutory Book\-Current Layer\-JE\-100\-Dr \(Cr\)</span></span> | <span data-ttu-id="57608-542">Registre statutaire\-Couche actuelle\-JE\-110\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="57608-542">Statutory Book\-Current Layer\-JE\-110\-Dr \(Cr\)</span></span> | <span data-ttu-id="57608-543">Registre statutaire\-Couche actuelle\-JE\-120\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="57608-543">Statutory Book\-Current Layer\-JE\-120\-Dr \(Cr\)</span></span> | <span data-ttu-id="57608-544">Couche actuelle \- Totaux</span><span class="sxs-lookup"><span data-stu-id="57608-544">Current Layer \- Totals</span></span> | - | <span data-ttu-id="57608-545">Registre de contrepassation\-Couche personnalisée\-JE\-130\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="57608-545">Reversal Book\-Custom layer\-JE\-130\-Dr \(Cr\)</span></span> | <span data-ttu-id="57608-546">Registre IFRS 16\-Couche personnalisée\-JE\-140\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="57608-546">IFRS 16 Book\-Custom layer\-JE\-140\-Dr \(Cr\)</span></span> | <span data-ttu-id="57608-547">Registre IFRS 16\-Couche personnalisée\-JE\-150\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="57608-547">IFRS 16 Book\-Custom layer\-JE\-150\-Dr \(Cr\)</span></span> | <span data-ttu-id="57608-548">Registre IFRS 16\-Couche personnalisée\-JE\-160\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="57608-548">IFRS 16 Book\-Custom layer\-JE\-160\-Dr \(Cr\)</span></span> | <span data-ttu-id="57608-549">Registre IFRS 16\-Couche personnalisée\-JE\-170\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="57608-549">IFRS 16 Book\-Custom layer\-JE\-170\-Dr \(Cr\)</span></span> | <span data-ttu-id="57608-550">Couche personnalisée \+ Couche actuelle \- Totaux</span><span class="sxs-lookup"><span data-stu-id="57608-550">Custom Layer \+ Current Layer \- Totals</span></span> |
|------------|--------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|-------------------------|---|-------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------|
| <span data-ttu-id="57608-551">1</span><span class="sxs-lookup"><span data-stu-id="57608-551">1</span></span>          | <span data-ttu-id="57608-552">Dépense de bail</span><span class="sxs-lookup"><span data-stu-id="57608-552">Lease expense</span></span>            | <span data-ttu-id="57608-553">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="57608-553">1,000\.00</span></span>                                         |                                                   |                                                   | <span data-ttu-id="57608-554">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="57608-554">1,000\.00</span></span>               |   | <span data-ttu-id="57608-555">\-1 000</span><span class="sxs-lookup"><span data-stu-id="57608-555">\-1,000</span></span>                                         |                                                |                                                |                                                |                                                | <span data-ttu-id="57608-556">0\.00</span><span class="sxs-lookup"><span data-stu-id="57608-556">0\.00</span></span>                                   |
| <span data-ttu-id="57608-557">2</span><span class="sxs-lookup"><span data-stu-id="57608-557">2</span></span>          | <span data-ttu-id="57608-558">Frais bancaires</span><span class="sxs-lookup"><span data-stu-id="57608-558">Bank fee</span></span>                 |                                                   | <span data-ttu-id="57608-559">3\.00</span><span class="sxs-lookup"><span data-stu-id="57608-559">3\.00</span></span>                                             |                                                   | <span data-ttu-id="57608-560">3\.00</span><span class="sxs-lookup"><span data-stu-id="57608-560">3\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="57608-561">3\.00</span><span class="sxs-lookup"><span data-stu-id="57608-561">3\.00</span></span>                                   |
| <span data-ttu-id="57608-562">3</span><span class="sxs-lookup"><span data-stu-id="57608-562">3</span></span>          | <span data-ttu-id="57608-563">Dépenses de TVA</span><span class="sxs-lookup"><span data-stu-id="57608-563">VAT expense</span></span>              |                                                   | <span data-ttu-id="57608-564">5\.00</span><span class="sxs-lookup"><span data-stu-id="57608-564">5\.00</span></span>                                             |                                                   | <span data-ttu-id="57608-565">5\.00</span><span class="sxs-lookup"><span data-stu-id="57608-565">5\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="57608-566">5\.00</span><span class="sxs-lookup"><span data-stu-id="57608-566">5\.00</span></span>                                   |
| <span data-ttu-id="57608-567">4</span><span class="sxs-lookup"><span data-stu-id="57608-567">4</span></span>          | <span data-ttu-id="57608-568">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="57608-568">Clearing account</span></span>         | <span data-ttu-id="57608-569">\-1 000\.00</span><span class="sxs-lookup"><span data-stu-id="57608-569">\-1,000\.00</span></span>                                       | <span data-ttu-id="57608-570">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="57608-570">1,000\.00</span></span>                                         |                                                   | <span data-ttu-id="57608-571">0\.00</span><span class="sxs-lookup"><span data-stu-id="57608-571">0\.00</span></span>                   |   | <span data-ttu-id="57608-572">1 000</span><span class="sxs-lookup"><span data-stu-id="57608-572">1,000</span></span>                                           |                                                | <span data-ttu-id="57608-573">\-1 000</span><span class="sxs-lookup"><span data-stu-id="57608-573">\-1,000</span></span>                                        |                                                |                                                | <span data-ttu-id="57608-574">0\.00</span><span class="sxs-lookup"><span data-stu-id="57608-574">0\.00</span></span>                                   |
| <span data-ttu-id="57608-575">5</span><span class="sxs-lookup"><span data-stu-id="57608-575">5</span></span>          | <span data-ttu-id="57608-576">Module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="57608-576">Accounts payable</span></span>         |                                                   | <span data-ttu-id="57608-577">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="57608-577">\-1,008\.00</span></span>                                       | <span data-ttu-id="57608-578">1,008\.00</span><span class="sxs-lookup"><span data-stu-id="57608-578">1,008\.00</span></span>                                         | <span data-ttu-id="57608-579">0\.00</span><span class="sxs-lookup"><span data-stu-id="57608-579">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="57608-580">0\.00</span><span class="sxs-lookup"><span data-stu-id="57608-580">0\.00</span></span>                                   |
| <span data-ttu-id="57608-581">6</span><span class="sxs-lookup"><span data-stu-id="57608-581">6</span></span>          | <span data-ttu-id="57608-582">Droit d’utilisation de l’actif</span><span class="sxs-lookup"><span data-stu-id="57608-582">ROU asset</span></span>                |                                                   |                                                   |                                                   | <span data-ttu-id="57608-583">0\.00</span><span class="sxs-lookup"><span data-stu-id="57608-583">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="57608-584">22,794</span><span class="sxs-lookup"><span data-stu-id="57608-584">22,794</span></span>                                         |                                                |                                                |                                                | <span data-ttu-id="57608-585">22,793\.90</span><span class="sxs-lookup"><span data-stu-id="57608-585">22,793\.90</span></span>                              |
| <span data-ttu-id="57608-586">7</span><span class="sxs-lookup"><span data-stu-id="57608-586">7</span></span>          | <span data-ttu-id="57608-587">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="57608-587">Finance lease obligation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="57608-588">0\.00</span><span class="sxs-lookup"><span data-stu-id="57608-588">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="57608-589">\-22 794</span><span class="sxs-lookup"><span data-stu-id="57608-589">\-22,794</span></span>                                       | <span data-ttu-id="57608-590">1 000</span><span class="sxs-lookup"><span data-stu-id="57608-590">1,000</span></span>                                          | <span data-ttu-id="57608-591">\-94\.97</span><span class="sxs-lookup"><span data-stu-id="57608-591">\-94\.97</span></span>                                       |                                                | <span data-ttu-id="57608-592">\-21 888\.87</span><span class="sxs-lookup"><span data-stu-id="57608-592">\-21,888\.87</span></span>                            |
| <span data-ttu-id="57608-593">8</span><span class="sxs-lookup"><span data-stu-id="57608-593">8</span></span>          | <span data-ttu-id="57608-594">Dépenses d’intérêts</span><span class="sxs-lookup"><span data-stu-id="57608-594">Interest expense</span></span>         |                                                   |                                                   |                                                   | <span data-ttu-id="57608-595">0\.00</span><span class="sxs-lookup"><span data-stu-id="57608-595">0\.00</span></span>                   |   |                                                 |                                                |                                                | <span data-ttu-id="57608-596">94\.97</span><span class="sxs-lookup"><span data-stu-id="57608-596">94\.97</span></span>                                         |                                                | <span data-ttu-id="57608-597">94\.97</span><span class="sxs-lookup"><span data-stu-id="57608-597">94\.97</span></span>                                  |
| <span data-ttu-id="57608-598">9</span><span class="sxs-lookup"><span data-stu-id="57608-598">9</span></span>          | <span data-ttu-id="57608-599">Monétaire</span><span class="sxs-lookup"><span data-stu-id="57608-599">Cash</span></span>                     |                                                   |                                                   | <span data-ttu-id="57608-600">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="57608-600">\-1,008\.00</span></span>                                       | <span data-ttu-id="57608-601">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="57608-601">\-1,008\.00</span></span>             |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="57608-602">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="57608-602">\-1,008\.00</span></span>                             |
| <span data-ttu-id="57608-603">10</span><span class="sxs-lookup"><span data-stu-id="57608-603">10</span></span>         | <span data-ttu-id="57608-604">Dépenses d’amortissement</span><span class="sxs-lookup"><span data-stu-id="57608-604">Depreciation expense</span></span>     |                                                   |                                                   |                                                   | <span data-ttu-id="57608-605">0\.00</span><span class="sxs-lookup"><span data-stu-id="57608-605">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="57608-606">949\.75</span><span class="sxs-lookup"><span data-stu-id="57608-606">949\.75</span></span>                                        | <span data-ttu-id="57608-607">949\.75</span><span class="sxs-lookup"><span data-stu-id="57608-607">949\.75</span></span>                                 |
| <span data-ttu-id="57608-608">11</span><span class="sxs-lookup"><span data-stu-id="57608-608">11</span></span>         | <span data-ttu-id="57608-609">Amortissement cumulé</span><span class="sxs-lookup"><span data-stu-id="57608-609">Accumulated depreciation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="57608-610">0\.00</span><span class="sxs-lookup"><span data-stu-id="57608-610">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="57608-611">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="57608-611">\-949\.75</span></span>                                      | <span data-ttu-id="57608-612">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="57608-612">\-949\.75</span></span>                               |




[!INCLUDE[footer-include](../../includes/footer-banner.md)]