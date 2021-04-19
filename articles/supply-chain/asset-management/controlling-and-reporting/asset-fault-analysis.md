---
title: Analyse des problèmes d’actifs
description: Cette rubrique explique les analyses de défaillance d’actif dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectFaultCalculate
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: a26ee80eb52e40b60ace9b1494b3512d85f04cfe
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837871"
---
# <a name="asset-fault-analysis"></a><span data-ttu-id="1b53a-103">Analyse des problèmes d’actifs</span><span class="sxs-lookup"><span data-stu-id="1b53a-103">Asset fault analysis</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="1b53a-104">Dans le module Gestion des actifs, vous pouvez analyser les enregistrements de défaillance d’actif afin d’obtenir une vue d’ensemble du nombre total de défaillances consignées durant une période spécifique.</span><span class="sxs-lookup"><span data-stu-id="1b53a-104">In Asset Management, you can analyze asset fault registrations to get an overview of the total number of faults registered during a specific period.</span></span> <span data-ttu-id="1b53a-105">Les enregistrements de défaillance peuvent être analysés à partir de perspectives différentes, par exemple en fonction des actifs, des types d’actifs, des postes techniques, des symptômes de défaillance, ou des types de défaillance.</span><span class="sxs-lookup"><span data-stu-id="1b53a-105">Fault registrations can be analyzed from different perspectives, for example with focus on assets, asset types, functional locations, fault symptoms, or fault types.</span></span>

1. <span data-ttu-id="1b53a-106">Cliquez sur **Gestion des actifs** > **Recherches** > **Défaillances des actifs** > **Analyses des défaillances des actifs**.</span><span class="sxs-lookup"><span data-stu-id="1b53a-106">Click **Asset management** > **Inquiries** > **Asset fault** > **Asset fault analysis**.</span></span>

2. <span data-ttu-id="1b53a-107">Dans la boîte de dialogue **Calcul d’analyse des défaillances des actifs**, vous pouvez utiliser le champ **Niveau** pour indiquer quel niveau de détail vous souhaitez dans les lignes de défaillance d’actif en fonction des postes techniques.</span><span class="sxs-lookup"><span data-stu-id="1b53a-107">In the **Asset fault analysis calculation** dialog, you can use the **Level** field to indicate how detailed you want the asset fault lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="1b53a-108">Par exemple, si vous insérez le chiffre 1 dans le champ, et que vous avez une structure de poste technique à plusieurs niveaux, toutes les lignes de défaillance d’actif pour un poste technique s’affichent dans le niveau supérieur et il est donc possible d’ajouter des heures à partir des postes techniques situés à un niveau inférieur.</span><span class="sxs-lookup"><span data-stu-id="1b53a-108">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all asset fault lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
        
    <span data-ttu-id="1b53a-109">Par exemple, si vous insérez le chiffre 0 dans le champ **Niveau**, un résultat détaillé s’affiche et indique toutes les lignes de défaillance d’actif sur tout le niveau du poste technique auquel elles sont liées.</span><span class="sxs-lookup"><span data-stu-id="1b53a-109">If you insert the number "0" in the **Level** field, you will see a detailed result showing all asset fault lines on all the functional location level to which they are related.</span></span>

3. <span data-ttu-id="1b53a-110">Pour limiter la recherche, vous pouvez sélectionner des actifs, des dates de défaillance, des causes de défaillance et des solutions spécifiques sur l’organisateur **Enregistrements à inclure**.</span><span class="sxs-lookup"><span data-stu-id="1b53a-110">If you want to limit the search, you can select specific assets, fault dates, fault causes, and fault remedies on the **Records to include** FastTab.</span></span>

4. <span data-ttu-id="1b53a-111">Cliquez sur **OK** pour démarrer le calcul.</span><span class="sxs-lookup"><span data-stu-id="1b53a-111">Click **OK** to start the calculation.</span></span>

5. <span data-ttu-id="1b53a-112">Dans l’onglet **Analyses des défaillances des actifs**, cliquez sur un ou plusieurs boutons **Grouper par** pour afficher le niveau de détail à afficher.</span><span class="sxs-lookup"><span data-stu-id="1b53a-112">On the **Asset fault analysis** tab, click one or more **Group by** buttons to display the detail level you want to see.</span></span> <span data-ttu-id="1b53a-113">Les boutons actionnés sont mis en surbrillance.</span><span class="sxs-lookup"><span data-stu-id="1b53a-113">Activated buttons are highlighted.</span></span> <span data-ttu-id="1b53a-114">Activez ou désactivez les boutons en cliquant dessus.</span><span class="sxs-lookup"><span data-stu-id="1b53a-114">Activate or deactivate buttons by clicking on them.</span></span>

6. <span data-ttu-id="1b53a-115">Cliquez sur **Mettre à jour les calculs** pour afficher vos sélections à l’écran.</span><span class="sxs-lookup"><span data-stu-id="1b53a-115">Click **Update calculations** to show your selections on the screen.</span></span> 

>[!NOTE]
><span data-ttu-id="1b53a-116">Chaque fois que vous activez ou de désactiver un bouton **Grouper par**, n’oubliez pas de cliquer sur le bouton **Mettre à jour les calculs**.</span><span class="sxs-lookup"><span data-stu-id="1b53a-116">Every time you activate or deactivate a **Group by** button, remember to click the **Update calculations** button.</span></span> <span data-ttu-id="1b53a-117">Cela est nécessaire car un grand nombre de données sont traitées lorsque vous recalculez la probabilité de défaillance.</span><span class="sxs-lookup"><span data-stu-id="1b53a-117">This is required because a large amount of data is processed as you are recalculating fault probability.</span></span>

## <a name="examples"></a><span data-ttu-id="1b53a-118">Exemples</span><span class="sxs-lookup"><span data-stu-id="1b53a-118">Examples</span></span>

<span data-ttu-id="1b53a-119">Il existe de nombreuses façons d’analyser les enregistrements de défaillance.</span><span class="sxs-lookup"><span data-stu-id="1b53a-119">There are many ways to analyze fault registrations.</span></span> <span data-ttu-id="1b53a-120">Cette section contient cinq exemples de la manière dont différentes sélections fournissent peuvent fournir plus d’analyse et de détails lors de l’analyse des enregistrements de défaillance des actifs.</span><span class="sxs-lookup"><span data-stu-id="1b53a-120">This section has five examples of how different data selections can provide more insight and detail when analyzing asset fault registrations.</span></span>

### <a name="group-by-symptoms"></a><span data-ttu-id="1b53a-121">Grouper par symptômes</span><span class="sxs-lookup"><span data-stu-id="1b53a-121">Group by symptoms</span></span>

<span data-ttu-id="1b53a-122">Dans la capture d’écran ci-dessous, seul le bouton **Symptôme** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="1b53a-122">In the screenshot below, only the **Symptom** button is selected.</span></span>

- <span data-ttu-id="1b53a-123">Les enregistrements de défaillance ont été effectués sur trois symptômes de défaillance : « Fuite d’air », « Fusible grillé » et « Équipement bloqué ».</span><span class="sxs-lookup"><span data-stu-id="1b53a-123">Fault registrations have been made on three fault symptoms: "Air leak", "Blown fuse", and "Equipment jammed".</span></span>  
- <span data-ttu-id="1b53a-124">Dans la colonne **% probabilité**, tous les pourcentages doivent totaliser 100 %.</span><span class="sxs-lookup"><span data-stu-id="1b53a-124">In the **Probability %** column, all percentages add up to 100%.</span></span> <span data-ttu-id="1b53a-125">La probabilité est basée sur tous les enregistrements de **Symptôme** de cette analyse des défaillances.</span><span class="sxs-lookup"><span data-stu-id="1b53a-125">Probability is based on all **Symptom** registrations in this fault analysis.</span></span>

![Figure 1](media/06-controlling-and-reporting.png)

### <a name="group-by-symptoms-and-time-period"></a><span data-ttu-id="1b53a-127">Grouper par symptôme et période</span><span class="sxs-lookup"><span data-stu-id="1b53a-127">Group by symptoms and time period</span></span>

<span data-ttu-id="1b53a-128">Dans le capture d’écran ci-dessous, **Année** et **Mois** ont été ajoutés pour afficher la manière dont vous pouvez afficher des enregistrements de défaillance durant une période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1b53a-128">In the screenshot below, **Year** and **Month** are added to show how you can view fault registrations during a selected period.</span></span>

- <span data-ttu-id="1b53a-129">Les symptômes de défaillance s’affichent comme des enregistrements par an/mois.</span><span class="sxs-lookup"><span data-stu-id="1b53a-129">The fault symptoms are now shown as registrations per year/month.</span></span>  
- <span data-ttu-id="1b53a-130">Dans la colonne **% probabilité**, si vous additionnez les pourcentages pour chaque mois, vous devez arriver à 100 %.</span><span class="sxs-lookup"><span data-stu-id="1b53a-130">In the **Probability %** column, if you add all percentages for each month, they add up to 100%.</span></span> <span data-ttu-id="1b53a-131">La probabilité est basée sur tous les enregistrements de **Symptôme** de cette analyse des défaillances.</span><span class="sxs-lookup"><span data-stu-id="1b53a-131">Probability is based on the **Symptom** registrations in this fault analysis.</span></span> <span data-ttu-id="1b53a-132">Si vous avez un grand nombre de lignes sur un actif, mais qu’un pourcentage élevé figure sur une ligne, cela peut indiquer un symptôme de défaillance à examiner de près pour trouver une manière de limiter le nombre d’enregistrements pour ce symptôme de défaillance.</span><span class="sxs-lookup"><span data-stu-id="1b53a-132">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault symptom to examine more closely to find a way to limit the number of registrations for that fault symptom.</span></span>

![Figure 2](media/07-controlling-and-reporting.png)

### <a name="group-by-multiple-symptoms-and-assets"></a><span data-ttu-id="1b53a-134">Grouper par plusieurs symptômes et actif</span><span class="sxs-lookup"><span data-stu-id="1b53a-134">Group by multiple symptoms and assets</span></span>

<span data-ttu-id="1b53a-135">La combinaison des actifs et d’un type d’actif est utilisée comme base pour les calculs affichés dans les trois captures d’écran ci-dessous, ce qui va augmenter le niveau de détail.</span><span class="sxs-lookup"><span data-stu-id="1b53a-135">The combination of assets and an asset type is used as a basis for the calculations shown in the three screenshots below, which will increase in detail level.</span></span>  

<span data-ttu-id="1b53a-136">En général, les boutons des groupes du volet Actions **Grouper par date**, **Grouper par actif**, **Grouper par poste technique**, ainsi que le bouton **Problème** (ID de défaillance), contiennent des périodes ou des relations entre les actifs.</span><span class="sxs-lookup"><span data-stu-id="1b53a-136">Generally, the buttons in the **Group by date**, **Group by asset**, **Group by functional location** Action Pane groups, as well as the **Fault** button (Fault ID), contain periods or asset relations.</span></span> <span data-ttu-id="1b53a-137">Les boutons **Symptôme**, **Secteur**, **Type**, **Cause** et **Remède** sont des catégorisations utilisées dans la gestion de défaillance pour analyser les enregistrements de défaillance d’actif et les domaines problématiques ponctuels.</span><span class="sxs-lookup"><span data-stu-id="1b53a-137">The **Symptom**, **Area**, **Type**, **Cause**, and **Remedy** buttons are categorizations used in fault management to analyze asset fault registrations and pinpoint problem areas.</span></span>  

<span data-ttu-id="1b53a-138">**Grouper par symptôme, actif et type d’actif**</span><span class="sxs-lookup"><span data-stu-id="1b53a-138">**Group by symptom, asset, and asset type**</span></span>

<span data-ttu-id="1b53a-139">Dans la capture d’écran ci-dessous, **Actif** et **Type d’actif** ont été ajoutés pour fournir plus de détails concernant les enregistrements de défaillance.</span><span class="sxs-lookup"><span data-stu-id="1b53a-139">In the screenshot below, **Asset** and **Asset type** were added to provide more detail regarding fault registrations.</span></span>

- <span data-ttu-id="1b53a-140">Les symptômes de défaillance sont désormais divisés dans des combinaisons **Actif** / **Type d’actif** / **Symptôme** .</span><span class="sxs-lookup"><span data-stu-id="1b53a-140">The fault symptoms are now split up in **Asset** / **Asset type** / **Symptom** combinations.</span></span>  
- <span data-ttu-id="1b53a-141">Dans la colonne **% probabilité** si vous additionnez tous les pourcentages des combinaisons **Actif** / **Type d’actif** / **Symptôme** respectivement, vous devez arriver à 100 %.</span><span class="sxs-lookup"><span data-stu-id="1b53a-141">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** respectively, they each add up to 100%.</span></span> <span data-ttu-id="1b53a-142">La probabilité est basée sur les enregistrements de **Symptôme** de cette analyse des défaillances.</span><span class="sxs-lookup"><span data-stu-id="1b53a-142">Probability is based on **Symptom** registrations in this fault analysis.</span></span> <span data-ttu-id="1b53a-143">Si vous avez un grand nombre de lignes sur un actif, mais qu’un pourcentage élevé figure sur une ligne, cela peut indiquer un symptôme de défaillance à examiner de près pour trouver une manière de limiter le nombre d’enregistrements pour ce symptôme de défaillance.</span><span class="sxs-lookup"><span data-stu-id="1b53a-143">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault symptom to examine more closely to find a way to limit the number of registrations for that fault symptom.</span></span>

![Figure 3](media/08-controlling-and-reporting.png)

<span data-ttu-id="1b53a-145">**Grouper par deux symptômes, actif et type d’actif**</span><span class="sxs-lookup"><span data-stu-id="1b53a-145">**Group by two symptoms, asset, and asset type**</span></span>

<span data-ttu-id="1b53a-146">Dans la capture d’écran ci-dessous, **Secteur** a été ajouté à **Symptôme**, **Actif** et **Type d’actif** pour fournir plus de détails concernant les enregistrements de défaillance.</span><span class="sxs-lookup"><span data-stu-id="1b53a-146">In the screenshot below, **Area** was added to **Symptom**, **Asset**, and **Asset type** to provide more detail regarding fault registrations.</span></span>

- <span data-ttu-id="1b53a-147">Dans la colonne **% probabilité** si vous additionnez tous les pourcentages des combinaisons **Actif** / **Type d’actif** / **Symptôme** d’un actif, vous devez arriver à 100 %.</span><span class="sxs-lookup"><span data-stu-id="1b53a-147">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** on an asset, they each add up to 100%.</span></span> <span data-ttu-id="1b53a-148">La probabilité est basée sur la combinaison **Symptôme** et **Zone** dans cette analyse des défaillances.</span><span class="sxs-lookup"><span data-stu-id="1b53a-148">Probability is based on the combination of **Symptom** and **Area** in this fault analysis.</span></span> <span data-ttu-id="1b53a-149">Si vous avez un grand nombre de lignes sur un actif, mais qu’un pourcentage élevé figure sur une ligne, cela peut indiquer une zone de défaillance à examiner de près pour trouver une manière de limiter le nombre d’enregistrements pour cette zone de défaillance.</span><span class="sxs-lookup"><span data-stu-id="1b53a-149">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault area to examine more closely to find a way to limit the number of registrations for that fault area.</span></span>  

![Figure 4](media/09-controlling-and-reporting.png)

<span data-ttu-id="1b53a-151">**Grouper par trois symptôme, actif et type d’actif**</span><span class="sxs-lookup"><span data-stu-id="1b53a-151">**Group by three symptom, asset, and asset type**</span></span>

<span data-ttu-id="1b53a-152">Dans le capture d’écran ci-dessous, **Type** a été ajouté, et le calcul le plus détaillé dans cet exemple s’affiche.</span><span class="sxs-lookup"><span data-stu-id="1b53a-152">In the screenshot below, **Type** was added, and the most detailed calculation in this example is shown.</span></span>
 
- <span data-ttu-id="1b53a-153">Dans la colonne **% probabilité** si vous additionnez tous les pourcentages des combinaisons **Actif** / **Type d’actif** / **Symptôme** d’un actif, vous devez arriver à 100 %.</span><span class="sxs-lookup"><span data-stu-id="1b53a-153">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** on an asset, they each add up to 100%.</span></span> <span data-ttu-id="1b53a-154">La probabilité est basée sur la combinaison **Symptôme**, **Secteur** et **Type** dans cette analyse des défaillances.</span><span class="sxs-lookup"><span data-stu-id="1b53a-154">Probability is based on the combination of **Symptom**, **Area**, and **Type** in this fault analysis.</span></span> <span data-ttu-id="1b53a-155">Si vous avez un grand nombre de lignes sur un actif, mais qu’un pourcentage élevé figure sur une ligne, cela peut indiquer un type de défaillance à examiner de près pour trouver une manière de limiter le nombre d’enregistrements pour ce type de défaillance.</span><span class="sxs-lookup"><span data-stu-id="1b53a-155">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault type to examine more closely to find a way to limit the number of registrations on that fault type.</span></span>

![Figure 5](media/10-controlling-and-reporting.png)


>[!NOTE]
><span data-ttu-id="1b53a-157">Pour obtenir une vue d’ensemble de tous les enregistrements de défaillance créés sur les ordres de travail et les demandes de maintenance, cliquez sur **Gestion des actifs** > **Recherches** > **Défaillance des actifs** > **Défaillance des actifs**.</span><span class="sxs-lookup"><span data-stu-id="1b53a-157">For an overview of all fault registrations created on work orders and maintenance requests, click **Asset management** > **Inquiries** > **Asset fault** > **Asset faults**.</span></span> <span data-ttu-id="1b53a-158">Dans la page **Défaillances des actifs**, sélectionnez un enregistrement de défaillance d’actif et développez le volet **Informations associées** pour afficher les informations concernant l’ordre de travail ou la demande de maintenance.</span><span class="sxs-lookup"><span data-stu-id="1b53a-158">On the **Asset faults** page, select an asset fault registration and expand the **Related information** pane to see information regarding the related work order or maintenance request.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]