---
title: Effectuer une mise à niveau vers le modèle de partie et de carnet d’adresses global
description: Cette rubrique décrit comment mettre à niveau les données à double écriture en modèle de carnet d'adresses global et de partie.
author: RamaKrishnamoorthy
ms.date: 03/31/2021
ms.topic: article
ms.service: dynamics-ax-applications
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: 76e64d483e833782733277a64d8dc37cbeba6130
ms.sourcegitcommit: 011468a6cffea8641bebc2922e0676d9f44b36fc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2021
ms.locfileid: "5857368"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a><span data-ttu-id="5ea5b-103">Effectuer une mise à niveau vers le modèle de partie et de carnet d’adresses global</span><span class="sxs-lookup"><span data-stu-id="5ea5b-103">Upgrade to the party and global address book model</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="5ea5b-104">Le [Modèle Azure Data Factory](https://aka.ms/dual-write-gab-adf) vous aide à mettre à niveau les données des tables **Compte**, **Contact** et **Fournisseur** en double écriture vers le modèle de carnet d'adresses global et de partie.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-104">The [Azure Data Factory template](https://aka.ms/dual-write-gab-adf) helps you upgrade existing **Account**, **Contact**, and **Vendor** table data in dual-write to the party and global address book model.</span></span> <span data-ttu-id="5ea5b-105">Le modèle rapproche les données des applications Finance and Operations et des applications d'engagement client.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-105">The template reconciles the data from both Finance and Operations apps and customer engagement applications.</span></span> <span data-ttu-id="5ea5b-106">À la fin du processus, les champs **Partie** et **Contact** des enregistrements **Partie** seront créés et associés aux enregistrements **Compte**, **Contact** et **Fournisseur** dans les applications d'engagement client.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-106">At the end of the process, **Party** and **Contact** fields for **Party** records will be created and associated with **Account**, **Contact**, and **Vendor** records in customer engagement applications.</span></span> <span data-ttu-id="5ea5b-107">Un fichier .csv (`FONewParty.csv`) est généré pour créer de nouveaux enregistrements **Partie** à l'intérieur de l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-107">A .csv file (`FONewParty.csv`) is generated to create new **Party** records inside the Finance and Operations app.</span></span> <span data-ttu-id="5ea5b-108">Cette rubrique fournit les instructions pour utiliser le modèle Data Factory et mettre à niveau vos données.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-108">This topic provides the instructions to use the Data Factory template and upgrade your data.</span></span>

<span data-ttu-id="5ea5b-109">Si vous n'avez aucune personnalisation, vous pouvez utiliser le modèle tel quel.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-109">If you don’t have any customizations, you can use the template as-is.</span></span> <span data-ttu-id="5ea5b-110">Si vous avez des personnalisations pour **Compte**, **Contact** et **Fournisseur**, vous devez modifier le modèle en suivant les instructions ci-après.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-110">If you have customizations for **Account**, **Contact**, and **Vendor** then you must modify the template using the following instructions.</span></span>

> [!Note]
> <span data-ttu-id="5ea5b-111">Le modèle permet de mettre à niveau uniquement les données de **Partie**.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-111">The template helps to upgrade only the **Party** data.</span></span> <span data-ttu-id="5ea5b-112">Dans une prochaine version, les adresses postales et électroniques seront incluses.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-112">In a future release, postal and electronic addresses will be included.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5ea5b-113">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="5ea5b-113">Prerequisites</span></span>

<span data-ttu-id="5ea5b-114">Ces conditions préalables sont obligatoires :</span><span class="sxs-lookup"><span data-stu-id="5ea5b-114">These prerequisites are required:</span></span>

+ [<span data-ttu-id="5ea5b-115">Abonnement Azure</span><span class="sxs-lookup"><span data-stu-id="5ea5b-115">Azure subscription</span></span>](https://portal.azure.com/)
+ [<span data-ttu-id="5ea5b-116">Accès au modèle</span><span class="sxs-lookup"><span data-stu-id="5ea5b-116">Access to the template</span></span>](https://aka.ms/dual-write-gab-adf)
+ <span data-ttu-id="5ea5b-117">Vous êtes déjà client de la double écriture.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-117">You are an existing dual-write customer.</span></span>

## <a name="prepare-for-the-upgrade"></a><span data-ttu-id="5ea5b-118">Préparation pour la mise à niveau</span><span class="sxs-lookup"><span data-stu-id="5ea5b-118">Prepare for the upgrade</span></span>

+ <span data-ttu-id="5ea5b-119">**Entièrement synchronisé** : les deux environnements sont entièrement synchronisés pour **Compte (client)**, **Contact** et **Fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-119">**Fully synched**: Both environments are fully synched state for **Account (Customer)**, **Contact**, and **Vendor**.</span></span>
+ <span data-ttu-id="5ea5b-120">**Clés d'intégration** : les tables **Compte (client)**, **Contacter** et **Fournisseur** dans les applications d'engagement client utilisent les clés d'intégration livrées prêtes à l'emploi.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-120">**Integration keys**: **Account (Customer)**, **Contact**, and **Vendor** tables in customer engagement apps are using the integration keys that shipped out-of-the-box.</span></span> <span data-ttu-id="5ea5b-121">Si vous avez personnalisé les clés d'intégration, vous devez personnaliser le modèle.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-121">If you customized the integration keys, you must customize the template.</span></span>
+ <span data-ttu-id="5ea5b-122">**Numéro de partie** : tous les enregistrements **Compte (client)**, **Contact** et **Fournisseur** qui seront mis à niveau ont un numéro de **Partie**.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-122">**Party number**: All **Account (Customer)**, **Contact**, and **Vendor** records that will be upgraded have a **Party** number.</span></span> <span data-ttu-id="5ea5b-123">Les enregistrements sans numéro de **Partie** seront ignorés.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-123">Records without a **Party** number will be ignored.</span></span> <span data-ttu-id="5ea5b-124">Si vous souhaitez mettre à niveau ces enregistrements, ajoutez-leur un numéro de **Partie** avant de commencer le processus de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-124">If you want to upgrade those records, add a **Party** number to them before you start the upgrade process.</span></span>
+ <span data-ttu-id="5ea5b-125">**Panne du système** : pendant le processus de mise à niveau, vous devrez mettre hors connexion les environnements Finance and Operations et d'engagement client.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-125">**System outage**: During the upgrade process, you will have to take both the Finance and Operations and customer engagement environments offline.</span></span>
+ <span data-ttu-id="5ea5b-126">**Instantané** : prenez des instantanés des applications Finance and Operations et d'engagement client.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-126">**Snapshot**: Take snapshots of both the Finance and Operations and customer engagement apps.</span></span> <span data-ttu-id="5ea5b-127">Utilisez les instantanés pour restaurer l'état précédent si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-127">Use the snapshots to restore the previous state if you need to.</span></span>

## <a name="deployment"></a><span data-ttu-id="5ea5b-128">Déploiement</span><span class="sxs-lookup"><span data-stu-id="5ea5b-128">Deployment</span></span>

1. <span data-ttu-id="5ea5b-129">Téléchargez le modèle depuis [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).</span><span class="sxs-lookup"><span data-stu-id="5ea5b-129">Download the template from [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).</span></span>

2. <span data-ttu-id="5ea5b-130">Connectez-vous à [Microsoft Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="5ea5b-130">Sign in to [Microsoft Azure](https://portal.azure.com/).</span></span>

3. <span data-ttu-id="5ea5b-131">Créez un [groupe de ressources](https://docs.microsoft.com/azure/azure-resource-manager/management/manage-resource-groups-portal).</span><span class="sxs-lookup"><span data-stu-id="5ea5b-131">Create a [resource group](https://docs.microsoft.com/azure/azure-resource-manager/management/manage-resource-groups-portal).</span></span>

4. <span data-ttu-id="5ea5b-132">Créez un [compte de stockage](https://docs.microsoft.com/azure/storage/common/storage-account-create?tabs=azure-portal) dans le groupe de ressources que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-132">Create a [storage account](https://docs.microsoft.com/azure/storage/common/storage-account-create?tabs=azure-portal) in the resource group that you created.</span></span>

5. <span data-ttu-id="5ea5b-133">Créez une [fabrique de données](https://docs.microsoft.com/azure/data-factory/quickstart-create-data-factory-portal) dans le groupe de ressources que vous avez créé ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-133">Create a [data factory](https://docs.microsoft.com/azure/data-factory/quickstart-create-data-factory-portal) in above resource group that you created.</span></span>

6. <span data-ttu-id="5ea5b-134">Ouvrez la fabrique de données et sélectionnez la vignette **Créer et surveiller**.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-134">Open the data factory and select the **Author & Monitor** tile.</span></span>

7. <span data-ttu-id="5ea5b-135">Dans l'onglet **Gérer**, sélectionnez **Modèle ARM**.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-135">On the **Manage** tab, select **ARM template**.</span></span>

8. <span data-ttu-id="5ea5b-136">Sélectionnez **Importer un modèle ARM** pour importer le modèle **Partie**.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-136">Select the **Import ARM template** to import the **Party** template.</span></span>

9. <span data-ttu-id="5ea5b-137">Importez le modèle dans la fabrique de données.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-137">Import the template into the data factory.</span></span> <span data-ttu-id="5ea5b-138">Entrez les valeurs suivantes pour les **Détails du projet** et les **Détails de l'instance**.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-138">Enter the following values for **Project details** and **Instance details**.</span></span>

    <span data-ttu-id="5ea5b-139">Champ</span><span class="sxs-lookup"><span data-stu-id="5ea5b-139">Field</span></span> | <span data-ttu-id="5ea5b-140">Valeur</span><span class="sxs-lookup"><span data-stu-id="5ea5b-140">Value</span></span>
    ---|---
    <span data-ttu-id="5ea5b-141">Abonnement</span><span class="sxs-lookup"><span data-stu-id="5ea5b-141">Subscription</span></span> | <span data-ttu-id="5ea5b-142">Abonnement Azure</span><span class="sxs-lookup"><span data-stu-id="5ea5b-142">Azure subscription</span></span>
    <span data-ttu-id="5ea5b-143">Groupe de ressources</span><span class="sxs-lookup"><span data-stu-id="5ea5b-143">Resource group</span></span> | <span data-ttu-id="5ea5b-144">Indiquez la même ressource sous laquelle le compte de stockage est créé.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-144">Provide same resource under which storage account is created.</span></span>
    <span data-ttu-id="5ea5b-145">Région</span><span class="sxs-lookup"><span data-stu-id="5ea5b-145">Region</span></span> | <span data-ttu-id="5ea5b-146">Spécifiez la région.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-146">Specify region.</span></span>
    <span data-ttu-id="5ea5b-147">Nom de la fabrique</span><span class="sxs-lookup"><span data-stu-id="5ea5b-147">Factory Name</span></span> | <span data-ttu-id="5ea5b-148">Spécifiez le nom de la fabrique.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-148">Specify factory name.</span></span>
    <span data-ttu-id="5ea5b-149">FO Linked Service_service Principal Key</span><span class="sxs-lookup"><span data-stu-id="5ea5b-149">FO Linked Service_service Principal Key</span></span> | <span data-ttu-id="5ea5b-150">Spécifiez la clé de l'application.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-150">Specify the application's key.</span></span>
    <span data-ttu-id="5ea5b-151">Azure Blob Storage_connection String</span><span class="sxs-lookup"><span data-stu-id="5ea5b-151">Azure Blob Storage_connection String</span></span> | <span data-ttu-id="5ea5b-152">Chaîne de connexion au Stockage Blob Azure</span><span class="sxs-lookup"><span data-stu-id="5ea5b-152">Azure Blob storage connection string.</span></span>
    <span data-ttu-id="5ea5b-153">Dynamics Crm Linked Service_password</span><span class="sxs-lookup"><span data-stu-id="5ea5b-153">Dynamics Crm Linked Service_password</span></span> | <span data-ttu-id="5ea5b-154">Le mot de passe du compte d'utilisateur que vous avez spécifié comme nom d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-154">The password for the user account you specified as the username.</span></span>
    <span data-ttu-id="5ea5b-155">FO Linked Service_properties_type Properties_url</span><span class="sxs-lookup"><span data-stu-id="5ea5b-155">FO Linked Service_properties_type Properties_url</span></span>  | `https://sampledynamics.sandbox-operationsdynamics.com/data`
    <span data-ttu-id="5ea5b-156">FO Linked Service_properties_type Properties_tenant</span><span class="sxs-lookup"><span data-stu-id="5ea5b-156">FO Linked Service_properties_type Properties_tenant</span></span> | <span data-ttu-id="5ea5b-157">Spécifiez les informations de locataire (nom de domaine ou ID de locataire) sous lesquelles réside votre application.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-157">Specify the tenant information (domain name or tenant ID) under which your application resides.</span></span>
    <span data-ttu-id="5ea5b-158">FO Linked Service_properties_type Properties_aad Resource Id</span><span class="sxs-lookup"><span data-stu-id="5ea5b-158">FO Linked Service_properties_type Properties_aad Resource Id</span></span> | `https://sampledynamics.sandboxoperationsdynamics.com`
    <span data-ttu-id="5ea5b-159">FO Linked Service_properties_type Properties_service Principal Id</span><span class="sxs-lookup"><span data-stu-id="5ea5b-159">FO Linked Service_properties_type Properties_service Principal Id</span></span> | <span data-ttu-id="5ea5b-160">Spécifiez l'ID du client de l'application.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-160">Specify the application's client ID.</span></span>
    <span data-ttu-id="5ea5b-161">Dynamics Crm Linked Service_properties_type Properties_username</span><span class="sxs-lookup"><span data-stu-id="5ea5b-161">Dynamics Crm Linked Service_properties_type Properties_username</span></span> | <span data-ttu-id="5ea5b-162">Le nom d'utilisateur pour se connecter à Dynamics.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-162">The username to connect to Dynamics.</span></span>

    <span data-ttu-id="5ea5b-163">Pour plus d'informations, consultez [Promouvoir manuellement un modèle Resource Manager pour chaque environnement](https://docs.microsoft.com/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment), [Propriétés du service lié](https://docs.microsoft.com/azure/data-factory/connector-dynamics-ax#linked-service-properties) et [Copier des données à l'aide d'Azure Data Factory](https://docs.microsoft.com/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)</span><span class="sxs-lookup"><span data-stu-id="5ea5b-163">For more information, see [Manually promote a Resource Manager template for each environment](https://docs.microsoft.com/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment), [Linked service properties](https://docs.microsoft.com/azure/data-factory/connector-dynamics-ax#linked-service-properties), and [Copy data using Azure Data Factory](https://docs.microsoft.com/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)</span></span>

10. <span data-ttu-id="5ea5b-164">Après le déploiement, vérifiez les jeux de données, le flux de données et le service lié de la fabrique de données.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-164">After deployment, validate the datasets, data flow, and linked service of the data factory.</span></span>

   ![Jeux de données, flux de données et service lié](media/data-factory-validate.png)

11. <span data-ttu-id="5ea5b-166">Accédez à **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-166">Navigate to **Manage**.</span></span> <span data-ttu-id="5ea5b-167">En dessous de **Connexions**, sélectionnez **Service lié**.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-167">Under **Connections**, select **Linked Service**.</span></span> <span data-ttu-id="5ea5b-168">Sélectionnez **DynamicsCrmLinkedService**.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-168">Select **DynamicsCrmLinkedService**.</span></span> <span data-ttu-id="5ea5b-169">Dans le formulaire **Modifier le service lié (Dynamics CRM)**, entrez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="5ea5b-169">In the **Edit linked service (Dynamics CRM)** form, enter the following values:</span></span>

    <span data-ttu-id="5ea5b-170">Champ</span><span class="sxs-lookup"><span data-stu-id="5ea5b-170">Field</span></span> | <span data-ttu-id="5ea5b-171">Valeur</span><span class="sxs-lookup"><span data-stu-id="5ea5b-171">Value</span></span>
    ---|---
    <span data-ttu-id="5ea5b-172">Nom</span><span class="sxs-lookup"><span data-stu-id="5ea5b-172">Name</span></span> | <span data-ttu-id="5ea5b-173">DynamicsCrmLinkedService</span><span class="sxs-lookup"><span data-stu-id="5ea5b-173">DynamicsCrmLinkedService</span></span>
    <span data-ttu-id="5ea5b-174">Description</span><span class="sxs-lookup"><span data-stu-id="5ea5b-174">Description</span></span> | <span data-ttu-id="5ea5b-175">Services liés pour se connecter à l'instance CRM pour récupérer les données des entités</span><span class="sxs-lookup"><span data-stu-id="5ea5b-175">Linked services to connect with CRM instance to fetch entities data</span></span>
    <span data-ttu-id="5ea5b-176">Connexion via le runtime d'intégration</span><span class="sxs-lookup"><span data-stu-id="5ea5b-176">Connect via integration runtime</span></span> | <span data-ttu-id="5ea5b-177">AutoResolvelntegrationRuntime</span><span class="sxs-lookup"><span data-stu-id="5ea5b-177">AutoResolvelntegrationRuntime</span></span>
    <span data-ttu-id="5ea5b-178">Type de déploiement</span><span class="sxs-lookup"><span data-stu-id="5ea5b-178">Deployment type</span></span> | <span data-ttu-id="5ea5b-179">En ligne</span><span class="sxs-lookup"><span data-stu-id="5ea5b-179">Online</span></span>
    <span data-ttu-id="5ea5b-180">URI du service</span><span class="sxs-lookup"><span data-stu-id="5ea5b-180">Service Uri</span></span> | `https://<organization-name>.crm[x].dynamics.com`
    <span data-ttu-id="5ea5b-181">Type d'authentification</span><span class="sxs-lookup"><span data-stu-id="5ea5b-181">Authentication type</span></span> | <span data-ttu-id="5ea5b-182">Office365</span><span class="sxs-lookup"><span data-stu-id="5ea5b-182">Office365</span></span>
    <span data-ttu-id="5ea5b-183">Nom d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="5ea5b-183">User name</span></span> |
    <span data-ttu-id="5ea5b-184">Mot de passe ou Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="5ea5b-184">Password or Azure Key Vault</span></span> | <span data-ttu-id="5ea5b-185">Mot de passe</span><span class="sxs-lookup"><span data-stu-id="5ea5b-185">Password</span></span>
    <span data-ttu-id="5ea5b-186">Mot de passe</span><span class="sxs-lookup"><span data-stu-id="5ea5b-186">Password</span></span> |

## <a name="run-the-template"></a><span data-ttu-id="5ea5b-187">Exécution du modèle</span><span class="sxs-lookup"><span data-stu-id="5ea5b-187">Run the template</span></span>

1. <span data-ttu-id="5ea5b-188">Arrêtez la double écriture de **Compte**, **Contact** et **Fournisseur** à l'aide de l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-188">Stop the following **Account**, **Contact**, and **Vendor** dual-write using the Finance and Operations app.</span></span>

    + <span data-ttu-id="5ea5b-189">Clients V3 (accounts)</span><span class="sxs-lookup"><span data-stu-id="5ea5b-189">Customers V3(accounts)</span></span>
    + <span data-ttu-id="5ea5b-190">Clients V3 (contacts)</span><span class="sxs-lookup"><span data-stu-id="5ea5b-190">Customers V3(contacts)</span></span>
    + <span data-ttu-id="5ea5b-191">CDS Contacts V2 (contacts)</span><span class="sxs-lookup"><span data-stu-id="5ea5b-191">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="5ea5b-192">CDS Contacts V2 (contacts)</span><span class="sxs-lookup"><span data-stu-id="5ea5b-192">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="5ea5b-193">Fournisseurs V2 (msdyn_vendor)</span><span class="sxs-lookup"><span data-stu-id="5ea5b-193">Vendor V2 (msdyn_vendor)</span></span>

2. <span data-ttu-id="5ea5b-194">Assurez-vous que les cartes sont supprimées de la table `msdy_dualwriteruntimeconfig` dans Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-194">Make sure the maps are removed from the `msdy_dualwriteruntimeconfig` table in Dataverse.</span></span>

3. <span data-ttu-id="5ea5b-195">Installez [Solutions de double écriture pour les Carnets d'adresses global et de partie](https://aka.ms/dual-write-gab) à partir de AppSource.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-195">Install [Dual-write Party and Global Address Book Solutions](https://aka.ms/dual-write-gab) from AppSource.</span></span>

4. <span data-ttu-id="5ea5b-196">Dans l'application Finance and Operations, si les tables suivantes contiennent des données, exécutez la **Synchronisation initiale** pour elles.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-196">In the Finance and Operations app, if the following tables contain data, then run **Initial Sync** for them.</span></span>

    + <span data-ttu-id="5ea5b-197">Salutations</span><span class="sxs-lookup"><span data-stu-id="5ea5b-197">Salutations</span></span>
    + <span data-ttu-id="5ea5b-198">Type de caractère personnel</span><span class="sxs-lookup"><span data-stu-id="5ea5b-198">Personal character types</span></span>
    + <span data-ttu-id="5ea5b-199">Politesses</span><span class="sxs-lookup"><span data-stu-id="5ea5b-199">Complimentary closing</span></span>
    + <span data-ttu-id="5ea5b-200">Titres des contacts</span><span class="sxs-lookup"><span data-stu-id="5ea5b-200">Contact person titles</span></span>
    + <span data-ttu-id="5ea5b-201">Rôles de prise de décision</span><span class="sxs-lookup"><span data-stu-id="5ea5b-201">Decision making roles</span></span>
    + <span data-ttu-id="5ea5b-202">Niveaux de fidélité</span><span class="sxs-lookup"><span data-stu-id="5ea5b-202">Loyalty levels</span></span>

5. <span data-ttu-id="5ea5b-203">Dans l'application d'engagement client, désactivez les étapes suivantes du plug-in.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-203">In the customer engagement app, disable the following plugin steps.</span></span>

    + <span data-ttu-id="5ea5b-204">Mise à jour du compte</span><span class="sxs-lookup"><span data-stu-id="5ea5b-204">Account Update</span></span>
         + <span data-ttu-id="5ea5b-205">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity : Mise à jour du compte</span><span class="sxs-lookup"><span data-stu-id="5ea5b-205">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="5ea5b-206">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes : Mise à jour du compte</span><span class="sxs-lookup"><span data-stu-id="5ea5b-206">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="5ea5b-207">Mise à jour du contact</span><span class="sxs-lookup"><span data-stu-id="5ea5b-207">Contact Update</span></span>
         + <span data-ttu-id="5ea5b-208">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity : Mise à jour du contact</span><span class="sxs-lookup"><span data-stu-id="5ea5b-208">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="5ea5b-209">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact : Mise à jour du contact</span><span class="sxs-lookup"><span data-stu-id="5ea5b-209">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="5ea5b-210">Mise à jour de msdyn_party</span><span class="sxs-lookup"><span data-stu-id="5ea5b-210">msdyn_party Update</span></span>
         + <span data-ttu-id="5ea5b-211">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity : Mise à jour de msdyn_party</span><span class="sxs-lookup"><span data-stu-id="5ea5b-211">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="5ea5b-212">Mise à jour de msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="5ea5b-212">msdyn_vendor Update</span></span>
         + <span data-ttu-id="5ea5b-213">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity : Mise à jour de msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="5ea5b-213">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

6. <span data-ttu-id="5ea5b-214">Dans l'application d'engagement client, désactivez les workflows suivants :</span><span class="sxs-lookup"><span data-stu-id="5ea5b-214">In the customer engagement app, disable the following workflows:</span></span>

    + <span data-ttu-id="5ea5b-215">Créer des fournisseurs dans la table Comptes</span><span class="sxs-lookup"><span data-stu-id="5ea5b-215">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="5ea5b-216">Créer des fournisseurs dans la table Comptes</span><span class="sxs-lookup"><span data-stu-id="5ea5b-216">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="5ea5b-217">Créer des fournisseurs de type Personne dans la table Contacts</span><span class="sxs-lookup"><span data-stu-id="5ea5b-217">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="5ea5b-218">Créer des fournisseurs de type Personne dans la table Fournisseurs</span><span class="sxs-lookup"><span data-stu-id="5ea5b-218">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="5ea5b-219">Mettre à jour des fournisseurs dans la table Comptes</span><span class="sxs-lookup"><span data-stu-id="5ea5b-219">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="5ea5b-220">Mettre à jour des fournisseurs dans la table Fournisseurs</span><span class="sxs-lookup"><span data-stu-id="5ea5b-220">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="5ea5b-221">Mettre à jour des fournisseurs de type Personne dans la table Contacts</span><span class="sxs-lookup"><span data-stu-id="5ea5b-221">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="5ea5b-222">Mettre à jour des fournisseurs de type Personne dans la table Fournisseurs</span><span class="sxs-lookup"><span data-stu-id="5ea5b-222">Update Vendors of type Person in Vendors Table</span></span>

7. <span data-ttu-id="5ea5b-223">Dans la fabrique de données, exécutez le modèle en sélectionnant **Déclencher maintenant**, comme indiqué dans l'image suivante.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-223">In the data factory, run the template by selecting **Trigger now** as shown in the following image.</span></span> <span data-ttu-id="5ea5b-224">Ce processus peut prendre quelques heures, en fonction du volume de données.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-224">This process might take a few hours to complete based on the data volume.</span></span>

    ![Déclencher l'exécution](media/data-factory-trigger.png)

    > [!NOTE]
    > <span data-ttu-id="5ea5b-226">Si vous avez des personnalisations pour **Compte**, **Contact** et **Fournisseur**, vous devez modifier le modèle.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-226">If you have customizations for **Account**, **Contact**, and **Vendor** then you must modify the template.</span></span>

8. <span data-ttu-id="5ea5b-227">Importez les nouveaux enregistrements **Partie** dans l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-227">Import the new **Party** records in the Finance and Operations app.</span></span>

    + <span data-ttu-id="5ea5b-228">Téléchargez le fichier `FONewParty.csv` à partir du stockage blob Azure.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-228">Download the `FONewParty.csv` file from Azure blob storage.</span></span> <span data-ttu-id="5ea5b-229">Le chemin d'accès est `partybootstrapping/output/FONewParty.csv`.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-229">The path is `partybootstrapping/output/FONewParty.csv`.</span></span>
    + <span data-ttu-id="5ea5b-230">Convertissez le fichier `FONewParty.csv` en fichier Excel et importez le fichier Excel dans l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-230">Convert the `FONewParty.csv` file into an Excel file and import the Excel file into the Finance and Operations app.</span></span>  <span data-ttu-id="5ea5b-231">Si l'importation csv fonctionne pour vous, vous pouvez importer le fichier csv directement.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-231">If the csv import works for you, you can import csv file directly.</span></span> <span data-ttu-id="5ea5b-232">L'importation peut prendre quelques heures, selon le volume de données.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-232">The import could take a few hours to run, depending on the data volume.</span></span> <span data-ttu-id="5ea5b-233">Pour plus d’informations, voir [Vue d’ensemble des tâches d’importation et d’exportation de données](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-import-export-job).</span><span class="sxs-lookup"><span data-stu-id="5ea5b-233">For more information, see [Data import and export jobs overview](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-import-export-job).</span></span>

    ![Importer les enregistrements de partie de Dataverse](media/data-factory-import-party.png)

9. <span data-ttu-id="5ea5b-235">Dans les applications d'engagement client, désactivez les étapes suivantes du plug-in :</span><span class="sxs-lookup"><span data-stu-id="5ea5b-235">In the customer engagement apps, enable the following plugin steps:</span></span>

    + <span data-ttu-id="5ea5b-236">Mise à jour du compte</span><span class="sxs-lookup"><span data-stu-id="5ea5b-236">Account Update</span></span>
         + <span data-ttu-id="5ea5b-237">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity : Mise à jour du compte</span><span class="sxs-lookup"><span data-stu-id="5ea5b-237">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="5ea5b-238">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes : Mise à jour du compte</span><span class="sxs-lookup"><span data-stu-id="5ea5b-238">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="5ea5b-239">Mise à jour du contact</span><span class="sxs-lookup"><span data-stu-id="5ea5b-239">Contact Update</span></span>
         + <span data-ttu-id="5ea5b-240">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity : Mise à jour du contact</span><span class="sxs-lookup"><span data-stu-id="5ea5b-240">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="5ea5b-241">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact : Mise à jour du contact</span><span class="sxs-lookup"><span data-stu-id="5ea5b-241">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="5ea5b-242">Mise à jour de msdyn_party</span><span class="sxs-lookup"><span data-stu-id="5ea5b-242">msdyn_party Update</span></span>
         + <span data-ttu-id="5ea5b-243">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity : Mise à jour de msdyn_party</span><span class="sxs-lookup"><span data-stu-id="5ea5b-243">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="5ea5b-244">Mise à jour de msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="5ea5b-244">msdyn_vendor Update</span></span>
         + <span data-ttu-id="5ea5b-245">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity : Mise à jour de msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="5ea5b-245">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

10. <span data-ttu-id="5ea5b-246">Dans les applications d'engagement client, activez les workflows suivants si vous les avez désactivés lors des étapes précédentes :</span><span class="sxs-lookup"><span data-stu-id="5ea5b-246">In the customer engagement apps, activate the following workflows if you deactivated them in previous steps:</span></span>

    + <span data-ttu-id="5ea5b-247">Créer des fournisseurs dans la table Comptes</span><span class="sxs-lookup"><span data-stu-id="5ea5b-247">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="5ea5b-248">Créer des fournisseurs dans la table Comptes</span><span class="sxs-lookup"><span data-stu-id="5ea5b-248">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="5ea5b-249">Créer des fournisseurs de type Personne dans la table Contacts</span><span class="sxs-lookup"><span data-stu-id="5ea5b-249">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="5ea5b-250">Créer des fournisseurs de type Personne dans la table Fournisseurs</span><span class="sxs-lookup"><span data-stu-id="5ea5b-250">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="5ea5b-251">Mettre à jour des fournisseurs dans la table Comptes</span><span class="sxs-lookup"><span data-stu-id="5ea5b-251">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="5ea5b-252">Mettre à jour des fournisseurs dans la table Fournisseurs</span><span class="sxs-lookup"><span data-stu-id="5ea5b-252">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="5ea5b-253">Mettre à jour des fournisseurs de type Personne dans la table Contacts</span><span class="sxs-lookup"><span data-stu-id="5ea5b-253">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="5ea5b-254">Mettre à jour des fournisseurs de type Personne dans la table Fournisseurs</span><span class="sxs-lookup"><span data-stu-id="5ea5b-254">Update Vendors of type Person in Vendors Table</span></span>

11. <span data-ttu-id="5ea5b-255">Exécutez les cartes associées à la **Partie** comme indiqué dans [Carnet d'adresses global et de partie](party-gab.md).</span><span class="sxs-lookup"><span data-stu-id="5ea5b-255">Run the **Party**-related maps as instructed in [Party and global address book](party-gab.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="5ea5b-256">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="5ea5b-256">Troubleshooting</span></span>

1. <span data-ttu-id="5ea5b-257">Dans le processus échoue, réexécutez la fabrique de données à partir de l'activité qui a échoué.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-257">In the process fails, rerun the data factory starting from the failed activity.</span></span>
2. <span data-ttu-id="5ea5b-258">Certains fichiers sont générés par la fabrique de données ; vous pouvez les utiliser à des fins de validation des données.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-258">Some files are generated by the data factory that you can use for data validation purpose.</span></span>
3. <span data-ttu-id="5ea5b-259">La fabrique de données s'exécute sur la base de fichiers csv séparés par des virgules.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-259">The data factory runs based on csv files that are comma-delimited.</span></span> <span data-ttu-id="5ea5b-260">Si une valeur de champ comporte une virgule, cela peut interférer avec les résultats.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-260">If there is a field value that has a comma, it may interfere with the results.</span></span> <span data-ttu-id="5ea5b-261">Vous devez supprimer les virgules.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-261">You need to remove the commas.</span></span>
4. <span data-ttu-id="5ea5b-262">L'onglet **Surveillance** fournit des informations sur toutes les étapes et les données traitées.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-262">The **Monitoring** tab provides information about all steps and data processed.</span></span> <span data-ttu-id="5ea5b-263">Sélectionnez une étape spécifique pour la déboguer.</span><span class="sxs-lookup"><span data-stu-id="5ea5b-263">Select a specific step to debug it.</span></span>

    ![Onglet Surveillance](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a><span data-ttu-id="5ea5b-265">En savoir plus sur le modèle</span><span class="sxs-lookup"><span data-stu-id="5ea5b-265">Learn more about the template</span></span>

<span data-ttu-id="5ea5b-266">Vous pouvez trouver des commentaires sur le modèle dans le fichier [readme.md](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).</span><span class="sxs-lookup"><span data-stu-id="5ea5b-266">You can find comments for the template the [readme.md](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md) file.</span></span>
