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
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 96e1d4d460aef2f74422d5e4bd4fc68255466455
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2020
ms.locfileid: "4443358"
---
# <a name="dual-reporting"></a><span data-ttu-id="a7aa8-103">Double déclaration</span><span class="sxs-lookup"><span data-stu-id="a7aa8-103">Dual reporting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a7aa8-104">Cette rubrique vous guide à travers un exemple qui montre comment vous pouvez remplir les exigences à la fois pour le reporting des normes internationales d’information financière (IFRS) et le reporting statutaire dans le bail d’actifs.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-104">This topic guides you through an example that shows how you can fulfill the requirements for both International Financial Reporting Standard (IFRS) reporting and statutory reporting in Asset leasing.</span></span> <span data-ttu-id="a7aa8-105">Il est nécessaire d’être familiarisé avec les couches de validation dans Microsoft Dynamics 365 Finance, ce qui rendra l’exemple plus facile à comprendre.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-105">Familiarity with posting layers in Microsoft Dynamics 365 Finance is required and will make the example easier to understand.</span></span>

## <a name="example"></a><span data-ttu-id="a7aa8-106">Exemple</span><span class="sxs-lookup"><span data-stu-id="a7aa8-106">Example</span></span>

<span data-ttu-id="a7aa8-107">L’exemple suivant rend compte d’un contrat de location selon le reporting statutaire italien en utilisant à la fois la méthode de la comptabilité de caisse et les méthodes de reporting IFRS.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-107">The following example accounts for a lease under Italian statutory reporting by using both the cash-basis method and IFRS reporting methods.</span></span> <span data-ttu-id="a7aa8-108">L’entreprise doit établir trois registres pour tenir compte à la fois des exigences légales italiennes et des exigences d’IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-108">The company must establish three books to account for both the Italian statutory requirements and the IFRS 16 requirements.</span></span> <span data-ttu-id="a7aa8-109">Un registre est requis pour IFRS 16, un registre est requis pour les exigences statutaires et un registre est requis pour annuler automatiquement les écritures statutaires.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-109">One book is required for IFRS 16, one book is required for statutory requirements, and one book is required to automatically reverse statutory postings.</span></span> <span data-ttu-id="a7aa8-110">Les registres sont configurés comme indiqué dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-110">The books are set up as shown in the following tables.</span></span>

<span data-ttu-id="a7aa8-111">**Registre IFRS 16**</span><span class="sxs-lookup"><span data-stu-id="a7aa8-111">**IFRS 16 book**</span></span>

<span data-ttu-id="a7aa8-112">Le registre IFRS 16 est mis en place de manière à être conforme à la norme comptable IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-112">The IFRS 16 book is set up so that it complies with the IFRS 16 accounting standard.</span></span> <span data-ttu-id="a7aa8-113">Toutes les entrées publiées dans ce livre seront publiées sur une couche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-113">All entries that are posted in this book will be posted to a custom layer.</span></span>

| <span data-ttu-id="a7aa8-114">Nom</span><span class="sxs-lookup"><span data-stu-id="a7aa8-114">Name</span></span>                                    | <span data-ttu-id="a7aa8-115">Description</span><span class="sxs-lookup"><span data-stu-id="a7aa8-115">Description</span></span>    |
|-----------------------------------------|----------------|
| <span data-ttu-id="a7aa8-116">Type de registre</span><span class="sxs-lookup"><span data-stu-id="a7aa8-116">Book type</span></span>                               | <span data-ttu-id="a7aa8-117">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="a7aa8-117">IFRS 16</span></span>        |
| <span data-ttu-id="a7aa8-118">Description du registre</span><span class="sxs-lookup"><span data-stu-id="a7aa8-118">Book description</span></span>                        | <span data-ttu-id="a7aa8-119">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="a7aa8-119">IFRS 16</span></span>        |
| <span data-ttu-id="a7aa8-120">Couche de comptabilisation</span><span class="sxs-lookup"><span data-stu-id="a7aa8-120">Posting Layer</span></span>                           | <span data-ttu-id="a7aa8-121">Couche personnalisée 1</span><span class="sxs-lookup"><span data-stu-id="a7aa8-121">Custom layer 1</span></span> |
| <span data-ttu-id="a7aa8-122">Type de bail</span><span class="sxs-lookup"><span data-stu-id="a7aa8-122">Lease Type</span></span>                              | <span data-ttu-id="a7aa8-123">Finances</span><span class="sxs-lookup"><span data-stu-id="a7aa8-123">Finance</span></span>        |
| <span data-ttu-id="a7aa8-124">Structure comptable</span><span class="sxs-lookup"><span data-stu-id="a7aa8-124">Accounting Framework</span></span>                    | <span data-ttu-id="a7aa8-125">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="a7aa8-125">IFRS 16</span></span>        |
| <span data-ttu-id="a7aa8-126">Configuration Durée du bail/Durée de vie utile</span><span class="sxs-lookup"><span data-stu-id="a7aa8-126">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="a7aa8-127">0,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-127">0.00</span></span>           |
| <span data-ttu-id="a7aa8-128">Configuration Valeur actuelle/Juste valeur de l’actif</span><span class="sxs-lookup"><span data-stu-id="a7aa8-128">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="a7aa8-129">0,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-129">0.00</span></span>           |
| <span data-ttu-id="a7aa8-130">Seuil à court terme</span><span class="sxs-lookup"><span data-stu-id="a7aa8-130">Short-term threshold</span></span>                    | <span data-ttu-id="a7aa8-131">12</span><span class="sxs-lookup"><span data-stu-id="a7aa8-131">12</span></span>             |
| <span data-ttu-id="a7aa8-132">Seuil de faible valeur</span><span class="sxs-lookup"><span data-stu-id="a7aa8-132">Low Value Threshold</span></span>                     | <span data-ttu-id="a7aa8-133">5,000.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-133">5,000.00</span></span>       |
| <span data-ttu-id="a7aa8-134">Payer au fournisseur</span><span class="sxs-lookup"><span data-stu-id="a7aa8-134">Pay to Vendor</span></span>                           | <span data-ttu-id="a7aa8-135">N°</span><span class="sxs-lookup"><span data-stu-id="a7aa8-135">No</span></span>             |

<span data-ttu-id="a7aa8-136">**Registre statutaire**</span><span class="sxs-lookup"><span data-stu-id="a7aa8-136">**Statutory book**</span></span>

<span data-ttu-id="a7aa8-137">Le registre statutaire est un registre de comptabilité de caisse dans lequel la société comptabilise les frais de location comme le montant en espèces payé chaque mois pour le loyer.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-137">The statutory book is a cash-basis book where the company will account for the lease expense as the amount of cash that is paid each month for rent.</span></span> <span data-ttu-id="a7aa8-138">Ce registre ne produira pas de droit d’utilisation de l’actif (ROU) ni de passif locatif.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-138">This book won't produce a right-of-use (ROU) asset or lease liability.</span></span>

| <span data-ttu-id="a7aa8-139">Nom</span><span class="sxs-lookup"><span data-stu-id="a7aa8-139">Name</span></span>                                    | <span data-ttu-id="a7aa8-140">Description</span><span class="sxs-lookup"><span data-stu-id="a7aa8-140">Description</span></span> |
|-----------------------------------------|-------------|
| <span data-ttu-id="a7aa8-141">Type de registre</span><span class="sxs-lookup"><span data-stu-id="a7aa8-141">Book type</span></span>                               | <span data-ttu-id="a7aa8-142">Statutaire</span><span class="sxs-lookup"><span data-stu-id="a7aa8-142">Statutory</span></span>   |
| <span data-ttu-id="a7aa8-143">Description du registre</span><span class="sxs-lookup"><span data-stu-id="a7aa8-143">Book description</span></span>                        | <span data-ttu-id="a7aa8-144">GAAP local</span><span class="sxs-lookup"><span data-stu-id="a7aa8-144">Local GAAP</span></span>  |
| <span data-ttu-id="a7aa8-145">Couche de comptabilisation</span><span class="sxs-lookup"><span data-stu-id="a7aa8-145">Posting Layer</span></span>                           | <span data-ttu-id="a7aa8-146">Actuelle</span><span class="sxs-lookup"><span data-stu-id="a7aa8-146">Current</span></span>     |
| <span data-ttu-id="a7aa8-147">Type de bail</span><span class="sxs-lookup"><span data-stu-id="a7aa8-147">Lease Type</span></span>                              | <span data-ttu-id="a7aa8-148">Automatique</span><span class="sxs-lookup"><span data-stu-id="a7aa8-148">Automatic</span></span>   |
| <span data-ttu-id="a7aa8-149">Structure comptable</span><span class="sxs-lookup"><span data-stu-id="a7aa8-149">Accounting Framework</span></span>                    | <span data-ttu-id="a7aa8-150">Base de trésorerie</span><span class="sxs-lookup"><span data-stu-id="a7aa8-150">Cash basis</span></span>  |
| <span data-ttu-id="a7aa8-151">Configuration Durée du bail/Durée de vie utile</span><span class="sxs-lookup"><span data-stu-id="a7aa8-151">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="a7aa8-152">0,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-152">0.00</span></span>        |
| <span data-ttu-id="a7aa8-153">Configuration Valeur actuelle/Juste valeur de l’actif</span><span class="sxs-lookup"><span data-stu-id="a7aa8-153">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="a7aa8-154">0,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-154">0.00</span></span>        |
| <span data-ttu-id="a7aa8-155">Seuil à court terme</span><span class="sxs-lookup"><span data-stu-id="a7aa8-155">Short-term threshold</span></span>                    | <span data-ttu-id="a7aa8-156">0</span><span class="sxs-lookup"><span data-stu-id="a7aa8-156">0</span></span>           |
| <span data-ttu-id="a7aa8-157">Seuil de faible valeur</span><span class="sxs-lookup"><span data-stu-id="a7aa8-157">Low Value Threshold</span></span>                     | <span data-ttu-id="a7aa8-158">0</span><span class="sxs-lookup"><span data-stu-id="a7aa8-158">0</span></span>           |
| <span data-ttu-id="a7aa8-159">Payer au fournisseur</span><span class="sxs-lookup"><span data-stu-id="a7aa8-159">Pay to Vendor</span></span>                           | <span data-ttu-id="a7aa8-160">N°</span><span class="sxs-lookup"><span data-stu-id="a7aa8-160">No</span></span>          |

<span data-ttu-id="a7aa8-161">**Registre de contrepassation statutaire**</span><span class="sxs-lookup"><span data-stu-id="a7aa8-161">**Statutory reversal book**</span></span>

<span data-ttu-id="a7aa8-162">Le registre de contrepassation statutaire est constitué de la même manière que le registre statutaire.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-162">The statutory reversal book is set up in the same way as the statutory book.</span></span>

| <span data-ttu-id="a7aa8-163">Nom</span><span class="sxs-lookup"><span data-stu-id="a7aa8-163">Name</span></span>                                    | <span data-ttu-id="a7aa8-164">Description</span><span class="sxs-lookup"><span data-stu-id="a7aa8-164">Description</span></span>                    |
|-----------------------------------------|--------------------------------|
| <span data-ttu-id="a7aa8-165">Type de registre</span><span class="sxs-lookup"><span data-stu-id="a7aa8-165">Book type</span></span>                               | <span data-ttu-id="a7aa8-166">Statutaire – contrepassation</span><span class="sxs-lookup"><span data-stu-id="a7aa8-166">Statutory – Reversal</span></span>           |
| <span data-ttu-id="a7aa8-167">Description du registre</span><span class="sxs-lookup"><span data-stu-id="a7aa8-167">Book description</span></span>                        | <span data-ttu-id="a7aa8-168">Registre pour contrepasser le registre statutaire</span><span class="sxs-lookup"><span data-stu-id="a7aa8-168">Book to reverse statutory book</span></span> |
| <span data-ttu-id="a7aa8-169">Couche de comptabilisation</span><span class="sxs-lookup"><span data-stu-id="a7aa8-169">Posting Layer</span></span>                           | <span data-ttu-id="a7aa8-170">Couche personnalisée 1</span><span class="sxs-lookup"><span data-stu-id="a7aa8-170">Custom layer 1</span></span>                 |
| <span data-ttu-id="a7aa8-171">Type de bail</span><span class="sxs-lookup"><span data-stu-id="a7aa8-171">Lease Type</span></span>                              | <span data-ttu-id="a7aa8-172">Automatique</span><span class="sxs-lookup"><span data-stu-id="a7aa8-172">Automatic</span></span>                      |
| <span data-ttu-id="a7aa8-173">Structure comptable</span><span class="sxs-lookup"><span data-stu-id="a7aa8-173">Accounting Framework</span></span>                    | <span data-ttu-id="a7aa8-174">Base de trésorerie</span><span class="sxs-lookup"><span data-stu-id="a7aa8-174">Cash basis</span></span>                     |
| <span data-ttu-id="a7aa8-175">Configuration Durée du bail/Durée de vie utile</span><span class="sxs-lookup"><span data-stu-id="a7aa8-175">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="a7aa8-176">0,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-176">0.00</span></span>                           |
| <span data-ttu-id="a7aa8-177">Configuration Valeur actuelle/Juste valeur de l’actif</span><span class="sxs-lookup"><span data-stu-id="a7aa8-177">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="a7aa8-178">0,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-178">0.00</span></span>                           |
| <span data-ttu-id="a7aa8-179">Seuil à court terme</span><span class="sxs-lookup"><span data-stu-id="a7aa8-179">Short-term threshold</span></span>                    | <span data-ttu-id="a7aa8-180">0</span><span class="sxs-lookup"><span data-stu-id="a7aa8-180">0</span></span>                              |
| <span data-ttu-id="a7aa8-181">Seuil de faible valeur</span><span class="sxs-lookup"><span data-stu-id="a7aa8-181">Low Value Threshold</span></span>                     | <span data-ttu-id="a7aa8-182">0</span><span class="sxs-lookup"><span data-stu-id="a7aa8-182">0</span></span>                              |
| <span data-ttu-id="a7aa8-183">Payer au fournisseur</span><span class="sxs-lookup"><span data-stu-id="a7aa8-183">Pay to Vendor</span></span>                           | <span data-ttu-id="a7aa8-184">N°</span><span class="sxs-lookup"><span data-stu-id="a7aa8-184">No</span></span>                             |

<span data-ttu-id="a7aa8-185">Pour cet exemple, un bail a été créé avec les paramètres suivants sur les onglets **Général** et **Lignes d’échéancier de paiement**.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-185">For this example, a lease has been created that has the following settings on the **General** and **Payment schedule lines** tabs.</span></span>

<span data-ttu-id="a7aa8-186">**Onglet Général**</span><span class="sxs-lookup"><span data-stu-id="a7aa8-186">**General tab**</span></span>

| <span data-ttu-id="a7aa8-187">Champ</span><span class="sxs-lookup"><span data-stu-id="a7aa8-187">Field</span></span>                      | <span data-ttu-id="a7aa8-188">Valeur</span><span class="sxs-lookup"><span data-stu-id="a7aa8-188">Value</span></span>            |
|----------------------------|------------------|
| <span data-ttu-id="a7aa8-189">Taux d’emprunt marginal</span><span class="sxs-lookup"><span data-stu-id="a7aa8-189">Incremental borrowing rate</span></span> | <span data-ttu-id="a7aa8-190">5 %</span><span class="sxs-lookup"><span data-stu-id="a7aa8-190">5%</span></span>               |
| <span data-ttu-id="a7aa8-191">Date d’entrée en vigueur</span><span class="sxs-lookup"><span data-stu-id="a7aa8-191">Commencement date</span></span>          | <span data-ttu-id="a7aa8-192">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="a7aa8-192">1/1/2020</span></span>         |
| <span data-ttu-id="a7aa8-193">Groupe de baux</span><span class="sxs-lookup"><span data-stu-id="a7aa8-193">Lease group</span></span>                | <span data-ttu-id="a7aa8-194">Bâtiments</span><span class="sxs-lookup"><span data-stu-id="a7aa8-194">Buildings</span></span>        |
| <span data-ttu-id="a7aa8-195">Fournisseur</span><span class="sxs-lookup"><span data-stu-id="a7aa8-195">Vendor</span></span>                     | <span data-ttu-id="a7aa8-196">1001</span><span class="sxs-lookup"><span data-stu-id="a7aa8-196">1001</span></span>             |
| <span data-ttu-id="a7aa8-197">Juste valeur de l’actif</span><span class="sxs-lookup"><span data-stu-id="a7aa8-197">Fair value of the asset</span></span>    | <span data-ttu-id="a7aa8-198">245,000</span><span class="sxs-lookup"><span data-stu-id="a7aa8-198">245,000</span></span>          |
| <span data-ttu-id="a7aa8-199">Durée de vie utile de l’actif</span><span class="sxs-lookup"><span data-stu-id="a7aa8-199">Asset useful life</span></span>          | <span data-ttu-id="a7aa8-200">120</span><span class="sxs-lookup"><span data-stu-id="a7aa8-200">120</span></span>              |
| <span data-ttu-id="a7aa8-201">Type d’annuité</span><span class="sxs-lookup"><span data-stu-id="a7aa8-201">Annuity type</span></span>               | <span data-ttu-id="a7aa8-202">Annuité ordinaire</span><span class="sxs-lookup"><span data-stu-id="a7aa8-202">Ordinary annuity</span></span> |
| <span data-ttu-id="a7aa8-203">Intervalle de composition</span><span class="sxs-lookup"><span data-stu-id="a7aa8-203">Compounding interval</span></span>       | <span data-ttu-id="a7aa8-204">Tous les mois</span><span class="sxs-lookup"><span data-stu-id="a7aa8-204">Monthly</span></span>          |

<span data-ttu-id="a7aa8-205">**Onglet Lignes d’échéancier de paiement**</span><span class="sxs-lookup"><span data-stu-id="a7aa8-205">**Payment schedule lines tab**</span></span>

| <span data-ttu-id="a7aa8-206">Champ</span><span class="sxs-lookup"><span data-stu-id="a7aa8-206">Field</span></span>             | <span data-ttu-id="a7aa8-207">Valeur</span><span class="sxs-lookup"><span data-stu-id="a7aa8-207">Value</span></span>      |
|-------------------|------------|
| <span data-ttu-id="a7aa8-208">Date de début</span><span class="sxs-lookup"><span data-stu-id="a7aa8-208">Start date</span></span>        | <span data-ttu-id="a7aa8-209">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="a7aa8-209">1/1/2020</span></span>   |
| <span data-ttu-id="a7aa8-210">Intervalle de périodes</span><span class="sxs-lookup"><span data-stu-id="a7aa8-210">Period interval</span></span>   | <span data-ttu-id="a7aa8-211">Mois</span><span class="sxs-lookup"><span data-stu-id="a7aa8-211">Months</span></span>     |
| <span data-ttu-id="a7aa8-212">Périodes</span><span class="sxs-lookup"><span data-stu-id="a7aa8-212">Periods</span></span>           | <span data-ttu-id="a7aa8-213">24</span><span class="sxs-lookup"><span data-stu-id="a7aa8-213">24</span></span>         |
| <span data-ttu-id="a7aa8-214">Date de fin</span><span class="sxs-lookup"><span data-stu-id="a7aa8-214">End date</span></span>          | <span data-ttu-id="a7aa8-215">31/12/2020</span><span class="sxs-lookup"><span data-stu-id="a7aa8-215">12/31/2020</span></span> |
| <span data-ttu-id="a7aa8-216">Fréquence de paiement</span><span class="sxs-lookup"><span data-stu-id="a7aa8-216">Payment frequency</span></span> | <span data-ttu-id="a7aa8-217">Tous les mois</span><span class="sxs-lookup"><span data-stu-id="a7aa8-217">Monthly</span></span>    |
| <span data-ttu-id="a7aa8-218">Montant du paiement</span><span class="sxs-lookup"><span data-stu-id="a7aa8-218">Payment amount</span></span>    | <span data-ttu-id="a7aa8-219">1 000</span><span class="sxs-lookup"><span data-stu-id="a7aa8-219">1,000</span></span>      |

<span data-ttu-id="a7aa8-220">Pour tenir compte de ce bail sous deux structures, vous utilisez une couche de validation actuelle et une couche de validation personnalisée.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-220">To account for this lease under two frameworks, you use a current posting layer and a custom posting layer.</span></span> <span data-ttu-id="a7aa8-221">Le tableau suivant montre un exemple de chaque écriture de journal nécessaire pour représenter fidèlement les données financières selon chaque norme de reporting.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-221">The following table shows an example of every journal entry that required to fairly represent the financials under each reporting standard.</span></span> <span data-ttu-id="a7aa8-222">Une description détaillée de chaque écriture de journal pour le premier mois du bail est fournie par la suite.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-222">A detailed description of each journal entry for the first month of the lease is provided afterward.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="a7aa8-223">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="a7aa8-223">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="a7aa8-224">Description</span><span class="sxs-lookup"><span data-stu-id="a7aa8-224">Description</span></span></th>
<th colspan='3'><span data-ttu-id="a7aa8-225">Registre statutaire (couche actuelle)</span><span class="sxs-lookup"><span data-stu-id="a7aa8-225">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="a7aa8-226">Total de la couche actuelle</span><span class="sxs-lookup"><span data-stu-id="a7aa8-226">Current layer total</span></span></th>
<th><span data-ttu-id="a7aa8-227">Registre de contrepassation (couche personnalisée)</span><span class="sxs-lookup"><span data-stu-id="a7aa8-227">Reversal book (custom layer)</span></span></th>
<th colspan='4'><span data-ttu-id="a7aa8-228">Registre IFRS 16 (couche personnalisée)</span><span class="sxs-lookup"><span data-stu-id="a7aa8-228">IFRS 16 book (custom layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="a7aa8-229">Couche actuelle + total de la couche personnalisée</span><span class="sxs-lookup"><span data-stu-id="a7aa8-229">Current layer + custom layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="a7aa8-230">JE-100</span><span class="sxs-lookup"><span data-stu-id="a7aa8-230">JE-100</span></span></th>
<th><span data-ttu-id="a7aa8-231">JE-110</span><span class="sxs-lookup"><span data-stu-id="a7aa8-231">JE-110</span></span></th>
<th><span data-ttu-id="a7aa8-232">JE-120</span><span class="sxs-lookup"><span data-stu-id="a7aa8-232">JE-120</span></span></th>
<th><span data-ttu-id="a7aa8-233">JE-130</span><span class="sxs-lookup"><span data-stu-id="a7aa8-233">JE-130</span></span></th>
<th><span data-ttu-id="a7aa8-234">JE-140</span><span class="sxs-lookup"><span data-stu-id="a7aa8-234">JE-140</span></span></th>
<th><span data-ttu-id="a7aa8-235">JE-150</span><span class="sxs-lookup"><span data-stu-id="a7aa8-235">JE-150</span></span></th>
<th><span data-ttu-id="a7aa8-236">JE-160</span><span class="sxs-lookup"><span data-stu-id="a7aa8-236">JE-160</span></span></th>
<th><span data-ttu-id="a7aa8-237">JE-170</span><span class="sxs-lookup"><span data-stu-id="a7aa8-237">JE-170</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="a7aa8-238">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="a7aa8-238">Dr (Cr)</span></span></th>
<th><span data-ttu-id="a7aa8-239">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="a7aa8-239">Dr (Cr)</span></span></th>
<th><span data-ttu-id="a7aa8-240">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="a7aa8-240">Dr (Cr)</span></span></th>
<th><span data-ttu-id="a7aa8-241">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="a7aa8-241">Dr (Cr)</span></span></th>
<th><span data-ttu-id="a7aa8-242">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="a7aa8-242">Dr (Cr)</span></span></th>
<th><span data-ttu-id="a7aa8-243">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="a7aa8-243">Dr (Cr)</span></span></th>
<th><span data-ttu-id="a7aa8-244">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="a7aa8-244">Dr (Cr)</span></span></th>
<th><span data-ttu-id="a7aa8-245">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="a7aa8-245">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a7aa8-246">1</span><span class="sxs-lookup"><span data-stu-id="a7aa8-246">1</span></span></td>
<td><span data-ttu-id="a7aa8-247">Dépense de bail</span><span class="sxs-lookup"><span data-stu-id="a7aa8-247">Lease expense</span></span></td>
<td><span data-ttu-id="a7aa8-248">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-248">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="a7aa8-249">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-249">1,000.00</span></span></td>
<td><span data-ttu-id="a7aa8-250">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-250">-1,000.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a7aa8-251">0,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-251">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a7aa8-252">2</span><span class="sxs-lookup"><span data-stu-id="a7aa8-252">2</span></span></td>
<td><span data-ttu-id="a7aa8-253">Frais bancaires</span><span class="sxs-lookup"><span data-stu-id="a7aa8-253">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="a7aa8-254">3.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-254">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="a7aa8-255">3.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-255">3.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a7aa8-256">3.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-256">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a7aa8-257">3</span><span class="sxs-lookup"><span data-stu-id="a7aa8-257">3</span></span></td>
<td><span data-ttu-id="a7aa8-258">Dépenses de TVA</span><span class="sxs-lookup"><span data-stu-id="a7aa8-258">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="a7aa8-259">5.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-259">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="a7aa8-260">5.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-260">5.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a7aa8-261">5.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-261">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a7aa8-262">4</span><span class="sxs-lookup"><span data-stu-id="a7aa8-262">4</span></span></td>
<td><span data-ttu-id="a7aa8-263">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="a7aa8-263">Clearing account</span></span></td>
<td><span data-ttu-id="a7aa8-264">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-264">-1,000.00</span></span></td>
<td><span data-ttu-id="a7aa8-265">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-265">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="a7aa8-266">0,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-266">0.00</span></span></td>
<td><span data-ttu-id="a7aa8-267">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-267">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="a7aa8-268">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-268">-1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="a7aa8-269">0,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-269">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a7aa8-270">5</span><span class="sxs-lookup"><span data-stu-id="a7aa8-270">5</span></span></td>
<td><span data-ttu-id="a7aa8-271">Module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="a7aa8-271">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="a7aa8-272">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-272">-1,008.00</span></span></td>
<td><span data-ttu-id="a7aa8-273">1,008.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-273">1,008.00</span></span></td>
<td><span data-ttu-id="a7aa8-274">0,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-274">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a7aa8-275">0,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-275">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a7aa8-276">6</span><span class="sxs-lookup"><span data-stu-id="a7aa8-276">6</span></span></td>
<td><span data-ttu-id="a7aa8-277">Droit d’utilisation de l’actif</span><span class="sxs-lookup"><span data-stu-id="a7aa8-277">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a7aa8-278">0,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-278">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="a7aa8-279">22,794.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-279">22,794.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a7aa8-280">22,793.90</span><span class="sxs-lookup"><span data-stu-id="a7aa8-280">22,793.90</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a7aa8-281">7</span><span class="sxs-lookup"><span data-stu-id="a7aa8-281">7</span></span></td>
<td><span data-ttu-id="a7aa8-282">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="a7aa8-282">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a7aa8-283">0,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-283">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="a7aa8-284">-22 794,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-284">-22,794.00</span></span></td>
<td><span data-ttu-id="a7aa8-285">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-285">1,000.00</span></span></td>
<td><span data-ttu-id="a7aa8-286">-94,97</span><span class="sxs-lookup"><span data-stu-id="a7aa8-286">-94.97</span></span></td>
<td></td>
<td><span data-ttu-id="a7aa8-287">-21 888,87</span><span class="sxs-lookup"><span data-stu-id="a7aa8-287">-21,888.87</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a7aa8-288">8</span><span class="sxs-lookup"><span data-stu-id="a7aa8-288">8</span></span></td>
<td><span data-ttu-id="a7aa8-289">Dépenses d’intérêts</span><span class="sxs-lookup"><span data-stu-id="a7aa8-289">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a7aa8-290">0,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-290">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a7aa8-291">94.97</span><span class="sxs-lookup"><span data-stu-id="a7aa8-291">94.97</span></span></td>
<td></td>
<td><span data-ttu-id="a7aa8-292">94.97</span><span class="sxs-lookup"><span data-stu-id="a7aa8-292">94.97</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a7aa8-293">9</span><span class="sxs-lookup"><span data-stu-id="a7aa8-293">9</span></span></td>
<td><span data-ttu-id="a7aa8-294">Monétaire</span><span class="sxs-lookup"><span data-stu-id="a7aa8-294">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="a7aa8-295">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-295">-1,008.00</span></span></td>
<td><span data-ttu-id="a7aa8-296">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-296">-1,008.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a7aa8-297">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-297">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a7aa8-298">10</span><span class="sxs-lookup"><span data-stu-id="a7aa8-298">10</span></span></td>
<td><span data-ttu-id="a7aa8-299">Dépenses d’amortissement</span><span class="sxs-lookup"><span data-stu-id="a7aa8-299">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a7aa8-300">0,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-300">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a7aa8-301">949.75</span><span class="sxs-lookup"><span data-stu-id="a7aa8-301">949.75</span></span></td>
<td><span data-ttu-id="a7aa8-302">949.75</span><span class="sxs-lookup"><span data-stu-id="a7aa8-302">949.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a7aa8-303">11</span><span class="sxs-lookup"><span data-stu-id="a7aa8-303">11</span></span></td>
<td><span data-ttu-id="a7aa8-304">Amortissement cumulé</span><span class="sxs-lookup"><span data-stu-id="a7aa8-304">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a7aa8-305">0,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-305">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a7aa8-306">-949,75</span><span class="sxs-lookup"><span data-stu-id="a7aa8-306">-949.75</span></span></td>
<td><span data-ttu-id="a7aa8-307">-949,75</span><span class="sxs-lookup"><span data-stu-id="a7aa8-307">-949.75</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a7aa8-308">Comme le montre le tableau précédent, trois registres sont tenus pour déclarer à la fois le reporting statutaire et le reporting IFRS.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-308">As the preceding table shows, three books are required to report under both statutory reporting and IFRS reporting.</span></span>

- <span data-ttu-id="a7aa8-309">Le registre statutaire enregistre le paiement de location selon les règles de comptabilité de caisse sous la couche actuelle.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-309">The statutory book records the lease payment according to the rules for cash-basis accounting under the current layer.</span></span>
- <span data-ttu-id="a7aa8-310">Le registre de contrepassation statutaire annule les écritures au journal statutaire.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-310">The statutory reversal book reverses the statutory journal entries.</span></span>
- <span data-ttu-id="a7aa8-311">Le registre IFRS 16 crée les écritures de journal requises en vertu d’IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-311">The IFRS 16 book creates the journal entries that are required under IFRS 16.</span></span>

<span data-ttu-id="a7aa8-312">Vous ne devez saisir un bail qu’une seule fois.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-312">You must enter a lease only one time.</span></span> <span data-ttu-id="a7aa8-313">Vous pouvez ensuite ouvrir la page **Registres** pour voir tous les registres associés au bail.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-313">You can then open the **Books** page to see all the books that are associated with the lease.</span></span>

> [!NOTE]
> <span data-ttu-id="a7aa8-314">Lorsque vous créez les registres, tous les trois doivent être associés au même enregistrement de bail.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-314">When you create the books, all three of them must be associated with the same lease record.</span></span>

<span data-ttu-id="a7aa8-315">La première écriture de journal enregistre les frais de location dans le registre statutaire.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-315">The first journal entry records the lease expense under the statutory book.</span></span> <span data-ttu-id="a7aa8-316">Vous pouvez créer les paiements soit par lots, soit en sélectionnant l’échéancier de paiement dans le registre statutaire.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-316">You can create the payments either in a batch or by selecting the payment schedule in the statutory book.</span></span>

<span data-ttu-id="a7aa8-317">Pour cet exemple, l’écriture de journal suivante est produite pour le registre statutaire à partir de l’échéancier de paiement.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-317">For this example, the following journal entry is produced for the statutory book from the payment schedule.</span></span>

### <a name="lease-payment--1312020--je-100"></a><span data-ttu-id="a7aa8-318">Paiement de location – 31/01/2020 – JE 100</span><span class="sxs-lookup"><span data-stu-id="a7aa8-318">Lease payment – 1/31/2020 – JE 100</span></span>

| <span data-ttu-id="a7aa8-319">Type de compte</span><span class="sxs-lookup"><span data-stu-id="a7aa8-319">Account type</span></span> | <span data-ttu-id="a7aa8-320">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="a7aa8-320">Account number</span></span> | <span data-ttu-id="a7aa8-321">Couche</span><span class="sxs-lookup"><span data-stu-id="a7aa8-321">Layer</span></span>   | <span data-ttu-id="a7aa8-322">Description du compte</span><span class="sxs-lookup"><span data-stu-id="a7aa8-322">Account description</span></span> | <span data-ttu-id="a7aa8-323">Débit</span><span class="sxs-lookup"><span data-stu-id="a7aa8-323">Debit</span></span>    | <span data-ttu-id="a7aa8-324">Crédit</span><span class="sxs-lookup"><span data-stu-id="a7aa8-324">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="a7aa8-325">Registre</span><span class="sxs-lookup"><span data-stu-id="a7aa8-325">Ledger</span></span>       | <span data-ttu-id="a7aa8-326">1</span><span class="sxs-lookup"><span data-stu-id="a7aa8-326">1</span></span>              | <span data-ttu-id="a7aa8-327">Actuelle</span><span class="sxs-lookup"><span data-stu-id="a7aa8-327">Current</span></span> | <span data-ttu-id="a7aa8-328">Dépense de bail</span><span class="sxs-lookup"><span data-stu-id="a7aa8-328">Lease expense</span></span>       | <span data-ttu-id="a7aa8-329">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-329">1,000.00</span></span> |          |
| <span data-ttu-id="a7aa8-330">Registre</span><span class="sxs-lookup"><span data-stu-id="a7aa8-330">Ledger</span></span>       | <span data-ttu-id="a7aa8-331">4</span><span class="sxs-lookup"><span data-stu-id="a7aa8-331">4</span></span>              | <span data-ttu-id="a7aa8-332">Actuelle</span><span class="sxs-lookup"><span data-stu-id="a7aa8-332">Current</span></span> | <span data-ttu-id="a7aa8-333">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="a7aa8-333">Clearing account</span></span>    |          | <span data-ttu-id="a7aa8-334">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-334">1,000.00</span></span> |

<span data-ttu-id="a7aa8-335">Un commis aux comptes fournisseurs utilise la fonctionnalité standard de Dynamics 365 pour créer une facture pour payer le bail en dehors de la location d’actifs.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-335">An Accounts payable clerk uses standard Dynamics 365 functionality to create an invoice to pay for the lease outside Asset leasing.</span></span> <span data-ttu-id="a7aa8-336">Cependant, au lieu de sélectionner **Frais de location** comme compte de débit, le commis aux comptes fournisseurs sélectionne un compte de compensation pour générer l’écriture suivante.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-336">However, instead of selecting **Lease expense** as the debit account, the Accounts payable clerk selects a clearing account to generate the following entry.</span></span>

### <a name="ap-process--1312020--je-110"></a><span data-ttu-id="a7aa8-337">Processus AP – 31/01/2020 – JE 110</span><span class="sxs-lookup"><span data-stu-id="a7aa8-337">AP process – 1/31/2020 – JE 110</span></span>

| <span data-ttu-id="a7aa8-338">Type de compte</span><span class="sxs-lookup"><span data-stu-id="a7aa8-338">Account type</span></span> | <span data-ttu-id="a7aa8-339">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="a7aa8-339">Account number</span></span> | <span data-ttu-id="a7aa8-340">Couche</span><span class="sxs-lookup"><span data-stu-id="a7aa8-340">Layer</span></span>   | <span data-ttu-id="a7aa8-341">Description du compte</span><span class="sxs-lookup"><span data-stu-id="a7aa8-341">Account description</span></span> | <span data-ttu-id="a7aa8-342">Débit</span><span class="sxs-lookup"><span data-stu-id="a7aa8-342">Debit</span></span>    | <span data-ttu-id="a7aa8-343">Crédit</span><span class="sxs-lookup"><span data-stu-id="a7aa8-343">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="a7aa8-344">Registre</span><span class="sxs-lookup"><span data-stu-id="a7aa8-344">Ledger</span></span>       | <span data-ttu-id="a7aa8-345">4</span><span class="sxs-lookup"><span data-stu-id="a7aa8-345">4</span></span>              | <span data-ttu-id="a7aa8-346">Actuelle</span><span class="sxs-lookup"><span data-stu-id="a7aa8-346">Current</span></span> | <span data-ttu-id="a7aa8-347">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="a7aa8-347">Clearing account</span></span>    | <span data-ttu-id="a7aa8-348">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-348">1,000.00</span></span> |          |
| <span data-ttu-id="a7aa8-349">Registre</span><span class="sxs-lookup"><span data-stu-id="a7aa8-349">Ledger</span></span>       | <span data-ttu-id="a7aa8-350">2</span><span class="sxs-lookup"><span data-stu-id="a7aa8-350">2</span></span>              | <span data-ttu-id="a7aa8-351">Actuelle</span><span class="sxs-lookup"><span data-stu-id="a7aa8-351">Current</span></span> | <span data-ttu-id="a7aa8-352">Frais bancaires</span><span class="sxs-lookup"><span data-stu-id="a7aa8-352">Bank fee</span></span>            | <span data-ttu-id="a7aa8-353">3.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-353">3.00</span></span>     |          |
| <span data-ttu-id="a7aa8-354">Registre</span><span class="sxs-lookup"><span data-stu-id="a7aa8-354">Ledger</span></span>       | <span data-ttu-id="a7aa8-355">3</span><span class="sxs-lookup"><span data-stu-id="a7aa8-355">3</span></span>              | <span data-ttu-id="a7aa8-356">Actuelle</span><span class="sxs-lookup"><span data-stu-id="a7aa8-356">Current</span></span> | <span data-ttu-id="a7aa8-357">Dépenses de TVA</span><span class="sxs-lookup"><span data-stu-id="a7aa8-357">VAT expense</span></span>         | <span data-ttu-id="a7aa8-358">5.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-358">5.00</span></span>     |          |
| <span data-ttu-id="a7aa8-359">Fournisseur</span><span class="sxs-lookup"><span data-stu-id="a7aa8-359">Vendor</span></span>       | <span data-ttu-id="a7aa8-360">5</span><span class="sxs-lookup"><span data-stu-id="a7aa8-360">5</span></span>              | <span data-ttu-id="a7aa8-361">Actuelle</span><span class="sxs-lookup"><span data-stu-id="a7aa8-361">Current</span></span> | <span data-ttu-id="a7aa8-362">Module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="a7aa8-362">Accounts payable</span></span>    |          | <span data-ttu-id="a7aa8-363">1,008.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-363">1,008.00</span></span> |

<span data-ttu-id="a7aa8-364">Lorsque la déclaration est délivrée au fournisseur, vous suivez le processus de paiement régulier.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-364">When the statement is issued to the vendor, you follow the regular payment process.</span></span> <span data-ttu-id="a7aa8-365">Au cours de ce processus, l’écriture de journal suivante est générée.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-365">During this process, the following journal entry is generated.</span></span>

### <a name="cash-payment--1312020--je-120"></a><span data-ttu-id="a7aa8-366">Paiement en espèces – 31/01/2020 – JE 120</span><span class="sxs-lookup"><span data-stu-id="a7aa8-366">Cash payment – 1/31/2020 – JE 120</span></span>

| <span data-ttu-id="a7aa8-367">Type de compte</span><span class="sxs-lookup"><span data-stu-id="a7aa8-367">Account type</span></span> | <span data-ttu-id="a7aa8-368">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="a7aa8-368">Account number</span></span> | <span data-ttu-id="a7aa8-369">Couche</span><span class="sxs-lookup"><span data-stu-id="a7aa8-369">Layer</span></span>   | <span data-ttu-id="a7aa8-370">Description du compte</span><span class="sxs-lookup"><span data-stu-id="a7aa8-370">Account description</span></span> | <span data-ttu-id="a7aa8-371">Débit</span><span class="sxs-lookup"><span data-stu-id="a7aa8-371">Debit</span></span>    | <span data-ttu-id="a7aa8-372">Crédit</span><span class="sxs-lookup"><span data-stu-id="a7aa8-372">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="a7aa8-373">Fournisseur</span><span class="sxs-lookup"><span data-stu-id="a7aa8-373">Vendor</span></span>       | <span data-ttu-id="a7aa8-374">5</span><span class="sxs-lookup"><span data-stu-id="a7aa8-374">5</span></span>              | <span data-ttu-id="a7aa8-375">Actuelle</span><span class="sxs-lookup"><span data-stu-id="a7aa8-375">Current</span></span> | <span data-ttu-id="a7aa8-376">Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="a7aa8-376">Accounts Payable</span></span>    | <span data-ttu-id="a7aa8-377">1,008.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-377">1,008.00</span></span> |          |
| <span data-ttu-id="a7aa8-378">Banque</span><span class="sxs-lookup"><span data-stu-id="a7aa8-378">Bank</span></span>         | <span data-ttu-id="a7aa8-379">9</span><span class="sxs-lookup"><span data-stu-id="a7aa8-379">9</span></span>              | <span data-ttu-id="a7aa8-380">Actuelle</span><span class="sxs-lookup"><span data-stu-id="a7aa8-380">Current</span></span> | <span data-ttu-id="a7aa8-381">Monétaire</span><span class="sxs-lookup"><span data-stu-id="a7aa8-381">Cash</span></span>                |          | <span data-ttu-id="a7aa8-382">1,008.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-382">1,008.00</span></span> |

<span data-ttu-id="a7aa8-383">À ce stade, vous avez pleinement pris en compte ce bail conformément aux exigences légales en matière de rapports et pouvez générer une balance comptable en utilisant la couche actuelle.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-383">At this point, you've fully accounted for this lease under statutory reporting requirements and can generate a trial balance by using the current layer.</span></span> <span data-ttu-id="a7aa8-384">Le système renvoie une balance comptable qui a les chiffres suivants.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-384">The system returns a trial balance that has the following figures.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="a7aa8-385">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="a7aa8-385">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="a7aa8-386">Description</span><span class="sxs-lookup"><span data-stu-id="a7aa8-386">Description</span></span></th>
<th colspan='3'><span data-ttu-id="a7aa8-387">Registre statutaire (couche actuelle)</span><span class="sxs-lookup"><span data-stu-id="a7aa8-387">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="a7aa8-388">Total de la couche actuelle</span><span class="sxs-lookup"><span data-stu-id="a7aa8-388">Current layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="a7aa8-389">JE-100</span><span class="sxs-lookup"><span data-stu-id="a7aa8-389">JE-100</span></span></th>
<th><span data-ttu-id="a7aa8-390">JE-110</span><span class="sxs-lookup"><span data-stu-id="a7aa8-390">JE-110</span></span></th>
<th><span data-ttu-id="a7aa8-391">JE-120</span><span class="sxs-lookup"><span data-stu-id="a7aa8-391">JE-120</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="a7aa8-392">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="a7aa8-392">Dr (Cr)</span></span></th>
<th><span data-ttu-id="a7aa8-393">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="a7aa8-393">Dr (Cr)</span></span></th>
<th><span data-ttu-id="a7aa8-394">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="a7aa8-394">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a7aa8-395">1</span><span class="sxs-lookup"><span data-stu-id="a7aa8-395">1</span></span></td>
<td><span data-ttu-id="a7aa8-396">Dépense de bail</span><span class="sxs-lookup"><span data-stu-id="a7aa8-396">Lease expense</span></span></td>
<td><span data-ttu-id="a7aa8-397">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-397">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="a7aa8-398">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-398">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a7aa8-399">2</span><span class="sxs-lookup"><span data-stu-id="a7aa8-399">2</span></span></td>
<td><span data-ttu-id="a7aa8-400">Frais bancaires</span><span class="sxs-lookup"><span data-stu-id="a7aa8-400">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="a7aa8-401">3.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-401">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="a7aa8-402">3.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-402">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a7aa8-403">3</span><span class="sxs-lookup"><span data-stu-id="a7aa8-403">3</span></span></td>
<td><span data-ttu-id="a7aa8-404">Dépenses de TVA</span><span class="sxs-lookup"><span data-stu-id="a7aa8-404">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="a7aa8-405">5.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-405">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="a7aa8-406">5.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-406">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a7aa8-407">4</span><span class="sxs-lookup"><span data-stu-id="a7aa8-407">4</span></span></td>
<td><span data-ttu-id="a7aa8-408">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="a7aa8-408">Clearing account</span></span></td>
<td><span data-ttu-id="a7aa8-409">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-409">-1,000.00</span></span></td>
<td><span data-ttu-id="a7aa8-410">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-410">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="a7aa8-411">0,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-411">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a7aa8-412">5</span><span class="sxs-lookup"><span data-stu-id="a7aa8-412">5</span></span></td>
<td><span data-ttu-id="a7aa8-413">Module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="a7aa8-413">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="a7aa8-414">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-414">-1,008.00</span></span></td>
<td><span data-ttu-id="a7aa8-415">1,008.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-415">1,008.00</span></span></td>
<td><span data-ttu-id="a7aa8-416">0,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-416">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a7aa8-417">6</span><span class="sxs-lookup"><span data-stu-id="a7aa8-417">6</span></span></td>
<td><span data-ttu-id="a7aa8-418">Droit d’utilisation de l’actif</span><span class="sxs-lookup"><span data-stu-id="a7aa8-418">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a7aa8-419">0,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-419">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a7aa8-420">7</span><span class="sxs-lookup"><span data-stu-id="a7aa8-420">7</span></span></td>
<td><span data-ttu-id="a7aa8-421">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="a7aa8-421">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a7aa8-422">0,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-422">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a7aa8-423">8</span><span class="sxs-lookup"><span data-stu-id="a7aa8-423">8</span></span></td>
<td><span data-ttu-id="a7aa8-424">Dépenses d’intérêts</span><span class="sxs-lookup"><span data-stu-id="a7aa8-424">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a7aa8-425">0,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-425">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a7aa8-426">9</span><span class="sxs-lookup"><span data-stu-id="a7aa8-426">9</span></span></td>
<td><span data-ttu-id="a7aa8-427">Monétaire</span><span class="sxs-lookup"><span data-stu-id="a7aa8-427">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="a7aa8-428">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-428">-1,008.00</span></span></td>
<td><span data-ttu-id="a7aa8-429">+1 008,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-429">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a7aa8-430">10</span><span class="sxs-lookup"><span data-stu-id="a7aa8-430">10</span></span></td>
<td><span data-ttu-id="a7aa8-431">Dépenses d’amortissement</span><span class="sxs-lookup"><span data-stu-id="a7aa8-431">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a7aa8-432">0,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-432">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a7aa8-433">11</span><span class="sxs-lookup"><span data-stu-id="a7aa8-433">11</span></span></td>
<td><span data-ttu-id="a7aa8-434">Amortissement cumulé</span><span class="sxs-lookup"><span data-stu-id="a7aa8-434">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="a7aa8-435">0,00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-435">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a7aa8-436">Si vous souhaitez utiliser les chiffres IFRS 16 pour exécuter la même balance comptable, les écritures comptables statutaires doivent être contrepassées et les écritures comptables IFRS 16 doivent être enregistrées.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-436">If you want to use the IFRS 16 figures to run the same trial balance, the statutory accounting journal entries must be reversed, and the IFRS 16 journal entries must be posted.</span></span> <span data-ttu-id="a7aa8-437">Pour contrepasser les écritures statutaires, cet exemple inclut un registre de contrepassation statutaire qui a la même configuration que le registre statutaire mais un profil de validation opposé.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-437">To reverse the statutory journal entries, this example includes a statutory reversal book that has the same setup as the statutory book but an opposite posting profile.</span></span> <span data-ttu-id="a7aa8-438">Par exemple, le registre statutaire *a débité* un compte de charges de location, mais le registre de contrepassation va *créditer* ce compte.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-438">For example, the statutory book *debited* a lease expense account, but the reversal book will *credit* this account.</span></span> <span data-ttu-id="a7aa8-439">Ces relations sont facilement définies dans les comptes de comptabilisation de la location d’actifs sur la page **Paramètres de location d’actifs** (**Location d’actifs \> Configurer \> Paramètres de location d’actifs**).</span><span class="sxs-lookup"><span data-stu-id="a7aa8-439">These relationships are easily defined in the Asset leasing posting accounts on the **Asset leasing parameters** page (**Asset leasing \> Setup \> Asset leasing parameters**).</span></span>

<span data-ttu-id="a7aa8-440">Lorsque le même processus que celui utilisé pour le registre statutaire est utilisé pour le registre de contrepassation, l’écriture de journal suivante est produite.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-440">When the same process that was used for the statutory book is used for the reversal book, the following journal entry is produced.</span></span> <span data-ttu-id="a7aa8-441">La différence est que le registre de contrepassation comptabilise les écritures de contrepassation du registre statutaire.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-441">The difference is that the reversal book books the reversing entries from the statutory book.</span></span> <span data-ttu-id="a7aa8-442">Les écritures de contrepassation sont également apportées à la couche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-442">The reversing entries are also made to the custom layer.</span></span> <span data-ttu-id="a7aa8-443">Lorsqu’une balance comptable est exécutée au niveau de la couche actuelle, les écritures de journal de contrepassation ne sont pas incluses.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-443">When a trial balance is run at the current layer, the reversing journal entries aren't included.</span></span>

### <a name="lease-payment--1312020--je-130"></a><span data-ttu-id="a7aa8-444">Paiement de location – 31/01/2020 – JE 130</span><span class="sxs-lookup"><span data-stu-id="a7aa8-444">Lease payment – 1/31/2020 – JE 130</span></span>

| <span data-ttu-id="a7aa8-445">Type de compte</span><span class="sxs-lookup"><span data-stu-id="a7aa8-445">Account type</span></span> | <span data-ttu-id="a7aa8-446">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="a7aa8-446">Account number</span></span> | <span data-ttu-id="a7aa8-447">Couche</span><span class="sxs-lookup"><span data-stu-id="a7aa8-447">Layer</span></span>  | <span data-ttu-id="a7aa8-448">Description du compte</span><span class="sxs-lookup"><span data-stu-id="a7aa8-448">Account description</span></span> | <span data-ttu-id="a7aa8-449">Débit</span><span class="sxs-lookup"><span data-stu-id="a7aa8-449">Debit</span></span>    | <span data-ttu-id="a7aa8-450">Crédit</span><span class="sxs-lookup"><span data-stu-id="a7aa8-450">Credit</span></span>   |
|--------------|----------------|--------|---------------------|----------|----------|
| <span data-ttu-id="a7aa8-451">Registre</span><span class="sxs-lookup"><span data-stu-id="a7aa8-451">Ledger</span></span>       | <span data-ttu-id="a7aa8-452">4</span><span class="sxs-lookup"><span data-stu-id="a7aa8-452">4</span></span>              | <span data-ttu-id="a7aa8-453">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="a7aa8-453">Custom</span></span> | <span data-ttu-id="a7aa8-454">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="a7aa8-454">Clearing account</span></span>    | <span data-ttu-id="a7aa8-455">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-455">1,000.00</span></span> |          |
| <span data-ttu-id="a7aa8-456">Registre</span><span class="sxs-lookup"><span data-stu-id="a7aa8-456">Ledger</span></span>       | <span data-ttu-id="a7aa8-457">1</span><span class="sxs-lookup"><span data-stu-id="a7aa8-457">1</span></span>              | <span data-ttu-id="a7aa8-458">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="a7aa8-458">Custom</span></span> | <span data-ttu-id="a7aa8-459">Dépense de bail</span><span class="sxs-lookup"><span data-stu-id="a7aa8-459">Lease expense</span></span>       |          | <span data-ttu-id="a7aa8-460">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-460">1,000.00</span></span> |

<span data-ttu-id="a7aa8-461">Maintenant que vous avez éliminé les écritures de journal statutaires, vous allez enregistrer toutes les écritures de journal requises par IFRS 16 dans le livre IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-461">Now that you've eliminated the statutory journal entries, you will book all the journal entries that IFRS 16 requires in the IFRS 16 book.</span></span> <span data-ttu-id="a7aa8-462">Ces écritures comprennent la reconnaissance initiale du droit d’utilisation de l’actif et du passif, ainsi que l’enregistrement des intérêts et des amortissements.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-462">These entries include the initial recognition of the ROU asset and the liability, and the record of interest and depreciation.</span></span>

### <a name="initial-recognition--112020--je-140"></a><span data-ttu-id="a7aa8-463">Reconnaissance initiale – 1/1/2020 – JE 140</span><span class="sxs-lookup"><span data-stu-id="a7aa8-463">Initial recognition – 1/1/2020 – JE 140</span></span>

| <span data-ttu-id="a7aa8-464">Type de compte</span><span class="sxs-lookup"><span data-stu-id="a7aa8-464">Account type</span></span> | <span data-ttu-id="a7aa8-465">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="a7aa8-465">Account number</span></span> | <span data-ttu-id="a7aa8-466">Couche</span><span class="sxs-lookup"><span data-stu-id="a7aa8-466">Layer</span></span>  | <span data-ttu-id="a7aa8-467">Description du compte</span><span class="sxs-lookup"><span data-stu-id="a7aa8-467">Account description</span></span>      | <span data-ttu-id="a7aa8-468">Débit</span><span class="sxs-lookup"><span data-stu-id="a7aa8-468">Debit</span></span>     | <span data-ttu-id="a7aa8-469">Crédit</span><span class="sxs-lookup"><span data-stu-id="a7aa8-469">Credit</span></span>    |
|--------------|----------------|--------|--------------------------|-----------|-----------|
| <span data-ttu-id="a7aa8-470">Registre</span><span class="sxs-lookup"><span data-stu-id="a7aa8-470">Ledger</span></span>       | <span data-ttu-id="a7aa8-471">6</span><span class="sxs-lookup"><span data-stu-id="a7aa8-471">6</span></span>              | <span data-ttu-id="a7aa8-472">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="a7aa8-472">Custom</span></span> | <span data-ttu-id="a7aa8-473">Droit d’utilisation de l’actif</span><span class="sxs-lookup"><span data-stu-id="a7aa8-473">ROU Asset</span></span>                | <span data-ttu-id="a7aa8-474">22,793.90</span><span class="sxs-lookup"><span data-stu-id="a7aa8-474">22,793.90</span></span> |           |
| <span data-ttu-id="a7aa8-475">Registre</span><span class="sxs-lookup"><span data-stu-id="a7aa8-475">Ledger</span></span>       | <span data-ttu-id="a7aa8-476">7</span><span class="sxs-lookup"><span data-stu-id="a7aa8-476">7</span></span>              | <span data-ttu-id="a7aa8-477">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="a7aa8-477">Custom</span></span> | <span data-ttu-id="a7aa8-478">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="a7aa8-478">Finance lease obligation</span></span> |           | <span data-ttu-id="a7aa8-479">22,793.90</span><span class="sxs-lookup"><span data-stu-id="a7aa8-479">22,793.90</span></span> |

<span data-ttu-id="a7aa8-480">Le paiement de location est comptabilisé comme les autres paiements de location.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-480">The lease payment is posted like the other lease payments.</span></span> <span data-ttu-id="a7aa8-481">La raison de l’utilisation du compte de compensation est de s’assurer que les espèces ne sont créditées qu’une seule fois.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-481">The reason for using the clearing account is to ensure that cash is credited only one time.</span></span>

### <a name="lease-payment--1312020--je-150"></a><span data-ttu-id="a7aa8-482">Paiement de location – 31/01/2020 – JE 150</span><span class="sxs-lookup"><span data-stu-id="a7aa8-482">Lease payment – 1/31/2020 – JE 150</span></span>

| <span data-ttu-id="a7aa8-483">Type de compte</span><span class="sxs-lookup"><span data-stu-id="a7aa8-483">Account type</span></span> | <span data-ttu-id="a7aa8-484">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="a7aa8-484">Account number</span></span> | <span data-ttu-id="a7aa8-485">Couche</span><span class="sxs-lookup"><span data-stu-id="a7aa8-485">Layer</span></span>  | <span data-ttu-id="a7aa8-486">Description du compte</span><span class="sxs-lookup"><span data-stu-id="a7aa8-486">Account description</span></span>      | <span data-ttu-id="a7aa8-487">Débit</span><span class="sxs-lookup"><span data-stu-id="a7aa8-487">Debit</span></span>    | <span data-ttu-id="a7aa8-488">Crédit</span><span class="sxs-lookup"><span data-stu-id="a7aa8-488">Credit</span></span>   |
|--------------|----------------|--------|--------------------------|----------|----------|
| <span data-ttu-id="a7aa8-489">Registre</span><span class="sxs-lookup"><span data-stu-id="a7aa8-489">Ledger</span></span>       | <span data-ttu-id="a7aa8-490">7</span><span class="sxs-lookup"><span data-stu-id="a7aa8-490">7</span></span>              | <span data-ttu-id="a7aa8-491">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="a7aa8-491">Custom</span></span> | <span data-ttu-id="a7aa8-492">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="a7aa8-492">Finance lease obligation</span></span> | <span data-ttu-id="a7aa8-493">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-493">1,000.00</span></span> |          |
| <span data-ttu-id="a7aa8-494">Registre</span><span class="sxs-lookup"><span data-stu-id="a7aa8-494">Ledger</span></span>       | <span data-ttu-id="a7aa8-495">4</span><span class="sxs-lookup"><span data-stu-id="a7aa8-495">4</span></span>              | <span data-ttu-id="a7aa8-496">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="a7aa8-496">Custom</span></span> | <span data-ttu-id="a7aa8-497">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="a7aa8-497">Clearing account</span></span>         |          | <span data-ttu-id="a7aa8-498">1,000.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-498">1,000.00</span></span> |

<span data-ttu-id="a7aa8-499">L’écriture de journal des charges d’intérêts est générée à partir du calendrier d’amortissement du passif.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-499">The interest expense journal entry is generated from the liability amortization schedule.</span></span>

### <a name="interest-expense--1312020--je-160"></a><span data-ttu-id="a7aa8-500">Dépenses d’intérêts – 31/1/2020 – JE 160</span><span class="sxs-lookup"><span data-stu-id="a7aa8-500">Interest expense – 1/31/2020 – JE 160</span></span>

| <span data-ttu-id="a7aa8-501">Type de compte</span><span class="sxs-lookup"><span data-stu-id="a7aa8-501">Account type</span></span> | <span data-ttu-id="a7aa8-502">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="a7aa8-502">Account number</span></span> | <span data-ttu-id="a7aa8-503">Couche</span><span class="sxs-lookup"><span data-stu-id="a7aa8-503">Layer</span></span>  | <span data-ttu-id="a7aa8-504">Description du compte</span><span class="sxs-lookup"><span data-stu-id="a7aa8-504">Account description</span></span>      | <span data-ttu-id="a7aa8-505">Débit</span><span class="sxs-lookup"><span data-stu-id="a7aa8-505">Debit</span></span> | <span data-ttu-id="a7aa8-506">Crédit</span><span class="sxs-lookup"><span data-stu-id="a7aa8-506">Credit</span></span> |
|--------------|----------------|--------|--------------------------|-------|--------|
| <span data-ttu-id="a7aa8-507">Registre</span><span class="sxs-lookup"><span data-stu-id="a7aa8-507">Ledger</span></span>       | <span data-ttu-id="a7aa8-508">8</span><span class="sxs-lookup"><span data-stu-id="a7aa8-508">8</span></span>              | <span data-ttu-id="a7aa8-509">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="a7aa8-509">Custom</span></span> | <span data-ttu-id="a7aa8-510">Dépenses d’intérêts</span><span class="sxs-lookup"><span data-stu-id="a7aa8-510">Interest expense</span></span>         | <span data-ttu-id="a7aa8-511">94.97</span><span class="sxs-lookup"><span data-stu-id="a7aa8-511">94.97</span></span> |        |
| <span data-ttu-id="a7aa8-512">Registre</span><span class="sxs-lookup"><span data-stu-id="a7aa8-512">Ledger</span></span>       | <span data-ttu-id="a7aa8-513">7</span><span class="sxs-lookup"><span data-stu-id="a7aa8-513">7</span></span>              | <span data-ttu-id="a7aa8-514">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="a7aa8-514">Custom</span></span> | <span data-ttu-id="a7aa8-515">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="a7aa8-515">Finance lease obligation</span></span> |       | <span data-ttu-id="a7aa8-516">94.97</span><span class="sxs-lookup"><span data-stu-id="a7aa8-516">94.97</span></span>  |

<span data-ttu-id="a7aa8-517">L’écriture de journal de dépense d’amortissement est générée à partir du programme d’amortissement du passif.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-517">The depreciation expense journal entry is generated from the asset depreciation schedule.</span></span>

### <a name="depreciation-expense--1312020--je-170"></a><span data-ttu-id="a7aa8-518">Dépenses d’amortissement – 1/31/2020 – JE 170</span><span class="sxs-lookup"><span data-stu-id="a7aa8-518">Depreciation expense – 1/31/2020 – JE 170</span></span>

| <span data-ttu-id="a7aa8-519">Type de compte</span><span class="sxs-lookup"><span data-stu-id="a7aa8-519">Account type</span></span> | <span data-ttu-id="a7aa8-520">Numéro de compte</span><span class="sxs-lookup"><span data-stu-id="a7aa8-520">Account number</span></span> | <span data-ttu-id="a7aa8-521">Couche</span><span class="sxs-lookup"><span data-stu-id="a7aa8-521">Layer</span></span>  | <span data-ttu-id="a7aa8-522">Description du compte</span><span class="sxs-lookup"><span data-stu-id="a7aa8-522">Account description</span></span>      | <span data-ttu-id="a7aa8-523">Débit</span><span class="sxs-lookup"><span data-stu-id="a7aa8-523">Debit</span></span>  | <span data-ttu-id="a7aa8-524">Crédit</span><span class="sxs-lookup"><span data-stu-id="a7aa8-524">Credit</span></span> |
|--------------|----------------|--------|--------------------------|--------|--------|
| <span data-ttu-id="a7aa8-525">Registre</span><span class="sxs-lookup"><span data-stu-id="a7aa8-525">Ledger</span></span>       | <span data-ttu-id="a7aa8-526">10</span><span class="sxs-lookup"><span data-stu-id="a7aa8-526">10</span></span>             | <span data-ttu-id="a7aa8-527">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="a7aa8-527">Custom</span></span> | <span data-ttu-id="a7aa8-528">Dépenses d’amortissement</span><span class="sxs-lookup"><span data-stu-id="a7aa8-528">Depreciation expense</span></span>     | <span data-ttu-id="a7aa8-529">949.75</span><span class="sxs-lookup"><span data-stu-id="a7aa8-529">949.75</span></span> |        |
| <span data-ttu-id="a7aa8-530">Registre</span><span class="sxs-lookup"><span data-stu-id="a7aa8-530">Ledger</span></span>       | <span data-ttu-id="a7aa8-531">11</span><span class="sxs-lookup"><span data-stu-id="a7aa8-531">11</span></span>             | <span data-ttu-id="a7aa8-532">Personnalisée</span><span class="sxs-lookup"><span data-stu-id="a7aa8-532">Custom</span></span> | <span data-ttu-id="a7aa8-533">Amortissement cumulé</span><span class="sxs-lookup"><span data-stu-id="a7aa8-533">Accumulated depreciation</span></span> |        | <span data-ttu-id="a7aa8-534">949.75</span><span class="sxs-lookup"><span data-stu-id="a7aa8-534">949.75</span></span> |

<span data-ttu-id="a7aa8-535">Une fois toutes ces entrées de journal créées et validées, vous verrez les valeurs de « couche personnalisée 1 » suivantes.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-535">After all these journal entries are created and posted, you will see the following "custom layer 1" values.</span></span> <span data-ttu-id="a7aa8-536">Notez que la dernière colonne comprend les frais bancaires, les frais de taxe sur la valeur ajoutée (TVA) et la réduction des liquidités de la couche précédente, mais elle n’inclut pas les écritures de reporting statutaires.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-536">Note that the last column includes the bank fee, the value-added tax (VAT) expense, and the reduction of cash from the previous layer, but it doesn't include the statutory reporting journal entries.</span></span> <span data-ttu-id="a7aa8-537">Par conséquent, vous obtenez de véritables capacités de double reporting.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-537">Therefore, you achieve true dual-reporting capabilities.</span></span> <span data-ttu-id="a7aa8-538">À ce stade, l’entreprise doit simplement exécuter sa balance comptable et combiner la couche actuelle et la couche personnalisée pour créer une balance comptable IFRS.</span><span class="sxs-lookup"><span data-stu-id="a7aa8-538">At this point, the company just has to run its trial balance, and combine the current layer and the custom layer to create an IFRS trial balance.</span></span>

| <span data-ttu-id="a7aa8-539">N° de compte</span><span class="sxs-lookup"><span data-stu-id="a7aa8-539">Account No</span></span> | <span data-ttu-id="a7aa8-540">Description</span><span class="sxs-lookup"><span data-stu-id="a7aa8-540">Description</span></span>              | <span data-ttu-id="a7aa8-541">Registre statutaire\-Couche actuelle\-JE\-100\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="a7aa8-541">Statutory Book\-Current Layer\-JE\-100\-Dr \(Cr\)</span></span> | <span data-ttu-id="a7aa8-542">Registre statutaire\-Couche actuelle\-JE\-110\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="a7aa8-542">Statutory Book\-Current Layer\-JE\-110\-Dr \(Cr\)</span></span> | <span data-ttu-id="a7aa8-543">Registre statutaire\-Couche actuelle\-JE\-120\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="a7aa8-543">Statutory Book\-Current Layer\-JE\-120\-Dr \(Cr\)</span></span> | <span data-ttu-id="a7aa8-544">Couche actuelle \- Totaux</span><span class="sxs-lookup"><span data-stu-id="a7aa8-544">Current Layer \- Totals</span></span> | - | <span data-ttu-id="a7aa8-545">Registre de contrepassation\-Couche personnalisée\-JE\-130\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="a7aa8-545">Reversal Book\-Custom layer\-JE\-130\-Dr \(Cr\)</span></span> | <span data-ttu-id="a7aa8-546">Registre IFRS 16\-Couche personnalisée\-JE\-140\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="a7aa8-546">IFRS 16 Book\-Custom layer\-JE\-140\-Dr \(Cr\)</span></span> | <span data-ttu-id="a7aa8-547">Registre IFRS 16\-Couche personnalisée\-JE\-150\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="a7aa8-547">IFRS 16 Book\-Custom layer\-JE\-150\-Dr \(Cr\)</span></span> | <span data-ttu-id="a7aa8-548">Registre IFRS 16\-Couche personnalisée\-JE\-160\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="a7aa8-548">IFRS 16 Book\-Custom layer\-JE\-160\-Dr \(Cr\)</span></span> | <span data-ttu-id="a7aa8-549">Registre IFRS 16\-Couche personnalisée\-JE\-170\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="a7aa8-549">IFRS 16 Book\-Custom layer\-JE\-170\-Dr \(Cr\)</span></span> | <span data-ttu-id="a7aa8-550">Couche personnalisée \+ Couche actuelle \- Totaux</span><span class="sxs-lookup"><span data-stu-id="a7aa8-550">Custom Layer \+ Current Layer \- Totals</span></span> |
|------------|--------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|-------------------------|---|-------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------|
| <span data-ttu-id="a7aa8-551">1</span><span class="sxs-lookup"><span data-stu-id="a7aa8-551">1</span></span>          | <span data-ttu-id="a7aa8-552">Dépense de bail</span><span class="sxs-lookup"><span data-stu-id="a7aa8-552">Lease expense</span></span>            | <span data-ttu-id="a7aa8-553">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-553">1,000\.00</span></span>                                         |                                                   |                                                   | <span data-ttu-id="a7aa8-554">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-554">1,000\.00</span></span>               |   | <span data-ttu-id="a7aa8-555">\-1 000</span><span class="sxs-lookup"><span data-stu-id="a7aa8-555">\-1,000</span></span>                                         |                                                |                                                |                                                |                                                | <span data-ttu-id="a7aa8-556">0\.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-556">0\.00</span></span>                                   |
| <span data-ttu-id="a7aa8-557">2</span><span class="sxs-lookup"><span data-stu-id="a7aa8-557">2</span></span>          | <span data-ttu-id="a7aa8-558">Frais bancaires</span><span class="sxs-lookup"><span data-stu-id="a7aa8-558">Bank fee</span></span>                 |                                                   | <span data-ttu-id="a7aa8-559">3\.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-559">3\.00</span></span>                                             |                                                   | <span data-ttu-id="a7aa8-560">3\.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-560">3\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="a7aa8-561">3\.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-561">3\.00</span></span>                                   |
| <span data-ttu-id="a7aa8-562">3</span><span class="sxs-lookup"><span data-stu-id="a7aa8-562">3</span></span>          | <span data-ttu-id="a7aa8-563">Dépenses de TVA</span><span class="sxs-lookup"><span data-stu-id="a7aa8-563">VAT expense</span></span>              |                                                   | <span data-ttu-id="a7aa8-564">5\.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-564">5\.00</span></span>                                             |                                                   | <span data-ttu-id="a7aa8-565">5\.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-565">5\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="a7aa8-566">5\.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-566">5\.00</span></span>                                   |
| <span data-ttu-id="a7aa8-567">4</span><span class="sxs-lookup"><span data-stu-id="a7aa8-567">4</span></span>          | <span data-ttu-id="a7aa8-568">Compte de compensation</span><span class="sxs-lookup"><span data-stu-id="a7aa8-568">Clearing account</span></span>         | <span data-ttu-id="a7aa8-569">\-1 000\.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-569">\-1,000\.00</span></span>                                       | <span data-ttu-id="a7aa8-570">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-570">1,000\.00</span></span>                                         |                                                   | <span data-ttu-id="a7aa8-571">0\.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-571">0\.00</span></span>                   |   | <span data-ttu-id="a7aa8-572">1 000</span><span class="sxs-lookup"><span data-stu-id="a7aa8-572">1,000</span></span>                                           |                                                | <span data-ttu-id="a7aa8-573">\-1 000</span><span class="sxs-lookup"><span data-stu-id="a7aa8-573">\-1,000</span></span>                                        |                                                |                                                | <span data-ttu-id="a7aa8-574">0\.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-574">0\.00</span></span>                                   |
| <span data-ttu-id="a7aa8-575">5</span><span class="sxs-lookup"><span data-stu-id="a7aa8-575">5</span></span>          | <span data-ttu-id="a7aa8-576">Module Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="a7aa8-576">Accounts payable</span></span>         |                                                   | <span data-ttu-id="a7aa8-577">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-577">\-1,008\.00</span></span>                                       | <span data-ttu-id="a7aa8-578">1,008\.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-578">1,008\.00</span></span>                                         | <span data-ttu-id="a7aa8-579">0\.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-579">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="a7aa8-580">0\.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-580">0\.00</span></span>                                   |
| <span data-ttu-id="a7aa8-581">6</span><span class="sxs-lookup"><span data-stu-id="a7aa8-581">6</span></span>          | <span data-ttu-id="a7aa8-582">Droit d’utilisation de l’actif</span><span class="sxs-lookup"><span data-stu-id="a7aa8-582">ROU asset</span></span>                |                                                   |                                                   |                                                   | <span data-ttu-id="a7aa8-583">0\.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-583">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="a7aa8-584">22,794</span><span class="sxs-lookup"><span data-stu-id="a7aa8-584">22,794</span></span>                                         |                                                |                                                |                                                | <span data-ttu-id="a7aa8-585">22,793\.90</span><span class="sxs-lookup"><span data-stu-id="a7aa8-585">22,793\.90</span></span>                              |
| <span data-ttu-id="a7aa8-586">7</span><span class="sxs-lookup"><span data-stu-id="a7aa8-586">7</span></span>          | <span data-ttu-id="a7aa8-587">Obligation de contrat de location-financement</span><span class="sxs-lookup"><span data-stu-id="a7aa8-587">Finance lease obligation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="a7aa8-588">0\.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-588">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="a7aa8-589">\-22 794</span><span class="sxs-lookup"><span data-stu-id="a7aa8-589">\-22,794</span></span>                                       | <span data-ttu-id="a7aa8-590">1 000</span><span class="sxs-lookup"><span data-stu-id="a7aa8-590">1,000</span></span>                                          | <span data-ttu-id="a7aa8-591">\-94\.97</span><span class="sxs-lookup"><span data-stu-id="a7aa8-591">\-94\.97</span></span>                                       |                                                | <span data-ttu-id="a7aa8-592">\-21 888\.87</span><span class="sxs-lookup"><span data-stu-id="a7aa8-592">\-21,888\.87</span></span>                            |
| <span data-ttu-id="a7aa8-593">8</span><span class="sxs-lookup"><span data-stu-id="a7aa8-593">8</span></span>          | <span data-ttu-id="a7aa8-594">Dépenses d’intérêts</span><span class="sxs-lookup"><span data-stu-id="a7aa8-594">Interest expense</span></span>         |                                                   |                                                   |                                                   | <span data-ttu-id="a7aa8-595">0\.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-595">0\.00</span></span>                   |   |                                                 |                                                |                                                | <span data-ttu-id="a7aa8-596">94\.97</span><span class="sxs-lookup"><span data-stu-id="a7aa8-596">94\.97</span></span>                                         |                                                | <span data-ttu-id="a7aa8-597">94\.97</span><span class="sxs-lookup"><span data-stu-id="a7aa8-597">94\.97</span></span>                                  |
| <span data-ttu-id="a7aa8-598">9</span><span class="sxs-lookup"><span data-stu-id="a7aa8-598">9</span></span>          | <span data-ttu-id="a7aa8-599">Monétaire</span><span class="sxs-lookup"><span data-stu-id="a7aa8-599">Cash</span></span>                     |                                                   |                                                   | <span data-ttu-id="a7aa8-600">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-600">\-1,008\.00</span></span>                                       | <span data-ttu-id="a7aa8-601">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-601">\-1,008\.00</span></span>             |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="a7aa8-602">\-1 008\.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-602">\-1,008\.00</span></span>                             |
| <span data-ttu-id="a7aa8-603">10</span><span class="sxs-lookup"><span data-stu-id="a7aa8-603">10</span></span>         | <span data-ttu-id="a7aa8-604">Dépenses d’amortissement</span><span class="sxs-lookup"><span data-stu-id="a7aa8-604">Depreciation expense</span></span>     |                                                   |                                                   |                                                   | <span data-ttu-id="a7aa8-605">0\.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-605">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="a7aa8-606">949\.75</span><span class="sxs-lookup"><span data-stu-id="a7aa8-606">949\.75</span></span>                                        | <span data-ttu-id="a7aa8-607">949\.75</span><span class="sxs-lookup"><span data-stu-id="a7aa8-607">949\.75</span></span>                                 |
| <span data-ttu-id="a7aa8-608">11</span><span class="sxs-lookup"><span data-stu-id="a7aa8-608">11</span></span>         | <span data-ttu-id="a7aa8-609">Amortissement cumulé</span><span class="sxs-lookup"><span data-stu-id="a7aa8-609">Accumulated depreciation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="a7aa8-610">0\.00</span><span class="sxs-lookup"><span data-stu-id="a7aa8-610">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="a7aa8-611">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="a7aa8-611">\-949\.75</span></span>                                      | <span data-ttu-id="a7aa8-612">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="a7aa8-612">\-949\.75</span></span>                               |


