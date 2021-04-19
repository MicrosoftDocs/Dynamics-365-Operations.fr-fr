---
title: Tenir à jour la nomenclature d’un modèle de configuration de produit
description: L’exécution de cette procédure nécessite un modèle de configuration de produit existant.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCBOMLineDetails, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 49aa17aa376f8536e9d2290292f877d314c2c078
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818011"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a><span data-ttu-id="700ee-103">Tenir à jour la nomenclature d’un modèle de configuration de produit</span><span class="sxs-lookup"><span data-stu-id="700ee-103">Maintain BOM for a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="700ee-104">L’exécution de cette procédure nécessite un modèle de configuration de produit existant.</span><span class="sxs-lookup"><span data-stu-id="700ee-104">Running this procedure requires an existing product configuration model.</span></span> <span data-ttu-id="700ee-105">Cette procédure utilise le modèle de haut-parleur haut de gamme de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="700ee-105">The High end speaker model in the demo company USMF is used to create this procedure.</span></span>


## <a name="add-a-bom-line"></a><span data-ttu-id="700ee-106">Ajouter une ligne de nomenclature</span><span class="sxs-lookup"><span data-stu-id="700ee-106">Add a BOM line</span></span>
1. <span data-ttu-id="700ee-107">Cliquez sur Définition du modèle de variante de produit.</span><span class="sxs-lookup"><span data-stu-id="700ee-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="700ee-108">Cliquez sur Modèles de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="700ee-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="700ee-109">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="700ee-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="700ee-110">Sélectionnez le Haut-parleur haut de gamme pour cette procédure.</span><span class="sxs-lookup"><span data-stu-id="700ee-110">Select the High end speaker for this procedure.</span></span>  
4. <span data-ttu-id="700ee-111">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="700ee-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="700ee-112">Développer la section Lignes de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="700ee-112">Expand the BOM lines section.</span></span>
6. <span data-ttu-id="700ee-113">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="700ee-113">Click Add.</span></span>
7. <span data-ttu-id="700ee-114">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="700ee-114">In the Name field, type a value.</span></span>
8. <span data-ttu-id="700ee-115">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="700ee-115">In the Description field, type a value.</span></span>
9. <span data-ttu-id="700ee-116">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="700ee-116">Click Save.</span></span>

## <a name="add-bom-line-details"></a><span data-ttu-id="700ee-117">Ajouter les détails de ligne de nomenclature</span><span class="sxs-lookup"><span data-stu-id="700ee-117">Add BOM line details</span></span>
1. <span data-ttu-id="700ee-118">Cliquez sur Détails de ligne de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="700ee-118">Click BOM line details.</span></span>
2. <span data-ttu-id="700ee-119">Entrez ou sélectionnez une valeur dans le champ Numéro d’article.</span><span class="sxs-lookup"><span data-stu-id="700ee-119">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="700ee-120">Par exemple, vous pouvez sélectionner l’article M0055.</span><span class="sxs-lookup"><span data-stu-id="700ee-120">For example, you can select the item M0055.</span></span>  
    * <span data-ttu-id="700ee-121">Pour chaque propriété de ligne de nomenclature, vous pouvez sélectionner si elle prend une valeur fixe ou est mise en correspondance avec un attribut.</span><span class="sxs-lookup"><span data-stu-id="700ee-121">For each BOM line property, you can select if it takes a fixed value or is mapped to an attribute.</span></span>  
3. <span data-ttu-id="700ee-122">Activez la case à cocher Définir.</span><span class="sxs-lookup"><span data-stu-id="700ee-122">Select the Set check box.</span></span>
4. <span data-ttu-id="700ee-123">Sélectionnez Oui dans le champ Calcul.</span><span class="sxs-lookup"><span data-stu-id="700ee-123">Select Yes in the Calculation field.</span></span>
    * <span data-ttu-id="700ee-124">Le fait de définir la propriété du calcul sur Oui garantit que la ligne de nomenclature sera incluse dans les calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="700ee-124">Setting the Calculation property to Yes ensures that the BOM line is included in cost calculations.</span></span>  
5. <span data-ttu-id="700ee-125">Cliquez sur l’onglet Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="700ee-125">Click the Setup tab.</span></span>
6. <span data-ttu-id="700ee-126">Activez la case à cocher Définir.</span><span class="sxs-lookup"><span data-stu-id="700ee-126">Select the Set check box.</span></span>
7. <span data-ttu-id="700ee-127">Dans le champ Quantité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="700ee-127">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="700ee-128">Le champ de quantité détermine la quantité d’articles qui sera incluse dans la nomenclature.</span><span class="sxs-lookup"><span data-stu-id="700ee-128">The quantity field determines how much of the item that will be included in the BOM.</span></span> <span data-ttu-id="700ee-129">Cela peut être un candidat idéal pour une mise en correspondance d’attributs.</span><span class="sxs-lookup"><span data-stu-id="700ee-129">This could be an obvious candidate for an attribute mapping.</span></span>  
8. <span data-ttu-id="700ee-130">Cliquez sur l’onglet Dimension.</span><span class="sxs-lookup"><span data-stu-id="700ee-130">Click the Dimension tab.</span></span>
    * <span data-ttu-id="700ee-131">Vérifiez si des dimensions de produit sont actives ; elles doivent donc avoir une valeur ou un attribut affecté.</span><span class="sxs-lookup"><span data-stu-id="700ee-131">Verify if any of the product dimensions are active,  and therefore must have a value or attribute assigned.</span></span>  
9. <span data-ttu-id="700ee-132">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="700ee-132">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]