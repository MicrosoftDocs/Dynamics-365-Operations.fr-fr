---
title: Configurer les entités virtuelles de Common Data Service
description: Cette rubrique montre comment configurer des entités virtuelles pour Dynamics 365 Human Resources. Générez et mettez à jour des entités virtuelles existantes et analysez les entités générées et disponibles.
author: andreabichsel
manager: tfehr
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0848b7556100fba38fcab0aa2a1a109e2e055fc9
ms.sourcegitcommit: b89baab13e530b5b1f079231619c628309a4742d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/05/2020
ms.locfileid: "3959573"
---
# <a name="configure-common-data-service-virtual-entities"></a><span data-ttu-id="8e1a5-104">Configurer les entités virtuelles de Common Data Service</span><span class="sxs-lookup"><span data-stu-id="8e1a5-104">Configure Common Data Service virtual entities</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="8e1a5-105">Dynamics 365 Human Resources est une source de données virtuelle dans Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-105">Dynamics 365 Human Resources is a virtual data source in Common Data Service.</span></span> <span data-ttu-id="8e1a5-106">Il fournit des opérations de création, de lecture, de mise à jour et de suppression (CRUD) complètes à partir de Common Data Service et Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-106">It provides full create, read, update, and delete (CRUD) operations from Common Data Service and Microsoft Power Platform.</span></span> <span data-ttu-id="8e1a5-107">Les données des entités virtuelles ne sont pas stockées dans Common Data Service, mais dans la base de données de l'application.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-107">The data for virtual entities isn't stored in Common Data Service, but in the application database.</span></span> 

<span data-ttu-id="8e1a5-108">Pour activer les opérations CRUD sur les entités Ressources humaines à partir de Common Data Service, vous devez rendre les entités disponibles en tant qu'entités virtuelles dans Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-108">To enable CRUD operations on Human Resources entities from Common Data Service, you must make the entities available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="8e1a5-109">Cela vous permet d'effectuer des opérations CRUD à partir de Common Data Service et Microsoft Power Platform sur les données contenues dans les ressources humaines.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-109">This lets you perform CRUD operations from Common Data Service and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="8e1a5-110">Les opérations prennent également en charge les validations complètes de la logique métier de Human Resources pour garantir l'intégrité des données lors de l'écriture des données dans les entités.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

## <a name="available-virtual-entities-for-human-resources"></a><span data-ttu-id="8e1a5-111">Entités virtuelles disponibles pour Human Resources</span><span class="sxs-lookup"><span data-stu-id="8e1a5-111">Available virtual entities for Human Resources</span></span>

<span data-ttu-id="8e1a5-112">Toutes les entités Open Data Protocol (OData) dans Human Resources sont disponibles en tant qu'entités virtuelles dans Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-112">All Open Data Protocol (OData) entities in Human Resources are available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="8e1a5-113">Elles sont également disponibles dans Power Platform.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-113">They're also available in Power Platform.</span></span> <span data-ttu-id="8e1a5-114">Vous pouvez désormais créer des applications et des expériences avec des données directement à partir de Human Resources avec une capacité CRUD complète, sans copier ni synchroniser les données vers Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-114">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Common Data Service.</span></span> <span data-ttu-id="8e1a5-115">Vous pouvez utiliser des portails Power Apps pour créer des sites Web externes qui permettent des scénarios de collaboration pour les processus métier dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-115">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="8e1a5-116">Vous pouvez afficher la liste des entités virtuelles activées dans l'environnement et commencer à travailler avec les entités dans [Power Apps](https://make.powerapps.com), dans la solution **Entités virtuelles Dynamics 365 HR**.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-116">You can view the list of virtual entities enabled in the environment, and begin working with the entities in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Entities** solution.</span></span>

![Entités virtuelles Dynamics 365 HR dans Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-entities-versus-natural-entities"></a><span data-ttu-id="8e1a5-118">Entités virtuelles et entités naturelles</span><span class="sxs-lookup"><span data-stu-id="8e1a5-118">Virtual entities versus natural entities</span></span>

<span data-ttu-id="8e1a5-119">Les entités virtuelles pour Human Resources ne sont pas les mêmes que les entités Common Data Service créées pour Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-119">Virtual entities for Human Resources aren't the same as the natural Common Data Service entities created for Human Resources.</span></span> <span data-ttu-id="8e1a5-120">Les entités naturelles de Human Resources sont générées séparément et gérées dans la solution HCM Common dans Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-120">The natural entities for Human Resources are generated separately and maintained in the HCM Common solution in Common Data Service.</span></span> <span data-ttu-id="8e1a5-121">Avec les entités naturelles, les données sont stockées dans Common Data Service et elles nécessitent une synchronisation avec la base de données applicative de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-121">With natural entities, the data is stored in Common Data Service and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="8e1a5-122">Pour une liste des entités naturelles Common Data Service pour Human Resources, voir [Entités Common Data Service](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span><span class="sxs-lookup"><span data-stu-id="8e1a5-122">For a list of the natural Common Data Service entities for Human Resources, see [Common Data Service entities](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span></span>

## <a name="setup"></a><span data-ttu-id="8e1a5-123">Paramétrage</span><span class="sxs-lookup"><span data-stu-id="8e1a5-123">Setup</span></span>

<span data-ttu-id="8e1a5-124">Suivez ces étapes de configuration pour activer les entités virtuelles dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-124">Follow these setup steps to enable virtual entities in your environment.</span></span> 

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="8e1a5-125">Enregistrez l'application dans Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="8e1a5-125">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="8e1a5-126">Tout d'abord, vous devez inscrire l'application dans le portail Azure afin que la plateforme d'identité Microsoft puisse fournir des services d'authentification et d'autorisation pour l'application et les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-126">First, you need to register the app in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="8e1a5-127">Pour plus d'informations sur l'enregistrement des applications dans Azure, voir [Démarrage rapide : enregistrer une application avec la plate-forme d'identité Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="8e1a5-127">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="8e1a5-128">Ouvrez le portail [Microsoft Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="8e1a5-128">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="8e1a5-129">Dans la liste de services Azure, cliquez sur **Enregistrements d'application**.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-129">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="8e1a5-130">Sélectionnez **Nouvelle inscription**.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-130">Select **New registration**.</span></span>

4. <span data-ttu-id="8e1a5-131">Dans le champ **Nom**, entrez un nom descriptif pour l'application.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-131">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="8e1a5-132">Par exemple, **Entités virtuelles Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-132">For example, **Dynamics 365 Human Resources Virtual Entities**.</span></span>

5. <span data-ttu-id="8e1a5-133">Dans le champ **URI de redirection**, saisissez l'URL de l'espace de noms de votre instance Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-133">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="8e1a5-134">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-134">Select **Register**.</span></span>

7. <span data-ttu-id="8e1a5-135">Une fois l'inscription terminée, le portail Azure affiche le volet **Aperçu** d'inscription de l'application, qui comprend son **ID d'application (client)**.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-135">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="8e1a5-136">Prenez note de l'**ID d'application (client)** à ce stade.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-136">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="8e1a5-137">Vous saisirez ces informations lorsque vous [Configurerez la source de données d'entité virtuelle](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="8e1a5-137">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

8. <span data-ttu-id="8e1a5-138">Dans le volet de navigation de gauche, sélectionnez **Certificats et secrets**.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-138">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="8e1a5-139">Dans la section **Clés secrètes client** de la page, sélectionnez **Nouvelle clé secrète client**.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-139">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="8e1a5-140">Fournissez une description, sélectionnez une durée et sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-140">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="8e1a5-141">Enregistrez la valeur du secret.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-141">Record the secret's value.</span></span> <span data-ttu-id="8e1a5-142">Vous saisirez ces informations lorsque vous [Configurerez la source de données d'entité virtuelle](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="8e1a5-142">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8e1a5-143">Assurez-vous de prendre note de la valeur du secret à ce stade.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-143">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="8e1a5-144">Le secret n'est plus jamais affiché une fois que vous avez quitté cette page.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-144">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-entity-app"></a><span data-ttu-id="8e1a5-145">Installez l'application Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="8e1a5-145">Install the Dynamics 365 HR Virtual Entity app</span></span>

<span data-ttu-id="8e1a5-146">Installez l'application Dynamics 365 HR Virtual Entity dans votre environnement Power Apps pour déployer le package de solution d'entité virtuelle dans Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-146">Install the Dynamics 365 HR Virtual Entity app in your Power Apps environment to deploy the virtual entity solution package to Common Data Service.</span></span>

1. <span data-ttu-id="8e1a5-147">Ouvrez le [Centre d'administration Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="8e1a5-147">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="8e1a5-148">Dans la liste **Environnements**, sélectionnez l'environnement Power Apps associé à votre instance Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-148">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="8e1a5-149">Dans la section **Ressources** de la page, sélectionnez **Applications Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-149">In the **Resources** section of the page, select **Dynamics 365 apps**.</span></span>

4. <span data-ttu-id="8e1a5-150">Sélectionnez l'option **Installer l'application**.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-150">Select the **Install app** action.</span></span>

5. <span data-ttu-id="8e1a5-151">Sélectionnez **Dynamics 365 HR Virtual Entity** et sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-151">Select **Dynamics 365 HR Virtual Entity**, and select **Next**.</span></span>

6. <span data-ttu-id="8e1a5-152">Passez en revue et acceptez les conditions d’utilisation du service.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-152">Review and mark to agree to the terms of service.</span></span>

7. <span data-ttu-id="8e1a5-153">Sélectionnez **Installer**.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-153">Select **Install**.</span></span>

<span data-ttu-id="8e1a5-154">L'installation prend quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-154">The install takes a few minutes.</span></span> <span data-ttu-id="8e1a5-155">Lorsqu'elle est terminée, passez aux étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-155">When it completes, continue to the next steps.</span></span>

![Installez l'application Dynamics 365 HR Virtual Entity à partir du Centre d'administration Power Platform](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-entity-data-source"></a><span data-ttu-id="8e1a5-157">Configurer la source de données d'entité virtuelle</span><span class="sxs-lookup"><span data-stu-id="8e1a5-157">Configure the virtual entity data source</span></span> 

<span data-ttu-id="8e1a5-158">L'étape suivante consiste à configurer la source de données d'entité virtuelle dans l' environnement Power Apps.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-158">The next step is to configure the virtual entity data source in the Power Apps environment.</span></span> 

1. <span data-ttu-id="8e1a5-159">Ouvrez le [Centre d'administration Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="8e1a5-159">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="8e1a5-160">Dans la liste **Environnements**, sélectionnez l'environnement Power Apps associé à votre instance Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-160">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="8e1a5-161">Sélectionnez l'**URL d'environnement** dans la section **Détails** de la page.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-161">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="8e1a5-162">Dans **Hub état solution**, sélectionnez l'icône **Recherche avancée** en haut à droite de la page de l'application.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-162">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="8e1a5-163">Sur la page **Recherche avancée**, dans la liste déroulante **Rechercher**, sélectionnez Configurations de source de données virtuelle **Finance and Operations**.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-163">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

6. <span data-ttu-id="8e1a5-164">Sélectionnez **Résultats**.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-164">Select **Results**.</span></span>

7. <span data-ttu-id="8e1a5-165">Sélectionnez l'enregistrement **Source de données Microsoft HR**.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-165">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="8e1a5-166">Entrez les informations requises pour la configuration de la source de données.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-166">Enter the required information for the data source configuration.</span></span>

   - <span data-ttu-id="8e1a5-167">**URL cible** : URL de votre espace de noms Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-167">**Target URL**: The URL of your Human Resources namespace.</span></span>
   - <span data-ttu-id="8e1a5-168">**ID du locataire** : ID du locataire Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="8e1a5-168">**Tenant ID**: The Azure Active Directory (Azure AD) tenant ID.</span></span>
   - <span data-ttu-id="8e1a5-169">**ID d'application AAD** : ID d'application (client) créé pour l'application enregistrée dans le portail Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-169">**AAD Application ID**: The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="8e1a5-170">Vous avez reçu ces informations plus tôt au cours de l'étape [Enregistrer l'application dans Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="8e1a5-170">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>
   - <span data-ttu-id="8e1a5-171">**Secret d'application AAD** : clé secrète client créée pour l'application enregistrée dans le portail Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-171">**AAD Application Secret**: The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="8e1a5-172">Vous avez reçu ces informations plus tôt au cours de l'étape [Enregistrer l'application dans Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="8e1a5-172">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

9. <span data-ttu-id="8e1a5-173">Sélectionnez **Enregistrer et Fermer**.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-173">Select **Save & Close**.</span></span>

   ![Source de données Microsoft HR](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="8e1a5-175">Accorder des autorisations d'application dans Human Resources</span><span class="sxs-lookup"><span data-stu-id="8e1a5-175">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="8e1a5-176">Accordez des autorisations pour les deux applications Azure AD dans Human Resources :</span><span class="sxs-lookup"><span data-stu-id="8e1a5-176">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="8e1a5-177">L'application créée pour votre locataire dans le portail Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="8e1a5-177">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="8e1a5-178">L'application Dynamics 365 HR Virtual Entity installée dans l'environnement Power Apps</span><span class="sxs-lookup"><span data-stu-id="8e1a5-178">The Dynamics 365 HR Virtual Entity app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="8e1a5-179">Dans Human Resources, ouvrez la page **Azure Active Directory applications**.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-179">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="8e1a5-180">Sélectionnez **Nouveau** pour créer un nouvel enregistrement d'application :</span><span class="sxs-lookup"><span data-stu-id="8e1a5-180">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="8e1a5-181">Dans le champ **ID client**, entrez l'ID client de l'application que vous avez enregistrée dans le portail Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-181">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="8e1a5-182">Dans le champ **Nom**, entrez le nom de l'application que vous avez enregistrée dans le portail Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-182">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="8e1a5-183">Dans le champ **ID utilisateur**, sélectionnez l'ID utilisateur d'un utilisateur avec des autorisations d'administrateur dans Human Resources et l'environnement Power Apps.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-183">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="8e1a5-184">Sélectionnez **Nouveau** pour créer un second enregistrement d'application :</span><span class="sxs-lookup"><span data-stu-id="8e1a5-184">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="8e1a5-185">**ID client** : f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="8e1a5-185">**Client Id**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="8e1a5-186">**Nom** : Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="8e1a5-186">**Name**: Dynamics 365 HR Virtual Entity</span></span>
    - <span data-ttu-id="8e1a5-187">Dans le champ **ID utilisateur**, sélectionnez l'ID utilisateur d'un utilisateur avec des autorisations d'administrateur dans Human Resources et l'environnement Power Apps.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-187">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-entities"></a><span data-ttu-id="8e1a5-188">Générer des entités virtuelles</span><span class="sxs-lookup"><span data-stu-id="8e1a5-188">Generate virtual entities</span></span>

<span data-ttu-id="8e1a5-189">Une fois la configuration terminée, vous pouvez sélectionner les entités virtuelles que vous souhaitez générer et activer dans votre instance Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-189">When setup completes, you can select the virtual entities you want to generate and enable in your Common Data Service instance.</span></span>

1. <span data-ttu-id="8e1a5-190">Ouvrez le [Centre d'administration Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="8e1a5-190">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="8e1a5-191">Dans la liste **Environnements**, sélectionnez l'environnement Power Apps associé à votre instance Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-191">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="8e1a5-192">Sélectionnez l'**URL d'environnement** dans la section **Détails** de la page.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-192">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="8e1a5-193">Dans **Hub état solution**, sélectionnez l'icône **Recherche avancée** en haut à droite de la page.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-193">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the page.</span></span>

5. <span data-ttu-id="8e1a5-194">Sur la page **Recherche avancée**, dans la liste déroulante **Rechercher**, sélectionnez **Entités HR disponibles**.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-194">On the **Advanced Find** page, in the **Look for** dropdown list, select **Available HR Entities**.</span></span>

6. <span data-ttu-id="8e1a5-195">Utilisez les options de filtre pour trouver l'entité ou les entités que vous souhaitez activer.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-195">Use the filter options to find the entity or entities you want to enable.</span></span>

7. <span data-ttu-id="8e1a5-196">Sélectionnez une entité dans la liste.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-196">Select an entity from the list.</span></span>

8. <span data-ttu-id="8e1a5-197">Sur la page d'entité, définissez la propriété **A été généré** sur **Oui** pour l'entité.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-197">On the entity page, change the **Has Been Generated** property to **Yes** for the entity.</span></span>

9. <span data-ttu-id="8e1a5-198">Enregistrez et fermez la page d'entité.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-198">Save and close the entity page.</span></span>

> [!NOTE]
> <span data-ttu-id="8e1a5-199">Vous pouvez générer plusieurs entités virtuelles à la fois en utilisant la page **Modifier plusieurs enregistrements**.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-199">You can generate multiple virtual entities at once by using the **Change Multiple Records** page.</span></span> <span data-ttu-id="8e1a5-200">Sélectionnez plusieurs enregistrements sur la page, puis sélectionnez **Éditer** sur le ruban.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-200">Select multiple records on the page, and select **Edit** on the ribbon.</span></span> <span data-ttu-id="8e1a5-201">Vous pouvez ensuite modifier la propriété **A été généré** pour tous les enregistrements sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-201">You can then change the **Has Been Generated** property for all selected records.</span></span>

![Entités RH disponibles](./media/hr-admin-integration-virtual-entities-available.jpg)

> [!NOTE]
> <span data-ttu-id="8e1a5-203">Pour rationaliser le processus de génération d'entités virtuelles dans les versions futures, le processus se déroulera dans une page de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8e1a5-203">To streamline the process of generating virtual entities in future releases, the process will occur in a page in Human Resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e1a5-204">Voir également :</span><span class="sxs-lookup"><span data-stu-id="8e1a5-204">See also</span></span>

[<span data-ttu-id="8e1a5-205">Qu'est-ce que Common Data Service ?</span><span class="sxs-lookup"><span data-stu-id="8e1a5-205">What is Common Data Service?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="8e1a5-206">Vue d'ensemble d'entité</span><span class="sxs-lookup"><span data-stu-id="8e1a5-206">Entity overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="8e1a5-207">Vue d'ensemble des relations d'entité</span><span class="sxs-lookup"><span data-stu-id="8e1a5-207">Entity relationships overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="8e1a5-208">Créer et modifier des entités virtuelles qui contiennent des données provenant d'une source de données externe</span><span class="sxs-lookup"><span data-stu-id="8e1a5-208">Create and edit virtual entities that contain data from an external data source</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="8e1a5-209">Que sont les portails Power Apps ?</span><span class="sxs-lookup"><span data-stu-id="8e1a5-209">What is Power Apps portals?</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="8e1a5-210">Présentation de la création d'applications dans Power Apps</span><span class="sxs-lookup"><span data-stu-id="8e1a5-210">Overview of creating apps in Power Apps</span></span>](https://docs.microsoft.com/powerapps/maker/)
