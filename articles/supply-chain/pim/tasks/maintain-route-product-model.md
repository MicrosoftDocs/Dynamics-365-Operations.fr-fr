---
title: Tenir à jour la gamme pour le modèle de configuration de produit
description: L'exécution de cette procédure nécessite qu'il existe un modèle de configuration de produit.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCRouteOperationDetails, WrkCtrCapabilityLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cc41f99085e5f30ae29edce296a5e3752cbabd33
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427745"
---
# <a name="maintain-route-for-a-product-model"></a><span data-ttu-id="6b268-103">Tenir à jour la gamme pour le modèle de configuration de produit</span><span class="sxs-lookup"><span data-stu-id="6b268-103">Maintain route for a product model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6b268-104">L'exécution de cette procédure nécessite qu'il existe un modèle de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="6b268-104">Running this procedure requires that a product configuration model exists.</span></span> <span data-ttu-id="6b268-105">Cette procédure utilise le modèle de haut-parleur haut de gamme de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="6b268-105">This procedure uses the High end speaker model in the demo company USMF to walk you through the process.</span></span>


## <a name="add-a-route-operation"></a><span data-ttu-id="6b268-106">Ajouter une opération de gamme</span><span class="sxs-lookup"><span data-stu-id="6b268-106">Add a route operation</span></span>
1. <span data-ttu-id="6b268-107">Cliquez sur Définition du modèle de variante de produit.</span><span class="sxs-lookup"><span data-stu-id="6b268-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="6b268-108">Cliquez sur Modèles de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="6b268-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="6b268-109">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="6b268-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="6b268-110">Sélectionnez le modèle de Haut-parleur haut de gamme pour cet exercice.</span><span class="sxs-lookup"><span data-stu-id="6b268-110">Select the High end speaker model for this exercise.</span></span>  
4. <span data-ttu-id="6b268-111">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6b268-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="6b268-112">Développez la section Opérations de gamme.</span><span class="sxs-lookup"><span data-stu-id="6b268-112">Expand the Route operations section.</span></span>
6. <span data-ttu-id="6b268-113">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="6b268-113">Click Add.</span></span>
7. <span data-ttu-id="6b268-114">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="6b268-114">In the Name field, type a value.</span></span>
8. <span data-ttu-id="6b268-115">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6b268-115">In the Description field, type a value.</span></span>
9. <span data-ttu-id="6b268-116">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="6b268-116">Click Save.</span></span>

## <a name="enter-route-operation-details"></a><span data-ttu-id="6b268-117">Entrer les détails de l'opération de gamme</span><span class="sxs-lookup"><span data-stu-id="6b268-117">Enter route operation details</span></span>
1. <span data-ttu-id="6b268-118">Cliquez sur Détails de l'opération de gamme.</span><span class="sxs-lookup"><span data-stu-id="6b268-118">Click Route operation details.</span></span>
2. <span data-ttu-id="6b268-119">Dans le champ Opération, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6b268-119">In the Operation field, enter or select a value.</span></span>
3. <span data-ttu-id="6b268-120">Dans le champ N° opér.</span><span class="sxs-lookup"><span data-stu-id="6b268-120">In the Oper.</span></span> <span data-ttu-id="6b268-121">N°</span><span class="sxs-lookup"><span data-stu-id="6b268-121">No.</span></span> <span data-ttu-id="6b268-122">, entrez un numéro.</span><span class="sxs-lookup"><span data-stu-id="6b268-122">field, enter a number.</span></span>
    * <span data-ttu-id="6b268-123">Les numéros d'opération déterminent la position dans la gamme.</span><span class="sxs-lookup"><span data-stu-id="6b268-123">Operation numbers determine the route sequence.</span></span>  
    * <span data-ttu-id="6b268-124">Chaque propriété sur une opération de gamme peut obtenir une valeur statique ou être mise en correspondance avec un attribut.</span><span class="sxs-lookup"><span data-stu-id="6b268-124">Each property on a route operation can get a static value or be mapped to an attribute.</span></span> <span data-ttu-id="6b268-125">La mise en correspondance avec un attribut aura pour résultat que les valeurs seront définies dans le cadre de la configuration.</span><span class="sxs-lookup"><span data-stu-id="6b268-125">Mapping to an attribute will result in the value being set as part of the configuration.</span></span>  
4. <span data-ttu-id="6b268-126">Dans le champ Groupe de gammes, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6b268-126">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="6b268-127">Le groupe de gammes détermine le comportement essentiel pour l'évaluation des coûts, la consommation et le paramétrage.</span><span class="sxs-lookup"><span data-stu-id="6b268-127">The route group determines essential behavior for costing, consumption, and setup.</span></span>  
5. <span data-ttu-id="6b268-128">Cliquez sur l'onglet Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="6b268-128">Click the Setup tab.</span></span>
6. <span data-ttu-id="6b268-129">Cliquer sur l'onglet Temps.</span><span class="sxs-lookup"><span data-stu-id="6b268-129">Click the Times tab.</span></span>
7. <span data-ttu-id="6b268-130">Dans le champ Qté à traiter , entrez un numéro.</span><span class="sxs-lookup"><span data-stu-id="6b268-130">In the Process qty. field, enter a number.</span></span>
    * <span data-ttu-id="6b268-131">Déterminez le nombre qui sera traité au cours d'une opération.</span><span class="sxs-lookup"><span data-stu-id="6b268-131">Determine how many will be processed during one operation.</span></span>  
8. <span data-ttu-id="6b268-132">Dans le champ Heures/temps, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="6b268-132">In the Hours/time field, enter a number.</span></span>
    * <span data-ttu-id="6b268-133">Entrez le ratio de durée.</span><span class="sxs-lookup"><span data-stu-id="6b268-133">Enter the time ratio.</span></span>  
9. <span data-ttu-id="6b268-134">Activez la case à cocher Définir.</span><span class="sxs-lookup"><span data-stu-id="6b268-134">Select the Set check box.</span></span>
10. <span data-ttu-id="6b268-135">Entrez un nombre dans le champ Temps d'exécution.</span><span class="sxs-lookup"><span data-stu-id="6b268-135">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="6b268-136">Déterminez le temps de traitement pour la quantité que vous avez spécifiée.</span><span class="sxs-lookup"><span data-stu-id="6b268-136">Determine the processing time for the quantity that you have specified.</span></span>  
11. <span data-ttu-id="6b268-137">Cliquez sur l'onglet Demandes de ressources.</span><span class="sxs-lookup"><span data-stu-id="6b268-137">Click the Resource requirements tab.</span></span>
12. <span data-ttu-id="6b268-138">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="6b268-138">Click Add.</span></span>
13. <span data-ttu-id="6b268-139">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6b268-139">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="6b268-140">Dans le champ Type de demande, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="6b268-140">In the Requirement type field, select an option.</span></span>
    * <span data-ttu-id="6b268-141">Décidez si vous souhaitez spécifier les ressources particulières ou les capacités qu'elles doivent posséder.</span><span class="sxs-lookup"><span data-stu-id="6b268-141">Decide if you want to specify specific resources or capabilities that they must possess.</span></span>  
15. <span data-ttu-id="6b268-142">Dans le champ Demande, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="6b268-142">In the Requirement field, enter or select a value.</span></span>
16. <span data-ttu-id="6b268-143">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="6b268-143">Click OK.</span></span>

