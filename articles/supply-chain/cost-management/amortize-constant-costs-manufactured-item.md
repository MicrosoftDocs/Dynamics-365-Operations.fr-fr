---
title: "Amortissement des coûts constants pour un article fabriqué"
description: "Les coûts constants d'un article fabriqué reflètent les temps de réglage de l'opération et les composants pour lesquels la quantité est constante ou la quantité de rebut est constante."
author: AndersGirke
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCalcDialog, BOMCalcTable, BOMCalcTrans
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 274503
ms.assetid: 535ab25d-a031-4e8c-84ec-478f2987a1ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: 1f3c837d601877142ac6708287a434f5afe088e6
ms.contentlocale: fr-fr
ms.lasthandoff: 01/17/2018

---

# <a name="amortize-constant-costs-for-a-manufactured-item"></a><span data-ttu-id="a6b5e-103">Amortissement des coûts constants pour un article fabriqué</span><span class="sxs-lookup"><span data-stu-id="a6b5e-103">Amortize constant costs for a manufactured item</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="a6b5e-104">Les coûts constants d'un article fabriqué reflètent les temps de réglage de l'opération et les composants pour lesquels la quantité est constante ou la quantité de rebut est constante.</span><span class="sxs-lookup"><span data-stu-id="a6b5e-104">A manufactured item’s constant costs reflect the operation setup times and the components that have a constant quantity or a constant scrap amount.</span></span> 

<span data-ttu-id="a6b5e-105">Le concept de taille du lot d'évaluation des coûts permet d'amortir ces coûts constants dans le coût calculé d'un article fabriqué.</span><span class="sxs-lookup"><span data-stu-id="a6b5e-105">The concept of a costing lot size is used to amortize these constant costs in the calculated cost of a manufactured item.</span></span> <span data-ttu-id="a6b5e-106">Ce concept a plusieurs synonymes, notamment celui de taille de lot comptable.</span><span class="sxs-lookup"><span data-stu-id="a6b5e-106">This concept has several synonyms, one of which is accounting lot size.</span></span> <span data-ttu-id="a6b5e-107">Le concept d'amortissement des coûts constants a également plusieurs synonymes, notamment celui de coûts constants proportionnels.</span><span class="sxs-lookup"><span data-stu-id="a6b5e-107">The concept of amortizing constant costs also has several synonyms, one of which is proportional constant costs.</span></span>

<span data-ttu-id="a6b5e-108">La quantité d'une taille de lot d'évaluation des coûts pour un article fabriqué est utilisée dans un calcul de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="a6b5e-108">The quantity of a costing lot size for a manufactured item is used in a bill of material (BOM) calculation.</span></span> <span data-ttu-id="a6b5e-109">La quantité dépend de la méthode d'initiation et d'exécution du calcul de nomenclature, comme illustré ci-après :</span><span class="sxs-lookup"><span data-stu-id="a6b5e-109">The quantity depends on how you initiate and perform the BOM calculation, as illustrated by the following:</span></span>

-   <span data-ttu-id="a6b5e-110">Quantité de calcul par défaut dans le calcul de nomenclature d'un article : la quantité de commande standard de l'article pour le stock fait office de taille du lot d'évaluation des coûts, mais la valeur par défaut peut être égale à une quantité supérieure afin de refléter la quantité multiple de commande de l'article.</span><span class="sxs-lookup"><span data-stu-id="a6b5e-110">Default calculation quantity in an item’s BOM calculation − The item’s standard order quantity for inventory acts as the costing lot size, but the default value might be a greater quantity to reflect the item’s order quantity multiple.</span></span> <span data-ttu-id="a6b5e-111">La quantité commandée standard de l'article et la quantité multiple peuvent être définies dans les paramètres de commande par défaut ou dans les paramètres de commande spécifiques au site.</span><span class="sxs-lookup"><span data-stu-id="a6b5e-111">The item’s standard order quantity and multiple can be defined within its default order settings or site-specific order settings.</span></span>
-   <span data-ttu-id="a6b5e-112">Quantité de calcul spécifiée dans le calcul de nomenclature d'un article : la quantité de calcul spécifiée fait office de taille du lot d'évaluation des coûts pour l'article.</span><span class="sxs-lookup"><span data-stu-id="a6b5e-112">Specified calculation quantity in an item’s BOM calculation − The specified calculation quantity acts as the costing lot size for the item.</span></span> <span data-ttu-id="a6b5e-113">Au départ, la quantité de calcul utilise la quantité de commande standard de l'article, mais la valeur par défaut peut être remplacée manuellement.</span><span class="sxs-lookup"><span data-stu-id="a6b5e-113">The calculation quantity initially uses the item’s standard order quantity, but the default value can be manually overridden.</span></span> <span data-ttu-id="a6b5e-114">La quantité de commande spécifiée représente la taille du lot d'évaluation des coûts pour l'article spécifié ainsi que pour les composants fabriqués dont la ligne de nomenclature est du type production.</span><span class="sxs-lookup"><span data-stu-id="a6b5e-114">The specified calculation quantity represents the costing lot size for the specified item, and for manufactured components that have a BOM line type of production.</span></span> <span data-ttu-id="a6b5e-115">Cela est dû au fait que le composant est censé être produit en quantité exacte.</span><span class="sxs-lookup"><span data-stu-id="a6b5e-115">This is because it is assumed that the component will be produced to the exact quantity.</span></span> <span data-ttu-id="a6b5e-116">La taille du lot d'évaluation des coûts pour les autres composants fabriqués dont la ligne de nomenclature est du type article reflètera leur quantité de commande standard.</span><span class="sxs-lookup"><span data-stu-id="a6b5e-116">The costing lot size for other manufactured components that have a BOM line type of item will reflect their standard order quantity.</span></span>
-   <span data-ttu-id="a6b5e-117">Quantité de calcul de fabrication à la commande spécifiée dans le calcul de nomenclature d'un article : la quantité de calcul spécifiée fait office de taille du lot d'évaluation des coûts pour l'article et ses composants fabriqués lorsque les calculs de nomenclature utilisent un mode d'éclatement de fabrication à la commande.</span><span class="sxs-lookup"><span data-stu-id="a6b5e-117">Specified make-to-order calculation quantity in an item’s BOM calculation − The specified calculation quantity acts as the costing lot size for the item and its manufactured components when BOM calculations use a make-to-order explosion mode.</span></span> <span data-ttu-id="a6b5e-118">Les composants fabriqués sont censés être produits en quantité exacte, comme un composant fabriqué dont la ligne de nomenclature est du type production.</span><span class="sxs-lookup"><span data-stu-id="a6b5e-118">It is assumed that the manufactured components will be produced to the exact quantity, just like a manufactured component that has a BOM line type of production.</span></span>
-   <span data-ttu-id="a6b5e-119">Quantité de calcul spécifiée dans un calcul de nomenclature spécifique à une commande : un calcul de nomenclature spécifique à une commande peut être réalisé pour une ligne d'une commande client, d'un devis de vente ou d'une commande de service.</span><span class="sxs-lookup"><span data-stu-id="a6b5e-119">Specified calculation quantity in an order-specific BOM calculation − An order-specific BOM calculation can be performed for a line item on a sales order, sales quotation, or service order.</span></span> <span data-ttu-id="a6b5e-120">Par défaut, la quantité de calcul spécifiée utilise la quantité de la ligne d'origine, mais la quantité par défaut peut être remplacée.</span><span class="sxs-lookup"><span data-stu-id="a6b5e-120">The specified calculation quantity uses the quantity on the originating line item, but the default quantity can be overridden.</span></span> <span data-ttu-id="a6b5e-121">Vous pouvez décider que le calcul de nomenclature spécifique à une commande utilise un mode d'éclatement de fabrication à la commande ou à plusieurs niveaux.</span><span class="sxs-lookup"><span data-stu-id="a6b5e-121">You can select whether the order-specific BOM calculation uses a make-to-order or multilevel explosion mode.</span></span>

<span data-ttu-id="a6b5e-122">Le montant calculé des coûts constants amortis d'un article fabriqué est appelé frais.</span><span class="sxs-lookup"><span data-stu-id="a6b5e-122">The calculated amount of a manufactured item’s amortized constant costs is termed charges.</span></span>






