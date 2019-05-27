---
title: Créer une nomenclature pour un produit générique fondé sur les dimensions
description: Pour cette procédure, vous devez avoir déjà suivi les 4 premiers guides de cette séquence de huit enregistrements.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventItemIdLookupSimple, HcmWorkerLookUp
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 19578f78c11bf0537708e8d516d478f00b13fa95
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568579"
---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a><span data-ttu-id="7f169-103">Créer une nomenclature pour un produit générique fondé sur les dimensions</span><span class="sxs-lookup"><span data-stu-id="7f169-103">Create a bill of materials for a dimension-based product master</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7f169-104">Pour cette procédure, vous devez avoir déjà suivi les 4 premiers guides de cette séquence de huit enregistrements.</span><span class="sxs-lookup"><span data-stu-id="7f169-104">For this procedure you should have completed the previous 4 guides in this sequence of eight recordings.</span></span> <span data-ttu-id="7f169-105">Les 4 premiers enregistrements paramètrent les données requises pour exécuter cette procédure.</span><span class="sxs-lookup"><span data-stu-id="7f169-105">The first 4 recordings set up data that is required to complete this procedure.</span></span> <span data-ttu-id="7f169-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="7f169-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="7f169-107">Cette tâche est généralement gérée par le concepteur de produit.</span><span class="sxs-lookup"><span data-stu-id="7f169-107">This task is typically handled by the product designer.</span></span>


## <a name="select-the-product"></a><span data-ttu-id="7f169-108">Sélectionner le produit</span><span class="sxs-lookup"><span data-stu-id="7f169-108">Select the product</span></span>
1. <span data-ttu-id="7f169-109">Cliquez sur Gestion des produits lancés.</span><span class="sxs-lookup"><span data-stu-id="7f169-109">Click Released product maintenance.</span></span>
2. <span data-ttu-id="7f169-110">Cliquez sur Produits lancés.</span><span class="sxs-lookup"><span data-stu-id="7f169-110">Click Released products.</span></span>
3. <span data-ttu-id="7f169-111">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7f169-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="7f169-112">Recherchez le produit générique lancé avec la technologie de configuration basée sur les dimensions que vous avez créée dans le premier guide des tâches dans cette séquence.</span><span class="sxs-lookup"><span data-stu-id="7f169-112">Find the released product master with dimension-based configuration technology that you created in the first task guide in this sequence.</span></span>  
4. <span data-ttu-id="7f169-113">Cliquez sur Ingénieur dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="7f169-113">On the Action Pane, click Engineer.</span></span>
5. <span data-ttu-id="7f169-114">Cliquez sur Versions de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="7f169-114">Click BOM versions.</span></span>

## <a name="create-new-bom-and-bom-version"></a><span data-ttu-id="7f169-115">Créer une nomenclature et une version de nomenclature</span><span class="sxs-lookup"><span data-stu-id="7f169-115">Create new BOM and BOM version</span></span>
1. <span data-ttu-id="7f169-116">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="7f169-116">Click New.</span></span>
2. <span data-ttu-id="7f169-117">Cliquez sur Nomenclature et version de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="7f169-117">Click BOM and BOM version.</span></span>
3. <span data-ttu-id="7f169-118">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="7f169-118">In the Name field, type a value.</span></span>
    * <span data-ttu-id="7f169-119">Paramétrage d'un site</span><span class="sxs-lookup"><span data-stu-id="7f169-119">Setting a site</span></span>  
    * <span data-ttu-id="7f169-120">Dans cette procédure, nous ne définissons pas de site spécifique pour la nomenclature.</span><span class="sxs-lookup"><span data-stu-id="7f169-120">In this procedure we don't set a specific site for the BOM.</span></span>  
4. <span data-ttu-id="7f169-121">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="7f169-121">Click OK.</span></span>
5. <span data-ttu-id="7f169-122">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="7f169-122">Click New.</span></span>
    * <span data-ttu-id="7f169-123">Dans cette procédure, nous ajouterons quatre lignes à la nomenclature.</span><span class="sxs-lookup"><span data-stu-id="7f169-123">In this procedure we will add four lines to the BOM.</span></span> <span data-ttu-id="7f169-124">Deux lignes représentent les options de câble et deux lignes représentent les options de meuble.</span><span class="sxs-lookup"><span data-stu-id="7f169-124">Two lines represent cable options and two lines represent cabinet options.</span></span>  
6. <span data-ttu-id="7f169-125">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7f169-125">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="7f169-126">Entrez ou sélectionnez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="7f169-126">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="7f169-127">Sélectionnez le numéro d'article A0001, câbles HDMI 6'.</span><span class="sxs-lookup"><span data-stu-id="7f169-127">Select item number A0001, HDMI 6' Cables.</span></span>  
8. <span data-ttu-id="7f169-128">Saisissez ou sélectionnez une valeur dans le champ Groupe de configurations.</span><span class="sxs-lookup"><span data-stu-id="7f169-128">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="7f169-129">Sélectionnez le groupe de configuration de câble créé dans le guide 4 de cette séquence.</span><span class="sxs-lookup"><span data-stu-id="7f169-129">Select the Cable configuration group created in guide 4 in this sequence.</span></span>  
9. <span data-ttu-id="7f169-130">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="7f169-130">Click New.</span></span>
    * <span data-ttu-id="7f169-131">Sélectionnez le numéro d'article A0002, câbles HDMI 12'.</span><span class="sxs-lookup"><span data-stu-id="7f169-131">Select item number A0002, HDMI 12' Cables.</span></span>  
10. <span data-ttu-id="7f169-132">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7f169-132">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="7f169-133">Entrez ou sélectionnez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="7f169-133">In the Item number field, enter or select a value.</span></span>
12. <span data-ttu-id="7f169-134">Saisissez ou sélectionnez une valeur dans le champ Groupe de configurations.</span><span class="sxs-lookup"><span data-stu-id="7f169-134">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="7f169-135">Sélectionnez à nouveau le groupe de configuration de câble.</span><span class="sxs-lookup"><span data-stu-id="7f169-135">Select the Cable configuration group again.</span></span>  
13. <span data-ttu-id="7f169-136">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="7f169-136">Click New.</span></span>
14. <span data-ttu-id="7f169-137">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7f169-137">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="7f169-138">Entrez ou sélectionnez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="7f169-138">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="7f169-139">Sélectionnez le numéro d'article Meuble D0002.</span><span class="sxs-lookup"><span data-stu-id="7f169-139">Select item number D0002 Cabinet.</span></span>  
16. <span data-ttu-id="7f169-140">Saisissez ou sélectionnez une valeur dans le champ Groupe de configurations.</span><span class="sxs-lookup"><span data-stu-id="7f169-140">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="7f169-141">Sélectionnez le groupe de configurations Meuble pour cette ligne de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="7f169-141">Select the Cabinet configuration group for this BOM line.</span></span>  
17. <span data-ttu-id="7f169-142">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="7f169-142">Click New.</span></span>
18. <span data-ttu-id="7f169-143">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7f169-143">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="7f169-144">Entrez ou sélectionnez une valeur dans le champ Numéro d'article.</span><span class="sxs-lookup"><span data-stu-id="7f169-144">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="7f169-145">Sélectionnez le numéro d'article Meuble standard M0007 comme dernière ligne de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="7f169-145">Select Item number M0007 StandardCabinet as the last BOM line.</span></span>  
20. <span data-ttu-id="7f169-146">Saisissez ou sélectionnez une valeur dans le champ Groupe de configurations.</span><span class="sxs-lookup"><span data-stu-id="7f169-146">In the Configuration group field, enter or select a value.</span></span>
    * <span data-ttu-id="7f169-147">Sélectionnez le groupe de configurations Meuble pour la dernière ligne de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="7f169-147">Select the Cabinet configuration group for the laste BOM line.</span></span>  

## <a name="approve-and-activate"></a><span data-ttu-id="7f169-148">Approuver et activer</span><span class="sxs-lookup"><span data-stu-id="7f169-148">Approve and activate</span></span>
1. <span data-ttu-id="7f169-149">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="7f169-149">Close the page.</span></span>
2. <span data-ttu-id="7f169-150">Cliquez sur Approuver.</span><span class="sxs-lookup"><span data-stu-id="7f169-150">Click Approve.</span></span>
3. <span data-ttu-id="7f169-151">Dans le champ Approuvé par, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="7f169-151">In the Approved by field, enter or select a value.</span></span>
4. <span data-ttu-id="7f169-152">Sélectionnez Oui dans le champ Voulez-vous également approuver les nomenclatures ? .</span><span class="sxs-lookup"><span data-stu-id="7f169-152">Select Yes in the Do you also want to approve the bill of materials? field.</span></span>
5. <span data-ttu-id="7f169-153">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="7f169-153">Click OK.</span></span>
6. <span data-ttu-id="7f169-154">Cliquez sur Activer.</span><span class="sxs-lookup"><span data-stu-id="7f169-154">Click Activate.</span></span>

