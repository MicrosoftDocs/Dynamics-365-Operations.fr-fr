---
title: Vue d'ensemble du module Gestion des services
description: Utilisez le module Gestion des services pour établir des accords de service et des services récurrents, traiter des commandes de service et des demandes de renseignements des clients, ainsi que pour gérer et analyser la fourniture de services aux clients.
author: ShylaThompson
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dd2f27c5797fbd34674e39013ed3e0e40cdb28b2
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251130"
---
# <a name="service-management-overview"></a><span data-ttu-id="e2bbd-103">Vue d'ensemble du module Gestion des services</span><span class="sxs-lookup"><span data-stu-id="e2bbd-103">Service management overview</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="e2bbd-104">Utilisez le module **Gestion des services** pour établir des accords de service et des services récurrents, traiter des commandes de service et des demandes de renseignements des clients, ainsi que pour gérer et analyser la fourniture de services aux clients.</span><span class="sxs-lookup"><span data-stu-id="e2bbd-104">Use **Service management** to establish service agreements and service subscriptions, handle service orders and customer inquiries, and to manage and analyze the delivery of services to customers.</span></span> <span data-ttu-id="e2bbd-105">Les accords de service permettent de définir les ressources utilisées dans une visite de service classique.</span><span class="sxs-lookup"><span data-stu-id="e2bbd-105">You can use service agreements to define the resources that are used in a typical service visit.</span></span> <span data-ttu-id="e2bbd-106">Vous pouvez également utiliser les accords de service pour visualiser la façon dont les ressources sont facturées au client.</span><span class="sxs-lookup"><span data-stu-id="e2bbd-106">You can also use service agreements to view how those resources are invoiced to the customer.</span></span> <span data-ttu-id="e2bbd-107">En outre, un accord de service peut inclure un contrat de niveau de service spécifiant les durées de réponse standard et offrant des outils permettant d'enregistrer l'heure réelle.</span><span class="sxs-lookup"><span data-stu-id="e2bbd-107">A service agreement can also include a service level agreement that specifies standard response times, and offers tools to record the actual time.</span></span>

<span data-ttu-id="e2bbd-108">Vous pouvez créer des commandes de service pour gérer les informations relatives aux visites prévues et non prévues sur un site client par un technicien de service.</span><span class="sxs-lookup"><span data-stu-id="e2bbd-108">You can create service orders to manage information about scheduled and unscheduled visits by a service technician to a customer site.</span></span> <span data-ttu-id="e2bbd-109">Les commandes de service incluent notamment les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="e2bbd-109">Service orders include information such as:</span></span>

1.  <span data-ttu-id="e2bbd-110">le nombre d'heures de travail qu'un technicien de service doit effectuer ;</span><span class="sxs-lookup"><span data-stu-id="e2bbd-110">The hours of work that the service technician will perform</span></span>

2.  <span data-ttu-id="e2bbd-111">le type de service ou de réparation ;</span><span class="sxs-lookup"><span data-stu-id="e2bbd-111">The type of service or repair</span></span>

3.  <span data-ttu-id="e2bbd-112">l'article à réparer, avec des détails sur les symptômes et le diagnostic ;</span><span class="sxs-lookup"><span data-stu-id="e2bbd-112">The item to repair, including details about the symptoms and diagnosis</span></span>

4.  <span data-ttu-id="e2bbd-113">les dépenses et les frais associés au service ou à la réparation.</span><span class="sxs-lookup"><span data-stu-id="e2bbd-113">Any expenses and fees related to the service or repair</span></span>

<span data-ttu-id="e2bbd-114">Vous pouvez recevoir, traiter et répartir les demandes de service.</span><span class="sxs-lookup"><span data-stu-id="e2bbd-114">You can receive, process, and dispatch service requests.</span></span> <span data-ttu-id="e2bbd-115">Après avoir créé une commande de service, vous pouvez utiliser les stades du service pour surveiller sa progression et spécifier des règles contrôlant les actions mises en œuvre à chaque stade.</span><span class="sxs-lookup"><span data-stu-id="e2bbd-115">After you have created a service order, you can use service stages to monitor progress and specify rules that control what actions are enabled in each stage.</span></span> <span data-ttu-id="e2bbd-116">À la fin d'une commande de service, vous pouvez fermer la session de la commande afin de confirmer qu'elle est terminée, puis la valider afin de lancer le processus de facturation.</span><span class="sxs-lookup"><span data-stu-id="e2bbd-116">When a service order is complete, you can sign off on the order to confirm that it is complete, and then post the order to start the invoice process.</span></span>

<span data-ttu-id="e2bbd-117">Utilisez les outils de génération d'états pour surveiller les marges de commande de service et les transactions d'abonnement, ainsi que pour imprimer les descriptions de travail et les accusés de réception des travaux.</span><span class="sxs-lookup"><span data-stu-id="e2bbd-117">Use the reporting tools to monitor service order margins and subscription transactions, and print work descriptions and work receipts.</span></span>

## <a name="business-processes"></a><span data-ttu-id="e2bbd-118">Processus entreprise</span><span class="sxs-lookup"><span data-stu-id="e2bbd-118">Business processes</span></span>

<span data-ttu-id="e2bbd-119">Le schéma suivant présente les processus entreprise généraux associés au module **Gestion des services** et indique à quel niveau les processus de service s'intègrent avec d'autres modules.</span><span class="sxs-lookup"><span data-stu-id="e2bbd-119">The following diagram illustrates the high level business processes for **Service management**, and shows where service processes integrate with other modules.</span></span>

<span data-ttu-id="e2bbd-120">[![Diagramme de processus entreprise de gestion des services](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span><span class="sxs-lookup"><span data-stu-id="e2bbd-120">[![Service management business process diagram](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span></span>

## <a name="service-management-at-a-glance"></a><span data-ttu-id="e2bbd-121">Aperçu du module Gestion des services</span><span class="sxs-lookup"><span data-stu-id="e2bbd-121">Service management at a glance</span></span>

|<span data-ttu-id="e2bbd-122">Tâches importantes</span><span class="sxs-lookup"><span data-stu-id="e2bbd-122">Important tasks</span></span>           | <span data-ttu-id="e2bbd-123">Pages principales</span><span class="sxs-lookup"><span data-stu-id="e2bbd-123">Primary pages</span></span>                         |<span data-ttu-id="e2bbd-124">États courants</span><span class="sxs-lookup"><span data-stu-id="e2bbd-124">Popular reports</span></span>              |
|--------------------------|---------------------------------------|-----------------------------|
|<span data-ttu-id="e2bbd-125">Réalisation d'accords de service</span><span class="sxs-lookup"><span data-stu-id="e2bbd-125">Fulfill service agreements</span></span>|<span data-ttu-id="e2bbd-126">Accords de service</span><span class="sxs-lookup"><span data-stu-id="e2bbd-126">Service agreements</span></span>                     |<span data-ttu-id="e2bbd-127">Marge de commande de service</span><span class="sxs-lookup"><span data-stu-id="e2bbd-127">Service order margin</span></span>         |
|<span data-ttu-id="e2bbd-128">Traitement des demandes des clients</span><span class="sxs-lookup"><span data-stu-id="e2bbd-128">Handle customer inquiries</span></span> |<span data-ttu-id="e2bbd-129">Commandes de service</span><span class="sxs-lookup"><span data-stu-id="e2bbd-129">Service orders</span></span>                         |<span data-ttu-id="e2bbd-130">Description du travail</span><span class="sxs-lookup"><span data-stu-id="e2bbd-130">Work description</span></span>             |
|                          |<span data-ttu-id="e2bbd-131">Tableau d'affectation</span><span class="sxs-lookup"><span data-stu-id="e2bbd-131">Dispatch board</span></span>                         |<span data-ttu-id="e2bbd-132">Transaction - Abonnement</span><span class="sxs-lookup"><span data-stu-id="e2bbd-132">Transaction - subscription</span></span>   |
|                          |                                       |<span data-ttu-id="e2bbd-133">Transactions de frais d'abonnement</span><span class="sxs-lookup"><span data-stu-id="e2bbd-133">Subscription fee transactions</span></span>|


## <a name="integration-of-service-management"></a><span data-ttu-id="e2bbd-134">Intégration du module Gestion des services</span><span class="sxs-lookup"><span data-stu-id="e2bbd-134">Integration of Service management</span></span>

<span data-ttu-id="e2bbd-135">Le module Gestion des services peut être intégré aux modules suivants :</span><span class="sxs-lookup"><span data-stu-id="e2bbd-135">Service management can be integrated with the following modules:</span></span>

  - [<span data-ttu-id="e2bbd-136">Ventes et marketing</span><span class="sxs-lookup"><span data-stu-id="e2bbd-136">Sales and marketing</span></span>](../sales-marketing/overview-sales-marketing.md)
  - [<span data-ttu-id="e2bbd-137">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="e2bbd-137">Human resources</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/index)

  

