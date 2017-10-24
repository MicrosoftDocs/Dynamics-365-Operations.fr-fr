---
title: "Déclaration de fin des ordres de fabrication"
description: "La déclaration de fin correspond à un stade de production. À ce stade, un produit fini est signalé et passé de l'ordre de fabrication au stock."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdJournalTransJob, ProdJournalTransProd, ProdJournalTransRoute, ProdParmReportFinished, ProdRouteOprOverview
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 27061
ms.assetid: 1c2dfc54-a293-49f2-9b96-5a912ac5762c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f8adcbcc2157058151c26179eb2eb925b0092d2d
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="report-production-orders-as-finished"></a><span data-ttu-id="df960-104">Déclaration de fin des ordres de fabrication</span><span class="sxs-lookup"><span data-stu-id="df960-104">Report production orders as finished</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="df960-105">La déclaration de fin correspond à un stade de production.</span><span class="sxs-lookup"><span data-stu-id="df960-105">Report as finished is a production stage.</span></span> <span data-ttu-id="df960-106">À ce stade, un produit fini est signalé et passé de l'ordre de fabrication au stock.</span><span class="sxs-lookup"><span data-stu-id="df960-106">At this stage, a finished product is reported and moved from the production order to the inventory.</span></span>

<span data-ttu-id="df960-107">Lorsqu'un ordre de fabrication est déclaré terminé, la quantité des produits finis déclarés terminés est mise à jour comme disponible dans le stock.</span><span class="sxs-lookup"><span data-stu-id="df960-107">When a quantity of the finished goods is reported as finished on a production order it is updated as on-hand in the inventory.</span></span> <span data-ttu-id="df960-108">Des quantités partielles de la quantité de l'ordre prévisionnel peuvent être déclarées terminées.</span><span class="sxs-lookup"><span data-stu-id="df960-108">Partial quantities of the originally planned order quantity can be reported as finished.</span></span> <span data-ttu-id="df960-109">Il est également possible de déclarer terminées les quantités d'erreur avec un motif d'erreur associé.</span><span class="sxs-lookup"><span data-stu-id="df960-109">It is also possible to report error quantities with an associated error reason when reporting quantities as finished.</span></span> <span data-ttu-id="df960-110">Lorsque l'ordre de fabrication atteint le stade Déclaré terminé, cela indique qu'aucune quantité supplémentaire ne sera déclarée à l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="df960-110">When the production order reach the stage Reported as finished it indicates that no more quantity is going to be reported at the production  order.</span></span>
<span data-ttu-id="df960-111">Les caractéristiques suivantes sont également associées au processus de **Déclaration de fin** :</span><span class="sxs-lookup"><span data-stu-id="df960-111">The following characteristics are also associated with the **Report as finished** process:</span></span>
-   <span data-ttu-id="df960-112">Il est possible de paramétrer la consommation des matières premières et du temps proportionnelles à la quantité déclarée (post-consommation)</span><span class="sxs-lookup"><span data-stu-id="df960-112">It is possible to set up consumption of raw material and time that are proportional to the reported quantity (back-flushing)</span></span>
-   <span data-ttu-id="df960-113">Le travail de rangement peut être généré pour les articles activés pour les processus de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="df960-113">Put-away work can be generated for items that are enabled for warehouse processes.</span></span>
-   <span data-ttu-id="df960-114">La valeur du coût standard ou prévisionnel des produits finis peut être paramétrée pour être déclarée aux comptes généraux.</span><span class="sxs-lookup"><span data-stu-id="df960-114">The planned or standard cost value of the finished goods can be set up to be reported to ledger accounts.</span></span>
-   <span data-ttu-id="df960-115">Un ordre de qualité peut être créé pour la quantité déclarée selon la configuration d'une association de qualité.</span><span class="sxs-lookup"><span data-stu-id="df960-115">A quality order can be created for the reported quantity based on the setup of a quality association.</span></span>

<span data-ttu-id="df960-116">La quantité est déclarée à l'emplacement de sortie.</span><span class="sxs-lookup"><span data-stu-id="df960-116">The quantity is reported to the output location.</span></span> <span data-ttu-id="df960-117">Le travail d'entrepôt est alors généré pour déplacer la quantité depuis l'emplacement de sortie vers sa destination finale définie par la directive d'emplacement pour le travail de rangement.</span><span class="sxs-lookup"><span data-stu-id="df960-117">Warehouse work is then generated to move the quantity from the output location to its final destination defined by the location directive for the put-away work.</span></span>

-   <span data-ttu-id="df960-118">Un ordre de qualité peut être créé lorsqu'un ordre de fabrication est déclaré terminé si une association de qualité a été paramétrée.</span><span class="sxs-lookup"><span data-stu-id="df960-118">A quality order can be created when a production order is reported as finished if a quality association has been set up.</span></span>

## <a name="set-a-production-order-to-reporting-as-finished"></a><span data-ttu-id="df960-119">Définir un ordre de fabrication sur Déclaration de fin</span><span class="sxs-lookup"><span data-stu-id="df960-119">Set a production order to Reporting as finished</span></span>
<span data-ttu-id="df960-120">Vous pouvez définir un ordre de fabrication sur **Déclaration de fini** via la fonction standard de mise à jour de l'ordre de fabrication ou via les journaux de gammes et de bons de travail, ou encore via le journal des **déclarations de fin**.</span><span class="sxs-lookup"><span data-stu-id="df960-120">You can set a production order to **Report as finished** through the standard production order update function, or through the route and job card journals, or through the journal **Report as finished**.</span></span> <span data-ttu-id="df960-121">Vous pouvez également mettre à jour le stade **Déclaration de fin** via les pages Terminal des bons de travail et Périphérique pour le bon de travail lorsque vous faites une déclaration concernant la dernière tâche de l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="df960-121">You can also update the stage to **Report as finished** through the job card terminal and job card device pages, when you report on the last job of the production order.</span></span> <span data-ttu-id="df960-122">Enfin, vous pouvez activer l'option **Déclaration de fin** comme processus pour la solution de l'appareil portable d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="df960-122">Finally, you can enable the **Report as finished** option as a process for the handheld warehouse device solution.</span></span>  




