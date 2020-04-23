---
title: Gestion des erreurs
description: Cette rubrique explique la gestion des erreurs dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6665e80342af1baa7176aee92693b77e83b368f0
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205918"
---
# <a name="fault-management"></a><span data-ttu-id="99ea4-103">Gestion des erreurs</span><span class="sxs-lookup"><span data-stu-id="99ea4-103">Fault management</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="99ea4-104">Dans le module Gestion des actifs, vous pouvez utiliser le concepteur de défaillance pour paramétrer les symptômes de défaillance, les zones de défaillance, et les types de défaillance sur les types d'actifs.</span><span class="sxs-lookup"><span data-stu-id="99ea4-104">In Asset Management, you can use the fault designer to set up fault symptoms, fault areas, and fault types on asset types.</span></span> <span data-ttu-id="99ea4-105">De cette manière, vous pouvez gérer les défaillances qui sont détectées sur les actifs.</span><span class="sxs-lookup"><span data-stu-id="99ea4-105">In this way, you can manage faults that are detected on assets.</span></span> <span data-ttu-id="99ea4-106">Il est en outre possible d'enregistrer les causes de défaillance, ainsi que des suggestions pour les résoudre sur un ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="99ea4-106">Additionally, fault causes and suggestions for fixing faults can be registered on a work order.</span></span>

<span data-ttu-id="99ea4-107">Le processus d'enregistrement et de gestion de défaillance se déroule comme suit :</span><span class="sxs-lookup"><span data-stu-id="99ea4-107">The process for fault registration and management consists of these steps.</span></span>

1. <span data-ttu-id="99ea4-108">Créez une liste des symptômes de défaillance, des zones de défaillance, et des types de défaillance qui peuvent se produire sur vos types d'actifs.</span><span class="sxs-lookup"><span data-stu-id="99ea4-108">Create a list of fault symptoms, fault areas, and fault types that might occur on your asset types.</span></span>
2. <span data-ttu-id="99ea4-109">Dans le concepteur de défaillance, paramétrez les symptômes de défaillance, les zones de défaillance, et les types de défaillance.</span><span class="sxs-lookup"><span data-stu-id="99ea4-109">In the fault designer, set up symptoms, fault areas, and fault types.</span></span>

<span data-ttu-id="99ea4-110">Voici quelques exemples pour vous aider à comprendre la différence entre les symptômes de défaillance, les zones de défaillance, et les types de défaillance.</span><span class="sxs-lookup"><span data-stu-id="99ea4-110">Here are some examples to help you understand the difference between fault symptoms, fault areas, and fault types.</span></span>

<span data-ttu-id="99ea4-111">**Symptômes de défaillance :**</span><span class="sxs-lookup"><span data-stu-id="99ea4-111">**Fault symptoms:**</span></span>

- <span data-ttu-id="99ea4-112">Tensions non équilibrées</span><span class="sxs-lookup"><span data-stu-id="99ea4-112">Unbalanced voltages</span></span>
- <span data-ttu-id="99ea4-113">Court circuit</span><span class="sxs-lookup"><span data-stu-id="99ea4-113">Short circuit</span></span>
- <span data-ttu-id="99ea4-114">Bruit</span><span class="sxs-lookup"><span data-stu-id="99ea4-114">Noise</span></span>
- <span data-ttu-id="99ea4-115">Fuite</span><span class="sxs-lookup"><span data-stu-id="99ea4-115">Leak</span></span>
- <span data-ttu-id="99ea4-116">Vibrations</span><span class="sxs-lookup"><span data-stu-id="99ea4-116">Vibrations</span></span>

<span data-ttu-id="99ea4-117">**Zones de défaillance :**</span><span class="sxs-lookup"><span data-stu-id="99ea4-117">**Fault areas:**</span></span>

- <span data-ttu-id="99ea4-118">Électrique</span><span class="sxs-lookup"><span data-stu-id="99ea4-118">Electrical</span></span>
- <span data-ttu-id="99ea4-119">Mécanique</span><span class="sxs-lookup"><span data-stu-id="99ea4-119">Mechanical</span></span>
- <span data-ttu-id="99ea4-120">Hydraulique</span><span class="sxs-lookup"><span data-stu-id="99ea4-120">Hydraulic</span></span>
- <span data-ttu-id="99ea4-121">Pneumatique</span><span class="sxs-lookup"><span data-stu-id="99ea4-121">Pneumatic</span></span>

<span data-ttu-id="99ea4-122">**Types de défaillance :**</span><span class="sxs-lookup"><span data-stu-id="99ea4-122">**Fault types:**</span></span>

- <span data-ttu-id="99ea4-123">Bobinage du stator principal défectueux</span><span class="sxs-lookup"><span data-stu-id="99ea4-123">Faulty main stator winding</span></span>
- <span data-ttu-id="99ea4-124">Diode défectueuse</span><span class="sxs-lookup"><span data-stu-id="99ea4-124">Faulty diode</span></span>
- <span data-ttu-id="99ea4-125">Enroulements encrassés</span><span class="sxs-lookup"><span data-stu-id="99ea4-125">Dirty windings</span></span>
- <span data-ttu-id="99ea4-126">Générateur défectueux</span><span class="sxs-lookup"><span data-stu-id="99ea4-126">Defective generator</span></span>
- <span data-ttu-id="99ea4-127">Capteur défectueux</span><span class="sxs-lookup"><span data-stu-id="99ea4-127">Defective sensor</span></span>

## <a name="create-fault-symptoms"></a><span data-ttu-id="99ea4-128">Créer les symptômes de défaillance</span><span class="sxs-lookup"><span data-stu-id="99ea4-128">Create fault symptoms</span></span>

<span data-ttu-id="99ea4-129">Procédez comme suit pour créer une liste des symptômes qui peuvent être utilisés dans le concepteur de défaillance.</span><span class="sxs-lookup"><span data-stu-id="99ea4-129">Follow these steps to create a list of symptoms that can be used in the fault designer.</span></span>

1. <span data-ttu-id="99ea4-130">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Problème** \> **Symptômes de défaillance**.</span><span class="sxs-lookup"><span data-stu-id="99ea4-130">Select **Asset management** \> **Setup** \> **Fault** \> **Fault symptoms**.</span></span>
2. <span data-ttu-id="99ea4-131">Sélectionnez **Nouveau** pour créer un enregistrement.</span><span class="sxs-lookup"><span data-stu-id="99ea4-131">Select **New** to create a record.</span></span>
3. <span data-ttu-id="99ea4-132">Entrez un nom pour le symptôme de défaillance dans le champ **Symptômes de défaillance**.</span><span class="sxs-lookup"><span data-stu-id="99ea4-132">In the **Fault symptom** field, enter a name for the fault symptom.</span></span>
4. <span data-ttu-id="99ea4-133">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="99ea4-133">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="99ea4-134">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="99ea4-134">Select **Save**.</span></span>

## <a name="create-fault-areas"></a><span data-ttu-id="99ea4-135">Créer des zones de défaillance</span><span class="sxs-lookup"><span data-stu-id="99ea4-135">Create fault areas</span></span>

<span data-ttu-id="99ea4-136">Procédez comme suit pour créer une liste des zones ou des emplacements qui peuvent être utilisés dans le concepteur de défaillance.</span><span class="sxs-lookup"><span data-stu-id="99ea4-136">Follow these steps to create a list of areas or locations that can be used in the fault designer.</span></span>

1. <span data-ttu-id="99ea4-137">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Problème** \> **Zones de défaillance**.</span><span class="sxs-lookup"><span data-stu-id="99ea4-137">Select **Asset management** \> **Setup** \> **Fault** \> **Fault areas**.</span></span>
2. <span data-ttu-id="99ea4-138">Sélectionnez **Nouveau** pour créer un enregistrement.</span><span class="sxs-lookup"><span data-stu-id="99ea4-138">Select **New** to create a record.</span></span>
3. <span data-ttu-id="99ea4-139">Entrez un nom pour la zone de défaillance dans le champ **Zone de défaillance**.</span><span class="sxs-lookup"><span data-stu-id="99ea4-139">In the **Fault area** field, enter a name for the fault area.</span></span>
4. <span data-ttu-id="99ea4-140">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="99ea4-140">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="99ea4-141">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="99ea4-141">Select **Save**.</span></span>

## <a name="create-fault-types"></a><span data-ttu-id="99ea4-142">Créer des types de défaillance</span><span class="sxs-lookup"><span data-stu-id="99ea4-142">Create fault types</span></span>

<span data-ttu-id="99ea4-143">Procédez comme suit pour créer une liste des types de défaillance qui peuvent être utilisés dans le concepteur de défaillance.</span><span class="sxs-lookup"><span data-stu-id="99ea4-143">Follow these steps to create a list of fault types that can be used in the fault designer.</span></span>

1. <span data-ttu-id="99ea4-144">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Problème** \> **Types de défaillance**.</span><span class="sxs-lookup"><span data-stu-id="99ea4-144">Select **Asset management** \> **Setup** \> **Fault** \> **Fault types**.</span></span>
2. <span data-ttu-id="99ea4-145">Sélectionnez **Nouveau** pour créer un enregistrement.</span><span class="sxs-lookup"><span data-stu-id="99ea4-145">Select **New** to create a record.</span></span>
3. <span data-ttu-id="99ea4-146">Dans le champ **Type de défaillance**, entrez un nom pour le type de défaillance.</span><span class="sxs-lookup"><span data-stu-id="99ea4-146">In the **Fault type** field, enter a name for the fault type.</span></span>
4. <span data-ttu-id="99ea4-147">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="99ea4-147">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="99ea4-148">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="99ea4-148">Select **Save**.</span></span>

## <a name="set-up-the-fault-designer"></a><span data-ttu-id="99ea4-149">Paramétrer le concepteur de défaillance</span><span class="sxs-lookup"><span data-stu-id="99ea4-149">Set up the fault designer</span></span>

<span data-ttu-id="99ea4-150">Dans le concepteur de défaillance, vous devez paramétrer des données de défaillance sur les types d'actifs.</span><span class="sxs-lookup"><span data-stu-id="99ea4-150">In the fault designer, you set up fault data on asset types.</span></span>

1. <span data-ttu-id="99ea4-151">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Problème** \> **Concepteur de défaillance**.</span><span class="sxs-lookup"><span data-stu-id="99ea4-151">Select **Asset management** \> **Setup** \> **Fault** \> **Fault designer**.</span></span>
2. <span data-ttu-id="99ea4-152">Dans le volet gauche, sélectionnez le type d'actif pour lequel paramétrer un enregistrement de défaillance.</span><span class="sxs-lookup"><span data-stu-id="99ea4-152">In the left pane, select the type of asset to set up a fault record for.</span></span>
3. <span data-ttu-id="99ea4-153">Dans le raccourci **Symptôme de défaillance**, sélectionnez **Ajouter une ligne**, puis, dans le champ **Symptôme de défaillance**, sélectionnez un symptôme de défaillance.</span><span class="sxs-lookup"><span data-stu-id="99ea4-153">On the **Fault symptom** FastTab, select **Add line**, and then, in the **Fault symptom** field, select a fault symptom.</span></span>
4. <span data-ttu-id="99ea4-154">Dans le raccourci **Zone de défaillance**, sélectionnez **Ajouter une ligne**, puis, dans le champ **Zone de défaillance**, sélectionnez une zone de défaillance.</span><span class="sxs-lookup"><span data-stu-id="99ea4-154">On the **Fault area** FastTab, select **Add line**, and then, in the **Fault area** field select a fault area.</span></span>
5. <span data-ttu-id="99ea4-155">Dans le raccourci **Type de défaillance**, sélectionnez **Ajouter une ligne**, puis, dans le champ **Type de défaillance**, sélectionnez un type de défaillance.</span><span class="sxs-lookup"><span data-stu-id="99ea4-155">On the **Fault type** FastTab, select **Add line**, and then, in the **Fault type** field, select a fault type.</span></span>
6. <span data-ttu-id="99ea4-156">Pour créer rapidement des combinaisons de tous les symptômes, de toutes les zones, et de tous les types de défaillance existants pour le type d'actif sélectionné, sélectionnez **Créer des combinaisons de défaillance**.</span><span class="sxs-lookup"><span data-stu-id="99ea4-156">To quickly create combinations of all existing fault symptoms, areas, and types for the selected asset type, select **Create fault combinations**.</span></span> <span data-ttu-id="99ea4-157">Cette fonction est utile si vous avez ajouté beaucoup de symptômes, de zones, et de types de défaillance.</span><span class="sxs-lookup"><span data-stu-id="99ea4-157">This function is useful if you've added many fault symptoms, areas, and types.</span></span> <span data-ttu-id="99ea4-158">Il est plus facile de supprimer les lignes des combinaisons qui ne conviennent pas pour le type d'actif que de créer de nouvelles lignes manuellement.</span><span class="sxs-lookup"><span data-stu-id="99ea4-158">It's easier to delete the lines for any combinations that aren't relevant to the asset type than to create new lines manually.</span></span>

    > [!NOTE]
    > <span data-ttu-id="99ea4-159">Copiez le paramétrage des symptômes, des zones et des types de défaillance d'un type d'actif sur le type d'actif sélectionné, sélectionnez **Copier à partir du type d'actif**.</span><span class="sxs-lookup"><span data-stu-id="99ea4-159">To copy the setup of fault symptoms, areas, and types from one asset type to the selected asset type, select **Copy from asset type**.</span></span>

7. <span data-ttu-id="99ea4-160">Sélectionnez **Enregistrer** pour enregistrer les modifications.</span><span class="sxs-lookup"><span data-stu-id="99ea4-160">Select **Save** to save your changes.</span></span>

![Page Concepteur de défaillance](media/21-setup-for-work-orders.png)

## <a name="create-fault-causes"></a><span data-ttu-id="99ea4-162">Créer des causes de défaillance</span><span class="sxs-lookup"><span data-stu-id="99ea4-162">Create fault causes</span></span>

<span data-ttu-id="99ea4-163">Procédez comme suit pour créer une liste des causes connues de défaillance pouvant être ajoutées à un ordre de travail ou à une demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="99ea4-163">Follow these steps to create a list of known fault causes that can be added to a work order or a maintenance request.</span></span>

1. <span data-ttu-id="99ea4-164">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Problème** \> **Causes de défaillance**.</span><span class="sxs-lookup"><span data-stu-id="99ea4-164">Select **Asset management** \> **Setup** \> **Fault** \> **Fault causes**.</span></span>
2. <span data-ttu-id="99ea4-165">Sélectionnez **Nouveau** pour créer un enregistrement.</span><span class="sxs-lookup"><span data-stu-id="99ea4-165">Select **New** to create a record.</span></span>
3. <span data-ttu-id="99ea4-166">Dans le champ **Cause de défaillance**, entrez un nom pour la cause de défaillance.</span><span class="sxs-lookup"><span data-stu-id="99ea4-166">In the **Fault cause** field, enter a name for the fault cause.</span></span>
4. <span data-ttu-id="99ea4-167">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="99ea4-167">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="99ea4-168">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="99ea4-168">Select **Save**.</span></span>

## <a name="create-fault-remedies"></a><span data-ttu-id="99ea4-169">Créer des solutions aux défaillances</span><span class="sxs-lookup"><span data-stu-id="99ea4-169">Create fault remedies</span></span>

<span data-ttu-id="99ea4-170">Procédez comme suit pour créer une liste de suggestions de résolution et de réparation pouvant être ajoutées à un ordre de travail ou à une demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="99ea4-170">Follow these steps to create a list of suggestions for remedy and repair that can be added to a work order or a maintenance request.</span></span>

1. <span data-ttu-id="99ea4-171">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Problème** \> **Solutions aux défaillances**.</span><span class="sxs-lookup"><span data-stu-id="99ea4-171">Select **Asset management** \> **Setup** \> **Fault** \> **Fault remedies**.</span></span>
2. <span data-ttu-id="99ea4-172">Sélectionnez **Nouveau** pour créer un enregistrement.</span><span class="sxs-lookup"><span data-stu-id="99ea4-172">Select **New** to create a record.</span></span>
3. <span data-ttu-id="99ea4-173">Entrez un nom pour la solution à la défaillance dans le champ **Solutions aux défaillances**.</span><span class="sxs-lookup"><span data-stu-id="99ea4-173">In the **Fault remedy** field, enter a name for the fault remedy.</span></span>
4. <span data-ttu-id="99ea4-174">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="99ea4-174">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="99ea4-175">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="99ea4-175">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="99ea4-176">Vous pouvez modifier les noms des symptômes, zones, types, causes, et recours pour les défaillances dont vous disposez comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="99ea4-176">You can change the names of your fault symptoms, areas, types, causes, and remedies as you require.</span></span> <span data-ttu-id="99ea4-177">Les modifications apportées au nom sont répercutées automatiquement dans les enregistrements de défaillance liés.</span><span class="sxs-lookup"><span data-stu-id="99ea4-177">The name changes are automatically reflected in the related fault registrations.</span></span>
