---
title: Gestion des tâches dans le PDV
description: Cette rubrique décrit la gestion des tâches dans l’application PDV de Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 18ba781795058de6228c712c6a22e59038e96368
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478360"
---
# <a name="task-management-in-pos"></a><span data-ttu-id="a7f98-103">Gestion des tâches dans le PDV</span><span class="sxs-lookup"><span data-stu-id="a7f98-103">Task management in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a7f98-104">Cette rubrique décrit la gestion des tâches dans l’application PDV de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a7f98-104">This topic describes task management in the Microsoft Dynamics 365 Commerce point of sale (POS) application.</span></span>

<span data-ttu-id="a7f98-105">L'application PDV de Dynamics 365 Commerce dispose de fonctionnalités de gestion des tâches qui permettent aux responsables de magasin et aux employés de gérer les tâches et de mettre à jour leur statut.</span><span class="sxs-lookup"><span data-stu-id="a7f98-105">The Dynamics 365 Commerce POS application has task management features that let store managers and workers manage tasks and update task status.</span></span> <span data-ttu-id="a7f98-106">Les employés du magasin peuvent accéder aux tâches en sélectionnant la vignette **Tâches** sur la page d'accueil PDV ou en sélectionnant les notifications de tâche.</span><span class="sxs-lookup"><span data-stu-id="a7f98-106">Store workers can access tasks either by selecting the **Tasks** tile on the POS home page or by selecting task notifications.</span></span> <span data-ttu-id="a7f98-107">Par défaut, les employés du magasin sont redirigés vers l'onglet **Mes tâches**, où ils peuvent afficher les tâches qui leur sont affectées.</span><span class="sxs-lookup"><span data-stu-id="a7f98-107">By default, store workers are taken to the **My tasks** tab, where they can view the tasks that are assigned to them.</span></span> <span data-ttu-id="a7f98-108">Cependant, ils peuvent facilement basculer vers les onglets **Tâches en retard**, **Tâches en cours** et **Listes de tâches**.</span><span class="sxs-lookup"><span data-stu-id="a7f98-108">However, they can easily switch to the **Overdue tasks**, **Open tasks**, and **Task lists** tabs.</span></span>

## <a name="task-operations-for-store-managers"></a><span data-ttu-id="a7f98-109">Opérations de tâche pour les responsables de magasin</span><span class="sxs-lookup"><span data-stu-id="a7f98-109">Task operations for store managers</span></span>

<span data-ttu-id="a7f98-110">Les responsables de magasin peuvent effectuer les opérations de tâche suivantes dans l'application PDV à l'aide des boutons de la barre de commandes :</span><span class="sxs-lookup"><span data-stu-id="a7f98-110">Store managers can perform the following task operations in the POS application by using the buttons on the command bar:</span></span>

- <span data-ttu-id="a7f98-111">**Affecter** : permet d'affecter les tâches sélectionnées à un employé du magasin.</span><span class="sxs-lookup"><span data-stu-id="a7f98-111">**Assign** – Assign selected tasks to a store worker.</span></span>
- <span data-ttu-id="a7f98-112">**Statut de la tâche** : permet de modifier le staut des tâches sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="a7f98-112">**Task status** – Change the status of selected tasks.</span></span>
- <span data-ttu-id="a7f98-113">**Filtrer** : par défaut, seules les tâches actives sont affichées.</span><span class="sxs-lookup"><span data-stu-id="a7f98-113">**Filter** – By default, only active tasks are shown.</span></span> <span data-ttu-id="a7f98-114">Cependant, en appliquant des filtres, les responsables peuvent afficher toutes les tâches, même les tâches terminées ou annulées.</span><span class="sxs-lookup"><span data-stu-id="a7f98-114">However, by applying filters, managers can view all tasks, even tasks that have been completed or canceled.</span></span>
- <span data-ttu-id="a7f98-115">**Nouvelle tâche** : permet de créer une tâche dans une liste de tâches existante ou de créer une tâche à but unique.</span><span class="sxs-lookup"><span data-stu-id="a7f98-115">**New task** – Create a task under an existing task list, or create an single-purpose task.</span></span>

<span data-ttu-id="a7f98-116">Les employés du magasin peuvent effectuer les opérations de tâche suivantes dans l'application PDV à l'aide des boutons de la barre de commandes :</span><span class="sxs-lookup"><span data-stu-id="a7f98-116">Store workers can perform the following task operations in the POS application by using the buttons on the command bar:</span></span>

- <span data-ttu-id="a7f98-117">**Statut de la tâche** : permet de modifier le staut des tâches sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="a7f98-117">**Task status** – Change the status of selected tasks.</span></span>
- <span data-ttu-id="a7f98-118">**Filtrer** : par défaut, seules les tâches actives sont affichées.</span><span class="sxs-lookup"><span data-stu-id="a7f98-118">**Filter** – By default, only active tasks are shown.</span></span> <span data-ttu-id="a7f98-119">Cependant, en appliquant des filtres, les employés peuvent afficher toutes les tâches, même les tâches terminées ou annulées.</span><span class="sxs-lookup"><span data-stu-id="a7f98-119">However, by applying filters, workers can view all tasks, even tasks that have been completed or canceled.</span></span>

<span data-ttu-id="a7f98-120">L'illustration suivante présente l'onglet **Mes tâches** dans l'application PDV de Commerce.</span><span class="sxs-lookup"><span data-stu-id="a7f98-120">The following illustration shows the **My tasks** tab in the Commerce POS application.</span></span>

![Onglet Mes tâches dans l'application PDV de Commerce](media/POS-task-management.png)

<span data-ttu-id="a7f98-122">L'illustration suivante présente l'onglet **Liste de tâches**.</span><span class="sxs-lookup"><span data-stu-id="a7f98-122">The following illustration shows the **Task lists** tab.</span></span>

![Onglet Listes de tâches dans l'application PDV de Commerce](media/POS-task-lists-management.png)

## <a name="additional-resources"></a><span data-ttu-id="a7f98-124">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="a7f98-124">Additional resources</span></span>

[<span data-ttu-id="a7f98-125">Vue d'ensemble de la gestion des tâches</span><span class="sxs-lookup"><span data-stu-id="a7f98-125">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="a7f98-126">Configurer la gestion des tâches</span><span class="sxs-lookup"><span data-stu-id="a7f98-126">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="a7f98-127">Créer des listes de tâches et ajouter des tâches</span><span class="sxs-lookup"><span data-stu-id="a7f98-127">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="a7f98-128">Affecter des listes de tâches à des magasins ou des employés</span><span class="sxs-lookup"><span data-stu-id="a7f98-128">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
