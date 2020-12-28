---
title: Intégration avec LinkedIn Talent Hub
description: Cette rubrique explique comment paramétrer l'intégration entre Microsoft Dynamics 365 Human Resources et LinkedIn Talent Hub.
author: jaredha
manager: tfehr
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6f70e3a6ccf9770c75334d355db5e9df9ee912dd
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527883"
---
# <a name="integrate-with-linkedin-talent-hub"></a><span data-ttu-id="63623-103">Intégration avec LinkedIn Talent Hub</span><span class="sxs-lookup"><span data-stu-id="63623-103">Integrate with LinkedIn Talent Hub</span></span>

[!include [banner](includes/preview-feature.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="63623-104">[LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub) est une plateforme de système de suivi des candidats (ATS).</span><span class="sxs-lookup"><span data-stu-id="63623-104">[LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub) is an applicant tracking system (ATS) platform.</span></span> <span data-ttu-id="63623-105">Elle vous permet de trouver, gérer et embaucher des employés en un seul endroit.</span><span class="sxs-lookup"><span data-stu-id="63623-105">It lets you source, manage, and hire employees all in one place.</span></span> <span data-ttu-id="63623-106">En intégrant Microsoft Dynamics 365 Human Resources avec LinkedIn Talent Hub, vous pouvez facilement créer des enregistrements d'employés dans Human Resources pour les candidats qui ont été embauchés pour un poste.</span><span class="sxs-lookup"><span data-stu-id="63623-106">By integrating Microsoft Dynamics 365 Human Resources with LinkedIn Talent Hub, you can easily create employee records in Human Resources for applicants who have been hired for a position.</span></span>

## <a name="setup"></a><span data-ttu-id="63623-107">Paramétrage</span><span class="sxs-lookup"><span data-stu-id="63623-107">Setup</span></span>

<span data-ttu-id="63623-108">Un administrateur système doit effectuer les tâches de configuration pour permettre l'intégration avec LinkedIn Talent Hub.</span><span class="sxs-lookup"><span data-stu-id="63623-108">A system administrator must complete setup tasks to enable integration with LinkedIn Talent Hub.</span></span> <span data-ttu-id="63623-109">Premièrement, dans l'environnement Power Apps, vous devez configurer un utilisateur et un rôle de sécurité pour accorder à LinkedIn Talent Hub les autorisations appropriées pour écrire des données dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="63623-109">First, in the Power Apps environment, you must set up a user and security role to grant LinkedIn Talent Hub the appropriate permissions to write data into Human Resources.</span></span>

### <a name="link-your-environment-to-linkedin-talent-hub"></a><span data-ttu-id="63623-110">Lier votre environnement à LinkedIn Talent Hub</span><span class="sxs-lookup"><span data-stu-id="63623-110">Link your environment to LinkedIn Talent Hub</span></span>

1. <span data-ttu-id="63623-111">Ouvrez [LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub).</span><span class="sxs-lookup"><span data-stu-id="63623-111">Open [LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub).</span></span>

2. <span data-ttu-id="63623-112">Dans le menu déroulant de l'utilisateur, sélectionnez **Paramètres du produit**.</span><span class="sxs-lookup"><span data-stu-id="63623-112">On the user drop-down menu, select **Product Settings**.</span></span>

3. <span data-ttu-id="63623-113">Dans le volet de navigation de gauche, dans la section **Avancés**, sélectionnez **Intégrations**.</span><span class="sxs-lookup"><span data-stu-id="63623-113">In the left navigation pane, in the **Advanced** section, select **Integrations**.</span></span>

4. <span data-ttu-id="63623-114">Sélectionnez **Autoriser** pour l'intégration de Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="63623-114">Select **Authorize** for the Microsoft Dynamics 365 Human Resources integration.</span></span>

5. <span data-ttu-id="63623-115">Sur la page **Dynamics 365 Human Resources**, sélectionnez l'environnement auquel lier LinkedIn Talent Hub, puis sélectionnez **Lien**.</span><span class="sxs-lookup"><span data-stu-id="63623-115">On the **Dynamics 365 Human Resources** page, select the environment to link LinkedIn Talent Hub to, and then select **Link**.</span></span>

    ![Intégration de LinkedIn Talent Hub](./media/hr-admin-integration-talent-hub-onboarding.jpg)

    > [!NOTE]
    > <span data-ttu-id="63623-117">Vous pouvez créer un lien uniquement vers les environnements dans lesquels votre compte utilisateur dispose d'un accès administrateur à la fois à l'environnement Human Resources et à l'environnement Power Apps associé.</span><span class="sxs-lookup"><span data-stu-id="63623-117">You can link only to environments where your user account has administrator access to both the Human Resources environment and the associated Power Apps environment.</span></span> <span data-ttu-id="63623-118">Si aucun environnement n'est répertorié sur la page de liens Human Resources, assurez-vous que vous disposez d'environnements Human Resources sous licence sur le client et que l'utilisateur que vous avez connecté à la page de liens dispose des autorisations d'administrateur sur l'environnement Human Resources et sur l'environnement Power Apps.</span><span class="sxs-lookup"><span data-stu-id="63623-118">If no environments are listed on the Human Resources link page, make sure that you have licensed Human Resources environments on the tenant, and that the user that you signed in to the link page as has administrator permissions to both the Human Resources environment and the Power Apps environment.</span></span>

### <a name="create-a-power-apps-security-role"></a><span data-ttu-id="63623-119">Création d’un rôle de sécurité Power Apps</span><span class="sxs-lookup"><span data-stu-id="63623-119">Create a Power Apps security role</span></span>

1. <span data-ttu-id="63623-120">Ouvrez le [Centre d'administration Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="63623-120">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="63623-121">Dans la liste **Environnements**, sélectionnez l'environnement associé à l'environnement Human Resources auquel vous souhaitez lier votre instance de LinkedIn Talent Hub.</span><span class="sxs-lookup"><span data-stu-id="63623-121">In the **Environments** list, select the environment that is associated with the Human Resources environment that you want to link your instance of LinkedIn Talent Hub to.</span></span>

3. <span data-ttu-id="63623-122">Sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="63623-122">Select **Settings**.</span></span>

4. <span data-ttu-id="63623-123">Développez le nœud **Utilisateurs + autorisations**, et sélectionnez **Rôles de sécurité**.</span><span class="sxs-lookup"><span data-stu-id="63623-123">Expand the **Users + Permissions** node, and select **Security Roles**.</span></span>

5. <span data-ttu-id="63623-124">Sur la page **Rôles de sécurité**, dans la barre d'outils, sélectionnez **Nouveau rôle**.</span><span class="sxs-lookup"><span data-stu-id="63623-124">On the **Security Roles** page, on the toolbar, select **New role**.</span></span>

6. <span data-ttu-id="63623-125">Sur l'onglet **Détails**, entrez un nom pour le rôle, tel que **Intégration SIRH LinkedIn Talent Hub**.</span><span class="sxs-lookup"><span data-stu-id="63623-125">On the **Details** tab, enter a name for the role, such as **LinkedIn Talent Hub HRIS Integration**.</span></span>

7. <span data-ttu-id="63623-126">Sur l'onglet **Personnalisation**, sélectionnez l'autorisation de **Lecture** au niveau de l'organisation pour les entités suivantes :</span><span class="sxs-lookup"><span data-stu-id="63623-126">On the **Customization** tab, select organization-level **Read** permission for the following entities:</span></span>

    - <span data-ttu-id="63623-127">Entité</span><span class="sxs-lookup"><span data-stu-id="63623-127">Entity</span></span>
    - <span data-ttu-id="63623-128">Champ</span><span class="sxs-lookup"><span data-stu-id="63623-128">Field</span></span>
    - <span data-ttu-id="63623-129">Relation</span><span class="sxs-lookup"><span data-stu-id="63623-129">Relationship</span></span>

8. <span data-ttu-id="63623-130">Enregistrez et fermez le rôle de sécurité.</span><span class="sxs-lookup"><span data-stu-id="63623-130">Save and close the security role.</span></span>

### <a name="create-a-power-apps-application-user"></a><span data-ttu-id="63623-131">Créer un utilisateur d'application Power Apps</span><span class="sxs-lookup"><span data-stu-id="63623-131">Create a Power Apps application user</span></span>

<span data-ttu-id="63623-132">Un utilisateur d'application doit être créé pour l'adaptateur LinkedIn Talent Hub, pour accorder des autorisations à l'adaptateur pour écrire des enregistrements de candidats dans l'environnement Power Apps.</span><span class="sxs-lookup"><span data-stu-id="63623-132">An application user must be created for the LinkedIn Talent Hub adapter to grant permissions to the adapter to write candidate records into the Power Apps environment.</span></span>

1. <span data-ttu-id="63623-133">Ouvrez le [Centre d'administration Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="63623-133">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="63623-134">Dans la liste **Environnements**, sélectionnez l'environnement associé à l'environnement Human Resources auquel vous souhaitez lier votre instance de LinkedIn Talent Hub.</span><span class="sxs-lookup"><span data-stu-id="63623-134">In the **Environments** list, select the environment that is associated with the Human Resources environment that you want to link your instance of LinkedIn Talent Hub to.</span></span>

3. <span data-ttu-id="63623-135">Sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="63623-135">Select **Settings**.</span></span>

4. <span data-ttu-id="63623-136">Développez le nœud **Utilisateurs + autorisations**, et sélectionnez **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="63623-136">Expand the **Users + Permissions** node, and select **Users**.</span></span>

5. <span data-ttu-id="63623-137">Sélectionnez **Gérer les utilisateurs dans Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="63623-137">Select **Manage users in Dynamics 365**.</span></span>

6. <span data-ttu-id="63623-138">Utilisez le menu déroulant au-dessus de la liste pour changer la vue de la vue par défaut **Utilisateurs activés** à **Utilisateurs de l'application**.</span><span class="sxs-lookup"><span data-stu-id="63623-138">Use the drop-down menu above the list to change the view from the default **Enabled Users** view to **Application Users**.</span></span>

    ![Vue Utilisateurs de l'application](./media/hr-admin-integration-power-apps-application-users.jpg)

7. <span data-ttu-id="63623-140">Dans la barre d'outils, sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="63623-140">On the toolbar, select **New**.</span></span>

8. <span data-ttu-id="63623-141">Sur la page **Nouvel utilisateur**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="63623-141">On the **New user** page, follow these steps:</span></span>

    1. <span data-ttu-id="63623-142">Changer la valeur du champ **Type d'utilisateur** sur **Utilisateur de l'application**.</span><span class="sxs-lookup"><span data-stu-id="63623-142">Change the value of the **User type** field to **Application User**.</span></span>
    2. <span data-ttu-id="63623-143">Définissez le champ **Nom d'utilisateur** sur **Intégration Dynamics365 HR SIRH LinkedIn**.</span><span class="sxs-lookup"><span data-stu-id="63623-143">Set the **User Name** field to **Dynamics365 HR LinkedIn HRIS Integration**.</span></span>
    3. <span data-ttu-id="63623-144">Définissez le champ **ID application** sur **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span><span class="sxs-lookup"><span data-stu-id="63623-144">Set the **Application ID** field to **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span></span>
    4. <span data-ttu-id="63623-145">Entrez une valeur dans les champs **Prénom**, **Nom de famille** et **Adresse e-mail principale**.</span><span class="sxs-lookup"><span data-stu-id="63623-145">Enter any value in the **First Name**, **Last Name**, and **Primary Email** fields.</span></span>
    5. <span data-ttu-id="63623-146">Dans la barre d'outils, sélectionnez **Enregistrer \& Fermer**.</span><span class="sxs-lookup"><span data-stu-id="63623-146">On the toolbar, select **Save \& Close**.</span></span>

### <a name="assign-a-security-role-to-the-new-user"></a><span data-ttu-id="63623-147">Attribuer un rôle de sécurité à un nouvel utilisateur</span><span class="sxs-lookup"><span data-stu-id="63623-147">Assign a security role to the new user</span></span>

<span data-ttu-id="63623-148">Après avoir enregistré et fermé le nouvel utilisateur de l'application dans la section précédente, vous revenez à la page **Liste des utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="63623-148">After you save and close the new application user in the previous section, you're returned to the **Users list** page.</span></span>

1. <span data-ttu-id="63623-149">Sur la page **Liste des utilisateurs**, changez la vue en **Utilisateurs de l'application**.</span><span class="sxs-lookup"><span data-stu-id="63623-149">On the **Users list** page, change the view to **Application Users**.</span></span>

2. <span data-ttu-id="63623-150">Sélectionnez l'utilisateur de l'application créé dans la section précédente.</span><span class="sxs-lookup"><span data-stu-id="63623-150">Select the application user that you created in the previous section.</span></span>

3. <span data-ttu-id="63623-151">Dans la barre d'outils, sélectionnez **Gérer les rôles**.</span><span class="sxs-lookup"><span data-stu-id="63623-151">On the toolbar, select **Manage Roles**.</span></span>

4. <span data-ttu-id="63623-152">Sélectionnez le rôle de sécurité que vous avez créé précédemment pour l'intégration.</span><span class="sxs-lookup"><span data-stu-id="63623-152">Select the security role that you created earlier for the integration.</span></span>

5. <span data-ttu-id="63623-153">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="63623-153">Select **OK**.</span></span>

### <a name="add-an-azure-active-directory-app-in-human-resources"></a><span data-ttu-id="63623-154">Ajouter une application Azure Active Directory dans Human Resources</span><span class="sxs-lookup"><span data-stu-id="63623-154">Add an Azure Active Directory app in Human Resources</span></span>

1. <span data-ttu-id="63623-155">Dans Dynamics 365 Human Resources, ouvrez la page **Applications Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="63623-155">In Dynamics 365 Human Resources, open the **Azure Active Directory applications** page.</span></span>
2. <span data-ttu-id="63623-156">Ajoutez un nouvel enregistrement à la liste et définissez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="63623-156">Add a new record to the list, and set the following fields:</span></span>

    - <span data-ttu-id="63623-157">**ID client** : Entrez **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span><span class="sxs-lookup"><span data-stu-id="63623-157">**Client ID**: Enter **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span></span>
    - <span data-ttu-id="63623-158">**Nom** : Saisissez le nom du rôle de sécurité Power Apps que vous avez créé précédemment, tel que **Intégration SIRH LinkedIn Talent Hub**.</span><span class="sxs-lookup"><span data-stu-id="63623-158">**Name**: Enter the name of the Power Apps security role that you created earlier, such as **LinkedIn Talent Hub HRIS Integration**.</span></span>
    - <span data-ttu-id="63623-159">**Identifiant utilisateur** : Sélectionnez un utilisateur autorisé à écrire des données dans Gestion du personnel.</span><span class="sxs-lookup"><span data-stu-id="63623-159">**User ID**: Select a user who has permissions to write data in Personnel Management.</span></span>

### <a name="create-the-entity-in-common-data-service"></a><span data-ttu-id="63623-160">Créer l'entité dans Common Data Service</span><span class="sxs-lookup"><span data-stu-id="63623-160">Create the entity in Common Data Service</span></span>

> [!IMPORTANT]
> <span data-ttu-id="63623-161">L'intégration avec LinkedIn Talent Hub dépend des entités virtuelles dans Common Data Service pour Human Resources.</span><span class="sxs-lookup"><span data-stu-id="63623-161">The integration with LinkedIn Talent Hub depends on virtual entities in Common Data Service for Human Resources.</span></span> <span data-ttu-id="63623-162">Comme condition préalable à cette étape de la configuration, vous devez configurer des entités virtuelles.</span><span class="sxs-lookup"><span data-stu-id="63623-162">As a prerequisite for this step in the setup, you must configure virtual entities.</span></span> <span data-ttu-id="63623-163">Pour plus d'informations sur la configuration des entités virtuelles, voir [Configurer des entités virtuelles Common Data Service](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).</span><span class="sxs-lookup"><span data-stu-id="63623-163">For information about how to configure virtual entities, see [Configure Common Data Service virtual entities](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).</span></span>

1. <span data-ttu-id="63623-164">Dans Human Resources, ouvrez la page **Intégration Common Data Service (CDS)**.</span><span class="sxs-lookup"><span data-stu-id="63623-164">In Human Resources, open the **Common Data Service (CDS) integration** page.</span></span>

2. <span data-ttu-id="63623-165">Sélectionnez l'onglet **Entités virtuelles**.</span><span class="sxs-lookup"><span data-stu-id="63623-165">Select the **Virtual entities** tab.</span></span>

3. <span data-ttu-id="63623-166">Filtrez la liste d'entités par étiquette d'entité pour trouver **Candidat exporté par LinkedIn**.</span><span class="sxs-lookup"><span data-stu-id="63623-166">Filter the entity list by entity label to find **LinkedIn exported candidate**.</span></span>

4. <span data-ttu-id="63623-167">Sélectionnez l'entité, puis sélectionnez **Générer/actualiser**.</span><span class="sxs-lookup"><span data-stu-id="63623-167">Select the entity, and then select **Generate/refresh**.</span></span>

## <a name="exporting-candidate-records"></a><span data-ttu-id="63623-168">Exporter les enregistrements de candidats</span><span class="sxs-lookup"><span data-stu-id="63623-168">Exporting candidate records</span></span>

<span data-ttu-id="63623-169">Une fois la configuration terminée, les recruteurs et les professionnels des ressources humaines (RH) peuvent utiliser la fonction **Exporter vers SIRH** dans LinkedIn Talent Hub pour exporter les enregistrements des candidats embauchés de LinkedIn Talent Hub vers Human resources.</span><span class="sxs-lookup"><span data-stu-id="63623-169">After the setup is completed, recruiters and Human resources (HR) professionals can use the **Export to HRIS** function in LinkedIn Talent Hub to export hired candidate records from LinkedIn Talent Hub to Human Resources.</span></span>

### <a name="export-records-from-linkedin-talent-hub"></a><span data-ttu-id="63623-170">Exporter des enregistrements depuis LinkedIn Talent Hub</span><span class="sxs-lookup"><span data-stu-id="63623-170">Export records from LinkedIn Talent Hub</span></span>

<span data-ttu-id="63623-171">Une fois qu'un candidat a franchi le processus de recrutement et a été embauché, vous pouvez exporter l'enregistrement du candidat de LinkedIn Talent Hub vers Human Resources.</span><span class="sxs-lookup"><span data-stu-id="63623-171">After a candidate has moved through the recruiting process and has been hired, you can export the candidate record from LinkedIn Talent Hub to Human Resources.</span></span>

1. <span data-ttu-id="63623-172">Dans LinkedIn Talent Hub, ouvrez le projet pour lequel vous avez embauché le nouvel employé.</span><span class="sxs-lookup"><span data-stu-id="63623-172">In LinkedIn Talent Hub, open the project that you hired the new employee for.</span></span>

2. <span data-ttu-id="63623-173">Sélectionnez un enregistrement de candidat.</span><span class="sxs-lookup"><span data-stu-id="63623-173">Select a candidate record.</span></span>

3. <span data-ttu-id="63623-174">Sélectionnez **Modifier le stade**, puis sélectionnez **Embauché**.</span><span class="sxs-lookup"><span data-stu-id="63623-174">Select **Change stage**, and then select **Hired**.</span></span>

4. <span data-ttu-id="63623-175">Dans le menu de points de suspension (**...**) du candidat, sélectionnez **Exporter vers SIRH**.</span><span class="sxs-lookup"><span data-stu-id="63623-175">On the ellipsis menu (**...**) for the candidate, select **Export to HRIS**.</span></span>

5. <span data-ttu-id="63623-176">Dans le volet **Exporter vers SIRH**, saisissez les informations à exporter :</span><span class="sxs-lookup"><span data-stu-id="63623-176">In the **Export to HRIS** pane, enter the information that must be exported:</span></span>

    - <span data-ttu-id="63623-177">Dans le champ **Fournisseur de SIRH**, sélectionnez **Microsoft Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="63623-177">In the **HRIS provider** field, select **Microsoft Dynamics 365 Human Resources**.</span></span>
    - <span data-ttu-id="63623-178">Dans le champ **Date de début**, sélectionnez une valeur pour le nouvel employé.</span><span class="sxs-lookup"><span data-stu-id="63623-178">In the **Start date** field, select a value for the new employee.</span></span>
    - <span data-ttu-id="63623-179">Dans le champ **Poste**, entrez le titre du poste du nouvel employé.</span><span class="sxs-lookup"><span data-stu-id="63623-179">In the **Job title** field, enter a job title for the new employee's job.</span></span>
    - <span data-ttu-id="63623-180">Dans le champ **Emplacement**, entrez le lieu où sera basé l'employé.</span><span class="sxs-lookup"><span data-stu-id="63623-180">In the **Location** field, enter the location where the employee will be based.</span></span>
    - <span data-ttu-id="63623-181">Saisissez ou vérifiez l'adresse e-mail de l'employé.</span><span class="sxs-lookup"><span data-stu-id="63623-181">Enter or verify the employee's email address.</span></span>

![Volet Exporter vers SIRH dans LinkedIn Talent Hub](./media/hr-admin-integration-linkedin-talent-hub-export.jpg)

## <a name="complete-onboarding-in-human-resources"></a><span data-ttu-id="63623-183">Terminer l'intégration dans Human Resources</span><span class="sxs-lookup"><span data-stu-id="63623-183">Complete onboarding in Human Resources</span></span>

<span data-ttu-id="63623-184">Les enregistrements de candidats exportés de LinkedIn Talent Hub vers Human Resources apparaissent dans la section **Candidats à embaucher** de la page **Gestion du personnel**.</span><span class="sxs-lookup"><span data-stu-id="63623-184">Candidate records that are exported from LinkedIn Talent Hub to Human Resources appear in the **Candidates to hire** section of the **Personnel management** page.</span></span>

1. <span data-ttu-id="63623-185">Dans Human Resources, ouvrez la page **Gestion du personnel**.</span><span class="sxs-lookup"><span data-stu-id="63623-185">In Human Resources, open the **Personnel management** page.</span></span>

2. <span data-ttu-id="63623-186">Dans la section **Candidats à embaucher**, sélectionnez **Embaucher** pour le candidat sélectionné.</span><span class="sxs-lookup"><span data-stu-id="63623-186">In the **Candidates to hire** section, select **Hire** for the selected candidate.</span></span>

3. <span data-ttu-id="63623-187">Dans la boîte de dialogue **Embaucher un nouveau collaborateur**, vérifiez l'enregistrement et ajoutez les informations requises.</span><span class="sxs-lookup"><span data-stu-id="63623-187">In the **Hire new worker** dialog box, review the record, and add any required information.</span></span> <span data-ttu-id="63623-188">Vous pouvez également sélectionner le numéro de poste pour lequel le candidat a été embauché.</span><span class="sxs-lookup"><span data-stu-id="63623-188">You can also select the position number that the candidate has been hired for.</span></span>

<span data-ttu-id="63623-189">Une fois les informations requises saisies, vous pouvez poursuivre vos processus standard de création d'enregistrements d'employés et d'intégration des employés.</span><span class="sxs-lookup"><span data-stu-id="63623-189">After the required information has been entered, you can continue with your standard processes for creating employee records and onboarding employees.</span></span>

<span data-ttu-id="63623-190">Les détails suivants sont importés et inclus dans l'enregistrement d'un nouvel employé :</span><span class="sxs-lookup"><span data-stu-id="63623-190">The following details are imported and included on the new employee record:</span></span>

- <span data-ttu-id="63623-191">Prénom</span><span class="sxs-lookup"><span data-stu-id="63623-191">First name</span></span>
- <span data-ttu-id="63623-192">Nom</span><span class="sxs-lookup"><span data-stu-id="63623-192">Last name</span></span>
- <span data-ttu-id="63623-193">Date de début de l'emploi</span><span class="sxs-lookup"><span data-stu-id="63623-193">Employment start date</span></span>
- <span data-ttu-id="63623-194">Adresse de messagerie</span><span class="sxs-lookup"><span data-stu-id="63623-194">Email address</span></span>
- <span data-ttu-id="63623-195">Numéro de téléphone</span><span class="sxs-lookup"><span data-stu-id="63623-195">Phone number</span></span>

## <a name="see-also"></a><span data-ttu-id="63623-196">Voir également :</span><span class="sxs-lookup"><span data-stu-id="63623-196">See also</span></span>

[<span data-ttu-id="63623-197">Configurer les entités virtuelles Common Data Service</span><span class="sxs-lookup"><span data-stu-id="63623-197">Configure Common Data Service virtual entities</span></span>](./hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="63623-198">Qu'est-ce que Common Data Service ?</span><span class="sxs-lookup"><span data-stu-id="63623-198">What is Common Data Service?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)
