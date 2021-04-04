---
title: Affecter des listes de tâches à des magasins ou des employés
description: Cette rubrique décrit comment affecter des listes de tâches à des magasins ou des employés dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 3d249809f15b50c59620d69a901a427dc3ecb2f0
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477582"
---
# <a name="assign-task-lists-to-stores-or-employees"></a><span data-ttu-id="3bb34-103">Affecter des listes de tâches aux magasins ou aux employés</span><span class="sxs-lookup"><span data-stu-id="3bb34-103">Assign task lists to stores or employees</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3bb34-104">Cette rubrique décrit comment affecter des listes de tâches à des magasins ou des employés dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3bb34-104">This topic describes how to assign task lists to stores or employees in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="3bb34-105">La gestion des tâches dans Dynamics 365 Commerce vous permet d'affecter une liste de tâches à plusieurs magasins ou employés, ou à une combinaison de magasins et d'employés.</span><span class="sxs-lookup"><span data-stu-id="3bb34-105">Task management in Dynamics 365 Commerce lets you assign a task list to multiple stores or employees, or to a combination of stores and employees.</span></span> <span data-ttu-id="3bb34-106">Par exemple, un responsable régional de 20 magasins peut être amené à affecter la liste de tâches **Préparation de la période des fêtes** à tous les 20 magasins.</span><span class="sxs-lookup"><span data-stu-id="3bb34-106">For example, a regional manager for 20 stores might want to assign the **Holiday season preparation** task list to all 20 stores.</span></span>

## <a name="start-the-task-list-assignment-process"></a><span data-ttu-id="3bb34-107">Démarrer le processus d'affectation de la liste de tâches</span><span class="sxs-lookup"><span data-stu-id="3bb34-107">Start the task list assignment process</span></span>

<span data-ttu-id="3bb34-108">Pour démarrer le processus d'affectation d'une liste de tâches, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3bb34-108">To start the process of assigning a task list, follow these steps.</span></span>

1. <span data-ttu-id="3bb34-109">Accédez à **Commerce et vente au détail \> Gestion des tâches \> Administration de la gestion des tâches**.</span><span class="sxs-lookup"><span data-stu-id="3bb34-109">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="3bb34-110">Sélectionnez la liste de tâches à affecter.</span><span class="sxs-lookup"><span data-stu-id="3bb34-110">Select the task list to assign.</span></span>
1. <span data-ttu-id="3bb34-111">Sélectionnez **Démarrer le processus**.</span><span class="sxs-lookup"><span data-stu-id="3bb34-111">Select **Start process**.</span></span>
1. <span data-ttu-id="3bb34-112">Dans la boîte de dialogue **Démarrer le processus**, sous l'onglet **Général**, dans le champ **Nom du processus**, entrez un nom (par exemple, **Magasins de la région Est**).</span><span class="sxs-lookup"><span data-stu-id="3bb34-112">In the **Start process** dialog box, on the **General** tab, in the **Process name** field, enter a name (for example, **East region stores**).</span></span>
1. <span data-ttu-id="3bb34-113">Dans le champ **Date cible**, spécifiez une date.</span><span class="sxs-lookup"><span data-stu-id="3bb34-113">In the **Target date** field, specify a date.</span></span>
1. <span data-ttu-id="3bb34-114">Pour affecter la liste de tâches aux magasins, sous l'onglet **Magasins**, utilisez le filtre **Hiérarchie d'organisation** pour rechercher et sélectionner les magasins.</span><span class="sxs-lookup"><span data-stu-id="3bb34-114">To assign the task list to stores, on the **Stores** tab, use the **Organization hierarchy** filter to find and select the stores.</span></span>

    <span data-ttu-id="3bb34-115">Pour affecter la liste de tâches aux employés, sous l'onglet **Collaborateurs**, recherchez et sélectionnez les employés.</span><span class="sxs-lookup"><span data-stu-id="3bb34-115">To assign the task list to employees, on the **Workers** tab, find and select the employees.</span></span>

1. <span data-ttu-id="3bb34-116">Sélectionnez **OK** pour démarrer le processus.</span><span class="sxs-lookup"><span data-stu-id="3bb34-116">Select **OK** to start the process.</span></span> <span data-ttu-id="3bb34-117">La liste de tâches est affectée aux magasins ou employés sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="3bb34-117">The tasks list is assigned to the selected stores or employees.</span></span>

<span data-ttu-id="3bb34-118">L'illustration suivante présente un exemple de recherche et de sélection de magasins dans la boîte de dialogue **Démarrer le processus**.</span><span class="sxs-lookup"><span data-stu-id="3bb34-118">The following illustration shows an example of how to find and select stores in the **Start process** dialog box.</span></span>

![Recherche et sélection de magasins dans la boîte de dialogue Démarrer le processus](media/HQ-Assign-Tasks-Lists.png)

## <a name="assign-task-lists-on-a-recurring-basis"></a><span data-ttu-id="3bb34-120">Affecter des listes de tâches de façon récurrente</span><span class="sxs-lookup"><span data-stu-id="3bb34-120">Assign task lists on a recurring basis</span></span>

<span data-ttu-id="3bb34-121">Les détaillants ont parfois des tâches récurrentes, comme « Liste de contrôle pour la fermeture du jeudi » ou « Liste de contrôle pour le premier jour du mois ».</span><span class="sxs-lookup"><span data-stu-id="3bb34-121">Retailer sometimes have recurrent tasks, such as "Thursday closure checklist" or "First day of the month checklist."</span></span> <span data-ttu-id="3bb34-122">Par conséquent, ils peuvent être amenés à affecter la liste de tâches de façon récurrente.</span><span class="sxs-lookup"><span data-stu-id="3bb34-122">Therefore, they might want to assign the task list on a recurring basis.</span></span>

1. <span data-ttu-id="3bb34-123">Accédez à **Commerce et vente au détail \> Gestion des tâches \> Administration de la gestion des tâches**.</span><span class="sxs-lookup"><span data-stu-id="3bb34-123">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="3bb34-124">Sélectionnez la liste de tâches à affecter.</span><span class="sxs-lookup"><span data-stu-id="3bb34-124">Select the task list to assign.</span></span>
1. <span data-ttu-id="3bb34-125">Sélectionnez **Démarrer le processus**.</span><span class="sxs-lookup"><span data-stu-id="3bb34-125">Select **Start process**.</span></span>
1. <span data-ttu-id="3bb34-126">Dans la boîte de dialogue **Démarrer le processus**, sous l'onglet **Général**, dans le champ **Nom du processus**, entrez un nom.</span><span class="sxs-lookup"><span data-stu-id="3bb34-126">In the **Start process** dialog box, on the **General** tab, in the **Process name** field, enter a name.</span></span>
1. <span data-ttu-id="3bb34-127">Définissez l'option **Récurrence** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="3bb34-127">Set the **Recurrence** option to **Yes**.</span></span>
1. <span data-ttu-id="3bb34-128">Dans le champ **Décalage de la date cible de récurrence en jours**, entrez un nombre de jours.</span><span class="sxs-lookup"><span data-stu-id="3bb34-128">In the **Recurrence target date offset in days** field, enter a number of days.</span></span> <span data-ttu-id="3bb34-129">Par exemple, si vous entrez **4**, la date cible correspond à la date de récurrence plus quatre jours.</span><span class="sxs-lookup"><span data-stu-id="3bb34-129">For example, if you enter **4**, the target date is the recurrence date plus four days.</span></span>
1. <span data-ttu-id="3bb34-130">Sous l'onglet **Exécuter en arrière-plan**, sélectionnez **Récurrence**.</span><span class="sxs-lookup"><span data-stu-id="3bb34-130">On the **Run in the background** tab, select **Recurrence**.</span></span>
1. <span data-ttu-id="3bb34-131">Dans la boîte de dialogue **Définir la récurrence**, entrez les critères de fréquence, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="3bb34-131">In the **Define recurrence** dialog box, enter the frequency criteria, and then select **OK**.</span></span>

<span data-ttu-id="3bb34-132">L'illustration suivante présente un exemple de saisie des critères de fréquence dans la boîte de dialogue **Définir la récurrence**.</span><span class="sxs-lookup"><span data-stu-id="3bb34-132">The following illustration shows an example of how to enter frequency criteria in the **Define recurrence** dialog box.</span></span>

![Saisie des critères de fréquence dans la boîte de dialogue Définir la récurrence](media/HQ-Assign-Tasks-Lists-Recurrently.png)

## <a name="track-task-list-status"></a><span data-ttu-id="3bb34-134">Suivre le statut de la liste de tâches</span><span class="sxs-lookup"><span data-stu-id="3bb34-134">Track task list status</span></span>

<span data-ttu-id="3bb34-135">Si vous êtes un directeur régional ou un responsable de magasin, vous pouvez être amené à suivre le statut des listes de tâches qui ont été affectées à plusieurs magasins ou employés.</span><span class="sxs-lookup"><span data-stu-id="3bb34-135">If you're a regional manager or store manager, you might want to track the status of task lists that have been assigned to multiple stores or employees.</span></span> <span data-ttu-id="3bb34-136">Vous pouvez ensuite effectuer le suivi des magasins ou des employés qui n'ont pas terminé les tâches qui leur ont été affectées dans les délais.</span><span class="sxs-lookup"><span data-stu-id="3bb34-136">You can then follow up with stores or workers that didn't complete their assigned tasks on time.</span></span> <span data-ttu-id="3bb34-137">Le back-office Commerce vous permet d'afficher le statut des listes de tâches, de réaffecter des tâches ou de modifier le statut d'une tâche.</span><span class="sxs-lookup"><span data-stu-id="3bb34-137">Commerce back office lets you view the status of task lists, reassign tasks, or change the status of a task.</span></span>

<span data-ttu-id="3bb34-138">Pour suivre le statut de la liste de tâches pour toutes les tâches, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3bb34-138">To track the task list status for all tasks, follow these steps.</span></span>

1. <span data-ttu-id="3bb34-139">Accédez à **Commerce et vente au détail \> Gestion des tâches \> Processus de gestion des tâches**.</span><span class="sxs-lookup"><span data-stu-id="3bb34-139">Go to **Retail and Commerce \> Task management \> Task management processes**.</span></span>
1. <span data-ttu-id="3bb34-140">Sélectionnez l'onglet **Toutes les listes de tâches** pour afficher le statut de toutes les listes de tâches affectées à différents magasins.</span><span class="sxs-lookup"><span data-stu-id="3bb34-140">Select the **All task lists** tab to view the status of all task lists that are assigned to various stores.</span></span>

<span data-ttu-id="3bb34-141">Pour suivre le statut de la liste de tâches pour toutes les tâches qui vous sont affectées, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3bb34-141">To track the task list status for all tasks that are assigned to you, follow these steps.</span></span>

1. <span data-ttu-id="3bb34-142">Accédez à **Commerce et vente au détail \> Gestion des tâches \> Processus de gestion des tâches**.</span><span class="sxs-lookup"><span data-stu-id="3bb34-142">Go to **Retail and Commerce \> Task management \> Task management processes**.</span></span>
1. <span data-ttu-id="3bb34-143">Sélectionnez l'onglet **Mes tâches** ou **Toutes les tâches** pour afficher ou mettre à jour le statut des tâches qui vous sont affectées.</span><span class="sxs-lookup"><span data-stu-id="3bb34-143">Select the **My tasks** or **All tasks** tab to view or update the status of tasks that are assigned to you.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3bb34-144">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="3bb34-144">Additional resources</span></span>

[<span data-ttu-id="3bb34-145">Vue d'ensemble de la gestion des tâches</span><span class="sxs-lookup"><span data-stu-id="3bb34-145">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="3bb34-146">Configurer la gestion des tâches</span><span class="sxs-lookup"><span data-stu-id="3bb34-146">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="3bb34-147">Créer des listes de tâches et ajouter des tâches</span><span class="sxs-lookup"><span data-stu-id="3bb34-147">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="3bb34-148">Gestion des tâches dans le PDV</span><span class="sxs-lookup"><span data-stu-id="3bb34-148">Task management in POS</span></span>](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
