---
title: "Objets de coût"
description: "Cet article fournit des informations sur les objets de coûts, et explique comment les coûts et les quantités sont accumulés. Un objet de coût est une entité pour laquelle des coûts et des quantités sont accumulés. Une entité d'objet de coûts peut être un produit ou des variantes de produit, telles que des variantes de style et de couleur."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19451
ms.assetid: ec776b98-813a-490d-848f-468452d98fac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 275855f2fb4d32df91449d7ebb9ad9ba2bd3f36b
ms.contentlocale: fr-fr
ms.lasthandoff: 08/07/2018

---

# <a name="cost-objects"></a><span data-ttu-id="b8987-105">Objets de coût</span><span class="sxs-lookup"><span data-stu-id="b8987-105">Cost objects</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b8987-106">Cet article fournit des informations sur les objets de coûts, et explique comment les coûts et les quantités sont accumulés.</span><span class="sxs-lookup"><span data-stu-id="b8987-106">This article provides information about costs objects, and explains how costs and quantities are accumulated.</span></span> <span data-ttu-id="b8987-107">Un objet de coût est une entité pour laquelle des coûts et des quantités sont accumulés.</span><span class="sxs-lookup"><span data-stu-id="b8987-107">A cost object is an entity that costs and quantities are accumulated for.</span></span> <span data-ttu-id="b8987-108">Une entité d'objet de coûts peut être un produit ou des variantes de produit, telles que des variantes de style et de couleur.</span><span class="sxs-lookup"><span data-stu-id="b8987-108">A cost object entity can be either a product or product variants, such as variants for style and color.</span></span>  

## <a name="cost-objects"></a><span data-ttu-id="b8987-109">Objets de coût</span><span class="sxs-lookup"><span data-stu-id="b8987-109">Cost objects</span></span>

<span data-ttu-id="b8987-110">La page **Objets de coût** répertorie tous les objets de coût qui sont enregistrés sur un produit.</span><span class="sxs-lookup"><span data-stu-id="b8987-110">The **Cost objects** page lists all cost objects that are registered on a product.</span></span> <span data-ttu-id="b8987-111">Les objets de coût sont définis par les données issues des sources suivantes :</span><span class="sxs-lookup"><span data-stu-id="b8987-111">The cost objects are defined by data from the following sources:</span></span>

-   <span data-ttu-id="b8987-112">Produit</span><span class="sxs-lookup"><span data-stu-id="b8987-112">Product</span></span>
-   <span data-ttu-id="b8987-113">Groupe de dimensions de produit</span><span class="sxs-lookup"><span data-stu-id="b8987-113">Product dimension group</span></span>
-   <span data-ttu-id="b8987-114">Groupe de dimension de stockage</span><span class="sxs-lookup"><span data-stu-id="b8987-114">Storage dimension group</span></span>
-   <span data-ttu-id="b8987-115">Groupe de dimension de suivi</span><span class="sxs-lookup"><span data-stu-id="b8987-115">Tracking dimension group</span></span>

<span data-ttu-id="b8987-116">**Remarque :** un objet de coût représente un élément de coût du type **Matières directes** uniquement.</span><span class="sxs-lookup"><span data-stu-id="b8987-116">**Note:** A cost object represents a cost element of the **Direct material** type only.</span></span> <span data-ttu-id="b8987-117">Un objet de coût et un objet de stock diffèrent en ce qu'un objet de coût est défini par les dimensions de stock sélectionnées pour le stock physique.</span><span class="sxs-lookup"><span data-stu-id="b8987-117">A cost object and an inventory object differ in the way that a cost object is defined by the inventory dimensions that are selected for financial inventory.</span></span> <span data-ttu-id="b8987-118">Par exemple, un article a la configuration suivante :</span><span class="sxs-lookup"><span data-stu-id="b8987-118">For example, an item has the following configuration:</span></span>

-   <span data-ttu-id="b8987-119">**Site :** Stock physique = oui, Stock financier = oui</span><span class="sxs-lookup"><span data-stu-id="b8987-119">**Site:** Physical inventory = Yes, Financial inventory = Yes</span></span>
-   <span data-ttu-id="b8987-120">**Entrepôt :** Stock physique = oui, Stock financier = non</span><span class="sxs-lookup"><span data-stu-id="b8987-120">**Warehouse:** Physical inventory = Yes, Financial inventory = No</span></span>
-   <span data-ttu-id="b8987-121">**N° de lot :** Stock physique = oui, Stock financier = non</span><span class="sxs-lookup"><span data-stu-id="b8987-121">**Batch No.:** Physical inventory = Yes, Financial inventory = No</span></span>

<span data-ttu-id="b8987-122">Le tableau suivant présente ce qui est un objet de coût et ce qui est un objet de stock.</span><span class="sxs-lookup"><span data-stu-id="b8987-122">The following table shows what is a cost object and what is an inventory object.</span></span>

| <span data-ttu-id="b8987-123">Type d'objet</span><span class="sxs-lookup"><span data-stu-id="b8987-123">Object type</span></span>      | <span data-ttu-id="b8987-124">Numéro d'article</span><span class="sxs-lookup"><span data-stu-id="b8987-124">Item number</span></span> | <span data-ttu-id="b8987-125">site ;</span><span class="sxs-lookup"><span data-stu-id="b8987-125">Site</span></span> | <span data-ttu-id="b8987-126">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="b8987-126">Warehouse</span></span> | <span data-ttu-id="b8987-127">N° de lot</span><span class="sxs-lookup"><span data-stu-id="b8987-127">Batch No.</span></span> |
|------------------|-------------|------|-----------|-----------|
| <span data-ttu-id="b8987-128">Objet de coût</span><span class="sxs-lookup"><span data-stu-id="b8987-128">Cost object</span></span>      | <span data-ttu-id="b8987-129">x</span><span class="sxs-lookup"><span data-stu-id="b8987-129">x</span></span>           | <span data-ttu-id="b8987-130">x</span><span class="sxs-lookup"><span data-stu-id="b8987-130">x</span></span>    |           |           |
| <span data-ttu-id="b8987-131">Objet de stock</span><span class="sxs-lookup"><span data-stu-id="b8987-131">Inventory object</span></span> | <span data-ttu-id="b8987-132">x</span><span class="sxs-lookup"><span data-stu-id="b8987-132">x</span></span>           | <span data-ttu-id="b8987-133">x</span><span class="sxs-lookup"><span data-stu-id="b8987-133">x</span></span>    |  <span data-ttu-id="b8987-134">x</span><span class="sxs-lookup"><span data-stu-id="b8987-134">x</span></span>        | <span data-ttu-id="b8987-135">x</span><span class="sxs-lookup"><span data-stu-id="b8987-135">x</span></span>         |

## <a name="accumulation-of-costs-and-quantities"></a><span data-ttu-id="b8987-136">Cumul des coûts et des quantités</span><span class="sxs-lookup"><span data-stu-id="b8987-136">Accumulation of costs and quantities</span></span>
-   <span data-ttu-id="b8987-137">La valeur dans le champ **Valeur** est une somme des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="b8987-137">The value in the **Value** fieldis a sum of the following values:</span></span>
    -   <span data-ttu-id="b8987-138">Montant du coût physique</span><span class="sxs-lookup"><span data-stu-id="b8987-138">Physical cost amount</span></span>
    -   <span data-ttu-id="b8987-139">Montant du coût financier</span><span class="sxs-lookup"><span data-stu-id="b8987-139">Financial cost amount</span></span>
    -   <span data-ttu-id="b8987-140">Ajustements</span><span class="sxs-lookup"><span data-stu-id="b8987-140">Adjustments</span></span>
-   <span data-ttu-id="b8987-141">La valeur dans le champ **Quantité** est une somme des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="b8987-141">The value in the **Quantity** field is a sum of the following values:</span></span>
    -   <span data-ttu-id="b8987-142">Reçue</span><span class="sxs-lookup"><span data-stu-id="b8987-142">Received</span></span>
    -   <span data-ttu-id="b8987-143">Déduit</span><span class="sxs-lookup"><span data-stu-id="b8987-143">Deducted</span></span>
    -   <span data-ttu-id="b8987-144">Quantité validée</span><span class="sxs-lookup"><span data-stu-id="b8987-144">Posted quantity</span></span>
-   <span data-ttu-id="b8987-145">Le champ **Coût unitaire moyen** est un champ calculé.</span><span class="sxs-lookup"><span data-stu-id="b8987-145">The **Average unit cost** field is a calculated field.</span></span> <span data-ttu-id="b8987-146">La valeur est calculée en divisant la valeur **Valeur** par la valeur **Quantité**.</span><span class="sxs-lookup"><span data-stu-id="b8987-146">The value is calculated by dividing the **Value** value by the **Quantity** value.</span></span>

<span data-ttu-id="b8987-147">**Remarque :** Le paramètre **Inclure la valeur physique** n'a aucun effet sur les calculs précédents.</span><span class="sxs-lookup"><span data-stu-id="b8987-147">**Note:** The **Include physical value **parameter has no effect on the preceding calculations.</span></span>

<a name="additional-resources"></a><span data-ttu-id="b8987-148">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b8987-148">Additional resources</span></span>
--------

[<span data-ttu-id="b8987-149">Groupe de dimensions de produit</span><span class="sxs-lookup"><span data-stu-id="b8987-149">Product dimension group</span></span>](https://technet.microsoft.com/en-us/library/aa499382.aspx)

[<span data-ttu-id="b8987-150">Groupe de dimension de stockage</span><span class="sxs-lookup"><span data-stu-id="b8987-150">Storage dimension group</span></span>](https://technet.microsoft.com/en-us/library/hh209317.aspx)

[<span data-ttu-id="b8987-151">Groupe de dimensions de suivi</span><span class="sxs-lookup"><span data-stu-id="b8987-151">Tracking dimension group</span></span>](https://technet.microsoft.com/en-us/library/hh209465.aspx)

[<span data-ttu-id="b8987-152">Nouveautés ou changements</span><span class="sxs-lookup"><span data-stu-id="b8987-152">What's new or changed</span></span>](../../fin-and-ops/get-started/whats-new-changed.md)

[<span data-ttu-id="b8987-153">Écritures de coût</span><span class="sxs-lookup"><span data-stu-id="b8987-153">Cost entries</span></span>](cost-entries.md)




