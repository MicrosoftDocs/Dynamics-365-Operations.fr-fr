---
title: Associer un index de carburant à un transporteur comme frais annexes
description: Ce guide indique comment créer une affectation annexe, des frais annexes transporteur et des données principales annexes pour la surcharge carburant, ainsi que comment associer un index de carburant de transport à un transporteur.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bfecdbd8ca2d6124906ef664493602a1d0ac0baf
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3981919"
---
# <a name="associate-a-fuel-index-with-a-carrier-as-an-accessorial-charge"></a><span data-ttu-id="15cfc-103">Associer un index de carburant à un transporteur comme frais annexes</span><span class="sxs-lookup"><span data-stu-id="15cfc-103">Associate a fuel index with a carrier as an accessorial charge</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="15cfc-104">Ce guide indique comment créer une affectation annexe, des frais annexes transporteur et des données principales annexes pour la surcharge carburant, ainsi que comment associer un index de carburant de transport à un transporteur.</span><span class="sxs-lookup"><span data-stu-id="15cfc-104">This guide shows how to create an accessorial assignment, carrier accessorial charge, accessorial master for fuel surcharge, and associate a carrier fuel index with a carrier.</span></span> <span data-ttu-id="15cfc-105">Vous devez avoir paramétré un index de carburant du transporteur avant d'exécuter ce guide.</span><span class="sxs-lookup"><span data-stu-id="15cfc-105">You need to have set up a carrier fuel index before you run this guide.</span></span> <span data-ttu-id="15cfc-106">Pour ce faire, vous pouvez utiliser le guide « Paramétrer un index de carburant du transporteur ».</span><span class="sxs-lookup"><span data-stu-id="15cfc-106">You can use the "Set up a carrier fuel index" guide to do this.</span></span> <span data-ttu-id="15cfc-107">Ces tâches de paramétrage sont généralement effectuées par un responsable logistique.</span><span class="sxs-lookup"><span data-stu-id="15cfc-107">These setup tasks are typically done by a Logistics manager.</span></span> <span data-ttu-id="15cfc-108">Les données de démonstration utilisées pour créer cette procédure sont USMF.</span><span class="sxs-lookup"><span data-stu-id="15cfc-108">The demo data used to create this procedure is USMF.</span></span>


## <a name="create-an-accessorial-master"></a><span data-ttu-id="15cfc-109">Créer des données principales annexes</span><span class="sxs-lookup"><span data-stu-id="15cfc-109">Create an accessorial master</span></span>
1. <span data-ttu-id="15cfc-110">Accédez à Gestion du transport > Configurer > Taux > Données principales de l'élément accessoire.</span><span class="sxs-lookup"><span data-stu-id="15cfc-110">Go to Transportation management > Setup > Rating > Accessorial masters.</span></span>
2. <span data-ttu-id="15cfc-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="15cfc-111">Click New.</span></span>
3. <span data-ttu-id="15cfc-112">Dans le champ Données principales annexes, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="15cfc-112">In the Accessorial master field, type a value.</span></span>
4. <span data-ttu-id="15cfc-113">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="15cfc-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="15cfc-114">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="15cfc-114">Click Save.</span></span>

## <a name="create-a-carrier-accessorial-charge"></a><span data-ttu-id="15cfc-115">Créer des frais annexes de transporteur</span><span class="sxs-lookup"><span data-stu-id="15cfc-115">Create a carrier accessorial charge</span></span>
1. <span data-ttu-id="15cfc-116">Accédez à Gestion du transport > Configurer > Classement > Frais annexes du transporteur.</span><span class="sxs-lookup"><span data-stu-id="15cfc-116">Go to Transportation management > Setup > Rating > Carrier accessorial charges.</span></span>
2. <span data-ttu-id="15cfc-117">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="15cfc-117">Click New.</span></span>
3. <span data-ttu-id="15cfc-118">Dans le champ ID annexe du transporteur, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="15cfc-118">In the Carrier accessorial ID field, type a value.</span></span>
4. <span data-ttu-id="15cfc-119">Dans le champ Transporteur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="15cfc-119">In the Shipping carrier field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="15cfc-120">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="15cfc-120">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="15cfc-121">Dans cet exemple, choisissez le transporteur par camion.</span><span class="sxs-lookup"><span data-stu-id="15cfc-121">In this example, choose Truck Carrier.</span></span>  
6. <span data-ttu-id="15cfc-122">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="15cfc-122">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="15cfc-123">Dans le champ Service de transport, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="15cfc-123">In the Carrier service field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="15cfc-124">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="15cfc-124">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="15cfc-125">Dans le champ Données principales annexes, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="15cfc-125">In the Accessorial master field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="15cfc-126">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="15cfc-126">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="15cfc-127">Dans cet exemple, sélectionnez l'enregistrement principal annexe nouvellement créé.</span><span class="sxs-lookup"><span data-stu-id="15cfc-127">In this example, choose the newly created Accessorial master.</span></span>  
11. <span data-ttu-id="15cfc-128">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="15cfc-128">Click Save.</span></span>

## <a name="create-an-accessorial-assignment"></a><span data-ttu-id="15cfc-129">Créer une affectation annexe</span><span class="sxs-lookup"><span data-stu-id="15cfc-129">Create an accessorial assignment</span></span>
1. <span data-ttu-id="15cfc-130">Cliquez sur Affectations annexes.</span><span class="sxs-lookup"><span data-stu-id="15cfc-130">Click Accessorial assignments.</span></span>
2. <span data-ttu-id="15cfc-131">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="15cfc-131">Click New.</span></span>
3. <span data-ttu-id="15cfc-132">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="15cfc-132">In the Name field, type a value.</span></span>
4. <span data-ttu-id="15cfc-133">Activez ou désactivez l'extension de la section Critères.</span><span class="sxs-lookup"><span data-stu-id="15cfc-133">Toggle the expansion of the Criteria section.</span></span>
    * <span data-ttu-id="15cfc-134">Dans les critères, vous pouvez choisir de toujours appliquer la surcharge carburant ou pour cet exemple, choisir qu'elle s'applique uniquement dans une région en particulier.</span><span class="sxs-lookup"><span data-stu-id="15cfc-134">In the criteria, you can choose to always apply the fuel surcharge or for this example choose that it only applies within a certain region.</span></span>  
5. <span data-ttu-id="15cfc-135">Dans le champ Code postal de départ, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="15cfc-135">In the ZIP/postal code from field, type a value.</span></span>
6. <span data-ttu-id="15cfc-136">Dans le champ Code postal d'arrivée, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="15cfc-136">In the ZIP/postal code to field, type a value.</span></span>
7. <span data-ttu-id="15cfc-137">Activez ou désactivez l'extension de la section Calcul.</span><span class="sxs-lookup"><span data-stu-id="15cfc-137">Toggle the expansion of the Calculation section.</span></span>
    * <span data-ttu-id="15cfc-138">Dans la section de calcul, vous pouvez spécifier le mode de calcul de la surcharge carburant.</span><span class="sxs-lookup"><span data-stu-id="15cfc-138">In the calculation section you can specify how to calculate the fuel surcharge.</span></span> <span data-ttu-id="15cfc-139">Ce calcul dépend de l'unité annexe que vous avez sélectionnée comme base pour le calcul.</span><span class="sxs-lookup"><span data-stu-id="15cfc-139">This calculation depends on the Accessorial unit that you chose as the base for your calculation.</span></span>  
8. <span data-ttu-id="15cfc-140">Dans le champ Type de frais annexes, sélectionnez « supplément carburant ».</span><span class="sxs-lookup"><span data-stu-id="15cfc-140">In the Accessorial fee type field, select 'Fuel surcharge'.</span></span>
9. <span data-ttu-id="15cfc-141">Dans le champ Unité annexe, sélectionnez « Kilométrage ».</span><span class="sxs-lookup"><span data-stu-id="15cfc-141">In the Accessorial unit field, select 'Mileage'.</span></span>
10. <span data-ttu-id="15cfc-142">Dans le champ Région, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="15cfc-142">In the Region field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="15cfc-143">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="15cfc-143">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="15cfc-144">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="15cfc-144">Click Save.</span></span>

## <a name="update-the-carrier-rating-profile"></a><span data-ttu-id="15cfc-145">Mettre à jour le profil de classement des transporteurs</span><span class="sxs-lookup"><span data-stu-id="15cfc-145">Update the carrier rating profile</span></span>
1. <span data-ttu-id="15cfc-146">Accédez à Gestion du transport > Paramétrage > Transporteurs > Transporteurs.</span><span class="sxs-lookup"><span data-stu-id="15cfc-146">Go to Transportation management > Setup > Carriers > Shipping carriers.</span></span>
2. <span data-ttu-id="15cfc-147">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="15cfc-147">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="15cfc-148">Activez ou désactivez l'extension de la section Profils de classement.</span><span class="sxs-lookup"><span data-stu-id="15cfc-148">Toggle the expansion of the Rating profiles section.</span></span>
4. <span data-ttu-id="15cfc-149">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="15cfc-149">Click Edit.</span></span>
5. <span data-ttu-id="15cfc-150">Dans le champ Index carburant transporteur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="15cfc-150">In the Carrier fuel index field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="15cfc-151">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="15cfc-151">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="15cfc-152">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="15cfc-152">Click Save.</span></span>

