---
title: Paramétrer des tables maître des taux
description: Cette procédure décrit le processus de paramétrage des données principales de taux.
author: ShylaThompson
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 91877c777c6f76bd4fcf1c786bd708051c2fcd47
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201454"
---
# <a name="set-up-rate-masters"></a><span data-ttu-id="7714f-103">Paramétrer des tables maître des taux</span><span class="sxs-lookup"><span data-stu-id="7714f-103">Set up rate masters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7714f-104">Cette procédure décrit le processus de paramétrage des données principales de taux.</span><span class="sxs-lookup"><span data-stu-id="7714f-104">This procedure shows you how to set up a rate master.</span></span> <span data-ttu-id="7714f-105">Le responsable logistique configure généralement les données principales de taux en fonction des contacts signés avec les transporteurs.</span><span class="sxs-lookup"><span data-stu-id="7714f-105">The logistic manager usually sets up rate masters, depending on the contracts signed with the carriers.</span></span> <span data-ttu-id="7714f-106">Dans ce scénario vous paramètrerez des données principales de taux pour un transporteur aérien.</span><span class="sxs-lookup"><span data-stu-id="7714f-106">In this scenario you will set up a rate master for an air carrier.</span></span> <span data-ttu-id="7714f-107">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="7714f-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-rate-master"></a><span data-ttu-id="7714f-108">Paramétrer des données principales de taux</span><span class="sxs-lookup"><span data-stu-id="7714f-108">Set up rate master</span></span>
1. <span data-ttu-id="7714f-109">Accédez à Gestion du transport > Configurer > Taux > Données principales de taux.</span><span class="sxs-lookup"><span data-stu-id="7714f-109">Go to Transportation management > Setup > Rating > Rate master.</span></span>
2. <span data-ttu-id="7714f-110">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="7714f-110">Click New.</span></span>
3. <span data-ttu-id="7714f-111">Dans le champ Données principales de taux, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="7714f-111">In the Rate master field, type a value.</span></span>
4. <span data-ttu-id="7714f-112">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="7714f-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="7714f-113">Dans le champ ID des métadonnées de taux, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="7714f-113">In the Rating metadata ID field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="7714f-114">L'ID des métadonnées de taux détermine les données nécessaires pour les données principales du taux, car cela définit les métadonnées attendues par le moteur de TMS utilisant cette table maître des taux.</span><span class="sxs-lookup"><span data-stu-id="7714f-114">The rating metadata ID will determine the data needed for the rate master, as it defines the metadata expected by the TMS engine using this rate master.</span></span>  
6. <span data-ttu-id="7714f-115">Pour cette exemple, sélectionnez l'option P2P</span><span class="sxs-lookup"><span data-stu-id="7714f-115">For this example, select the P2P option</span></span>
7. <span data-ttu-id="7714f-116">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7714f-116">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="7714f-117">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="7714f-117">Click Save.</span></span>

## <a name="set-up-rate-base"></a><span data-ttu-id="7714f-118">Paramétrer la base de taux</span><span class="sxs-lookup"><span data-stu-id="7714f-118">Set up rate base</span></span>
1. <span data-ttu-id="7714f-119">Cliquez sur Base de taux.</span><span class="sxs-lookup"><span data-stu-id="7714f-119">Click Rate base.</span></span>
    * <span data-ttu-id="7714f-120">La base de taux détermine le taux du transporteur, et peut être utilisée pour paramétrer une structure tarifaire car elle structure les taux dans les points d'arrêt définis dans les données principales des ruptures.</span><span class="sxs-lookup"><span data-stu-id="7714f-120">The rate base determines the rate of the carrier, and can be used to set up a tariff structure as it structures the rates in the breakpoints defined in the break master.</span></span>  
2. <span data-ttu-id="7714f-121">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="7714f-121">Click New.</span></span>
3. <span data-ttu-id="7714f-122">Dans le champ Base de taux, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="7714f-122">In the Rate base field, type a value.</span></span>
4. <span data-ttu-id="7714f-123">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="7714f-123">In the Name field, type a value.</span></span>
5. <span data-ttu-id="7714f-124">Dans le champ Données principales de la rupture, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="7714f-124">In the Break master field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="7714f-125">Les données principales des ruptures permettent de définir la structure de tarification et les points d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="7714f-125">Break masters are used to define the pricing structure and its breakpoints.</span></span> <span data-ttu-id="7714f-126">La structure de tarification utilise la tarification progressive basée sur les dimensions physiques.</span><span class="sxs-lookup"><span data-stu-id="7714f-126">The pricing structure uses tiered pricing that is based on physical dimensions.</span></span>  
6. <span data-ttu-id="7714f-127">Pour cet exemple, utilisez le poids</span><span class="sxs-lookup"><span data-stu-id="7714f-127">For this example, use weight</span></span>
7. <span data-ttu-id="7714f-128">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7714f-128">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="7714f-129">Activez ou désactivez l'extension de la section Détails.</span><span class="sxs-lookup"><span data-stu-id="7714f-129">Toggle the expansion of the Details section.</span></span>
9. <span data-ttu-id="7714f-130">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="7714f-130">Click New.</span></span>
10. <span data-ttu-id="7714f-131">Dans le champ Code postal du lieu de livraison de départ, saisissez « 30301 ».</span><span class="sxs-lookup"><span data-stu-id="7714f-131">In the Drop-off Postal Code From field, type '30301'.</span></span>
11. <span data-ttu-id="7714f-132">Dans le champ Code postal de lieu de livraison d'arrivée, saisissez « 30318 ».</span><span class="sxs-lookup"><span data-stu-id="7714f-132">In the Drop-off Postal Code To field, type '30318'.</span></span>
12. <span data-ttu-id="7714f-133">Dans le champ Région du pays de livraison, saisissez « USA ».</span><span class="sxs-lookup"><span data-stu-id="7714f-133">In the Drop-off Country Region field, type 'USA'.</span></span>
13. <span data-ttu-id="7714f-134">Dans le champ <1.00 Lbs, saisissez « 100 ».</span><span class="sxs-lookup"><span data-stu-id="7714f-134">In the <1.00 Lbs field, type '100'.</span></span>
    * <span data-ttu-id="7714f-135">Insérez le taux par livres si le poids total de la charge est inférieur à 1 livre.</span><span class="sxs-lookup"><span data-stu-id="7714f-135">Insert the rate per lbs if the total weight of the load is less than 1 pound.</span></span>  
14. <span data-ttu-id="7714f-136">Dans le champ <5,00 Lbs, saisissez « 300 ».</span><span class="sxs-lookup"><span data-stu-id="7714f-136">In the <5.00 Lbs field, type '300'.</span></span>
    * <span data-ttu-id="7714f-137">Insérez le taux par livres si le poids total de la charge est inférieur à 5 livres.</span><span class="sxs-lookup"><span data-stu-id="7714f-137">Insert the rate per lbs if the total weight of the load is less than 5 pounds.</span></span>  
15. <span data-ttu-id="7714f-138">Dans le champ <20,00 Lbs, saisissez « 500 ».</span><span class="sxs-lookup"><span data-stu-id="7714f-138">In the <20.00 Lbs field, type '500'.</span></span>
    * <span data-ttu-id="7714f-139">Insérez le taux par livres si le poids total de la charge est inférieur à 20 livres.</span><span class="sxs-lookup"><span data-stu-id="7714f-139">Insert the rate per lbs if the total weight of the load is less than 20 pounds.</span></span>  
16. <span data-ttu-id="7714f-140">Dans le champ <100,00 Lbs, saisissez « 1000 ».</span><span class="sxs-lookup"><span data-stu-id="7714f-140">In the <100.00 Lbs field, type '1000'.</span></span>
    * <span data-ttu-id="7714f-141">Insérez le taux par livres si le poids total de la charge est inférieur à 100 livres.</span><span class="sxs-lookup"><span data-stu-id="7714f-141">Insert the rate per lbs if the total weight of the load is less than 100 pounds.</span></span>  
17. <span data-ttu-id="7714f-142">Dans le champ <1 000,00 Lbs, saisissez « 3000 ».</span><span class="sxs-lookup"><span data-stu-id="7714f-142">In the <1,000.00 Lbs field, type '3000'.</span></span>
    * <span data-ttu-id="7714f-143">Insérez le taux par livres si le poids total de la charge est inférieur à 1000 livres.</span><span class="sxs-lookup"><span data-stu-id="7714f-143">Insert the rate per lbs if the total weight of the load is less than 1000 pounds.</span></span>  
18. <span data-ttu-id="7714f-144">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="7714f-144">Click Save.</span></span>
19. <span data-ttu-id="7714f-145">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="7714f-145">Close the page.</span></span>

## <a name="assign-rate-base"></a><span data-ttu-id="7714f-146">Affecter la base de taux</span><span class="sxs-lookup"><span data-stu-id="7714f-146">Assign rate base</span></span>
1. <span data-ttu-id="7714f-147">Activer l'extension de la section des attributions de la base de taux.</span><span class="sxs-lookup"><span data-stu-id="7714f-147">Toggle the expansion of the Rate base assignments section.</span></span>
2. <span data-ttu-id="7714f-148">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="7714f-148">Click New.</span></span>
    * <span data-ttu-id="7714f-149">Vous pouvez avoir plusieurs affectations de base de taux pour chaque table maître des taux.</span><span class="sxs-lookup"><span data-stu-id="7714f-149">You can have several rate base assignments for each rate master.</span></span> <span data-ttu-id="7714f-150">Cela permet de créer différents niveaux de prix pour chaque transporteur selon les destinations, les services ou les bases de taux.</span><span class="sxs-lookup"><span data-stu-id="7714f-150">This makes it possible to create several different price points for each carrier depending on destinations, services, or different rate bases.</span></span> <span data-ttu-id="7714f-151">Dans cette procédure, vous allez créer une seule affectation de base de taux.</span><span class="sxs-lookup"><span data-stu-id="7714f-151">In this procedure you will only create one rate base assignment.</span></span>  
3. <span data-ttu-id="7714f-152">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="7714f-152">In the Name field, type a value.</span></span>
4. <span data-ttu-id="7714f-153">Dans le champ Base de taux, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="7714f-153">In the Rate base field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="7714f-154">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7714f-154">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="7714f-155">Dans le champ Service, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="7714f-155">In the Service field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="7714f-156">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="7714f-156">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="7714f-157">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7714f-157">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="7714f-158">Dans le champ Code postal d'enlèvement, saisissez « 98052 ».</span><span class="sxs-lookup"><span data-stu-id="7714f-158">In the Pick-up Postal Code field, type '98052'.</span></span>
    * <span data-ttu-id="7714f-159">Spécifiez le code postal à partir duquel cette affectation de base de taux doit être valide.</span><span class="sxs-lookup"><span data-stu-id="7714f-159">Specify which postal code this rate base assignment should be valid from.</span></span>    
10. <span data-ttu-id="7714f-160">Dans le champ Région du pays d'enlèvement, saisissez « USA ».</span><span class="sxs-lookup"><span data-stu-id="7714f-160">In the Pick-up Country Region field, type 'USA'.</span></span>
11. <span data-ttu-id="7714f-161">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="7714f-161">Click Save.</span></span>

