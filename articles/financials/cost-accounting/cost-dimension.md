---
title: "Créer des dimensions et importer des membres de la dimension"
description: "Le Contrôle de gestion est un module indépendant qui nécessite les données principales d'autres modules."
author: YuyuScheller
manager: AnnBe
ms.date: 09/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 256254
ms.assetid: e1b0a6e3-0c72-4a7d-90e1-20f870c6dbad
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: a3726f7de1679fa3aaeda43a55b9ca14895f5ac4
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="create-dimensions-and-import-dimension-members"></a><span data-ttu-id="a4b0a-103">Créer des dimensions et importer des membres de la dimension</span><span class="sxs-lookup"><span data-stu-id="a4b0a-103">Create dimensions and import dimension members</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a4b0a-104">Le Contrôle de gestion est un module indépendant qui nécessite les données d'autres modules.</span><span class="sxs-lookup"><span data-stu-id="a4b0a-104">Cost accounting is an independent module that requires data from other modules.</span></span> <span data-ttu-id="a4b0a-105">Ces données sont classées par catégorie comme suit :</span><span class="sxs-lookup"><span data-stu-id="a4b0a-105">This data is categorized into the following:</span></span>

-  <span data-ttu-id="a4b0a-106">Éléments de coût</span><span class="sxs-lookup"><span data-stu-id="a4b0a-106">Cost elements</span></span>
-  <span data-ttu-id="a4b0a-107">Objets de coût</span><span class="sxs-lookup"><span data-stu-id="a4b0a-107">Cost objects</span></span>
-  <span data-ttu-id="a4b0a-108">Dimensions statistiques</span><span class="sxs-lookup"><span data-stu-id="a4b0a-108">Statistical dimensions</span></span>

<span data-ttu-id="a4b0a-109">Un **élément de coût** correspond à un article dont le coût est pertinent dans le plan de comptes.</span><span class="sxs-lookup"><span data-stu-id="a4b0a-109">A **Cost element** corresponds to a cost-relevant item in the chart of accounts.</span></span> <span data-ttu-id="a4b0a-110">Un **objet de coût** correspond à tout type de dimension financière, comme les produits, les centres de coût et les projets que vous voulez estimer, auxquels vous voulez affecter des coûts, ou que vous voulez mesurer directement.</span><span class="sxs-lookup"><span data-stu-id="a4b0a-110">A **Cost object** corresponds to any type of financial dimension, such as products, cost centers, and projects that you want to estimate, allocate costs to, or measure directly.</span></span> <span data-ttu-id="a4b0a-111">Une **dimension statistique** et ses membres permettent d'enregistrer les entrées non monétaires.</span><span class="sxs-lookup"><span data-stu-id="a4b0a-111">A **Statistical dimension** and its members are used to register non-monetary entries.</span></span> <span data-ttu-id="a4b0a-112">Les membres de la dimension statistique peuvent être utilisés comme base de répartition pour la distribution et la répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="a4b0a-112">Statistical dimension members can be used as an allocation base in cost distribution and allocation</span></span> 

<span data-ttu-id="a4b0a-113">Le diagramme suivant illustre les dimensions utilisées dans le Contrôle de gestion.</span><span class="sxs-lookup"><span data-stu-id="a4b0a-113">The following diagram illustrates the dimensions that are used in Cost accounting.</span></span>

<span data-ttu-id="a4b0a-114">[![Dimensions de Contrôle de gestion](./media/cost-eos-dimensions.png)](./media/cost-eos-dimensions.png)</span><span class="sxs-lookup"><span data-stu-id="a4b0a-114">[![Cost accounting dimensions](./media/cost-eos-dimensions.png)](./media/cost-eos-dimensions.png)</span></span>

<span data-ttu-id="a4b0a-115">Une fois que les données sont importées dans le Contrôle de gestion, vous pouvez l'utiliser pour créer les différentes perspectives qui fournissent des analyses aux responsables à tous les niveaux de l'organisation.</span><span class="sxs-lookup"><span data-stu-id="a4b0a-115">After the data is imported into Cost accounting, you can use it to build various perspectives that provide insights to managers at all levels of the organization.</span></span> <span data-ttu-id="a4b0a-116">Les rubriques suivantes fournissent des informations sur la création des dimensions et l'importation des membres de la dimension.</span><span class="sxs-lookup"><span data-stu-id="a4b0a-116">The following topics provide information about creating dimensions and importing dimension members.</span></span> 

-  [<span data-ttu-id="a4b0a-117">Dimensions d'éléments de coût</span><span class="sxs-lookup"><span data-stu-id="a4b0a-117">Cost element dimensions</span></span>](cost-elements.md)
-  [<span data-ttu-id="a4b0a-118">Créer des éléments de coût (guide de tâche)</span><span class="sxs-lookup"><span data-stu-id="a4b0a-118">Create cost elements (Task guide)</span></span>](./tasks/create-cost-elements.md)
-  [<span data-ttu-id="a4b0a-119">Dimensions d'objets de coût</span><span class="sxs-lookup"><span data-stu-id="a4b0a-119">Cost object dimensions</span></span>](cost-objects.md)
-  [<span data-ttu-id="a4b0a-120">Créer des éléments de coût (guide de tâche)</span><span class="sxs-lookup"><span data-stu-id="a4b0a-120">Create cost elements (Task guide)</span></span>](./tasks/create-cost-objects.md)
-  [<span data-ttu-id="a4b0a-121">Mappage de membres de dimension d'élément de coût à un ensemble commun de membres de dimension</span><span class="sxs-lookup"><span data-stu-id="a4b0a-121">Map cost element dimension members to a common set of dimension members</span></span>](map-cost-elements-dimension-members.md)
-  [<span data-ttu-id="a4b0a-122">Mapper une dimension d'élément de coût (guide de tâche)</span><span class="sxs-lookup"><span data-stu-id="a4b0a-122">Map a cost element dimension (Task guide)</span></span>](./tasks/map-cost-element-dimension.md)
-  [<span data-ttu-id="a4b0a-123">Membres de la dimension statistique et modèles de fournisseur de mesures statistiques</span><span class="sxs-lookup"><span data-stu-id="a4b0a-123">Statistical dimension members and statistical measure provider templates</span></span>](statistical-measure-provider-template.md)







