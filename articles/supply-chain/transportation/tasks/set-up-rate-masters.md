---
title: Paramétrer des tables maître des taux
description: Cette procédure décrit le processus de paramétrage des données principales de taux.
author: ShylaThompson
manager: tfehr
ms.date: 10/16/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSBreakMaster,TMSRateMaster,TMSRateMasterBase,TMSRateBaseType, TMSRouteWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 47fa7edeba81d826a00668a2da74113f552437f4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974258"
---
# <a name="set-up-rate-masters"></a><span data-ttu-id="6a398-103">Paramétrer des tables maître des taux</span><span class="sxs-lookup"><span data-stu-id="6a398-103">Set up rate masters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6a398-104">Cette procédure décrit le processus de paramétrage des données principales de taux.</span><span class="sxs-lookup"><span data-stu-id="6a398-104">This procedure shows you how to set up a rate master.</span></span> <span data-ttu-id="6a398-105">Le responsable logistique configure généralement les données principales de taux en fonction des contacts signés avec les transporteurs.</span><span class="sxs-lookup"><span data-stu-id="6a398-105">The logistic manager usually sets up rate masters, depending on the contracts signed with the carriers.</span></span> <span data-ttu-id="6a398-106">Dans ce scénario vous paramètrerez des données principales de taux pour un transporteur aérien.</span><span class="sxs-lookup"><span data-stu-id="6a398-106">In this scenario you will set up a rate master for an air carrier.</span></span> <span data-ttu-id="6a398-107">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="6a398-107">The demo data company used to create this procedure is USMF.</span></span>

## <a name="set-up-break-master"></a><span data-ttu-id="6a398-108">Paramétrer une table maître des pauses</span><span class="sxs-lookup"><span data-stu-id="6a398-108">Set up break master</span></span>

1. <span data-ttu-id="6a398-109">Accédez à **Gestion du transport > Configurer > Taux > Table maître des pauses**.</span><span class="sxs-lookup"><span data-stu-id="6a398-109">Go to **Transportation management > Setup > Rating > Break master**.</span></span> <span data-ttu-id="6a398-110">Les données principales des ruptures permettent de définir la structure de tarification et les points d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="6a398-110">Break masters are used to define the pricing structure and its breakpoints.</span></span> <span data-ttu-id="6a398-111">La structure de tarification utilise la tarification progressive basée sur les dimensions physiques.</span><span class="sxs-lookup"><span data-stu-id="6a398-111">The pricing structure uses tiered pricing that is based on physical dimensions.</span></span>  
1. <span data-ttu-id="6a398-112">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="6a398-112">Select **New**.</span></span>
1. <span data-ttu-id="6a398-113">Dans le champ **Table maître des pauses**, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6a398-113">In the **Break master** field, enter a value.</span></span>
1. <span data-ttu-id="6a398-114">Dans le champ **Nom**, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6a398-114">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="6a398-115">Dans le champ **Type de données**, sélectionnez le type de données.</span><span class="sxs-lookup"><span data-stu-id="6a398-115">In the **Data type** field, select the data type.</span></span>
1. <span data-ttu-id="6a398-116">Dans le champ **Comparaison**, saisissez le type de comparaison demandé (à l'aide des opérateurs).</span><span class="sxs-lookup"><span data-stu-id="6a398-116">In the **Comparison** field, enter the kind of comparison requested (using operators).</span></span>
1. <span data-ttu-id="6a398-117">Entrez le champ **Valeurs de pause** entrez l'unité de pause.</span><span class="sxs-lookup"><span data-stu-id="6a398-117">In the **Break unit** field, enter the break unit.</span></span>
1. <span data-ttu-id="6a398-118">Dans la section **Détails**, créez autant de pauses que nécessaire pour la structure de prix.</span><span class="sxs-lookup"><span data-stu-id="6a398-118">In the **Details** section, create as many breaks as needed for the pricing structure.</span></span>
1. <span data-ttu-id="6a398-119">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6a398-119">Select **Save**.</span></span>

## <a name="set-up-rate-master"></a><span data-ttu-id="6a398-120">Paramétrer des données principales de taux</span><span class="sxs-lookup"><span data-stu-id="6a398-120">Set up rate master</span></span>

1. <span data-ttu-id="6a398-121">Accédez à **Gestion du transport > Configurer > Taux > Données principales de taux**.</span><span class="sxs-lookup"><span data-stu-id="6a398-121">Go to **Transportation management > Setup > Rating > Rate master**.</span></span>
1. <span data-ttu-id="6a398-122">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="6a398-122">Select **New**.</span></span>
1. <span data-ttu-id="6a398-123">Dans le champ **Données principales de taux**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6a398-123">In the **Rate master** field, type a value.</span></span>
1. <span data-ttu-id="6a398-124">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="6a398-124">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="6a398-125">Dans le champ **ID des métadonnées de taux**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="6a398-125">In the **Rating metadata ID** field, select the drop-down button to open the lookup.</span></span> <span data-ttu-id="6a398-126">L'ID des métadonnées de taux détermine les données nécessaires pour les données principales du taux, car cela définit les métadonnées attendues par le moteur de gestion des transports utilisant cette table maître des taux.</span><span class="sxs-lookup"><span data-stu-id="6a398-126">The rating metadata ID will determine the data needed for the rate master, as it defines the metadata expected by the transportation management engine using this rate master.</span></span>  
1. <span data-ttu-id="6a398-127">Pour cette exemple, sélectionnez l'option P2P.</span><span class="sxs-lookup"><span data-stu-id="6a398-127">For this example, select the P2P option.</span></span> <span data-ttu-id="6a398-128">Ceci est déjà défini dans les données de démonstration.</span><span class="sxs-lookup"><span data-stu-id="6a398-128">This is already defined in the demo data.</span></span>
1. <span data-ttu-id="6a398-129">Dans la liste, sélectionnez le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6a398-129">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="6a398-130">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6a398-130">Select **Save**.</span></span>

## <a name="set-up-rate-base"></a><span data-ttu-id="6a398-131">Paramétrer la base de taux</span><span class="sxs-lookup"><span data-stu-id="6a398-131">Set up rate base</span></span>

1. <span data-ttu-id="6a398-132">Sélectionnez la **base de taux**.</span><span class="sxs-lookup"><span data-stu-id="6a398-132">Select **Rate base**.</span></span>
    * <span data-ttu-id="6a398-133">La base de taux détermine le taux du transporteur, et peut être utilisée pour paramétrer une structure tarifaire car elle structure les taux dans les points d'arrêt définis dans les données principales des ruptures.</span><span class="sxs-lookup"><span data-stu-id="6a398-133">The rate base determines the rate of the carrier, and can be used to set up a tariff structure as it structures the rates in the breakpoints defined in the break master.</span></span>  
2. <span data-ttu-id="6a398-134">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="6a398-134">Select **New**.</span></span>
3. <span data-ttu-id="6a398-135">Dans le champ **Base de taux**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6a398-135">In the **Rate base** field, type a value.</span></span>
4. <span data-ttu-id="6a398-136">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="6a398-136">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="6a398-137">Dans le champ **Données principales de pause**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="6a398-137">In the **Break master** field, select the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="6a398-138">Les données principales des ruptures permettent de définir la structure de tarification et les points d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="6a398-138">Break masters are used to define the pricing structure and its breakpoints.</span></span> <span data-ttu-id="6a398-139">La structure de tarification utilise la tarification progressive basée sur les dimensions physiques.</span><span class="sxs-lookup"><span data-stu-id="6a398-139">The pricing structure uses tiered pricing that is based on physical dimensions.</span></span>  
6. <span data-ttu-id="6a398-140">Pour cet exemple, utilisez le poids.</span><span class="sxs-lookup"><span data-stu-id="6a398-140">For this example, use weight.</span></span> <span data-ttu-id="6a398-141">Ceci est déjà défini dans les données de démonstration.</span><span class="sxs-lookup"><span data-stu-id="6a398-141">This is already defined in the demo data.</span></span>
7. <span data-ttu-id="6a398-142">Dans la liste, sélectionnez le lien dans la ligne en surbrillance.</span><span class="sxs-lookup"><span data-stu-id="6a398-142">In the list, select the link in the highlighted row.</span></span>
8. <span data-ttu-id="6a398-143">Développez la section **Détails**.</span><span class="sxs-lookup"><span data-stu-id="6a398-143">Expand the **Details** section.</span></span>
9. <span data-ttu-id="6a398-144">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="6a398-144">Select **New**.</span></span>
10. <span data-ttu-id="6a398-145">Dans le champ **Code postal du lieu de livraison de départ**, saisissez « 30301 ».</span><span class="sxs-lookup"><span data-stu-id="6a398-145">In the **Drop-off Postal Code From** field, type "30301".</span></span>
11. <span data-ttu-id="6a398-146">Dans le champ **Code postal de lieu de livraison d'arrivée**, saisissez « 30318 ».</span><span class="sxs-lookup"><span data-stu-id="6a398-146">In the **Drop-off Postal Code To** field, type "30318".</span></span>
12. <span data-ttu-id="6a398-147">Dans le champ **Région du pays de livraison**, saisissez « USA ».</span><span class="sxs-lookup"><span data-stu-id="6a398-147">In the **Drop-off Country Region** field, type "USA".</span></span>
13. <span data-ttu-id="6a398-148">Dans le champ **<1,00 Lb**, saisissez « 100 ».</span><span class="sxs-lookup"><span data-stu-id="6a398-148">In the **<1.00 Lbs** field, type "100".</span></span>
    * <span data-ttu-id="6a398-149">Insérez le taux par livres si le poids total de la charge est inférieur à 1 livre.</span><span class="sxs-lookup"><span data-stu-id="6a398-149">Insert the rate per pounds if the total weight of the load is less than 1 pound.</span></span>  
14. <span data-ttu-id="6a398-150">Dans le champ **<5,00 Lb**, saisissez « 300 ».</span><span class="sxs-lookup"><span data-stu-id="6a398-150">In the **<5.00 Lbs** field, type "300".</span></span>
    * <span data-ttu-id="6a398-151">Insérez le taux par livres si le poids total de la charge est inférieur à 5 livres.</span><span class="sxs-lookup"><span data-stu-id="6a398-151">Insert the rate per pounds if the total weight of the load is less than 5 pounds.</span></span>  
15. <span data-ttu-id="6a398-152">Dans le champ **<20,00 Lb**, saisissez « 500 ».</span><span class="sxs-lookup"><span data-stu-id="6a398-152">In the **<20.00 Lbs** field, type "500".</span></span>
    * <span data-ttu-id="6a398-153">Insérez le taux par livres si le poids total de la charge est inférieur à 20 livres.</span><span class="sxs-lookup"><span data-stu-id="6a398-153">Insert the rate per pounds if the total weight of the load is less than 20 pounds.</span></span>  
16. <span data-ttu-id="6a398-154">Dans le champ **<100,00 Lb**, saisissez « 1000 ».</span><span class="sxs-lookup"><span data-stu-id="6a398-154">In the **<100.00 Lbs** field, type "1000".</span></span>
    * <span data-ttu-id="6a398-155">Insérez le taux par livres si le poids total de la charge est inférieur à 100 livres.</span><span class="sxs-lookup"><span data-stu-id="6a398-155">Insert the rate per pounds if the total weight of the load is less than 100 pounds.</span></span>  
17. <span data-ttu-id="6a398-156">Dans le champ **<1 000,00 Lb**, saisissez « 3 000 ».</span><span class="sxs-lookup"><span data-stu-id="6a398-156">In the **<1,000.00 Lbs** field, type "3000".</span></span>
    * <span data-ttu-id="6a398-157">Insérez le taux par livres si le poids total de la charge est inférieur à 1 000 livres.</span><span class="sxs-lookup"><span data-stu-id="6a398-157">Insert the rate per pounds if the total weight of the load is less than 1000 pounds.</span></span>  
18. <span data-ttu-id="6a398-158">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6a398-158">Select **Save**.</span></span>
19. <span data-ttu-id="6a398-159">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="6a398-159">Close the page.</span></span>

## <a name="assign-rate-base"></a><span data-ttu-id="6a398-160">Affecter la base de taux</span><span class="sxs-lookup"><span data-stu-id="6a398-160">Assign rate base</span></span>

1. <span data-ttu-id="6a398-161">Développer la section **Affectations de base de taux**.</span><span class="sxs-lookup"><span data-stu-id="6a398-161">Expand the **Rate base assignments** section.</span></span>
2. <span data-ttu-id="6a398-162">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="6a398-162">Select **New**.</span></span>
    * <span data-ttu-id="6a398-163">Vous pouvez avoir plusieurs affectations de base de taux pour chaque table maître des taux.</span><span class="sxs-lookup"><span data-stu-id="6a398-163">You can have several rate base assignments for each rate master.</span></span> <span data-ttu-id="6a398-164">Cela permet de créer différents niveaux de prix pour chaque transporteur selon les destinations, les services ou les bases de taux.</span><span class="sxs-lookup"><span data-stu-id="6a398-164">This makes it possible to create several different price points for each carrier depending on destinations, services, or different rate bases.</span></span> <span data-ttu-id="6a398-165">Dans cette procédure, vous allez créer une seule affectation de base de taux.</span><span class="sxs-lookup"><span data-stu-id="6a398-165">In this procedure you will only create one rate base assignment.</span></span>  
3. <span data-ttu-id="6a398-166">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="6a398-166">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="6a398-167">Dans le champ **Base de taux**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="6a398-167">In the **Rate base** field, select the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="6a398-168">Dans la liste, sélectionnez le lien dans la ligne en surbrillance.</span><span class="sxs-lookup"><span data-stu-id="6a398-168">In the list, select the link in the highlighted row.</span></span>
6. <span data-ttu-id="6a398-169">Dans le champ **Service**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="6a398-169">In the **Service** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="6a398-170">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="6a398-170">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="6a398-171">Dans la liste, sélectionnez le lien dans la ligne en surbrillance.</span><span class="sxs-lookup"><span data-stu-id="6a398-171">In the list, select the link in the highlighted row.</span></span>
9. <span data-ttu-id="6a398-172">Dans le champ **Code postal d'enlèvement**, saisissez « 98052 ».</span><span class="sxs-lookup"><span data-stu-id="6a398-172">In the **Pick-up Postal Code** field, type "98052".</span></span>
    * <span data-ttu-id="6a398-173">Spécifiez le code postal à partir duquel cette affectation de base de taux doit être valide.</span><span class="sxs-lookup"><span data-stu-id="6a398-173">Specify which postal code this rate base assignment should be valid from.</span></span>
10. <span data-ttu-id="6a398-174">Dans le champ **Région du pays d'enlèvement**, saisissez « USA ».</span><span class="sxs-lookup"><span data-stu-id="6a398-174">In the **Pick-up Country Region** field, type "USA".</span></span>
11. <span data-ttu-id="6a398-175">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6a398-175">Select **Save**.</span></span>
