---
title: Créer une cellule de travail sous-traitée de lean manufacturing
description: Pour modéliser le travail sous-traité pour lean manufacturing, vous devez créer une cellule de travail associée au fournisseur qui fournit le travail.
author: cvocph
manager: tfehr
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 236ce97fcf4ca76f07ae5f9308cf45240590b399
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5228537"
---
# <a name="create-a-subcontracted-work-cell-for-lean-manufacturing"></a><span data-ttu-id="beb40-103">Créer une cellule de travail sous-traitée de lean manufacturing</span><span class="sxs-lookup"><span data-stu-id="beb40-103">Create a subcontracted work cell for lean manufacturing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="beb40-104">Pour modéliser le travail sous-traité pour lean manufacturing, vous devez créer une cellule de travail associée au fournisseur qui fournit le travail.</span><span class="sxs-lookup"><span data-stu-id="beb40-104">To model subcontracted work for lean manufacturing, you must create a work cell that is associated with the vendor that provides the work.</span></span> <span data-ttu-id="beb40-105">Une cellule de travail sous-traitée est liée au fournisseur via l’association d’une ressource du type Fournisseur.</span><span class="sxs-lookup"><span data-stu-id="beb40-105">A subcontracted work cell is linked to the vendor through the association of a resource of the Vendor type.</span></span> <span data-ttu-id="beb40-106">Si vous lisez cet enregistrement dans la société fictive USMF, vous pouvez sélectionner l’ID compte fournisseur 1002 et le site 1.</span><span class="sxs-lookup"><span data-stu-id="beb40-106">If you play this recording in the USMF demo company, you can select vendor account ID 1002 and site 1.</span></span>


## <a name="create-a-vendor-resource"></a><span data-ttu-id="beb40-107">Créer un groupe de ressources</span><span class="sxs-lookup"><span data-stu-id="beb40-107">Create a vendor resource</span></span>
1. <span data-ttu-id="beb40-108">Allez dans Ressources.</span><span class="sxs-lookup"><span data-stu-id="beb40-108">Go to Resources.</span></span>
2. <span data-ttu-id="beb40-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="beb40-109">Click New.</span></span>
3. <span data-ttu-id="beb40-110">Tapez une valeur dans le champ Ressource.</span><span class="sxs-lookup"><span data-stu-id="beb40-110">In the Resource field, type a value.</span></span>
4. <span data-ttu-id="beb40-111">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="beb40-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="beb40-112">Dans le champ Type, sélectionnez « Fournisseur ».</span><span class="sxs-lookup"><span data-stu-id="beb40-112">In the Type field, select 'Vendor'.</span></span>
6. <span data-ttu-id="beb40-113">Dans le champ Fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="beb40-113">In the Vendor field, click the drop-down button to open the lookup.</span></span>

## <a name="create-the-resource-group"></a><span data-ttu-id="beb40-114">Créer le groupe de ressources</span><span class="sxs-lookup"><span data-stu-id="beb40-114">Create the resource group</span></span>
1. <span data-ttu-id="beb40-115">Allez dans Groupes de ressources.</span><span class="sxs-lookup"><span data-stu-id="beb40-115">Go to Resource groups.</span></span>
2. <span data-ttu-id="beb40-116">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="beb40-116">Click New.</span></span>
3. <span data-ttu-id="beb40-117">Tapez une valeur dans le champ Groupe de ressources.</span><span class="sxs-lookup"><span data-stu-id="beb40-117">In the Resource group field, type a value.</span></span>
4. <span data-ttu-id="beb40-118">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="beb40-118">In the Description field, type a value.</span></span>
5. <span data-ttu-id="beb40-119">Dans le champ Site, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="beb40-119">In the Site field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="beb40-120">Sélectionnez le site auquel la cellule de travail doit être affectée.</span><span class="sxs-lookup"><span data-stu-id="beb40-120">Select the site that the work cell should be allocated to.</span></span> <span data-ttu-id="beb40-121">En théorie, un site peut représenter un site unique exploité par un fournisseur.</span><span class="sxs-lookup"><span data-stu-id="beb40-121">In theory, a site can represent a single site that is operated by a vendor.</span></span> <span data-ttu-id="beb40-122">Toutefois, dans la plupart des cas, les ressources sous-traitées sont simplement affectées au site qui commande le travail sous-traité.</span><span class="sxs-lookup"><span data-stu-id="beb40-122">However, in most cases, subcontracted resources are just allocated to the site that orders the subcontracted work.</span></span> <span data-ttu-id="beb40-123">Notez que les entrepôts d’entrée et de sortie des cellules de travail sous-traitées doivent être sur le même site.</span><span class="sxs-lookup"><span data-stu-id="beb40-123">Note that the input and output warehouses of subcontracted work cells must be on the same site.</span></span>  
6. <span data-ttu-id="beb40-124">Tapez une valeur dans le champ Site.</span><span class="sxs-lookup"><span data-stu-id="beb40-124">In the Site field, type a value.</span></span>
7. <span data-ttu-id="beb40-125">@SysTaskRecorder:_RequestClose</span><span class="sxs-lookup"><span data-stu-id="beb40-125">@SysTaskRecorder:_RequestClose</span></span>
8. <span data-ttu-id="beb40-126">Activez ou désactivez la case à cocher Cellule de travail.</span><span class="sxs-lookup"><span data-stu-id="beb40-126">Select or clear the Work cell check box.</span></span>
9. <span data-ttu-id="beb40-127">Dans le champ Entrepôt d’entrée, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="beb40-127">In the Input warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="beb40-128">Sélectionnez l’entrepôt et l’emplacement utilisés pour stocker les matières pour la cellule de travail gérée par le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="beb40-128">Select the warehouse and location that are used to stage the material for the vendor-managed work cell.</span></span> <span data-ttu-id="beb40-129">Dans de nombreux cas, l’entrepôt et l’emplacement sont modélisés en utilisant un entrepôt distinct par fournisseur et un emplacement par cellule de travail.</span><span class="sxs-lookup"><span data-stu-id="beb40-129">In many cases, the warehouse and location are modeled by using a separate warehouse per vendor and one location per work cell.</span></span>  
10. <span data-ttu-id="beb40-130">Dans le champ Emplacement de l’entrée, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="beb40-130">In the Input location field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="beb40-131">Dans le champ Entrepôt de sortie, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="beb40-131">In the Output warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="beb40-132">Définissez l’entrepôt et l’emplacement où les matières sont validées lorsque les activités sous-traitées de la cellule de travail sont validées.</span><span class="sxs-lookup"><span data-stu-id="beb40-132">Define the warehouse and location where the material is posted when the subcontracted activities of the work cell are posted.</span></span> <span data-ttu-id="beb40-133">L’entrepôt et l’emplacement peuvent être sur le site du fournisseur si le fournisseur déclare les tâches de kanban.</span><span class="sxs-lookup"><span data-stu-id="beb40-133">The warehouse and location can be at the vendor site if the vendor reports the kanban jobs.</span></span> <span data-ttu-id="beb40-134">Sinon, l’entrepôt et l’emplacement peuvent être l’emplacement de réception associé à l’étape suivante du flux de production.</span><span class="sxs-lookup"><span data-stu-id="beb40-134">Alternatively, the warehouse and location can be the receiving location that is associated with the next step of the production flow.</span></span>  
12. <span data-ttu-id="beb40-135">Dans le champ Emplacement de sortie, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="beb40-135">In the Output location field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="beb40-136">Développez ou réduisez la section Calendriers.</span><span class="sxs-lookup"><span data-stu-id="beb40-136">Expand or collapse the Calendars section.</span></span>
14. <span data-ttu-id="beb40-137">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="beb40-137">Click Add.</span></span>
15. <span data-ttu-id="beb40-138">Dans le champ Calendrier, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="beb40-138">In the Calendar field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="beb40-139">Associez le calendrier du temps de travail de la cellule de travail au groupe de ressources.</span><span class="sxs-lookup"><span data-stu-id="beb40-139">Associate the working time calendar of the work cell with the resource group.</span></span> <span data-ttu-id="beb40-140">Pour les ressources critiques, il est recommandé de définir des calendriers spécifiques qui représentent les temps de travail exacts et les capacités associées de la cellule de travail ou du site du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="beb40-140">For critical resources, we recommend that you define specific calendars that represent the exact working times and related capacities of the work cell or vendor site.</span></span>  
16. <span data-ttu-id="beb40-141">Développez ou réduisez la section Ressources.</span><span class="sxs-lookup"><span data-stu-id="beb40-141">Expand or collapse the Resources section.</span></span>
17. <span data-ttu-id="beb40-142">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="beb40-142">Click Add.</span></span>
    * <span data-ttu-id="beb40-143">Un groupe de ressources sous-traitées doit avoir une ressource associée du type Fournisseur qui lie le groupe de ressources au compte fournisseur.</span><span class="sxs-lookup"><span data-stu-id="beb40-143">A subcontracted resource group must have an associated resource of the Vendor type that links the resource group to the vendor account.</span></span>  
18. <span data-ttu-id="beb40-144">Dans le champ Ressources, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="beb40-144">In the Resource field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="beb40-145">Sélectionnez ou entrez la ressource fournisseur que vous avez créée dans la sous-tâche précédente.</span><span class="sxs-lookup"><span data-stu-id="beb40-145">Select or enter the vendor resource that you created in the previous sub-task.</span></span>  
19. <span data-ttu-id="beb40-146">Développez ou réduisez la section Capacité de cellule de travail.</span><span class="sxs-lookup"><span data-stu-id="beb40-146">Expand or collapse the Work cell capacity section.</span></span>
20. <span data-ttu-id="beb40-147">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="beb40-147">Click Add.</span></span>
    * <span data-ttu-id="beb40-148">Une cellule de travail doit avoir une capacité définie.</span><span class="sxs-lookup"><span data-stu-id="beb40-148">A work cell must have a defined capacity.</span></span> <span data-ttu-id="beb40-149">Dans cet exemple, nous créons une capacité de production de 100 pièces par jour de travail standard.</span><span class="sxs-lookup"><span data-stu-id="beb40-149">In this example, we create a throughput capacity of 100 pieces per standard workday.</span></span>  
21. <span data-ttu-id="beb40-150">Dans le champ Modèle de flux de production, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="beb40-150">In the Production flow model field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="beb40-151">Dans le champ Période de capacité, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="beb40-151">In the Capacity period field, select an option.</span></span>
23. <span data-ttu-id="beb40-152">Dans le champ Quantité moyenne de débit, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="beb40-152">In the Average throughput quantity field, enter a number.</span></span>
24. <span data-ttu-id="beb40-153">Dans le champ Unité, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="beb40-153">In the Unit field, click the drop-down button to open the lookup.</span></span>
25. <span data-ttu-id="beb40-154">Résolvez les modifications de l’unité.</span><span class="sxs-lookup"><span data-stu-id="beb40-154">ResolveChanges the Unit.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]