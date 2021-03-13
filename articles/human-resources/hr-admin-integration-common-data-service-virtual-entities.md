---
title: Configurer des tables virtuelles Dataverse
description: Cette rubrique montre comment configurer des tables virtuelles pour Dynamics 365 Human Resources. Générez et mettez à jour des tables virtuelles existantes et analysez les tables générées et disponibles.
author: andreabichsel
manager: tfehr
ms.date: 01/25/2021
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
ms.openlocfilehash: cd299b51e38cc30c3e18f3ef9de1f43fa817b840
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112567"
---
# <a name="configure-dataverse-virtual-tables"></a><span data-ttu-id="cc9bb-104">Configurer des tables virtuelles Dataverse</span><span class="sxs-lookup"><span data-stu-id="cc9bb-104">Configure Dataverse virtual tables</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="cc9bb-105">Dynamics 365 Human Resources est une source de données virtuelle dans Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-105">Dynamics 365 Human Resources is a virtual data source in Microsoft Dataverse.</span></span> <span data-ttu-id="cc9bb-106">Il fournit des opérations de création, de lecture, de mise à jour et de suppression (CRUD) complètes à partir de Dataverse et Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-106">It provides full create, read, update, and delete (CRUD) operations from Dataverse and Microsoft Power Platform.</span></span> <span data-ttu-id="cc9bb-107">Les données des tables virtuelles ne sont pas stockées dans Dataverse, mais dans la base de données de l'application.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-107">The data for virtual tables isn't stored in Dataverse, but in the application database.</span></span>

<span data-ttu-id="cc9bb-108">Pour activer les opérations CRUD sur les entités Ressources humaines à partir de Dataverse, vous devez rendre les entités disponibles en tant que tables virtuelles dans Dataverse.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-108">To enable CRUD operations on Human Resources entities from Dataverse, you must make the entities available as virtual tables in Dataverse.</span></span> <span data-ttu-id="cc9bb-109">Cela vous permet d'effectuer des opérations CRUD à partir de Dataverse et Microsoft Power Platform sur les données contenues dans les ressources humaines.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-109">This lets you perform CRUD operations from Dataverse and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="cc9bb-110">Les opérations prennent également en charge les validations complètes de la logique métier de Human Resources pour garantir l'intégrité des données lors de l'écriture des données dans les entités.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

> [!NOTE]
> <span data-ttu-id="cc9bb-111">Les entités Human Resources correspondent aux tables Dataverse.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-111">Human Resources entities correspond to Dataverse tables.</span></span> <span data-ttu-id="cc9bb-112">Pour plus d'informations sur Dataverse (auparavant Common Data Service) et les mises à jour terminologiques, voir [Qu'est-ce que Microsoft Dataverse ?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="cc9bb-112">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span></span>

## <a name="available-virtual-tables-for-human-resources"></a><span data-ttu-id="cc9bb-113">Tables virtuelles disponibles pour Human Resources</span><span class="sxs-lookup"><span data-stu-id="cc9bb-113">Available virtual tables for Human Resources</span></span>

<span data-ttu-id="cc9bb-114">Toutes les entités Open Data Protocol (OData) dans Human Resources sont disponibles en tant que tables virtuelles dans Dataverse.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-114">All Open Data Protocol (OData) entities in Human Resources are available as virtual tables in Dataverse.</span></span> <span data-ttu-id="cc9bb-115">Elles sont également disponibles dans Power Platform.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-115">They're also available in Power Platform.</span></span> <span data-ttu-id="cc9bb-116">Vous pouvez désormais créer des applications et des expériences avec des données directement à partir de Human Resources avec une capacité CRUD complète, sans copier ni synchroniser les données vers Dataverse.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-116">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Dataverse.</span></span> <span data-ttu-id="cc9bb-117">Vous pouvez utiliser des portails Power Apps pour créer des sites Web externes qui permettent des scénarios de collaboration pour les processus métier dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-117">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="cc9bb-118">Vous pouvez afficher la liste des tables virtuelles activées dans l'environnement et commencer à travailler avec les tables dans [Power Apps](https://make.powerapps.com), dans la solution **Tables virtuelles Dynamics 365 HR**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-118">You can view the list of virtual tables enabled in the environment, and begin working with the tables in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Tables** solution.</span></span>

![Tables virtuelles Dynamics 365 HR dans Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-tables-versus-native-tables"></a><span data-ttu-id="cc9bb-120">Tables virtuelles et tables natives</span><span class="sxs-lookup"><span data-stu-id="cc9bb-120">Virtual tables versus native tables</span></span>

<span data-ttu-id="cc9bb-121">Les tables virtuelles pour Human Resources ne sont pas les mêmes que les tables Dataverse créées pour Human Resources.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-121">Virtual tables for Human Resources aren't the same as the native Dataverse tables created for Human Resources.</span></span> 

<span data-ttu-id="cc9bb-122">Les tables natives de Human Resources sont générées séparément et gérées dans la solution HCM Common dans Dataverse.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-122">The native tables for Human Resources are generated separately and maintained in the HCM Common solution in Dataverse.</span></span> <span data-ttu-id="cc9bb-123">Avec les tables natives, les données sont stockées dans Dataverse et elles nécessitent une synchronisation avec la base de données applicative de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-123">With native tables, the data is stored in Dataverse and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="cc9bb-124">Pour obtenir la liste des tables Dataverse natives pour Human Resources, voir [Tables Dataverse](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span><span class="sxs-lookup"><span data-stu-id="cc9bb-124">For a list of the native Dataverse tables for Human Resources, see [Dataverse tables](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span></span>

## <a name="setup"></a><span data-ttu-id="cc9bb-125">Paramétrage</span><span class="sxs-lookup"><span data-stu-id="cc9bb-125">Setup</span></span>

<span data-ttu-id="cc9bb-126">Suivez ces étapes de configuration pour activer les tables virtuelles dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-126">Follow these setup steps to enable virtual tables in your environment.</span></span>

### <a name="enable-virtual-tables-in-human-resources"></a><span data-ttu-id="cc9bb-127">Activer des tables virtuelles dans Human Resources</span><span class="sxs-lookup"><span data-stu-id="cc9bb-127">Enable virtual tables in Human Resources</span></span>

<span data-ttu-id="cc9bb-128">Tout d'abord, vous devez activer les tables virtuelles dans l'espace de travail **Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-128">First, you must enable virtual tables in the **Feature management** workspace.</span></span>

1. <span data-ttu-id="cc9bb-129">Dans Human Resources, sélectionnez **Administration du système**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-129">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="cc9bb-130">Sélectionnez la vignette **Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-130">Select the **Feature management** tile.</span></span>

3. <span data-ttu-id="cc9bb-131">Sélectionnez **Prise en charge de tables virtuelles pour HR dans Dataverse**, puis sélectionnez **Activer**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-131">Select **Virtual table support for HR in Dataverse**, and then select **Enable**.</span></span>

<span data-ttu-id="cc9bb-132">Pour plus d’informations sur l’activation et la désactivation des fonctionnalités en version préliminaire, consultez [Gérer les fonctionnalités](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="cc9bb-132">For more information about enabling and disabling features, see [Manage features](hr-admin-manage-features.md).</span></span>

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="cc9bb-133">Enregistrez l'application dans Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="cc9bb-133">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="cc9bb-134">Vous devez inscrire votre instance de Human Resources dans le portail Azure afin que la plateforme d'identité Microsoft puisse fournir des services d'authentification et d'autorisation pour l'application et les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-134">You must register your Human Resources instance in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="cc9bb-135">Pour plus d'informations sur l'enregistrement des applications dans Azure, voir [Démarrage rapide : enregistrer une application avec la plate-forme d'identité Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="cc9bb-135">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="cc9bb-136">Ouvrez le portail [Microsoft Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="cc9bb-136">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="cc9bb-137">Dans la liste de services Azure, cliquez sur **Enregistrements d'application**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-137">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="cc9bb-138">Sélectionnez **Nouvelle inscription**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-138">Select **New registration**.</span></span>

4. <span data-ttu-id="cc9bb-139">Dans le champ **Nom**, entrez un nom descriptif pour l'application.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-139">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="cc9bb-140">Par exemple, **Tables virtuelles Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-140">For example, **Dynamics 365 Human Resources Virtual Tables**.</span></span>

5. <span data-ttu-id="cc9bb-141">Dans le champ **URI de redirection**, saisissez l'URL de l'espace de noms de votre instance Human Resources.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-141">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="cc9bb-142">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-142">Select **Register**.</span></span>

7. <span data-ttu-id="cc9bb-143">Une fois l'inscription terminée, le portail Azure affiche le volet **Aperçu** d'inscription de l'application, qui comprend son **ID d'application (client)**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-143">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="cc9bb-144">Prenez note de l'**ID d'application (client)** à ce stade.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-144">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="cc9bb-145">Vous devez saisir ces informations lorsque vous [Configurez la source de données de table virtuelle](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span><span class="sxs-lookup"><span data-stu-id="cc9bb-145">You'll enter this information when you [Configure the virtual table data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span></span>

8. <span data-ttu-id="cc9bb-146">Dans le volet de navigation de gauche, sélectionnez **Certificats et secrets**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-146">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="cc9bb-147">Dans la section **Clés secrètes client** de la page, sélectionnez **Nouvelle clé secrète client**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-147">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="cc9bb-148">Fournissez une description, sélectionnez une durée et sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-148">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="cc9bb-149">Enregistrez la valeur du secret.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-149">Record the secret's value.</span></span> <span data-ttu-id="cc9bb-150">Vous devez saisir ces informations lorsque vous [Configurez la source de données de table virtuelle](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span><span class="sxs-lookup"><span data-stu-id="cc9bb-150">You'll enter this information when you [Configure the virtual table data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="cc9bb-151">Assurez-vous de prendre note de la valeur du secret à ce stade.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-151">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="cc9bb-152">Le secret n'est plus jamais affiché une fois que vous avez quitté cette page.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-152">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-table-app"></a><span data-ttu-id="cc9bb-153">Installer l'application Tables virtuelles Dynamics 365 HR</span><span class="sxs-lookup"><span data-stu-id="cc9bb-153">Install the Dynamics 365 HR Virtual Table app</span></span>

<span data-ttu-id="cc9bb-154">Installez l'application Tables virtuelles Dynamics 365 HR dans votre environnement Power Apps pour déployer le package de solution de table virtuelle dans Dataverse.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-154">Install the Dynamics 365 HR Virtual Table app in your Power Apps environment to deploy the virtual table solution package to Dataverse.</span></span>

1. <span data-ttu-id="cc9bb-155">Ouvrez le [Centre d'administration Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="cc9bb-155">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="cc9bb-156">Dans la liste **Environnements**, sélectionnez l'environnement Power Apps associé à votre instance Human Resources.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-156">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="cc9bb-157">Dans la section **Ressources** de la page, sélectionnez **Applications Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-157">In the **Resources** section of the page, select **Dynamics 365 apps**.</span></span>

4. <span data-ttu-id="cc9bb-158">Sélectionnez l'option **Installer l'application**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-158">Select the **Install app** action.</span></span>

5. <span data-ttu-id="cc9bb-159">Sélectionnez **Tables virtuelles Dynamics 365 HR** et sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-159">Select **Dynamics 365 HR Virtual Table**, and select **Next**.</span></span>

6. <span data-ttu-id="cc9bb-160">Passez en revue et acceptez les conditions d’utilisation du service.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-160">Review and mark to agree to the terms of service.</span></span>

7. <span data-ttu-id="cc9bb-161">Sélectionnez **Installer**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-161">Select **Install**.</span></span>

<span data-ttu-id="cc9bb-162">L'installation prend quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-162">The install takes a few minutes.</span></span> <span data-ttu-id="cc9bb-163">Lorsqu'elle est terminée, passez aux étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-163">When it completes, continue to the next steps.</span></span>

![Installez l'application Tables virtuelles Dynamics 365 HR à partir du Centre d'administration Power Platform](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-table-data-source"></a><span data-ttu-id="cc9bb-165">Configurer la source de données de table virtuelle</span><span class="sxs-lookup"><span data-stu-id="cc9bb-165">Configure the virtual table data source</span></span> 

<span data-ttu-id="cc9bb-166">L'étape suivante consiste à configurer la source de données de table virtuelle dans l'environnement Power Apps.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-166">The next step is to configure the virtual table data source in the Power Apps environment.</span></span> 

1. <span data-ttu-id="cc9bb-167">Ouvrez le [Centre d'administration Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="cc9bb-167">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="cc9bb-168">Dans la liste **Environnements**, sélectionnez l'environnement Power Apps associé à votre instance Human Resources.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-168">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="cc9bb-169">Sélectionnez l'**URL d'environnement** dans la section **Détails** de la page.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-169">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="cc9bb-170">Dans **Hub état solution**, sélectionnez l'icône **Recherche avancée** en haut à droite de la page de l'application.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-170">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="cc9bb-171">Sur la page **Recherche avancée**, dans la liste déroulante **Rechercher**, sélectionnez Configurations de source de données virtuelle **Finance and Operations**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-171">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

6. <span data-ttu-id="cc9bb-172">Sélectionnez **Résultats**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-172">Select **Results**.</span></span>

7. <span data-ttu-id="cc9bb-173">Sélectionnez l'enregistrement **Source de données Microsoft HR**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-173">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="cc9bb-174">Entrez les informations requises pour la configuration de la source de données :</span><span class="sxs-lookup"><span data-stu-id="cc9bb-174">Enter the required information for the data source configuration:</span></span>

   - <span data-ttu-id="cc9bb-175">**URL cible** : URL de votre espace de noms Human Resources.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-175">**Target URL**: The URL of your Human Resources namespace.</span></span> <span data-ttu-id="cc9bb-176">Le format de l'URL cible est :</span><span class="sxs-lookup"><span data-stu-id="cc9bb-176">The format of the target URL is:</span></span>
     
     <span data-ttu-id="cc9bb-177">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span><span class="sxs-lookup"><span data-stu-id="cc9bb-177">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span></span>

     <span data-ttu-id="cc9bb-178">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="cc9bb-178">For example:</span></span>
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     ><span data-ttu-id="cc9bb-179">Assurez-vous d'inclure le caractère "**/**" à la fin de l'URL pour éviter de recevoir une erreur.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-179">Be sure to include the "**/**" character at the end of the URL to avoid receiving an error.</span></span>

   - <span data-ttu-id="cc9bb-180">**ID du locataire** : ID du locataire Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="cc9bb-180">**Tenant ID**: The Azure Active Directory (Azure AD) tenant ID.</span></span>

   - <span data-ttu-id="cc9bb-181">**ID d'application AAD** : ID d'application (client) créé pour l'application enregistrée dans le portail Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-181">**AAD Application ID**: The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="cc9bb-182">Vous avez reçu ces informations plus tôt au cours de l'étape [Enregistrer l'application dans Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="cc9bb-182">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   - <span data-ttu-id="cc9bb-183">**Secret d'application AAD** : clé secrète client créée pour l'application enregistrée dans le portail Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-183">**AAD Application Secret**: The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="cc9bb-184">Vous avez reçu ces informations plus tôt au cours de l'étape [Enregistrer l'application dans Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="cc9bb-184">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   ![Source de données Microsoft HR](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. <span data-ttu-id="cc9bb-186">Sélectionnez **Enregistrer et Fermer**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-186">Select **Save & Close**.</span></span>

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="cc9bb-187">Accorder des autorisations d'application dans Human Resources</span><span class="sxs-lookup"><span data-stu-id="cc9bb-187">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="cc9bb-188">Accordez des autorisations pour les deux applications Azure AD dans Human Resources :</span><span class="sxs-lookup"><span data-stu-id="cc9bb-188">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="cc9bb-189">L'application créée pour votre locataire dans le portail Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="cc9bb-189">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="cc9bb-190">L'application Tables virtuelles Dynamics 365 HR installée dans l'environnement Power Apps</span><span class="sxs-lookup"><span data-stu-id="cc9bb-190">The Dynamics 365 HR Virtual Table app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="cc9bb-191">Dans Human Resources, ouvrez la page **Azure Active Directory applications**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-191">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="cc9bb-192">Sélectionnez **Nouveau** pour créer un nouvel enregistrement d'application :</span><span class="sxs-lookup"><span data-stu-id="cc9bb-192">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="cc9bb-193">Dans le champ **ID client**, entrez l'ID client de l'application que vous avez enregistrée dans le portail Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-193">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="cc9bb-194">Dans le champ **Nom**, entrez le nom de l'application que vous avez enregistrée dans le portail Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-194">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="cc9bb-195">Dans le champ **ID utilisateur**, sélectionnez l'ID utilisateur d'un utilisateur avec des autorisations d'administrateur dans Human Resources et l'environnement Power Apps.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-195">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="cc9bb-196">Sélectionnez **Nouveau** pour créer un second enregistrement d'application :</span><span class="sxs-lookup"><span data-stu-id="cc9bb-196">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="cc9bb-197">**ID client** : f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="cc9bb-197">**Client Id**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="cc9bb-198">**Nom** : Tables virtuelles Dynamics 365 HR</span><span class="sxs-lookup"><span data-stu-id="cc9bb-198">**Name**: Dynamics 365 HR Virtual Table</span></span>
    - <span data-ttu-id="cc9bb-199">Dans le champ **ID utilisateur**, sélectionnez l'ID utilisateur d'un utilisateur avec des autorisations d'administrateur dans Human Resources et l'environnement Power Apps.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-199">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-tables"></a><span data-ttu-id="cc9bb-200">Générer des tables virtuelles</span><span class="sxs-lookup"><span data-stu-id="cc9bb-200">Generate virtual tables</span></span>

<span data-ttu-id="cc9bb-201">Une fois la configuration terminée, vous pouvez sélectionner les tables virtuelles que vous souhaitez générer et activer dans votre instance Dataverse.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-201">When setup completes, you can select the virtual tables you want to generate and enable in your Dataverse instance.</span></span>

1. <span data-ttu-id="cc9bb-202">Dans Human Resources, ouvrez la page **Intégration Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-202">In Human Resources, open the **Dataverse integration** page.</span></span>

2. <span data-ttu-id="cc9bb-203">Sélectionnez l'onglet **Tables virtuelles**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-203">Select the **Virtual tables** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="cc9bb-204">La bascule **Activer les tables virtuelles** sera définie sur **Oui** automatiquement lorsque toute la configuration requise est terminée.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-204">The **Enable virtual tables** toggle will be set to **Yes** automatically when all required setup has been completed.</span></span> <span data-ttu-id="cc9bb-205">Si la bascule est définie sur **Non**, passez en revue les étapes des sections précédentes de ce document pour vous assurer que toutes les configurations préalables sont terminées.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-205">If the toggle is set to **No**, review the steps in previous sections of this document to ensure all prerequisite setup is completed.</span></span>

3. <span data-ttu-id="cc9bb-206">Sélectionnez la table ou les tables que vous souhaitez générer dans Dataverse.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-206">Select the table or tables you want to generate in Dataverse.</span></span>

4. <span data-ttu-id="cc9bb-207">Sélectionnez **Générer/actualiser**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-207">Select **Generate/refresh**.</span></span>

![Intégration de Dataverse](./media/hr-admin-integration-common-data-service-integration.jpg)

## <a name="check-table-generation-status"></a><span data-ttu-id="cc9bb-209">Vérifier le statut de la génération de la table</span><span class="sxs-lookup"><span data-stu-id="cc9bb-209">Check table generation status</span></span>

<span data-ttu-id="cc9bb-210">Les tables virtuelles sont générées dans Dataverse via un processus d'arrière-plan asynchrone.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-210">Virtual tables are generated in Dataverse through an asynchronous background process.</span></span> <span data-ttu-id="cc9bb-211">Les mises à jour sur le processus s'affichent dans le centre d'actions.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-211">Updates on the process display in the action center.</span></span> <span data-ttu-id="cc9bb-212">Les détails du processus, y compris les journaux d'erreurs, apparaissent dans la page **Automatisations de processus**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-212">Details on the process, including error logs, appear in the **Process automations** page.</span></span>

1. <span data-ttu-id="cc9bb-213">Dans Human Resources, ouvrez la page de liste **Automatisations de processus**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-213">In Human Resources, open the **Process automations** page.</span></span>

2. <span data-ttu-id="cc9bb-214">Sélectionnez l'onglet **Processus en arrière-plan**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-214">Select the **Background processes** tab.</span></span>

3. <span data-ttu-id="cc9bb-215">Sélectionnez **Processus d'arrière-plan d'opération asynchrone d'interrogation de table virtuelle**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-215">Select **Virtual table poll async operation background process**.</span></span>

4. <span data-ttu-id="cc9bb-216">Sélectionnez **Afficher les résultats les plus récents**.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-216">Select **View most recent results**.</span></span>

<span data-ttu-id="cc9bb-217">Le volet coulissant affiche les résultats d'exécution les plus récents du processus.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-217">The slideout pane displays the most recent execution results for the process.</span></span> <span data-ttu-id="cc9bb-218">Vous pouvez afficher le journal du processus, y compris les erreurs renvoyées par Dataverse.</span><span class="sxs-lookup"><span data-stu-id="cc9bb-218">You can view the log for the process, including any errors returned from Dataverse.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc9bb-219">Voir également :</span><span class="sxs-lookup"><span data-stu-id="cc9bb-219">See also</span></span>

[<span data-ttu-id="cc9bb-220">Qu'est-ce que Dataverse ?</span><span class="sxs-lookup"><span data-stu-id="cc9bb-220">What is Dataverse?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="cc9bb-221">Tables dans Dataverse</span><span class="sxs-lookup"><span data-stu-id="cc9bb-221">Tables in Dataverse</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="cc9bb-222">Vue d'ensemble des relations de table</span><span class="sxs-lookup"><span data-stu-id="cc9bb-222">Table relationships overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="cc9bb-223">Créer et modifier des tables virtuelles qui contiennent des données provenant d'une source de données externe</span><span class="sxs-lookup"><span data-stu-id="cc9bb-223">Create and edit virtual tables that contain data from an external data source</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="cc9bb-224">Que sont les portails Power Apps ?</span><span class="sxs-lookup"><span data-stu-id="cc9bb-224">What is Power Apps portals?</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="cc9bb-225">Présentation de la création d'applications dans Power Apps</span><span class="sxs-lookup"><span data-stu-id="cc9bb-225">Overview of creating apps in Power Apps</span></span>](https://docs.microsoft.com/powerapps/maker/)
