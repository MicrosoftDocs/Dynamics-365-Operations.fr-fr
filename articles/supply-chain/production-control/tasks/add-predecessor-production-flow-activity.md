---
title: Ajouter un prédécesseur à une activité de flux de production
description: Dans une version de flux de production, toutes les activités doivent être séquencées.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d76ec6ac928228011f42355bebd553576bcfd275
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5255443"
---
# <a name="add-a-predecessor-to-a-production-flow-activity"></a><span data-ttu-id="91cc3-103">Ajouter un prédécesseur à une activité de flux de production</span><span class="sxs-lookup"><span data-stu-id="91cc3-103">Add a predecessor to a production flow activity</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="91cc3-104">Dans une version de flux de production, toutes les activités doivent être séquencées.</span><span class="sxs-lookup"><span data-stu-id="91cc3-104">In a production flow version, all activities must be sequenced.</span></span> <span data-ttu-id="91cc3-105">Une activité peut avoir un ou plusieurs prédécesseurs ou successeurs.</span><span class="sxs-lookup"><span data-stu-id="91cc3-105">An activity can have one or multiple predecessors or successors.</span></span> 

<span data-ttu-id="91cc3-106">Cette procédure indique comment associer un prédécesseur à une activité.</span><span class="sxs-lookup"><span data-stu-id="91cc3-106">This procedure shows how to associate a predecessor to an activity.</span></span> 

<span data-ttu-id="91cc3-107">Pour exécuter cette tâche, vous devez disposer d’un flux de production en version brouillon avec au moins deux activités pouvant être connectées.</span><span class="sxs-lookup"><span data-stu-id="91cc3-107">To perform this task, you need a production flow that has the Draft version with at least two activities that can be connected.</span></span> 

<span data-ttu-id="91cc3-108">Pour en savoir plus, lisez le livre blanc « Production flows and activities in lean manufacturing (Flux et activités de production liés au lean manufacturing) ».</span><span class="sxs-lookup"><span data-stu-id="91cc3-108">To learn more, read the white paper "Production flows and activities in lean manufacturing."</span></span>


## <a name="find-the-production-flow-and-version"></a><span data-ttu-id="91cc3-109">Rechercher la version et le flux de production</span><span class="sxs-lookup"><span data-stu-id="91cc3-109">Find the production flow and version</span></span>
1. <span data-ttu-id="91cc3-110">Accédez à Contrôle de la production > Paramétrage > Flux de production lean > Flux de production.</span><span class="sxs-lookup"><span data-stu-id="91cc3-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="91cc3-111">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="91cc3-111">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="91cc3-112">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="91cc3-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="91cc3-113">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="91cc3-113">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="91cc3-114">Cliquez sur Activités.</span><span class="sxs-lookup"><span data-stu-id="91cc3-114">Click Activities.</span></span>

## <a name="select-an-activity-and-add-a-predecessor"></a><span data-ttu-id="91cc3-115">Sélectionner une activité et ajouter un prédécesseur</span><span class="sxs-lookup"><span data-stu-id="91cc3-115">Select an activity and add a predecessor</span></span>
1. <span data-ttu-id="91cc3-116">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="91cc3-116">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="91cc3-117">Cliquez sur Ajouter un prédécesseur.</span><span class="sxs-lookup"><span data-stu-id="91cc3-117">Click Add predecessor.</span></span>
3. <span data-ttu-id="91cc3-118">Dans le champ Activité, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="91cc3-118">In the Activity field, enter or select a value.</span></span>
4. <span data-ttu-id="91cc3-119">Entrez un nombre dans le champ Ratio de durée de cycle.</span><span class="sxs-lookup"><span data-stu-id="91cc3-119">In the Cycle time ratio field, enter a number.</span></span>
    * <span data-ttu-id="91cc3-120">Le ratio de durée de cycle par défaut d’une relation d’activité est 1.</span><span class="sxs-lookup"><span data-stu-id="91cc3-120">The default cycle time ratio of an activity relation is 1.</span></span> <span data-ttu-id="91cc3-121">Cela suppose que les deux activités s’exécutent au même rythme ou takt time.</span><span class="sxs-lookup"><span data-stu-id="91cc3-121">This assumes that both activities run at the same pace or takt time.</span></span> <span data-ttu-id="91cc3-122">Si un prédécesseur s’exécute à un rythme plus élevé (takt time inférieur), le ratio peut être inférieur à 1, si le prédécesseur s’exécute à un rythme plus lent (takt time supérieur), le ratio de durée de cycle est supérieur à 1.</span><span class="sxs-lookup"><span data-stu-id="91cc3-122">If the predecessor runs at a higher pace (lower takt time), the ratio should be lower than 1, if the predecessor runs at a slower pace (higher takt time) the cycle time ratio is greater than 1.</span></span>  
5. <span data-ttu-id="91cc3-123">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="91cc3-123">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]