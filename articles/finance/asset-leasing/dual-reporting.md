---
title: Double déclaration
description: Cette rubrique vous guide à travers un exemple qui montre comment vous pouvez remplir les exigences à la fois pour le reporting des normes internationales d’information financière (IFRS) et le reporting statutaire dans le bail d’actifs.
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
ms.openlocfilehash: a7d9b3ea3d4f1d48b8a7326bd5a01d3119310c62
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003179"
---
# <a name="dual-reporting"></a><span data-ttu-id="7580b-103">Double déclaration</span><span class="sxs-lookup"><span data-stu-id="7580b-103">Dual reporting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7580b-104">Cette rubrique vous guide à travers un exemple qui montre comment vous pouvez remplir les exigences à la fois pour le reporting des normes internationales d’information financière (IFRS) et le reporting statutaire dans le bail d’actifs.</span><span class="sxs-lookup"><span data-stu-id="7580b-104">This topic guides you through an example that shows how you can fulfill the requirements for both International Financial Reporting Standard (IFRS) reporting and statutory reporting in Asset leasing.</span></span> <span data-ttu-id="7580b-105">Il est nécessaire d’être familiarisé avec les couches de validation dans Microsoft Dynamics 365 Finance, ce qui rendra l’exemple plus facile à comprendre.</span><span class="sxs-lookup"><span data-stu-id="7580b-105">Familiarity with posting layers in Microsoft Dynamics 365 Finance is required and will make the example easier to understand.</span></span>

## <a name="example"></a><span data-ttu-id="7580b-106">Exemple</span><span class="sxs-lookup"><span data-stu-id="7580b-106">Example</span></span>

<span data-ttu-id="7580b-107">L’exemple suivant rend compte d’un contrat de location selon le reporting statutaire italien en utilisant à la fois la méthode de la comptabilité de caisse et les méthodes de reporting IFRS.</span><span class="sxs-lookup"><span data-stu-id="7580b-107">The following example accounts for a lease under Italian statutory reporting by using both the cash-basis method and IFRS reporting methods.</span></span> <span data-ttu-id="7580b-108">L’entreprise doit établir trois registres pour tenir compte à la fois des exigences légales italiennes et des exigences d’IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="7580b-108">The company must establish three books to account for both the Italian statutory requirements and the IFRS 16 requirements.</span></span> <span data-ttu-id="7580b-109">Un registre est requis pour IFRS 16, un registre est requis pour les exigences statutaires et un registre est requis pour annuler automatiquement les écritures statutaires.</span><span class="sxs-lookup"><span data-stu-id="7580b-109">One book is required for IFRS 16, one book is required for statutory requirements, and one book is required to automatically reverse statutory postings.</span></span> <span data-ttu-id="7580b-110">Les registres sont configurés comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="7580b-110">The books are set up as shown in the following tables.</span></span>

<span data-ttu-id="7580b-111">**Registre IFRS 16**</span><span class="sxs-lookup"><span data-stu-id="7580b-111">**IFRS 16 book**</span></span>

<span data-ttu-id="7580b-112">Le registre IFRS 16 est mis en place de manière à être conforme à la norme comptable IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="7580b-112">The IFRS 16 book is set up so that it complies with the IFRS 16 accounting standard.</span></span> <span data-ttu-id="7580b-113">Toutes les entrées publiées dans ce livre seront publiées sur une couche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="7580b-113">All entries that are posted in this book will be posted to a custom layer.</span></span>

| <span data-ttu-id="7580b-114">Nom</span><span class="sxs-lookup"><span data-stu-id="7580b-114">Name</span></span>                                    | <span data-ttu-id="7580b-115">Description</span><span class="sxs-lookup"><span data-stu-id="7580b-115">Description</span></span>    |
|-----------------------------------------|----------------|
| <span data-ttu-id="7580b-116">Type de registre</span><span class="sxs-lookup"><span data-stu-id="7580b-116">Book type</span></span>                               | <span data-ttu-id="7580b-117">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="7580b-117">IFRS 16</span></span>        |
| <span data-ttu-id="7580b-118">Description du registre</span><span class="sxs-lookup"><span data-stu-id="7580b-118">Book description</span></span>                        | <span data-ttu-id="7580b-119">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="7580b-119">IFRS 16</span></span>        |
| <span data-ttu-id="7580b-120">Couche de comptabilisation</span><span class="sxs-lookup"><span data-stu-id="7580b-120">Posting Layer</span></span>                           | <span data-ttu-id="7580b-121">Couche personnalisée 1</span><span class="sxs-lookup"><span data-stu-id="7580b-121">Custom layer 1</span></span> |
| <span data-ttu-id="7580b-122">Type de bail</span><span class="sxs-lookup"><span data-stu-id="7580b-122">Lease Type</span></span>                              | <span data-ttu-id="7580b-123">Finances</span><span class="sxs-lookup"><span data-stu-id="7580b-123">Finance</span></span>        |
| <span data-ttu-id="7580b-124">Structure comptable</span><span class="sxs-lookup"><span data-stu-id="7580b-124">Accounting Framework</span></span>                    | <span data-ttu-id="7580b-125">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="7580b-125">IFRS 16</span></span>        |
| <span data-ttu-id="7580b-126">Configuration Durée du bail/Durée de vie utile</span><span class="sxs-lookup"><span data-stu-id="7580b-126">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="7580b-127">0,00</span><span class="sxs-lookup"><span data-stu-id="7580b-127">0.00</span></span>           |
| <span data-ttu-id="7580b-128">Configuration Valeur actuelle/Juste valeur de l’actif</span><span class="sxs-lookup"><span data-stu-id="7580b-128">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="7580b-129">0,00</span><span class="sxs-lookup"><span data-stu-id="7580b-129">0.00</span></span>           |
| <span data-ttu-id="7580b-130">Seuil à court terme</span><span class="sxs-lookup"><span data-stu-id="7580b-130">Short-term threshold</span></span>                    | <span data-ttu-id="7580b-131">12</span><span class="sxs-lookup"><span data-stu-id="7580b-131">12</span></span>             |
| <span data-ttu-id="7580b-132">Seuil de faible valeur</span><span class="sxs-lookup"><span data-stu-id="7580b-132">Low Value Threshold</span></span>                     | <span data-ttu-id="7580b-133">5,000.00</span><span class="sxs-lookup"><span data-stu-id="7580b-133">5,000.00</span></span>       |
| <span data-ttu-id="7580b-134">Payer au fournisseur</span><span class="sxs-lookup"><span data-stu-id="7580b-134">Pay to Vendor</span></span>                           | <span data-ttu-id="7580b-135">N°</span><span class="sxs-lookup"><span data-stu-id="7580b-135">No</span></span>             |

<span data-ttu-id="7580b-136">**Registre statutaire**</span><span class="sxs-lookup"><span data-stu-id="7580b-136">**Statutory book**</span></span>

<span data-ttu-id="7580b-137">Le registre statutaire est un registre de comptabilité de caisse dans lequel la société comptabilise les frais de location comme le montant en espèces payé chaque mois pour le loyer.</span><span class="sxs-lookup"><span data-stu-id="7580b-137">The statutory book is a cash-basis book where the company will account for the lease expense as the amount of cash that is paid each month for rent.</span></span> <span data-ttu-id="7580b-138">Ce registre ne produira pas de droit d’utilisation de l’actif (ROU) ni de passif locatif.</span><span class="sxs-lookup"><span data-stu-id="7580b-138">This book won't produce a right-of-use (ROU) asset or lease liability.</span></span>

| <span data-ttu-id="7580b-139">Nom</span><span class="sxs-lookup"><span data-stu-id="7580b-139">Name</span></span>                                    | <span data-ttu-id="7580b-140">Description</span><span class="sxs-lookup"><span data-stu-id="7580b-140">Description</span></span> |
|-----------------------------------------|-------------|
| <span data-ttu-id="7580b-141">Type de registre</span><span class="sxs-lookup"><span data-stu-id="7580b-141">Book type</span></span>                               | <span data-ttu-id="7580b-142">Statutaire</span><span class="sxs-lookup"><span data-stu-id="7580b-142">Statutory</span></span>   |
| <span data-ttu-id="7580b-143">Description du registre</span><span class="sxs-lookup"><span data-stu-id="7580b-143">Book description</span></span>                        | <span data-ttu-id="7580b-144">GAAP local</span><span class="sxs-lookup"><span data-stu-id="7580b-144">Local GAAP</span></span>  |
| <span data-ttu-id="7580b-145">Couche de comptabilisation</span><span class="sxs-lookup"><span data-stu-id="7580b-145">Posting Layer</span></span>                           | <span data-ttu-id="7580b-146">Actuelle</span><span class="sxs-lookup"><span data-stu-id="7580b-146">Current</span></span>     |
| <span data-ttu-id="7580b-147">Type de bail</span><span class="sxs-lookup"><span data-stu-id="7580b-147">Lease Type</span></span>                              | <span data-ttu-id="7580b-148">Automatique</span><span class="sxs-lookup"><span data-stu-id="7580b-148">Automatic</span></span>   |
| <span data-ttu-id="7580b-149">Structure comptable</span><span class="sxs-lookup"><span data-stu-id="7580b-149">Accounting Framework</span></span>                    | <span data-ttu-id="7580b-150">Base de trésorerie</span><span class="sxs-lookup"><span data-stu-id="7580b-150">Cash basis</span></span>  |
| <span data-ttu-id="7580b-151">Configuration Durée du bail/Durée de vie utile</span><span class="sxs-lookup"><span data-stu-id="7580b-151">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="7580b-152">0,00</span><span class="sxs-lookup"><span data-stu-id="7580b-152">0.00</span></span>        |
| <span data-ttu-id="7580b-153">Configuration Valeur actuelle/Juste valeur de l’actif</span><span class="sxs-lookup"><span data-stu-id="7580b-153">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="7580b-154">0,00</span><span class="sxs-lookup"><span data-stu-id="7580b-154">0.00</span></span>        |
| <span data-ttu-id="7580b-155">Seuil à court terme</span><span class="sxs-lookup"><span data-stu-id="7580b-155">Short-term threshold</span></span>                    | <span data-ttu-id="7580b-156">0</span><span class="sxs-lookup"><span data-stu-id="7580b-156">0</span></span>           |
| <span data-ttu-id="7580b-157">Seuil de faible valeur</span><span class="sxs-lookup"><span data-stu-id="7580b-157">Low Value Threshold</span></span>                     | <span data-ttu-id="7580b-158">0</span><span class="sxs-lookup"><span data-stu-id="7580b-158">0</span></span>           |
| <span data-ttu-id="7580b-159">Payer au fournisseur</span><span class="sxs-lookup"><span data-stu-id="7580b-159">Pay to Vendor</span></span>                           | <span data-ttu-id="7580b-160">N°</span><span class="sxs-lookup"><span data-stu-id="7580b-160">No</span></span>          |

<span data-ttu-id="7580b-161">**Registre de contrepassation statutaire**</span><span class="sxs-lookup"><span data-stu-id="7580b-161">**Statutory reversal book**</span></span>

<span data-ttu-id="7580b-162">Le registre de contrepassation statutaire est constitué de la même manière que le registre statutaire.</span><span class="sxs-lookup"><span data-stu-id="7580b-162">The statutory reversal book is set up in the same way as the statutory book.</span></span>

| <span data-ttu-id="7580b-163">Nom</span><span class="sxs-lookup"><span data-stu-id="7580b-163">Name</span></span>                                    | <span data-ttu-id="7580b-164">Description</span><span class="sxs-lookup"><span data-stu-id="7580b-164">Description</span></span>                    |
|-----------------------------------------|--------------------------------|
| <span data-ttu-id="7580b-165">Type de registre</span><span class="sxs-lookup"><span data-stu-id="7580b-165">Book type</span></span>                               | <span data-ttu-id="7580b-166">Statutaire – contrepassation</span><span class="sxs-lookup"><span data-stu-id="7580b-166">Statutory – Reversal</span></span>           |
| <span data-ttu-id="7580b-167">Description du registre</span><span class="sxs-lookup"><span data-stu-id="7580b-167">Book description</span></span>                        | <span data-ttu-id="7580b-168">Registre pour contrepasser le registre statutaire</span><span class="sxs-lookup"><span data-stu-id="7580b-168">Book to reverse statutory book</span></span> |
| <span data-ttu-id="7580b-169">Couche de comptabilisation</span><span class="sxs-lookup"><span data-stu-id="7580b-169">Posting Layer</span></span>                           | <span data-ttu-id="7580b-170">Couche personnalisée 1</span><span class="sxs-lookup"><span data-stu-id="7580b-170">Custom layer 1</span></span>                 |
| <span data-ttu-id="7580b-171">Type de bail</span><span class="sxs-lookup"><span data-stu-id="7580b-171">Lease Type</span></span>                              | <span data-ttu-id="7580b-172">Automatique</span><span class="sxs-lookup"><span data-stu-id="7580b-172">Automatic</span></span>                      |
| <span data-ttu-id="7580b-173">Structure comptable</span><span class="sxs-lookup"><span data-stu-id="7580b-173">Accounting Framework</span></span>                    | <span data-ttu-id="7580b-174">Base de trésorerie</span><span class="sxs-lookup"><span data-stu-id="7580b-174">Cash basis</span></span>                     |
| <span data-ttu-id="7580b-175">Configuration Durée du bail/Durée de vie utile</span><span class="sxs-lookup"><span data-stu-id="7580b-175">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="7580b-176">0,00</span><span class="sxs-lookup"><span data-stu-id="7580b-176">0.00</span></span>                           |
| <span data-ttu-id="7580b-177">Configuration Valeur actuelle/Juste valeur de l’actif</span><span class="sxs-lookup"><span data-stu-id="7580b-177">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="7580b-178">0,00</span><span class="sxs-lookup"><span data-stu-id="7580b-178">0.00</span></span>                           |
| <span data-ttu-id="7580b-179">Seuil à court terme</span><span class="sxs-lookup"><span data-stu-id="7580b-179">Short-term threshold</span></span>                    | <span data-ttu-id="7580b-180">0</span><span class="sxs-lookup"><span data-stu-id="7580b-180">0</span></span>                              |
| <span data-ttu-id="7580b-181">Seuil de faible valeur</span><span class="sxs-lookup"><span data-stu-id="7580b-181">Low Value Threshold</span></span>                     | <span data-ttu-id="7580b-182">0</span><span class="sxs-lookup"><span data-stu-id="7580b-182">0</span></span>                              |
| <span data-ttu-id="7580b-183">Payer au fournisseur</span><span class="sxs-lookup"><span data-stu-id="7580b-183">Pay to Vendor</span></span>                           | <span data-ttu-id="7580b-184">N°</span><span class="sxs-lookup"><span data-stu-id="7580b-184">No</span></span>                             |

<span data-ttu-id="7580b-185">Pour cet exemple, un bail a été créé avec les paramètres suivants sur les onglets **Général** et **Lignes d’échéancier de paiement**.</span><span class="sxs-lookup"><span data-stu-id="7580b-185">For this example, a lease has been created that has the following settings on the **General** and **Payment schedule lines** tabs.</span></span>

<span data-ttu-id="7580b-186">**Onglet Général**</span><span class="sxs-lookup"><span data-stu-id="7580b-186">**General tab**</span></span>

| <span data-ttu-id="7580b-187">Champ</span><span class="sxs-lookup"><span data-stu-id="7580b-187">Field</span></span>                      | <span data-ttu-id="7580b-188">Valeur</span><span class="sxs-lookup"><span data-stu-id="7580b-188">Value</span></span>            |
|----------------------------|------------------|
| <span data-ttu-id="7580b-189">Taux d’emprunt marginal</span><span class="sxs-lookup"><span data-stu-id="7580b-189">Incremental borrowing rate</span></span> | <span data-ttu-id="7580b-190">5 %</span><span class="sxs-lookup"><span data-stu-id="7580b-190">5%</span></span>               |
| <span data-ttu-id="7580b-191">Date d’entrée en vigueur</span><span class="sxs-lookup"><span data-stu-id="7580b-191">Commencement date</span></span>          | <span data-ttu-id="7580b-192">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="7580b-192">1/1/2020</span></span>         |
| <span data-ttu-id="7580b-193">Groupe de baux</span><span class="sxs-lookup"><span data-stu-id="7580b-193">Lease group</span></span>                | <span data-ttu-id="7580b-194">Bâtiments</span><span class="sxs-lookup"><span data-stu-id="7580b-194">Buildings</span></span>        |
| <span data-ttu-id="7580b-195">Fournisseur</span><span class="sxs-lookup"><span data-stu-id="7580b-195">Vendor</span></span>                     | <span data-ttu-id="7580b-196">1001</span><span class="sxs-lookup"><span data-stu-id="7580b-196">1001</span></span>             |
| <span data-ttu-id="7580b-197">Juste valeur de l’actif</span><span class="sxs-lookup"><span data-stu-id="7580b-197">Fair value of the asset</span></span>    | <span data-ttu-id="7580b-198">245,000</span><span class="sxs-lookup"><span data-stu-id="7580b-198">245,000</span></span>          |
| <span data-ttu-id="7580b-199">Durée de vie utile de l’actif</span><span class="sxs-lookup"><span data-stu-id="7580b-199">Asset useful life</span></span>          | <span data-ttu-id="7580b-200">120</span><span class="sxs-lookup"><span data-stu-id="7580b-200">120</span></span>              |
| <span data-ttu-id="7580b-201">Type d’annuité</span><span class="sxs-lookup"><span data-stu-id="7580b-201">Annuity type</span></span>               | <span data-ttu-id="7580b-202">Annuité ordinaire</span><span class="sxs-lookup"><span data-stu-id="7580b-202">Ordinary annuity</span></span> |
| <span data-ttu-id="7580b-203">Intervalle de composition</span><span class="sxs-lookup"><span data-stu-id="7580b-203">Compounding interval</span></span>       | <span data-ttu-id="7580b-204">Tous les mois</span><span class="sxs-lookup"><span data-stu-id="7580b-204">Monthly</span></span>          |

<span data-ttu-id="7580b-205">**Onglet Lignes d’échéancier de paiement**</span><span class="sxs-lookup"><span data-stu-id="7580b-205">**Payment schedule lines tab**</span></span>

| <span data-ttu-id="7580b-206">Champ</span><span class="sxs-lookup"><span data-stu-id="7580b-206">Field</span></span>             | <span data-ttu-id="7580b-207">Valeur</span><span class="sxs-lookup"><span data-stu-id="7580b-207">Value</span></span>      |
|-------------------|------------|
| <span data-ttu-id="7580b-208">Date de début</span><span class="sxs-lookup"><span data-stu-id="7580b-208">Start date</span></span>        | <span data-ttu-id="7580b-209">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="7580b-209">1/1/2020</span></span>   |
| <span data-ttu-id="7580b-210">Intervalle de périodes</span><span class="sxs-lookup"><span data-stu-id="7580b-210">Period interval</span></span>   | <span data-ttu-id="7580b-211">Mois</span><span class="sxs-lookup"><span data-stu-id="7580b-211">Months</span></span>     |
| <span data-ttu-id="7580b-212">Périodes</span><span class="sxs-lookup"><span data-stu-id="7580b-212">Periods</span></span>           | <span data-ttu-id="7580b-213">24</span><span class="sxs-lookup"><span data-stu-id="7580b-213">24</span></span>         |
| <span data-ttu-id="7580b-214">Date de fin</span><span class="sxs-lookup"><span data-stu-id="7580b-214">End date</span></span>          | <span data-ttu-id="7580b-215">31/12/2020</span><span class="sxs-lookup"><span data-stu-id="7580b-215">12/31/2020</span></span> |
| <span data-ttu-id="7580b-216">Fréquence de paiement</span><span class="sxs-lookup"><span data-stu-id="7580b-216">Payment frequency</span></span> | <span data-ttu-id="7580b-217">Tous les mois</span><span class="sxs-lookup"><span data-stu-id="7580b-217">Monthly</span></span>    |
| <span data-ttu-id="7580b-218">Montant du paiement</span><span class="sxs-lookup"><span data-stu-id="7580b-218">Payment amount</span></span>    | <span data-ttu-id="7580b-219">1 000</span><span class="sxs-lookup"><span data-stu-id="7580b-219">1,000</span></span>      |

<span data-ttu-id="7580b-220">Pour tenir compte de ce bail sous deux structures, vous utilisez une couche de validation actuelle et une couche de validation personnalisée.</span><span class="sxs-lookup"><span data-stu-id="7580b-220">To account for this lease under two frameworks, you use a current posting layer and a custom posting layer.</span></span> <span data-ttu-id="7580b-221">Le tableau suivant montre un exemple de chaque écriture de journal nécessaire pour représenter fidèlement les données financières selon chaque norme de reporting.</span><span class="sxs-lookup"><span data-stu-id="7580b-221">The following table shows an example of every journal entry that required to fairly represent the financials under each reporting standard.</span></span> <span data-ttu-id="7580b-222">Une description détaillée de chaque écriture de journal pour le premier mois du bail est fournie par la suite.</span><span class="sxs-lookup"><span data-stu-id="7580b-222">A detailed description of each journal entry for the first month of the lease is provided afterward.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="7580b-223">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="7580b-223">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="7580b-224">Description</span><span class="sxs-lookup"><span data-stu-id="7580b-224">Description</span></span></th>
<th colspan='3'><span data-ttu-id="7580b-225">Registre statutaire (couche actuelle)</span><span class="sxs-lookup"><span data-stu-id="7580b-225">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="7580b-226">Total de la couche actuelle</span><span class="sxs-lookup"><span data-stu-id="7580b-226">Current layer total</span></span></th>
<th><span data-ttu-id="7580b-227">Registre de contrepassation (couche personnalisée)</span><span class="sxs-lookup"><span data-stu-id="7580b-227">Reversal book (custom layer)</span></span></th>
<th colspan='4'><span data-ttu-id="7580b-228">Registre IFRS 16 (couche personnalisée)</span><span class="sxs-lookup"><span data-stu-id="7580b-228">IFRS 16 book (custom layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="7580b-229">Couche actuelle + total de la couche personnalisée</span><span class="sxs-lookup"><span data-stu-id="7580b-229">Current layer + custom layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="7580b-230">JE-100</span><span class="sxs-lookup"><span data-stu-id="7580b-230">JE-100</span></span></th>
<th><span data-ttu-id="7580b-231">JE-110</span><span class="sxs-lookup"><span data-stu-id="7580b-231">JE-110</span></span></th>
<th><span data-ttu-id="7580b-232">JE-120</span><span class="sxs-lookup"><span data-stu-id="7580b-232">JE-120</span></span></th>
<th><span data-ttu-id="7580b-233">JE-130</span><span class="sxs-lookup"><span data-stu-id="7580b-233">JE-130</span></span></th>
<th><span data-ttu-id="7580b-234">JE-140</span><span class="sxs-lookup"><span data-stu-id="7580b-234">JE-140</span></span></th>
<th><span data-ttu-id="7580b-235">JE-150</span><span class="sxs-lookup"><span data-stu-id="7580b-235">JE-150</span></span></th>
<th><span data-ttu-id="7580b-236">JE-160</span><span class="sxs-lookup"><span data-stu-id="7580b-236">JE-160</span></span></th>
<th><span data-ttu-id="7580b-237">JE-170</span><span class="sxs-lookup"><span data-stu-id="7580b-237">JE-170</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="7580b-238">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="7580b-238">Dr (Cr)</span></span></th>
<th><span data-ttu-id="7580b-239">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="7580b-239">Dr (Cr)</span></span></th>
<th><span data-ttu-id="7580b-240">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="7580b-240">Dr (Cr)</span></span></th>
<th><span data-ttu-id="7580b-241">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="7580b-241">Dr (Cr)</span></span></th>
<th><span data-ttu-id="7580b-242">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="7580b-242">Dr (Cr)</span></span></th>
<th><span data-ttu-id="7580b-243">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="7580b-243">Dr (Cr)</span></span></th>
<th><span data-ttu-id="7580b-244">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="7580b-244">Dr (Cr)</span></span></th>
<th><span data-ttu-id="7580b-245">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="7580b-245">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7580b-246">1</span><span class="sxs-lookup"><span data-stu-id="7580b-246">1</span></span></td>
<td><span data-ttu-id="7580b-247">Dépense de bail</span><span class="sxs-lookup"><span data-stu-id="7580b-247">Lease expense</span></span></td>
<td><span data-ttu-id="7580b-248">1,000.00</span><span class="sxs-lookup"><span data-stu-id="7580b-248">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="7580b-249">1,000.00</span><span class="sxs-lookup"><span data-stu-id="7580b-249">1,000.00</span></span></td>
<td><span data-ttu-id="7580b-250">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="7580b-250">-1,000.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="7580b-251">0,00</span><span class="sxs-lookup"><span data-stu-id="7580b-251">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7580b-252">2</span><span class="sxs-lookup"><span data-stu-id="7580b-252">2</span></span></td>
<td><span data-ttu-id="7580b-253">Frais bancaires</span><span class="sxs-lookup"><span data-stu-id="7580b-253">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="7580b-254">3.00</span><span class="sxs-lookup"><span data-stu-id="7580b-254">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="7580b-255">3.00</span><span class="sxs-lookup"><span data-stu-id="7580b-255">3.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="7580b-256">3.00</span><span class="sxs-lookup"><span data-stu-id="7580b-256">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7580b-257">3</span><span class="sxs-lookup"><span data-stu-id="7580b-257">3</span></span></td>
<td><span data-ttu-id="7580b-258">Dépenses de TVA</span><span class="sxs-lookup"><span data-stu-id="7580b-258">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="7580b-259">5.00</span><span class="sxs-lookup"><span data-stu-id="7580b-259">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="7580b-260">5.00</span><span class="sxs-lookup"><span data-stu-id="7580b-260">5.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="7580b-261">5.00</span><span class="sxs-lookup"><span data-stu-id="7580b-261">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7580b-262">4</span><span class="sxs-lookup"><span data-stu-id="7580b-262">4</span></span></td>
<td><span data-ttu-id="7580b-263">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="7580b-263">Clearing account</span></span></td>
<td><span data-ttu-id="7580b-264">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="7580b-264">-1,000.00</span></span></td>
<td><span data-ttu-id="7580b-265">1,000.00</span><span class="sxs-lookup"><span data-stu-id="7580b-265">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="7580b-266">0,00</span><span class="sxs-lookup"><span data-stu-id="7580b-266">0.00</span></span></td>
<td><span data-ttu-id="7580b-267">1,000.00</span><span class="sxs-lookup"><span data-stu-id="7580b-267">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="7580b-268">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="7580b-268">-1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="7580b-269">0,00</span><span class="sxs-lookup"><span data-stu-id="7580b-269">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7580b-270">5</span><span class="sxs-lookup"><span data-stu-id="7580b-270">5</span></span></td>
<td><span data-ttu-id="7580b-271">Module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="7580b-271">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="7580b-272">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="7580b-272">-1,008.00</span></span></td>
<td><span data-ttu-id="7580b-273">1,008.00</span><span class="sxs-lookup"><span data-stu-id="7580b-273">1,008.00</span></span></td>
<td><span data-ttu-id="7580b-274">0,00</span><span class="sxs-lookup"><span data-stu-id="7580b-274">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="7580b-275">0,00</span><span class="sxs-lookup"><span data-stu-id="7580b-275">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7580b-276">6</span><span class="sxs-lookup"><span data-stu-id="7580b-276">6</span></span></td>
<td><span data-ttu-id="7580b-277">Droit d’utilisation de l’actif</span><span class="sxs-lookup"><span data-stu-id="7580b-277">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="7580b-278">0,00</span><span class="sxs-lookup"><span data-stu-id="7580b-278">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="7580b-279">22,794.00</span><span class="sxs-lookup"><span data-stu-id="7580b-279">22,794.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="7580b-280">22,793.90</span><span class="sxs-lookup"><span data-stu-id="7580b-280">22,793.90</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7580b-281">7</span><span class="sxs-lookup"><span data-stu-id="7580b-281">7</span></span></td>
<td><span data-ttu-id="7580b-282">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="7580b-282">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="7580b-283">0,00</span><span class="sxs-lookup"><span data-stu-id="7580b-283">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="7580b-284">-22 794,00</span><span class="sxs-lookup"><span data-stu-id="7580b-284">-22,794.00</span></span></td>
<td><span data-ttu-id="7580b-285">1,000.00</span><span class="sxs-lookup"><span data-stu-id="7580b-285">1,000.00</span></span></td>
<td><span data-ttu-id="7580b-286">-94,97</span><span class="sxs-lookup"><span data-stu-id="7580b-286">-94.97</span></span></td>
<td></td>
<td><span data-ttu-id="7580b-287">-21 888,87</span><span class="sxs-lookup"><span data-stu-id="7580b-287">-21,888.87</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7580b-288">8</span><span class="sxs-lookup"><span data-stu-id="7580b-288">8</span></span></td>
<td><span data-ttu-id="7580b-289">Dépenses d’intérêts</span><span class="sxs-lookup"><span data-stu-id="7580b-289">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="7580b-290">0,00</span><span class="sxs-lookup"><span data-stu-id="7580b-290">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="7580b-291">94.97</span><span class="sxs-lookup"><span data-stu-id="7580b-291">94.97</span></span></td>
<td></td>
<td><span data-ttu-id="7580b-292">94.97</span><span class="sxs-lookup"><span data-stu-id="7580b-292">94.97</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7580b-293">9</span><span class="sxs-lookup"><span data-stu-id="7580b-293">9</span></span></td>
<td><span data-ttu-id="7580b-294">Monétaire</span><span class="sxs-lookup"><span data-stu-id="7580b-294">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="7580b-295">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="7580b-295">-1,008.00</span></span></td>
<td><span data-ttu-id="7580b-296">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="7580b-296">-1,008.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="7580b-297">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="7580b-297">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7580b-298">10</span><span class="sxs-lookup"><span data-stu-id="7580b-298">10</span></span></td>
<td><span data-ttu-id="7580b-299">Dépenses d’amortissement</span><span class="sxs-lookup"><span data-stu-id="7580b-299">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="7580b-300">0,00</span><span class="sxs-lookup"><span data-stu-id="7580b-300">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="7580b-301">949.75</span><span class="sxs-lookup"><span data-stu-id="7580b-301">949.75</span></span></td>
<td><span data-ttu-id="7580b-302">949.75</span><span class="sxs-lookup"><span data-stu-id="7580b-302">949.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7580b-303">11</span><span class="sxs-lookup"><span data-stu-id="7580b-303">11</span></span></td>
<td><span data-ttu-id="7580b-304">Amortissement cumulé</span><span class="sxs-lookup"><span data-stu-id="7580b-304">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="7580b-305">0,00</span><span class="sxs-lookup"><span data-stu-id="7580b-305">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="7580b-306">-949,75</span><span class="sxs-lookup"><span data-stu-id="7580b-306">-949.75</span></span></td>
<td><span data-ttu-id="7580b-307">-949,75</span><span class="sxs-lookup"><span data-stu-id="7580b-307">-949.75</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7580b-308">Comme le montre le tableau précédent, trois registres sont tenus pour déclarer à la fois le reporting statutaire et le reporting IFRS.</span><span class="sxs-lookup"><span data-stu-id="7580b-308">As the preceding table shows, three books are required to report under both statutory reporting and IFRS reporting.</span></span>

- <span data-ttu-id="7580b-309">Le registre statutaire enregistre le paiement de location selon les règles de comptabilité de caisse sous la couche actuelle.</span><span class="sxs-lookup"><span data-stu-id="7580b-309">The statutory book records the lease payment according to the rules for cash-basis accounting under the current layer.</span></span>
- <span data-ttu-id="7580b-310">Le registre de contrepassation statutaire annule les écritures au journal statutaire.</span><span class="sxs-lookup"><span data-stu-id="7580b-310">The statutory reversal book reverses the statutory journal entries.</span></span>
- <span data-ttu-id="7580b-311">Le registre IFRS 16 crée les écritures de journal requises en vertu d’IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="7580b-311">The IFRS 16 book creates the journal entries that are required under IFRS 16.</span></span>

<span data-ttu-id="7580b-312">Vous ne devez saisir un bail qu’une seule fois.</span><span class="sxs-lookup"><span data-stu-id="7580b-312">You must enter a lease only one time.</span></span> <span data-ttu-id="7580b-313">Vous pouvez ensuite ouvrir la page **Registres** pour voir tous les registres associés au bail.</span><span class="sxs-lookup"><span data-stu-id="7580b-313">You can then open the **Books** page to see all the books that are associated with the lease.</span></span>

> [!NOTE]
> <span data-ttu-id="7580b-314">Lorsque vous créez les registres, tous les trois doivent être associés au même enregistrement de bail.</span><span class="sxs-lookup"><span data-stu-id="7580b-314">When you create the books, all three of them must be associated with the same lease record.</span></span>

<span data-ttu-id="7580b-315">La première écriture de journal enregistre les frais de location dans le registre statutaire.</span><span class="sxs-lookup"><span data-stu-id="7580b-315">The first journal entry records the lease expense under the statutory book.</span></span> <span data-ttu-id="7580b-316">Vous pouvez créer les paiements soit par lots, soit en sélectionnant l’échéancier de paiement dans le registre statutaire.</span><span class="sxs-lookup"><span data-stu-id="7580b-316">You can create the payments either in a batch or by selecting the payment schedule in the statutory book.</span></span>

<span data-ttu-id="7580b-317">Pour cet exemple, l’écriture de journal suivante est produite pour le registre statutaire à partir de l’échéancier de paiement.</span><span class="sxs-lookup"><span data-stu-id="7580b-317">For this example, the following journal entry is produced for the statutory book from the payment schedule.</span></span>

### <a name="lease-payment--1312020--je-100"></a><span data-ttu-id="7580b-318">Paiement de location – 31/01/2020 – JE 100</span><span class="sxs-lookup"><span data-stu-id="7580b-318">Lease payment – 1/31/2020 – JE 100</span></span>

| <span data-ttu-id="7580b-319">Type de compte</span><span class="sxs-lookup"><span data-stu-id="7580b-319">Account type</span></span> | <span data-ttu-id="7580b-320">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="7580b-320">Account number</span></span> | <span data-ttu-id="7580b-321">Couche</span><span class="sxs-lookup"><span data-stu-id="7580b-321">Layer</span></span>   | <span data-ttu-id="7580b-322">Description du compte</span><span class="sxs-lookup"><span data-stu-id="7580b-322">Account description</span></span> | <span data-ttu-id="7580b-323">Débit</span><span class="sxs-lookup"><span data-stu-id="7580b-323">Debit</span></span>    | <span data-ttu-id="7580b-324">Crédit</span><span class="sxs-lookup"><span data-stu-id="7580b-324">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="7580b-325">Registre</span><span class="sxs-lookup"><span data-stu-id="7580b-325">Ledger</span></span>       | <span data-ttu-id="7580b-326">1</span><span class="sxs-lookup"><span data-stu-id="7580b-326">1</span></span>              | <span data-ttu-id="7580b-327">Actuelle</span><span class="sxs-lookup"><span data-stu-id="7580b-327">Current</span></span> | <span data-ttu-id="7580b-328">Dépense de bail</span><span class="sxs-lookup"><span data-stu-id="7580b-328">Lease expense</span></span>       | <span data-ttu-id="7580b-329">1,000.00</span><span class="sxs-lookup"><span data-stu-id="7580b-329">1,000.00</span></span> |          |
| <span data-ttu-id="7580b-330">Registre</span><span class="sxs-lookup"><span data-stu-id="7580b-330">Ledger</span></span>       | <span data-ttu-id="7580b-331">4</span><span class="sxs-lookup"><span data-stu-id="7580b-331">4</span></span>              | <span data-ttu-id="7580b-332">Actuelle</span><span class="sxs-lookup"><span data-stu-id="7580b-332">Current</span></span> | <span data-ttu-id="7580b-333">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="7580b-333">Clearing account</span></span>    |          | <span data-ttu-id="7580b-334">1,000.00</span><span class="sxs-lookup"><span data-stu-id="7580b-334">1,000.00</span></span> |

<span data-ttu-id="7580b-335">Un commis aux comptes fournisseurs utilise la fonctionnalité standard de Dynamics 365 pour créer une facture pour payer le bail en dehors de la location d’actifs.</span><span class="sxs-lookup"><span data-stu-id="7580b-335">An Accounts payable clerk uses standard Dynamics 365 functionality to create an invoice to pay for the lease outside Asset leasing.</span></span> <span data-ttu-id="7580b-336">Cependant, au lieu de sélectionner **Frais de location** comme compte de débit, le commis aux comptes fournisseurs sélectionne un compte de compensation pour générer l’écriture suivante.</span><span class="sxs-lookup"><span data-stu-id="7580b-336">However, instead of selecting **Lease expense** as the debit account, the Accounts payable clerk selects a clearing account to generate the following entry.</span></span>

### <a name="ap-process--1312020--je-110"></a><span data-ttu-id="7580b-337">Processus AP – 31/01/2020 – JE 110</span><span class="sxs-lookup"><span data-stu-id="7580b-337">AP process – 1/31/2020 – JE 110</span></span>

| <span data-ttu-id="7580b-338">Type de compte</span><span class="sxs-lookup"><span data-stu-id="7580b-338">Account type</span></span> | <span data-ttu-id="7580b-339">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="7580b-339">Account number</span></span> | <span data-ttu-id="7580b-340">Couche</span><span class="sxs-lookup"><span data-stu-id="7580b-340">Layer</span></span>   | <span data-ttu-id="7580b-341">Description du compte</span><span class="sxs-lookup"><span data-stu-id="7580b-341">Account description</span></span> | <span data-ttu-id="7580b-342">Débit</span><span class="sxs-lookup"><span data-stu-id="7580b-342">Debit</span></span>    | <span data-ttu-id="7580b-343">Crédit</span><span class="sxs-lookup"><span data-stu-id="7580b-343">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="7580b-344">Registre</span><span class="sxs-lookup"><span data-stu-id="7580b-344">Ledger</span></span>       | <span data-ttu-id="7580b-345">4</span><span class="sxs-lookup"><span data-stu-id="7580b-345">4</span></span>              | <span data-ttu-id="7580b-346">Actuelle</span><span class="sxs-lookup"><span data-stu-id="7580b-346">Current</span></span> | <span data-ttu-id="7580b-347">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="7580b-347">Clearing account</span></span>    | <span data-ttu-id="7580b-348">1,000.00</span><span class="sxs-lookup"><span data-stu-id="7580b-348">1,000.00</span></span> |          |
| <span data-ttu-id="7580b-349">Registre</span><span class="sxs-lookup"><span data-stu-id="7580b-349">Ledger</span></span>       | <span data-ttu-id="7580b-350">2</span><span class="sxs-lookup"><span data-stu-id="7580b-350">2</span></span>              | <span data-ttu-id="7580b-351">Actuelle</span><span class="sxs-lookup"><span data-stu-id="7580b-351">Current</span></span> | <span data-ttu-id="7580b-352">Frais bancaires</span><span class="sxs-lookup"><span data-stu-id="7580b-352">Bank fee</span></span>            | <span data-ttu-id="7580b-353">3.00</span><span class="sxs-lookup"><span data-stu-id="7580b-353">3.00</span></span>     |          |
| <span data-ttu-id="7580b-354">Registre</span><span class="sxs-lookup"><span data-stu-id="7580b-354">Ledger</span></span>       | <span data-ttu-id="7580b-355">3</span><span class="sxs-lookup"><span data-stu-id="7580b-355">3</span></span>              | <span data-ttu-id="7580b-356">Actuelle</span><span class="sxs-lookup"><span data-stu-id="7580b-356">Current</span></span> | <span data-ttu-id="7580b-357">Dépenses de TVA</span><span class="sxs-lookup"><span data-stu-id="7580b-357">VAT expense</span></span>         | <span data-ttu-id="7580b-358">5.00</span><span class="sxs-lookup"><span data-stu-id="7580b-358">5.00</span></span>     |          |
| <span data-ttu-id="7580b-359">Fournisseur</span><span class="sxs-lookup"><span data-stu-id="7580b-359">Vendor</span></span>       | <span data-ttu-id="7580b-360">5</span><span class="sxs-lookup"><span data-stu-id="7580b-360">5</span></span>              | <span data-ttu-id="7580b-361">Actuelle</span><span class="sxs-lookup"><span data-stu-id="7580b-361">Current</span></span> | <span data-ttu-id="7580b-362">Module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="7580b-362">Accounts payable</span></span>    |          | <span data-ttu-id="7580b-363">1,008.00</span><span class="sxs-lookup"><span data-stu-id="7580b-363">1,008.00</span></span> |

<span data-ttu-id="7580b-364">Lorsque la déclaration est délivrée au fournisseur, vous suivez le processus de paiement régulier.</span><span class="sxs-lookup"><span data-stu-id="7580b-364">When the statement is issued to the vendor, you follow the regular payment process.</span></span> <span data-ttu-id="7580b-365">Au cours de ce processus, l’écriture de journal suivante est générée.</span><span class="sxs-lookup"><span data-stu-id="7580b-365">During this process, the following journal entry is generated.</span></span>

### <a name="cash-payment--1312020--je-120"></a><span data-ttu-id="7580b-366">Paiement en espèces – 31/01/2020 – JE 120</span><span class="sxs-lookup"><span data-stu-id="7580b-366">Cash payment – 1/31/2020 – JE 120</span></span>

| <span data-ttu-id="7580b-367">Type de compte</span><span class="sxs-lookup"><span data-stu-id="7580b-367">Account type</span></span> | <span data-ttu-id="7580b-368">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="7580b-368">Account number</span></span> | <span data-ttu-id="7580b-369">Couche</span><span class="sxs-lookup"><span data-stu-id="7580b-369">Layer</span></span>   | <span data-ttu-id="7580b-370">Description du compte</span><span class="sxs-lookup"><span data-stu-id="7580b-370">Account description</span></span> | <span data-ttu-id="7580b-371">Débit</span><span class="sxs-lookup"><span data-stu-id="7580b-371">Debit</span></span>    | <span data-ttu-id="7580b-372">Crédit</span><span class="sxs-lookup"><span data-stu-id="7580b-372">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="7580b-373">Fournisseur</span><span class="sxs-lookup"><span data-stu-id="7580b-373">Vendor</span></span>       | <span data-ttu-id="7580b-374">5</span><span class="sxs-lookup"><span data-stu-id="7580b-374">5</span></span>              | <span data-ttu-id="7580b-375">Actuelle</span><span class="sxs-lookup"><span data-stu-id="7580b-375">Current</span></span> | <span data-ttu-id="7580b-376">Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="7580b-376">Accounts Payable</span></span>    | <span data-ttu-id="7580b-377">1,008.00</span><span class="sxs-lookup"><span data-stu-id="7580b-377">1,008.00</span></span> |          |
| <span data-ttu-id="7580b-378">Banque</span><span class="sxs-lookup"><span data-stu-id="7580b-378">Bank</span></span>         | <span data-ttu-id="7580b-379">9</span><span class="sxs-lookup"><span data-stu-id="7580b-379">9</span></span>              | <span data-ttu-id="7580b-380">Actuelle</span><span class="sxs-lookup"><span data-stu-id="7580b-380">Current</span></span> | <span data-ttu-id="7580b-381">Monétaire</span><span class="sxs-lookup"><span data-stu-id="7580b-381">Cash</span></span>                |          | <span data-ttu-id="7580b-382">1,008.00</span><span class="sxs-lookup"><span data-stu-id="7580b-382">1,008.00</span></span> |

<span data-ttu-id="7580b-383">À ce stade, vous avez pleinement pris en compte ce bail conformément aux exigences légales en matière de rapports et pouvez générer une balance comptable en utilisant la couche actuelle.</span><span class="sxs-lookup"><span data-stu-id="7580b-383">At this point, you've fully accounted for this lease under statutory reporting requirements and can generate a trial balance by using the current layer.</span></span> <span data-ttu-id="7580b-384">Le système renvoie une balance comptable qui a les chiffres suivants.</span><span class="sxs-lookup"><span data-stu-id="7580b-384">The system returns a trial balance that has the following figures.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="7580b-385">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="7580b-385">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="7580b-386">Description</span><span class="sxs-lookup"><span data-stu-id="7580b-386">Description</span></span></th>
<th colspan='3'><span data-ttu-id="7580b-387">Registre statutaire (couche actuelle)</span><span class="sxs-lookup"><span data-stu-id="7580b-387">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="7580b-388">Total de la couche actuelle</span><span class="sxs-lookup"><span data-stu-id="7580b-388">Current layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="7580b-389">JE-100</span><span class="sxs-lookup"><span data-stu-id="7580b-389">JE-100</span></span></th>
<th><span data-ttu-id="7580b-390">JE-110</span><span class="sxs-lookup"><span data-stu-id="7580b-390">JE-110</span></span></th>
<th><span data-ttu-id="7580b-391">JE-120</span><span class="sxs-lookup"><span data-stu-id="7580b-391">JE-120</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="7580b-392">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="7580b-392">Dr (Cr)</span></span></th>
<th><span data-ttu-id="7580b-393">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="7580b-393">Dr (Cr)</span></span></th>
<th><span data-ttu-id="7580b-394">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="7580b-394">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7580b-395">1</span><span class="sxs-lookup"><span data-stu-id="7580b-395">1</span></span></td>
<td><span data-ttu-id="7580b-396">Dépense de bail</span><span class="sxs-lookup"><span data-stu-id="7580b-396">Lease expense</span></span></td>
<td><span data-ttu-id="7580b-397">1,000.00</span><span class="sxs-lookup"><span data-stu-id="7580b-397">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="7580b-398">1,000.00</span><span class="sxs-lookup"><span data-stu-id="7580b-398">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7580b-399">2</span><span class="sxs-lookup"><span data-stu-id="7580b-399">2</span></span></td>
<td><span data-ttu-id="7580b-400">Frais bancaires</span><span class="sxs-lookup"><span data-stu-id="7580b-400">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="7580b-401">3.00</span><span class="sxs-lookup"><span data-stu-id="7580b-401">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="7580b-402">3.00</span><span class="sxs-lookup"><span data-stu-id="7580b-402">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7580b-403">3</span><span class="sxs-lookup"><span data-stu-id="7580b-403">3</span></span></td>
<td><span data-ttu-id="7580b-404">Dépenses de TVA</span><span class="sxs-lookup"><span data-stu-id="7580b-404">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="7580b-405">5.00</span><span class="sxs-lookup"><span data-stu-id="7580b-405">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="7580b-406">5.00</span><span class="sxs-lookup"><span data-stu-id="7580b-406">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7580b-407">4</span><span class="sxs-lookup"><span data-stu-id="7580b-407">4</span></span></td>
<td><span data-ttu-id="7580b-408">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="7580b-408">Clearing account</span></span></td>
<td><span data-ttu-id="7580b-409">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="7580b-409">-1,000.00</span></span></td>
<td><span data-ttu-id="7580b-410">1,000.00</span><span class="sxs-lookup"><span data-stu-id="7580b-410">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="7580b-411">0,00</span><span class="sxs-lookup"><span data-stu-id="7580b-411">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7580b-412">5</span><span class="sxs-lookup"><span data-stu-id="7580b-412">5</span></span></td>
<td><span data-ttu-id="7580b-413">Module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="7580b-413">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="7580b-414">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="7580b-414">-1,008.00</span></span></td>
<td><span data-ttu-id="7580b-415">1,008.00</span><span class="sxs-lookup"><span data-stu-id="7580b-415">1,008.00</span></span></td>
<td><span data-ttu-id="7580b-416">0,00</span><span class="sxs-lookup"><span data-stu-id="7580b-416">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7580b-417">6</span><span class="sxs-lookup"><span data-stu-id="7580b-417">6</span></span></td>
<td><span data-ttu-id="7580b-418">Droit d’utilisation de l’actif</span><span class="sxs-lookup"><span data-stu-id="7580b-418">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="7580b-419">0,00</span><span class="sxs-lookup"><span data-stu-id="7580b-419">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7580b-420">7</span><span class="sxs-lookup"><span data-stu-id="7580b-420">7</span></span></td>
<td><span data-ttu-id="7580b-421">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="7580b-421">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="7580b-422">0,00</span><span class="sxs-lookup"><span data-stu-id="7580b-422">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7580b-423">8</span><span class="sxs-lookup"><span data-stu-id="7580b-423">8</span></span></td>
<td><span data-ttu-id="7580b-424">Dépenses d’intérêts</span><span class="sxs-lookup"><span data-stu-id="7580b-424">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="7580b-425">0,00</span><span class="sxs-lookup"><span data-stu-id="7580b-425">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7580b-426">9</span><span class="sxs-lookup"><span data-stu-id="7580b-426">9</span></span></td>
<td><span data-ttu-id="7580b-427">Monétaire</span><span class="sxs-lookup"><span data-stu-id="7580b-427">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="7580b-428">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="7580b-428">-1,008.00</span></span></td>
<td><span data-ttu-id="7580b-429">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="7580b-429">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7580b-430">10</span><span class="sxs-lookup"><span data-stu-id="7580b-430">10</span></span></td>
<td><span data-ttu-id="7580b-431">Dépenses d’amortissement</span><span class="sxs-lookup"><span data-stu-id="7580b-431">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="7580b-432">0,00</span><span class="sxs-lookup"><span data-stu-id="7580b-432">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7580b-433">11</span><span class="sxs-lookup"><span data-stu-id="7580b-433">11</span></span></td>
<td><span data-ttu-id="7580b-434">Amortissement cumulé</span><span class="sxs-lookup"><span data-stu-id="7580b-434">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="7580b-435">0,00</span><span class="sxs-lookup"><span data-stu-id="7580b-435">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7580b-436">Si vous souhaitez utiliser les chiffres IFRS 16 pour exécuter la même balance comptable, les écritures comptables statutaires doivent être contrepassées et les écritures comptables IFRS 16 doivent être enregistrées.</span><span class="sxs-lookup"><span data-stu-id="7580b-436">If you want to use the IFRS 16 figures to run the same trial balance, the statutory accounting journal entries must be reversed, and the IFRS 16 journal entries must be posted.</span></span> <span data-ttu-id="7580b-437">Pour contrepasser les écritures statutaires, cet exemple inclut un registre de contrepassation statutaire qui a la même configuration que le registre statutaire mais un profil de validation opposé.</span><span class="sxs-lookup"><span data-stu-id="7580b-437">To reverse the statutory journal entries, this example includes a statutory reversal book that has the same setup as the statutory book but an opposite posting profile.</span></span> <span data-ttu-id="7580b-438">Par exemple, le registre statutaire *a débité* un compte de charges de location, mais le registre de contrepassation va *créditer* ce compte.</span><span class="sxs-lookup"><span data-stu-id="7580b-438">For example, the statutory book *debited* a lease expense account, but the reversal book will *credit* this account.</span></span> <span data-ttu-id="7580b-439">Ces relations sont facilement définies dans les comptes de comptabilisation de la location d’actifs sur la page **Paramètres de location d’actifs** (**Location d’actifs \> Configurer \> Paramètres de location d’actifs**).</span><span class="sxs-lookup"><span data-stu-id="7580b-439">These relationships are easily defined in the Asset leasing posting accounts on the **Asset leasing parameters** page (**Asset leasing \> Setup \> Asset leasing parameters**).</span></span>

<span data-ttu-id="7580b-440">Lorsque le même processus que celui utilisé pour le registre statutaire est utilisé pour le registre de contrepassation, l’écriture de journal suivante est produite.</span><span class="sxs-lookup"><span data-stu-id="7580b-440">When the same process that was used for the statutory book is used for the reversal book, the following journal entry is produced.</span></span> <span data-ttu-id="7580b-441">La différence est que le registre de contrepassation comptabilise les écritures de contrepassation du registre statutaire.</span><span class="sxs-lookup"><span data-stu-id="7580b-441">The difference is that the reversal book books the reversing entries from the statutory book.</span></span> <span data-ttu-id="7580b-442">Les écritures de contrepassation sont également apportées à la couche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="7580b-442">The reversing entries are also made to the custom layer.</span></span> <span data-ttu-id="7580b-443">Lorsqu’une balance comptable est exécutée au niveau de la couche actuelle, les écritures de journal de contrepassation ne sont pas incluses.</span><span class="sxs-lookup"><span data-stu-id="7580b-443">When a trial balance is run at the current layer, the reversing journal entries aren't included.</span></span>

### <a name="lease-payment--1312020--je-130"></a><span data-ttu-id="7580b-444">Paiement de location – 31/01/2020 – JE 130</span><span class="sxs-lookup"><span data-stu-id="7580b-444">Lease payment – 1/31/2020 – JE 130</span></span>

| <span data-ttu-id="7580b-445">Type de compte</span><span class="sxs-lookup"><span data-stu-id="7580b-445">Account type</span></span> | <span data-ttu-id="7580b-446">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="7580b-446">Account number</span></span> | <span data-ttu-id="7580b-447">Couche</span><span class="sxs-lookup"><span data-stu-id="7580b-447">Layer</span></span>  | <span data-ttu-id="7580b-448">Description du compte</span><span class="sxs-lookup"><span data-stu-id="7580b-448">Account description</span></span> | <span data-ttu-id="7580b-449">Débit</span><span class="sxs-lookup"><span data-stu-id="7580b-449">Debit</span></span>    | <span data-ttu-id="7580b-450">Crédit</span><span class="sxs-lookup"><span data-stu-id="7580b-450">Credit</span></span>   |
|--------------|----------------|--------|---------------------|----------|----------|
| <span data-ttu-id="7580b-451">Registre</span><span class="sxs-lookup"><span data-stu-id="7580b-451">Ledger</span></span>       | <span data-ttu-id="7580b-452">4</span><span class="sxs-lookup"><span data-stu-id="7580b-452">4</span></span>              | <span data-ttu-id="7580b-453">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="7580b-453">Custom</span></span> | <span data-ttu-id="7580b-454">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="7580b-454">Clearing account</span></span>    | <span data-ttu-id="7580b-455">1,000.00</span><span class="sxs-lookup"><span data-stu-id="7580b-455">1,000.00</span></span> |          |
| <span data-ttu-id="7580b-456">Registre</span><span class="sxs-lookup"><span data-stu-id="7580b-456">Ledger</span></span>       | <span data-ttu-id="7580b-457">1</span><span class="sxs-lookup"><span data-stu-id="7580b-457">1</span></span>              | <span data-ttu-id="7580b-458">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="7580b-458">Custom</span></span> | <span data-ttu-id="7580b-459">Dépense de bail</span><span class="sxs-lookup"><span data-stu-id="7580b-459">Lease expense</span></span>       |          | <span data-ttu-id="7580b-460">1,000.00</span><span class="sxs-lookup"><span data-stu-id="7580b-460">1,000.00</span></span> |

<span data-ttu-id="7580b-461">Maintenant que vous avez éliminé les écritures de journal statutaires, vous allez enregistrer toutes les écritures de journal requises par IFRS 16 dans le livre IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="7580b-461">Now that you've eliminated the statutory journal entries, you will book all the journal entries that IFRS 16 requires in the IFRS 16 book.</span></span> <span data-ttu-id="7580b-462">Ces écritures comprennent la reconnaissance initiale du droit d’utilisation de l’actif et du passif, ainsi que l’enregistrement des intérêts et des amortissements.</span><span class="sxs-lookup"><span data-stu-id="7580b-462">These entries include the initial recognition of the ROU asset and the liability, and the record of interest and depreciation.</span></span>

### <a name="initial-recognition--112020--je-140"></a><span data-ttu-id="7580b-463">Reconnaissance initiale – 1/1/2020 – JE 140</span><span class="sxs-lookup"><span data-stu-id="7580b-463">Initial recognition – 1/1/2020 – JE 140</span></span>

| <span data-ttu-id="7580b-464">Type de compte</span><span class="sxs-lookup"><span data-stu-id="7580b-464">Account type</span></span> | <span data-ttu-id="7580b-465">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="7580b-465">Account number</span></span> | <span data-ttu-id="7580b-466">Couche</span><span class="sxs-lookup"><span data-stu-id="7580b-466">Layer</span></span>  | <span data-ttu-id="7580b-467">Description du compte</span><span class="sxs-lookup"><span data-stu-id="7580b-467">Account description</span></span>      | <span data-ttu-id="7580b-468">Débit</span><span class="sxs-lookup"><span data-stu-id="7580b-468">Debit</span></span>     | <span data-ttu-id="7580b-469">Crédit</span><span class="sxs-lookup"><span data-stu-id="7580b-469">Credit</span></span>    |
|--------------|----------------|--------|--------------------------|-----------|-----------|
| <span data-ttu-id="7580b-470">Registre</span><span class="sxs-lookup"><span data-stu-id="7580b-470">Ledger</span></span>       | <span data-ttu-id="7580b-471">6</span><span class="sxs-lookup"><span data-stu-id="7580b-471">6</span></span>              | <span data-ttu-id="7580b-472">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="7580b-472">Custom</span></span> | <span data-ttu-id="7580b-473">Droit d’utilisation de l’actif</span><span class="sxs-lookup"><span data-stu-id="7580b-473">ROU Asset</span></span>                | <span data-ttu-id="7580b-474">22,793.90</span><span class="sxs-lookup"><span data-stu-id="7580b-474">22,793.90</span></span> |           |
| <span data-ttu-id="7580b-475">Registre</span><span class="sxs-lookup"><span data-stu-id="7580b-475">Ledger</span></span>       | <span data-ttu-id="7580b-476">7</span><span class="sxs-lookup"><span data-stu-id="7580b-476">7</span></span>              | <span data-ttu-id="7580b-477">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="7580b-477">Custom</span></span> | <span data-ttu-id="7580b-478">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="7580b-478">Finance lease obligation</span></span> |           | <span data-ttu-id="7580b-479">22,793.90</span><span class="sxs-lookup"><span data-stu-id="7580b-479">22,793.90</span></span> |

<span data-ttu-id="7580b-480">Le paiement de location est comptabilisé comme les autres paiements de location.</span><span class="sxs-lookup"><span data-stu-id="7580b-480">The lease payment is posted like the other lease payments.</span></span> <span data-ttu-id="7580b-481">La raison de l’utilisation du compte de compensation est de s’assurer que les espèces ne sont créditées qu’une seule fois.</span><span class="sxs-lookup"><span data-stu-id="7580b-481">The reason for using the clearing account is to ensure that cash is credited only one time.</span></span>

### <a name="lease-payment--1312020--je-150"></a><span data-ttu-id="7580b-482">Paiement de location – 31/01/2020 – JE 150</span><span class="sxs-lookup"><span data-stu-id="7580b-482">Lease payment – 1/31/2020 – JE 150</span></span>

| <span data-ttu-id="7580b-483">Type de compte</span><span class="sxs-lookup"><span data-stu-id="7580b-483">Account type</span></span> | <span data-ttu-id="7580b-484">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="7580b-484">Account number</span></span> | <span data-ttu-id="7580b-485">Couche</span><span class="sxs-lookup"><span data-stu-id="7580b-485">Layer</span></span>  | <span data-ttu-id="7580b-486">Description du compte</span><span class="sxs-lookup"><span data-stu-id="7580b-486">Account description</span></span>      | <span data-ttu-id="7580b-487">Débit</span><span class="sxs-lookup"><span data-stu-id="7580b-487">Debit</span></span>    | <span data-ttu-id="7580b-488">Crédit</span><span class="sxs-lookup"><span data-stu-id="7580b-488">Credit</span></span>   |
|--------------|----------------|--------|--------------------------|----------|----------|
| <span data-ttu-id="7580b-489">Registre</span><span class="sxs-lookup"><span data-stu-id="7580b-489">Ledger</span></span>       | <span data-ttu-id="7580b-490">7</span><span class="sxs-lookup"><span data-stu-id="7580b-490">7</span></span>              | <span data-ttu-id="7580b-491">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="7580b-491">Custom</span></span> | <span data-ttu-id="7580b-492">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="7580b-492">Finance lease obligation</span></span> | <span data-ttu-id="7580b-493">1,000.00</span><span class="sxs-lookup"><span data-stu-id="7580b-493">1,000.00</span></span> |          |
| <span data-ttu-id="7580b-494">Registre</span><span class="sxs-lookup"><span data-stu-id="7580b-494">Ledger</span></span>       | <span data-ttu-id="7580b-495">4</span><span class="sxs-lookup"><span data-stu-id="7580b-495">4</span></span>              | <span data-ttu-id="7580b-496">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="7580b-496">Custom</span></span> | <span data-ttu-id="7580b-497">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="7580b-497">Clearing account</span></span>         |          | <span data-ttu-id="7580b-498">1,000.00</span><span class="sxs-lookup"><span data-stu-id="7580b-498">1,000.00</span></span> |

<span data-ttu-id="7580b-499">L’écriture de journal des charges d’intérêts est générée à partir du calendrier d’amortissement du passif.</span><span class="sxs-lookup"><span data-stu-id="7580b-499">The interest expense journal entry is generated from the liability amortization schedule.</span></span>

### <a name="interest-expense--1312020--je-160"></a><span data-ttu-id="7580b-500">Dépenses d’intérêts – 31/1/2020 – JE 160</span><span class="sxs-lookup"><span data-stu-id="7580b-500">Interest expense – 1/31/2020 – JE 160</span></span>

| <span data-ttu-id="7580b-501">Type de compte</span><span class="sxs-lookup"><span data-stu-id="7580b-501">Account type</span></span> | <span data-ttu-id="7580b-502">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="7580b-502">Account number</span></span> | <span data-ttu-id="7580b-503">Couche</span><span class="sxs-lookup"><span data-stu-id="7580b-503">Layer</span></span>  | <span data-ttu-id="7580b-504">Description du compte</span><span class="sxs-lookup"><span data-stu-id="7580b-504">Account description</span></span>      | <span data-ttu-id="7580b-505">Débit</span><span class="sxs-lookup"><span data-stu-id="7580b-505">Debit</span></span> | <span data-ttu-id="7580b-506">Crédit</span><span class="sxs-lookup"><span data-stu-id="7580b-506">Credit</span></span> |
|--------------|----------------|--------|--------------------------|-------|--------|
| <span data-ttu-id="7580b-507">Registre</span><span class="sxs-lookup"><span data-stu-id="7580b-507">Ledger</span></span>       | <span data-ttu-id="7580b-508">8</span><span class="sxs-lookup"><span data-stu-id="7580b-508">8</span></span>              | <span data-ttu-id="7580b-509">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="7580b-509">Custom</span></span> | <span data-ttu-id="7580b-510">Dépenses d’intérêts</span><span class="sxs-lookup"><span data-stu-id="7580b-510">Interest expense</span></span>         | <span data-ttu-id="7580b-511">94.97</span><span class="sxs-lookup"><span data-stu-id="7580b-511">94.97</span></span> |        |
| <span data-ttu-id="7580b-512">Registre</span><span class="sxs-lookup"><span data-stu-id="7580b-512">Ledger</span></span>       | <span data-ttu-id="7580b-513">7</span><span class="sxs-lookup"><span data-stu-id="7580b-513">7</span></span>              | <span data-ttu-id="7580b-514">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="7580b-514">Custom</span></span> | <span data-ttu-id="7580b-515">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="7580b-515">Finance lease obligation</span></span> |       | <span data-ttu-id="7580b-516">94.97</span><span class="sxs-lookup"><span data-stu-id="7580b-516">94.97</span></span>  |

<span data-ttu-id="7580b-517">L’écriture de journal de dépense d’amortissement est générée à partir du programme d’amortissement du passif.</span><span class="sxs-lookup"><span data-stu-id="7580b-517">The depreciation expense journal entry is generated from the asset depreciation schedule.</span></span>

### <a name="depreciation-expense--1312020--je-170"></a><span data-ttu-id="7580b-518">Dépenses d’amortissement – 1/31/2020 – JE 170</span><span class="sxs-lookup"><span data-stu-id="7580b-518">Depreciation expense – 1/31/2020 – JE 170</span></span>

| <span data-ttu-id="7580b-519">Type de compte</span><span class="sxs-lookup"><span data-stu-id="7580b-519">Account type</span></span> | <span data-ttu-id="7580b-520">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="7580b-520">Account number</span></span> | <span data-ttu-id="7580b-521">Couche</span><span class="sxs-lookup"><span data-stu-id="7580b-521">Layer</span></span>  | <span data-ttu-id="7580b-522">Description du compte</span><span class="sxs-lookup"><span data-stu-id="7580b-522">Account description</span></span>      | <span data-ttu-id="7580b-523">Débit</span><span class="sxs-lookup"><span data-stu-id="7580b-523">Debit</span></span>  | <span data-ttu-id="7580b-524">Crédit</span><span class="sxs-lookup"><span data-stu-id="7580b-524">Credit</span></span> |
|--------------|----------------|--------|--------------------------|--------|--------|
| <span data-ttu-id="7580b-525">Registre</span><span class="sxs-lookup"><span data-stu-id="7580b-525">Ledger</span></span>       | <span data-ttu-id="7580b-526">10</span><span class="sxs-lookup"><span data-stu-id="7580b-526">10</span></span>             | <span data-ttu-id="7580b-527">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="7580b-527">Custom</span></span> | <span data-ttu-id="7580b-528">Dépenses d’amortissement</span><span class="sxs-lookup"><span data-stu-id="7580b-528">Depreciation expense</span></span>     | <span data-ttu-id="7580b-529">949.75</span><span class="sxs-lookup"><span data-stu-id="7580b-529">949.75</span></span> |        |
| <span data-ttu-id="7580b-530">Registre</span><span class="sxs-lookup"><span data-stu-id="7580b-530">Ledger</span></span>       | <span data-ttu-id="7580b-531">11</span><span class="sxs-lookup"><span data-stu-id="7580b-531">11</span></span>             | <span data-ttu-id="7580b-532">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="7580b-532">Custom</span></span> | <span data-ttu-id="7580b-533">Amortissement cumulé</span><span class="sxs-lookup"><span data-stu-id="7580b-533">Accumulated depreciation</span></span> |        | <span data-ttu-id="7580b-534">949.75</span><span class="sxs-lookup"><span data-stu-id="7580b-534">949.75</span></span> |

<span data-ttu-id="7580b-535">Une fois toutes ces entrées de journal créées et validées, vous verrez les valeurs de « couche personnalisée 1 » suivantes.</span><span class="sxs-lookup"><span data-stu-id="7580b-535">After all these journal entries are created and posted, you will see the following "custom layer 1" values.</span></span> <span data-ttu-id="7580b-536">Notez que la dernière colonne comprend les frais bancaires, les frais de taxe sur la valeur ajoutée (TVA) et la réduction des liquidités de la couche précédente, mais elle n’inclut pas les écritures de reporting statutaires.</span><span class="sxs-lookup"><span data-stu-id="7580b-536">Note that the last column includes the bank fee, the value-added tax (VAT) expense, and the reduction of cash from the previous layer, but it doesn't include the statutory reporting journal entries.</span></span> <span data-ttu-id="7580b-537">Par conséquent, vous obtenez de véritables capacités de double reporting.</span><span class="sxs-lookup"><span data-stu-id="7580b-537">Therefore, you achieve true dual-reporting capabilities.</span></span> <span data-ttu-id="7580b-538">À ce stade, l’entreprise doit simplement exécuter sa balance comptable et combiner la couche actuelle et la couche personnalisée pour créer une balance comptable IFRS.</span><span class="sxs-lookup"><span data-stu-id="7580b-538">At this point, the company just has to run its trial balance, and combine the current layer and the custom layer to create an IFRS trial balance.</span></span>

| <span data-ttu-id="7580b-539">N° de compte</span><span class="sxs-lookup"><span data-stu-id="7580b-539">Account No</span></span> | <span data-ttu-id="7580b-540">Description</span><span class="sxs-lookup"><span data-stu-id="7580b-540">Description</span></span>              | <span data-ttu-id="7580b-541">Registre statutaire\-Couche actuelle\-JE\-100\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="7580b-541">Statutory Book\-Current Layer\-JE\-100\-Dr \(Cr\)</span></span> | <span data-ttu-id="7580b-542">Registre statutaire\-Couche actuelle\-JE\-110\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="7580b-542">Statutory Book\-Current Layer\-JE\-110\-Dr \(Cr\)</span></span> | <span data-ttu-id="7580b-543">Registre statutaire\-Couche actuelle\-JE\-120\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="7580b-543">Statutory Book\-Current Layer\-JE\-120\-Dr \(Cr\)</span></span> | <span data-ttu-id="7580b-544">Couche actuelle \- Totaux</span><span class="sxs-lookup"><span data-stu-id="7580b-544">Current Layer \- Totals</span></span> | - | <span data-ttu-id="7580b-545">Registre de contrepassation\-Couche personnalisée\-JE\-130\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="7580b-545">Reversal Book\-Custom layer\-JE\-130\-Dr \(Cr\)</span></span> | <span data-ttu-id="7580b-546">Registre IFRS 16\-Couche personnalisée\-JE\-140\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="7580b-546">IFRS 16 Book\-Custom layer\-JE\-140\-Dr \(Cr\)</span></span> | <span data-ttu-id="7580b-547">Registre IFRS 16\-Couche personnalisée\-JE\-150\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="7580b-547">IFRS 16 Book\-Custom layer\-JE\-150\-Dr \(Cr\)</span></span> | <span data-ttu-id="7580b-548">Registre IFRS 16\-Couche personnalisée\-JE\-160\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="7580b-548">IFRS 16 Book\-Custom layer\-JE\-160\-Dr \(Cr\)</span></span> | <span data-ttu-id="7580b-549">Registre IFRS 16\-Couche personnalisée\-JE\-170\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="7580b-549">IFRS 16 Book\-Custom layer\-JE\-170\-Dr \(Cr\)</span></span> | <span data-ttu-id="7580b-550">Couche personnalisée \+ Couche actuelle \- Totaux</span><span class="sxs-lookup"><span data-stu-id="7580b-550">Custom Layer \+ Current Layer \- Totals</span></span> |
|------------|--------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|-------------------------|---|-------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------|
| <span data-ttu-id="7580b-551">1</span><span class="sxs-lookup"><span data-stu-id="7580b-551">1</span></span>          | <span data-ttu-id="7580b-552">Dépense de bail</span><span class="sxs-lookup"><span data-stu-id="7580b-552">Lease expense</span></span>            | <span data-ttu-id="7580b-553">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="7580b-553">1,000\.00</span></span>                                         |                                                   |                                                   | <span data-ttu-id="7580b-554">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="7580b-554">1,000\.00</span></span>               |   | <span data-ttu-id="7580b-555">\-1 000</span><span class="sxs-lookup"><span data-stu-id="7580b-555">\-1,000</span></span>                                         |                                                |                                                |                                                |                                                | <span data-ttu-id="7580b-556">0\.00</span><span class="sxs-lookup"><span data-stu-id="7580b-556">0\.00</span></span>                                   |
| <span data-ttu-id="7580b-557">2</span><span class="sxs-lookup"><span data-stu-id="7580b-557">2</span></span>          | <span data-ttu-id="7580b-558">Frais bancaires</span><span class="sxs-lookup"><span data-stu-id="7580b-558">Bank fee</span></span>                 |                                                   | <span data-ttu-id="7580b-559">3\.00</span><span class="sxs-lookup"><span data-stu-id="7580b-559">3\.00</span></span>                                             |                                                   | <span data-ttu-id="7580b-560">3\.00</span><span class="sxs-lookup"><span data-stu-id="7580b-560">3\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="7580b-561">3\.00</span><span class="sxs-lookup"><span data-stu-id="7580b-561">3\.00</span></span>                                   |
| <span data-ttu-id="7580b-562">3</span><span class="sxs-lookup"><span data-stu-id="7580b-562">3</span></span>          | <span data-ttu-id="7580b-563">Dépenses de TVA</span><span class="sxs-lookup"><span data-stu-id="7580b-563">VAT expense</span></span>              |                                                   | <span data-ttu-id="7580b-564">5\.00</span><span class="sxs-lookup"><span data-stu-id="7580b-564">5\.00</span></span>                                             |                                                   | <span data-ttu-id="7580b-565">5\.00</span><span class="sxs-lookup"><span data-stu-id="7580b-565">5\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="7580b-566">5\.00</span><span class="sxs-lookup"><span data-stu-id="7580b-566">5\.00</span></span>                                   |
| <span data-ttu-id="7580b-567">4</span><span class="sxs-lookup"><span data-stu-id="7580b-567">4</span></span>          | <span data-ttu-id="7580b-568">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="7580b-568">Clearing account</span></span>         | <span data-ttu-id="7580b-569">\-1 000\.00</span><span class="sxs-lookup"><span data-stu-id="7580b-569">\-1,000\.00</span></span>                                       | <span data-ttu-id="7580b-570">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="7580b-570">1,000\.00</span></span>                                         |                                                   | <span data-ttu-id="7580b-571">0\.00</span><span class="sxs-lookup"><span data-stu-id="7580b-571">0\.00</span></span>                   |   | <span data-ttu-id="7580b-572">1 000</span><span class="sxs-lookup"><span data-stu-id="7580b-572">1,000</span></span>                                           |                                                | <span data-ttu-id="7580b-573">\-1 000</span><span class="sxs-lookup"><span data-stu-id="7580b-573">\-1,000</span></span>                                        |                                                |                                                | <span data-ttu-id="7580b-574">0\.00</span><span class="sxs-lookup"><span data-stu-id="7580b-574">0\.00</span></span>                                   |
| <span data-ttu-id="7580b-575">5</span><span class="sxs-lookup"><span data-stu-id="7580b-575">5</span></span>          | <span data-ttu-id="7580b-576">Module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="7580b-576">Accounts payable</span></span>         |                                                   | <span data-ttu-id="7580b-577">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="7580b-577">\-1,008\.00</span></span>                                       | <span data-ttu-id="7580b-578">1,008\.00</span><span class="sxs-lookup"><span data-stu-id="7580b-578">1,008\.00</span></span>                                         | <span data-ttu-id="7580b-579">0\.00</span><span class="sxs-lookup"><span data-stu-id="7580b-579">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="7580b-580">0\.00</span><span class="sxs-lookup"><span data-stu-id="7580b-580">0\.00</span></span>                                   |
| <span data-ttu-id="7580b-581">6</span><span class="sxs-lookup"><span data-stu-id="7580b-581">6</span></span>          | <span data-ttu-id="7580b-582">Droit d’utilisation de l’actif</span><span class="sxs-lookup"><span data-stu-id="7580b-582">ROU asset</span></span>                |                                                   |                                                   |                                                   | <span data-ttu-id="7580b-583">0\.00</span><span class="sxs-lookup"><span data-stu-id="7580b-583">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="7580b-584">22,794</span><span class="sxs-lookup"><span data-stu-id="7580b-584">22,794</span></span>                                         |                                                |                                                |                                                | <span data-ttu-id="7580b-585">22,793\.90</span><span class="sxs-lookup"><span data-stu-id="7580b-585">22,793\.90</span></span>                              |
| <span data-ttu-id="7580b-586">7</span><span class="sxs-lookup"><span data-stu-id="7580b-586">7</span></span>          | <span data-ttu-id="7580b-587">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="7580b-587">Finance lease obligation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="7580b-588">0\.00</span><span class="sxs-lookup"><span data-stu-id="7580b-588">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="7580b-589">\-22 794</span><span class="sxs-lookup"><span data-stu-id="7580b-589">\-22,794</span></span>                                       | <span data-ttu-id="7580b-590">1 000</span><span class="sxs-lookup"><span data-stu-id="7580b-590">1,000</span></span>                                          | <span data-ttu-id="7580b-591">\-94\.97</span><span class="sxs-lookup"><span data-stu-id="7580b-591">\-94\.97</span></span>                                       |                                                | <span data-ttu-id="7580b-592">\-21 888\.87</span><span class="sxs-lookup"><span data-stu-id="7580b-592">\-21,888\.87</span></span>                            |
| <span data-ttu-id="7580b-593">8</span><span class="sxs-lookup"><span data-stu-id="7580b-593">8</span></span>          | <span data-ttu-id="7580b-594">Dépenses d’intérêts</span><span class="sxs-lookup"><span data-stu-id="7580b-594">Interest expense</span></span>         |                                                   |                                                   |                                                   | <span data-ttu-id="7580b-595">0\.00</span><span class="sxs-lookup"><span data-stu-id="7580b-595">0\.00</span></span>                   |   |                                                 |                                                |                                                | <span data-ttu-id="7580b-596">94\.97</span><span class="sxs-lookup"><span data-stu-id="7580b-596">94\.97</span></span>                                         |                                                | <span data-ttu-id="7580b-597">94\.97</span><span class="sxs-lookup"><span data-stu-id="7580b-597">94\.97</span></span>                                  |
| <span data-ttu-id="7580b-598">9</span><span class="sxs-lookup"><span data-stu-id="7580b-598">9</span></span>          | <span data-ttu-id="7580b-599">Monétaire</span><span class="sxs-lookup"><span data-stu-id="7580b-599">Cash</span></span>                     |                                                   |                                                   | <span data-ttu-id="7580b-600">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="7580b-600">\-1,008\.00</span></span>                                       | <span data-ttu-id="7580b-601">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="7580b-601">\-1,008\.00</span></span>             |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="7580b-602">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="7580b-602">\-1,008\.00</span></span>                             |
| <span data-ttu-id="7580b-603">10</span><span class="sxs-lookup"><span data-stu-id="7580b-603">10</span></span>         | <span data-ttu-id="7580b-604">Dépenses d’amortissement</span><span class="sxs-lookup"><span data-stu-id="7580b-604">Depreciation expense</span></span>     |                                                   |                                                   |                                                   | <span data-ttu-id="7580b-605">0\.00</span><span class="sxs-lookup"><span data-stu-id="7580b-605">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="7580b-606">949\.75</span><span class="sxs-lookup"><span data-stu-id="7580b-606">949\.75</span></span>                                        | <span data-ttu-id="7580b-607">949\.75</span><span class="sxs-lookup"><span data-stu-id="7580b-607">949\.75</span></span>                                 |
| <span data-ttu-id="7580b-608">11</span><span class="sxs-lookup"><span data-stu-id="7580b-608">11</span></span>         | <span data-ttu-id="7580b-609">Amortissement cumulé</span><span class="sxs-lookup"><span data-stu-id="7580b-609">Accumulated depreciation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="7580b-610">0\.00</span><span class="sxs-lookup"><span data-stu-id="7580b-610">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="7580b-611">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="7580b-611">\-949\.75</span></span>                                      | <span data-ttu-id="7580b-612">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="7580b-612">\-949\.75</span></span>                               |


