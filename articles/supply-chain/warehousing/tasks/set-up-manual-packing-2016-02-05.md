--- 
title: "Paramétrer l'emballage manuel (février et mai 2016 uniquement)"
description: Le processus d'emballage vous permet de valider et conditionner les produits dans des conteneurs.
author: BibiSp
manager: AnnBe
ms.date: 11/04/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 714fd4762ae54f8f6638e81dd19fdd636091b88e
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---
# <a name="set-up-manual-packing-february--may-2016-only"></a><span data-ttu-id="64c50-103">Paramétrer l'emballage manuel (février et mai 2016 uniquement)</span><span class="sxs-lookup"><span data-stu-id="64c50-103">Set up manual packing (February & May 2016 only)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="64c50-104">Le processus d'emballage vous permet de valider et conditionner les produits dans des conteneurs.</span><span class="sxs-lookup"><span data-stu-id="64c50-104">The packing process allows you to validate and pack products into containers.</span></span> <span data-ttu-id="64c50-105">Dans ce processus, les magasiniers prélèvent les produits dans les emplacements de stockage et les déplacent dans un centre d'emballage dans lequel ils vérifient les quantités et les types d'article, puis ils les affectent aux conteneurs appropriés.</span><span class="sxs-lookup"><span data-stu-id="64c50-105">In this process, warehouse workers pick products from the storage locations and move them to a packing station where they check the item quantities and types, and assign them to appropriate containers.</span></span> <span data-ttu-id="64c50-106">Lorsqu'un conteneur est entièrement emballé, ils peuvent le fermer et le déplacer vers les quais d’expédition, et les produits sont alors prêts à expédier.</span><span class="sxs-lookup"><span data-stu-id="64c50-106">When a container is fully packed, they can close it and move it to the outbound docks, and the products are ready to ship.</span></span> <span data-ttu-id="64c50-107">La société fictive USMF sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="64c50-107">This procedure uses the USMF demo company.</span></span>


## <a name="set-up-location-profiles"></a><span data-ttu-id="64c50-108">Définir des profils d'emplacement</span><span class="sxs-lookup"><span data-stu-id="64c50-108">Set up location profiles</span></span>
1. <span data-ttu-id="64c50-109">Accédez à Gestion des entrepôts > Paramétrage > Entrepôt > Profils d'emplacement.</span><span class="sxs-lookup"><span data-stu-id="64c50-109">Go to Warehouse management > Setup > Warehouse > Location profiles.</span></span>
2. <span data-ttu-id="64c50-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="64c50-110">Click New.</span></span>
    * <span data-ttu-id="64c50-111">Le profil d'emplacement est utilisé pour les centres d'emballage et contient des informations et des règles pour un emplacement.</span><span class="sxs-lookup"><span data-stu-id="64c50-111">The location profile is used for packing stations and contains information and rules for a location.</span></span>  
3. <span data-ttu-id="64c50-112">Dans le champ ID du profil d'emplacement, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="64c50-112">In the Location profile ID field, type a value.</span></span>
4. <span data-ttu-id="64c50-113">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="64c50-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="64c50-114">Saisissez ou sélectionnez une valeur dans le champ Format de l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="64c50-114">In the Location format field, enter or select a value.</span></span>
6. <span data-ttu-id="64c50-115">Saisissez ou sélectionnez une valeur dans le champ Type d'emplacement.</span><span class="sxs-lookup"><span data-stu-id="64c50-115">In the Location type field, enter or select a value.</span></span>
7. <span data-ttu-id="64c50-116">Sélectionnez Oui dans le champ Autoriser les articles mixtes.</span><span class="sxs-lookup"><span data-stu-id="64c50-116">Select Yes in the Allow mixed items field.</span></span>
8. <span data-ttu-id="64c50-117">Sélectionnez Oui dans le champ Autoriser les statuts de stock mixtes.</span><span class="sxs-lookup"><span data-stu-id="64c50-117">Select Yes in the Allow mixed  inventory statuses field.</span></span>
9. <span data-ttu-id="64c50-118">Sélectionnez Oui dans le champ Règles de remplacement pour les jours de traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="64c50-118">Select Yes in the Override rules for batch days field.</span></span>
10. <span data-ttu-id="64c50-119">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="64c50-119">Close the page.</span></span>

## <a name="set-up-warehouse-management-parameters"></a><span data-ttu-id="64c50-120">Définir les paramètres de gestion des entrepôts</span><span class="sxs-lookup"><span data-stu-id="64c50-120">Set up warehouse management parameters</span></span> 
1. <span data-ttu-id="64c50-121">Acccédez à Gestion des entrepôts > Configuration > Paramètres de gestion des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="64c50-121">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="64c50-122">Cliquez sur l'onglet Emballage.</span><span class="sxs-lookup"><span data-stu-id="64c50-122">Click the Packing tab.</span></span>
3. <span data-ttu-id="64c50-123">Saisissez ou sélectionnez une valeur dans le champ ID profil pour l'emplacement d'emballage.</span><span class="sxs-lookup"><span data-stu-id="64c50-123">In the Profile ID for packing location field, enter or select a value.</span></span>
    * <span data-ttu-id="64c50-124">Sélectionnez le profil d'emplacement que vous voulez utiliser pour l'emballage.</span><span class="sxs-lookup"><span data-stu-id="64c50-124">Select the location profile that you want to use for packing.</span></span>  
4. <span data-ttu-id="64c50-125">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="64c50-125">Close the page.</span></span>

## <a name="set-up-container-types"></a><span data-ttu-id="64c50-126">Paramétrer les types de conteneur</span><span class="sxs-lookup"><span data-stu-id="64c50-126">Set up container types</span></span>
1. <span data-ttu-id="64c50-127">Accédez à Gestion des entrepôts > Paramétrage > Conteneurs > Types de conteneurs.</span><span class="sxs-lookup"><span data-stu-id="64c50-127">Go to Warehouse management > Setup > Containers > Container types.</span></span>
2. <span data-ttu-id="64c50-128">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="64c50-128">Click New.</span></span>
    * <span data-ttu-id="64c50-129">Vous pouvez définir les types de conteneurs à utiliser.</span><span class="sxs-lookup"><span data-stu-id="64c50-129">You can define the types of containers to use.</span></span> <span data-ttu-id="64c50-130">Vous pouvez spécifier les dimensions physiques du conteneur, notamment le poids de la tare, le poids maximum, le volume maximum, la longueur, la largeur et le poids.</span><span class="sxs-lookup"><span data-stu-id="64c50-130">You can specify the physical dimensions of the container, including tare weight, maximum weight, maximum volume, length, width, and weight.</span></span>  <span data-ttu-id="64c50-131">Les attributs sont des champs personnalisés qui permettent d'ajouter des dimensions supplémentaires sur le type de conteneur.</span><span class="sxs-lookup"><span data-stu-id="64c50-131">The Attributes are customized fields that allow you to add extra dimensions on the container type.</span></span>     
3. <span data-ttu-id="64c50-132">Tapez une valeur dans le champ Type de conteneur.</span><span class="sxs-lookup"><span data-stu-id="64c50-132">In the Container type code field, type a value.</span></span>
4. <span data-ttu-id="64c50-133">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="64c50-133">In the Description field, type a value.</span></span>
5. <span data-ttu-id="64c50-134">Entrez un nombre dans le champ Tare.</span><span class="sxs-lookup"><span data-stu-id="64c50-134">In the Tare weight field, enter a number.</span></span>
6. <span data-ttu-id="64c50-135">Entrez un nombre dans le champ Poids maximal.</span><span class="sxs-lookup"><span data-stu-id="64c50-135">In the Maximum weight field, enter a number.</span></span>
7. <span data-ttu-id="64c50-136">Dans le champ Volume, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="64c50-136">In the Volume field, enter a number.</span></span>
8. <span data-ttu-id="64c50-137">Dans le champ Longueur, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="64c50-137">In the Length field, enter a number.</span></span>
9. <span data-ttu-id="64c50-138">Entrez un nombre dans le champ Largeur.</span><span class="sxs-lookup"><span data-stu-id="64c50-138">In the Width field, enter a number.</span></span>
10. <span data-ttu-id="64c50-139">Entrez un nombre dans le champ Hauteur.</span><span class="sxs-lookup"><span data-stu-id="64c50-139">In the Height field, enter a number.</span></span>
11. <span data-ttu-id="64c50-140">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="64c50-140">Click Save.</span></span>
12. <span data-ttu-id="64c50-141">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="64c50-141">Close the page.</span></span>

## <a name="set-up-packing-profiles"></a><span data-ttu-id="64c50-142">Paramétrer les profils de conditionnement</span><span class="sxs-lookup"><span data-stu-id="64c50-142">Set up packing profiles</span></span>
1. <span data-ttu-id="64c50-143">Accédez à Gestion des entrepôts > Paramétrage > Emballage > Profils d'emballage.</span><span class="sxs-lookup"><span data-stu-id="64c50-143">Go to Warehouse management > Setup > Packing > Packing profiles.</span></span>
2. <span data-ttu-id="64c50-144">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="64c50-144">Click New.</span></span>
3. <span data-ttu-id="64c50-145">Tapez une valeur dans le champ ID profil d'emballage.</span><span class="sxs-lookup"><span data-stu-id="64c50-145">In the Packing profile ID field, type a value.</span></span>
4. <span data-ttu-id="64c50-146">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="64c50-146">In the Description field, type a value.</span></span>
5. <span data-ttu-id="64c50-147">Saisissez ou sélectionnez une valeur dans le champ ID profil de clôture de conteneur.</span><span class="sxs-lookup"><span data-stu-id="64c50-147">In the Container closing profile ID field, enter or select a value.</span></span>
    * <span data-ttu-id="64c50-148">Un ID profil de clôture de conteneur est facultatif, il s'agit du profil de fermeture de conteneur par défaut pour ce profil d'emballage.</span><span class="sxs-lookup"><span data-stu-id="64c50-148">A container closing profile ID is optional and is the default close container profile for this packing profile.</span></span>  
6. <span data-ttu-id="64c50-149">Sélectionnez une option dans le champ Mode ID conteneur.</span><span class="sxs-lookup"><span data-stu-id="64c50-149">In the Container ID mode field, select an option.</span></span>
    * <span data-ttu-id="64c50-150">Cette option détermine si un ID conteneur est automatiquement généré lorsqu'un conteneur est créé ou si un ID conteneur sera créé manuellement.</span><span class="sxs-lookup"><span data-stu-id="64c50-150">This option determines whether a container ID will be automatically generated when a container is created or if a container ID will be created manually.</span></span>  
7. <span data-ttu-id="64c50-151">Saisissez ou sélectionnez une valeur dans le champ Type de conteneur.</span><span class="sxs-lookup"><span data-stu-id="64c50-151">In the Container type field, enter or select a value.</span></span>
    * <span data-ttu-id="64c50-152">Le type de conteneur sera utilisé par défaut lorsqu'un nouveau conteneur est créé.</span><span class="sxs-lookup"><span data-stu-id="64c50-152">The container type will be used by default when a new container is created.</span></span>  
8. <span data-ttu-id="64c50-153">Activez la case à cocher Créer automatiquement un conteneur à la clôture du conteneur.</span><span class="sxs-lookup"><span data-stu-id="64c50-153">Select the Autocreate container at container close check box.</span></span>
9. <span data-ttu-id="64c50-154">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="64c50-154">Click Save.</span></span>
10. <span data-ttu-id="64c50-155">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="64c50-155">Close the page.</span></span>

## <a name="set-up-container-closing-profiles"></a><span data-ttu-id="64c50-156">Paramétrer les profils de clôture de conteneur</span><span class="sxs-lookup"><span data-stu-id="64c50-156">Set up container closing profiles</span></span>
1. <span data-ttu-id="64c50-157">Accédez à Gestion des entrepôts > Paramétrage > Conteneurs > Profils de clôture de conteneur.</span><span class="sxs-lookup"><span data-stu-id="64c50-157">Go to Warehouse management > Setup > Containers > Container closing profiles.</span></span>
    * <span data-ttu-id="64c50-158">Les profils de clôture de conteneur définissent ce qui se produit lorsqu'un conteneur est clôturé.</span><span class="sxs-lookup"><span data-stu-id="64c50-158">Container closing profiles define what happens when a container is closed.</span></span> <span data-ttu-id="64c50-159">Vous pouvez paramétrer plusieurs profils de fermeture de conteneur.</span><span class="sxs-lookup"><span data-stu-id="64c50-159">You can set up multiple close container profiles.</span></span>       
2. <span data-ttu-id="64c50-160">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="64c50-160">Click New.</span></span>
3. <span data-ttu-id="64c50-161">Tapez une valeur dans le champ ID profil de clôture de conteneur.</span><span class="sxs-lookup"><span data-stu-id="64c50-161">In the Container closing profile ID field, type a value.</span></span>
4. <span data-ttu-id="64c50-162">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="64c50-162">In the Description field, type a value.</span></span>
5. <span data-ttu-id="64c50-163">Sélectionnez une option dans le champ Date manifeste.</span><span class="sxs-lookup"><span data-stu-id="64c50-163">In the Manifest at field, select an option.</span></span>
    * <span data-ttu-id="64c50-164">Spécifiez si la manifestation a lieu lors de la fermeture des conteneurs ou lors de la confirmation de l'expédition.</span><span class="sxs-lookup"><span data-stu-id="64c50-164">Specify whether manifesting will occur when closing containers or when confirming the shipment.</span></span> <span data-ttu-id="64c50-165">Notez que la gestion du transport est nécessaire pour la manifestation.</span><span class="sxs-lookup"><span data-stu-id="64c50-165">Note that manifesting requires Transportation management.</span></span> <span data-ttu-id="64c50-166">Pour pouvoir fonctionner, la manifestation doit être implémentée dans les moteurs de transport.</span><span class="sxs-lookup"><span data-stu-id="64c50-166">Manifesting must be implemented in the transportation engines in order for it work.</span></span>  
6. <span data-ttu-id="64c50-167">Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="64c50-167">In the Warehouse field, enter or select a value.</span></span>
7. <span data-ttu-id="64c50-168">Saisissez ou sélectionnez une valeur dans le champ Emplacement par défaut pour l'expédition finale.</span><span class="sxs-lookup"><span data-stu-id="64c50-168">In the Default location for final shipment field, enter or select a value.</span></span>
    * <span data-ttu-id="64c50-169">Il s'agit de l'emplacement où les produits seront déplacés une fois les conteneurs clôturés.</span><span class="sxs-lookup"><span data-stu-id="64c50-169">This will be location to which products will be moved after the containers are closed.</span></span> <span data-ttu-id="64c50-170">Cet emplacement doit avoir un profil d'emplacement défini dans les paramètres d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="64c50-170">This location must have a location profile defined on Warehouse parameters.</span></span>  
8. <span data-ttu-id="64c50-171">Saisissez ou sélectionnez une valeur dans le champ Unité de poids.</span><span class="sxs-lookup"><span data-stu-id="64c50-171">In the Weight unit field, enter or select a value.</span></span>
9. <span data-ttu-id="64c50-172">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="64c50-172">Click Save.</span></span>


