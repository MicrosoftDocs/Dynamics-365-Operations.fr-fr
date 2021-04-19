---
title: Retards
description: Cette rubrique fournit des informations sur les dates retardées de la planification. Une date retardée est une date d’échéance réaliste attribuée à une transaction si la date d’exécution la plus proche calculée par la planification est postérieure à la date demandée.
author: roxanadiaconu
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4216ed1d9b981eee94cfd4c621abd1da99111512
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813673"
---
# <a name="delays"></a><span data-ttu-id="783d3-104">Retards</span><span class="sxs-lookup"><span data-stu-id="783d3-104">Delays</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="783d3-105">Cette rubrique fournit des informations sur les dates retardées de la planification.</span><span class="sxs-lookup"><span data-stu-id="783d3-105">This topic provides information about delayed dates in master planning.</span></span> <span data-ttu-id="783d3-106">Une date retardée est une date d’échéance réaliste attribuée à une transaction si la date d’exécution la plus proche calculée par la planification est postérieure à la date demandée.</span><span class="sxs-lookup"><span data-stu-id="783d3-106">A delayed date is a realistic due date that a transaction receives if the earliest fulfillment date that master planning calculates is later than the requested date.</span></span>

<span data-ttu-id="783d3-107">La planification peut calculer la date d’exécution la plus proche pour une transaction, en fonction des délais, de la disponibilité des matières, de la disponibilité de la capacité et de divers paramètres de planification.</span><span class="sxs-lookup"><span data-stu-id="783d3-107">Master planning can calculate the earliest fulfillment date for a transaction, based on lead times, material availability, capacity availability, and various planning parameters.</span></span> 

<span data-ttu-id="783d3-108">Si la planification calcule une date de commande qui précède la date du jour, la commande ne peut pas être exécutée à temps.</span><span class="sxs-lookup"><span data-stu-id="783d3-108">If master planning calculates an order date that precedes the current date, the order can't be fulfilled on time.</span></span> <span data-ttu-id="783d3-109">Par conséquent, la commande est retardée.</span><span class="sxs-lookup"><span data-stu-id="783d3-109">Therefore, the order is delayed.</span></span> <span data-ttu-id="783d3-110">Dans ce cas, la planification jalonne la commande en aval à partir de la date actuelle et inclut des délais.</span><span class="sxs-lookup"><span data-stu-id="783d3-110">In this case, master planning forward-plans the order from the current date and includes lead times.</span></span> <span data-ttu-id="783d3-111">Ces délais débutent avec chaque composant de niveau inférieur.</span><span class="sxs-lookup"><span data-stu-id="783d3-111">These lead times start with any lower-level component items.</span></span> <span data-ttu-id="783d3-112">La commande reçoit ensuite une date différée.</span><span class="sxs-lookup"><span data-stu-id="783d3-112">The order then receives a delayed date.</span></span> <span data-ttu-id="783d3-113">Une date différée est une date d’échéance réaliste basée sur les données actuelles.</span><span class="sxs-lookup"><span data-stu-id="783d3-113">A delayed date is a realistic due date, based on the current data.</span></span> <span data-ttu-id="783d3-114">La planification calcule également le nombre de jours de retard.</span><span class="sxs-lookup"><span data-stu-id="783d3-114">Master planning also calculates the number of delay days.</span></span> 

<span data-ttu-id="783d3-115">Dans certains cas, vous pouvez choisir de ne pas calculer les retards, par exemple lorsque les utilisateurs savent qu’ils peuvent accélérer les délais en sélectionnant d’autres modes de livraison.</span><span class="sxs-lookup"><span data-stu-id="783d3-115">In some situations, you might choose not to calculate delays, such as when users know that they can expedite lead times by selecting alternative modes of delivery.</span></span> 

<span data-ttu-id="783d3-116">Vous pouvez configurer la manière dont les retards sont calculés pour un groupe de couverture.</span><span class="sxs-lookup"><span data-stu-id="783d3-116">You can configure how delays are calculated for a coverage group.</span></span> <span data-ttu-id="783d3-117">Vous pouvez ensuite lier le groupe de couverture à un article ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="783d3-117">You can then attach the coverage group to an item later.</span></span> 

<span data-ttu-id="783d3-118">Dans la page **Paramètres de planification**, vous pouvez définir l’heure de début pour le calcul des retards.</span><span class="sxs-lookup"><span data-stu-id="783d3-118">On the **Master planning parameters** page, you can set the start time for the calculation of delays.</span></span> <span data-ttu-id="783d3-119">Si une commande est exécutée après cette heure, un retard d’une journée est ajouté à la date de retard de la commande.</span><span class="sxs-lookup"><span data-stu-id="783d3-119">If an order is fulfilled after this time, a delay of one day is added to the delay date of the order.</span></span> 

> [!NOTE]
> <span data-ttu-id="783d3-120">Dans les versions précédentes, les retards calculés étaient appelés *messages de perspectives*, la date différée était appelée *date au plus tôt*, et une transaction différée était appelée *transaction définie dans le futur*.</span><span class="sxs-lookup"><span data-stu-id="783d3-120">In earlier versions, calculated delays were known as *futures messages*, the delayed date was known as the *futures date*, and a delayed transaction was referred to as *a transaction that was future set*.</span></span>

## <a name="limited-delays-in-production-setup-with-multiple-bom-levels"></a><span data-ttu-id="783d3-121">Retards limités à la configuration de la production avec plusieurs niveaux de nomenclature</span><span class="sxs-lookup"><span data-stu-id="783d3-121">Limited delays in production setup with multiple BOM levels</span></span>
<span data-ttu-id="783d3-122">Lorsque vous travaillez avec des retards dans une configuration de production avec plusieurs niveaux de nomenclature, il est important de noter que seuls les articles directement au-dessus de l’article (dans la structure de nomenclature) provoquant le retard, seront mis à jour avec un retard dans le cadre de l’exécution de la planification principale.</span><span class="sxs-lookup"><span data-stu-id="783d3-122">When you work with delays in a production setup that has multiple BOM levels, it is important to note that only the items directly above the item (in the BOM structure) causing the delay, will be updated with a delay as part of the master planning run.</span></span> <span data-ttu-id="783d3-123">Le retard ne sera pas appliqué aux autres articles de la structure de la nomenclature tant que la première exécution de la planification principale n’est pas terminée, une fois l’ordre planifié pour le niveau supérieur approuvé ou confirmé.</span><span class="sxs-lookup"><span data-stu-id="783d3-123">Other items in the BOM structure will not get the delay applied until the first master planning run, when the planned order for the top level is approved or firmed.</span></span> 

<span data-ttu-id="783d3-124">Pour contourner cette limitation connue, les ordres de fabrication en haut de la structure de la nomenclature avec des retards peuvent être approuvés (ou confirmés) avant la prochaine exécution de la planification principale.</span><span class="sxs-lookup"><span data-stu-id="783d3-124">To work around this known limitation, the production orders on the top of the BOM structure with delays can be approved (or firmed) prior to the next master planning run.</span></span> <span data-ttu-id="783d3-125">De cette façon, le retard par rapport à l’ordre de fabrication prévisionnel approuvé retardé sera conservé et tous les composants sous-jacents seront mis à jour en conséquence.</span><span class="sxs-lookup"><span data-stu-id="783d3-125">This way the delay from the delayed approved planned production order will be kept and all underlying components will be updated accordingly.</span></span>
<span data-ttu-id="783d3-126">Les messages d’action peuvent être également utilisés pour identifier les ordres planifiés qui peuvent être déplacés à une date ultérieure, en raison d’autres retards dans la structure de la nomenclature.</span><span class="sxs-lookup"><span data-stu-id="783d3-126">Action messages can also be used to identify planned orders that can be moved to a later date, due to other delays in the BOM structure.</span></span>

## <a name="desired-date"></a><span data-ttu-id="783d3-127">Date souhaitée</span><span class="sxs-lookup"><span data-stu-id="783d3-127">Desired date</span></span>

<span data-ttu-id="783d3-128">Dans la page **Ordre prévisionnel**, sous l’onglet **Retards**, se trouve la **Date souhaitée** pour l’ordre prévisionnel.</span><span class="sxs-lookup"><span data-stu-id="783d3-128">On the **Planned order** page, under the **Delays** tab is the **Desired date** for the planned order.</span></span> <span data-ttu-id="783d3-129">La date souhaitée d’un ordre prévisionnel est la date de référence pour les retards, qui est une date calculée équivalente à la **Date demandée** calculée à partir des **Besoins nets**.</span><span class="sxs-lookup"><span data-stu-id="783d3-129">The desired date of a planned order is the base date for delays, which is a computed date that equals the **Requested date** calculated from the **Net Requirement**.</span></span> <span data-ttu-id="783d3-130">Si l’ordre prévisionnel est une ligne de nomenclature, une ligne de production ou une ligne de kanban, la date souhaitée est basée sur la **Date de besoin** et la date souhaitée ne s’affiche pas dans la page **Ordre prévisionnel**.</span><span class="sxs-lookup"><span data-stu-id="783d3-130">If the planned order is a BOM line, production line or kanban line, the desired date is based on the **Requirement date** and the desired date will not be shown on the **Planned order** page.</span></span>

<a name="additional-resources"></a><span data-ttu-id="783d3-131">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="783d3-131">Additional resources</span></span>
--------

[<span data-ttu-id="783d3-132">Paramètres de couverture</span><span class="sxs-lookup"><span data-stu-id="783d3-132">Coverage settings</span></span>](coverage-settings.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]