---
title: "Objets de coût"
description: "Cet article fournit des informations sur les objets de coûts, et explique comment les coûts et les quantités sont accumulés. Un objet de coût est une entité pour laquelle des coûts et des quantités sont accumulés. Une entité d'objet de coûts peut être un produit ou des variantes de produit, telles que des variantes de style et de couleur."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19451
ms.assetid: ec776b98-813a-490d-848f-468452d98fac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: d43ea6c0d80a1602f298bbbedb88dd8f7decca4e
ms.contentlocale: fr-fr
ms.lasthandoff: 07/18/2017

---

# <a name="cost-objects"></a><span data-ttu-id="4a4a9-105">Objets de coût</span><span class="sxs-lookup"><span data-stu-id="4a4a9-105">Cost objects</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="4a4a9-106">Cet article fournit des informations sur les objets de coûts, et explique comment les coûts et les quantités sont accumulés.</span><span class="sxs-lookup"><span data-stu-id="4a4a9-106">This article provides information about costs objects, and explains how costs and quantities are accumulated.</span></span> <span data-ttu-id="4a4a9-107">Un objet de coût est une entité pour laquelle des coûts et des quantités sont accumulés.</span><span class="sxs-lookup"><span data-stu-id="4a4a9-107">A cost object is an entity that costs and quantities are accumulated for.</span></span> <span data-ttu-id="4a4a9-108">Une entité d'objet de coûts peut être un produit ou des variantes de produit, telles que des variantes de style et de couleur.</span><span class="sxs-lookup"><span data-stu-id="4a4a9-108">A cost object entity can be either a product or product variants, such as variants for style and color.</span></span>  

<a name="cost-objects"></a><span data-ttu-id="4a4a9-109">Objets de coût</span><span class="sxs-lookup"><span data-stu-id="4a4a9-109">Cost objects</span></span>
------------

<span data-ttu-id="4a4a9-110">La page **Objets de coût** répertorie tous les objets de coût qui sont enregistrés sur un produit.</span><span class="sxs-lookup"><span data-stu-id="4a4a9-110">The **Cost objects** page lists all cost objects that are registered on a product.</span></span> <span data-ttu-id="4a4a9-111">Les objets de coût sont définis par les données issues des sources suivantes :</span><span class="sxs-lookup"><span data-stu-id="4a4a9-111">The cost objects are defined by data from the following sources:</span></span>

-   <span data-ttu-id="4a4a9-112">Produit</span><span class="sxs-lookup"><span data-stu-id="4a4a9-112">Product</span></span>
-   <span data-ttu-id="4a4a9-113">Groupe de dimensions de produit</span><span class="sxs-lookup"><span data-stu-id="4a4a9-113">Product dimension group</span></span>
-   <span data-ttu-id="4a4a9-114">Groupe de dimension de stockage</span><span class="sxs-lookup"><span data-stu-id="4a4a9-114">Storage dimension group</span></span>
-   <span data-ttu-id="4a4a9-115">Groupe de dimension de suivi</span><span class="sxs-lookup"><span data-stu-id="4a4a9-115">Tracking dimension group</span></span>

<span data-ttu-id="4a4a9-116">**Remarque :** un objet de coût représente un élément de coût du type **Matières directes** uniquement.</span><span class="sxs-lookup"><span data-stu-id="4a4a9-116">**Note:** A cost object represents a cost element of the **Direct material** type only.</span></span> <span data-ttu-id="4a4a9-117">Un objet de coût et un objet de stock diffèrent en ce qu'un objet de coût est défini par les dimensions de stock sélectionnées pour le stock physique.</span><span class="sxs-lookup"><span data-stu-id="4a4a9-117">A cost object and an inventory object differ in the way that a cost object is defined by the inventory dimensions that are selected for financial inventory.</span></span> <span data-ttu-id="4a4a9-118">Par exemple, un article a la configuration suivante :</span><span class="sxs-lookup"><span data-stu-id="4a4a9-118">For example, an item has the following configuration:</span></span>

-   <span data-ttu-id="4a4a9-119">**Site :** Stock physique = oui, Stock financier = oui</span><span class="sxs-lookup"><span data-stu-id="4a4a9-119">**Site:** Physical inventory = Yes, Financial inventory = Yes</span></span>
-   <span data-ttu-id="4a4a9-120">**Entrepôt :** Stock physique = oui, Stock financier = non</span><span class="sxs-lookup"><span data-stu-id="4a4a9-120">**Warehouse:** Physical inventory = Yes, Financial inventory = No</span></span>
-   <span data-ttu-id="4a4a9-121">**N° de lot :** Stock physique = oui, Stock financier = non</span><span class="sxs-lookup"><span data-stu-id="4a4a9-121">**Batch No.:** Physical inventory = Yes, Financial inventory = No</span></span>

<span data-ttu-id="4a4a9-122">Le tableau suivant présente ce qui est un objet de coût et ce qui est un objet de stock.</span><span class="sxs-lookup"><span data-stu-id="4a4a9-122">The following table shows what is a cost object and what is an inventory object.</span></span>

| <span data-ttu-id="4a4a9-123">Type d'objet</span><span class="sxs-lookup"><span data-stu-id="4a4a9-123">Object type</span></span>      | <span data-ttu-id="4a4a9-124">Numéro d'article</span><span class="sxs-lookup"><span data-stu-id="4a4a9-124">Item number</span></span> | <span data-ttu-id="4a4a9-125">site ;</span><span class="sxs-lookup"><span data-stu-id="4a4a9-125">Site</span></span> | <span data-ttu-id="4a4a9-126">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="4a4a9-126">Warehouse</span></span> | <span data-ttu-id="4a4a9-127">N° de lot</span><span class="sxs-lookup"><span data-stu-id="4a4a9-127">Batch No.</span></span> |
|------------------|-------------|------|-----------|-----------|
| <span data-ttu-id="4a4a9-128">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="4a4a9-128">Cost object</span></span>      | <span data-ttu-id="4a4a9-129">x</span><span class="sxs-lookup"><span data-stu-id="4a4a9-129">x</span></span>           | <span data-ttu-id="4a4a9-130">x</span><span class="sxs-lookup"><span data-stu-id="4a4a9-130">x</span></span>    |           |           |
| <span data-ttu-id="4a4a9-131">Objet de stock</span><span class="sxs-lookup"><span data-stu-id="4a4a9-131">Inventory object</span></span> | <span data-ttu-id="4a4a9-132">x</span><span class="sxs-lookup"><span data-stu-id="4a4a9-132">x</span></span>           | <span data-ttu-id="4a4a9-133">x</span><span class="sxs-lookup"><span data-stu-id="4a4a9-133">x</span></span>    |  <span data-ttu-id="4a4a9-134">x</span><span class="sxs-lookup"><span data-stu-id="4a4a9-134">x</span></span>        | <span data-ttu-id="4a4a9-135">x</span><span class="sxs-lookup"><span data-stu-id="4a4a9-135">x</span></span>         |

## <a name="accumulation-of-costs-and-quantities"></a><span data-ttu-id="4a4a9-136">Cumul des coûts et des quantités</span><span class="sxs-lookup"><span data-stu-id="4a4a9-136">Accumulation of costs and quantities</span></span>
-   <span data-ttu-id="4a4a9-137">La valeur dans le champ **Valeur** est une somme des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="4a4a9-137">The value in the **Value** fieldis a sum of the following values:</span></span>
    -   <span data-ttu-id="4a4a9-138">Montant du coût physique</span><span class="sxs-lookup"><span data-stu-id="4a4a9-138">Physical cost amount</span></span>
    -   <span data-ttu-id="4a4a9-139">Montant du coût financier</span><span class="sxs-lookup"><span data-stu-id="4a4a9-139">Financial cost amount</span></span>
    -   <span data-ttu-id="4a4a9-140">Ajustements</span><span class="sxs-lookup"><span data-stu-id="4a4a9-140">Adjustments</span></span>
-   <span data-ttu-id="4a4a9-141">La valeur dans le champ **Quantité** est une somme des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="4a4a9-141">The value in the **Quantity** field is a sum of the following values:</span></span>
    -   <span data-ttu-id="4a4a9-142">Reçue</span><span class="sxs-lookup"><span data-stu-id="4a4a9-142">Received</span></span>
    -   <span data-ttu-id="4a4a9-143">Déduit</span><span class="sxs-lookup"><span data-stu-id="4a4a9-143">Deducted</span></span>
    -   <span data-ttu-id="4a4a9-144">Quantité validée</span><span class="sxs-lookup"><span data-stu-id="4a4a9-144">Posted quantity</span></span>
-   <span data-ttu-id="4a4a9-145">Le champ **Coût unitaire moyen** est un champ calculé.</span><span class="sxs-lookup"><span data-stu-id="4a4a9-145">The **Average unit cost** field is a calculated field.</span></span> <span data-ttu-id="4a4a9-146">La valeur est calculée en divisant la valeur **Valeur** par la valeur **Quantité**.</span><span class="sxs-lookup"><span data-stu-id="4a4a9-146">The value is calculated by dividing the **Value** value by the **Quantity** value.</span></span>

<span data-ttu-id="4a4a9-147">**Remarque :** Le paramètre **Inclure la valeur physique** n'a aucun effet sur les calculs précédents.</span><span class="sxs-lookup"><span data-stu-id="4a4a9-147">**Note:** The **Include physical value **parameter has no effect on the preceding calculations.</span></span>

<a name="see-also"></a><span data-ttu-id="4a4a9-148">Voir également :</span><span class="sxs-lookup"><span data-stu-id="4a4a9-148">See also</span></span>
--------

[<span data-ttu-id="4a4a9-149">Groupe de dimensions de produit</span><span class="sxs-lookup"><span data-stu-id="4a4a9-149">Product dimension group</span></span>](https://technet.microsoft.com/en-us/library/aa499382.aspx)

[<span data-ttu-id="4a4a9-150">Groupe de dimension de stockage</span><span class="sxs-lookup"><span data-stu-id="4a4a9-150">Storage dimension group</span></span>](https://technet.microsoft.com/en-us/library/hh209317.aspx)

[<span data-ttu-id="4a4a9-151">Groupe de dimensions de suivi</span><span class="sxs-lookup"><span data-stu-id="4a4a9-151">Tracking dimension group</span></span>](https://technet.microsoft.com/en-us/library/hh209465.aspx)

[<span data-ttu-id="4a4a9-152">Nouveautés ou changements</span><span class="sxs-lookup"><span data-stu-id="4a4a9-152">What's new or changed</span></span>](/dynamics365/unified-operations/dev-itpro/get-started/whats-new-changed)

[<span data-ttu-id="4a4a9-153">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="4a4a9-153">Cost entries</span></span>](cost-entries.md)




