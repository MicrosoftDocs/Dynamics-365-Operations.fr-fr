---
title: Créer des listes de tâches et ajouter des tâches
description: Cette rubrique décrit comment créer des listes de tâches et y ajouter des tâches dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 1cab31784db9f3242dce20e98762088436a5a8f8
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412331"
---
# <a name="create-task-lists-and-add-tasks"></a><span data-ttu-id="033a6-103">Créer des listes de tâches et ajouter des tâches</span><span class="sxs-lookup"><span data-stu-id="033a6-103">Create task lists and add tasks</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="033a6-104">Cette rubrique décrit comment créer des listes de tâches et y ajouter des tâches dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="033a6-104">This topic describes how to create task lists and add tasks to them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="033a6-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="033a6-105">Overview</span></span>

<span data-ttu-id="033a6-106">Une *tâche* définit un travail spécifique ou une action qu'une personne doit effectuer au plus tard à la date d'échéance spécifiée.</span><span class="sxs-lookup"><span data-stu-id="033a6-106">A *task* defines a specific piece of work or an action that someone must complete on or before a specified due date.</span></span> <span data-ttu-id="033a6-107">Dans Dynamics 365 Commerce, une tâche peut inclure des instructions détaillées et des informations sur la personne à contacter.</span><span class="sxs-lookup"><span data-stu-id="033a6-107">In Dynamics 365 Commerce, a task can include detailed instructions and information about a contact person.</span></span> <span data-ttu-id="033a6-108">Elle peut également inclure des liens vers des opérations du back-office, des opérations PDV ou des pages de site, pour aider à améliorer la productivité et fournir le contexte dont le propriétaire de la tâche a besoin pour effectuer efficacement la tâche.</span><span class="sxs-lookup"><span data-stu-id="033a6-108">It can also include links to back-office operations, point of sale (POS) operations, or site pages, to help improve productivity and provide the context that the task owner requires to complete the task efficiently.</span></span>

<span data-ttu-id="033a6-109">Une *liste de tâches* est un ensemble de tâches qui doivent être effectuées dans le cadre d'un processus métier.</span><span class="sxs-lookup"><span data-stu-id="033a6-109">A *task list* is a collection of tasks that must be completed as part of a business process.</span></span> <span data-ttu-id="033a6-110">Par exemple, il peut s'agir d'une liste de tâches qu'un nouveau employé doit effectuer pendant l'intégration, d'une liste de tâches pour les caissiers qui travaillent le soir ou d'une liste de tâches qui doit être effectuée pour préparer le magasin pour la période des fêtes à venir.</span><span class="sxs-lookup"><span data-stu-id="033a6-110">For example, there might be a task list that a new worker must complete during onboarding, a task list for cashiers who work evening shifts, or a task list that must be completed to prepare the store for an upcoming holiday season.</span></span> <span data-ttu-id="033a6-111">Dans Commerce, chaque liste de tâches ayant une date cible peut être affectée à plusieurs magasins ou employés, et elle peut être configurée pour se reproduire.</span><span class="sxs-lookup"><span data-stu-id="033a6-111">In Commerce, every task list that has a target date can be assigned to any number of stores or employees, and it can be configured to recur.</span></span>

<span data-ttu-id="033a6-112">Les responsables et les employés peuvent créer des listes de tâches dans le back-office Commerce, puis les affecter à un ensemble de magasins.</span><span class="sxs-lookup"><span data-stu-id="033a6-112">Both managers and workers can create task lists in Commerce back office, and then assign them to a set of stores.</span></span>

## <a name="create-a-task-list"></a><span data-ttu-id="033a6-113">Créer une liste de tâches</span><span class="sxs-lookup"><span data-stu-id="033a6-113">Create a task list</span></span>

<span data-ttu-id="033a6-114">Pour créer une liste de tâches, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="033a6-114">To create a task list, follow these steps.</span></span>

1. <span data-ttu-id="033a6-115">Accédez à **Commerce et vente au détail \> Gestion des tâches \> Administration de la gestion des tâches**.</span><span class="sxs-lookup"><span data-stu-id="033a6-115">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="033a6-116">Sélectionnez **Nouveau**, puis entrez des valeurs dans les champs **Nom**, **Description** et **Propriétaire**.</span><span class="sxs-lookup"><span data-stu-id="033a6-116">Select **New**, and then enter values in the **Name**, **Description**, and **Owner** fields.</span></span>
1. <span data-ttu-id="033a6-117">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="033a6-117">Select **Save**.</span></span>

## <a name="add-tasks-to-a-task-list"></a><span data-ttu-id="033a6-118">Ajouter des tâches à une liste de tâches</span><span class="sxs-lookup"><span data-stu-id="033a6-118">Add tasks to a task list</span></span>

<span data-ttu-id="033a6-119">Pour ajouter des tâches à une liste de tâches, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="033a6-119">To add tasks to a task list, follow these steps.</span></span>
 
1. <span data-ttu-id="033a6-120">Dans le raccourci **Tâches** d'une liste de tâches existante, sélectionnez **Nouveau** pour ajouter une tâche.</span><span class="sxs-lookup"><span data-stu-id="033a6-120">On the **Tasks** FastTab of an existing task list, select **New** to add a task.</span></span>
1. <span data-ttu-id="033a6-121">Dans la boîte de dialogue **Créer une tâche**, dans le champ **Nom**, entrez un nom pour la tâche.</span><span class="sxs-lookup"><span data-stu-id="033a6-121">In the **Create a new task** dialog box, in the **Name** field, enter a name for the task.</span></span>
1. <span data-ttu-id="033a6-122">Dans le champ **Décalage des données d'échéance par rapport à la date cible**, entrez une valeur entière positive ou négative.</span><span class="sxs-lookup"><span data-stu-id="033a6-122">In the **Due data offset from target date** field, enter a positive or negative integer value.</span></span> <span data-ttu-id="033a6-123">Par exemple, entrez **-2** si la tâche doit être terminée deux jours avant la date d'échéance de la liste de tâches.</span><span class="sxs-lookup"><span data-stu-id="033a6-123">For example, enter **-2** if the task should be completed two days before the task list's due date.</span></span>
1. <span data-ttu-id="033a6-124">Dans le champ **Notes**, entrez des instructions détaillées.</span><span class="sxs-lookup"><span data-stu-id="033a6-124">In the **Notes** field, enter detailed instructions.</span></span>
1. <span data-ttu-id="033a6-125">Dans le champ **Personne à contacter**, entrez le nom d'un expert en la matière que le propriétaire de la tâche peut contacter en cas de besoin.</span><span class="sxs-lookup"><span data-stu-id="033a6-125">In the **Contact person** field, enter the name of a subject matter expert that the task owner can contact if he or she needs help.</span></span>
1. <span data-ttu-id="033a6-126">Dans le champ **Lien de la tâche**, entrez un lien en fonction de la nature de la tâche.</span><span class="sxs-lookup"><span data-stu-id="033a6-126">In the **Task link** field, enter a link, based on the nature of the task.</span></span>

> [!TIP]
> <span data-ttu-id="033a6-127">Bien qu'il soit possible d'utiliser le champ **Affecté à** pour affecter des tâches à une personne tout en créant une liste de tâches, il est déconseillé d'affecter des tâches pendant la création d'une liste de tâches.</span><span class="sxs-lookup"><span data-stu-id="033a6-127">Although you can use the **Assigned to** field to assign tasks to someone while you're creating a task list, we recommend that you avoid assigning tasks during task list creation.</span></span> <span data-ttu-id="033a6-128">À la place, affectez les tâches une fois la liste instanciée pour des magasins individuels.</span><span class="sxs-lookup"><span data-stu-id="033a6-128">Instead, assign the tasks after the list is instantiated for individual stores.</span></span>

## <a name="use-task-links-to-help-improve-worker-productivity"></a><span data-ttu-id="033a6-129">Utiliser les liens de tâche pour aider à améliorer la productivité des employés</span><span class="sxs-lookup"><span data-stu-id="033a6-129">Use task links to help improve worker productivity</span></span>

<span data-ttu-id="033a6-130">Commerce vous permet de lier des tâches à des opérations PDV spécifiques, comme l'exécution d'un rapport de vente, l'affichage d'une vidéo de formation en ligne pour l'orientation des nouveaux employés ou l'exécution d'une opération du back-office.</span><span class="sxs-lookup"><span data-stu-id="033a6-130">Commerce lets you link tasks to specific POS operations, such as running a sales report, viewing an online training video for new employee orientation, or performing a back-office operation.</span></span> <span data-ttu-id="033a6-131">Cette fonctionnalité aide les propriétaires de tâche à obtenir les informations nécessaires pour effectuer efficacement une tâche.</span><span class="sxs-lookup"><span data-stu-id="033a6-131">This feature helps task owners get the information that they need to complete a task efficiently.</span></span>

<span data-ttu-id="033a6-132">Pour ajouter des liens de tâche lorsque vous créez une tâche, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="033a6-132">To add task links while you create a task, follow these steps.</span></span>

1. <span data-ttu-id="033a6-133">Dans le raccourci **Tâches** d'une liste de tâches existante, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="033a6-133">On the **Tasks** FastTab of an existing task list, select **Edit**.</span></span>
1. <span data-ttu-id="033a6-134">Dans la boîte de dialogue **Modifier la tâche**, dans le champ **Lien de la tâche**, sélectionnez une ou plusieurs des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="033a6-134">In the **Edit task** dialog box, in the **Task link** field, select one or more of the following options:</span></span>

    - <span data-ttu-id="033a6-135">Sélectionnez **Option de menu** pour configurer une opération du back-office, par exemple « Kits de produits ».</span><span class="sxs-lookup"><span data-stu-id="033a6-135">Select **Menu item** to configure a back-office operation, such as "Product kits."</span></span>
    - <span data-ttu-id="033a6-136">Sélectionnez **Opération PDV** pour configurer une opération PDV, par exemple « Rapports de vente ».</span><span class="sxs-lookup"><span data-stu-id="033a6-136">Select **POS Operation** to configure a POS operation, such as "Sales reports."</span></span>
    - <span data-ttu-id="033a6-137">Sélectionnez **URL** pour configurer une URL absolue.</span><span class="sxs-lookup"><span data-stu-id="033a6-137">Select **URL** to configure an absolute URL.</span></span>

<span data-ttu-id="033a6-138">L'illustration suivante présente la sélection de liens de tâche dans la boite de dialogue **Modifier la tâche**.</span><span class="sxs-lookup"><span data-stu-id="033a6-138">The following illustration shows the selection of task links in the **Edit task** dialog box.</span></span>

![Sélection de liens de tâche dans la boîte de dialogue Modifier la tâche](media/HQ-POS-Tasks-Linking.png)

### <a name="configure-a-pos-operation-so-that-it-can-be-linked-to-a-task"></a><span data-ttu-id="033a6-140">Configurer une opération PDV pour pouvoir la lier à une tâche</span><span class="sxs-lookup"><span data-stu-id="033a6-140">Configure a POS operation so that it can be linked to a task</span></span>

<span data-ttu-id="033a6-141">Pour configurer une opération PDV afin qu'elle puisse être liée à une tâche, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="033a6-141">To configure a POS operation so that it can be linked to a task, follow these steps.</span></span>

1. <span data-ttu-id="033a6-142">Accédez à **Commerce et vente au détail \> Paramétrage du canal \> Paramétrage du PDV \> PDV \> Opérations PDV**.</span><span class="sxs-lookup"><span data-stu-id="033a6-142">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> POS operations**.</span></span>
1. <span data-ttu-id="033a6-143">Sélectionnez **Modifier**, recherchez l'opération PDV, puis activez la case à cocher **Activer la gestion des tâches** correspondante.</span><span class="sxs-lookup"><span data-stu-id="033a6-143">Select **Edit**, find the POS operation, and then select the **Enable Task Management** check box for it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="033a6-144">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="033a6-144">Additional resources</span></span>

[<span data-ttu-id="033a6-145">Vue d'ensemble de la gestion des tâches</span><span class="sxs-lookup"><span data-stu-id="033a6-145">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="033a6-146">Configurer la gestion des tâches</span><span class="sxs-lookup"><span data-stu-id="033a6-146">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="033a6-147">Affecter des listes de tâches à des magasins ou des employés</span><span class="sxs-lookup"><span data-stu-id="033a6-147">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)

[<span data-ttu-id="033a6-148">Gestion des tâches dans le PDV</span><span class="sxs-lookup"><span data-stu-id="033a6-148">Task management in POS</span></span>](task-mgmt-POS.md)
