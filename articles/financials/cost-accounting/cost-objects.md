---
title: Dimensions d'objets de coût
description: Lorsque vous analysez les coûts, vous utilisez des dimensions d'élément de coût pour déterminer le flux des coûts. Vous utilisez les dimensions d'objet de coût pour déterminer où vous devez affecter des coûts. Cette rubrique fournit des informations sur les dimensions d'objet de coût.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimensionMember
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 223174
ms.assetid: 2a1cdd35-30cb-41e7-9506-67fd04a537c5
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 60a6575387a6ebe3b349a61368a7561d78dc69f3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565413"
---
# <a name="cost-object-dimensions"></a><span data-ttu-id="2ed88-105">Dimensions d'objets de coût</span><span class="sxs-lookup"><span data-stu-id="2ed88-105">Cost object dimensions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2ed88-106">Lorsque vous analysez les coûts, vous utilisez des dimensions d'élément de coût pour déterminer le flux des coûts.</span><span class="sxs-lookup"><span data-stu-id="2ed88-106">When you analyze costs, you use cost element dimensions to determine where costs flow to.</span></span> <span data-ttu-id="2ed88-107">Vous utilisez les dimensions d'objet de coût pour déterminer où vous devez affecter des coûts.</span><span class="sxs-lookup"><span data-stu-id="2ed88-107">You use cost object dimensions to determine where you should assign costs.</span></span> <span data-ttu-id="2ed88-108">Cette rubrique fournit des informations sur les dimensions d'objet de coût.</span><span class="sxs-lookup"><span data-stu-id="2ed88-108">This topic provides information about cost object dimensions.</span></span>

<span data-ttu-id="2ed88-109">Un objet de coût peut être n'importe quel type d'objet que vous voulez estimer, affecter des coûts, ou mesurer directement.</span><span class="sxs-lookup"><span data-stu-id="2ed88-109">A cost object can be any type of object that you want to estimate, allocate costs to, or measure directly.</span></span> <span data-ttu-id="2ed88-110">Les objets de coût comprennent les produits, les projets, les ressources, les services, les centres de coût, et les zones géographiques.</span><span class="sxs-lookup"><span data-stu-id="2ed88-110">Typical cost objects include products, projects, resources, departments, cost centers, and geographical regions.</span></span> <span data-ttu-id="2ed88-111">La gestion utilise les objets de coût pour mesurer les coûts, mais aussi pour réaliser l'analyse de rentabilité.</span><span class="sxs-lookup"><span data-stu-id="2ed88-111">Management uses cost objects to quantify costs and also to drive profitability analysis.</span></span>

## <a name="cost-object-dimensions-and-cost-object-dimension-members"></a><span data-ttu-id="2ed88-112">Dimensions d'objet de coût, et membres de la dimension d'objet de coût</span><span class="sxs-lookup"><span data-stu-id="2ed88-112">Cost object dimensions and cost object dimension members</span></span>
<span data-ttu-id="2ed88-113">Les objets de coût sont appelés *dimensions d'objet de coût*.</span><span class="sxs-lookup"><span data-stu-id="2ed88-113">Cost objects are known as *cost object dimensions*.</span></span> <span data-ttu-id="2ed88-114">Une fois que vous avez décidé à quelle l'entité la dimension d'objets de coût doit faire référence, vous devez spécifier les valeurs de dimension individuelle ou les importer dans le contrôle de gestion depuis d'autres systèmes sources.</span><span class="sxs-lookup"><span data-stu-id="2ed88-114">After you’ve decided which entity the cost object dimension should refer to, you must specify the individual dimension values or import them into Cost accounting from other source systems.</span></span> <span data-ttu-id="2ed88-115">Ces valeurs de dimension individuelle sont appelées *membres de la dimension d'objet de coût*.</span><span class="sxs-lookup"><span data-stu-id="2ed88-115">These individual dimension values are known as *cost object dimension members*.</span></span> <span data-ttu-id="2ed88-116">Par exemple, vous souhaitez utiliser la dimension financière qui est nommée Centre de coût comme dimension d'objet de coût.</span><span class="sxs-lookup"><span data-stu-id="2ed88-116">For example, you want to use the financial dimension that is named Cost center as the cost object dimension.</span></span> <span data-ttu-id="2ed88-117">Pour voir comment le flux des coûts vers les différents centres de coût, vous devez importer les membres de la dimension d'objet de coût.</span><span class="sxs-lookup"><span data-stu-id="2ed88-117">To see how costs flow to the individual cost centers, you must import the cost object dimension members.</span></span> <span data-ttu-id="2ed88-118">Dans ce cas, les membres de la dimension d'objet de coût sont les centres de coût réels, tels que les Ventes, la Production, l'Administration, et les Emplacements géographiques.</span><span class="sxs-lookup"><span data-stu-id="2ed88-118">In this case, the cost object dimension members are the actual cost centers, such as Sales, Production, Administration, and Geographic locations.</span></span> <span data-ttu-id="2ed88-119">La capture d'écran suivante illustre un exemple de Centres de coûts comme dimension d'objet de coût avec ses centres de coûts réels comme membres de la dimension d'objet de coût.</span><span class="sxs-lookup"><span data-stu-id="2ed88-119">The following screenshot shows an example of Cost Centers as the cost object dimension with its actual cost centers as cost object dimension members.</span></span> 

<span data-ttu-id="2ed88-120">[![cost-object-dimensions](./media/cost-object-dimensions.png)](./media/cost-object-dimensions.png)</span><span class="sxs-lookup"><span data-stu-id="2ed88-120">[![cost-object-dimensions](./media/cost-object-dimensions.png)](./media/cost-object-dimensions.png)</span></span>

## <a name="import-cost-object-dimension-members-through-data-connectors"></a><span data-ttu-id="2ed88-121">Importer les membres de la dimension d'objet de coût à l'aide de connecteurs de données</span><span class="sxs-lookup"><span data-stu-id="2ed88-121">Import cost object dimension members through data connectors</span></span>
<span data-ttu-id="2ed88-122">Pour faciliter l'importation de membres de dimension d'objet de coût, vous utilisez des connecteurs de données pour récupérer les valeurs des entités à utiliser en tant que dimensions de coût d'objet.</span><span class="sxs-lookup"><span data-stu-id="2ed88-122">To make the import of cost object dimension members easier, you use data connectors to retrieve the values from the entities that you want to use as cost object dimensions.</span></span> <span data-ttu-id="2ed88-123">Vous pouvez utiliser des connecteurs de données préconçus ou des personnalisés que vous créez.</span><span class="sxs-lookup"><span data-stu-id="2ed88-123">You can use either the pre-built data connectors or custom data connectors that you build.</span></span>



