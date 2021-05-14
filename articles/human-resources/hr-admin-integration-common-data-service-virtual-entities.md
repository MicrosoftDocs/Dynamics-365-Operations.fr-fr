---
title: Configurer des tables virtuelles Dataverse
description: Cette rubrique montre comment configurer des tables virtuelles pour Dynamics 365 Human Resources. Générez et mettez à jour des tables virtuelles existantes et analysez les tables générées et disponibles.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 04997aba427ae6013c8154593b09ae1a45a580c3
ms.sourcegitcommit: 9283caad2d0636f98579c995784abec19fda2e3f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2021
ms.locfileid: "5935751"
---
# <a name="configure-dataverse-virtual-tables"></a><span data-ttu-id="af7a4-104">Configurer des tables virtuelles Dataverse</span><span class="sxs-lookup"><span data-stu-id="af7a4-104">Configure Dataverse virtual tables</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="af7a4-105">Dynamics 365 Human Resources est une source de données virtuelle dans Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="af7a4-105">Dynamics 365 Human Resources is a virtual data source in Microsoft Dataverse.</span></span> <span data-ttu-id="af7a4-106">Il fournit des opérations de création, de lecture, de mise à jour et de suppression (CRUD) complètes à partir de Dataverse et Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="af7a4-106">It provides full create, read, update, and delete (CRUD) operations from Dataverse and Microsoft Power Platform.</span></span> <span data-ttu-id="af7a4-107">Les données des tables virtuelles ne sont pas stockées dans Dataverse, mais dans la base de données de l’application.</span><span class="sxs-lookup"><span data-stu-id="af7a4-107">The data for virtual tables isn't stored in Dataverse, but in the application database.</span></span>

<span data-ttu-id="af7a4-108">Pour activer les opérations CRUD sur les entités Ressources humaines à partir de Dataverse, vous devez rendre les entités disponibles en tant que tables virtuelles dans Dataverse.</span><span class="sxs-lookup"><span data-stu-id="af7a4-108">To enable CRUD operations on Human Resources entities from Dataverse, you must make the entities available as virtual tables in Dataverse.</span></span> <span data-ttu-id="af7a4-109">Cela vous permet d’effectuer des opérations CRUD à partir de Dataverse et Microsoft Power Platform sur les données contenues dans les ressources humaines.</span><span class="sxs-lookup"><span data-stu-id="af7a4-109">This lets you perform CRUD operations from Dataverse and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="af7a4-110">Les opérations prennent également en charge les validations complètes de la logique métier de Human Resources pour garantir l’intégrité des données lors de l’écriture des données dans les entités.</span><span class="sxs-lookup"><span data-stu-id="af7a4-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

> [!NOTE]
> <span data-ttu-id="af7a4-111">Les entités Human Resources correspondent aux tables Dataverse.</span><span class="sxs-lookup"><span data-stu-id="af7a4-111">Human Resources entities correspond to Dataverse tables.</span></span> <span data-ttu-id="af7a4-112">Pour plus d’informations sur Dataverse (auparavant Common Data Service) et les mises à jour terminologiques, voir [Qu’est-ce que Microsoft Dataverse ?](/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="af7a4-112">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)</span></span>

## <a name="available-virtual-tables-for-human-resources"></a><span data-ttu-id="af7a4-113">Tables virtuelles disponibles pour Human Resources</span><span class="sxs-lookup"><span data-stu-id="af7a4-113">Available virtual tables for Human Resources</span></span>

<span data-ttu-id="af7a4-114">Toutes les entités Open Data Protocol (OData) dans Human Resources sont disponibles en tant que tables virtuelles dans Dataverse.</span><span class="sxs-lookup"><span data-stu-id="af7a4-114">All Open Data Protocol (OData) entities in Human Resources are available as virtual tables in Dataverse.</span></span> <span data-ttu-id="af7a4-115">Elles sont également disponibles dans Power Platform.</span><span class="sxs-lookup"><span data-stu-id="af7a4-115">They're also available in Power Platform.</span></span> <span data-ttu-id="af7a4-116">Vous pouvez désormais créer des applications et des expériences avec des données directement à partir de Human Resources avec une capacité CRUD complète, sans copier ni synchroniser les données vers Dataverse.</span><span class="sxs-lookup"><span data-stu-id="af7a4-116">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Dataverse.</span></span> <span data-ttu-id="af7a4-117">Vous pouvez utiliser des portails Power Apps pour créer des sites Web externes qui permettent des scénarios de collaboration pour les processus métier dans Human Resources.</span><span class="sxs-lookup"><span data-stu-id="af7a4-117">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="af7a4-118">Vous pouvez afficher la liste des tables virtuelles activées dans l’environnement et commencer à travailler avec les tables dans [Power Apps](https://make.powerapps.com), dans la solution **Tables virtuelles Dynamics 365 HR**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-118">You can view the list of virtual tables enabled in the environment, and begin working with the tables in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Tables** solution.</span></span>

![Tables virtuelles Dynamics 365 HR dans Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-tables-versus-native-tables"></a><span data-ttu-id="af7a4-120">Tables virtuelles et tables natives</span><span class="sxs-lookup"><span data-stu-id="af7a4-120">Virtual tables versus native tables</span></span>

<span data-ttu-id="af7a4-121">Les tables virtuelles pour Human Resources ne sont pas les mêmes que les tables Dataverse créées pour Human Resources.</span><span class="sxs-lookup"><span data-stu-id="af7a4-121">Virtual tables for Human Resources aren't the same as the native Dataverse tables created for Human Resources.</span></span> 

<span data-ttu-id="af7a4-122">Les tables natives de Human Resources sont générées séparément et gérées dans la solution HCM Common dans Dataverse.</span><span class="sxs-lookup"><span data-stu-id="af7a4-122">The native tables for Human Resources are generated separately and maintained in the HCM Common solution in Dataverse.</span></span> <span data-ttu-id="af7a4-123">Avec les tables natives, les données sont stockées dans Dataverse et elles nécessitent une synchronisation avec la base de données applicative de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="af7a4-123">With native tables, the data is stored in Dataverse and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="af7a4-124">Pour obtenir la liste des tables Dataverse natives pour Human Resources, voir [Tables Dataverse](./hr-developer-entities.md).</span><span class="sxs-lookup"><span data-stu-id="af7a4-124">For a list of the native Dataverse tables for Human Resources, see [Dataverse tables](./hr-developer-entities.md).</span></span>

## <a name="setup"></a><span data-ttu-id="af7a4-125">Paramétrage</span><span class="sxs-lookup"><span data-stu-id="af7a4-125">Setup</span></span>

<span data-ttu-id="af7a4-126">Suivez ces étapes de configuration pour activer les tables virtuelles dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="af7a4-126">Follow these setup steps to enable virtual tables in your environment.</span></span>

### <a name="enable-virtual-tables-in-human-resources"></a><span data-ttu-id="af7a4-127">Activer des tables virtuelles dans Human Resources</span><span class="sxs-lookup"><span data-stu-id="af7a4-127">Enable virtual tables in Human Resources</span></span>

<span data-ttu-id="af7a4-128">Tout d’abord, vous devez activer les tables virtuelles dans l’espace de travail **Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-128">First, you must enable virtual tables in the **Feature management** workspace.</span></span>

1. <span data-ttu-id="af7a4-129">Dans Human Resources, sélectionnez **Administration du système**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-129">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="af7a4-130">Sélectionnez la vignette **Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-130">Select the **Feature management** tile.</span></span>

3. <span data-ttu-id="af7a4-131">Sélectionnez **Prise en charge de tables virtuelles pour HR dans Dataverse**, puis sélectionnez **Activer**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-131">Select **Virtual table support for HR in Dataverse**, and then select **Enable**.</span></span>

<span data-ttu-id="af7a4-132">Pour plus d’informations sur l’activation et la désactivation des fonctionnalités en version préliminaire, consultez [Gérer les fonctionnalités](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="af7a4-132">For more information about enabling and disabling features, see [Manage features](hr-admin-manage-features.md).</span></span>

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="af7a4-133">Enregistrez l’application dans Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="af7a4-133">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="af7a4-134">Vous devez inscrire votre instance de Human Resources dans le portail Azure afin que la plateforme d’identité Microsoft puisse fournir des services d’authentification et d’autorisation pour l’application et les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="af7a4-134">You must register your Human Resources instance in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="af7a4-135">Pour plus d’informations sur l’enregistrement des applications dans Azure, voir [Démarrage rapide : enregistrer une application avec la plate-forme d’identité Microsoft](/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="af7a4-135">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="af7a4-136">Ouvrez le portail [Microsoft Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="af7a4-136">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="af7a4-137">Dans la liste de services Azure, cliquez sur **Enregistrements d’application**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-137">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="af7a4-138">Sélectionnez **Nouvelle inscription**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-138">Select **New registration**.</span></span>

4. <span data-ttu-id="af7a4-139">Dans le champ **Nom**, entrez un nom descriptif pour l’application.</span><span class="sxs-lookup"><span data-stu-id="af7a4-139">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="af7a4-140">Par exemple, **Tables virtuelles Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-140">For example, **Dynamics 365 Human Resources Virtual Tables**.</span></span>

5. <span data-ttu-id="af7a4-141">Dans le champ **URI de redirection**, saisissez l’URL de l’espace de noms de votre instance Human Resources.</span><span class="sxs-lookup"><span data-stu-id="af7a4-141">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="af7a4-142">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-142">Select **Register**.</span></span>

7. <span data-ttu-id="af7a4-143">Une fois l’inscription terminée, le portail Azure affiche le volet **Aperçu** d’inscription de l’application, qui comprend son **ID d’application (client)**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-143">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="af7a4-144">Prenez note de l’**ID d’application (client)** à ce stade.</span><span class="sxs-lookup"><span data-stu-id="af7a4-144">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="af7a4-145">Vous devez saisir ces informations lorsque vous [Configurez la source de données de table virtuelle](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span><span class="sxs-lookup"><span data-stu-id="af7a4-145">You'll enter this information when you [Configure the virtual table data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span></span>

8. <span data-ttu-id="af7a4-146">Dans le volet de navigation de gauche, sélectionnez **Certificats et secrets**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-146">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="af7a4-147">Dans la section **Clés secrètes client** de la page, sélectionnez **Nouvelle clé secrète client**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-147">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="af7a4-148">Fournissez une description, sélectionnez une durée et sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-148">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="af7a4-149">Enregistrez la valeur du secret à partir de la propriété **Valeur** de la table.</span><span class="sxs-lookup"><span data-stu-id="af7a4-149">Record the secret's value from the **Value** property of the table.</span></span> <span data-ttu-id="af7a4-150">Vous devez saisir ces informations lorsque vous [Configurez la source de données de table virtuelle](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span><span class="sxs-lookup"><span data-stu-id="af7a4-150">You'll enter this information when you [Configure the virtual table data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="af7a4-151">Assurez-vous de prendre note de la valeur du secret à ce stade.</span><span class="sxs-lookup"><span data-stu-id="af7a4-151">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="af7a4-152">Le secret n’est plus jamais affiché une fois que vous avez quitté cette page.</span><span class="sxs-lookup"><span data-stu-id="af7a4-152">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-table-app"></a><span data-ttu-id="af7a4-153">Installer l’application Tables virtuelles Dynamics 365 HR</span><span class="sxs-lookup"><span data-stu-id="af7a4-153">Install the Dynamics 365 HR Virtual Table app</span></span>

<span data-ttu-id="af7a4-154">Installez l’application Tables virtuelles Dynamics 365 HR dans votre environnement Power Apps pour déployer le package de solution de table virtuelle dans Dataverse.</span><span class="sxs-lookup"><span data-stu-id="af7a4-154">Install the Dynamics 365 HR Virtual Table app in your Power Apps environment to deploy the virtual table solution package to Dataverse.</span></span>

1. <span data-ttu-id="af7a4-155">Dans Human Resources, ouvrez la page **Intégration Microsoft Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-155">In Human Resources, open the **Microsoft Dataverse integration** page.</span></span>

2. <span data-ttu-id="af7a4-156">Sélectionnez l’onglet **Tables virtuelles**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-156">Select the **Virtual tables** tab.</span></span>

3. <span data-ttu-id="af7a4-157">Sélectionnez **Installer l'application de table virtuelle**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-157">Select **Install virtual table app**.</span></span>

### <a name="configure-the-virtual-table-data-source"></a><span data-ttu-id="af7a4-158">Configurer la source de données de table virtuelle</span><span class="sxs-lookup"><span data-stu-id="af7a4-158">Configure the virtual table data source</span></span>

<span data-ttu-id="af7a4-159">L’étape suivante consiste à configurer la source de données de table virtuelle dans l’environnement Power Apps.</span><span class="sxs-lookup"><span data-stu-id="af7a4-159">The next step is to configure the virtual table data source in the Power Apps environment.</span></span>

1. <span data-ttu-id="af7a4-160">Ouvrez le [Centre d’administration Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="af7a4-160">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="af7a4-161">Dans la liste **Environnements**, sélectionnez l’environnement Power Apps associé à votre instance Human Resources.</span><span class="sxs-lookup"><span data-stu-id="af7a4-161">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="af7a4-162">Sélectionnez l’**URL d’environnement** dans la section **Détails** de la page.</span><span class="sxs-lookup"><span data-stu-id="af7a4-162">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="af7a4-163">Dans **Hub état solution**, sélectionnez l’icône **Recherche avancée** en haut à droite de la page de l’application.</span><span class="sxs-lookup"><span data-stu-id="af7a4-163">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="af7a4-164">Sur la page **Recherche avancée**, dans la liste déroulante **Rechercher**, sélectionnez Configurations de source de données virtuelle **Finance and Operations**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-164">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="af7a4-165">L'installation de l'application de table virtuelle à partir de l'étape de configuration précédente peut prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="af7a4-165">The installation of the virtual table app from the previous setup step can take a few minutes.</span></span> <span data-ttu-id="af7a4-166">Si **Configurations de source de données virtuelle Finance and Operations** n'est pas disponible dans la liste, attendez une minute et actualisez la liste.</span><span class="sxs-lookup"><span data-stu-id="af7a4-166">If **Finance and Operations Virtual Data Source Configurations** isn't available in the list, wait for a minute and refresh the list.</span></span>

6. <span data-ttu-id="af7a4-167">Sélectionnez **Résultats**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-167">Select **Results**.</span></span>

7. <span data-ttu-id="af7a4-168">Sélectionnez l’enregistrement **Source de données Microsoft HR**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-168">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="af7a4-169">Entrez les informations requises pour la configuration de la source de données :</span><span class="sxs-lookup"><span data-stu-id="af7a4-169">Enter the required information for the data source configuration:</span></span>

   - <span data-ttu-id="af7a4-170">**URL cible** : URL de votre espace de noms Human Resources.</span><span class="sxs-lookup"><span data-stu-id="af7a4-170">**Target URL**: The URL of your Human Resources namespace.</span></span> <span data-ttu-id="af7a4-171">Le format de l’URL cible est :</span><span class="sxs-lookup"><span data-stu-id="af7a4-171">The format of the target URL is:</span></span>
     
     <span data-ttu-id="af7a4-172">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span><span class="sxs-lookup"><span data-stu-id="af7a4-172">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span></span>

     <span data-ttu-id="af7a4-173">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="af7a4-173">For example:</span></span>
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     ><span data-ttu-id="af7a4-174">Assurez-vous d’inclure le caractère "**/**" à la fin de l’URL pour éviter de recevoir une erreur.</span><span class="sxs-lookup"><span data-stu-id="af7a4-174">Be sure to include the "**/**" character at the end of the URL to avoid receiving an error.</span></span>

   - <span data-ttu-id="af7a4-175">**ID du locataire** : ID du locataire Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="af7a4-175">**Tenant ID**: The Azure Active Directory (Azure AD) tenant ID.</span></span>

   - <span data-ttu-id="af7a4-176">**ID d’application AAD** : ID d’application (client) créé pour l’application enregistrée dans le portail Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="af7a4-176">**AAD Application ID**: The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="af7a4-177">Vous avez reçu ces informations plus tôt au cours de l’étape [Enregistrer l’application dans Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="af7a4-177">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   - <span data-ttu-id="af7a4-178">**Secret d’application AAD** : clé secrète client créée pour l’application enregistrée dans le portail Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="af7a4-178">**AAD Application Secret**: The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="af7a4-179">Vous avez reçu ces informations plus tôt au cours de l’étape [Enregistrer l’application dans Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="af7a4-179">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   ![Source de données Microsoft HR](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. <span data-ttu-id="af7a4-181">Sélectionnez **Enregistrer et Fermer**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-181">Select **Save & Close**.</span></span>

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="af7a4-182">Accorder des autorisations d’application dans Human Resources</span><span class="sxs-lookup"><span data-stu-id="af7a4-182">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="af7a4-183">Accordez des autorisations pour les deux applications Azure AD dans Human Resources :</span><span class="sxs-lookup"><span data-stu-id="af7a4-183">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="af7a4-184">L’application créée pour votre locataire dans le portail Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="af7a4-184">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="af7a4-185">L’application Tables virtuelles Dynamics 365 HR installée dans l’environnement Power Apps</span><span class="sxs-lookup"><span data-stu-id="af7a4-185">The Dynamics 365 HR Virtual Table app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="af7a4-186">Dans Human Resources, ouvrez la page **Azure Active Directory applications**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-186">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="af7a4-187">Sélectionnez **Nouveau** pour créer un nouvel enregistrement d’application :</span><span class="sxs-lookup"><span data-stu-id="af7a4-187">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="af7a4-188">Dans le champ **ID client**, entrez l’ID client de l’application que vous avez enregistrée dans le portail Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="af7a4-188">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="af7a4-189">Dans le champ **Nom**, entrez le nom de l’application que vous avez enregistrée dans le portail Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="af7a4-189">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="af7a4-190">Dans le champ **ID utilisateur**, sélectionnez l’ID utilisateur d’un utilisateur avec des autorisations d’administrateur dans Human Resources et l’environnement Power Apps.</span><span class="sxs-lookup"><span data-stu-id="af7a4-190">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="af7a4-191">Sélectionnez **Nouveau** pour créer un second enregistrement d’application :</span><span class="sxs-lookup"><span data-stu-id="af7a4-191">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="af7a4-192">**ID client** : f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="af7a4-192">**Client Id**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="af7a4-193">**Nom** : Tables virtuelles Dynamics 365 HR</span><span class="sxs-lookup"><span data-stu-id="af7a4-193">**Name**: Dynamics 365 HR Virtual Table</span></span>
    - <span data-ttu-id="af7a4-194">Dans le champ **ID utilisateur**, sélectionnez l’ID utilisateur d’un utilisateur avec des autorisations d’administrateur dans Human Resources et l’environnement Power Apps.</span><span class="sxs-lookup"><span data-stu-id="af7a4-194">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-tables"></a><span data-ttu-id="af7a4-195">Générer des tables virtuelles</span><span class="sxs-lookup"><span data-stu-id="af7a4-195">Generate virtual tables</span></span>

<span data-ttu-id="af7a4-196">Une fois la configuration terminée, vous pouvez sélectionner les tables virtuelles que vous souhaitez générer et activer dans votre instance Dataverse.</span><span class="sxs-lookup"><span data-stu-id="af7a4-196">When setup completes, you can select the virtual tables you want to generate and enable in your Dataverse instance.</span></span>

1. <span data-ttu-id="af7a4-197">Dans Human Resources, ouvrez la page **Intégration Microsoft Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-197">In Human Resources, open the **Microsoft Dataverse integration** page.</span></span>

2. <span data-ttu-id="af7a4-198">Sélectionnez l’onglet **Tables virtuelles**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-198">Select the **Virtual tables** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="af7a4-199">La bascule **Activer les tables virtuelles** sera définie sur **Oui** automatiquement lorsque toute la configuration requise est terminée.</span><span class="sxs-lookup"><span data-stu-id="af7a4-199">The **Enable virtual tables** toggle will be set to **Yes** automatically when all required setup has been completed.</span></span> <span data-ttu-id="af7a4-200">Si la bascule est définie sur **Non**, passez en revue les étapes des sections précédentes de ce document pour vous assurer que toutes les configurations préalables sont terminées.</span><span class="sxs-lookup"><span data-stu-id="af7a4-200">If the toggle is set to **No**, review the steps in previous sections of this document to ensure all prerequisite setup is completed.</span></span>

3. <span data-ttu-id="af7a4-201">Sélectionnez la table ou les tables que vous souhaitez générer dans Dataverse.</span><span class="sxs-lookup"><span data-stu-id="af7a4-201">Select the table or tables you want to generate in Dataverse.</span></span>

4. <span data-ttu-id="af7a4-202">Sélectionnez **Générer/actualiser**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-202">Select **Generate/refresh**.</span></span>

![Intégration de Dataverse](./media/hr-admin-integration-dataverse-integration.png)

## <a name="check-table-generation-status"></a><span data-ttu-id="af7a4-204">Vérifier le statut de la génération de la table</span><span class="sxs-lookup"><span data-stu-id="af7a4-204">Check table generation status</span></span>

<span data-ttu-id="af7a4-205">Les tables virtuelles sont générées dans Dataverse via un processus d’arrière-plan asynchrone.</span><span class="sxs-lookup"><span data-stu-id="af7a4-205">Virtual tables are generated in Dataverse through an asynchronous background process.</span></span> <span data-ttu-id="af7a4-206">Les mises à jour sur le processus s’affichent dans le centre d’actions.</span><span class="sxs-lookup"><span data-stu-id="af7a4-206">Updates on the process display in the action center.</span></span> <span data-ttu-id="af7a4-207">Les détails du processus, y compris les journaux d’erreurs, apparaissent dans la page **Automatisations de processus**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-207">Details on the process, including error logs, appear in the **Process automations** page.</span></span>

1. <span data-ttu-id="af7a4-208">Dans Human Resources, ouvrez la page de liste **Automatisations de processus**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-208">In Human Resources, open the **Process automations** page.</span></span>

2. <span data-ttu-id="af7a4-209">Sélectionnez l’onglet **Processus en arrière-plan**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-209">Select the **Background processes** tab.</span></span>

3. <span data-ttu-id="af7a4-210">Sélectionnez **Processus d’arrière-plan d’opération asynchrone d’interrogation de table virtuelle**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-210">Select **Virtual table poll async operation background process**.</span></span>

4. <span data-ttu-id="af7a4-211">Sélectionnez **Afficher les résultats les plus récents**.</span><span class="sxs-lookup"><span data-stu-id="af7a4-211">Select **View most recent results**.</span></span>

<span data-ttu-id="af7a4-212">Le volet coulissant affiche les résultats d’exécution les plus récents du processus.</span><span class="sxs-lookup"><span data-stu-id="af7a4-212">The slideout pane displays the most recent execution results for the process.</span></span> <span data-ttu-id="af7a4-213">Vous pouvez afficher le journal du processus, y compris les erreurs renvoyées par Dataverse.</span><span class="sxs-lookup"><span data-stu-id="af7a4-213">You can view the log for the process, including any errors returned from Dataverse.</span></span>

## <a name="see-also"></a><span data-ttu-id="af7a4-214">Voir également :</span><span class="sxs-lookup"><span data-stu-id="af7a4-214">See also</span></span>

[<span data-ttu-id="af7a4-215">Qu’est-ce que Dataverse ?</span><span class="sxs-lookup"><span data-stu-id="af7a4-215">What is Dataverse?</span></span>](/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="af7a4-216">Tables dans Dataverse</span><span class="sxs-lookup"><span data-stu-id="af7a4-216">Tables in Dataverse</span></span>](/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="af7a4-217">Vue d’ensemble des relations de table</span><span class="sxs-lookup"><span data-stu-id="af7a4-217">Table relationships overview</span></span>](/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="af7a4-218">Créer et modifier des tables virtuelles qui contiennent des données provenant d’une source de données externe</span><span class="sxs-lookup"><span data-stu-id="af7a4-218">Create and edit virtual tables that contain data from an external data source</span></span>](/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="af7a4-219">Que sont les portails Power Apps ?</span><span class="sxs-lookup"><span data-stu-id="af7a4-219">What is Power Apps portals?</span></span>](/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="af7a4-220">Présentation de la création d’applications dans Power Apps</span><span class="sxs-lookup"><span data-stu-id="af7a4-220">Overview of creating apps in Power Apps</span></span>](/powerapps/maker/)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
