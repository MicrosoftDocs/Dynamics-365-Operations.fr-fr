---
title: Paramétrer l'emballage manuel (février 2016 et mai 2016)
description: Le processus d'emballage vous permet de valider et conditionner les produits dans des conteneurs.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile, WHSParameters, WHSContainerType, WHSPackProfile, WHSCloseContainerProfile, InventLocationIdLookup, UnitOfMeasureLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 30bbb404e624c33e047c5505c5b21565ed8cce10
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1847181"
---
# <a name="set-up-manual-packing-february-2016--may-2016"></a><span data-ttu-id="e4fb2-103">Paramétrer l'emballage manuel (février 2016 et mai 2016)</span><span class="sxs-lookup"><span data-stu-id="e4fb2-103">Set up manual packing (February 2016 & May 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e4fb2-104">Le processus d'emballage vous permet de valider et conditionner les produits dans des conteneurs.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-104">The packing process allows you to validate and pack products into containers.</span></span> <span data-ttu-id="e4fb2-105">Dans ce processus, les magasiniers prélèvent les produits dans les emplacements de stockage et les déplacent dans un centre d'emballage dans lequel ils vérifient les quantités et les types d'article, puis ils les affectent aux conteneurs appropriés.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-105">In this process, warehouse workers pick products from the storage locations and move them to a packing station where they check the item quantities and types, and assign them to appropriate containers.</span></span> <span data-ttu-id="e4fb2-106">Lorsqu'un conteneur est entièrement emballé, ils peuvent le fermer et le déplacer vers les quais d’expédition, et les produits sont alors prêts à expédier.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-106">When a container is fully packed, they can close it and move it to the outbound docks, and the products are ready to ship.</span></span> <span data-ttu-id="e4fb2-107">La société fictive USMF sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-107">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="e4fb2-108">Cette procédure s'applique aux versions de février 2016 et mai 2016 de Dynamics 365 for Operations uniquement.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-108">This procedure is for the February 2016 & May 2016 versions of Dynamics 365 for Operations only.</span></span>


## <a name="set-up-location-profiles"></a><span data-ttu-id="e4fb2-109">Définir des profils d'emplacement</span><span class="sxs-lookup"><span data-stu-id="e4fb2-109">Set up location profiles</span></span>
1. <span data-ttu-id="e4fb2-110">Accédez à Gestion des entrepôts > Paramétrage > Entrepôt > Profils d'emplacement.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-110">Go to Warehouse management > Setup > Warehouse > Location profiles.</span></span>
2. <span data-ttu-id="e4fb2-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-111">Click New.</span></span>
    * <span data-ttu-id="e4fb2-112">Le profil d'emplacement est utilisé pour les centres d'emballage et contient des informations et des règles pour un emplacement.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-112">The location profile is used for packing stations and contains information and rules for a location.</span></span>  
3. <span data-ttu-id="e4fb2-113">Dans le champ ID du profil d'emplacement, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-113">In the Location profile ID field, type a value.</span></span>
4. <span data-ttu-id="e4fb2-114">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-114">In the Name field, type a value.</span></span>
5. <span data-ttu-id="e4fb2-115">Saisissez ou sélectionnez une valeur dans le champ Format de l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-115">In the Location format field, enter or select a value.</span></span>
6. <span data-ttu-id="e4fb2-116">Saisissez ou sélectionnez une valeur dans le champ Type d'emplacement.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-116">In the Location type field, enter or select a value.</span></span>
7. <span data-ttu-id="e4fb2-117">Sélectionnez Oui dans le champ Autoriser les articles mixtes.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-117">Select Yes in the Allow mixed items field.</span></span>
8. <span data-ttu-id="e4fb2-118">Sélectionnez Oui dans le champ Autoriser les statuts de stock mixtes.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-118">Select Yes in the Allow mixed  inventory statuses field.</span></span>
9. <span data-ttu-id="e4fb2-119">Sélectionnez Oui dans le champ Règles de remplacement pour les jours de traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-119">Select Yes in the Override rules for batch days field.</span></span>
10. <span data-ttu-id="e4fb2-120">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-120">Close the page.</span></span>

## <a name="set-up-warehouse-management-parameters"></a><span data-ttu-id="e4fb2-121">Définir les paramètres de gestion des entrepôts</span><span class="sxs-lookup"><span data-stu-id="e4fb2-121">Set up warehouse management parameters</span></span> 
1. <span data-ttu-id="e4fb2-122">Acccédez à Gestion des entrepôts > Configuration > Paramètres de gestion des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-122">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="e4fb2-123">Cliquez sur l'onglet Emballage.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-123">Click the Packing tab.</span></span>
3. <span data-ttu-id="e4fb2-124">Saisissez ou sélectionnez une valeur dans le champ ID profil pour l'emplacement d'emballage.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-124">In the Profile ID for packing location field, enter or select a value.</span></span>
    * <span data-ttu-id="e4fb2-125">Sélectionnez le profil d'emplacement que vous voulez utiliser pour l'emballage.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-125">Select the location profile that you want to use for packing.</span></span>  
4. <span data-ttu-id="e4fb2-126">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-126">Close the page.</span></span>

## <a name="set-up-container-types"></a><span data-ttu-id="e4fb2-127">Paramétrer les types de conteneur</span><span class="sxs-lookup"><span data-stu-id="e4fb2-127">Set up container types</span></span>
1. <span data-ttu-id="e4fb2-128">Accédez à Gestion des entrepôts > Paramétrage > Conteneurs > Types de conteneurs.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-128">Go to Warehouse management > Setup > Containers > Container types.</span></span>
2. <span data-ttu-id="e4fb2-129">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-129">Click New.</span></span>
    * <span data-ttu-id="e4fb2-130">Vous pouvez définir les types de conteneurs à utiliser.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-130">You can define the types of containers to use.</span></span> <span data-ttu-id="e4fb2-131">Vous pouvez spécifier les dimensions physiques du conteneur, notamment le poids de la tare, le poids maximum, le volume maximum, la longueur, la largeur et le poids.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-131">You can specify the physical dimensions of the container, including tare weight, maximum weight, maximum volume, length, width, and weight.</span></span>  <span data-ttu-id="e4fb2-132">Les attributs sont des champs personnalisés qui permettent d'ajouter des dimensions supplémentaires sur le type de conteneur.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-132">The Attributes are customized fields that allow you to add extra dimensions on the container type.</span></span>     
3. <span data-ttu-id="e4fb2-133">Tapez une valeur dans le champ Type de conteneur.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-133">In the Container type code field, type a value.</span></span>
4. <span data-ttu-id="e4fb2-134">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-134">In the Description field, type a value.</span></span>
5. <span data-ttu-id="e4fb2-135">Entrez un nombre dans le champ Tare.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-135">In the Tare weight field, enter a number.</span></span>
6. <span data-ttu-id="e4fb2-136">Entrez un nombre dans le champ Poids maximal.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-136">In the Maximum weight field, enter a number.</span></span>
7. <span data-ttu-id="e4fb2-137">Dans le champ Volume, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-137">In the Volume field, enter a number.</span></span>
8. <span data-ttu-id="e4fb2-138">Dans le champ Longueur, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-138">In the Length field, enter a number.</span></span>
9. <span data-ttu-id="e4fb2-139">Entrez un nombre dans le champ Largeur.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-139">In the Width field, enter a number.</span></span>
10. <span data-ttu-id="e4fb2-140">Entrez un nombre dans le champ Hauteur.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-140">In the Height field, enter a number.</span></span>
11. <span data-ttu-id="e4fb2-141">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-141">Click Save.</span></span>
12. <span data-ttu-id="e4fb2-142">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-142">Close the page.</span></span>

## <a name="set-up-packing-profiles"></a><span data-ttu-id="e4fb2-143">Paramétrer les profils de conditionnement</span><span class="sxs-lookup"><span data-stu-id="e4fb2-143">Set up packing profiles</span></span>
1. <span data-ttu-id="e4fb2-144">Accédez à Gestion des entrepôts > Paramétrage > Emballage > Profils d'emballage.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-144">Go to Warehouse management > Setup > Packing > Packing profiles.</span></span>
2. <span data-ttu-id="e4fb2-145">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-145">Click New.</span></span>
3. <span data-ttu-id="e4fb2-146">Tapez une valeur dans le champ ID profil d'emballage.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-146">In the Packing profile ID field, type a value.</span></span>
4. <span data-ttu-id="e4fb2-147">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-147">In the Description field, type a value.</span></span>
5. <span data-ttu-id="e4fb2-148">Saisissez ou sélectionnez une valeur dans le champ ID profil de clôture de conteneur.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-148">In the Container closing profile ID field, enter or select a value.</span></span>
    * <span data-ttu-id="e4fb2-149">Un ID profil de clôture de conteneur est facultatif, il s'agit du profil de fermeture de conteneur par défaut pour ce profil d'emballage.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-149">A container closing profile ID is optional and is the default close container profile for this packing profile.</span></span>  
6. <span data-ttu-id="e4fb2-150">Sélectionnez une option dans le champ Mode ID conteneur.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-150">In the Container ID mode field, select an option.</span></span>
    * <span data-ttu-id="e4fb2-151">Cette option détermine si un ID conteneur est automatiquement généré lorsqu'un conteneur est créé ou si un ID conteneur sera créé manuellement.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-151">This option determines whether a container ID will be automatically generated when a container is created or if a container ID will be created manually.</span></span>  
7. <span data-ttu-id="e4fb2-152">Saisissez ou sélectionnez une valeur dans le champ Type de conteneur.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-152">In the Container type field, enter or select a value.</span></span>
    * <span data-ttu-id="e4fb2-153">Le type de conteneur sera utilisé par défaut lorsqu'un nouveau conteneur est créé.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-153">The container type will be used by default when a new container is created.</span></span>  
8. <span data-ttu-id="e4fb2-154">Activez la case à cocher Créer automatiquement un conteneur à la clôture du conteneur.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-154">Select the Autocreate container at container close check box.</span></span>
9. <span data-ttu-id="e4fb2-155">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-155">Click Save.</span></span>
10. <span data-ttu-id="e4fb2-156">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-156">Close the page.</span></span>

## <a name="set-up-container-closing-profiles"></a><span data-ttu-id="e4fb2-157">Paramétrer les profils de clôture de conteneur</span><span class="sxs-lookup"><span data-stu-id="e4fb2-157">Set up container closing profiles</span></span>
1. <span data-ttu-id="e4fb2-158">Accédez à Gestion des entrepôts > Paramétrage > Conteneurs > Profils de clôture de conteneur.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-158">Go to Warehouse management > Setup > Containers > Container closing profiles.</span></span>
    * <span data-ttu-id="e4fb2-159">Les profils de clôture de conteneur définissent ce qui se produit lorsqu'un conteneur est clôturé.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-159">Container closing profiles define what happens when a container is closed.</span></span> <span data-ttu-id="e4fb2-160">Vous pouvez paramétrer plusieurs profils de fermeture de conteneur.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-160">You can set up multiple close container profiles.</span></span>       
2. <span data-ttu-id="e4fb2-161">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-161">Click New.</span></span>
3. <span data-ttu-id="e4fb2-162">Tapez une valeur dans le champ ID profil de clôture de conteneur.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-162">In the Container closing profile ID field, type a value.</span></span>
4. <span data-ttu-id="e4fb2-163">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-163">In the Description field, type a value.</span></span>
5. <span data-ttu-id="e4fb2-164">Sélectionnez une option dans le champ Date manifeste.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-164">In the Manifest at field, select an option.</span></span>
    * <span data-ttu-id="e4fb2-165">Spécifiez si la manifestation a lieu lors de la fermeture des conteneurs ou lors de la confirmation de l'expédition.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-165">Specify whether manifesting will occur when closing containers or when confirming the shipment.</span></span> <span data-ttu-id="e4fb2-166">Notez que la gestion du transport est nécessaire pour la manifestation.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-166">Note that manifesting requires Transportation management.</span></span> <span data-ttu-id="e4fb2-167">Pour pouvoir fonctionner, la manifestation doit être implémentée dans les moteurs de transport.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-167">Manifesting must be implemented in the transportation engines in order for it work.</span></span>  
6. <span data-ttu-id="e4fb2-168">Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-168">In the Warehouse field, enter or select a value.</span></span>
7. <span data-ttu-id="e4fb2-169">Saisissez ou sélectionnez une valeur dans le champ Emplacement par défaut pour l'expédition finale.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-169">In the Default location for final shipment field, enter or select a value.</span></span>
    * <span data-ttu-id="e4fb2-170">Il s'agit de l'emplacement où les produits seront déplacés une fois les conteneurs clôturés.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-170">This will be location to which products will be moved after the containers are closed.</span></span> <span data-ttu-id="e4fb2-171">Cet emplacement doit avoir un profil d'emplacement défini dans les paramètres d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-171">This location must have a location profile defined on Warehouse parameters.</span></span>  
8. <span data-ttu-id="e4fb2-172">Saisissez ou sélectionnez une valeur dans le champ Unité de poids.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-172">In the Weight unit field, enter or select a value.</span></span>
9. <span data-ttu-id="e4fb2-173">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e4fb2-173">Click Save.</span></span>

