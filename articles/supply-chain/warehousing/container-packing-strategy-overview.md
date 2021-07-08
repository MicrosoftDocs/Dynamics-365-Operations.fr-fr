---
title: Stratégies de conditionnement en conteneurs
description: Cette rubrique décrit les différences entre les stratégies d’emballage dans des conteneurs et en donne des exemples.
author: GalynaFedorova
ms.date: 06/11/2021
ms.topic: article
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak, WHSContainerStructure, WHSContainerTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: f481f6ca047ee0285fe0e81d8fa96665e9d27cee
ms.sourcegitcommit: 8e846b52763f90d2232ec7d427839f4722570bce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/22/2021
ms.locfileid: "6292759"
---
# <a name="container-packing-strategies"></a><span data-ttu-id="e0062-103">Stratégies de conditionnement en conteneurs</span><span class="sxs-lookup"><span data-stu-id="e0062-103">Container packing strategies</span></span>

<span data-ttu-id="e0062-104">Une *stratégie de conditionnement en conteneurs* est une stratégie que vous pouvez utiliser pour définir les répartitions entre les conteneurs.</span><span class="sxs-lookup"><span data-stu-id="e0062-104">A *container packing strategy* is a strategy that you can use to define item allocations across containers.</span></span> <span data-ttu-id="e0062-105">Cette rubrique explique les différences entre les stratégies *Conditionner dans tous les conteneurs ouverts* et *Conditionner dans le conteneur en cours uniquement*.</span><span class="sxs-lookup"><span data-stu-id="e0062-105">This topic explains the differences between the *Pack into all open containers* and *Pack into current container only* strategies.</span></span>

- <span data-ttu-id="e0062-106">**Conditionner dans tous les conteneurs ouverts** : le système doit vérifier tous les conteneurs ouverts qui ont déjà été créés pendant le cycle de conteneurisation, pour s’assurer que l’article rentrera dans l’un d’entre eux.</span><span class="sxs-lookup"><span data-stu-id="e0062-106">**Pack into all open containers** – The system must check all open containers that have already been created during the containerization cycle, to make sure that the item will fit into one of them.</span></span> <span data-ttu-id="e0062-107">Lors de l’emballage, le système vérifie chaque article pour déterminer s’il rentre dans l’un des conteneurs créés précédemment.</span><span class="sxs-lookup"><span data-stu-id="e0062-107">During packing, the system checks each item to determine whether it will fit into any of the previously created containers.</span></span> <span data-ttu-id="e0062-108">Si l’article ne rentre dans aucun conteneur existant, le système crée un nouveau conteneur et continue jusqu’à ce qu’il ait fini d’emballer toute la commande.</span><span class="sxs-lookup"><span data-stu-id="e0062-108">If the item won't fit into an existing container, the system creates a new container and continues until it has finished packing the whole order.</span></span>

    <span data-ttu-id="e0062-109">Par example, *n* articles commandés nécessitent une conteneurisation.</span><span class="sxs-lookup"><span data-stu-id="e0062-109">For example, *n* ordered items require containerization.</span></span> <span data-ttu-id="e0062-110">Dans le pire des cas, chaque fois que le système traite un article qui ne rentre dans aucun conteneur existant, il effectue un total de (\[(*n* – 1) × (*n* + 1)\] ÷ 2) contrôles pour voir si l’article rentre dans les conteneurs existants.</span><span class="sxs-lookup"><span data-stu-id="e0062-110">In the worst case, every time that the system processes an item that doesn't fit into any existing container, it will do a total of (\[(*n* – 1) × (*n* + 1)\] ÷ 2) checks to evaluate whether the item fits into the existing containers.</span></span>

- <span data-ttu-id="e0062-111">**Conditionner dans le conteneur en cours uniquement** – Le système ne vérifie que le conteneur créé le plus récemment pour s’assurer que l’article y rentrera.</span><span class="sxs-lookup"><span data-stu-id="e0062-111">**Pack into current container only** – The system must check only the most recently created container to make sure that the item will fit into it.</span></span> <span data-ttu-id="e0062-112">Lors de l’emballage, le système vérifie chaque article pour déterminer s’il rentre dans le conteneur créé le plus récemment.</span><span class="sxs-lookup"><span data-stu-id="e0062-112">During packing, the system checks each item to determine whether it will fit into the most recently created container.</span></span> <span data-ttu-id="e0062-113">Si l’article ne rentre pas dans ce conteneur, le système crée un nouveau conteneur et continue jusqu’à ce qu’il ait fini d’emballer toute la commande.</span><span class="sxs-lookup"><span data-stu-id="e0062-113">If the item won't fit into that container, the system creates a new container and continues until it has finished packing the whole order.</span></span>

    <span data-ttu-id="e0062-114">Par example, *n* articles commandés nécessitent une conteneurisation.</span><span class="sxs-lookup"><span data-stu-id="e0062-114">For example, *n* ordered items require containerization.</span></span> <span data-ttu-id="e0062-115">Dans le pire des cas, le système fera un total de (*n* – 1) contrôles pour évaluer si l’article rentre dans les conteneurs.</span><span class="sxs-lookup"><span data-stu-id="e0062-115">In the worst case, the system will do a total of (*n* – 1) checks to evaluate whether the item fits into the containers.</span></span>

## <a name="example-of-the-flow-for-container-packing-strategies"></a><span data-ttu-id="e0062-116">Exemple de flux pour les stratégies de conditionnement en conteneurs</span><span class="sxs-lookup"><span data-stu-id="e0062-116">Example of the flow for container packing strategies</span></span>

<span data-ttu-id="e0062-117">Vous configurez les articles suivants pour la conteneurisation.</span><span class="sxs-lookup"><span data-stu-id="e0062-117">You set up the following items for containerization.</span></span>

| <span data-ttu-id="e0062-118">Article</span><span class="sxs-lookup"><span data-stu-id="e0062-118">Item</span></span> | <span data-ttu-id="e0062-119">Dimensions physiques (largeur × profondeur × hauteur)</span><span class="sxs-lookup"><span data-stu-id="e0062-119">Physical dimensions (width × depth × height)</span></span> | <span data-ttu-id="e0062-120">Pondération</span><span class="sxs-lookup"><span data-stu-id="e0062-120">Weight</span></span> |
|---|---|---|
| <span data-ttu-id="e0062-121">Câble HDMI 6 po</span><span class="sxs-lookup"><span data-stu-id="e0062-121">HDMI Cable 6'</span></span> | <span data-ttu-id="e0062-122">1 × 1 × 1</span><span class="sxs-lookup"><span data-stu-id="e0062-122">1 × 1 × 1</span></span> | <span data-ttu-id="e0062-123">1</span><span class="sxs-lookup"><span data-stu-id="e0062-123">1</span></span> |
| <span data-ttu-id="e0062-124">Câble HDMI 12 po</span><span class="sxs-lookup"><span data-stu-id="e0062-124">HDMI Cable 12'</span></span> | <span data-ttu-id="e0062-125">2 × 1 × 1</span><span class="sxs-lookup"><span data-stu-id="e0062-125">2 × 1 × 1</span></span> | <span data-ttu-id="e0062-126">1</span><span class="sxs-lookup"><span data-stu-id="e0062-126">1</span></span> |
| <span data-ttu-id="e0062-127">Câble HDMI 18 po</span><span class="sxs-lookup"><span data-stu-id="e0062-127">HDMI Cable 18'</span></span> | <span data-ttu-id="e0062-128">3 × 1 × 1</span><span class="sxs-lookup"><span data-stu-id="e0062-128">3 × 1 × 1</span></span> | <span data-ttu-id="e0062-129">2</span><span class="sxs-lookup"><span data-stu-id="e0062-129">2</span></span> |

<span data-ttu-id="e0062-130">Vous configurez également le carton suivant qui sera utilisé pour l’emballage.</span><span class="sxs-lookup"><span data-stu-id="e0062-130">You also set up the following box that will be used for packaging.</span></span>

| <span data-ttu-id="e0062-131">Conteneur</span><span class="sxs-lookup"><span data-stu-id="e0062-131">Container</span></span> | <span data-ttu-id="e0062-132">Dimensions physiques (longueur × largeur × hauteur)</span><span class="sxs-lookup"><span data-stu-id="e0062-132">Physical dimensions (length × width × height)</span></span> | <span data-ttu-id="e0062-133">Pondération</span><span class="sxs-lookup"><span data-stu-id="e0062-133">Weight</span></span> | <span data-ttu-id="e0062-134">Volume</span><span class="sxs-lookup"><span data-stu-id="e0062-134">Volume</span></span> |
|---|---|---|---|
| <span data-ttu-id="e0062-135">Carton moyen</span><span class="sxs-lookup"><span data-stu-id="e0062-135">Medium Box</span></span> | <span data-ttu-id="e0062-136">6 × 3 × 2</span><span class="sxs-lookup"><span data-stu-id="e0062-136">6 × 3 × 2</span></span> | <span data-ttu-id="e0062-137">10</span><span class="sxs-lookup"><span data-stu-id="e0062-137">10</span></span> | <span data-ttu-id="e0062-138">100</span><span class="sxs-lookup"><span data-stu-id="e0062-138">100</span></span> |

<span data-ttu-id="e0062-139">Enfin, vous configurez une commande qui contient les produits et quantités suivants.</span><span class="sxs-lookup"><span data-stu-id="e0062-139">Finally, you set up an order that has the following products and quantities.</span></span>

| <span data-ttu-id="e0062-140">Ligne de commande client</span><span class="sxs-lookup"><span data-stu-id="e0062-140">Sales order line</span></span> | <span data-ttu-id="e0062-141">Quantité</span><span class="sxs-lookup"><span data-stu-id="e0062-141">Quantity</span></span> |
|---|---|
| <span data-ttu-id="e0062-142">Câble HDMI 12 po</span><span class="sxs-lookup"><span data-stu-id="e0062-142">HDMI Cable 12'</span></span> | <span data-ttu-id="e0062-143">9</span><span class="sxs-lookup"><span data-stu-id="e0062-143">9</span></span> |
| <span data-ttu-id="e0062-144">Câble HDMI 18 po</span><span class="sxs-lookup"><span data-stu-id="e0062-144">HDMI Cable 18'</span></span> | <span data-ttu-id="e0062-145">8</span><span class="sxs-lookup"><span data-stu-id="e0062-145">8</span></span> |
| <span data-ttu-id="e0062-146">Câble HDMI 6 po</span><span class="sxs-lookup"><span data-stu-id="e0062-146">HDMI Cable 6'</span></span> | <span data-ttu-id="e0062-147">13</span><span class="sxs-lookup"><span data-stu-id="e0062-147">13</span></span> |

<span data-ttu-id="e0062-148">Le tableau suivant résume le fonctionnement de la conteneurisation lorsque vous utilisez la stratégie *Conditionner dans tous les conteneurs ouverts* et lorsque vous utilisez la stratégie *Conditionner dans le conteneur en cours uniquement*.</span><span class="sxs-lookup"><span data-stu-id="e0062-148">The following table summarizes how containerization works when you use the *Pack into all open containers* strategy and when you use the *Pack into current container only* strategy.</span></span>

| <span data-ttu-id="e0062-149">Conditionner dans tous les conteneurs ouverts</span><span class="sxs-lookup"><span data-stu-id="e0062-149">Pack into all open containers</span></span> | <span data-ttu-id="e0062-150">Conditionner dans le conteneur en cours</span><span class="sxs-lookup"><span data-stu-id="e0062-150">Pack into current container</span></span> |
|---|---|
| <p><span data-ttu-id="e0062-151">Câble HDMI 12 po :</span><span class="sxs-lookup"><span data-stu-id="e0062-151">HDMI Cable 12':</span></span></p><ol><li><span data-ttu-id="e0062-152">Créez un nouveau conteneur, CONT0001.</span><span class="sxs-lookup"><span data-stu-id="e0062-152">Create a new container, CONT0001.</span></span></li><li><span data-ttu-id="e0062-153">Mettez 9 unités dans le conteneur CONT0001.</span><span class="sxs-lookup"><span data-stu-id="e0062-153">Put 9 ea into container CONT0001.</span></span></li></ol> | <p><span data-ttu-id="e0062-154">Câble HDMI 12 po :</span><span class="sxs-lookup"><span data-stu-id="e0062-154">HDMI Cable 12':</span></span></p><ol><li><span data-ttu-id="e0062-155">Créez un nouveau conteneur, CONT0001.</span><span class="sxs-lookup"><span data-stu-id="e0062-155">Create a new container, CONT0001.</span></span></li><li><span data-ttu-id="e0062-156">Mettez 9 unités dans le conteneur CONT0001.</span><span class="sxs-lookup"><span data-stu-id="e0062-156">Put 9 ea into container CONT0001.</span></span></li></ol> |
| <p><span data-ttu-id="e0062-157">Câble HDMI 18 po :</span><span class="sxs-lookup"><span data-stu-id="e0062-157">HDMI Cable 18':</span></span></p><ol><li><span data-ttu-id="e0062-158">Vérifiez si l’article peut tenir dans le conteneur CONT0001.</span><span class="sxs-lookup"><span data-stu-id="e0062-158">Check whether the item can fit into container CONT0001.</span></span></li><li><span data-ttu-id="e0062-159">Créez un nouveau conteneur, CONT0002.</span><span class="sxs-lookup"><span data-stu-id="e0062-159">Create a new container, CONT0002.</span></span></li><li><span data-ttu-id="e0062-160">Mettez 5 unités dans le conteneur CONT0002.</span><span class="sxs-lookup"><span data-stu-id="e0062-160">Put 5 ea into container CONT0002.</span></span></li><li><span data-ttu-id="e0062-161">Créez un nouveau conteneur, CONT0003.</span><span class="sxs-lookup"><span data-stu-id="e0062-161">Create a new container, CONT0003.</span></span></li><li><span data-ttu-id="e0062-162">Mettez 3 unités dans le conteneur CONT0003.</span><span class="sxs-lookup"><span data-stu-id="e0062-162">Put 3 ea into container CONT0003.</span></span></li></ol> | <p><span data-ttu-id="e0062-163">Câble HDMI 18 po :</span><span class="sxs-lookup"><span data-stu-id="e0062-163">HDMI Cable 18':</span></span></p><ol><li><span data-ttu-id="e0062-164">Vérifiez si l’article peut tenir dans le conteneur CONT0001.</span><span class="sxs-lookup"><span data-stu-id="e0062-164">Check whether the item can fit into container CONT0001.</span></span></li><li><span data-ttu-id="e0062-165">Créez un nouveau conteneur, CONT0002.</span><span class="sxs-lookup"><span data-stu-id="e0062-165">Create a new container, CONT0002.</span></span></li><li><span data-ttu-id="e0062-166">Mettez 5 unités dans le conteneur CONT0002.</span><span class="sxs-lookup"><span data-stu-id="e0062-166">Put 5 ea into container CONT0002.</span></span></li><li><span data-ttu-id="e0062-167">Créez un nouveau conteneur, CONT0003.</span><span class="sxs-lookup"><span data-stu-id="e0062-167">Create a new container, CONT0003.</span></span></li><li><span data-ttu-id="e0062-168">Mettez 3 unités dans le conteneur CONT0003.</span><span class="sxs-lookup"><span data-stu-id="e0062-168">Put 3 ea into container CONT0003.</span></span></li></ol> |
| <p><span data-ttu-id="e0062-169">Câble HDMI 6 po :</span><span class="sxs-lookup"><span data-stu-id="e0062-169">HDMI Cable 6':</span></span></p><ol><li><span data-ttu-id="e0062-170">Vérifiez si l’article peut tenir dans le conteneur CONT0001.</span><span class="sxs-lookup"><span data-stu-id="e0062-170">Check whether the item can fit into container CONT0001.</span></span></li><li><span data-ttu-id="e0062-171">Mettez 1 unité dans le conteneur CONT0001.</span><span class="sxs-lookup"><span data-stu-id="e0062-171">Put 1 ea into container CONT0001.</span></span></li><li><span data-ttu-id="e0062-172">Vérifiez si l’article peut tenir dans le conteneur CONT0002.</span><span class="sxs-lookup"><span data-stu-id="e0062-172">Check whether the item can fit into container CONT0002.</span></span></li><li><span data-ttu-id="e0062-173">Vérifiez si l’article peut tenir dans le conteneur CONT0003.</span><span class="sxs-lookup"><span data-stu-id="e0062-173">Check whether the item can fit into container CONT0003.</span></span></li><li><span data-ttu-id="e0062-174">Mettez 4 unités dans le conteneur CONT0003.</span><span class="sxs-lookup"><span data-stu-id="e0062-174">Put 4 ea into container CONT0003.</span></span></li><li><span data-ttu-id="e0062-175">Créez un nouveau conteneur, CONT0004.</span><span class="sxs-lookup"><span data-stu-id="e0062-175">Create a new container, CONT0004.</span></span></li><li><span data-ttu-id="e0062-176">Mettez 8 unités dans le conteneur CONT0004.</span><span class="sxs-lookup"><span data-stu-id="e0062-176">Put 8 ea into container CONT0004.</span></span></li></ol> | <p><span data-ttu-id="e0062-177">Câble HDMI 6 po :</span><span class="sxs-lookup"><span data-stu-id="e0062-177">HDMI Cable 6':</span></span></p><ol><li><span data-ttu-id="e0062-178">Vérifiez si l’article peut tenir dans le conteneur CONT0003.</span><span class="sxs-lookup"><span data-stu-id="e0062-178">Check whether the item can fit into container CONT0003.</span></span></li><li><span data-ttu-id="e0062-179">Mettez 4 unités dans le conteneur CONT0003.</span><span class="sxs-lookup"><span data-stu-id="e0062-179">Put 4 ea into container CONT0003.</span></span></li><li><span data-ttu-id="e0062-180">Créez un nouveau conteneur, CONT0004.</span><span class="sxs-lookup"><span data-stu-id="e0062-180">Create a new container, CONT0004.</span></span></li><li><span data-ttu-id="e0062-181">Mettez 9 unités dans le conteneur CONT0004.</span><span class="sxs-lookup"><span data-stu-id="e0062-181">Put 9 ea into container CONT0004.</span></span></li></ol> |

## <a name="example-scenario-pack-single-orders-per-container"></a><span data-ttu-id="e0062-182">Exemple de scénario : emballer des commandes uniques par conteneur</span><span class="sxs-lookup"><span data-stu-id="e0062-182">Example scenario: Pack single orders per container</span></span>

<span data-ttu-id="e0062-183">Cette section présente un scénario dans lequel le système est configuré pour regrouper plusieurs commandes en une seule expédition.</span><span class="sxs-lookup"><span data-stu-id="e0062-183">This section presents a scenario where the system is set up to consolidate multiple orders into one shipment.</span></span> <span data-ttu-id="e0062-184">Par conséquent, la conteneurisation sera effectuée à partir de la commande client pour garantir que chaque commande contenant plusieurs produits est emballée dans son propre conteneur.</span><span class="sxs-lookup"><span data-stu-id="e0062-184">Therefore, containerization will be done from the sales order to ensure that every order that contains multiple products is packed into its own container.</span></span>

<span data-ttu-id="e0062-185">Cette fonctionnalité vous permet de gérer des scénarios dans lesquels vous ne devez emballer qu’une seule commande client dans chaque conteneur, afin que le centre de distribution puisse transborder des conteneurs pleins entre les magasins de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="e0062-185">This functionality lets you handle scenarios where you must pack only one sales order into each container, so that the distribution center can cross-dock full containers between retail stores.</span></span> <span data-ttu-id="e0062-186">En plus des scénarios de vente au détail (commande par magasin de détail et expédition vers un centre de distribution pour le transbordement), cette technique est également couramment utilisée dans les chaînes d’approvisionnement « lean » (commande client par ligne de production juste à temps).</span><span class="sxs-lookup"><span data-stu-id="e0062-186">In addition to the retail scenarios (order per retail store and shipping to a distribution center for cross-docking) this technique is also commonly used in lean supply chains (sales order per just-in-time production line).</span></span>

<span data-ttu-id="e0062-187">Ce scénario montre comment vous pouvez réduire le nombre de conteneurs évalués lors de l’emballage en utilisant la stratégie *Conditionner dans le conteneur en cours uniquement* pour la conteneurisation.</span><span class="sxs-lookup"><span data-stu-id="e0062-187">This scenario shows how you can decrease the number of containers that are evaluated during packing by using the *Pack into current container only* strategy for containerization.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="e0062-188">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="e0062-188">Prerequisites</span></span>

#### <a name="turn-on-the-consolidate-shipments-feature-in-your-system"></a><span data-ttu-id="e0062-189">Activer la fonction Regrouper les expéditions dans votre système</span><span class="sxs-lookup"><span data-stu-id="e0062-189">Turn on the Consolidate shipments feature in your system</span></span>

<span data-ttu-id="e0062-190">Ce scénario utilise la fonctionnalité *Regrouper les expéditions*.</span><span class="sxs-lookup"><span data-stu-id="e0062-190">This scenario uses the *Consolidate shipments* feature.</span></span> <span data-ttu-id="e0062-191">Si cette fonctionnalité n’est pas déjà disponible dans votre système, vous devez l’activer en utilisant la [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e0062-191">If that feature isn't already available in your system, you must turn it on by using [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>

#### <a name="make-demo-data-available"></a><span data-ttu-id="e0062-192">Rendre les données de démonstration disponibles</span><span class="sxs-lookup"><span data-stu-id="e0062-192">Make demo data available</span></span>

<span data-ttu-id="e0062-193">Ce scénario fait référence à des valeurs et des enregistrements inclus dans les données de démonstration standard fournies pour Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e0062-193">This scenario references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="e0062-194">Pour utiliser les valeurs fournies ici lorsque vous effectuez les exercices, assurez-vous de travailler dans un environnement où les données de démonstration sont installées et définissez l’entité juridique sur **USMF** avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="e0062-194">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

### <a name="inspect-or-create-container-types"></a><span data-ttu-id="e0062-195">Inspecter ou créer des types de conteneurs</span><span class="sxs-lookup"><span data-stu-id="e0062-195">Inspect or create container types</span></span>

<span data-ttu-id="e0062-196">Pour inspecter vos types de conteneurs ou pour en créer de nouveaux au besoin, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e0062-196">To inspect your container types, or to create new container types if they are required, follow these steps.</span></span>

1. <span data-ttu-id="e0062-197">Accédez à **Gestion des entrepôts** \> **Paramétrage** \> **Conteneurs** \> **Types de conteneurs**.</span><span class="sxs-lookup"><span data-stu-id="e0062-197">Go to **Warehouse management** \> **Setup** \> **Containers** \> **Container types**.</span></span>
1. <span data-ttu-id="e0062-198">Assurez-vous que chacun des types de conteneurs suivants est disponible dans vos données de démonstration.</span><span class="sxs-lookup"><span data-stu-id="e0062-198">Make sure that each of the following container types is available in your demo data.</span></span> <span data-ttu-id="e0062-199">Modifiez ou créez des types de conteneurs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="e0062-199">Edit or create container types as required.</span></span>

    - <span data-ttu-id="e0062-200">Type de conteneur 1 :</span><span class="sxs-lookup"><span data-stu-id="e0062-200">Container type 1:</span></span>

        - <span data-ttu-id="e0062-201">**Code de type de conteneur :** *Boîte-Large*</span><span class="sxs-lookup"><span data-stu-id="e0062-201">**Container type code:** *Box-Large*</span></span>
        - <span data-ttu-id="e0062-202">**Description:** *Grande boîte*</span><span class="sxs-lookup"><span data-stu-id="e0062-202">**Description:** *Large Box*</span></span>
        - <span data-ttu-id="e0062-203">**Poids net maximal :** *100*</span><span class="sxs-lookup"><span data-stu-id="e0062-203">**Maximum net weight:** *100*</span></span>
        - <span data-ttu-id="e0062-204">**Volume :** *400*</span><span class="sxs-lookup"><span data-stu-id="e0062-204">**Volume:** *400*</span></span>
        - <span data-ttu-id="e0062-205">**Longueur :** *4*</span><span class="sxs-lookup"><span data-stu-id="e0062-205">**Length:** *4*</span></span>
        - <span data-ttu-id="e0062-206">**Largeur :** *10*</span><span class="sxs-lookup"><span data-stu-id="e0062-206">**Width:** *10*</span></span>
        - <span data-ttu-id="e0062-207">**Hauteur :** *10*</span><span class="sxs-lookup"><span data-stu-id="e0062-207">**Height:** *10*</span></span>

    - <span data-ttu-id="e0062-208">Type de conteneur 2 :</span><span class="sxs-lookup"><span data-stu-id="e0062-208">Container type 2:</span></span>

        - <span data-ttu-id="e0062-209">**Code de type de conteneur :** *Boîte-Moyenne*</span><span class="sxs-lookup"><span data-stu-id="e0062-209">**Container type code:** *Box-Medium*</span></span>
        - <span data-ttu-id="e0062-210">**Description :** *Boîte moyenne*</span><span class="sxs-lookup"><span data-stu-id="e0062-210">**Description:** *Medium Box*</span></span>
        - <span data-ttu-id="e0062-211">**Poids net maximal :** *50*</span><span class="sxs-lookup"><span data-stu-id="e0062-211">**Maximum net weight:** *50*</span></span>
        - <span data-ttu-id="e0062-212">**Volume :** *200*</span><span class="sxs-lookup"><span data-stu-id="e0062-212">**Volume:** *200*</span></span>
        - <span data-ttu-id="e0062-213">**Longueur :** *2*</span><span class="sxs-lookup"><span data-stu-id="e0062-213">**Length:** *2*</span></span>
        - <span data-ttu-id="e0062-214">**Largeur :** *10*</span><span class="sxs-lookup"><span data-stu-id="e0062-214">**Width:** *10*</span></span>
        - <span data-ttu-id="e0062-215">**Hauteur :** *10*</span><span class="sxs-lookup"><span data-stu-id="e0062-215">**Height:** *10*</span></span>

    - <span data-ttu-id="e0062-216">Type de conteneur 3 :</span><span class="sxs-lookup"><span data-stu-id="e0062-216">Container type 3:</span></span>

        - <span data-ttu-id="e0062-217">**Code de type de conteneur :** *Boîte-Petite*</span><span class="sxs-lookup"><span data-stu-id="e0062-217">**Container type code:** *Box-Small*</span></span>
        - <span data-ttu-id="e0062-218">**Description :** *Petite boîte*</span><span class="sxs-lookup"><span data-stu-id="e0062-218">**Description:** *Small Box*</span></span>
        - <span data-ttu-id="e0062-219">**Poids net maximal :** *20*</span><span class="sxs-lookup"><span data-stu-id="e0062-219">**Maximum net weight:** *20*</span></span>
        - <span data-ttu-id="e0062-220">**Volume :** *100*</span><span class="sxs-lookup"><span data-stu-id="e0062-220">**Volume:** *100*</span></span>
        - <span data-ttu-id="e0062-221">**Longueur :** *1*</span><span class="sxs-lookup"><span data-stu-id="e0062-221">**Length:** *1*</span></span>
        - <span data-ttu-id="e0062-222">**Largeur :** *10*</span><span class="sxs-lookup"><span data-stu-id="e0062-222">**Width:** *10*</span></span>
        - <span data-ttu-id="e0062-223">**Hauteur :** *10*</span><span class="sxs-lookup"><span data-stu-id="e0062-223">**Height:** *10*</span></span>

### <a name="inspect-or-create-container-groups"></a><span data-ttu-id="e0062-224">Inspecter ou créer des groupes de conteneurs</span><span class="sxs-lookup"><span data-stu-id="e0062-224">Inspect or create container groups</span></span>

<span data-ttu-id="e0062-225">Pour inspecter vos groupes de conteneurs ou pour en créer de nouveaux au besoin, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e0062-225">To inspect your container groups, or to create new container groups if they are required, follow these steps.</span></span>

1. <span data-ttu-id="e0062-226">Accédez à **Gestion des entrepôts** \> **Paramétrage** \> **Conteneurs** \> **Groupes de conteneurs**.</span><span class="sxs-lookup"><span data-stu-id="e0062-226">Go to **Warehouse management** \> **Setup** \> **Containers** \> **Container groups**.</span></span>
1. <span data-ttu-id="e0062-227">Assurez-vous que chacun des groupes de conteneurs suivants est disponible dans vos données de démonstration.</span><span class="sxs-lookup"><span data-stu-id="e0062-227">Make sure that the following container group is available in your demo data.</span></span> <span data-ttu-id="e0062-228">S’il n’est pas disponible, sélectionnez **Nouveau** pour le créer.</span><span class="sxs-lookup"><span data-stu-id="e0062-228">If it isn't available, select **New** to create it.</span></span>

    - <span data-ttu-id="e0062-229">**ID groupe de conteneurs :** *Boîtes*</span><span class="sxs-lookup"><span data-stu-id="e0062-229">**Container group ID:** *Boxes*</span></span>
    - <span data-ttu-id="e0062-230">**Description :** *Tailles de boîte*</span><span class="sxs-lookup"><span data-stu-id="e0062-230">**Description:** *Box sizes*</span></span>

1. <span data-ttu-id="e0062-231">Dans le raccourci **Détails** du groupe de conteneurs *Boîtes*, assurez-vous que les lignes suivantes existent.</span><span class="sxs-lookup"><span data-stu-id="e0062-231">On the **Details** FastTab for the *Boxes* container group, make sure that the following lines exist.</span></span> <span data-ttu-id="e0062-232">Si ce n’est pas le cas, sélectionnez **Nouveau** pour les ajouter.</span><span class="sxs-lookup"><span data-stu-id="e0062-232">If they don't, select **New** to add them.</span></span>

    - <span data-ttu-id="e0062-233">Ligne 1 :</span><span class="sxs-lookup"><span data-stu-id="e0062-233">Line 1:</span></span>

        - <span data-ttu-id="e0062-234">**Souche de N° :** *1*</span><span class="sxs-lookup"><span data-stu-id="e0062-234">**Sequence number:** *1*</span></span>
        - <span data-ttu-id="e0062-235">**Type de conteneur :** *Boîte-Large*</span><span class="sxs-lookup"><span data-stu-id="e0062-235">**Container type:** *Box-Large*</span></span>
        - <span data-ttu-id="e0062-236">**Pourcentage d’utilisation du conteneur :** *100*</span><span class="sxs-lookup"><span data-stu-id="e0062-236">**Container utilization percentage:** *100*</span></span>

    - <span data-ttu-id="e0062-237">Ligne 2 :</span><span class="sxs-lookup"><span data-stu-id="e0062-237">Line 2:</span></span>

        - <span data-ttu-id="e0062-238">**Souche de N° :** *2*</span><span class="sxs-lookup"><span data-stu-id="e0062-238">**Sequence number:** *2*</span></span>
        - <span data-ttu-id="e0062-239">**Type de conteneur :** *Boîte-Moyenne*</span><span class="sxs-lookup"><span data-stu-id="e0062-239">**Container type:** *Box-Medium*</span></span>
        - <span data-ttu-id="e0062-240">**Pourcentage d’utilisation du conteneur :** *100*</span><span class="sxs-lookup"><span data-stu-id="e0062-240">**Container utilization percentage:** *100*</span></span>

    - <span data-ttu-id="e0062-241">Ligne 3 :</span><span class="sxs-lookup"><span data-stu-id="e0062-241">Line 3:</span></span>

        - <span data-ttu-id="e0062-242">**Souche de N° :** *3*</span><span class="sxs-lookup"><span data-stu-id="e0062-242">**Sequence number:** *3*</span></span>
        - <span data-ttu-id="e0062-243">**Type de conteneur :** *Boîte-Petite*</span><span class="sxs-lookup"><span data-stu-id="e0062-243">**Container type:** *Box-Small*</span></span>
        - <span data-ttu-id="e0062-244">**Pourcentage d’utilisation du conteneur :** *100*</span><span class="sxs-lookup"><span data-stu-id="e0062-244">**Container utilization percentage:** *100*</span></span>

### <a name="create-a-new-container-build-template"></a><span data-ttu-id="e0062-245">Créer un modèle de création de conteneur</span><span class="sxs-lookup"><span data-stu-id="e0062-245">Create a new container build template</span></span>

<span data-ttu-id="e0062-246">Pour créer un modèle de création de conteneur, suivez les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="e0062-246">To create a new container build template, follow these steps.</span></span>

1. <span data-ttu-id="e0062-247">Accédez à **Gestion des entrepôts** \> **Paramétrage** \> **Conteneurs** \> **Modèles de création de conteneur**.</span><span class="sxs-lookup"><span data-stu-id="e0062-247">Go to **Warehouse management** \> **Setup** \> **Containers** \> **Container build template**.</span></span>
1. <span data-ttu-id="e0062-248">Sélectionnez **Nouveau** pour créer un modèle de ccréation de conteneur avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="e0062-248">Select **New** to create a container build template that has the following settings:</span></span>

    - <span data-ttu-id="e0062-249">**Souche de N° :** *1*</span><span class="sxs-lookup"><span data-stu-id="e0062-249">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="e0062-250">**ID modèle de conteneur :** *Boîte*</span><span class="sxs-lookup"><span data-stu-id="e0062-250">**Container template ID:** *Box*</span></span>
    - <span data-ttu-id="e0062-251">**ID groupe de conteneurs :** *Boîtes*</span><span class="sxs-lookup"><span data-stu-id="e0062-251">**Container group ID:** *Boxes*</span></span>
    - <span data-ttu-id="e0062-252">**Types de requêtes de base :** *Ligne de répartition des ventes*</span><span class="sxs-lookup"><span data-stu-id="e0062-252">**Base query types:** *Sales allocation line*</span></span>
    - <span data-ttu-id="e0062-253">**Code étape de vague :** *234*</span><span class="sxs-lookup"><span data-stu-id="e0062-253">**Wave step code:** *234*</span></span>
    - <span data-ttu-id="e0062-254">**Autoriser la répartition des prélèvements :** *Oui*</span><span class="sxs-lookup"><span data-stu-id="e0062-254">**Allow split picks:** *Yes*</span></span>
    - <span data-ttu-id="e0062-255">**Stratégie de conditionnement en conteneurs :** *Conditionner dans le conteneur en cours uniquement*</span><span class="sxs-lookup"><span data-stu-id="e0062-255">**Container packing strategy:** *Pack into current container only*</span></span>
    - <span data-ttu-id="e0062-256">**Conditionner par unité de directive :** *Non*</span><span class="sxs-lookup"><span data-stu-id="e0062-256">**Pack by directive unit:** *No*</span></span>

1. <span data-ttu-id="e0062-257">Alors que la ligne du nouveau modèle est toujours sélectionnée, sélectionnez **Modifier la requête** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="e0062-257">While the row for the new template is still selected, select **Edit query** on the Action Pane.</span></span>
1. <span data-ttu-id="e0062-258">Une boîte de dialogue d’éditeur de requête standard s’affiche.</span><span class="sxs-lookup"><span data-stu-id="e0062-258">A standard query editor dialog box appears.</span></span> <span data-ttu-id="e0062-259">Dans l’onglet **tri**, sélectionnez **Ajouter** pour ajouter une ligne ayant les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="e0062-259">On the **Sorting** tab, select **Add** to add a row that has the following settings:</span></span>

    - <span data-ttu-id="e0062-260">**Table :** *Transactions de travail temporaire*</span><span class="sxs-lookup"><span data-stu-id="e0062-260">**Table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="e0062-261">**Table dérivée :** *Transactions de travail temporaire*</span><span class="sxs-lookup"><span data-stu-id="e0062-261">**Derived table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="e0062-262">**Champ :** *Numéro de commande*</span><span class="sxs-lookup"><span data-stu-id="e0062-262">**Field:** *Order number*</span></span>
    - <span data-ttu-id="e0062-263">**Ordre de tri :** *Croissant*</span><span class="sxs-lookup"><span data-stu-id="e0062-263">**Search direction:** *Ascending*</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e0062-264">Pour éviter de parcourir tous les autres conteneurs ouverts et pour accélérer le processus en vérifiant un conteneur à la fois, utilisez la stratégie *Conditionner dans le conteneur en cours uniquement* en plus du tri par numéro de commande.</span><span class="sxs-lookup"><span data-stu-id="e0062-264">To avoid cycling over all the other open containers, and to speed up the process by checking one container at a time, use the *Pack into current container only* strategy in addition to sorting by order number.</span></span> <span data-ttu-id="e0062-265">Cette combinaison fonctionnera comme une répartition du travail dans un modèle de travail.</span><span class="sxs-lookup"><span data-stu-id="e0062-265">This combination will work like a work break on a work template.</span></span>

1. <span data-ttu-id="e0062-266">Sélectionnez **OK** pour fermer la boîte de dialogue de l’éditeur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="e0062-266">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="e0062-267">Alors que la ligne du nouveau modèle est toujours sélectionnée, sélectionnez **Contraintes de mélange en conteneur** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="e0062-267">While the row for the new template is still selected, select **Container mixing constraints** on the Action Pane.</span></span>

    <span data-ttu-id="e0062-268">Vous allez maintenant ajouter une contrainte qui place les articles d’une seule commande dans un seul conteneur.</span><span class="sxs-lookup"><span data-stu-id="e0062-268">You will now add a constraint that puts items from a single order into a single container.</span></span> <span data-ttu-id="e0062-269">Les articles de toute autre commande seront placés dans un conteneur séparé.</span><span class="sxs-lookup"><span data-stu-id="e0062-269">Items from any other order will be put into a separate container.</span></span>

1. <span data-ttu-id="e0062-270">Sélectionnez **Nouveau** pour créer une contrainte de mélange avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="e0062-270">Select **New** to create a mixing constraint that has the following settings:</span></span>

    - <span data-ttu-id="e0062-271">**Table :** *Commandes client*</span><span class="sxs-lookup"><span data-stu-id="e0062-271">**Table:** *Sales orders*</span></span>
    - <span data-ttu-id="e0062-272">**Sélection de champ :** *SalesId* (Le champ apparaîtra comme *Commande client* dans la grille.)</span><span class="sxs-lookup"><span data-stu-id="e0062-272">**Field select:** *SalesId* (The field will appear as *Sales order* in the grid.)</span></span>

1. <span data-ttu-id="e0062-273">Sélectionnez **OK** pour ajouter la contrainte.</span><span class="sxs-lookup"><span data-stu-id="e0062-273">Select **OK** to add the constraint.</span></span>
1. <span data-ttu-id="e0062-274">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e0062-274">Close the page.</span></span>

### <a name="set-up-a-wave-template-for-containerization"></a><span data-ttu-id="e0062-275">Paramétrer un modèle de vague pour la mise en conteneur</span><span class="sxs-lookup"><span data-stu-id="e0062-275">Set up a wave template for containerization</span></span>

<span data-ttu-id="e0062-276">Pour paramétrer un modèle de vague, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e0062-276">To set up a wave template, follow these steps.</span></span>

1. <span data-ttu-id="e0062-277">Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Modèles de vague**.</span><span class="sxs-lookup"><span data-stu-id="e0062-277">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="e0062-278">Dans le volet de liste, définissez le champ **Type de modèle de vague** sur *Expédition*.</span><span class="sxs-lookup"><span data-stu-id="e0062-278">In the list pane, set the **Wave template type** field to *Shipping*.</span></span>
1. <span data-ttu-id="e0062-279">Sélectionnez le modèle **Conteneurisation 63** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e0062-279">Select the **63 Containerization** template in the list.</span></span>
1. <span data-ttu-id="e0062-280">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="e0062-280">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="e0062-281">Sur l’organisateur **Méthodes**, dans la colonne **Méthodes sélectionnées**, recherchez la ligne suivante :</span><span class="sxs-lookup"><span data-stu-id="e0062-281">On the **Methods** FastTab, in the **Selected methods** column, find the following line:</span></span>

    - <span data-ttu-id="e0062-282">**Nom de la méthode :** *conteneurisation*</span><span class="sxs-lookup"><span data-stu-id="e0062-282">**Method name:** *containerization*</span></span>
    - <span data-ttu-id="e0062-283">**Nom :** *Conteneurisation*</span><span class="sxs-lookup"><span data-stu-id="e0062-283">**Name:** *Containerization*</span></span>

1. <span data-ttu-id="e0062-284">Définissez le champ **Code d’étape de vague** pour la ligne sur *234*.</span><span class="sxs-lookup"><span data-stu-id="e0062-284">Set the **Wave step code** field for the line to *234*.</span></span>

### <a name="set-up-a-work-template"></a><span data-ttu-id="e0062-285">Définir un modèle de travail</span><span class="sxs-lookup"><span data-stu-id="e0062-285">Set up a work template</span></span>

<span data-ttu-id="e0062-286">Pour paramétrer un modèle de travail, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e0062-286">To set up a work template, follow these steps.</span></span>

1. <span data-ttu-id="e0062-287">Allez dans **Gestion des entrepôts \> Paramétrage \> Travail \> Modèles de travail**.</span><span class="sxs-lookup"><span data-stu-id="e0062-287">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="e0062-288">Définissez le champ **Type d’ordre de travail** sur *Commandes client*.</span><span class="sxs-lookup"><span data-stu-id="e0062-288">Set the **Work order type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="e0062-289">Dans la grille **Vue d’ensemble**, recherchez et sélectionnez le modèle de travail à utiliser pour conditionner les commandes uniques par conteneur.</span><span class="sxs-lookup"><span data-stu-id="e0062-289">In the **Overview** grid, find and select the work template that should be used for packing single orders per container.</span></span> <span data-ttu-id="e0062-290">Pour ce scénario, sélectionnez le modèle **63 Prélever vers le conteneur**.</span><span class="sxs-lookup"><span data-stu-id="e0062-290">For this scenario, select the **63 Pick to container** template.</span></span>
1. <span data-ttu-id="e0062-291">Dans le volet Actions, sélectionnez **Modifier une requête**.</span><span class="sxs-lookup"><span data-stu-id="e0062-291">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="e0062-292">Une boîte de dialogue d’éditeur de requête standard s’affiche.</span><span class="sxs-lookup"><span data-stu-id="e0062-292">A standard query editor dialog box appears.</span></span> <span data-ttu-id="e0062-293">Sous l’onglet **Tri**, ajoutez les ligne suivantes :</span><span class="sxs-lookup"><span data-stu-id="e0062-293">On the **Sorting** tab, add the following lines:</span></span>

    - <span data-ttu-id="e0062-294">Ligne 1 :</span><span class="sxs-lookup"><span data-stu-id="e0062-294">Line 1:</span></span>

        - <span data-ttu-id="e0062-295">**Table :** *Transactions de travail temporaire*</span><span class="sxs-lookup"><span data-stu-id="e0062-295">**Table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="e0062-296">**Table dérivée :** *Transactions de travail temporaire*</span><span class="sxs-lookup"><span data-stu-id="e0062-296">**Derived table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="e0062-297">**Champ :** *ID expédition*</span><span class="sxs-lookup"><span data-stu-id="e0062-297">**Field:** *Shipment ID*</span></span>
        - <span data-ttu-id="e0062-298">**Ordre de tri :** *Croissant*</span><span class="sxs-lookup"><span data-stu-id="e0062-298">**Search direction:** *Ascending*</span></span>

    - <span data-ttu-id="e0062-299">Ligne 2 :</span><span class="sxs-lookup"><span data-stu-id="e0062-299">Line 2:</span></span>

        - <span data-ttu-id="e0062-300">**Table :** *Transactions de travail temporaire*</span><span class="sxs-lookup"><span data-stu-id="e0062-300">**Table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="e0062-301">**Table dérivée :** *Transactions de travail temporaire*</span><span class="sxs-lookup"><span data-stu-id="e0062-301">**Derived table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="e0062-302">**Champ :** *Numéro de commande*</span><span class="sxs-lookup"><span data-stu-id="e0062-302">**Field:** *Order number*</span></span>
        - <span data-ttu-id="e0062-303">**Ordre de tri :** *Croissant*</span><span class="sxs-lookup"><span data-stu-id="e0062-303">**Search direction:** *Ascending*</span></span>

    - <span data-ttu-id="e0062-304">Ligne 3 :</span><span class="sxs-lookup"><span data-stu-id="e0062-304">Line 3:</span></span>

        - <span data-ttu-id="e0062-305">**Table :** *Transactions de travail temporaire*</span><span class="sxs-lookup"><span data-stu-id="e0062-305">**Table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="e0062-306">**Table dérivée :** *Transactions de travail temporaire*</span><span class="sxs-lookup"><span data-stu-id="e0062-306">**Derived table:** *Temporary work transactions*</span></span>
        - <span data-ttu-id="e0062-307">**Champ :** *ID conteneur*</span><span class="sxs-lookup"><span data-stu-id="e0062-307">**Field:** *Container ID*</span></span>
        - <span data-ttu-id="e0062-308">**Ordre de tri :** *Croissant*</span><span class="sxs-lookup"><span data-stu-id="e0062-308">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="e0062-309">Sélectionnez **OK** pour fermer la boîte de dialogue de l’éditeur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="e0062-309">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="e0062-310">Le message suivant s’affiche : « Le regroupement sera réinitialisé, continuer ? »</span><span class="sxs-lookup"><span data-stu-id="e0062-310">You receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="e0062-311">Sélectionnez **Oui** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="e0062-311">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="e0062-312">Tandis que le modèle **63 Prélever vers le conteneur** est toujours sélectionné, sélectionnez **Décompositions de l’en-tête de travail** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="e0062-312">While the **63 Pick to container** template is still selected, select **Work header breaks** on the Action Pane.</span></span>

    <span data-ttu-id="e0062-313">Vous allez maintenant appliquer des paramètres pour décomposer le travail de sorte que chaque conteneur de la commande soit lié à un seul ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="e0062-313">You will now apply settings to break the work so that each container in the order is linked to one work order.</span></span>

1. <span data-ttu-id="e0062-314">Sélectionnez la case à cocher **Regrouper par ce champ** pour chaque ligne de la page **Décompositions de l’en-tête de travail** (**ID expédition**, **Numéro de commande** et **ID conteneur**).</span><span class="sxs-lookup"><span data-stu-id="e0062-314">Select the **Group by this field** checkbox for each row on the **Work header breaks** page (**Shipment ID**, **Order number**, and **Container ID**).</span></span>
1. <span data-ttu-id="e0062-315">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e0062-315">Close the page.</span></span>

### <a name="set-up-shipment-consolidation-policies"></a><span data-ttu-id="e0062-316">Configurer des stratégies de regroupement des expéditions</span><span class="sxs-lookup"><span data-stu-id="e0062-316">Set up shipment consolidation policies</span></span>

<span data-ttu-id="e0062-317">Pour configurer une stratégie de regroupement des expéditions, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e0062-317">To set up a shipment consolidation policy, follow these steps.</span></span>

1. <span data-ttu-id="e0062-318">Allez dans **Gestion des entrepôts \> Configuration \> Lancement dans l’entrepôt \> Stratégies de consolidation de l’expédition**.</span><span class="sxs-lookup"><span data-stu-id="e0062-318">Go to **Warehouse management \> Setup \> Release to warehouse \> Shipment consolidation policies**.</span></span>
1. <span data-ttu-id="e0062-319">Dans le volet de liste, définissez le champ **Type de stratégie** sur *Commandes client*.</span><span class="sxs-lookup"><span data-stu-id="e0062-319">In the list pane, set the **Policy type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="e0062-320">Sélectionnez la stratégie **Par défaut** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e0062-320">Select the **Default** policy in the list.</span></span>
1. <span data-ttu-id="e0062-321">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="e0062-321">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="e0062-322">Dans le raccourci **Champs de regroupement**, dans la liste **Champs sélectionnés**, sélectionnez la ligne où **Nom de champ** est défini sur *Numéro de commande*.</span><span class="sxs-lookup"><span data-stu-id="e0062-322">On the **Consolidation fields** FastTab, in the **Selected fields** list, select the row where the **Field name** field is set to *Order number*.</span></span>
1. <span data-ttu-id="e0062-323">Sélectionnez le bouton **Retirer** ![Flèche gauche](media/backward-button.png) pour déplacer le champ vers la liste **Champs restants**.</span><span class="sxs-lookup"><span data-stu-id="e0062-323">Select the **Remove** button ![Left arrow](media/backward-button.png) to move the field to the **Remaining fields** list.</span></span>
1. <span data-ttu-id="e0062-324">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e0062-324">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-physical-dimensions-for-the-product"></a><span data-ttu-id="e0062-325">Configurer les dimensions physiques du produit</span><span class="sxs-lookup"><span data-stu-id="e0062-325">Set up physical dimensions for the product</span></span>

<span data-ttu-id="e0062-326">Pour configurer les dimensions physiques des produits qui seront utilisés dans ce scénario, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e0062-326">To set up physical dimensions for the products that will be used in this scenario, follow these steps.</span></span>

1. <span data-ttu-id="e0062-327">Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="e0062-327">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="e0062-328">Sélectionnez le produit dont le champ **Numéro d’article** est défini sur *A0001*.</span><span class="sxs-lookup"><span data-stu-id="e0062-328">Select the product where the **Item number** field is set to *A0001*.</span></span>
1. <span data-ttu-id="e0062-329">Dans le volet Action,s dans l’onglet **Gérer le stock**, dans le groupe **Entrepôt**, sélectionnez **Dimensions physiques**.</span><span class="sxs-lookup"><span data-stu-id="e0062-329">On the Action Pane, on the **Manage inventory** tab, in the **Warehouse** group, select **Physical dimensions**.</span></span>
1. <span data-ttu-id="e0062-330">Sur la page **Dimensions physiques**, vous devriez voir la ligne suivante dans la grille :</span><span class="sxs-lookup"><span data-stu-id="e0062-330">On the **Physical dimensions** page, you should see the following line in the grid:</span></span>

    - <span data-ttu-id="e0062-331">**Unité :** *pièces*</span><span class="sxs-lookup"><span data-stu-id="e0062-331">**Unit:** *pcs*</span></span>
    - <span data-ttu-id="e0062-332">**Poids brut :** *3,00*</span><span class="sxs-lookup"><span data-stu-id="e0062-332">**Gross weight:** *3.00*</span></span>
    - <span data-ttu-id="e0062-333">**Largeur :** *2,00*</span><span class="sxs-lookup"><span data-stu-id="e0062-333">**Width:** *2.00*</span></span>
    - <span data-ttu-id="e0062-334">**Profondeur :** *2,00*</span><span class="sxs-lookup"><span data-stu-id="e0062-334">**Depth:** *2.00*</span></span>
    - <span data-ttu-id="e0062-335">**Hauteur :** *4,00*</span><span class="sxs-lookup"><span data-stu-id="e0062-335">**Height:** *4.00*</span></span>
    - <span data-ttu-id="e0062-336">**Volume :** *16,00*</span><span class="sxs-lookup"><span data-stu-id="e0062-336">**Volume:** *16.00*</span></span>

1. <span data-ttu-id="e0062-337">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e0062-337">Close the page.</span></span>
1. <span data-ttu-id="e0062-338">Sélectionnez le produit dont le champ **Numéro d’article** est défini sur *A0002*.</span><span class="sxs-lookup"><span data-stu-id="e0062-338">Select the product where the **Item number** field is set to *A0002*.</span></span>
1. <span data-ttu-id="e0062-339">Dans le volet Action,s dans l’onglet **Gérer le stock**, dans le groupe **Entrepôt**, sélectionnez **Dimensions physiques**.</span><span class="sxs-lookup"><span data-stu-id="e0062-339">On the Action Pane, on the **Manage inventory** tab, in the **Warehouse** group, select **Physical dimensions**.</span></span>
1. <span data-ttu-id="e0062-340">Sur la page **Dimensions physiques**, vous devriez voir la ligne suivante dans la grille :</span><span class="sxs-lookup"><span data-stu-id="e0062-340">On the **Physical dimensions** page, you should see the following line in the grid:</span></span>

    - <span data-ttu-id="e0062-341">**Unité :** *pièces*</span><span class="sxs-lookup"><span data-stu-id="e0062-341">**Unit:** *pcs*</span></span>
    - <span data-ttu-id="e0062-342">**Poids brut :** *4,00*</span><span class="sxs-lookup"><span data-stu-id="e0062-342">**Gross weight:** *4.00*</span></span>
    - <span data-ttu-id="e0062-343">**Largeur :** *3,00*</span><span class="sxs-lookup"><span data-stu-id="e0062-343">**Width:** *3.00*</span></span>
    - <span data-ttu-id="e0062-344">**Profondeur :** *1,00*</span><span class="sxs-lookup"><span data-stu-id="e0062-344">**Depth:** *1.00*</span></span>
    - <span data-ttu-id="e0062-345">**Hauteur :** *3,00*</span><span class="sxs-lookup"><span data-stu-id="e0062-345">**Height:** *3.00*</span></span>
    - <span data-ttu-id="e0062-346">**Volume :** *9,00*</span><span class="sxs-lookup"><span data-stu-id="e0062-346">**Volume:** *9.00*</span></span>

### <a name="create-sales-order-1"></a><span data-ttu-id="e0062-347">Créer une commande client 1</span><span class="sxs-lookup"><span data-stu-id="e0062-347">Create sales order 1</span></span>

<span data-ttu-id="e0062-348">Pour créer une commande vente, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e0062-348">To create a sales order, follow these steps.</span></span>

1. <span data-ttu-id="e0062-349">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="e0062-349">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="e0062-350">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e0062-350">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="e0062-351">Une boîte de dialogue de création d’une nouvelle commande client apparaît.</span><span class="sxs-lookup"><span data-stu-id="e0062-351">A dialog box for creating a new sales order appears.</span></span> <span data-ttu-id="e0062-352">Définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e0062-352">Set the following values:</span></span>

    - <span data-ttu-id="e0062-353">**Compte client :** *US-001*</span><span class="sxs-lookup"><span data-stu-id="e0062-353">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="e0062-354">**Entrepôt :** *63*</span><span class="sxs-lookup"><span data-stu-id="e0062-354">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="e0062-355">Sélectionnez **OK** pour créer la commande client et fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e0062-355">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="e0062-356">La nouvelle commande client est ouverte.</span><span class="sxs-lookup"><span data-stu-id="e0062-356">The new sales order is opened.</span></span> <span data-ttu-id="e0062-357">Dans le raccourci **Lignes de commande client**, ajoutez les lignes de vente +suivantes :</span><span class="sxs-lookup"><span data-stu-id="e0062-357">On the **Sales order lines** FastTab, add the following sales lines:</span></span>

    - <span data-ttu-id="e0062-358">Ligne 1 :</span><span class="sxs-lookup"><span data-stu-id="e0062-358">Line 1:</span></span>

        - <span data-ttu-id="e0062-359">**Numéro d’article :** *A0001*</span><span class="sxs-lookup"><span data-stu-id="e0062-359">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="e0062-360">**Quantité :** *2*</span><span class="sxs-lookup"><span data-stu-id="e0062-360">**Quantity:** *2*</span></span>

    - <span data-ttu-id="e0062-361">Ligne 2 :</span><span class="sxs-lookup"><span data-stu-id="e0062-361">Line 2:</span></span>

        - <span data-ttu-id="e0062-362">**Numéro d’article :** *A0002*</span><span class="sxs-lookup"><span data-stu-id="e0062-362">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="e0062-363">**Quantité :** *2*</span><span class="sxs-lookup"><span data-stu-id="e0062-363">**Quantity:** *2*</span></span>

1. <span data-ttu-id="e0062-364">Sélectionnez la première ligne, puis sélectionnez **Stock \> Réservation**.</span><span class="sxs-lookup"><span data-stu-id="e0062-364">Select the first line, and then select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="e0062-365">Sur la page **Réservation**, sélectionnez **Réserver un lot**.</span><span class="sxs-lookup"><span data-stu-id="e0062-365">On the **Reservation** page, select **Reserve lot**.</span></span> <span data-ttu-id="e0062-366">Fermez ensuite la page.</span><span class="sxs-lookup"><span data-stu-id="e0062-366">Then close the page.</span></span>
1. <span data-ttu-id="e0062-367">Répétez les deux étapes précédentes pour la deuxième ligne.</span><span class="sxs-lookup"><span data-stu-id="e0062-367">Repeat the previous two steps for the second line.</span></span>
1. <span data-ttu-id="e0062-368">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e0062-368">Close the page.</span></span>

### <a name="create-sales-order-2"></a><span data-ttu-id="e0062-369">Créer une commande client 2</span><span class="sxs-lookup"><span data-stu-id="e0062-369">Create sales order 2</span></span>

<span data-ttu-id="e0062-370">Procédez comme suit pour créer une deuxième commande client.</span><span class="sxs-lookup"><span data-stu-id="e0062-370">To create a second sales order, follow these steps.</span></span>

1. <span data-ttu-id="e0062-371">Accédez à **Ventes et marketing \> Commandes client \> Toutes les commandes client**.</span><span class="sxs-lookup"><span data-stu-id="e0062-371">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="e0062-372">Dans le volet Actions, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e0062-372">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="e0062-373">Une boîte de dialogue de création d’une nouvelle commande client apparaît.</span><span class="sxs-lookup"><span data-stu-id="e0062-373">A dialog box for creating a new sales order appears.</span></span> <span data-ttu-id="e0062-374">Définissez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e0062-374">Set the following values:</span></span>

    - <span data-ttu-id="e0062-375">**Compte client :** *US-001*</span><span class="sxs-lookup"><span data-stu-id="e0062-375">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="e0062-376">**Entrepôt :** *63*</span><span class="sxs-lookup"><span data-stu-id="e0062-376">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="e0062-377">Sélectionnez **OK** pour créer la commande client et fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e0062-377">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="e0062-378">La nouvelle commande client est ouverte.</span><span class="sxs-lookup"><span data-stu-id="e0062-378">The new sales order is opened.</span></span> <span data-ttu-id="e0062-379">Dans le raccourci **Lignes de commande client**, ajoutez les lignes de vente +suivantes :</span><span class="sxs-lookup"><span data-stu-id="e0062-379">On the **Sales order lines** FastTab, add the following sales lines:</span></span>

    - <span data-ttu-id="e0062-380">Ligne 1 :</span><span class="sxs-lookup"><span data-stu-id="e0062-380">Line 1:</span></span>

        - <span data-ttu-id="e0062-381">**Numéro d’article :** *A0001*</span><span class="sxs-lookup"><span data-stu-id="e0062-381">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="e0062-382">**Quantité :** *4*</span><span class="sxs-lookup"><span data-stu-id="e0062-382">**Quantity:** *4*</span></span>

    - <span data-ttu-id="e0062-383">Ligne 2 :</span><span class="sxs-lookup"><span data-stu-id="e0062-383">Line 2:</span></span>

        - <span data-ttu-id="e0062-384">**Numéro d’article :** *A0002*</span><span class="sxs-lookup"><span data-stu-id="e0062-384">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="e0062-385">**Quantité :** *4*</span><span class="sxs-lookup"><span data-stu-id="e0062-385">**Quantity:** *4*</span></span>

1. <span data-ttu-id="e0062-386">Sélectionnez la première ligne, puis sélectionnez **Stock \> Réservation**.</span><span class="sxs-lookup"><span data-stu-id="e0062-386">Select the first line, and then select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="e0062-387">Sur la page **Réservation**, sélectionnez **Réserver un lot**.</span><span class="sxs-lookup"><span data-stu-id="e0062-387">On the **Reservation** page, select **Reserve lot**.</span></span> <span data-ttu-id="e0062-388">Fermez ensuite la page.</span><span class="sxs-lookup"><span data-stu-id="e0062-388">Then close the page.</span></span>
1. <span data-ttu-id="e0062-389">Répétez les deux étapes précédentes pour la deuxième ligne.</span><span class="sxs-lookup"><span data-stu-id="e0062-389">Repeat the previous two steps for the second line.</span></span>
1. <span data-ttu-id="e0062-390">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e0062-390">Close the page.</span></span>

### <a name="create-the-load"></a><span data-ttu-id="e0062-391">Créer le chargement</span><span class="sxs-lookup"><span data-stu-id="e0062-391">Create the load</span></span>

<span data-ttu-id="e0062-392">Pour créer un chargement pour chaque commande que vous avez créée pour ce scénario, puis le lancer dans l’entrepôt, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e0062-392">To create a load for each order that you created for this scenario and then release it to the warehouse, follow these steps.</span></span>

1. <span data-ttu-id="e0062-393">Allez dans **Gestion des entrepôts \> Chargements \> Atelier de planification des chargements**.</span><span class="sxs-lookup"><span data-stu-id="e0062-393">Go to **Warehouse management \> Loads \> Load planning workbench**.</span></span>
1. <span data-ttu-id="e0062-394">Sur l’onglet **Lignes de vente**, recherchez et sélectionnez toutes les lignes de commande client des commandes client que vous avez créées pour ce scénario.</span><span class="sxs-lookup"><span data-stu-id="e0062-394">On the **Sales lines** tab, find and select all the sales order lines from the sales orders that you created for this scenario.</span></span>
1. <span data-ttu-id="e0062-395">Dans le volet Actions, sous l’onglet **Approvisionnement et demande**, dans le groupe **Ajouter**, sélectionnez **Dans un nouveau chargement**.</span><span class="sxs-lookup"><span data-stu-id="e0062-395">On the Action Pane, on the **Supply and demand** tab, in the **Add** group, select **To new load**.</span></span> <span data-ttu-id="e0062-396">Les lignes de commande sélectionnées sont ajoutées à un nouveau chargement.</span><span class="sxs-lookup"><span data-stu-id="e0062-396">The selected order lines are added to a new load.</span></span>
1. <span data-ttu-id="e0062-397">Dans la boîte de dialogue **Affectation des modèles de chargement**, dans le champ **ID du modèle de chargement**, sélectionnez un modèle de chargement, tel que *Conteneur 40 po*.</span><span class="sxs-lookup"><span data-stu-id="e0062-397">In the **Load template assignment** dialog box, in the **Load template ID** field, select a load template, such as *40' Container*.</span></span>
1. <span data-ttu-id="e0062-398">Sélectionnez **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e0062-398">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="e0062-399">Dans la section **Chargements**, recherchez et sélectionnez le chargement que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="e0062-399">In the **Loads** section, find and select the load that you just created.</span></span>
1. <span data-ttu-id="e0062-400">Sélectionnez **Lancer \> Lancement dans l’entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="e0062-400">Select **Release \> Release to warehouse**.</span></span>
1. <span data-ttu-id="e0062-401">Dans la boîte de dialogue **Lancement dans l’entrepôt**, sélectionnez **OK** pour lancer le chargement sélectionné dans l’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="e0062-401">In the **Release to warehouse** dialog box, select **OK** to release the selected load to the warehouse.</span></span>

### <a name="verify-the-shipments-and-containers"></a><span data-ttu-id="e0062-402">Vérifier les expéditions et les conteneurs</span><span class="sxs-lookup"><span data-stu-id="e0062-402">Verify the shipments and containers</span></span>

<span data-ttu-id="e0062-403">La procédure suivante vous permet de vérifier les expéditions qui ont été créées.</span><span class="sxs-lookup"><span data-stu-id="e0062-403">The following procedure lets you verify the shipments that have been created.</span></span> <span data-ttu-id="e0062-404">Utilisez-la pour examiner la commande que vous avez créée pour ce scénario, afin de vous assurer que vous avez obtenu les résultats attendus.</span><span class="sxs-lookup"><span data-stu-id="e0062-404">Use it to review the order that you created for this scenario, to make sure that you've obtained the expected results.</span></span>

1. <span data-ttu-id="e0062-405">Allez dans **Gestion des entrepôts \> Expéditions \> Toutes les expéditions**.</span><span class="sxs-lookup"><span data-stu-id="e0062-405">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="e0062-406">Recherchez et sélectionnez l’expédition qui a été créée pour le chargement que vous venez de lancer.</span><span class="sxs-lookup"><span data-stu-id="e0062-406">Find and select the shipment that was created for the load that you just released.</span></span>
1. <span data-ttu-id="e0062-407">Dans le volet Actions, dans l’onglet **Transport**, sélectionnez **Afficher les conteneurs**.</span><span class="sxs-lookup"><span data-stu-id="e0062-407">On the Action Pane, on the **Transportation** tab, select **View containers**.</span></span>
1. <span data-ttu-id="e0062-408">Vérifiez que les articles des commandes clients ont été conteneurisés dans deux conteneurs différents.</span><span class="sxs-lookup"><span data-stu-id="e0062-408">Confirm that the items from the sales orders were containerized into two different containers.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e0062-409">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e0062-409">Additional resources</span></span>

- [<span data-ttu-id="e0062-410">Mise en conteneur</span><span class="sxs-lookup"><span data-stu-id="e0062-410">Containerization</span></span>](wave-containerization.md)
