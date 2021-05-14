---
title: Tenir à jour la gamme pour le modèle de configuration de produit
description: L’exécution de cette procédure nécessite qu’il existe un modèle de configuration de produit.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCRouteOperationDetails, WrkCtrCapabilityLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 45c6b1e6e75645bb17ce4defa0bca0e6d2131b6e
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921263"
---
# <a name="maintain-route-for-a-product-model"></a><span data-ttu-id="b3200-103">Tenir à jour la gamme pour le modèle de configuration de produit</span><span class="sxs-lookup"><span data-stu-id="b3200-103">Maintain route for a product model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b3200-104">L’exécution de cette procédure nécessite qu’il existe un modèle de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="b3200-104">Running this procedure requires that a product configuration model exists.</span></span> <span data-ttu-id="b3200-105">Cette procédure utilise le modèle de haut-parleur haut de gamme de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="b3200-105">This procedure uses the High end speaker model in the demo company USMF to walk you through the process.</span></span>

## <a name="add-a-route-operation"></a><span data-ttu-id="b3200-106">Ajouter une opération de gamme</span><span class="sxs-lookup"><span data-stu-id="b3200-106">Add a route operation</span></span>

1. <span data-ttu-id="b3200-107">Accédez à **Gestion des informations sur les produits \> Produits \> Modèles de configuration de produit**.</span><span class="sxs-lookup"><span data-stu-id="b3200-107">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="b3200-108">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="b3200-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="b3200-109">Sélectionnez le modèle de Haut-parleur haut de gamme pour cet exercice.</span><span class="sxs-lookup"><span data-stu-id="b3200-109">Select the High end speaker model for this exercise.</span></span>  
1. <span data-ttu-id="b3200-110">Dans la liste, sélectionnez le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b3200-110">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="b3200-111">Développez la section **Opérations de gamme**.</span><span class="sxs-lookup"><span data-stu-id="b3200-111">Expand the **Route operations** section.</span></span>
1. <span data-ttu-id="b3200-112">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="b3200-112">Select **Add**.</span></span>
1. <span data-ttu-id="b3200-113">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="b3200-113">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="b3200-114">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="b3200-114">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="b3200-115">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b3200-115">Select **Save**.</span></span>

## <a name="enter-route-operation-details"></a><span data-ttu-id="b3200-116">Entrer les détails de l’opération de gamme</span><span class="sxs-lookup"><span data-stu-id="b3200-116">Enter route operation details</span></span>

1. <span data-ttu-id="b3200-117">Cliquez sur **Détails de l'opération de gamme**.</span><span class="sxs-lookup"><span data-stu-id="b3200-117">Select **Route operation details**.</span></span>
1. <span data-ttu-id="b3200-118">Dans le champ **Opération**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="b3200-118">In the **Operation** field, enter or select a value.</span></span>
1. <span data-ttu-id="b3200-119">Dans le champ **Au n° opér.**</span><span class="sxs-lookup"><span data-stu-id="b3200-119">In the **Oper. No.**</span></span> <span data-ttu-id="b3200-120">, entrez un numéro.</span><span class="sxs-lookup"><span data-stu-id="b3200-120">field, enter a number.</span></span>
    * <span data-ttu-id="b3200-121">Les numéros d’opération déterminent la position dans la gamme.</span><span class="sxs-lookup"><span data-stu-id="b3200-121">Operation numbers determine the route sequence.</span></span>  
    * <span data-ttu-id="b3200-122">Chaque propriété sur une opération de gamme peut obtenir une valeur statique ou être mise en correspondance avec un attribut.</span><span class="sxs-lookup"><span data-stu-id="b3200-122">Each property on a route operation can get a static value or be mapped to an attribute.</span></span> <span data-ttu-id="b3200-123">La mise en correspondance avec un attribut aura pour résultat que les valeurs seront définies dans le cadre de la configuration.</span><span class="sxs-lookup"><span data-stu-id="b3200-123">Mapping to an attribute will result in the value being set as part of the configuration.</span></span>  
1. <span data-ttu-id="b3200-124">Dans le champ **Groupe de gammes**, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="b3200-124">In the **Route group** field, enter or select a value.</span></span>
    * <span data-ttu-id="b3200-125">Le groupe de gammes détermine le comportement essentiel pour l’évaluation des coûts, la consommation et le paramétrage.</span><span class="sxs-lookup"><span data-stu-id="b3200-125">The route group determines essential behavior for costing, consumption, and setup.</span></span>  
1. <span data-ttu-id="b3200-126">Sélectionnez l’onglet **Paramétrage**.</span><span class="sxs-lookup"><span data-stu-id="b3200-126">Select the **Setup** tab.</span></span>
1. <span data-ttu-id="b3200-127">Sélectionnez l’onglet **Heures**.</span><span class="sxs-lookup"><span data-stu-id="b3200-127">Select the **Times** tab.</span></span>
1. <span data-ttu-id="b3200-128">Dans le champ **Qté à traiter**, entrez un numéro.</span><span class="sxs-lookup"><span data-stu-id="b3200-128">In the **Process qty.** field, enter a number.</span></span>
    * <span data-ttu-id="b3200-129">Déterminez le nombre qui sera traité au cours d’une opération.</span><span class="sxs-lookup"><span data-stu-id="b3200-129">Determine how many will be processed during one operation.</span></span>  
1. <span data-ttu-id="b3200-130">Dans le champ **Heures/temps**, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="b3200-130">In the **Hours/time** field, enter a number.</span></span>
    * <span data-ttu-id="b3200-131">Entrez le ratio de durée.</span><span class="sxs-lookup"><span data-stu-id="b3200-131">Enter the time ratio.</span></span>  
1. <span data-ttu-id="b3200-132">Activez la case à cocher **Définir**.</span><span class="sxs-lookup"><span data-stu-id="b3200-132">Select the **Set** check box.</span></span>
1. <span data-ttu-id="b3200-133">Entrez un nombre dans le champ **Temps d’exécution**.</span><span class="sxs-lookup"><span data-stu-id="b3200-133">In the **Run time** field, enter a number.</span></span>
    * <span data-ttu-id="b3200-134">Déterminez le temps de traitement pour la quantité que vous avez spécifiée.</span><span class="sxs-lookup"><span data-stu-id="b3200-134">Determine the processing time for the quantity that you have specified.</span></span>  
1. <span data-ttu-id="b3200-135">Sélectionnez l’onglet **Demandes de ressources**.</span><span class="sxs-lookup"><span data-stu-id="b3200-135">Select the **Resource requirements** tab.</span></span>
1. <span data-ttu-id="b3200-136">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="b3200-136">Select **Add**.</span></span>
1. <span data-ttu-id="b3200-137">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b3200-137">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="b3200-138">Dans le champ **Type de demande**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="b3200-138">In the **Requirement type** field, select an option.</span></span>
    * <span data-ttu-id="b3200-139">Décidez si vous souhaitez spécifier les ressources particulières ou les capacités qu’elles doivent posséder.</span><span class="sxs-lookup"><span data-stu-id="b3200-139">Decide if you want to specify specific resources or capabilities that they must possess.</span></span>  
1. <span data-ttu-id="b3200-140">Dans le champ **Demande**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="b3200-140">In the **Requirement** field, enter or select a value.</span></span>
1. <span data-ttu-id="b3200-141">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3200-141">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]