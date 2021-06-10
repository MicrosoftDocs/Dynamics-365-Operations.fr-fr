---
title: Effectuer une mise à niveau vers le modèle de partie et de carnet d’adresses global
description: Cette rubrique décrit comment mettre à niveau les données à double écriture en modèle de carnet d'adresses global et de partie.
author: RamaKrishnamoorthy
ms.date: 03/31/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: 90ddbe704ab21d62752b581a813601e8986c2103
ms.sourcegitcommit: 180548e3c10459776cf199989d3753e0c1555912
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2021
ms.locfileid: "6112671"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a><span data-ttu-id="7e545-103">Effectuer une mise à niveau vers le modèle de partie et de carnet d’adresses global</span><span class="sxs-lookup"><span data-stu-id="7e545-103">Upgrade to the party and global address book model</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="7e545-104">Le [Modèle Microsoft Azure Data Factory](https://aka.ms/dual-write-gab-adf) vous aide à mettre à niveau les données des tables **Compte**, **Contact** et **Fournisseur** existantes en double écriture vers le modèle de partie et de carnet d’adresses global.</span><span class="sxs-lookup"><span data-stu-id="7e545-104">The [Microsoft Azure Data Factory template](https://aka.ms/dual-write-gab-adf) helps you upgrade existing **Account**, **Contact**, and **Vendor** table data in dual-write to the party and global address book model.</span></span> <span data-ttu-id="7e545-105">Le modèle rapproche les données des applications Finance and Operations et des applications Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="7e545-105">The template reconciles the data from both finance and operations apps and customer engagement applications.</span></span> <span data-ttu-id="7e545-106">À la fin du processus, les champs **Partie** et **Contact** des enregistrements **Partie** seront créés et associés aux enregistrements **Compte**, **Contact** et **Fournisseur** dans les applications d'engagement client.</span><span class="sxs-lookup"><span data-stu-id="7e545-106">At the end of the process, **Party** and **Contact** fields for **Party** records will be created and associated with **Account**, **Contact**, and **Vendor** records in customer engagement applications.</span></span> <span data-ttu-id="7e545-107">Un fichier .csv (`FONewParty.csv`) est généré pour créer de nouveaux enregistrements de **Partie** à l’intérieur de l’application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7e545-107">A .csv file (`FONewParty.csv`) is generated to create new **Party** records inside the finance and operations app.</span></span> <span data-ttu-id="7e545-108">Cette rubrique fournit des instructions sur l’utilisation du modèle Data Factory et la mise à niveau de vos données.</span><span class="sxs-lookup"><span data-stu-id="7e545-108">This topic provides instructions about how to use the Data Factory template and upgrade your data.</span></span>

<span data-ttu-id="7e545-109">Si vous n’avez aucune personnalisation, vous pouvez utiliser le modèle tel quel.</span><span class="sxs-lookup"><span data-stu-id="7e545-109">If you don’t have any customizations, you can use the template as is.</span></span> <span data-ttu-id="7e545-110">Si vous avez des personnalisations pour **Compte**, **Contact** et **Fournisseur**, vous devez modifier le modèle en suivant les instructions ci-après.</span><span class="sxs-lookup"><span data-stu-id="7e545-110">If you have customizations for **Account**, **Contact**, and **Vendor** then you must modify the template using the following instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="7e545-111">Le modèle ne met à niveau que les données de **Partie**.</span><span class="sxs-lookup"><span data-stu-id="7e545-111">The template only upgrades the **Party** data.</span></span> <span data-ttu-id="7e545-112">Dans une prochaine version, les adresses postales et électroniques seront incluses.</span><span class="sxs-lookup"><span data-stu-id="7e545-112">In a future release, postal and electronic addresses will be included.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7e545-113">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="7e545-113">Prerequisites</span></span>

<span data-ttu-id="7e545-114">Les conditions préalables suivantes sont requises pour effectuer une mise à niveau vers le modèle de partie et de carnet d’adresses global :</span><span class="sxs-lookup"><span data-stu-id="7e545-114">The following prerequisites are required to upgrade to the party and global address book model:</span></span>

+ [<span data-ttu-id="7e545-115">Abonnement Azure</span><span class="sxs-lookup"><span data-stu-id="7e545-115">Azure subscription</span></span>](https://portal.azure.com/)
+ [<span data-ttu-id="7e545-116">Accès au modèle</span><span class="sxs-lookup"><span data-stu-id="7e545-116">Access to the template</span></span>](https://aka.ms/dual-write-gab-adf)
+ <span data-ttu-id="7e545-117">Vous devez déjà être client de la double écriture.</span><span class="sxs-lookup"><span data-stu-id="7e545-117">You must be an existing dual-write customer.</span></span>

## <a name="prepare-for-the-upgrade"></a><span data-ttu-id="7e545-118">Préparation pour la mise à niveau</span><span class="sxs-lookup"><span data-stu-id="7e545-118">Prepare for the upgrade</span></span>
<span data-ttu-id="7e545-119">Les activités suivantes sont nécessaires pour préparer la mise à niveau :</span><span class="sxs-lookup"><span data-stu-id="7e545-119">The following activities are needed to prepare for the upgrade:</span></span>

+ <span data-ttu-id="7e545-120">**Entièrement synchronisé** : les deux environnements sont dans un état entièrement synchronisé pour **Compte (client)**, **Contact** et **Fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="7e545-120">**Fully synced**: Both environments are in a fully synced state for **Account (Customer)**, **Contact**, and **Vendor**.</span></span>
+ <span data-ttu-id="7e545-121">**Clés d'intégration** : les tables **Compte (client)**, **Contacter** et **Fournisseur** dans les applications d'engagement client utilisent les clés d'intégration livrées prêtes à l'emploi.</span><span class="sxs-lookup"><span data-stu-id="7e545-121">**Integration keys**: **Account (Customer)**, **Contact**, and **Vendor** tables in customer engagement apps are using the integration keys that shipped out-of-the-box.</span></span> <span data-ttu-id="7e545-122">Si vous avez personnalisé les clés d'intégration, vous devez personnaliser le modèle.</span><span class="sxs-lookup"><span data-stu-id="7e545-122">If you customized the integration keys, you must customize the template.</span></span>
+ <span data-ttu-id="7e545-123">**Numéro de partie** : tous les enregistrements **Compte (client)**, **Contact** et **Fournisseur** qui seront mis à niveau ont un numéro de **Partie**.</span><span class="sxs-lookup"><span data-stu-id="7e545-123">**Party number**: All **Account (Customer)**, **Contact**, and **Vendor** records that will be upgraded have a **Party** number.</span></span> <span data-ttu-id="7e545-124">Les enregistrements sans numéro de **Partie** seront ignorés.</span><span class="sxs-lookup"><span data-stu-id="7e545-124">Records without a **Party** number will be ignored.</span></span> <span data-ttu-id="7e545-125">Si vous souhaitez mettre à niveau ces enregistrements, ajoutez-leur un numéro de **Partie** avant de commencer le processus de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="7e545-125">If you want to upgrade those records, add a **Party** number to them before you start the upgrade process.</span></span>
+ <span data-ttu-id="7e545-126">**Panne du système** : pendant le processus de mise à niveau, vous devrez mettre hors connexion les environnements Finance and Operations et Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="7e545-126">**System outage**: During the upgrade process, you will have to take both the finance and operations and customer engagement environments offline.</span></span>
+ <span data-ttu-id="7e545-127">**Instantané** : prenez des instantanés des applications Finance and Operations et des applications Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="7e545-127">**Snapshot**: Take snapshots of both the finance and operations apps and customer engagement apps.</span></span> <span data-ttu-id="7e545-128">Utilisez les instantanés pour restaurer l'état précédent si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="7e545-128">Use the snapshots to restore the previous state if you need to.</span></span>

## <a name="deployment"></a><span data-ttu-id="7e545-129">Déploiement</span><span class="sxs-lookup"><span data-stu-id="7e545-129">Deployment</span></span>

1. <span data-ttu-id="7e545-130">Téléchargez le modèle depuis [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).</span><span class="sxs-lookup"><span data-stu-id="7e545-130">Download the template from [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).</span></span>

2. <span data-ttu-id="7e545-131">Connectez-vous à [Microsoft Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="7e545-131">Sign in to [Microsoft Azure](https://portal.azure.com/).</span></span>

3. <span data-ttu-id="7e545-132">Créez un [groupe de ressources](/azure/azure-resource-manager/management/manage-resource-groups-portal).</span><span class="sxs-lookup"><span data-stu-id="7e545-132">Create a [resource group](/azure/azure-resource-manager/management/manage-resource-groups-portal).</span></span>

4. <span data-ttu-id="7e545-133">Créez un [compte de stockage](/azure/storage/common/storage-account-create?tabs=azure-portal) dans le groupe de ressources que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="7e545-133">Create a [storage account](/azure/storage/common/storage-account-create?tabs=azure-portal) in the resource group that you created.</span></span>

5. <span data-ttu-id="7e545-134">Créez une [fabrique de données](/azure/data-factory/quickstart-create-data-factory-portal) dans le groupe de ressources que vous avez créé ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="7e545-134">Create a [data factory](/azure/data-factory/quickstart-create-data-factory-portal) in above resource group that you created.</span></span>

6. <span data-ttu-id="7e545-135">Ouvrez la fabrique de données et sélectionnez la vignette **Créer et surveiller**.</span><span class="sxs-lookup"><span data-stu-id="7e545-135">Open the data factory and select the **Author & Monitor** tile.</span></span>

7. <span data-ttu-id="7e545-136">Dans l'onglet **Gérer**, sélectionnez **Modèle ARM**.</span><span class="sxs-lookup"><span data-stu-id="7e545-136">On the **Manage** tab, select **ARM template**.</span></span>

8. <span data-ttu-id="7e545-137">Sélectionnez **Importer un modèle ARM** pour importer le modèle **Partie**.</span><span class="sxs-lookup"><span data-stu-id="7e545-137">Select the **Import ARM template** to import the **Party** template.</span></span>

9. <span data-ttu-id="7e545-138">Importez le modèle dans la fabrique de données.</span><span class="sxs-lookup"><span data-stu-id="7e545-138">Import the template into the data factory.</span></span> <span data-ttu-id="7e545-139">Entrez les valeurs suivantes pour les **Détails du projet** et les **Détails de l'instance**.</span><span class="sxs-lookup"><span data-stu-id="7e545-139">Enter the following values for **Project details** and **Instance details**.</span></span>

    <span data-ttu-id="7e545-140">Champ</span><span class="sxs-lookup"><span data-stu-id="7e545-140">Field</span></span> | <span data-ttu-id="7e545-141">Valeur</span><span class="sxs-lookup"><span data-stu-id="7e545-141">Value</span></span>
    ---|---
    <span data-ttu-id="7e545-142">Abonnement</span><span class="sxs-lookup"><span data-stu-id="7e545-142">Subscription</span></span> | <span data-ttu-id="7e545-143">Abonnement Azure</span><span class="sxs-lookup"><span data-stu-id="7e545-143">Azure subscription</span></span>
    <span data-ttu-id="7e545-144">Groupe de ressources</span><span class="sxs-lookup"><span data-stu-id="7e545-144">Resource group</span></span> | <span data-ttu-id="7e545-145">Indiquez la même ressource sous laquelle le compte de stockage est créé.</span><span class="sxs-lookup"><span data-stu-id="7e545-145">Provide same resource under which storage account is created.</span></span>
    <span data-ttu-id="7e545-146">Région</span><span class="sxs-lookup"><span data-stu-id="7e545-146">Region</span></span> | <span data-ttu-id="7e545-147">Spécifiez la région.</span><span class="sxs-lookup"><span data-stu-id="7e545-147">Specify region.</span></span>
    <span data-ttu-id="7e545-148">Nom de la fabrique</span><span class="sxs-lookup"><span data-stu-id="7e545-148">Factory Name</span></span> | <span data-ttu-id="7e545-149">Spécifiez le nom de la fabrique.</span><span class="sxs-lookup"><span data-stu-id="7e545-149">Specify factory name.</span></span>
    <span data-ttu-id="7e545-150">FO Linked Service_service Principal Key</span><span class="sxs-lookup"><span data-stu-id="7e545-150">FO Linked Service_service Principal Key</span></span> | <span data-ttu-id="7e545-151">Spécifiez la clé de l'application.</span><span class="sxs-lookup"><span data-stu-id="7e545-151">Specify the application's key.</span></span>
    <span data-ttu-id="7e545-152">Azure Blob Storage_connection String</span><span class="sxs-lookup"><span data-stu-id="7e545-152">Azure Blob Storage_connection String</span></span> | <span data-ttu-id="7e545-153">Chaîne de connexion au Stockage Blob Azure</span><span class="sxs-lookup"><span data-stu-id="7e545-153">Azure Blob storage connection string.</span></span>
    <span data-ttu-id="7e545-154">Dynamics Crm Linked Service_password</span><span class="sxs-lookup"><span data-stu-id="7e545-154">Dynamics Crm Linked Service_password</span></span> | <span data-ttu-id="7e545-155">Le mot de passe du compte d'utilisateur que vous avez spécifié comme nom d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7e545-155">The password for the user account you specified as the username.</span></span>
    <span data-ttu-id="7e545-156">FO Linked Service_properties_type Properties_url</span><span class="sxs-lookup"><span data-stu-id="7e545-156">FO Linked Service_properties_type Properties_url</span></span>  | `https://sampledynamics.sandbox-operationsdynamics.com/data`
    <span data-ttu-id="7e545-157">FO Linked Service_properties_type Properties_tenant</span><span class="sxs-lookup"><span data-stu-id="7e545-157">FO Linked Service_properties_type Properties_tenant</span></span> | <span data-ttu-id="7e545-158">Spécifiez les informations de locataire (nom de domaine ou ID de locataire) sous lesquelles réside votre application.</span><span class="sxs-lookup"><span data-stu-id="7e545-158">Specify the tenant information (domain name or tenant ID) under which your application resides.</span></span>
    <span data-ttu-id="7e545-159">FO Linked Service_properties_type Properties_aad Resource Id</span><span class="sxs-lookup"><span data-stu-id="7e545-159">FO Linked Service_properties_type Properties_aad Resource Id</span></span> | `https://sampledynamics.sandboxoperationsdynamics.com`
    <span data-ttu-id="7e545-160">FO Linked Service_properties_type Properties_service Principal Id</span><span class="sxs-lookup"><span data-stu-id="7e545-160">FO Linked Service_properties_type Properties_service Principal Id</span></span> | <span data-ttu-id="7e545-161">Spécifiez l'ID du client de l'application.</span><span class="sxs-lookup"><span data-stu-id="7e545-161">Specify the application's client ID.</span></span>
    <span data-ttu-id="7e545-162">Dynamics Crm Linked Service_properties_type Properties_username</span><span class="sxs-lookup"><span data-stu-id="7e545-162">Dynamics Crm Linked Service_properties_type Properties_username</span></span> | <span data-ttu-id="7e545-163">Le nom d’utilisateur pour se connecter à Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="7e545-163">The username to connect to Dynamics 365.</span></span>

    <span data-ttu-id="7e545-164">Pour des informations supplémentaires, consultez l’une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="7e545-164">For additional information, refer to the following topics:</span></span> 
    
    - [<span data-ttu-id="7e545-165">Promouvoir manuellement un modèle Resource Manager pour chaque environnement</span><span class="sxs-lookup"><span data-stu-id="7e545-165">Manually promote a Resource Manager template for each environment</span></span>](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment)
    - [<span data-ttu-id="7e545-166">Propriétés du service lié</span><span class="sxs-lookup"><span data-stu-id="7e545-166">Linked service properties</span></span>](/azure/data-factory/connector-dynamics-ax#linked-service-properties)
    - [<span data-ttu-id="7e545-167">Copier des données à l’aide d’Azure Data Factory</span><span class="sxs-lookup"><span data-stu-id="7e545-167">Copy data using Azure Data Factory</span></span>](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)

10. <span data-ttu-id="7e545-168">Après le déploiement, vérifiez les jeux de données, le flux de données et le service lié de la fabrique de données.</span><span class="sxs-lookup"><span data-stu-id="7e545-168">After deployment, validate the datasets, data flow, and linked service of the data factory.</span></span>

   ![Jeux de données, flux de données et service lié](media/data-factory-validate.png)

11. <span data-ttu-id="7e545-170">Accédez à **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="7e545-170">Navigate to **Manage**.</span></span> <span data-ttu-id="7e545-171">En dessous de **Connexions**, sélectionnez **Service lié**.</span><span class="sxs-lookup"><span data-stu-id="7e545-171">Under **Connections**, select **Linked Service**.</span></span> <span data-ttu-id="7e545-172">Sélectionnez **DynamicsCrmLinkedService**.</span><span class="sxs-lookup"><span data-stu-id="7e545-172">Select **DynamicsCrmLinkedService**.</span></span> <span data-ttu-id="7e545-173">Dans le formulaire **Modifier le service lié (Dynamics CRM)**, entrez les valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="7e545-173">In the **Edit linked service (Dynamics CRM)** form, enter the following values.</span></span>

    <span data-ttu-id="7e545-174">Champ</span><span class="sxs-lookup"><span data-stu-id="7e545-174">Field</span></span> | <span data-ttu-id="7e545-175">Valeur </span><span class="sxs-lookup"><span data-stu-id="7e545-175">Value</span></span>
    ---|---
    <span data-ttu-id="7e545-176">Nom</span><span class="sxs-lookup"><span data-stu-id="7e545-176">Name</span></span> | <span data-ttu-id="7e545-177">DynamicsCrmLinkedService</span><span class="sxs-lookup"><span data-stu-id="7e545-177">DynamicsCrmLinkedService</span></span>
    <span data-ttu-id="7e545-178">Description </span><span class="sxs-lookup"><span data-stu-id="7e545-178">Description</span></span> | <span data-ttu-id="7e545-179">Services liés pour se connecter à l'instance CRM pour récupérer les données des entités</span><span class="sxs-lookup"><span data-stu-id="7e545-179">Linked services to connect with CRM instance to fetch entities data</span></span>
    <span data-ttu-id="7e545-180">Connexion via le runtime d'intégration</span><span class="sxs-lookup"><span data-stu-id="7e545-180">Connect via integration runtime</span></span> | <span data-ttu-id="7e545-181">AutoResolvelntegrationRuntime</span><span class="sxs-lookup"><span data-stu-id="7e545-181">AutoResolvelntegrationRuntime</span></span>
    <span data-ttu-id="7e545-182">Type de déploiement</span><span class="sxs-lookup"><span data-stu-id="7e545-182">Deployment type</span></span> | <span data-ttu-id="7e545-183">En ligne</span><span class="sxs-lookup"><span data-stu-id="7e545-183">Online</span></span>
    <span data-ttu-id="7e545-184">URI du service</span><span class="sxs-lookup"><span data-stu-id="7e545-184">Service Uri</span></span> | `https://<organization-name>.crm[x].dynamics.com`
    <span data-ttu-id="7e545-185">Type d'authentification</span><span class="sxs-lookup"><span data-stu-id="7e545-185">Authentication type</span></span> | <span data-ttu-id="7e545-186">Office365</span><span class="sxs-lookup"><span data-stu-id="7e545-186">Office365</span></span>
    <span data-ttu-id="7e545-187">Nom d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="7e545-187">User name</span></span> |
    <span data-ttu-id="7e545-188">Mot de passe ou Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="7e545-188">Password or Azure Key Vault</span></span> | <span data-ttu-id="7e545-189">Mot de passe</span><span class="sxs-lookup"><span data-stu-id="7e545-189">Password</span></span>
    <span data-ttu-id="7e545-190">Mot de passe</span><span class="sxs-lookup"><span data-stu-id="7e545-190">Password</span></span> |

## <a name="run-the-template"></a><span data-ttu-id="7e545-191">Exécution du modèle</span><span class="sxs-lookup"><span data-stu-id="7e545-191">Run the template</span></span>

1. <span data-ttu-id="7e545-192">Arrêtez les mappages de double écriture de **Compte**, **Contact** et **Fournisseur** suivants à l’aide de l’application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7e545-192">Stop the following **Account**, **Contact**, and **Vendor** dual-write maps using the Finance and Operations app.</span></span>

    + <span data-ttu-id="7e545-193">Clients V3 (accounts)</span><span class="sxs-lookup"><span data-stu-id="7e545-193">Customers V3(accounts)</span></span>
    + <span data-ttu-id="7e545-194">Clients V3 (contacts)</span><span class="sxs-lookup"><span data-stu-id="7e545-194">Customers V3(contacts)</span></span>
    + <span data-ttu-id="7e545-195">CDS Contacts V2 (contacts)</span><span class="sxs-lookup"><span data-stu-id="7e545-195">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="7e545-196">CDS Contacts V2 (contacts)</span><span class="sxs-lookup"><span data-stu-id="7e545-196">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="7e545-197">Fournisseurs V2 (msdyn_vendor)</span><span class="sxs-lookup"><span data-stu-id="7e545-197">Vendor V2 (msdyn_vendor)</span></span>

2. <span data-ttu-id="7e545-198">Assurez-vous que les cartes sont supprimées de la table `msdy_dualwriteruntimeconfig` dans Dataverse.</span><span class="sxs-lookup"><span data-stu-id="7e545-198">Make sure the maps are removed from the `msdy_dualwriteruntimeconfig` table in Dataverse.</span></span>

3. <span data-ttu-id="7e545-199">Installez [Solutions de double écriture pour les Carnets d'adresses global et de partie](https://aka.ms/dual-write-gab) à partir de AppSource.</span><span class="sxs-lookup"><span data-stu-id="7e545-199">Install [Dual-write Party and Global Address Book Solutions](https://aka.ms/dual-write-gab) from AppSource.</span></span>

4. <span data-ttu-id="7e545-200">Dans l’application Finance and Operations, si les tables suivantes contiennent des données, exécutez la **Synchronisation initiale** pour elles.</span><span class="sxs-lookup"><span data-stu-id="7e545-200">In the finance and operations app, if the following tables contain data, then run **Initial Sync** for them.</span></span>

    + <span data-ttu-id="7e545-201">Salutations</span><span class="sxs-lookup"><span data-stu-id="7e545-201">Salutations</span></span>
    + <span data-ttu-id="7e545-202">Type de caractère personnel</span><span class="sxs-lookup"><span data-stu-id="7e545-202">Personal character types</span></span>
    + <span data-ttu-id="7e545-203">Politesses</span><span class="sxs-lookup"><span data-stu-id="7e545-203">Complimentary closing</span></span>
    + <span data-ttu-id="7e545-204">Titres des contacts</span><span class="sxs-lookup"><span data-stu-id="7e545-204">Contact person titles</span></span>
    + <span data-ttu-id="7e545-205">Rôles de prise de décision</span><span class="sxs-lookup"><span data-stu-id="7e545-205">Decision making roles</span></span>
    + <span data-ttu-id="7e545-206">Niveaux de fidélité</span><span class="sxs-lookup"><span data-stu-id="7e545-206">Loyalty levels</span></span>

5. <span data-ttu-id="7e545-207">Dans l’application Customer Engagement, désactivez les étapes suivantes du plug-in.</span><span class="sxs-lookup"><span data-stu-id="7e545-207">In the customer engagement app, disable the following plug-in steps.</span></span>

    + <span data-ttu-id="7e545-208">Mise à jour du compte</span><span class="sxs-lookup"><span data-stu-id="7e545-208">Account Update</span></span>
         + <span data-ttu-id="7e545-209">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity : Mise à jour du compte</span><span class="sxs-lookup"><span data-stu-id="7e545-209">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="7e545-210">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes : Mise à jour du compte</span><span class="sxs-lookup"><span data-stu-id="7e545-210">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="7e545-211">Mise à jour du contact</span><span class="sxs-lookup"><span data-stu-id="7e545-211">Contact Update</span></span>
         + <span data-ttu-id="7e545-212">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity : Mise à jour du contact</span><span class="sxs-lookup"><span data-stu-id="7e545-212">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="7e545-213">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact : Mise à jour du contact</span><span class="sxs-lookup"><span data-stu-id="7e545-213">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="7e545-214">Mise à jour de msdyn_party</span><span class="sxs-lookup"><span data-stu-id="7e545-214">msdyn_party Update</span></span>
         + <span data-ttu-id="7e545-215">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity : Mise à jour de msdyn_party</span><span class="sxs-lookup"><span data-stu-id="7e545-215">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="7e545-216">Mise à jour de msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="7e545-216">msdyn_vendor Update</span></span>
         + <span data-ttu-id="7e545-217">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity : Mise à jour de msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="7e545-217">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

6. <span data-ttu-id="7e545-218">Dans l'application d'engagement client, désactivez les workflows suivants :</span><span class="sxs-lookup"><span data-stu-id="7e545-218">In the customer engagement app, disable the following workflows:</span></span>

    + <span data-ttu-id="7e545-219">Créer des fournisseurs dans la table Comptes</span><span class="sxs-lookup"><span data-stu-id="7e545-219">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="7e545-220">Créer des fournisseurs dans la table Comptes</span><span class="sxs-lookup"><span data-stu-id="7e545-220">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="7e545-221">Créer des fournisseurs de type Personne dans la table Contacts</span><span class="sxs-lookup"><span data-stu-id="7e545-221">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="7e545-222">Créer des fournisseurs de type Personne dans la table Fournisseurs</span><span class="sxs-lookup"><span data-stu-id="7e545-222">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="7e545-223">Mettre à jour des fournisseurs dans la table Comptes</span><span class="sxs-lookup"><span data-stu-id="7e545-223">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="7e545-224">Mettre à jour des fournisseurs dans la table Fournisseurs</span><span class="sxs-lookup"><span data-stu-id="7e545-224">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="7e545-225">Mettre à jour des fournisseurs de type Personne dans la table Contacts</span><span class="sxs-lookup"><span data-stu-id="7e545-225">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="7e545-226">Mettre à jour des fournisseurs de type Personne dans la table Fournisseurs</span><span class="sxs-lookup"><span data-stu-id="7e545-226">Update Vendors of type Person in Vendors Table</span></span>

7. <span data-ttu-id="7e545-227">Dans la fabrique de données, exécutez le modèle en sélectionnant **Déclencher maintenant**, comme indiqué dans l'image suivante.</span><span class="sxs-lookup"><span data-stu-id="7e545-227">In the data factory, run the template by selecting **Trigger now** as shown in the following image.</span></span> <span data-ttu-id="7e545-228">Ce processus peut prendre quelques heures, en fonction du volume de données.</span><span class="sxs-lookup"><span data-stu-id="7e545-228">This process might take a few hours to complete based on the data volume.</span></span>

    ![Déclencher l'exécution](media/data-factory-trigger.png)

    > [!NOTE]
    > <span data-ttu-id="7e545-230">Si vous avez des personnalisations pour **Compte**, **Contact** et **Fournisseur**, vous devez modifier le modèle.</span><span class="sxs-lookup"><span data-stu-id="7e545-230">If you have customizations for **Account**, **Contact**, and **Vendor**, then you need to modify the template.</span></span>

8. <span data-ttu-id="7e545-231">Importez les nouveaux enregistrements **Partie** dans l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7e545-231">Import the new **Party** records in the Finance and Operations app.</span></span>

    + <span data-ttu-id="7e545-232">Téléchargez le fichier `FONewParty.csv` à partir du stockage blob Azure.</span><span class="sxs-lookup"><span data-stu-id="7e545-232">Download the `FONewParty.csv` file from Azure blob storage.</span></span> <span data-ttu-id="7e545-233">Le chemin d'accès est `partybootstrapping/output/FONewParty.csv`.</span><span class="sxs-lookup"><span data-stu-id="7e545-233">The path is `partybootstrapping/output/FONewParty.csv`.</span></span>
    + <span data-ttu-id="7e545-234">Convertissez le fichier `FONewParty.csv` en fichier Excel et importez le fichier Excel dans l’application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7e545-234">Convert the `FONewParty.csv` file into an Excel file and import the Excel file into the finance and operations app.</span></span> <span data-ttu-id="7e545-235">Si l’importation csv fonctionne pour vous, vous pouvez importer le fichier csv directement.</span><span class="sxs-lookup"><span data-stu-id="7e545-235">If the csv import works for you, you can import the csv file directly.</span></span> <span data-ttu-id="7e545-236">L'importation peut prendre quelques heures, selon le volume de données.</span><span class="sxs-lookup"><span data-stu-id="7e545-236">The import could take a few hours to run, depending on the data volume.</span></span> <span data-ttu-id="7e545-237">Pour plus d’informations, voir [Vue d’ensemble des tâches d’importation et d’exportation de données](../data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="7e545-237">For more information, see [Data import and export jobs overview](../data-import-export-job.md).</span></span>

    ![Importer les enregistrements de partie de Dataverse](media/data-factory-import-party.png)

9. <span data-ttu-id="7e545-239">Dans les applications Customer Engagement, désactivez les étapes suivantes du plug-in :</span><span class="sxs-lookup"><span data-stu-id="7e545-239">In the customer engagement apps, enable the following plug-in steps:</span></span>

    + <span data-ttu-id="7e545-240">Mise à jour du compte</span><span class="sxs-lookup"><span data-stu-id="7e545-240">Account Update</span></span>
         + <span data-ttu-id="7e545-241">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity : Mise à jour du compte</span><span class="sxs-lookup"><span data-stu-id="7e545-241">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="7e545-242">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes : Mise à jour du compte</span><span class="sxs-lookup"><span data-stu-id="7e545-242">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="7e545-243">Mise à jour du contact</span><span class="sxs-lookup"><span data-stu-id="7e545-243">Contact Update</span></span>
         + <span data-ttu-id="7e545-244">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity : Mise à jour du contact</span><span class="sxs-lookup"><span data-stu-id="7e545-244">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="7e545-245">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact : Mise à jour du contact</span><span class="sxs-lookup"><span data-stu-id="7e545-245">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="7e545-246">Mise à jour de msdyn_party</span><span class="sxs-lookup"><span data-stu-id="7e545-246">msdyn_party Update</span></span>
         + <span data-ttu-id="7e545-247">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity : Mise à jour de msdyn_party</span><span class="sxs-lookup"><span data-stu-id="7e545-247">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="7e545-248">Mise à jour de msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="7e545-248">msdyn_vendor Update</span></span>
         + <span data-ttu-id="7e545-249">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity : Mise à jour de msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="7e545-249">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

10. <span data-ttu-id="7e545-250">Dans les applications d'engagement client, activez les workflows suivants si vous les avez désactivés lors des étapes précédentes :</span><span class="sxs-lookup"><span data-stu-id="7e545-250">In the customer engagement apps, activate the following workflows if you deactivated them in previous steps:</span></span>

    + <span data-ttu-id="7e545-251">Créer des fournisseurs dans la table Comptes</span><span class="sxs-lookup"><span data-stu-id="7e545-251">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="7e545-252">Créer des fournisseurs dans la table Comptes</span><span class="sxs-lookup"><span data-stu-id="7e545-252">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="7e545-253">Créer des fournisseurs de type Personne dans la table Contacts</span><span class="sxs-lookup"><span data-stu-id="7e545-253">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="7e545-254">Créer des fournisseurs de type Personne dans la table Fournisseurs</span><span class="sxs-lookup"><span data-stu-id="7e545-254">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="7e545-255">Mettre à jour des fournisseurs dans la table Comptes</span><span class="sxs-lookup"><span data-stu-id="7e545-255">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="7e545-256">Mettre à jour des fournisseurs dans la table Fournisseurs</span><span class="sxs-lookup"><span data-stu-id="7e545-256">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="7e545-257">Mettre à jour des fournisseurs de type Personne dans la table Contacts</span><span class="sxs-lookup"><span data-stu-id="7e545-257">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="7e545-258">Mettre à jour des fournisseurs de type Personne dans la table Fournisseurs</span><span class="sxs-lookup"><span data-stu-id="7e545-258">Update Vendors of type Person in Vendors Table</span></span>

11. <span data-ttu-id="7e545-259">Exécutez les cartes associées à la **Partie** comme indiqué dans [Carnet d'adresses global et de partie](party-gab.md).</span><span class="sxs-lookup"><span data-stu-id="7e545-259">Run the **Party**-related maps as instructed in [Party and global address book](party-gab.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="7e545-260">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="7e545-260">Troubleshooting</span></span>

1. <span data-ttu-id="7e545-261">Si le processus échoue, réexécutez la fabrique de données à partir de l’activité qui a échoué.</span><span class="sxs-lookup"><span data-stu-id="7e545-261">If the process fails, rerun the data factory starting from the failed activity.</span></span>
2. <span data-ttu-id="7e545-262">Certains fichiers sont générés par la fabrique de données ; vous pouvez les utiliser à des fins de validation des données.</span><span class="sxs-lookup"><span data-stu-id="7e545-262">Some files are generated by the data factory that you can use for data validation purpose.</span></span>
3. <span data-ttu-id="7e545-263">La fabrique de données s'exécute sur la base de fichiers csv séparés par des virgules.</span><span class="sxs-lookup"><span data-stu-id="7e545-263">The data factory runs based on csv files that are comma-delimited.</span></span> <span data-ttu-id="7e545-264">Si une valeur de champ comporte une virgule, cela peut interférer avec les résultats.</span><span class="sxs-lookup"><span data-stu-id="7e545-264">If there is a field value that has a comma, it may interfere with the results.</span></span> <span data-ttu-id="7e545-265">Vous devez supprimer les virgules.</span><span class="sxs-lookup"><span data-stu-id="7e545-265">You need to remove the commas.</span></span>
4. <span data-ttu-id="7e545-266">L'onglet **Surveillance** fournit des informations sur toutes les étapes et les données traitées.</span><span class="sxs-lookup"><span data-stu-id="7e545-266">The **Monitoring** tab provides information about all steps and data processed.</span></span> <span data-ttu-id="7e545-267">Sélectionnez une étape spécifique pour la déboguer.</span><span class="sxs-lookup"><span data-stu-id="7e545-267">Select a specific step to debug it.</span></span>

    ![Onglet Surveillance](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a><span data-ttu-id="7e545-269">En savoir plus sur le modèle</span><span class="sxs-lookup"><span data-stu-id="7e545-269">Learn more about the template</span></span>

<span data-ttu-id="7e545-270">Vous trouverez des informations supplémentaires sur le modèle dans [Commentaires pour le fichier Lisez-moi du modèle Azure Data Factory](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).</span><span class="sxs-lookup"><span data-stu-id="7e545-270">You can find additional information about the template in [Comments for Azure Data Factory template readme](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).</span></span>
