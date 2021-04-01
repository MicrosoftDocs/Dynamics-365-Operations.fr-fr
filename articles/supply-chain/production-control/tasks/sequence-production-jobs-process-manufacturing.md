---
title: Classer les tâches de production pour le traitement de la production
description: Cette procédure utilise la peinture comme exemple pour indiquer comment séquencer des ordres prévisionnels selon la priorité en matière de couleur et de taille de colis.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransPo, PMFSeqReqRouteChangesListPage, PMFSeqReqRoute, PMFSeqReqRouteChanges, PMFSeqReqSchedDetailsFactBox, PMFSequenceGroup, PMFSequenceItemTable, PMFSequenceTable, PmfSeqWrkCtrCapRes
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d9ca04c140e7e7810e84a9efe73a6d97a7525ea1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231910"
---
# <a name="sequence-production-jobs-for-process-manufacturing"></a><span data-ttu-id="160da-103">Classer les tâches de production pour le traitement de la production</span><span class="sxs-lookup"><span data-stu-id="160da-103">Sequence production jobs for process manufacturing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="160da-104">Cette procédure utilise la peinture comme exemple pour indiquer comment séquencer des ordres prévisionnels selon la priorité en matière de couleur et de taille de colis.</span><span class="sxs-lookup"><span data-stu-id="160da-104">This procedure uses paint products as an example to show how to sequence planned orders according to the priority of color and package size.</span></span> <span data-ttu-id="160da-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USPI.</span><span class="sxs-lookup"><span data-stu-id="160da-105">The demo data company used to create this procedure is USPI.</span></span> <span data-ttu-id="160da-106">Cette procédure est destinée au gestionnaire de production.</span><span class="sxs-lookup"><span data-stu-id="160da-106">This procedure is intended for the production planner.</span></span>


## <a name="run-master-planning-for-uspi"></a><span data-ttu-id="160da-107">Exécuter la planification pour USPI</span><span class="sxs-lookup"><span data-stu-id="160da-107">Run master planning for USPI</span></span>
1. <span data-ttu-id="160da-108">Accédez à Planification > Planification > Exécuter > Planification.</span><span class="sxs-lookup"><span data-stu-id="160da-108">Go to Master planning > Master planning > Run > Master planning.</span></span>
2. <span data-ttu-id="160da-109">Dans le champ Plan général, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="160da-109">In the Master plan field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="160da-110">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="160da-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="160da-111">Sélectionnez Programme.</span><span class="sxs-lookup"><span data-stu-id="160da-111">Select MasterPlan.</span></span>  
4. <span data-ttu-id="160da-112">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="160da-112">Click OK.</span></span>
    * <span data-ttu-id="160da-113">Cela démarre la planification, notamment le processus de séquence.</span><span class="sxs-lookup"><span data-stu-id="160da-113">This starts Master Planning, including the sequence process.</span></span> <span data-ttu-id="160da-114">Ce processus peut prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="160da-114">This process can take a few minutes.</span></span>  

## <a name="view-planned-orders-for-the-paint-products"></a><span data-ttu-id="160da-115">Afficher les ordres prévisionnels pour la peinture</span><span class="sxs-lookup"><span data-stu-id="160da-115">View planned orders for the paint products</span></span>
1. <span data-ttu-id="160da-116">Accédez à Planification > Planification > Ordres prévisionnels.</span><span class="sxs-lookup"><span data-stu-id="160da-116">Go to Master planning > Master planning > Planned orders.</span></span>
2. <span data-ttu-id="160da-117">Développez le récapitulatif Détails de l’article.</span><span class="sxs-lookup"><span data-stu-id="160da-117">Expand the Item details FactBox.</span></span>
3. <span data-ttu-id="160da-118">Développez le récapitulatif Détails du programme.</span><span class="sxs-lookup"><span data-stu-id="160da-118">Expand the Schedule details FactBox.</span></span>
4. <span data-ttu-id="160da-119">Dans le champ Régime, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="160da-119">In the Plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="160da-120">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="160da-120">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="160da-121">Sélectionnez Programme.</span><span class="sxs-lookup"><span data-stu-id="160da-121">Select MasterPlan.</span></span>  
6. <span data-ttu-id="160da-122">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="160da-122">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="160da-123">Utilisez le filtre rapide pour filtrer sur le champ Numéro d’article avec une valeur de « P300 ».</span><span class="sxs-lookup"><span data-stu-id="160da-123">Use the Quick Filter to filter on the Item number field with a value of 'P300'.</span></span>
    * <span data-ttu-id="160da-124">Déverrouillez pour faire défiler vers la droite pour consulter la date de commande et la date de livraison.</span><span class="sxs-lookup"><span data-stu-id="160da-124">Unlock to scroll to the right to see the order date and delivery date.</span></span> <span data-ttu-id="160da-125">Notez que ces articles ont une date de commande définie sur Aujourd’hui et les dates de livraison pour les ordres prévisionnels ne sont pas séquencées après la priorité de couleur et la taille du colis, comme indiqué dans le nom de produit.</span><span class="sxs-lookup"><span data-stu-id="160da-125">Notice that these items have an order date of Today and the delivery dates for the planned orders are not sequenced after the priority of color and package size, as shown in the product name.</span></span> <span data-ttu-id="160da-126">Vous pouvez pointer sur un numéro d’article pour afficher le nom du produit et la priorité.</span><span class="sxs-lookup"><span data-stu-id="160da-126">You can hover over an item number to see the product name and priority.</span></span>  

## <a name="sequence-planned-orders-for-paint"></a><span data-ttu-id="160da-127">Séquencer les ordres prévisionnels pour la peinture</span><span class="sxs-lookup"><span data-stu-id="160da-127">Sequence planned orders for paint</span></span>
1. <span data-ttu-id="160da-128">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="160da-128">Close the page.</span></span>
2. <span data-ttu-id="160da-129">Accédez à Planification > Planification > Ordre prévisionnel séquencé.</span><span class="sxs-lookup"><span data-stu-id="160da-129">Go to Master planning > Master planning > Sequenced planned orders.</span></span>
3. <span data-ttu-id="160da-130">Développez le récapitulatif Détails de l’article.</span><span class="sxs-lookup"><span data-stu-id="160da-130">Expand the Item details FactBox.</span></span>
4. <span data-ttu-id="160da-131">Développez le récapitulatif Détails du programme.</span><span class="sxs-lookup"><span data-stu-id="160da-131">Expand the Schedule details FactBox.</span></span>
    * <span data-ttu-id="160da-132">Remarque : Ici vous voyez que la date/l’heure de début pour les ordres prévisionnels sont séquencées selon la couleur et la taille du colis dans un intervalle de 28 jours.</span><span class="sxs-lookup"><span data-stu-id="160da-132">Note: Here you see that the Start date/time for the planned orders are sequenced according to color and package size within a bucket period of 28 days.</span></span> <span data-ttu-id="160da-133">Ces périodes sont définies par un numéro dans le champ Campagne.</span><span class="sxs-lookup"><span data-stu-id="160da-133">These periods are defined by a number in the field Campaign.</span></span> <span data-ttu-id="160da-134">L’écran Ordres prévisionnels séquencés agit comme l’écran d’ordre prévisionnel classique, et le responsable de production peut y confirmer les ordres prévisionnels.</span><span class="sxs-lookup"><span data-stu-id="160da-134">The sequenced planned order form acts like the typical planned order form, and the production planner can firm the planned orders here.</span></span>  
5. <span data-ttu-id="160da-135">Marquez toutes les lignes.</span><span class="sxs-lookup"><span data-stu-id="160da-135">Mark all rows.</span></span>
6. <span data-ttu-id="160da-136">Cliquez sur Accepter.</span><span class="sxs-lookup"><span data-stu-id="160da-136">Click Accept.</span></span>
    * <span data-ttu-id="160da-137">Cela mettra les ordres prévisionnels à jour avec l’action de séquence sélectionnée, soit Ajourner soit Avancer.</span><span class="sxs-lookup"><span data-stu-id="160da-137">This will update the planned orders with the selected sequence action of either Postpone or Advance.</span></span>  

## <a name="verify-the-sequence-of-the-planned-orders"></a><span data-ttu-id="160da-138">Vérifier la séquence des ordres prévisionnels</span><span class="sxs-lookup"><span data-stu-id="160da-138">Verify the sequence of the planned orders</span></span>
1. <span data-ttu-id="160da-139">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="160da-139">Close the page.</span></span>
2. <span data-ttu-id="160da-140">Accédez à Planification > Planification > Ordres prévisionnels.</span><span class="sxs-lookup"><span data-stu-id="160da-140">Go to Master planning > Master planning > Planned orders.</span></span>
3. <span data-ttu-id="160da-141">Développez le récapitulatif Détails de l’article.</span><span class="sxs-lookup"><span data-stu-id="160da-141">Expand the Item details FactBox.</span></span>
4. <span data-ttu-id="160da-142">Développez le récapitulatif Détails du programme.</span><span class="sxs-lookup"><span data-stu-id="160da-142">Expand the Schedule details FactBox.</span></span>
5. <span data-ttu-id="160da-143">Dans le champ Régime, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="160da-143">In the Plan field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="160da-144">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="160da-144">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="160da-145">Sélectionnez Programme.</span><span class="sxs-lookup"><span data-stu-id="160da-145">Select MasterPlan.</span></span>  
7. <span data-ttu-id="160da-146">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="160da-146">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="160da-147">Utilisez le filtre rapide pour filtrer sur le champ Numéro d’article avec une valeur de « P300 ».</span><span class="sxs-lookup"><span data-stu-id="160da-147">Use the Quick Filter to filter on the Item number field with a value of 'P300'.</span></span>
    * <span data-ttu-id="160da-148">Notez que les commandes sont désormais séquencées selon la priorité en matière de couleur et de taille et les ordres prévisionnels démarrent à la date de commande et de livraison au plus tôt.</span><span class="sxs-lookup"><span data-stu-id="160da-148">Notice that the orders now are sequenced according to the priority of color and size and the planned orders start at the earliest order date and delivery date.</span></span> <span data-ttu-id="160da-149">Validez la colonne Date de commande ou la date de début dans le volet Détails du programme.</span><span class="sxs-lookup"><span data-stu-id="160da-149">Validate the Order date column or the Start date in the Schedule details FactBbox.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]