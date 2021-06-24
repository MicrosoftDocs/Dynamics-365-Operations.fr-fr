---
title: Configuration de Informations financières pour la version préliminaire publique (version préliminaire) - versions 10.0.20 et ultérieures
description: Cette rubrique explique comment configurer votre système pour utiliser les fonctionnalités disponibles dans Informations financières pour la version 10.0.20 en version préliminaire publique et les versions ultérieures.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-06-03
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: 613bd4816e2f0c4fbb56cf79779a08c6a09592bd
ms.sourcegitcommit: 655b0e16c7aef6182cd58bc816b901470e1bb2ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2021
ms.locfileid: "6222610"
---
# <a name="configuration-for-finance-insights-for-public-preview-preview---version-10020-and-later"></a><span data-ttu-id="be480-103">Configuration de Informations financières pour la version préliminaire publique (version préliminaire) - versions 10.0.20 et ultérieures</span><span class="sxs-lookup"><span data-stu-id="be480-103">Configuration for Finance insights for public preview (preview) - version 10.0.20 and later</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="be480-104">Informations financières combine les fonctionnalités de Microsoft Dynamics 365 Finance avec Dataverse, Azure et AI Builder pour fournir de puissants outils de prévision à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="be480-104">Finance insights combines functionality from Microsoft Dynamics 365 Finance with Dataverse, Azure, and AI Builder to provide powerful forecasting tools for your organization.</span></span> <span data-ttu-id="be480-105">Cette rubrique explique comment configurer Dynamics 365 Finance version 10.0.20 pour que votre système puisse utiliser les fonctionnalités disponibles dans la version préliminaire publique de Informations financières.</span><span class="sxs-lookup"><span data-stu-id="be480-105">This topic explains how to configure Dynamics 365 Finance version 10.0.20 so that your system can use the capabilities that are available in Finance insights public preview.</span></span>

> [!NOTE]
> <span data-ttu-id="be480-106">Les étapes de configuration décrites dans cette rubrique s’appliquent uniquement à Finance, version 10.0.20 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="be480-106">The configuration steps that are described in this topic apply only to Finance version 10.0.20 and later.</span></span> <span data-ttu-id="be480-107">Pour configurer Informations financières version 10.0.19 et versions ultérieures, voir [Configuration de Informations financières - versions jusqu’à 10.0.18](configure-for-fin-insites.md).</span><span class="sxs-lookup"><span data-stu-id="be480-107">'To set up Finance insights on version 10.0.19 and earlier, see [Configuration for Finance insights - versions up to 10.0.18](configure-for-fin-insites.md).</span></span>

## <a name="deploy-finance"></a><span data-ttu-id="be480-108">Déploiement de Finance</span><span class="sxs-lookup"><span data-stu-id="be480-108">Deploy Finance</span></span>

<span data-ttu-id="be480-109">Procédez comme suit pour déployer les environnements.</span><span class="sxs-lookup"><span data-stu-id="be480-109">Follow these steps to deploy the environments.</span></span>

1. <span data-ttu-id="be480-110">Dans Microsoft Dynamics Lifecycle Services (LCS), créez ou mettez à jour un environnement Finance.</span><span class="sxs-lookup"><span data-stu-id="be480-110">In Microsoft Dynamics Lifecycle Services (LCS), create or update a Finance environment.</span></span> <span data-ttu-id="be480-111">L’environnement nécessite la version 10.0.20 ou ultérieure des applications Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="be480-111">The environment requires app version 10.0.20 or later of Finance and Operations apps.</span></span>
2. <span data-ttu-id="be480-112">L’environnement doit être un environnement haute disponibilité (HA) dans Sandbox.</span><span class="sxs-lookup"><span data-stu-id="be480-112">The environment must be a high-availability (HA) environment in Sandbox.</span></span> <span data-ttu-id="be480-113">(Ce type d’environnement est également appelé environnement de niveau 2.) Pour plus d’informations, voir [Planification de l’environnement](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="be480-113">(This type of environment is also known as a Tier-2 environment.) For more information, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
3. <span data-ttu-id="be480-114">Si vous configurez Informations financières dans un environnement bac à sable, vous devrez peut-être copier les données de production dans cet environnement pour que les prédictions fonctionnent.</span><span class="sxs-lookup"><span data-stu-id="be480-114">If you are configuring Finance insights in a Sandbox environment, you might need to copy production data to that environment for predictions to work.</span></span> <span data-ttu-id="be480-115">Le modèle de prédiction utilise plusieurs années de données pour créer les prédictions.</span><span class="sxs-lookup"><span data-stu-id="be480-115">The prediction model uses multiple years of data to build predictions.</span></span> <span data-ttu-id="be480-116">Les données de démonstration de Contoso ne contiennent pas suffisamment de données historiques pour entraîner correctement le modèle de prédiction.</span><span class="sxs-lookup"><span data-stu-id="be480-116">The Contoso demo data doesn’t contain enough historical data to train the prediction model adequately.</span></span> 

## <a name="configure-dataverse"></a><span data-ttu-id="be480-117">Configurer Dataverse</span><span class="sxs-lookup"><span data-stu-id="be480-117">Configure Dataverse</span></span>

<span data-ttu-id="be480-118">Procédez comme suit pour configurer Dataverse pour Informations financières.</span><span class="sxs-lookup"><span data-stu-id="be480-118">Follow these steps to configure Dataverse for Finance insights.</span></span>

1. <span data-ttu-id="be480-119">Dans LCS, ouvrez la page d’environnement et vérifiez que la section **Intégration Power Platform** est déjà configurée.</span><span class="sxs-lookup"><span data-stu-id="be480-119">In LCS, open the environment page, and verify that the **Power Platform Integration** section is already set up.</span></span>

    - <span data-ttu-id="be480-120">Si elle est déjà configurée, le nom d’environnement Dataverse lié à l’environnement Finance doit être répertorié.</span><span class="sxs-lookup"><span data-stu-id="be480-120">If it's already set up, the Dataverse environment name that is linked to the Finance environment should be listed.</span></span>
    - <span data-ttu-id="be480-121">Si elle n’est pas encore configurée, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="be480-121">If it isn't yet set up, follow these steps:</span></span>

        1. <span data-ttu-id="be480-122">Dans la section **Intégration Power Platform**, sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="be480-122">In the **Power Platform Integration** section, select **Setup**.</span></span> <span data-ttu-id="be480-123">La configuration de l’environnement peut prendre jusqu’à une heure.</span><span class="sxs-lookup"><span data-stu-id="be480-123">Setup of the environment might take up to an hour.</span></span>
        2. <span data-ttu-id="be480-124">Si l’environnement Dataverse est correctement configuré, le nom de l’environnement Dataverse lié à l’environnement Finance devrait figurer dans la liste.</span><span class="sxs-lookup"><span data-stu-id="be480-124">If the Dataverse environment is successfully set up, the Dataverse environment name that is linked to the Finance environment should be listed.</span></span>

        > [!NOTE]
        > <span data-ttu-id="be480-125">Après avoir terminé la configuration de l’environnement, **ne sélectionnez pas** **Lien vers CDS for Apps**.</span><span class="sxs-lookup"><span data-stu-id="be480-125">After you complete the environment setup, do **not** select **Link to CDS for Apps**.</span></span> <span data-ttu-id="be480-126">Ce bouton n’est pas requis pour Informations financières.</span><span class="sxs-lookup"><span data-stu-id="be480-126">This button isn't required for Finance insights.</span></span> <span data-ttu-id="be480-127">Si vous le sélectionnez, vous ne pourrez pas configurer les compléments d’environnement requis dans LCS.</span><span class="sxs-lookup"><span data-stu-id="be480-127">If you select it, you won't be able to configure the required environment add-ins in LCS.</span></span>

## <a name="configure-azure"></a><span data-ttu-id="be480-128">Configurer Azure</span><span class="sxs-lookup"><span data-stu-id="be480-128">Configure Azure</span></span>

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a><span data-ttu-id="be480-129">Utiliser Azure Cloud Shell pour configurer les ressources Data Lake de Informations financières</span><span class="sxs-lookup"><span data-stu-id="be480-129">Use Azure Cloud Shell to set up Finance insights Data Lake resources</span></span>

# <a name="use-a-windows-powershell-script"></a>[<span data-ttu-id="be480-130">Utiliser un script de configuration Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="be480-130">Use a Windows PowerShell script</span></span>](#tab/use-a-powershell-script)

<span data-ttu-id="be480-131">Un script Windows PowerShell a été fourni pour que vous puissiez facilement configurer les ressources Azure décrites dans [Configurer l’exportation vers Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="be480-131">A Windows PowerShell script has been provided so that you can easily set up the Azure resources that are described in [Configure export to Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span></span> <span data-ttu-id="be480-132">Si vous préférez effectuer une configuration manuelle, ignorez cette procédure et suivez la procédure de la section [Configuration manuelle](#manual-setup) à la place.</span><span class="sxs-lookup"><span data-stu-id="be480-132">If you prefer to do the setup manually, skip this procedure, and complete the procedure in the [Manual setup](#manual-setup) section instead.</span></span>

> [!NOTE]
> <span data-ttu-id="be480-133">Utilisez la procédure suivante pour exécuter le script Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="be480-133">Use the following procedure to run the Windows PowerShell script.</span></span> <span data-ttu-id="be480-134">La configuration peut ne pas fonctionner si vous utilisez l’option **Essayer** dans Azure CLI ou si vous exécutez le script sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="be480-134">The setup might not work if you use the **Try it** option in Azure CLI or if you run the script on your computer.</span></span>

<span data-ttu-id="be480-135">Suivez ces étapes pour utiliser le script Windows PowerShell pour configurer Azure.</span><span class="sxs-lookup"><span data-stu-id="be480-135">Follow these steps to use the Windows PowerShell script to configure Azure.</span></span> <span data-ttu-id="be480-136">Vous devez disposer des droits pour créer un groupe de ressources Azure, des ressources Azure et une application Azure AD.</span><span class="sxs-lookup"><span data-stu-id="be480-136">You must have rights to create an Azure resource group, Azure resources, and an Azure AD application.</span></span> <span data-ttu-id="be480-137">Pour plus d’informations sur les autorisations requises, voir [Vérifier les autorisations Azure AD](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span><span class="sxs-lookup"><span data-stu-id="be480-137">For information about the required permissions, see [Check Azure AD permissions](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span></span>

1. <span data-ttu-id="be480-138">Dans le [portail Azure](https://portal.azure.com), accédez à votre abonnement Azure cible.</span><span class="sxs-lookup"><span data-stu-id="be480-138">In the [Azure portal](https://portal.azure.com), go to your target Azure subscription.</span></span>
2. <span data-ttu-id="be480-139">Sélectionnez **Cloud Shell** à droite du champ **Recherche**.</span><span class="sxs-lookup"><span data-stu-id="be480-139">Select **Cloud Shell** to the right of the **Search** field.</span></span>
3. <span data-ttu-id="be480-140">Sélectionnez **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="be480-140">Select **PowerShell**.</span></span>
4. <span data-ttu-id="be480-141">Créez un espace de stockage, si vous êtes invité à le faire.</span><span class="sxs-lookup"><span data-stu-id="be480-141">Create storage if you're prompted to create it.</span></span>
5. <span data-ttu-id="be480-142">Dans l’onglet **Azure CLI**, sélectionnez **Copier**.</span><span class="sxs-lookup"><span data-stu-id="be480-142">On the **Azure CLI** tab, select **Copy**.</span></span>
6. <span data-ttu-id="be480-143">Dans le Bloc-notes, ouvrez un nouveau fichier et collez le script Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="be480-143">In Notepad, open a new file, and paste in the Windows PowerShell script.</span></span>
7. <span data-ttu-id="be480-144">Enregistrez le fichier sous **ConfigureDataLake.ps1**.</span><span class="sxs-lookup"><span data-stu-id="be480-144">Save the file as **ConfigureDataLake.ps1**.</span></span>
8. <span data-ttu-id="be480-145">Téléchargez le script Windows PowerShell dans la session à l’aide de l’option de menu pour le chargement dans Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="be480-145">Upload the Windows PowerShell script to the session by using the menu option for upload in Cloud Shell.</span></span>
9. <span data-ttu-id="be480-146">Exécutez le script **.\ConfigureDataLake.ps1**.</span><span class="sxs-lookup"><span data-stu-id="be480-146">Run the **.\ConfigureDataLake.ps1** script.</span></span>
10. <span data-ttu-id="be480-147">Suivez les invites pour exécuter le script.</span><span class="sxs-lookup"><span data-stu-id="be480-147">Follow the prompts to run the script.</span></span>
11. <span data-ttu-id="be480-148">Utilisez les informations de la sortie du script pour installer le complément Exporter vers Data Lake dans LCS.</span><span class="sxs-lookup"><span data-stu-id="be480-148">Use the information from the script output to install the Export to Data Lake add-in in LCS.</span></span>

### <a name="manual-setup"></a><span data-ttu-id="be480-149">Configuration manuelle</span><span class="sxs-lookup"><span data-stu-id="be480-149">Manual setup</span></span>

#### <a name="add-applications-to-the-azure-ad-tenant"></a><span data-ttu-id="be480-150">Ajouter des applications au locataire Azure AD</span><span class="sxs-lookup"><span data-stu-id="be480-150">Add applications to the Azure AD tenant</span></span>

1. <span data-ttu-id="be480-151">Dans le [portail Azure](https://portal.azure.com), accédez à **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="be480-151">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**.</span></span>
2. <span data-ttu-id="be480-152">Sélectionnez **Gérer \> Applications de l’entreprise**.</span><span class="sxs-lookup"><span data-stu-id="be480-152">Select **Manage \> Enterprise applications**.</span></span>
3. <span data-ttu-id="be480-153">Recherchez les applications suivantes par ID d’application.</span><span class="sxs-lookup"><span data-stu-id="be480-153">Search for the following applications by app ID.</span></span>

    | <span data-ttu-id="be480-154">Demande</span><span class="sxs-lookup"><span data-stu-id="be480-154">Application</span></span>                              | <span data-ttu-id="be480-155">ID d’application</span><span class="sxs-lookup"><span data-stu-id="be480-155">App ID</span></span>                               |
    |------------------------------------------|--------------------------------------|
    | <span data-ttu-id="be480-156">Microservices ERP Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="be480-156">Microsoft Dynamics ERP Microservices</span></span>     | <span data-ttu-id="be480-157">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="be480-157">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
    | <span data-ttu-id="be480-158">CDS Microservices ERP Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="be480-158">Microsoft Dynamics ERP Microservices CDS</span></span> | <span data-ttu-id="be480-159">703e2651-d3fc-48f5-942c-74274233dba8</span><span class="sxs-lookup"><span data-stu-id="be480-159">703e2651-d3fc-48f5-942c-74274233dba8</span></span> |
    | <span data-ttu-id="be480-160">Service d’autorisation AI Builder</span><span class="sxs-lookup"><span data-stu-id="be480-160">AI Builder Authorization Service</span></span>         | <span data-ttu-id="be480-161">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span><span class="sxs-lookup"><span data-stu-id="be480-161">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span></span> |

<span data-ttu-id="be480-162">Si vous ne trouvez aucune des applications précédentes, essayez les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="be480-162">If you can't find any of the preceding applications, try the following steps.</span></span>

1. <span data-ttu-id="be480-163">Sur votre ordinateur local, sélectionnez le menu **Démarrer** et recherchez **powershell**.</span><span class="sxs-lookup"><span data-stu-id="be480-163">On your local computer, on the **Start** menu, search for **powershell**.</span></span>
2. <span data-ttu-id="be480-164">Sélectionnez et maintenez (ou cliquez avec le bouton droit) sur **Windows PowerShell**, puis sélectionnez **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="be480-164">Select and hold (or right-click) **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="be480-165">Exécutez la commande suivante pour installer le module **AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="be480-165">Run the following command to install the **AzureAD** module.</span></span>

    `Install-Module -Name AzureAD`

4. <span data-ttu-id="be480-166">Si un fournisseur NuGet doit continuer, sélectionnez **O** pour l’installer.</span><span class="sxs-lookup"><span data-stu-id="be480-166">If a NuGet provider is required to continue, select **Y** to install it.</span></span>
5. <span data-ttu-id="be480-167">Si vous recevez un message « Référentiel non approuvé », sélectionnez **O** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="be480-167">If you receive an "Untrusted repository" message, select **Y** to continue.</span></span>
6. <span data-ttu-id="be480-168">Pour chaque application à ajouter, exécutez les commandes suivantes pour ajouter l’application à Azure AD.</span><span class="sxs-lookup"><span data-stu-id="be480-168">For each application that must be added, run the following commands to add the application to Azure AD.</span></span> <span data-ttu-id="be480-169">Lorsque vous y êtes invité, connectez-vous en tant qu’administrateur Azure AD.</span><span class="sxs-lookup"><span data-stu-id="be480-169">When you're prompted, sign in as the Azure AD administrator.</span></span>

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a><span data-ttu-id="be480-170">Créer des ressources Azure</span><span class="sxs-lookup"><span data-stu-id="be480-170">Create Azure resources</span></span>

> [!NOTE]
> <span data-ttu-id="be480-171">Assurez-vous de créer les ressources suivantes dans la même instance Azure AD qui contient l’environnement Dataverse.</span><span class="sxs-lookup"><span data-stu-id="be480-171">Make sure that you create the following resources in the same Azure AD instance that the Dataverse environment is in.</span></span> <span data-ttu-id="be480-172">Vous ne pouvez pas utiliser les ressources d’une autre instance Azure AD.</span><span class="sxs-lookup"><span data-stu-id="be480-172">You can't use resources from a different Azure AD instance.</span></span>

1. <span data-ttu-id="be480-173">Création d’un compte de stockage :</span><span class="sxs-lookup"><span data-stu-id="be480-173">Create a storage account:</span></span>

    1. <span data-ttu-id="be480-174">Dans le [portail Azure](https://portal.azure.com), créez un compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="be480-174">In the [Azure portal](https://portal.azure.com), create a storage account.</span></span>
    2. <span data-ttu-id="be480-175">Dans la boîte de dialogue **Créer un compte de stockage**, définissez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="be480-175">In the **Create storage account** dialog box, set the following fields:</span></span>

        - <span data-ttu-id="be480-176">**Emplacement** : sélectionnez le centre de données où se trouve votre environnement.</span><span class="sxs-lookup"><span data-stu-id="be480-176">**Location** – Select the data center where your environment is located.</span></span>
        - <span data-ttu-id="be480-177">**Performance** : nous vous recommandons de sélectionner **Standard**.</span><span class="sxs-lookup"><span data-stu-id="be480-177">**Performance** – We recommend that you select **Standard**.</span></span>
        - <span data-ttu-id="be480-178">**Type de compte** : vous devez sélectionner **StorageV2**.</span><span class="sxs-lookup"><span data-stu-id="be480-178">**Account kind** – You must select **StorageV2**.</span></span>

    3. <span data-ttu-id="be480-179">Dans la boîte de dialogue **Options avancées**, pour l’option **Stockage Data Lake Gen2**, sélectionnez **Activer** sous la fonctionnalité **Espaces de noms hiérarchiques**.</span><span class="sxs-lookup"><span data-stu-id="be480-179">In the **Advanced options** dialog box, for the **Data Lake storage Gen2** option, select **Enable** under the **Hierarchical namespaces** feature.</span></span> <span data-ttu-id="be480-180">Si vous n’activez pas cette fonctionnalité, vous ne pouvez pas consommer les données que les applications Finance and Operations écrivent à l’aide de services tels que les flux de données Power BI.</span><span class="sxs-lookup"><span data-stu-id="be480-180">If you don't enable this feature, you can't consume data that Finance and Operations apps write by using services such as Power BI data flows.</span></span>
    4. <span data-ttu-id="be480-181">Sélectionnez **Réviser et créer**.</span><span class="sxs-lookup"><span data-stu-id="be480-181">Select **Review and create**.</span></span> <span data-ttu-id="be480-182">Une fois le déploiement terminé, la nouvelle ressource s’affiche dans le portail Azure.</span><span class="sxs-lookup"><span data-stu-id="be480-182">When the deployment is completed, the new resource is shown in the Azure portal.</span></span>
    5. <span data-ttu-id="be480-183">Accédez au compte de stockage que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="be480-183">Go to the storage account that you created.</span></span>
    6. <span data-ttu-id="be480-184">Dans le menu de gauche, sélectionnez **Clés d’accès**.</span><span class="sxs-lookup"><span data-stu-id="be480-184">On the left menu, select **Access keys**.</span></span>
    7. <span data-ttu-id="be480-185">Copiez et enregistrez le nom du compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="be480-185">Copy and save the name of the storage account.</span></span> <span data-ttu-id="be480-186">Vous devrez fournir cette valeur ultérieurement, lors de la configuration des secrets du coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="be480-186">You will have to provide this value later, when you set up key vault secrets.</span></span>

2. <span data-ttu-id="be480-187">Création d’un coffre de clés :</span><span class="sxs-lookup"><span data-stu-id="be480-187">Create a key vault:</span></span>

    1. <span data-ttu-id="be480-188">Dans le [portail Azure](https://portal.azure.com), créez un coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="be480-188">In the [Azure portal](https://portal.azure.com), create a key vault.</span></span>
    2. <span data-ttu-id="be480-189">Dans la boîte de dialogue **Créer un coffre de clés**, dans le champ **Emplacement**, sélectionnez le centre de données dans lequel se trouve votre environnement.</span><span class="sxs-lookup"><span data-stu-id="be480-189">In the **Create key vault** dialog box, in the **Location** field, select the data center where your environment is located.</span></span>
    3. <span data-ttu-id="be480-190">Une fois le coffre de clés créé, accédez à **Vue d’ensemble de Key Vault**, puis copiez et enregistrez le nom DNS.</span><span class="sxs-lookup"><span data-stu-id="be480-190">After key vault is created, go to **Key Vault Overview**, and copy and save the DNS name.</span></span> <span data-ttu-id="be480-191">Vous devrez fournir cette valeur ultérieurement, lors de la configuration du complément Data Lake.</span><span class="sxs-lookup"><span data-stu-id="be480-191">You will have to provide this value later, when you set up the Data Lake add-in.</span></span>

3. <span data-ttu-id="be480-192">Créer et enregistrer une application Azure AD :</span><span class="sxs-lookup"><span data-stu-id="be480-192">Create and register an Azure AD application:</span></span>

    1. <span data-ttu-id="be480-193">Dans le [portail Azure](https://portal.azure.com), accédez à **Azure Active Directory**, puis sélectionnez **Inscriptions d’applications**.</span><span class="sxs-lookup"><span data-stu-id="be480-193">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and then select **App registrations**.</span></span>
    2. <span data-ttu-id="be480-194">Sélectionnez **Inscription d’une nouvelle application** et définissez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="be480-194">Select **New application registration**, and set the following fields:</span></span>

        - <span data-ttu-id="be480-195">**Nom** : saisissez le nom de l’application.</span><span class="sxs-lookup"><span data-stu-id="be480-195">**Name** – Enter the name of the app.</span></span>
        - <span data-ttu-id="be480-196">**Type d’application** : sélectionnez **API Web**.</span><span class="sxs-lookup"><span data-stu-id="be480-196">**Application type** – Select **Web API**.</span></span>
        - <span data-ttu-id="be480-197">**Rediriger la configuration de l’URI** : saisissez l’URL de votre instance Dynamics 365, par exemple `https://yourdynamicsinstance.dynamics.com/auth`.</span><span class="sxs-lookup"><span data-stu-id="be480-197">**Redirect URI setup** – Enter the URL for your Dynamics 365 instance, such as `https://yourdynamicsinstance.dynamics.com/auth`.</span></span>

    3. <span data-ttu-id="be480-198">Accédez à l’application que vous venez de créer, copiez et enregistrez sa valeur **ID de l’application (client)**.</span><span class="sxs-lookup"><span data-stu-id="be480-198">Go to the app that you just created, and copy and save its **Application (client) ID** value.</span></span> <span data-ttu-id="be480-199">Vous devrez fournir cette valeur ultérieurement, lors de la configuration des secrets du coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="be480-199">You will have to provide this value later, when you set up key vault secrets.</span></span>
    4. <span data-ttu-id="be480-200">Accédez à **Autorisations API** et suivez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="be480-200">Go to **API permissions**, and follow these steps:</span></span>

        1. <span data-ttu-id="be480-201">Sélectionnez **Ajouter une autorisation**.</span><span class="sxs-lookup"><span data-stu-id="be480-201">Select **Add a permission**.</span></span>
        2. <span data-ttu-id="be480-202">Sélectionnez **Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="be480-202">Select **Azure Key vault**.</span></span>
        3. <span data-ttu-id="be480-203">Après avoir sélectionné les autorisations déléguées, sélectionnez **utilisateur\_emprunt d’identité**.</span><span class="sxs-lookup"><span data-stu-id="be480-203">After you select delegated permissions, select **user\_impersonation**.</span></span>
        4. <span data-ttu-id="be480-204">Sélectionnez **Ajouter des autorisations**.</span><span class="sxs-lookup"><span data-stu-id="be480-204">Select **Add permissions**.</span></span>

    5. <span data-ttu-id="be480-205">Dans le menu de l’application, sélectionnez **Certificats \& secrets**, puis suivez ces étapes pour créer des secrets Key Vault :</span><span class="sxs-lookup"><span data-stu-id="be480-205">On the menu for the app, select **Certificates \& secrets**, and then follow these steps to create Key Vault secrets:</span></span>

        1. <span data-ttu-id="be480-206">Sélectionnez **Nouvelle clé secrète client**.</span><span class="sxs-lookup"><span data-stu-id="be480-206">Select **New client secret**.</span></span>
        2. <span data-ttu-id="be480-207">Entrez un nom dans le champ **Description clé**.</span><span class="sxs-lookup"><span data-stu-id="be480-207">In the **Key Description** field, enter a name.</span></span>
        3. <span data-ttu-id="be480-208">Sélectionnez une durée, puis **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="be480-208">Select a duration, and then select **Add**.</span></span> <span data-ttu-id="be480-209">Un secret est généré dans le champ **Valeur**.</span><span class="sxs-lookup"><span data-stu-id="be480-209">A secret is generated in the **Value** field.</span></span>
        4. <span data-ttu-id="be480-210">Copiez et enregistrez la clé secrète client.</span><span class="sxs-lookup"><span data-stu-id="be480-210">Copy and save the client secret value.</span></span> <span data-ttu-id="be480-211">Vous devrez fournir cette valeur ultérieurement, lors de la configuration des secrets du coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="be480-211">You will have to provide this value later, when you set up key vault secrets.</span></span>

4. <span data-ttu-id="be480-212">Créer des secrets Key Vault :</span><span class="sxs-lookup"><span data-stu-id="be480-212">Create Key Vault secrets:</span></span>

    1. <span data-ttu-id="be480-213">Accédez au coffre de clés que vous avez créé précédemment et sélectionnez **Secrets**.</span><span class="sxs-lookup"><span data-stu-id="be480-213">Go to the key vault that you created earlier, and select **Secrets**.</span></span>
    2. <span data-ttu-id="be480-214">Pour chaque nom de secret dans le tableau suivant, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="be480-214">For each secret name in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="be480-215">Sélectionnez **Générer/Importer**.</span><span class="sxs-lookup"><span data-stu-id="be480-215">Select **Generate/Import**.</span></span>
        2. <span data-ttu-id="be480-216">Dans la boîte de dialogue **Créer un secret**, dans le champ **Options de téléchargement**, sélectionnez **Manuel**.</span><span class="sxs-lookup"><span data-stu-id="be480-216">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
        3. <span data-ttu-id="be480-217">Créez le nom et la valeur du secret à partir du tableau.</span><span class="sxs-lookup"><span data-stu-id="be480-217">Create the secret name and value from the table.</span></span>
        4. <span data-ttu-id="be480-218">Sélectionnez **Activé**, puis sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="be480-218">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="be480-219">Le secret est créé et ajouté à Key Vault.</span><span class="sxs-lookup"><span data-stu-id="be480-219">The secret is created and added to Key Vault.</span></span>

        | <span data-ttu-id="be480-220">Nom du secret</span><span class="sxs-lookup"><span data-stu-id="be480-220">Secret name</span></span>                       | <span data-ttu-id="be480-221">Valeur secrète</span><span class="sxs-lookup"><span data-stu-id="be480-221">Secret value</span></span>                                                                                 |
        |-----------------------------------|----------------------------------------------------------------------------------------------|
        | <span data-ttu-id="be480-222">app-id</span><span class="sxs-lookup"><span data-stu-id="be480-222">app-id</span></span>                            | <span data-ttu-id="be480-223">L’ID d’application de l’application que vous avez créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="be480-223">The app ID of the application that you created earlier.</span></span>                                      |
        | <span data-ttu-id="be480-224">app-secret</span><span class="sxs-lookup"><span data-stu-id="be480-224">app-secret</span></span>                        | <span data-ttu-id="be480-225">Le secret client que vous avez enregistré précédemment.</span><span class="sxs-lookup"><span data-stu-id="be480-225">The client secret that you saved earlier.</span></span>                                                    |
        | <span data-ttu-id="be480-226">storage-account-name</span><span class="sxs-lookup"><span data-stu-id="be480-226">storage-account-name</span></span>              | <span data-ttu-id="be480-227">Le nom du compte de stockage que vous avez créé précédemment, tel que **storageaccount1**.</span><span class="sxs-lookup"><span data-stu-id="be480-227">The name of the storage account that you created earlier, such as **storageaccount1**.</span></span>       |

5. <span data-ttu-id="be480-228">Autorisez l’application à accéder au coffre de clés :</span><span class="sxs-lookup"><span data-stu-id="be480-228">Authorize the application to access the key vault:</span></span>

    1. <span data-ttu-id="be480-229">Dans le [portail Azure](https://portal.azure.com), ouvrez le coffre de clés que vous avez créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="be480-229">In the [Azure portal](https://portal.azure.com), open the key vault that you created earlier.</span></span>
    2. <span data-ttu-id="be480-230">Sélectionnez les politiques d’accès.</span><span class="sxs-lookup"><span data-stu-id="be480-230">Select the access policies.</span></span>
    3. <span data-ttu-id="be480-231">Pour chaque application dans le tableau suivant, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="be480-231">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="be480-232">Pour créer une stratégie d’accès, sélectionnez **Ajouter une stratégie d’accès**.</span><span class="sxs-lookup"><span data-stu-id="be480-232">Select **Add Access Policy** to create an access policy.</span></span>
        2. <span data-ttu-id="be480-233">Dans le champ **Autorisations secrètes**, sélectionnez les autorisations dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="be480-233">In the **Secret permissions** field, select the permissions from the table.</span></span>
        3. <span data-ttu-id="be480-234">Dans le champ **Sélectionner le principal**, recherchez le nom d’affichage de l’application dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="be480-234">In the **Select principal** field, search for the application display name from the table.</span></span>
        4. <span data-ttu-id="be480-235">Cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="be480-235">Select **Select**.</span></span>
        5. <span data-ttu-id="be480-236">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="be480-236">Select **Add**.</span></span>
        6. <span data-ttu-id="be480-237">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="be480-237">Select **Save**.</span></span>

        | <span data-ttu-id="be480-238">Demande</span><span class="sxs-lookup"><span data-stu-id="be480-238">Application</span></span>                                              | <span data-ttu-id="be480-239">Autorisations</span><span class="sxs-lookup"><span data-stu-id="be480-239">Permissions</span></span> |
        |----------------------------------------------------------|-------------|
        | <span data-ttu-id="be480-240">Le nom d’affichage de la nouvelle application que vous avez créée</span><span class="sxs-lookup"><span data-stu-id="be480-240">The display name of the new application that you created</span></span> | <span data-ttu-id="be480-241">Obtenir, liste</span><span class="sxs-lookup"><span data-stu-id="be480-241">Get, List</span></span>   |
        | <span data-ttu-id="be480-242">**Microservices ERP Microsoft Dynamics**</span><span class="sxs-lookup"><span data-stu-id="be480-242">**Microsoft Dynamics ERP Microservices**</span></span>                 | <span data-ttu-id="be480-243">Obtenir, liste</span><span class="sxs-lookup"><span data-stu-id="be480-243">Get, List</span></span>   |

6. <span data-ttu-id="be480-244">Attribuez des rôles pour accéder au compte de stockage :</span><span class="sxs-lookup"><span data-stu-id="be480-244">Assign roles to access the storage account:</span></span>

    1. <span data-ttu-id="be480-245">Dans le [portail Azure](https://portal.azure.com), ouvrez le compte de stockage que vous avez créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="be480-245">In the [Azure portal](https://portal.azure.com), open the storage account that you created earlier.</span></span>
    2. <span data-ttu-id="be480-246">Sélectionnez **Contrôle d’accès (IAM)**, puis sélectionnez **Attributions de rôle**.</span><span class="sxs-lookup"><span data-stu-id="be480-246">Select **Access Control (IAM)**, and then select **Role Assignments**.</span></span>
    3. <span data-ttu-id="be480-247">Sélectionnez **Ajouter, Ajouter une attribution de rôle**.</span><span class="sxs-lookup"><span data-stu-id="be480-247">Select **Add, Add Role Assignment**.</span></span>
    4. <span data-ttu-id="be480-248">Pour chaque application dans le tableau suivant, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="be480-248">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="be480-249">Sélectionnez le rôle dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="be480-249">Select the role from the table.</span></span>
        2. <span data-ttu-id="be480-250">Laissez le champ **Affecter l’accès** défini sur **Utilisateur, groupe ou service principal Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="be480-250">Leave the **Assign access to** field set to **Azure AD user, group, or service principal**.</span></span>
        3. <span data-ttu-id="be480-251">Dans le champ **Sélectionner**, saisissez l’application dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="be480-251">In the **Select** field, enter the application from the table.</span></span>
        4. <span data-ttu-id="be480-252">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="be480-252">Select **Save**.</span></span>

        | <span data-ttu-id="be480-253">Demande</span><span class="sxs-lookup"><span data-stu-id="be480-253">Application</span></span>                                              | <span data-ttu-id="be480-254">Rôle</span><span class="sxs-lookup"><span data-stu-id="be480-254">Role</span></span>                        |
        |----------------------------------------------------------|-----------------------------|
        | <span data-ttu-id="be480-255">Le nom d’affichage de la nouvelle application que vous avez créée</span><span class="sxs-lookup"><span data-stu-id="be480-255">The display name of the new application that you created</span></span> | <span data-ttu-id="be480-256">Propriétaire</span><span class="sxs-lookup"><span data-stu-id="be480-256">Owner</span></span>                       |
        | <span data-ttu-id="be480-257">Le nom d’affichage de la nouvelle application que vous avez créée</span><span class="sxs-lookup"><span data-stu-id="be480-257">The display name of the new application that you created</span></span> | <span data-ttu-id="be480-258">Contributeur</span><span class="sxs-lookup"><span data-stu-id="be480-258">Contributor</span></span>                 |
        | <span data-ttu-id="be480-259">Le nom d’affichage de la nouvelle application que vous avez créée</span><span class="sxs-lookup"><span data-stu-id="be480-259">The display name of the new application that you created</span></span> | <span data-ttu-id="be480-260">Contributeur de compte de stockage</span><span class="sxs-lookup"><span data-stu-id="be480-260">Storage Account Contributor</span></span> |
        | <span data-ttu-id="be480-261">Le nom d’affichage de la nouvelle application que vous avez créée</span><span class="sxs-lookup"><span data-stu-id="be480-261">The display name of the new application that you created</span></span> | <span data-ttu-id="be480-262">Propriétaire des données de l’objet blob de stockage</span><span class="sxs-lookup"><span data-stu-id="be480-262">Storage Blob Data Owner</span></span>     |
        | <span data-ttu-id="be480-263">**Service d’autorisation AI Builder**</span><span class="sxs-lookup"><span data-stu-id="be480-263">**AI Builder Authorization Service**</span></span>                     | <span data-ttu-id="be480-264">Lecteur de données de l’objet blob de stockage</span><span class="sxs-lookup"><span data-stu-id="be480-264">Storage Blob Data Reader</span></span>    |

# <a name="azure-cli"></a>[<span data-ttu-id="be480-265">Service de contrôle d’accès Azure (CLI)</span><span class="sxs-lookup"><span data-stu-id="be480-265">Azure CLI</span></span>](#tab/azure-azure-cli)

```
function New-FinanceDataLakeAzureResources {
    Assert-ScriptSetup

    $ClientAppName = 'Finance Data Lake Application'
    $DefaultSecretExpiryInYear = 1
    $MicrosoftDynamicsERPMicroservicesAppId = '0cdb527f-a8d1-4bf8-9436-b352c68682b2'
    $MicrosoftDynamicsERPMicroservicesCDSAppId = '703e2651-d3fc-48f5-942c-74274233dba8'
    $AIBuilderAuthorizationServiceAppId = 'ad40333e-9910-4b61-b281-e3aeeb8c3ef3'
    $KeyVaultServicePrincipalAppId = 'cfa8b339-82a2-471a-a3c9-0fc0be7a4093'
    $GraphServicePrincipalAppId = '00000003-0000-0000-c000-000000000000'

    Import-Module AzureAD.Standard.Preview
    $connectAzureADParameters = @{ 'Identity' = $true; 'TenantId' = $env:ACC_TID }
    $azContext = AzureAD.Standard.Preview\Connect-AzureAD @connectAzureADParameters
    $userContext = ConvertFrom-Json ((az ad signed-in-user show) -join '')
    $user = Get-AzureADUser -Filter ("UserPrincipalName eq '" + $userContext.UserPrincipalName + "'")

    Set-AzureSubscription
    
    $resourceGroup = $null
    $ResourceGroupName = 'D365FinanceInsightsDataLake'
    $ResourceGroupNameSuffix = ''
    $FullResourceGroupName = ''
    Write-Output ("The default Azure Resource Group name is '{0}'" -f $ResourceGroupName)
    while (-not ($resourceGroup)) {
        $ResourceGroupNameSuffix = (Read-Host -Prompt "Enter optional Azure Resource Group name suffix: (leave blank for no suffix)")
        if ([string]::IsNullOrWhitespace($ResourceGroupNameSuffix))
        {
            $FullResourceGroupName = $ResourceGroupName
        }
        else
        {
            if ($ResourceGroupNameSuffix -notmatch "^[A-Za-z0-9]+$") {
                Write-Warning "The Azure Resource Group name suffix can only include alphanumeric characters."
                continue
            }

            if ($ResourceGroupNameSuffix.Length -gt 60) {
                Write-Warning "The Azure Resource Group name suffix cannot be longer than 60 characters."
                continue
            }

            $FullResourceGroupName = $ResourceGroupName + $ResourceGroupNameSuffix
        }
        
        $resourceGroup = Get-AzResourceGroup -Name $FullResourceGroupName -ErrorAction SilentlyContinue

        if (-not ($resourceGroup)) {
            Write-Output ("Your new Azure Resource Group name is '{0}'" -f $FullResourceGroupName)
            $resourceLocation = ''
            $azResourceLocations = (Get-AzLocation | Select-Object Location).Location
            while ([string]::IsNullOrWhitespace($resourceLocation) -or (-not ($resourceLocation -in $azResourceLocations))) {
                $resourceLocation = (Read-Host -Prompt "Enter the location in which to create the Azure Resource Group: ('help' to see values)")
                if ($resourceLocation -eq 'help') {
                    Write-Output ("List of available regions is '{0}'" -f ($azResourceLocations -join ','))
                }
                elseif ([string]::IsNullOrWhitespace($resourceLocation) -or (-not ($resourceLocation -in $azResourceLocations)))
                {
                    Write-Warning ("The provided location is not available for resource group. List of available regions is '{0}'" -f ($azResourceLocations -join ','))
                }
            }
            $resourceGroup = New-AzResourceGroup -Name $FullResourceGroupName -Location $resourceLocation
            Write-Output ("Created Azure Resource Group '{0}'" -f $resourceGroup.ResourceGroupName)
        }
        else {
            Write-Output ("Found Azure Resource Group '{0}'" -f ($resourceGroup.ResourceGroupName))
        }
    }

    Write-Output '================================================================================='
    $MicrosoftDynamicsERPMicroservicesAppObjectId = Create-ADServicePrincipal -AppId $MicrosoftDynamicsERPMicroservicesAppId
    Create-ADServicePrincipal -AppId $MicrosoftDynamicsERPMicroservicesCDSAppId | Out-Null
    $aibuilderAuthorizationServiceObjectId = Create-ADServicePrincipal -AppId $AIBuilderAuthorizationServiceAppId
    Write-Output ('=================================================================================')

    $clientAppSPN = Get-AzureADServicePrincipal -Filter ("DisplayName eq '" + $ClientAppName + "'")
    if (-not ($clientAppSPN)) {
        $keyVaultPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $KeyVaultServicePrincipalAppId + "'")
        if (-not $keyVaultPrincipal)
        {
            New-AzureADServicePrincipal -AppId $KeyVaultServicePrincipalAppId | Format-Table -AutoSize
            Write-Output "Added Key Vault principal to AAD"
            $keyVaultPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $KeyVaultServicePrincipalAppId + "'")
        }
        $keyVaultAccess = New-Object -TypeName "Microsoft.Open.AzureAD.Model.RequiredResourceAccess"
        $keyVaultAccess.ResourceAppId = $keyVaultPrincipal.AppId
        $keyVaultAccess.ResourceAccess = (New-Object -TypeName "microsoft.open.azuread.model.resourceAccess" -ArgumentList $keyVaultPrincipal.Oauth2Permissions.Id, "Scope")

        $graphPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $GraphServicePrincipalAppId + "'")
        if (-not $graphPrincipal)
        {
            New-AzureADServicePrincipal -AppId $GraphServicePrincipalAppId | Format-Table -AutoSize
            Write-Output "Added Graph principal to AAD"
            $graphPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $GraphServicePrincipalAppId + "'")
        }
        $userRead = $graphPrincipal.Oauth2Permissions | Where-Object { $_.Type -eq "User" -and $_.Value -eq "User.Read" }
        $graphAccess = New-Object -TypeName "Microsoft.Open.AzureAD.Model.RequiredResourceAccess"
        $graphAccess.ResourceAppId = $graphPrincipal.AppId
        $graphAccess.ResourceAccess = (New-Object -TypeName "microsoft.open.azuread.model.resourceAccess" -ArgumentList $userRead.Id, "Scope")

        $clientApp = New-AzureADApplication -DisplayName $ClientAppName -RequiredResourceAccess @($keyVaultAccess, $graphAccess)
        $clientAppSPN = New-AzureADServicePrincipal -AppId $clientApp.AppId -Tags @($ClientAppName)
        $clientAppId = $clientApp.AppId
        Write-Output ('Created App Registration "' + $ClientAppName + '" with Application Id: ' + $clientAppId)
    }
    else {
        $clientApp = Get-AzureADApplication -Filter ("DisplayName eq '" + $ClientAppName + "'")
        $clientAppId = $clientApp.AppId
        Write-Output ('Found App Registration "' + $ClientAppName + '" with Application Id: ' + $clientAppId)
    }
            
    $clientAppSecretCredential = New-AzureADApplicationPasswordCredential -ObjectId $clientApp.ObjectId -CustomKeyIdentifier "ClientAppAccessKey" -EndDate (get-date).AddYears($DefaultSecretExpiryInYear)
    $ClientAppSecret = $clientAppSecretCredential.Value
    $clientAppSpId = $clientAppSPN.ObjectId

    Write-Output ('Generated application secret: ' + $ClientAppSecret)
    Write-Output '================================================================================='

    $templateObject = ConvertFrom-Json $azureTemplate -AsHashtable
    $templateObject.{$schema} = "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#"
    Write-Output 'Provisioning Azure resources. This may take a few minutes.'
    try {
        $deployment = New-AzResourceGroupDeployment -ResourceGroupName $FullResourceGroupName -TemplateObject $templateObject -aibuilderAppObjectId $aibuilderAuthorizationServiceObjectId -clientAppId $clientAppId -clientAppSecret $ClientAppSecret -clientAppSpObjectId  $clientAppSpId -microserviceSpObjectId $MicrosoftDynamicsERPMicroservicesAppObjectId -userSpObjectId $user.ObjectId -Force -ErrorAction Stop
    }
    catch {
        $ErrorMessage = $_.Exception.Message
        if ($ErrorMessage.Contains("not allowed to be updated"))
        {
            Write-Error ($ErrorMessage)
            Write-Warning "Some items in the existing resource group $FullResourceGroupName could not be updated. To resolve the issue, remove the existing resource group $FullResourceGroupName and run the script again."
        }
        else {
            throw
        }

    }
    if ($deployment.ProvisioningState -eq 'Succeeded') {
        Write-Output "Successfully deployed the following resources to Azure:"
        Write-Output ("  Key Vault:                         " + $deployment.Outputs.keyVaultName.Value)
        Write-Output ("  Storage Account:                   " + $deployment.Outputs.storageAccountName.Value)
        
        $keyVault = Get-AzKeyVault -VaultName $deployment.Outputs.keyVaultName.Value
        $tenantId = (Get-AzContext).Tenant.Id

        Write-Output "Values for LCS Data Lake Add-In:"
        Write-Output ("  Tenant ID:                         " + $tenantId)
        Write-Output ("  DNS Name:                          " + $keyVault.VaultUri)
        Write-Output "  Storage account secret name:       storage-account-name"
        Write-Output "  Application ID secret name:        app-id"
        Write-Output "  Application Secret secret name:    app-secret"
        Write-Warning "Copy this information for the LCS Add-in for easy access. Azure Cloud Shell will eventually time out and close."

        Write-Output '================================================================================='
        Write-Output "Values for System parameters > Data connections:"
        Write-Output ("  Application ID:                    " + $clientAppId)
        Write-Output ("  Application Secret:                " + $ClientAppSecret)
        Write-Output ("  DNS name:                          " + $keyVault.VaultUri)
        Write-Output "  Secret name:                       storage-account-connection-string"
        Write-Warning "Copy this information for the System parameters for easy access. Azure Cloud Shell will eventually time out and close."
    }
    else {
        Write-Output ("Provisioning Azure resources failed with the following state: " + $deployment.ProvisioningState)
        Write-Output ("Some of the resources may have been created in resource group: " + $FullResourceGroupName)
    }
}

function Assert-ScriptSetup {
    if ($PSVersionTable.PSEdition -ne 'Core' -or -not $env:ACC_TID) { 
        throw "This script needs to be uploaded and run from Azure Cloud Shell (PowerShell)." 
    }
    
    if ((Get-AzContext) -eq $null -and (Connect-AzAccount) -eq $null) {
        throw 'Unable to connect to Azure account.'
    }
}

function Set-AzureSubscription {
    $azSubscription = $null
    while (-not ($azSubscription)) {
        $subscriptionId = (Read-Host -Prompt "Enter the Azure Subscription ID: (leave blank for default)")
        if ([string]::IsNullOrWhitespace($subscriptionId)){
            break
        }
        elseif (-not [guid]::TryParse($subscriptionId, $([ref][guid]::Empty))) {
                Write-Warning "Azure Subscription ID must be a valid GUID."
                continue
        }

        $azSubscription = Select-AzSubscription -SubscriptionId $subscriptionId
    }
}

function Create-ADServicePrincipal {
    param (
        [string] $AppId
    )

    $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $AppId + "'")
    if (-not $service) {
        New-AzureADServicePrincipal -AppId $AppId | Out-Null
        $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $AppId + "'")
        Write-Host ("Added AAD Enterprise Application {0} with Application ID {1}" -f $service.DisplayName,$AppId)
    }
    else {
        Write-Host ("Found AAD Enterprise Application {0} with Application ID {1}" -f $service.DisplayName,$AppId)
    }

    return $service.ObjectId
}

$azureTemplate = @"
{
    "contentVersion": "1.0.0.0",
    "parameters": {
      "aibuilderAppObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of the AI Builder application."
        }
      },
      "clientAppId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the application ID of client application."
        }
      },
      "clientAppSecret": {
        "type": "String",
        "metadata": {
          "description": "Specifies the Azure App ID client secret to in azure key vault."
        }
      },
      "clientAppSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of a client application service principal."
        }
      },
      "userSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of tenant admin service principal."
        }
      },
      "microserviceSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of Microsoft Dynamics ERP Microservices service principal."
        }
      },
      "storageAccountType": {
        "type": "string",
        "defaultValue": "Standard_LRS",
        "allowedValues": [
          "Standard_LRS",
          "Standard_GRS",
          "Standard_ZRS",
          "Premium_LRS"
        ],
        "metadata": {
          "description": "Storage Account type"
        }
      }
    },
    "variables": {
      "storageAccountApiVersion": "2019-06-01",
      "keyVaultApiVersion": "2018-02-14",
      "secretsPermissions": [
        "list",
        "get"
      ],
      "location": "[resourceGroup().location]",
      "storageAccountName": "[concat('store', uniquestring(resourceGroup().id))]",
      "keyVaultName": "[concat('keyvault', uniquestring(resourceGroup().id))]",
      "owner": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '8e3af657-a8ff-443c-a75c-2fe8c4bcb635')]",
      "contributor": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', 'b24988ac-6180-42a0-ab88-20f7382dd24c')]",
      "storageAccountContributor": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '17d1049b-9a84-46fb-8f53-869881c3d3ab')]",
      "storageBlobDataOwner": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', 'b7e6dc6d-f1e8-4753-8033-0f276bb0955b')]",
      "storageBlobDataReader": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '2a2b9908-6ea1-4ae2-8e65-a410df84e7d1')]"
    },
    "resources": [
      {
        "type": "Microsoft.Storage/storageAccounts",
        "apiVersion": "[variables('storageAccountApiVersion')]",
        "name": "[variables('storageAccountName')]",
        "location": "[variables('location')]",
        "sku": {
          "name": "[parameters('storageAccountType')]"
        },
        "kind": "StorageV2",
        "properties": {
          "accessTier": "Hot",
          "supportsHttpsTrafficOnly": true,
          "isHnsEnabled": true
        },
        "resources": [
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'1')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('owner')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'2')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('contributor')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'3')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageAccountContributor')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'4')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageBlobDataOwner')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'5')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageBlobDataReader')]",
              "principalId": "[parameters('aibuilderAppObjectId')]"
            }
          }
        ]
      },
      {
        "type": "Microsoft.KeyVault/vaults",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "name": "[variables('keyVaultName')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.Storage/storageAccounts', variables('storageAccountName'))]"
        ],
        "tags": {
        },
        "properties": {
          "enabledForDeployment": false,
          "enabledForTemplateDeployment": false,
          "enabledForDiskEncryption": false,
          "enableRbacAuthorization": false,
          "accessPolicies": [
            {
              "objectId": "[parameters('clientAppSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            },
            {
              "objectId": "[parameters('microserviceSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            },
            {
              "objectId": "[parameters('userSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            }
          ],
          "tenantId": "[subscription().tenantId]",
          "sku": {
            "name": "Standard",
            "family": "A"
          },
          "enableSoftDelete": false,
          "networkAcls": {
            "defaultAction": "Allow",
            "bypass": "AzureServices"
          }
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'app-id')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[parameters('clientAppId')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'app-secret')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[parameters('clientAppSecret')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'storage-account-name')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[variables('storageAccountName')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'storage-account-connection-string')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[concat('DefaultEndpointsProtocol=https;AccountName=', variables('storageAccountName'), ';AccountKey=', listKeys(resourceId('Microsoft.Storage/storageAccounts', variables('storageAccountName')), variables('storageAccountApiVersion')).keys[0].value, ';EndpointSuffix=core.windows.net')]"
        }
      }
    ],
    "outputs": {
      "storageAccountName": {
        "type": "string",
        "value": "[variables('storageAccountName')]"
      },
      "keyVaultName": {
        "type": "string",
        "value": "[variables('keyVaultName')]"
      }
    }
  }
"@

try {
  Start-Transcript -path (Join-Path $HOME Provision-FinInsights-Azure.log)
  New-FinanceDataLakeAzureResources
}
catch {
  Write-Error $_.Exception.Message

  if ($PSItem.Exception.StackTrace -ne $null)
  {
      Write-Warning $_.Exception.StackTrace
  }

  $inner = $_.Exception.InnerException
  while ($null -ne $inner) {
    Write-Output 'Inner Exception:'
    Write-Error $_.Exception.Message
    Write-Warning $_.Exception.StackTrace
    $inner = $inner.InnerException
  }
}
finally {
  Stop-Transcript
}
```
---

## <a name="configure-the-export-to-data-lake-add-in"></a><span data-ttu-id="be480-266">Configurer le complément Exporter vers Data Lake</span><span class="sxs-lookup"><span data-stu-id="be480-266">Configure the Export to Data Lake add-in</span></span>

<span data-ttu-id="be480-267">Suivez ces étapes pour utiliser LCS pour ajouter le complément Exporter vers Data Lake à l’environnement.</span><span class="sxs-lookup"><span data-stu-id="be480-267">Follow these steps to use LCS to add the Export to Data Lake add-in to the environment.</span></span>

1. <span data-ttu-id="be480-268">Connectez-vous à LCS, puis, sous le nom de l’environnement sur le côté droit de la page, sélectionnez **Tous les détails**.</span><span class="sxs-lookup"><span data-stu-id="be480-268">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="be480-269">Dans la section **Compléments de l’environnement**, sélectionnez **Installer un nouveau complément**.</span><span class="sxs-lookup"><span data-stu-id="be480-269">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="be480-270">Sélectionnez le complément **Exporter vers Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="be480-270">Select the **Export to Data Lake** add-in.</span></span>
4. <span data-ttu-id="be480-271">Saisissez les valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="be480-271">Enter the following values.</span></span>

    | <span data-ttu-id="be480-272">Valeur</span><span class="sxs-lookup"><span data-stu-id="be480-272">Value</span></span>                                                              | <span data-ttu-id="be480-273">Description</span><span class="sxs-lookup"><span data-stu-id="be480-273">Description</span></span> |
    |--------------------------------------------------------------------|-------------|
    | <span data-ttu-id="be480-274">ID de locataire de l’abonnement Azure où se trouve le coffre de clés</span><span class="sxs-lookup"><span data-stu-id="be480-274">Tenant ID of the Azure Subscription where the Key Vault is located</span></span> | <span data-ttu-id="be480-275">ID de locataire où se trouvent le compte de stockage, les applications et les coffres de clés.</span><span class="sxs-lookup"><span data-stu-id="be480-275">The tenant ID where the storage account, apps, and key vaults are located.</span></span> <span data-ttu-id="be480-276">Pour obtenir cette valeur, ouvrez le [Portail Azure](https://portal.azure.com), accédez à **Azure Active Directory**, et copiez la valeur **ID du locataire**.</span><span class="sxs-lookup"><span data-stu-id="be480-276">To obtain this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="be480-277">Fournir le nom DNS de votre Key Vault</span><span class="sxs-lookup"><span data-stu-id="be480-277">Provide the DNS name of your Key Vault</span></span>                             | <span data-ttu-id="be480-278">Nom DNS du coffre de clés, tel que `https://customkeyvault.vault.azure.net/`.</span><span class="sxs-lookup"><span data-stu-id="be480-278">The DNS name of the key vault, such as `https://customkeyvault.vault.azure.net/`.</span></span> |
    | <span data-ttu-id="be480-279">Fournir le secret contenant le nom du compte de stockage</span><span class="sxs-lookup"><span data-stu-id="be480-279">Provide the secret that contains the name of the storage account</span></span>   | <span data-ttu-id="be480-280">**storage-account-name**</span><span class="sxs-lookup"><span data-stu-id="be480-280">**storage-account-name**</span></span> |
    | <span data-ttu-id="be480-281">Nom secret de l’ID d’application à utiliser pour accéder à Data Lake</span><span class="sxs-lookup"><span data-stu-id="be480-281">Secret Name for App ID to be used for accessing Data Lake</span></span>          | <span data-ttu-id="be480-282">**app-id**</span><span class="sxs-lookup"><span data-stu-id="be480-282">**app-id**</span></span> |
    | <span data-ttu-id="be480-283">Nom secret du secret client de l’application</span><span class="sxs-lookup"><span data-stu-id="be480-283">Secret name for App client secret</span></span>                                  | <span data-ttu-id="be480-284">**app-secret**</span><span class="sxs-lookup"><span data-stu-id="be480-284">**app-secret**</span></span> |

5. <span data-ttu-id="be480-285">Acceptez les conditions, puis sélectionnez **Installer**.</span><span class="sxs-lookup"><span data-stu-id="be480-285">Agree to the terms, and then select **Install**.</span></span>

<span data-ttu-id="be480-286">Le complément sera installé dans quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="be480-286">The add-in will be installed within a few minutes.</span></span>

## <a name="configure-the-finance-insights-add-in"></a><span data-ttu-id="be480-287">Configurer le complément Informations financières</span><span class="sxs-lookup"><span data-stu-id="be480-287">Configure the Finance insights add-in</span></span>

> [!NOTE]
> <span data-ttu-id="be480-288">Si vous avez déjà installé le complément Obtenir des informations, désinstallez-le avant de réaliser la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="be480-288">If you previously installed the Get insights add-in, uninstall it before you complete the following procedure.</span></span>

<span data-ttu-id="be480-289">Suivez ces étapes pour installer le complément Informations financières.</span><span class="sxs-lookup"><span data-stu-id="be480-289">Follow these steps to install the Finance insights add-in.</span></span>

1. <span data-ttu-id="be480-290">Connectez-vous à LCS, puis, sous le nom de l’environnement sur le côté droit de la page, sélectionnez **Tous les détails**.</span><span class="sxs-lookup"><span data-stu-id="be480-290">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="be480-291">Dans la section **Compléments de l’environnement**, sélectionnez **Installer un nouveau complément**.</span><span class="sxs-lookup"><span data-stu-id="be480-291">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="be480-292">Sélectionnez le complément **Informations financières**.</span><span class="sxs-lookup"><span data-stu-id="be480-292">Select the **Finance insights** add-in.</span></span>
4. <span data-ttu-id="be480-293">Acceptez les conditions, puis sélectionnez **Installer**.</span><span class="sxs-lookup"><span data-stu-id="be480-293">Agree to the terms, and then select **Install**.</span></span>

## <a name="feedback-and-support"></a><span data-ttu-id="be480-294">Commentaires et support</span><span class="sxs-lookup"><span data-stu-id="be480-294">Feedback and support</span></span>

<span data-ttu-id="be480-295">Si vous souhaitez fournir des commentaires ou si vous avez besoin d’aide, veuillez envoyer un e-mail à [Informations financières (version préliminaire)](mailto:fiap@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="be480-295">If you're interested in providing feedback, or if you require support, send an email to [Finance insights (Preview)](mailto:fiap@microsoft.com).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
