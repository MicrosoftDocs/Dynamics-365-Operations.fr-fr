---
title: Synchroniser la gestion des tâches entre Microsoft Teams et les PDV Dynamics 365 Commerce
description: Cette rubrique décrit comment synchroniser la gestion des tâches entre Microsoft Teams et les points de vente (PDV) Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 74d53a850113c83979fba6baa4ff3c3e5d9ca02d
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020625"
---
# <a name="synchronize-task-management-between-microsoft-teams-and-dynamics-365-commerce-pos"></a><span data-ttu-id="3e800-103">Synchroniser la gestion des tâches entre Microsoft Teams et les PDV Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="3e800-103">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3e800-104">Cette rubrique décrit comment synchroniser la gestion des tâches entre Microsoft Teams et les points de vente (PDV) Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3e800-104">This topic describes how to synchronize task management between Microsoft Teams and Dynamics 365 Commerce point of sale (POS).</span></span>

<span data-ttu-id="3e800-105">L’un des principaux objectifs de l’intégration de Teams est de permettre la synchronisation de la gestion des tâches entre l’application de PDV et Teams.</span><span class="sxs-lookup"><span data-stu-id="3e800-105">One of the main purposes of Teams integration is to enable the synchronization of task management between the POS application and Teams.</span></span> <span data-ttu-id="3e800-106">De cette façon, les employés du magasin peuvent utiliser l’application de PDV ou Teams pour gérer les tâches et n’ont pas à changer d’application.</span><span class="sxs-lookup"><span data-stu-id="3e800-106">In this way, store employees can use either the POS application or Teams to manage tasks, and don't have to switch applications.</span></span>

<span data-ttu-id="3e800-107">Étant donné que le planificateur est utilisé comme référentiel pour les tâches dans Teams, il doit y avoir un lien entre Teams et Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3e800-107">Because Planner is used as a repository for tasks in Teams, there must be a link between Teams and Dynamics 365 Commerce.</span></span> <span data-ttu-id="3e800-108">Ce lien est établi à l’aide d’un ID de plan spécifique pour une équipe de magasin donnée.</span><span class="sxs-lookup"><span data-stu-id="3e800-108">This link is established by using a specific plan ID for a given store team.</span></span>

<span data-ttu-id="3e800-109">Les procédures suivantes montrent comment configurer la synchronisation de la gestion des tâches entre les applications de PDV et Teams.</span><span class="sxs-lookup"><span data-stu-id="3e800-109">The following procedures show how to set up task management synchronization between the POS and Teams applications.</span></span>

## <a name="publish-a-test-task-list-in-teams"></a><span data-ttu-id="3e800-110">Publier une liste de tâches de test dans Teams</span><span class="sxs-lookup"><span data-stu-id="3e800-110">Publish a test task list in Teams</span></span>

<span data-ttu-id="3e800-111">La procédure suivante suppose que les équipes de votre magasin utilisent l’intégration de la gestion des tâche de Microsoft Teams avec Commerce pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="3e800-111">The following procedure assumes that your store teams are using Microsoft Teams task management integration with Commerce for the first time.</span></span>

<span data-ttu-id="3e800-112">Pour publier une liste de tâches de test dans Teams, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3e800-112">To publish a test task list in Teams, follow these steps.</span></span>

1. <span data-ttu-id="3e800-113">Connectez-vous à Teams en tant que responsable de la communication.</span><span class="sxs-lookup"><span data-stu-id="3e800-113">Sign in to Teams as a communications manager.</span></span> <span data-ttu-id="3e800-114">En règle générale, les responsables de la communication sont des utilisateurs qui ont le rôle **Directeur régional** dans Commerce.</span><span class="sxs-lookup"><span data-stu-id="3e800-114">Typically, communications managers are users who have the **Regional manager** role in Commerce.</span></span>
1. <span data-ttu-id="3e800-115">Dans le volet de navigation de gauche, sélectionnez **Tâches du planificateur**.</span><span class="sxs-lookup"><span data-stu-id="3e800-115">In the left navigation pane, select **Tasks by Planner**.</span></span>
1. <span data-ttu-id="3e800-116">Sur l’onglet **Listes publiées**, sélectionnez **Nouvelle liste** en bas à gauche, et nommez la nouvelle liste **Liste des tâches de test**.</span><span class="sxs-lookup"><span data-stu-id="3e800-116">On the **Published lists** tab, select **New list** in the lower left, and name the new list **Test task list**.</span></span>
1. <span data-ttu-id="3e800-117">Sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="3e800-117">Select **Create**.</span></span> <span data-ttu-id="3e800-118">La nouvelle liste apparaît sous **Brouillons**.</span><span class="sxs-lookup"><span data-stu-id="3e800-118">The new list appears under **Drafts**.</span></span>
1. <span data-ttu-id="3e800-119">Sous **Titre de la tâche**, donnez le titre à la première tâche **Test de l’intégration de Teams**.</span><span class="sxs-lookup"><span data-stu-id="3e800-119">Under **Task title**, give the first task the title **Testing Teams integration**.</span></span> <span data-ttu-id="3e800-120">Sélectionnez ensuite **Entrée**.</span><span class="sxs-lookup"><span data-stu-id="3e800-120">Then select **Enter**.</span></span>
1. <span data-ttu-id="3e800-121">Dans la liste **Brouillons**, sélectionnez la liste des tâches.</span><span class="sxs-lookup"><span data-stu-id="3e800-121">In the **Drafts** list, select the task list.</span></span> <span data-ttu-id="3e800-122">Puis sélectionnez  **Publier**  dans le coin supérieur droit.</span><span class="sxs-lookup"><span data-stu-id="3e800-122">Then select **Publish** in the upper-right corner.</span></span>
1. <span data-ttu-id="3e800-123">Dans la boîte de dialogue **Sélectionner les destinataires de la publication**, sélectionnez les équipes qui doivent recevoir la liste des tâches de test.</span><span class="sxs-lookup"><span data-stu-id="3e800-123">In the **Select who to publish to** dialog box, select the teams that should receive the test task list.</span></span>
1. <span data-ttu-id="3e800-124">Sélectionnez **Suivant** pour examiner votre plan de publication.</span><span class="sxs-lookup"><span data-stu-id="3e800-124">Select **Next** to review your publication plan.</span></span> <span data-ttu-id="3e800-125">Si vous devez apporter des modifications, sélectionnez  **Retour**.</span><span class="sxs-lookup"><span data-stu-id="3e800-125">If you must make changes, select **Back**.</span></span> 
1. <span data-ttu-id="3e800-126">Sélectionnez **Confirmer pour continuer**, puis sélectionnez **Publier**.</span><span class="sxs-lookup"><span data-stu-id="3e800-126">Select **Confirm to proceed**, and then select **Publish**.</span></span>
1. <span data-ttu-id="3e800-127">Une fois la publication terminée, un message en haut de l’onglet **Listes publiées** indique si votre liste de tâches a été livrée avec succès.</span><span class="sxs-lookup"><span data-stu-id="3e800-127">After publishing is completed, a message at the top of the **Published lists** tab indicates whether your task list was successfully delivered.</span></span>

<span data-ttu-id="3e800-128">Pour plus d’informations, consultez [Publier des listes de tâches pour créer et suivre le travail dans votre organisation](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df).</span><span class="sxs-lookup"><span data-stu-id="3e800-128">For more information, see [Publish task lists to create and track work in your organization](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df).</span></span>

## <a name="link-pos-and-teams-for-task-management"></a><span data-ttu-id="3e800-129">Lier le point de vente et Teams pour la gestion des tâches</span><span class="sxs-lookup"><span data-stu-id="3e800-129">Link POS and Teams for task management</span></span>

<span data-ttu-id="3e800-130">Pour lier les applications de PDV et Microsoft Teams pour la gestion des tâches dans Commerce Headquarters, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3e800-130">To link the POS and Microsoft Teams applications for task management in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="3e800-131">Accédez à **Retail et Commerce \> Gestion des tâches \> Intégration des tâches avec Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="3e800-131">Go to **Retail and Commerce \> Task management \> Tasks integration with Microsoft Teams**.</span></span>
1. <span data-ttu-id="3e800-132">Dans le volet Actions, sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="3e800-132">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="3e800-133">Définissez l’option **Activer l’intégration de la gestion des tâches** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="3e800-133">Set the **Enable Task Management Integration** option to **Yes**.</span></span>
1. <span data-ttu-id="3e800-134">Dans le volet Actions, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="3e800-134">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="3e800-135">Dans le volet Actions, sélectionnez **Configurer la gestion des tâches**.</span><span class="sxs-lookup"><span data-stu-id="3e800-135">On the Action Pane, select **Setup task management**.</span></span> <span data-ttu-id="3e800-136">Vous devriez recevoir une notification indiquant qu’un travail par lots nommé **Configuration de Teams** est en cours de création.</span><span class="sxs-lookup"><span data-stu-id="3e800-136">You should receive a notification that indicates that a batch job that is named **Teams provision** is being created.</span></span>
1. <span data-ttu-id="3e800-137">Accédez à **Administration système \> Recherches \> Traitements par lots** et recherchez le travail le plus récent ayant la description **Configuration de Teams**.</span><span class="sxs-lookup"><span data-stu-id="3e800-137">Go to **System administration \> Inquiries \> Batch jobs**, and find the most recent job that has the description **Teams provision**.</span></span> <span data-ttu-id="3e800-138">Attendez que ce travail soit terminé.</span><span class="sxs-lookup"><span data-stu-id="3e800-138">Wait until this job has finished running.</span></span>
1. <span data-ttu-id="3e800-139">Exécutez la **Tâche CDX 1070** pour publier l’ID du plan et stocker les références à Retail Server.</span><span class="sxs-lookup"><span data-stu-id="3e800-139">Run the **CDX job 1070** to publish the plan ID and store references to Retail Server.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3e800-140">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="3e800-140">Additional resources</span></span>

[<span data-ttu-id="3e800-141">Présentation de l’intégration de Dynamics 365 Commerce et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3e800-141">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="3e800-142">Activer l’intégration de Dynamics 365 Commerce et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3e800-142">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="3e800-143">Configuration de Microsoft Teams à partir de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="3e800-143">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="3e800-144">Gérer les rôles utilisateur dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3e800-144">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="3e800-145">Mapper les magasins et les équipes si votre organisation a des équipes préexistantes dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3e800-145">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="3e800-146">FAQ sur l’intégration de Dynamics 365 Commerce et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3e800-146">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
