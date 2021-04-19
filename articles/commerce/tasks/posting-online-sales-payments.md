---
title: Validation des ventes et des paiements en ligne
description: Cette procédure décrit la configuration et l’exécution d’un traitement par lots récurrent pour créer des commandes client et des paiements pour les transactions de magasin en ligne.
author: psimolin
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a2e482b0fb5f2cf67e687c2b278bc5b54ad09839
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802669"
---
# <a name="posting-of-online-sales-and-payments"></a><span data-ttu-id="0c866-103">Validation des ventes et des paiements en ligne</span><span class="sxs-lookup"><span data-stu-id="0c866-103">Posting of online sales and payments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0c866-104">Cette procédure décrit la configuration et l’exécution d’un traitement par lots récurrent pour créer des commandes client et des paiements pour les transactions de magasin en ligne.</span><span class="sxs-lookup"><span data-stu-id="0c866-104">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span>

<span data-ttu-id="0c866-105">La validation des ventes et des paiements en ligne est un processus en deux étapes.</span><span class="sxs-lookup"><span data-stu-id="0c866-105">Posting online sales and payments is a two-stage process.</span></span>

- <span data-ttu-id="0c866-106">Extraction des données de transaction du commerce en ligne au siège social.</span><span class="sxs-lookup"><span data-stu-id="0c866-106">Pulling the online commerce transaction data in HQ.</span></span>
- <span data-ttu-id="0c866-107">Synchronisation des commandes pour créer des commandes client au siège social.</span><span class="sxs-lookup"><span data-stu-id="0c866-107">Synchronizing orders to create sales orders in HQ.</span></span>

<span data-ttu-id="0c866-108">L’extraction des données de transaction en ligne peut se faire soit manuellement en exécutant la tâche P, soit en créant un traitement par lots récurrent.</span><span class="sxs-lookup"><span data-stu-id="0c866-108">Pulling the online transaction data can be done either by manually running the P-job or by creating a recurrent batch job.</span></span>

### <a name="manually-running-the-p-job"></a><span data-ttu-id="0c866-109">Exécution manuelle de la tâche P</span><span class="sxs-lookup"><span data-stu-id="0c866-109">Manually running the P-job</span></span>

1. <span data-ttu-id="0c866-110">Accédez à Tous les espaces de travail > Informatique Retail et Commerce.</span><span class="sxs-lookup"><span data-stu-id="0c866-110">Go to All workspaces > Retail and Commerce IT.</span></span>
2. <span data-ttu-id="0c866-111">Cliquez sur Programme de distribution.</span><span class="sxs-lookup"><span data-stu-id="0c866-111">Click Distribution schedule.</span></span>
3. <span data-ttu-id="0c866-112">Sélectionnez P-0001.</span><span class="sxs-lookup"><span data-stu-id="0c866-112">Select P-0001.</span></span>
4. <span data-ttu-id="0c866-113">Ajustez les groupes de base de données des canaux, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="0c866-113">Adjust channel database groups, if required.</span></span>
5. <span data-ttu-id="0c866-114">Cliquez sur Exécuter maintenant.</span><span class="sxs-lookup"><span data-stu-id="0c866-114">Click Run now.</span></span>
6. <span data-ttu-id="0c866-115">Cliquez sur Oui.</span><span class="sxs-lookup"><span data-stu-id="0c866-115">Click Yes.</span></span>

### <a name="scheduling-a-recurring-p-job"></a><span data-ttu-id="0c866-116">Planification d’une tâche P récurrente</span><span class="sxs-lookup"><span data-stu-id="0c866-116">Scheduling a recurring P-job</span></span>

1. <span data-ttu-id="0c866-117">Accédez à Tous les espaces de travail > Informatique Retail et Commerce.</span><span class="sxs-lookup"><span data-stu-id="0c866-117">Go to All workspaces > Retail and Commerce IT.</span></span>
2. <span data-ttu-id="0c866-118">Cliquez sur Programme de distribution.</span><span class="sxs-lookup"><span data-stu-id="0c866-118">Click Distribution schedule.</span></span>
3. <span data-ttu-id="0c866-119">Sélectionnez P-0001.</span><span class="sxs-lookup"><span data-stu-id="0c866-119">Select P-0001.</span></span>
4. <span data-ttu-id="0c866-120">Cliquez sur Créer un traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="0c866-120">Click Create batch job.</span></span>
5. <span data-ttu-id="0c866-121">Cliquez sur Exécuter à l’arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="0c866-121">Click Run in the background.</span></span>
5. <span data-ttu-id="0c866-122">Activez le traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="0c866-122">Enable Batch processing.</span></span>
6. <span data-ttu-id="0c866-123">Cliquez sur Répétition.</span><span class="sxs-lookup"><span data-stu-id="0c866-123">Click Recurrence..</span></span>
7. <span data-ttu-id="0c866-124">Sélectionnez l’option Pas de date de fin.</span><span class="sxs-lookup"><span data-stu-id="0c866-124">Select the No end date option.</span></span>
8. <span data-ttu-id="0c866-125">Dans le champ Nombre, saisissez l’intervalle entre les exécutions en minutes.</span><span class="sxs-lookup"><span data-stu-id="0c866-125">In the Count field, enter interval between the runs in minutes.</span></span> <span data-ttu-id="0c866-126">Généralement ce serait 5-10.</span><span class="sxs-lookup"><span data-stu-id="0c866-126">Typically this would be 5-10.</span></span>
9. <span data-ttu-id="0c866-127">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0c866-127">Click OK.</span></span>
10. <span data-ttu-id="0c866-128">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0c866-128">Click OK.</span></span>

<span data-ttu-id="0c866-129">Les commandes peuvent être synchronisées soit en exécutant manuellement la tâche « Synchroniser des commandes », soit en créant un traitement par lots récurrent.</span><span class="sxs-lookup"><span data-stu-id="0c866-129">Orders can be synchronized either by manually running the "Synchronize orders"-job or by creating a recurring batch job.</span></span>

### <a name="manually-running-order-synchronization"></a><span data-ttu-id="0c866-130">Exécution d’une synchronisation manuelle d’une commande</span><span class="sxs-lookup"><span data-stu-id="0c866-130">Manually running order synchronization</span></span> 

<span data-ttu-id="0c866-131">Suivez ces étapes pour exécuter manuellement la tâche « Synchroniser les commandes » une seule fois.</span><span class="sxs-lookup"><span data-stu-id="0c866-131">Follow these steps to manually run "Synchronize orders" job once.</span></span>

1. <span data-ttu-id="0c866-132">Accédez à Tous les espaces de travail > Finances du magasin.</span><span class="sxs-lookup"><span data-stu-id="0c866-132">Go to All workspaces > Store financials.</span></span>
2. <span data-ttu-id="0c866-133">Cliquez sur Synchroniser les commandes.</span><span class="sxs-lookup"><span data-stu-id="0c866-133">Click Synchronize orders.</span></span>
3. <span data-ttu-id="0c866-134">Dans le champ Hiérarchie d’organisation, sélectionnez Magasins par région.</span><span class="sxs-lookup"><span data-stu-id="0c866-134">In the Organization hierarchy field, select 'Stores by Region'.</span></span>
    * <span data-ttu-id="0c866-135">Sélectionnez un magasin en ligne spécifique ou un nœud si vous souhaitez créer le traitement par lots pour un groupe de magasins.</span><span class="sxs-lookup"><span data-stu-id="0c866-135">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="0c866-136">Cliquez sur la flèche pour ajouter votre sélection.</span><span class="sxs-lookup"><span data-stu-id="0c866-136">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="0c866-137">Cliquez sur l’onglet Exécuter à l’arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="0c866-137">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="0c866-138">Désactiver le traitement par lots</span><span class="sxs-lookup"><span data-stu-id="0c866-138">Disable Batch processing</span></span>
6. <span data-ttu-id="0c866-139">Cliquez sur Répétition.</span><span class="sxs-lookup"><span data-stu-id="0c866-139">Click Recurrence.</span></span>
7. <span data-ttu-id="0c866-140">Sélectionner l’option Fin après le</span><span class="sxs-lookup"><span data-stu-id="0c866-140">Select End After option</span></span>
8. <span data-ttu-id="0c866-141">Dans le champ Fin après le, saisissez 1.</span><span class="sxs-lookup"><span data-stu-id="0c866-141">In the End After field, enter 1.</span></span>
9. <span data-ttu-id="0c866-142">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0c866-142">Click OK.</span></span>
10. <span data-ttu-id="0c866-143">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0c866-143">Click OK.</span></span>

### <a name="scheduling-recurring-order-synchronization"></a><span data-ttu-id="0c866-144">Planification de la synchronisation des commandes récurrentes</span><span class="sxs-lookup"><span data-stu-id="0c866-144">Scheduling recurring order synchronization</span></span>

<span data-ttu-id="0c866-145">Cette procédure décrit la configuration et l’exécution d’un traitement par lots récurrent pour créer des commandes client et des paiements pour les transactions de magasin en ligne.</span><span class="sxs-lookup"><span data-stu-id="0c866-145">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span> <span data-ttu-id="0c866-146">Cette procédure utilise la société USRT dans les données de démonstration.</span><span class="sxs-lookup"><span data-stu-id="0c866-146">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="0c866-147">Accédez à Tous les espaces de travail > Finances du magasin.</span><span class="sxs-lookup"><span data-stu-id="0c866-147">Go to All workspaces > Store financials.</span></span>
2. <span data-ttu-id="0c866-148">Cliquez sur Synchroniser les commandes.</span><span class="sxs-lookup"><span data-stu-id="0c866-148">Click Synchronize orders.</span></span>
3. <span data-ttu-id="0c866-149">Dans le champ Hiérarchie d’organisation, sélectionnez Magasins par région.</span><span class="sxs-lookup"><span data-stu-id="0c866-149">In the Organization hierarchy field, select 'Stores by Region'.</span></span>
    * <span data-ttu-id="0c866-150">Sélectionnez un magasin en ligne spécifique ou un nœud si vous souhaitez créer le traitement par lots pour un groupe de magasins.</span><span class="sxs-lookup"><span data-stu-id="0c866-150">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="0c866-151">Cliquez sur la flèche pour ajouter votre sélection.</span><span class="sxs-lookup"><span data-stu-id="0c866-151">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="0c866-152">Cliquez sur l’onglet Exécuter à l’arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="0c866-152">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="0c866-153">Activer le traitement par lots</span><span class="sxs-lookup"><span data-stu-id="0c866-153">Enable Batch processing</span></span>
6. <span data-ttu-id="0c866-154">Cliquez sur Répétition.</span><span class="sxs-lookup"><span data-stu-id="0c866-154">Click Recurrence.</span></span>
7. <span data-ttu-id="0c866-155">Sélectionnez l’option Pas de date de fin.</span><span class="sxs-lookup"><span data-stu-id="0c866-155">Select the No end date option.</span></span>
8. <span data-ttu-id="0c866-156">Dans le champ Nombre, saisissez l’intervalle entre les exécutions en minutes.</span><span class="sxs-lookup"><span data-stu-id="0c866-156">In the Count field, enter interval between the runs in minutes.</span></span> <span data-ttu-id="0c866-157">Généralement ce serait 2-20</span><span class="sxs-lookup"><span data-stu-id="0c866-157">Typically this would be 2-20</span></span>
9. <span data-ttu-id="0c866-158">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0c866-158">Click OK.</span></span>
10. <span data-ttu-id="0c866-159">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="0c866-159">Click OK.</span></span>

## <a name="data-entities-involved-in-the-process"></a><span data-ttu-id="0c866-160">Entités des données impliquées dans le processus</span><span class="sxs-lookup"><span data-stu-id="0c866-160">Data entities involved in the process</span></span>

- <span data-ttu-id="0c866-161">RetailTransactionTable</span><span class="sxs-lookup"><span data-stu-id="0c866-161">RetailTransactionTable</span></span>
- <span data-ttu-id="0c866-162">RetailTransactionAddressTrans</span><span class="sxs-lookup"><span data-stu-id="0c866-162">RetailTransactionAddressTrans</span></span>
- <span data-ttu-id="0c866-163">RetailTransactionInfocodeTrans</span><span class="sxs-lookup"><span data-stu-id="0c866-163">RetailTransactionInfocodeTrans</span></span>
- <span data-ttu-id="0c866-164">RetailTransactionTaxTrans</span><span class="sxs-lookup"><span data-stu-id="0c866-164">RetailTransactionTaxTrans</span></span>
- <span data-ttu-id="0c866-165">RetailTransactionSalesTrans</span><span class="sxs-lookup"><span data-stu-id="0c866-165">RetailTransactionSalesTrans</span></span>
- <span data-ttu-id="0c866-166">RetailTransactionTaxMeasure</span><span class="sxs-lookup"><span data-stu-id="0c866-166">RetailTransactionTaxMeasure</span></span>
- <span data-ttu-id="0c866-167">RetailTransactionDiscountTrans</span><span class="sxs-lookup"><span data-stu-id="0c866-167">RetailTransactionDiscountTrans</span></span>
- <span data-ttu-id="0c866-168">RetailTransactionTaxTransGTE</span><span class="sxs-lookup"><span data-stu-id="0c866-168">RetailTransactionTaxTransGTE</span></span>
- <span data-ttu-id="0c866-169">RetailTransactionMarkupTrans</span><span class="sxs-lookup"><span data-stu-id="0c866-169">RetailTransactionMarkupTrans</span></span>
- <span data-ttu-id="0c866-170">RetailTransactionPaymentTrans</span><span class="sxs-lookup"><span data-stu-id="0c866-170">RetailTransactionPaymentTrans</span></span>
- <span data-ttu-id="0c866-171">RetailTransactionAttributeTrans</span><span class="sxs-lookup"><span data-stu-id="0c866-171">RetailTransactionAttributeTrans</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]