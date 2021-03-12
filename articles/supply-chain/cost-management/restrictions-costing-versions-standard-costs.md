---
title: Restrictions applicables aux version d'évaluation des coûts standard
description: Cette rubrique décrit les restrictions qui s'appliquent à une version d'évaluation des coûts standard.
author: AndersGirke
manager: tfehr
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5339c3c4a62b94a06cbffc200ed1e9b227d6b6af
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963786"
---
#  <a name="restrictions-on-costing-versions-for-standard-costs"></a><span data-ttu-id="35e27-103">Restrictions applicables aux version d'évaluation des coûts standard</span><span class="sxs-lookup"><span data-stu-id="35e27-103">Restrictions on costing versions for standard costs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="35e27-104">Cette rubrique décrit les restrictions qui s'appliquent à une version d'évaluation des coûts standard.</span><span class="sxs-lookup"><span data-stu-id="35e27-104">This topic describes the restrictions that apply to a costing version for standard costs.</span></span> 

<span data-ttu-id="35e27-105">Les restrictions suivantes aident à garantir le respect des principes d'évaluation des coûts standard :</span><span class="sxs-lookup"><span data-stu-id="35e27-105">The following restrictions help guarantee adherence to standard costing principles:</span></span>

-  <span data-ttu-id="35e27-106">Les frais doivent être inclus dans le coût d'un article.</span><span class="sxs-lookup"><span data-stu-id="35e27-106">Charges must be included in an item's cost.</span></span> <span data-ttu-id="35e27-107">Les frais d'un article fabriqué représentent les coûts constants amortis dans les informations de nomenclature et de gamme.</span><span class="sxs-lookup"><span data-stu-id="35e27-107">The charges for a manufactured item represent the amortized constant costs in the bill of materials (BOM) and route information.</span></span> <span data-ttu-id="35e27-108">Il faut donc les inclure dans le coût unitaire.</span><span class="sxs-lookup"><span data-stu-id="35e27-108">Therefore, the charges must be included in the unit cost.</span></span> <span data-ttu-id="35e27-109">Les frais d'un article acheté sont également inclus dans le coût unitaire de l'article.</span><span class="sxs-lookup"><span data-stu-id="35e27-109">The charges for a purchased item are also included in the item's unit cost.</span></span>

-  <span data-ttu-id="35e27-110">Le calcul des coûts standard des articles fabriqués doit être basé sur les enregistrements des coûts dans une version d'évaluation des coûts standard.</span><span class="sxs-lookup"><span data-stu-id="35e27-110">Calculation of standard costs for manufactured items must be based on the cost records in a costing version for standard costs.</span></span> <span data-ttu-id="35e27-111">D'autres sources de données de coût peuvent être utilisées uniquement avec une version d'évaluation des coûts planifiés, comme les accords commerciaux de prix d'achat pour les articles achetés.</span><span class="sxs-lookup"><span data-stu-id="35e27-111">Alternative sources of cost data can be used only with a costing version for planned costs, such as purchase price trade agreements for purchased items.</span></span> <span data-ttu-id="35e27-112">D'autres sources de données de coût sont définies par le groupe de calcul de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="35e27-112">Alternative sources of cost data are defined by the BOM calculation group.</span></span>

-  <span data-ttu-id="35e27-113">Les calculs de nomenclature doivent être effectués en mode d'éclatement à un seul niveau.</span><span class="sxs-lookup"><span data-stu-id="35e27-113">BOM calculations must be performed in a single-level explosion mode.</span></span>

<span data-ttu-id="35e27-114">Les données de coût de l'article pour les coûts standard peuvent être copiées dans une autre version d'évaluation des coûts qui contient des coûts standard ou des coûts planifiés.</span><span class="sxs-lookup"><span data-stu-id="35e27-114">The item cost data for standard costs can be copied to another costing version that contains standard costs or planned costs.</span></span> <span data-ttu-id="35e27-115">Toutefois, les données de coût d'article pour les coûts planifiés ne peuvent pas être copiées dans une version d'évaluation des coûts qui contient des coûts standard, car les restrictions répertoriées précédemment dans cette rubrique ne s'appliquent pas aux coûts planifiés.</span><span class="sxs-lookup"><span data-stu-id="35e27-115">However, the item cost data for planned costs can't be copied to a cost version that contains standard costs, because the restrictions that are listed earlier in this topic don't apply to planned costs.</span></span>

<a name="related-topics"></a><span data-ttu-id="35e27-116">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="35e27-116">Related topics</span></span>
--------

[<span data-ttu-id="35e27-117">Vue d'ensemble des versions d'évaluation des coûts</span><span class="sxs-lookup"><span data-stu-id="35e27-117">Costing versions overview</span></span>](costing-versions.md)

[<span data-ttu-id="35e27-118">Mise à jour des coûts standard dans un environnement hors fabrication</span><span class="sxs-lookup"><span data-stu-id="35e27-118">Update standard costs in a non-manufacturing environment</span></span>](update-standard-costs-non-manufacturing-environment.md)

[<span data-ttu-id="35e27-119">Préparation de la mise à jour des coûts standard pour les articles fabriqués</span><span class="sxs-lookup"><span data-stu-id="35e27-119">Prepare to maintain standard costs for manufactured items</span></span>](update-standard-costs-manufacturing-environment.md)

