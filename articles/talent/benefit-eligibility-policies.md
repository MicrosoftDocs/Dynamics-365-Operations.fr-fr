---
title: "Stratégies de droit aux avantages"
description: "Cet article fournit des informations sur les stratégies de droit aux avantages, qui vous permettent de définir qui peut prétendre à des avantages spécifiques."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: 5c0af3d9446b4f8ae80eeb44494f1ef1e6667e55
ms.contentlocale: fr-fr
ms.lasthandoff: 01/19/2018

---

# <a name="benefit-eligibility-policies"></a><span data-ttu-id="0c5b4-103">Stratégies de droit aux avantages</span><span class="sxs-lookup"><span data-stu-id="0c5b4-103">Benefit eligibility policies</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="0c5b4-104">Cette rubrique fournit des informations sur les stratégies de droit aux avantages, qui vous permettent de définir qui peut prétendre à des avantages spécifiques.</span><span class="sxs-lookup"><span data-stu-id="0c5b4-104">This topic provides information about benefit eligibility policies, which help you define who is eligible for specific benefits.</span></span>

<span data-ttu-id="0c5b4-105">Lorsque vous créez des avantages, vous décidez quels avantages sont accessibles pour des employés donnés.</span><span class="sxs-lookup"><span data-stu-id="0c5b4-105">When you create benefits, you decide which benefits will be available to which employees.</span></span> <span data-ttu-id="0c5b4-106">Le tableau suivant indique les exemples des avantages que vous pouvez rendre disponibles à des employés spécifiques.</span><span class="sxs-lookup"><span data-stu-id="0c5b4-106">The following table shows examples of benefits that you might make available to specific employees.</span></span>

| <span data-ttu-id="0c5b4-107">Avantage</span><span class="sxs-lookup"><span data-stu-id="0c5b4-107">Benefit</span></span>          | <span data-ttu-id="0c5b4-108">Pour qui l'avantage est disponible</span><span class="sxs-lookup"><span data-stu-id="0c5b4-108">Who the benefit is available to</span></span> |
|------------------|---------------------------------|
| <span data-ttu-id="0c5b4-109">Assurance médicale maladie</span><span class="sxs-lookup"><span data-stu-id="0c5b4-109">Health insurance</span></span> | <span data-ttu-id="0c5b4-110">Tous les employés</span><span class="sxs-lookup"><span data-stu-id="0c5b4-110">All employees</span></span>                   |
| <span data-ttu-id="0c5b4-111">Téléphone portable</span><span class="sxs-lookup"><span data-stu-id="0c5b4-111">Mobile phone</span></span>     | <span data-ttu-id="0c5b4-112">Vendeurs, cadres</span><span class="sxs-lookup"><span data-stu-id="0c5b4-112">Sales staff, executives</span></span>         |
| <span data-ttu-id="0c5b4-113">Cartes de parking</span><span class="sxs-lookup"><span data-stu-id="0c5b4-113">Parking passes</span></span>   | <span data-ttu-id="0c5b4-114">Cadres</span><span class="sxs-lookup"><span data-stu-id="0c5b4-114">Executives</span></span>                      |

<span data-ttu-id="0c5b4-115">Les composants suivants permettent de créer des stratégies d'éligibilité :</span><span class="sxs-lookup"><span data-stu-id="0c5b4-115">The following components in are used to create eligibility policies:</span></span>

-   <span data-ttu-id="0c5b4-116">Types de règles de stratégie</span><span class="sxs-lookup"><span data-stu-id="0c5b4-116">Policy rule types</span></span>
-   <span data-ttu-id="0c5b4-117">Stratégies de droit aux avantages</span><span class="sxs-lookup"><span data-stu-id="0c5b4-117">Benefit eligibility policies</span></span>

<span data-ttu-id="0c5b4-118">Les types de règles de stratégie définissent les paramètres de requête utilisés lorsque vous développez des règles de stratégie spécifiques.</span><span class="sxs-lookup"><span data-stu-id="0c5b4-118">Policy rule types define the query parameters that are used when you develop specific policy rules.</span></span> <span data-ttu-id="0c5b4-119">Après avoir créé des types de règles de stratégie, vous pouvez créer des stratégies de droit aux avantages.</span><span class="sxs-lookup"><span data-stu-id="0c5b4-119">After you create policy rule types, you can create benefit eligibility policies.</span></span> <span data-ttu-id="0c5b4-120">Les stratégies permettent de créer une collection de règles qui s'appliquent à une ou plusieurs entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="0c5b4-120">The policies let you create a collection of rules that apply to one or more legal entities.</span></span> <span data-ttu-id="0c5b4-121">Dans chaque stratégie, vous pouvez afficher les types de règles de stratégie de droit aux avantages que vous avez créés précédemment.</span><span class="sxs-lookup"><span data-stu-id="0c5b4-121">Within each policy, you can view any of the benefit eligibility policy rule types that you created earlier.</span></span> 

<span data-ttu-id="0c5b4-122">Vous définissez la portée de la règle dans la stratégie.</span><span class="sxs-lookup"><span data-stu-id="0c5b4-122">You define the scope of the rule within the policy.</span></span> <span data-ttu-id="0c5b4-123">Par exemple, si vous créez un type de règle de stratégie de droit aux avantages nommé **Direction**, vous pouvez spécifier ce qu'est la règle de cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="0c5b4-123">For example, if you create a benefit eligibility policy rule type that is named **Executive**, you can specify what the rule is within that policy.</span></span> <span data-ttu-id="0c5b4-124">Dans cet exemple, la règle peut stipuler que toute fonction qui contient le mot « directeur » doit être comprise dans la règle.</span><span class="sxs-lookup"><span data-stu-id="0c5b4-124">In this example, the rule might state that any job title that contains the word “executive” should be included in the rule.</span></span> <span data-ttu-id="0c5b4-125">Après avoir défini les paramètres des règles incluses dans la stratégie, vous pouvez affecter une règle spécifique à l'avantage.</span><span class="sxs-lookup"><span data-stu-id="0c5b4-125">After you've defined the parameters of the rule or rules that are included in the policy, you can assign a specific rule to the benefit.</span></span>

<a name="see-also"></a><span data-ttu-id="0c5b4-126">Voir également :</span><span class="sxs-lookup"><span data-stu-id="0c5b4-126">See also</span></span>
--------

[<span data-ttu-id="0c5b4-127">Définition et gestion d'un programme social</span><span class="sxs-lookup"><span data-stu-id="0c5b4-127">Defining and managing a benefit program</span></span>](manage-benefit-program.md)




