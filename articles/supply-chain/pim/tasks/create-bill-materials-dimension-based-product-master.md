---
title: Créer une nomenclature pour un produit générique fondé sur les dimensions
description: Pour cette procédure, vous devez avoir déjà suivi les 4 premiers guides de cette séquence de huit enregistrements.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventItemIdLookupSimple, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13053dd87242963586678b46c64493feb3383c4c
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920703"
---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a><span data-ttu-id="2d91c-103">Créer une nomenclature pour un produit générique fondé sur les dimensions</span><span class="sxs-lookup"><span data-stu-id="2d91c-103">Create a bill of materials for a dimension-based product master</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2d91c-104">Pour cette procédure, vous devez avoir déjà suivi les 4 premiers guides de cette séquence de huit enregistrements.</span><span class="sxs-lookup"><span data-stu-id="2d91c-104">For this procedure you should have completed the previous 4 guides in this sequence of eight recordings.</span></span> <span data-ttu-id="2d91c-105">Les 4 premiers enregistrements paramètrent les données requises pour exécuter cette procédure.</span><span class="sxs-lookup"><span data-stu-id="2d91c-105">The first 4 recordings set up data that is required to complete this procedure.</span></span> <span data-ttu-id="2d91c-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="2d91c-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="2d91c-107">Cette tâche est généralement gérée par le concepteur de produit.</span><span class="sxs-lookup"><span data-stu-id="2d91c-107">This task is typically handled by the product designer.</span></span>

## <a name="select-the-product"></a><span data-ttu-id="2d91c-108">Sélectionner le produit</span><span class="sxs-lookup"><span data-stu-id="2d91c-108">Select the product</span></span>

1. <span data-ttu-id="2d91c-109">Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="2d91c-109">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="2d91c-110">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2d91c-110">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="2d91c-111">Recherchez le produit générique lancé avec la technologie de configuration basée sur les dimensions que vous avez créée dans le premier guide des tâches dans cette séquence.</span><span class="sxs-lookup"><span data-stu-id="2d91c-111">Find the released product master with dimension-based configuration technology that you created in the first task guide in this sequence.</span></span>  
1. <span data-ttu-id="2d91c-112">Dans le volet Actions, sélectionnez **Ingénieur**.</span><span class="sxs-lookup"><span data-stu-id="2d91c-112">On the Action Pane, select **Engineer**.</span></span>
1. <span data-ttu-id="2d91c-113">Sélectionnez **Versions de nomenclature**.</span><span class="sxs-lookup"><span data-stu-id="2d91c-113">Select **BOM versions**.</span></span>

## <a name="create-new-bom-and-bom-version"></a><span data-ttu-id="2d91c-114">Créer une nomenclature et une version de nomenclature</span><span class="sxs-lookup"><span data-stu-id="2d91c-114">Create new BOM and BOM version</span></span>

1. <span data-ttu-id="2d91c-115">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="2d91c-115">Select **New**.</span></span>
1. <span data-ttu-id="2d91c-116">Sélectionnez **Nomenclature et version de nomenclature**.</span><span class="sxs-lookup"><span data-stu-id="2d91c-116">Select **BOM and BOM version**.</span></span>
1. <span data-ttu-id="2d91c-117">Tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="2d91c-117">In the **Name** field, type a value.</span></span>
    * <span data-ttu-id="2d91c-118">Paramétrage d’un site</span><span class="sxs-lookup"><span data-stu-id="2d91c-118">Setting a site</span></span>  
    * <span data-ttu-id="2d91c-119">Dans cette procédure, nous ne définissons pas de site spécifique pour la nomenclature.</span><span class="sxs-lookup"><span data-stu-id="2d91c-119">In this procedure we don't set a specific site for the BOM.</span></span>  
1. <span data-ttu-id="2d91c-120">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d91c-120">Select **OK**.</span></span>
1. <span data-ttu-id="2d91c-121">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="2d91c-121">Select **New**.</span></span>
    * <span data-ttu-id="2d91c-122">Dans cette procédure, nous ajouterons quatre lignes à la nomenclature.</span><span class="sxs-lookup"><span data-stu-id="2d91c-122">In this procedure we will add four lines to the BOM.</span></span> <span data-ttu-id="2d91c-123">Deux lignes représentent les options de câble et deux lignes représentent les options de meuble.</span><span class="sxs-lookup"><span data-stu-id="2d91c-123">Two lines represent cable options and two lines represent cabinet options.</span></span>  
1. <span data-ttu-id="2d91c-124">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2d91c-124">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="2d91c-125">Entrez ou sélectionnez une valeur dans le champ **Numéro d’article**.</span><span class="sxs-lookup"><span data-stu-id="2d91c-125">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="2d91c-126">Sélectionnez le numéro d’article A0001, câbles HDMI 6’.</span><span class="sxs-lookup"><span data-stu-id="2d91c-126">Select item number A0001, HDMI 6' Cables.</span></span>  
1. <span data-ttu-id="2d91c-127">Saisissez ou sélectionnez une valeur dans le champ **Groupe de configurations**.</span><span class="sxs-lookup"><span data-stu-id="2d91c-127">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="2d91c-128">Sélectionnez le groupe de configuration de câble créé dans le guide 4 de cette séquence.</span><span class="sxs-lookup"><span data-stu-id="2d91c-128">Select the cable configuration group created in guide 4 in this sequence.</span></span>  
1. <span data-ttu-id="2d91c-129">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="2d91c-129">Select **New**.</span></span>
    * <span data-ttu-id="2d91c-130">Sélectionnez le numéro d’article A0002, câbles HDMI 12’.</span><span class="sxs-lookup"><span data-stu-id="2d91c-130">Select item number A0002, HDMI 12' Cables.</span></span>  
1. <span data-ttu-id="2d91c-131">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2d91c-131">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="2d91c-132">Entrez ou sélectionnez une valeur dans le champ **Numéro d’article**.</span><span class="sxs-lookup"><span data-stu-id="2d91c-132">In the **Item number** field, enter or select a value.</span></span>
1. <span data-ttu-id="2d91c-133">Saisissez ou sélectionnez une valeur dans le champ **Groupe de configurations**.</span><span class="sxs-lookup"><span data-stu-id="2d91c-133">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="2d91c-134">Sélectionnez à nouveau le groupe de configuration de câble.</span><span class="sxs-lookup"><span data-stu-id="2d91c-134">Select the cable configuration group again.</span></span>  
1. <span data-ttu-id="2d91c-135">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="2d91c-135">Select **New**.</span></span>
1. <span data-ttu-id="2d91c-136">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2d91c-136">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="2d91c-137">Entrez ou sélectionnez une valeur dans le champ **Numéro d’article**.</span><span class="sxs-lookup"><span data-stu-id="2d91c-137">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="2d91c-138">Sélectionnez le numéro d’article Meuble D0002.</span><span class="sxs-lookup"><span data-stu-id="2d91c-138">Select item number D0002 Cabinet.</span></span>  
1. <span data-ttu-id="2d91c-139">Saisissez ou sélectionnez une valeur dans le champ **Groupe de configurations**.</span><span class="sxs-lookup"><span data-stu-id="2d91c-139">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="2d91c-140">Sélectionnez le groupe de configurations Meuble pour cette ligne de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="2d91c-140">Select the cabinet configuration group for this BOM line.</span></span>  
1. <span data-ttu-id="2d91c-141">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="2d91c-141">Select **New**.</span></span>
1. <span data-ttu-id="2d91c-142">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2d91c-142">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="2d91c-143">Entrez ou sélectionnez une valeur dans le champ **Numéro d’article**.</span><span class="sxs-lookup"><span data-stu-id="2d91c-143">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="2d91c-144">Sélectionnez le numéro d’article Meuble standard M0007 comme dernière ligne de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="2d91c-144">Select Item number M0007 StandardCabinet as the last BOM line.</span></span>  
1. <span data-ttu-id="2d91c-145">Saisissez ou sélectionnez une valeur dans le champ **Groupe de configurations**.</span><span class="sxs-lookup"><span data-stu-id="2d91c-145">In the **Configuration group** field, enter or select a value.</span></span>
    * <span data-ttu-id="2d91c-146">Sélectionnez le groupe de configurations Meuble pour la dernière ligne de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="2d91c-146">Select the Cabinet configuration group for the last BOM line.</span></span>  

## <a name="approve-and-activate"></a><span data-ttu-id="2d91c-147">Approuver et activer</span><span class="sxs-lookup"><span data-stu-id="2d91c-147">Approve and activate</span></span>

1. <span data-ttu-id="2d91c-148">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="2d91c-148">Close the page.</span></span>
1. <span data-ttu-id="2d91c-149">Sélectionnez **Approuver**.</span><span class="sxs-lookup"><span data-stu-id="2d91c-149">Select **Approve**.</span></span>
1. <span data-ttu-id="2d91c-150">Dans le champ **Approuvé par**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2d91c-150">In the **Approved by** field, enter or select a value.</span></span>
1. <span data-ttu-id="2d91c-151">Sélectionnez *Oui* dans le champ **Voulez-vous également approuver les nomenclatures ?**.</span><span class="sxs-lookup"><span data-stu-id="2d91c-151">Select *Yes* in the **Do you also want to approve the bill of materials?** field.</span></span>
1. <span data-ttu-id="2d91c-152">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d91c-152">Select **OK**.</span></span>
1. <span data-ttu-id="2d91c-153">Sélectionnez **Activer**.</span><span class="sxs-lookup"><span data-stu-id="2d91c-153">Select **Activate**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]