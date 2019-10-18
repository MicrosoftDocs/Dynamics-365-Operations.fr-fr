---
title: Vue d'ensemble de la gestion de la qualité
description: Cette rubrique décrit la manière dont vous pouvez utiliser la gestion de la qualité dans Dynamics 365 Supply Chain Management pour vous aider à améliorer la qualité des produits de votre chaîne logistique.
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c9600e165da76948bb53a0188ec0b212a0fed84a
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249576"
---
# <a name="quality-management-overview"></a><span data-ttu-id="886d4-103">Vue d'ensemble de la gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="886d4-103">Quality management overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="886d4-104">Cette rubrique décrit la manière dont vous pouvez utiliser la gestion de la qualité dans Dynamics 365 Supply Chain Management pour vous aider à améliorer la qualité des produits de votre chaîne logistique.</span><span class="sxs-lookup"><span data-stu-id="886d4-104">This topic describes how you can use quality management in Dynamics 365 Supply Chain Management to help improve product quality within your supply chain.</span></span>

<span data-ttu-id="886d4-105">La gestion de la qualité peut vous aider à gérer les délais de rotation lorsque vous traitez des produits non conformes, indépendamment de leur point d'origine.</span><span class="sxs-lookup"><span data-stu-id="886d4-105">Quality management can help you manage turnaround times when you handle nonconforming products, regardless of their point of origin.</span></span> <span data-ttu-id="886d4-106">Étant donné que les types de diagnostics sont liés à la génération d'états de correction, Finance and Operations peut programmer des tâches afin de corriger les problèmes et les empêcher de se reproduire.</span><span class="sxs-lookup"><span data-stu-id="886d4-106">Because diagnostic types are linked to correction reporting, Finance and Operations can schedule tasks to correct problems and prevent them from recurring.</span></span>

<span data-ttu-id="886d4-107">Outre la fonctionnalité de gestion de la non-conformité, la gestion de la qualité inclut la fonctionnalité de suivi des problèmes par type de problème (même les problèmes internes) et d'identification des solutions comme à court terme ou à long terme.</span><span class="sxs-lookup"><span data-stu-id="886d4-107">In addition to functionality for managing nonconformance, quality management includes functionality for tracking issues by problem type (even internal problems), and for identifying solutions as short-term or long-term.</span></span> <span data-ttu-id="886d4-108">Les statistiques concernant les indicateurs clés de performance (KPI) donnent des indications sur l'historique des problèmes de non-conformité antérieurs et sur les solutions qui ont été utilisées pour les corriger.</span><span class="sxs-lookup"><span data-stu-id="886d4-108">Statistics about key performance indicators (KPIs) provide insight into the history of previous nonconformance issues and the solutions that were used to correct them.</span></span> <span data-ttu-id="886d4-109">Vous pouvez utiliser les données historiques pour examiner l'efficacité des mesures de qualité antérieures et déterminer les mesures appropriées à utiliser à l'avenir.</span><span class="sxs-lookup"><span data-stu-id="886d4-109">You can use historical data to review the effectiveness of previous quality measures and determine appropriate measures to use in the future.</span></span>

<span data-ttu-id="886d4-110">Lorsque vous paramétrez une association de qualité, Supply Chain Management peut générer des ordres de qualité pour différents processus d'entreprise, événements et conditions.</span><span class="sxs-lookup"><span data-stu-id="886d4-110">When you set up a quality association, Supply Chain Management can generate quality orders for various business processes, events, and conditions.</span></span> <span data-ttu-id="886d4-111">L'association de qualité peut couvrir un article spécifique, un groupe d'articles spécifique, ou tous les articles.</span><span class="sxs-lookup"><span data-stu-id="886d4-111">The quality association can cover a specific item, a specific group of items, or all items.</span></span>

## <a name="examples-of-the-use-of-quality-management"></a><span data-ttu-id="886d4-112">Exemples de l'utilisation de la gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="886d4-112">Examples of the use of quality management</span></span>
<span data-ttu-id="886d4-113">La gestion de la qualité est flexible et peut être mise en œuvre de différentes manières afin de répondre aux exigences de niveaux spécifiques des opérations de chaîne d'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="886d4-113">Quality management is flexible and can be implemented in various ways to meet the requirements of specific levels of supply chain operations.</span></span> <span data-ttu-id="886d4-114">Les exemples suivants illustrent les utilisations possibles de ces fonctionnalités :</span><span class="sxs-lookup"><span data-stu-id="886d4-114">The following examples illustrate possible uses of these features:</span></span>

-   <span data-ttu-id="886d4-115">Démarrer automatiquement un processus de contrôle qualité, basé sur des critères prédéfinis (lors de l'enregistrement en entrepôt d'une commande fournisseur provenant d'un fournisseur spécifique).</span><span class="sxs-lookup"><span data-stu-id="886d4-115">Automatically start a quality control process, based on predefined criteria (upon warehouse registration of a purchase order from a specific vendor).</span></span>
-   <span data-ttu-id="886d4-116">Bloquer le stock au cours de l'inspection pour empêcher l'utilisation d'un stock non-approuvé (blocage complet des quantités des commande fournisseur).</span><span class="sxs-lookup"><span data-stu-id="886d4-116">Block inventory during inspection to prevent non-approved inventory from being used (full blocking of purchase order quantities).</span></span>
-   <span data-ttu-id="886d4-117">Utiliser l'échantillonnage d'article dans le cadre d'une association de qualité pour définir la quantité de stock physique actuel qui doit être inspectée.</span><span class="sxs-lookup"><span data-stu-id="886d4-117">Use item sampling as part of a quality association to define the amount of current physical inventory that must be inspected.</span></span> <span data-ttu-id="886d4-118">L'échantillonnage peut être basé sur des quantités fixes ou sur un pourcentage.</span><span class="sxs-lookup"><span data-stu-id="886d4-118">Sampling can be based on fixed quantities or a percentage.</span></span>
-   <span data-ttu-id="886d4-119">Créez des ordres de qualité pour les réceptions partielles.</span><span class="sxs-lookup"><span data-stu-id="886d4-119">Create quality orders for partial receipts.</span></span> <span data-ttu-id="886d4-120">Pour créer un ordre de qualité basé sur la quantité qui est reçue physiquement avec une commande, vous devez activer la case à cocher **Par quantité mise à jour** sur l'écran **Échantillonnage d'article**.</span><span class="sxs-lookup"><span data-stu-id="886d4-120">To create a quality order that is based on the quantity that is physically received with an order, you must select the **Per updated quantity** check box on the **Item sampling** form.</span></span>
-   <span data-ttu-id="886d4-121">Créer des types de test qui incluent les valeurs minimales, maximales, ainsi que les valeurs de test cibles, et réaliser des tests quantitatifs/qualitatifs ayant des résultats de contrôle prédéfinis.</span><span class="sxs-lookup"><span data-stu-id="886d4-121">Create test types that include minimum, maximum, and target test values, and perform qualitative-versus-quantitative testing that has predefined validation results.</span></span>
-   <span data-ttu-id="886d4-122">Spécifier un niveau de qualité acceptable pour contrôler les tolérances de la mesure de qualité.</span><span class="sxs-lookup"><span data-stu-id="886d4-122">Specify an acceptable quality level (AQL) to control quality measure tolerances.</span></span>
-   <span data-ttu-id="886d4-123">Spécifier les ressources qu'une opération d'inspection nécessite, telles qu'une zone de test et des instruments de test.</span><span class="sxs-lookup"><span data-stu-id="886d4-123">Specify the resources that an inspection operation requires, such as a test area and test instruments.</span></span>

## <a name="working-with-quality-associations"></a><span data-ttu-id="886d4-124">Utilisation des associations de qualité</span><span class="sxs-lookup"><span data-stu-id="886d4-124">Working with quality associations</span></span>
<span data-ttu-id="886d4-125">Le processus d'entreprise qui utilise une association de qualité peut être associé à diverses documents source, tels que des commandes fournisseur, des commandes client ou des ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="886d4-125">The business process that uses a quality association can be related to various source documents, such as purchase orders, sales orders, or production orders.</span></span>

<span data-ttu-id="886d4-126">Chaque enregistrement d'association de qualité définit l'ensemble de tests, le niveau de qualité acceptable et le programme d'échantillonnage qui s'applique aux ordres de qualité générés.</span><span class="sxs-lookup"><span data-stu-id="886d4-126">Each quality association record defines the set of tests, the AQL, and the sampling plan that applies to the quality orders that are generated.</span></span> <span data-ttu-id="886d4-127">Vous devez définir un enregistrement d'association de qualité pour chaque variation d'un processus d'entreprise.</span><span class="sxs-lookup"><span data-stu-id="886d4-127">You must define a quality association record for each variation in a business process.</span></span> <span data-ttu-id="886d4-128">Par exemple, vous pouvez paramétrer une association de qualité qui génère un ordre de qualité lorsqu'un accusé de réception de marchandises de commande fournisseur est mis à jour.</span><span class="sxs-lookup"><span data-stu-id="886d4-128">For example, you can set up a quality association that generates a quality order when a purchase order product receipt is updated.</span></span> <span data-ttu-id="886d4-129">Selon le paramétrage du plan d'exécution, le processus de déclenchement lui-même peut être bloqué tant qu'il existe un ordre de qualité en cours, ou les processus suivants, tels que la facturation d'une commande fournisseur, peuvent être bloqués.</span><span class="sxs-lookup"><span data-stu-id="886d4-129">Depending on the setup of the execution plan, the triggering process itself can be blocked while there is an open quality order, or the next processes, such as purchase order invoicing, can be blocked.</span></span>

<span data-ttu-id="886d4-130">**Remarque :** tant qu'il existe des ordres de qualité en cours, le lancement des quantités en stock est automatiquement bloqué.</span><span class="sxs-lookup"><span data-stu-id="886d4-130">**Note:** While there are open quality orders, inventory quantities are automatically blocked from being issued.</span></span> <span data-ttu-id="886d4-131">En fonction du paramètre **Blocage total** de la page **Échantillonnage d'article**, la quantité est soit la quantité de l'ordre de qualité, soit la quantité de la ligne de document source.</span><span class="sxs-lookup"><span data-stu-id="886d4-131">Depending on the **Full blocking** setting on the **Item samplings** page, the quantity is either the quantity on the quality order or the quantity on the source document line.</span></span>

<span data-ttu-id="886d4-132">Pour un processus entreprise donné, l'enregistrement d'association de qualité identifie l'événement et les conditions pour lesquels un ordre de qualité est généré.</span><span class="sxs-lookup"><span data-stu-id="886d4-132">For a given business process, the quality association record identifies the event and the conditions that a quality order is generated for.</span></span> <span data-ttu-id="886d4-133">Les conditions peuvent être spécifiques à un site ou à une entité juridique.</span><span class="sxs-lookup"><span data-stu-id="886d4-133">The conditions can be specific to either a site or a legal entity.</span></span> <span data-ttu-id="886d4-134">Un ordre de qualité qui implique des tests destructifs ne peut être généré que si le stock disponible existe pour l'événement.</span><span class="sxs-lookup"><span data-stu-id="886d4-134">A quality order that involves destructive tests can be generated only when on-hand inventory exists for the event.</span></span>

<span data-ttu-id="886d4-135">Les exemples suivants présentent la manière dont un enregistrement d'association de qualité est défini pour les variations de chaque processus entreprise.</span><span class="sxs-lookup"><span data-stu-id="886d4-135">The following examples illustrate how a quality association record is defined for the variations in each business process.</span></span> <span data-ttu-id="886d4-136">Pour chaque exemple, le tableau suivant résume les événements et les conditions définis par un enregistrement d'association de qualité.</span><span class="sxs-lookup"><span data-stu-id="886d4-136">For each example, the following table summarizes the events and conditions that are defined by a quality association record.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="886d4-137">Type de référence</span><span class="sxs-lookup"><span data-stu-id="886d4-137">Reference type</span></span></th>
<th><span data-ttu-id="886d4-138">Type de droit</span><span class="sxs-lookup"><span data-stu-id="886d4-138">Event type</span></span></th>
<th><span data-ttu-id="886d4-139">Exécution</span><span class="sxs-lookup"><span data-stu-id="886d4-139">Execution</span></span></th>
<th><span data-ttu-id="886d4-140">Blocage d'événement</span><span class="sxs-lookup"><span data-stu-id="886d4-140">Event blocking</span></span></th>
<th><span data-ttu-id="886d4-141">Références du document</span><span class="sxs-lookup"><span data-stu-id="886d4-141">Document reference</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="886d4-142">Stock</span><span class="sxs-lookup"><span data-stu-id="886d4-142">Inventory</span></span></td>
<td><span data-ttu-id="886d4-143">Non applicable</span><span class="sxs-lookup"><span data-stu-id="886d4-143">Not applicable</span></span></td>
<td><span data-ttu-id="886d4-144">Non applicable</span><span class="sxs-lookup"><span data-stu-id="886d4-144">Not applicable</span></span></td>
<td><span data-ttu-id="886d4-145">Aucun(e)</span><span class="sxs-lookup"><span data-stu-id="886d4-145">None</span></span></td>
<td><span data-ttu-id="886d4-146">Tout</span><span class="sxs-lookup"><span data-stu-id="886d4-146">All</span></span></td>
</tr>
<tr>
<td rowspan="7"><span data-ttu-id="886d4-147">Ventes</span><span class="sxs-lookup"><span data-stu-id="886d4-147">Sales</span></span></td>
<td rowspan="4"><span data-ttu-id="886d4-148">Le processus de prélèvement est planifié</span><span class="sxs-lookup"><span data-stu-id="886d4-148">Picking process is scheduled</span></span></td>
<td rowspan="4"><span data-ttu-id="886d4-149">Avant</span><span class="sxs-lookup"><span data-stu-id="886d4-149">Before</span></span></td>
<td><span data-ttu-id="886d4-150">Aucun(e)</span><span class="sxs-lookup"><span data-stu-id="886d4-150">None</span></span></td>
<td rowspan="22"><span data-ttu-id="886d4-151">ID spécifique, Groupe, ou Tous uniquement</span><span class="sxs-lookup"><span data-stu-id="886d4-151">Specific ID, Group, or All only</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-152">Processus de prélèvement</span><span class="sxs-lookup"><span data-stu-id="886d4-152">Picking process</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-153">Bon de livraison</span><span class="sxs-lookup"><span data-stu-id="886d4-153">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-154">Facture</span><span class="sxs-lookup"><span data-stu-id="886d4-154">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="886d4-155">Bon de livraison</span><span class="sxs-lookup"><span data-stu-id="886d4-155">Packing slip</span></span></td>
<td rowspan="3"><span data-ttu-id="886d4-156">Avant</span><span class="sxs-lookup"><span data-stu-id="886d4-156">Before</span></span></td>
<td><span data-ttu-id="886d4-157">Aucun(e)</span><span class="sxs-lookup"><span data-stu-id="886d4-157">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-158">Bon de livraison</span><span class="sxs-lookup"><span data-stu-id="886d4-158">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-159">Facture</span><span class="sxs-lookup"><span data-stu-id="886d4-159">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="15"><span data-ttu-id="886d4-160">Achat</span><span class="sxs-lookup"><span data-stu-id="886d4-160">Purchase</span></span></td>
<td rowspan="7"><span data-ttu-id="886d4-161">Liste de réception</span><span class="sxs-lookup"><span data-stu-id="886d4-161">Receipt list</span></span></td>
<td rowspan="4"><span data-ttu-id="886d4-162">Avant</span><span class="sxs-lookup"><span data-stu-id="886d4-162">Before</span></span></td>
<td><span data-ttu-id="886d4-163">Aucun(e)</span><span class="sxs-lookup"><span data-stu-id="886d4-163">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-164">Liste de réception</span><span class="sxs-lookup"><span data-stu-id="886d4-164">Receipt list</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-165">Accusé de réception de marchandises</span><span class="sxs-lookup"><span data-stu-id="886d4-165">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-166">Facture</span><span class="sxs-lookup"><span data-stu-id="886d4-166">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="886d4-167">Après</span><span class="sxs-lookup"><span data-stu-id="886d4-167">After</span></span></td>
<td><span data-ttu-id="886d4-168">Aucun(e)</span><span class="sxs-lookup"><span data-stu-id="886d4-168">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-169">Accusé de réception de marchandises</span><span class="sxs-lookup"><span data-stu-id="886d4-169">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-170">Facture</span><span class="sxs-lookup"><span data-stu-id="886d4-170">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="886d4-171">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="886d4-171">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="886d4-172">Non applicable</span><span class="sxs-lookup"><span data-stu-id="886d4-172">Not applicable</span></span></td>
<td><span data-ttu-id="886d4-173">Aucun(e)</span><span class="sxs-lookup"><span data-stu-id="886d4-173">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-174">Accusé de réception de marchandises</span><span class="sxs-lookup"><span data-stu-id="886d4-174">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-175">Facture</span><span class="sxs-lookup"><span data-stu-id="886d4-175">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="886d4-176">Accusé de réception de marchandises</span><span class="sxs-lookup"><span data-stu-id="886d4-176">Product receipt</span></span></td>
<td rowspan="3"><span data-ttu-id="886d4-177">Avant</span><span class="sxs-lookup"><span data-stu-id="886d4-177">Before</span></span></td>
<td><span data-ttu-id="886d4-178">Aucun(e)</span><span class="sxs-lookup"><span data-stu-id="886d4-178">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-179">Accusé de réception de marchandises</span><span class="sxs-lookup"><span data-stu-id="886d4-179">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-180">Facture</span><span class="sxs-lookup"><span data-stu-id="886d4-180">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="886d4-181">Après</span><span class="sxs-lookup"><span data-stu-id="886d4-181">After</span></span></td>
<td><span data-ttu-id="886d4-182">Aucun(e)</span><span class="sxs-lookup"><span data-stu-id="886d4-182">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-183">Facture</span><span class="sxs-lookup"><span data-stu-id="886d4-183">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="8"><span data-ttu-id="886d4-184">Production</span><span class="sxs-lookup"><span data-stu-id="886d4-184">Production</span></span></td>
<td rowspan="3"><span data-ttu-id="886d4-185">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="886d4-185">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="886d4-186">Non applicable</span><span class="sxs-lookup"><span data-stu-id="886d4-186">Not applicable</span></span></td>
<td><span data-ttu-id="886d4-187">Aucun(e)</span><span class="sxs-lookup"><span data-stu-id="886d4-187">None</span></span></td>
<td rowspan="12"><span data-ttu-id="886d4-188">Tout</span><span class="sxs-lookup"><span data-stu-id="886d4-188">All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-189">Déclaration de fin</span><span class="sxs-lookup"><span data-stu-id="886d4-189">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-190">Fin</span><span class="sxs-lookup"><span data-stu-id="886d4-190">End</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="886d4-191">Déclaration de fin</span><span class="sxs-lookup"><span data-stu-id="886d4-191">Report as finished</span></span></td>
<td rowspan="3"><span data-ttu-id="886d4-192">Avant</span><span class="sxs-lookup"><span data-stu-id="886d4-192">Before</span></span></td>
<td><span data-ttu-id="886d4-193">Aucun(e)</span><span class="sxs-lookup"><span data-stu-id="886d4-193">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-194">Déclaration de fin</span><span class="sxs-lookup"><span data-stu-id="886d4-194">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-195">Fin</span><span class="sxs-lookup"><span data-stu-id="886d4-195">End</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="886d4-196">Après</span><span class="sxs-lookup"><span data-stu-id="886d4-196">After</span></span></td>
<td><span data-ttu-id="886d4-197">Aucun(e)</span><span class="sxs-lookup"><span data-stu-id="886d4-197">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-198">Fin</span><span class="sxs-lookup"><span data-stu-id="886d4-198">End</span></span></td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="886d4-199">Contrôle</span><span class="sxs-lookup"><span data-stu-id="886d4-199">Quarantine</span></span></td>
<td rowspan="3"><span data-ttu-id="886d4-200">Déclaration de fin</span><span class="sxs-lookup"><span data-stu-id="886d4-200">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="886d4-201">Avant</span><span class="sxs-lookup"><span data-stu-id="886d4-201">Before</span></span></td>
<td><span data-ttu-id="886d4-202">Déclaration de fin</span><span class="sxs-lookup"><span data-stu-id="886d4-202">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-203">Fin</span><span class="sxs-lookup"><span data-stu-id="886d4-203">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-204">Après</span><span class="sxs-lookup"><span data-stu-id="886d4-204">After</span></span></td>
<td><span data-ttu-id="886d4-205">Fin</span><span class="sxs-lookup"><span data-stu-id="886d4-205">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-206">Fin</span><span class="sxs-lookup"><span data-stu-id="886d4-206">End</span></span></td>
<td><span data-ttu-id="886d4-207">Avant</span><span class="sxs-lookup"><span data-stu-id="886d4-207">Before</span></span></td>
<td><span data-ttu-id="886d4-208">Fin</span><span class="sxs-lookup"><span data-stu-id="886d4-208">End</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="886d4-209">Opération de gamme</span><span class="sxs-lookup"><span data-stu-id="886d4-209">Route operation</span></span></td>
<td rowspan="3"><span data-ttu-id="886d4-210">Déclaration de fin</span><span class="sxs-lookup"><span data-stu-id="886d4-210">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="886d4-211">Avant</span><span class="sxs-lookup"><span data-stu-id="886d4-211">Before</span></span></td>
<td><span data-ttu-id="886d4-212">Aucun(e)</span><span class="sxs-lookup"><span data-stu-id="886d4-212">None</span></span></td>
<td rowspan="3"><span data-ttu-id="886d4-213">ID spécifique, Groupes ou Tous, et Spécifique à la ressource, Groupe ou Tous</span><span class="sxs-lookup"><span data-stu-id="886d4-213">Specific ID, Group, or All, and Resource specific, Group, or All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-214">Déclaration de fin</span><span class="sxs-lookup"><span data-stu-id="886d4-214">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-215">Après</span><span class="sxs-lookup"><span data-stu-id="886d4-215">After</span></span></td>
<td><span data-ttu-id="886d4-216">Aucun(e)</span><span class="sxs-lookup"><span data-stu-id="886d4-216">None</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="886d4-217">Production de coproduits</span><span class="sxs-lookup"><span data-stu-id="886d4-217">Co-product production</span></span></td>
<td><span data-ttu-id="886d4-218">Enregistrement</span><span class="sxs-lookup"><span data-stu-id="886d4-218">Registration</span></span></td>
<td><span data-ttu-id="886d4-219">Non applicable</span><span class="sxs-lookup"><span data-stu-id="886d4-219">Not applicable</span></span></td>
<td rowspan="3"><span data-ttu-id="886d4-220">Aucun(e)</span><span class="sxs-lookup"><span data-stu-id="886d4-220">None</span></span></td>
<td rowspan="3"><span data-ttu-id="886d4-221">Tout</span><span class="sxs-lookup"><span data-stu-id="886d4-221">All</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="886d4-222">Déclaration de fin</span><span class="sxs-lookup"><span data-stu-id="886d4-222">Report as finished</span></span></td>
<td><span data-ttu-id="886d4-223">Avant</span><span class="sxs-lookup"><span data-stu-id="886d4-223">Before</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-224">Après</span><span class="sxs-lookup"><span data-stu-id="886d4-224">After</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="886d4-225">Le tableau suivant fournit plus d'informations sur la manière dont les ordres de qualité peuvent être générés pour des types de processus spécifiques.</span><span class="sxs-lookup"><span data-stu-id="886d4-225">The following table provides more information about how quality orders can be generated for specific types of processes.</span></span>
<div class="tableSection">

<table>
<tbody>
<tr>
<th><span data-ttu-id="886d4-226">Type de processus</span><span class="sxs-lookup"><span data-stu-id="886d4-226">Type of process</span></span></th>
<th><span data-ttu-id="886d4-227">Lorsque des ordres de qualité peuvent être automatiquement générés</span><span class="sxs-lookup"><span data-stu-id="886d4-227">When quality orders can be automatically generated</span></span></th>
<th><span data-ttu-id="886d4-228">Lorsque des ordres de qualité peuvent être générés si les tests destructifs sont requis</span><span class="sxs-lookup"><span data-stu-id="886d4-228">When quality orders can be generated if destructive testing is required</span></span></th>
<th><span data-ttu-id="886d4-229">Informations de condition</span><span class="sxs-lookup"><span data-stu-id="886d4-229">Condition information</span></span></th>
<th><span data-ttu-id="886d4-230">Informations de génération manuelle</span><span class="sxs-lookup"><span data-stu-id="886d4-230">Manual generation information</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="886d4-231">Commande fournisseur</span><span class="sxs-lookup"><span data-stu-id="886d4-231">Purchase order</span></span></td>
<td><span data-ttu-id="886d4-232">Avant ou après la validation d'une liste de réceptions ou d'un accusé de réception de marchandises reçu pour les matières</span><span class="sxs-lookup"><span data-stu-id="886d4-232">Before or after a receipts list or product receipt for the material that is received is posted</span></span></td>
<td><span data-ttu-id="886d4-233">Après la validation de l'accusé de réception de marchandises pour les matières reçu, car les matières doivent être disponibles pour les tests destructifs</span><span class="sxs-lookup"><span data-stu-id="886d4-233">After the product receipt for the material that is received is posted, because the material must be available for destructive testing</span></span></td>
<td><span data-ttu-id="886d4-234">La nécessité d'établir un ordre de qualité peut refléter un site, un article ou un vendeur spécifique ou une combinaison de ces conditions.</span><span class="sxs-lookup"><span data-stu-id="886d4-234">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="886d4-235">Un ordre de qualité généré manuellement qui fait référence à une commande fournisseur peut utiliser les informations dans un enregistrement d'association de qualité, telles que le programme d'échantillonnage de test.</span><span class="sxs-lookup"><span data-stu-id="886d4-235">A manually generated quality order that refers to a purchase order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-236">Ordre de contrôle</span><span class="sxs-lookup"><span data-stu-id="886d4-236">Quarantine order</span></span></td>
<td><span data-ttu-id="886d4-237">Avant ou après la déclaration de fin de l'ordre de contrôle</span><span class="sxs-lookup"><span data-stu-id="886d4-237">Before or after the quarantine order is reported as finished or ended</span></span></td>
<td><span data-ttu-id="886d4-238">Les ordres de qualité nécessitant des tests destructifs ne peuvent pas être générés.</span><span class="sxs-lookup"><span data-stu-id="886d4-238">Quality orders that require destructive tests can&#39;t be generated.</span></span> <span data-ttu-id="886d4-239">On suppose que la fonctionnalité d'ordre de contrôle gère l'élimination des matières détruites.</span><span class="sxs-lookup"><span data-stu-id="886d4-239">It&#39;s assumed that the quarantine order functionality handles the disposition of the material that is destroyed.</span></span></td>
<td><span data-ttu-id="886d4-240">La nécessité d'établir un ordre de qualité peut refléter un site, un article ou un vendeur spécifique ou une combinaison de ces conditions.</span><span class="sxs-lookup"><span data-stu-id="886d4-240">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="886d4-241">Un ordre de qualité généré manuellement qui fait référence à un ordre de contrôle peut utiliser les informations dans un enregistrement d'association de qualité, telles que le programme d'échantillonnage de test.</span><span class="sxs-lookup"><span data-stu-id="886d4-241">A manually generated quality order that refers to a quarantine order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-242">Commande client</span><span class="sxs-lookup"><span data-stu-id="886d4-242">Sales order</span></span></td>
<td><span data-ttu-id="886d4-243">Avant la mise à jour d'un processus de prélèvement planifié ou d'un bon de livraison pour les articles qui sont expédiés</span><span class="sxs-lookup"><span data-stu-id="886d4-243">Before a scheduled picking process or packing slip update for the items that are being shipped</span></span></td>
<td><span data-ttu-id="886d4-244">À toute étape</span><span class="sxs-lookup"><span data-stu-id="886d4-244">At any step</span></span></td>
<td><span data-ttu-id="886d4-245">La nécessité d'établir un ordre de qualité peut refléter un site, un article ou un client spécifique ou une combinaison de ces conditions.</span><span class="sxs-lookup"><span data-stu-id="886d4-245">The requirement for a quality order can reflect a particular site, item, or customer, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="886d4-246">Un ordre de qualité généré manuellement qui fait référence à une commande client peut utiliser les informations dans un enregistrement d'association de qualité, telles que le programme d'échantillonnage de test.</span><span class="sxs-lookup"><span data-stu-id="886d4-246">A manually generated quality order that refers to a sales order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-247">Ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="886d4-247">Production order</span></span></td>
<td><span data-ttu-id="886d4-248">Avant ou après la déclaration de la quantité terminée pour l'ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="886d4-248">Before or after the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="886d4-249">Après la déclaration de la quantité terminée pour l'ordre de fabrication</span><span class="sxs-lookup"><span data-stu-id="886d4-249">After the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="886d4-250">La nécessité d'établir un ordre de qualité peut refléter un site, un article ou un client spécifique ou une combinaison de ces conditions.</span><span class="sxs-lookup"><span data-stu-id="886d4-250">The requirement for a quality order can reflect a particular site or item, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="886d4-251">Un ordre de qualité généré manuellement qui fait référence à un ordre de fabrication peut utiliser les informations dans un enregistrement d'association de qualité, telles que le programme d'échantillonnage de test.</span><span class="sxs-lookup"><span data-stu-id="886d4-251">A manually generated quality order that refers to a production order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-252">Ordre de fabrication qui a une opération de gamme</span><span class="sxs-lookup"><span data-stu-id="886d4-252">Production order that has a route operation</span></span></td>
<td><span data-ttu-id="886d4-253">Avant ou après la fin de l'état pour une opération</span><span class="sxs-lookup"><span data-stu-id="886d4-253">Before or after the report is finished for an operation</span></span></td>
<td><span data-ttu-id="886d4-254">Après la déclaration de fin de production pour la dernière opération</span><span class="sxs-lookup"><span data-stu-id="886d4-254">After the reporting production is finished for the last operation</span></span></td>
<td><span data-ttu-id="886d4-255">La nécessité d'établir un ordre de qualité peut refléter un site, un article ou d'une ressource opérationnelle, ou une combinaison de ces conditions.</span><span class="sxs-lookup"><span data-stu-id="886d4-255">The requirement for a quality order can reflect a particular, site, item, or operations resource, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="886d4-256">Un ordre de qualité généré manuellement qui fait référence à une opération de gamme peut utiliser les informations dans un enregistrement d'association de qualité, telles que le programme d'échantillonnage de test.</span><span class="sxs-lookup"><span data-stu-id="886d4-256">A manually generated quality order that refers to a route operation can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="886d4-257">Stock</span><span class="sxs-lookup"><span data-stu-id="886d4-257">Inventory</span></span></td>
<td><span data-ttu-id="886d4-258">Un ordre de qualité ne peut pas être automatiquement généré pour une transaction dans un journal de stock ou pour des transactions d'ordre de transfert</span><span class="sxs-lookup"><span data-stu-id="886d4-258">A quality order cannot be automatically generated for a transaction in an inventory journal or for transfer order transactions.</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="886d4-259">Un ordre de qualité doit être créé manuellement pour la quantité de stock d'un article.</span><span class="sxs-lookup"><span data-stu-id="886d4-259">A quality order must be created manually for an item&#39;s inventory quantity.</span></span> <span data-ttu-id="886d4-260">Le stock physique disponible est exigé.</span><span class="sxs-lookup"><span data-stu-id="886d4-260">Physical on-hand inventory is required.</span></span></td>
</tr>
</tbody>
</table>

## <a name="quality-management-pages"></a><span data-ttu-id="886d4-261">Pages Gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="886d4-261">Quality management pages</span></span>
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="886d4-262">Page</span><span class="sxs-lookup"><span data-stu-id="886d4-262">Page</span></span></th>
<th><span data-ttu-id="886d4-263">Description</span><span class="sxs-lookup"><span data-stu-id="886d4-263">Description</span></span></th>
<th><span data-ttu-id="886d4-264">Exemple</span><span class="sxs-lookup"><span data-stu-id="886d4-264">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="886d4-265">Associations de qualité</span><span class="sxs-lookup"><span data-stu-id="886d4-265">Quality associations</span></span></td>
<td><span data-ttu-id="886d4-266">Voir les sections précédentes de cet article.</span><span class="sxs-lookup"><span data-stu-id="886d4-266">See the previous sections of this article.</span></span></td>
<td><span data-ttu-id="886d4-267">Une association de qualité définit toutes les informations suivantes pour un ordre de qualité qui est généré :</span><span class="sxs-lookup"><span data-stu-id="886d4-267">A quality association defines all the following information for a quality order that is generated:</span></span>
<ul>
<li><span data-ttu-id="886d4-268">L'événement de transaction</span><span class="sxs-lookup"><span data-stu-id="886d4-268">The transaction event</span></span></li>
<li><span data-ttu-id="886d4-269">L'ensemble des tests qui doivent être exécutés sur les articles</span><span class="sxs-lookup"><span data-stu-id="886d4-269">The set of tests that must be performed on the items</span></span></li>
<li><span data-ttu-id="886d4-270">Le niveau de qualité acceptable</span><span class="sxs-lookup"><span data-stu-id="886d4-270">The AQL</span></span></li>
<li><span data-ttu-id="886d4-271">Le programme d'échantillonnage</span><span class="sxs-lookup"><span data-stu-id="886d4-271">The sampling plan</span></span></li>
</ul>
<span data-ttu-id="886d4-272">Vous devez définir une association de qualité pour chaque variation dans un processus d'entreprise qui requiert la génération automatique d'ordres de qualité.</span><span class="sxs-lookup"><span data-stu-id="886d4-272">You must define a quality association for each variation in a business process that requires automatic generation of quality orders.</span></span> <span data-ttu-id="886d4-273">Par exemple, un ordre de qualité peut être généré dans le processus d'entreprise pour les commandes fournisseur, les ordres de contrôle,, les commandes client et les ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="886d4-273">For example, a quality order can be generated in the business processes for purchase orders, quarantine orders, sales orders, and production orders.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="886d4-274">Tests</span><span class="sxs-lookup"><span data-stu-id="886d4-274">Tests</span></span></td>
<td><span data-ttu-id="886d4-275">Cette page permet de définir et d'afficher les tests individuels qui déterminent si vos produits correspondent aux spécifications de qualité.</span><span class="sxs-lookup"><span data-stu-id="886d4-275">Use this page to define and view the individual tests that determine whether your products meet quality specifications.</span></span> <span data-ttu-id="886d4-276">Vous pouvez affecter un ou plusieurs tests à un groupe de tests.</span><span class="sxs-lookup"><span data-stu-id="886d4-276">You can assign one or more individual tests to a test group.</span></span> <span data-ttu-id="886d4-277">Dans ce cas, vous pouvez également spécifier des informations spécifiques aux tests, telles que les valeurs de mesures acceptables.</span><span class="sxs-lookup"><span data-stu-id="886d4-277">In this case, you also specify test-specific information, such as the acceptable measurement values.</span></span> <span data-ttu-id="886d4-278">Celles-ci sont utilisées dans le cadre des tests quantitatifs et les variables de test sont utilisées lors des tests qualitatifs.</span><span class="sxs-lookup"><span data-stu-id="886d4-278">Measurement values are used for quantitative tests, and test variables are used for qualitative tests.</span></span>
<ul>
<li><span data-ttu-id="886d4-279">Un test quantitatif est associé à un type de test <strong>Entier</strong> ou <strong>Fraction</strong>, et est également doté d'une unité de mesure spécifiée.</span><span class="sxs-lookup"><span data-stu-id="886d4-279">A quantitative test has a test type of <strong>Integer</strong> or <strong>Fraction</strong>, and also has a designated unit of measure.</span></span> <span data-ttu-id="886d4-280">Les spécifications de qualité et les résultats des tests peuvent être exprimés sous forme de nombres.</span><span class="sxs-lookup"><span data-stu-id="886d4-280">Quality specifications and test results are expressed as numbers.</span></span></li>
<li><span data-ttu-id="886d4-281">Le test qualitatif possède le type de test <strong>Option</strong>.</span><span class="sxs-lookup"><span data-stu-id="886d4-281">A qualitative test has a test type of <strong>Option</strong>.</span></span> <span data-ttu-id="886d4-282">Les tests qualitatifs exigent des informations supplémentaires sur la variable de test mesurée et la liste de ses options.</span><span class="sxs-lookup"><span data-stu-id="886d4-282">Qualitative tests require additional information about the test variable that is being measured and its enumerated options.</span></span> <span data-ttu-id="886d4-283">Les spécifications de qualité et les résultats des tests peuvent être exprimés sous forme de résultat.</span><span class="sxs-lookup"><span data-stu-id="886d4-283">Quality specifications and test results are expressed according to an outcome.</span></span></li>
</ul></td>
<td><span data-ttu-id="886d4-284">Une société de fabrication réalise deux tests sur du matériel acheté : un test quantitatif concernant la qualité du matériel et un test qualitatif concernant la solidité de l'emballage.</span><span class="sxs-lookup"><span data-stu-id="886d4-284">A manufacturing company performs two tests on purchased material: a quantitative test about material quality and a qualitative test about packaging damage.</span></span> <span data-ttu-id="886d4-285">Elle définit des informations supplémentaires concernant le test qualitatif afin d'identifier la variable de test (solidité de l'emballage) et ses résultats.</span><span class="sxs-lookup"><span data-stu-id="886d4-285">The company defines additional information about the qualitative test to identify the test variable (damaged packaging) and its outcomes.</span></span> <span data-ttu-id="886d4-286">Elle utilise la page <strong>Groupes de test</strong> pour affecter les deux tests à un groupe de test et spécifier les informations spécifiques aux tests.</span><span class="sxs-lookup"><span data-stu-id="886d4-286">The company uses the <strong>Test groups</strong> page to assign the two tests to a test group and to specify the test-specific information.</span></span> <span data-ttu-id="886d4-287">Le groupe de tests est affecté à un ordre de qualité, de sorte que la société puisse générer un état à partir des résultats des deux tests.</span><span class="sxs-lookup"><span data-stu-id="886d4-287">The test group is assigned to a quality order, so that the company can report test results for the two tests.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="886d4-288">Groupes de test</span><span class="sxs-lookup"><span data-stu-id="886d4-288">Test groups</span></span></td>
<td><span data-ttu-id="886d4-289">Cette page permet de paramétrer, de modifier et d'afficher des groupes de test et des tests individuels affectés à un groupe de test.</span><span class="sxs-lookup"><span data-stu-id="886d4-289">Use this page to set up, edit, and view test groups and the individual tests that are assigned to a test group.</span></span> <span data-ttu-id="886d4-290">Le volet supérieur affiche les groupes de test et le volet inférieur affiche les tests affectés à un groupe de test sélectionné.</span><span class="sxs-lookup"><span data-stu-id="886d4-290">The upper pane displays test groups, and the lower pane displays the tests that are assigned to a selected test group.</span></span> <span data-ttu-id="886d4-291">Vous affectez plusieurs stratégies à un groupe de test, notamment un programme d'échantillonnage, un niveau de qualité acceptable et la demande de tests destructifs.</span><span class="sxs-lookup"><span data-stu-id="886d4-291">You assign several policies to a test group, such as a sampling plan, an AQL, and the requirement for destructive testing.</span></span> <span data-ttu-id="886d4-292">Lorsque vous affectez un test individuel à un groupe de test, vous définissez des informations supplémentaires, telles que l'ordre, les documents et les dates de validité</span><span class="sxs-lookup"><span data-stu-id="886d4-292">When you assign an individual test to a test group, you define additional information, such as the sequence, documents, and validity dates.</span></span> <span data-ttu-id="886d4-293">Pour un test quantitatif; les informations que vous définissez incluent également les valeurs de mesures acceptables.</span><span class="sxs-lookup"><span data-stu-id="886d4-293">For a quantitative test, the information that you define also includes the acceptable measurement values.</span></span> <span data-ttu-id="886d4-294">Pour un test qualitatif, ces informations incluent la variable de test et le résultat par défaut.</span><span class="sxs-lookup"><span data-stu-id="886d4-294">For a qualitative test, the information includes the test variable and default outcome.</span></span> <span data-ttu-id="886d4-295">Le groupe de test affecté à un ordre de qualité définit l'ensemble des tests par défaut devant être exécutés sur l'article spécifié.</span><span class="sxs-lookup"><span data-stu-id="886d4-295">The test group that is assigned to a quality order defines the default set of tests that must be performed on the specified item.</span></span> <span data-ttu-id="886d4-296">Toutefois, vous pouvez ajouter, supprimer ou modifier les tests pour un ordre de qualité.</span><span class="sxs-lookup"><span data-stu-id="886d4-296">However, you can add, delete, or change tests on the quality order.</span></span> <span data-ttu-id="886d4-297">Les résultats de test sont reportés pour chaque test sur un ordre de qualité.</span><span class="sxs-lookup"><span data-stu-id="886d4-297">Test results are reported for each test on a quality order.</span></span></td>
<td><span data-ttu-id="886d4-298">Une société de fabrication définit un groupe de tests pour chaque variation de ses directives qualité.</span><span class="sxs-lookup"><span data-stu-id="886d4-298">A manufacturing company defines a test group for each variation of its quality guidelines.</span></span> <span data-ttu-id="886d4-299">Les groupes de test reflètent les différences entre les programmes d'échantillonnage, les ensembles de tests devant être exécutés simultanément, le niveau de qualité acceptable, ainsi que d'autres facteurs.</span><span class="sxs-lookup"><span data-stu-id="886d4-299">The various test groups reflect differences in the sampling plans, the sets of tests that must be performed together, the AQL, and other factors.</span></span> <span data-ttu-id="886d4-300">Pour les tests quantitatifs, il existe également des différences entre les valeurs de mesures acceptables.</span><span class="sxs-lookup"><span data-stu-id="886d4-300">For quantitative tests, there are also differences in the acceptable measurement values.</span></span> <span data-ttu-id="886d4-301">Pour appliquer ses directives qualité, la société affecte un groupe de test à chaque règle pour la génération automatique d'ordres de qualité sur la page <strong>Associations de qualité</strong>, et affecte également un groupe de test aux ordres de qualité créés manuellement.</span><span class="sxs-lookup"><span data-stu-id="886d4-301">To enforce its quality guidelines, the company assigns a test group to each rule for automatically generating quality orders on the <strong>Quality associations</strong> page, and also assigns a test group to quality orders that are manually created.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="886d4-302">Groupes de qualité d'article</span><span class="sxs-lookup"><span data-stu-id="886d4-302">Item quality groups</span></span></td>
<td><span data-ttu-id="886d4-303">Cette page permet de paramétrer, de modifier et d'afficher les articles affectés à un groupe de qualité ou les groupes de qualité affectés à un article.</span><span class="sxs-lookup"><span data-stu-id="886d4-303">Use this page to set up, edit, and view the items that are assigned to a quality group or the quality groups that are assigned to an item.</span></span> <span data-ttu-id="886d4-304">Un groupe de qualité représente des besoins de test communs pour les articles.</span><span class="sxs-lookup"><span data-stu-id="886d4-304">A quality group represents common testing requirements for items.</span></span> <span data-ttu-id="886d4-305">Une fois que vous avez défini les besoins de test sur la page <strong>Groupes de test</strong>, vous pouvez définir les règles de génération automatique des ordres de qualité.</span><span class="sxs-lookup"><span data-stu-id="886d4-305">After you define the test requirements on the <strong>Test groups</strong> page, you can define the rules for automatically generating quality orders.</span></span> <span data-ttu-id="886d4-306">Pour simplifier le processus, vous ne définissez pas de règles pour des articles individuels.</span><span class="sxs-lookup"><span data-stu-id="886d4-306">To simplify the process, you don&#39;t define rules for individual items.</span></span> <span data-ttu-id="886d4-307">Au lieu de cela, vous définissez des règles pour un groupe de qualité, par l'intermédiaire de la page <strong>Associations de qualité</strong>.</span><span class="sxs-lookup"><span data-stu-id="886d4-307">Instead, you define rules for a quality group, by using the <strong>Quality associations</strong> page.</span></span> <span data-ttu-id="886d4-308">Vous pouvez également utiliser la page <strong>Groupes de qualité d'article</strong> pour un groupe de qualité sélectionné afin d'affecter les articles pertinents à ce groupe.</span><span class="sxs-lookup"><span data-stu-id="886d4-308">You can also use the <strong>Item quality groups</strong> page for a selected quality group to assign relevant items to that group.</span></span> <span data-ttu-id="886d4-309">Vous pouvez également utiliser la page <strong>Groupes de qualité d'article</strong> pour un article sélectionné afin d'affecter les groupes de qualité pertinents à cet article.</span><span class="sxs-lookup"><span data-stu-id="886d4-309">You can also use the <strong>Item quality groups</strong> page for a selected item to assign relevant quality groups to that item.</span></span></td>
<td><span data-ttu-id="886d4-310">Une société de fabrication achète diverses matières premières présentant les mêmes besoins de test pour l'inspection à venir.</span><span class="sxs-lookup"><span data-stu-id="886d4-310">A manufacturing company purchases various raw materials that have the same testing requirements for incoming inspection.</span></span> <span data-ttu-id="886d4-311">La société définit un groupe de qualité, puis affecte les numéros d'articles associés aux matières premières à ce groupe.</span><span class="sxs-lookup"><span data-stu-id="886d4-311">The company defines a quality group and then assigns the item numbers that are associated with the raw materials to that group.</span></span> <span data-ttu-id="886d4-312">Ensuite, la société achète un nouveau type de matières premières ayant les mêmes besoins de test.</span><span class="sxs-lookup"><span data-stu-id="886d4-312">Later, the company purchases a new type of raw material that has the same testing requirements.</span></span> <span data-ttu-id="886d4-313">Au lieu de paramétrer de nouveaux besoins de test pour les nouvelles matières, la société ajoute le numéro d'article pour la nouvelle matière au groupe de qualité existant.</span><span class="sxs-lookup"><span data-stu-id="886d4-313">Instead of setting up new testing requirements for the new material, the company adds the item number for the new material to the existing quality group.</span></span> <span data-ttu-id="886d4-314">La même société de fabrication produit également des articles ayant les mêmes besoins de test de production et expédie les articles dotés des mêmes besoins en tests de pré-expédition.</span><span class="sxs-lookup"><span data-stu-id="886d4-314">The same manufacturing company also produces items that have the same production testing requirements and ships items that have the same requirement for pre-shipment testing.</span></span> <span data-ttu-id="886d4-315">La société définit deux groupes de qualité supplémentaires, puis affecte les numéros d'articles pertinents à chaque groupe.</span><span class="sxs-lookup"><span data-stu-id="886d4-315">The company defines two additional quality groups and then assigns the relevant item numbers to each group.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="886d4-316">Variables de test</span><span class="sxs-lookup"><span data-stu-id="886d4-316">Test variables</span></span></td>
<td><span data-ttu-id="886d4-317">Cette page vous permet de définir et d'afficher les variables associées à un test qualitatif.</span><span class="sxs-lookup"><span data-stu-id="886d4-317">Use this page to define and view the variables that are associated with a qualitative test.</span></span> <span data-ttu-id="886d4-318">Pour chaque variable, vous définissez les résultats énumérés qui représentent les options possibles.</span><span class="sxs-lookup"><span data-stu-id="886d4-318">For each variable, you define enumerated outcomes that represent the possible options.</span></span> <span data-ttu-id="886d4-319">Vous définissez des tests sur la page <strong>Tests</strong>.</span><span class="sxs-lookup"><span data-stu-id="886d4-319">You define tests on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="886d4-320">Pour les tests qualitatifs, vous devez définir le type de test à <strong>Option</strong>.</span><span class="sxs-lookup"><span data-stu-id="886d4-320">For qualitative tests, you must set the test type to <strong>Option</strong>.</span></span> <span data-ttu-id="886d4-321">La page <strong>Groupes de test</strong> vous permet d'affecter une variable de test à un test individuel.</span><span class="sxs-lookup"><span data-stu-id="886d4-321">Use the <strong>Test groups</strong> page to assign a test variable to an individual test.</span></span></td>
<td><span data-ttu-id="886d4-322">Une société de fabrication de biscuits utilise un test d'inspection pour le produit fini.</span><span class="sxs-lookup"><span data-stu-id="886d4-322">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="886d4-323">Ce test d'inspection comporte plusieurs variables.</span><span class="sxs-lookup"><span data-stu-id="886d4-323">This inspection test has several variables.</span></span> <span data-ttu-id="886d4-324">L'une des variables est le goût et les résultats possibles pour cette variable sont Bon et Mauvais.</span><span class="sxs-lookup"><span data-stu-id="886d4-324">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="886d4-325">Une deuxième variable est la couleur et les résultats possibles sont Trop foncé, Trop clair et Correct.</span><span class="sxs-lookup"><span data-stu-id="886d4-325">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="886d4-326">Résultats de la variable de test</span><span class="sxs-lookup"><span data-stu-id="886d4-326">Test variable outcomes</span></span></td>
<td><span data-ttu-id="886d4-327">Cette page permet de paramétrer, de modifier et d'afficher les résultats de tests possibles pour une variable de test associée à un test qualitatif.</span><span class="sxs-lookup"><span data-stu-id="886d4-327">Use this page to set up, edit, and to view the possible test results for a test variable that is associated with a qualitative test.</span></span> <span data-ttu-id="886d4-328">Pour chaque résultat, vous affectez un statut <strong>Réussite</strong> ou <strong>Échec</strong>.</span><span class="sxs-lookup"><span data-stu-id="886d4-328">For each outcome, you assign a <strong>pass</strong> or <strong>fail</strong> status.</span></span> <span data-ttu-id="886d4-329">Vous devez définir une variable et ses résultats pour chaque test qualitatif défini sur la page <strong>Tests</strong>.</span><span class="sxs-lookup"><span data-stu-id="886d4-329">You must define a variable and its outcomes for each qualitative test that is defined on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="886d4-330">(Pour les tests qualitatifs, le type de test est défini sur <strong>Option</strong> dans la page <strong>Tests</strong>.) La page <strong>Groupes de tests</strong> permet d'affecter une variable de test et le résultat par défaut à un test qualitatif individuel.</span><span class="sxs-lookup"><span data-stu-id="886d4-330">(For qualitative tests, the test type is set to <strong>Option</strong> on the <strong>Tests</strong> page.) Use the <strong>Test groups</strong> page to assign a test variable and the default outcome to an individual qualitative test.</span></span></td>
<td><span data-ttu-id="886d4-331">Une société de fabrication de biscuits utilise un test d'inspection pour le produit fini.</span><span class="sxs-lookup"><span data-stu-id="886d4-331">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="886d4-332">Ce test d'inspection comporte plusieurs variables.</span><span class="sxs-lookup"><span data-stu-id="886d4-332">This inspection test has of several variables.</span></span> <span data-ttu-id="886d4-333">L'une des variables est le goût et les résultats possibles pour cette variable sont Bon et Mauvais.</span><span class="sxs-lookup"><span data-stu-id="886d4-333">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="886d4-334">Une deuxième variable est la couleur et les résultats possibles sont Trop foncé, Trop clair et Correct.</span><span class="sxs-lookup"><span data-stu-id="886d4-334">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span> <span data-ttu-id="886d4-335">Un statut <strong>Réussite</strong> ou <strong>Échec</strong> est affecté à chaque résultat.</span><span class="sxs-lookup"><span data-stu-id="886d4-335">A status of <strong>pass</strong> or <strong>fail</strong> is assigned to each outcome.</span></span> <span data-ttu-id="886d4-336">Au cours du test d'inspection effectué pour chaque variable, l'inspecteur présente le résultat du test en sélectionnant l'un des résultats.</span><span class="sxs-lookup"><span data-stu-id="886d4-336">During the inspection test for each variable, the inspector reports the test result by selecting one of the outcomes.</span></span></td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a><span data-ttu-id="886d4-337">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="886d4-337">Additional resources</span></span>
--------

[<span data-ttu-id="886d4-338">Processus de gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="886d4-338">Quality management processes</span></span>](quality-management-processes.md)

[<span data-ttu-id="886d4-339">Activation de la gestion de non-conformité</span><span class="sxs-lookup"><span data-stu-id="886d4-339">Enabling nonconformance management</span></span>](enable-nonconformance-management.md)
