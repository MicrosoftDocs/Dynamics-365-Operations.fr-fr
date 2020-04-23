---
title: Vue d'ensemble des prérequis pour les coûts standard
description: Cette rubrique décrit les étapes essentielles de l'utilisation des coûts standard.
author: AndersGirke
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventStdCostConv, CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f66f7061c608379689016e3c0b9c5ba4ad23dc9e
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214509"
---
# <a name="prerequisites-for-standard-costs-overview"></a><span data-ttu-id="0fd44-103">Vue d'ensemble des prérequis pour les coûts standard</span><span class="sxs-lookup"><span data-stu-id="0fd44-103">Prerequisites for standard costs overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0fd44-104">Cette rubrique décrit les étapes essentielles de l'utilisation des coûts standard.</span><span class="sxs-lookup"><span data-stu-id="0fd44-104">This topic describes the basic steps for using standard costs.</span></span> <span data-ttu-id="0fd44-105">Les étapes suivantes dépendent des opérations de la société.</span><span class="sxs-lookup"><span data-stu-id="0fd44-105">Subsequent steps depend on the company's operations.</span></span> <span data-ttu-id="0fd44-106">Par exemple, les étapes diffèrent pour un environnement hors fabrication, un environnement de fabrication qui n'utilise pas de gammes et un environnement de fabrication qui utilise des gammes.</span><span class="sxs-lookup"><span data-stu-id="0fd44-106">For example, the steps differ for a nonmanufacturing environment, a manufacturing environment that doesn't use routings, and a manufacturing environment that uses routings.</span></span> 

<span data-ttu-id="0fd44-107">Pour paramétrer les coûts standard, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0fd44-107">To set up standard costs, follow these steps.</span></span>

<span data-ttu-id="0fd44-108">**1. Créez un groupe de modèles d'article pour les coûts standard.**</span><span class="sxs-lookup"><span data-stu-id="0fd44-108">**1. Create an item model group for standard costs.**</span></span>

<span data-ttu-id="0fd44-109">La page **Groupes de modèles d'article** permet de créer un nouveau groupe de coûts standard et d'affecter un modèle de stock de **Coût standard**.</span><span class="sxs-lookup"><span data-stu-id="0fd44-109">Use the **Item model groups** page to create a new group for standard costs, and assign an inventory model of **Standard cost**.</span></span> <span data-ttu-id="0fd44-110">L'identificateur du groupe de modèles d'article doit être significatif, comme **Coût std**.</span><span class="sxs-lookup"><span data-stu-id="0fd44-110">The identifier for the item model group should be meaningful, such as **Std Cost**.</span></span> <span data-ttu-id="0fd44-111">Activez les cases à cocher pour indiquer que le groupe doit autoriser les stocks financiers négatifs et valider les stocks physiques et financiers.</span><span class="sxs-lookup"><span data-stu-id="0fd44-111">Select the check boxes to indicate that the group should allow financial negative inventory, and that it should post physical inventory and financial inventory.</span></span> <span data-ttu-id="0fd44-112">Ce groupe de coûts standard sera affecté aux articles.</span><span class="sxs-lookup"><span data-stu-id="0fd44-112">This standard cost group will be assigned to items.</span></span>

<span data-ttu-id="0fd44-113">**2. Définissez les comptes généraux associés aux écarts de coûts standard.**</span><span class="sxs-lookup"><span data-stu-id="0fd44-113">**2. Define ledger accounts that are related to standard cost variances.**</span></span> 

<span data-ttu-id="0fd44-114">La page **Plan de comptes** permet de définir les comptes généraux associés aux écarts de coûts standard.</span><span class="sxs-lookup"><span data-stu-id="0fd44-114">Use the **Chart of accounts** page to define ledger accounts that are related to standard cost variances.</span></span> <span data-ttu-id="0fd44-115">Ces comptes généraux doivent être définis avant qu'ils puissent être affectés dans la page **Validation**.</span><span class="sxs-lookup"><span data-stu-id="0fd44-115">These ledger accounts must be defined before they can be assigned on the **Posting** page.</span></span> <span data-ttu-id="0fd44-116">Les comptes généraux peuvent refléter les groupes d'articles et les groupes de coûts.</span><span class="sxs-lookup"><span data-stu-id="0fd44-116">The ledger accounts can reflect item groups and cost groups.</span></span>

<span data-ttu-id="0fd44-117">**3. Affectez des comptes généraux aux validations d'articles associées aux écarts de coûts standard.**</span><span class="sxs-lookup"><span data-stu-id="0fd44-117">**3. Assign ledger accounts to item postings that are related to standard cost variances.**</span></span> 

<span data-ttu-id="0fd44-118">La page **Validation** permet d'affecter les comptes généraux associés aux écarts de coûts standard.</span><span class="sxs-lookup"><span data-stu-id="0fd44-118">Use the **Posting** page to assign the ledger accounts that are related to standard cost variances.</span></span> <span data-ttu-id="0fd44-119">Vous pouvez spécifier un compte général d'écart par article (ou groupe d'articles) et par groupe de coûts (ou type de groupe de coûts) ou spécifier que le compte spécifique s'applique à tous les articles et tous les groupes de coûts.</span><span class="sxs-lookup"><span data-stu-id="0fd44-119">You can specify a variance's ledger account by item (or item group) and by cost group (or cost group type), or you can specify that the ledger account applies to all items and all cost groups.</span></span> <span data-ttu-id="0fd44-120">Ces options correspondent aux relations de coûts pour les tables, les groupes et pour tous.</span><span class="sxs-lookup"><span data-stu-id="0fd44-120">These options correspond to cost relations for tables, groups, and all.</span></span> 

<span data-ttu-id="0fd44-121">Avant de définir les règles de validation d'articles, utilisez la page **Combinaisons de transactions** pour activer les relations de coûts (pour les tables, les groupes et pour tous).</span><span class="sxs-lookup"><span data-stu-id="0fd44-121">Before you define the item posting rules, use the **Transaction combinations** page to enable cost relations (for tables, groups, and all).</span></span>

<span data-ttu-id="0fd44-122">**4. Définissez les paramètres de stock associés aux coûts standard.**</span><span class="sxs-lookup"><span data-stu-id="0fd44-122">**4. Define inventory parameters that are related to standard costs.**</span></span> 

-  <span data-ttu-id="0fd44-123">L'onglet **Comptabilité de stock** de la page **Paramétrage des stratégies comptables de stock > Paramètres** permet de définir deux paramètres de contrôle des coûts associés aux coûts standard.</span><span class="sxs-lookup"><span data-stu-id="0fd44-123">Use the **Inventory accounting** tab on the **Inventory accounting policies setup > Parameters** page to define two cost control parameters that are related to standard costs.</span></span>

    -  <span data-ttu-id="0fd44-124">Dans le champ **Analyse des coûts**, sélectionnez **Aucun** ou **Sous-comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="0fd44-124">In the **Cost breakdown** field, select **None** or **Sub ledger**.</span></span> <span data-ttu-id="0fd44-125">Si vous sélectionnez **Sous-comptabilité**, l'analyse des coûts est *active*.</span><span class="sxs-lookup"><span data-stu-id="0fd44-125">If you select **Sub ledger**, the cost breakdown is an *active* cost breakdown.</span></span> <span data-ttu-id="0fd44-126">Une analyse active des coûts est essentielle pour le calcul, la retenue et l'affichage de la segmentation des groupes de coûts dans une structure de produits à plusieurs niveaux pour des articles de coûts standard.</span><span class="sxs-lookup"><span data-stu-id="0fd44-126">An active cost breakdown is critical for calculating, retaining, and viewing cost group segmentation across a multilevel product structure for standard cost items.</span></span> <span data-ttu-id="0fd44-127">Lorsque l'analyse des coûts est active, vous pouvez déclarer et analyser le stock, les travaux en cours et le coût des marchandises vendues par groupe de coûts dans un niveau, dans plusieurs niveaux ou dans le format total.</span><span class="sxs-lookup"><span data-stu-id="0fd44-127">When the cost breakdown is active, you can report and analyze inventory, work in process (WIP), and cost of goods sold (COGS) per cost group in a single-level, multilevel, or total format.</span></span> <span data-ttu-id="0fd44-128">Lorsque l'analyse des coûts est active, l'activation du coût d'un article fabriqué entraînera le stockage de la segmentation des groupes de coûts dans l'enregistrement des coûts de l'article.</span><span class="sxs-lookup"><span data-stu-id="0fd44-128">When the cost breakdown is active, if you activate a manufactured item's cost, the cost group segmentation will be stored in the item's cost record.</span></span> 

    -  <span data-ttu-id="0fd44-129">Si vous sélectionnez **Aucun**, la segmentation des groupes de coûts ne sera pas mise à jour pour les articles de coût standard.</span><span class="sxs-lookup"><span data-stu-id="0fd44-129">If you select **None**, cost group segmentation won't be maintained for standard cost items.</span></span> <span data-ttu-id="0fd44-130">En d'autres termes, le coût standard d'un article fabriqué sera calculé et mis à jour en tant que montant unique sans segmentation des groupes de coûts.</span><span class="sxs-lookup"><span data-stu-id="0fd44-130">In other words, a manufactured item's standard cost will be calculated and maintained as a single amount, without cost group segmentation.</span></span> <span data-ttu-id="0fd44-131">Les contributions de coûts des composants fabriqués seront regroupées sur le montant unique.</span><span class="sxs-lookup"><span data-stu-id="0fd44-131">The cost contributions of manufactured components will be aggregated into the single amount.</span></span>

-  <span data-ttu-id="0fd44-132">Dans le champ **Écarts par rapport à standard**, sélectionnez **Résumé** ou **Par groupe de coûts**.</span><span class="sxs-lookup"><span data-stu-id="0fd44-132">In the **Variances to standard** field, select **Summarized** or **Per cost group**.</span></span> <span data-ttu-id="0fd44-133">Si vous sélectionnez **Par groupe de coûts**, vous pouvez identifier les écarts de prix d'achat et les écarts de production par groupe de coûts.</span><span class="sxs-lookup"><span data-stu-id="0fd44-133">If you select **Per cost group**, you can identify purchase price variances and production variances by cost group.</span></span> <span data-ttu-id="0fd44-134">Vous pouvez également identifier les quatre types d'écarts de production : taille du lot, quantité, prix et écarts de remplacement.</span><span class="sxs-lookup"><span data-stu-id="0fd44-134">You can also identify the four types of production variances: the lot size, quantity, price, and substitution variances.</span></span> <span data-ttu-id="0fd44-135">Si vous sélectionnez **Résumé**, vous ne pouvez pas identifier les écarts par groupe de coûts, ni les quatre types d'écarts de production.</span><span class="sxs-lookup"><span data-stu-id="0fd44-135">If you select **Summarized**, you can't identify variances by cost group, and you can't identify the four types of production variances.</span></span> <span data-ttu-id="0fd44-136">Vous pouvez uniquement afficher un écart de production récapitulé.</span><span class="sxs-lookup"><span data-stu-id="0fd44-136">You can just view a summarized production variance.</span></span>

-  <span data-ttu-id="0fd44-137">La stratégie d'écarts de coûts standard fonctionne indépendamment de la stratégie d'analyse des coûts.</span><span class="sxs-lookup"><span data-stu-id="0fd44-137">The policy about variance to standard works independently of the cost breakdown policy.</span></span> <span data-ttu-id="0fd44-138">En d'autres termes, vous pouvez choisir la stratégie d'analyse des coûts **Aucun** et sélectionner des écarts par groupe de coûts, pour que les écarts de production par groupe de coûts soient tout de même capturés.</span><span class="sxs-lookup"><span data-stu-id="0fd44-138">In other words, you can select a cost breakdown policy of **None** and select variances per cost group, so that production variances by cost group will still be captured.</span></span>

<span data-ttu-id="0fd44-139">**5. Créez des versions d'évaluation des coûts standard.**</span><span class="sxs-lookup"><span data-stu-id="0fd44-139">**5. Create costing versions for standard costs.**</span></span> 

<span data-ttu-id="0fd44-140">La page **Paramétrage de la version d'évaluation des coûts** permet de créer une ou plusieurs versions d'évaluation des coûts standard.</span><span class="sxs-lookup"><span data-stu-id="0fd44-140">Use the **Costing version setup** page to create one or more costing versions for standard costs.</span></span> <span data-ttu-id="0fd44-141">Chaque version d'évaluation des coûts doit être désignée par un type d'évaluation des **coûts standard** et doit permettre d'inclure des données de coûts.</span><span class="sxs-lookup"><span data-stu-id="0fd44-141">Each costing version must be designated by a costing type of **Standard cost** and must allow content to include cost data.</span></span>

<span data-ttu-id="0fd44-142">**6. Préparez un client existant pour utiliser les coûts standard.**</span><span class="sxs-lookup"><span data-stu-id="0fd44-142">**6. Prepare an existing customer to use standard costs.**</span></span> 

<span data-ttu-id="0fd44-143">Les clients qui souhaitent modifier leurs articles existants pour passer à un modèle de stock de coûts standard doivent utiliser la page **Conversions de coût standard**.</span><span class="sxs-lookup"><span data-stu-id="0fd44-143">Customers who want to change their existing items to a standard cost inventory model must use the **Standard cost conversions** page.</span></span>


<a name="related-topics"></a><span data-ttu-id="0fd44-144">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="0fd44-144">Related topics</span></span>
--------

[<span data-ttu-id="0fd44-145">Vue d'ensemble de la conversion du coût standard</span><span class="sxs-lookup"><span data-stu-id="0fd44-145">Standard cost conversion overview</span></span>](standard-cost-conversion-overview.md)

### <a name="blogs"></a><span data-ttu-id="0fd44-146">Blogs</span><span class="sxs-lookup"><span data-stu-id="0fd44-146">Blogs</span></span>

#### <a name="community-blogs"></a><span data-ttu-id="0fd44-147">Blogs de la communauté</span><span class="sxs-lookup"><span data-stu-id="0fd44-147">Community blogs</span></span>

- [<span data-ttu-id="0fd44-148">Procédure de paramétrage des coûts standard pour les matières directes dans Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0fd44-148">How to set up standard costs for direct materials in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/06/07/how-to-set-up-standard-costs-for-direct-materials-in-dynamics-365-for-finance-and-operations)
- [<span data-ttu-id="0fd44-149">Coûts de main d'œuvre directs standard dans Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0fd44-149">Standard direct labor costs in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/07/16/standard-direct-labor-cost-in-dynamics-365-for-finance-and-operations)
