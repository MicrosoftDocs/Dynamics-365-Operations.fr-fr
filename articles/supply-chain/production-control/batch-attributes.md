---
title: Attributs de lot
description: "Cette rubrique fournit des informations sur les attributs de lot. Les attributs de lot sont des caractéristiques de matières premières et de produits finis qui constituent des lots de stock. La rubrique décrit également les manières d'affecter des attributs de lot et d'y effectuer une recherche lorsque vous réservez des traitements par lots."
author: ShylaThompson
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PdsBatchAttrib, PdsBatchAttribAssociate, PdsBatchAttribByAttribGroup, PdsBatchAttribByItem, PdsBatchAttribByitemCustomer, PdsBatchAttribGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19271
ms.assetid: 41de0250-4a96-412e-a412-aa06615b6b1d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 325e647185e3eb4c0eacdfd00c320804e31ddb48
ms.contentlocale: fr-fr
ms.lasthandoff: 08/07/2018

---

# <a name="batch-attributes"></a><span data-ttu-id="8bf95-105">Attributs de lot</span><span class="sxs-lookup"><span data-stu-id="8bf95-105">Batch attributes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8bf95-106">Cette rubrique fournit des informations sur les attributs de lot.</span><span class="sxs-lookup"><span data-stu-id="8bf95-106">This topic provides information about batch attributes.</span></span> <span data-ttu-id="8bf95-107">Les attributs de lot sont des caractéristiques de matières premières et de produits finis qui constituent des lots de stock.</span><span class="sxs-lookup"><span data-stu-id="8bf95-107">Batch attributes are characteristics of raw materials and finished products that make up inventory batches.</span></span> <span data-ttu-id="8bf95-108">La rubrique décrit également les manières d'affecter des attributs de lot et d'y effectuer une recherche lorsque vous réservez des traitements par lots.</span><span class="sxs-lookup"><span data-stu-id="8bf95-108">The topic also explains how to assign batch attributes, and how you can search on them when you reserve batches.</span></span>

<span data-ttu-id="8bf95-109">Les attributs de lot sont des caractéristiques de matières premières et de produits finis qui constituent des lots de stock.</span><span class="sxs-lookup"><span data-stu-id="8bf95-109">Batch attributes are characteristics of raw materials and finished products that make up inventory batches.</span></span> <span data-ttu-id="8bf95-110">Les attributs de lot peuvent varier en fonction de plusieurs facteurs, comme les conditions environnementales, la qualité des matières premières utilisées pour produire le lot ou le résultat du produit fini.</span><span class="sxs-lookup"><span data-stu-id="8bf95-110">Batch attributes can vary, depending on factors such as environmental conditions, the quality of the raw materials that are used to produce the batch, or the outcome of the finished product.</span></span> <span data-ttu-id="8bf95-111">Le nombre et les types d'attributs de lot utilisés peuvent fortement varier d'un secteur à l'autre.</span><span class="sxs-lookup"><span data-stu-id="8bf95-111">The number and types of batch attributes that are used can vary widely from one industry to another.</span></span> <span data-ttu-id="8bf95-112">Voici deux exemples d'utilisation d'attributs de lot :</span><span class="sxs-lookup"><span data-stu-id="8bf95-112">Here are two examples that show how to use batch attributes:</span></span>

-   <span data-ttu-id="8bf95-113">Dans l'industrie fromagère, le lait, une des matières premières utilisées dans la production de fromage, peut disposer d'attributs tels que la teneur en matière grasse et le pourcentage en masse.</span><span class="sxs-lookup"><span data-stu-id="8bf95-113">In the cheese industry, milk, which is one of the raw materials that are used to produce the cheese, can have attributes such as fat content and percentage weight.</span></span> <span data-ttu-id="8bf95-114">D'autres attributs, comme l'humidité et la maturité, peuvent s'ajouter au fromage fabriqué à partir du lait.</span><span class="sxs-lookup"><span data-stu-id="8bf95-114">The cheese that is produced from the milk can have other attributes, such as moisture and age.</span></span>
-   <span data-ttu-id="8bf95-115">Dans l'industrie sidérurgique, les attributs du fer produit peuvent correspondre aux pourcentages de contenu en magnésium, argent et zinc.</span><span class="sxs-lookup"><span data-stu-id="8bf95-115">In the steel industry, the iron that is produced might have attributes such as the percentages of magnesium content, silver content, and zinc content.</span></span>

<span data-ttu-id="8bf95-116">Pour mieux gérer le nombre et les types d'attributs, vous pouvez utiliser des groupes d'attributs de lot.</span><span class="sxs-lookup"><span data-stu-id="8bf95-116">To better manage the number and types of attributes, you can use batch attribute groups.</span></span> <span data-ttu-id="8bf95-117">Ainsi, il n'est pas nécessaire d'ajouter chaque attribut individuellement.</span><span class="sxs-lookup"><span data-stu-id="8bf95-117">In this way, you don't have to add each attribute individually.</span></span>

## <a name="assign-batch-attributes"></a><span data-ttu-id="8bf95-118">Affecter des attributs de lot</span><span class="sxs-lookup"><span data-stu-id="8bf95-118">Assign batch attributes</span></span>
<span data-ttu-id="8bf95-119">Vous pouvez affecter des attributs de lot à différents produits dans des lots de stock ou à des produits liés à des clients spécifiques.</span><span class="sxs-lookup"><span data-stu-id="8bf95-119">You can assign batch attributes to individual products that are held in inventory batches, or you can assign them to products that are associated with specific customers.</span></span> <span data-ttu-id="8bf95-120">Pour pouvoir affecter un attribut de lot au niveau du client, vous devez d'abord l'affecter au niveau du produit.</span><span class="sxs-lookup"><span data-stu-id="8bf95-120">Before you can assign a batch attribute at the customer level, you must assign it at the product level.</span></span> <span data-ttu-id="8bf95-121">La dimension de lot du produit doit être définie sur **Actif** dans le groupe de dimensions de suivi.</span><span class="sxs-lookup"><span data-stu-id="8bf95-121">The product must have the batch dimension set to **Active** in the tracking dimension group.</span></span> <span data-ttu-id="8bf95-122">Pour affecter un attribut de lot à un produit individuel, utilisez la page spécifique au produit.</span><span class="sxs-lookup"><span data-stu-id="8bf95-122">To assign a batch attribute to an individual product, use the product-specific page.</span></span> <span data-ttu-id="8bf95-123">Si l'attribut est spécifique à un produit pour un client, utilisez la page spécifique au client.</span><span class="sxs-lookup"><span data-stu-id="8bf95-123">If the attribute is specific to a product for a customer, use the customer-specific page.</span></span> <span data-ttu-id="8bf95-124">Lorsque vous ajoutez un attribut à un produit, vous définissez également d'autres paramètres.</span><span class="sxs-lookup"><span data-stu-id="8bf95-124">When you add an attribute to a product, you also define other parameters.</span></span> <span data-ttu-id="8bf95-125">Voici quelques exemples :</span><span class="sxs-lookup"><span data-stu-id="8bf95-125">Here are some examples:</span></span>

-   <span data-ttu-id="8bf95-126">Les plages Minimum et Maximum d'un attribut de type **Entier** ou **Fraction**.</span><span class="sxs-lookup"><span data-stu-id="8bf95-126">The minimum and maximum ranges for an attribute of the **Integer** or **Fraction** type.</span></span>
-   <span data-ttu-id="8bf95-127">Les actions de tolérance d'un attribut du type **Entier** ou **Fraction**.</span><span class="sxs-lookup"><span data-stu-id="8bf95-127">The tolerance actions for an attribute of the **Integer** or **Fraction** type.</span></span> <span data-ttu-id="8bf95-128">Si la valeur de l'attribut n'est pas comprise dans la plage Minimum et Maximum, l'action peut être un message d'avertissement ou un message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="8bf95-128">If the value of the attribute falls outside the minimum and maximum range, the action can be either a warning message or an error message.</span></span>
-   <span data-ttu-id="8bf95-129">La valeur cible de l'attribut.</span><span class="sxs-lookup"><span data-stu-id="8bf95-129">The target value for the attribute.</span></span> <span data-ttu-id="8bf95-130">Cette valeur est la valeur optimale de l'attribut et s'applique à tous les types d'attributs.</span><span class="sxs-lookup"><span data-stu-id="8bf95-130">This value is the optimal value of the attribute, and it applies to all attribute types.</span></span>

<span data-ttu-id="8bf95-131">Vous pouvez accéder aux pages des produits que vous sélectionnez dans la page **Produits lancés** dans Gestion des informations sur les produits.</span><span class="sxs-lookup"><span data-stu-id="8bf95-131">You can access the pages for products that you select on the **Released products** page in Product information management.</span></span> <span data-ttu-id="8bf95-132">Après avoir affecté des attributs de lot à un produit, vous pouvez ajouter des valeurs spécifiques aux attributs dans la page **Attributs de lot de stock**.</span><span class="sxs-lookup"><span data-stu-id="8bf95-132">After you assign batch attributes to a product, you can add specific values to the attributes on the **Inventory batch attributes** page.</span></span>

## <a name="reserve-batches"></a><span data-ttu-id="8bf95-133">Réservation de lots</span><span class="sxs-lookup"><span data-stu-id="8bf95-133">Reserve batches</span></span>
<span data-ttu-id="8bf95-134">Vous pouvez effectuer une recherche dans les attributs de lot lorsque vous effectuez des réservations de lot pour une commande client pour honorer la commande d'un client, ou lorsque vous prélevez et réservez des lots pour un ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="8bf95-134">You can search on batch attributes when you do batch reservations for a sales order to fulfill a customer's order, or when you pick and reserve batches for a production order.</span></span> <span data-ttu-id="8bf95-135">La recherche permet de trouver un lot de stock qui contient le produit présentant l'attribut de lot souhaité.</span><span class="sxs-lookup"><span data-stu-id="8bf95-135">The search helps locate an inventory batch that contains the product that has the batch attribute that you want.</span></span> <span data-ttu-id="8bf95-136">Une fois le ou les lots trouvés, vous pouvez réserver le produit dans la ligne de mouvement de stock d'origine.</span><span class="sxs-lookup"><span data-stu-id="8bf95-136">After you locate the batch or batches, you can reserve the product to the originating inventory transaction line.</span></span>




