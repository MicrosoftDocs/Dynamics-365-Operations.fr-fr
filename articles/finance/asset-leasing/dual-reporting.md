---
title: Double déclaration
description: Cette rubrique vous guide à travers un exemple qui montre comment vous pouvez remplir les exigences à la fois pour le reporting des normes internationales d’information financière (IFRS) et le reporting statutaire dans le bail d’actifs.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseBookMaster
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 86f42f8db707f3b8c62b9ec4c39ad6464f080748
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881154"
---
# <a name="dual-reporting"></a><span data-ttu-id="48e2c-103">Double déclaration</span><span class="sxs-lookup"><span data-stu-id="48e2c-103">Dual reporting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="48e2c-104">Cette rubrique vous guide à travers un exemple qui montre comment vous pouvez remplir les exigences à la fois pour le reporting des normes internationales d’information financière (IFRS) et le reporting statutaire dans le bail d’actifs.</span><span class="sxs-lookup"><span data-stu-id="48e2c-104">This topic guides you through an example that shows how you can fulfill the requirements for both International Financial Reporting Standard (IFRS) reporting and statutory reporting in Asset leasing.</span></span> <span data-ttu-id="48e2c-105">Il est nécessaire d’être familiarisé avec les couches de validation dans Microsoft Dynamics 365 Finance, ce qui rendra l’exemple plus facile à comprendre.</span><span class="sxs-lookup"><span data-stu-id="48e2c-105">Familiarity with posting layers in Microsoft Dynamics 365 Finance is required and will make the example easier to understand.</span></span>

## <a name="example"></a><span data-ttu-id="48e2c-106">Exemple</span><span class="sxs-lookup"><span data-stu-id="48e2c-106">Example</span></span>

<span data-ttu-id="48e2c-107">L’exemple suivant rend compte d’un contrat de location selon le reporting statutaire italien en utilisant à la fois la méthode de la comptabilité de caisse et les méthodes de reporting IFRS.</span><span class="sxs-lookup"><span data-stu-id="48e2c-107">The following example accounts for a lease under Italian statutory reporting by using both the cash-basis method and IFRS reporting methods.</span></span> <span data-ttu-id="48e2c-108">L’entreprise doit établir trois registres pour tenir compte à la fois des exigences légales italiennes et des exigences d’IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="48e2c-108">The company must establish three books to account for both the Italian statutory requirements and the IFRS 16 requirements.</span></span> <span data-ttu-id="48e2c-109">Un registre est requis pour IFRS 16, un registre est requis pour les exigences statutaires et un registre est requis pour annuler automatiquement les écritures statutaires.</span><span class="sxs-lookup"><span data-stu-id="48e2c-109">One book is required for IFRS 16, one book is required for statutory requirements, and one book is required to automatically reverse statutory postings.</span></span> <span data-ttu-id="48e2c-110">Les registres sont configurés comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="48e2c-110">The books are set up as shown in the following tables.</span></span>

<span data-ttu-id="48e2c-111">**Registre IFRS 16**</span><span class="sxs-lookup"><span data-stu-id="48e2c-111">**IFRS 16 book**</span></span>

<span data-ttu-id="48e2c-112">Le registre IFRS 16 est mis en place de manière à être conforme à la norme comptable IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="48e2c-112">The IFRS 16 book is set up so that it complies with the IFRS 16 accounting standard.</span></span> <span data-ttu-id="48e2c-113">Toutes les entrées publiées dans ce livre seront publiées sur une couche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="48e2c-113">All entries that are posted in this book will be posted to a custom layer.</span></span>

| <span data-ttu-id="48e2c-114">Nom</span><span class="sxs-lookup"><span data-stu-id="48e2c-114">Name</span></span>                                    | <span data-ttu-id="48e2c-115">Description</span><span class="sxs-lookup"><span data-stu-id="48e2c-115">Description</span></span>    |
|-----------------------------------------|----------------|
| <span data-ttu-id="48e2c-116">Type de registre</span><span class="sxs-lookup"><span data-stu-id="48e2c-116">Book type</span></span>                               | <span data-ttu-id="48e2c-117">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="48e2c-117">IFRS 16</span></span>        |
| <span data-ttu-id="48e2c-118">Description du registre</span><span class="sxs-lookup"><span data-stu-id="48e2c-118">Book description</span></span>                        | <span data-ttu-id="48e2c-119">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="48e2c-119">IFRS 16</span></span>        |
| <span data-ttu-id="48e2c-120">Couche de comptabilisation</span><span class="sxs-lookup"><span data-stu-id="48e2c-120">Posting Layer</span></span>                           | <span data-ttu-id="48e2c-121">Couche personnalisée 1</span><span class="sxs-lookup"><span data-stu-id="48e2c-121">Custom layer 1</span></span> |
| <span data-ttu-id="48e2c-122">Type de bail</span><span class="sxs-lookup"><span data-stu-id="48e2c-122">Lease Type</span></span>                              | <span data-ttu-id="48e2c-123">Finances</span><span class="sxs-lookup"><span data-stu-id="48e2c-123">Finance</span></span>        |
| <span data-ttu-id="48e2c-124">Structure comptable</span><span class="sxs-lookup"><span data-stu-id="48e2c-124">Accounting Framework</span></span>                    | <span data-ttu-id="48e2c-125">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="48e2c-125">IFRS 16</span></span>        |
| <span data-ttu-id="48e2c-126">Configuration Durée du bail/Durée de vie utile</span><span class="sxs-lookup"><span data-stu-id="48e2c-126">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="48e2c-127">0,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-127">0.00</span></span>           |
| <span data-ttu-id="48e2c-128">Configuration Valeur actuelle/Juste valeur de l’actif</span><span class="sxs-lookup"><span data-stu-id="48e2c-128">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="48e2c-129">0,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-129">0.00</span></span>           |
| <span data-ttu-id="48e2c-130">Seuil à court terme</span><span class="sxs-lookup"><span data-stu-id="48e2c-130">Short-term threshold</span></span>                    | <span data-ttu-id="48e2c-131">12</span><span class="sxs-lookup"><span data-stu-id="48e2c-131">12</span></span>             |
| <span data-ttu-id="48e2c-132">Seuil de faible valeur</span><span class="sxs-lookup"><span data-stu-id="48e2c-132">Low Value Threshold</span></span>                     | <span data-ttu-id="48e2c-133">5,000.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-133">5,000.00</span></span>       |
| <span data-ttu-id="48e2c-134">Payer au fournisseur</span><span class="sxs-lookup"><span data-stu-id="48e2c-134">Pay to Vendor</span></span>                           | <span data-ttu-id="48e2c-135">N°</span><span class="sxs-lookup"><span data-stu-id="48e2c-135">No</span></span>             |

<span data-ttu-id="48e2c-136">**Registre statutaire**</span><span class="sxs-lookup"><span data-stu-id="48e2c-136">**Statutory book**</span></span>

<span data-ttu-id="48e2c-137">Le registre statutaire est un registre de comptabilité de caisse dans lequel la société comptabilise les frais de location comme le montant en espèces payé chaque mois pour le loyer.</span><span class="sxs-lookup"><span data-stu-id="48e2c-137">The statutory book is a cash-basis book where the company will account for the lease expense as the amount of cash that is paid each month for rent.</span></span> <span data-ttu-id="48e2c-138">Ce registre ne produira pas de droit d’utilisation de l’actif (ROU) ni de passif locatif.</span><span class="sxs-lookup"><span data-stu-id="48e2c-138">This book won't produce a right-of-use (ROU) asset or lease liability.</span></span>

| <span data-ttu-id="48e2c-139">Nom</span><span class="sxs-lookup"><span data-stu-id="48e2c-139">Name</span></span>                                    | <span data-ttu-id="48e2c-140">Description</span><span class="sxs-lookup"><span data-stu-id="48e2c-140">Description</span></span> |
|-----------------------------------------|-------------|
| <span data-ttu-id="48e2c-141">Type de registre</span><span class="sxs-lookup"><span data-stu-id="48e2c-141">Book type</span></span>                               | <span data-ttu-id="48e2c-142">Statutaire</span><span class="sxs-lookup"><span data-stu-id="48e2c-142">Statutory</span></span>   |
| <span data-ttu-id="48e2c-143">Description du registre</span><span class="sxs-lookup"><span data-stu-id="48e2c-143">Book description</span></span>                        | <span data-ttu-id="48e2c-144">GAAP local</span><span class="sxs-lookup"><span data-stu-id="48e2c-144">Local GAAP</span></span>  |
| <span data-ttu-id="48e2c-145">Couche de comptabilisation</span><span class="sxs-lookup"><span data-stu-id="48e2c-145">Posting Layer</span></span>                           | <span data-ttu-id="48e2c-146">Actuelle</span><span class="sxs-lookup"><span data-stu-id="48e2c-146">Current</span></span>     |
| <span data-ttu-id="48e2c-147">Type de bail</span><span class="sxs-lookup"><span data-stu-id="48e2c-147">Lease Type</span></span>                              | <span data-ttu-id="48e2c-148">Automatique</span><span class="sxs-lookup"><span data-stu-id="48e2c-148">Automatic</span></span>   |
| <span data-ttu-id="48e2c-149">Structure comptable</span><span class="sxs-lookup"><span data-stu-id="48e2c-149">Accounting Framework</span></span>                    | <span data-ttu-id="48e2c-150">Base de trésorerie</span><span class="sxs-lookup"><span data-stu-id="48e2c-150">Cash basis</span></span>  |
| <span data-ttu-id="48e2c-151">Configuration Durée du bail/Durée de vie utile</span><span class="sxs-lookup"><span data-stu-id="48e2c-151">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="48e2c-152">0,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-152">0.00</span></span>        |
| <span data-ttu-id="48e2c-153">Configuration Valeur actuelle/Juste valeur de l’actif</span><span class="sxs-lookup"><span data-stu-id="48e2c-153">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="48e2c-154">0,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-154">0.00</span></span>        |
| <span data-ttu-id="48e2c-155">Seuil à court terme</span><span class="sxs-lookup"><span data-stu-id="48e2c-155">Short-term threshold</span></span>                    | <span data-ttu-id="48e2c-156">0</span><span class="sxs-lookup"><span data-stu-id="48e2c-156">0</span></span>           |
| <span data-ttu-id="48e2c-157">Seuil de faible valeur</span><span class="sxs-lookup"><span data-stu-id="48e2c-157">Low Value Threshold</span></span>                     | <span data-ttu-id="48e2c-158">0</span><span class="sxs-lookup"><span data-stu-id="48e2c-158">0</span></span>           |
| <span data-ttu-id="48e2c-159">Payer au fournisseur</span><span class="sxs-lookup"><span data-stu-id="48e2c-159">Pay to Vendor</span></span>                           | <span data-ttu-id="48e2c-160">N°</span><span class="sxs-lookup"><span data-stu-id="48e2c-160">No</span></span>          |

<span data-ttu-id="48e2c-161">**Registre de contrepassation statutaire**</span><span class="sxs-lookup"><span data-stu-id="48e2c-161">**Statutory reversal book**</span></span>

<span data-ttu-id="48e2c-162">Le registre de contrepassation statutaire est constitué de la même manière que le registre statutaire.</span><span class="sxs-lookup"><span data-stu-id="48e2c-162">The statutory reversal book is set up in the same way as the statutory book.</span></span>

| <span data-ttu-id="48e2c-163">Nom</span><span class="sxs-lookup"><span data-stu-id="48e2c-163">Name</span></span>                                    | <span data-ttu-id="48e2c-164">Description</span><span class="sxs-lookup"><span data-stu-id="48e2c-164">Description</span></span>                    |
|-----------------------------------------|--------------------------------|
| <span data-ttu-id="48e2c-165">Type de registre</span><span class="sxs-lookup"><span data-stu-id="48e2c-165">Book type</span></span>                               | <span data-ttu-id="48e2c-166">Statutaire – contrepassation</span><span class="sxs-lookup"><span data-stu-id="48e2c-166">Statutory – Reversal</span></span>           |
| <span data-ttu-id="48e2c-167">Description du registre</span><span class="sxs-lookup"><span data-stu-id="48e2c-167">Book description</span></span>                        | <span data-ttu-id="48e2c-168">Registre pour contrepasser le registre statutaire</span><span class="sxs-lookup"><span data-stu-id="48e2c-168">Book to reverse statutory book</span></span> |
| <span data-ttu-id="48e2c-169">Couche de comptabilisation</span><span class="sxs-lookup"><span data-stu-id="48e2c-169">Posting Layer</span></span>                           | <span data-ttu-id="48e2c-170">Couche personnalisée 1</span><span class="sxs-lookup"><span data-stu-id="48e2c-170">Custom layer 1</span></span>                 |
| <span data-ttu-id="48e2c-171">Type de bail</span><span class="sxs-lookup"><span data-stu-id="48e2c-171">Lease Type</span></span>                              | <span data-ttu-id="48e2c-172">Automatique</span><span class="sxs-lookup"><span data-stu-id="48e2c-172">Automatic</span></span>                      |
| <span data-ttu-id="48e2c-173">Structure comptable</span><span class="sxs-lookup"><span data-stu-id="48e2c-173">Accounting Framework</span></span>                    | <span data-ttu-id="48e2c-174">Base de trésorerie</span><span class="sxs-lookup"><span data-stu-id="48e2c-174">Cash basis</span></span>                     |
| <span data-ttu-id="48e2c-175">Configuration Durée du bail/Durée de vie utile</span><span class="sxs-lookup"><span data-stu-id="48e2c-175">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="48e2c-176">0,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-176">0.00</span></span>                           |
| <span data-ttu-id="48e2c-177">Configuration Valeur actuelle/Juste valeur de l’actif</span><span class="sxs-lookup"><span data-stu-id="48e2c-177">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="48e2c-178">0,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-178">0.00</span></span>                           |
| <span data-ttu-id="48e2c-179">Seuil à court terme</span><span class="sxs-lookup"><span data-stu-id="48e2c-179">Short-term threshold</span></span>                    | <span data-ttu-id="48e2c-180">0</span><span class="sxs-lookup"><span data-stu-id="48e2c-180">0</span></span>                              |
| <span data-ttu-id="48e2c-181">Seuil de faible valeur</span><span class="sxs-lookup"><span data-stu-id="48e2c-181">Low Value Threshold</span></span>                     | <span data-ttu-id="48e2c-182">0</span><span class="sxs-lookup"><span data-stu-id="48e2c-182">0</span></span>                              |
| <span data-ttu-id="48e2c-183">Payer au fournisseur</span><span class="sxs-lookup"><span data-stu-id="48e2c-183">Pay to Vendor</span></span>                           | <span data-ttu-id="48e2c-184">N°</span><span class="sxs-lookup"><span data-stu-id="48e2c-184">No</span></span>                             |

<span data-ttu-id="48e2c-185">Pour cet exemple, un bail a été créé avec les paramètres suivants sur les onglets **Général** et **Lignes d’échéancier de paiement**.</span><span class="sxs-lookup"><span data-stu-id="48e2c-185">For this example, a lease has been created that has the following settings on the **General** and **Payment schedule lines** tabs.</span></span>

<span data-ttu-id="48e2c-186">**Onglet Général**</span><span class="sxs-lookup"><span data-stu-id="48e2c-186">**General tab**</span></span>

| <span data-ttu-id="48e2c-187">Champ</span><span class="sxs-lookup"><span data-stu-id="48e2c-187">Field</span></span>                      | <span data-ttu-id="48e2c-188">Valeur</span><span class="sxs-lookup"><span data-stu-id="48e2c-188">Value</span></span>            |
|----------------------------|------------------|
| <span data-ttu-id="48e2c-189">Taux d’emprunt marginal</span><span class="sxs-lookup"><span data-stu-id="48e2c-189">Incremental borrowing rate</span></span> | <span data-ttu-id="48e2c-190">5 %</span><span class="sxs-lookup"><span data-stu-id="48e2c-190">5%</span></span>               |
| <span data-ttu-id="48e2c-191">Date d’entrée en vigueur</span><span class="sxs-lookup"><span data-stu-id="48e2c-191">Commencement date</span></span>          | <span data-ttu-id="48e2c-192">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="48e2c-192">1/1/2020</span></span>         |
| <span data-ttu-id="48e2c-193">Groupe de baux</span><span class="sxs-lookup"><span data-stu-id="48e2c-193">Lease group</span></span>                | <span data-ttu-id="48e2c-194">Bâtiments</span><span class="sxs-lookup"><span data-stu-id="48e2c-194">Buildings</span></span>        |
| <span data-ttu-id="48e2c-195">Fournisseur</span><span class="sxs-lookup"><span data-stu-id="48e2c-195">Vendor</span></span>                     | <span data-ttu-id="48e2c-196">1001</span><span class="sxs-lookup"><span data-stu-id="48e2c-196">1001</span></span>             |
| <span data-ttu-id="48e2c-197">Juste valeur de l’actif</span><span class="sxs-lookup"><span data-stu-id="48e2c-197">Fair value of the asset</span></span>    | <span data-ttu-id="48e2c-198">245,000</span><span class="sxs-lookup"><span data-stu-id="48e2c-198">245,000</span></span>          |
| <span data-ttu-id="48e2c-199">Durée de vie utile de l’actif</span><span class="sxs-lookup"><span data-stu-id="48e2c-199">Asset useful life</span></span>          | <span data-ttu-id="48e2c-200">120</span><span class="sxs-lookup"><span data-stu-id="48e2c-200">120</span></span>              |
| <span data-ttu-id="48e2c-201">Type d’annuité</span><span class="sxs-lookup"><span data-stu-id="48e2c-201">Annuity type</span></span>               | <span data-ttu-id="48e2c-202">Annuité ordinaire</span><span class="sxs-lookup"><span data-stu-id="48e2c-202">Ordinary annuity</span></span> |
| <span data-ttu-id="48e2c-203">Intervalle de composition</span><span class="sxs-lookup"><span data-stu-id="48e2c-203">Compounding interval</span></span>       | <span data-ttu-id="48e2c-204">Tous les mois</span><span class="sxs-lookup"><span data-stu-id="48e2c-204">Monthly</span></span>          |

<span data-ttu-id="48e2c-205">**Onglet Lignes d’échéancier de paiement**</span><span class="sxs-lookup"><span data-stu-id="48e2c-205">**Payment schedule lines tab**</span></span>

| <span data-ttu-id="48e2c-206">Champ</span><span class="sxs-lookup"><span data-stu-id="48e2c-206">Field</span></span>             | <span data-ttu-id="48e2c-207">Valeur</span><span class="sxs-lookup"><span data-stu-id="48e2c-207">Value</span></span>      |
|-------------------|------------|
| <span data-ttu-id="48e2c-208">Date de début</span><span class="sxs-lookup"><span data-stu-id="48e2c-208">Start date</span></span>        | <span data-ttu-id="48e2c-209">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="48e2c-209">1/1/2020</span></span>   |
| <span data-ttu-id="48e2c-210">Intervalle de périodes</span><span class="sxs-lookup"><span data-stu-id="48e2c-210">Period interval</span></span>   | <span data-ttu-id="48e2c-211">Mois</span><span class="sxs-lookup"><span data-stu-id="48e2c-211">Months</span></span>     |
| <span data-ttu-id="48e2c-212">Périodes</span><span class="sxs-lookup"><span data-stu-id="48e2c-212">Periods</span></span>           | <span data-ttu-id="48e2c-213">24</span><span class="sxs-lookup"><span data-stu-id="48e2c-213">24</span></span>         |
| <span data-ttu-id="48e2c-214">Date de fin</span><span class="sxs-lookup"><span data-stu-id="48e2c-214">End date</span></span>          | <span data-ttu-id="48e2c-215">31/12/2020</span><span class="sxs-lookup"><span data-stu-id="48e2c-215">12/31/2020</span></span> |
| <span data-ttu-id="48e2c-216">Fréquence de paiement</span><span class="sxs-lookup"><span data-stu-id="48e2c-216">Payment frequency</span></span> | <span data-ttu-id="48e2c-217">Tous les mois</span><span class="sxs-lookup"><span data-stu-id="48e2c-217">Monthly</span></span>    |
| <span data-ttu-id="48e2c-218">Montant du paiement</span><span class="sxs-lookup"><span data-stu-id="48e2c-218">Payment amount</span></span>    | <span data-ttu-id="48e2c-219">1 000</span><span class="sxs-lookup"><span data-stu-id="48e2c-219">1,000</span></span>      |

<span data-ttu-id="48e2c-220">Pour tenir compte de ce bail sous deux structures, vous utilisez une couche de validation actuelle et une couche de validation personnalisée.</span><span class="sxs-lookup"><span data-stu-id="48e2c-220">To account for this lease under two frameworks, you use a current posting layer and a custom posting layer.</span></span> <span data-ttu-id="48e2c-221">Le tableau suivant montre un exemple de chaque écriture de journal nécessaire pour représenter fidèlement les données financières selon chaque norme de reporting.</span><span class="sxs-lookup"><span data-stu-id="48e2c-221">The following table shows an example of every journal entry that required to fairly represent the financials under each reporting standard.</span></span> <span data-ttu-id="48e2c-222">Une description détaillée de chaque écriture de journal pour le premier mois du bail est fournie par la suite.</span><span class="sxs-lookup"><span data-stu-id="48e2c-222">A detailed description of each journal entry for the first month of the lease is provided afterward.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="48e2c-223">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="48e2c-223">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="48e2c-224">Description</span><span class="sxs-lookup"><span data-stu-id="48e2c-224">Description</span></span></th>
<th colspan='3'><span data-ttu-id="48e2c-225">Registre statutaire (couche actuelle)</span><span class="sxs-lookup"><span data-stu-id="48e2c-225">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="48e2c-226">Total de la couche actuelle</span><span class="sxs-lookup"><span data-stu-id="48e2c-226">Current layer total</span></span></th>
<th><span data-ttu-id="48e2c-227">Registre de contrepassation (couche personnalisée)</span><span class="sxs-lookup"><span data-stu-id="48e2c-227">Reversal book (custom layer)</span></span></th>
<th colspan='4'><span data-ttu-id="48e2c-228">Registre IFRS 16 (couche personnalisée)</span><span class="sxs-lookup"><span data-stu-id="48e2c-228">IFRS 16 book (custom layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="48e2c-229">Couche actuelle + total de la couche personnalisée</span><span class="sxs-lookup"><span data-stu-id="48e2c-229">Current layer + custom layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="48e2c-230">JE-100</span><span class="sxs-lookup"><span data-stu-id="48e2c-230">JE-100</span></span></th>
<th><span data-ttu-id="48e2c-231">JE-110</span><span class="sxs-lookup"><span data-stu-id="48e2c-231">JE-110</span></span></th>
<th><span data-ttu-id="48e2c-232">JE-120</span><span class="sxs-lookup"><span data-stu-id="48e2c-232">JE-120</span></span></th>
<th><span data-ttu-id="48e2c-233">JE-130</span><span class="sxs-lookup"><span data-stu-id="48e2c-233">JE-130</span></span></th>
<th><span data-ttu-id="48e2c-234">JE-140</span><span class="sxs-lookup"><span data-stu-id="48e2c-234">JE-140</span></span></th>
<th><span data-ttu-id="48e2c-235">JE-150</span><span class="sxs-lookup"><span data-stu-id="48e2c-235">JE-150</span></span></th>
<th><span data-ttu-id="48e2c-236">JE-160</span><span class="sxs-lookup"><span data-stu-id="48e2c-236">JE-160</span></span></th>
<th><span data-ttu-id="48e2c-237">JE-170</span><span class="sxs-lookup"><span data-stu-id="48e2c-237">JE-170</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="48e2c-238">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="48e2c-238">Dr (Cr)</span></span></th>
<th><span data-ttu-id="48e2c-239">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="48e2c-239">Dr (Cr)</span></span></th>
<th><span data-ttu-id="48e2c-240">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="48e2c-240">Dr (Cr)</span></span></th>
<th><span data-ttu-id="48e2c-241">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="48e2c-241">Dr (Cr)</span></span></th>
<th><span data-ttu-id="48e2c-242">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="48e2c-242">Dr (Cr)</span></span></th>
<th><span data-ttu-id="48e2c-243">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="48e2c-243">Dr (Cr)</span></span></th>
<th><span data-ttu-id="48e2c-244">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="48e2c-244">Dr (Cr)</span></span></th>
<th><span data-ttu-id="48e2c-245">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="48e2c-245">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="48e2c-246">1</span><span class="sxs-lookup"><span data-stu-id="48e2c-246">1</span></span></td>
<td><span data-ttu-id="48e2c-247">Dépense de bail</span><span class="sxs-lookup"><span data-stu-id="48e2c-247">Lease expense</span></span></td>
<td><span data-ttu-id="48e2c-248">1,000.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-248">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="48e2c-249">1,000.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-249">1,000.00</span></span></td>
<td><span data-ttu-id="48e2c-250">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-250">-1,000.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="48e2c-251">0,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-251">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="48e2c-252">2</span><span class="sxs-lookup"><span data-stu-id="48e2c-252">2</span></span></td>
<td><span data-ttu-id="48e2c-253">Frais bancaires</span><span class="sxs-lookup"><span data-stu-id="48e2c-253">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="48e2c-254">3.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-254">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="48e2c-255">3.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-255">3.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="48e2c-256">3.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-256">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="48e2c-257">3</span><span class="sxs-lookup"><span data-stu-id="48e2c-257">3</span></span></td>
<td><span data-ttu-id="48e2c-258">Dépenses de TVA</span><span class="sxs-lookup"><span data-stu-id="48e2c-258">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="48e2c-259">5.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-259">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="48e2c-260">5.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-260">5.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="48e2c-261">5.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-261">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="48e2c-262">4</span><span class="sxs-lookup"><span data-stu-id="48e2c-262">4</span></span></td>
<td><span data-ttu-id="48e2c-263">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="48e2c-263">Clearing account</span></span></td>
<td><span data-ttu-id="48e2c-264">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-264">-1,000.00</span></span></td>
<td><span data-ttu-id="48e2c-265">1,000.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-265">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="48e2c-266">0,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-266">0.00</span></span></td>
<td><span data-ttu-id="48e2c-267">1,000.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-267">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="48e2c-268">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-268">-1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="48e2c-269">0,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-269">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="48e2c-270">5</span><span class="sxs-lookup"><span data-stu-id="48e2c-270">5</span></span></td>
<td><span data-ttu-id="48e2c-271">Module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="48e2c-271">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="48e2c-272">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-272">-1,008.00</span></span></td>
<td><span data-ttu-id="48e2c-273">1,008.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-273">1,008.00</span></span></td>
<td><span data-ttu-id="48e2c-274">0,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-274">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="48e2c-275">0,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-275">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="48e2c-276">6</span><span class="sxs-lookup"><span data-stu-id="48e2c-276">6</span></span></td>
<td><span data-ttu-id="48e2c-277">Droit d’utilisation de l’actif</span><span class="sxs-lookup"><span data-stu-id="48e2c-277">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="48e2c-278">0,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-278">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="48e2c-279">22,794.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-279">22,794.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="48e2c-280">22,793.90</span><span class="sxs-lookup"><span data-stu-id="48e2c-280">22,793.90</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="48e2c-281">7</span><span class="sxs-lookup"><span data-stu-id="48e2c-281">7</span></span></td>
<td><span data-ttu-id="48e2c-282">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="48e2c-282">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="48e2c-283">0,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-283">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="48e2c-284">-22 794,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-284">-22,794.00</span></span></td>
<td><span data-ttu-id="48e2c-285">1,000.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-285">1,000.00</span></span></td>
<td><span data-ttu-id="48e2c-286">-94,97</span><span class="sxs-lookup"><span data-stu-id="48e2c-286">-94.97</span></span></td>
<td></td>
<td><span data-ttu-id="48e2c-287">-21 888,87</span><span class="sxs-lookup"><span data-stu-id="48e2c-287">-21,888.87</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="48e2c-288">8</span><span class="sxs-lookup"><span data-stu-id="48e2c-288">8</span></span></td>
<td><span data-ttu-id="48e2c-289">Dépenses d’intérêts</span><span class="sxs-lookup"><span data-stu-id="48e2c-289">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="48e2c-290">0,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-290">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="48e2c-291">94.97</span><span class="sxs-lookup"><span data-stu-id="48e2c-291">94.97</span></span></td>
<td></td>
<td><span data-ttu-id="48e2c-292">94.97</span><span class="sxs-lookup"><span data-stu-id="48e2c-292">94.97</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="48e2c-293">9</span><span class="sxs-lookup"><span data-stu-id="48e2c-293">9</span></span></td>
<td><span data-ttu-id="48e2c-294">Monétaire</span><span class="sxs-lookup"><span data-stu-id="48e2c-294">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="48e2c-295">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-295">-1,008.00</span></span></td>
<td><span data-ttu-id="48e2c-296">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-296">-1,008.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="48e2c-297">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-297">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="48e2c-298">10</span><span class="sxs-lookup"><span data-stu-id="48e2c-298">10</span></span></td>
<td><span data-ttu-id="48e2c-299">Dépenses d’amortissement</span><span class="sxs-lookup"><span data-stu-id="48e2c-299">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="48e2c-300">0,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-300">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="48e2c-301">949.75</span><span class="sxs-lookup"><span data-stu-id="48e2c-301">949.75</span></span></td>
<td><span data-ttu-id="48e2c-302">949.75</span><span class="sxs-lookup"><span data-stu-id="48e2c-302">949.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="48e2c-303">11</span><span class="sxs-lookup"><span data-stu-id="48e2c-303">11</span></span></td>
<td><span data-ttu-id="48e2c-304">Amortissement cumulé</span><span class="sxs-lookup"><span data-stu-id="48e2c-304">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="48e2c-305">0,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-305">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="48e2c-306">-949,75</span><span class="sxs-lookup"><span data-stu-id="48e2c-306">-949.75</span></span></td>
<td><span data-ttu-id="48e2c-307">-949,75</span><span class="sxs-lookup"><span data-stu-id="48e2c-307">-949.75</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="48e2c-308">Comme le montre le tableau précédent, trois registres sont tenus pour déclarer à la fois le reporting statutaire et le reporting IFRS.</span><span class="sxs-lookup"><span data-stu-id="48e2c-308">As the preceding table shows, three books are required to report under both statutory reporting and IFRS reporting.</span></span>

- <span data-ttu-id="48e2c-309">Le registre statutaire enregistre le paiement de location selon les règles de comptabilité de caisse sous la couche actuelle.</span><span class="sxs-lookup"><span data-stu-id="48e2c-309">The statutory book records the lease payment according to the rules for cash-basis accounting under the current layer.</span></span>
- <span data-ttu-id="48e2c-310">Le registre de contrepassation statutaire annule les écritures au journal statutaire.</span><span class="sxs-lookup"><span data-stu-id="48e2c-310">The statutory reversal book reverses the statutory journal entries.</span></span>
- <span data-ttu-id="48e2c-311">Le registre IFRS 16 crée les écritures de journal requises en vertu d’IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="48e2c-311">The IFRS 16 book creates the journal entries that are required under IFRS 16.</span></span>

<span data-ttu-id="48e2c-312">Vous ne devez saisir un bail qu’une seule fois.</span><span class="sxs-lookup"><span data-stu-id="48e2c-312">You must enter a lease only one time.</span></span> <span data-ttu-id="48e2c-313">Vous pouvez ensuite ouvrir la page **Registres** pour voir tous les registres associés au bail.</span><span class="sxs-lookup"><span data-stu-id="48e2c-313">You can then open the **Books** page to see all the books that are associated with the lease.</span></span>

> [!NOTE]
> <span data-ttu-id="48e2c-314">Lorsque vous créez les registres, tous les trois doivent être associés au même enregistrement de bail.</span><span class="sxs-lookup"><span data-stu-id="48e2c-314">When you create the books, all three of them must be associated with the same lease record.</span></span>

<span data-ttu-id="48e2c-315">La première écriture de journal enregistre les frais de location dans le registre statutaire.</span><span class="sxs-lookup"><span data-stu-id="48e2c-315">The first journal entry records the lease expense under the statutory book.</span></span> <span data-ttu-id="48e2c-316">Vous pouvez créer les paiements soit par lots, soit en sélectionnant l’échéancier de paiement dans le registre statutaire.</span><span class="sxs-lookup"><span data-stu-id="48e2c-316">You can create the payments either in a batch or by selecting the payment schedule in the statutory book.</span></span>

<span data-ttu-id="48e2c-317">Pour cet exemple, l’écriture de journal suivante est produite pour le registre statutaire à partir de l’échéancier de paiement.</span><span class="sxs-lookup"><span data-stu-id="48e2c-317">For this example, the following journal entry is produced for the statutory book from the payment schedule.</span></span>

### <a name="lease-payment--1312020--je-100"></a><span data-ttu-id="48e2c-318">Paiement de location – 31/01/2020 – JE 100</span><span class="sxs-lookup"><span data-stu-id="48e2c-318">Lease payment – 1/31/2020 – JE 100</span></span>

| <span data-ttu-id="48e2c-319">Type de compte</span><span class="sxs-lookup"><span data-stu-id="48e2c-319">Account type</span></span> | <span data-ttu-id="48e2c-320">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="48e2c-320">Account number</span></span> | <span data-ttu-id="48e2c-321">Couche</span><span class="sxs-lookup"><span data-stu-id="48e2c-321">Layer</span></span>   | <span data-ttu-id="48e2c-322">Description du compte</span><span class="sxs-lookup"><span data-stu-id="48e2c-322">Account description</span></span> | <span data-ttu-id="48e2c-323">Débit</span><span class="sxs-lookup"><span data-stu-id="48e2c-323">Debit</span></span>    | <span data-ttu-id="48e2c-324">Crédit</span><span class="sxs-lookup"><span data-stu-id="48e2c-324">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="48e2c-325">Registre</span><span class="sxs-lookup"><span data-stu-id="48e2c-325">Ledger</span></span>       | <span data-ttu-id="48e2c-326">1</span><span class="sxs-lookup"><span data-stu-id="48e2c-326">1</span></span>              | <span data-ttu-id="48e2c-327">Actuelle</span><span class="sxs-lookup"><span data-stu-id="48e2c-327">Current</span></span> | <span data-ttu-id="48e2c-328">Dépense de bail</span><span class="sxs-lookup"><span data-stu-id="48e2c-328">Lease expense</span></span>       | <span data-ttu-id="48e2c-329">1,000.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-329">1,000.00</span></span> |          |
| <span data-ttu-id="48e2c-330">Registre</span><span class="sxs-lookup"><span data-stu-id="48e2c-330">Ledger</span></span>       | <span data-ttu-id="48e2c-331">4</span><span class="sxs-lookup"><span data-stu-id="48e2c-331">4</span></span>              | <span data-ttu-id="48e2c-332">Actuelle</span><span class="sxs-lookup"><span data-stu-id="48e2c-332">Current</span></span> | <span data-ttu-id="48e2c-333">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="48e2c-333">Clearing account</span></span>    |          | <span data-ttu-id="48e2c-334">1,000.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-334">1,000.00</span></span> |

<span data-ttu-id="48e2c-335">Un commis aux comptes fournisseurs utilise la fonctionnalité standard de Dynamics 365 pour créer une facture pour payer le bail en dehors de la location d’actifs.</span><span class="sxs-lookup"><span data-stu-id="48e2c-335">An Accounts payable clerk uses standard Dynamics 365 functionality to create an invoice to pay for the lease outside Asset leasing.</span></span> <span data-ttu-id="48e2c-336">Cependant, au lieu de sélectionner **Frais de location** comme compte de débit, le commis aux comptes fournisseurs sélectionne un compte de compensation pour générer l’écriture suivante.</span><span class="sxs-lookup"><span data-stu-id="48e2c-336">However, instead of selecting **Lease expense** as the debit account, the Accounts payable clerk selects a clearing account to generate the following entry.</span></span>

### <a name="ap-process--1312020--je-110"></a><span data-ttu-id="48e2c-337">Processus AP – 31/01/2020 – JE 110</span><span class="sxs-lookup"><span data-stu-id="48e2c-337">AP process – 1/31/2020 – JE 110</span></span>

| <span data-ttu-id="48e2c-338">Type de compte</span><span class="sxs-lookup"><span data-stu-id="48e2c-338">Account type</span></span> | <span data-ttu-id="48e2c-339">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="48e2c-339">Account number</span></span> | <span data-ttu-id="48e2c-340">Couche</span><span class="sxs-lookup"><span data-stu-id="48e2c-340">Layer</span></span>   | <span data-ttu-id="48e2c-341">Description du compte</span><span class="sxs-lookup"><span data-stu-id="48e2c-341">Account description</span></span> | <span data-ttu-id="48e2c-342">Débit</span><span class="sxs-lookup"><span data-stu-id="48e2c-342">Debit</span></span>    | <span data-ttu-id="48e2c-343">Crédit</span><span class="sxs-lookup"><span data-stu-id="48e2c-343">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="48e2c-344">Registre</span><span class="sxs-lookup"><span data-stu-id="48e2c-344">Ledger</span></span>       | <span data-ttu-id="48e2c-345">4</span><span class="sxs-lookup"><span data-stu-id="48e2c-345">4</span></span>              | <span data-ttu-id="48e2c-346">Actuelle</span><span class="sxs-lookup"><span data-stu-id="48e2c-346">Current</span></span> | <span data-ttu-id="48e2c-347">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="48e2c-347">Clearing account</span></span>    | <span data-ttu-id="48e2c-348">1,000.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-348">1,000.00</span></span> |          |
| <span data-ttu-id="48e2c-349">Registre</span><span class="sxs-lookup"><span data-stu-id="48e2c-349">Ledger</span></span>       | <span data-ttu-id="48e2c-350">2</span><span class="sxs-lookup"><span data-stu-id="48e2c-350">2</span></span>              | <span data-ttu-id="48e2c-351">Actuelle</span><span class="sxs-lookup"><span data-stu-id="48e2c-351">Current</span></span> | <span data-ttu-id="48e2c-352">Frais bancaires</span><span class="sxs-lookup"><span data-stu-id="48e2c-352">Bank fee</span></span>            | <span data-ttu-id="48e2c-353">3.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-353">3.00</span></span>     |          |
| <span data-ttu-id="48e2c-354">Registre</span><span class="sxs-lookup"><span data-stu-id="48e2c-354">Ledger</span></span>       | <span data-ttu-id="48e2c-355">3</span><span class="sxs-lookup"><span data-stu-id="48e2c-355">3</span></span>              | <span data-ttu-id="48e2c-356">Actuelle</span><span class="sxs-lookup"><span data-stu-id="48e2c-356">Current</span></span> | <span data-ttu-id="48e2c-357">Dépenses de TVA</span><span class="sxs-lookup"><span data-stu-id="48e2c-357">VAT expense</span></span>         | <span data-ttu-id="48e2c-358">5.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-358">5.00</span></span>     |          |
| <span data-ttu-id="48e2c-359">Fournisseur</span><span class="sxs-lookup"><span data-stu-id="48e2c-359">Vendor</span></span>       | <span data-ttu-id="48e2c-360">5</span><span class="sxs-lookup"><span data-stu-id="48e2c-360">5</span></span>              | <span data-ttu-id="48e2c-361">Actuelle</span><span class="sxs-lookup"><span data-stu-id="48e2c-361">Current</span></span> | <span data-ttu-id="48e2c-362">Module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="48e2c-362">Accounts payable</span></span>    |          | <span data-ttu-id="48e2c-363">1,008.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-363">1,008.00</span></span> |

<span data-ttu-id="48e2c-364">Lorsque la déclaration est délivrée au fournisseur, vous suivez le processus de paiement régulier.</span><span class="sxs-lookup"><span data-stu-id="48e2c-364">When the statement is issued to the vendor, you follow the regular payment process.</span></span> <span data-ttu-id="48e2c-365">Au cours de ce processus, l’écriture de journal suivante est générée.</span><span class="sxs-lookup"><span data-stu-id="48e2c-365">During this process, the following journal entry is generated.</span></span>

### <a name="cash-payment--1312020--je-120"></a><span data-ttu-id="48e2c-366">Paiement en espèces – 31/01/2020 – JE 120</span><span class="sxs-lookup"><span data-stu-id="48e2c-366">Cash payment – 1/31/2020 – JE 120</span></span>

| <span data-ttu-id="48e2c-367">Type de compte</span><span class="sxs-lookup"><span data-stu-id="48e2c-367">Account type</span></span> | <span data-ttu-id="48e2c-368">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="48e2c-368">Account number</span></span> | <span data-ttu-id="48e2c-369">Couche</span><span class="sxs-lookup"><span data-stu-id="48e2c-369">Layer</span></span>   | <span data-ttu-id="48e2c-370">Description du compte</span><span class="sxs-lookup"><span data-stu-id="48e2c-370">Account description</span></span> | <span data-ttu-id="48e2c-371">Débit</span><span class="sxs-lookup"><span data-stu-id="48e2c-371">Debit</span></span>    | <span data-ttu-id="48e2c-372">Crédit</span><span class="sxs-lookup"><span data-stu-id="48e2c-372">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="48e2c-373">Fournisseur</span><span class="sxs-lookup"><span data-stu-id="48e2c-373">Vendor</span></span>       | <span data-ttu-id="48e2c-374">5</span><span class="sxs-lookup"><span data-stu-id="48e2c-374">5</span></span>              | <span data-ttu-id="48e2c-375">Actuelle</span><span class="sxs-lookup"><span data-stu-id="48e2c-375">Current</span></span> | <span data-ttu-id="48e2c-376">Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="48e2c-376">Accounts Payable</span></span>    | <span data-ttu-id="48e2c-377">1,008.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-377">1,008.00</span></span> |          |
| <span data-ttu-id="48e2c-378">Banque</span><span class="sxs-lookup"><span data-stu-id="48e2c-378">Bank</span></span>         | <span data-ttu-id="48e2c-379">9</span><span class="sxs-lookup"><span data-stu-id="48e2c-379">9</span></span>              | <span data-ttu-id="48e2c-380">Actuelle</span><span class="sxs-lookup"><span data-stu-id="48e2c-380">Current</span></span> | <span data-ttu-id="48e2c-381">Monétaire</span><span class="sxs-lookup"><span data-stu-id="48e2c-381">Cash</span></span>                |          | <span data-ttu-id="48e2c-382">1,008.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-382">1,008.00</span></span> |

<span data-ttu-id="48e2c-383">À ce stade, vous avez pleinement pris en compte ce bail conformément aux exigences légales en matière de rapports et pouvez générer une balance comptable en utilisant la couche actuelle.</span><span class="sxs-lookup"><span data-stu-id="48e2c-383">At this point, you've fully accounted for this lease under statutory reporting requirements and can generate a trial balance by using the current layer.</span></span> <span data-ttu-id="48e2c-384">Le système renvoie une balance comptable qui a les chiffres suivants.</span><span class="sxs-lookup"><span data-stu-id="48e2c-384">The system returns a trial balance that has the following figures.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="48e2c-385">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="48e2c-385">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="48e2c-386">Description</span><span class="sxs-lookup"><span data-stu-id="48e2c-386">Description</span></span></th>
<th colspan='3'><span data-ttu-id="48e2c-387">Registre statutaire (couche actuelle)</span><span class="sxs-lookup"><span data-stu-id="48e2c-387">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="48e2c-388">Total de la couche actuelle</span><span class="sxs-lookup"><span data-stu-id="48e2c-388">Current layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="48e2c-389">JE-100</span><span class="sxs-lookup"><span data-stu-id="48e2c-389">JE-100</span></span></th>
<th><span data-ttu-id="48e2c-390">JE-110</span><span class="sxs-lookup"><span data-stu-id="48e2c-390">JE-110</span></span></th>
<th><span data-ttu-id="48e2c-391">JE-120</span><span class="sxs-lookup"><span data-stu-id="48e2c-391">JE-120</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="48e2c-392">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="48e2c-392">Dr (Cr)</span></span></th>
<th><span data-ttu-id="48e2c-393">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="48e2c-393">Dr (Cr)</span></span></th>
<th><span data-ttu-id="48e2c-394">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="48e2c-394">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="48e2c-395">1</span><span class="sxs-lookup"><span data-stu-id="48e2c-395">1</span></span></td>
<td><span data-ttu-id="48e2c-396">Dépense de bail</span><span class="sxs-lookup"><span data-stu-id="48e2c-396">Lease expense</span></span></td>
<td><span data-ttu-id="48e2c-397">1,000.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-397">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="48e2c-398">1,000.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-398">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="48e2c-399">2</span><span class="sxs-lookup"><span data-stu-id="48e2c-399">2</span></span></td>
<td><span data-ttu-id="48e2c-400">Frais bancaires</span><span class="sxs-lookup"><span data-stu-id="48e2c-400">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="48e2c-401">3.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-401">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="48e2c-402">3.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-402">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="48e2c-403">3</span><span class="sxs-lookup"><span data-stu-id="48e2c-403">3</span></span></td>
<td><span data-ttu-id="48e2c-404">Dépenses de TVA</span><span class="sxs-lookup"><span data-stu-id="48e2c-404">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="48e2c-405">5.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-405">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="48e2c-406">5.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-406">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="48e2c-407">4</span><span class="sxs-lookup"><span data-stu-id="48e2c-407">4</span></span></td>
<td><span data-ttu-id="48e2c-408">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="48e2c-408">Clearing account</span></span></td>
<td><span data-ttu-id="48e2c-409">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-409">-1,000.00</span></span></td>
<td><span data-ttu-id="48e2c-410">1,000.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-410">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="48e2c-411">0,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-411">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="48e2c-412">5</span><span class="sxs-lookup"><span data-stu-id="48e2c-412">5</span></span></td>
<td><span data-ttu-id="48e2c-413">Module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="48e2c-413">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="48e2c-414">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-414">-1,008.00</span></span></td>
<td><span data-ttu-id="48e2c-415">1,008.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-415">1,008.00</span></span></td>
<td><span data-ttu-id="48e2c-416">0,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-416">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="48e2c-417">6</span><span class="sxs-lookup"><span data-stu-id="48e2c-417">6</span></span></td>
<td><span data-ttu-id="48e2c-418">Droit d’utilisation de l’actif</span><span class="sxs-lookup"><span data-stu-id="48e2c-418">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="48e2c-419">0,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-419">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="48e2c-420">7</span><span class="sxs-lookup"><span data-stu-id="48e2c-420">7</span></span></td>
<td><span data-ttu-id="48e2c-421">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="48e2c-421">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="48e2c-422">0,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-422">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="48e2c-423">8</span><span class="sxs-lookup"><span data-stu-id="48e2c-423">8</span></span></td>
<td><span data-ttu-id="48e2c-424">Dépenses d’intérêts</span><span class="sxs-lookup"><span data-stu-id="48e2c-424">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="48e2c-425">0,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-425">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="48e2c-426">9</span><span class="sxs-lookup"><span data-stu-id="48e2c-426">9</span></span></td>
<td><span data-ttu-id="48e2c-427">Monétaire</span><span class="sxs-lookup"><span data-stu-id="48e2c-427">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="48e2c-428">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-428">-1,008.00</span></span></td>
<td><span data-ttu-id="48e2c-429">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-429">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="48e2c-430">10</span><span class="sxs-lookup"><span data-stu-id="48e2c-430">10</span></span></td>
<td><span data-ttu-id="48e2c-431">Dépenses d’amortissement</span><span class="sxs-lookup"><span data-stu-id="48e2c-431">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="48e2c-432">0,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-432">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="48e2c-433">11</span><span class="sxs-lookup"><span data-stu-id="48e2c-433">11</span></span></td>
<td><span data-ttu-id="48e2c-434">Amortissement cumulé</span><span class="sxs-lookup"><span data-stu-id="48e2c-434">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="48e2c-435">0,00</span><span class="sxs-lookup"><span data-stu-id="48e2c-435">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="48e2c-436">Si vous souhaitez utiliser les chiffres IFRS 16 pour exécuter la même balance comptable, les écritures comptables statutaires doivent être contrepassées et les écritures comptables IFRS 16 doivent être enregistrées.</span><span class="sxs-lookup"><span data-stu-id="48e2c-436">If you want to use the IFRS 16 figures to run the same trial balance, the statutory accounting journal entries must be reversed, and the IFRS 16 journal entries must be posted.</span></span> <span data-ttu-id="48e2c-437">Pour contrepasser les écritures statutaires, cet exemple inclut un registre de contrepassation statutaire qui a la même configuration que le registre statutaire mais un profil de validation opposé.</span><span class="sxs-lookup"><span data-stu-id="48e2c-437">To reverse the statutory journal entries, this example includes a statutory reversal book that has the same setup as the statutory book but an opposite posting profile.</span></span> <span data-ttu-id="48e2c-438">Par exemple, le registre statutaire *a débité* un compte de charges de location, mais le registre de contrepassation va *créditer* ce compte.</span><span class="sxs-lookup"><span data-stu-id="48e2c-438">For example, the statutory book *debited* a lease expense account, but the reversal book will *credit* this account.</span></span> <span data-ttu-id="48e2c-439">Ces relations sont facilement définies dans les comptes de comptabilisation de la location d’actifs sur la page **Paramètres de location d’actifs** (**Location d’actifs \> Configurer \> Paramètres de location d’actifs**).</span><span class="sxs-lookup"><span data-stu-id="48e2c-439">These relationships are easily defined in the Asset leasing posting accounts on the **Asset leasing parameters** page (**Asset leasing \> Setup \> Asset leasing parameters**).</span></span>

<span data-ttu-id="48e2c-440">Lorsque le même processus que celui utilisé pour le registre statutaire est utilisé pour le registre de contrepassation, l’écriture de journal suivante est produite.</span><span class="sxs-lookup"><span data-stu-id="48e2c-440">When the same process that was used for the statutory book is used for the reversal book, the following journal entry is produced.</span></span> <span data-ttu-id="48e2c-441">La différence est que le registre de contrepassation comptabilise les écritures de contrepassation du registre statutaire.</span><span class="sxs-lookup"><span data-stu-id="48e2c-441">The difference is that the reversal book books the reversing entries from the statutory book.</span></span> <span data-ttu-id="48e2c-442">Les écritures de contrepassation sont également apportées à la couche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="48e2c-442">The reversing entries are also made to the custom layer.</span></span> <span data-ttu-id="48e2c-443">Lorsqu’une balance comptable est exécutée au niveau de la couche actuelle, les écritures de journal de contrepassation ne sont pas incluses.</span><span class="sxs-lookup"><span data-stu-id="48e2c-443">When a trial balance is run at the current layer, the reversing journal entries aren't included.</span></span>

### <a name="lease-payment--1312020--je-130"></a><span data-ttu-id="48e2c-444">Paiement de location – 31/01/2020 – JE 130</span><span class="sxs-lookup"><span data-stu-id="48e2c-444">Lease payment – 1/31/2020 – JE 130</span></span>

| <span data-ttu-id="48e2c-445">Type de compte</span><span class="sxs-lookup"><span data-stu-id="48e2c-445">Account type</span></span> | <span data-ttu-id="48e2c-446">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="48e2c-446">Account number</span></span> | <span data-ttu-id="48e2c-447">Couche</span><span class="sxs-lookup"><span data-stu-id="48e2c-447">Layer</span></span>  | <span data-ttu-id="48e2c-448">Description du compte</span><span class="sxs-lookup"><span data-stu-id="48e2c-448">Account description</span></span> | <span data-ttu-id="48e2c-449">Débit</span><span class="sxs-lookup"><span data-stu-id="48e2c-449">Debit</span></span>    | <span data-ttu-id="48e2c-450">Crédit</span><span class="sxs-lookup"><span data-stu-id="48e2c-450">Credit</span></span>   |
|--------------|----------------|--------|---------------------|----------|----------|
| <span data-ttu-id="48e2c-451">Registre</span><span class="sxs-lookup"><span data-stu-id="48e2c-451">Ledger</span></span>       | <span data-ttu-id="48e2c-452">4</span><span class="sxs-lookup"><span data-stu-id="48e2c-452">4</span></span>              | <span data-ttu-id="48e2c-453">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="48e2c-453">Custom</span></span> | <span data-ttu-id="48e2c-454">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="48e2c-454">Clearing account</span></span>    | <span data-ttu-id="48e2c-455">1,000.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-455">1,000.00</span></span> |          |
| <span data-ttu-id="48e2c-456">Registre</span><span class="sxs-lookup"><span data-stu-id="48e2c-456">Ledger</span></span>       | <span data-ttu-id="48e2c-457">1</span><span class="sxs-lookup"><span data-stu-id="48e2c-457">1</span></span>              | <span data-ttu-id="48e2c-458">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="48e2c-458">Custom</span></span> | <span data-ttu-id="48e2c-459">Dépense de bail</span><span class="sxs-lookup"><span data-stu-id="48e2c-459">Lease expense</span></span>       |          | <span data-ttu-id="48e2c-460">1,000.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-460">1,000.00</span></span> |

<span data-ttu-id="48e2c-461">Maintenant que vous avez éliminé les écritures de journal statutaires, vous allez enregistrer toutes les écritures de journal requises par IFRS 16 dans le livre IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="48e2c-461">Now that you've eliminated the statutory journal entries, you will book all the journal entries that IFRS 16 requires in the IFRS 16 book.</span></span> <span data-ttu-id="48e2c-462">Ces écritures comprennent la reconnaissance initiale du droit d’utilisation de l’actif et du passif, ainsi que l’enregistrement des intérêts et des amortissements.</span><span class="sxs-lookup"><span data-stu-id="48e2c-462">These entries include the initial recognition of the ROU asset and the liability, and the record of interest and depreciation.</span></span>

### <a name="initial-recognition--112020--je-140"></a><span data-ttu-id="48e2c-463">Reconnaissance initiale – 1/1/2020 – JE 140</span><span class="sxs-lookup"><span data-stu-id="48e2c-463">Initial recognition – 1/1/2020 – JE 140</span></span>

| <span data-ttu-id="48e2c-464">Type de compte</span><span class="sxs-lookup"><span data-stu-id="48e2c-464">Account type</span></span> | <span data-ttu-id="48e2c-465">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="48e2c-465">Account number</span></span> | <span data-ttu-id="48e2c-466">Couche</span><span class="sxs-lookup"><span data-stu-id="48e2c-466">Layer</span></span>  | <span data-ttu-id="48e2c-467">Description du compte</span><span class="sxs-lookup"><span data-stu-id="48e2c-467">Account description</span></span>      | <span data-ttu-id="48e2c-468">Débit</span><span class="sxs-lookup"><span data-stu-id="48e2c-468">Debit</span></span>     | <span data-ttu-id="48e2c-469">Crédit</span><span class="sxs-lookup"><span data-stu-id="48e2c-469">Credit</span></span>    |
|--------------|----------------|--------|--------------------------|-----------|-----------|
| <span data-ttu-id="48e2c-470">Registre</span><span class="sxs-lookup"><span data-stu-id="48e2c-470">Ledger</span></span>       | <span data-ttu-id="48e2c-471">6</span><span class="sxs-lookup"><span data-stu-id="48e2c-471">6</span></span>              | <span data-ttu-id="48e2c-472">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="48e2c-472">Custom</span></span> | <span data-ttu-id="48e2c-473">Droit d’utilisation de l’actif</span><span class="sxs-lookup"><span data-stu-id="48e2c-473">ROU Asset</span></span>                | <span data-ttu-id="48e2c-474">22,793.90</span><span class="sxs-lookup"><span data-stu-id="48e2c-474">22,793.90</span></span> |           |
| <span data-ttu-id="48e2c-475">Registre</span><span class="sxs-lookup"><span data-stu-id="48e2c-475">Ledger</span></span>       | <span data-ttu-id="48e2c-476">7</span><span class="sxs-lookup"><span data-stu-id="48e2c-476">7</span></span>              | <span data-ttu-id="48e2c-477">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="48e2c-477">Custom</span></span> | <span data-ttu-id="48e2c-478">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="48e2c-478">Finance lease obligation</span></span> |           | <span data-ttu-id="48e2c-479">22,793.90</span><span class="sxs-lookup"><span data-stu-id="48e2c-479">22,793.90</span></span> |

<span data-ttu-id="48e2c-480">Le paiement de location est comptabilisé comme les autres paiements de location.</span><span class="sxs-lookup"><span data-stu-id="48e2c-480">The lease payment is posted like the other lease payments.</span></span> <span data-ttu-id="48e2c-481">La raison de l’utilisation du compte de compensation est de s’assurer que les espèces ne sont créditées qu’une seule fois.</span><span class="sxs-lookup"><span data-stu-id="48e2c-481">The reason for using the clearing account is to ensure that cash is credited only one time.</span></span>

### <a name="lease-payment--1312020--je-150"></a><span data-ttu-id="48e2c-482">Paiement de location – 31/01/2020 – JE 150</span><span class="sxs-lookup"><span data-stu-id="48e2c-482">Lease payment – 1/31/2020 – JE 150</span></span>

| <span data-ttu-id="48e2c-483">Type de compte</span><span class="sxs-lookup"><span data-stu-id="48e2c-483">Account type</span></span> | <span data-ttu-id="48e2c-484">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="48e2c-484">Account number</span></span> | <span data-ttu-id="48e2c-485">Couche</span><span class="sxs-lookup"><span data-stu-id="48e2c-485">Layer</span></span>  | <span data-ttu-id="48e2c-486">Description du compte</span><span class="sxs-lookup"><span data-stu-id="48e2c-486">Account description</span></span>      | <span data-ttu-id="48e2c-487">Débit</span><span class="sxs-lookup"><span data-stu-id="48e2c-487">Debit</span></span>    | <span data-ttu-id="48e2c-488">Crédit</span><span class="sxs-lookup"><span data-stu-id="48e2c-488">Credit</span></span>   |
|--------------|----------------|--------|--------------------------|----------|----------|
| <span data-ttu-id="48e2c-489">Registre</span><span class="sxs-lookup"><span data-stu-id="48e2c-489">Ledger</span></span>       | <span data-ttu-id="48e2c-490">7</span><span class="sxs-lookup"><span data-stu-id="48e2c-490">7</span></span>              | <span data-ttu-id="48e2c-491">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="48e2c-491">Custom</span></span> | <span data-ttu-id="48e2c-492">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="48e2c-492">Finance lease obligation</span></span> | <span data-ttu-id="48e2c-493">1,000.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-493">1,000.00</span></span> |          |
| <span data-ttu-id="48e2c-494">Registre</span><span class="sxs-lookup"><span data-stu-id="48e2c-494">Ledger</span></span>       | <span data-ttu-id="48e2c-495">4</span><span class="sxs-lookup"><span data-stu-id="48e2c-495">4</span></span>              | <span data-ttu-id="48e2c-496">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="48e2c-496">Custom</span></span> | <span data-ttu-id="48e2c-497">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="48e2c-497">Clearing account</span></span>         |          | <span data-ttu-id="48e2c-498">1,000.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-498">1,000.00</span></span> |

<span data-ttu-id="48e2c-499">L’écriture de journal des charges d’intérêts est générée à partir du calendrier d’amortissement du passif.</span><span class="sxs-lookup"><span data-stu-id="48e2c-499">The interest expense journal entry is generated from the liability amortization schedule.</span></span>

### <a name="interest-expense--1312020--je-160"></a><span data-ttu-id="48e2c-500">Dépenses d’intérêts – 31/1/2020 – JE 160</span><span class="sxs-lookup"><span data-stu-id="48e2c-500">Interest expense – 1/31/2020 – JE 160</span></span>

| <span data-ttu-id="48e2c-501">Type de compte</span><span class="sxs-lookup"><span data-stu-id="48e2c-501">Account type</span></span> | <span data-ttu-id="48e2c-502">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="48e2c-502">Account number</span></span> | <span data-ttu-id="48e2c-503">Couche</span><span class="sxs-lookup"><span data-stu-id="48e2c-503">Layer</span></span>  | <span data-ttu-id="48e2c-504">Description du compte</span><span class="sxs-lookup"><span data-stu-id="48e2c-504">Account description</span></span>      | <span data-ttu-id="48e2c-505">Débit</span><span class="sxs-lookup"><span data-stu-id="48e2c-505">Debit</span></span> | <span data-ttu-id="48e2c-506">Crédit</span><span class="sxs-lookup"><span data-stu-id="48e2c-506">Credit</span></span> |
|--------------|----------------|--------|--------------------------|-------|--------|
| <span data-ttu-id="48e2c-507">Registre</span><span class="sxs-lookup"><span data-stu-id="48e2c-507">Ledger</span></span>       | <span data-ttu-id="48e2c-508">8</span><span class="sxs-lookup"><span data-stu-id="48e2c-508">8</span></span>              | <span data-ttu-id="48e2c-509">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="48e2c-509">Custom</span></span> | <span data-ttu-id="48e2c-510">Dépenses d’intérêts</span><span class="sxs-lookup"><span data-stu-id="48e2c-510">Interest expense</span></span>         | <span data-ttu-id="48e2c-511">94.97</span><span class="sxs-lookup"><span data-stu-id="48e2c-511">94.97</span></span> |        |
| <span data-ttu-id="48e2c-512">Registre</span><span class="sxs-lookup"><span data-stu-id="48e2c-512">Ledger</span></span>       | <span data-ttu-id="48e2c-513">7</span><span class="sxs-lookup"><span data-stu-id="48e2c-513">7</span></span>              | <span data-ttu-id="48e2c-514">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="48e2c-514">Custom</span></span> | <span data-ttu-id="48e2c-515">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="48e2c-515">Finance lease obligation</span></span> |       | <span data-ttu-id="48e2c-516">94.97</span><span class="sxs-lookup"><span data-stu-id="48e2c-516">94.97</span></span>  |

<span data-ttu-id="48e2c-517">L’écriture de journal de dépense d’amortissement est générée à partir du programme d’amortissement du passif.</span><span class="sxs-lookup"><span data-stu-id="48e2c-517">The depreciation expense journal entry is generated from the asset depreciation schedule.</span></span>

### <a name="depreciation-expense--1312020--je-170"></a><span data-ttu-id="48e2c-518">Dépenses d’amortissement – 1/31/2020 – JE 170</span><span class="sxs-lookup"><span data-stu-id="48e2c-518">Depreciation expense – 1/31/2020 – JE 170</span></span>

| <span data-ttu-id="48e2c-519">Type de compte</span><span class="sxs-lookup"><span data-stu-id="48e2c-519">Account type</span></span> | <span data-ttu-id="48e2c-520">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="48e2c-520">Account number</span></span> | <span data-ttu-id="48e2c-521">Couche</span><span class="sxs-lookup"><span data-stu-id="48e2c-521">Layer</span></span>  | <span data-ttu-id="48e2c-522">Description du compte</span><span class="sxs-lookup"><span data-stu-id="48e2c-522">Account description</span></span>      | <span data-ttu-id="48e2c-523">Débit</span><span class="sxs-lookup"><span data-stu-id="48e2c-523">Debit</span></span>  | <span data-ttu-id="48e2c-524">Crédit</span><span class="sxs-lookup"><span data-stu-id="48e2c-524">Credit</span></span> |
|--------------|----------------|--------|--------------------------|--------|--------|
| <span data-ttu-id="48e2c-525">Registre</span><span class="sxs-lookup"><span data-stu-id="48e2c-525">Ledger</span></span>       | <span data-ttu-id="48e2c-526">10</span><span class="sxs-lookup"><span data-stu-id="48e2c-526">10</span></span>             | <span data-ttu-id="48e2c-527">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="48e2c-527">Custom</span></span> | <span data-ttu-id="48e2c-528">Dépenses d’amortissement</span><span class="sxs-lookup"><span data-stu-id="48e2c-528">Depreciation expense</span></span>     | <span data-ttu-id="48e2c-529">949.75</span><span class="sxs-lookup"><span data-stu-id="48e2c-529">949.75</span></span> |        |
| <span data-ttu-id="48e2c-530">Registre</span><span class="sxs-lookup"><span data-stu-id="48e2c-530">Ledger</span></span>       | <span data-ttu-id="48e2c-531">11</span><span class="sxs-lookup"><span data-stu-id="48e2c-531">11</span></span>             | <span data-ttu-id="48e2c-532">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="48e2c-532">Custom</span></span> | <span data-ttu-id="48e2c-533">Amortissement cumulé</span><span class="sxs-lookup"><span data-stu-id="48e2c-533">Accumulated depreciation</span></span> |        | <span data-ttu-id="48e2c-534">949.75</span><span class="sxs-lookup"><span data-stu-id="48e2c-534">949.75</span></span> |

<span data-ttu-id="48e2c-535">Une fois toutes ces entrées de journal créées et validées, vous verrez les valeurs de « couche personnalisée 1 » suivantes.</span><span class="sxs-lookup"><span data-stu-id="48e2c-535">After all these journal entries are created and posted, you will see the following "custom layer 1" values.</span></span> <span data-ttu-id="48e2c-536">Notez que la dernière colonne comprend les frais bancaires, les frais de taxe sur la valeur ajoutée (TVA) et la réduction des liquidités de la couche précédente, mais elle n’inclut pas les écritures de reporting statutaires.</span><span class="sxs-lookup"><span data-stu-id="48e2c-536">Note that the last column includes the bank fee, the value-added tax (VAT) expense, and the reduction of cash from the previous layer, but it doesn't include the statutory reporting journal entries.</span></span> <span data-ttu-id="48e2c-537">Par conséquent, vous obtenez de véritables capacités de double reporting.</span><span class="sxs-lookup"><span data-stu-id="48e2c-537">Therefore, you achieve true dual-reporting capabilities.</span></span> <span data-ttu-id="48e2c-538">À ce stade, l’entreprise doit simplement exécuter sa balance comptable et combiner la couche actuelle et la couche personnalisée pour créer une balance comptable IFRS.</span><span class="sxs-lookup"><span data-stu-id="48e2c-538">At this point, the company just has to run its trial balance, and combine the current layer and the custom layer to create an IFRS trial balance.</span></span>

| <span data-ttu-id="48e2c-539">N° de compte</span><span class="sxs-lookup"><span data-stu-id="48e2c-539">Account No</span></span> | <span data-ttu-id="48e2c-540">Description</span><span class="sxs-lookup"><span data-stu-id="48e2c-540">Description</span></span>              | <span data-ttu-id="48e2c-541">Registre statutaire\-Couche actuelle\-JE\-100\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="48e2c-541">Statutory Book\-Current Layer\-JE\-100\-Dr \(Cr\)</span></span> | <span data-ttu-id="48e2c-542">Registre statutaire\-Couche actuelle\-JE\-110\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="48e2c-542">Statutory Book\-Current Layer\-JE\-110\-Dr \(Cr\)</span></span> | <span data-ttu-id="48e2c-543">Registre statutaire\-Couche actuelle\-JE\-120\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="48e2c-543">Statutory Book\-Current Layer\-JE\-120\-Dr \(Cr\)</span></span> | <span data-ttu-id="48e2c-544">Couche actuelle \- Totaux</span><span class="sxs-lookup"><span data-stu-id="48e2c-544">Current Layer \- Totals</span></span> | - | <span data-ttu-id="48e2c-545">Registre de contrepassation\-Couche personnalisée\-JE\-130\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="48e2c-545">Reversal Book\-Custom layer\-JE\-130\-Dr \(Cr\)</span></span> | <span data-ttu-id="48e2c-546">Registre IFRS 16\-Couche personnalisée\-JE\-140\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="48e2c-546">IFRS 16 Book\-Custom layer\-JE\-140\-Dr \(Cr\)</span></span> | <span data-ttu-id="48e2c-547">Registre IFRS 16\-Couche personnalisée\-JE\-150\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="48e2c-547">IFRS 16 Book\-Custom layer\-JE\-150\-Dr \(Cr\)</span></span> | <span data-ttu-id="48e2c-548">Registre IFRS 16\-Couche personnalisée\-JE\-160\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="48e2c-548">IFRS 16 Book\-Custom layer\-JE\-160\-Dr \(Cr\)</span></span> | <span data-ttu-id="48e2c-549">Registre IFRS 16\-Couche personnalisée\-JE\-170\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="48e2c-549">IFRS 16 Book\-Custom layer\-JE\-170\-Dr \(Cr\)</span></span> | <span data-ttu-id="48e2c-550">Couche personnalisée \+ Couche actuelle \- Totaux</span><span class="sxs-lookup"><span data-stu-id="48e2c-550">Custom Layer \+ Current Layer \- Totals</span></span> |
|------------|--------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|-------------------------|---|-------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------|
| <span data-ttu-id="48e2c-551">1</span><span class="sxs-lookup"><span data-stu-id="48e2c-551">1</span></span>          | <span data-ttu-id="48e2c-552">Dépense de bail</span><span class="sxs-lookup"><span data-stu-id="48e2c-552">Lease expense</span></span>            | <span data-ttu-id="48e2c-553">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-553">1,000\.00</span></span>                                         |                                                   |                                                   | <span data-ttu-id="48e2c-554">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-554">1,000\.00</span></span>               |   | <span data-ttu-id="48e2c-555">\-1 000</span><span class="sxs-lookup"><span data-stu-id="48e2c-555">\-1,000</span></span>                                         |                                                |                                                |                                                |                                                | <span data-ttu-id="48e2c-556">0\.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-556">0\.00</span></span>                                   |
| <span data-ttu-id="48e2c-557">2</span><span class="sxs-lookup"><span data-stu-id="48e2c-557">2</span></span>          | <span data-ttu-id="48e2c-558">Frais bancaires</span><span class="sxs-lookup"><span data-stu-id="48e2c-558">Bank fee</span></span>                 |                                                   | <span data-ttu-id="48e2c-559">3\.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-559">3\.00</span></span>                                             |                                                   | <span data-ttu-id="48e2c-560">3\.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-560">3\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="48e2c-561">3\.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-561">3\.00</span></span>                                   |
| <span data-ttu-id="48e2c-562">3</span><span class="sxs-lookup"><span data-stu-id="48e2c-562">3</span></span>          | <span data-ttu-id="48e2c-563">Dépenses de TVA</span><span class="sxs-lookup"><span data-stu-id="48e2c-563">VAT expense</span></span>              |                                                   | <span data-ttu-id="48e2c-564">5\.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-564">5\.00</span></span>                                             |                                                   | <span data-ttu-id="48e2c-565">5\.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-565">5\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="48e2c-566">5\.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-566">5\.00</span></span>                                   |
| <span data-ttu-id="48e2c-567">4</span><span class="sxs-lookup"><span data-stu-id="48e2c-567">4</span></span>          | <span data-ttu-id="48e2c-568">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="48e2c-568">Clearing account</span></span>         | <span data-ttu-id="48e2c-569">\-1 000\.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-569">\-1,000\.00</span></span>                                       | <span data-ttu-id="48e2c-570">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-570">1,000\.00</span></span>                                         |                                                   | <span data-ttu-id="48e2c-571">0\.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-571">0\.00</span></span>                   |   | <span data-ttu-id="48e2c-572">1 000</span><span class="sxs-lookup"><span data-stu-id="48e2c-572">1,000</span></span>                                           |                                                | <span data-ttu-id="48e2c-573">\-1 000</span><span class="sxs-lookup"><span data-stu-id="48e2c-573">\-1,000</span></span>                                        |                                                |                                                | <span data-ttu-id="48e2c-574">0\.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-574">0\.00</span></span>                                   |
| <span data-ttu-id="48e2c-575">5</span><span class="sxs-lookup"><span data-stu-id="48e2c-575">5</span></span>          | <span data-ttu-id="48e2c-576">Module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="48e2c-576">Accounts payable</span></span>         |                                                   | <span data-ttu-id="48e2c-577">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-577">\-1,008\.00</span></span>                                       | <span data-ttu-id="48e2c-578">1,008\.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-578">1,008\.00</span></span>                                         | <span data-ttu-id="48e2c-579">0\.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-579">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="48e2c-580">0\.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-580">0\.00</span></span>                                   |
| <span data-ttu-id="48e2c-581">6</span><span class="sxs-lookup"><span data-stu-id="48e2c-581">6</span></span>          | <span data-ttu-id="48e2c-582">Droit d’utilisation de l’actif</span><span class="sxs-lookup"><span data-stu-id="48e2c-582">ROU asset</span></span>                |                                                   |                                                   |                                                   | <span data-ttu-id="48e2c-583">0\.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-583">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="48e2c-584">22,794</span><span class="sxs-lookup"><span data-stu-id="48e2c-584">22,794</span></span>                                         |                                                |                                                |                                                | <span data-ttu-id="48e2c-585">22,793\.90</span><span class="sxs-lookup"><span data-stu-id="48e2c-585">22,793\.90</span></span>                              |
| <span data-ttu-id="48e2c-586">7</span><span class="sxs-lookup"><span data-stu-id="48e2c-586">7</span></span>          | <span data-ttu-id="48e2c-587">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="48e2c-587">Finance lease obligation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="48e2c-588">0\.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-588">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="48e2c-589">\-22 794</span><span class="sxs-lookup"><span data-stu-id="48e2c-589">\-22,794</span></span>                                       | <span data-ttu-id="48e2c-590">1 000</span><span class="sxs-lookup"><span data-stu-id="48e2c-590">1,000</span></span>                                          | <span data-ttu-id="48e2c-591">\-94\.97</span><span class="sxs-lookup"><span data-stu-id="48e2c-591">\-94\.97</span></span>                                       |                                                | <span data-ttu-id="48e2c-592">\-21 888\.87</span><span class="sxs-lookup"><span data-stu-id="48e2c-592">\-21,888\.87</span></span>                            |
| <span data-ttu-id="48e2c-593">8</span><span class="sxs-lookup"><span data-stu-id="48e2c-593">8</span></span>          | <span data-ttu-id="48e2c-594">Dépenses d’intérêts</span><span class="sxs-lookup"><span data-stu-id="48e2c-594">Interest expense</span></span>         |                                                   |                                                   |                                                   | <span data-ttu-id="48e2c-595">0\.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-595">0\.00</span></span>                   |   |                                                 |                                                |                                                | <span data-ttu-id="48e2c-596">94\.97</span><span class="sxs-lookup"><span data-stu-id="48e2c-596">94\.97</span></span>                                         |                                                | <span data-ttu-id="48e2c-597">94\.97</span><span class="sxs-lookup"><span data-stu-id="48e2c-597">94\.97</span></span>                                  |
| <span data-ttu-id="48e2c-598">9</span><span class="sxs-lookup"><span data-stu-id="48e2c-598">9</span></span>          | <span data-ttu-id="48e2c-599">Monétaire</span><span class="sxs-lookup"><span data-stu-id="48e2c-599">Cash</span></span>                     |                                                   |                                                   | <span data-ttu-id="48e2c-600">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-600">\-1,008\.00</span></span>                                       | <span data-ttu-id="48e2c-601">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-601">\-1,008\.00</span></span>             |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="48e2c-602">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-602">\-1,008\.00</span></span>                             |
| <span data-ttu-id="48e2c-603">10</span><span class="sxs-lookup"><span data-stu-id="48e2c-603">10</span></span>         | <span data-ttu-id="48e2c-604">Dépenses d’amortissement</span><span class="sxs-lookup"><span data-stu-id="48e2c-604">Depreciation expense</span></span>     |                                                   |                                                   |                                                   | <span data-ttu-id="48e2c-605">0\.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-605">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="48e2c-606">949\.75</span><span class="sxs-lookup"><span data-stu-id="48e2c-606">949\.75</span></span>                                        | <span data-ttu-id="48e2c-607">949\.75</span><span class="sxs-lookup"><span data-stu-id="48e2c-607">949\.75</span></span>                                 |
| <span data-ttu-id="48e2c-608">11</span><span class="sxs-lookup"><span data-stu-id="48e2c-608">11</span></span>         | <span data-ttu-id="48e2c-609">Amortissement cumulé</span><span class="sxs-lookup"><span data-stu-id="48e2c-609">Accumulated depreciation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="48e2c-610">0\.00</span><span class="sxs-lookup"><span data-stu-id="48e2c-610">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="48e2c-611">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="48e2c-611">\-949\.75</span></span>                                      | <span data-ttu-id="48e2c-612">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="48e2c-612">\-949\.75</span></span>                               |




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
