---
title: Gestion des erreurs
description: Cette rubrique explique la gestion des erreurs dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 48c90a8b776cc16804de8e20ada7d8ca347fa5b9
ms.sourcegitcommit: 802dbf0a744d70f9e546632d419415b0993331ab
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2019
ms.locfileid: "1874737"
---
# <a name="fault-management"></a><span data-ttu-id="3a165-103">Gestion des erreurs</span><span class="sxs-lookup"><span data-stu-id="3a165-103">Fault management</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="3a165-104">Dans le module Gestion des actifs, vous pouvez utiliser le concepteur de défaillance pour paramétrer les symptômes de défaillance, les zones de défaillance, et les types de défaillance sur les types d'actifs.</span><span class="sxs-lookup"><span data-stu-id="3a165-104">In Asset Management, you can use the fault designer to set up fault symptoms, fault areas, and fault types on asset types.</span></span> <span data-ttu-id="3a165-105">De cette manière, vous pouvez gérer les défaillances qui sont détectées sur les actifs.</span><span class="sxs-lookup"><span data-stu-id="3a165-105">In this way, you can manage faults that are detected on assets.</span></span> <span data-ttu-id="3a165-106">Il est en outre possible d'enregistrer les causes de défaillance, ainsi que des suggestions pour les résoudre sur un ordre de travail.</span><span class="sxs-lookup"><span data-stu-id="3a165-106">Additionally, fault causes and suggestions for fixing faults can be registered on a work order.</span></span>

<span data-ttu-id="3a165-107">Le processus d'enregistrement et de gestion de défaillance se déroule comme suit :</span><span class="sxs-lookup"><span data-stu-id="3a165-107">The process for fault registration and management consists of these steps.</span></span>

1. <span data-ttu-id="3a165-108">Créez une liste des symptômes de défaillance, des zones de défaillance, et des types de défaillance qui peuvent se produire sur vos types d'actifs.</span><span class="sxs-lookup"><span data-stu-id="3a165-108">Create a list of fault symptoms, fault areas, and fault types that might occur on your asset types.</span></span>
2. <span data-ttu-id="3a165-109">Dans le concepteur de défaillance, paramétrez les symptômes de défaillance, les zones de défaillance, et les types de défaillance.</span><span class="sxs-lookup"><span data-stu-id="3a165-109">In the fault designer, set up symptoms, fault areas, and fault types.</span></span>

<span data-ttu-id="3a165-110">Voici quelques exemples pour vous aider à comprendre la différence entre les symptômes de défaillance, les zones de défaillance, et les types de défaillance.</span><span class="sxs-lookup"><span data-stu-id="3a165-110">Here are some examples to help you understand the difference between fault symptoms, fault areas, and fault types.</span></span>

<span data-ttu-id="3a165-111">**Symptômes de défaillance :**</span><span class="sxs-lookup"><span data-stu-id="3a165-111">**Fault symptoms:**</span></span>

- <span data-ttu-id="3a165-112">Tensions non équilibrées</span><span class="sxs-lookup"><span data-stu-id="3a165-112">Unbalanced voltages</span></span>
- <span data-ttu-id="3a165-113">Court circuit</span><span class="sxs-lookup"><span data-stu-id="3a165-113">Short circuit</span></span>
- <span data-ttu-id="3a165-114">Bruit</span><span class="sxs-lookup"><span data-stu-id="3a165-114">Noise</span></span>
- <span data-ttu-id="3a165-115">Fuite</span><span class="sxs-lookup"><span data-stu-id="3a165-115">Leak</span></span>
- <span data-ttu-id="3a165-116">Vibrations</span><span class="sxs-lookup"><span data-stu-id="3a165-116">Vibrations</span></span>

<span data-ttu-id="3a165-117">**Zones de défaillance :**</span><span class="sxs-lookup"><span data-stu-id="3a165-117">**Fault areas:**</span></span>

- <span data-ttu-id="3a165-118">Électrique</span><span class="sxs-lookup"><span data-stu-id="3a165-118">Electrical</span></span>
- <span data-ttu-id="3a165-119">Mécanique</span><span class="sxs-lookup"><span data-stu-id="3a165-119">Mechanical</span></span>
- <span data-ttu-id="3a165-120">Hydraulique</span><span class="sxs-lookup"><span data-stu-id="3a165-120">Hydraulic</span></span>
- <span data-ttu-id="3a165-121">Pneumatique</span><span class="sxs-lookup"><span data-stu-id="3a165-121">Pneumatic</span></span>

<span data-ttu-id="3a165-122">**Types de défaillance :**</span><span class="sxs-lookup"><span data-stu-id="3a165-122">**Fault types:**</span></span>

- <span data-ttu-id="3a165-123">Bobinage du stator principal défectueux</span><span class="sxs-lookup"><span data-stu-id="3a165-123">Faulty main stator winding</span></span>
- <span data-ttu-id="3a165-124">Diode défectueuse</span><span class="sxs-lookup"><span data-stu-id="3a165-124">Faulty diode</span></span>
- <span data-ttu-id="3a165-125">Enroulements encrassés</span><span class="sxs-lookup"><span data-stu-id="3a165-125">Dirty windings</span></span>
- <span data-ttu-id="3a165-126">Générateur défectueux</span><span class="sxs-lookup"><span data-stu-id="3a165-126">Defective generator</span></span>
- <span data-ttu-id="3a165-127">Capteur défectueux</span><span class="sxs-lookup"><span data-stu-id="3a165-127">Defective sensor</span></span>

## <a name="create-fault-symptoms"></a><span data-ttu-id="3a165-128">Créer les symptômes de défaillance</span><span class="sxs-lookup"><span data-stu-id="3a165-128">Create fault symptoms</span></span>

<span data-ttu-id="3a165-129">Procédez comme suit pour créer une liste des symptômes qui peuvent être utilisés dans le concepteur de défaillance.</span><span class="sxs-lookup"><span data-stu-id="3a165-129">Follow these steps to create a list of symptoms that can be used in the fault designer.</span></span>

1. <span data-ttu-id="3a165-130">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Problème** \> **Symptômes de défaillance**.</span><span class="sxs-lookup"><span data-stu-id="3a165-130">Select **Asset management** \> **Setup** \> **Fault** \> **Fault symptoms**.</span></span>
2. <span data-ttu-id="3a165-131">Sélectionnez **Nouveau** pour créer un enregistrement.</span><span class="sxs-lookup"><span data-stu-id="3a165-131">Select **New** to create a record.</span></span>
3. <span data-ttu-id="3a165-132">Entrez un nom pour le symptôme de défaillance dans le champ **Symptômes de défaillance**.</span><span class="sxs-lookup"><span data-stu-id="3a165-132">In the **Fault symptom** field, enter a name for the fault symptom.</span></span>
4. <span data-ttu-id="3a165-133">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="3a165-133">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="3a165-134">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="3a165-134">Select **Save**.</span></span>

## <a name="create-fault-areas"></a><span data-ttu-id="3a165-135">Créer des zones de défaillance</span><span class="sxs-lookup"><span data-stu-id="3a165-135">Create fault areas</span></span>

<span data-ttu-id="3a165-136">Procédez comme suit pour créer une liste des zones ou des emplacements qui peuvent être utilisés dans le concepteur de défaillance.</span><span class="sxs-lookup"><span data-stu-id="3a165-136">Follow these steps to create a list of areas or locations that can be used in the fault designer.</span></span>

1. <span data-ttu-id="3a165-137">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Problème** \> **Zones de défaillance**.</span><span class="sxs-lookup"><span data-stu-id="3a165-137">Select **Asset management** \> **Setup** \> **Fault** \> **Fault areas**.</span></span>
2. <span data-ttu-id="3a165-138">Sélectionnez **Nouveau** pour créer un enregistrement.</span><span class="sxs-lookup"><span data-stu-id="3a165-138">Select **New** to create a record.</span></span>
3. <span data-ttu-id="3a165-139">Entrez un nom pour la zone de défaillance dans le champ **Zone de défaillance**.</span><span class="sxs-lookup"><span data-stu-id="3a165-139">In the **Fault area** field, enter a name for the fault area.</span></span>
4. <span data-ttu-id="3a165-140">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="3a165-140">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="3a165-141">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="3a165-141">Select **Save**.</span></span>

## <a name="create-fault-types"></a><span data-ttu-id="3a165-142">Créer des types de défaillance</span><span class="sxs-lookup"><span data-stu-id="3a165-142">Create fault types</span></span>

<span data-ttu-id="3a165-143">Procédez comme suit pour créer une liste des types de défaillance qui peuvent être utilisés dans le concepteur de défaillance.</span><span class="sxs-lookup"><span data-stu-id="3a165-143">Follow these steps to create a list of fault types that can be used in the fault designer.</span></span>

1. <span data-ttu-id="3a165-144">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Problème** \> **Types de défaillance**.</span><span class="sxs-lookup"><span data-stu-id="3a165-144">Select **Asset management** \> **Setup** \> **Fault** \> **Fault types**.</span></span>
2. <span data-ttu-id="3a165-145">Sélectionnez **Nouveau** pour créer un enregistrement.</span><span class="sxs-lookup"><span data-stu-id="3a165-145">Select **New** to create a record.</span></span>
3. <span data-ttu-id="3a165-146">Dans le champ **Type de défaillance**, entrez un nom pour le type de défaillance.</span><span class="sxs-lookup"><span data-stu-id="3a165-146">In the **Fault type** field, enter a name for the fault type.</span></span>
4. <span data-ttu-id="3a165-147">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="3a165-147">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="3a165-148">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="3a165-148">Select **Save**.</span></span>

## <a name="set-up-the-fault-designer"></a><span data-ttu-id="3a165-149">Paramétrer le concepteur de défaillance</span><span class="sxs-lookup"><span data-stu-id="3a165-149">Set up the fault designer</span></span>

<span data-ttu-id="3a165-150">Dans le concepteur de défaillance, vous devez paramétrer des données de défaillance sur les types d'actifs.</span><span class="sxs-lookup"><span data-stu-id="3a165-150">In the fault designer, you set up fault data on asset types.</span></span>

1. <span data-ttu-id="3a165-151">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Problème** \> **Concepteur de défaillance**.</span><span class="sxs-lookup"><span data-stu-id="3a165-151">Select **Asset management** \> **Setup** \> **Fault** \> **Fault designer**.</span></span>
2. <span data-ttu-id="3a165-152">Dans le volet gauche, sélectionnez le type d'actif pour lequel paramétrer un enregistrement de défaillance.</span><span class="sxs-lookup"><span data-stu-id="3a165-152">In the left pane, select the type of asset to set up a fault record for.</span></span>
3. <span data-ttu-id="3a165-153">Dans le raccourci **Symptôme de défaillance**, sélectionnez **Ajouter une ligne**, puis, dans le champ **Symptôme de défaillance**, sélectionnez un symptôme de défaillance.</span><span class="sxs-lookup"><span data-stu-id="3a165-153">On the **Fault symptom** FastTab, select **Add line**, and then, in the **Fault symptom** field, select a fault symptom.</span></span>
4. <span data-ttu-id="3a165-154">Dans le raccourci **Zone de défaillance**, sélectionnez **Ajouter une ligne**, puis, dans le champ **Zone de défaillance**, sélectionnez une zone de défaillance.</span><span class="sxs-lookup"><span data-stu-id="3a165-154">On the **Fault area** FastTab, select **Add line**, and then, in the **Fault area** field select a fault area.</span></span>
5. <span data-ttu-id="3a165-155">Dans le raccourci **Type de défaillance**, sélectionnez **Ajouter une ligne**, puis, dans le champ **Type de défaillance**, sélectionnez un type de défaillance.</span><span class="sxs-lookup"><span data-stu-id="3a165-155">On the **Fault type** FastTab, select **Add line**, and then, in the **Fault type** field, select a fault type.</span></span>
6. <span data-ttu-id="3a165-156">Pour créer rapidement des combinaisons de tous les symptômes, de toutes les zones, et de tous les types de défaillance existants pour le type d'actif sélectionné, sélectionnez **Créer des combinaisons de défaillance**.</span><span class="sxs-lookup"><span data-stu-id="3a165-156">To quickly create combinations of all existing fault symptoms, areas, and types for the selected asset type, select **Create fault combinations**.</span></span> <span data-ttu-id="3a165-157">Cette fonction est utile si vous avez ajouté beaucoup de symptômes, de zones, et de types de défaillance.</span><span class="sxs-lookup"><span data-stu-id="3a165-157">This function is useful if you've added many fault symptoms, areas, and types.</span></span> <span data-ttu-id="3a165-158">Il est plus facile de supprimer les lignes des combinaisons qui ne conviennent pas pour le type d'actif que de créer de nouvelles lignes manuellement.</span><span class="sxs-lookup"><span data-stu-id="3a165-158">It's easier to delete the lines for any combinations that aren't relevant to the asset type than to create new lines manually.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3a165-159">Copiez le paramétrage des symptômes, des zones et des types de défaillance d'un type d'actif sur le type d'actif sélectionné, sélectionnez **Copier à partir du type d'actif**.</span><span class="sxs-lookup"><span data-stu-id="3a165-159">To copy the setup of fault symptoms, areas, and types from one asset type to the selected asset type, select **Copy from asset type**.</span></span>

7. <span data-ttu-id="3a165-160">Sélectionnez **Enregistrer** pour enregistrer les modifications.</span><span class="sxs-lookup"><span data-stu-id="3a165-160">Select **Save** to save your changes.</span></span>

![Figure 1](media/21-setup-for-work-orders.png)

## <a name="create-fault-causes"></a><span data-ttu-id="3a165-162">Créer des causes de défaillance</span><span class="sxs-lookup"><span data-stu-id="3a165-162">Create fault causes</span></span>

<span data-ttu-id="3a165-163">Procédez comme suit pour créer une liste des causes connues de défaillance pouvant être ajoutées à un ordre de travail ou à une demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="3a165-163">Follow these steps to create a list of known fault causes that can be added to a work order or a maintenance request.</span></span>

1. <span data-ttu-id="3a165-164">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Problème** \> **Causes de défaillance**.</span><span class="sxs-lookup"><span data-stu-id="3a165-164">Select **Asset management** \> **Setup** \> **Fault** \> **Fault causes**.</span></span>
2. <span data-ttu-id="3a165-165">Sélectionnez **Nouveau** pour créer un enregistrement.</span><span class="sxs-lookup"><span data-stu-id="3a165-165">Select **New** to create a record.</span></span>
3. <span data-ttu-id="3a165-166">Dans le champ **Cause de défaillance**, entrez un nom pour la cause de défaillance.</span><span class="sxs-lookup"><span data-stu-id="3a165-166">In the **Fault cause** field, enter a name for the fault cause.</span></span>
4. <span data-ttu-id="3a165-167">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="3a165-167">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="3a165-168">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="3a165-168">Select **Save**.</span></span>

## <a name="create-fault-remedies"></a><span data-ttu-id="3a165-169">Créer des solutions aux défaillances</span><span class="sxs-lookup"><span data-stu-id="3a165-169">Create fault remedies</span></span>

<span data-ttu-id="3a165-170">Procédez comme suit pour créer une liste de suggestions de résolution et de réparation pouvant être ajoutées à un ordre de travail ou à une demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="3a165-170">Follow these steps to create a list of suggestions for remedy and repair that can be added to a work order or a maintenance request.</span></span>

1. <span data-ttu-id="3a165-171">Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Problème** \> **Solutions aux défaillances**.</span><span class="sxs-lookup"><span data-stu-id="3a165-171">Select **Asset management** \> **Setup** \> **Fault** \> **Fault remedies**.</span></span>
2. <span data-ttu-id="3a165-172">Sélectionnez **Nouveau** pour créer un enregistrement.</span><span class="sxs-lookup"><span data-stu-id="3a165-172">Select **New** to create a record.</span></span>
3. <span data-ttu-id="3a165-173">Entrez un nom pour la solution à la défaillance dans le champ **Solutions aux défaillances**.</span><span class="sxs-lookup"><span data-stu-id="3a165-173">In the **Fault remedy** field, enter a name for the fault remedy.</span></span>
4. <span data-ttu-id="3a165-174">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="3a165-174">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="3a165-175">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="3a165-175">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="3a165-176">Vous pouvez modifier les noms des symptômes, zones, types, causes, et recours pour les défaillances dont vous disposez comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="3a165-176">You can change the names of your fault symptoms, areas, types, causes, and remedies as you require.</span></span> <span data-ttu-id="3a165-177">Les modifications apportées au nom sont répercutées automatiquement dans les enregistrements de défaillance liés.</span><span class="sxs-lookup"><span data-stu-id="3a165-177">The name changes are automatically reflected in the related fault registrations.</span></span>
