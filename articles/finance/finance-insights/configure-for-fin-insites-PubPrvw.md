---
title: Configuration pour Finance Insights – versions 10.0.20 et ultérieures
description: Cet article explique comment configurer votre système pour utiliser les fonctionnalités disponibles dans Finance Insights pour la version 10.0.20 et les versions ultérieures.
author: ShivamPandey-msft
ms.date: 06/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
ROBOTS: noindex,nofollow
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-06-03
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: d05403113c9b178553134ce1a9066bb2acf59b0f
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9068103"
---
# <a name="configuration-for-finance-insights---version-10020-and-later"></a>Configuration pour Finance Insights – versions 10.0.20 et ultérieures

[!include [banner](../includes/banner.md)]



Finance Insights combine les fonctionnalités de Microsoft Dynamics 365 Finance avec Dataverse, Azure et AI Builder pour fournir de puissants outils de prévision à votre organisation. Cet article explique comment configurer Dynamics 365 Finance version 10.0.20 pour que votre système puisse utiliser les fonctionnalités disponibles dans Finance Insights.

> [!NOTE]
> Les étapes de configuration décrites dans cet article s’appliquent uniquement à Finance, version 10.0.20 et versions ultérieures. Pour configurer Finance Insights version 10.0.19 et versions ultérieures, voir [Configuration de Finance insights – versions jusqu’à 10.0.19](configure-for-fin-insites.md).

## <a name="deploy-finance"></a>Déploiement de Finance

Procédez comme suit pour déployer les environnements.

1. Dans Microsoft Dynamics Lifecycle Services (LCS), créez ou mettez à jour un environnement Finance. L’environnement nécessite la version 10.0.20 ou ultérieure des applications de finances et d’opérations.
2. L’environnement doit être un environnement haute disponibilité (HA) dans Sandbox. (Ce type d’environnement est également appelé environnement de niveau 2.) Pour plus d’informations, voir [Planification de l’environnement](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).
3. Si vous configurez Finance Insights dans un environnement bac à sable, vous devrez peut-être copier les données de production dans cet environnement pour que les prédictions fonctionnent. Le modèle de prédiction utilise plusieurs années de données pour créer les prédictions. Les données de démonstration de Contoso ne contiennent pas suffisamment de données historiques pour entraîner comme il se doit le modèle de prédiction. 

## <a name="configure-dataverse"></a>Configurer Dataverse

Procédez comme suit pour configurer Dataverse pour Finance Insights.

1. Dans LCS, ouvrez la page d’environnement et vérifiez que la section **Intégration Power Platform** est déjà configurée.

    - Si elle est déjà configurée, le nom d’environnement Dataverse lié à l’environnement Finance doit être répertorié.
    - Si elle n’est pas encore configurée, procédez comme suit :

        1. Dans la section **Intégration Power Platform**, sélectionnez **Configurer**. La configuration de l’environnement peut prendre jusqu’à une heure.
        2. Si l’environnement Dataverse est correctement configuré, le nom de l’environnement Dataverse lié à l’environnement Finance devrait figurer dans la liste.

        > [!NOTE]
        > Après avoir terminé la configuration de l’environnement, **ne sélectionnez pas** **Lien vers CDS for Apps**. Ce bouton n’est pas requis pour Finance Insights. Si vous le sélectionnez, vous ne pourrez pas configurer les compléments d’environnement requis dans LCS.

## <a name="configure-azure"></a>Configurer Azure

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a>Utiliser Azure Cloud Shell pour configurer les ressources Data Lake de Finance Insights

# <a name="use-a-windows-powershell-script"></a>[Utiliser un script de configuration Windows PowerShell](#tab/use-a-powershell-script)

Un script Windows PowerShell a été fourni pour que vous puissiez facilement configurer les ressources Azure décrites dans [Configurer l’exportation vers Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md). Si vous préférez effectuer une configuration manuelle, ignorez cette procédure et suivez la procédure de la section [Configuration manuelle](#manual-setup) à la place.

> [!NOTE]
> Utilisez la procédure suivante pour exécuter le script Windows PowerShell. La configuration peut ne pas fonctionner si vous utilisez l’option **Essayer** dans Azure CLI ou si vous exécutez le script sur votre ordinateur.

Suivez ces étapes pour utiliser le script Windows PowerShell pour configurer Azure. Vous devez disposer des droits pour créer un groupe de ressources Azure, des ressources Azure et une application Azure AD. Pour plus d’informations sur les autorisations requises, voir [Vérifier les autorisations Azure AD](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).

1. Dans le [portail Azure](https://portal.azure.com), accédez à votre abonnement Azure cible.
2. Sélectionnez **Cloud Shell** à droite du champ **Recherche**.
3. Sélectionnez **PowerShell**.
4. Créez un espace de stockage, si vous êtes invité à le faire.
5. Dans l’onglet **Azure CLI**, sélectionnez **Copier**.
6. Dans le Bloc-notes, ouvrez un nouveau fichier et collez le script Windows PowerShell.
7. Enregistrez le fichier sous **ConfigureDataLake.ps1**.
8. Téléchargez le script Windows PowerShell dans la session à l’aide de l’option de menu pour le chargement dans Cloud Shell.
9. Exécutez le script **.\ConfigureDataLake.ps1**.
10. Suivez les invites pour exécuter le script.
11. Utilisez les informations de la sortie du script pour installer le complément Exporter vers Data Lake dans LCS.

### <a name="manual-setup"></a>Configuration manuelle

#### <a name="add-applications-to-the-azure-ad-tenant"></a>Ajouter des applications au locataire Azure AD

1. Dans le [portail Azure](https://portal.azure.com), accédez à **Azure Active Directory**.
2. Sélectionnez **Gérer \> Applications de l’entreprise**.
3. Recherchez les applications suivantes par ID d’application.

    | Demande                              | ID d’application                               |
    |------------------------------------------|--------------------------------------|
    | Microservices ERP Microsoft Dynamics     | 0cdb527f-a8d1-4bf8-9436-b352c68682b2 |
    | CDS Microservices ERP Microsoft Dynamics | 703e2651-d3fc-48f5-942c-74274233dba8 |
    | Service d’autorisation AI Builder         | ad40333e-9910-4b61-b281-e3aeeb8c3ef3 |

Si vous ne trouvez aucune des applications précédentes, essayez les étapes suivantes.

1. Sur votre ordinateur local, sélectionnez le menu **Démarrer** et recherchez **powershell**.
2. Sélectionnez et maintenez (ou cliquez avec le bouton droit) sur **Windows PowerShell**, puis sélectionnez **Exécuter en tant qu’administrateur**.
3. Exécutez la commande suivante pour installer le module **AzureAD**.

    `Install-Module -Name AzureAD`

4. Si un fournisseur NuGet doit continuer, sélectionnez **O** pour l’installer.
5. Si vous recevez un message « Référentiel non approuvé », sélectionnez **O** pour continuer.
6. Pour chaque application à ajouter, exécutez les commandes suivantes pour ajouter l’application à Azure AD. Lorsque vous y êtes invité, connectez-vous en tant qu’administrateur Azure AD.

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a>Créer des ressources Azure

> [!NOTE]
> Assurez-vous de créer les ressources suivantes dans la même instance Azure AD qui contient l’environnement Dataverse. Vous ne pouvez pas utiliser les ressources d’une autre instance Azure AD.

1. Création d’un compte de stockage :

    1. Dans le [portail Azure](https://portal.azure.com), créez un compte de stockage.
    2. Dans la boîte de dialogue **Créer un compte de stockage**, définissez les champs suivants :

        - **Emplacement** : sélectionnez le centre de données où se trouve votre environnement.
        - **Performance** : nous vous recommandons de sélectionner **Standard**.
        - **Type de compte** : vous devez sélectionner **StorageV2**.

    3. Dans la boîte de dialogue **Options avancées**, pour l’option **Stockage Data Lake Gen2**, sélectionnez **Activer** sous la fonctionnalité **Espaces de noms hiérarchiques**. Si vous n’activez pas cette fonctionnalité, vous ne pouvez pas consommer les données que les applications de finances et d’opérations écrivent à l’aide de services tels que les flux de données Power BI.
    4. Sélectionnez **Réviser et créer**. Une fois le déploiement terminé, la nouvelle ressource s’affiche dans le portail Azure.
    5. Accédez au compte de stockage que vous avez créé.
    6. Dans le menu de gauche, sélectionnez **Clés d’accès**.
    7. Copiez et enregistrez le nom du compte de stockage. Vous devrez fournir cette valeur ultérieurement, lors de la configuration des secrets du coffre de clés.

2. Création d’un coffre de clés :

    1. Dans le [portail Azure](https://portal.azure.com), créez un coffre de clés.
    2. Dans la boîte de dialogue **Créer un coffre de clés**, dans le champ **Emplacement**, sélectionnez le centre de données dans lequel se trouve votre environnement.
    3. Une fois le coffre de clés créé, accédez à **Vue d’ensemble de Key Vault**, puis copiez et enregistrez le nom DNS. Vous devrez fournir cette valeur ultérieurement, lors de la configuration du complément Data Lake.

3. Créer et enregistrer une application Azure AD :

    1. Dans le [portail Azure](https://portal.azure.com), accédez à **Azure Active Directory**, puis sélectionnez **Inscriptions d’applications**.
    2. Sélectionnez **Inscription d’une nouvelle application** et définissez les champs suivants :

        - **Nom** : saisissez le nom de l’application.
        - **Type d’application** : sélectionnez **API Web**.
        - **Rediriger la configuration de l’URI** : saisissez l’URL de votre instance Dynamics 365, par exemple `https://yourdynamicsinstance.dynamics.com/auth`.

    3. Accédez à l’application que vous venez de créer, copiez et enregistrez sa valeur **ID de l’application (client)**. Vous devrez fournir cette valeur ultérieurement, lors de la configuration des secrets du coffre de clés.
    4. Accédez à **Autorisations API** et suivez ces étapes :

        1. Sélectionnez **Ajouter une autorisation**.
        2. Sélectionnez **Azure Key Vault**.
        3. Après avoir sélectionné les autorisations déléguées, sélectionnez **utilisateur\_emprunt d’identité**.
        4. Sélectionnez **Ajouter des autorisations**.

    5. Dans le menu de l’application, sélectionnez **Certificats \& secrets**, puis suivez ces étapes pour créer des secrets Key Vault :

        1. Sélectionnez **Nouvelle clé secrète client**.
        2. Entrez un nom dans le champ **Description clé**.
        3. Sélectionnez une durée, puis **Ajouter**. Un secret est généré dans le champ **Valeur**.
        4. Copiez et enregistrez la clé secrète client. Vous devrez fournir cette valeur ultérieurement, lors de la configuration des secrets du coffre de clés.

4. Créer des secrets Key Vault :

    1. Accédez au coffre de clés que vous avez créé précédemment et sélectionnez **Secrets**.
    2. Pour chaque nom de secret dans le tableau suivant, procédez comme suit :

        1. Sélectionnez **Générer/Importer**.
        2. Dans la boîte de dialogue **Créer un secret**, dans le champ **Options de téléchargement**, sélectionnez **Manuel**.
        3. Créez le nom et la valeur du secret à partir du tableau.
        4. Sélectionnez **Activé**, puis sélectionnez **Créer**. Le secret est créé et ajouté à Key Vault.

        | Nom du secret                       | Valeur secrète                                                                                 |
        |-----------------------------------|----------------------------------------------------------------------------------------------|
        | app-id                            | L’ID d’application de l’application que vous avez créée précédemment.                                      |
        | app-secret                        | Le secret client que vous avez enregistré précédemment.                                                    |
        | storage-account-name              | Le nom du compte de stockage que vous avez créé précédemment, tel que **storageaccount1**.       |

5. Autorisez l’application à accéder au coffre de clés :

    1. Dans le [portail Azure](https://portal.azure.com), ouvrez le coffre de clés que vous avez créé précédemment.
    2. Sélectionnez les politiques d’accès.
    3. Pour chaque application dans le tableau suivant, procédez comme suit :

        1. Pour créer une stratégie d’accès, sélectionnez **Ajouter une stratégie d’accès**.
        2. Dans le champ **Autorisations secrètes**, sélectionnez les autorisations dans le tableau.
        3. Dans le champ **Sélectionner le principal**, recherchez le nom d’affichage de l’application dans le tableau.
        4. Cliquez sur **Sélectionner**.
        5. Sélectionnez **Ajouter**.
        6. Sélectionnez **Enregistrer**.

        | Demande                                              | Autorisations |
        |----------------------------------------------------------|-------------|
        | Le nom d’affichage de la nouvelle application que vous avez créée | Obtenir, liste   |
        | **Microservices ERP Microsoft Dynamics**                 | Obtenir, liste   |

6. Attribuez des rôles pour accéder au compte de stockage :

    1. Dans le [portail Azure](https://portal.azure.com), ouvrez le compte de stockage que vous avez créé précédemment.
    2. Sélectionnez **Contrôle d’accès (IAM)**, puis sélectionnez **Attributions de rôle**.
    3. Sélectionnez **Ajouter, Ajouter une attribution de rôle**.
    4. Pour chaque application dans le tableau suivant, procédez comme suit :

        1. Sélectionnez le rôle dans le tableau.
        2. Laissez le champ **Affecter l’accès** défini sur **Utilisateur, groupe ou service principal Azure AD**.
        3. Dans le champ **Sélectionner**, saisissez l’application dans le tableau.
        4. Sélectionnez **Enregistrer**.

        | Demande                                              | Rôle                        |
        |----------------------------------------------------------|-----------------------------|
        | Le nom d’affichage de la nouvelle application que vous avez créée | Propriétaire                       |
        | Le nom d’affichage de la nouvelle application que vous avez créée | Contributeur                 |
        | Le nom d’affichage de la nouvelle application que vous avez créée | Contributeur de compte de stockage |
        | Le nom d’affichage de la nouvelle application que vous avez créée | Propriétaire des données de l’objet blob de stockage     |
        | **Service d’autorisation AI Builder**                     | Lecteur de données de l’objet blob de stockage    |

# <a name="azure-cli"></a>[Service de contrôle d’accès Azure (CLI)](#tab/azure-azure-cli)

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

## <a name="configure-the-export-to-data-lake-add-in"></a>Configurer le complément Exporter vers Data Lake

Suivez ces étapes pour utiliser LCS pour ajouter le complément Exporter vers Data Lake à l’environnement.

1. Connectez-vous à LCS, puis, sous le nom de l’environnement sur le côté droit de la page, sélectionnez **Tous les détails**.
2. Dans la section **Compléments de l’environnement**, sélectionnez **Installer un nouveau complément**.
3. Sélectionnez le complément **Exporter vers Data Lake**.
4. Saisissez les valeurs suivantes.

    | Valeur                                                              | Description |
    |--------------------------------------------------------------------|-------------|
    | ID de locataire de l’abonnement Azure où se trouve le coffre de clés | ID de locataire où se trouvent le compte de stockage, les applications et les coffres de clés. Pour obtenir cette valeur, ouvrez le [Portail Azure](https://portal.azure.com), accédez à **Azure Active Directory**, et copiez la valeur **ID du locataire**. |
    | Fournir le nom DNS de votre Key Vault                             | Nom DNS du coffre de clés, tel que `https://customkeyvault.vault.azure.net/`. |
    | Fournir le secret contenant le nom du compte de stockage   | **storage-account-name** |
    | Nom secret de l’ID d’application à utiliser pour accéder à Data Lake          | **app-id** |
    | Nom secret du secret client de l’application                                  | **app-secret** |

5. Acceptez les conditions, puis sélectionnez **Installer**.

Le complément sera installé dans quelques minutes.

## <a name="configure-the-finance-insights-add-in"></a>Configurer le complément Finance Insights

> [!NOTE]
> Si vous avez déjà installé le complément Obtenir des informations, désinstallez-le avant de réaliser la procédure suivante.

Suivez ces étapes pour installer le complément Finance Insights.

1. Connectez-vous à LCS, puis, sous le nom de l’environnement sur le côté droit de la page, sélectionnez **Tous les détails**.
2. Dans la section **Compléments de l’environnement**, sélectionnez **Installer un nouveau complément**.
3. Sélectionnez le complément **Informations financières**.
4. Acceptez les conditions, puis sélectionnez **Installer**.

L’installation du complément peut prendre plusieurs minutes.

## <a name="feedback-and-support"></a>Commentaires et support

Si vous souhaitez fournir des commentaires ou si vous avez besoin d’aide, veuillez envoyer un e-mail à [Finance Insights](mailto:fiap@microsoft.com).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

