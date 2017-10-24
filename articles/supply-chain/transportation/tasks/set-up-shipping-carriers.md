--- 
title: "Paramétrage des transporteurs"
description: "Cette procédure décrit comment paramétrer un transporteur et définir des détails tels que le service, le mode d'expédition, l'offre de transport, les contraintes de transport, et les frais de livraison."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e27be049bebd63c9266029b8981874417a9f0a8c
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-shipping-carriers"></a><span data-ttu-id="6a7c5-103">Paramétrage des transporteurs</span><span class="sxs-lookup"><span data-stu-id="6a7c5-103">Set up shipping carriers</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6a7c5-104">Cette procédure décrit comment paramétrer un transporteur et définir des détails tels que le service, le mode d'expédition, l'offre de transport, les contraintes de transport, et les frais de livraison.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-104">This procedure shows how to set up a shipping carrier and define details such as service, shipment mode, transportation tender, transportation constraints, and shipping rate.</span></span> <span data-ttu-id="6a7c5-105">Un coordinateur de transport pourra ensuite affecter un transporteur à une charge entrante ou sortante.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-105">A transportation coordinator can then assign a shipping carrier to an inbound or outbound load.</span></span>


## <a name="create-a-new-shipping-carrier"></a><span data-ttu-id="6a7c5-106">Créer un transporteur</span><span class="sxs-lookup"><span data-stu-id="6a7c5-106">Create a new shipping carrier</span></span>
1. <span data-ttu-id="6a7c5-107">Accédez à Gestion du transport > Paramétrage > Transporteurs > Transporteurs.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-107">Go to Transportation management > Setup > Carriers > Shipping carriers.</span></span>
2. <span data-ttu-id="6a7c5-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-108">Click New.</span></span>
3. <span data-ttu-id="6a7c5-109">Tapez une valeur dans le champ Transporteur.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-109">In the Shipping carrier field, type a value.</span></span>
4. <span data-ttu-id="6a7c5-110">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="6a7c5-111">Dans le champ Mode, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-111">In the Mode field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="6a7c5-112">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-112">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="6a7c5-113">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-113">In the list, click the link in the selected row.</span></span>

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a><span data-ttu-id="6a7c5-114">Renseigner les informations générales du transporteur</span><span class="sxs-lookup"><span data-stu-id="6a7c5-114">Fill in the general information for the shipping carrier</span></span>
1. <span data-ttu-id="6a7c5-115">Activez ou désactivez l'extension de la section Vue d'ensemble.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-115">Toggle the expansion of the Overview section.</span></span>
2. <span data-ttu-id="6a7c5-116">Activez ou désactivez la case à cocher Activation du transporteur.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-116">Check or uncheck the Activate shipping carrier checkbox.</span></span>
3. <span data-ttu-id="6a7c5-117">Dans le champ Fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-117">In the Vendor field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="6a7c5-118">Sélectionnez le compte fournisseur à affecter au transporteur.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-118">Select the vendor account to assign the shipping carrier to.</span></span>  
4. <span data-ttu-id="6a7c5-119">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-119">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="6a7c5-120">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-120">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="6a7c5-121">Sélectionnez une option dans le champ Type d'offre de transport.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-121">In the Transportation tender type field, select an option.</span></span>
    * <span data-ttu-id="6a7c5-122">Sélectionnez Manuel pour utiliser la page Offre de transport ou sélectionnez EDI pour mettre à jour l'offre à l'aide de l'échange de données informatisé (EDI).</span><span class="sxs-lookup"><span data-stu-id="6a7c5-122">Select Manual to use the Transportation Tender page, or select EDI to update the tender by using Electronic Data Interchange (EDI).</span></span>  
7. <span data-ttu-id="6a7c5-123">Activez ou désactivez la case à cocher Activer le classement du transporteur.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-123">Check or uncheck the Activate carrier rating checkbox.</span></span>

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a><span data-ttu-id="6a7c5-124">Créer les services nécessaires pour le transporteur</span><span class="sxs-lookup"><span data-stu-id="6a7c5-124">Create the necessary services for the shipping carrier</span></span>
1. <span data-ttu-id="6a7c5-125">Activez ou désactivez l'extension de la section Services.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-125">Toggle the expansion of the Services section.</span></span>
2. <span data-ttu-id="6a7c5-126">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-126">Click New.</span></span>
3. <span data-ttu-id="6a7c5-127">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-127">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="6a7c5-128">Tapez une valeur dans le champ Service de transporteur.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-128">In the Carrier service field, type a value.</span></span>
5. <span data-ttu-id="6a7c5-129">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-129">In the Name field, type a value.</span></span>
6. <span data-ttu-id="6a7c5-130">Dans le champ Mode de transport, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-130">In the Transportation method field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="6a7c5-131">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-131">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="6a7c5-132">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-132">In the list, click the link in the selected row.</span></span>

## <a name="set-up-the-address-for-the-carrier-optional"></a><span data-ttu-id="6a7c5-133">Paramétrer l'adresse du transporteur (facultatif)</span><span class="sxs-lookup"><span data-stu-id="6a7c5-133">Set up the address for the carrier (optional)</span></span>
1. <span data-ttu-id="6a7c5-134">Activez ou désactivez l'extension de la section Adresses.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-134">Toggle the expansion of the Addresses section.</span></span>
2. <span data-ttu-id="6a7c5-135">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-135">Click New.</span></span>
3. <span data-ttu-id="6a7c5-136">Tapez une valeur dans le champ Nom ou description.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-136">In the Name or description field, type a value.</span></span>
4. <span data-ttu-id="6a7c5-137">Dans le champ Pays/Région, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-137">In the Country/region field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="6a7c5-138">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-138">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="6a7c5-139">Dans le champ Code postal, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-139">In the ZIP/postal code field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="6a7c5-140">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-140">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="6a7c5-141">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-141">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="6a7c5-142">Tapez une valeur dans le champ Rue.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-142">In the Street field, type a value.</span></span>
10. <span data-ttu-id="6a7c5-143">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-143">Click OK.</span></span>

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a><span data-ttu-id="6a7c5-144">Paramétrer le profil de classement du transporteur</span><span class="sxs-lookup"><span data-stu-id="6a7c5-144">Set up the rating profile for the shipping carrier</span></span>
1. <span data-ttu-id="6a7c5-145">Activez ou désactivez l'extension de la section Profils de classement.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-145">Toggle the expansion of the Rating profiles section.</span></span>
2. <span data-ttu-id="6a7c5-146">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-146">Click New.</span></span>
3. <span data-ttu-id="6a7c5-147">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-147">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="6a7c5-148">Tapez une valeur dans le champ Profil de classement.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-148">In the Rating profile field, type a value.</span></span>
5. <span data-ttu-id="6a7c5-149">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-149">In the Name field, type a value.</span></span>
6. <span data-ttu-id="6a7c5-150">Dans le champ Site, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-150">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="6a7c5-151">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-151">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="6a7c5-152">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-152">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="6a7c5-153">Dans le champ Entrepôt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-153">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="6a7c5-154">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-154">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="6a7c5-155">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-155">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="6a7c5-156">Dans le champ Moteur de taux, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-156">In the Rate engine field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="6a7c5-157">Sélectionnez le moteur de frais correspondant au contrat que vous avez avec le transporteur.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-157">Select the Rate engine that is in accordance with the contract that you have with the carrier.</span></span>  
13. <span data-ttu-id="6a7c5-158">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-158">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="6a7c5-159">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-159">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="6a7c5-160">Dans le champ Données principales du taux, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-160">In the Rate master field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="6a7c5-161">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-161">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="6a7c5-162">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-162">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="6a7c5-163">Dans le champ Moteur de temps de transit, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-163">In the Transit time engine field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="6a7c5-164">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-164">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="6a7c5-165">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="6a7c5-165">Click Save.</span></span>


