---
title: Configuration de Finance Insights (version préliminaire)
description: Cette rubrique explique les étapes de configuration qui permettront à votre système d’utiliser les fonctionnalités disponibles dans Finance Insights.
author: ShivamPandey-msft
ms.date: 11/25/2020
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
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 60e4d69157d7b73bd9e47310adae320687230080
ms.sourcegitcommit: a202bf67c3c2c054e2a47cb7b3145cb7c0ee635e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/25/2021
ms.locfileid: "5941224"
---
# <a name="configuration-for-finance-insights-preview"></a><span data-ttu-id="5866d-103">Configuration de Finance Insights (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="5866d-103">Configuration for Finance insights (preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="5866d-104">Finance Insights combine les fonctionnalités de Microsoft Dynamics 365 Finance avec Microsoft Dataverse, Azure et AI Builder pour fournir de puissants outils de prévision à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="5866d-104">Finance insights combines functionality from Microsoft Dynamics 365 Finance with Microsoft Dataverse, Azure, and AI Builder to provide powerful forecasting tools for your organization.</span></span> <span data-ttu-id="5866d-105">Cette rubrique explique les étapes de configuration qui permettront à votre système d’utiliser les fonctionnalités disponibles dans Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="5866d-105">This topic explains the configuration steps that will enable your system to use the capabilities that are available in Finance insights.</span></span>

## <a name="deploy-dynamics-365-finance"></a><span data-ttu-id="5866d-106">Déployer Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="5866d-106">Deploy Dynamics 365 Finance</span></span>

<span data-ttu-id="5866d-107">Déployez les environnements comme suit.</span><span class="sxs-lookup"><span data-stu-id="5866d-107">Deploy the environments by following these steps.</span></span>

1. <span data-ttu-id="5866d-108">Dans Microsoft Dynamics Lifecycle Services (LCS), créez ou mettez à jour un environnement Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="5866d-108">In Microsoft Dynamics Lifecycle Services (LCS), create or update a Dynamics 365 Finance environment.</span></span> <span data-ttu-id="5866d-109">L’environnement nécessite la version d’application 10.0.11/Platform update 35 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="5866d-109">The environment requires app version 10.0.11/Platform update 35 or later.</span></span>
2. <span data-ttu-id="5866d-110">L’environnement doit être un environnement haute disponibilité (HA) dans Sandbox.</span><span class="sxs-lookup"><span data-stu-id="5866d-110">The environment must be a high-availability (HA) environment in Sandbox.</span></span> <span data-ttu-id="5866d-111">(Ce type d’environnement est également appelé environnement de niveau 2.) Pour plus d’informations, voir [Planification de l’environnement](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="5866d-111">(This type of environment is also known as a Tier-2 environment.) For more information, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
3. <span data-ttu-id="5866d-112">Si vous utilisez des données de démonstration Contoso, vous aurez besoin d’exemples de données supplémentaires pour utiliser les fonctionnalités de prévisions de paiement client, de prévisions de flux de trésorerie et de prévisions budgétaires.</span><span class="sxs-lookup"><span data-stu-id="5866d-112">If you're using Contoso demo data, you will require additional sample data to use the Customer payment predictions, Cash flow forecasts, and Budget forecasts features.</span></span> 

## <a name="configure-dataverse"></a><span data-ttu-id="5866d-113">Configurer Dataverse</span><span class="sxs-lookup"><span data-stu-id="5866d-113">Configure Dataverse</span></span>

<span data-ttu-id="5866d-114">Utilisez les étapes suivantes pour configurer Dataverse for Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="5866d-114">Use the following steps to configure Dataverse for Finance insights.</span></span>

1. <span data-ttu-id="5866d-115">Ouvrez la page d'environnement dans LCS et vérifiez que la section **Intégration Power Platform** est déjà configurée.</span><span class="sxs-lookup"><span data-stu-id="5866d-115">Open the environment page in LCS and verify that the **Power Platform Integration** section is already setup.</span></span>
    1. <span data-ttu-id="5866d-116">Si elle est déjà configurée, le nom d'environnement Dataverse lié à l'environnement Dynamics 365 Finance doit être répertorié.</span><span class="sxs-lookup"><span data-stu-id="5866d-116">If it is already set up, the Dataverse environment name linked to the Dynamics 365 Finance Environment should be listed.</span></span> <span data-ttu-id="5866d-117">Copiez le nom de l'environnement Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5866d-117">Copy the Dataverse environment name.</span></span>
    2. <span data-ttu-id="5866d-118">Si elle n'est pas configurée, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5866d-118">If it is not set up, follow these steps:</span></span>
        1. <span data-ttu-id="5866d-119">Sélectionnez le bouton **Installer** dans la section Intégration Power Platform.</span><span class="sxs-lookup"><span data-stu-id="5866d-119">Select the **Setup** button in the Power Platform Integration section.</span></span> <span data-ttu-id="5866d-120">La configuration de l'environnement peut prendre jusqu'à une heure.</span><span class="sxs-lookup"><span data-stu-id="5866d-120">It may take up to an hour for the environment to be set up.</span></span>
        2. <span data-ttu-id="5866d-121">Si l'environnement Dataverse est correctement configuré, le nom de l'environnement Dataverse lié à l'environnement Dynamics 365 Finance devrait figurer dans la liste.</span><span class="sxs-lookup"><span data-stu-id="5866d-121">If the Dataverse environment is successfully set up, the Dataverse environment name linked to the Dynamics 365 Finance Environment should be listed.</span></span> <span data-ttu-id="5866d-122">Copiez le nom de l'environnement Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5866d-122">Copy the Dataverse environment name.</span></span>
> [!NOTE]
> <span data-ttu-id="5866d-123">Après avoir terminé la configuration de l'environnement, ne sélectionnez **PAS** le bouton **Lien vers CDS for Apps**.</span><span class="sxs-lookup"><span data-stu-id="5866d-123">After completing the environment set up, **DO NOT** select the **Link to CDS for Apps** button.</span></span> <span data-ttu-id="5866d-124">Cela n'est pas nécessaire pour Finance Insights et désactiverait la possibilité de compléter les compléments d'environnement requis dans LCS.</span><span class="sxs-lookup"><span data-stu-id="5866d-124">This is not needed for Finance Insights and will disable the ability to complete the required Environment Add-ins in LCS.</span></span>

2. <span data-ttu-id="5866d-125">Ouvrez le [centre d’administration Power Platform](https://admin.powerplatform.microsoft.com/) et suivez ces étapes pour créer un environnement Dataverse dans le même client Active Directory :</span><span class="sxs-lookup"><span data-stu-id="5866d-125">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com/), and follow these steps to create a new Dataverse environment in the same Active Directory tenant:</span></span>

    1. <span data-ttu-id="5866d-126">Ouvrez la page **Environnements**.</span><span class="sxs-lookup"><span data-stu-id="5866d-126">Open the **Environments** page.</span></span>

        <span data-ttu-id="5866d-127">[![Page Environnements](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span><span class="sxs-lookup"><span data-stu-id="5866d-127">[![Environments page](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span></span>

    2. <span data-ttu-id="5866d-128">Sélectionnez l’environnement Dataverse créé ci-dessus, puis sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="5866d-128">Select the Dataverse environment created above and then select **Settings**.</span></span>
    3. <span data-ttu-id="5866d-129">Sélectionnez **Ressources \> Tous les anciens paramètres**.</span><span class="sxs-lookup"><span data-stu-id="5866d-129">Select **Resources \> All Legacy Settings**.</span></span>
    4. <span data-ttu-id="5866d-130">Dans la barre de navigation supérieure, sélectionnez **Paramètres**, puis **Personnalisations**.</span><span class="sxs-lookup"><span data-stu-id="5866d-130">On the top navigation bar, select **Settings**, and then select **Customizations**.</span></span>
    5. <span data-ttu-id="5866d-131">Sélectionnez **Ressources du développeur**.</span><span class="sxs-lookup"><span data-stu-id="5866d-131">Select **Developer Resources**.</span></span>
    6. <span data-ttu-id="5866d-132">Copiez la valeur de l'**ID d'organisation Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="5866d-132">Copy the **Dataverse organization ID** value.</span></span>
    7. <span data-ttu-id="5866d-133">Dans la barre d’adresse du navigateur, notez l’URL de l’organisation Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5866d-133">In the browser's address bar, make a note of the URL for the Dataverse organization.</span></span> <span data-ttu-id="5866d-134">Par exemple, l’URL peut être `https://org42b2b3d3.crm.dynamics.com`.</span><span class="sxs-lookup"><span data-stu-id="5866d-134">For example, the URL might be `https://org42b2b3d3.crm.dynamics.com`.</span></span>

3. <span data-ttu-id="5866d-135">Si vous prévoyez d’utiliser la fonctionnalité Prévisions de flux de trésorerie ou Prévisions budgétaires, procédez comme suit pour mettre à jour la limite d’annotation pour votre organisation à au moins 50 mégaoctets (Mo) :</span><span class="sxs-lookup"><span data-stu-id="5866d-135">If you plan to use the Cash flow forecasts or Budget forecasts feature, follow these steps to update the annotation limit for your organization to at least 50 megabytes (MB):</span></span>

    1. <span data-ttu-id="5866d-136">Ouvrez le portail [Power Apps](https://make.powerapps.com).</span><span class="sxs-lookup"><span data-stu-id="5866d-136">Open the [Power Apps portal](https://make.powerapps.com).</span></span>
    2. <span data-ttu-id="5866d-137">Sélectionnez l’environnement que vous venez de créer, puis sélectionnez **Paramètres avancés**.</span><span class="sxs-lookup"><span data-stu-id="5866d-137">Select the environment that you just created, and then select **Advanced settings**.</span></span>
    3. <span data-ttu-id="5866d-138">Sélectionnez **Paramètres \> Configuration de messagerie**.</span><span class="sxs-lookup"><span data-stu-id="5866d-138">Select **Settings \> Email Configuration**.</span></span>
    4. <span data-ttu-id="5866d-139">Changez la valeur du champ **Taille maximale du fichier** sur **51 200**.</span><span class="sxs-lookup"><span data-stu-id="5866d-139">Change the value of the **Maximum file size** field to **51,200**.</span></span> <span data-ttu-id="5866d-140">(La valeur est exprimée en kilooctets \[Ko\].)</span><span class="sxs-lookup"><span data-stu-id="5866d-140">(The value is expressed in kilobytes \[KB\].)</span></span>
    5. <span data-ttu-id="5866d-141">Cliquez sur **OK** pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="5866d-141">Select **OK** to save your changes.</span></span>

## <a name="configure-the-azure-setup"></a><span data-ttu-id="5866d-142">Configurer la configuration Azure</span><span class="sxs-lookup"><span data-stu-id="5866d-142">Configure the Azure setup</span></span>

### <a name="enter-the-dataverse-directory-id-and-the-users-azure-ad-object-id"></a><span data-ttu-id="5866d-143">Saisir l’ID de répertoire Dataverse et l’ID d’objet Azure AD de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="5866d-143">Enter the Dataverse directory ID and the user's Azure AD object ID</span></span>

1. <span data-ttu-id="5866d-144">Saisissez l’ID de répertoire Dataverse :</span><span class="sxs-lookup"><span data-stu-id="5866d-144">Enter the Dataverse directory ID:</span></span>

    1. <span data-ttu-id="5866d-145">Ouvrez le [Portail Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="5866d-145">Open the [Azure portal](https://portal.azure.com).</span></span>
    2. <span data-ttu-id="5866d-146">Connectez-vous en utilisant l’ID utilisateur qui a été utilisé pour créer l’environnement Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5866d-146">Sign in by using the user ID that was used to create the Dataverse environment.</span></span>
    3. <span data-ttu-id="5866d-147">Atteindre **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="5866d-147">Go to **Azure Active Directory**.</span></span>
    4. <span data-ttu-id="5866d-148">Copiez la valeur **ID du locataire**.</span><span class="sxs-lookup"><span data-stu-id="5866d-148">Copy the **Tenant ID** value.</span></span>

2. <span data-ttu-id="5866d-149">Saisissez l’ID d’objet Azure Active Directory (Azure AD) de l’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="5866d-149">Enter the user's Azure Active Directory (Azure AD) object ID:</span></span>

    1. <span data-ttu-id="5866d-150">Dans le [portail Azure](https://portal.azure.com), accédez à **Utilisateurs** et recherchez l’utilisateur par adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="5866d-150">In the [Azure portal](https://portal.azure.com), go to **Users**, and search for the user by email address.</span></span>
    2. <span data-ttu-id="5866d-151">Sélectionnez le nom de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5866d-151">Select the user's name.</span></span>
    3. <span data-ttu-id="5866d-152">Copiez la valeur **ID de l’objet**.</span><span class="sxs-lookup"><span data-stu-id="5866d-152">Copy the **Object ID** value.</span></span>

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a><span data-ttu-id="5866d-153">Utiliser Azure Cloud Shell pour configurer les ressources Finance Insights Data Lake</span><span class="sxs-lookup"><span data-stu-id="5866d-153">Use Azure Cloud Shell to set up Finance insights Data Lake resources</span></span>

# <a name="use-a-windows-powershell-script"></a>[<span data-ttu-id="5866d-154">Utiliser un script de configuration Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5866d-154">Use a Windows PowerShell script</span></span>](#tab/use-a-powershell-script)

<span data-ttu-id="5866d-155">Un script Windows PowerShell a été fourni, afin que vous puissiez facilement configurer les ressources Azure décrites dans [Configurer l’exportation vers Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="5866d-155">A Windows PowerShell script has been provided, so that you can easily set up the Azure resources that are described in [Configure export to Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span></span> <span data-ttu-id="5866d-156">Si vous préférez effectuer une configuration manuelle, ignorez cette procédure et continuez avec la procédure dans la section [Configuration manuelle](#manual-setup).</span><span class="sxs-lookup"><span data-stu-id="5866d-156">If you prefer to do manual setup, skip this procedure, and continue with the procedure in the [Manual setup](#manual-setup) section.</span></span>

> [!NOTE]
> <span data-ttu-id="5866d-157">Pour exécuter le script PowerShell, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5866d-157">Follow the steps below to run the PowerShell script.</span></span> <span data-ttu-id="5866d-158">L’option « Essayer » d’Azure CLI, ou l’exécution du script sur votre ordinateur risque de ne pas fonctionner.</span><span class="sxs-lookup"><span data-stu-id="5866d-158">The Azure CLI "Try it" option, or running the script on your PC may not work.</span></span>

<span data-ttu-id="5866d-159">Suivez ces étapes pour configurer Azure à l’aide du script Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5866d-159">Follow these steps to configure Azure by using the Windows PowerShell script.</span></span> <span data-ttu-id="5866d-160">Vous devez disposer des droits pour créer un groupe de ressources Azure, des ressources Azure et une application Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5866d-160">You must have rights to create an Azure resource group, Azure resources, and an Azure AD application.</span></span> <span data-ttu-id="5866d-161">Pour plus d’informations sur les autorisations requises, voir [Vérifier les autorisations Azure AD](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span><span class="sxs-lookup"><span data-stu-id="5866d-161">For information about the required permissions, see [Check Azure AD permissions](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span></span>

1. <span data-ttu-id="5866d-162">Dans le [portail Azure](https://portal.azure.com), accédez à votre abonnement Azure cible.</span><span class="sxs-lookup"><span data-stu-id="5866d-162">In the [Azure portal](https://portal.azure.com), go to your target Azure subscription.</span></span> <span data-ttu-id="5866d-163">Sélectionnez le bouton **Cloud Shell** à droite du champ **Recherche**.</span><span class="sxs-lookup"><span data-stu-id="5866d-163">Select the **Cloud Shell** button to the right of the **Search** field.</span></span>
2. <span data-ttu-id="5866d-164">Sélectionnez **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="5866d-164">Select **PowerShell**.</span></span>
3. <span data-ttu-id="5866d-165">Créez un espace de stockage, si vous êtes invité à le faire.</span><span class="sxs-lookup"><span data-stu-id="5866d-165">Create storage if you're prompted to do so.</span></span>
4. <span data-ttu-id="5866d-166">Accédez à l'onglet **Azure CLI** et sélectionnez **Copier**.</span><span class="sxs-lookup"><span data-stu-id="5866d-166">Go to the **Azure CLI** tab and select **Copy**.</span></span>  
5. <span data-ttu-id="5866d-167">Ouvrez le Bloc-notes et collez le script PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5866d-167">Open Notepad and paste the PowerShell script.</span></span> <span data-ttu-id="5866d-168">Enregistrez le fichier sous ConfigureDataLake.ps1.</span><span class="sxs-lookup"><span data-stu-id="5866d-168">Save the file as ConfigureDataLake.ps1.</span></span>
6. <span data-ttu-id="5866d-169">Téléchargez le script Windows PowerShell dans la session à l'aide de l'option de menu pour le téléchargement dans Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="5866d-169">Upload the Windows PowerShell script to the session using the menu option for upload in Cloud Shell.</span></span>
7. <span data-ttu-id="5866d-170">Exécutez le script .\ConfigureDataLake.ps1.</span><span class="sxs-lookup"><span data-stu-id="5866d-170">Run the script .\ConfigureDataLake.ps1.</span></span>
8. <span data-ttu-id="5866d-171">Suivez les invites pour exécuter le script.</span><span class="sxs-lookup"><span data-stu-id="5866d-171">Follow the prompts to run the script.</span></span>
9. <span data-ttu-id="5866d-172">Utilisez les informations de la sortie du script pour installer le complément **Exporter vers Data Lake** dans LCS.</span><span class="sxs-lookup"><span data-stu-id="5866d-172">Use the information from the script output to install the **Export to Data Lake** add-in in LCS.</span></span>
10. <span data-ttu-id="5866d-173">Utilisez les informations de la sortie du script pour activer le magasin d’entités sur la page **Connexions de données** dans Finance (**Administration du système \> Paramètres système \> Connexions des données**).</span><span class="sxs-lookup"><span data-stu-id="5866d-173">Use the information from the script output to enable the entity store on the **Data connections** page in Finance (**System administration \> System parameters \> Data connections**).</span></span>

### <a name="manual-setup"></a><span data-ttu-id="5866d-174">Configuration manuelle</span><span class="sxs-lookup"><span data-stu-id="5866d-174">Manual setup</span></span>

#### <a name="add-applications-to-the-azure-ad-tenant"></a><span data-ttu-id="5866d-175">Ajouter des applications au locataire Azure AD</span><span class="sxs-lookup"><span data-stu-id="5866d-175">Add applications to the Azure AD tenant</span></span>

1. <span data-ttu-id="5866d-176">Dans le [portail Azure](https://portal.azure.com), accédez à **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="5866d-176">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**.</span></span>
2. <span data-ttu-id="5866d-177">Sélectionnez **Gérer \> Applications de l’entreprise**.</span><span class="sxs-lookup"><span data-stu-id="5866d-177">Select **Manage \> Enterprise applications**.</span></span>
3. <span data-ttu-id="5866d-178">Recherchez les applications suivantes par ID d’application.</span><span class="sxs-lookup"><span data-stu-id="5866d-178">Search for the following applications by app ID.</span></span>

    | <span data-ttu-id="5866d-179">Demande</span><span class="sxs-lookup"><span data-stu-id="5866d-179">Application</span></span>                              | <span data-ttu-id="5866d-180">ID d’application</span><span class="sxs-lookup"><span data-stu-id="5866d-180">App ID</span></span>                               |
    |------------------------------------------|--------------------------------------|
    | <span data-ttu-id="5866d-181">Microservices ERP Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="5866d-181">Microsoft Dynamics ERP Microservices</span></span>     | <span data-ttu-id="5866d-182">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="5866d-182">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
    | <span data-ttu-id="5866d-183">CDS Microservices ERP Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="5866d-183">Microsoft Dynamics ERP Microservices CDS</span></span> | <span data-ttu-id="5866d-184">703e2651-d3fc-48f5-942c-74274233dba8</span><span class="sxs-lookup"><span data-stu-id="5866d-184">703e2651-d3fc-48f5-942c-74274233dba8</span></span> |
    | <span data-ttu-id="5866d-185">Service d’autorisation AI Builder</span><span class="sxs-lookup"><span data-stu-id="5866d-185">AI Builder Authorization Service</span></span>         | <span data-ttu-id="5866d-186">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span><span class="sxs-lookup"><span data-stu-id="5866d-186">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span></span> |

<span data-ttu-id="5866d-187">Si vous ne trouvez aucune des applications précédentes, essayez les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="5866d-187">If you can't find any of the preceding applications, try the following steps.</span></span>

1. <span data-ttu-id="5866d-188">Sur votre ordinateur local, sélectionnez le menu **Démarrer** et recherchez **powershell**.</span><span class="sxs-lookup"><span data-stu-id="5866d-188">On your local machine, select the **Start** menu, and search for **powershell**.</span></span>
2. <span data-ttu-id="5866d-189">Sélectionnez et maintenez (ou cliquez avec le bouton droit) sur **Windows PowerShell**, puis sélectionnez **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="5866d-189">Select and hold (or right-click) **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="5866d-190">Exécutez la commande suivante pour installer le module **AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="5866d-190">Run the following command to install the **AzureAD** module.</span></span>

    `Install-Module -Name AzureAD`

4. <span data-ttu-id="5866d-191">Si un fournisseur NuGet doit continuer, sélectionnez **O** pour l’installer.</span><span class="sxs-lookup"><span data-stu-id="5866d-191">If a NuGet provider is required to continue, select **Y** to install it.</span></span>
5. <span data-ttu-id="5866d-192">Si un message « Référentiel non approuvé » apparaît, sélectionnez **O** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="5866d-192">If an "Untrusted repository" message appears, select **Y** to continue.</span></span>
6. <span data-ttu-id="5866d-193">Pour chaque application à ajouter, exécutez les commandes suivantes pour ajouter l’application à Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5866d-193">For each application that must be added, run the following commands to add the application to Azure AD.</span></span> <span data-ttu-id="5866d-194">Lorsque vous y êtes invité, connectez-vous en tant qu’administrateur Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5866d-194">When you're prompted, sign in as the Azure AD administrator.</span></span>

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a><span data-ttu-id="5866d-195">Créer des ressources Azure</span><span class="sxs-lookup"><span data-stu-id="5866d-195">Create Azure resources</span></span>

> [!NOTE]
> <span data-ttu-id="5866d-196">Assurez-vous de créer les ressources suivantes dans la même instance Azure AD en tant qu’environnement Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5866d-196">Make sure that you create the following resources in the same Azure AD instance as the Dataverse environment.</span></span> <span data-ttu-id="5866d-197">Vous ne pouvez pas utiliser les ressources d’une autre instance Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5866d-197">You can't use resources from a different Azure AD instance.</span></span>

1. <span data-ttu-id="5866d-198">Création d’un compte de stockage :</span><span class="sxs-lookup"><span data-stu-id="5866d-198">Create a new storage account:</span></span>

    1. <span data-ttu-id="5866d-199">Dans le [portail Azure](https://portal.azure.com), créez un compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="5866d-199">In the [Azure portal](https://portal.azure.com), create a storage account.</span></span>
    2. <span data-ttu-id="5866d-200">Dans la boîte de dialogue **Créer un compte de stockage**, définissez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="5866d-200">In the **Create storage account** dialog box, set the following fields:</span></span>

        - <span data-ttu-id="5866d-201">**Emplacement** : sélectionnez le centre de données où se trouve votre environnement.</span><span class="sxs-lookup"><span data-stu-id="5866d-201">**Location** – Select the data center where your environment is located.</span></span>
        - <span data-ttu-id="5866d-202">**Performance** : nous vous recommandons de sélectionner **Standard**.</span><span class="sxs-lookup"><span data-stu-id="5866d-202">**Performance** – We recommend that you select **Standard**.</span></span>
        - <span data-ttu-id="5866d-203">**Type de compte** : vous devez sélectionner **StorageV2**.</span><span class="sxs-lookup"><span data-stu-id="5866d-203">**Account kind** – You must select **StorageV2**.</span></span>

    3. <span data-ttu-id="5866d-204">Dans la boîte de dialogue **Options avancées**, pour l’option **Stockage Data Lake Gen2**, sélectionnez **Activer** sous la fonctionnalité **Espaces de noms hiérarchiques**.</span><span class="sxs-lookup"><span data-stu-id="5866d-204">In the **Advanced options** dialog box, for the **Data Lake storage Gen2** option, select **Enable** under the **Hierarchical namespaces** feature.</span></span> <span data-ttu-id="5866d-205">Si vous désactivez cette fonctionnalité, vous ne pouvez pas consommer de données que les applications Finance and Operations écrivent à l’aide de services tels que les flux de données Power BI.</span><span class="sxs-lookup"><span data-stu-id="5866d-205">If you disable this feature, you can't consume data that Finance and Operations apps write by using services such as Power BI data flows.</span></span>
    4. <span data-ttu-id="5866d-206">Sélectionnez **Réviser et créer**.</span><span class="sxs-lookup"><span data-stu-id="5866d-206">Select **Review and create**.</span></span> <span data-ttu-id="5866d-207">Une fois le déploiement terminé, la nouvelle ressource sera affichée dans le portail Azure.</span><span class="sxs-lookup"><span data-stu-id="5866d-207">When the deployment is completed, the new resource will be shown in the Azure portal.</span></span>
    5. <span data-ttu-id="5866d-208">Accédez au compte de stockage que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="5866d-208">Go to the storage account that you created.</span></span>
    6. <span data-ttu-id="5866d-209">Dans le menu de gauche, sélectionnez **Clés d’accès**.</span><span class="sxs-lookup"><span data-stu-id="5866d-209">On the left menu, select **Access keys**.</span></span>
    7. <span data-ttu-id="5866d-210">Copiez et enregistrez la chaîne de connexion pour **Key1** ou **Key2**.</span><span class="sxs-lookup"><span data-stu-id="5866d-210">Copy and save the connection string for either **Key1** or **Key2**.</span></span>
    8. <span data-ttu-id="5866d-211">Copiez et enregistrez le nom du compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="5866d-211">Copy and save the storage account name.</span></span>

2. <span data-ttu-id="5866d-212">Créer un coffre de clés :</span><span class="sxs-lookup"><span data-stu-id="5866d-212">Create a new key vault:</span></span>

    1. <span data-ttu-id="5866d-213">Dans le [portail Azure](https://portal.azure.com), créez un coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="5866d-213">In the [Azure portal](https://portal.azure.com), create a key vault.</span></span>
    2. <span data-ttu-id="5866d-214">Dans la boîte de dialogue **Créer un coffre de clés**, dans le champ **Emplacement**, sélectionnez le centre de données dans lequel se trouve votre environnement.</span><span class="sxs-lookup"><span data-stu-id="5866d-214">In the **Create key vault** dialog box, in the **Location** field, select the data center where your environment is located.</span></span>
    3. <span data-ttu-id="5866d-215">Une fois le coffre de clés créé, sélectionnez-le dans la liste, puis sélectionnez **Secrets**.</span><span class="sxs-lookup"><span data-stu-id="5866d-215">After key vault is created, select it in the list, and then select **Secrets**.</span></span>
    4. <span data-ttu-id="5866d-216">Sélectionnez **Générer/Importer**.</span><span class="sxs-lookup"><span data-stu-id="5866d-216">Select **Generate/Import**.</span></span>
    5. <span data-ttu-id="5866d-217">Dans la boîte de dialogue **Créer un secret**, dans le champ **Options de téléchargement**, sélectionnez **Manuel**.</span><span class="sxs-lookup"><span data-stu-id="5866d-217">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
    6. <span data-ttu-id="5866d-218">Permet d’entrer un nom pour le secret.</span><span class="sxs-lookup"><span data-stu-id="5866d-218">Enter a name for the secret.</span></span> <span data-ttu-id="5866d-219">Notez le nom, car vous devrez le fournir ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="5866d-219">Make a note of the name, because you will have to provide it later.</span></span>
    7. <span data-ttu-id="5866d-220">Dans le champ **Valeur**, saisissez la chaîne de connexion que vous avez obtenue du compte de stockage dans la procédure précédente.</span><span class="sxs-lookup"><span data-stu-id="5866d-220">In the **Value** field, enter the connection string that you obtained from the storage account in the previous procedure.</span></span>
    8. <span data-ttu-id="5866d-221">Sélectionnez **Activé**, puis sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="5866d-221">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="5866d-222">Le secret est créé et ajouté à Key Vault.</span><span class="sxs-lookup"><span data-stu-id="5866d-222">The secret is created and added to Key Vault.</span></span>
    9. <span data-ttu-id="5866d-223">Accédez à **Vue d’ensemble de Key Vault**, et notez le nom DNS.</span><span class="sxs-lookup"><span data-stu-id="5866d-223">Go to the **Key Vault Overview**, and make a note of the DNS name.</span></span>

3. <span data-ttu-id="5866d-224">Créer et enregistrer une application Azure AD :</span><span class="sxs-lookup"><span data-stu-id="5866d-224">Create and register an Azure AD application:</span></span>

    1. <span data-ttu-id="5866d-225">Dans le [portail Azure](https://portal.azure.com), accédez à **Azure Active Directory**, puis sélectionnez **Inscriptions d’applications**.</span><span class="sxs-lookup"><span data-stu-id="5866d-225">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and then select **App registrations**.</span></span>
    2. <span data-ttu-id="5866d-226">Sélectionnez **Inscription d’une nouvelle application** et définissez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="5866d-226">Select **New application registration**, and set the following fields:</span></span>

        - <span data-ttu-id="5866d-227">**Nom** : saisissez le nom de l’application.</span><span class="sxs-lookup"><span data-stu-id="5866d-227">**Name** – Enter the name of the app.</span></span>
        - <span data-ttu-id="5866d-228">**Type d’application** : sélectionnez **API Web**.</span><span class="sxs-lookup"><span data-stu-id="5866d-228">**Application type** – Select **Web API**.</span></span>
        - <span data-ttu-id="5866d-229">**Rediriger la configuration de l’URI** : saisissez l’URL de votre instance Dynamics 365, par exemple, `https://yourdynamicsinstance.dynamics.com/auth`.</span><span class="sxs-lookup"><span data-stu-id="5866d-229">**Redirect URI setup** – Enter the URL for your Dynamics 365 instance, such as, `https://yourdynamicsinstance.dynamics.com/auth`.</span></span>

    3. <span data-ttu-id="5866d-230">Accédez à l’application que vous venez de créer, copiez et enregistrez sa valeur **ID de l’application (client)**.</span><span class="sxs-lookup"><span data-stu-id="5866d-230">Go to the app that you just created, and copy and save its **Application (client) ID** value.</span></span> <span data-ttu-id="5866d-231">Vous devrez fournir cette valeur ultérieurement, lors de la configuration du coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="5866d-231">You will have to provide this value later, when you set up the key vault.</span></span>
    4. <span data-ttu-id="5866d-232">Accédez à **Autorisations API** et suivez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="5866d-232">Go to **API permissions**, and follow these steps:</span></span>

        1. <span data-ttu-id="5866d-233">Sélectionnez **Ajouter une autorisation**.</span><span class="sxs-lookup"><span data-stu-id="5866d-233">Select **Add a permission**.</span></span>
        2. <span data-ttu-id="5866d-234">Sélectionnez **Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="5866d-234">Select **Azure Key vault**.</span></span>
        3. <span data-ttu-id="5866d-235">Après avoir sélectionné les autorisations déléguées, sélectionnez **utilisateur\_emprunt d’identité**.</span><span class="sxs-lookup"><span data-stu-id="5866d-235">After you select delegated permissions, select **user\_impersonation**.</span></span>
        4. <span data-ttu-id="5866d-236">Sélectionnez **Ajouter des autorisations**.</span><span class="sxs-lookup"><span data-stu-id="5866d-236">Select **Add permissions**.</span></span>

    5. <span data-ttu-id="5866d-237">Dans le menu de l’application, sélectionnez **Certificats \& secrets**, puis suivez ces étapes pour créer des secrets Key Vault :</span><span class="sxs-lookup"><span data-stu-id="5866d-237">On the menu for the app, select **Certificates \& secrets**, and then follow these steps to create Key Vault secrets:</span></span>

        1. <span data-ttu-id="5866d-238">Sélectionnez **Nouvelle clé secrète client**.</span><span class="sxs-lookup"><span data-stu-id="5866d-238">Select **New client secret**.</span></span>
        2. <span data-ttu-id="5866d-239">Entrez un nom dans le champ **Description clé**.</span><span class="sxs-lookup"><span data-stu-id="5866d-239">In the **Key Description** field, enter a name.</span></span>
        3. <span data-ttu-id="5866d-240">Sélectionnez une durée, puis **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="5866d-240">Select a duration, and then select **Add**.</span></span> <span data-ttu-id="5866d-241">Un secret est généré dans le champ **Valeur**.</span><span class="sxs-lookup"><span data-stu-id="5866d-241">A secret is generated in the **Value** field.</span></span>
        4. <span data-ttu-id="5866d-242">Copiez et enregistrez la valeur secrète.</span><span class="sxs-lookup"><span data-stu-id="5866d-242">Copy and save the secret value.</span></span>

4. <span data-ttu-id="5866d-243">Créer des secrets Key Vault :</span><span class="sxs-lookup"><span data-stu-id="5866d-243">Create Key Vault secrets:</span></span>

    1. <span data-ttu-id="5866d-244">Accédez au coffre de clés que vous avez créé précédemment et sélectionnez **Secrets**.</span><span class="sxs-lookup"><span data-stu-id="5866d-244">Go to the key vault that you created earlier, and select **Secrets**.</span></span>
    2. <span data-ttu-id="5866d-245">Pour chaque nom de secret dans le tableau suivant, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5866d-245">For each secret name in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="5866d-246">Sélectionnez **Générer/Importer**.</span><span class="sxs-lookup"><span data-stu-id="5866d-246">Select **Generate/Import**.</span></span>
        2. <span data-ttu-id="5866d-247">Dans la boîte de dialogue **Créer un secret**, dans le champ **Options de téléchargement**, sélectionnez **Manuel**.</span><span class="sxs-lookup"><span data-stu-id="5866d-247">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
        3. <span data-ttu-id="5866d-248">Créez le nom et la valeur du secret à partir du tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="5866d-248">Create the secret name and value from the following table.</span></span>
        4. <span data-ttu-id="5866d-249">Sélectionnez **Activé**, puis sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="5866d-249">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="5866d-250">Le secret est créé et ajouté à Key Vault.</span><span class="sxs-lookup"><span data-stu-id="5866d-250">The secret is created and added to Key Vault.</span></span>

        | <span data-ttu-id="5866d-251">Nom du secret</span><span class="sxs-lookup"><span data-stu-id="5866d-251">Secret name</span></span>                       | <span data-ttu-id="5866d-252">Valeur secrète</span><span class="sxs-lookup"><span data-stu-id="5866d-252">Secret value</span></span>                                                                                |
        |-----------------------------------|---------------------------------------------------------------------------------------------|
        | <span data-ttu-id="5866d-253">app-id</span><span class="sxs-lookup"><span data-stu-id="5866d-253">app-id</span></span>                            | <span data-ttu-id="5866d-254">L’ID d’application de l’application que vous avez créée précédemment</span><span class="sxs-lookup"><span data-stu-id="5866d-254">The app ID of the application that you created earlier</span></span>                                      |
        | <span data-ttu-id="5866d-255">app-secret</span><span class="sxs-lookup"><span data-stu-id="5866d-255">app-secret</span></span>                        | <span data-ttu-id="5866d-256">Le secret client que vous avez enregistré précédemment</span><span class="sxs-lookup"><span data-stu-id="5866d-256">The client secret that you saved earlier</span></span>                                                    |
        | <span data-ttu-id="5866d-257">storage-account-name</span><span class="sxs-lookup"><span data-stu-id="5866d-257">storage-account-name</span></span>              | <span data-ttu-id="5866d-258">Le nom du compte de stockage que vous avez créé précédemment, tel que **storageaccount1**</span><span class="sxs-lookup"><span data-stu-id="5866d-258">The name of the storage account that you created earlier, such as **storageaccount1**</span></span>       |
        | <span data-ttu-id="5866d-259">storage-account-connection-string</span><span class="sxs-lookup"><span data-stu-id="5866d-259">storage-account-connection-string</span></span> | <span data-ttu-id="5866d-260">La chaîne de connexion que vous avez copiée à partir de la page **Clés d’accès** pour le compte de stockage</span><span class="sxs-lookup"><span data-stu-id="5866d-260">The connection string that you copied from the **Access keys** page for the storage account</span></span> |

5. <span data-ttu-id="5866d-261">Autorisez l’application à accéder au coffre de clés :</span><span class="sxs-lookup"><span data-stu-id="5866d-261">Authorize the application to access the key vault:</span></span>

    1. <span data-ttu-id="5866d-262">Dans le [portail Azure](https://portal.azure.com), ouvrez le coffre de clés que vous avez créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="5866d-262">In the [Azure portal](https://portal.azure.com), open the key vault that you created earlier.</span></span>
    2. <span data-ttu-id="5866d-263">Sélectionnez les politiques d’accès.</span><span class="sxs-lookup"><span data-stu-id="5866d-263">Select the access policies.</span></span>
    3. <span data-ttu-id="5866d-264">Pour chaque application dans le tableau suivant, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5866d-264">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="5866d-265">Pour créer une stratégie d’accès, sélectionnez **Ajouter une stratégie d’accès**.</span><span class="sxs-lookup"><span data-stu-id="5866d-265">Select **Add Access Policy** to create an access policy.</span></span>
        2. <span data-ttu-id="5866d-266">Dans le champ **Autorisations secrètes**, sélectionnez les autorisations dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="5866d-266">In the **Secret permissions** field, select the permissions from the following table.</span></span>
        3. <span data-ttu-id="5866d-267">Dans le champ **Sélectionner le principal**, recherchez le nom d’affichage de l’application dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="5866d-267">In the **Select principal** field, search for the application display name from the following table.</span></span>
        4. <span data-ttu-id="5866d-268">Cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="5866d-268">Select **Select**.</span></span>
        5. <span data-ttu-id="5866d-269">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="5866d-269">Select **Add**.</span></span>
        6. <span data-ttu-id="5866d-270">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="5866d-270">Select **Save**.</span></span>

        | <span data-ttu-id="5866d-271">Demande</span><span class="sxs-lookup"><span data-stu-id="5866d-271">Application</span></span>                                              | <span data-ttu-id="5866d-272">Autorisations</span><span class="sxs-lookup"><span data-stu-id="5866d-272">Permissions</span></span> |
        |----------------------------------------------------------|-------------|
        | <span data-ttu-id="5866d-273">Le nom d’affichage de la nouvelle application que vous avez créée</span><span class="sxs-lookup"><span data-stu-id="5866d-273">The display name of the new application that you created</span></span> | <span data-ttu-id="5866d-274">Obtenir, liste</span><span class="sxs-lookup"><span data-stu-id="5866d-274">Get, List</span></span>   |
        | <span data-ttu-id="5866d-275">**Microservices ERP Microsoft Dynamics**</span><span class="sxs-lookup"><span data-stu-id="5866d-275">**Microsoft Dynamics ERP Microservices**</span></span>                 | <span data-ttu-id="5866d-276">Obtenir, liste</span><span class="sxs-lookup"><span data-stu-id="5866d-276">Get, List</span></span>   |

6. <span data-ttu-id="5866d-277">Attribuez des rôles pour accéder au compte de stockage :</span><span class="sxs-lookup"><span data-stu-id="5866d-277">Assign roles to access the storage account:</span></span>

    1. <span data-ttu-id="5866d-278">Dans le [portail Azure](https://portal.azure.com), ouvrez le compte de stockage que vous avez créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="5866d-278">In the [Azure portal](https://portal.azure.com), open the storage account that you created earlier.</span></span>
    2. <span data-ttu-id="5866d-279">Sélectionnez **Contrôle d’accès (IAM)**, puis sélectionnez **Attributions de rôle**.</span><span class="sxs-lookup"><span data-stu-id="5866d-279">Select **Access Control (IAM)**, and then select **Role Assignments**.</span></span>
    3. <span data-ttu-id="5866d-280">Sélectionnez **Ajouter, Ajouter une attribution de rôle**.</span><span class="sxs-lookup"><span data-stu-id="5866d-280">Select **Add, Add Role Assignment**.</span></span>
    4. <span data-ttu-id="5866d-281">Pour chaque application dans le tableau suivant, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5866d-281">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="5866d-282">Sélectionnez le rôle depuis la table suivante.</span><span class="sxs-lookup"><span data-stu-id="5866d-282">Select the role from the following table.</span></span>
        2. <span data-ttu-id="5866d-283">Laissez le champ **Affecter l’accès** défini sur **Utilisateur, groupe ou service principal Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="5866d-283">Leave the **Assign access to** field set to **Azure AD user, group, or service principal**.</span></span>
        3. <span data-ttu-id="5866d-284">Dans le champ **Sélectionner**, saisissez l’application dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="5866d-284">In the **Select** field, enter the application from the following table.</span></span>
        4. <span data-ttu-id="5866d-285">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="5866d-285">Select **Save**.</span></span>

        | <span data-ttu-id="5866d-286">Demande</span><span class="sxs-lookup"><span data-stu-id="5866d-286">Application</span></span>                                              | <span data-ttu-id="5866d-287">Rôle</span><span class="sxs-lookup"><span data-stu-id="5866d-287">Role</span></span>                        |
        |----------------------------------------------------------|-----------------------------|
        | <span data-ttu-id="5866d-288">Le nom d’affichage de la nouvelle application que vous avez créée</span><span class="sxs-lookup"><span data-stu-id="5866d-288">The display name of the new application that you created</span></span> | <span data-ttu-id="5866d-289">Propriétaire</span><span class="sxs-lookup"><span data-stu-id="5866d-289">Owner</span></span>                       |
        | <span data-ttu-id="5866d-290">Le nom d’affichage de la nouvelle application que vous avez créée</span><span class="sxs-lookup"><span data-stu-id="5866d-290">The display name of the new application that you created</span></span> | <span data-ttu-id="5866d-291">Contributeur</span><span class="sxs-lookup"><span data-stu-id="5866d-291">Contributor</span></span>                 |
        | <span data-ttu-id="5866d-292">Le nom d’affichage de la nouvelle application que vous avez créée</span><span class="sxs-lookup"><span data-stu-id="5866d-292">The display name of the new application that you created</span></span> | <span data-ttu-id="5866d-293">Contributeur de compte de stockage</span><span class="sxs-lookup"><span data-stu-id="5866d-293">Storage Account Contributor</span></span> |
        | <span data-ttu-id="5866d-294">Le nom d’affichage de la nouvelle application que vous avez créée</span><span class="sxs-lookup"><span data-stu-id="5866d-294">The display name of the new application that you created</span></span> | <span data-ttu-id="5866d-295">Propriétaire des données de l’objet blob de stockage</span><span class="sxs-lookup"><span data-stu-id="5866d-295">Storage Blob Data Owner</span></span>     |
        | <span data-ttu-id="5866d-296">**Service d’autorisation AI Builder**</span><span class="sxs-lookup"><span data-stu-id="5866d-296">**AI Builder Authorization Service**</span></span>                     | <span data-ttu-id="5866d-297">Lecteur de données de l’objet blob de stockage</span><span class="sxs-lookup"><span data-stu-id="5866d-297">Storage Blob Data Reader</span></span>    |

# <a name="azure-cli"></a>[<span data-ttu-id="5866d-298">Service de contrôle d’accès Azure (CLI)</span><span class="sxs-lookup"><span data-stu-id="5866d-298">Azure CLI</span></span>](#tab/azure-azure-cli)

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



## <a name="configure-the-data-lake"></a><span data-ttu-id="5866d-299">Configurer le lac de données</span><span class="sxs-lookup"><span data-stu-id="5866d-299">Configure the data lake</span></span>

<span data-ttu-id="5866d-300">Suivez ces étapes pour utiliser LCS pour ajouter le complément Azure Data Lake à l’environnement.</span><span class="sxs-lookup"><span data-stu-id="5866d-300">Follow these steps to use LCS to add the Azure Data Lake add-in to the environment.</span></span>

1. <span data-ttu-id="5866d-301">Connectez-vous à LCS, puis, sous le nom de l’environnement sur le côté droit de la page, sélectionnez **Tous les détails**.</span><span class="sxs-lookup"><span data-stu-id="5866d-301">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="5866d-302">Dans la section **Compléments de l’environnement**, sélectionnez **Installer un nouveau complément**.</span><span class="sxs-lookup"><span data-stu-id="5866d-302">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="5866d-303">Sélectionnez le complément **Exporter vers Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="5866d-303">Select the **Export to Data Lake** add-in.</span></span>
4. <span data-ttu-id="5866d-304">Saisissez les valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="5866d-304">Enter the following values.</span></span>

    | <span data-ttu-id="5866d-305">Valeur</span><span class="sxs-lookup"><span data-stu-id="5866d-305">Value</span></span>                                                              | <span data-ttu-id="5866d-306">Description</span><span class="sxs-lookup"><span data-stu-id="5866d-306">Description</span></span> |
    |--------------------------------------------------------------------|-------------|
    | <span data-ttu-id="5866d-307">ID de locataire de l’abonnement Azure où se trouve le coffre de clés</span><span class="sxs-lookup"><span data-stu-id="5866d-307">Tenant ID of the Azure Subscription where the Key Vault is located</span></span> | <span data-ttu-id="5866d-308">ID de locataire où se trouvent le compte de stockage, les applications et les coffres de clés.</span><span class="sxs-lookup"><span data-stu-id="5866d-308">The tenant ID where the storage account, apps, and key vaults are located.</span></span> <span data-ttu-id="5866d-309">Pour trouver cette valeur, ouvrez le [Portail Azure](https://portal.azure.com), accédez à **Azure Active Directory**, et copiez la valeur **ID du locataire**.</span><span class="sxs-lookup"><span data-stu-id="5866d-309">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="5866d-310">Fournir le nom DNS de votre Key Vault</span><span class="sxs-lookup"><span data-stu-id="5866d-310">Provide the DNS name of your Key Vault</span></span>                             | <span data-ttu-id="5866d-311">Nom DNS du coffre de clés, tel que `https://customkeyvault.vault.azure.net/`.</span><span class="sxs-lookup"><span data-stu-id="5866d-311">The DNS name of the key vault, such as `https://customkeyvault.vault.azure.net/`.</span></span> <span data-ttu-id="5866d-312">(Cette valeur correspond au nom DNS utilisé dans le magasin d’entités.)</span><span class="sxs-lookup"><span data-stu-id="5866d-312">(This value matches the DNS name that is used in the entity store.)</span></span> |
    | <span data-ttu-id="5866d-313">Fournir le secret contenant le nom du compte de stockage</span><span class="sxs-lookup"><span data-stu-id="5866d-313">Provide the secret that contains the name of the storage account</span></span>   | <span data-ttu-id="5866d-314">**storage-account-name**</span><span class="sxs-lookup"><span data-stu-id="5866d-314">**storage-account-name**</span></span> |
    | <span data-ttu-id="5866d-315">Nom secret de l’ID d’application à utiliser pour accéder à Data Lake</span><span class="sxs-lookup"><span data-stu-id="5866d-315">Secret Name for App ID to be used for accessing Data Lake</span></span>          | <span data-ttu-id="5866d-316">**app-id**</span><span class="sxs-lookup"><span data-stu-id="5866d-316">**app-id**</span></span> |
    | <span data-ttu-id="5866d-317">Nom secret à utiliser avec l’ID de l’application</span><span class="sxs-lookup"><span data-stu-id="5866d-317">Secret name to be used with App ID</span></span>                                 | <span data-ttu-id="5866d-318">**app-secret**</span><span class="sxs-lookup"><span data-stu-id="5866d-318">**app-secret**</span></span> |

5. <span data-ttu-id="5866d-319">Acceptez les conditions et sélectionnez **Installer**.</span><span class="sxs-lookup"><span data-stu-id="5866d-319">Agree to the terms, and select **Install**.</span></span>

<span data-ttu-id="5866d-320">Le complément sera installé dans quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="5866d-320">The add-in will be installed within a few minutes.</span></span>

## <a name="configure-ai-builder"></a><span data-ttu-id="5866d-321">Configurer AI Builder</span><span class="sxs-lookup"><span data-stu-id="5866d-321">Configure AI Builder</span></span>

1. <span data-ttu-id="5866d-322">Connectez-vous à LCS, et ouvrez la page **Détails de l’environnement**.</span><span class="sxs-lookup"><span data-stu-id="5866d-322">Sign in to LCS, and open the **Environment details** page.</span></span>
2. <span data-ttu-id="5866d-323">Faites défiler jusqu’à la section **Compléments d’environnement**.</span><span class="sxs-lookup"><span data-stu-id="5866d-323">Scroll to the **Environment add-ins** section.</span></span> <span data-ttu-id="5866d-324">Vous devriez voir les compléments qui sont déjà installés dans cet environnement.</span><span class="sxs-lookup"><span data-stu-id="5866d-324">You should see the add-ins that are already installed in this environment.</span></span> <span data-ttu-id="5866d-325">Si le complément **Exporter vers Data Lake** n’est pas parmi eux, configurez ce complément.</span><span class="sxs-lookup"><span data-stu-id="5866d-325">If the **Export to Data Lake** add-in isn't among them, configure this add-in.</span></span>
3. <span data-ttu-id="5866d-326">Sélectionnez le complément **Obtenir des informations**.</span><span class="sxs-lookup"><span data-stu-id="5866d-326">Select the **Get insights** add-in.</span></span>
4. <span data-ttu-id="5866d-327">Sur la page des détails du complément **Obtenir des informations**, entrez les valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="5866d-327">On the **Get insights** add-in details page, enter the following values.</span></span>

    | <span data-ttu-id="5866d-328">Valeur</span><span class="sxs-lookup"><span data-stu-id="5866d-328">Value</span></span>                                                    | <span data-ttu-id="5866d-329">Description</span><span class="sxs-lookup"><span data-stu-id="5866d-329">Description</span></span> |
    |----------------------------------------------------------|-------------|
    | <span data-ttu-id="5866d-330">URL de l’organisation CDS</span><span class="sxs-lookup"><span data-stu-id="5866d-330">CDS Organization URL</span></span>                                     | <span data-ttu-id="5866d-331">URL de l'organisation Dataverse copiée.</span><span class="sxs-lookup"><span data-stu-id="5866d-331">The Dataverse organization URL copied from above.</span></span> |
    | <span data-ttu-id="5866d-332">ID org. CDS</span><span class="sxs-lookup"><span data-stu-id="5866d-332">CDS Org ID</span></span>                                               | <span data-ttu-id="5866d-333">ID de l'organisation Dataverse copié.</span><span class="sxs-lookup"><span data-stu-id="5866d-333">The Dataverse organization ID copied from above.</span></span> |
5. <span data-ttu-id="5866d-334">Activez **S’agit-il de l’environnement CDS par défaut pour le locataire ?**.</span><span class="sxs-lookup"><span data-stu-id="5866d-334">Enable **Is this the default environment for you Tenant**.</span></span>
    
## <a name="configure-the-entity-store"></a><span data-ttu-id="5866d-335">Configurer le magasin des entités</span><span class="sxs-lookup"><span data-stu-id="5866d-335">Configure the entity store</span></span>

<span data-ttu-id="5866d-336">Suivez ces étapes pour configurer le magasin des entités dans votre environnement Finance.</span><span class="sxs-lookup"><span data-stu-id="5866d-336">Follow these steps to set up the entity store in your Finance environment.</span></span>

1. <span data-ttu-id="5866d-337">Accédez à **Administration système \> Paramétrage \> Paramètres système \> Connexions des données**.</span><span class="sxs-lookup"><span data-stu-id="5866d-337">Go to **System administration \> Setup \> System parameters \> Data connections**.</span></span>
2. <span data-ttu-id="5866d-338">Définissez les champs de coffre de clés suivants :</span><span class="sxs-lookup"><span data-stu-id="5866d-338">Set the following key vault fields:</span></span>

    - <span data-ttu-id="5866d-339">**ID de l’application (client)**  : saisissez l’ID client d’application que vous avez créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="5866d-339">**Application (client) ID** – Enter the application client ID that you created earlier.</span></span>
    - <span data-ttu-id="5866d-340">**Secret d’application** : entrez le secret que vous avez enregistré pour l’application que vous avez créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="5866d-340">**Application Secret** – Enter the secret that you saved for the application that you created earlier.</span></span>
    - <span data-ttu-id="5866d-341">**Nom DNS** : vous pouvez trouver le nom DNS (Domain Name System) sur la page des détails de l’application que vous avez créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="5866d-341">**DNS name** – You can find the Domain Name System (DNS) name on the application details page for the application that you created earlier.</span></span>
    - <span data-ttu-id="5866d-342">**Nom secret** : saisissez **storage-account-connection-string**.</span><span class="sxs-lookup"><span data-stu-id="5866d-342">**Secret name** – Enter **storage-account-connection-string**.</span></span>
3. <span data-ttu-id="5866d-343">Paramétrez **Activer l’intégration de Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="5866d-343">Enable **Enable Data Lake integration**.</span></span>
4. <span data-ttu-id="5866d-344">Sélectionnez **Tester Azure Key Vault** et vérifiez qu'il n'y a pas d'erreurs.</span><span class="sxs-lookup"><span data-stu-id="5866d-344">Select **Test Azure Key Vault** and verify there are no errors.</span></span>
5. <span data-ttu-id="5866d-345">Sélectionnez **Tester le stockage Azure** et vérifiez qu'il n'y a pas d'erreurs.</span><span class="sxs-lookup"><span data-stu-id="5866d-345">Select **Test Azure storage** and verify there are no errors.</span></span>

## <a name="feedback-and-support"></a><span data-ttu-id="5866d-346">Commentaires et support</span><span class="sxs-lookup"><span data-stu-id="5866d-346">Feedback and support</span></span>

<span data-ttu-id="5866d-347">Veuillez envoyer un e-mail à [Informations sur les paiements des clients (aperçu)](mailto:fiap@microsoft.com) si vous souhaitez fournir des commentaires ou si vous avez besoin d’aide.</span><span class="sxs-lookup"><span data-stu-id="5866d-347">Please send an email to [Customer payment insights (Preview)](mailto:fiap@microsoft.com) if you are interested in providing feedback or need support.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="5866d-348">Avis de confidentialité</span><span class="sxs-lookup"><span data-stu-id="5866d-348">Privacy notice</span></span>

<span data-ttu-id="5866d-349">Les versions préliminaires (1) peuvent utiliser moins de mesures de confidentialité et de sécurité que le service Dynamics 365 Finance and Operations, (2) ne sont pas inclus dans le contrat de niveau de service (SLA) pour ce service, (3) ne doivent pas être utilisés pour traiter des données personnelles ou autres données soumises à des exigences de conformité juridique ou réglementaire, et (4) bénéficient d’un support limité.</span><span class="sxs-lookup"><span data-stu-id="5866d-349">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
