---
title: "Mappage de membres de dimension d'élément de coût à un ensemble commun de membres de dimension"
description: "En mappant différents membres de la dimension d'élément de coût à un ensemble commun de membres de la dimension d'élément de coût, vous fusionnez les données en un format commun à des fins de analyse."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMDimension, CAMDimensionMember
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 223234
ms.assetid: 4c66a231-aed2-48b5-9727-b3eb4fe6e6aa
ms.search.region: global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b15e251410937ff4f85ecdfaa55ca1a998d1d1ac
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="map-cost-element-dimension-members-to-a-common-set-of-dimension-members"></a><span data-ttu-id="e8a18-103">Mappage de membres de dimension d'élément de coût à un ensemble commun de membres de dimension</span><span class="sxs-lookup"><span data-stu-id="e8a18-103">Map cost element dimension members to a common set of dimension members</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="e8a18-104">En mappant différents membres de la dimension d'élément de coût à un ensemble commun de membres de la dimension d'élément de coût, vous fusionnez les données en un format commun à des fins de analyse.</span><span class="sxs-lookup"><span data-stu-id="e8a18-104">By mapping different cost element dimension members to a common set of cost element dimension members, you merge data into a common format for analysis purposes.</span></span>

<span data-ttu-id="e8a18-105">Si vous êtes une société internationale et que vous vous conformez aux besoins statutaires de comptabilité, vous pouvez utiliser plusieurs plans de comptes.</span><span class="sxs-lookup"><span data-stu-id="e8a18-105">If you're a global company and comply with statutory accounting requirements, you might use multiple charts of accounts.</span></span> <span data-ttu-id="e8a18-106">Lorsque vous importez des membres de la dimension d'article des coûts de différents plans de comptes, vous pouvez vous retrouver avec une combinaison de comptes.</span><span class="sxs-lookup"><span data-stu-id="e8a18-106">When you import cost element dimension members from different charts of accounts, you can end up with a mix of accounts.</span></span> <span data-ttu-id="e8a18-107">Toutefois, ces comptes peuvent en fait être de même nature, et vous pouvez analyser et répartir les coûts associés à l'aide d'un format courant.</span><span class="sxs-lookup"><span data-stu-id="e8a18-107">However, these accounts might actually have the same nature, and you might want to analyze and allocate costs for them by using a common format.</span></span>

## <a name="map-cost-element-dimension-members-to-a-common-format"></a><span data-ttu-id="e8a18-108">Mapper les membres de la dimension d'élément de coût à un format commun</span><span class="sxs-lookup"><span data-stu-id="e8a18-108">Map cost element dimension members to a common format</span></span>
<span data-ttu-id="e8a18-109">L'exemple suivant illustre comment vous, contrôleur de coût, pouvez créer une nouvelle dimension d'élément de coût dans le contrôle de gestion qui mappe des membres de la dimension d'élément de coût dans la structure du plan de comptes américain et la structure de plan de comptes française à un ensemble commun de membres de la dimension d'élément de coût.</span><span class="sxs-lookup"><span data-stu-id="e8a18-109">The following example shows how you, as a cost controller, can create a new cost element dimension in Cost accounting that maps cost element dimension members from the US chart of accounts structure and the French chart of accounts structure to a common set of cost element dimension members.</span></span> <span data-ttu-id="e8a18-110">Vous pouvez ensuite utiliser l'ensemble commun de membres de la dimension d'élément de coût pour analyser les données de coût des deux entités juridiques dans la comptabilité de contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="e8a18-110">You can then use the common set of cost element dimension members to analyze cost data from the two legal entities in a cost accounting ledger.</span></span>

| <span data-ttu-id="e8a18-111">Source : Plan de comptes américain</span><span class="sxs-lookup"><span data-stu-id="e8a18-111">Source: US chart of accounts</span></span>                                          | <span data-ttu-id="e8a18-112">Source : Plan de comptes français</span><span class="sxs-lookup"><span data-stu-id="e8a18-112">Source: French chart of accounts</span></span>                                          | <span data-ttu-id="e8a18-113">Nouvel ensemble commun de membres de la dimension d'élément de coût</span><span class="sxs-lookup"><span data-stu-id="e8a18-113">New common set of cost element dimension members</span></span>                        |
|-----------------------------------------------------------------------|---------------------------------------------------------------------------|-------------------------------------------------------------------------|
| <span data-ttu-id="e8a18-114">Membres de dimension d'élément de coût importés du plan de comptes américain</span><span class="sxs-lookup"><span data-stu-id="e8a18-114">Imported cost element dimension members from the US chart of accounts</span></span> | <span data-ttu-id="e8a18-115">Membres de dimension d'élément de coût importés du plan de comptes français</span><span class="sxs-lookup"><span data-stu-id="e8a18-115">Imported cost element dimension members from the French chart of accounts</span></span> | <span data-ttu-id="e8a18-116">Mappage des membres de dimension d'élément de coût américains et français à un ensemble commun</span><span class="sxs-lookup"><span data-stu-id="e8a18-116">Mapping of US and French cost element dimension members to a common set</span></span> |
| <span data-ttu-id="e8a18-117">5001 : Ventes</span><span class="sxs-lookup"><span data-stu-id="e8a18-117">5001: Sales</span></span>                                                           | <span data-ttu-id="e8a18-118">5001 : Ventes et publicité</span><span class="sxs-lookup"><span data-stu-id="e8a18-118">5001: Sales and advertising</span></span>                                               | <span data-ttu-id="e8a18-119">5000 : Ventes et publicité</span><span class="sxs-lookup"><span data-stu-id="e8a18-119">5000: Sales and advertising</span></span>                                             |
| <span data-ttu-id="e8a18-120">5030 : Publicité</span><span class="sxs-lookup"><span data-stu-id="e8a18-120">5030: Advertising</span></span>                                                     | <span data-ttu-id="e8a18-121">6390 : Achat d'actions\*</span><span class="sxs-lookup"><span data-stu-id="e8a18-121">6390: Stock purchase\*</span></span>                                                    | <span data-ttu-id="e8a18-122">7000 : Dépenses de nettoyage</span><span class="sxs-lookup"><span data-stu-id="e8a18-122">7000: Cleaning expenses</span></span>                                                 |
| <span data-ttu-id="e8a18-123">7001 : Dépenses de nettoyage</span><span class="sxs-lookup"><span data-stu-id="e8a18-123">7001: Cleaning expenses</span></span>                                               | <span data-ttu-id="e8a18-124">7001 : Dépenses de déplacements</span><span class="sxs-lookup"><span data-stu-id="e8a18-124">7001: Travel expense</span></span>                                                      | <span data-ttu-id="e8a18-125">7001 : Dépenses de déplacements</span><span class="sxs-lookup"><span data-stu-id="e8a18-125">7001: Travel expenses</span></span>                                                   |

<span data-ttu-id="e8a18-126">\*Le membre de dimension de l'élément du coût d'achat d'actions français n'est pas mappé.</span><span class="sxs-lookup"><span data-stu-id="e8a18-126">\*The Stock purchase French cost element dimension member isn't mapped.</span></span>

## <a name="currency-conversion"></a><span data-ttu-id="e8a18-127">Conversion de devise</span><span class="sxs-lookup"><span data-stu-id="e8a18-127">Currency conversion</span></span>
<span data-ttu-id="e8a18-128">Les différents plans de comptes que vous utilisez peuvent être paramétrés pour utiliser plusieurs devises.</span><span class="sxs-lookup"><span data-stu-id="e8a18-128">The various charts of accounts that you use might be set up to use different currencies.</span></span> <span data-ttu-id="e8a18-129">Dans ce cas, assurez-vous de spécifier une conversion de devise, afin que les données de coût soient traitées à l'aide de la devise appropriée, comme défini dans la comptabilité de contrôle de gestion dans laquelle les membres de la dimension d'élément de coût sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="e8a18-129">In this case, be sure to specify a currency conversion, so that cost data is processed by using the correct currency, as defined in the cost accounting ledger where the cost element dimension members are used.</span></span> <span data-ttu-id="e8a18-130">Dans l'exemple précédent, si les dollars américains (USD) sont utilisés dans la comptabilité de contrôle de gestion, vous devez créer une conversion de devise des USD en euro (EUR) pour traiter les transactions des membres de dimension d'élément de coût mappés.</span><span class="sxs-lookup"><span data-stu-id="e8a18-130">In the preceding example, if US dollars (USD) are used in the cost accounting ledger, you must create a currency conversion from USD to euros (EUR) to process transactions for the mapped cost element dimension members.</span></span>

## <a name="update-mappings-at-any-time"></a><span data-ttu-id="e8a18-131">Mettre à jour les mappages à tout moment</span><span class="sxs-lookup"><span data-stu-id="e8a18-131">Update mappings at any time</span></span>
<span data-ttu-id="e8a18-132">Vous pouvez mettre à jour les définitions de mappage pour une dimension d'article de coût à tout moment.</span><span class="sxs-lookup"><span data-stu-id="e8a18-132">You can update the mapping definitions for a cost element dimension at any time.</span></span> <span data-ttu-id="e8a18-133">Comme les mappages n'ont pas de dates d'effet, les modifications sont appliquées la prochaine fois que vous exécutez des transactions de coût ou des calculs de coûts.</span><span class="sxs-lookup"><span data-stu-id="e8a18-133">Because mappings aren't date-effective, changes are applied the next time that you process cost transactions or run cost calculations.</span></span>




