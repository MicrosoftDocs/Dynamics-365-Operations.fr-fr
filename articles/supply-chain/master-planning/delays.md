---
title: Retards
description: "Cet article fournit des informations sur les dates retardées de la planification. Une date retardée est une date d'échéance réaliste attribuée à une transaction si la date d'exécution la plus proche calculée par la planification est postérieure à la date demandée."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: a87b19732f413aa2844101f76dea83535da86599
ms.contentlocale: fr-fr
ms.lasthandoff: 08/07/2018

---

# <a name="delays"></a><span data-ttu-id="a980e-104">Retards</span><span class="sxs-lookup"><span data-stu-id="a980e-104">Delays</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a980e-105">Cet article fournit des informations sur les dates retardées de la planification.</span><span class="sxs-lookup"><span data-stu-id="a980e-105">This article provides information about delayed dates in master planning.</span></span> <span data-ttu-id="a980e-106">Une date retardée est une date d'échéance réaliste attribuée à une transaction si la date d'exécution la plus proche calculée par la planification est postérieure à la date demandée.</span><span class="sxs-lookup"><span data-stu-id="a980e-106">A delayed date is a realistic due date that a transaction receives if the earliest fulfillment date that master planning calculates is later than the requested date.</span></span>

<span data-ttu-id="a980e-107">La planification peut calculer la date d'exécution la plus proche pour une transaction, en fonction des délais, de la disponibilité des matières, de la disponibilité de la capacité et de divers paramètres de planification.</span><span class="sxs-lookup"><span data-stu-id="a980e-107">Master planning can calculate the earliest fulfillment date for a transaction, based on lead times, material availability, capacity availability, and various planning parameters.</span></span> 

<span data-ttu-id="a980e-108">Si la planification calcule une date de commande qui précède la date du jour, la commande ne peut pas être exécutée à temps.</span><span class="sxs-lookup"><span data-stu-id="a980e-108">If master planning calculates an order date that precedes the current date, the order can't be fulfilled on time.</span></span> <span data-ttu-id="a980e-109">Par conséquent, la commande est retardée.</span><span class="sxs-lookup"><span data-stu-id="a980e-109">Therefore, the order is delayed.</span></span> <span data-ttu-id="a980e-110">Dans ce cas, la planification jalonne la commande en aval à partir de la date actuelle et inclut des délais.</span><span class="sxs-lookup"><span data-stu-id="a980e-110">In this case, master planning forward-plans the order from the current date and includes lead times.</span></span> <span data-ttu-id="a980e-111">Ces délais débutent avec chaque composant de niveau inférieur.</span><span class="sxs-lookup"><span data-stu-id="a980e-111">These lead times start with any lower-level component items.</span></span> <span data-ttu-id="a980e-112">La commande reçoit ensuite une date différée.</span><span class="sxs-lookup"><span data-stu-id="a980e-112">The order then receives a delayed date.</span></span> <span data-ttu-id="a980e-113">Une date différée est une date d'échéance réaliste basée sur les données actuelles.</span><span class="sxs-lookup"><span data-stu-id="a980e-113">A delayed date is a realistic due date, based on the current data.</span></span> <span data-ttu-id="a980e-114">La planification calcule également le nombre de jours de retard.</span><span class="sxs-lookup"><span data-stu-id="a980e-114">Master planning also calculates the number of delay days.</span></span> 

<span data-ttu-id="a980e-115">Dans certains cas, vous pouvez choisir de ne pas calculer les retards, par exemple lorsque les utilisateurs savent qu'ils peuvent accélérer les délais en sélectionnant d'autres modes de livraison.</span><span class="sxs-lookup"><span data-stu-id="a980e-115">In some situations, you might choose not to calculate delays, such as when users know that they can expedite lead times by selecting alternative modes of delivery.</span></span> 

<span data-ttu-id="a980e-116">Vous pouvez configurer la manière dont les retards sont calculés pour un groupe de couverture.</span><span class="sxs-lookup"><span data-stu-id="a980e-116">You can configure how delays are calculated for a coverage group.</span></span> <span data-ttu-id="a980e-117">Vous pouvez ensuite lier le groupe de couverture à un article ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="a980e-117">You can then attach the coverage group to an item later.</span></span> 

<span data-ttu-id="a980e-118">Dans la page **Paramètres de planification**, vous pouvez définir l'heure de début pour le calcul des retards.</span><span class="sxs-lookup"><span data-stu-id="a980e-118">On the **Master planning parameters** page, you can set the start time for the calculation of delays.</span></span> <span data-ttu-id="a980e-119">Si une commande est exécutée après cette heure, un retard d'une journée est ajouté à la date de retard de la commande.</span><span class="sxs-lookup"><span data-stu-id="a980e-119">If an order is fulfilled after this time, a delay of one day is added to the delay date of the order.</span></span> 

<span data-ttu-id="a980e-120">**Remarque :** Dans les versions précédentes, les retards calculés étaient appelés *messages de perspectives*, la date différée était appelée *date au plus tôt*, et une transaction différée était appelée *transaction définie dans le futur*.</span><span class="sxs-lookup"><span data-stu-id="a980e-120">**Note:** In earlier versions, calculated delays were known as *futures messages*, the delayed date was known as the *futures date*, and a delayed transaction was referred to as *a transaction that was future set*.</span></span>

<a name="additional-resources"></a><span data-ttu-id="a980e-121">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="a980e-121">Additional resources</span></span>
--------

[<span data-ttu-id="a980e-122">Paramètres de couverture</span><span class="sxs-lookup"><span data-stu-id="a980e-122">Coverage settings</span></span>](coverage-settings.md)




