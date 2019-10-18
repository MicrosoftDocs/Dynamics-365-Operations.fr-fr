---
title: Paramétrer le prélèvement de groupement
description: Cette rubrique décrit la procédure de paramétrage du prélèvement de groupement et comment appliquer la confirmation d'article avec le prélèvement de groupement.
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSClusterProfile, WHSRFAutoConfirm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 84b6d3c3caa09b9601701ca4ac1992b151c0b8d4
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249748"
---
[!include[banner](../includes/banner.md)]

# <a name="set-up-cluster-picking"></a><span data-ttu-id="04c74-103">Paramétrer le prélèvement de groupement</span><span class="sxs-lookup"><span data-stu-id="04c74-103">Set up cluster picking</span></span>

<span data-ttu-id="04c74-104">Cette rubrique décrit comment permettre aux collaborateurs d'utiliser leurs appareils mobiles pour regrouper les travaux de prélèvement en groupements, afin de pouvoir prélever des articles depuis un même emplacement pour plusieurs ordres de fabrication simultanément.</span><span class="sxs-lookup"><span data-stu-id="04c74-104">This topic describes how to enable workers to use their mobile devices to group picking work into clusters, so that they can pick items from a single location for multiple work orders at the same time.</span></span> <span data-ttu-id="04c74-105">On parle alors de *prélèvement de groupement*.</span><span class="sxs-lookup"><span data-stu-id="04c74-105">This is called *cluster picking*.</span></span>

## <a name="about-cluster-picking"></a><span data-ttu-id="04c74-106">À propos du prélèvement de groupement</span><span class="sxs-lookup"><span data-stu-id="04c74-106">About cluster picking</span></span>

<span data-ttu-id="04c74-107">Une fois les ordres de fabrication lancés dans l'entrepôt, le collaborateur peut utiliser un appareil mobile pour affecter les ordres à un groupement.</span><span class="sxs-lookup"><span data-stu-id="04c74-107">After work orders are released to the warehouse, the worker can use a mobile device to assign the orders to a cluster.</span></span> <span data-ttu-id="04c74-108">Le groupement organisera le travail de prélèvement pour le collaborateur.</span><span class="sxs-lookup"><span data-stu-id="04c74-108">The cluster will organize the picking work for the worker.</span></span> <span data-ttu-id="04c74-109">Lorsqu'un ordre de fabrication est affecté à un groupement, le collaborateur doit utiliser le prélèvement de groupement pour effectuer le travail de prélèvement pour l'ordre.</span><span class="sxs-lookup"><span data-stu-id="04c74-109">When a work order is assigned to a cluster, the worker must use cluster picking to perform the picking work for the order.</span></span> <span data-ttu-id="04c74-110">Le collaborateur ne peut pas utiliser d'autres méthodes de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="04c74-110">The worker cannot use other picking methods.</span></span> <span data-ttu-id="04c74-111">Si un ordre de fabrication est affecté à un groupement par erreur, le collaborateur doit rompre le groupement et le recréer.</span><span class="sxs-lookup"><span data-stu-id="04c74-111">If a work order is assigned to a cluster by mistake, the worker must break the cluster and then re-create it.</span></span>

<span data-ttu-id="04c74-112">Si nécessaire, un collaborateur peut transmettre un groupement à un autre collaborateur.</span><span class="sxs-lookup"><span data-stu-id="04c74-112">If needed, a worker can pass a cluster to another worker.</span></span> <span data-ttu-id="04c74-113">Le statut du groupement devient alors Transmis.</span><span class="sxs-lookup"><span data-stu-id="04c74-113">This changes the cluster status to Passed.</span></span> <span data-ttu-id="04c74-114">Lorsque le collaborateur utilise un appareil mobile pour indiquer que le travail de prélèvement et de rangement est terminé, l'expédition ou le chargement doit être confirmé dans le client.</span><span class="sxs-lookup"><span data-stu-id="04c74-114">When the worker uses a mobile device to indicate that the picking and put away work is completed, the shipment or load must be confirmed in the client.</span></span>

## <a name="set-up-cluster-picking"></a><span data-ttu-id="04c74-115">Paramétrer le prélèvement du groupement</span><span class="sxs-lookup"><span data-stu-id="04c74-115">Set up cluster picking</span></span>

<span data-ttu-id="04c74-116">Pour activer le prélèvement de groupement, vous devez paramétrer les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="04c74-116">To enable cluster picking, you must set up the following:</span></span>

-   <span data-ttu-id="04c74-117">**Profils de groupement** – Permet de spécifier si les ID groupement sont générés automatiquement, le nombre de postes à utiliser, quand rompre les groupements, et comment séquencer et vérifier le travail de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="04c74-117">**Cluster profiles** – Specify whether to automatically generate cluster IDs, the number of positions to use, when to break clusters, and how to sequence and verify the picking work.</span></span>

-   <span data-ttu-id="04c74-118">**Modèles de travail** – Permet de définir comment créer le travail de prélèvement pour le prélèvement de groupement.</span><span class="sxs-lookup"><span data-stu-id="04c74-118">**Work templates** – Define how to create the picking work for cluster picking.</span></span>

-   <span data-ttu-id="04c74-119">**Instructions d'emplacement** – Permet de spécifier où prélever les articles, et où les ranger.</span><span class="sxs-lookup"><span data-stu-id="04c74-119">**Location directives** – Specify where to pick items from, and where to put them.</span></span>

-   <span data-ttu-id="04c74-120">**Options de menu d'appareil mobile** – Permet de configurer une option de menu d'appareil mobile pour utiliser le travail existant qui est dirigé par le prélèvement de groupement.</span><span class="sxs-lookup"><span data-stu-id="04c74-120">**Mobile device menu items** – Configure a mobile device menu item to use existing work that is directed by cluster picking.</span></span> <span data-ttu-id="04c74-121">Vous devez ensuite ajouter l'option de menu à un menu d'appareil mobile afin qu'il soit affiché sur les appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="04c74-121">You must then add the menu item to a mobile device menu so that it is displayed on mobile devices.</span></span>

-   <span data-ttu-id="04c74-122">**Paramètres de gestion des entrepôts** – Permet de spécifier la souche de numéros à utiliser si vous souhaitez générer des identificateurs pour les groupements.</span><span class="sxs-lookup"><span data-stu-id="04c74-122">**Warehouse management parameters** – Specify the number sequence to use if you want to generate identifiers for clusters.</span></span>

## <a name="set-up-a-cluster-profile"></a><span data-ttu-id="04c74-123">Paramétrer un profil de groupement</span><span class="sxs-lookup"><span data-stu-id="04c74-123">Set up a cluster profile</span></span>

<span data-ttu-id="04c74-124">Pour paramétrer un profil de groupement, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="04c74-124">To set up a cluster profile, follow these steps:</span></span>

1.  <span data-ttu-id="04c74-125">Cliquez sur **Gestion des entrepôts** \> **Paramétrage** \> **Appareil mobile** \> **Profils de groupement**.</span><span class="sxs-lookup"><span data-stu-id="04c74-125">Click **Warehouse management** \> **Setup** \> **Mobile device** \> **Cluster profiles**.</span></span>

2.  <span data-ttu-id="04c74-126">Cliquez sur **Nouveau** pour créer un profil.</span><span class="sxs-lookup"><span data-stu-id="04c74-126">Click **New** to create a new profile.</span></span>

3.  <span data-ttu-id="04c74-127">Cliquez sur **Créer un groupement** et, sous **Tri de groupement**, cliquez sur **Nouveau** pour paramétrer les critères de tri du groupement.</span><span class="sxs-lookup"><span data-stu-id="04c74-127">Click **Create cluster** and, under **Cluster sorting**, click **New** to set up the sorting criteria for the cluster.</span></span> <span data-ttu-id="04c74-128">Les critères de tri contrôlent l'ordre dans lequel le collaborateur réalisera le travail de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="04c74-128">The sorting criteria control the order in which the worker will perform the picking work.</span></span> <span data-ttu-id="04c74-129">Vous pouvez ajouter autant de critères que nécessaire.</span><span class="sxs-lookup"><span data-stu-id="04c74-129">You can add as many criteria as needed.</span></span>

4.  <span data-ttu-id="04c74-130">Dans le champ **Souche de N°**, entrez un nombre pour définir l'ordre dans lequel les critères de tri sont traités.</span><span class="sxs-lookup"><span data-stu-id="04c74-130">In the **Sequence number** field, enter a number to define the order in which the sorting criteria are processed.</span></span>

5.  <span data-ttu-id="04c74-131">Dans le champ **Nom de champ**, sélectionnez le champ qui déterminera le tri.</span><span class="sxs-lookup"><span data-stu-id="04c74-131">In the **Field name** field, select the field that will determine the sorting.</span></span> <span data-ttu-id="04c74-132">Par exemple, si vous sélectionnez le champ **WMSLocationId**, le travail sera trié par emplacement.</span><span class="sxs-lookup"><span data-stu-id="04c74-132">For example, if you select the **WMSLocationId** field, the work will be sorted by location.</span></span>

6.  <span data-ttu-id="04c74-133">Dans le champ **Tri**, sélectionnez l'une des options suivantes.</span><span class="sxs-lookup"><span data-stu-id="04c74-133">In the **Sorting** field, select one of the following options.</span></span>

| <span data-ttu-id="04c74-134">**Option**</span><span class="sxs-lookup"><span data-stu-id="04c74-134">**Option**</span></span>     | <span data-ttu-id="04c74-135">**Description**</span><span class="sxs-lookup"><span data-stu-id="04c74-135">**Description**</span></span>                                                                                                                                                                                                                    |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="04c74-136">**Croissant**</span><span class="sxs-lookup"><span data-stu-id="04c74-136">**Ascending**</span></span>  | <span data-ttu-id="04c74-137">Le travail de prélèvement est séquencé dans l'ordre croissant sur la base des critères de tri.</span><span class="sxs-lookup"><span data-stu-id="04c74-137">Picking work is sequenced in ascending order based on the sorting criteria.</span></span> <span data-ttu-id="04c74-138">Par exemple, si vous utilisez le champ **WMSLocationId** comme critères de tri, et que les ID d'emplacement sont 1, 2, 3, et 4, vous prélèverez depuis l'emplacement 4 en premier.</span><span class="sxs-lookup"><span data-stu-id="04c74-138">For example, if you use the **WMSLocationId** field as sorting criteria, and your location IDs are 1, 2, 3, and 4, you will pick from location 4 first.</span></span> |
| <span data-ttu-id="04c74-139">**Décroissant**</span><span class="sxs-lookup"><span data-stu-id="04c74-139">**Descending**</span></span> | <span data-ttu-id="04c74-140">Le travail de prélèvement est séquencé dans l'ordre décroissant sur la base des critères de tri.</span><span class="sxs-lookup"><span data-stu-id="04c74-140">Picking work is sequenced in descending order based on the sorting criteria.</span></span> <span data-ttu-id="04c74-141">Par exemple, si vous utilisez le champ **WMSLocationId** comme critères de tri, et que les ID d'emplacement sont 1, 2, 3, et 4, vous prélèverez depuis l'emplacement 1 en premier.</span><span class="sxs-lookup"><span data-stu-id="04c74-141">For example, if you use the **WMSLocationId** field as sorting criteria, and your location IDs are 1, 2, 3, and 4, you will pick from location 1 first.</span></span> |

## <a name="item-confirmation"></a><span data-ttu-id="04c74-142">Confirmation d'article</span><span class="sxs-lookup"><span data-stu-id="04c74-142">Item confirmation</span></span>

<span data-ttu-id="04c74-143">Lorsque la sélection du groupement est appliqué, la confirmation d'article est cruciale pour vérifier les articles qui sont ajoutés aux clusters.</span><span class="sxs-lookup"><span data-stu-id="04c74-143">When cluster picking is applied, item confirmation is crucial to verify the items that are added to clusters.</span></span> <span data-ttu-id="04c74-144">Vous pouvez vérifier les articles de la sélection du groupement lors du processus de sélection du groupement.</span><span class="sxs-lookup"><span data-stu-id="04c74-144">You can verify items in cluster picking during the cluster picking process.</span></span> <span data-ttu-id="04c74-145">Le paramétrage est basé sur le paramétrage de code-barres de produit.</span><span class="sxs-lookup"><span data-stu-id="04c74-145">The setup is based on the product bar code setup.</span></span>

### <a name="set-up-item-verification-with-cluster-picking"></a><span data-ttu-id="04c74-146">Paramétrage de la vérification d'article avec la sélection du groupement</span><span class="sxs-lookup"><span data-stu-id="04c74-146">Set up item verification with cluster picking</span></span>

1.  <span data-ttu-id="04c74-147">Dans une option de menu de l'appareil mobile, ouvrez l'écran de paramétrage pour la confirmation du travail : **Gestion des entrepôts** \> **Gestion des entrepôts** \> **Paramétrage** \> **Appareil mobile** \> **Options de menu d'appareil mobile**.</span><span class="sxs-lookup"><span data-stu-id="04c74-147">On a mobile device menu item, open the setup form for work confirmation: **Warehouse management** \> **Warehouse management** \> **Setup** \> **Mobile device** \> **Mobile device menu items**.</span></span>

2.  <span data-ttu-id="04c74-148">Dans l'option de menu de l'appareil mobile, ouvrez **Paramétrage de la confirmation du travail**.</span><span class="sxs-lookup"><span data-stu-id="04c74-148">From the mobile device menu item, open **Work confirmation setup**.</span></span> <span data-ttu-id="04c74-149">L'option **Confirmation du produit** permet de confirmer chaque pièce du stock de l'appareil mobile lors de la lecture.</span><span class="sxs-lookup"><span data-stu-id="04c74-149">The **Product confirmation** option allows you to verify each piece of inventory from the mobile device when scanned.</span></span>
