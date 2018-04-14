--- 
title: "Tenir à jour la nomenclature d'un modèle de configuration de produit"
description: "L'exécution de cette procédure nécessite un modèle de configuration de produit existant."
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: ef7fc230ea028ef790ad7989fe53f95c70c3b5b1
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---
# <a name="maintain-bom-for-a-product-configuration-model"></a><span data-ttu-id="e995f-103">Tenir à jour la nomenclature d'un modèle de configuration de produit</span><span class="sxs-lookup"><span data-stu-id="e995f-103">Maintain BOM for a product configuration model</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e995f-104">L'exécution de cette procédure nécessite un modèle de configuration de produit existant.</span><span class="sxs-lookup"><span data-stu-id="e995f-104">Running this procedure requires an existing product configuration model.</span></span> <span data-ttu-id="e995f-105">Cette procédure utilise le modèle de haut-parleur haut de gamme de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="e995f-105">The High end speaker model in the demo company USMF is used to create this procedure.</span></span>


## <a name="add-a-bom-line"></a><span data-ttu-id="e995f-106">Ajouter une ligne de nomenclature</span><span class="sxs-lookup"><span data-stu-id="e995f-106">Add a BOM line</span></span>
1. <span data-ttu-id="e995f-107">Cliquez sur Définition du modèle de variante de produit.</span><span class="sxs-lookup"><span data-stu-id="e995f-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="e995f-108">Cliquez sur Modèles de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="e995f-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="e995f-109">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="e995f-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="e995f-110">Sélectionnez le Haut-parleur haut de gamme pour cette procédure.</span><span class="sxs-lookup"><span data-stu-id="e995f-110">Select the High end speaker for this procedure.</span></span>  
4. <span data-ttu-id="e995f-111">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e995f-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="e995f-112">Développer la section Lignes de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="e995f-112">Expand the BOM lines section.</span></span>
6. <span data-ttu-id="e995f-113">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e995f-113">Click Add.</span></span>
7. <span data-ttu-id="e995f-114">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="e995f-114">In the Name field, type a value.</span></span>
8. <span data-ttu-id="e995f-115">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e995f-115">In the Description field, type a value.</span></span>
9. <span data-ttu-id="e995f-116">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e995f-116">Click Save.</span></span>

## <a name="add-bom-line-details"></a><span data-ttu-id="e995f-117">Ajouter les détails de ligne de nomenclature</span><span class="sxs-lookup"><span data-stu-id="e995f-117">Add BOM line details</span></span>
1. <span data-ttu-id="e995f-118">Cliquez sur Détails de ligne de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="e995f-118">Click BOM line details.</span></span>
2. <span data-ttu-id="e995f-119">Entrez ou sélectionnez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="e995f-119">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="e995f-120">Par exemple, vous pouvez sélectionner l'article M0055.</span><span class="sxs-lookup"><span data-stu-id="e995f-120">For example, you can select the item M0055.</span></span>  
    * <span data-ttu-id="e995f-121">Pour chaque propriété de ligne de nomenclature, vous pouvez sélectionner si elle prend une valeur fixe ou est mise en correspondance avec un attribut.</span><span class="sxs-lookup"><span data-stu-id="e995f-121">For each BOM line property, you can select if it takes a fixed value or is mapped to an attribute.</span></span>  
3. <span data-ttu-id="e995f-122">Activez la case à cocher Définir.</span><span class="sxs-lookup"><span data-stu-id="e995f-122">Select the Set check box.</span></span>
4. <span data-ttu-id="e995f-123">Sélectionnez Oui dans le champ Calcul.</span><span class="sxs-lookup"><span data-stu-id="e995f-123">Select Yes in the Calculation field.</span></span>
    * <span data-ttu-id="e995f-124">Le fait de définir la propriété du calcul sur Oui garantit que la ligne de nomenclature sera incluse dans les calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="e995f-124">Setting the Calculation property to Yes ensures that the BOM line is included in cost calculations.</span></span>  
5. <span data-ttu-id="e995f-125">Cliquez sur l'onglet Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="e995f-125">Click the Setup tab.</span></span>
6. <span data-ttu-id="e995f-126">Activez la case à cocher Définir.</span><span class="sxs-lookup"><span data-stu-id="e995f-126">Select the Set check box.</span></span>
7. <span data-ttu-id="e995f-127">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="e995f-127">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="e995f-128">Le champ de quantité détermine la quantité d'articles qui sera incluse dans la nomenclature.</span><span class="sxs-lookup"><span data-stu-id="e995f-128">The quantity field determines how much of the item that will be included in the BOM.</span></span> <span data-ttu-id="e995f-129">Cela peut être un candidat idéal pour une mise en correspondance d'attributs.</span><span class="sxs-lookup"><span data-stu-id="e995f-129">This could be an obvious candidate for an attribute mapping.</span></span>  
8. <span data-ttu-id="e995f-130">Cliquez sur l'onglet Dimension.</span><span class="sxs-lookup"><span data-stu-id="e995f-130">Click the Dimension tab.</span></span>
    * <span data-ttu-id="e995f-131">Vérifiez si des dimensions de produit sont actives ; elles doivent donc avoir une valeur ou un attribut affecté.</span><span class="sxs-lookup"><span data-stu-id="e995f-131">Verify if any of the product dimensions are active,  and therefore must have a value or attribute assigned.</span></span>  
9. <span data-ttu-id="e995f-132">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="e995f-132">Click OK.</span></span>


