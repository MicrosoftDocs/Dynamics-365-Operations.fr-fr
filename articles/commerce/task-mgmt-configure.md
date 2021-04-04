---
title: Configurer la gestion des tâches
description: Cette rubrique décrit comment configurer les fonctionnalités de gestion des tâches dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: ba2283bbfa2fdce75d3fbef6fcff47dd872c7998
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478042"
---
# <a name="configure-task-management"></a><span data-ttu-id="eb7b8-103">Configurer la gestion des tâches</span><span class="sxs-lookup"><span data-stu-id="eb7b8-103">Configure task management</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="eb7b8-104">Cette rubrique décrit comment configurer les fonctionnalités de gestion des tâches dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-104">This topic describes how to configure task management features in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="eb7b8-105">Avant que les responsables et les employés de Dynamics 365 Commerce puissent utiliser les fonctionnalités de gestion des tâches de Commerce, la gestion des tâches doit être configurée.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-105">Before Dynamics 365 Commerce managers and employees can use the task management features in Commerce, task management must be configured.</span></span> <span data-ttu-id="eb7b8-106">Les étapes de configuration sont notamment l'octroi d'autorisations aux responsables et employés, la distribution d'autorisations aux clients PDV, la configuration des notifications PDV et la configuration de la vignette **Tâches** sur la page d'accueil d'une application PDV.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-106">Configuration steps include granting permissions to managers and employees, distributing permissions to point of sale (POS) clients, setting up POS notifications, and configuring the **Tasks** tile on the home page of a POS application.</span></span>

## <a name="configure-permissions-for-store-managers"></a><span data-ttu-id="eb7b8-107">Configurer des autorisations pour les responsables de magasin</span><span class="sxs-lookup"><span data-stu-id="eb7b8-107">Configure permissions for store managers</span></span>

<span data-ttu-id="eb7b8-108">Chaque employé d'un magasin donné peut afficher toutes les tâches qui sont affectées à ce magasin.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-108">Every worker in a given store can view all tasks that are assigned to that store.</span></span> <span data-ttu-id="eb7b8-109">Il peut également mettre à jour le statut des tâches qui lui sont affectées.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-109">They can also update the status of the tasks that are assigned to them.</span></span> <span data-ttu-id="eb7b8-110">Cependant, les personnes telles que les responsables de magasin doivent disposer d'autorisations de gestion des tâches pour gérer les tâches affectées au magasin et pour créer des tâches à but unique.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-110">However, personas such as store managers must have task management permissions to manage tasks that are assigned to the store and to create single-purpose tasks.</span></span>

<span data-ttu-id="eb7b8-111">Pour configurer les autorisations de gestion des tâches pour les responsables de magasin, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-111">To configure task management permissions for store managers, follow these steps.</span></span>

1. <span data-ttu-id="eb7b8-112">Accédez à **Commerce et vente au détail \> Employés \> Groupes d'autorisations**.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-112">Go to **Retail and Commerce \> Employees \> Permission groups**.</span></span>
1. <span data-ttu-id="eb7b8-113">Sélectionnez un groupe d'autorisations spécifique (par exemple, **Responsable**), puis sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-113">Select a specific permission group (for example, **Manager**), and then select **Edit**.</span></span>
1. <span data-ttu-id="eb7b8-114">Dans le raccourci **Autorisations**, définissez l'option **Autoriser la gestion des tâches** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-114">On the **Permissions** FastTab, set the **Allow task management** option to **Yes**.</span></span>
1. <span data-ttu-id="eb7b8-115">Dans le raccourci **Notifications**, ajoutez l'opération **Gestion des tâches** et entrez une valeur dans le champ **Ordre d'affichage**.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-115">On the **Notifications** FastTab, add the **Task management** operation, and enter a value in the **Display order** field.</span></span> <span data-ttu-id="eb7b8-116">Par exemple, entrez **2** si l'opération **Exécution des commandes** a déjà la valeur **Ordre d'affichage** définie sur **1**.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-116">For example, enter **2** if the **Order fulfillment** operation already has a **Display order** value of **1**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="eb7b8-117">Si une personne autre qu'un responsable doit disposer d'autorisations de gestion des tâches dans le PDV, vous pouvez les lui accorder.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-117">If a non-manager persona must have task management permissions in the POS, you can grant permission to the individual.</span></span> <span data-ttu-id="eb7b8-118">Vous pouvez également créer un groupe d'autorisations pour les personnes autres que les responsables et définir l'option **Autoriser la gestion des tâches** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-118">Alternatively, you can create a new permission group for non-managers and set the **Allow task management** option to **Yes**.</span></span>

<span data-ttu-id="eb7b8-119">L'illustraton suivante montre comment configurer des autorisations de gestion des tâches pour les responsables de magasin.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-119">The following illustration shows how to configure task management permissions for store managers.</span></span>

![Configuration des autorisations de gestion des tâches pour les responsables de magasin](media/HQ-POS-Tasks-Notifications-User-Permission.png)

## <a name="configure-permissions-for-employees"></a><span data-ttu-id="eb7b8-121">Configurer des autorisations pour les employés</span><span class="sxs-lookup"><span data-stu-id="eb7b8-121">Configure permissions for employees</span></span>

<span data-ttu-id="eb7b8-122">Les employés doivent être autorisés à créer des listes de tâches, à gérer les critères d'affectation et à configurer la récurrence d'une liste de tâches.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-122">Employees must have permissions to create task lists, manage assignment criteria, and configure the recurrence of any task list.</span></span> <span data-ttu-id="eb7b8-123">Pour configurer ces autorisations, vous affectez les employés au rôle **Gestionnaire des tâches de vente au détail**.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-123">To configure these permissions, you assign employees to the **Retail task manager** role.</span></span>

<span data-ttu-id="eb7b8-124">Pour configurer des autorisations pour un employé, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-124">To configure permissions for an employee, follow these steps.</span></span>

1. <span data-ttu-id="eb7b8-125">Accédez à **Commerce et vente au détail \> Employés \> Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-125">Go to **Retail and Commerce \> Employees \> Users**.</span></span>
1. <span data-ttu-id="eb7b8-126">Sélectionnez un employé.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-126">Select an employee.</span></span>
1. <span data-ttu-id="eb7b8-127">Dans le raccourci **Rôle de l'utilisateur**, sélectionnez **Affecter des rôles**.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-127">On the **User's roles** FastTab, select **Assign roles**.</span></span>
1. <span data-ttu-id="eb7b8-128">Dans la boîte de dialogue **Affecter des rôles à l'utilisateur**, sélectionnez le rôle **Gestionnaire des tâches de vente au détail**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-128">In the **Assign roles to user** dialog box, select the **Retail task manager** role, and then select **OK**.</span></span>

## <a name="distribute-permissions-to-pos-clients"></a><span data-ttu-id="eb7b8-129">Distribuer des autorisations aux clients PDV</span><span class="sxs-lookup"><span data-stu-id="eb7b8-129">Distribute permissions to POS clients</span></span>

<span data-ttu-id="eb7b8-130">Avant que les employés puissent utiliser les clients PDV, des autorisations doivent être distribuées aux clients et synchronisées avec ceux-ci.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-130">Before employees can use POS clients, permissions must be distributed and synced to those clients.</span></span>

<span data-ttu-id="eb7b8-131">Pour distribuer des autorisations aux clients PDV, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-131">To distribute permissions to POS clients, follow these steps.</span></span>

1. <span data-ttu-id="eb7b8-132">Accédez à **Commerce et vente au détail \> Informatique Commerce et vente au détail \> Programme de distribution**.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-132">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="eb7b8-133">Sélectionnez le programme de distribution **1060** (**Personnel**), puis sélectionnez **Exécuter maintenant**.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-133">Select the **1060** (**Staff**) distribution schedule, and then select **Run now**.</span></span>
1. <span data-ttu-id="eb7b8-134">Sélectionnez le programme de distribution **1070** (**Configuration du canal**), puis sélectionnez **Exécuter maintenant**.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-134">Select the **1070** (**Channel configuration**) distribution schedule, and then select **Run now**.</span></span>

## <a name="configure-pos-notifications-for-tasks"></a><span data-ttu-id="eb7b8-135">Configurer des notifications PDV pour les tâches</span><span class="sxs-lookup"><span data-stu-id="eb7b8-135">Configure POS notifications for tasks</span></span>

<span data-ttu-id="eb7b8-136">La gestion des tâches doit être configurée pour que les notifications soient disponibles dans l'application PDV.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-136">Task management must be configured so that notifications are available in the POS application.</span></span>

<span data-ttu-id="eb7b8-137">Pour configurer des notifications PDV pour les tâches, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-137">To configure POS notifications for tasks, follow these steps.</span></span>

1. <span data-ttu-id="eb7b8-138">Accédez à **Commerce et vente au détail \> Paramétrage du canal \> Paramétrage du PDV \> PDV \> Opérations PDV**.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-138">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> POS operations**.</span></span>
1. <span data-ttu-id="eb7b8-139">Recherchez l'opération **1400** (**Gestion des tâches**), puis activez la case à cocher **Activer les notifications** correspondante.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-139">Find operation **1400** (**Task management**), and select the **Enable notifications** check box for it.</span></span>

<span data-ttu-id="eb7b8-140">L'illustration suivante présente l'opération **Gestion des tâches** sur la page **Opérations PDV**.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-140">The following illustration shows the **Task management** operation on the **POS operations** page.</span></span>

![Opération de gestion des tâches sur la page Opérations PDV](media/HQ-POS-Tasks-Notifications.png)

<span data-ttu-id="eb7b8-142">Pour plus d'informations sur la configuration des notifications PDV, consultez [Afficher les notifications de commande dans le point de vente (PDV)](notifications-pos.md).</span><span class="sxs-lookup"><span data-stu-id="eb7b8-142">For more information about how to configure POS notifications, see [Show order notifications in the point of sale (POS)](notifications-pos.md).</span></span>

## <a name="configure-the-tasks-tile-on-a-pos-application-home-page"></a><span data-ttu-id="eb7b8-143">Configurer la vignette Tâches sur la page d'accueil d'une application PDV</span><span class="sxs-lookup"><span data-stu-id="eb7b8-143">Configure the Tasks tile on a POS application home page</span></span>

<span data-ttu-id="eb7b8-144">Avant de configurer la vignette **Tâches** sur la page d'accueil d'une application PDV, consultez [Mises en page de l'écran pour le point de vente (PDV)](pos-screen-layouts.md) pour obtenir des informations sur la configuration et l'ajout de nouveaux boutons à une mise en page de l'écran PDV.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-144">Before you configure the **Tasks** tile on the home page of a POS application, see [Screen layouts for the point of sale (POS)](pos-screen-layouts.md) for information about how to configure and add new buttons to a POS screen layout.</span></span>

<span data-ttu-id="eb7b8-145">Pour configurer la vignette **Tâches** sur la page d'accueil d'une application PDV, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-145">To configure the **Tasks** tile on a POS application home page, follow these steps.</span></span>

1. <span data-ttu-id="eb7b8-146">Accédez à **Commerce et vente au détail \> Paramétrage du canal \> Paramétrage du PDV \> PDV \> Mises en page de l'écran**.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-146">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> Screen layouts**.</span></span>
1. <span data-ttu-id="eb7b8-147">Sélectionnez une mise en page de l'écran, sélectionnez une taille de mise en page et sélectionnez une grille de boutons.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-147">Select a screen layout, select a layout size, and select a button grid.</span></span>
1. <span data-ttu-id="eb7b8-148">Dans le raccourci **Grilles de boutons**, sélectionnez **Concepteur** pour modifier la grille de boutons sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-148">On the **Button grids** FastTab, select **Designer** to edit the selected button grid.</span></span>
1. <span data-ttu-id="eb7b8-149">Ajoutez une vignette **Tâches** à la section appropriée de la page d'accueil.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-149">Add a **Tasks** tile to the appropriate section of the home page.</span></span>

<span data-ttu-id="eb7b8-150">L'illustration suivante présente un exemple de vignette **Tâches** sur une page d'accueil PDV.</span><span class="sxs-lookup"><span data-stu-id="eb7b8-150">The following illustration shows an example of a **Tasks** tile on a POS home page.</span></span>

![Vignette Tâches sur une page d'accueil PDV](media/POS-home-screen-tasks-button-image.png)

## <a name="additional-resources"></a><span data-ttu-id="eb7b8-152">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="eb7b8-152">Additional resources</span></span>

[<span data-ttu-id="eb7b8-153">Vue d'ensemble de la gestion des tâches</span><span class="sxs-lookup"><span data-stu-id="eb7b8-153">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="eb7b8-154">Créer des listes de tâches et ajouter des tâches</span><span class="sxs-lookup"><span data-stu-id="eb7b8-154">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="eb7b8-155">Affecter des listes de tâches à des magasins ou des employés</span><span class="sxs-lookup"><span data-stu-id="eb7b8-155">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)

[<span data-ttu-id="eb7b8-156">Gestion des tâches dans le PDV</span><span class="sxs-lookup"><span data-stu-id="eb7b8-156">Task management in POS</span></span>](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
