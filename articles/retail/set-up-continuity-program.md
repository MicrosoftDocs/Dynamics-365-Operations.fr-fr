---
title: "Paramétrez un programme de continuité pour un centre d'appels"
description: "Cet article décrit le paramétrage d'un programme périodique pour un centre d'appels."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16081
ms.assetid: 426a9be7-a931-4780-b372-e06f6083dd60
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 0fa2c5aaf6953eed75729017cca8cf3c2220e80d
ms.contentlocale: fr-fr
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-a-continuity-program-for-a-call-center"></a><span data-ttu-id="f5d90-103">Paramétrez un programme de continuité pour un centre d'appels</span><span class="sxs-lookup"><span data-stu-id="f5d90-103">Set up a continuity program for a call center</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="f5d90-104">Cet article décrit le paramétrage d'un programme périodique pour un centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="f5d90-104">This article describes how to set up a continuity program for a call center.</span></span>

<span data-ttu-id="f5d90-105">Dans un programme périodique, qui est également appelé programme de commande récurrent, des clients reçoivent régulièrement des expéditions de produits selon un programme prédéfini.</span><span class="sxs-lookup"><span data-stu-id="f5d90-105">In a continuity program, which is also known as a recurring order program, customers receive regular product shipments according to a predefined schedule.</span></span> <span data-ttu-id="f5d90-106">Chaque expédition peut contenir un produit différent, comme dans le cas d'un club « Livre du mois », ou le même produit peut être envoyé à plusieurs reprises.</span><span class="sxs-lookup"><span data-stu-id="f5d90-106">Each shipment can contain a different product, as in the case of a book-of-the-month club, or the same product can be sent repeatedly.</span></span> <span data-ttu-id="f5d90-107">Pour paramétrer un programme périodique, effectuez les tâches suivantes.</span><span class="sxs-lookup"><span data-stu-id="f5d90-107">To set up a continuity program, you must complete the following tasks.</span></span>

1.  <span data-ttu-id="f5d90-108">Définissez les paramètres périodiques dans la page **Paramètres du centre d'appels**.</span><span class="sxs-lookup"><span data-stu-id="f5d90-108">Set the continuity parameters on the **Call center parameters** page.</span></span>
2.  <span data-ttu-id="f5d90-109">Créez un programme périodique qui spécifie des détails tels que l'échéancier de paiement, l'échéance des expéditions, et si la facturation est immédiate.</span><span class="sxs-lookup"><span data-stu-id="f5d90-109">Create a continuity program that specifies details such as the payment schedule, the timing of the shipments, and whether billing is up front.</span></span> <span data-ttu-id="f5d90-110">Vous devez également ajouter une liste des produits inclus dans le programme périodique.</span><span class="sxs-lookup"><span data-stu-id="f5d90-110">You must also add a list of products that are included in the continuity program.</span></span> <span data-ttu-id="f5d90-111">Chaque produit reçoit un numéro d'identité d'événement qui est affecté de manière séquentielle, en commençant par 1.</span><span class="sxs-lookup"><span data-stu-id="f5d90-111">Each product receives an event ID number that is assigned sequentially, beginning with 1.</span></span> <span data-ttu-id="f5d90-112">Les ID d'événement déterminent la commande où sont envoyés les produits.</span><span class="sxs-lookup"><span data-stu-id="f5d90-112">The event IDs determine the order that products are sent in.</span></span>
    -   <span data-ttu-id="f5d90-113">Lorsque les clients reçoivent un produit différent dans chaque expédition, les produits sont envoyés selon un ordre séquentiel, basé sur leurs ID événement, en commençant par l'événement actuel.</span><span class="sxs-lookup"><span data-stu-id="f5d90-113">If customers receive a different product in each shipment, the products are sent in sequential order, based on their event IDs and beginning with the current event.</span></span>
    -   <span data-ttu-id="f5d90-114">Si les clients reçoivent le même produit dans chaque expédition, la liste contient un seul produit ayant un ID événement.</span><span class="sxs-lookup"><span data-stu-id="f5d90-114">If customers receive the same product in each shipment, the list contains only one product that has one event ID.</span></span> <span data-ttu-id="f5d90-115">Le même événement se produit à plusieurs reprises.</span><span class="sxs-lookup"><span data-stu-id="f5d90-115">The same event occurs repeatedly.</span></span> <span data-ttu-id="f5d90-116">Vous pouvez spécifier le nombre de répétitions de chaque événement.</span><span class="sxs-lookup"><span data-stu-id="f5d90-116">You can specify how many times each event is repeated.</span></span>

3.  <span data-ttu-id="f5d90-117">Créez un produit parent qui représente le programme de périodicité créé à la tâche 2.</span><span class="sxs-lookup"><span data-stu-id="f5d90-117">Create a parent product that represents the continuity program that you created in task 2.</span></span> <span data-ttu-id="f5d90-118">Si vous ajoutez ce produit à une commande client, la page **Périodicité** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="f5d90-118">If you add this product to a sales order, the **Continuity** page opens.</span></span> <span data-ttu-id="f5d90-119">Vous pouvez ensuite utiliser cette page pour créer la commande périodique réelle.</span><span class="sxs-lookup"><span data-stu-id="f5d90-119">You can then use that page to create the actual continuity order.</span></span> <span data-ttu-id="f5d90-120">Le produit parent ne spécifie pas les produits individuels que le client reçoit dans chaque expédition.</span><span class="sxs-lookup"><span data-stu-id="f5d90-120">The parent product doesn't specify the individual products that the customer receives in each shipment.</span></span>

<span data-ttu-id="f5d90-121">Après avoir paramétré un programme périodique comme décrit ci-dessus, vous pouvez créer une commande périodique pour un client.</span><span class="sxs-lookup"><span data-stu-id="f5d90-121">After you've set up a continuity program as described above, you can create a continuity order for a customer.</span></span> <span data-ttu-id="f5d90-122">Vous devrez également peut-être effectuer les tâches de maintenance supplémentaires suivantes.</span><span class="sxs-lookup"><span data-stu-id="f5d90-122">You might also have to perform the following additional maintenance tasks.</span></span>

-   <span data-ttu-id="f5d90-123">**Mise à jour de la période de l'événement périodique actuel** – Permet de paramétrer un traitement par lots qui indique au système quelle est la période de l'événement actuel.</span><span class="sxs-lookup"><span data-stu-id="f5d90-123">**Update the current continuity event period** – Set up a batch job that tells the system what the current event period is.</span></span>
-   <span data-ttu-id="f5d90-124">**Créer des commandes enfant périodiques** – Permet de créer des commandes enfant à partir de la commande périodique parent.</span><span class="sxs-lookup"><span data-stu-id="f5d90-124">**Create continuity child orders** – Create child orders from the parent continuity order.</span></span>
-   <span data-ttu-id="f5d90-125">**Traiter les paiements périodiques** – Permet de traiter la facturation et les notifications pour les paiements associés aux commandes client périodiques.</span><span class="sxs-lookup"><span data-stu-id="f5d90-125">**Process continuity payments** – Process billing and notifications for payments that are associated with continuity sales orders.</span></span>
-   <span data-ttu-id="f5d90-126">**Étendre les lignes périodiques** (le cas échéant) – Permet de prolonger le nombre de répétitions possibles d'un événement périodique.</span><span class="sxs-lookup"><span data-stu-id="f5d90-126">**Extend continuity lines** (if required) – Extend the number of times that a continuity event can be repeated.</span></span> <span data-ttu-id="f5d90-127">La récurrence des expéditions peut ensuite s'étendre au-delà de la limite qui a été définie dans le champ **Seuil de répétition de la périodicité** dans les paramètres du centre d'appels.</span><span class="sxs-lookup"><span data-stu-id="f5d90-127">The repetition of shipments can then extend beyond the limit that was set in the **Continuity repeat threshold** field in the call center parameters.</span></span>
-   <span data-ttu-id="f5d90-128">**Réaliser une mise à jour périodique** (le cas échéant) – Permet de synchroniser les modifications entre le programme périodique et des commandes client parentes périodiques.</span><span class="sxs-lookup"><span data-stu-id="f5d90-128">**Perform a continuity update** (if required) – Synchronize changes between the continuity program and the continuity parent sales orders.</span></span>
-   <span data-ttu-id="f5d90-129">**Clôturer les commandes et lignes parentes périodiques** – Permet de clôturer les commandes périodiques.</span><span class="sxs-lookup"><span data-stu-id="f5d90-129">**Close continuity parent lines and orders** – Close continuity orders.</span></span>





