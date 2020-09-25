---
title: Créer un nouveau projet
description: Cette rubrique fournit des informations sur la manière de créer un projet.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c8c52b8c1c86ea2f6e03cf439ba5930f1006ab4f
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760543"
---
# <a name="create-a-new-project"></a><span data-ttu-id="1ebcb-103">Créer un nouveau projet</span><span class="sxs-lookup"><span data-stu-id="1ebcb-103">Create a new project</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1ebcb-104">Procédez comme suit pour créer un projet.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-104">Complete the following steps to create a new project.</span></span>

1. <span data-ttu-id="1ebcb-105">Sur la page **Gestion de projets**, sélectionnez **Nouveau projet**, puis entrez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="1ebcb-105">On the **Project management** page, select **New project**, and enter the following values:</span></span>

    - <span data-ttu-id="1ebcb-106">**Type de projet :** Régie</span><span class="sxs-lookup"><span data-stu-id="1ebcb-106">**Project type:** Time and material</span></span>
    - <span data-ttu-id="1ebcb-107">**Nom du projet :** Phase 2 de mise à niveau de XYZ</span><span class="sxs-lookup"><span data-stu-id="1ebcb-107">**Project name:** XYZ Upgrade Phase 2</span></span>
    - <span data-ttu-id="1ebcb-108">**Groupe de projets :** TM\_WIP</span><span class="sxs-lookup"><span data-stu-id="1ebcb-108">**Project group:** TM\_WIP</span></span>
    - <span data-ttu-id="1ebcb-109">**ID contrat de projet :** 00000002</span><span class="sxs-lookup"><span data-stu-id="1ebcb-109">**Project contract ID:** 00000002</span></span>

2. <span data-ttu-id="1ebcb-110">Sélectionnez **Créer un projet**.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-110">Select **Create project**.</span></span>

## <a name="assign-a-resource-to-a-project"></a><span data-ttu-id="1ebcb-111">Affectez une ressource à un projet</span><span class="sxs-lookup"><span data-stu-id="1ebcb-111">Assign a resource to a project</span></span>

1. <span data-ttu-id="1ebcb-112">Sur la page **Collaborateurs**, dans la liste **Collaborateurs**, sélectionnez l’enregistrement pour le collaborateur dont vous avez précédemment paramétré les compétences et ouvrez l’enregistrement de collaborateur.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-112">On the **Workers** page, in the **Workers** list, select the record for the worker that you previously set up competencies for, and open the worker record.</span></span>
2. <span data-ttu-id="1ebcb-113">Dans le volet Actions, sous l’onglet **Projet**, dans le groupe **Paramétrage**, sélectionnez **Affecter des projets**.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-113">On the Action Pane, on the **Project** tab, in the **Setup** group, select **Assign projects**.</span></span>
3. <span data-ttu-id="1ebcb-114">Sur la page **Affectations du projet de contrôle des ressources**, sous l’onglet **Projet**, dans le champ **Ajoutez le projet aux projets sélectionnés**, filtrez sur le projet **Phase 2 de mise à niveau de XYZ**.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-114">On the **Resource validation project assignments** page, on the **Projects** tab, in the **Add the project to selected projects** field, filter on the **XYZ Upgrade Phase 2** project.</span></span>
4. <span data-ttu-id="1ebcb-115">Dans le volet **Projets restants**, sélectionnez un projet, puis sélectionnez le bouton fléché pour l’ajouter au volet **Projets sélectionnés**.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-115">In the **Remaining projects** pane, select a project, and then select the arrow button to add it to the **Selected projects** pane.</span></span>

<span data-ttu-id="1ebcb-116">Vous pouvez également affecter des catégories à une ressource en fonction de vos besoins.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-116">You can also assign categories for a resource as you require.</span></span> <span data-ttu-id="1ebcb-117">Le type de catégorie est **Coût** ou **Produit**.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-117">The category type is either **Cost** or **Revenue**.</span></span> <span data-ttu-id="1ebcb-118">Le type de catégorie est déterminé par votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-118">The category type is determined by your organization.</span></span> <span data-ttu-id="1ebcb-119">Si aucune catégorie n’est affectée à une ressource, Finance recherche la catégorie par défaut dans les prix horaires en matière de coût et de produit.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-119">If no categories are assigned for a resource, Finance looks up the default category on hour prices for cost and revenue.</span></span>

## <a name="set-up-project-resource-and-role-characteristics"></a><span data-ttu-id="1ebcb-120">Configurer des ressources de projet et les caractéristiques du rôle</span><span class="sxs-lookup"><span data-stu-id="1ebcb-120">Set up project resource and role characteristics</span></span>

<span data-ttu-id="1ebcb-121">Un chef de projet peut utiliser la fonctionnalité de ressources de projet pour créer les rôles requis pour le projet.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-121">A project manager can use the project resourcing functionality to create the roles that are required for the project.</span></span> <span data-ttu-id="1ebcb-122">Les rôles peuvent être utilisés lorsque les ressources confirmées sont encore inconnues lors de la réservation des ressources.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-122">Roles can be used if confirmed resources are still unknown when resources are being reserved.</span></span> <span data-ttu-id="1ebcb-123">Les rôles peuvent être réservés temporairement en tant que ressources planifiées pour que vous puissiez poursuivre les stades de planification du projet.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-123">Roles can be temporarily reserved as planned resources, so that you can continue the project planning stages.</span></span>

<span data-ttu-id="1ebcb-124">[![Exemple de rôle](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg)</span><span class="sxs-lookup"><span data-stu-id="1ebcb-124">[![Example of a role](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg)</span></span> 

<span data-ttu-id="1ebcb-125">**Scénario :** Contoso a été engagé pour réaliser un projet en régie avec une charte de projet approuvée.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-125">**Scenario:** Contoso was hired to complete a Time and material project that has an approved project charter.</span></span> <span data-ttu-id="1ebcb-126">Le chef de projet junior termine toujours la portée du projet.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-126">The junior project manager is still completing the scope of the project.</span></span> <span data-ttu-id="1ebcb-127">Le gestionnaire de ressources identifie actuellement les ressources spécifiques qui seront réservées pour travailler sur le nouveau projet.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-127">The resource manager is currently identifying specific resources that will be reserved to work on the new project.</span></span> <span data-ttu-id="1ebcb-128">En raison de la nature critique du projet, le commanditaire du projet a demandé le rôle de chef de projet senior.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-128">Because of the critical nature of the project, the project sponsor requested Senior project manager as one of the roles.</span></span> <span data-ttu-id="1ebcb-129">Le gestionnaire de ressources doit acquérir la nouvelle ressource et définit le rôle dans le système, au cas où le chef de projet junior aurait besoin des informations de ressource lors de la planification des projets.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-129">The resource manager must acquire the new resource and define the role in the system in case the junior project manager requires the resource information during project planning.</span></span>

<span data-ttu-id="1ebcb-130">Les étapes suivantes indiquent comment le gestionnaire de ressources peut paramétrer le rôle de chef de projet senior et lui associer caractéristiques de la ressource.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-130">The following steps show how the resource manager can set up the Senior project manager role and associate resource characteristics with it.</span></span> <span data-ttu-id="1ebcb-131">Ensuite, le rôle peut être utilisé pour rechercher des ressources disponibles correspondant aux compétences de ressource requises.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-131">Later, the role can be used to search for available resources that match the required resource competencies.</span></span>

1. <span data-ttu-id="1ebcb-132">Sur la page **Paramétrer les rôles**, sélectionnez **Nouveau**, puis entrez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="1ebcb-132">On the **Setup roles** page, select **New**, and enter the following values:</span></span>

    - <span data-ttu-id="1ebcb-133">**ID rôle :** Chef de projet senior</span><span class="sxs-lookup"><span data-stu-id="1ebcb-133">**Role ID:** Senior Project Manager</span></span>
    - <span data-ttu-id="1ebcb-134">**Description :** Chef de projet senior</span><span class="sxs-lookup"><span data-stu-id="1ebcb-134">**Description:** Senior Project Manager</span></span>

2. <span data-ttu-id="1ebcb-135">Sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-135">Select **Create**.</span></span>
3. <span data-ttu-id="1ebcb-136">Sélectionnez le rôle **Chef de projet senior**, puis sélectionnez **Configurer les caractéristiques**.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-136">Select the **Senior Project Manager** role, and then select **Configure characteristics**.</span></span>
4. <span data-ttu-id="1ebcb-137">Dans le champ **Type de caractéristiques**, sélectionnez **Qualification**.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-137">In the **Characteristics type** field, select **Skill**.</span></span>
5. <span data-ttu-id="1ebcb-138">Dans le champ **Caractéristiques disponibles**, entrez la compétence que vous recherchez.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-138">In the **Available characteristics** field, enter the skill to search for.</span></span>
6. <span data-ttu-id="1ebcb-139">Dans le champ **Type de caractéristiques**, sélectionnez **Certificat**.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-139">In the **Characteristic type** field, select **Certificate**.</span></span>
7. <span data-ttu-id="1ebcb-140">Dans le champ **Caractéristiques disponibles**, entrez le type de certificat que vous recherchez.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-140">In the **Available characteristics** field, enter the certificate type to search for.</span></span>

## <a name="assign-a-project-resource-to-a-project"></a><span data-ttu-id="1ebcb-141">Affectez une ressource de projet à un projet</span><span class="sxs-lookup"><span data-stu-id="1ebcb-141">Assign a project resource to a project</span></span>

1. <span data-ttu-id="1ebcb-142">Sur la page **Tous les projets**, sélectionnez le projet **Phase 2 de mise à niveau de XYZ**.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-142">On the **All projects** page, select the **XYZ Upgrade Phase 2** project.</span></span>
2. <span data-ttu-id="1ebcb-143">Sous l’onglet **Équipe de projet et planification**, sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-143">On the **Project team and scheduling** tab, select **Add**.</span></span>
3. <span data-ttu-id="1ebcb-144">Dans le champ **Rôle**, sélectionnez **Membre de l’équipe**.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-144">In the **Role** field, select **Team member**.</span></span>
4. <span data-ttu-id="1ebcb-145">Sélectionnez **Réserver à partir du calendrier**.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-145">Select **Book from calendar**.</span></span>
5. <span data-ttu-id="1ebcb-146">Sur la page **Disponibilité des ressources**, sélectionnez **Afficher les paramètres**.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-146">On the **Resource availability** page, select **View settings**.</span></span>
6. <span data-ttu-id="1ebcb-147">Dans la page **Régler les paramètres de la vue**, entrez des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="1ebcb-147">On the **Adjust view settings** page, enter the following values:</span></span>

    - <span data-ttu-id="1ebcb-148">**Format pour la vue de la plage de dates :** Jour</span><span class="sxs-lookup"><span data-stu-id="1ebcb-148">**Format for date range view:** Day</span></span>
    - <span data-ttu-id="1ebcb-149">**Afficher les descriptions disponibles :** Oui</span><span class="sxs-lookup"><span data-stu-id="1ebcb-149">**Display availability descriptions:** Yes</span></span>
    - <span data-ttu-id="1ebcb-150">**Afficher la capacité restante :** Oui</span><span class="sxs-lookup"><span data-stu-id="1ebcb-150">**Display remaining capacity:** Yes</span></span>

7. <span data-ttu-id="1ebcb-151">Dans la liste des ressources, sélectionnez une ressource.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-151">In the list of resources, select a resource.</span></span>
8. <span data-ttu-id="1ebcb-152">Sélectionnez **Effectuer une réservation fixe** et **Capacité totale**.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-152">Select **Hard book** and **Full capacity**.</span></span>

## <a name="assign-a-resource-to-a-default-role"></a><span data-ttu-id="1ebcb-153">Affectez une ressource à un rôle par défaut</span><span class="sxs-lookup"><span data-stu-id="1ebcb-153">Assign a resource to a default role</span></span>

<span data-ttu-id="1ebcb-154">Pour aider les responsables de ressources ou de projet, ils peuvent zoomer en avant sur les ressources qui peuvent être réservées à un projet.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-154">To help project or resource managers can drill down further on the resources that can be reserved for a project.</span></span> <span data-ttu-id="1ebcb-155">Vous pouvez associer un rôle par défaut à une ressource existante ou une ressource récemment acquise.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-155">You can associate a default role with an existing resource or a newly acquired resource.</span></span> <span data-ttu-id="1ebcb-156">Par exemple, lorsque Daniel a été embauché, il avait l’expérience et les qualifications requises pour remplir le rôle d’analyste d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-156">For example, when Daniel was hired, he had the experience and skills to fill the Business analyst role.</span></span> <span data-ttu-id="1ebcb-157">Le gestionnaire de ressources a affecté ce rôle comme rôle par défaut de Daniel.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-157">The resource manager assigned this role as Daniel's default role.</span></span> <span data-ttu-id="1ebcb-158">Par conséquent, le responsable des ressources a ajouté Daniel à un groupe d’analystes d’entreprise qui sont disponibles pour les projets.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-158">Therefore, the resource manager added Daniel to a pool of business analysts who are available to work on projects.</span></span>

<span data-ttu-id="1ebcb-159">Lors de la réservation des ressources, les chefs de projet peuvent filtrer les ressources de rôles disponibles pour travailler sur des projets.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-159">During resource reservation, project managers can filter the role resources that are available to work on projects.</span></span> <span data-ttu-id="1ebcb-160">Ils peuvent utiliser ces informations comme un critère lorsqu’ils exécutent une analyse de décision multi-critères au cours du traitement des ressources.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-160">They can use this information as one criterion when they perform multi-criteria decision analysis during resource fulfillment.</span></span> <span data-ttu-id="1ebcb-161">Ils peuvent également ajouter d’autres caractéristiques de ressource au filtre pour rechercher des ressources possédant des qualifications spécifiques, une formation et de l’expérience pour un projet donné.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-161">They can also add other resource characteristics to the filter to search for resources that have specific skills, education, and experience for a given project.</span></span>

<span data-ttu-id="1ebcb-162">**Scénario :** Un projet approuvé a démarré et le rôle de chef de projet senior a été réservé en tant que ressource planifiée lors du stade de planification du projet.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-162">**Scenario:** An approved project has started, and the Senior project manager role was reserved as a planned resource during the project planning stage.</span></span> <span data-ttu-id="1ebcb-163">Le gestionnaire de ressources a désormais acquis une ressource pour traiter le rôle de gestionnaire de projet senior.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-163">The resource manager has now acquired a resource to fulfill the Senior project manager role.</span></span>

1. <span data-ttu-id="1ebcb-164">Sur la page **Liste des ressources**, sélectionnez **Daniel Goldschmidt**.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-164">On the **Resources list** page, select **Daniel Goldschmidt**.</span></span>
2. <span data-ttu-id="1ebcb-165">Sur la page **Rôle de la ressource**, sélectionnez **Nouveau**, puis entrez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="1ebcb-165">On the **Resource role** page, select **New**, and enter the following values:</span></span>

    - <span data-ttu-id="1ebcb-166">**Date d’effet :** Saisissez la date actuelle.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-166">**Effective:** Enter the current date.</span></span>
    - <span data-ttu-id="1ebcb-167">**Expiration :** Définissez **Jamais**.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-167">**Expiration:** Enter **Never**.</span></span>
    - <span data-ttu-id="1ebcb-168">**ID rôle :** Définissez **Chef de projet senior**.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-168">**Role:** Enter **Senior Project Manager**.</span></span>

3. <span data-ttu-id="1ebcb-169">Sélectionnez **Sauvegarder**, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-169">Select **Save**, and then close the page.</span></span>
4. <span data-ttu-id="1ebcb-170">Sous l’onglet **Compétences**, ajoutez la qualification **ProjectMgmt** et le certificat **PMP**.</span><span class="sxs-lookup"><span data-stu-id="1ebcb-170">On the **Competencies** tab, add the **ProjectMgmt** skill and the **PMP** certificate.</span></span>
