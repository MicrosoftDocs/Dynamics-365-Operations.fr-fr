---
title: Configuration de Finance Insights (version préliminaire)
description: Cette rubrique explique les étapes de configuration qui permettront à votre système d’utiliser les fonctionnalités disponibles dans Finance Insights.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: cf29e3c05f9fdcc685017a4c640ef32c40989c73
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208555"
---
# <a name="configuration-for-finance-insights-preview"></a><span data-ttu-id="755b2-103">Configuration de Finance Insights (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="755b2-103">Configuration for Finance insights (preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="755b2-104">Finance Insights combine les fonctionnalités de Microsoft Dynamics 365 Finance avec Microsoft Dataverse, Azure et AI Builder pour fournir de puissants outils de prévision à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="755b2-104">Finance insights combines functionality from Microsoft Dynamics 365 Finance with Microsoft Dataverse, Azure, and AI Builder to provide powerful forecasting tools for your organization.</span></span> <span data-ttu-id="755b2-105">Cette rubrique explique les étapes de configuration qui permettront à votre système d’utiliser les fonctionnalités disponibles dans Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="755b2-105">This topic explains the configuration steps that will enable your system to use the capabilities that are available in Finance insights.</span></span>

## <a name="deploy-dynamics-365-finance"></a><span data-ttu-id="755b2-106">Déployer Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="755b2-106">Deploy Dynamics 365 Finance</span></span>

<span data-ttu-id="755b2-107">Déployez les environnements comme suit.</span><span class="sxs-lookup"><span data-stu-id="755b2-107">Deploy the environments by following these steps.</span></span>

1. <span data-ttu-id="755b2-108">Dans Microsoft Dynamics Lifecycle Services (LCS), créez ou mettez à jour un environnement Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="755b2-108">In Microsoft Dynamics Lifecycle Services (LCS), create or update a Dynamics 365 Finance environment.</span></span> <span data-ttu-id="755b2-109">L’environnement nécessite la version d’application 10.0.11/Platform update 35 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="755b2-109">The environment requires app version 10.0.11/Platform update 35 or later.</span></span>
2. <span data-ttu-id="755b2-110">L’environnement doit être un environnement haute disponibilité (HA) dans Sandbox.</span><span class="sxs-lookup"><span data-stu-id="755b2-110">The environment must be a high-availability (HA) environment in Sandbox.</span></span> <span data-ttu-id="755b2-111">(Ce type d’environnement est également appelé environnement de niveau 2.) Pour plus d’informations, voir [Planification de l’environnement](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="755b2-111">(This type of environment is also known as a Tier-2 environment.) For more information, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
3. <span data-ttu-id="755b2-112">Si vous utilisez des données de démonstration Contoso, vous aurez besoin d’exemples de données supplémentaires pour utiliser les fonctionnalités de prévisions de paiement client, de prévisions de flux de trésorerie et de prévisions budgétaires.</span><span class="sxs-lookup"><span data-stu-id="755b2-112">If you're using Contoso demo data, you will require additional sample data to use the Customer payment predictions, Cash flow forecasts, and Budget forecasts features.</span></span> 

## <a name="configure-dataverse"></a><span data-ttu-id="755b2-113">Configurer Dataverse</span><span class="sxs-lookup"><span data-stu-id="755b2-113">Configure Dataverse</span></span>

<span data-ttu-id="755b2-114">Vous pouvez effectuer les étapes de configuration manuelle suivantes, ou accélérer le processus de configuration à l’aide du script Windows PowerShell fourni.</span><span class="sxs-lookup"><span data-stu-id="755b2-114">You can complete the manual configuration steps that follow, or you can speed up the configuration process by using the Windows PowerShell script that is provided.</span></span> <span data-ttu-id="755b2-115">Une fois l’exécution du script PowerShell terminée, il vous donnera les valeurs à utiliser pour configurer Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="755b2-115">When the PowerShell script has finished running, it will give you values to use to configure Finance insights.</span></span> 

> [!NOTE]
> <span data-ttu-id="755b2-116">Ouvrez PowerShell sur votre ordinateur pour exécuter le script.</span><span class="sxs-lookup"><span data-stu-id="755b2-116">Open PowerShell on your PC to run the script.</span></span> <span data-ttu-id="755b2-117">Vous aurez peut-être besoin de PowerShell version 5.</span><span class="sxs-lookup"><span data-stu-id="755b2-117">You may need PowerShell version 5.</span></span> <span data-ttu-id="755b2-118">L’option « Essayer » de Microsoft Azure CLI risque de ne pas fonctionner.</span><span class="sxs-lookup"><span data-stu-id="755b2-118">The Microsoft Azure CLI "Try it" option may not work.</span></span>

# <a name="manual-configuration-steps"></a>[<span data-ttu-id="755b2-119">Étapes de configuration manuelle</span><span class="sxs-lookup"><span data-stu-id="755b2-119">Manual configuration steps</span></span>](#tab/configuration-steps)

1. <span data-ttu-id="755b2-120">Ouvrez le [centre d’administration Power Platform](https://admin.powerplatform.microsoft.com/) et suivez ces étapes pour créer un environnement Dataverse dans le même client Active Directory :</span><span class="sxs-lookup"><span data-stu-id="755b2-120">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com/), and follow these steps to create a new Dataverse environment in the same Active Directory tenant:</span></span>

    1. <span data-ttu-id="755b2-121">Ouvrez la page **Environnements**.</span><span class="sxs-lookup"><span data-stu-id="755b2-121">Open the **Environments** page.</span></span>

        <span data-ttu-id="755b2-122">[![Page Environnements](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span><span class="sxs-lookup"><span data-stu-id="755b2-122">[![Environments page](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span></span>

    2. <span data-ttu-id="755b2-123">Sélectionnez **Nouvel environnement**.</span><span class="sxs-lookup"><span data-stu-id="755b2-123">Select **New environment**.</span></span>
    3. <span data-ttu-id="755b2-124">Dans le champ **Type**, sélectionnez **Sandbox**.</span><span class="sxs-lookup"><span data-stu-id="755b2-124">In the **Type** field, select **Sandbox**.</span></span>
    4. <span data-ttu-id="755b2-125">Définissez l’option **Créer une base de données** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="755b2-125">Set the **Create Database** option to **Yes**.</span></span>
    5. <span data-ttu-id="755b2-126">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="755b2-126">Select **Next**.</span></span>
    6. <span data-ttu-id="755b2-127">Sélectionnez la langue et la devise de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="755b2-127">Select the language and currency for your organization.</span></span>
    7. <span data-ttu-id="755b2-128">Acceptez les valeurs par défaut dans les autres champs.</span><span class="sxs-lookup"><span data-stu-id="755b2-128">Accept the default values for the other fields.</span></span>
    8. <span data-ttu-id="755b2-129">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="755b2-129">Select **Save**.</span></span>
    9. <span data-ttu-id="755b2-130">Actualisez la page **Environnements**.</span><span class="sxs-lookup"><span data-stu-id="755b2-130">Refresh the **Environments** page.</span></span>
    10. <span data-ttu-id="755b2-131">Attendez que la valeur du champ **État** soit mise à jour sur la valeur **Prêt**.</span><span class="sxs-lookup"><span data-stu-id="755b2-131">Wait until the value of the **State** field is updated to **Ready**.</span></span>
    11. <span data-ttu-id="755b2-132">Prenez note de l’ID de l’organisation Dataverse.</span><span class="sxs-lookup"><span data-stu-id="755b2-132">Make a note of the Dataverse organization ID.</span></span>
    12. <span data-ttu-id="755b2-133">Sélectionnez l’environnement à copier, puis sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="755b2-133">Select the environment, and then select **Settings**.</span></span>
    13. <span data-ttu-id="755b2-134">Sélectionnez **Ressources \> Tous les anciens paramètres**.</span><span class="sxs-lookup"><span data-stu-id="755b2-134">Select **Resources \> All Legacy Settings**.</span></span>
    14. <span data-ttu-id="755b2-135">Dans la barre de navigation supérieure, sélectionnez **Paramètres**, puis **Personnalisations**.</span><span class="sxs-lookup"><span data-stu-id="755b2-135">On the top navigation bar, select **Settings**, and then select **Customizations**.</span></span>
    15. <span data-ttu-id="755b2-136">Sélectionnez **Ressources du développeur**.</span><span class="sxs-lookup"><span data-stu-id="755b2-136">Select **Developer Resources**.</span></span>
    16. <span data-ttu-id="755b2-137">Définissez le champ **ID d’informations de référence d’instance** sur la valeur d’ID d’organisation Dataverse que vous avez notée précédemment.</span><span class="sxs-lookup"><span data-stu-id="755b2-137">Set the **Instance Reference Information ID** field to the Dataverse organization ID value that you made a note of earlier.</span></span>
    17. <span data-ttu-id="755b2-138">Dans la barre d’adresse du navigateur, notez l’URL de l’organisation Dataverse.</span><span class="sxs-lookup"><span data-stu-id="755b2-138">In the browser's address bar, make a note of the URL for the Dataverse organization.</span></span> <span data-ttu-id="755b2-139">Par exemple, l’URL peut être `https://org42b2b3d3.crm.dynamics.com`.</span><span class="sxs-lookup"><span data-stu-id="755b2-139">For example, the URL might be `https://org42b2b3d3.crm.dynamics.com`.</span></span>

2. <span data-ttu-id="755b2-140">Si vous prévoyez d’utiliser la fonctionnalité Prévisions de flux de trésorerie ou Prévisions budgétaires, procédez comme suit pour mettre à jour la limite d’annotation pour votre organisation à au moins 50 mégaoctets (Mo) :</span><span class="sxs-lookup"><span data-stu-id="755b2-140">If you plan to use the Cash flow forecasts or Budget forecasts feature, follow these steps to update the annotation limit for your organization to at least 50 megabytes (MB):</span></span>

    1. <span data-ttu-id="755b2-141">Ouvrez le portail [Power Apps](https://make.powerapps.com).</span><span class="sxs-lookup"><span data-stu-id="755b2-141">Open the [Power Apps portal](https://make.powerapps.com).</span></span>
    2. <span data-ttu-id="755b2-142">Sélectionnez l’environnement que vous venez de créer, puis sélectionnez **Paramètres avancés**.</span><span class="sxs-lookup"><span data-stu-id="755b2-142">Select the environment that you just created, and then select **Advanced settings**.</span></span>
    3. <span data-ttu-id="755b2-143">Sélectionnez **Paramètres \> Configuration de messagerie**.</span><span class="sxs-lookup"><span data-stu-id="755b2-143">Select **Settings \> Email Configuration**.</span></span>
    4. <span data-ttu-id="755b2-144">Changez la valeur du champ **Taille maximale du fichier** sur **51 200**.</span><span class="sxs-lookup"><span data-stu-id="755b2-144">Change the value of the **Maximum file size** field to **51,200**.</span></span> <span data-ttu-id="755b2-145">(La valeur est exprimée en kilooctets \[Ko\].)</span><span class="sxs-lookup"><span data-stu-id="755b2-145">(The value is expressed in kilobytes \[KB\].)</span></span>
    5. <span data-ttu-id="755b2-146">Cliquez sur **OK** pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="755b2-146">Select **OK** to save your changes.</span></span>

# <a name="windows-powershell-configuration-script"></a>[<span data-ttu-id="755b2-147">Script de configuration Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="755b2-147">Windows PowerShell configuration script</span></span>](#tab/powershell-configuration-script)

```azurecli-interactive
Write-Output 'The following modules need to be present for execution of this script:'
Write-Output '  Microsoft.PowerApps.Administration.PowerShell'
Write-Output '  Microsoft.PowerApps.PowerShell'
Write-Output '  Microsoft.Xrm.Tooling.CrmConnector.PowerShell'

try {
    $moduleConsent = Read-Host 'Is it ok to install or update these modules as needed? (yes/no)'
    if ($moduleConsent -ne 'yes' -and $moduleConsent -ne 'y') {
        Write-Warning 'User declined to install required modules.'
        return
    }

    $module = 'Microsoft.PowerApps.Administration.PowerShell'
    if (-not (Get-InstalledModule -Name $module -MinimumVersion '2.0.61' -ErrorAction SilentlyContinue)) {
        Install-Module -Name $module -MinimumVersion '2.0.61' -Force
        Write-Output ('Installed {0} module.' -f $module)
    }
    else {
        Write-Output ('{0} module found.' -f $module)
    }

    $module = 'Microsoft.PowerApps.PowerShell'
    if (-not (Get-InstalledModule -Name $module -MinimumVersion '1.0.9' -ErrorAction SilentlyContinue)) {
        Install-Module -Name $module -MinimumVersion '1.0.9' -AllowClobber -Force
        Write-Output ('Installed {0} module.' -f $module)
    }
    else {
        Write-Output ('{0} module found.' -f $module)
    }

    $module = 'Microsoft.Xrm.Tooling.CrmConnector.PowerShell'
    if (-not (Get-InstalledModule -Name $module -MinimumVersion '3.3.0.892' -ErrorAction SilentlyContinue)) {
        Install-Module -Name $module -MinimumVersion '3.3.0.892' -Force
        Write-Output ('Installed {0} module.' -f $module)
    }
    else {
        Write-Output ('{0} module found.' -f $module)
    }

    Write-Output '================================================================================='

    $useMfa = $false
    $useMfaPrompt = Read-Host "Does your organization require the use of multi-factor authentication? (yes/no)"
    if ($useMfaPrompt -eq 'yes' -or $useMfaPrompt -eq 'y') {
        $useMfa = $true
    }
    if(-not $useMfa) {
        $credential = Get-Credential -Message 'Power Apps Credential'
    }

    $orgFriendlyName = Read-Host "Enter the name of the CDS Organization to use or create: (blank for 'FinanceInsightsOrg')"
    if ($orgFriendlyName.Trim() -eq '') {
        $orgFriendlyName = 'FinanceInsightsOrg'
    }

    $isDefaultOrgPrompt = Read-Host ("Is '" + $orgFriendlyName + "' the default organization for your tenant? (yes/no)")
    if ($isDefaultOrgPrompt -eq 'yes' -or $isDefaultOrgPrompt -eq 'y') {
        $isDefaultOrg = $true
    }

    if ($credential) {
        Add-PowerAppsAccount -Username $credential.UserName -Password $credential.Password
    }
    else {
        Add-PowerAppsAccount
    }

    if ($isDefaultOrg) {
        $orgMatch = ('(default)')
        $environment = (Get-AdminPowerAppEnvironment | Where-Object { $_.IsDefault -eq $true })
    }
    else {
        $orgMatch = ('{0} (*)' -f $orgFriendlyName)
        $environment = (Get-AdminPowerAppEnvironment | Where-Object { ($_.IsDefault -eq $false -and ($_.DisplayName -eq $orgFriendlyName -or $_.DisplayName -like $orgMatch)) })
    }

    $getCrmOrgParams = @{ 'OnlineType' = 'Office365' }
    if ($credential) {
        $getCrmOrgParams.Credential = $credential
    }

    if ($null -eq $environment) {
        Write-Output '================================================================================='
        Write-Output 'PowerApps environment not found. A new one will be provisioned.'

        $invalid = 'invalid'

        $location = $invalid
        $cdsLocations = (Get-AdminPowerAppEnvironmentLocations | Select-Object LocationName).LocationName
        while (-not ($location -in $cdsLocations)) {
            $location = (Read-Host -Prompt "Enter the location in which to create the new PowerApps environment: ('help' to see values)")
            if ($location -eq 'help') {
                $cdsLocations
            }
        }

        $currency = $invalid
        $cdsCurrencies = (Get-AdminPowerAppCdsDatabaseCurrencies -Location $location | Select-Object CurrencyName).CurrencyName
        while ($currency -ne '' -and -not ($currency -in $cdsCurrencies)) {
            $currency = (Read-Host -Prompt "Enter the currency to use for the new PowerApps environment: ('help' to see values, blank for default)")
            if ($currency -eq 'help') {
                $cdsCurrencies
            }
        }

        $language = $invalid
        $cdsLanguages = (Get-AdminPowerAppCdsDatabaseLanguages -Location $location | Select-Object LanguageName, LanguageDisplayName)
        while ($language -ne '' -and -not ($language -in $cdsLanguages.LanguageName)) {
            $language = (Read-Host -Prompt "Enter the language name to use for the new PowerApps environment: ('help' to see values, blank for default)")
            if ($language -eq 'help') {
                $cdsLanguages | Format-Table -Property LanguageName, LanguageDisplayName
            }
        }

        Write-Output 'Provisioning PowerApps environment. This may take several minutes.'

        $sleep = 15

        $envParams = @{ 'DisplayName' = $orgFriendlyName; 'EnvironmentSku' = 'Sandbox'; 'ProvisionDatabase' = $true; 'Location' = $location; 'WaitUntilFinished' = $true }
        if ($language.Trim() -ne '') {
            $envParams.LanguageName = $language
        }
        if ($currency.Trim() -ne '') {
            $envParams.CurrencyName = $currency
        }
        $newEnvResult = New-AdminPowerAppEnvironment @envParams
        if (($null -eq $newEnvResult) -or ($newEnvResult.CommonDataServiceDatabaseProvisioningState -ne 'Succeeded')) {
            Write-Warning 'Failed to create to PowerApps environment'
            if ($null -ne $newEnvResult) {
                $newEnvResult
            }
        }
        else {
            $environment = $null
            $retryCount = 0
            while (($null -eq $environment) -and ($retryCount -lt 5)) {
                Start-Sleep -Seconds $sleep
                $environment = (Get-AdminPowerAppEnvironment | Where-Object { ($_.DisplayName -like $orgMatch) })
            }
            Write-Output ("Provisioned PowerApps environment with name: '" + $environment.DisplayName + "'")
        }

        Write-Output 'Waiting for CDS organization provisioning. This may take several minutes.'
        if (-not $credential) {
            $sleep = 120
            Write-Output 'You may be prompted for credentials multiple times while checking the status of the provisioning.'
        }

        while ($null -eq $crmOrg) {
            Start-Sleep -Seconds $sleep
            $crmOrg = (Get-CrmOrganizations @getCrmOrgParams) | Where-Object { $_.FriendlyName -eq $orgFriendlyName }
        }
    }
    else {
        $crmOrgs = Get-CrmOrganizations @getCrmOrgParams
        if ($UseDefaultOrganization -eq $true) {
            $crmOrg = $crmOrgs | Where-Object { $_.FriendlyName -match $orgMatch }
        }
        else {
            $crmOrg = $crmOrgs | Where-Object { $_.FriendlyName -eq $orgFriendlyName }
        }
    }

    Write-Output '================================================================================='
    Write-Output 'Values for PowerAI LCS Add-In:'
    Write-Output ("  CDS organization url:             " + $crmOrg.WebApplicationUrl)
    Write-Output ("  CDS organization ID:              " + $crmOrg.OrganizationId)
}
catch {
    Write-Error $_.Exception.Message
    Write-Warning $_.Exception.StackTrace
    $inner = $_.Exception.InnerException
    while ($null -ne $inner) {
        Write-Output 'Inner Exception:'
        Write-Error $_.Exception.Message
        Write-Warning $_.Exception.StackTrace
        $inner = $inner.InnerException
    }
}
```
---

## <a name="configure-the-azure-setup"></a><span data-ttu-id="755b2-148">Configurer la configuration Azure</span><span class="sxs-lookup"><span data-stu-id="755b2-148">Configure the Azure setup</span></span>

### <a name="enter-the-dataverse-directory-id-and-the-users-azure-ad-object-id"></a><span data-ttu-id="755b2-149">Saisir l’ID de répertoire Dataverse et l’ID d’objet Azure AD de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="755b2-149">Enter the Dataverse directory ID and the user's Azure AD object ID</span></span>

1. <span data-ttu-id="755b2-150">Saisissez l’ID de répertoire Dataverse :</span><span class="sxs-lookup"><span data-stu-id="755b2-150">Enter the Dataverse directory ID:</span></span>

    1. <span data-ttu-id="755b2-151">Ouvrez le [Portail Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="755b2-151">Open the [Azure portal](https://portal.azure.com).</span></span>
    2. <span data-ttu-id="755b2-152">Connectez-vous en utilisant l’ID utilisateur qui a été utilisé pour créer l’environnement Dataverse.</span><span class="sxs-lookup"><span data-stu-id="755b2-152">Sign in by using the user ID that was used to create the Dataverse environment.</span></span>
    3. <span data-ttu-id="755b2-153">Atteindre **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="755b2-153">Go to **Azure Active Directory**.</span></span>
    4. <span data-ttu-id="755b2-154">Copiez la valeur **ID du locataire**.</span><span class="sxs-lookup"><span data-stu-id="755b2-154">Copy the **Tenant ID** value.</span></span>

2. <span data-ttu-id="755b2-155">Saisissez l’ID d’objet Azure Active Directory (Azure AD) de l’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="755b2-155">Enter the user's Azure Active Directory (Azure AD) object ID:</span></span>

    1. <span data-ttu-id="755b2-156">Dans le [portail Azure](https://portal.azure.com), accédez à **Utilisateurs** et recherchez l’utilisateur par adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="755b2-156">In the [Azure portal](https://portal.azure.com), go to **Users**, and search for the user by email address.</span></span>
    2. <span data-ttu-id="755b2-157">Sélectionnez le nom de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="755b2-157">Select the user's name.</span></span>
    3. <span data-ttu-id="755b2-158">Copiez la valeur **ID de l’objet**.</span><span class="sxs-lookup"><span data-stu-id="755b2-158">Copy the **Object ID** value.</span></span>

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a><span data-ttu-id="755b2-159">Utiliser Azure Cloud Shell pour configurer les ressources Finance Insights Data Lake</span><span class="sxs-lookup"><span data-stu-id="755b2-159">Use Azure Cloud Shell to set up Finance insights Data Lake resources</span></span>

# <a name="use-a-windows-powershell-script"></a>[<span data-ttu-id="755b2-160">Utiliser un script de configuration Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="755b2-160">Use a Windows PowerShell script</span></span>](#tab/use-a-powershell-script)

<span data-ttu-id="755b2-161">Un script Windows PowerShell a été fourni, afin que vous puissiez facilement configurer les ressources Azure décrites dans [Configurer l’exportation vers Azure Data Lake](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/configure-export-data-lake).</span><span class="sxs-lookup"><span data-stu-id="755b2-161">A Windows PowerShell script has been provided, so that you can easily set up the Azure resources that are described in [Configure export to Azure Data Lake](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/configure-export-data-lake).</span></span> <span data-ttu-id="755b2-162">Si vous préférez effectuer une configuration manuelle, ignorez cette procédure et continuez avec la procédure dans la section [Configuration manuelle](#manual-setup).</span><span class="sxs-lookup"><span data-stu-id="755b2-162">If you prefer to do manual setup, skip this procedure, and continue with the procedure in the [Manual setup](#manual-setup) section.</span></span>

> [!NOTE]
> <span data-ttu-id="755b2-163">Pour exécuter le script PowerShell, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="755b2-163">Follow the steps below to run the PowerShell script.</span></span> <span data-ttu-id="755b2-164">L’option « Essayer » d’Azure CLI, ou l’exécution du script sur votre ordinateur risque de ne pas fonctionner.</span><span class="sxs-lookup"><span data-stu-id="755b2-164">The Azure CLI "Try it" option, or running the script on your PC may not work.</span></span>

<span data-ttu-id="755b2-165">Suivez ces étapes pour configurer Azure à l’aide du script Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="755b2-165">Follow these steps to configure Azure by using the Windows PowerShell script.</span></span> <span data-ttu-id="755b2-166">Vous devez disposer des droits pour créer un groupe de ressources Azure, des ressources Azure et une application Azure AD.</span><span class="sxs-lookup"><span data-stu-id="755b2-166">You must have rights to create an Azure resource group, Azure resources, and an Azure AD application.</span></span> <span data-ttu-id="755b2-167">Pour plus d’informations sur les autorisations requises, voir [Vérifier les autorisations Azure AD](https://docs.microsoft.com/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span><span class="sxs-lookup"><span data-stu-id="755b2-167">For information about the required permissions, see [Check Azure AD permissions](https://docs.microsoft.com/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span></span>

1. <span data-ttu-id="755b2-168">Dans le [portail Azure](https://portal.azure.com), accédez à votre abonnement Azure cible.</span><span class="sxs-lookup"><span data-stu-id="755b2-168">In the [Azure portal](https://portal.azure.com), go to your target Azure subscription.</span></span> <span data-ttu-id="755b2-169">Sélectionnez le bouton **Cloud Shell** à droite du champ **Recherche**.</span><span class="sxs-lookup"><span data-stu-id="755b2-169">Select the **Cloud Shell** button to the right of the **Search** field.</span></span>
2. <span data-ttu-id="755b2-170">Sélectionnez **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="755b2-170">Select **PowerShell**.</span></span>
3. <span data-ttu-id="755b2-171">Créez un espace de stockage, si vous êtes invité à le faire.</span><span class="sxs-lookup"><span data-stu-id="755b2-171">Create storage, if you're prompted to do so.</span></span> <span data-ttu-id="755b2-172">Ensuite, téléchargez le script Windows PowerShell dans la session.</span><span class="sxs-lookup"><span data-stu-id="755b2-172">Then upload the Windows PowerShell script to the session.</span></span>
4. <span data-ttu-id="755b2-173">Exécutez le script.</span><span class="sxs-lookup"><span data-stu-id="755b2-173">Run the script.</span></span>
5. <span data-ttu-id="755b2-174">Suivez les invites pour exécuter le script.</span><span class="sxs-lookup"><span data-stu-id="755b2-174">Follow the prompts to run the script.</span></span>
6. <span data-ttu-id="755b2-175">Utilisez les informations de la sortie du script pour installer le complément **Exporter vers Data Lake** dans LCS.</span><span class="sxs-lookup"><span data-stu-id="755b2-175">Use the information from the script output to install the **Export to Data Lake** add-in in LCS.</span></span>
7. <span data-ttu-id="755b2-176">Utilisez les informations de la sortie du script pour activer le magasin d’entités sur la page **Connexions de données** dans Finance (**Administration du système \> Paramètres système \> Connexions des données**).</span><span class="sxs-lookup"><span data-stu-id="755b2-176">Use the information from the script output to enable the entity store on the **Data connections** page in Finance (**System administration \> System parameters \> Data connections**).</span></span>

### <a name="manual-setup"></a><span data-ttu-id="755b2-177">Configuration manuelle</span><span class="sxs-lookup"><span data-stu-id="755b2-177">Manual setup</span></span>

#### <a name="add-applications-to-the-azure-ad-tenant"></a><span data-ttu-id="755b2-178">Ajouter des applications au locataire Azure AD</span><span class="sxs-lookup"><span data-stu-id="755b2-178">Add applications to the Azure AD tenant</span></span>

1. <span data-ttu-id="755b2-179">Dans le [portail Azure](https://portal.azure.com), accédez à **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="755b2-179">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**.</span></span>
2. <span data-ttu-id="755b2-180">Sélectionnez **Gérer \> Applications de l’entreprise**.</span><span class="sxs-lookup"><span data-stu-id="755b2-180">Select **Manage \> Enterprise applications**.</span></span>
3. <span data-ttu-id="755b2-181">Recherchez les applications suivantes par ID d’application.</span><span class="sxs-lookup"><span data-stu-id="755b2-181">Search for the following applications by app ID.</span></span>

    | <span data-ttu-id="755b2-182">Demande</span><span class="sxs-lookup"><span data-stu-id="755b2-182">Application</span></span>                              | <span data-ttu-id="755b2-183">ID d’application</span><span class="sxs-lookup"><span data-stu-id="755b2-183">App ID</span></span>                               |
    |------------------------------------------|--------------------------------------|
    | <span data-ttu-id="755b2-184">Microservices ERP Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="755b2-184">Microsoft Dynamics ERP Microservices</span></span>     | <span data-ttu-id="755b2-185">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="755b2-185">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
    | <span data-ttu-id="755b2-186">CDS Microservices ERP Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="755b2-186">Microsoft Dynamics ERP Microservices CDS</span></span> | <span data-ttu-id="755b2-187">703e2651-d3fc-48f5-942c-74274233dba8</span><span class="sxs-lookup"><span data-stu-id="755b2-187">703e2651-d3fc-48f5-942c-74274233dba8</span></span> |
    | <span data-ttu-id="755b2-188">Service d’autorisation AI Builder</span><span class="sxs-lookup"><span data-stu-id="755b2-188">AI Builder Authorization Service</span></span>         | <span data-ttu-id="755b2-189">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span><span class="sxs-lookup"><span data-stu-id="755b2-189">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span></span> |

<span data-ttu-id="755b2-190">Si vous ne trouvez aucune des applications précédentes, essayez les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="755b2-190">If you can't find any of the preceding applications, try the following steps.</span></span>

1. <span data-ttu-id="755b2-191">Sur votre ordinateur local, sélectionnez le menu **Démarrer** et recherchez **powershell**.</span><span class="sxs-lookup"><span data-stu-id="755b2-191">On your local machine, select the **Start** menu, and search for **powershell**.</span></span>
2. <span data-ttu-id="755b2-192">Sélectionnez et maintenez (ou cliquez avec le bouton droit) sur **Windows PowerShell**, puis sélectionnez **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="755b2-192">Select and hold (or right-click) **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="755b2-193">Exécutez la commande suivante pour installer le module **AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="755b2-193">Run the following command to install the **AzureAD** module.</span></span>

    `Install-Module -Name AzureAD`

4. <span data-ttu-id="755b2-194">Si un fournisseur NuGet doit continuer, sélectionnez **O** pour l’installer.</span><span class="sxs-lookup"><span data-stu-id="755b2-194">If a NuGet provider is required to continue, select **Y** to install it.</span></span>
5. <span data-ttu-id="755b2-195">Si un message « Référentiel non approuvé » apparaît, sélectionnez **O** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="755b2-195">If an "Untrusted repository" message appears, select **Y** to continue.</span></span>
6. <span data-ttu-id="755b2-196">Pour chaque application à ajouter, exécutez les commandes suivantes pour ajouter l’application à Azure AD.</span><span class="sxs-lookup"><span data-stu-id="755b2-196">For each application that must be added, run the following commands to add the application to Azure AD.</span></span> <span data-ttu-id="755b2-197">Lorsque vous y êtes invité, connectez-vous en tant qu’administrateur Azure AD.</span><span class="sxs-lookup"><span data-stu-id="755b2-197">When you're prompted, sign in as the Azure AD administrator.</span></span>

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a><span data-ttu-id="755b2-198">Créer des ressources Azure</span><span class="sxs-lookup"><span data-stu-id="755b2-198">Create Azure resources</span></span>

> [!NOTE]
> <span data-ttu-id="755b2-199">Assurez-vous de créer les ressources suivantes dans la même instance Azure AD en tant qu’environnement Dataverse.</span><span class="sxs-lookup"><span data-stu-id="755b2-199">Make sure that you create the following resources in the same Azure AD instance as the Dataverse environment.</span></span> <span data-ttu-id="755b2-200">Vous ne pouvez pas utiliser les ressources d’une autre instance Azure AD.</span><span class="sxs-lookup"><span data-stu-id="755b2-200">You can't use resources from a different Azure AD instance.</span></span>

1. <span data-ttu-id="755b2-201">Création d’un compte de stockage :</span><span class="sxs-lookup"><span data-stu-id="755b2-201">Create a new storage account:</span></span>

    1. <span data-ttu-id="755b2-202">Dans le [portail Azure](https://portal.azure.com), créez un compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="755b2-202">In the [Azure portal](https://portal.azure.com), create a storage account.</span></span>
    2. <span data-ttu-id="755b2-203">Dans la boîte de dialogue **Créer un compte de stockage**, définissez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="755b2-203">In the **Create storage account** dialog box, set the following fields:</span></span>

        - <span data-ttu-id="755b2-204">**Emplacement** : sélectionnez le centre de données où se trouve votre environnement.</span><span class="sxs-lookup"><span data-stu-id="755b2-204">**Location** – Select the data center where your environment is located.</span></span>
        - <span data-ttu-id="755b2-205">**Performance** : nous vous recommandons de sélectionner **Standard**.</span><span class="sxs-lookup"><span data-stu-id="755b2-205">**Performance** – We recommend that you select **Standard**.</span></span>
        - <span data-ttu-id="755b2-206">**Type de compte** : vous devez sélectionner **StorageV2**.</span><span class="sxs-lookup"><span data-stu-id="755b2-206">**Account kind** – You must select **StorageV2**.</span></span>

    3. <span data-ttu-id="755b2-207">Dans la boîte de dialogue **Options avancées**, pour l’option **Stockage Data Lake Gen2**, sélectionnez **Activer** sous la fonctionnalité **Espaces de noms hiérarchiques**.</span><span class="sxs-lookup"><span data-stu-id="755b2-207">In the **Advanced options** dialog box, for the **Data Lake storage Gen2** option, select **Enable** under the **Hierarchical namespaces** feature.</span></span> <span data-ttu-id="755b2-208">Si vous désactivez cette fonctionnalité, vous ne pouvez pas consommer de données que les applications Finance and Operations écrivent à l’aide de services tels que les flux de données Power BI.</span><span class="sxs-lookup"><span data-stu-id="755b2-208">If you disable this feature, you can't consume data that Finance and Operations apps write by using services such as Power BI data flows.</span></span>
    4. <span data-ttu-id="755b2-209">Sélectionnez **Réviser et créer**.</span><span class="sxs-lookup"><span data-stu-id="755b2-209">Select **Review and create**.</span></span> <span data-ttu-id="755b2-210">Une fois le déploiement terminé, la nouvelle ressource sera affichée dans le portail Azure.</span><span class="sxs-lookup"><span data-stu-id="755b2-210">When the deployment is completed, the new resource will be shown in the Azure portal.</span></span>
    5. <span data-ttu-id="755b2-211">Accédez au compte de stockage que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="755b2-211">Go to the storage account that you created.</span></span>
    6. <span data-ttu-id="755b2-212">Dans le menu de gauche, sélectionnez **Clés d’accès**.</span><span class="sxs-lookup"><span data-stu-id="755b2-212">On the left menu, select **Access keys**.</span></span>
    7. <span data-ttu-id="755b2-213">Copiez et enregistrez la chaîne de connexion pour **Key1** ou **Key2**.</span><span class="sxs-lookup"><span data-stu-id="755b2-213">Copy and save the connection string for either **Key1** or **Key2**.</span></span>
    8. <span data-ttu-id="755b2-214">Copiez et enregistrez le nom du compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="755b2-214">Copy and save the storage account name.</span></span>

2. <span data-ttu-id="755b2-215">Créer un coffre de clés :</span><span class="sxs-lookup"><span data-stu-id="755b2-215">Create a new key vault:</span></span>

    1. <span data-ttu-id="755b2-216">Dans le [portail Azure](https://portal.azure.com), créez un coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="755b2-216">In the [Azure portal](https://portal.azure.com), create a key vault.</span></span>
    2. <span data-ttu-id="755b2-217">Dans la boîte de dialogue **Créer un coffre de clés**, dans le champ **Emplacement**, sélectionnez le centre de données dans lequel se trouve votre environnement.</span><span class="sxs-lookup"><span data-stu-id="755b2-217">In the **Create key vault** dialog box, in the **Location** field, select the data center where your environment is located.</span></span>
    3. <span data-ttu-id="755b2-218">Une fois le coffre de clés créé, sélectionnez-le dans la liste, puis sélectionnez **Secrets**.</span><span class="sxs-lookup"><span data-stu-id="755b2-218">After key vault is created, select it in the list, and then select **Secrets**.</span></span>
    4. <span data-ttu-id="755b2-219">Sélectionnez **Générer/Importer**.</span><span class="sxs-lookup"><span data-stu-id="755b2-219">Select **Generate/Import**.</span></span>
    5. <span data-ttu-id="755b2-220">Dans la boîte de dialogue **Créer un secret**, dans le champ **Options de téléchargement**, sélectionnez **Manuel**.</span><span class="sxs-lookup"><span data-stu-id="755b2-220">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
    6. <span data-ttu-id="755b2-221">Permet d’entrer un nom pour le secret.</span><span class="sxs-lookup"><span data-stu-id="755b2-221">Enter a name for the secret.</span></span> <span data-ttu-id="755b2-222">Notez le nom, car vous devrez le fournir ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="755b2-222">Make a note of the name, because you will have to provide it later.</span></span>
    7. <span data-ttu-id="755b2-223">Dans le champ **Valeur**, saisissez la chaîne de connexion que vous avez obtenue du compte de stockage dans la procédure précédente.</span><span class="sxs-lookup"><span data-stu-id="755b2-223">In the **Value** field, enter the connection string that you obtained from the storage account in the previous procedure.</span></span>
    8. <span data-ttu-id="755b2-224">Sélectionnez **Activé**, puis sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="755b2-224">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="755b2-225">Le secret est créé et ajouté à Key Vault.</span><span class="sxs-lookup"><span data-stu-id="755b2-225">The secret is created and added to Key Vault.</span></span>
    9. <span data-ttu-id="755b2-226">Accédez à **Vue d’ensemble de Key Vault**, et notez le nom DNS.</span><span class="sxs-lookup"><span data-stu-id="755b2-226">Go to the **Key Vault Overview**, and make a note of the DNS name.</span></span>

3. <span data-ttu-id="755b2-227">Créer et enregistrer une application Azure AD :</span><span class="sxs-lookup"><span data-stu-id="755b2-227">Create and register an Azure AD application:</span></span>

    1. <span data-ttu-id="755b2-228">Dans le [portail Azure](https://portal.azure.com), accédez à **Azure Active Directory**, puis sélectionnez **Inscriptions d’applications**.</span><span class="sxs-lookup"><span data-stu-id="755b2-228">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and then select **App registrations**.</span></span>
    2. <span data-ttu-id="755b2-229">Sélectionnez **Inscription d’une nouvelle application** et définissez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="755b2-229">Select **New application registration**, and set the following fields:</span></span>

        - <span data-ttu-id="755b2-230">**Nom** : saisissez le nom de l’application.</span><span class="sxs-lookup"><span data-stu-id="755b2-230">**Name** – Enter the name of the app.</span></span>
        - <span data-ttu-id="755b2-231">**Type d’application** : sélectionnez **API Web**.</span><span class="sxs-lookup"><span data-stu-id="755b2-231">**Application type** – Select **Web API**.</span></span>
        - <span data-ttu-id="755b2-232">**Rediriger la configuration de l’URI** : saisissez l’URL de votre instance Dynamics 365, par exemple, `https://yourdynamicsinstance.dynamics.com/auth`.</span><span class="sxs-lookup"><span data-stu-id="755b2-232">**Redirect URI setup** – Enter the URL for your Dynamics 365 instance, such as, `https://yourdynamicsinstance.dynamics.com/auth`.</span></span>

    3. <span data-ttu-id="755b2-233">Accédez à l’application que vous venez de créer, copiez et enregistrez sa valeur **ID de l’application (client)**.</span><span class="sxs-lookup"><span data-stu-id="755b2-233">Go to the app that you just created, and copy and save its **Application (client) ID** value.</span></span> <span data-ttu-id="755b2-234">Vous devrez fournir cette valeur ultérieurement, lors de la configuration du coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="755b2-234">You will have to provide this value later, when you set up the key vault.</span></span>
    4. <span data-ttu-id="755b2-235">Accédez à **Autorisations API** et suivez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="755b2-235">Go to **API permissions**, and follow these steps:</span></span>

        1. <span data-ttu-id="755b2-236">Sélectionnez **Ajouter une autorisation**.</span><span class="sxs-lookup"><span data-stu-id="755b2-236">Select **Add a permission**.</span></span>
        2. <span data-ttu-id="755b2-237">Sélectionnez **Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="755b2-237">Select **Azure Key vault**.</span></span>
        3. <span data-ttu-id="755b2-238">Après avoir sélectionné les autorisations déléguées, sélectionnez **utilisateur\_emprunt d’identité**.</span><span class="sxs-lookup"><span data-stu-id="755b2-238">After you select delegated permissions, select **user\_impersonation**.</span></span>
        4. <span data-ttu-id="755b2-239">Sélectionnez **Ajouter des autorisations**.</span><span class="sxs-lookup"><span data-stu-id="755b2-239">Select **Add permissions**.</span></span>

    5. <span data-ttu-id="755b2-240">Dans le menu de l’application, sélectionnez **Certificats \& secrets**, puis suivez ces étapes pour créer des secrets Key Vault :</span><span class="sxs-lookup"><span data-stu-id="755b2-240">On the menu for the app, select **Certificates \& secrets**, and then follow these steps to create Key Vault secrets:</span></span>

        1. <span data-ttu-id="755b2-241">Sélectionnez **Nouvelle clé secrète client**.</span><span class="sxs-lookup"><span data-stu-id="755b2-241">Select **New client secret**.</span></span>
        2. <span data-ttu-id="755b2-242">Entrez un nom dans le champ **Description clé**.</span><span class="sxs-lookup"><span data-stu-id="755b2-242">In the **Key Description** field, enter a name.</span></span>
        3. <span data-ttu-id="755b2-243">Sélectionnez une durée, puis **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="755b2-243">Select a duration, and then select **Add**.</span></span> <span data-ttu-id="755b2-244">Un secret est généré dans le champ **Valeur**.</span><span class="sxs-lookup"><span data-stu-id="755b2-244">A secret is generated in the **Value** field.</span></span>
        4. <span data-ttu-id="755b2-245">Copiez et enregistrez la valeur secrète.</span><span class="sxs-lookup"><span data-stu-id="755b2-245">Copy and save the secret value.</span></span>

4. <span data-ttu-id="755b2-246">Créer des secrets Key Vault :</span><span class="sxs-lookup"><span data-stu-id="755b2-246">Create Key Vault secrets:</span></span>

    1. <span data-ttu-id="755b2-247">Accédez au coffre de clés que vous avez créé précédemment et sélectionnez **Secrets**.</span><span class="sxs-lookup"><span data-stu-id="755b2-247">Go to the key vault that you created earlier, and select **Secrets**.</span></span>
    2. <span data-ttu-id="755b2-248">Pour chaque nom de secret dans le tableau suivant, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="755b2-248">For each secret name in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="755b2-249">Sélectionnez **Générer/Importer**.</span><span class="sxs-lookup"><span data-stu-id="755b2-249">Select **Generate/Import**.</span></span>
        2. <span data-ttu-id="755b2-250">Dans la boîte de dialogue **Créer un secret**, dans le champ **Options de téléchargement**, sélectionnez **Manuel**.</span><span class="sxs-lookup"><span data-stu-id="755b2-250">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
        3. <span data-ttu-id="755b2-251">Créez le nom et la valeur du secret à partir du tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="755b2-251">Create the secret name and value from the following table.</span></span>
        4. <span data-ttu-id="755b2-252">Sélectionnez **Activé**, puis sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="755b2-252">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="755b2-253">Le secret est créé et ajouté à Key Vault.</span><span class="sxs-lookup"><span data-stu-id="755b2-253">The secret is created and added to Key Vault.</span></span>

        | <span data-ttu-id="755b2-254">Nom du secret</span><span class="sxs-lookup"><span data-stu-id="755b2-254">Secret name</span></span>                       | <span data-ttu-id="755b2-255">Valeur secrète</span><span class="sxs-lookup"><span data-stu-id="755b2-255">Secret value</span></span>                                                                                |
        |-----------------------------------|---------------------------------------------------------------------------------------------|
        | <span data-ttu-id="755b2-256">app-id</span><span class="sxs-lookup"><span data-stu-id="755b2-256">app-id</span></span>                            | <span data-ttu-id="755b2-257">L’ID d’application de l’application que vous avez créée précédemment</span><span class="sxs-lookup"><span data-stu-id="755b2-257">The app ID of the application that you created earlier</span></span>                                      |
        | <span data-ttu-id="755b2-258">app-secret</span><span class="sxs-lookup"><span data-stu-id="755b2-258">app-secret</span></span>                        | <span data-ttu-id="755b2-259">Le secret client que vous avez enregistré précédemment</span><span class="sxs-lookup"><span data-stu-id="755b2-259">The client secret that you saved earlier</span></span>                                                    |
        | <span data-ttu-id="755b2-260">storage-account-name</span><span class="sxs-lookup"><span data-stu-id="755b2-260">storage-account-name</span></span>              | <span data-ttu-id="755b2-261">Le nom du compte de stockage que vous avez créé précédemment, tel que **storageaccount1**</span><span class="sxs-lookup"><span data-stu-id="755b2-261">The name of the storage account that you created earlier, such as **storageaccount1**</span></span>       |
        | <span data-ttu-id="755b2-262">storage-account-connection-string</span><span class="sxs-lookup"><span data-stu-id="755b2-262">storage-account-connection-string</span></span> | <span data-ttu-id="755b2-263">La chaîne de connexion que vous avez copiée à partir de la page **Clés d’accès** pour le compte de stockage</span><span class="sxs-lookup"><span data-stu-id="755b2-263">The connection string that you copied from the **Access keys** page for the storage account</span></span> |

5. <span data-ttu-id="755b2-264">Autorisez l’application à accéder au coffre de clés :</span><span class="sxs-lookup"><span data-stu-id="755b2-264">Authorize the application to access the key vault:</span></span>

    1. <span data-ttu-id="755b2-265">Dans le [portail Azure](https://portal.azure.com), ouvrez le coffre de clés que vous avez créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="755b2-265">In the [Azure portal](https://portal.azure.com), open the key vault that you created earlier.</span></span>
    2. <span data-ttu-id="755b2-266">Sélectionnez les politiques d’accès.</span><span class="sxs-lookup"><span data-stu-id="755b2-266">Select the access policies.</span></span>
    3. <span data-ttu-id="755b2-267">Pour chaque application dans le tableau suivant, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="755b2-267">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="755b2-268">Pour créer une stratégie d’accès, sélectionnez **Ajouter une stratégie d’accès**.</span><span class="sxs-lookup"><span data-stu-id="755b2-268">Select **Add Access Policy** to create an access policy.</span></span>
        2. <span data-ttu-id="755b2-269">Dans le champ **Autorisations secrètes**, sélectionnez les autorisations dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="755b2-269">In the **Secret permissions** field, select the permissions from the following table.</span></span>
        3. <span data-ttu-id="755b2-270">Dans le champ **Sélectionner le principal**, recherchez le nom d’affichage de l’application dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="755b2-270">In the **Select principal** field, search for the application display name from the following table.</span></span>
        4. <span data-ttu-id="755b2-271">Cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="755b2-271">Select **Select**.</span></span>
        5. <span data-ttu-id="755b2-272">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="755b2-272">Select **Add**.</span></span>
        6. <span data-ttu-id="755b2-273">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="755b2-273">Select **Save**.</span></span>

        | <span data-ttu-id="755b2-274">Demande</span><span class="sxs-lookup"><span data-stu-id="755b2-274">Application</span></span>                                              | <span data-ttu-id="755b2-275">Autorisations</span><span class="sxs-lookup"><span data-stu-id="755b2-275">Permissions</span></span> |
        |----------------------------------------------------------|-------------|
        | <span data-ttu-id="755b2-276">Le nom d’affichage de la nouvelle application que vous avez créée</span><span class="sxs-lookup"><span data-stu-id="755b2-276">The display name of the new application that you created</span></span> | <span data-ttu-id="755b2-277">Obtenir, liste</span><span class="sxs-lookup"><span data-stu-id="755b2-277">Get, List</span></span>   |
        | <span data-ttu-id="755b2-278">**Microservices ERP Microsoft Dynamics**</span><span class="sxs-lookup"><span data-stu-id="755b2-278">**Microsoft Dynamics ERP Microservices**</span></span>                 | <span data-ttu-id="755b2-279">Obtenir, liste</span><span class="sxs-lookup"><span data-stu-id="755b2-279">Get, List</span></span>   |

6. <span data-ttu-id="755b2-280">Attribuez des rôles pour accéder au compte de stockage :</span><span class="sxs-lookup"><span data-stu-id="755b2-280">Assign roles to access the storage account:</span></span>

    1. <span data-ttu-id="755b2-281">Dans le [portail Azure](https://portal.azure.com), ouvrez le compte de stockage que vous avez créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="755b2-281">In the [Azure portal](https://portal.azure.com), open the storage account that you created earlier.</span></span>
    2. <span data-ttu-id="755b2-282">Sélectionnez **Contrôle d’accès (IAM)**, puis sélectionnez **Attributions de rôle**.</span><span class="sxs-lookup"><span data-stu-id="755b2-282">Select **Access Control (IAM)**, and then select **Role Assignments**.</span></span>
    3. <span data-ttu-id="755b2-283">Sélectionnez **Ajouter, Ajouter une attribution de rôle**.</span><span class="sxs-lookup"><span data-stu-id="755b2-283">Select **Add, Add Role Assignment**.</span></span>
    4. <span data-ttu-id="755b2-284">Pour chaque application dans le tableau suivant, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="755b2-284">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="755b2-285">Sélectionnez le rôle depuis la table suivante.</span><span class="sxs-lookup"><span data-stu-id="755b2-285">Select the role from the following table.</span></span>
        2. <span data-ttu-id="755b2-286">Laissez le champ **Affecter l’accès** défini sur **Utilisateur, groupe ou service principal Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="755b2-286">Leave the **Assign access to** field set to **Azure AD user, group, or service principal**.</span></span>
        3. <span data-ttu-id="755b2-287">Dans le champ **Sélectionner**, saisissez l’application dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="755b2-287">In the **Select** field, enter the application from the following table.</span></span>
        4. <span data-ttu-id="755b2-288">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="755b2-288">Select **Save**.</span></span>

        | <span data-ttu-id="755b2-289">Demande</span><span class="sxs-lookup"><span data-stu-id="755b2-289">Application</span></span>                                              | <span data-ttu-id="755b2-290">Rôle</span><span class="sxs-lookup"><span data-stu-id="755b2-290">Role</span></span>                        |
        |----------------------------------------------------------|-----------------------------|
        | <span data-ttu-id="755b2-291">Le nom d’affichage de la nouvelle application que vous avez créée</span><span class="sxs-lookup"><span data-stu-id="755b2-291">The display name of the new application that you created</span></span> | <span data-ttu-id="755b2-292">Propriétaire</span><span class="sxs-lookup"><span data-stu-id="755b2-292">Owner</span></span>                       |
        | <span data-ttu-id="755b2-293">Le nom d’affichage de la nouvelle application que vous avez créée</span><span class="sxs-lookup"><span data-stu-id="755b2-293">The display name of the new application that you created</span></span> | <span data-ttu-id="755b2-294">Contributeur</span><span class="sxs-lookup"><span data-stu-id="755b2-294">Contributor</span></span>                 |
        | <span data-ttu-id="755b2-295">Le nom d’affichage de la nouvelle application que vous avez créée</span><span class="sxs-lookup"><span data-stu-id="755b2-295">The display name of the new application that you created</span></span> | <span data-ttu-id="755b2-296">Contributeur de compte de stockage</span><span class="sxs-lookup"><span data-stu-id="755b2-296">Storage Account Contributor</span></span> |
        | <span data-ttu-id="755b2-297">Le nom d’affichage de la nouvelle application que vous avez créée</span><span class="sxs-lookup"><span data-stu-id="755b2-297">The display name of the new application that you created</span></span> | <span data-ttu-id="755b2-298">Propriétaire des données de l’objet blob de stockage</span><span class="sxs-lookup"><span data-stu-id="755b2-298">Storage Blob Data Owner</span></span>     |
        | <span data-ttu-id="755b2-299">**Service d’autorisation AI Builder**</span><span class="sxs-lookup"><span data-stu-id="755b2-299">**AI Builder Authorization Service**</span></span>                     | <span data-ttu-id="755b2-300">Lecteur de données de l’objet blob de stockage</span><span class="sxs-lookup"><span data-stu-id="755b2-300">Storage Blob Data Reader</span></span>    |

# <a name="azure-cli"></a>[<span data-ttu-id="755b2-301">Service de contrôle d’accès Azure (CLI)</span><span class="sxs-lookup"><span data-stu-id="755b2-301">Azure CLI</span></span>](#tab/azure-azure-cli)

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

## <a name="configure-the-entity-store"></a><span data-ttu-id="755b2-302">Configurer le magasin des entités</span><span class="sxs-lookup"><span data-stu-id="755b2-302">Configure the entity store</span></span>

<span data-ttu-id="755b2-303">Suivez ces étapes pour configurer le magasin des entités dans votre environnement Finance.</span><span class="sxs-lookup"><span data-stu-id="755b2-303">Follow these steps to set up the entity store in your Finance environment.</span></span>

1. <span data-ttu-id="755b2-304">Accédez à **Administration système \> Paramétrage \> Paramètres système \> Connexions des données**.</span><span class="sxs-lookup"><span data-stu-id="755b2-304">Go to **System administration \> Setup \> System parameters \> Data connections**.</span></span>
2. <span data-ttu-id="755b2-305">Définissez l’option **Activer l’intégration de Data Lake** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="755b2-305">Set the **Enable Data Lake integration** option to **Yes**.</span></span>
3. <span data-ttu-id="755b2-306">Définissez les champs Key Vault suivants :</span><span class="sxs-lookup"><span data-stu-id="755b2-306">Set the following Key Vault fields:</span></span>

    - <span data-ttu-id="755b2-307">**ID de l’application (client)**  : saisissez l’ID client d’application que vous avez créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="755b2-307">**Application (client) ID** – Enter the application client ID that you created earlier.</span></span>
    - <span data-ttu-id="755b2-308">**Secret d’application** : entrez le secret que vous avez enregistré pour l’application que vous avez créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="755b2-308">**Application Secret** – Enter the secret that you saved for the application that you created earlier.</span></span>
    - <span data-ttu-id="755b2-309">**Nom DNS** : vous pouvez trouver le nom DNS (Domain Name System) sur la page des détails de l’application que vous avez créée précédemment.</span><span class="sxs-lookup"><span data-stu-id="755b2-309">**DNS name** – You can find the Domain Name System (DNS) name on the application details page for the application that you created earlier.</span></span>
    - <span data-ttu-id="755b2-310">**Nom secret** : saisissez **storage-account-connection-string**.</span><span class="sxs-lookup"><span data-stu-id="755b2-310">**Secret name** – Enter **storage-account-connection-string**.</span></span>

## <a name="configure-the-data-lake"></a><span data-ttu-id="755b2-311">Configurer le lac de données</span><span class="sxs-lookup"><span data-stu-id="755b2-311">Configure the data lake</span></span>

<span data-ttu-id="755b2-312">Suivez ces étapes pour utiliser LCS pour ajouter le complément Azure Data Lake à l’environnement.</span><span class="sxs-lookup"><span data-stu-id="755b2-312">Follow these steps to use LCS to add the Azure Data Lake add-in to the environment.</span></span>

1. <span data-ttu-id="755b2-313">Connectez-vous à LCS, puis, sous le nom de l’environnement sur le côté droit de la page, sélectionnez **Tous les détails**.</span><span class="sxs-lookup"><span data-stu-id="755b2-313">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="755b2-314">Dans la section **Compléments de l’environnement**, sélectionnez **Installer un nouveau complément**.</span><span class="sxs-lookup"><span data-stu-id="755b2-314">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="755b2-315">Sélectionnez le complément **Exporter vers Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="755b2-315">Select the **Export to Data Lake** add-in.</span></span>
4. <span data-ttu-id="755b2-316">Saisissez les valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="755b2-316">Enter the following values.</span></span>

    | <span data-ttu-id="755b2-317">Valeur</span><span class="sxs-lookup"><span data-stu-id="755b2-317">Value</span></span>                                                              | <span data-ttu-id="755b2-318">Description</span><span class="sxs-lookup"><span data-stu-id="755b2-318">Description</span></span> |
    |--------------------------------------------------------------------|-------------|
    | <span data-ttu-id="755b2-319">ID de locataire de l’abonnement Azure où se trouve le coffre de clés</span><span class="sxs-lookup"><span data-stu-id="755b2-319">Tenant ID of the Azure Subscription where the Key Vault is located</span></span> | <span data-ttu-id="755b2-320">ID de locataire où se trouvent le compte de stockage, les applications et les coffres de clés.</span><span class="sxs-lookup"><span data-stu-id="755b2-320">The tenant ID where the storage account, apps, and key vaults are located.</span></span> <span data-ttu-id="755b2-321">Pour trouver cette valeur, ouvrez le [Portail Azure](https://portal.azure.com), accédez à **Azure Active Directory**, et copiez la valeur **ID du locataire**.</span><span class="sxs-lookup"><span data-stu-id="755b2-321">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="755b2-322">Fournir le nom DNS de votre Key Vault</span><span class="sxs-lookup"><span data-stu-id="755b2-322">Provide the DNS name of your Key Vault</span></span>                             | <span data-ttu-id="755b2-323">Nom DNS du coffre de clés, tel que `https://customkeyvault.vault.azure.net/`.</span><span class="sxs-lookup"><span data-stu-id="755b2-323">The DNS name of the key vault, such as `https://customkeyvault.vault.azure.net/`.</span></span> <span data-ttu-id="755b2-324">(Cette valeur correspond au nom DNS utilisé dans le magasin d’entités.)</span><span class="sxs-lookup"><span data-stu-id="755b2-324">(This value matches the DNS name that is used in the entity store.)</span></span> |
    | <span data-ttu-id="755b2-325">Fournir le secret contenant le nom du compte de stockage</span><span class="sxs-lookup"><span data-stu-id="755b2-325">Provide the secret that contains the name of the storage account</span></span>   | <span data-ttu-id="755b2-326">**storage-account-name**</span><span class="sxs-lookup"><span data-stu-id="755b2-326">**storage-account-name**</span></span> |
    | <span data-ttu-id="755b2-327">Nom secret de l’ID d’application à utiliser pour accéder à Data Lake</span><span class="sxs-lookup"><span data-stu-id="755b2-327">Secret Name for App ID to be used for accessing Data Lake</span></span>          | <span data-ttu-id="755b2-328">**app-id**</span><span class="sxs-lookup"><span data-stu-id="755b2-328">**app-id**</span></span> |
    | <span data-ttu-id="755b2-329">Nom secret à utiliser avec l’ID de l’application</span><span class="sxs-lookup"><span data-stu-id="755b2-329">Secret name to be used with App ID</span></span>                                 | <span data-ttu-id="755b2-330">**app-secret**</span><span class="sxs-lookup"><span data-stu-id="755b2-330">**app-secret**</span></span> |

5. <span data-ttu-id="755b2-331">Acceptez les conditions et sélectionnez **Installer**.</span><span class="sxs-lookup"><span data-stu-id="755b2-331">Agree to the terms, and select **Install**.</span></span>

<span data-ttu-id="755b2-332">Le complément sera installé dans quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="755b2-332">The add-in will be installed within a few minutes.</span></span>

## <a name="configure-ai-builder"></a><span data-ttu-id="755b2-333">Configurer AI Builder</span><span class="sxs-lookup"><span data-stu-id="755b2-333">Configure AI Builder</span></span>

1. <span data-ttu-id="755b2-334">Connectez-vous à LCS, et ouvrez la page **Détails de l’environnement**.</span><span class="sxs-lookup"><span data-stu-id="755b2-334">Sign in to LCS, and open the **Environment details** page.</span></span>
2. <span data-ttu-id="755b2-335">Faites défiler jusqu’à la section **Compléments d’environnement**.</span><span class="sxs-lookup"><span data-stu-id="755b2-335">Scroll to the **Environment add-ins** section.</span></span> <span data-ttu-id="755b2-336">Vous devriez voir les compléments qui sont déjà installés dans cet environnement.</span><span class="sxs-lookup"><span data-stu-id="755b2-336">You should see the add-ins that are already installed in this environment.</span></span> <span data-ttu-id="755b2-337">Si le complément **Exporter vers Data Lake** n’est pas parmi eux, configurez ce complément.</span><span class="sxs-lookup"><span data-stu-id="755b2-337">If the **Export to Data Lake** add-in isn't among them, configure this add-in.</span></span>
3. <span data-ttu-id="755b2-338">Sélectionnez le complément **Obtenir des informations**.</span><span class="sxs-lookup"><span data-stu-id="755b2-338">Select the **Get insights** add-in.</span></span>
4. <span data-ttu-id="755b2-339">Sur la page des détails du complément **Obtenir des informations**, entrez les valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="755b2-339">On the **Get insights** add-in details page, enter the following values.</span></span>

    | <span data-ttu-id="755b2-340">Valeur</span><span class="sxs-lookup"><span data-stu-id="755b2-340">Value</span></span>                                                    | <span data-ttu-id="755b2-341">Description</span><span class="sxs-lookup"><span data-stu-id="755b2-341">Description</span></span> |
    |----------------------------------------------------------|-------------|
    | <span data-ttu-id="755b2-342">URL de l’organisation CDS</span><span class="sxs-lookup"><span data-stu-id="755b2-342">CDS Organization URL</span></span>                                     | <span data-ttu-id="755b2-343">L’URL de l’organisation Dataverse de l’instance Dataverse.</span><span class="sxs-lookup"><span data-stu-id="755b2-343">The Dataverse organization URL of the Dataverse instance.</span></span> <span data-ttu-id="755b2-344">Pour trouver cette valeur, ouvrez le [portail Power Apps](https://make.powerapps.com), sélectionnez le bouton **Réglages** (symbole d’engrenage) dans le coin supérieur droit, sélectionnez **Paramètres avancés** et copiez l’URL.</span><span class="sxs-lookup"><span data-stu-id="755b2-344">To find this value, open the [Power Apps portal](https://make.powerapps.com), select the **Settings** button (gear symbol) in the upper-right upper corner, select **Advanced settings**, and copy the URL.</span></span> <span data-ttu-id="755b2-345">(L’URL se termine par « dynamics.com ».)</span><span class="sxs-lookup"><span data-stu-id="755b2-345">(The URL ends with "dynamics.com.")</span></span> |
    | <span data-ttu-id="755b2-346">ID org. CDS</span><span class="sxs-lookup"><span data-stu-id="755b2-346">CDS Org ID</span></span>                                               | <span data-ttu-id="755b2-347">L’ID d’environnement de l’instance Dataverse.</span><span class="sxs-lookup"><span data-stu-id="755b2-347">The environment ID of the Dataverse instance.</span></span> <span data-ttu-id="755b2-348">Pour trouver cette valeur, ouvrez le [portail Power Apps](https://make.powerapps.com), sélectionnez le bouton **Paramètres** (symbole d’engrenage) dans le coin supérieur droit, sélectionnez **Personnalisations \> Ressources du développeur \> Informations de référence de l’instance** et copiez la valeur **ID**.</span><span class="sxs-lookup"><span data-stu-id="755b2-348">To find this value, open the [Power Apps portal](https://make.powerapps.com), select the **Settings** button (gear symbol) in the upper-right upper corner, select **Customizations \> Developer resources \> Instance Reference Information**, and copy the **ID** value.</span></span> |
    | <span data-ttu-id="755b2-349">ID de locataire CDS (ID d’annuaire d’AAD)</span><span class="sxs-lookup"><span data-stu-id="755b2-349">CDS Tenant ID (Directory ID from AAD)</span></span>               | <span data-ttu-id="755b2-350">L’ID de locataire de l’instance Dataverse.</span><span class="sxs-lookup"><span data-stu-id="755b2-350">The tenant ID of the Dataverse instance.</span></span> <span data-ttu-id="755b2-351">Pour trouver cette valeur, ouvrez le [Portail Azure](https://portal.azure.com), accédez à **Azure Active Directory**, et copiez la valeur **ID du locataire**.</span><span class="sxs-lookup"><span data-stu-id="755b2-351">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="755b2-352">Fournissez l’ID objet utilisateur qui dispose du rôle d’administrateur système</span><span class="sxs-lookup"><span data-stu-id="755b2-352">Provide user object ID who has system administrator role</span></span> | <span data-ttu-id="755b2-353">ID d’objet d’utilisateur Azure AD dans Dataverse.</span><span class="sxs-lookup"><span data-stu-id="755b2-353">The Azure AD user object ID of the user in Dataverse.</span></span> <span data-ttu-id="755b2-354">Cet utilisateur doit être un administrateur système de l’instance Dataverse.</span><span class="sxs-lookup"><span data-stu-id="755b2-354">This user must be a system administrator of the Dataverse instance.</span></span> <span data-ttu-id="755b2-355">Pour trouver cette valeur, ouvrez le [portail Azure](https://portal.azure.com), accédez à **Azure Active Directory\> Utilisateurs**, sélectionnez l’utilisateur, puis, dans la section **Identité**, copiez la valeur **ID d’objet**.</span><span class="sxs-lookup"><span data-stu-id="755b2-355">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory \> Users**, select the user, and then, in the **Identity** section, copy the **Object ID** value.</span></span> |
    | <span data-ttu-id="755b2-356">S’agit-il de l’environnement CDS par défaut pour le locataire ?</span><span class="sxs-lookup"><span data-stu-id="755b2-356">Is this the default CDS environment for the tenant?</span></span>      | <span data-ttu-id="755b2-357">Si l’instance Dataverse a été la première instance de production créée, cochez cette case.</span><span class="sxs-lookup"><span data-stu-id="755b2-357">If the Dataverse instance was the first production instance that was created, select this check box.</span></span> <span data-ttu-id="755b2-358">Si l’instance Dataverse a été créée manuellement, décochez cette case.</span><span class="sxs-lookup"><span data-stu-id="755b2-358">If the Dataverse instance was manually created, clear this check box.</span></span> |

## <a name="feedback-and-support"></a><span data-ttu-id="755b2-359">Commentaires et support</span><span class="sxs-lookup"><span data-stu-id="755b2-359">Feedback and support</span></span>

<span data-ttu-id="755b2-360">Veuillez envoyer un e-mail à [Informations sur les paiements des clients (aperçu)](mailto:fiap@microsoft.com) si vous souhaitez fournir des commentaires ou si vous avez besoin d’aide.</span><span class="sxs-lookup"><span data-stu-id="755b2-360">Please send an email to [Customer payment insights (Preview)](mailto:fiap@microsoft.com) if you are interested in providing feedback or need support.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="755b2-361">Avis de confidentialité</span><span class="sxs-lookup"><span data-stu-id="755b2-361">Privacy notice</span></span>

<span data-ttu-id="755b2-362">Les versions préliminaires (1) peuvent utiliser moins de mesures de confidentialité et de sécurité que le service Dynamics 365 Finance and Operations, (2) ne sont pas inclus dans le contrat de niveau de service (SLA) pour ce service, (3) ne doivent pas être utilisés pour traiter des données personnelles ou autres données soumises à des exigences de conformité juridique ou réglementaire, et (4) bénéficient d’un support limité.</span><span class="sxs-lookup"><span data-stu-id="755b2-362">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]