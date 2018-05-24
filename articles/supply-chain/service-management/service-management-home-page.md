---
title: Gestion des services
description: "Utilisez le module Gestion des services pour établir des accords de service et des services récurrents, traiter des commandes de service et des demandes de renseignements des clients, ainsi que pour gérer et analyser la fourniture de services aux clients."
author: YuyuScheller
manager: AnnBe
ms.date: 05/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 02cdf4615e2071f2b7de2e86b6f9e6637c6e5d8d
ms.openlocfilehash: 236ab21b2d1c5a4e82270e5381d163e97437cb7f
ms.contentlocale: fr-fr
ms.lasthandoff: 05/09/2018

---


# <a name="service-management"></a><span data-ttu-id="4754b-103">Gestion des services</span><span class="sxs-lookup"><span data-stu-id="4754b-103">Service management</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="4754b-104">Utilisez le module **Gestion des services** pour établir des accords de service et des services récurrents, traiter des commandes de service et des demandes de renseignements des clients, ainsi que pour gérer et analyser la fourniture de services aux clients.</span><span class="sxs-lookup"><span data-stu-id="4754b-104">Use **Service management** to establish service agreements and service subscriptions, handle service orders and customer inquiries, and to manage and analyze the delivery of services to customers.</span></span> <span data-ttu-id="4754b-105">Les accords de service permettent de définir les ressources utilisées dans une visite de service classique.</span><span class="sxs-lookup"><span data-stu-id="4754b-105">You can use service agreements to define the resources that are used in a typical service visit.</span></span> <span data-ttu-id="4754b-106">Vous pouvez également utiliser les accords de service pour visualiser la façon dont les ressources sont facturées au client.</span><span class="sxs-lookup"><span data-stu-id="4754b-106">You can also use service agreements to view how those resources are invoiced to the customer.</span></span> <span data-ttu-id="4754b-107">En outre, un accord de service peut inclure un contrat de niveau de service spécifiant les durées de réponse standard et offrant des outils permettant d'enregistrer l'heure réelle.</span><span class="sxs-lookup"><span data-stu-id="4754b-107">A service agreement can also include a service level agreement that specifies standard response times, and offers tools to record the actual time.</span></span>

<span data-ttu-id="4754b-108">Vous pouvez créer des commandes de service pour gérer les informations relatives aux visites prévues et non prévues sur un site client par un technicien de service.</span><span class="sxs-lookup"><span data-stu-id="4754b-108">You can create service orders to manage information about scheduled and unscheduled visits by a service technician to a customer site.</span></span> <span data-ttu-id="4754b-109">Les commandes de service incluent notamment les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4754b-109">Service orders include information such as:</span></span>

1.  <span data-ttu-id="4754b-110">le nombre d'heures de travail qu'un technicien de service doit effectuer ;</span><span class="sxs-lookup"><span data-stu-id="4754b-110">The hours of work that the service technician will perform</span></span>

2.  <span data-ttu-id="4754b-111">le type de service ou de réparation ;</span><span class="sxs-lookup"><span data-stu-id="4754b-111">The type of service or repair</span></span>

3.  <span data-ttu-id="4754b-112">l'article à réparer, avec des détails sur les symptômes et le diagnostic ;</span><span class="sxs-lookup"><span data-stu-id="4754b-112">The item to repair, including details about the symptoms and diagnosis</span></span>

4.  <span data-ttu-id="4754b-113">les dépenses et les frais associés au service ou à la réparation.</span><span class="sxs-lookup"><span data-stu-id="4754b-113">Any expenses and fees related to the service or repair</span></span>

<span data-ttu-id="4754b-114">Les clients peuvent envoyer des demandes de service par Internet via Enterprise Portal.</span><span class="sxs-lookup"><span data-stu-id="4754b-114">Customers can submit service requests through the Internet by using the Enterprise Portal.</span></span> <span data-ttu-id="4754b-115">Vous pouvez recevoir, traiter et répartir ces demandes.</span><span class="sxs-lookup"><span data-stu-id="4754b-115">You can receive, process, and dispatch these requests.</span></span> <span data-ttu-id="4754b-116">Après avoir créé une commande de service, vous pouvez utiliser les stades du service pour surveiller sa progression et spécifier des règles contrôlant les actions mises en œuvre à chaque stade.</span><span class="sxs-lookup"><span data-stu-id="4754b-116">After you have created a service order, you can use service stages to monitor progress and specify rules that control what actions are enabled in each stage.</span></span> <span data-ttu-id="4754b-117">À la fin d'une commande de service, vous pouvez fermer la session de la commande afin de confirmer qu'elle est terminée, puis la valider afin de lancer le processus de facturation.</span><span class="sxs-lookup"><span data-stu-id="4754b-117">When a service order is complete, you can sign off on the order to confirm that it is complete, and then post the order to start the invoice process.</span></span>

<span data-ttu-id="4754b-118">Utilisez les outils de génération d'états pour surveiller les marges de commande de service et les transactions d'abonnement, ainsi que pour imprimer les descriptions de travail et les accusés de réception des travaux.</span><span class="sxs-lookup"><span data-stu-id="4754b-118">Use the reporting tools to monitor service order margins and subscription transactions, and print work descriptions and work receipts.</span></span>

## <a name="business-processes"></a><span data-ttu-id="4754b-119">Processus entreprise</span><span class="sxs-lookup"><span data-stu-id="4754b-119">Business processes</span></span>

<span data-ttu-id="4754b-120">Le schéma suivant présente les processus entreprise généraux associés au module **Gestion des services**, et indique à quel niveau les processus de service s'intègrent avec d'autres modules dans Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4754b-120">The following diagram illustrates the high level business processes for **Service management**, and shows where service processes integrate with other modules in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="4754b-121">[![Diagramme de processus entreprise de gestion des services](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span><span class="sxs-lookup"><span data-stu-id="4754b-121">[![Service management business process diagram](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span></span>

## <a name="service-management-at-a-glance"></a><span data-ttu-id="4754b-122">Aperçu du module Gestion des services</span><span class="sxs-lookup"><span data-stu-id="4754b-122">Service management at a glance</span></span>

<table>
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4754b-123">Tâches importantes</span><span class="sxs-lookup"><span data-stu-id="4754b-123">Important tasks</span></span></p></th>
<th><p><span data-ttu-id="4754b-124">Écrans principaux</span><span class="sxs-lookup"><span data-stu-id="4754b-124">Primary forms</span></span></p></th>
<th><p><span data-ttu-id="4754b-125">États courants</span><span class="sxs-lookup"><span data-stu-id="4754b-125">Popular reports</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4754b-126">Réalisation d'accords de service</span><span class="sxs-lookup"><span data-stu-id="4754b-126">Fulfill service agreements</span></span></a></p></td>
<td><p><span data-ttu-id="4754b-127"><a href="https://technet.microsoft.com/en-us/library/aa617823(v=ax.60)">Accords de service (écran)</a></span><span class="sxs-lookup"><span data-stu-id="4754b-127"><a href="https://technet.microsoft.com/en-us/library/aa617823(v=ax.60)">Service agreements (form)</a></span></span></p></td>
<td><p><span data-ttu-id="4754b-128"><strong>Marge de commande de service</strong></span><span class="sxs-lookup"><span data-stu-id="4754b-128"><strong>Service order margin</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4754b-129">Traitement des demandes des clients</span><span class="sxs-lookup"><span data-stu-id="4754b-129">Handle customer inquiries</span></span></a></p></td>
<td><p><span data-ttu-id="4754b-130"><a href="https://technet.microsoft.com/en-us/library/aa554361(v=ax.60)">Commandes de service (écran)</a></span><span class="sxs-lookup"><span data-stu-id="4754b-130"><a href="https://technet.microsoft.com/en-us/library/aa554361(v=ax.60)">Service orders (form)</a></span></span></p></td>
<td><p><span data-ttu-id="4754b-131"><strong>Description du travail</strong></span><span class="sxs-lookup"><span data-stu-id="4754b-131"><strong>Work description</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="4754b-132"><a href="https://technet.microsoft.com/en-us/library/hh242789(v=ax.60)">Tableau d'affectation (écran)</a></span><span class="sxs-lookup"><span data-stu-id="4754b-132"><a href="https://technet.microsoft.com/en-us/library/hh242789(v=ax.60)">Dispatch board (form)</a></span></span></p></td>
<td><p><span data-ttu-id="4754b-133"><strong>Transaction - Abonnement</strong></span><span class="sxs-lookup"><span data-stu-id="4754b-133"><strong>Transaction - subscription</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="4754b-134"><strong>Transactions de frais d'abonnement</strong></span><span class="sxs-lookup"><span data-stu-id="4754b-134"><strong>Subscription fee transactions</strong></span></span></p></td>
</tr>
</tbody>
</table>


## <a name="integration-of-service-management"></a><span data-ttu-id="4754b-135">Intégration du module Gestion des services</span><span class="sxs-lookup"><span data-stu-id="4754b-135">Integration of Service management</span></span>

<span data-ttu-id="4754b-136">Le module Gestion des services peut être intégré aux modules suivants dans Microsoft Dynamics 365 for Finance and Operations :</span><span class="sxs-lookup"><span data-stu-id="4754b-136">Service management can be integrated with the following modules in Microsoft Dynamics 365 for Finance and Operations:</span></span>

  - [<span data-ttu-id="4754b-137">Ventes et marketing</span><span class="sxs-lookup"><span data-stu-id="4754b-137">Sales and marketing</span></span>](../sales-marketing/overview-sales-marketing.md)

  - [<span data-ttu-id="4754b-138">Ressources humaines</span><span class="sxs-lookup"><span data-stu-id="4754b-138">Human resources</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/index)

  


