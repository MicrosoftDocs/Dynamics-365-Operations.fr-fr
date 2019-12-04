---
title: Création de relations de tâches de service
description: Vous pouvez associer des tâches de service à des accords de service ou des commandes de service afin de décrire la tâche de service à exécuter pour l'accord ou la commande.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ed0800c4a650233190c6a33b1690790f0e2bf051
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/18/2019
ms.locfileid: "2814096"
---
# <a name="create-service-task-relations"></a><span data-ttu-id="f5f53-103">Création de relations de tâches de service</span><span class="sxs-lookup"><span data-stu-id="f5f53-103">Create service task relations</span></span>    

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f5f53-104">Vous pouvez associer des tâches de service à des accords de service ou des commandes de service afin de décrire la tâche de service à exécuter pour l'accord ou la commande.</span><span class="sxs-lookup"><span data-stu-id="f5f53-104">You can associate service tasks with service agreements or service orders in order to describe the service task to be completed for the agreement or order.</span></span> <span data-ttu-id="f5f53-105">Les techniciens de service et les clients ont accès à ces informations.</span><span class="sxs-lookup"><span data-stu-id="f5f53-105">This information is available to service technicians and customers.</span></span>

## <a name="create-a-relation-with-a-service-agreement"></a><span data-ttu-id="f5f53-106">Création d'une relation avec un accord de service</span><span class="sxs-lookup"><span data-stu-id="f5f53-106">Create a relation with a service agreement</span></span>

1.  <span data-ttu-id="f5f53-107">Cliquez sur **Gestion des services** \> **Commun** \> **Accords de service** \> **Accords de service**.</span><span class="sxs-lookup"><span data-stu-id="f5f53-107">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="f5f53-108">Sélectionnez un accord de service ou créez-en un.</span><span class="sxs-lookup"><span data-stu-id="f5f53-108">Select an existing service agreement, or create a new service agreement.</span></span>

3.  <span data-ttu-id="f5f53-109">Dans le volet Actions, cliquez sur le bouton **Tâches de service**.</span><span class="sxs-lookup"><span data-stu-id="f5f53-109">On the Action Pane, click the **Service tasks** button.</span></span>

4.  <span data-ttu-id="f5f53-110">Dans l'écran **Tâches de service**, appuyez sur Ctrl+N pour créer une ligne, puis sélectionnez une tâche de service dans la liste **Tâche de service** pour lier la tâche de service à l'accord de service.</span><span class="sxs-lookup"><span data-stu-id="f5f53-110">On the **Service tasks** form, press CTRL+N to create a new line, and then select a service task from the **Service task** list to attach the service task to the service agreement.</span></span>

5.  <span data-ttu-id="f5f53-111">Sous l'onglet **Description**, entrez les descriptions de note internes ou externes dans les champs à texte libre.</span><span class="sxs-lookup"><span data-stu-id="f5f53-111">On the **Description** tab, enter any internal or external note descriptions in the free text fields.</span></span>

6.  <span data-ttu-id="f5f53-112">Fermez l'écran pour sauvegarder l'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="f5f53-112">Close the form to save the record.</span></span>

<span data-ttu-id="f5f53-113">Répétez cette procédure jusqu'à ce que vous ayez créé toutes les relations de tâches de service nécessaires pour l'accord de service.</span><span class="sxs-lookup"><span data-stu-id="f5f53-113">Repeat this procedure until you have created all the necessary service task relations for the service agreement.</span></span> <span data-ttu-id="f5f53-114">Vous pouvez désormais spécifier ces tâches de service pour toutes les lignes d'accord associées.</span><span class="sxs-lookup"><span data-stu-id="f5f53-114">You can now specify these service tasks for any attached agreement lines.</span></span>

<span data-ttu-id="f5f53-115">Une relation de tâches de service créée dans une commande de service est disponible à partir de toutes les commandes de service associées à l'accord de service.</span><span class="sxs-lookup"><span data-stu-id="f5f53-115">A service tasks relation that is created on a service agreement is available from all service orders that are attached to the service agreement.</span></span>

## <a name="create-a-relation-with-a-service-order"></a><span data-ttu-id="f5f53-116">Création d'une relation avec une commande de service</span><span class="sxs-lookup"><span data-stu-id="f5f53-116">Create a relation with a service order</span></span>

1.  <span data-ttu-id="f5f53-117">Cliquez sur **Gestion des services** \> **Commun** \> **Commandes de service** \> **Commandes de service**.</span><span class="sxs-lookup"><span data-stu-id="f5f53-117">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="f5f53-118">Sélectionnez une commande de service ou créez-en une.</span><span class="sxs-lookup"><span data-stu-id="f5f53-118">Select an existing service order, or create a new service order.</span></span>

3.  <span data-ttu-id="f5f53-119">Dans le volet Actions, cliquez sur le bouton **Tâches de service**.</span><span class="sxs-lookup"><span data-stu-id="f5f53-119">On the Action Pane, click the **Service tasks** button.</span></span>

4.  <span data-ttu-id="f5f53-120">Dans l'écran **Tâches de service**, appuyez sur Ctrl+N pour créer une ligne, puis sélectionnez une tâche de service dans la liste **Tâche de service** pour lier les tâches de service à la commande de service.</span><span class="sxs-lookup"><span data-stu-id="f5f53-120">From the **Service tasks** form, press CTRL+N to create a new line, and then select a service task from the **Service task** list to attach the service tasks to the service order.</span></span>

5.  <span data-ttu-id="f5f53-121">Sous l'onglet **Description**, entrez les descriptions de note internes ou externes dans les champs à texte libre.</span><span class="sxs-lookup"><span data-stu-id="f5f53-121">On the **Description** tab, enter any internal or external note descriptions in the free text fields.</span></span>

6.  <span data-ttu-id="f5f53-122">Fermez l'écran pour sauvegarder l'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="f5f53-122">Close the form to save the record.</span></span>

<span data-ttu-id="f5f53-123">Répétez cette procédure jusqu'à ce que vous ayez créé toutes les relations de tâches de service nécessaires pour la commande de service.</span><span class="sxs-lookup"><span data-stu-id="f5f53-123">Repeat this procedure until you have created all the necessary service task relations for the service order.</span></span> <span data-ttu-id="f5f53-124">Vous pouvez désormais sélectionner la tâche de service pour laquelle vous avez créé une relation lors de la création des lignes de commande de service.</span><span class="sxs-lookup"><span data-stu-id="f5f53-124">You can now select the service task for which you have created the relation when you create service order lines.</span></span>

<span data-ttu-id="f5f53-125">Les relations de tâches de service créées dans une commande de service sont disponibles dans la commande de service spécifique.</span><span class="sxs-lookup"><span data-stu-id="f5f53-125">Service task relations that are created on a service order are available on the specific service order.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5f53-126">Voir également :</span><span class="sxs-lookup"><span data-stu-id="f5f53-126">See also</span></span>

[<span data-ttu-id="f5f53-127">Vue d'ensemble des tâches de service</span><span class="sxs-lookup"><span data-stu-id="f5f53-127">Service tasks overview</span></span>](service-tasks.md)


  


