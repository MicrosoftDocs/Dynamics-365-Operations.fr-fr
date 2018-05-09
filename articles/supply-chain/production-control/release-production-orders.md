---
title: Lancement des ordres de fabrication
description: "Un ordre de fabrication lancé est une commande qui a été autorisée pour la production. Le terme Lancé permet de décrire un état du cycle de vie de l'ordre de fabrication où l'ordre de fabrication est disponible pour l'exécution dans l'atelier de production et pour les processus d'entrepôt."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdParmRelease
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 2414
ms.assetid: 50c2257b-2924-44f5-b7c1-11f498092053
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: e0e7f3747980ff2fb5d055c9496167888e067f8d
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="release-production-orders"></a><span data-ttu-id="4fbb6-104">Lancement des ordres de fabrication</span><span class="sxs-lookup"><span data-stu-id="4fbb6-104">Release production orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4fbb6-105">Un ordre de fabrication lancé est une commande qui a été autorisée pour la production.</span><span class="sxs-lookup"><span data-stu-id="4fbb6-105">A released production order is an order that has been authorized for production.</span></span> <span data-ttu-id="4fbb6-106">Le terme Lancé permet de décrire un état du cycle de vie de l'ordre de fabrication où l'ordre de fabrication est disponible pour l'exécution dans l'atelier de production et pour les processus d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="4fbb6-106">The term Released is used to describe a state in the production order life cycle, where the production order is available for execution on the production shop floor and for warehouse processes.</span></span> 

<a name="characteristics-of-the-released-state"></a><span data-ttu-id="4fbb6-107">Caractéristiques de l'état Lancé</span><span class="sxs-lookup"><span data-stu-id="4fbb6-107">Characteristics of the Released state</span></span>
-------------------------------------

<span data-ttu-id="4fbb6-108">L'état **Lancé** est un état du cycle de vie de l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="4fbb6-108">The **Released** state is one state in the production order life cycle.</span></span> <span data-ttu-id="4fbb6-109">Les ordres de fabrication dont l'état est **Lancé** sont disponibles pour exécution dans l'atelier de production et pour les processus de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="4fbb6-109">Production orders that are in the **Released** state are available for execution on the production shop floor and for warehouse processes.</span></span> <span data-ttu-id="4fbb6-110">L'état **Lancé** a les caractéristiques suivantes :</span><span class="sxs-lookup"><span data-stu-id="4fbb6-110">The **Released** state has the following characteristics:</span></span>

-   <span data-ttu-id="4fbb6-111">Un ordre de fabrication peut passer à l'état **Lancé** à partir de l'ordre de fabrication ou à l'aide d'un processus de traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="4fbb6-111">A production order can be changed to the **Released** state either from the production order or by using a batch process.</span></span> <span data-ttu-id="4fbb6-112">L'ordre de fabrication peut être également mis à jour automatiquement à partir des ordres de fabrication prévisionnels qui sont confirmés à l'aide du champ **Plage de gestion de la confirmation** sur la page **Plan général**.</span><span class="sxs-lookup"><span data-stu-id="4fbb6-112">The production order can also be updated automatically from planned production orders that are firmed by using the **Firming time fence** field on the **Master plan** page.</span></span>
-   <span data-ttu-id="4fbb6-113">L'état **Lancé**est le signal pour les opérateurs de l'atelier (opérateurs) afin de démarrer l'exécution des tâches de production dans l'atelier.</span><span class="sxs-lookup"><span data-stu-id="4fbb6-113">The **Released** state is the signal for the shop floor operators (operators) to start executing the production jobs on the shop floor.</span></span>
-   <span data-ttu-id="4fbb6-114">Les documents de production tels que les fiches production, les tâches de gamme et les bons de travail offrent les informations relatives aux tâches de production et peuvent être publiés.</span><span class="sxs-lookup"><span data-stu-id="4fbb6-114">Production papers, such as route cards, route jobs, and jobs cards provide information about production jobs and can be issued.</span></span>
-   <span data-ttu-id="4fbb6-115">Pour les matières réservées physiquement, le travail à l'entrepôt est généré pour prélever les matières pour l'ordre de fabrication.</span><span class="sxs-lookup"><span data-stu-id="4fbb6-115">For materials that are physically reserved, warehouse work is generated to pick materials for the production order.</span></span>

## <a name="releasing-jobs-to-the-shop-floor"></a><span data-ttu-id="4fbb6-116">Lancement des tâches à l'atelier</span><span class="sxs-lookup"><span data-stu-id="4fbb6-116">Releasing jobs to the shop floor</span></span>
<span data-ttu-id="4fbb6-117">Une fois un ordre de fabrication lancé, les tâches de production concernant l'ordre sont visibles et prêts à être enregistrés.</span><span class="sxs-lookup"><span data-stu-id="4fbb6-117">After a production order is released, production jobs that are related to the order are visible and ready for registration.</span></span> <span data-ttu-id="4fbb6-118">Les opérateurs peuvent effectuer des enregistrements des tâches, tels que le début, l'arrêt et l'achèvement, sur la page **Terminal des bons de travail** ou **Périphérique pour le bon de travail**.</span><span class="sxs-lookup"><span data-stu-id="4fbb6-118">The operators can make job registrations, such as Start, Stop, and Completion, on either the **Job card terminal** page or the **Job card device** page.</span></span> <span data-ttu-id="4fbb6-119">Le temps et la quantité enregistrés sont automatiquement transférés depuis les pages d'enregistrement vers les journaux de production pour permettre le suivi du temps et de la quantité consommés.</span><span class="sxs-lookup"><span data-stu-id="4fbb6-119">The registered time and quantity are automatically transferred from the registration pages to production journals to keep track of the consumed time and quantity.</span></span>

## <a name="route-cards"></a><span data-ttu-id="4fbb6-120">Fiches productions</span><span class="sxs-lookup"><span data-stu-id="4fbb6-120">Route cards</span></span>
<span data-ttu-id="4fbb6-121">Une fiche production offre une vue d'ensemble des informations qui viennent du paramétrage des gammes et des opérations et des méthodes de planification des tâches.</span><span class="sxs-lookup"><span data-stu-id="4fbb6-121">A route card provides an overview of information that comes from route and operation setups, and from operation and job scheduling methods.</span></span>

## <a name="route-jobs"></a><span data-ttu-id="4fbb6-122">Tâches de gamme</span><span class="sxs-lookup"><span data-stu-id="4fbb6-122">Route jobs</span></span>
<span data-ttu-id="4fbb6-123">Une tâche de gamme répertorie en détails chaque tâche d'une opération, notamment les temps de réglage, de traitement, d'attente et de transport.</span><span class="sxs-lookup"><span data-stu-id="4fbb6-123">A route job lists each job of an operation in detail, and includes setup, process, queue, and transportation times.</span></span> <span data-ttu-id="4fbb6-124">Par exemple, une opération de peinture peut nécessiter des tâches individuelles comme les temps de paramétrage et d'exécution pour le processus de peinture et le temps d'attente pour le séchage.</span><span class="sxs-lookup"><span data-stu-id="4fbb6-124">For example, an operation such as painting might require individual jobs, such as setup time, run time for the painting process, and queue time for drying.</span></span>

## <a name="job-cards"></a><span data-ttu-id="4fbb6-125">Bons de travail</span><span class="sxs-lookup"><span data-stu-id="4fbb6-125">Job cards</span></span>
<span data-ttu-id="4fbb6-126">Un bon de travail répertorie les numéros de travail individuels d'une opération particulière.</span><span class="sxs-lookup"><span data-stu-id="4fbb6-126">A job card lists the individual job numbers of a particular operation.</span></span> <span data-ttu-id="4fbb6-127">Une tâche apparaît dans chaque page.</span><span class="sxs-lookup"><span data-stu-id="4fbb6-127">One job appears on each page.</span></span> <span data-ttu-id="4fbb6-128">Les tâches incluses sur un bon de travail, et leurs temps estimés, viennent des informations de paramétrage de la gamme et de l'opération.</span><span class="sxs-lookup"><span data-stu-id="4fbb6-128">The jobs that are included on a job card, and their estimated times, come from the route and operation setup information.</span></span> <span data-ttu-id="4fbb6-129">Depuis un bon de travail, vous pouvez ouvrir la page **Lignes de journal de production**, **bon de travail**.</span><span class="sxs-lookup"><span data-stu-id="4fbb6-129">From a job card, you can open the **Production journal lines**, **job card** page.</span></span> <span data-ttu-id="4fbb6-130">Les personnes qui exécutent des ressources opérationnelles peuvent donner leur avis sur le processus de production.</span><span class="sxs-lookup"><span data-stu-id="4fbb6-130">People who run operations resources can provide feedback about the production process.</span></span> <span data-ttu-id="4fbb6-131">Il existe des champs dans lesquels vous pouvez entrer des statistiques et des informations de consommation telles que la quantité d'erreurs.</span><span class="sxs-lookup"><span data-stu-id="4fbb6-131">There are fields where you can enter consumption statistics and information such as the error quantity.</span></span>

## <a name="warehouse-work-for-raw-material-picking"></a><span data-ttu-id="4fbb6-132">Travail d'entrepôt pour le prélèvement des matières premières</span><span class="sxs-lookup"><span data-stu-id="4fbb6-132">Warehouse work for raw material picking</span></span>
<span data-ttu-id="4fbb6-133">Le travail pour le prélèvement des matières premières est généré lors du lancement.</span><span class="sxs-lookup"><span data-stu-id="4fbb6-133">Work for raw material picking is generated during release.</span></span> <span data-ttu-id="4fbb6-134">Le travail est généré uniquement pour la quantité des matières physiquement réservées pour l'ordre de fabrication, avant le lancement de l'ordre.</span><span class="sxs-lookup"><span data-stu-id="4fbb6-134">Work is generated only for the quantity of materials that was physically reserved for the production order before the order was released.</span></span> <span data-ttu-id="4fbb6-135">Le paramétrage suivant est nécessaire pour générer le travail d'entrepôt pour le prélèvement des matières premières :</span><span class="sxs-lookup"><span data-stu-id="4fbb6-135">The following setup is required to generate warehouse work for raw material picking:</span></span>

-   <span data-ttu-id="4fbb6-136">Une directive d'emplacement pour le prélèvement des matières premières qui détermine où prélever les matériaux dans l'entrepôt</span><span class="sxs-lookup"><span data-stu-id="4fbb6-136">A location directive for raw materials picking that determines which warehouse location to pick the materials in</span></span>
-   <span data-ttu-id="4fbb6-137">Un modèle de vague pour les matières premières, où sont configurées les stratégies d'exécution du travail d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="4fbb6-137">A wave template for raw materials, where policies for the execution of warehouse work are configured</span></span>
-   <span data-ttu-id="4fbb6-138">Un emplacement d'entrée en production qui détermine où sont déposées les matières</span><span class="sxs-lookup"><span data-stu-id="4fbb6-138">A production input location that determines where materials are put</span></span>





