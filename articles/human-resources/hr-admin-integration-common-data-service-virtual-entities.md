---
title: Configurer les entités virtuelles de Common Data Service
description: Cette rubrique montre comment configurer des entités virtuelles pour Dynamics 365 Human Resources. Générez et mettez à jour des entités virtuelles existantes et analysez les entités générées et disponibles.
author: andreabichsel
manager: tfehr
ms.date: 11/02/2020
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
ms.openlocfilehash: 2b590faeab600d04c9d5303693ec1e9ac682250d
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645599"
---
# <a name="configure-common-data-service-virtual-entities"></a><span data-ttu-id="af026-104">Configurer les entités virtuelles de Common Data Service</span><span class="sxs-lookup"><span data-stu-id="af026-104">Configure Common Data Service virtual entities</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="af026-105">Dynamics 365 Human Resources est une source de données virtuelle dans Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="af026-105">Dynamics 365 Human Resources is a virtual data source in Common Data Service.</span></span> <span data-ttu-id="af026-106">Il fournit des opérations de création, de lecture, de mise à jour et de suppression (CRUD) complètes à partir de Common Data Service et Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="af026-106">It provides full create, read, update, and delete (CRUD) operations from Common Data Service and Microsoft Power Platform.</span></span> <span data-ttu-id="af026-107">Les données des entités virtuelles ne sont pas stockées dans Common Data Service, mais dans la base de données de l'application.</span><span class="sxs-lookup"><span data-stu-id="af026-107">The data for virtual entities isn't stored in Common Data Service, but in the application database.</span></span> 

<span data-ttu-id="af026-108">Pour activer les opérations CRUD sur les entités Ressources humaines à partir de Common Data Service, vous devez rendre les entités disponibles en tant qu'entités virtuelles dans Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="af026-108">To enable CRUD operations on Human Resources entities from Common Data Service, you must make the entities available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="af026-109">Cela vous permet d'effectuer des opérations CRUD à partir de Common Data Service et Microsoft Power Platform sur les données contenues dans les ressources humaines.</span><span class="sxs-lookup"><span data-stu-id="af026-109">This lets you perform CRUD operations from Common Data Service and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="af026-110">Les opérations prennent également en charge les validations complètes de la logique métier de Human Resources pour garantir l'intégrité des données lors de l'écriture des données dans les entités.</span><span class="sxs-lookup"><span data-stu-id="af026-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

## <a name="available-virtual-entities-for-human-resources"></a><span data-ttu-id="af026-111">Entités virtuelles disponibles pour Human Resources</span><span class="sxs-lookup"><span data-stu-id="af026-111">Available virtual entities for Human Resources</span></span>

<span data-ttu-id="af026-112">Toutes les entités Open Data Protocol (OData) dans Human Resources sont disponibles en tant qu'entités virtuelles dans Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="af026-112">All Open Data Protocol (OData) entities in Human Resources are available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="af026-113">Elles sont également disponibles dans Power Platform.</span><span class="sxs-lookup"><span data-stu-id="af026-113">They're also available in Power Platform.</span></span> <span data-ttu-id="af026-114">Vous pouvez désormais créer des applications et des expériences avec des données directement à partir de Human Resources avec une capacité CRUD complète, sans copier ni synchroniser les données vers Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="af026-114">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Common Data Service.</span></span> <span data-ttu-id="af026-115">Vous pouvez utiliser des portails Power Apps pour créer des sites Web externes qui permettent des scénarios de collaboration pour les processus métier dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="af026-115">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="af026-116">Vous pouvez afficher la liste des entités virtuelles activées dans l'environnement et commencer à travailler avec les entités dans [Power Apps](https://make.powerapps.com), dans la solution **Entités virtuelles Dynamics 365 HR**.</span><span class="sxs-lookup"><span data-stu-id="af026-116">You can view the list of virtual entities enabled in the environment, and begin working with the entities in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Entities** solution.</span></span>

![Entités virtuelles Dynamics 365 HR dans Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-entities-versus-natural-entities"></a><span data-ttu-id="af026-118">Entités virtuelles et entités naturelles</span><span class="sxs-lookup"><span data-stu-id="af026-118">Virtual entities versus natural entities</span></span>

<span data-ttu-id="af026-119">Les entités virtuelles pour Human Resources ne sont pas les mêmes que les entités Common Data Service créées pour Human Resources.</span><span class="sxs-lookup"><span data-stu-id="af026-119">Virtual entities for Human Resources aren't the same as the natural Common Data Service entities created for Human Resources.</span></span> <span data-ttu-id="af026-120">Les entités naturelles de Human Resources sont générées séparément et gérées dans la solution HCM Common dans Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="af026-120">The natural entities for Human Resources are generated separately and maintained in the HCM Common solution in Common Data Service.</span></span> <span data-ttu-id="af026-121">Avec les entités naturelles, les données sont stockées dans Common Data Service et elles nécessitent une synchronisation avec la base de données applicative de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="af026-121">With natural entities, the data is stored in Common Data Service and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="af026-122">Pour une liste des entités naturelles Common Data Service pour Human Resources, voir [Entités Common Data Service](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span><span class="sxs-lookup"><span data-stu-id="af026-122">For a list of the natural Common Data Service entities for Human Resources, see [Common Data Service entities](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span></span>

## <a name="setup"></a><span data-ttu-id="af026-123">Paramétrage</span><span class="sxs-lookup"><span data-stu-id="af026-123">Setup</span></span>

<span data-ttu-id="af026-124">Suivez ces étapes de configuration pour activer les entités virtuelles dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="af026-124">Follow these setup steps to enable virtual entities in your environment.</span></span>

### <a name="enable-virtual-entities-in-human-resources"></a><span data-ttu-id="af026-125">Activer des entités virtuelles dans Human Resources</span><span class="sxs-lookup"><span data-stu-id="af026-125">Enable virtual entities in Human Resources</span></span>

<span data-ttu-id="af026-126">Tout d'abord, vous devez activer les entités virtuelles dans l'espace de travail **Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="af026-126">First, you must enable virtual entities in the **Feature management** workspace.</span></span>

1. <span data-ttu-id="af026-127">Dans Human Resources, sélectionnez **Administration du système**.</span><span class="sxs-lookup"><span data-stu-id="af026-127">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="af026-128">Sélectionnez la vignette **Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="af026-128">Select the **Feature management** tile.</span></span>

3. <span data-ttu-id="af026-129">Sélectionnez **Prise en charge d'entités virtuelles dans HR/CDS**, puis sélectionnez **Activer**.</span><span class="sxs-lookup"><span data-stu-id="af026-129">Select **Virtual Entity support in HR/CDS**, and then select **Enable**.</span></span>

<span data-ttu-id="af026-130">Pour plus d’informations sur l’activation et la désactivation des fonctionnalités en version préliminaire, consultez [Gérer les fonctionnalités](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="af026-130">For more information about enabling and disabling features, see [Manage features](hr-admin-manage-features.md).</span></span>

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="af026-131">Enregistrez l'application dans Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="af026-131">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="af026-132">Vous devez inscrire votre instance de Human Resources dans le portail Azure afin que la plateforme d'identité Microsoft puisse fournir des services d'authentification et d'autorisation pour l'application et les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="af026-132">You must register your Human Resources instance in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="af026-133">Pour plus d'informations sur l'enregistrement des applications dans Azure, voir [Démarrage rapide : enregistrer une application avec la plate-forme d'identité Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="af026-133">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="af026-134">Ouvrez le portail [Microsoft Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="af026-134">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="af026-135">Dans la liste de services Azure, cliquez sur **Enregistrements d'application**.</span><span class="sxs-lookup"><span data-stu-id="af026-135">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="af026-136">Sélectionnez **Nouvelle inscription**.</span><span class="sxs-lookup"><span data-stu-id="af026-136">Select **New registration**.</span></span>

4. <span data-ttu-id="af026-137">Dans le champ **Nom**, entrez un nom descriptif pour l'application.</span><span class="sxs-lookup"><span data-stu-id="af026-137">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="af026-138">Par exemple, **Entités virtuelles Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="af026-138">For example, **Dynamics 365 Human Resources Virtual Entities**.</span></span>

5. <span data-ttu-id="af026-139">Dans le champ **URI de redirection**, saisissez l'URL de l'espace de noms de votre instance Human Resources.</span><span class="sxs-lookup"><span data-stu-id="af026-139">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="af026-140">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="af026-140">Select **Register**.</span></span>

7. <span data-ttu-id="af026-141">Une fois l'inscription terminée, le portail Azure affiche le volet **Aperçu** d'inscription de l'application, qui comprend son **ID d'application (client)**.</span><span class="sxs-lookup"><span data-stu-id="af026-141">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="af026-142">Prenez note de l'**ID d'application (client)** à ce stade.</span><span class="sxs-lookup"><span data-stu-id="af026-142">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="af026-143">Vous saisirez ces informations lorsque vous [Configurerez la source de données d'entité virtuelle](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="af026-143">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

8. <span data-ttu-id="af026-144">Dans le volet de navigation de gauche, sélectionnez **Certificats et secrets**.</span><span class="sxs-lookup"><span data-stu-id="af026-144">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="af026-145">Dans la section **Clés secrètes client** de la page, sélectionnez **Nouvelle clé secrète client**.</span><span class="sxs-lookup"><span data-stu-id="af026-145">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="af026-146">Fournissez une description, sélectionnez une durée et sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="af026-146">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="af026-147">Enregistrez la valeur du secret.</span><span class="sxs-lookup"><span data-stu-id="af026-147">Record the secret's value.</span></span> <span data-ttu-id="af026-148">Vous saisirez ces informations lorsque vous [Configurerez la source de données d'entité virtuelle](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="af026-148">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="af026-149">Assurez-vous de prendre note de la valeur du secret à ce stade.</span><span class="sxs-lookup"><span data-stu-id="af026-149">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="af026-150">Le secret n'est plus jamais affiché une fois que vous avez quitté cette page.</span><span class="sxs-lookup"><span data-stu-id="af026-150">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-entity-app"></a><span data-ttu-id="af026-151">Installez l'application Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="af026-151">Install the Dynamics 365 HR Virtual Entity app</span></span>

<span data-ttu-id="af026-152">Installez l'application Dynamics 365 HR Virtual Entity dans votre environnement Power Apps pour déployer le package de solution d'entité virtuelle dans Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="af026-152">Install the Dynamics 365 HR Virtual Entity app in your Power Apps environment to deploy the virtual entity solution package to Common Data Service.</span></span>

1. <span data-ttu-id="af026-153">Ouvrez le [Centre d'administration Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="af026-153">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="af026-154">Dans la liste **Environnements**, sélectionnez l'environnement Power Apps associé à votre instance Human Resources.</span><span class="sxs-lookup"><span data-stu-id="af026-154">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="af026-155">Dans la section **Ressources** de la page, sélectionnez **Applications Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="af026-155">In the **Resources** section of the page, select **Dynamics 365 apps**.</span></span>

4. <span data-ttu-id="af026-156">Sélectionnez l'option **Installer l'application**.</span><span class="sxs-lookup"><span data-stu-id="af026-156">Select the **Install app** action.</span></span>

5. <span data-ttu-id="af026-157">Sélectionnez **Dynamics 365 HR Virtual Entity** et sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="af026-157">Select **Dynamics 365 HR Virtual Entity**, and select **Next**.</span></span>

6. <span data-ttu-id="af026-158">Passez en revue et acceptez les conditions d’utilisation du service.</span><span class="sxs-lookup"><span data-stu-id="af026-158">Review and mark to agree to the terms of service.</span></span>

7. <span data-ttu-id="af026-159">Sélectionnez **Installer**.</span><span class="sxs-lookup"><span data-stu-id="af026-159">Select **Install**.</span></span>

<span data-ttu-id="af026-160">L'installation prend quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="af026-160">The install takes a few minutes.</span></span> <span data-ttu-id="af026-161">Lorsqu'elle est terminée, passez aux étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="af026-161">When it completes, continue to the next steps.</span></span>

![Installez l'application Dynamics 365 HR Virtual Entity à partir du Centre d'administration Power Platform](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-entity-data-source"></a><span data-ttu-id="af026-163">Configurer la source de données d'entité virtuelle</span><span class="sxs-lookup"><span data-stu-id="af026-163">Configure the virtual entity data source</span></span> 

<span data-ttu-id="af026-164">L'étape suivante consiste à configurer la source de données d'entité virtuelle dans l' environnement Power Apps.</span><span class="sxs-lookup"><span data-stu-id="af026-164">The next step is to configure the virtual entity data source in the Power Apps environment.</span></span> 

1. <span data-ttu-id="af026-165">Ouvrez le [Centre d'administration Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="af026-165">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="af026-166">Dans la liste **Environnements**, sélectionnez l'environnement Power Apps associé à votre instance Human Resources.</span><span class="sxs-lookup"><span data-stu-id="af026-166">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="af026-167">Sélectionnez l'**URL d'environnement** dans la section **Détails** de la page.</span><span class="sxs-lookup"><span data-stu-id="af026-167">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="af026-168">Dans **Hub état solution**, sélectionnez l'icône **Recherche avancée** en haut à droite de la page de l'application.</span><span class="sxs-lookup"><span data-stu-id="af026-168">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="af026-169">Sur la page **Recherche avancée**, dans la liste déroulante **Rechercher**, sélectionnez Configurations de source de données virtuelle **Finance and Operations**.</span><span class="sxs-lookup"><span data-stu-id="af026-169">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

6. <span data-ttu-id="af026-170">Sélectionnez **Résultats**.</span><span class="sxs-lookup"><span data-stu-id="af026-170">Select **Results**.</span></span>

7. <span data-ttu-id="af026-171">Sélectionnez l'enregistrement **Source de données Microsoft HR**.</span><span class="sxs-lookup"><span data-stu-id="af026-171">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="af026-172">Entrez les informations requises pour la configuration de la source de données :</span><span class="sxs-lookup"><span data-stu-id="af026-172">Enter the required information for the data source configuration:</span></span>

   - <span data-ttu-id="af026-173">**URL cible** : URL de votre espace de noms Human Resources.</span><span class="sxs-lookup"><span data-stu-id="af026-173">**Target URL**: The URL of your Human Resources namespace.</span></span> <span data-ttu-id="af026-174">Le format de l'URL cible est :</span><span class="sxs-lookup"><span data-stu-id="af026-174">The format of the target URL is:</span></span>
     
     <span data-ttu-id="af026-175">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span><span class="sxs-lookup"><span data-stu-id="af026-175">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span></span>

     <span data-ttu-id="af026-176">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="af026-176">For example:</span></span>
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     ><span data-ttu-id="af026-177">Assurez-vous d'inclure le caractère "**/**" à la fin de l'URL pour éviter de recevoir une erreur.</span><span class="sxs-lookup"><span data-stu-id="af026-177">Be sure to include the "**/**" character at the end of the URL to avoid receiving an error.</span></span>

   - <span data-ttu-id="af026-178">**ID du locataire** : ID du locataire Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="af026-178">**Tenant ID**: The Azure Active Directory (Azure AD) tenant ID.</span></span>

   - <span data-ttu-id="af026-179">**ID d'application AAD** : ID d'application (client) créé pour l'application enregistrée dans le portail Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="af026-179">**AAD Application ID**: The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="af026-180">Vous avez reçu ces informations plus tôt au cours de l'étape [Enregistrer l'application dans Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="af026-180">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   - <span data-ttu-id="af026-181">**Secret d'application AAD** : clé secrète client créée pour l'application enregistrée dans le portail Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="af026-181">**AAD Application Secret**: The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="af026-182">Vous avez reçu ces informations plus tôt au cours de l'étape [Enregistrer l'application dans Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="af026-182">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   ![Source de données Microsoft HR](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. <span data-ttu-id="af026-184">Sélectionnez **Enregistrer et Fermer**.</span><span class="sxs-lookup"><span data-stu-id="af026-184">Select **Save & Close**.</span></span>

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="af026-185">Accorder des autorisations d'application dans Human Resources</span><span class="sxs-lookup"><span data-stu-id="af026-185">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="af026-186">Accordez des autorisations pour les deux applications Azure AD dans Human Resources :</span><span class="sxs-lookup"><span data-stu-id="af026-186">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="af026-187">L'application créée pour votre locataire dans le portail Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="af026-187">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="af026-188">L'application Dynamics 365 HR Virtual Entity installée dans l'environnement Power Apps</span><span class="sxs-lookup"><span data-stu-id="af026-188">The Dynamics 365 HR Virtual Entity app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="af026-189">Dans Human Resources, ouvrez la page **Azure Active Directory applications**.</span><span class="sxs-lookup"><span data-stu-id="af026-189">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="af026-190">Sélectionnez **Nouveau** pour créer un nouvel enregistrement d'application :</span><span class="sxs-lookup"><span data-stu-id="af026-190">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="af026-191">Dans le champ **ID client**, entrez l'ID client de l'application que vous avez enregistrée dans le portail Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="af026-191">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="af026-192">Dans le champ **Nom**, entrez le nom de l'application que vous avez enregistrée dans le portail Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="af026-192">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="af026-193">Dans le champ **ID utilisateur**, sélectionnez l'ID utilisateur d'un utilisateur avec des autorisations d'administrateur dans Human Resources et l'environnement Power Apps.</span><span class="sxs-lookup"><span data-stu-id="af026-193">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="af026-194">Sélectionnez **Nouveau** pour créer un second enregistrement d'application :</span><span class="sxs-lookup"><span data-stu-id="af026-194">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="af026-195">**ID client** : f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="af026-195">**Client Id**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="af026-196">**Nom** : Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="af026-196">**Name**: Dynamics 365 HR Virtual Entity</span></span>
    - <span data-ttu-id="af026-197">Dans le champ **ID utilisateur**, sélectionnez l'ID utilisateur d'un utilisateur avec des autorisations d'administrateur dans Human Resources et l'environnement Power Apps.</span><span class="sxs-lookup"><span data-stu-id="af026-197">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-entities"></a><span data-ttu-id="af026-198">Générer des entités virtuelles</span><span class="sxs-lookup"><span data-stu-id="af026-198">Generate virtual entities</span></span>

<span data-ttu-id="af026-199">Une fois la configuration terminée, vous pouvez sélectionner les entités virtuelles que vous souhaitez générer et activer dans votre instance Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="af026-199">When setup completes, you can select the virtual entities you want to generate and enable in your Common Data Service instance.</span></span>

1. <span data-ttu-id="af026-200">Dans Human Resources, ouvrez la page **Intégration Common Data Service (CDS)**.</span><span class="sxs-lookup"><span data-stu-id="af026-200">In Human Resources, open the **Common Data Service (CDS) integration** page.</span></span>

2. <span data-ttu-id="af026-201">Sélectionnez l'onglet **Entités virtuelles**.</span><span class="sxs-lookup"><span data-stu-id="af026-201">Select the **Virtual entities** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="af026-202">La bascule **Activer l'entité virtuelle** sera définie sur **Oui** automatiquement lorsque toute la configuration requise est terminée.</span><span class="sxs-lookup"><span data-stu-id="af026-202">The **Enable the virtual entity** toggle will be set to **Yes** automatically when all required setup has been completed.</span></span> <span data-ttu-id="af026-203">Si la bascule est définie sur **Non**, passez en revue les étapes des sections précédentes de ce document pour vous assurer que toutes les configurations préalables sont terminées.</span><span class="sxs-lookup"><span data-stu-id="af026-203">If the toggle is set to **No**, review the steps in previous sections of this document to ensure all prerequisite setup is completed.</span></span>

3. <span data-ttu-id="af026-204">Sélectionnez l'entité ou les entités que vous souhaitez générer dans Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="af026-204">Select the entity or entities you want to generate in Common Data Service.</span></span>

4. <span data-ttu-id="af026-205">Sélectionnez **Générer/actualiser**.</span><span class="sxs-lookup"><span data-stu-id="af026-205">Select **Generate/refresh**.</span></span>

![Intégration de Common Data Service](./media/hr-admin-integration-common-data-service-integration.jpg)

## <a name="check-entity-generation-status"></a><span data-ttu-id="af026-207">Vérifier le statut de la génération d'entité</span><span class="sxs-lookup"><span data-stu-id="af026-207">Check entity generation status</span></span>

<span data-ttu-id="af026-208">Les entités virtuelles sont générées dans Common Data Service via un processus d'arrière-plan asynchrone.</span><span class="sxs-lookup"><span data-stu-id="af026-208">Virtual entities are generated in Common Data Service through an asynchronous background process.</span></span> <span data-ttu-id="af026-209">Les mises à jour sur le processus s'affichent dans le centre d'actions.</span><span class="sxs-lookup"><span data-stu-id="af026-209">Updates on the process display in the action center.</span></span> <span data-ttu-id="af026-210">Les détails du processus, y compris les journaux d'erreurs, apparaissent dans la page **Automatisations de processus**.</span><span class="sxs-lookup"><span data-stu-id="af026-210">Details on the process, including error logs, appear in the **Process automations** page.</span></span>

1. <span data-ttu-id="af026-211">Dans Human Resources, ouvrez la page de liste **Automatisations de processus**.</span><span class="sxs-lookup"><span data-stu-id="af026-211">In Human Resources, open the **Process automations** page.</span></span>

2. <span data-ttu-id="af026-212">Sélectionnez l'onglet **Processus en arrière-plan**.</span><span class="sxs-lookup"><span data-stu-id="af026-212">Select the **Background processes** tab.</span></span>

3. <span data-ttu-id="af026-213">Sélectionnez **Processus d'arrière-plan d'opération asynchrone d'interrogation d'entité virtuelle**.</span><span class="sxs-lookup"><span data-stu-id="af026-213">Select **Virtual entity poll async operation background process**.</span></span>

4. <span data-ttu-id="af026-214">Sélectionnez **Afficher les résultats les plus récents**.</span><span class="sxs-lookup"><span data-stu-id="af026-214">Select **View most recent results**.</span></span>

<span data-ttu-id="af026-215">Le volet coulissant affiche les résultats d'exécution les plus récents du processus.</span><span class="sxs-lookup"><span data-stu-id="af026-215">The slideout pane displays the most recent execution results for the process.</span></span> <span data-ttu-id="af026-216">Vous pouvez afficher le journal du processus, y compris les erreurs renvoyées par Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="af026-216">You can view the log for the process, including any errors returned from Common Data Service.</span></span>

## <a name="see-also"></a><span data-ttu-id="af026-217">Voir également :</span><span class="sxs-lookup"><span data-stu-id="af026-217">See also</span></span>

[<span data-ttu-id="af026-218">Qu'est-ce que Common Data Service ?</span><span class="sxs-lookup"><span data-stu-id="af026-218">What is Common Data Service?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="af026-219">Vue d'ensemble d'entité</span><span class="sxs-lookup"><span data-stu-id="af026-219">Entity overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="af026-220">Vue d'ensemble des relations d'entité</span><span class="sxs-lookup"><span data-stu-id="af026-220">Entity relationships overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="af026-221">Créer et modifier des entités virtuelles qui contiennent des données provenant d'une source de données externe</span><span class="sxs-lookup"><span data-stu-id="af026-221">Create and edit virtual entities that contain data from an external data source</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="af026-222">Que sont les portails Power Apps ?</span><span class="sxs-lookup"><span data-stu-id="af026-222">What is Power Apps portals?</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="af026-223">Présentation de la création d'applications dans Power Apps</span><span class="sxs-lookup"><span data-stu-id="af026-223">Overview of creating apps in Power Apps</span></span>](https://docs.microsoft.com/powerapps/maker/)
