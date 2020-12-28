---
title: Gestion des tâches dans le PDV
description: Cette rubrique décrit la gestion des tâches dans l'application PDV de Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: cc685fcd584fe2ab5cd9282e8fbefbd284d5b2a2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412330"
---
# <a name="task-management-in-pos"></a><span data-ttu-id="af7a2-103">Gestion des tâches dans le PDV</span><span class="sxs-lookup"><span data-stu-id="af7a2-103">Task management in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="af7a2-104">Cette rubrique décrit la gestion des tâches dans l'application PDV de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="af7a2-104">This topic describes task management in the Microsoft Dynamics 365 Commerce point of sale (POS) application.</span></span>

## <a name="overview"></a><span data-ttu-id="af7a2-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="af7a2-105">Overview</span></span>

<span data-ttu-id="af7a2-106">L'application PDV de Dynamics 365 Commerce dispose de fonctionnalités de gestion des tâches qui permettent aux responsables de magasin et aux employés de gérer les tâches et de mettre à jour leur statut.</span><span class="sxs-lookup"><span data-stu-id="af7a2-106">The Dynamics 365 Commerce POS application has task management features that let store managers and workers manage tasks and update task status.</span></span> <span data-ttu-id="af7a2-107">Les employés du magasin peuvent accéder aux tâches en sélectionnant la vignette **Tâches** sur la page d'accueil PDV ou en sélectionnant les notifications de tâche.</span><span class="sxs-lookup"><span data-stu-id="af7a2-107">Store workers can access tasks either by selecting the **Tasks** tile on the POS home page or by selecting task notifications.</span></span> <span data-ttu-id="af7a2-108">Par défaut, les employés du magasin sont redirigés vers l'onglet **Mes tâches**, où ils peuvent afficher les tâches qui leur sont affectées.</span><span class="sxs-lookup"><span data-stu-id="af7a2-108">By default, store workers are taken to the **My tasks** tab, where they can view the tasks that are assigned to them.</span></span> <span data-ttu-id="af7a2-109">Cependant, ils peuvent facilement basculer vers les onglets **Tâches en retard**, **Tâches en cours** et **Listes de tâches**.</span><span class="sxs-lookup"><span data-stu-id="af7a2-109">However, they can easily switch to the **Overdue tasks**, **Open tasks**, and **Task lists** tabs.</span></span>

## <a name="task-operations-for-store-managers"></a><span data-ttu-id="af7a2-110">Opérations de tâche pour les responsables de magasin</span><span class="sxs-lookup"><span data-stu-id="af7a2-110">Task operations for store managers</span></span>

<span data-ttu-id="af7a2-111">Les responsables de magasin peuvent effectuer les opérations de tâche suivantes dans l'application PDV à l'aide des boutons de la barre de commandes :</span><span class="sxs-lookup"><span data-stu-id="af7a2-111">Store managers can perform the following task operations in the POS application by using the buttons on the command bar:</span></span>

- <span data-ttu-id="af7a2-112">**Affecter** : permet d'affecter les tâches sélectionnées à un employé du magasin.</span><span class="sxs-lookup"><span data-stu-id="af7a2-112">**Assign** – Assign selected tasks to a store worker.</span></span>
- <span data-ttu-id="af7a2-113">**Statut de la tâche** : permet de modifier le staut des tâches sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="af7a2-113">**Task status** – Change the status of selected tasks.</span></span>
- <span data-ttu-id="af7a2-114">**Filtrer** : par défaut, seules les tâches actives sont affichées.</span><span class="sxs-lookup"><span data-stu-id="af7a2-114">**Filter** – By default, only active tasks are shown.</span></span> <span data-ttu-id="af7a2-115">Cependant, en appliquant des filtres, les responsables peuvent afficher toutes les tâches, même les tâches terminées ou annulées.</span><span class="sxs-lookup"><span data-stu-id="af7a2-115">However, by applying filters, managers can view all tasks, even tasks that have been completed or canceled.</span></span>
- <span data-ttu-id="af7a2-116">**Nouvelle tâche** : permet de créer une tâche dans une liste de tâches existante ou de créer une tâche à but unique.</span><span class="sxs-lookup"><span data-stu-id="af7a2-116">**New task** – Create a task under an existing task list, or create an single-purpose task.</span></span>

<span data-ttu-id="af7a2-117">Les employés du magasin peuvent effectuer les opérations de tâche suivantes dans l'application PDV à l'aide des boutons de la barre de commandes :</span><span class="sxs-lookup"><span data-stu-id="af7a2-117">Store workers can perform the following task operations in the POS application by using the buttons on the command bar:</span></span>

- <span data-ttu-id="af7a2-118">**Statut de la tâche** : permet de modifier le staut des tâches sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="af7a2-118">**Task status** – Change the status of selected tasks.</span></span>
- <span data-ttu-id="af7a2-119">**Filtrer** : par défaut, seules les tâches actives sont affichées.</span><span class="sxs-lookup"><span data-stu-id="af7a2-119">**Filter** – By default, only active tasks are shown.</span></span> <span data-ttu-id="af7a2-120">Cependant, en appliquant des filtres, les employés peuvent afficher toutes les tâches, même les tâches terminées ou annulées.</span><span class="sxs-lookup"><span data-stu-id="af7a2-120">However, by applying filters, workers can view all tasks, even tasks that have been completed or canceled.</span></span>

<span data-ttu-id="af7a2-121">L'illustration suivante présente l'onglet **Mes tâches** dans l'application PDV de Commerce.</span><span class="sxs-lookup"><span data-stu-id="af7a2-121">The following illustration shows the **My tasks** tab in the Commerce POS application.</span></span>

![Onglet Mes tâches dans l'application PDV de Commerce](media/POS-task-management.png)

<span data-ttu-id="af7a2-123">L'illustration suivante présente l'onglet **Liste de tâches**.</span><span class="sxs-lookup"><span data-stu-id="af7a2-123">The following illustration shows the **Task lists** tab.</span></span>

![Onglet Listes de tâches dans l'application PDV de Commerce](media/POS-task-lists-management.png)

## <a name="additional-resources"></a><span data-ttu-id="af7a2-125">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="af7a2-125">Additional resources</span></span>

[<span data-ttu-id="af7a2-126">Vue d'ensemble de la gestion des tâches</span><span class="sxs-lookup"><span data-stu-id="af7a2-126">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="af7a2-127">Configurer la gestion des tâches</span><span class="sxs-lookup"><span data-stu-id="af7a2-127">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="af7a2-128">Créer des listes de tâches et ajouter des tâches</span><span class="sxs-lookup"><span data-stu-id="af7a2-128">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="af7a2-129">Affecter des listes de tâches à des magasins ou des employés</span><span class="sxs-lookup"><span data-stu-id="af7a2-129">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)
