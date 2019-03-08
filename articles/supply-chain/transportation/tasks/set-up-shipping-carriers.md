---
title: Paramétrage des transporteurs
description: Cette procédure décrit comment paramétrer un transporteur et définir des détails tels que le service, le mode d'expédition, l'offre de transport, les contraintes de transport, et les frais de livraison.
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6c5ac13d17c97f20ee79e7faf57c570f02158424
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "314484"
---
# <a name="set-up-shipping-carriers"></a><span data-ttu-id="fac0e-103">Paramétrage des transporteurs</span><span class="sxs-lookup"><span data-stu-id="fac0e-103">Set up shipping carriers</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fac0e-104">Cette procédure décrit comment paramétrer un transporteur et définir des détails tels que le service, le mode d'expédition, l'offre de transport, les contraintes de transport, et les frais de livraison.</span><span class="sxs-lookup"><span data-stu-id="fac0e-104">This procedure shows how to set up a shipping carrier and define details such as service, shipment mode, transportation tender, transportation constraints, and shipping rate.</span></span> <span data-ttu-id="fac0e-105">Un coordinateur de transport pourra ensuite affecter un transporteur à une charge entrante ou sortante.</span><span class="sxs-lookup"><span data-stu-id="fac0e-105">A transportation coordinator can then assign a shipping carrier to an inbound or outbound load.</span></span>


## <a name="create-a-new-shipping-carrier"></a><span data-ttu-id="fac0e-106">Créer un transporteur</span><span class="sxs-lookup"><span data-stu-id="fac0e-106">Create a new shipping carrier</span></span>
1. <span data-ttu-id="fac0e-107">Accédez à Gestion du transport > Paramétrage > Transporteurs > Transporteurs.</span><span class="sxs-lookup"><span data-stu-id="fac0e-107">Go to Transportation management > Setup > Carriers > Shipping carriers.</span></span>
2. <span data-ttu-id="fac0e-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="fac0e-108">Click New.</span></span>
3. <span data-ttu-id="fac0e-109">Tapez une valeur dans le champ Transporteur.</span><span class="sxs-lookup"><span data-stu-id="fac0e-109">In the Shipping carrier field, type a value.</span></span>
4. <span data-ttu-id="fac0e-110">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="fac0e-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="fac0e-111">Dans le champ Mode, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="fac0e-111">In the Mode field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="fac0e-112">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="fac0e-112">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="fac0e-113">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fac0e-113">In the list, click the link in the selected row.</span></span>

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a><span data-ttu-id="fac0e-114">Renseigner les informations générales du transporteur</span><span class="sxs-lookup"><span data-stu-id="fac0e-114">Fill in the general information for the shipping carrier</span></span>
1. <span data-ttu-id="fac0e-115">Activez ou désactivez l'extension de la section Vue d'ensemble.</span><span class="sxs-lookup"><span data-stu-id="fac0e-115">Toggle the expansion of the Overview section.</span></span>
2. <span data-ttu-id="fac0e-116">Activez ou désactivez la case à cocher Activation du transporteur.</span><span class="sxs-lookup"><span data-stu-id="fac0e-116">Check or uncheck the Activate shipping carrier checkbox.</span></span>
3. <span data-ttu-id="fac0e-117">Dans le champ Fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="fac0e-117">In the Vendor field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="fac0e-118">Sélectionnez le compte fournisseur à affecter au transporteur.</span><span class="sxs-lookup"><span data-stu-id="fac0e-118">Select the vendor account to assign the shipping carrier to.</span></span>  
4. <span data-ttu-id="fac0e-119">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="fac0e-119">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="fac0e-120">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fac0e-120">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="fac0e-121">Sélectionnez une option dans le champ Type d'offre de transport.</span><span class="sxs-lookup"><span data-stu-id="fac0e-121">In the Transportation tender type field, select an option.</span></span>
    * <span data-ttu-id="fac0e-122">Sélectionnez Manuel pour utiliser la page Offre de transport ou sélectionnez EDI pour mettre à jour l'offre à l'aide de l'échange de données informatisé (EDI).</span><span class="sxs-lookup"><span data-stu-id="fac0e-122">Select Manual to use the Transportation Tender page, or select EDI to update the tender by using Electronic Data Interchange (EDI).</span></span>  
7. <span data-ttu-id="fac0e-123">Activez ou désactivez la case à cocher Activer le classement du transporteur.</span><span class="sxs-lookup"><span data-stu-id="fac0e-123">Check or uncheck the Activate carrier rating checkbox.</span></span>

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a><span data-ttu-id="fac0e-124">Créer les services nécessaires pour le transporteur</span><span class="sxs-lookup"><span data-stu-id="fac0e-124">Create the necessary services for the shipping carrier</span></span>
1. <span data-ttu-id="fac0e-125">Activez ou désactivez l'extension de la section Services.</span><span class="sxs-lookup"><span data-stu-id="fac0e-125">Toggle the expansion of the Services section.</span></span>
2. <span data-ttu-id="fac0e-126">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="fac0e-126">Click New.</span></span>
3. <span data-ttu-id="fac0e-127">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fac0e-127">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="fac0e-128">Tapez une valeur dans le champ Service de transporteur.</span><span class="sxs-lookup"><span data-stu-id="fac0e-128">In the Carrier service field, type a value.</span></span>
5. <span data-ttu-id="fac0e-129">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="fac0e-129">In the Name field, type a value.</span></span>
6. <span data-ttu-id="fac0e-130">Dans le champ Mode de transport, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="fac0e-130">In the Transportation method field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="fac0e-131">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="fac0e-131">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="fac0e-132">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fac0e-132">In the list, click the link in the selected row.</span></span>

## <a name="set-up-the-address-for-the-carrier-optional"></a><span data-ttu-id="fac0e-133">Paramétrer l'adresse du transporteur (facultatif)</span><span class="sxs-lookup"><span data-stu-id="fac0e-133">Set up the address for the carrier (optional)</span></span>
1. <span data-ttu-id="fac0e-134">Activez ou désactivez l'extension de la section Adresses.</span><span class="sxs-lookup"><span data-stu-id="fac0e-134">Toggle the expansion of the Addresses section.</span></span>
2. <span data-ttu-id="fac0e-135">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="fac0e-135">Click New.</span></span>
3. <span data-ttu-id="fac0e-136">Tapez une valeur dans le champ Nom ou description.</span><span class="sxs-lookup"><span data-stu-id="fac0e-136">In the Name or description field, type a value.</span></span>
4. <span data-ttu-id="fac0e-137">Dans le champ Pays/Région, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="fac0e-137">In the Country/region field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="fac0e-138">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fac0e-138">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="fac0e-139">Dans le champ Code postal, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="fac0e-139">In the ZIP/postal code field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="fac0e-140">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="fac0e-140">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="fac0e-141">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fac0e-141">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="fac0e-142">Tapez une valeur dans le champ Rue.</span><span class="sxs-lookup"><span data-stu-id="fac0e-142">In the Street field, type a value.</span></span>
10. <span data-ttu-id="fac0e-143">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="fac0e-143">Click OK.</span></span>

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a><span data-ttu-id="fac0e-144">Paramétrer le profil de classement du transporteur</span><span class="sxs-lookup"><span data-stu-id="fac0e-144">Set up the rating profile for the shipping carrier</span></span>
1. <span data-ttu-id="fac0e-145">Activez ou désactivez l'extension de la section Profils de classement.</span><span class="sxs-lookup"><span data-stu-id="fac0e-145">Toggle the expansion of the Rating profiles section.</span></span>
2. <span data-ttu-id="fac0e-146">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="fac0e-146">Click New.</span></span>
3. <span data-ttu-id="fac0e-147">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fac0e-147">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="fac0e-148">Tapez une valeur dans le champ Profil de classement.</span><span class="sxs-lookup"><span data-stu-id="fac0e-148">In the Rating profile field, type a value.</span></span>
5. <span data-ttu-id="fac0e-149">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="fac0e-149">In the Name field, type a value.</span></span>
6. <span data-ttu-id="fac0e-150">Dans le champ Site, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="fac0e-150">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="fac0e-151">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="fac0e-151">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="fac0e-152">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fac0e-152">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="fac0e-153">Dans le champ Entrepôt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="fac0e-153">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="fac0e-154">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="fac0e-154">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="fac0e-155">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fac0e-155">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="fac0e-156">Dans le champ Moteur de taux, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="fac0e-156">In the Rate engine field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="fac0e-157">Sélectionnez le moteur de frais correspondant au contrat que vous avez avec le transporteur.</span><span class="sxs-lookup"><span data-stu-id="fac0e-157">Select the Rate engine that is in accordance with the contract that you have with the carrier.</span></span>  
13. <span data-ttu-id="fac0e-158">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="fac0e-158">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="fac0e-159">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fac0e-159">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="fac0e-160">Dans le champ Données principales du taux, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="fac0e-160">In the Rate master field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="fac0e-161">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="fac0e-161">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="fac0e-162">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fac0e-162">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="fac0e-163">Dans le champ Moteur de temps de transit, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="fac0e-163">In the Transit time engine field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="fac0e-164">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fac0e-164">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="fac0e-165">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="fac0e-165">Click Save.</span></span>

