---
title: Créer des listes de tâches et ajouter des tâches
description: Cette rubrique décrit comment créer des listes de tâches et y ajouter des tâches dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: f3fcfae9f4ab458b4f14f18859f22fc25bf98623
ms.sourcegitcommit: cabd991fda2bfcabb55db84c225b24a7bb061631
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6027622"
---
# <a name="create-task-lists-and-add-tasks"></a><span data-ttu-id="febed-103">Créer des listes de tâches et ajouter des tâches</span><span class="sxs-lookup"><span data-stu-id="febed-103">Create task lists and add tasks</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="febed-104">Cette rubrique décrit comment créer des listes de tâches et y ajouter des tâches dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="febed-104">This topic describes how to create task lists and add tasks to them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="febed-105">Une *tâche* définit un travail spécifique ou une action qu’une personne doit effectuer au plus tard à la date d’échéance spécifiée.</span><span class="sxs-lookup"><span data-stu-id="febed-105">A *task* defines a specific piece of work or an action that someone must complete on or before a specified due date.</span></span> <span data-ttu-id="febed-106">Dans Dynamics 365 Commerce, une tâche peut inclure des instructions détaillées et des informations sur la personne à contacter.</span><span class="sxs-lookup"><span data-stu-id="febed-106">In Dynamics 365 Commerce, a task can include detailed instructions and information about a contact person.</span></span> <span data-ttu-id="febed-107">Elle peut également inclure des liens vers des opérations du back-office, des opérations PDV ou des pages de site, pour aider à améliorer la productivité et fournir le contexte dont le propriétaire de la tâche a besoin pour effectuer efficacement la tâche.</span><span class="sxs-lookup"><span data-stu-id="febed-107">It can also include links to back-office operations, point of sale (POS) operations, or site pages, to help improve productivity and provide the context that the task owner requires to complete the task efficiently.</span></span>

<span data-ttu-id="febed-108">Une *liste de tâches* est un ensemble de tâches qui doivent être effectuées dans le cadre d’un processus métier.</span><span class="sxs-lookup"><span data-stu-id="febed-108">A *task list* is a collection of tasks that must be completed as part of a business process.</span></span> <span data-ttu-id="febed-109">Par exemple, il peut s’agir d’une liste de tâches qu’un nouveau employé doit effectuer pendant l’intégration, d’une liste de tâches pour les caissiers qui travaillent le soir ou d’une liste de tâches qui doit être effectuée pour préparer le magasin pour la période des fêtes à venir.</span><span class="sxs-lookup"><span data-stu-id="febed-109">For example, there might be a task list that a new worker must complete during onboarding, a task list for cashiers who work evening shifts, or a task list that must be completed to prepare the store for an upcoming holiday season.</span></span> <span data-ttu-id="febed-110">Dans Commerce, chaque liste de tâches ayant une date cible peut être affectée à plusieurs magasins ou employés, et elle peut être configurée pour se reproduire.</span><span class="sxs-lookup"><span data-stu-id="febed-110">In Commerce, every task list that has a target date can be assigned to any number of stores or employees, and it can be configured to recur.</span></span>

<span data-ttu-id="febed-111">Les responsables et les employés peuvent créer des listes de tâches dans le back-office Commerce, puis les affecter à un ensemble de magasins.</span><span class="sxs-lookup"><span data-stu-id="febed-111">Both managers and workers can create task lists in Commerce back office, and then assign them to a set of stores.</span></span>

## <a name="create-a-task-list"></a><span data-ttu-id="febed-112">Créer une liste de tâches</span><span class="sxs-lookup"><span data-stu-id="febed-112">Create a task list</span></span>

<span data-ttu-id="febed-113">Pour créer une liste de tâches, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="febed-113">To create a task list, follow these steps.</span></span>

1. <span data-ttu-id="febed-114">Accédez à **Commerce et vente au détail \> Gestion des tâches \> Administration de la gestion des tâches**.</span><span class="sxs-lookup"><span data-stu-id="febed-114">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="febed-115">Sélectionnez **Nouveau**, puis entrez des valeurs dans les champs **Nom**, **Description** et **Propriétaire**.</span><span class="sxs-lookup"><span data-stu-id="febed-115">Select **New**, and then enter values in the **Name**, **Description**, and **Owner** fields.</span></span>
1. <span data-ttu-id="febed-116">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="febed-116">Select **Save**.</span></span>

## <a name="add-tasks-to-a-task-list"></a><span data-ttu-id="febed-117">Ajouter des tâches à une liste de tâches</span><span class="sxs-lookup"><span data-stu-id="febed-117">Add tasks to a task list</span></span>

<span data-ttu-id="febed-118">Pour ajouter des tâches à une liste de tâches, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="febed-118">To add tasks to a task list, follow these steps.</span></span>
 
1. <span data-ttu-id="febed-119">Dans le raccourci **Tâches** d’une liste de tâches existante, sélectionnez **Nouveau** pour ajouter une tâche.</span><span class="sxs-lookup"><span data-stu-id="febed-119">On the **Tasks** FastTab of an existing task list, select **New** to add a task.</span></span>
1. <span data-ttu-id="febed-120">Dans la boîte de dialogue **Créer une tâche**, dans le champ **Nom**, entrez un nom pour la tâche.</span><span class="sxs-lookup"><span data-stu-id="febed-120">In the **Create a new task** dialog box, in the **Name** field, enter a name for the task.</span></span>
1. <span data-ttu-id="febed-121">Dans le champ **Décalage des données d’échéance par rapport à la date cible**, entrez une valeur entière positive ou négative.</span><span class="sxs-lookup"><span data-stu-id="febed-121">In the **Due data offset from target date** field, enter a positive or negative integer value.</span></span> <span data-ttu-id="febed-122">Par exemple, entrez **-2** si la tâche doit être terminée deux jours avant la date d’échéance de la liste de tâches.</span><span class="sxs-lookup"><span data-stu-id="febed-122">For example, enter **-2** if the task should be completed two days before the task list's due date.</span></span>
1. <span data-ttu-id="febed-123">Dans le champ **Notes**, entrez des instructions détaillées.</span><span class="sxs-lookup"><span data-stu-id="febed-123">In the **Notes** field, enter detailed instructions.</span></span>
1. <span data-ttu-id="febed-124">Dans le champ **Personne à contacter**, entrez le nom d’un expert en la matière que le propriétaire de la tâche peut contacter en cas de besoin.</span><span class="sxs-lookup"><span data-stu-id="febed-124">In the **Contact person** field, enter the name of a subject matter expert that the task owner can contact if the task owner needs help.</span></span>
1. <span data-ttu-id="febed-125">Dans le champ **Lien de la tâche**, entrez un lien en fonction de la nature de la tâche.</span><span class="sxs-lookup"><span data-stu-id="febed-125">In the **Task link** field, enter a link, based on the nature of the task.</span></span>

> [!TIP]
> <span data-ttu-id="febed-126">Bien qu’il soit possible d’utiliser le champ **Affecté à** pour affecter des tâches à une personne tout en créant une liste de tâches, il est déconseillé d’affecter des tâches pendant la création d’une liste de tâches.</span><span class="sxs-lookup"><span data-stu-id="febed-126">Although you can use the **Assigned to** field to assign tasks to someone while you're creating a task list, we recommend that you avoid assigning tasks during task list creation.</span></span> <span data-ttu-id="febed-127">À la place, affectez les tâches une fois la liste instanciée pour des magasins individuels.</span><span class="sxs-lookup"><span data-stu-id="febed-127">Instead, assign the tasks after the list is instantiated for individual stores.</span></span>

## <a name="use-task-links-to-help-improve-worker-productivity"></a><span data-ttu-id="febed-128">Utiliser les liens de tâche pour aider à améliorer la productivité des employés</span><span class="sxs-lookup"><span data-stu-id="febed-128">Use task links to help improve worker productivity</span></span>

<span data-ttu-id="febed-129">Commerce vous permet de lier des tâches à des opérations PDV spécifiques, comme l’exécution d’un rapport de vente, l’affichage d’une vidéo de formation en ligne pour l’orientation des nouveaux employés ou l’exécution d’une opération du back-office.</span><span class="sxs-lookup"><span data-stu-id="febed-129">Commerce lets you link tasks to specific POS operations, such as running a sales report, viewing an online training video for new employee orientation, or performing a back-office operation.</span></span> <span data-ttu-id="febed-130">Cette fonctionnalité aide les propriétaires de tâche à obtenir les informations nécessaires pour effectuer efficacement une tâche.</span><span class="sxs-lookup"><span data-stu-id="febed-130">This feature helps task owners get the information that they need to complete a task efficiently.</span></span>

<span data-ttu-id="febed-131">Pour ajouter des liens de tâche lorsque vous créez une tâche, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="febed-131">To add task links while you create a task, follow these steps.</span></span>

1. <span data-ttu-id="febed-132">Dans le raccourci **Tâches** d’une liste de tâches existante, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="febed-132">On the **Tasks** FastTab of an existing task list, select **Edit**.</span></span>
1. <span data-ttu-id="febed-133">Dans la boîte de dialogue **Modifier la tâche**, dans le champ **Lien de la tâche**, sélectionnez une ou plusieurs des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="febed-133">In the **Edit task** dialog box, in the **Task link** field, select one or more of the following options:</span></span>

    - <span data-ttu-id="febed-134">Sélectionnez **Option de menu** pour configurer une opération du back-office, par exemple « Kits de produits ».</span><span class="sxs-lookup"><span data-stu-id="febed-134">Select **Menu item** to configure a back-office operation, such as "Product kits."</span></span>
    - <span data-ttu-id="febed-135">Sélectionnez **Opération PDV** pour configurer une opération PDV, par exemple « Rapports de vente ».</span><span class="sxs-lookup"><span data-stu-id="febed-135">Select **POS Operation** to configure a POS operation, such as "Sales reports."</span></span>
    - <span data-ttu-id="febed-136">Sélectionnez **URL** pour configurer une URL absolue.</span><span class="sxs-lookup"><span data-stu-id="febed-136">Select **URL** to configure an absolute URL.</span></span>

<span data-ttu-id="febed-137">L’illustration suivante présente la sélection de liens de tâche dans la boite de dialogue **Modifier la tâche**.</span><span class="sxs-lookup"><span data-stu-id="febed-137">The following illustration shows the selection of task links in the **Edit task** dialog box.</span></span>

![Sélection de liens de tâche dans la boîte de dialogue Modifier la tâche](media/HQ-POS-Tasks-Linking.png)

### <a name="configure-a-pos-operation-so-that-it-can-be-linked-to-a-task"></a><span data-ttu-id="febed-139">Configurer une opération PDV pour pouvoir la lier à une tâche</span><span class="sxs-lookup"><span data-stu-id="febed-139">Configure a POS operation so that it can be linked to a task</span></span>

<span data-ttu-id="febed-140">Pour configurer une opération PDV afin qu’elle puisse être liée à une tâche, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="febed-140">To configure a POS operation so that it can be linked to a task, follow these steps.</span></span>

1. <span data-ttu-id="febed-141">Accédez à **Commerce et vente au détail \> Paramétrage du canal \> Paramétrage du PDV \> PDV \> Opérations PDV**.</span><span class="sxs-lookup"><span data-stu-id="febed-141">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> POS operations**.</span></span>
1. <span data-ttu-id="febed-142">Sélectionnez **Modifier**, recherchez l’opération PDV, puis activez la case à cocher **Activer la gestion des tâches** correspondante.</span><span class="sxs-lookup"><span data-stu-id="febed-142">Select **Edit**, find the POS operation, and then select the **Enable Task Management** check box for it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="febed-143">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="febed-143">Additional resources</span></span>

[<span data-ttu-id="febed-144">Vue d’ensemble de la gestion des tâches</span><span class="sxs-lookup"><span data-stu-id="febed-144">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="febed-145">Configurer la gestion des tâches</span><span class="sxs-lookup"><span data-stu-id="febed-145">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="febed-146">Affecter des listes de tâches à des magasins ou des employés</span><span class="sxs-lookup"><span data-stu-id="febed-146">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)

[<span data-ttu-id="febed-147">Gestion des tâches dans le PDV</span><span class="sxs-lookup"><span data-stu-id="febed-147">Task management in POS</span></span>](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
