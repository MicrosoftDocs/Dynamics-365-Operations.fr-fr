---
title: Créer des activités de transfert pour la lean manufacturing
description: Créez une activité de transfert pour la lean manufacturing.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityWizard, LeanWorkCellLookup, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5e3c92c5fc9cdba7c77942fae5c32d625cc939f1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5237916"
---
# <a name="create-transfer-activities-for-lean-manufacturing"></a><span data-ttu-id="b780f-103">Créer des activités de transfert pour la lean manufacturing</span><span class="sxs-lookup"><span data-stu-id="b780f-103">Create transfer activities for lean manufacturing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b780f-104">Créez une activité de transfert pour la lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="b780f-104">Create a transfer activity for lean manufacturing.</span></span> 

<span data-ttu-id="b780f-105">Conditions préalables :</span><span class="sxs-lookup"><span data-stu-id="b780f-105">Prerequisites:</span></span> 

1. <span data-ttu-id="b780f-106">Un flux de production et une version non actifs doivent être créés.</span><span class="sxs-lookup"><span data-stu-id="b780f-106">A production flow and version that is not active must be created.</span></span>

2. <span data-ttu-id="b780f-107">Les emplacements et l’entrepôt d’origine et de destination doivent être créés.</span><span class="sxs-lookup"><span data-stu-id="b780f-107">The from and to warehouse and locations must be created.</span></span> <span data-ttu-id="b780f-108">Le cas échéant, il convient de créer le réapprovisionnement ou la cellule de travail réapprovisionnée.</span><span class="sxs-lookup"><span data-stu-id="b780f-108">Optionally, the replenishing or the replenished work cell should be created.</span></span>


## <a name="find-the-production-flow-version"></a><span data-ttu-id="b780f-109">Cherchez la version du flux de production.</span><span class="sxs-lookup"><span data-stu-id="b780f-109">Find the production flow version</span></span>
1. <span data-ttu-id="b780f-110">Accédez à Contrôle de la production > Paramétrage > Flux de production lean > Flux de production.</span><span class="sxs-lookup"><span data-stu-id="b780f-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="b780f-111">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="b780f-111">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="b780f-112">Notez que le flux de production doit avoir une version à l’état de brouillon.</span><span class="sxs-lookup"><span data-stu-id="b780f-112">Note that the production flow must have a version in draft status.</span></span>  
3. <span data-ttu-id="b780f-113">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b780f-113">In the list, click the link in the selected row.</span></span>

## <a name="create-a-new-activity"></a><span data-ttu-id="b780f-114">Créer une nouvelle activité</span><span class="sxs-lookup"><span data-stu-id="b780f-114">Create a new activity</span></span>
1. <span data-ttu-id="b780f-115">Cliquez sur Activités.</span><span class="sxs-lookup"><span data-stu-id="b780f-115">Click Activities.</span></span>
    * <span data-ttu-id="b780f-116">Vérifiez que le flux de production sélectionné a une version à l’état de brouillon, et sélectionnez celle-ci.</span><span class="sxs-lookup"><span data-stu-id="b780f-116">Ensure that the selected production flow has a version in draft and select that version.</span></span>  
2. <span data-ttu-id="b780f-117">Cliquez sur Créer une nouvelle activité de plan.</span><span class="sxs-lookup"><span data-stu-id="b780f-117">Click Create new plan activity.</span></span>
3. <span data-ttu-id="b780f-118">Cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="b780f-118">Click Next.</span></span>
4. <span data-ttu-id="b780f-119">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="b780f-119">In the Name field, type a value.</span></span>
5. <span data-ttu-id="b780f-120">Dans le champ Type d’activité, sélectionnez « Transfert ».</span><span class="sxs-lookup"><span data-stu-id="b780f-120">In the Activity type field, select 'Transfer'.</span></span>
6. <span data-ttu-id="b780f-121">Dans le champ Quantité à traiter, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="b780f-121">In the Process quantity field, enter a number.</span></span>
7. <span data-ttu-id="b780f-122">Cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="b780f-122">Click Next.</span></span>

## <a name="select-the-work-cells"></a><span data-ttu-id="b780f-123">Sélectionnez les cellules de travail.</span><span class="sxs-lookup"><span data-stu-id="b780f-123">Select the Work cells</span></span>
1. <span data-ttu-id="b780f-124">Dans le champ Réapprovisionnement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="b780f-124">In the Replenishing field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="b780f-125">Pour utiliser l’emplacement de sortie de la cellule de travail comme emplacement d’origine dans l’activité de transfert, sélectionnez une cellule de travail.</span><span class="sxs-lookup"><span data-stu-id="b780f-125">To use the work cell output location as the from location in the transfer activity, select a work cell.</span></span> <span data-ttu-id="b780f-126">Il est possible de faire la même chose avec la cellule de travail réapprovisionnée, ce qui définit l’emplacement cible de l’activité de transfert.</span><span class="sxs-lookup"><span data-stu-id="b780f-126">The same can be done with the replenished work cell, which sets the target location of the transfer activity.</span></span>  
2. <span data-ttu-id="b780f-127">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b780f-127">In the list, click the link in the selected row.</span></span>

## <a name="define-the-inventory-updates"></a><span data-ttu-id="b780f-128">Définir les mises à jour de stock</span><span class="sxs-lookup"><span data-stu-id="b780f-128">Define the inventory updates</span></span>
1. <span data-ttu-id="b780f-129">Dans le champ Type de produit, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="b780f-129">In the Product type field, select an option.</span></span>
    * <span data-ttu-id="b780f-130">Notez qu’un transfert ne modifie pas le type de produit.</span><span class="sxs-lookup"><span data-stu-id="b780f-130">Note that a transfer does not change the type of product.</span></span> <span data-ttu-id="b780f-131">Vous pouvez transférer des produits finis ou semi-finis (transfert entre deux activités d’un flux de production et éventuellement d’un flux kanban).</span><span class="sxs-lookup"><span data-stu-id="b780f-131">You can transfer finished products or semi-finished products (transfer between two activities of a production flow and possibly a kanban flow).</span></span>     <span data-ttu-id="b780f-132">Lors du transfert de produits finis, vous pouvez choisir si le prélèvement ou la réception des résultats est une transaction de stock.</span><span class="sxs-lookup"><span data-stu-id="b780f-132">When transferring finished products, you can select if picking or receiving results in an inventory transaction.</span></span>  

## <a name="define-the-transfer-locations"></a><span data-ttu-id="b780f-133">Définir les emplacements de transfert</span><span class="sxs-lookup"><span data-stu-id="b780f-133">Define the transfer locations</span></span>
1. <span data-ttu-id="b780f-134">Cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="b780f-134">Click Next.</span></span>
2. <span data-ttu-id="b780f-135">Dans le champ Entrepôt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="b780f-135">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="b780f-136">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="b780f-136">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="b780f-137">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b780f-137">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="b780f-138">Dans le champ Emplacement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="b780f-138">In the Location field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="b780f-139">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b780f-139">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="b780f-140">Dans le champ Transporté par, sélectionnez « Expéditeur ».</span><span class="sxs-lookup"><span data-stu-id="b780f-140">In the Freighted by field, select 'Shipper'.</span></span>
    * <span data-ttu-id="b780f-141">Les options sont les suivantes : Expéditeur - l’organisations qui exploite l’entrepôt d’expédition, Destinataire - l’organisation qui exploite l’entrepôt de réception, Transporteur - un fournisseur tiers.</span><span class="sxs-lookup"><span data-stu-id="b780f-141">Options include: Shipper - the organization operating the shipping warehouse, Recipient -  the organization operating the receiving warehouse, Carrier - a third party vendor.</span></span> <span data-ttu-id="b780f-142">Si l’organisation exploitante est un fournisseur, l’activité de transfert nécessite un accord de sous-traitance.</span><span class="sxs-lookup"><span data-stu-id="b780f-142">If the operating organization is a vendor, the transfer activity requires a subcontracting agreement.</span></span>  
8. <span data-ttu-id="b780f-143">Cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="b780f-143">Click Next.</span></span>

## <a name="define-the-activity-times"></a><span data-ttu-id="b780f-144">Définir les durées d’activité</span><span class="sxs-lookup"><span data-stu-id="b780f-144">Define the activity times</span></span>
1. <span data-ttu-id="b780f-145">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="b780f-145">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="b780f-146">La définition d’un Délai d’exécution est requise.</span><span class="sxs-lookup"><span data-stu-id="b780f-146">The definition of a Runtime is required.</span></span> <span data-ttu-id="b780f-147">Le délai d’exécution est utilisé pour calculer les coûts et les délais de débit des tâches de kanban.</span><span class="sxs-lookup"><span data-stu-id="b780f-147">The Runtime is used to calculate cost and the throughput times of the kanban jobs.</span></span> <span data-ttu-id="b780f-148">Les délais d’exécution ne sont pas utilisés pour calculer la charge de la capacité et la consommation, qui sont calculées par durée de cycle, dérivée de la tâche de version du flux de production.</span><span class="sxs-lookup"><span data-stu-id="b780f-148">Runtimes are not used to calculate capacity load and consumption, which is calculated by cycle time, derived from the production flow version task.</span></span>  
2. <span data-ttu-id="b780f-149">Entrez un nombre dans le champ Durée.</span><span class="sxs-lookup"><span data-stu-id="b780f-149">In the Time field, enter a number.</span></span>
3. <span data-ttu-id="b780f-150">Dans le champ Unité, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="b780f-150">In the Unit field, type a value.</span></span>
4. <span data-ttu-id="b780f-151">Sélectionnez l’Unité de temps.</span><span class="sxs-lookup"><span data-stu-id="b780f-151">Select the Time unit.</span></span>
5. <span data-ttu-id="b780f-152">Dans le champ Par quantité, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="b780f-152">In the Per quantity field, enter a number.</span></span>
6. <span data-ttu-id="b780f-153">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="b780f-153">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="b780f-154">Les temps d’attente sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="b780f-154">Queue times are optional.</span></span>  
7. <span data-ttu-id="b780f-155">Entrez un nombre dans le champ Durée.</span><span class="sxs-lookup"><span data-stu-id="b780f-155">In the Time field, enter a number.</span></span>
8. <span data-ttu-id="b780f-156">Dans le champ Unité, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="b780f-156">In the Unit field, type a value.</span></span>
9. <span data-ttu-id="b780f-157">Sélectionnez l’Unité de temps.</span><span class="sxs-lookup"><span data-stu-id="b780f-157">Select the Time unit.</span></span>
10. <span data-ttu-id="b780f-158">Dans le champ Par quantité, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="b780f-158">In the Per quantity field, enter a number.</span></span>
11. <span data-ttu-id="b780f-159">Cliquez sur Suivant.</span><span class="sxs-lookup"><span data-stu-id="b780f-159">Click Next.</span></span>
12. <span data-ttu-id="b780f-160">Cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="b780f-160">Click Finish.</span></span>
13. <span data-ttu-id="b780f-161">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="b780f-161">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]