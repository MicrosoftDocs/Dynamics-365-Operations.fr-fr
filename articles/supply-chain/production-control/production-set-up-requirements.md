---
title: "Conditions requises pour le paramétrage de la production"
description: "Cet article fournit des informations sur les conditions requises pour le paramétrage avant d'utiliser le contrôle de la production."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdParameters, RouteOpr, RouteOprTable, WorkCalendarTable, WorkTimeTable, WrkCtrTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 55561
ms.assetid: 1953059f-478d-4706-b461-25b89ace5fc3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: ade7e55e0568acd7eff3ceead29c3c6d0ca2da1e
ms.contentlocale: fr-fr
ms.lasthandoff: 05/08/2018

---

# <a name="production-setup-requirements"></a><span data-ttu-id="c3242-103">Conditions requises pour le paramétrage de la production</span><span class="sxs-lookup"><span data-stu-id="c3242-103">Production setup requirements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c3242-104">Cet article fournit des informations sur les conditions requises pour le paramétrage avant d'utiliser le contrôle de la production.</span><span class="sxs-lookup"><span data-stu-id="c3242-104">This article provides information about setup requirements before you can work with Production control.</span></span> 

<span data-ttu-id="c3242-105">Le contrôle de la production figure dans les fonctionnalités d'autres modules.</span><span class="sxs-lookup"><span data-stu-id="c3242-105">Production control is integrated with features in other modules.</span></span> <span data-ttu-id="c3242-106">Cette interconnectivité permet de modifier les ordres de fabrication et de s'assurer qu'ils sont automatiquement mis à jour dans tous les autres processus et calculs associés du système.</span><span class="sxs-lookup"><span data-stu-id="c3242-106">This interconnectivity lets you change production orders and make sure that they are automatically updated in all other related processes and calculations in the system.</span></span> <span data-ttu-id="c3242-107">Les processus de paramétrage suivants sont listés dans leur ordre de réalisation.</span><span class="sxs-lookup"><span data-stu-id="c3242-107">The following setup processes are listed in the order that you should complete them in.</span></span>

## <a name="required-baseline-setup-in-other-modules"></a><span data-ttu-id="c3242-108">Paramétrages de bases requis dans les autres modules</span><span class="sxs-lookup"><span data-stu-id="c3242-108">Required baseline setup in other modules</span></span>
<span data-ttu-id="c3242-109">Vous devez paramétrer les informations des autres modules avant de pouvoir utiliser le module Contrôle de la production.</span><span class="sxs-lookup"><span data-stu-id="c3242-109">Information in other modules must be set up before you can work with Production control.</span></span> <span data-ttu-id="c3242-110">Ce paramétrage inclut les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="c3242-110">This setup includes the following tasks:</span></span>

-   <span data-ttu-id="c3242-111">paramétrage des informations générales sur la société ;</span><span class="sxs-lookup"><span data-stu-id="c3242-111">Set up general company information.</span></span>
-   <span data-ttu-id="c3242-112">paramétrage de la comptabilité ;</span><span class="sxs-lookup"><span data-stu-id="c3242-112">Set up the general ledger.</span></span>
-   <span data-ttu-id="c3242-113">définition des groupes d'articles ;</span><span class="sxs-lookup"><span data-stu-id="c3242-113">Define item groups.</span></span>
-   <span data-ttu-id="c3242-114">paramétrage des comptes généraux pour les groupes d'articles ;</span><span class="sxs-lookup"><span data-stu-id="c3242-114">Set up ledger accounts for item groups.</span></span>
-   <span data-ttu-id="c3242-115">Paramétrage de la table des articles en stock dans le module Gestion des stocks.</span><span class="sxs-lookup"><span data-stu-id="c3242-115">Set up the inventory item table in Inventory management.</span></span>
-   <span data-ttu-id="c3242-116">Création de nomenclatures et de versions de nomenclature dans le module Gestion des stocks.</span><span class="sxs-lookup"><span data-stu-id="c3242-116">Create bills of materials (BOMs) and BOM versions in Inventory management.</span></span>

## <a name="required-calendar-and-resource-setup"></a><span data-ttu-id="c3242-117">Paramétrage de calendrier et de ressource requis</span><span class="sxs-lookup"><span data-stu-id="c3242-117">Required calendar and resource setup</span></span>
<span data-ttu-id="c3242-118">Avant d'utiliser le module Contrôle de la production, ouvrez le module Administration d'organisation, puis créez et définissez le calendrier et les ressources opérationnelles dans l'ordre suivant :</span><span class="sxs-lookup"><span data-stu-id="c3242-118">Before you use Production control, open Organization administration, and create and define the calendar and operations resources in the following order:</span></span>

1.  <span data-ttu-id="c3242-119">**Modèles de temps de travail** – Paramétrez les modèles de temps de travail pour définir les temps disponibles pour la planification de la production.</span><span class="sxs-lookup"><span data-stu-id="c3242-119">**Working time templates** – Set up working time templates to define the times that are available for production scheduling.</span></span>
2.  <span data-ttu-id="c3242-120">**Calendriers** - Paramétrez les calendriers de temps de travail afin de définir quels jours de l'année sont disponibles pour la planification de la production.</span><span class="sxs-lookup"><span data-stu-id="c3242-120">**Calendars** – Set up working time calendars to define the days of the year that are available for production scheduling.</span></span>
3.  <span data-ttu-id="c3242-121">**Groupes de ressources** – Paramétrez les groupes de ressources pour regrouper les ressources opérationnelles afin d'obtenir une vue d'ensemble de la capacité libre lors de l'exécution de la planification.</span><span class="sxs-lookup"><span data-stu-id="c3242-121">**Resource groups** – Set up resource groups to group the operations resources, so that you can get an overview of any free capacity when you run scheduling.</span></span> <span data-ttu-id="c3242-122">Vous ne devez pas paramétrer des groupes de ressources avant de paramétrer des ressources opérationnelles.</span><span class="sxs-lookup"><span data-stu-id="c3242-122">You don't have to set up resource groups before you set up operations resources.</span></span> <span data-ttu-id="c3242-123">Toutefois, il est recommandé de comprendre comment regrouper des ressources lorsque vous paramétrez le module Contrôle de la production.</span><span class="sxs-lookup"><span data-stu-id="c3242-123">However, we recommend that you understand how to group resources when you set up Production control.</span></span>
4.  <span data-ttu-id="c3242-124">**Ressources** – Paramétrez des ressources opérationnelles afin de définir les ressources utilisées pour exécuter le processus de production et planifier la capacité.</span><span class="sxs-lookup"><span data-stu-id="c3242-124">**Resources** – Set up operations resources to define the resources that are used to complete the production process and plan for capacity.</span></span>

## <a name="required-production-parameters-setup"></a><span data-ttu-id="c3242-125">Paramétrage requis des paramètres de production</span><span class="sxs-lookup"><span data-stu-id="c3242-125">Required production parameters setup</span></span>
<span data-ttu-id="c3242-126">**Paramètres de contrôle de la production** – Définissez des paramètres de production de base afin de définir la manière dont le système gère et traite les ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="c3242-126">**Production control parameters** – Set up basic production parameters to define how the system handles and processes production orders.</span></span> <span data-ttu-id="c3242-127">Définissez le mode de création, d'estimation, de planification et de consommation des ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="c3242-127">Define how production orders are created, estimated, scheduled, and consumed.</span></span> <span data-ttu-id="c3242-128">Vous pouvez également sélectionner le type de rétroaction souhaité et la manière dont le contrôle de gestion doit être réalisé.</span><span class="sxs-lookup"><span data-stu-id="c3242-128">You can also select what kind of feedback you want and how cost accounting is done.</span></span>

## <a name="required-journal-name-identification"></a><span data-ttu-id="c3242-129">Identification requise des noms de journal</span><span class="sxs-lookup"><span data-stu-id="c3242-129">Required journal name identification</span></span>
<span data-ttu-id="c3242-130">**Noms des journaux de production** – Permet de spécifier les noms des journaux de production à utiliser afin d'enregistrer et de valider des transactions.</span><span class="sxs-lookup"><span data-stu-id="c3242-130">**Production journal names** – Specify the production journal names that are used to record and post transactions.</span></span>

## <a name="setup-if-you-use-operations"></a><span data-ttu-id="c3242-131">Paramétrage pour l'utilisation des opérations</span><span class="sxs-lookup"><span data-stu-id="c3242-131">Setup if you use operations</span></span>
<span data-ttu-id="c3242-132">Ces opérations représentent des activités spécifiques qui permettent de fabriquer le produit fini.</span><span class="sxs-lookup"><span data-stu-id="c3242-132">Operations represent the specific activities that are completed to produce the finished product.</span></span> <span data-ttu-id="c3242-133">**Remarque :** Vous devez savoir quelles sont les activités nécessaires à la fabrication de l'article, et l'ordre et les priorités de ces activités.</span><span class="sxs-lookup"><span data-stu-id="c3242-133">**Note:** You must know the types of activities that are required in order to produce your item, and the order and priorities of those activities.</span></span> <span data-ttu-id="c3242-134">Vous devez également savoir quelles ressources sont impliquées, et leur nombre.</span><span class="sxs-lookup"><span data-stu-id="c3242-134">You must also know which resources are involved, and how many.</span></span>

1.  <span data-ttu-id="c3242-135">**Opérations** - Paramétrez des opérations afin de représenter les tâches à réaliser pour produire un article fini.</span><span class="sxs-lookup"><span data-stu-id="c3242-135">**Operations** – Set up operations to represent the tasks that must be completed to produce the finished item.</span></span>
2.  <span data-ttu-id="c3242-136">**Relations** – Paramétrez des relations d'opération afin de définir les propriétés détaillées.</span><span class="sxs-lookup"><span data-stu-id="c3242-136">**Relations** – Set up operation relations to establish detailed properties.</span></span> <span data-ttu-id="c3242-137">Pour définir les relations d'opération, cliquez sur **Relations** sur la page **Opérations**.</span><span class="sxs-lookup"><span data-stu-id="c3242-137">To define operation relations, click **Relations** on the **Operations** page.</span></span>

## <a name="setup-if-you-use-routes"></a><span data-ttu-id="c3242-138">Paramétrage pour l'utilisation des gammes</span><span class="sxs-lookup"><span data-stu-id="c3242-138">Setup if you use routes</span></span>
<span data-ttu-id="c3242-139">Si vous utilisez des gammes, les opérations doivent être définies pour chaque gamme de production que vous paramétrez.</span><span class="sxs-lookup"><span data-stu-id="c3242-139">If you're working with routes, operations must be defined for every production route that you set up.</span></span> <span data-ttu-id="c3242-140">Une gamme représente le chemin suivi par l'article d'opération en opération, du début à la fin du processus de production.</span><span class="sxs-lookup"><span data-stu-id="c3242-140">The route represents the path that the item takes from operation to operation, from the start of the production process to the end.</span></span>

1.  <span data-ttu-id="c3242-141">**Catégories de coûts** – Paramétrez des catégories de coûts afin de définir le coût par heure des processus spécifiés et les temps de réglage.</span><span class="sxs-lookup"><span data-stu-id="c3242-141">**Cost categories** – Set up cost categories to define the cost per hour of specified processes and setup times.</span></span>
2.  <span data-ttu-id="c3242-142">**Groupes de coûts** – Paramétrez les groupes de coûts afin de créer et de mettre à jour les différents types de coûts.</span><span class="sxs-lookup"><span data-stu-id="c3242-142">**Cost groups** – Set up cost groups to create and maintain different types of costing.</span></span>
3.  <span data-ttu-id="c3242-143">**Groupes de gammes** – Paramétrez des groupes de gammes pour définir les paramètres liés à des groupes de gammes.</span><span class="sxs-lookup"><span data-stu-id="c3242-143">**Route groups** – Set up route groups to define parameters that are related to groups of routes.</span></span> <span data-ttu-id="c3242-144">Vous devez paramétrer les groupes de gammes avant de pouvoir créer des gammes de production.</span><span class="sxs-lookup"><span data-stu-id="c3242-144">You must set up route groups before you can create production routes.</span></span>
4.  <span data-ttu-id="c3242-145">**Gammes** – Paramétrez des gammes de production et définissez les paramètres par défaut afin de contrôler la planification, l'évaluation des coûts et le prix des opérations de gamme, ainsi que la progression de la génération d'états.</span><span class="sxs-lookup"><span data-stu-id="c3242-145">**Routes** – Set up production routes, and define default settings to control scheduling, costing, and pricing of route operations, and to control progress reporting.</span></span>
5.  <span data-ttu-id="c3242-146">**Gammes** – Paramétrez les versions de gamme afin d'autoriser les variations d'article en production.</span><span class="sxs-lookup"><span data-stu-id="c3242-146">**Routes** – Set up route versions to enable item variations in production.</span></span>

## <a name="optional-advanced-settings"></a><span data-ttu-id="c3242-147">Paramètres facultatifs et avancés</span><span class="sxs-lookup"><span data-stu-id="c3242-147">Optional advanced settings</span></span>
1.  <span data-ttu-id="c3242-148">**Groupes de productions** – Paramétrez les groupes de production afin de définir les relations entre l'ordre de fabrication et les comptes généraux.</span><span class="sxs-lookup"><span data-stu-id="c3242-148">**Production groups** – Set up production groups to establish relationships between the production order and ledger accounts.</span></span> <span data-ttu-id="c3242-149">Ces derniers sont utilisés pour valider ou regrouper les ordres à des fins de génération d'états.</span><span class="sxs-lookup"><span data-stu-id="c3242-149">The ledger accounts are used to post or group orders for reporting.</span></span>
2.  <span data-ttu-id="c3242-150">**Regroupements de productions** – Créez des regroupements de production afin de regrouper les ordres de fabrication pour leur traitement urgent ou pour la suppression ou la validation des groupes d'ordres.</span><span class="sxs-lookup"><span data-stu-id="c3242-150">**Production pools** – Create production pools to group production orders so that you can process urgent production orders, or delete and post groups of orders.</span></span>
3.  <span data-ttu-id="c3242-151">**Propriétés** – Définissez les propriétés pour créer les attributs spéciaux que vous pouvez affecter à vos ressources pour contrôler la séquence de production.</span><span class="sxs-lookup"><span data-stu-id="c3242-151">**Properties** – Define properties to create special attributes that you can assign to your resources to control the order of productions.</span></span> <span data-ttu-id="c3242-152">Ces attributs sont connectés au modèle de temps de travail.</span><span class="sxs-lookup"><span data-stu-id="c3242-152">These attributes are connected to the working time template.</span></span>





