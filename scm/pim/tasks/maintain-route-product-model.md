--- 
title: "Tenir à jour une gamme pour un modèle de produit"
description: "L'exécution de cette procédure nécessite qu'il existe un modèle de configuration de produit."
author: BibiSp
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bibis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 3f6bacc54664c32a7d42f2befc51c420e29ada56
ms.contentlocale: fr-fr
ms.lasthandoff: 07/28/2017

---
# <a name="maintain-a-route-for-a-product-model"></a><span data-ttu-id="f4ed3-103">Tenir à jour une gamme pour un modèle de produit</span><span class="sxs-lookup"><span data-stu-id="f4ed3-103">Maintain a route for a product model</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f4ed3-104">L'exécution de cette procédure nécessite qu'il existe un modèle de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-104">Running this procedure requires that a product configuration model exists.</span></span> <span data-ttu-id="f4ed3-105">Cette procédure utilise le modèle de haut-parleur haut de gamme de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-105">This procedure uses the High end speaker model in the demo company USMF to walk you through the process.</span></span>


## <a name="add-a-route-operation"></a><span data-ttu-id="f4ed3-106">Ajouter une opération de gamme</span><span class="sxs-lookup"><span data-stu-id="f4ed3-106">Add a route operation</span></span>
1. <span data-ttu-id="f4ed3-107">Cliquez sur Définition du modèle de variante de produit.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="f4ed3-108">Cliquez sur Modèles de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="f4ed3-109">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="f4ed3-110">Sélectionnez le modèle de Haut-parleur haut de gamme pour cet exercice.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-110">Select the High end speaker model for this exercise.</span></span>  
4. <span data-ttu-id="f4ed3-111">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="f4ed3-112">Développez la section Opérations de gamme.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-112">Expand the Route operations section.</span></span>
6. <span data-ttu-id="f4ed3-113">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-113">Click Add.</span></span>
7. <span data-ttu-id="f4ed3-114">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-114">In the Name field, type a value.</span></span>
8. <span data-ttu-id="f4ed3-115">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-115">In the Description field, type a value.</span></span>
9. <span data-ttu-id="f4ed3-116">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-116">Click Save.</span></span>

## <a name="enter-route-operation-details"></a><span data-ttu-id="f4ed3-117">Entrer les détails de l'opération de gamme</span><span class="sxs-lookup"><span data-stu-id="f4ed3-117">Enter route operation details</span></span>
1. <span data-ttu-id="f4ed3-118">Cliquez sur Détails de l'opération de gamme.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-118">Click Route operation details.</span></span>
2. <span data-ttu-id="f4ed3-119">Dans le champ Opération, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-119">In the Operation field, enter or select a value.</span></span>
3. <span data-ttu-id="f4ed3-120">Dans le champ N° opér.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-120">In the Oper.</span></span> <span data-ttu-id="f4ed3-121">N°</span><span class="sxs-lookup"><span data-stu-id="f4ed3-121">No.</span></span> <span data-ttu-id="f4ed3-122">, entrez un numéro.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-122">field, enter a number.</span></span>
    * <span data-ttu-id="f4ed3-123">Les numéros d'opération déterminent la position dans la gamme.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-123">Operation numbers determine the route sequence.</span></span>  
    * <span data-ttu-id="f4ed3-124">Chaque propriété sur une opération de gamme peut obtenir une valeur statique ou être mise en correspondance avec un attribut.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-124">Each property on a route operation can get a static value or be mapped to an attribute.</span></span> <span data-ttu-id="f4ed3-125">La mise en correspondance avec un attribut aura pour résultat que les valeurs seront définies dans le cadre de la configuration.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-125">Mapping to an attribute will result in the value being set as part of the configuration.</span></span>  
4. <span data-ttu-id="f4ed3-126">Dans le champ Groupe de gammes, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-126">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="f4ed3-127">Le groupe de gammes détermine le comportement essentiel pour l'évaluation des coûts, la consommation et le paramétrage.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-127">The route group determines essential behavior for costing, consumption, and setup.</span></span>  
5. <span data-ttu-id="f4ed3-128">Cliquez sur l'onglet Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-128">Click the Setup tab.</span></span>
6. <span data-ttu-id="f4ed3-129">Cliquer sur l'onglet Temps.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-129">Click the Times tab.</span></span>
7. <span data-ttu-id="f4ed3-130">Dans le champ Qté à traiter</span><span class="sxs-lookup"><span data-stu-id="f4ed3-130">In the Process qty.</span></span> <span data-ttu-id="f4ed3-131">, entrez un numéro.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-131">field, enter a number.</span></span>
    * <span data-ttu-id="f4ed3-132">Déterminez le nombre qui sera traité au cours d'une opération.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-132">Determine how many will be processed during one operation.</span></span>  
8. <span data-ttu-id="f4ed3-133">Dans le champ Heures/temps, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-133">In the Hours/time field, enter a number.</span></span>
    * <span data-ttu-id="f4ed3-134">Entrez le ratio de durée.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-134">Enter the time ratio.</span></span>  
9. <span data-ttu-id="f4ed3-135">Activez la case à cocher Définir.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-135">Select the Set check box.</span></span>
10. <span data-ttu-id="f4ed3-136">Entrez un nombre dans le champ Temps d'exécution.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-136">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="f4ed3-137">Déterminez le temps de traitement pour la quantité que vous avez spécifiée.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-137">Determine the processing time for the quantity that you have specified.</span></span>  
11. <span data-ttu-id="f4ed3-138">Cliquez sur l'onglet Demandes de ressources.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-138">Click the Resource requirements tab.</span></span>
12. <span data-ttu-id="f4ed3-139">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-139">Click Add.</span></span>
13. <span data-ttu-id="f4ed3-140">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-140">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="f4ed3-141">Dans le champ Type de demande, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-141">In the Requirement type field, select an option.</span></span>
    * <span data-ttu-id="f4ed3-142">Décidez si vous souhaitez spécifier les ressources particulières ou les capacités qu'elles doivent posséder.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-142">Decide if you want to specify specific resources or capabilities that they must possess.</span></span>  
15. <span data-ttu-id="f4ed3-143">Dans le champ Demande, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-143">In the Requirement field, enter or select a value.</span></span>
16. <span data-ttu-id="f4ed3-144">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="f4ed3-144">Click OK.</span></span>


