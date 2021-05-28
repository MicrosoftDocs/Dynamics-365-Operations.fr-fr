---
title: Associations de qualité
description: Cette rubrique décrit comment vous pouvez utiliser les associations de qualité dans Microsoft Dynamics 365 Supply Chain Management pour générer automatiquement des ordres de qualité liés à vos processus de vente, d'achat et de production.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2020-06-18
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6c6fab1b89b7e58d9e443c27da03a6b13afcc9c6
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022322"
---
# <a name="quality-associations"></a><span data-ttu-id="1b5aa-103">Associations de qualité</span><span class="sxs-lookup"><span data-stu-id="1b5aa-103">Quality associations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1b5aa-104">Cette rubrique décrit comment vous pouvez utiliser les associations de qualité dans Microsoft Dynamics 365 Supply Chain Management pour générer automatiquement des ordres de qualité liés à vos processus de vente, d'achat et de production.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-104">This topic describes how you can use quality associations in Microsoft Dynamics 365 Supply Chain Management to automatically generate quality orders that are related to your sales, purchase, and production processes.</span></span>

<span data-ttu-id="1b5aa-105">Une association de qualité définit toutes les informations suivantes pour un ordre de qualité qui est généré :</span><span class="sxs-lookup"><span data-stu-id="1b5aa-105">A quality association defines all the following information for a quality order that is generated:</span></span>

- <span data-ttu-id="1b5aa-106">L’événement de transaction</span><span class="sxs-lookup"><span data-stu-id="1b5aa-106">The transaction event</span></span>
- <span data-ttu-id="1b5aa-107">L’ensemble des tests qui doivent être exécutés sur les articles</span><span class="sxs-lookup"><span data-stu-id="1b5aa-107">The set of tests that must be performed on the items</span></span>
- <span data-ttu-id="1b5aa-108">Le niveau de qualité acceptable</span><span class="sxs-lookup"><span data-stu-id="1b5aa-108">The acceptable quality level (AQL)</span></span>
- <span data-ttu-id="1b5aa-109">Le programme d’échantillonnage</span><span class="sxs-lookup"><span data-stu-id="1b5aa-109">The sampling plan</span></span>

<span data-ttu-id="1b5aa-110">Vous devez définir une association de qualité pour chaque variation dans un processus d’entreprise qui requiert la génération automatique d’ordres de qualité.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-110">You must define a quality association for each variation in a business process that requires automatic generation of quality orders.</span></span> <span data-ttu-id="1b5aa-111">Par exemple, un ordre de qualité peut être généré dans le processus d’entreprise pour les commandes fournisseur, les ordres de contrôle,, les commandes client et les ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-111">For example, a quality order can be generated in the business processes for purchase orders, quarantine orders, sales orders, and production orders.</span></span>

## <a name="working-with-quality-associations"></a><span data-ttu-id="1b5aa-112">Utilisation des associations de qualité</span><span class="sxs-lookup"><span data-stu-id="1b5aa-112">Working with quality associations</span></span>

<span data-ttu-id="1b5aa-113">Le processus d’entreprise qui utilise une association de qualité peut être associé à divers documents source, tels que des commandes fournisseur, des commandes client ou des ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-113">The business process that uses a quality association can be related to various source documents, such as purchase orders, sales orders, or production orders.</span></span>

<span data-ttu-id="1b5aa-114">Chaque enregistrement d’association de qualité définit l’ensemble de tests, le niveau de qualité acceptable et le programme d’échantillonnage qui s’applique aux ordres de qualité générés.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-114">Each quality association record defines the set of tests, the AQL, and the sampling plan that applies to the quality orders that are generated.</span></span> <span data-ttu-id="1b5aa-115">Vous devez définir un enregistrement d’association de qualité pour chaque variation d’un processus d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-115">You must define a quality association record for each variation in a business process.</span></span> <span data-ttu-id="1b5aa-116">Par exemple, vous pouvez paramétrer une association de qualité qui génère un ordre de qualité lorsqu’un accusé de réception de marchandises de commande fournisseur est mis à jour.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-116">For example, you can set up a quality association that generates a quality order when a purchase order product receipt is updated.</span></span> <span data-ttu-id="1b5aa-117">En fonction de la configuration du plan d'exécution, le processus de déclenchement lui-même peut être bloqué lors d'un ordre de qualité en cours.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-117">Depending on the setup of the execution plan, the triggering process itself can be blocked while there is an open quality order.</span></span> <span data-ttu-id="1b5aa-118">Sinon, les processus ultérieurs, tels que la facturation des bons de commande, peuvent être bloqués.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-118">Alternatively, subsequent processes, such as purchase order invoicing, can be blocked.</span></span>

> [!NOTE]
> <span data-ttu-id="1b5aa-119">Tant qu’il existe des ordres de qualité en cours, le lancement des quantités en stock est automatiquement bloqué.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-119">While there are open quality orders, inventory quantities are automatically blocked from being issued.</span></span> <span data-ttu-id="1b5aa-120">En fonction du paramètre du champ **Blocage total** de la page **Échantillonnage d’article**, la quantité est soit la quantité de l’ordre de qualité, soit la quantité de la ligne de document source.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-120">Depending on the setting of the **Full blocking** field on the **Item samplings** page, the quantity is either the quantity on the quality order or the quantity on the source document line.</span></span> <span data-ttu-id="1b5aa-121">Pour plus d'informations, consultez [Échantillonnage d’articles de gestion de la qualité](quality-item-sampling.md).</span><span class="sxs-lookup"><span data-stu-id="1b5aa-121">For more information, see [Quality management item sampling](quality-item-sampling.md).</span></span>

<span data-ttu-id="1b5aa-122">Pour un processus entreprise donné, l’enregistrement d’association de qualité identifie l’événement et les conditions pour lesquels un ordre de qualité est généré.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-122">For a given business process, the quality association record identifies the event and conditions that a quality order is generated for.</span></span> <span data-ttu-id="1b5aa-123">Les conditions peuvent être spécifiques à un site ou à une entité juridique.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-123">The conditions can be specific to either a site or a legal entity.</span></span> <span data-ttu-id="1b5aa-124">Un ordre de qualité qui implique des tests destructifs ne peut être généré que si le stock disponible existe pour l’événement.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-124">A quality order that involves destructive tests can be generated only when on-hand inventory exists for the event.</span></span>

<span data-ttu-id="1b5aa-125">Pour travailler avec des associations de qualité, accédez à **Gestion des stocks \> Paramétrage \> Contrôle de la qualité \> Associations de qualité**.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-125">To work with quality associations, go to **Inventory management \> Setup \> Quality control \> Quality associations**.</span></span> <span data-ttu-id="1b5aa-126">Les exemples suivants indiquent comment un enregistrement d’association de qualité est défini pour les variations de chaque processus entreprise.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-126">The following examples show how a quality association record is defined for the variations in each business process.</span></span> <span data-ttu-id="1b5aa-127">Pour chaque exemple, le tableau suivant résume les événements et les conditions définis par un enregistrement d’association de qualité.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-127">For each example, the following table summarizes the events and conditions that are defined by a quality association record.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1b5aa-128">Type de référence</span><span class="sxs-lookup"><span data-stu-id="1b5aa-128">Reference type</span></span></th>
<th><span data-ttu-id="1b5aa-129">Type de droit</span><span class="sxs-lookup"><span data-stu-id="1b5aa-129">Event type</span></span></th>
<th><span data-ttu-id="1b5aa-130">Exécution</span><span class="sxs-lookup"><span data-stu-id="1b5aa-130">Execution</span></span></th>
<th><span data-ttu-id="1b5aa-131">Blocage d’événement</span><span class="sxs-lookup"><span data-stu-id="1b5aa-131">Event blocking</span></span></th>
<th><span data-ttu-id="1b5aa-132">Références du document</span><span class="sxs-lookup"><span data-stu-id="1b5aa-132">Document reference</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b5aa-133">Stock</span><span class="sxs-lookup"><span data-stu-id="1b5aa-133">Inventory</span></span></td>
<td><span data-ttu-id="1b5aa-134">Non applicable</span><span class="sxs-lookup"><span data-stu-id="1b5aa-134">Not applicable</span></span></td>
<td><span data-ttu-id="1b5aa-135">Non applicable</span><span class="sxs-lookup"><span data-stu-id="1b5aa-135">Not applicable</span></span></td>
<td><span data-ttu-id="1b5aa-136">Aucun(e)</span><span class="sxs-lookup"><span data-stu-id="1b5aa-136">None</span></span></td>
<td><span data-ttu-id="1b5aa-137">Tout</span><span class="sxs-lookup"><span data-stu-id="1b5aa-137">All</span></span></td>
</tr>
<tr>
<td rowspan="7"><span data-ttu-id="1b5aa-138">Ventes</span><span class="sxs-lookup"><span data-stu-id="1b5aa-138">Sales</span></span></td>
<td rowspan="4"><span data-ttu-id="1b5aa-139">Le processus de prélèvement est planifié</span><span class="sxs-lookup"><span data-stu-id="1b5aa-139">Picking process is scheduled</span></span></td>
<td rowspan="4"><span data-ttu-id="1b5aa-140">Avant</span><span class="sxs-lookup"><span data-stu-id="1b5aa-140">Before</span></span></td>
<td><span data-ttu-id="1b5aa-141">Aucun(e)</span><span class="sxs-lookup"><span data-stu-id="1b5aa-141">None</span></span></td>
<td rowspan="22"><span data-ttu-id="1b5aa-142">ID spécifique, Groupe, ou Tous uniquement</span><span class="sxs-lookup"><span data-stu-id="1b5aa-142">Specific ID, Group, or All only</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-143">Processus de prélèvement</span><span class="sxs-lookup"><span data-stu-id="1b5aa-143">Picking process</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-144">Bon de livraison</span><span class="sxs-lookup"><span data-stu-id="1b5aa-144">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-145">Facture</span><span class="sxs-lookup"><span data-stu-id="1b5aa-145">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="1b5aa-146">Bon de livraison</span><span class="sxs-lookup"><span data-stu-id="1b5aa-146">Packing slip</span></span></td>
<td rowspan="3"><span data-ttu-id="1b5aa-147">Avant</span><span class="sxs-lookup"><span data-stu-id="1b5aa-147">Before</span></span></td>
<td><span data-ttu-id="1b5aa-148">Aucun(e)</span><span class="sxs-lookup"><span data-stu-id="1b5aa-148">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-149">Bon de livraison</span><span class="sxs-lookup"><span data-stu-id="1b5aa-149">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-150">Facture</span><span class="sxs-lookup"><span data-stu-id="1b5aa-150">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="15"><span data-ttu-id="1b5aa-151">Achat</span><span class="sxs-lookup"><span data-stu-id="1b5aa-151">Purchase</span></span></td>
<td rowspan="7"><span data-ttu-id="1b5aa-152">Liste de réception</span><span class="sxs-lookup"><span data-stu-id="1b5aa-152">Receipt list</span></span></td>
<td rowspan="4"><span data-ttu-id="1b5aa-153">Avant</span><span class="sxs-lookup"><span data-stu-id="1b5aa-153">Before</span></span></td>
<td><span data-ttu-id="1b5aa-154">Aucun(e)</span><span class="sxs-lookup"><span data-stu-id="1b5aa-154">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-155">Liste de réception</span><span class="sxs-lookup"><span data-stu-id="1b5aa-155">Receipt list</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-156">Accusé de réception de marchandises</span><span class="sxs-lookup"><span data-stu-id="1b5aa-156">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-157">Facture</span><span class="sxs-lookup"><span data-stu-id="1b5aa-157">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="1b5aa-158">Après</span><span class="sxs-lookup"><span data-stu-id="1b5aa-158">After</span></span></td>
<td><span data-ttu-id="1b5aa-159">Aucun(e)</span><span class="sxs-lookup"><span data-stu-id="1b5aa-159">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-160">Accusé de réception de marchandises</span><span class="sxs-lookup"><span data-stu-id="1b5aa-160">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-161">Facture</span><span class="sxs-lookup"><span data-stu-id="1b5aa-161">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="1b5aa-162">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="1b5aa-162">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="1b5aa-163">Non applicable</span><span class="sxs-lookup"><span data-stu-id="1b5aa-163">Not applicable</span></span></td>
<td><span data-ttu-id="1b5aa-164">Aucun(e)</span><span class="sxs-lookup"><span data-stu-id="1b5aa-164">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-165">Accusé de réception de marchandises</span><span class="sxs-lookup"><span data-stu-id="1b5aa-165">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-166">Facture</span><span class="sxs-lookup"><span data-stu-id="1b5aa-166">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="1b5aa-167">Accusé de réception de marchandises</span><span class="sxs-lookup"><span data-stu-id="1b5aa-167">Product receipt</span></span></td>
<td rowspan="3"><span data-ttu-id="1b5aa-168">Avant</span><span class="sxs-lookup"><span data-stu-id="1b5aa-168">Before</span></span></td>
<td><span data-ttu-id="1b5aa-169">Aucun(e)</span><span class="sxs-lookup"><span data-stu-id="1b5aa-169">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-170">Accusé de réception de marchandises</span><span class="sxs-lookup"><span data-stu-id="1b5aa-170">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-171">Facture</span><span class="sxs-lookup"><span data-stu-id="1b5aa-171">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="1b5aa-172">Après</span><span class="sxs-lookup"><span data-stu-id="1b5aa-172">After</span></span></td>
<td><span data-ttu-id="1b5aa-173">Aucun(e)</span><span class="sxs-lookup"><span data-stu-id="1b5aa-173">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-174">Facture</span><span class="sxs-lookup"><span data-stu-id="1b5aa-174">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="8"><span data-ttu-id="1b5aa-175">Production</span><span class="sxs-lookup"><span data-stu-id="1b5aa-175">Production</span></span></td>
<td rowspan="3"><span data-ttu-id="1b5aa-176">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="1b5aa-176">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="1b5aa-177">Non applicable</span><span class="sxs-lookup"><span data-stu-id="1b5aa-177">Not applicable</span></span></td>
<td><span data-ttu-id="1b5aa-178">Aucun(e)</span><span class="sxs-lookup"><span data-stu-id="1b5aa-178">None</span></span></td>
<td rowspan="12"><span data-ttu-id="1b5aa-179">Tout</span><span class="sxs-lookup"><span data-stu-id="1b5aa-179">All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-180">Déclaration de fin</span><span class="sxs-lookup"><span data-stu-id="1b5aa-180">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-181">Fin</span><span class="sxs-lookup"><span data-stu-id="1b5aa-181">End</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="1b5aa-182">Déclaration de fin</span><span class="sxs-lookup"><span data-stu-id="1b5aa-182">Report as finished</span></span></td>
<td rowspan="3"><span data-ttu-id="1b5aa-183">Avant</span><span class="sxs-lookup"><span data-stu-id="1b5aa-183">Before</span></span></td>
<td><span data-ttu-id="1b5aa-184">Aucun(e)</span><span class="sxs-lookup"><span data-stu-id="1b5aa-184">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-185">Déclaration de fin</span><span class="sxs-lookup"><span data-stu-id="1b5aa-185">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-186">Fin</span><span class="sxs-lookup"><span data-stu-id="1b5aa-186">End</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="1b5aa-187">Après</span><span class="sxs-lookup"><span data-stu-id="1b5aa-187">After</span></span></td>
<td><span data-ttu-id="1b5aa-188">Aucun(e)</span><span class="sxs-lookup"><span data-stu-id="1b5aa-188">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-189">Fin</span><span class="sxs-lookup"><span data-stu-id="1b5aa-189">End</span></span></td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="1b5aa-190">Contrôle</span><span class="sxs-lookup"><span data-stu-id="1b5aa-190">Quarantine</span></span></td>
<td rowspan="3"><span data-ttu-id="1b5aa-191">Déclaration de fin</span><span class="sxs-lookup"><span data-stu-id="1b5aa-191">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="1b5aa-192">Avant</span><span class="sxs-lookup"><span data-stu-id="1b5aa-192">Before</span></span></td>
<td><span data-ttu-id="1b5aa-193">Déclaration de fin</span><span class="sxs-lookup"><span data-stu-id="1b5aa-193">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-194">Fin</span><span class="sxs-lookup"><span data-stu-id="1b5aa-194">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-195">Après</span><span class="sxs-lookup"><span data-stu-id="1b5aa-195">After</span></span></td>
<td><span data-ttu-id="1b5aa-196">Fin</span><span class="sxs-lookup"><span data-stu-id="1b5aa-196">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-197">Fin</span><span class="sxs-lookup"><span data-stu-id="1b5aa-197">End</span></span></td>
<td><span data-ttu-id="1b5aa-198">Avant</span><span class="sxs-lookup"><span data-stu-id="1b5aa-198">Before</span></span></td>
<td><span data-ttu-id="1b5aa-199">Fin</span><span class="sxs-lookup"><span data-stu-id="1b5aa-199">End</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="1b5aa-200">Opération de gamme</span><span class="sxs-lookup"><span data-stu-id="1b5aa-200">Route operation</span></span></td>
<td rowspan="3"><span data-ttu-id="1b5aa-201">Déclaration de fin</span><span class="sxs-lookup"><span data-stu-id="1b5aa-201">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="1b5aa-202">Avant</span><span class="sxs-lookup"><span data-stu-id="1b5aa-202">Before</span></span></td>
<td><span data-ttu-id="1b5aa-203">None</span><span class="sxs-lookup"><span data-stu-id="1b5aa-203">None</span></span></td>
<td rowspan="3"><span data-ttu-id="1b5aa-204">ID spécifique, Groupes ou Tous, et Spécifique à la ressource, Groupe ou Tous</span><span class="sxs-lookup"><span data-stu-id="1b5aa-204">Specific ID, Group, or All, and specific Resource, Group, or All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-205">Déclaration de fin</span><span class="sxs-lookup"><span data-stu-id="1b5aa-205">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-206">Après</span><span class="sxs-lookup"><span data-stu-id="1b5aa-206">After</span></span></td>
<td><span data-ttu-id="1b5aa-207">None</span><span class="sxs-lookup"><span data-stu-id="1b5aa-207">None</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="1b5aa-208">Production de coproduits</span><span class="sxs-lookup"><span data-stu-id="1b5aa-208">Co-product production</span></span></td>
<td><span data-ttu-id="1b5aa-209">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="1b5aa-209">Registration</span></span></td>
<td><span data-ttu-id="1b5aa-210">Non applicable</span><span class="sxs-lookup"><span data-stu-id="1b5aa-210">Not applicable</span></span></td>
<td rowspan="3"><span data-ttu-id="1b5aa-211">None</span><span class="sxs-lookup"><span data-stu-id="1b5aa-211">None</span></span></td>
<td rowspan="3"><span data-ttu-id="1b5aa-212">Tous</span><span class="sxs-lookup"><span data-stu-id="1b5aa-212">All</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="1b5aa-213">Déclaration de fin</span><span class="sxs-lookup"><span data-stu-id="1b5aa-213">Report as finished</span></span></td>
<td><span data-ttu-id="1b5aa-214">Avant</span><span class="sxs-lookup"><span data-stu-id="1b5aa-214">Before</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-215">Après</span><span class="sxs-lookup"><span data-stu-id="1b5aa-215">After</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="1b5aa-216">La fonctionnalité *Gestion de la qualité pour les processus d’entrepôt* ajoute des capacités de traitement des ordres de qualité pour la production avec le champ **Type d’événement** défini sur *Signaler comme terminé* et le champ **Exécution** défini sur *Après*, et pour les achats avec le champ **Type d’événement** défini sur *Enregistrement*.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-216">The *Quality management for warehouse processes* feature adds capabilities for quality order processing for production where the **Event type** field is set to *Report as finished* and the **Execution** field is set to *After*, and for purchases where the **Event type** field is set to *Registration*.</span></span> <span data-ttu-id="1b5aa-217">Pour plus d’informations, voir [Gestion de la qualité pour les processus d’entrepôt](quality-management-for-warehouses-processes.md).</span><span class="sxs-lookup"><span data-stu-id="1b5aa-217">For more information, see [Quality management for warehouse processes](quality-management-for-warehouses-processes.md).</span></span>

<span data-ttu-id="1b5aa-218">Le tableau suivant fournit plus d’informations sur la manière dont les ordres de qualité peuvent être générés pour des types de processus spécifiques.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-218">The following table provides more information about how quality orders can be generated for specific types of processes.</span></span>

<div class="tableSection">
<table>
<thead>
<tr>
<th><span data-ttu-id="1b5aa-219">Type de processus</span><span class="sxs-lookup"><span data-stu-id="1b5aa-219">Type of process</span></span></th>
<th><span data-ttu-id="1b5aa-220">Lorsque des ordres de qualité peuvent être automatiquement générés</span><span class="sxs-lookup"><span data-stu-id="1b5aa-220">When quality orders can be automatically generated</span></span></th>
<th><span data-ttu-id="1b5aa-221">Lorsque des ordres de qualité peuvent être générés si les tests destructifs sont requis</span><span class="sxs-lookup"><span data-stu-id="1b5aa-221">When quality orders can be generated if destructive testing is required</span></span></th>
<th><span data-ttu-id="1b5aa-222">Informations de condition</span><span class="sxs-lookup"><span data-stu-id="1b5aa-222">Condition information</span></span></th>
<th><span data-ttu-id="1b5aa-223">Informations de génération manuelle</span><span class="sxs-lookup"><span data-stu-id="1b5aa-223">Manual generation information</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b5aa-224">Commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="1b5aa-224">Purchase order</span></span></td>
<td><span data-ttu-id="1b5aa-225">Avant ou après la validation d’une liste de réceptions ou d’un accusé de réception de marchandises reçu pour les matières</span><span class="sxs-lookup"><span data-stu-id="1b5aa-225">Before or after a receipts list or product receipt for the material that is received is posted</span></span></td>
<td><span data-ttu-id="1b5aa-226">Après la validation de l’accusé de réception de marchandises pour les matières reçu, car les matières doivent être disponibles pour les tests destructifs</span><span class="sxs-lookup"><span data-stu-id="1b5aa-226">After the product receipt for the material that is received is posted, because the material must be available for destructive testing</span></span></td>
<td><span data-ttu-id="1b5aa-227">La nécessité d’établir un ordre de qualité peut refléter un site, un article ou un vendeur spécifique ou une combinaison de ces conditions.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-227">The requirement for a quality order can reflect a specific site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="1b5aa-228">Un ordre de qualité généré manuellement qui fait référence à une commande fournisseur peut utiliser les informations dans un enregistrement d’association de qualité, telles que le programme d’échantillonnage de test.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-228">A manually generated quality order that refers to a purchase order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-229">Ordre de contrôle</span><span class="sxs-lookup"><span data-stu-id="1b5aa-229">Quarantine order</span></span></td>
<td><span data-ttu-id="1b5aa-230">Avant ou après la déclaration de fin de l’ordre de contrôle</span><span class="sxs-lookup"><span data-stu-id="1b5aa-230">Before or after the quarantine order is reported as finished or ended</span></span></td>
<td><span data-ttu-id="1b5aa-231">Les ordres de qualité nécessitant des tests destructifs ne peuvent pas être générés.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-231">Quality orders that require destructive tests can't be generated.</span></span> <span data-ttu-id="1b5aa-232">On suppose que la fonctionnalité d'ordre de contrôle gère l'élimination des matières détruites.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-232">It's assumed that the quarantine order functionality handles the disposition of the material that is destroyed.</span></span></td>
<td><span data-ttu-id="1b5aa-233">La nécessité d’établir un ordre de qualité peut refléter un site, un article ou un vendeur spécifique ou une combinaison de ces conditions.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-233">The requirement for a quality order can reflect a specific site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="1b5aa-234">Un ordre de qualité généré manuellement qui fait référence à un ordre de contrôle peut utiliser les informations dans un enregistrement d’association de qualité, telles que le programme d’échantillonnage de test.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-234">A manually generated quality order that refers to a quarantine order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-235">Commande client</span><span class="sxs-lookup"><span data-stu-id="1b5aa-235">Sales order</span></span></td>
<td><span data-ttu-id="1b5aa-236">Avant la mise à jour d’un processus de prélèvement planifié ou d’un bon de livraison pour les articles qui sont expédiés</span><span class="sxs-lookup"><span data-stu-id="1b5aa-236">Before a scheduled picking process or packing slip update for the items that are being shipped</span></span></td>
<td><span data-ttu-id="1b5aa-237">À toute étape</span><span class="sxs-lookup"><span data-stu-id="1b5aa-237">At any step</span></span></td>
<td><span data-ttu-id="1b5aa-238">La nécessité d’établir un ordre de qualité peut refléter un site, un article ou un client spécifique ou une combinaison de ces conditions.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-238">The requirement for a quality order can reflect a specific site, item, or customer, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="1b5aa-239">Un ordre de qualité généré manuellement qui fait référence à une commande client peut utiliser les informations dans un enregistrement d’association de qualité, telles que le programme d’échantillonnage de test.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-239">A manually generated quality order that refers to a sales order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-240">Ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="1b5aa-240">Production order</span></span></td>
<td><span data-ttu-id="1b5aa-241">Avant ou après la déclaration de la quantité terminée pour l’ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="1b5aa-241">Before or after the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="1b5aa-242">Après la déclaration de la quantité terminée pour l’ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="1b5aa-242">After the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="1b5aa-243">La nécessité d’établir un ordre de qualité peut refléter un site, un article ou un vendeur spécifique ou une combinaison de ces conditions.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-243">The requirement for a quality order can reflect a specific site or item, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="1b5aa-244">Un ordre de qualité généré manuellement qui fait référence à un ordre de fabrication peut utiliser les informations dans un enregistrement d’association de qualité, telles que le programme d’échantillonnage de test.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-244">A manually generated quality order that refers to a production order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-245">Ordre de fabrication qui a une opération de gamme</span><span class="sxs-lookup"><span data-stu-id="1b5aa-245">Production order that has a route operation</span></span></td>
<td><span data-ttu-id="1b5aa-246">Avant ou après la fin de l’état pour une opération</span><span class="sxs-lookup"><span data-stu-id="1b5aa-246">Before or after the report is finished for an operation</span></span></td>
<td><span data-ttu-id="1b5aa-247">Après la déclaration de fin de production pour la dernière opération</span><span class="sxs-lookup"><span data-stu-id="1b5aa-247">After the reporting production is finished for the last operation</span></span></td>
<td><span data-ttu-id="1b5aa-248">La nécessité d’établir un ordre de qualité peut refléter un site, un article ou d’une ressource opérationnelle, ou une combinaison de ces conditions.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-248">The requirement for a quality order can reflect a specific site, item, or operations resource, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="1b5aa-249">Un ordre de qualité généré manuellement qui fait référence à une opération de gamme peut utiliser les informations dans un enregistrement d’association de qualité, telles que le programme d’échantillonnage de test.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-249">A manually generated quality order that refers to a route operation can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-250">Stocks</span><span class="sxs-lookup"><span data-stu-id="1b5aa-250">Inventory</span></span></td>
<td><span data-ttu-id="1b5aa-251">Un ordre de qualité ne peut pas être automatiquement généré pour une transaction dans un journal de stock ou pour des transactions d’ordre de transfert</span><span class="sxs-lookup"><span data-stu-id="1b5aa-251">A quality order can't be automatically generated for a transaction in an inventory journal or for transfer order transactions.</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="1b5aa-252">Un ordre de qualité doit être créé manuellement pour la quantité de stock d'un article.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-252">A quality order must be manually created for an item's inventory quantity.</span></span> <span data-ttu-id="1b5aa-253">Le stock physique disponible est exigé.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-253">Physical on-hand inventory is required.</span></span></td>
</tr>
</tbody>
</table>
</div>

## <a name="examples-of-automatic-generation-of-quality-orders"></a><span data-ttu-id="1b5aa-254">Exemples de génération automatique d’ordres de qualité</span><span class="sxs-lookup"><span data-stu-id="1b5aa-254">Examples of automatic generation of quality orders</span></span>

### <a name="purchasing"></a><span data-ttu-id="1b5aa-255">Achat en cours</span><span class="sxs-lookup"><span data-stu-id="1b5aa-255">Purchasing</span></span>

<span data-ttu-id="1b5aa-256">Dans l’achat, vous définissez le champ **Type d’événement** sur *Accusé de réception de marchandises* et le champ **Exécution** sur *Après* sur la page **Associations de qualité**, vous obtenez les résultats suivants :</span><span class="sxs-lookup"><span data-stu-id="1b5aa-256">In purchasing, if you set the **Event type** field to *Product receipt* and the **Execution** field to *After* on the **Quality associations** page, you get the following results:</span></span>

- <span data-ttu-id="1b5aa-257">Si l’option **Par quantité mise à jour** est définie sur *Oui*, un ordre de qualité est généré pour chaque réception par rapport à la commande fournisseur, selon la quantité réceptionnée et les paramètres dans l’échantillonnage d’article.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-257">If the **Per updated quantity** option is set to *Yes*, a quality order is generated for every receipt against the purchase order, based on the received quantity and settings in the item sampling.</span></span> <span data-ttu-id="1b5aa-258">Chaque fois qu’une quantité est reçue par rapport à la commande fournisseur, de nouveaux ordres de qualité sont générés selon la nouvelle quantité de réception.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-258">Every time that a quantity is received against the purchase order, new quality orders are generated based on the newly received quantity.</span></span>
- <span data-ttu-id="1b5aa-259">Si l’option **Par quantité mise à jour** est définie sur *Non*, un ordre de qualité est généré pour la première réception par rapport à la commande fournisseur, selon la quantité réceptionnée.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-259">If the **Per updated quantity** option is set to *No*, a quality order is generated for the first receipt against the purchase order, based on the received quantity.</span></span> <span data-ttu-id="1b5aa-260">En outre, un ou plusieurs ordres de qualité sont créés selon la quantité restante, selon les dimensions de suivi.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-260">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions.</span></span> <span data-ttu-id="1b5aa-261">Les ordres de qualité ne sont pas générés pour les réceptions suivantes par rapport à la commande fournisseur.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-261">Quality orders aren't generated for subsequent receipts against the purchase order.</span></span>

### <a name="production"></a><span data-ttu-id="1b5aa-262">Production</span><span class="sxs-lookup"><span data-stu-id="1b5aa-262">Production</span></span>

<span data-ttu-id="1b5aa-263">Dans la production, vous définissez le champ **Type d’événement** sur *Déclarer comme terminé* et le champ **Exécution** sur *Après* sur la page **Associations de qualité**, vous obtenez les résultats suivants :</span><span class="sxs-lookup"><span data-stu-id="1b5aa-263">In production, if you set the **Event type** field to *Report as finished* and the **Execution** field to *After* on the **Quality associations** page, you get the following results:</span></span>

- <span data-ttu-id="1b5aa-264">Si l’option **Par quantité mise à jour** est définie sur *Oui*, un ordre de qualité est généré selon chaque quantité finie et les paramètres dans l’échantillonnage d’article.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-264">If the **Per updated quantity** option is set to *Yes*, a quality order is generated based on every finished quantity and settings in the item sampling.</span></span> <span data-ttu-id="1b5aa-265">Chaque fois qu’une quantité est déclarée comme terminé par rapport à l’ordre de fabrication, de nouveaux ordres de qualité sont générés selon la quantité nouvellement terminée.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-265">Every time that a quantity is reported as finished against the production order, new quality orders are generated based on the newly finished quantity.</span></span> <span data-ttu-id="1b5aa-266">Cette logique de déclaration est compatible avec l’achat.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-266">This generation logic is consistent with purchasing.</span></span>
- <span data-ttu-id="1b5aa-267">Si l’option **Par quantité mise à jour** est définie sur *Non*, un ordre de qualité est généré la première fois qu’une quantité est déclarée comme terminée, selon la quantité finie.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-267">If the **Per updated quantity** option is set to *No*, a quality order is generated the first time that a quantity is reported as finished, based on the finished quantity.</span></span> <span data-ttu-id="1b5aa-268">En outre, un ou plusieurs ordres de qualité sont créés selon la quantité restante, selon les dimensions de suivi de l’échantillonnage d’article.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-268">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions of the item sampling.</span></span> <span data-ttu-id="1b5aa-269">Aucun ordre de qualité n’est pas créé pour les quantités terminées suivantes.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-269">Quality orders aren't generated for subsequent finished quantities.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="1b5aa-270">Spécification de la qualité</span><span class="sxs-lookup"><span data-stu-id="1b5aa-270">Quality specification</span></span></th>
<th><span data-ttu-id="1b5aa-271">Par quantité mise à jour</span><span class="sxs-lookup"><span data-stu-id="1b5aa-271">Per updated quantity</span></span></th>
<th><span data-ttu-id="1b5aa-272">Par dimension de suivi</span><span class="sxs-lookup"><span data-stu-id="1b5aa-272">Per tracking dimension</span></span></th>
<th><span data-ttu-id="1b5aa-273">Résultat</span><span class="sxs-lookup"><span data-stu-id="1b5aa-273">Result</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="1b5aa-274">Pourcentage : 10 %</span><span class="sxs-lookup"><span data-stu-id="1b5aa-274">Percentage: 10%</span></span></td>
<td><span data-ttu-id="1b5aa-275">Oui</span><span class="sxs-lookup"><span data-stu-id="1b5aa-275">Yes</span></span></td>
<td>
<p><span data-ttu-id="1b5aa-276">Numéro du lot : Non</span><span class="sxs-lookup"><span data-stu-id="1b5aa-276">Batch number: No</span></span></p>
<p><span data-ttu-id="1b5aa-277">Numéro de série : Non</span><span class="sxs-lookup"><span data-stu-id="1b5aa-277">Serial number: No</span></span></p>
</td>
<td>
<p><span data-ttu-id="1b5aa-278">Quantité de la commande : 100</span><span class="sxs-lookup"><span data-stu-id="1b5aa-278">Order quantity: 100</span></span></p>
<ol>
<li><span data-ttu-id="1b5aa-279">Déclarer comme terminé pour 30</span><span class="sxs-lookup"><span data-stu-id="1b5aa-279">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="1b5aa-280">Ordre de qualité n° 1 pour 3 (10 % de 30)</span><span class="sxs-lookup"><span data-stu-id="1b5aa-280">Quality order 1 for 3 (10% of 30)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="1b5aa-281">Déclarer comme terminé pour 70</span><span class="sxs-lookup"><span data-stu-id="1b5aa-281">Report as finished for 70</span></span>
<ul>
<li><span data-ttu-id="1b5aa-282">Ordre de qualité n° 2 pour 7 (10 % de la quantité commandée restante, qui est égale à 70 dans ce cas)</span><span class="sxs-lookup"><span data-stu-id="1b5aa-282">Quality order 2 for 7 (10% of the remaining order quantity, which is 70 in this case)</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-283">Quantité fixe : 1</span><span class="sxs-lookup"><span data-stu-id="1b5aa-283">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="1b5aa-284">N°</span><span class="sxs-lookup"><span data-stu-id="1b5aa-284">No</span></span></td>
<td>
<p><span data-ttu-id="1b5aa-285">Numéro du lot : Non</span><span class="sxs-lookup"><span data-stu-id="1b5aa-285">Batch number: No</span></span></p>
<p><span data-ttu-id="1b5aa-286">Numéro de série : Non</span><span class="sxs-lookup"><span data-stu-id="1b5aa-286">Serial number: No</span></span></p>
</td>
<td><span data-ttu-id="1b5aa-287">Quantité de la commande : 100</span><span class="sxs-lookup"><span data-stu-id="1b5aa-287">Order quantity: 100</span></span>
<ol>
<li><span data-ttu-id="1b5aa-288">Déclarer comme terminé pour 30</span><span class="sxs-lookup"><span data-stu-id="1b5aa-288">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="1b5aa-289">L’ordre de qualité n° 1 pour 1 (pour la première quantité déclarée comme terminée, qui a une valeur fixe de 1)</span><span class="sxs-lookup"><span data-stu-id="1b5aa-289">Quality order 1 for 1 (for the first reported-as-finished quantity, which has a fixed value of 1)</span></span></li>
<li><span data-ttu-id="1b5aa-290">L’ordre de qualité n° 2 pour 1 (pour la quantité restante, qui a toujours une valeur fixe de 1)</span><span class="sxs-lookup"><span data-stu-id="1b5aa-290">Quality order 2 for 1 (for the remaining quantity, which still has a fixed value of 1)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="1b5aa-291">Déclarer comme terminé pour 10</span><span class="sxs-lookup"><span data-stu-id="1b5aa-291">Report as finished for 10</span></span>
<ul>
<li><span data-ttu-id="1b5aa-292">Aucun ordre de qualité n’est créé.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-292">No quality orders are created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="1b5aa-293">Déclarer comme terminé pour 60</span><span class="sxs-lookup"><span data-stu-id="1b5aa-293">Report as finished for 60</span></span>
<ul>
<li><span data-ttu-id="1b5aa-294">Aucun ordre de qualité n’est créé.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-294">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-295">Quantité fixe : 1</span><span class="sxs-lookup"><span data-stu-id="1b5aa-295">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="1b5aa-296">Oui</span><span class="sxs-lookup"><span data-stu-id="1b5aa-296">Yes</span></span></td>
<td>
<p><span data-ttu-id="1b5aa-297">Numéro du lot : Oui</span><span class="sxs-lookup"><span data-stu-id="1b5aa-297">Batch number: Yes</span></span></p>
<p><span data-ttu-id="1b5aa-298">Numéro de série : Oui</span><span class="sxs-lookup"><span data-stu-id="1b5aa-298">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="1b5aa-299">Quantité de la commande : 10</span><span class="sxs-lookup"><span data-stu-id="1b5aa-299">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="1b5aa-300">Déclarer comme terminé pour 3 : 1 pour le numéro de lot b1, le numéro de série s1 ; 1 pour le numéro de lot b2, le numéro de série s2 ; et 1 pour le numéro de lot b3, le numéro de série s3</span><span class="sxs-lookup"><span data-stu-id="1b5aa-300">Report as finished for 3: 1 for batch number b1, serial number s1; 1 for batch number b2, serial number s2; and 1 for batch number b3, serial number s3</span></span>
<ul>
<li><span data-ttu-id="1b5aa-301">Ordre de qualité 1 pour 1 du numéro de lot b1, numéro de série s1</span><span class="sxs-lookup"><span data-stu-id="1b5aa-301">Quality order 1 for 1 of batch number b1, serial number s1</span></span></li>
<li><span data-ttu-id="1b5aa-302">Ordre de qualité 2 pour 1 du numéro de lot b2, numéro de série s2</span><span class="sxs-lookup"><span data-stu-id="1b5aa-302">Quality order 2 for 1 of batch number b2, serial number s2</span></span></li>
<li><span data-ttu-id="1b5aa-303">Ordre de qualité 3 pour 1 du numéro de lot b3, numéro de série s3</span><span class="sxs-lookup"><span data-stu-id="1b5aa-303">Quality order 3 for 1 of batch number b3, serial number s3</span></span></li>
</ul>
</li>
<li><span data-ttu-id="1b5aa-304">Déclarer comme terminé pour 2 : 1 pour le numéro de lot b4, le numéro de série s4 ; et 1 pour le numéro de lot b5, le numéro de série s5</span><span class="sxs-lookup"><span data-stu-id="1b5aa-304">Report as finished for 2: 1 for batch number b4, serial number s4; and 1 for batch number b5, serial number s5</span></span>
<ul>
<li><span data-ttu-id="1b5aa-305">Ordre de qualité 4 pour 1 du numéro de lot b4, numéro de série s4</span><span class="sxs-lookup"><span data-stu-id="1b5aa-305">Quality order 4 for 1 of batch number b4, serial number s4</span></span></li>
<li><span data-ttu-id="1b5aa-306">Ordre de qualité 5 pour 1 du numéro de lot b5, numéro de série s5</span><span class="sxs-lookup"><span data-stu-id="1b5aa-306">Quality order 5 for 1 of batch number b5, serial number s5</span></span></li>
</ul>
</li>
</ol>
<p><span data-ttu-id="1b5aa-307"><strong>Remarque :</strong> le lot peut être réutilisé.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-307"><strong>Note:</strong> The batch can be reused.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="1b5aa-308">Quantité fixe : 2</span><span class="sxs-lookup"><span data-stu-id="1b5aa-308">Fixed quantity: 2</span></span></td>
<td><span data-ttu-id="1b5aa-309">N°</span><span class="sxs-lookup"><span data-stu-id="1b5aa-309">No</span></span></td>
<td>
<p><span data-ttu-id="1b5aa-310">Numéro du lot : Oui</span><span class="sxs-lookup"><span data-stu-id="1b5aa-310">Batch number: Yes</span></span></p>
<p><span data-ttu-id="1b5aa-311">Numéro de série : Oui</span><span class="sxs-lookup"><span data-stu-id="1b5aa-311">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="1b5aa-312">Quantité de la commande : 10</span><span class="sxs-lookup"><span data-stu-id="1b5aa-312">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="1b5aa-313">Déclarer comme terminé pour 4 : 1 pour le numéro de lot b1, le numéro de série s1 ; 1 pour le numéro de lot b2, le numéro de série s2 ; et 1 pour le numéro de lot b3, le numéro de série s3 et 1 pour le numéro de lot b4, le numéro de série s4</span><span class="sxs-lookup"><span data-stu-id="1b5aa-313">Report as finished for 4: 1 for batch number b1, serial number s1; 1 for batch number b2, serial number s2; 1 for batch number b3, serial number s3; and 1 for batch number b4, serial number s4</span></span>
<ul>
<li><span data-ttu-id="1b5aa-314">Ordre de qualité 1 pour 1 du numéro de lot b1, numéro de série s1</span><span class="sxs-lookup"><span data-stu-id="1b5aa-314">Quality order 1 for 1 of batch number b1, serial number s1</span></span></li>
<li><span data-ttu-id="1b5aa-315">Ordre de qualité 2 pour 1 du numéro de lot b2, numéro de série s2</span><span class="sxs-lookup"><span data-stu-id="1b5aa-315">Quality order 2 for 1 of batch number b2, serial number s2</span></span></li>
<li><span data-ttu-id="1b5aa-316">Ordre de qualité 3 pour 1 du numéro de lot b3, numéro de série s3</span><span class="sxs-lookup"><span data-stu-id="1b5aa-316">Quality order 3 for 1 of batch number b3, serial number s3</span></span></li>
<li><span data-ttu-id="1b5aa-317">Ordre de qualité 4 pour 1 du numéro de lot b4, numéro de série s4</span><span class="sxs-lookup"><span data-stu-id="1b5aa-317">Quality order 4 for 1 of batch number b4, serial number s4</span></span></li>
</ul>
<ul>
<li><span data-ttu-id="1b5aa-318">Ordre de qualité n° 5 pour 2, sans référence à un numéro de traitement par lots et à un numéro de série</span><span class="sxs-lookup"><span data-stu-id="1b5aa-318">Quality order 5 for 2, without a reference to a batch number and a serial number</span></span></li>
</ul>
</li>
<li><span data-ttu-id="1b5aa-319">Déclarer comme terminé pour 6 : 1 pour le numéro de lot b5, le numéro de série s5 ; 1 pour le numéro de lot b6, le numéro de série s6 ; 1 pour le numéro de lot b7, le numéro de série s7 ; 1 pour le numéro de lot b8, le numéro de série s8 ; 1 pour le numéro de lot b9, le numéro de série s9 ; et 1 pour le numéro de lot b10, le numéro de série s10</span><span class="sxs-lookup"><span data-stu-id="1b5aa-319">Report as finished for 6: 1 for batch number b5, serial number s5; 1 for batch number b6, serial number s6; 1 for batch number b7, serial number s7; 1 for batch number b8, serial number s8; 1 for batch number b9, serial number s9; and 1 for batch number b10, serial number s10</span></span>
<ul>
<li><span data-ttu-id="1b5aa-320">Aucun ordre de qualité n’est créé.</span><span class="sxs-lookup"><span data-stu-id="1b5aa-320">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="1b5aa-321">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="1b5aa-321">Additional resources</span></span>

- [<span data-ttu-id="1b5aa-322">Processus de gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="1b5aa-322">Quality management processes</span></span>](quality-management-processes.md)
- [<span data-ttu-id="1b5aa-323">Activer la gestion de la qualité et de la non-conformité</span><span class="sxs-lookup"><span data-stu-id="1b5aa-323">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="1b5aa-324">Gestion de la qualité pour les processus d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="1b5aa-324">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
