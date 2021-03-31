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
ms.openlocfilehash: d6daa43178625316a40427728e7e4186691cc13c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5229548"
---
# <a name="dual-reporting"></a><span data-ttu-id="9ffa9-103">Double déclaration</span><span class="sxs-lookup"><span data-stu-id="9ffa9-103">Dual reporting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9ffa9-104">Cette rubrique vous guide à travers un exemple qui montre comment vous pouvez remplir les exigences à la fois pour le reporting des normes internationales d’information financière (IFRS) et le reporting statutaire dans le bail d’actifs.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-104">This topic guides you through an example that shows how you can fulfill the requirements for both International Financial Reporting Standard (IFRS) reporting and statutory reporting in Asset leasing.</span></span> <span data-ttu-id="9ffa9-105">Il est nécessaire d’être familiarisé avec les couches de validation dans Microsoft Dynamics 365 Finance, ce qui rendra l’exemple plus facile à comprendre.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-105">Familiarity with posting layers in Microsoft Dynamics 365 Finance is required and will make the example easier to understand.</span></span>

## <a name="example"></a><span data-ttu-id="9ffa9-106">Exemple</span><span class="sxs-lookup"><span data-stu-id="9ffa9-106">Example</span></span>

<span data-ttu-id="9ffa9-107">L’exemple suivant rend compte d’un contrat de location selon le reporting statutaire italien en utilisant à la fois la méthode de la comptabilité de caisse et les méthodes de reporting IFRS.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-107">The following example accounts for a lease under Italian statutory reporting by using both the cash-basis method and IFRS reporting methods.</span></span> <span data-ttu-id="9ffa9-108">L’entreprise doit établir trois registres pour tenir compte à la fois des exigences légales italiennes et des exigences d’IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-108">The company must establish three books to account for both the Italian statutory requirements and the IFRS 16 requirements.</span></span> <span data-ttu-id="9ffa9-109">Un registre est requis pour IFRS 16, un registre est requis pour les exigences statutaires et un registre est requis pour annuler automatiquement les écritures statutaires.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-109">One book is required for IFRS 16, one book is required for statutory requirements, and one book is required to automatically reverse statutory postings.</span></span> <span data-ttu-id="9ffa9-110">Les registres sont configurés comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-110">The books are set up as shown in the following tables.</span></span>

<span data-ttu-id="9ffa9-111">**Registre IFRS 16**</span><span class="sxs-lookup"><span data-stu-id="9ffa9-111">**IFRS 16 book**</span></span>

<span data-ttu-id="9ffa9-112">Le registre IFRS 16 est mis en place de manière à être conforme à la norme comptable IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-112">The IFRS 16 book is set up so that it complies with the IFRS 16 accounting standard.</span></span> <span data-ttu-id="9ffa9-113">Toutes les entrées publiées dans ce livre seront publiées sur une couche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-113">All entries that are posted in this book will be posted to a custom layer.</span></span>

| <span data-ttu-id="9ffa9-114">Nom</span><span class="sxs-lookup"><span data-stu-id="9ffa9-114">Name</span></span>                                    | <span data-ttu-id="9ffa9-115">Description</span><span class="sxs-lookup"><span data-stu-id="9ffa9-115">Description</span></span>    |
|-----------------------------------------|----------------|
| <span data-ttu-id="9ffa9-116">Type de registre</span><span class="sxs-lookup"><span data-stu-id="9ffa9-116">Book type</span></span>                               | <span data-ttu-id="9ffa9-117">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="9ffa9-117">IFRS 16</span></span>        |
| <span data-ttu-id="9ffa9-118">Description du registre</span><span class="sxs-lookup"><span data-stu-id="9ffa9-118">Book description</span></span>                        | <span data-ttu-id="9ffa9-119">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="9ffa9-119">IFRS 16</span></span>        |
| <span data-ttu-id="9ffa9-120">Couche de comptabilisation</span><span class="sxs-lookup"><span data-stu-id="9ffa9-120">Posting Layer</span></span>                           | <span data-ttu-id="9ffa9-121">Couche personnalisée 1</span><span class="sxs-lookup"><span data-stu-id="9ffa9-121">Custom layer 1</span></span> |
| <span data-ttu-id="9ffa9-122">Type de bail</span><span class="sxs-lookup"><span data-stu-id="9ffa9-122">Lease Type</span></span>                              | <span data-ttu-id="9ffa9-123">Finances</span><span class="sxs-lookup"><span data-stu-id="9ffa9-123">Finance</span></span>        |
| <span data-ttu-id="9ffa9-124">Structure comptable</span><span class="sxs-lookup"><span data-stu-id="9ffa9-124">Accounting Framework</span></span>                    | <span data-ttu-id="9ffa9-125">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="9ffa9-125">IFRS 16</span></span>        |
| <span data-ttu-id="9ffa9-126">Configuration Durée du bail/Durée de vie utile</span><span class="sxs-lookup"><span data-stu-id="9ffa9-126">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="9ffa9-127">0,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-127">0.00</span></span>           |
| <span data-ttu-id="9ffa9-128">Configuration Valeur actuelle/Juste valeur de l’actif</span><span class="sxs-lookup"><span data-stu-id="9ffa9-128">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="9ffa9-129">0,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-129">0.00</span></span>           |
| <span data-ttu-id="9ffa9-130">Seuil à court terme</span><span class="sxs-lookup"><span data-stu-id="9ffa9-130">Short-term threshold</span></span>                    | <span data-ttu-id="9ffa9-131">12</span><span class="sxs-lookup"><span data-stu-id="9ffa9-131">12</span></span>             |
| <span data-ttu-id="9ffa9-132">Seuil de faible valeur</span><span class="sxs-lookup"><span data-stu-id="9ffa9-132">Low Value Threshold</span></span>                     | <span data-ttu-id="9ffa9-133">5,000.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-133">5,000.00</span></span>       |
| <span data-ttu-id="9ffa9-134">Payer au fournisseur</span><span class="sxs-lookup"><span data-stu-id="9ffa9-134">Pay to Vendor</span></span>                           | <span data-ttu-id="9ffa9-135">N°</span><span class="sxs-lookup"><span data-stu-id="9ffa9-135">No</span></span>             |

<span data-ttu-id="9ffa9-136">**Registre statutaire**</span><span class="sxs-lookup"><span data-stu-id="9ffa9-136">**Statutory book**</span></span>

<span data-ttu-id="9ffa9-137">Le registre statutaire est un registre de comptabilité de caisse dans lequel la société comptabilise les frais de location comme le montant en espèces payé chaque mois pour le loyer.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-137">The statutory book is a cash-basis book where the company will account for the lease expense as the amount of cash that is paid each month for rent.</span></span> <span data-ttu-id="9ffa9-138">Ce registre ne produira pas de droit d’utilisation de l’actif (ROU) ni de passif locatif.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-138">This book won't produce a right-of-use (ROU) asset or lease liability.</span></span>

| <span data-ttu-id="9ffa9-139">Nom</span><span class="sxs-lookup"><span data-stu-id="9ffa9-139">Name</span></span>                                    | <span data-ttu-id="9ffa9-140">Description</span><span class="sxs-lookup"><span data-stu-id="9ffa9-140">Description</span></span> |
|-----------------------------------------|-------------|
| <span data-ttu-id="9ffa9-141">Type de registre</span><span class="sxs-lookup"><span data-stu-id="9ffa9-141">Book type</span></span>                               | <span data-ttu-id="9ffa9-142">Statutaire</span><span class="sxs-lookup"><span data-stu-id="9ffa9-142">Statutory</span></span>   |
| <span data-ttu-id="9ffa9-143">Description du registre</span><span class="sxs-lookup"><span data-stu-id="9ffa9-143">Book description</span></span>                        | <span data-ttu-id="9ffa9-144">GAAP local</span><span class="sxs-lookup"><span data-stu-id="9ffa9-144">Local GAAP</span></span>  |
| <span data-ttu-id="9ffa9-145">Couche de comptabilisation</span><span class="sxs-lookup"><span data-stu-id="9ffa9-145">Posting Layer</span></span>                           | <span data-ttu-id="9ffa9-146">Actuelle</span><span class="sxs-lookup"><span data-stu-id="9ffa9-146">Current</span></span>     |
| <span data-ttu-id="9ffa9-147">Type de bail</span><span class="sxs-lookup"><span data-stu-id="9ffa9-147">Lease Type</span></span>                              | <span data-ttu-id="9ffa9-148">Automatique</span><span class="sxs-lookup"><span data-stu-id="9ffa9-148">Automatic</span></span>   |
| <span data-ttu-id="9ffa9-149">Structure comptable</span><span class="sxs-lookup"><span data-stu-id="9ffa9-149">Accounting Framework</span></span>                    | <span data-ttu-id="9ffa9-150">Base de trésorerie</span><span class="sxs-lookup"><span data-stu-id="9ffa9-150">Cash basis</span></span>  |
| <span data-ttu-id="9ffa9-151">Configuration Durée du bail/Durée de vie utile</span><span class="sxs-lookup"><span data-stu-id="9ffa9-151">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="9ffa9-152">0,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-152">0.00</span></span>        |
| <span data-ttu-id="9ffa9-153">Configuration Valeur actuelle/Juste valeur de l’actif</span><span class="sxs-lookup"><span data-stu-id="9ffa9-153">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="9ffa9-154">0,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-154">0.00</span></span>        |
| <span data-ttu-id="9ffa9-155">Seuil à court terme</span><span class="sxs-lookup"><span data-stu-id="9ffa9-155">Short-term threshold</span></span>                    | <span data-ttu-id="9ffa9-156">0</span><span class="sxs-lookup"><span data-stu-id="9ffa9-156">0</span></span>           |
| <span data-ttu-id="9ffa9-157">Seuil de faible valeur</span><span class="sxs-lookup"><span data-stu-id="9ffa9-157">Low Value Threshold</span></span>                     | <span data-ttu-id="9ffa9-158">0</span><span class="sxs-lookup"><span data-stu-id="9ffa9-158">0</span></span>           |
| <span data-ttu-id="9ffa9-159">Payer au fournisseur</span><span class="sxs-lookup"><span data-stu-id="9ffa9-159">Pay to Vendor</span></span>                           | <span data-ttu-id="9ffa9-160">N°</span><span class="sxs-lookup"><span data-stu-id="9ffa9-160">No</span></span>          |

<span data-ttu-id="9ffa9-161">**Registre de contrepassation statutaire**</span><span class="sxs-lookup"><span data-stu-id="9ffa9-161">**Statutory reversal book**</span></span>

<span data-ttu-id="9ffa9-162">Le registre de contrepassation statutaire est constitué de la même manière que le registre statutaire.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-162">The statutory reversal book is set up in the same way as the statutory book.</span></span>

| <span data-ttu-id="9ffa9-163">Nom</span><span class="sxs-lookup"><span data-stu-id="9ffa9-163">Name</span></span>                                    | <span data-ttu-id="9ffa9-164">Description</span><span class="sxs-lookup"><span data-stu-id="9ffa9-164">Description</span></span>                    |
|-----------------------------------------|--------------------------------|
| <span data-ttu-id="9ffa9-165">Type de registre</span><span class="sxs-lookup"><span data-stu-id="9ffa9-165">Book type</span></span>                               | <span data-ttu-id="9ffa9-166">Statutaire – contrepassation</span><span class="sxs-lookup"><span data-stu-id="9ffa9-166">Statutory – Reversal</span></span>           |
| <span data-ttu-id="9ffa9-167">Description du registre</span><span class="sxs-lookup"><span data-stu-id="9ffa9-167">Book description</span></span>                        | <span data-ttu-id="9ffa9-168">Registre pour contrepasser le registre statutaire</span><span class="sxs-lookup"><span data-stu-id="9ffa9-168">Book to reverse statutory book</span></span> |
| <span data-ttu-id="9ffa9-169">Couche de comptabilisation</span><span class="sxs-lookup"><span data-stu-id="9ffa9-169">Posting Layer</span></span>                           | <span data-ttu-id="9ffa9-170">Couche personnalisée 1</span><span class="sxs-lookup"><span data-stu-id="9ffa9-170">Custom layer 1</span></span>                 |
| <span data-ttu-id="9ffa9-171">Type de bail</span><span class="sxs-lookup"><span data-stu-id="9ffa9-171">Lease Type</span></span>                              | <span data-ttu-id="9ffa9-172">Automatique</span><span class="sxs-lookup"><span data-stu-id="9ffa9-172">Automatic</span></span>                      |
| <span data-ttu-id="9ffa9-173">Structure comptable</span><span class="sxs-lookup"><span data-stu-id="9ffa9-173">Accounting Framework</span></span>                    | <span data-ttu-id="9ffa9-174">Base de trésorerie</span><span class="sxs-lookup"><span data-stu-id="9ffa9-174">Cash basis</span></span>                     |
| <span data-ttu-id="9ffa9-175">Configuration Durée du bail/Durée de vie utile</span><span class="sxs-lookup"><span data-stu-id="9ffa9-175">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="9ffa9-176">0,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-176">0.00</span></span>                           |
| <span data-ttu-id="9ffa9-177">Configuration Valeur actuelle/Juste valeur de l’actif</span><span class="sxs-lookup"><span data-stu-id="9ffa9-177">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="9ffa9-178">0,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-178">0.00</span></span>                           |
| <span data-ttu-id="9ffa9-179">Seuil à court terme</span><span class="sxs-lookup"><span data-stu-id="9ffa9-179">Short-term threshold</span></span>                    | <span data-ttu-id="9ffa9-180">0</span><span class="sxs-lookup"><span data-stu-id="9ffa9-180">0</span></span>                              |
| <span data-ttu-id="9ffa9-181">Seuil de faible valeur</span><span class="sxs-lookup"><span data-stu-id="9ffa9-181">Low Value Threshold</span></span>                     | <span data-ttu-id="9ffa9-182">0</span><span class="sxs-lookup"><span data-stu-id="9ffa9-182">0</span></span>                              |
| <span data-ttu-id="9ffa9-183">Payer au fournisseur</span><span class="sxs-lookup"><span data-stu-id="9ffa9-183">Pay to Vendor</span></span>                           | <span data-ttu-id="9ffa9-184">N°</span><span class="sxs-lookup"><span data-stu-id="9ffa9-184">No</span></span>                             |

<span data-ttu-id="9ffa9-185">Pour cet exemple, un bail a été créé avec les paramètres suivants sur les onglets **Général** et **Lignes d’échéancier de paiement**.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-185">For this example, a lease has been created that has the following settings on the **General** and **Payment schedule lines** tabs.</span></span>

<span data-ttu-id="9ffa9-186">**Onglet Général**</span><span class="sxs-lookup"><span data-stu-id="9ffa9-186">**General tab**</span></span>

| <span data-ttu-id="9ffa9-187">Champ</span><span class="sxs-lookup"><span data-stu-id="9ffa9-187">Field</span></span>                      | <span data-ttu-id="9ffa9-188">Valeur</span><span class="sxs-lookup"><span data-stu-id="9ffa9-188">Value</span></span>            |
|----------------------------|------------------|
| <span data-ttu-id="9ffa9-189">Taux d’emprunt marginal</span><span class="sxs-lookup"><span data-stu-id="9ffa9-189">Incremental borrowing rate</span></span> | <span data-ttu-id="9ffa9-190">5 %</span><span class="sxs-lookup"><span data-stu-id="9ffa9-190">5%</span></span>               |
| <span data-ttu-id="9ffa9-191">Date d’entrée en vigueur</span><span class="sxs-lookup"><span data-stu-id="9ffa9-191">Commencement date</span></span>          | <span data-ttu-id="9ffa9-192">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="9ffa9-192">1/1/2020</span></span>         |
| <span data-ttu-id="9ffa9-193">Groupe de baux</span><span class="sxs-lookup"><span data-stu-id="9ffa9-193">Lease group</span></span>                | <span data-ttu-id="9ffa9-194">Bâtiments</span><span class="sxs-lookup"><span data-stu-id="9ffa9-194">Buildings</span></span>        |
| <span data-ttu-id="9ffa9-195">Fournisseur</span><span class="sxs-lookup"><span data-stu-id="9ffa9-195">Vendor</span></span>                     | <span data-ttu-id="9ffa9-196">1001</span><span class="sxs-lookup"><span data-stu-id="9ffa9-196">1001</span></span>             |
| <span data-ttu-id="9ffa9-197">Juste valeur de l’actif</span><span class="sxs-lookup"><span data-stu-id="9ffa9-197">Fair value of the asset</span></span>    | <span data-ttu-id="9ffa9-198">245,000</span><span class="sxs-lookup"><span data-stu-id="9ffa9-198">245,000</span></span>          |
| <span data-ttu-id="9ffa9-199">Durée de vie utile de l’actif</span><span class="sxs-lookup"><span data-stu-id="9ffa9-199">Asset useful life</span></span>          | <span data-ttu-id="9ffa9-200">120</span><span class="sxs-lookup"><span data-stu-id="9ffa9-200">120</span></span>              |
| <span data-ttu-id="9ffa9-201">Type d’annuité</span><span class="sxs-lookup"><span data-stu-id="9ffa9-201">Annuity type</span></span>               | <span data-ttu-id="9ffa9-202">Annuité ordinaire</span><span class="sxs-lookup"><span data-stu-id="9ffa9-202">Ordinary annuity</span></span> |
| <span data-ttu-id="9ffa9-203">Intervalle de composition</span><span class="sxs-lookup"><span data-stu-id="9ffa9-203">Compounding interval</span></span>       | <span data-ttu-id="9ffa9-204">Tous les mois</span><span class="sxs-lookup"><span data-stu-id="9ffa9-204">Monthly</span></span>          |

<span data-ttu-id="9ffa9-205">**Onglet Lignes d’échéancier de paiement**</span><span class="sxs-lookup"><span data-stu-id="9ffa9-205">**Payment schedule lines tab**</span></span>

| <span data-ttu-id="9ffa9-206">Champ</span><span class="sxs-lookup"><span data-stu-id="9ffa9-206">Field</span></span>             | <span data-ttu-id="9ffa9-207">Valeur</span><span class="sxs-lookup"><span data-stu-id="9ffa9-207">Value</span></span>      |
|-------------------|------------|
| <span data-ttu-id="9ffa9-208">Date de début</span><span class="sxs-lookup"><span data-stu-id="9ffa9-208">Start date</span></span>        | <span data-ttu-id="9ffa9-209">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="9ffa9-209">1/1/2020</span></span>   |
| <span data-ttu-id="9ffa9-210">Intervalle de périodes</span><span class="sxs-lookup"><span data-stu-id="9ffa9-210">Period interval</span></span>   | <span data-ttu-id="9ffa9-211">Mois</span><span class="sxs-lookup"><span data-stu-id="9ffa9-211">Months</span></span>     |
| <span data-ttu-id="9ffa9-212">Périodes</span><span class="sxs-lookup"><span data-stu-id="9ffa9-212">Periods</span></span>           | <span data-ttu-id="9ffa9-213">24</span><span class="sxs-lookup"><span data-stu-id="9ffa9-213">24</span></span>         |
| <span data-ttu-id="9ffa9-214">Date de fin</span><span class="sxs-lookup"><span data-stu-id="9ffa9-214">End date</span></span>          | <span data-ttu-id="9ffa9-215">31/12/2020</span><span class="sxs-lookup"><span data-stu-id="9ffa9-215">12/31/2020</span></span> |
| <span data-ttu-id="9ffa9-216">Fréquence de paiement</span><span class="sxs-lookup"><span data-stu-id="9ffa9-216">Payment frequency</span></span> | <span data-ttu-id="9ffa9-217">Tous les mois</span><span class="sxs-lookup"><span data-stu-id="9ffa9-217">Monthly</span></span>    |
| <span data-ttu-id="9ffa9-218">Montant du paiement</span><span class="sxs-lookup"><span data-stu-id="9ffa9-218">Payment amount</span></span>    | <span data-ttu-id="9ffa9-219">1 000</span><span class="sxs-lookup"><span data-stu-id="9ffa9-219">1,000</span></span>      |

<span data-ttu-id="9ffa9-220">Pour tenir compte de ce bail sous deux structures, vous utilisez une couche de validation actuelle et une couche de validation personnalisée.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-220">To account for this lease under two frameworks, you use a current posting layer and a custom posting layer.</span></span> <span data-ttu-id="9ffa9-221">Le tableau suivant montre un exemple de chaque écriture de journal nécessaire pour représenter fidèlement les données financières selon chaque norme de reporting.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-221">The following table shows an example of every journal entry that required to fairly represent the financials under each reporting standard.</span></span> <span data-ttu-id="9ffa9-222">Une description détaillée de chaque écriture de journal pour le premier mois du bail est fournie par la suite.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-222">A detailed description of each journal entry for the first month of the lease is provided afterward.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="9ffa9-223">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="9ffa9-223">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="9ffa9-224">Description</span><span class="sxs-lookup"><span data-stu-id="9ffa9-224">Description</span></span></th>
<th colspan='3'><span data-ttu-id="9ffa9-225">Registre statutaire (couche actuelle)</span><span class="sxs-lookup"><span data-stu-id="9ffa9-225">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="9ffa9-226">Total de la couche actuelle</span><span class="sxs-lookup"><span data-stu-id="9ffa9-226">Current layer total</span></span></th>
<th><span data-ttu-id="9ffa9-227">Registre de contrepassation (couche personnalisée)</span><span class="sxs-lookup"><span data-stu-id="9ffa9-227">Reversal book (custom layer)</span></span></th>
<th colspan='4'><span data-ttu-id="9ffa9-228">Registre IFRS 16 (couche personnalisée)</span><span class="sxs-lookup"><span data-stu-id="9ffa9-228">IFRS 16 book (custom layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="9ffa9-229">Couche actuelle + total de la couche personnalisée</span><span class="sxs-lookup"><span data-stu-id="9ffa9-229">Current layer + custom layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="9ffa9-230">JE-100</span><span class="sxs-lookup"><span data-stu-id="9ffa9-230">JE-100</span></span></th>
<th><span data-ttu-id="9ffa9-231">JE-110</span><span class="sxs-lookup"><span data-stu-id="9ffa9-231">JE-110</span></span></th>
<th><span data-ttu-id="9ffa9-232">JE-120</span><span class="sxs-lookup"><span data-stu-id="9ffa9-232">JE-120</span></span></th>
<th><span data-ttu-id="9ffa9-233">JE-130</span><span class="sxs-lookup"><span data-stu-id="9ffa9-233">JE-130</span></span></th>
<th><span data-ttu-id="9ffa9-234">JE-140</span><span class="sxs-lookup"><span data-stu-id="9ffa9-234">JE-140</span></span></th>
<th><span data-ttu-id="9ffa9-235">JE-150</span><span class="sxs-lookup"><span data-stu-id="9ffa9-235">JE-150</span></span></th>
<th><span data-ttu-id="9ffa9-236">JE-160</span><span class="sxs-lookup"><span data-stu-id="9ffa9-236">JE-160</span></span></th>
<th><span data-ttu-id="9ffa9-237">JE-170</span><span class="sxs-lookup"><span data-stu-id="9ffa9-237">JE-170</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="9ffa9-238">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="9ffa9-238">Dr (Cr)</span></span></th>
<th><span data-ttu-id="9ffa9-239">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="9ffa9-239">Dr (Cr)</span></span></th>
<th><span data-ttu-id="9ffa9-240">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="9ffa9-240">Dr (Cr)</span></span></th>
<th><span data-ttu-id="9ffa9-241">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="9ffa9-241">Dr (Cr)</span></span></th>
<th><span data-ttu-id="9ffa9-242">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="9ffa9-242">Dr (Cr)</span></span></th>
<th><span data-ttu-id="9ffa9-243">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="9ffa9-243">Dr (Cr)</span></span></th>
<th><span data-ttu-id="9ffa9-244">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="9ffa9-244">Dr (Cr)</span></span></th>
<th><span data-ttu-id="9ffa9-245">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="9ffa9-245">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9ffa9-246">1</span><span class="sxs-lookup"><span data-stu-id="9ffa9-246">1</span></span></td>
<td><span data-ttu-id="9ffa9-247">Dépense de bail</span><span class="sxs-lookup"><span data-stu-id="9ffa9-247">Lease expense</span></span></td>
<td><span data-ttu-id="9ffa9-248">1,000.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-248">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="9ffa9-249">1,000.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-249">1,000.00</span></span></td>
<td><span data-ttu-id="9ffa9-250">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-250">-1,000.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9ffa9-251">0,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-251">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9ffa9-252">2</span><span class="sxs-lookup"><span data-stu-id="9ffa9-252">2</span></span></td>
<td><span data-ttu-id="9ffa9-253">Frais bancaires</span><span class="sxs-lookup"><span data-stu-id="9ffa9-253">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="9ffa9-254">3.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-254">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="9ffa9-255">3.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-255">3.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9ffa9-256">3.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-256">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9ffa9-257">3</span><span class="sxs-lookup"><span data-stu-id="9ffa9-257">3</span></span></td>
<td><span data-ttu-id="9ffa9-258">Dépenses de TVA</span><span class="sxs-lookup"><span data-stu-id="9ffa9-258">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="9ffa9-259">5.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-259">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="9ffa9-260">5.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-260">5.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9ffa9-261">5.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-261">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9ffa9-262">4</span><span class="sxs-lookup"><span data-stu-id="9ffa9-262">4</span></span></td>
<td><span data-ttu-id="9ffa9-263">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="9ffa9-263">Clearing account</span></span></td>
<td><span data-ttu-id="9ffa9-264">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-264">-1,000.00</span></span></td>
<td><span data-ttu-id="9ffa9-265">1,000.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-265">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="9ffa9-266">0,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-266">0.00</span></span></td>
<td><span data-ttu-id="9ffa9-267">1,000.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-267">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="9ffa9-268">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-268">-1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="9ffa9-269">0,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-269">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9ffa9-270">5</span><span class="sxs-lookup"><span data-stu-id="9ffa9-270">5</span></span></td>
<td><span data-ttu-id="9ffa9-271">Module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="9ffa9-271">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="9ffa9-272">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-272">-1,008.00</span></span></td>
<td><span data-ttu-id="9ffa9-273">1,008.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-273">1,008.00</span></span></td>
<td><span data-ttu-id="9ffa9-274">0,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-274">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9ffa9-275">0,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-275">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9ffa9-276">6</span><span class="sxs-lookup"><span data-stu-id="9ffa9-276">6</span></span></td>
<td><span data-ttu-id="9ffa9-277">Droit d’utilisation de l’actif</span><span class="sxs-lookup"><span data-stu-id="9ffa9-277">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9ffa9-278">0,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-278">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="9ffa9-279">22,794.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-279">22,794.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9ffa9-280">22,793.90</span><span class="sxs-lookup"><span data-stu-id="9ffa9-280">22,793.90</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9ffa9-281">7</span><span class="sxs-lookup"><span data-stu-id="9ffa9-281">7</span></span></td>
<td><span data-ttu-id="9ffa9-282">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="9ffa9-282">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9ffa9-283">0,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-283">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="9ffa9-284">-22 794,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-284">-22,794.00</span></span></td>
<td><span data-ttu-id="9ffa9-285">1,000.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-285">1,000.00</span></span></td>
<td><span data-ttu-id="9ffa9-286">-94,97</span><span class="sxs-lookup"><span data-stu-id="9ffa9-286">-94.97</span></span></td>
<td></td>
<td><span data-ttu-id="9ffa9-287">-21 888,87</span><span class="sxs-lookup"><span data-stu-id="9ffa9-287">-21,888.87</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9ffa9-288">8</span><span class="sxs-lookup"><span data-stu-id="9ffa9-288">8</span></span></td>
<td><span data-ttu-id="9ffa9-289">Dépenses d’intérêts</span><span class="sxs-lookup"><span data-stu-id="9ffa9-289">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9ffa9-290">0,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-290">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9ffa9-291">94.97</span><span class="sxs-lookup"><span data-stu-id="9ffa9-291">94.97</span></span></td>
<td></td>
<td><span data-ttu-id="9ffa9-292">94.97</span><span class="sxs-lookup"><span data-stu-id="9ffa9-292">94.97</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9ffa9-293">9</span><span class="sxs-lookup"><span data-stu-id="9ffa9-293">9</span></span></td>
<td><span data-ttu-id="9ffa9-294">Monétaire</span><span class="sxs-lookup"><span data-stu-id="9ffa9-294">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="9ffa9-295">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-295">-1,008.00</span></span></td>
<td><span data-ttu-id="9ffa9-296">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-296">-1,008.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9ffa9-297">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-297">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9ffa9-298">10</span><span class="sxs-lookup"><span data-stu-id="9ffa9-298">10</span></span></td>
<td><span data-ttu-id="9ffa9-299">Dépenses d’amortissement</span><span class="sxs-lookup"><span data-stu-id="9ffa9-299">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9ffa9-300">0,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-300">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9ffa9-301">949.75</span><span class="sxs-lookup"><span data-stu-id="9ffa9-301">949.75</span></span></td>
<td><span data-ttu-id="9ffa9-302">949.75</span><span class="sxs-lookup"><span data-stu-id="9ffa9-302">949.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9ffa9-303">11</span><span class="sxs-lookup"><span data-stu-id="9ffa9-303">11</span></span></td>
<td><span data-ttu-id="9ffa9-304">Amortissement cumulé</span><span class="sxs-lookup"><span data-stu-id="9ffa9-304">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9ffa9-305">0,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-305">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9ffa9-306">-949,75</span><span class="sxs-lookup"><span data-stu-id="9ffa9-306">-949.75</span></span></td>
<td><span data-ttu-id="9ffa9-307">-949,75</span><span class="sxs-lookup"><span data-stu-id="9ffa9-307">-949.75</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="9ffa9-308">Comme le montre le tableau précédent, trois registres sont tenus pour déclarer à la fois le reporting statutaire et le reporting IFRS.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-308">As the preceding table shows, three books are required to report under both statutory reporting and IFRS reporting.</span></span>

- <span data-ttu-id="9ffa9-309">Le registre statutaire enregistre le paiement de location selon les règles de comptabilité de caisse sous la couche actuelle.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-309">The statutory book records the lease payment according to the rules for cash-basis accounting under the current layer.</span></span>
- <span data-ttu-id="9ffa9-310">Le registre de contrepassation statutaire annule les écritures au journal statutaire.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-310">The statutory reversal book reverses the statutory journal entries.</span></span>
- <span data-ttu-id="9ffa9-311">Le registre IFRS 16 crée les écritures de journal requises en vertu d’IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-311">The IFRS 16 book creates the journal entries that are required under IFRS 16.</span></span>

<span data-ttu-id="9ffa9-312">Vous ne devez saisir un bail qu’une seule fois.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-312">You must enter a lease only one time.</span></span> <span data-ttu-id="9ffa9-313">Vous pouvez ensuite ouvrir la page **Registres** pour voir tous les registres associés au bail.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-313">You can then open the **Books** page to see all the books that are associated with the lease.</span></span>

> [!NOTE]
> <span data-ttu-id="9ffa9-314">Lorsque vous créez les registres, tous les trois doivent être associés au même enregistrement de bail.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-314">When you create the books, all three of them must be associated with the same lease record.</span></span>

<span data-ttu-id="9ffa9-315">La première écriture de journal enregistre les frais de location dans le registre statutaire.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-315">The first journal entry records the lease expense under the statutory book.</span></span> <span data-ttu-id="9ffa9-316">Vous pouvez créer les paiements soit par lots, soit en sélectionnant l’échéancier de paiement dans le registre statutaire.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-316">You can create the payments either in a batch or by selecting the payment schedule in the statutory book.</span></span>

<span data-ttu-id="9ffa9-317">Pour cet exemple, l’écriture de journal suivante est produite pour le registre statutaire à partir de l’échéancier de paiement.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-317">For this example, the following journal entry is produced for the statutory book from the payment schedule.</span></span>

### <a name="lease-payment--1312020--je-100"></a><span data-ttu-id="9ffa9-318">Paiement de location – 31/01/2020 – JE 100</span><span class="sxs-lookup"><span data-stu-id="9ffa9-318">Lease payment – 1/31/2020 – JE 100</span></span>

| <span data-ttu-id="9ffa9-319">Type de compte</span><span class="sxs-lookup"><span data-stu-id="9ffa9-319">Account type</span></span> | <span data-ttu-id="9ffa9-320">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="9ffa9-320">Account number</span></span> | <span data-ttu-id="9ffa9-321">Couche</span><span class="sxs-lookup"><span data-stu-id="9ffa9-321">Layer</span></span>   | <span data-ttu-id="9ffa9-322">Description du compte</span><span class="sxs-lookup"><span data-stu-id="9ffa9-322">Account description</span></span> | <span data-ttu-id="9ffa9-323">Débit</span><span class="sxs-lookup"><span data-stu-id="9ffa9-323">Debit</span></span>    | <span data-ttu-id="9ffa9-324">Crédit</span><span class="sxs-lookup"><span data-stu-id="9ffa9-324">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="9ffa9-325">Registre</span><span class="sxs-lookup"><span data-stu-id="9ffa9-325">Ledger</span></span>       | <span data-ttu-id="9ffa9-326">1</span><span class="sxs-lookup"><span data-stu-id="9ffa9-326">1</span></span>              | <span data-ttu-id="9ffa9-327">Actuelle</span><span class="sxs-lookup"><span data-stu-id="9ffa9-327">Current</span></span> | <span data-ttu-id="9ffa9-328">Dépense de bail</span><span class="sxs-lookup"><span data-stu-id="9ffa9-328">Lease expense</span></span>       | <span data-ttu-id="9ffa9-329">1,000.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-329">1,000.00</span></span> |          |
| <span data-ttu-id="9ffa9-330">Registre</span><span class="sxs-lookup"><span data-stu-id="9ffa9-330">Ledger</span></span>       | <span data-ttu-id="9ffa9-331">4</span><span class="sxs-lookup"><span data-stu-id="9ffa9-331">4</span></span>              | <span data-ttu-id="9ffa9-332">Actuelle</span><span class="sxs-lookup"><span data-stu-id="9ffa9-332">Current</span></span> | <span data-ttu-id="9ffa9-333">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="9ffa9-333">Clearing account</span></span>    |          | <span data-ttu-id="9ffa9-334">1,000.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-334">1,000.00</span></span> |

<span data-ttu-id="9ffa9-335">Un commis aux comptes fournisseurs utilise la fonctionnalité standard de Dynamics 365 pour créer une facture pour payer le bail en dehors de la location d’actifs.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-335">An Accounts payable clerk uses standard Dynamics 365 functionality to create an invoice to pay for the lease outside Asset leasing.</span></span> <span data-ttu-id="9ffa9-336">Cependant, au lieu de sélectionner **Frais de location** comme compte de débit, le commis aux comptes fournisseurs sélectionne un compte de compensation pour générer l’écriture suivante.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-336">However, instead of selecting **Lease expense** as the debit account, the Accounts payable clerk selects a clearing account to generate the following entry.</span></span>

### <a name="ap-process--1312020--je-110"></a><span data-ttu-id="9ffa9-337">Processus AP – 31/01/2020 – JE 110</span><span class="sxs-lookup"><span data-stu-id="9ffa9-337">AP process – 1/31/2020 – JE 110</span></span>

| <span data-ttu-id="9ffa9-338">Type de compte</span><span class="sxs-lookup"><span data-stu-id="9ffa9-338">Account type</span></span> | <span data-ttu-id="9ffa9-339">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="9ffa9-339">Account number</span></span> | <span data-ttu-id="9ffa9-340">Couche</span><span class="sxs-lookup"><span data-stu-id="9ffa9-340">Layer</span></span>   | <span data-ttu-id="9ffa9-341">Description du compte</span><span class="sxs-lookup"><span data-stu-id="9ffa9-341">Account description</span></span> | <span data-ttu-id="9ffa9-342">Débit</span><span class="sxs-lookup"><span data-stu-id="9ffa9-342">Debit</span></span>    | <span data-ttu-id="9ffa9-343">Crédit</span><span class="sxs-lookup"><span data-stu-id="9ffa9-343">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="9ffa9-344">Registre</span><span class="sxs-lookup"><span data-stu-id="9ffa9-344">Ledger</span></span>       | <span data-ttu-id="9ffa9-345">4</span><span class="sxs-lookup"><span data-stu-id="9ffa9-345">4</span></span>              | <span data-ttu-id="9ffa9-346">Actuelle</span><span class="sxs-lookup"><span data-stu-id="9ffa9-346">Current</span></span> | <span data-ttu-id="9ffa9-347">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="9ffa9-347">Clearing account</span></span>    | <span data-ttu-id="9ffa9-348">1,000.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-348">1,000.00</span></span> |          |
| <span data-ttu-id="9ffa9-349">Registre</span><span class="sxs-lookup"><span data-stu-id="9ffa9-349">Ledger</span></span>       | <span data-ttu-id="9ffa9-350">2</span><span class="sxs-lookup"><span data-stu-id="9ffa9-350">2</span></span>              | <span data-ttu-id="9ffa9-351">Actuelle</span><span class="sxs-lookup"><span data-stu-id="9ffa9-351">Current</span></span> | <span data-ttu-id="9ffa9-352">Frais bancaires</span><span class="sxs-lookup"><span data-stu-id="9ffa9-352">Bank fee</span></span>            | <span data-ttu-id="9ffa9-353">3.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-353">3.00</span></span>     |          |
| <span data-ttu-id="9ffa9-354">Registre</span><span class="sxs-lookup"><span data-stu-id="9ffa9-354">Ledger</span></span>       | <span data-ttu-id="9ffa9-355">3</span><span class="sxs-lookup"><span data-stu-id="9ffa9-355">3</span></span>              | <span data-ttu-id="9ffa9-356">Actuelle</span><span class="sxs-lookup"><span data-stu-id="9ffa9-356">Current</span></span> | <span data-ttu-id="9ffa9-357">Dépenses de TVA</span><span class="sxs-lookup"><span data-stu-id="9ffa9-357">VAT expense</span></span>         | <span data-ttu-id="9ffa9-358">5.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-358">5.00</span></span>     |          |
| <span data-ttu-id="9ffa9-359">Fournisseur</span><span class="sxs-lookup"><span data-stu-id="9ffa9-359">Vendor</span></span>       | <span data-ttu-id="9ffa9-360">5</span><span class="sxs-lookup"><span data-stu-id="9ffa9-360">5</span></span>              | <span data-ttu-id="9ffa9-361">Actuelle</span><span class="sxs-lookup"><span data-stu-id="9ffa9-361">Current</span></span> | <span data-ttu-id="9ffa9-362">Module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="9ffa9-362">Accounts payable</span></span>    |          | <span data-ttu-id="9ffa9-363">1,008.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-363">1,008.00</span></span> |

<span data-ttu-id="9ffa9-364">Lorsque la déclaration est délivrée au fournisseur, vous suivez le processus de paiement régulier.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-364">When the statement is issued to the vendor, you follow the regular payment process.</span></span> <span data-ttu-id="9ffa9-365">Au cours de ce processus, l’écriture de journal suivante est générée.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-365">During this process, the following journal entry is generated.</span></span>

### <a name="cash-payment--1312020--je-120"></a><span data-ttu-id="9ffa9-366">Paiement en espèces – 31/01/2020 – JE 120</span><span class="sxs-lookup"><span data-stu-id="9ffa9-366">Cash payment – 1/31/2020 – JE 120</span></span>

| <span data-ttu-id="9ffa9-367">Type de compte</span><span class="sxs-lookup"><span data-stu-id="9ffa9-367">Account type</span></span> | <span data-ttu-id="9ffa9-368">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="9ffa9-368">Account number</span></span> | <span data-ttu-id="9ffa9-369">Couche</span><span class="sxs-lookup"><span data-stu-id="9ffa9-369">Layer</span></span>   | <span data-ttu-id="9ffa9-370">Description du compte</span><span class="sxs-lookup"><span data-stu-id="9ffa9-370">Account description</span></span> | <span data-ttu-id="9ffa9-371">Débit</span><span class="sxs-lookup"><span data-stu-id="9ffa9-371">Debit</span></span>    | <span data-ttu-id="9ffa9-372">Crédit</span><span class="sxs-lookup"><span data-stu-id="9ffa9-372">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="9ffa9-373">Fournisseur</span><span class="sxs-lookup"><span data-stu-id="9ffa9-373">Vendor</span></span>       | <span data-ttu-id="9ffa9-374">5</span><span class="sxs-lookup"><span data-stu-id="9ffa9-374">5</span></span>              | <span data-ttu-id="9ffa9-375">Actuelle</span><span class="sxs-lookup"><span data-stu-id="9ffa9-375">Current</span></span> | <span data-ttu-id="9ffa9-376">Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="9ffa9-376">Accounts Payable</span></span>    | <span data-ttu-id="9ffa9-377">1,008.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-377">1,008.00</span></span> |          |
| <span data-ttu-id="9ffa9-378">Banque</span><span class="sxs-lookup"><span data-stu-id="9ffa9-378">Bank</span></span>         | <span data-ttu-id="9ffa9-379">9</span><span class="sxs-lookup"><span data-stu-id="9ffa9-379">9</span></span>              | <span data-ttu-id="9ffa9-380">Actuelle</span><span class="sxs-lookup"><span data-stu-id="9ffa9-380">Current</span></span> | <span data-ttu-id="9ffa9-381">Monétaire</span><span class="sxs-lookup"><span data-stu-id="9ffa9-381">Cash</span></span>                |          | <span data-ttu-id="9ffa9-382">1,008.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-382">1,008.00</span></span> |

<span data-ttu-id="9ffa9-383">À ce stade, vous avez pleinement pris en compte ce bail conformément aux exigences légales en matière de rapports et pouvez générer une balance comptable en utilisant la couche actuelle.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-383">At this point, you've fully accounted for this lease under statutory reporting requirements and can generate a trial balance by using the current layer.</span></span> <span data-ttu-id="9ffa9-384">Le système renvoie une balance comptable qui a les chiffres suivants.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-384">The system returns a trial balance that has the following figures.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="9ffa9-385">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="9ffa9-385">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="9ffa9-386">Description</span><span class="sxs-lookup"><span data-stu-id="9ffa9-386">Description</span></span></th>
<th colspan='3'><span data-ttu-id="9ffa9-387">Registre statutaire (couche actuelle)</span><span class="sxs-lookup"><span data-stu-id="9ffa9-387">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="9ffa9-388">Total de la couche actuelle</span><span class="sxs-lookup"><span data-stu-id="9ffa9-388">Current layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="9ffa9-389">JE-100</span><span class="sxs-lookup"><span data-stu-id="9ffa9-389">JE-100</span></span></th>
<th><span data-ttu-id="9ffa9-390">JE-110</span><span class="sxs-lookup"><span data-stu-id="9ffa9-390">JE-110</span></span></th>
<th><span data-ttu-id="9ffa9-391">JE-120</span><span class="sxs-lookup"><span data-stu-id="9ffa9-391">JE-120</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="9ffa9-392">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="9ffa9-392">Dr (Cr)</span></span></th>
<th><span data-ttu-id="9ffa9-393">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="9ffa9-393">Dr (Cr)</span></span></th>
<th><span data-ttu-id="9ffa9-394">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="9ffa9-394">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9ffa9-395">1</span><span class="sxs-lookup"><span data-stu-id="9ffa9-395">1</span></span></td>
<td><span data-ttu-id="9ffa9-396">Dépense de bail</span><span class="sxs-lookup"><span data-stu-id="9ffa9-396">Lease expense</span></span></td>
<td><span data-ttu-id="9ffa9-397">1,000.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-397">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="9ffa9-398">1,000.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-398">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9ffa9-399">2</span><span class="sxs-lookup"><span data-stu-id="9ffa9-399">2</span></span></td>
<td><span data-ttu-id="9ffa9-400">Frais bancaires</span><span class="sxs-lookup"><span data-stu-id="9ffa9-400">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="9ffa9-401">3.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-401">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="9ffa9-402">3.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-402">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9ffa9-403">3</span><span class="sxs-lookup"><span data-stu-id="9ffa9-403">3</span></span></td>
<td><span data-ttu-id="9ffa9-404">Dépenses de TVA</span><span class="sxs-lookup"><span data-stu-id="9ffa9-404">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="9ffa9-405">5.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-405">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="9ffa9-406">5.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-406">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9ffa9-407">4</span><span class="sxs-lookup"><span data-stu-id="9ffa9-407">4</span></span></td>
<td><span data-ttu-id="9ffa9-408">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="9ffa9-408">Clearing account</span></span></td>
<td><span data-ttu-id="9ffa9-409">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-409">-1,000.00</span></span></td>
<td><span data-ttu-id="9ffa9-410">1,000.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-410">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="9ffa9-411">0,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-411">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9ffa9-412">5</span><span class="sxs-lookup"><span data-stu-id="9ffa9-412">5</span></span></td>
<td><span data-ttu-id="9ffa9-413">Module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="9ffa9-413">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="9ffa9-414">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-414">-1,008.00</span></span></td>
<td><span data-ttu-id="9ffa9-415">1,008.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-415">1,008.00</span></span></td>
<td><span data-ttu-id="9ffa9-416">0,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-416">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9ffa9-417">6</span><span class="sxs-lookup"><span data-stu-id="9ffa9-417">6</span></span></td>
<td><span data-ttu-id="9ffa9-418">Droit d’utilisation de l’actif</span><span class="sxs-lookup"><span data-stu-id="9ffa9-418">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9ffa9-419">0,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-419">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9ffa9-420">7</span><span class="sxs-lookup"><span data-stu-id="9ffa9-420">7</span></span></td>
<td><span data-ttu-id="9ffa9-421">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="9ffa9-421">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9ffa9-422">0,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-422">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9ffa9-423">8</span><span class="sxs-lookup"><span data-stu-id="9ffa9-423">8</span></span></td>
<td><span data-ttu-id="9ffa9-424">Dépenses d’intérêts</span><span class="sxs-lookup"><span data-stu-id="9ffa9-424">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9ffa9-425">0,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-425">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9ffa9-426">9</span><span class="sxs-lookup"><span data-stu-id="9ffa9-426">9</span></span></td>
<td><span data-ttu-id="9ffa9-427">Monétaire</span><span class="sxs-lookup"><span data-stu-id="9ffa9-427">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="9ffa9-428">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-428">-1,008.00</span></span></td>
<td><span data-ttu-id="9ffa9-429">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-429">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9ffa9-430">10</span><span class="sxs-lookup"><span data-stu-id="9ffa9-430">10</span></span></td>
<td><span data-ttu-id="9ffa9-431">Dépenses d’amortissement</span><span class="sxs-lookup"><span data-stu-id="9ffa9-431">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9ffa9-432">0,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-432">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9ffa9-433">11</span><span class="sxs-lookup"><span data-stu-id="9ffa9-433">11</span></span></td>
<td><span data-ttu-id="9ffa9-434">Amortissement cumulé</span><span class="sxs-lookup"><span data-stu-id="9ffa9-434">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9ffa9-435">0,00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-435">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="9ffa9-436">Si vous souhaitez utiliser les chiffres IFRS 16 pour exécuter la même balance comptable, les écritures comptables statutaires doivent être contrepassées et les écritures comptables IFRS 16 doivent être enregistrées.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-436">If you want to use the IFRS 16 figures to run the same trial balance, the statutory accounting journal entries must be reversed, and the IFRS 16 journal entries must be posted.</span></span> <span data-ttu-id="9ffa9-437">Pour contrepasser les écritures statutaires, cet exemple inclut un registre de contrepassation statutaire qui a la même configuration que le registre statutaire mais un profil de validation opposé.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-437">To reverse the statutory journal entries, this example includes a statutory reversal book that has the same setup as the statutory book but an opposite posting profile.</span></span> <span data-ttu-id="9ffa9-438">Par exemple, le registre statutaire *a débité* un compte de charges de location, mais le registre de contrepassation va *créditer* ce compte.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-438">For example, the statutory book *debited* a lease expense account, but the reversal book will *credit* this account.</span></span> <span data-ttu-id="9ffa9-439">Ces relations sont facilement définies dans les comptes de comptabilisation de la location d’actifs sur la page **Paramètres de location d’actifs** (**Location d’actifs \> Configurer \> Paramètres de location d’actifs**).</span><span class="sxs-lookup"><span data-stu-id="9ffa9-439">These relationships are easily defined in the Asset leasing posting accounts on the **Asset leasing parameters** page (**Asset leasing \> Setup \> Asset leasing parameters**).</span></span>

<span data-ttu-id="9ffa9-440">Lorsque le même processus que celui utilisé pour le registre statutaire est utilisé pour le registre de contrepassation, l’écriture de journal suivante est produite.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-440">When the same process that was used for the statutory book is used for the reversal book, the following journal entry is produced.</span></span> <span data-ttu-id="9ffa9-441">La différence est que le registre de contrepassation comptabilise les écritures de contrepassation du registre statutaire.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-441">The difference is that the reversal book books the reversing entries from the statutory book.</span></span> <span data-ttu-id="9ffa9-442">Les écritures de contrepassation sont également apportées à la couche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-442">The reversing entries are also made to the custom layer.</span></span> <span data-ttu-id="9ffa9-443">Lorsqu’une balance comptable est exécutée au niveau de la couche actuelle, les écritures de journal de contrepassation ne sont pas incluses.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-443">When a trial balance is run at the current layer, the reversing journal entries aren't included.</span></span>

### <a name="lease-payment--1312020--je-130"></a><span data-ttu-id="9ffa9-444">Paiement de location – 31/01/2020 – JE 130</span><span class="sxs-lookup"><span data-stu-id="9ffa9-444">Lease payment – 1/31/2020 – JE 130</span></span>

| <span data-ttu-id="9ffa9-445">Type de compte</span><span class="sxs-lookup"><span data-stu-id="9ffa9-445">Account type</span></span> | <span data-ttu-id="9ffa9-446">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="9ffa9-446">Account number</span></span> | <span data-ttu-id="9ffa9-447">Couche</span><span class="sxs-lookup"><span data-stu-id="9ffa9-447">Layer</span></span>  | <span data-ttu-id="9ffa9-448">Description du compte</span><span class="sxs-lookup"><span data-stu-id="9ffa9-448">Account description</span></span> | <span data-ttu-id="9ffa9-449">Débit</span><span class="sxs-lookup"><span data-stu-id="9ffa9-449">Debit</span></span>    | <span data-ttu-id="9ffa9-450">Crédit</span><span class="sxs-lookup"><span data-stu-id="9ffa9-450">Credit</span></span>   |
|--------------|----------------|--------|---------------------|----------|----------|
| <span data-ttu-id="9ffa9-451">Registre</span><span class="sxs-lookup"><span data-stu-id="9ffa9-451">Ledger</span></span>       | <span data-ttu-id="9ffa9-452">4</span><span class="sxs-lookup"><span data-stu-id="9ffa9-452">4</span></span>              | <span data-ttu-id="9ffa9-453">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="9ffa9-453">Custom</span></span> | <span data-ttu-id="9ffa9-454">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="9ffa9-454">Clearing account</span></span>    | <span data-ttu-id="9ffa9-455">1,000.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-455">1,000.00</span></span> |          |
| <span data-ttu-id="9ffa9-456">Registre</span><span class="sxs-lookup"><span data-stu-id="9ffa9-456">Ledger</span></span>       | <span data-ttu-id="9ffa9-457">1</span><span class="sxs-lookup"><span data-stu-id="9ffa9-457">1</span></span>              | <span data-ttu-id="9ffa9-458">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="9ffa9-458">Custom</span></span> | <span data-ttu-id="9ffa9-459">Dépense de bail</span><span class="sxs-lookup"><span data-stu-id="9ffa9-459">Lease expense</span></span>       |          | <span data-ttu-id="9ffa9-460">1,000.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-460">1,000.00</span></span> |

<span data-ttu-id="9ffa9-461">Maintenant que vous avez éliminé les écritures de journal statutaires, vous allez enregistrer toutes les écritures de journal requises par IFRS 16 dans le livre IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-461">Now that you've eliminated the statutory journal entries, you will book all the journal entries that IFRS 16 requires in the IFRS 16 book.</span></span> <span data-ttu-id="9ffa9-462">Ces écritures comprennent la reconnaissance initiale du droit d’utilisation de l’actif et du passif, ainsi que l’enregistrement des intérêts et des amortissements.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-462">These entries include the initial recognition of the ROU asset and the liability, and the record of interest and depreciation.</span></span>

### <a name="initial-recognition--112020--je-140"></a><span data-ttu-id="9ffa9-463">Reconnaissance initiale – 1/1/2020 – JE 140</span><span class="sxs-lookup"><span data-stu-id="9ffa9-463">Initial recognition – 1/1/2020 – JE 140</span></span>

| <span data-ttu-id="9ffa9-464">Type de compte</span><span class="sxs-lookup"><span data-stu-id="9ffa9-464">Account type</span></span> | <span data-ttu-id="9ffa9-465">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="9ffa9-465">Account number</span></span> | <span data-ttu-id="9ffa9-466">Couche</span><span class="sxs-lookup"><span data-stu-id="9ffa9-466">Layer</span></span>  | <span data-ttu-id="9ffa9-467">Description du compte</span><span class="sxs-lookup"><span data-stu-id="9ffa9-467">Account description</span></span>      | <span data-ttu-id="9ffa9-468">Débit</span><span class="sxs-lookup"><span data-stu-id="9ffa9-468">Debit</span></span>     | <span data-ttu-id="9ffa9-469">Crédit</span><span class="sxs-lookup"><span data-stu-id="9ffa9-469">Credit</span></span>    |
|--------------|----------------|--------|--------------------------|-----------|-----------|
| <span data-ttu-id="9ffa9-470">Registre</span><span class="sxs-lookup"><span data-stu-id="9ffa9-470">Ledger</span></span>       | <span data-ttu-id="9ffa9-471">6</span><span class="sxs-lookup"><span data-stu-id="9ffa9-471">6</span></span>              | <span data-ttu-id="9ffa9-472">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="9ffa9-472">Custom</span></span> | <span data-ttu-id="9ffa9-473">Droit d’utilisation de l’actif</span><span class="sxs-lookup"><span data-stu-id="9ffa9-473">ROU Asset</span></span>                | <span data-ttu-id="9ffa9-474">22,793.90</span><span class="sxs-lookup"><span data-stu-id="9ffa9-474">22,793.90</span></span> |           |
| <span data-ttu-id="9ffa9-475">Registre</span><span class="sxs-lookup"><span data-stu-id="9ffa9-475">Ledger</span></span>       | <span data-ttu-id="9ffa9-476">7</span><span class="sxs-lookup"><span data-stu-id="9ffa9-476">7</span></span>              | <span data-ttu-id="9ffa9-477">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="9ffa9-477">Custom</span></span> | <span data-ttu-id="9ffa9-478">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="9ffa9-478">Finance lease obligation</span></span> |           | <span data-ttu-id="9ffa9-479">22,793.90</span><span class="sxs-lookup"><span data-stu-id="9ffa9-479">22,793.90</span></span> |

<span data-ttu-id="9ffa9-480">Le paiement de location est comptabilisé comme les autres paiements de location.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-480">The lease payment is posted like the other lease payments.</span></span> <span data-ttu-id="9ffa9-481">La raison de l’utilisation du compte de compensation est de s’assurer que les espèces ne sont créditées qu’une seule fois.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-481">The reason for using the clearing account is to ensure that cash is credited only one time.</span></span>

### <a name="lease-payment--1312020--je-150"></a><span data-ttu-id="9ffa9-482">Paiement de location – 31/01/2020 – JE 150</span><span class="sxs-lookup"><span data-stu-id="9ffa9-482">Lease payment – 1/31/2020 – JE 150</span></span>

| <span data-ttu-id="9ffa9-483">Type de compte</span><span class="sxs-lookup"><span data-stu-id="9ffa9-483">Account type</span></span> | <span data-ttu-id="9ffa9-484">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="9ffa9-484">Account number</span></span> | <span data-ttu-id="9ffa9-485">Couche</span><span class="sxs-lookup"><span data-stu-id="9ffa9-485">Layer</span></span>  | <span data-ttu-id="9ffa9-486">Description du compte</span><span class="sxs-lookup"><span data-stu-id="9ffa9-486">Account description</span></span>      | <span data-ttu-id="9ffa9-487">Débit</span><span class="sxs-lookup"><span data-stu-id="9ffa9-487">Debit</span></span>    | <span data-ttu-id="9ffa9-488">Crédit</span><span class="sxs-lookup"><span data-stu-id="9ffa9-488">Credit</span></span>   |
|--------------|----------------|--------|--------------------------|----------|----------|
| <span data-ttu-id="9ffa9-489">Registre</span><span class="sxs-lookup"><span data-stu-id="9ffa9-489">Ledger</span></span>       | <span data-ttu-id="9ffa9-490">7</span><span class="sxs-lookup"><span data-stu-id="9ffa9-490">7</span></span>              | <span data-ttu-id="9ffa9-491">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="9ffa9-491">Custom</span></span> | <span data-ttu-id="9ffa9-492">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="9ffa9-492">Finance lease obligation</span></span> | <span data-ttu-id="9ffa9-493">1,000.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-493">1,000.00</span></span> |          |
| <span data-ttu-id="9ffa9-494">Registre</span><span class="sxs-lookup"><span data-stu-id="9ffa9-494">Ledger</span></span>       | <span data-ttu-id="9ffa9-495">4</span><span class="sxs-lookup"><span data-stu-id="9ffa9-495">4</span></span>              | <span data-ttu-id="9ffa9-496">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="9ffa9-496">Custom</span></span> | <span data-ttu-id="9ffa9-497">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="9ffa9-497">Clearing account</span></span>         |          | <span data-ttu-id="9ffa9-498">1,000.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-498">1,000.00</span></span> |

<span data-ttu-id="9ffa9-499">L’écriture de journal des charges d’intérêts est générée à partir du calendrier d’amortissement du passif.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-499">The interest expense journal entry is generated from the liability amortization schedule.</span></span>

### <a name="interest-expense--1312020--je-160"></a><span data-ttu-id="9ffa9-500">Dépenses d’intérêts – 31/1/2020 – JE 160</span><span class="sxs-lookup"><span data-stu-id="9ffa9-500">Interest expense – 1/31/2020 – JE 160</span></span>

| <span data-ttu-id="9ffa9-501">Type de compte</span><span class="sxs-lookup"><span data-stu-id="9ffa9-501">Account type</span></span> | <span data-ttu-id="9ffa9-502">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="9ffa9-502">Account number</span></span> | <span data-ttu-id="9ffa9-503">Couche</span><span class="sxs-lookup"><span data-stu-id="9ffa9-503">Layer</span></span>  | <span data-ttu-id="9ffa9-504">Description du compte</span><span class="sxs-lookup"><span data-stu-id="9ffa9-504">Account description</span></span>      | <span data-ttu-id="9ffa9-505">Débit</span><span class="sxs-lookup"><span data-stu-id="9ffa9-505">Debit</span></span> | <span data-ttu-id="9ffa9-506">Crédit</span><span class="sxs-lookup"><span data-stu-id="9ffa9-506">Credit</span></span> |
|--------------|----------------|--------|--------------------------|-------|--------|
| <span data-ttu-id="9ffa9-507">Registre</span><span class="sxs-lookup"><span data-stu-id="9ffa9-507">Ledger</span></span>       | <span data-ttu-id="9ffa9-508">8</span><span class="sxs-lookup"><span data-stu-id="9ffa9-508">8</span></span>              | <span data-ttu-id="9ffa9-509">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="9ffa9-509">Custom</span></span> | <span data-ttu-id="9ffa9-510">Dépenses d’intérêts</span><span class="sxs-lookup"><span data-stu-id="9ffa9-510">Interest expense</span></span>         | <span data-ttu-id="9ffa9-511">94.97</span><span class="sxs-lookup"><span data-stu-id="9ffa9-511">94.97</span></span> |        |
| <span data-ttu-id="9ffa9-512">Registre</span><span class="sxs-lookup"><span data-stu-id="9ffa9-512">Ledger</span></span>       | <span data-ttu-id="9ffa9-513">7</span><span class="sxs-lookup"><span data-stu-id="9ffa9-513">7</span></span>              | <span data-ttu-id="9ffa9-514">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="9ffa9-514">Custom</span></span> | <span data-ttu-id="9ffa9-515">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="9ffa9-515">Finance lease obligation</span></span> |       | <span data-ttu-id="9ffa9-516">94.97</span><span class="sxs-lookup"><span data-stu-id="9ffa9-516">94.97</span></span>  |

<span data-ttu-id="9ffa9-517">L’écriture de journal de dépense d’amortissement est générée à partir du programme d’amortissement du passif.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-517">The depreciation expense journal entry is generated from the asset depreciation schedule.</span></span>

### <a name="depreciation-expense--1312020--je-170"></a><span data-ttu-id="9ffa9-518">Dépenses d’amortissement – 1/31/2020 – JE 170</span><span class="sxs-lookup"><span data-stu-id="9ffa9-518">Depreciation expense – 1/31/2020 – JE 170</span></span>

| <span data-ttu-id="9ffa9-519">Type de compte</span><span class="sxs-lookup"><span data-stu-id="9ffa9-519">Account type</span></span> | <span data-ttu-id="9ffa9-520">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="9ffa9-520">Account number</span></span> | <span data-ttu-id="9ffa9-521">Couche</span><span class="sxs-lookup"><span data-stu-id="9ffa9-521">Layer</span></span>  | <span data-ttu-id="9ffa9-522">Description du compte</span><span class="sxs-lookup"><span data-stu-id="9ffa9-522">Account description</span></span>      | <span data-ttu-id="9ffa9-523">Débit</span><span class="sxs-lookup"><span data-stu-id="9ffa9-523">Debit</span></span>  | <span data-ttu-id="9ffa9-524">Crédit</span><span class="sxs-lookup"><span data-stu-id="9ffa9-524">Credit</span></span> |
|--------------|----------------|--------|--------------------------|--------|--------|
| <span data-ttu-id="9ffa9-525">Registre</span><span class="sxs-lookup"><span data-stu-id="9ffa9-525">Ledger</span></span>       | <span data-ttu-id="9ffa9-526">10</span><span class="sxs-lookup"><span data-stu-id="9ffa9-526">10</span></span>             | <span data-ttu-id="9ffa9-527">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="9ffa9-527">Custom</span></span> | <span data-ttu-id="9ffa9-528">Dépenses d’amortissement</span><span class="sxs-lookup"><span data-stu-id="9ffa9-528">Depreciation expense</span></span>     | <span data-ttu-id="9ffa9-529">949.75</span><span class="sxs-lookup"><span data-stu-id="9ffa9-529">949.75</span></span> |        |
| <span data-ttu-id="9ffa9-530">Registre</span><span class="sxs-lookup"><span data-stu-id="9ffa9-530">Ledger</span></span>       | <span data-ttu-id="9ffa9-531">11</span><span class="sxs-lookup"><span data-stu-id="9ffa9-531">11</span></span>             | <span data-ttu-id="9ffa9-532">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="9ffa9-532">Custom</span></span> | <span data-ttu-id="9ffa9-533">Amortissement cumulé</span><span class="sxs-lookup"><span data-stu-id="9ffa9-533">Accumulated depreciation</span></span> |        | <span data-ttu-id="9ffa9-534">949.75</span><span class="sxs-lookup"><span data-stu-id="9ffa9-534">949.75</span></span> |

<span data-ttu-id="9ffa9-535">Une fois toutes ces entrées de journal créées et validées, vous verrez les valeurs de « couche personnalisée 1 » suivantes.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-535">After all these journal entries are created and posted, you will see the following "custom layer 1" values.</span></span> <span data-ttu-id="9ffa9-536">Notez que la dernière colonne comprend les frais bancaires, les frais de taxe sur la valeur ajoutée (TVA) et la réduction des liquidités de la couche précédente, mais elle n’inclut pas les écritures de reporting statutaires.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-536">Note that the last column includes the bank fee, the value-added tax (VAT) expense, and the reduction of cash from the previous layer, but it doesn't include the statutory reporting journal entries.</span></span> <span data-ttu-id="9ffa9-537">Par conséquent, vous obtenez de véritables capacités de double reporting.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-537">Therefore, you achieve true dual-reporting capabilities.</span></span> <span data-ttu-id="9ffa9-538">À ce stade, l’entreprise doit simplement exécuter sa balance comptable et combiner la couche actuelle et la couche personnalisée pour créer une balance comptable IFRS.</span><span class="sxs-lookup"><span data-stu-id="9ffa9-538">At this point, the company just has to run its trial balance, and combine the current layer and the custom layer to create an IFRS trial balance.</span></span>

| <span data-ttu-id="9ffa9-539">N° de compte</span><span class="sxs-lookup"><span data-stu-id="9ffa9-539">Account No</span></span> | <span data-ttu-id="9ffa9-540">Description</span><span class="sxs-lookup"><span data-stu-id="9ffa9-540">Description</span></span>              | <span data-ttu-id="9ffa9-541">Registre statutaire\-Couche actuelle\-JE\-100\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="9ffa9-541">Statutory Book\-Current Layer\-JE\-100\-Dr \(Cr\)</span></span> | <span data-ttu-id="9ffa9-542">Registre statutaire\-Couche actuelle\-JE\-110\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="9ffa9-542">Statutory Book\-Current Layer\-JE\-110\-Dr \(Cr\)</span></span> | <span data-ttu-id="9ffa9-543">Registre statutaire\-Couche actuelle\-JE\-120\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="9ffa9-543">Statutory Book\-Current Layer\-JE\-120\-Dr \(Cr\)</span></span> | <span data-ttu-id="9ffa9-544">Couche actuelle \- Totaux</span><span class="sxs-lookup"><span data-stu-id="9ffa9-544">Current Layer \- Totals</span></span> | - | <span data-ttu-id="9ffa9-545">Registre de contrepassation\-Couche personnalisée\-JE\-130\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="9ffa9-545">Reversal Book\-Custom layer\-JE\-130\-Dr \(Cr\)</span></span> | <span data-ttu-id="9ffa9-546">Registre IFRS 16\-Couche personnalisée\-JE\-140\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="9ffa9-546">IFRS 16 Book\-Custom layer\-JE\-140\-Dr \(Cr\)</span></span> | <span data-ttu-id="9ffa9-547">Registre IFRS 16\-Couche personnalisée\-JE\-150\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="9ffa9-547">IFRS 16 Book\-Custom layer\-JE\-150\-Dr \(Cr\)</span></span> | <span data-ttu-id="9ffa9-548">Registre IFRS 16\-Couche personnalisée\-JE\-160\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="9ffa9-548">IFRS 16 Book\-Custom layer\-JE\-160\-Dr \(Cr\)</span></span> | <span data-ttu-id="9ffa9-549">Registre IFRS 16\-Couche personnalisée\-JE\-170\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="9ffa9-549">IFRS 16 Book\-Custom layer\-JE\-170\-Dr \(Cr\)</span></span> | <span data-ttu-id="9ffa9-550">Couche personnalisée \+ Couche actuelle \- Totaux</span><span class="sxs-lookup"><span data-stu-id="9ffa9-550">Custom Layer \+ Current Layer \- Totals</span></span> |
|------------|--------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|-------------------------|---|-------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------|
| <span data-ttu-id="9ffa9-551">1</span><span class="sxs-lookup"><span data-stu-id="9ffa9-551">1</span></span>          | <span data-ttu-id="9ffa9-552">Dépense de bail</span><span class="sxs-lookup"><span data-stu-id="9ffa9-552">Lease expense</span></span>            | <span data-ttu-id="9ffa9-553">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-553">1,000\.00</span></span>                                         |                                                   |                                                   | <span data-ttu-id="9ffa9-554">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-554">1,000\.00</span></span>               |   | <span data-ttu-id="9ffa9-555">\-1 000</span><span class="sxs-lookup"><span data-stu-id="9ffa9-555">\-1,000</span></span>                                         |                                                |                                                |                                                |                                                | <span data-ttu-id="9ffa9-556">0\.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-556">0\.00</span></span>                                   |
| <span data-ttu-id="9ffa9-557">2</span><span class="sxs-lookup"><span data-stu-id="9ffa9-557">2</span></span>          | <span data-ttu-id="9ffa9-558">Frais bancaires</span><span class="sxs-lookup"><span data-stu-id="9ffa9-558">Bank fee</span></span>                 |                                                   | <span data-ttu-id="9ffa9-559">3\.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-559">3\.00</span></span>                                             |                                                   | <span data-ttu-id="9ffa9-560">3\.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-560">3\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="9ffa9-561">3\.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-561">3\.00</span></span>                                   |
| <span data-ttu-id="9ffa9-562">3</span><span class="sxs-lookup"><span data-stu-id="9ffa9-562">3</span></span>          | <span data-ttu-id="9ffa9-563">Dépenses de TVA</span><span class="sxs-lookup"><span data-stu-id="9ffa9-563">VAT expense</span></span>              |                                                   | <span data-ttu-id="9ffa9-564">5\.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-564">5\.00</span></span>                                             |                                                   | <span data-ttu-id="9ffa9-565">5\.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-565">5\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="9ffa9-566">5\.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-566">5\.00</span></span>                                   |
| <span data-ttu-id="9ffa9-567">4</span><span class="sxs-lookup"><span data-stu-id="9ffa9-567">4</span></span>          | <span data-ttu-id="9ffa9-568">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="9ffa9-568">Clearing account</span></span>         | <span data-ttu-id="9ffa9-569">\-1 000\.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-569">\-1,000\.00</span></span>                                       | <span data-ttu-id="9ffa9-570">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-570">1,000\.00</span></span>                                         |                                                   | <span data-ttu-id="9ffa9-571">0\.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-571">0\.00</span></span>                   |   | <span data-ttu-id="9ffa9-572">1 000</span><span class="sxs-lookup"><span data-stu-id="9ffa9-572">1,000</span></span>                                           |                                                | <span data-ttu-id="9ffa9-573">\-1 000</span><span class="sxs-lookup"><span data-stu-id="9ffa9-573">\-1,000</span></span>                                        |                                                |                                                | <span data-ttu-id="9ffa9-574">0\.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-574">0\.00</span></span>                                   |
| <span data-ttu-id="9ffa9-575">5</span><span class="sxs-lookup"><span data-stu-id="9ffa9-575">5</span></span>          | <span data-ttu-id="9ffa9-576">Module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="9ffa9-576">Accounts payable</span></span>         |                                                   | <span data-ttu-id="9ffa9-577">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-577">\-1,008\.00</span></span>                                       | <span data-ttu-id="9ffa9-578">1,008\.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-578">1,008\.00</span></span>                                         | <span data-ttu-id="9ffa9-579">0\.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-579">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="9ffa9-580">0\.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-580">0\.00</span></span>                                   |
| <span data-ttu-id="9ffa9-581">6</span><span class="sxs-lookup"><span data-stu-id="9ffa9-581">6</span></span>          | <span data-ttu-id="9ffa9-582">Droit d’utilisation de l’actif</span><span class="sxs-lookup"><span data-stu-id="9ffa9-582">ROU asset</span></span>                |                                                   |                                                   |                                                   | <span data-ttu-id="9ffa9-583">0\.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-583">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="9ffa9-584">22,794</span><span class="sxs-lookup"><span data-stu-id="9ffa9-584">22,794</span></span>                                         |                                                |                                                |                                                | <span data-ttu-id="9ffa9-585">22,793\.90</span><span class="sxs-lookup"><span data-stu-id="9ffa9-585">22,793\.90</span></span>                              |
| <span data-ttu-id="9ffa9-586">7</span><span class="sxs-lookup"><span data-stu-id="9ffa9-586">7</span></span>          | <span data-ttu-id="9ffa9-587">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="9ffa9-587">Finance lease obligation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="9ffa9-588">0\.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-588">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="9ffa9-589">\-22 794</span><span class="sxs-lookup"><span data-stu-id="9ffa9-589">\-22,794</span></span>                                       | <span data-ttu-id="9ffa9-590">1 000</span><span class="sxs-lookup"><span data-stu-id="9ffa9-590">1,000</span></span>                                          | <span data-ttu-id="9ffa9-591">\-94\.97</span><span class="sxs-lookup"><span data-stu-id="9ffa9-591">\-94\.97</span></span>                                       |                                                | <span data-ttu-id="9ffa9-592">\-21 888\.87</span><span class="sxs-lookup"><span data-stu-id="9ffa9-592">\-21,888\.87</span></span>                            |
| <span data-ttu-id="9ffa9-593">8</span><span class="sxs-lookup"><span data-stu-id="9ffa9-593">8</span></span>          | <span data-ttu-id="9ffa9-594">Dépenses d’intérêts</span><span class="sxs-lookup"><span data-stu-id="9ffa9-594">Interest expense</span></span>         |                                                   |                                                   |                                                   | <span data-ttu-id="9ffa9-595">0\.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-595">0\.00</span></span>                   |   |                                                 |                                                |                                                | <span data-ttu-id="9ffa9-596">94\.97</span><span class="sxs-lookup"><span data-stu-id="9ffa9-596">94\.97</span></span>                                         |                                                | <span data-ttu-id="9ffa9-597">94\.97</span><span class="sxs-lookup"><span data-stu-id="9ffa9-597">94\.97</span></span>                                  |
| <span data-ttu-id="9ffa9-598">9</span><span class="sxs-lookup"><span data-stu-id="9ffa9-598">9</span></span>          | <span data-ttu-id="9ffa9-599">Monétaire</span><span class="sxs-lookup"><span data-stu-id="9ffa9-599">Cash</span></span>                     |                                                   |                                                   | <span data-ttu-id="9ffa9-600">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-600">\-1,008\.00</span></span>                                       | <span data-ttu-id="9ffa9-601">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-601">\-1,008\.00</span></span>             |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="9ffa9-602">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-602">\-1,008\.00</span></span>                             |
| <span data-ttu-id="9ffa9-603">10</span><span class="sxs-lookup"><span data-stu-id="9ffa9-603">10</span></span>         | <span data-ttu-id="9ffa9-604">Dépenses d’amortissement</span><span class="sxs-lookup"><span data-stu-id="9ffa9-604">Depreciation expense</span></span>     |                                                   |                                                   |                                                   | <span data-ttu-id="9ffa9-605">0\.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-605">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="9ffa9-606">949\.75</span><span class="sxs-lookup"><span data-stu-id="9ffa9-606">949\.75</span></span>                                        | <span data-ttu-id="9ffa9-607">949\.75</span><span class="sxs-lookup"><span data-stu-id="9ffa9-607">949\.75</span></span>                                 |
| <span data-ttu-id="9ffa9-608">11</span><span class="sxs-lookup"><span data-stu-id="9ffa9-608">11</span></span>         | <span data-ttu-id="9ffa9-609">Amortissement cumulé</span><span class="sxs-lookup"><span data-stu-id="9ffa9-609">Accumulated depreciation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="9ffa9-610">0\.00</span><span class="sxs-lookup"><span data-stu-id="9ffa9-610">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="9ffa9-611">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="9ffa9-611">\-949\.75</span></span>                                      | <span data-ttu-id="9ffa9-612">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="9ffa9-612">\-949\.75</span></span>                               |




[!INCLUDE[footer-include](../../includes/footer-banner.md)]