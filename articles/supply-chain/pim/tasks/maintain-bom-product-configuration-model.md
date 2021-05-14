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
ms.openlocfilehash: b4ad73265e321b6339c061a7866b55cb2769954b
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921315"
---
# <a name="maintain-bom-for-a-product-configuration-model"></a><span data-ttu-id="51ad1-103">Tenir à jour la nomenclature d’un modèle de configuration de produit</span><span class="sxs-lookup"><span data-stu-id="51ad1-103">Maintain BOM for a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="51ad1-104">L’exécution de cette procédure nécessite un modèle de configuration de produit existant.</span><span class="sxs-lookup"><span data-stu-id="51ad1-104">Running this procedure requires an existing product configuration model.</span></span> <span data-ttu-id="51ad1-105">Cette procédure utilise le modèle de haut-parleur haut de gamme de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="51ad1-105">The High end speaker model in the demo company USMF is used to create this procedure.</span></span>

## <a name="add-a-bom-line"></a><span data-ttu-id="51ad1-106">Ajouter une ligne de nomenclature</span><span class="sxs-lookup"><span data-stu-id="51ad1-106">Add a BOM line</span></span>

1. <span data-ttu-id="51ad1-107">Accédez à **Gestion des informations sur les produits \> Produits \> Modèles de configuration de produit**.</span><span class="sxs-lookup"><span data-stu-id="51ad1-107">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="51ad1-108">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="51ad1-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="51ad1-109">Sélectionnez le Haut-parleur haut de gamme pour cette procédure.</span><span class="sxs-lookup"><span data-stu-id="51ad1-109">Select the High end speaker for this procedure.</span></span>  
1. <span data-ttu-id="51ad1-110">Dans la liste, sélectionnez le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="51ad1-110">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="51ad1-111">Développer la section **Lignes de nomenclature**.</span><span class="sxs-lookup"><span data-stu-id="51ad1-111">Expand the **BOM lines** section.</span></span>
1. <span data-ttu-id="51ad1-112">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="51ad1-112">Select **Add**.</span></span>
1. <span data-ttu-id="51ad1-113">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="51ad1-113">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="51ad1-114">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="51ad1-114">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="51ad1-115">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="51ad1-115">Select **Save**.</span></span>

## <a name="add-bom-line-details"></a><span data-ttu-id="51ad1-116">Ajouter les détails de ligne de nomenclature</span><span class="sxs-lookup"><span data-stu-id="51ad1-116">Add BOM line details</span></span>

1. <span data-ttu-id="51ad1-117">Sélectionnez **Détails de la ligne de nomenclature**.</span><span class="sxs-lookup"><span data-stu-id="51ad1-117">Select **BOM line details**.</span></span>
2. <span data-ttu-id="51ad1-118">Entrez ou sélectionnez une valeur dans le champ **Numéro d’article**.</span><span class="sxs-lookup"><span data-stu-id="51ad1-118">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="51ad1-119">Par exemple, vous pouvez sélectionner l’article M0055.</span><span class="sxs-lookup"><span data-stu-id="51ad1-119">For example, you can select the item M0055.</span></span>  
    * <span data-ttu-id="51ad1-120">Pour chaque propriété de ligne de nomenclature, vous pouvez sélectionner si elle prend une valeur fixe ou est mise en correspondance avec un attribut.</span><span class="sxs-lookup"><span data-stu-id="51ad1-120">For each BOM line property, you can select if it takes a fixed value or is mapped to an attribute.</span></span>  
3. <span data-ttu-id="51ad1-121">Activez la case à cocher **Définir**.</span><span class="sxs-lookup"><span data-stu-id="51ad1-121">Select the **Set** check box.</span></span>
4. <span data-ttu-id="51ad1-122">Sélectionnez *Oui* dans le champ **Calcul**.</span><span class="sxs-lookup"><span data-stu-id="51ad1-122">Select *Yes* in the **Calculation** field.</span></span>
    * <span data-ttu-id="51ad1-123">Le fait de définir la propriété du champ **Calcul** sur *Oui* garantit que la ligne de nomenclature sera incluse dans les calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="51ad1-123">Setting the **Calculation** property to *Yes* ensures that the BOM line is included in cost calculations.</span></span>  
5. <span data-ttu-id="51ad1-124">Sélectionnez l’onglet **Paramétrage**.</span><span class="sxs-lookup"><span data-stu-id="51ad1-124">Select the **Setup** tab.</span></span>
6. <span data-ttu-id="51ad1-125">Activez la case à cocher **Définir**.</span><span class="sxs-lookup"><span data-stu-id="51ad1-125">Select the **Set** check box.</span></span>
7. <span data-ttu-id="51ad1-126">Entrez un nombre dans le champ **Quantité**.</span><span class="sxs-lookup"><span data-stu-id="51ad1-126">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="51ad1-127">Le champ de quantité détermine la quantité d’articles qui sera incluse dans la nomenclature.</span><span class="sxs-lookup"><span data-stu-id="51ad1-127">The quantity field determines how much of the item that will be included in the BOM.</span></span> <span data-ttu-id="51ad1-128">Cela peut être un candidat idéal pour une mise en correspondance d’attributs.</span><span class="sxs-lookup"><span data-stu-id="51ad1-128">This could be an obvious candidate for an attribute mapping.</span></span>  
8. <span data-ttu-id="51ad1-129">Cliquez sur l’onglet **Dimension**.</span><span class="sxs-lookup"><span data-stu-id="51ad1-129">Select the **Dimension** tab.</span></span>
    * <span data-ttu-id="51ad1-130">Vérifiez si des dimensions de produit sont actives ; elles doivent donc avoir une valeur ou un attribut affecté.</span><span class="sxs-lookup"><span data-stu-id="51ad1-130">Verify if any of the product dimensions are active,  and therefore must have a value or attribute assigned.</span></span>  
9. <span data-ttu-id="51ad1-131">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="51ad1-131">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]