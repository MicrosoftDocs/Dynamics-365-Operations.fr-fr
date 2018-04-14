---
title: "Paramétrer les produits pouvant être produits ou approvisionnés"
description: "L'approvisionnement des produits peut se faire suivant différentes manières -  ils peuvent être produits (fabriqués) ou être obtenus (achetés). Cet article décrit certains points habituels dont vous devez tenir compte lors de la configuration des produits pour prendre en charge le multi- approvisionnement."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqGroup, ReqItemTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 21841
ms.assetid: acc608b7-2cad-4fba-afee-9b7cc93761ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 81f556dca0bfa17623bb1a0f1c712bfa5a4a2a9b
ms.contentlocale: fr-fr
ms.lasthandoff: 04/13/2018

---

# <a name="set-up-products-that-can-be-produced-or-procured"></a><span data-ttu-id="6d136-104">Paramétrer les produits pouvant être produits ou approvisionnés</span><span class="sxs-lookup"><span data-stu-id="6d136-104">Set up products that can be produced or procured</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="6d136-105">L'approvisionnement des produits peut se faire suivant différentes manières -  ils peuvent être produits (fabriqués) ou être obtenus (achetés).</span><span class="sxs-lookup"><span data-stu-id="6d136-105">Products can be sourced in various ways -  they can be produced (manufactured) or procured (purchased).</span></span> <span data-ttu-id="6d136-106">Cet article décrit certains points habituels dont vous devez tenir compte lors de la configuration des produits pour prendre en charge le multi- approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="6d136-106">This article describes some typical points to consider when you configure products to support multi-sourcing.</span></span> 

<span data-ttu-id="6d136-107">Les sources d'approvisionnement multiples sont généralement utilisées pour un article acheté qui est occasionnellement fabriqué, ou lorsqu'un article qui est principalement un article fabriqué est modifié pour devenir principalement un article acheté.</span><span class="sxs-lookup"><span data-stu-id="6d136-107">Multi-sourcing is typically used for a purchased item that is occasionally manufactured, or when an item that was primarily a manufactured item is changed so that it's now primarily a purchased item.</span></span> <span data-ttu-id="6d136-108">L'article est d'abord désigné comme un article fabriqué afin de définir les informations de nomenclature et de gamme et de prendre en charge les ordres de fabrication pour l'article.</span><span class="sxs-lookup"><span data-stu-id="6d136-108">The item is first designated as a manufactured item, so that bill of materials (BOM) and route information can be defined, and to support production orders for the item.</span></span> <span data-ttu-id="6d136-109">Le type de production doit être défini sur **Nomenclature** (ou, pour le traitement de la production, **Formule** ou **Coproduit**).</span><span class="sxs-lookup"><span data-stu-id="6d136-109">The production type should be set to **BOM** (or, for process manufacturing, **Formula** or **Co-Product**).</span></span>

<span data-ttu-id="6d136-110">Lorsque vous utilisez le coût standard, l'enregistrement des coûts de l'article peut être calculé pour l'article fabriqué.</span><span class="sxs-lookup"><span data-stu-id="6d136-110">When you use standard cost, the item cost record can be calculated for the manufactured item.</span></span> <span data-ttu-id="6d136-111">Toutefois, il se peut que l'enregistrement des coûts de l'article ne corresponde pas au coût standard que vous souhaitez pour l'achat.</span><span class="sxs-lookup"><span data-stu-id="6d136-111">However, the item cost record might not match the standard cost that you want for purchasing purposes.</span></span> <span data-ttu-id="6d136-112">Dans ce cas, le coût standard doit être entré et activé manuellement pour l'enregistrement des coûts de l'article.</span><span class="sxs-lookup"><span data-stu-id="6d136-112">In this case, the standard cost must be manually entered and activated for the item cost record.</span></span> <span data-ttu-id="6d136-113">Pour le calcul des coûts, envisagez d'utiliser une nomenclature et une gamme spéciales qui représentent la combinaison d'approvisionnement du produit au cours d'une période fiscale, pour réduire les écarts dans le temps.</span><span class="sxs-lookup"><span data-stu-id="6d136-113">For the cost calculation, consider using a special BOM and route that represent the supply mix of the product over the course of a fiscal period, to minimize the variances over time.</span></span> <span data-ttu-id="6d136-114">En outre, un article fabriqué sur un seul site peut être transféré vers un autre site.</span><span class="sxs-lookup"><span data-stu-id="6d136-114">Additionally, a manufactured item at one site can be transferred to another site.</span></span> <span data-ttu-id="6d136-115">Aussi, le coût de l'article doit être entré et activé manuellement pour le site vers lequel l'article est transféré.</span><span class="sxs-lookup"><span data-stu-id="6d136-115">Therefore, the item's cost must be manually entered and activated for the site that the item is transferred to.</span></span> <span data-ttu-id="6d136-116">Lorsque vous utilisez l'article fabriqué comme composant de produits de niveau supérieur, les coûts du composant doivent être considérés comme un article acheté,</span><span class="sxs-lookup"><span data-stu-id="6d136-116">When you use the manufactured item as a component in higher-level products, the component's costs should be treated as a purchased item.</span></span> <span data-ttu-id="6d136-117">Ces instructions s'appliquent, que les coûts du composant soient calculés ou entrés manuellement.</span><span class="sxs-lookup"><span data-stu-id="6d136-117">This guideline applies, regardless of whether the component’s costs were calculated or manually entered.</span></span> <span data-ttu-id="6d136-118">En d'autres termes, le calcul de la nomenclature doit considérer les coûts de l'article comme un composant acheté au lieu d'utiliser les informations de nomenclature et de gamme de l'article pour calculer les coûts.</span><span class="sxs-lookup"><span data-stu-id="6d136-118">In other words, a BOM calculation should treat the item's costs as a purchased component instead of using the item's BOM and route information to calculate costs.</span></span> 

<span data-ttu-id="6d136-119">Pour éviter le calcul, sélectionnez l'indicateur **Arrêter l'éclatement** qui est intégré au groupe de calcul de la nomenclature attribué à l'article.</span><span class="sxs-lookup"><span data-stu-id="6d136-119">To prevent the calculation from occurring, select the **Stop explosion** flag that is embedded in the BOM calculation group that is assigned to the item.</span></span> <span data-ttu-id="6d136-120">Pour empêcher les calculs PDP/MRP de faire éclater les demandes d'article, définissez la plage d'éclatement sur 0 (zéro) jours dans la couverture d'article ou dans le groupe de couverture.</span><span class="sxs-lookup"><span data-stu-id="6d136-120">To prevent master scheduling calculations from exploding requirements through the item, set the explosion fence to 0 (zero) days in item coverage or in the coverage group.</span></span> <span data-ttu-id="6d136-121">Le calcul PDP/MRP considère l'article comme un article acheté et n'effectue plus de calculs pour les informations de nomenclature et de gamme de l'article.</span><span class="sxs-lookup"><span data-stu-id="6d136-121">The master scheduling calculation will then treat the item as a purchased item and won't perform more calculations for the item's BOM and route information.</span></span>






