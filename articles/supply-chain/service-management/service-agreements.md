---
title: Vue d'ensemble de développement et d'établissement d'accords de service
description: Les accords de service permettent de définir les ressources utilisées dans une visite de service classique et leur mode de facturation au client.
author: ShylaThompson
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 41081525fb9ff7bfa3adb87ba038d899f58e436a
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216158"
---
# <a name="develop-and-establish-service-agreements-overview"></a><span data-ttu-id="6aa1d-103">Vue d'ensemble de développement et d'établissement d'accords de service</span><span class="sxs-lookup"><span data-stu-id="6aa1d-103">Develop and establish service agreements overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6aa1d-104">Les accords de service permettent de définir les ressources utilisées dans une visite de service classique et leur mode de facturation au client.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-104">Service agreements let you define the resources that are used in a typical service visit and how those resources are invoiced to the customer.</span></span>

<span data-ttu-id="6aa1d-105">Chaque accord de service est associé à un projet, via lequel des transactions sont validées et facturées.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-105">Every service agreement is attached to a project through which transactions are posted and invoiced.</span></span> <span data-ttu-id="6aa1d-106">Toutefois, vous pouvez également facturer des transactions de commande de service directement via le projet sans associer au préalable la commande de service à l'accord de service.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-106">However, you can also invoice service order transactions directly through the project without first having to connect the service order to a service agreement.</span></span> <span data-ttu-id="6aa1d-107">Cette option est envisageable si la commande de service correspond à une visite de service unique et si la nécessité d'un traitement rapide des transactions de service prend rapidement le pas sur la nécessité de mettre à jour des informations d'accord de service détaillées sur le client pour une période donnée.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-107">You might decide to do this if the service order is for a one-time-only service visit and the need for processing the service transactions quickly outweighs the need for maintaining detailed service-agreement information about the customer over a period of time.</span></span>

## <a name="service-agreement"></a><span data-ttu-id="6aa1d-108">Accord de service</span><span class="sxs-lookup"><span data-stu-id="6aa1d-108">Service agreement</span></span>

<span data-ttu-id="6aa1d-109">Dans chaque accord de service, vous devez spécifier un projet, un ID accord de service et un groupe d'accords de service.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-109">In each service agreement, you must specify a project, a service-agreement ID, and a service-agreement group.</span></span> <span data-ttu-id="6aa1d-110">Vous pouvez utiliser ce dernier pour trier et organiser les accords de service.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-110">The service-agreement group can be used to sort and organize service agreements.</span></span>

<span data-ttu-id="6aa1d-111">L'en-tête de l'accord de service contient des paramètres qui s'appliquent à toutes les lignes d'accord associées :</span><span class="sxs-lookup"><span data-stu-id="6aa1d-111">A service agreement header contains settings that apply to all attached agreement lines:</span></span>

-  <span data-ttu-id="6aa1d-112">Si l'accord de service est suspendu.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-112">Whether the service agreement is suspended.</span></span> <span data-ttu-id="6aa1d-113">Dans ce cas, vous ne pouvez pas générer de commandes de service à partir d'un accord de service.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-113">If the service agreement is suspended, you cannot generate service orders from the service agreement.</span></span>
-  <span data-ttu-id="6aa1d-114">La durée de l'accord de service.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-114">The duration of the service agreement.</span></span>
-  <span data-ttu-id="6aa1d-115">La manière dont les lignes de commande de service doivent être combinées dans les commandes de service.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-115">How service-order lines are to be combined into service orders.</span></span>
-  <span data-ttu-id="6aa1d-116">Si l'accord de service est un modèle.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-116">Whether the service agreement is a template.</span></span>

<span data-ttu-id="6aa1d-117">Dans l'en-tête d'accord de service, vous pouvez également définir tous les objets de service et tâches de service qui peuvent être utilisés dans l'accord de service en entrant les tâches ou objets de service spécifiques à associer aux lignes de l'accord.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-117">In the service-agreement header, you also set up all the service objects and service tasks that can be used with the service agreement by entering the specific service tasks or service objects that are to be attached to the various lines of the agreement.</span></span>

<span data-ttu-id="6aa1d-118">À partir de l'en-tête d'accord de service, vous pouvez également copier les lignes d'accord de service ou de modèle de service dans l'accord de service en cours.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-118">From the service-agreement header, you can also copy service-agreement lines or service-template lines into the current service agreement.</span></span>

<span data-ttu-id="6aa1d-119">Vous pouvez suspendre des accords de service et bloquer des lignes d'accord de service spécifiques.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-119">You can suspend service agreements and stop individual service agreement lines.</span></span>

<span data-ttu-id="6aa1d-120">Si vous activez la case à cocher **En suspens** pour une ligne d'accord de service, vous ne pouvez pas :</span><span class="sxs-lookup"><span data-stu-id="6aa1d-120">If you select the **Suspended** check box on a service agreement, you cannot:</span></span>

-    <span data-ttu-id="6aa1d-121">créer des commandes de service automatiquement ou manuellement à partir de l'accord de service.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-121">Create service orders automatically or manually from the service agreement.</span></span>

<span data-ttu-id="6aa1d-122">Si vous activez la case à cocher **Arrêté** pour une ligne d'accord de service, vous ne pouvez pas :</span><span class="sxs-lookup"><span data-stu-id="6aa1d-122">If you select the **Stopped** check box on a service agreement line, you cannot:</span></span>

-    <span data-ttu-id="6aa1d-123">créer des commandes de service automatiquement ou manuellement à partir de la ligne d'accord de service ;</span><span class="sxs-lookup"><span data-stu-id="6aa1d-123">Create service orders automatically or manually from the service agreement line.</span></span>
-    <span data-ttu-id="6aa1d-124">copier la ligne d'accord de service dans un autre accord de service ou une autre commande de service.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-124">Copy the service agreement line into another service agreement or service order.</span></span>


> [!NOTE]
> <span data-ttu-id="6aa1d-125">Si un accord de service est suspendu, toutes les lignes associées sont bloquées quel que soit leur statut.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-125">If a service agreement is suspended, all the attached lines are stopped, regardless of their individual status.</span></span>

## <a name="service-agreement-lines"></a><span data-ttu-id="6aa1d-126">Lignes d'accord de service</span><span class="sxs-lookup"><span data-stu-id="6aa1d-126">Service-agreement lines</span></span>

<span data-ttu-id="6aa1d-127">Chaque ligne d'accord de service décrit précisément le contenu de la tâche de service proposée.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-127">Each service-agreement line describes in detail the content of the proposed service work.</span></span> <span data-ttu-id="6aa1d-128">Elles contiennent les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6aa1d-128">The lines contain the following settings:</span></span>

-  <span data-ttu-id="6aa1d-129">le type de transaction et la description correspondante ;</span><span class="sxs-lookup"><span data-stu-id="6aa1d-129">The transaction type and the description of the transaction type.</span></span>
-  <span data-ttu-id="6aa1d-130">l'employé qui exécute la tâche de service ;</span><span class="sxs-lookup"><span data-stu-id="6aa1d-130">The employee who performs the service work.</span></span>
-  <span data-ttu-id="6aa1d-131">les objets sur lesquels le service doit être exécuté pour l'accord de service ;</span><span class="sxs-lookup"><span data-stu-id="6aa1d-131">The objects on which service must be performed for the service agreement.</span></span>
-  <span data-ttu-id="6aa1d-132">la fréquence d'exécution de la tâche et d'enregistrement des articles, dépenses et transactions de frais ;</span><span class="sxs-lookup"><span data-stu-id="6aa1d-132">The frequency with which work is performed and associated item, expense, and fee transactions are registered.</span></span>
-  <span data-ttu-id="6aa1d-133">la fenêtre Délai dans laquelle les lignes de commande de service peuvent être regroupées dans une commande de service ;</span><span class="sxs-lookup"><span data-stu-id="6aa1d-133">The time window within which service-order lines can be grouped into a service order.</span></span>
-  <span data-ttu-id="6aa1d-134">les tâches de service permettant de regrouper un ensemble de lignes d'accord en tâches et de résumer aux techniciens et aux clients la tâche de service qui doit être fournie ;</span><span class="sxs-lookup"><span data-stu-id="6aa1d-134">The service tasks that are used to group sets of agreement lines together into work tasks and to summarize for service technicians and customers what service task is to be provided.</span></span>
-  <span data-ttu-id="6aa1d-135">si la ligne est interrompue.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-135">Whether a line is stopped.</span></span> <span data-ttu-id="6aa1d-136">Dans ce cas, vous ne pouvez pas créer de commande de service pour cette ligne individuelle ;</span><span class="sxs-lookup"><span data-stu-id="6aa1d-136">If a line is stopped, you cannot create service orders for that individual line.</span></span>
-  <span data-ttu-id="6aa1d-137">les paramètres du projet, tels que la catégorie et la propriété de ligne.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-137">Project settings, such as the category and the line property.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6aa1d-138">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="6aa1d-138">Related topics</span></span>

[<span data-ttu-id="6aa1d-139">Création d'accords de service</span><span class="sxs-lookup"><span data-stu-id="6aa1d-139">Create service agreements</span></span>](create-service-agreements.md)
