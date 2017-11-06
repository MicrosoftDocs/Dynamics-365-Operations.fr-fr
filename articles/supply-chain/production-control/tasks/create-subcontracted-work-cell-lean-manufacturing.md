--- 
title: "Créer une cellule de travail sous-traitée de lean manufacturing"
description: "Pour modéliser le travail sous-traité pour lean manufacturing, vous devez créer une cellule de travail associée au fournisseur qui fournit le travail."
author: cvocph
manager: AnnBe
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fc8dc0bc29c6bdb662c46808491abf5395f0be5d
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-a-subcontracted-work-cell-for-lean-manufacturing"></a><span data-ttu-id="e99da-103">Créer une cellule de travail sous-traitée de lean manufacturing</span><span class="sxs-lookup"><span data-stu-id="e99da-103">Create a subcontracted work cell for lean manufacturing</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e99da-104">Pour modéliser le travail sous-traité pour lean manufacturing, vous devez créer une cellule de travail associée au fournisseur qui fournit le travail.</span><span class="sxs-lookup"><span data-stu-id="e99da-104">To model subcontracted work for lean manufacturing, you must create a work cell that is associated with the vendor that provides the work.</span></span> <span data-ttu-id="e99da-105">Une cellule de travail sous-traitée est liée au fournisseur via l'association d'une ressource du type Fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e99da-105">A subcontracted work cell is linked to the vendor through the association of a resource of the Vendor type.</span></span> <span data-ttu-id="e99da-106">Si vous lisez cet enregistrement dans la société fictive USMF, vous pouvez sélectionner l'ID compte fournisseur 1002 et le site 1.</span><span class="sxs-lookup"><span data-stu-id="e99da-106">If you play this recording in the USMF demo company, you can select vendor account ID 1002 and site 1.</span></span>


## <a name="create-a-vendor-resource"></a><span data-ttu-id="e99da-107">Créer un groupe de ressources</span><span class="sxs-lookup"><span data-stu-id="e99da-107">Create a vendor resource</span></span>
1. <span data-ttu-id="e99da-108">Allez dans Ressources.</span><span class="sxs-lookup"><span data-stu-id="e99da-108">Go to Resources.</span></span>
2. <span data-ttu-id="e99da-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e99da-109">Click New.</span></span>
3. <span data-ttu-id="e99da-110">Tapez une valeur dans le champ Ressource.</span><span class="sxs-lookup"><span data-stu-id="e99da-110">In the Resource field, type a value.</span></span>
4. <span data-ttu-id="e99da-111">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e99da-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="e99da-112">Dans le champ Type, sélectionnez « Fournisseur ».</span><span class="sxs-lookup"><span data-stu-id="e99da-112">In the Type field, select 'Vendor'.</span></span>
6. <span data-ttu-id="e99da-113">Dans le champ Fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e99da-113">In the Vendor field, click the drop-down button to open the lookup.</span></span>

## <a name="create-the-resource-group"></a><span data-ttu-id="e99da-114">Créer le groupe de ressources</span><span class="sxs-lookup"><span data-stu-id="e99da-114">Create the resource group</span></span>
1. <span data-ttu-id="e99da-115">Allez dans Groupes de ressources.</span><span class="sxs-lookup"><span data-stu-id="e99da-115">Go to Resource groups.</span></span>
2. <span data-ttu-id="e99da-116">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e99da-116">Click New.</span></span>
3. <span data-ttu-id="e99da-117">Tapez une valeur dans le champ Groupe de ressources.</span><span class="sxs-lookup"><span data-stu-id="e99da-117">In the Resource group field, type a value.</span></span>
4. <span data-ttu-id="e99da-118">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e99da-118">In the Description field, type a value.</span></span>
5. <span data-ttu-id="e99da-119">Dans le champ Site, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e99da-119">In the Site field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="e99da-120">Sélectionnez le site auquel la cellule de travail doit être affectée.</span><span class="sxs-lookup"><span data-stu-id="e99da-120">Select the site that the work cell should be allocated to.</span></span> <span data-ttu-id="e99da-121">En théorie, un site peut représenter un site unique exploité par un fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e99da-121">In theory, a site can represent a single site that is operated by a vendor.</span></span> <span data-ttu-id="e99da-122">Toutefois, dans la plupart des cas, les ressources sous-traitées sont simplement affectées au site qui commande le travail sous-traité.</span><span class="sxs-lookup"><span data-stu-id="e99da-122">However, in most cases, subcontracted resources are just allocated to the site that orders the subcontracted work.</span></span> <span data-ttu-id="e99da-123">Notez que les entrepôts d'entrée et de sortie des cellules de travail sous-traitées doivent être sur le même site.</span><span class="sxs-lookup"><span data-stu-id="e99da-123">Note that the input and output warehouses of subcontracted work cells must be on the same site.</span></span>  
6. <span data-ttu-id="e99da-124">Tapez une valeur dans le champ Site.</span><span class="sxs-lookup"><span data-stu-id="e99da-124">In the Site field, type a value.</span></span>
7. @SysTaskRecorder:_RequestClose
8. <span data-ttu-id="e99da-125">Activez ou désactivez la case à cocher Cellule de travail.</span><span class="sxs-lookup"><span data-stu-id="e99da-125">Select or clear the Work cell check box.</span></span>
9. <span data-ttu-id="e99da-126">Dans le champ Entrepôt d'entrée, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e99da-126">In the Input warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="e99da-127">Sélectionnez l'entrepôt et l'emplacement utilisés pour stocker les matières pour la cellule de travail gérée par le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e99da-127">Select the warehouse and location that are used to stage the material for the vendor-managed work cell.</span></span> <span data-ttu-id="e99da-128">Dans de nombreux cas, l'entrepôt et l'emplacement sont modélisés en utilisant un entrepôt distinct par fournisseur et un emplacement par cellule de travail.</span><span class="sxs-lookup"><span data-stu-id="e99da-128">In many cases, the warehouse and location are modeled by using a separate warehouse per vendor and one location per work cell.</span></span>  
10. <span data-ttu-id="e99da-129">Dans le champ Emplacement de l'entrée, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e99da-129">In the Input location field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="e99da-130">Dans le champ Entrepôt de sortie, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e99da-130">In the Output warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="e99da-131">Définissez l'entrepôt et l'emplacement où les matières sont validées lorsque les activités sous-traitées de la cellule de travail sont validées.</span><span class="sxs-lookup"><span data-stu-id="e99da-131">Define the warehouse and location where the material is posted when the subcontracted activities of the work cell are posted.</span></span> <span data-ttu-id="e99da-132">L'entrepôt et l'emplacement peuvent être sur le site du fournisseur si le fournisseur déclare les tâches de kanban.</span><span class="sxs-lookup"><span data-stu-id="e99da-132">The warehouse and location can be at the vendor site if the vendor reports the kanban jobs.</span></span> <span data-ttu-id="e99da-133">Sinon, l'entrepôt et l'emplacement peuvent être l'emplacement de réception associé à l'étape suivante du flux de production.</span><span class="sxs-lookup"><span data-stu-id="e99da-133">Alternatively, the warehouse and location can be the receiving location that is associated with the next step of the production flow.</span></span>  
12. <span data-ttu-id="e99da-134">Dans le champ Emplacement de sortie, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e99da-134">In the Output location field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="e99da-135">Développez ou réduisez la section Calendriers.</span><span class="sxs-lookup"><span data-stu-id="e99da-135">Expand or collapse the Calendars section.</span></span>
14. <span data-ttu-id="e99da-136">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e99da-136">Click Add.</span></span>
15. <span data-ttu-id="e99da-137">Dans le champ Calendrier, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e99da-137">In the Calendar field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="e99da-138">Associez le calendrier du temps de travail de la cellule de travail au groupe de ressources.</span><span class="sxs-lookup"><span data-stu-id="e99da-138">Associate the working time calendar of the work cell with the resource group.</span></span> <span data-ttu-id="e99da-139">Pour les ressources critiques, il est recommandé de définir des calendriers spécifiques qui représentent les temps de travail exacts et les capacités associées de la cellule de travail ou du site du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e99da-139">For critical resources, we recommend that you define specific calendars that represent the exact working times and related capacities of the work cell or vendor site.</span></span>  
16. <span data-ttu-id="e99da-140">Développez ou réduisez la section Ressources.</span><span class="sxs-lookup"><span data-stu-id="e99da-140">Expand or collapse the Resources section.</span></span>
17. <span data-ttu-id="e99da-141">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e99da-141">Click Add.</span></span>
    * <span data-ttu-id="e99da-142">Un groupe de ressources sous-traitées doit avoir une ressource associée du type Fournisseur qui lie le groupe de ressources au compte fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e99da-142">A subcontracted resource group must have an associated resource of the Vendor type that links the resource group to the vendor account.</span></span>  
18. <span data-ttu-id="e99da-143">Dans le champ Ressources, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e99da-143">In the Resource field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="e99da-144">Sélectionnez ou entrez la ressource fournisseur que vous avez créée dans la sous-tâche précédente.</span><span class="sxs-lookup"><span data-stu-id="e99da-144">Select or enter the vendor resource that you created in the previous sub-task.</span></span>  
19. <span data-ttu-id="e99da-145">Développez ou réduisez la section Capacité de cellule de travail.</span><span class="sxs-lookup"><span data-stu-id="e99da-145">Expand or collapse the Work cell capacity section.</span></span>
20. <span data-ttu-id="e99da-146">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="e99da-146">Click Add.</span></span>
    * <span data-ttu-id="e99da-147">Une cellule de travail doit avoir une capacité définie.</span><span class="sxs-lookup"><span data-stu-id="e99da-147">A work cell must have a defined capacity.</span></span> <span data-ttu-id="e99da-148">Dans cet exemple, nous créons une capacité de production de 100 pièces par jour de travail standard.</span><span class="sxs-lookup"><span data-stu-id="e99da-148">In this example, we create a throughput capacity of 100 pieces per standard workday.</span></span>  
21. <span data-ttu-id="e99da-149">Dans le champ Modèle de flux de production, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e99da-149">In the Production flow model field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="e99da-150">Dans le champ Période de capacité, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="e99da-150">In the Capacity period field, select an option.</span></span>
23. <span data-ttu-id="e99da-151">Dans le champ Quantité moyenne de débit, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="e99da-151">In the Average throughput quantity field, enter a number.</span></span>
24. <span data-ttu-id="e99da-152">Dans le champ Unité, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="e99da-152">In the Unit field, click the drop-down button to open the lookup.</span></span>
25. <span data-ttu-id="e99da-153">Résolvez les modifications de l'unité.</span><span class="sxs-lookup"><span data-stu-id="e99da-153">ResolveChanges the Unit.</span></span>


