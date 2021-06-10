---
title: Stratégies de droit aux avantages
description: Cet article fournit des informations sur les stratégies de droit aux avantages, qui vous permettent de définir qui peut prétendre à des avantages spécifiques.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 87a080c47e34a3265afea6494ff1733dac5bc384
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053103"
---
# <a name="benefit-eligibility-policies"></a><span data-ttu-id="98921-103">Stratégies de droit aux avantages</span><span class="sxs-lookup"><span data-stu-id="98921-103">Benefit eligibility policies</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="98921-104">Cet article fournit des informations sur les stratégies de droit aux avantages, qui vous permettent de définir qui peut prétendre à des avantages spécifiques.</span><span class="sxs-lookup"><span data-stu-id="98921-104">This article provides information about benefit eligibility policies, which help you define who is eligible for specific benefits.</span></span>

<span data-ttu-id="98921-105">Lorsque vous créez des avantages, vous décidez quels avantages sont accessibles pour des employés donnés.</span><span class="sxs-lookup"><span data-stu-id="98921-105">When you create benefits, you decide which benefits will be available to which employees.</span></span> <span data-ttu-id="98921-106">Le tableau suivant indique les exemples des avantages que vous pouvez rendre disponibles à des employés spécifiques.</span><span class="sxs-lookup"><span data-stu-id="98921-106">The following table shows examples of benefits that you might make available to specific employees.</span></span>

| <span data-ttu-id="98921-107">Avantage</span><span class="sxs-lookup"><span data-stu-id="98921-107">Benefit</span></span>          | <span data-ttu-id="98921-108">Pour qui l’avantage est disponible</span><span class="sxs-lookup"><span data-stu-id="98921-108">Who the benefit is available to</span></span> |
|------------------|---------------------------------|
| <span data-ttu-id="98921-109">Assurance médicale maladie</span><span class="sxs-lookup"><span data-stu-id="98921-109">Health insurance</span></span> | <span data-ttu-id="98921-110">Tous les employés</span><span class="sxs-lookup"><span data-stu-id="98921-110">All employees</span></span>                   |
| <span data-ttu-id="98921-111">Téléphone portable</span><span class="sxs-lookup"><span data-stu-id="98921-111">Mobile phone</span></span>     | <span data-ttu-id="98921-112">Vendeurs, cadres</span><span class="sxs-lookup"><span data-stu-id="98921-112">Sales staff, executives</span></span>         |
| <span data-ttu-id="98921-113">Cartes de parking</span><span class="sxs-lookup"><span data-stu-id="98921-113">Parking passes</span></span>   | <span data-ttu-id="98921-114">Cadres</span><span class="sxs-lookup"><span data-stu-id="98921-114">Executives</span></span>                      |

<span data-ttu-id="98921-115">Les composants suivants permettent de créer des stratégies d’éligibilité :</span><span class="sxs-lookup"><span data-stu-id="98921-115">The following components in are used to create eligibility policies:</span></span>

-   <span data-ttu-id="98921-116">Types de règles de stratégie</span><span class="sxs-lookup"><span data-stu-id="98921-116">Policy rule types</span></span>
-   <span data-ttu-id="98921-117">Stratégies de droit aux avantages</span><span class="sxs-lookup"><span data-stu-id="98921-117">Benefit eligibility policies</span></span>

<span data-ttu-id="98921-118">Les types de règles de stratégie définissent les paramètres de requête utilisés lorsque vous développez des règles de stratégie spécifiques.</span><span class="sxs-lookup"><span data-stu-id="98921-118">Policy rule types define the query parameters that are used when you develop specific policy rules.</span></span> <span data-ttu-id="98921-119">Après avoir créé des types de règles de stratégie, vous pouvez créer des stratégies de droit aux avantages.</span><span class="sxs-lookup"><span data-stu-id="98921-119">After you create policy rule types, you can create benefit eligibility policies.</span></span> <span data-ttu-id="98921-120">Les stratégies permettent de créer une collection de règles qui s’appliquent à une ou plusieurs entités juridiques.</span><span class="sxs-lookup"><span data-stu-id="98921-120">The policies let you create a collection of rules that apply to one or more legal entities.</span></span> <span data-ttu-id="98921-121">Dans chaque stratégie, vous pouvez afficher les types de règles de stratégie de droit aux avantages que vous avez créés précédemment.</span><span class="sxs-lookup"><span data-stu-id="98921-121">Within each policy, you can view any of the benefit eligibility policy rule types that you created earlier.</span></span> 

<span data-ttu-id="98921-122">Vous définissez la portée de la règle dans la stratégie.</span><span class="sxs-lookup"><span data-stu-id="98921-122">You define the scope of the rule within the policy.</span></span> <span data-ttu-id="98921-123">Par exemple, si vous créez un type de règle de stratégie de droit aux avantages nommé **Direction**, vous pouvez spécifier ce qu’est la règle de cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="98921-123">For example, if you create a benefit eligibility policy rule type that is named **Executive**, you can specify what the rule is within that policy.</span></span> <span data-ttu-id="98921-124">Dans cet exemple, la règle peut stipuler que toute fonction qui contient le mot « directeur » doit être comprise dans la règle.</span><span class="sxs-lookup"><span data-stu-id="98921-124">In this example, the rule might state that any job title that contains the word "executive" should be included in the rule.</span></span> <span data-ttu-id="98921-125">Après avoir défini les paramètres des règles incluses dans la stratégie, vous pouvez affecter une règle spécifique à l’avantage.</span><span class="sxs-lookup"><span data-stu-id="98921-125">After you've defined the parameters of the rule or rules that are included in the policy, you can assign a specific rule to the benefit.</span></span>






[!INCLUDE[footer-include](../includes/footer-banner.md)]