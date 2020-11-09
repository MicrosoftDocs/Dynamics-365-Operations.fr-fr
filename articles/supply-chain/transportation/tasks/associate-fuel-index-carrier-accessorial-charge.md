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
ms.search.form: TMSRatingProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c91d49c2ccdc274632e3acf94b836e19dc6cdaa8
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016998"
---
# <a name="associate-a-fuel-index-with-a-carrier-as-an-accessorial-charge"></a><span data-ttu-id="58a55-103">Associer un index de carburant à un transporteur comme frais annexes</span><span class="sxs-lookup"><span data-stu-id="58a55-103">Associate a fuel index with a carrier as an accessorial charge</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="58a55-104">Ce guide indique comment créer une affectation annexe, des frais annexes transporteur et des données principales annexes pour la surcharge carburant, ainsi que comment associer un index de carburant de transport à un transporteur.</span><span class="sxs-lookup"><span data-stu-id="58a55-104">This guide shows how to create an accessorial assignment, carrier accessorial charge, accessorial master for fuel surcharge, and associate a carrier fuel index with a carrier.</span></span> <span data-ttu-id="58a55-105">Vous devez avoir paramétré un index de carburant du transporteur avant d'exécuter ce guide.</span><span class="sxs-lookup"><span data-stu-id="58a55-105">You need to have set up a carrier fuel index before you run this guide.</span></span> <span data-ttu-id="58a55-106">Pour ce faire, vous pouvez utiliser le guide « Paramétrer un index de carburant du transporteur ».</span><span class="sxs-lookup"><span data-stu-id="58a55-106">You can use the "Set up a carrier fuel index" guide to do this.</span></span> <span data-ttu-id="58a55-107">Ces tâches de paramétrage sont généralement effectuées par un responsable logistique.</span><span class="sxs-lookup"><span data-stu-id="58a55-107">These setup tasks are typically done by a Logistics manager.</span></span> <span data-ttu-id="58a55-108">Les données de démonstration utilisées pour créer cette procédure sont USMF.</span><span class="sxs-lookup"><span data-stu-id="58a55-108">The demo data used to create this procedure is USMF.</span></span>


## <a name="create-an-accessorial-master"></a><span data-ttu-id="58a55-109">Créer des données principales annexes</span><span class="sxs-lookup"><span data-stu-id="58a55-109">Create an accessorial master</span></span>
1. <span data-ttu-id="58a55-110">Accédez à Gestion du transport > Configurer > Taux > Données principales de l'élément accessoire.</span><span class="sxs-lookup"><span data-stu-id="58a55-110">Go to Transportation management > Setup > Rating > Accessorial masters.</span></span>
2. <span data-ttu-id="58a55-111">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="58a55-111">Click New.</span></span>
3. <span data-ttu-id="58a55-112">Dans le champ Données principales annexes, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="58a55-112">In the Accessorial master field, type a value.</span></span>
4. <span data-ttu-id="58a55-113">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="58a55-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="58a55-114">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="58a55-114">Click Save.</span></span>

## <a name="create-a-carrier-accessorial-charge"></a><span data-ttu-id="58a55-115">Créer des frais annexes de transporteur</span><span class="sxs-lookup"><span data-stu-id="58a55-115">Create a carrier accessorial charge</span></span>
1. <span data-ttu-id="58a55-116">Accédez à Gestion du transport > Configurer > Classement > Frais annexes du transporteur.</span><span class="sxs-lookup"><span data-stu-id="58a55-116">Go to Transportation management > Setup > Rating > Carrier accessorial charges.</span></span>
2. <span data-ttu-id="58a55-117">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="58a55-117">Click New.</span></span>
3. <span data-ttu-id="58a55-118">Dans le champ ID annexe du transporteur, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="58a55-118">In the Carrier accessorial ID field, type a value.</span></span>
4. <span data-ttu-id="58a55-119">Dans le champ Transporteur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="58a55-119">In the Shipping carrier field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="58a55-120">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="58a55-120">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="58a55-121">Dans cet exemple, choisissez le transporteur par camion.</span><span class="sxs-lookup"><span data-stu-id="58a55-121">In this example, choose Truck Carrier.</span></span>  
6. <span data-ttu-id="58a55-122">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="58a55-122">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="58a55-123">Dans le champ Service de transport, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="58a55-123">In the Carrier service field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="58a55-124">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="58a55-124">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="58a55-125">Dans le champ Données principales annexes, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="58a55-125">In the Accessorial master field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="58a55-126">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="58a55-126">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="58a55-127">Dans cet exemple, sélectionnez l'enregistrement principal annexe nouvellement créé.</span><span class="sxs-lookup"><span data-stu-id="58a55-127">In this example, choose the newly created Accessorial master.</span></span>  
11. <span data-ttu-id="58a55-128">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="58a55-128">Click Save.</span></span>

## <a name="create-an-accessorial-assignment"></a><span data-ttu-id="58a55-129">Créer une affectation annexe</span><span class="sxs-lookup"><span data-stu-id="58a55-129">Create an accessorial assignment</span></span>
1. <span data-ttu-id="58a55-130">Cliquez sur Affectations annexes.</span><span class="sxs-lookup"><span data-stu-id="58a55-130">Click Accessorial assignments.</span></span>
2. <span data-ttu-id="58a55-131">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="58a55-131">Click New.</span></span>
3. <span data-ttu-id="58a55-132">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="58a55-132">In the Name field, type a value.</span></span>
4. <span data-ttu-id="58a55-133">Activez ou désactivez l'extension de la section Critères.</span><span class="sxs-lookup"><span data-stu-id="58a55-133">Toggle the expansion of the Criteria section.</span></span>
    * <span data-ttu-id="58a55-134">Dans les critères, vous pouvez choisir de toujours appliquer la surcharge carburant ou pour cet exemple, choisir qu'elle s'applique uniquement dans une région en particulier.</span><span class="sxs-lookup"><span data-stu-id="58a55-134">In the criteria, you can choose to always apply the fuel surcharge or for this example choose that it only applies within a certain region.</span></span>  
5. <span data-ttu-id="58a55-135">Dans le champ Code postal de départ, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="58a55-135">In the ZIP/postal code from field, type a value.</span></span>
6. <span data-ttu-id="58a55-136">Dans le champ Code postal d'arrivée, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="58a55-136">In the ZIP/postal code to field, type a value.</span></span>
7. <span data-ttu-id="58a55-137">Activez ou désactivez l'extension de la section Calcul.</span><span class="sxs-lookup"><span data-stu-id="58a55-137">Toggle the expansion of the Calculation section.</span></span>
    * <span data-ttu-id="58a55-138">Dans la section de calcul, vous pouvez spécifier le mode de calcul de la surcharge carburant.</span><span class="sxs-lookup"><span data-stu-id="58a55-138">In the calculation section you can specify how to calculate the fuel surcharge.</span></span> <span data-ttu-id="58a55-139">Ce calcul dépend de l'unité annexe que vous avez sélectionnée comme base pour le calcul.</span><span class="sxs-lookup"><span data-stu-id="58a55-139">This calculation depends on the Accessorial unit that you chose as the base for your calculation.</span></span>  
8. <span data-ttu-id="58a55-140">Dans le champ Type de frais annexes, sélectionnez « supplément carburant ».</span><span class="sxs-lookup"><span data-stu-id="58a55-140">In the Accessorial fee type field, select 'Fuel surcharge'.</span></span>
9. <span data-ttu-id="58a55-141">Dans le champ Unité annexe, sélectionnez « Kilométrage ».</span><span class="sxs-lookup"><span data-stu-id="58a55-141">In the Accessorial unit field, select 'Mileage'.</span></span>
10. <span data-ttu-id="58a55-142">Dans le champ Région, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="58a55-142">In the Region field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="58a55-143">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="58a55-143">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="58a55-144">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="58a55-144">Click Save.</span></span>

## <a name="update-the-carrier-rating-profile"></a><span data-ttu-id="58a55-145">Mettre à jour le profil de classement des transporteurs</span><span class="sxs-lookup"><span data-stu-id="58a55-145">Update the carrier rating profile</span></span>
1. <span data-ttu-id="58a55-146">Accédez à Gestion du transport > Paramétrage > Transporteurs > Transporteurs.</span><span class="sxs-lookup"><span data-stu-id="58a55-146">Go to Transportation management > Setup > Carriers > Shipping carriers.</span></span>
2. <span data-ttu-id="58a55-147">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="58a55-147">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="58a55-148">Activez ou désactivez l'extension de la section Profils de classement.</span><span class="sxs-lookup"><span data-stu-id="58a55-148">Toggle the expansion of the Rating profiles section.</span></span>
4. <span data-ttu-id="58a55-149">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="58a55-149">Click Edit.</span></span>
5. <span data-ttu-id="58a55-150">Dans le champ Index carburant transporteur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="58a55-150">In the Carrier fuel index field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="58a55-151">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="58a55-151">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="58a55-152">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="58a55-152">Click Save.</span></span>

