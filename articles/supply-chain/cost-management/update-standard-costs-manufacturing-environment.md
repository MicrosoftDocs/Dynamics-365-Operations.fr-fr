---
title: Mise à jour des coûts standard dans un environnement de fabrication
description: Cet article fournit des instructions sur la mise à jour des coûts standard dans un environnement de fabrication.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79663
ms.assetid: 3a7c3d13-8dbc-442d-a281-ac0ebe99ec83
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 726eccdc8a9350a292ba719784b5db99afdfad4f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5262427"
---
# <a name="update-standard-costs-in-a-manufacturing-environment"></a><span data-ttu-id="481b8-103">Mise à jour des coûts standard dans un environnement de fabrication</span><span class="sxs-lookup"><span data-stu-id="481b8-103">Update standard costs in a manufacturing environment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="481b8-104">Cet article fournit des instructions sur la mise à jour des coûts standard dans un environnement de fabrication.</span><span class="sxs-lookup"><span data-stu-id="481b8-104">This article provides guidance about how to update standard costs in a manufacturing environment.</span></span> 

<span data-ttu-id="481b8-105">Les mises à jour peuvent refléter les nouveaux articles, les catégories de coûts ou les formules de calcul des coûts indirects.</span><span class="sxs-lookup"><span data-stu-id="481b8-105">Updates can reflect new items, cost categories, or indirect cost calculation formulas.</span></span> <span data-ttu-id="481b8-106">Elles peuvent également refléter des corrections et des modifications de coûts.</span><span class="sxs-lookup"><span data-stu-id="481b8-106">They can also reflect corrections and cost changes.</span></span> <span data-ttu-id="481b8-107">Le type de mise à jour affecte les étapes nécessaires à exécuter pour mettre à jour les coûts standard, comme illustré dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="481b8-107">The type of update affects the steps that you must complete to update standard costs, as illustrated in the following cases:</span></span>

-   <span data-ttu-id="481b8-108">Entrez les modifications prévues des coûts standard pour les articles achetés, puis modifiez le statut des enregistrements des coûts des articles à **Actif** à la date appropriée.</span><span class="sxs-lookup"><span data-stu-id="481b8-108">Enter expected standard cost changes for purchased items, and then change the status of the item cost records to **Active** on the appropriate date.</span></span> <span data-ttu-id="481b8-109">Toutefois, ne recalculez pas les coûts des articles fabriqués qui utilisent les articles achetés.</span><span class="sxs-lookup"><span data-stu-id="481b8-109">However, don't recalculate the costs of manufactured items that use the purchased items.</span></span>
-   <span data-ttu-id="481b8-110">Entrez les coûts standard pour un nouvel article acheté mais ne recalculez pas les coûts des articles fabriqués avec une version de nomenclature qui contient le nouvel article acheté comme composant.</span><span class="sxs-lookup"><span data-stu-id="481b8-110">Enter standard costs for a new purchased item, but don't recalculate the costs of manufactured items that have a bill of materials (BOM) version that contains the new purchased item as a component.</span></span>
-   <span data-ttu-id="481b8-111">Corrigez ou modifiez le coût d’un article acheté ou modifiez le groupe de coûts attribué à un article acheté et calculez le coût de tous les articles fabriqués avec une version de nomenclature qui contient l’article acheté comme composant.</span><span class="sxs-lookup"><span data-stu-id="481b8-111">Correct or change the cost of a purchased item, or change the cost group that is assigned to a purchased item, and calculate the cost for all manufactured items that have a BOM version that contains the purchased item as a component.</span></span>
-   <span data-ttu-id="481b8-112">Modifiez le coût pour une catégorie de coûts et calculez le coût de tous les articles fabriqués avec une version de gamme qui contient les opérations de gamme qui utilisent la catégorie de coûts.</span><span class="sxs-lookup"><span data-stu-id="481b8-112">Change the cost for a cost category, and calculate the cost for all manufactured items that have a route version that contains routing operations that use the cost category.</span></span>
-   <span data-ttu-id="481b8-113">Modifiez les catégories de coûts qui sont affectées aux opérations de gamme ou au groupe de coûts affecté aux catégories de coûts.</span><span class="sxs-lookup"><span data-stu-id="481b8-113">Change the cost categories that are assigned to routing operations or the cost group that is assigned to cost categories.</span></span> <span data-ttu-id="481b8-114">Puis calculez le coût de tous les articles fabriqués avec une version de gamme qui contient les opérations de gamme qui utilisent la catégorie de coûts.</span><span class="sxs-lookup"><span data-stu-id="481b8-114">Then calculate the cost for all manufactured items that have a route version that contains routing operations that use the cost category.</span></span>
-   <span data-ttu-id="481b8-115">Modifiez une formule de calcul de coûts indirects et calculez le coût de tous les articles fabriqués concernés par la modification.</span><span class="sxs-lookup"><span data-stu-id="481b8-115">Change an indirect cost calculation formula, and calculate the cost for all manufactured items that are affected by the change.</span></span>
-   <span data-ttu-id="481b8-116">Modifiez ou ajoutez un site de fabrication pour un article fabriqué et calculez le coût de fabrication de l’article pour le site.</span><span class="sxs-lookup"><span data-stu-id="481b8-116">Change or add a manufacturing site for a manufactured item, and calculate the item's manufactured cost for the site.</span></span>
-   <span data-ttu-id="481b8-117">Calculez, ou recalculez, le coût d’un article fabriqué et recalculez le coût de tous les articles fabriqués avec une version de nomenclature qui contient l’article fabriqué comme composant.</span><span class="sxs-lookup"><span data-stu-id="481b8-117">Calculate, or recalculate, the cost for a manufactured item, and recalculate the cost for all manufactured items that have a BOM version that contains the manufactured item as a component.</span></span>
-   <span data-ttu-id="481b8-118">Calculez les coûts pour un nouvel article fabriqué sur la base de sa nomenclature définie, approuvée et active et de ses informations de gamme.</span><span class="sxs-lookup"><span data-stu-id="481b8-118">Calculate costs for a new manufactured item, based on its defined, approved, and active BOM and route information.</span></span>

<span data-ttu-id="481b8-119">Chaque cas nécessite un examen attentif de la façon de mettre à jour les coûts standard.</span><span class="sxs-lookup"><span data-stu-id="481b8-119">Each case requires careful consideration about how to update standard costs.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]