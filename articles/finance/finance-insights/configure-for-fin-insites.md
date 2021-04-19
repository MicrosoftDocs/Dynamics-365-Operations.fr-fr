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
ms.openlocfilehash: 2443bb057a8b7fe280ed26ecae4e50f671b5e082
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818797"
---
# <a name="configuration-for-finance-insights-preview"></a>Configuration de Finance Insights (version préliminaire)

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Finance Insights combine les fonctionnalités de Microsoft Dynamics 365 Finance avec Microsoft Dataverse, Azure et AI Builder pour fournir de puissants outils de prévision à votre organisation. Cette rubrique explique les étapes de configuration qui permettront à votre système d’utiliser les fonctionnalités disponibles dans Finance Insights.

## <a name="deploy-dynamics-365-finance"></a>Déployer Dynamics 365 Finance

Déployez les environnements comme suit.

1. Dans Microsoft Dynamics Lifecycle Services (LCS), créez ou mettez à jour un environnement Dynamics 365 Finance. L’environnement nécessite la version d’application 10.0.11/Platform update 35 ou version ultérieure.
2. L’environnement doit être un environnement haute disponibilité (HA) dans Sandbox. (Ce type d’environnement est également appelé environnement de niveau 2.) Pour plus d’informations, voir [Planification de l’environnement](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).
3. Si vous utilisez des données de démonstration Contoso, vous aurez besoin d’exemples de données supplémentaires pour utiliser les fonctionnalités de prévisions de paiement client, de prévisions de flux de trésorerie et de prévisions budgétaires. 

## <a name="configure-dataverse"></a>Configurer Dataverse

Vous pouvez effectuer les étapes de configuration manuelle suivantes, ou accélérer le processus de configuration à l’aide du script Windows PowerShell fourni. Une fois l’exécution du script PowerShell terminée, il vous donnera les valeurs à utiliser pour configurer Finance Insights. 

> [!NOTE]
> Ouvrez PowerShell sur votre ordinateur pour exécuter le script. Vous aurez peut-être besoin de PowerShell version 5. L’option « Essayer » de Microsoft Azure CLI risque de ne pas fonctionner.

# <a name="manual-configuration-steps"></a>[Étapes de configuration manuelle](#tab/configuration-steps)

1. Ouvrez le [centre d’administration Power Platform](https://admin.powerplatform.microsoft.com/) et suivez ces étapes pour créer un environnement Dataverse dans le même client Active Directory :

    1. Ouvrez la page **Environnements**.

        [![Page Environnements](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)

    2. Sélectionnez **Nouvel environnement**.
    3. Dans le champ **Type**, sélectionnez **Sandbox**.
    4. Définissez l’option **Créer une base de données** sur **Oui**.
    5. Sélectionnez **Suivant**.
    6. Sélectionnez la langue et la devise de votre organisation.
    7. Acceptez les valeurs par défaut dans les autres champs.
    8. Sélectionnez **Enregistrer**.
    9. Actualisez la page **Environnements**.
    10. Attendez que la valeur du champ **État** soit mise à jour sur la valeur **Prêt**.
    11. Prenez note de l’ID de l’organisation Dataverse.
    12. Sélectionnez l’environnement à copier, puis sélectionnez **Paramètres**.
    13. Sélectionnez **Ressources \> Tous les anciens paramètres**.
    14. Dans la barre de navigation supérieure, sélectionnez **Paramètres**, puis **Personnalisations**.
    15. Sélectionnez **Ressources du développeur**.
    16. Définissez le champ **ID d’informations de référence d’instance** sur la valeur d’ID d’organisation Dataverse que vous avez notée précédemment.
    17. Dans la barre d’adresse du navigateur, notez l’URL de l’organisation Dataverse. Par exemple, l’URL peut être `https://org42b2b3d3.crm.dynamics.com`.

2. Si vous prévoyez d’utiliser la fonctionnalité Prévisions de flux de trésorerie ou Prévisions budgétaires, procédez comme suit pour mettre à jour la limite d’annotation pour votre organisation à au moins 50 mégaoctets (Mo) :

    1. Ouvrez le portail [Power Apps](https://make.powerapps.com).
    2. Sélectionnez l’environnement que vous venez de créer, puis sélectionnez **Paramètres avancés**.
    3. Sélectionnez **Paramètres \> Configuration de messagerie**.
    4. Changez la valeur du champ **Taille maximale du fichier** sur **51 200**. (La valeur est exprimée en kilooctets \[Ko\].)
    5. Cliquez sur **OK** pour enregistrer vos modifications.

# <a name="windows-powershell-configuration-script"></a>[Script de configuration Windows PowerShell](#tab/powershell-configuration-script)

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

## <a name="configure-the-azure-setup"></a>Configurer la configuration Azure

### <a name="enter-the-dataverse-directory-id-and-the-users-azure-ad-object-id"></a>Saisir l’ID de répertoire Dataverse et l’ID d’objet Azure AD de l’utilisateur

1. Saisissez l’ID de répertoire Dataverse :

    1. Ouvrez le [Portail Azure](https://portal.azure.com).
    2. Connectez-vous en utilisant l’ID utilisateur qui a été utilisé pour créer l’environnement Dataverse.
    3. Atteindre **Azure Active Directory**.
    4. Copiez la valeur **ID du locataire**.

2. Saisissez l’ID d’objet Azure Active Directory (Azure AD) de l’utilisateur :

    1. Dans le [portail Azure](https://portal.azure.com), accédez à **Utilisateurs** et recherchez l’utilisateur par adresse e-mail.
    2. Sélectionnez le nom de l’utilisateur.
    3. Copiez la valeur **ID de l’objet**.

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a>Utiliser Azure Cloud Shell pour configurer les ressources Finance Insights Data Lake

# <a name="use-a-windows-powershell-script"></a>[Utiliser un script de configuration Windows PowerShell](#tab/use-a-powershell-script)

Un script Windows PowerShell a été fourni, afin que vous puissiez facilement configurer les ressources Azure décrites dans [Configurer l’exportation vers Azure Data Lake](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/configure-export-data-lake). Si vous préférez effectuer une configuration manuelle, ignorez cette procédure et continuez avec la procédure dans la section [Configuration manuelle](#manual-setup).

> [!NOTE]
> Pour exécuter le script PowerShell, procédez comme suit : L’option « Essayer » d’Azure CLI, ou l’exécution du script sur votre ordinateur risque de ne pas fonctionner.

Suivez ces étapes pour configurer Azure à l’aide du script Windows PowerShell. Vous devez disposer des droits pour créer un groupe de ressources Azure, des ressources Azure et une application Azure AD. Pour plus d’informations sur les autorisations requises, voir [Vérifier les autorisations Azure AD](https://docs.microsoft.com/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).

1. Dans le [portail Azure](https://portal.azure.com), accédez à votre abonnement Azure cible. Sélectionnez le bouton **Cloud Shell** à droite du champ **Recherche**.
2. Sélectionnez **PowerShell**.
3. Créez un espace de stockage, si vous êtes invité à le faire. Ensuite, téléchargez le script Windows PowerShell dans la session.
4. Exécutez le script.
5. Suivez les invites pour exécuter le script.
6. Utilisez les informations de la sortie du script pour installer le complément **Exporter vers Data Lake** dans LCS.
7. Utilisez les informations de la sortie du script pour activer le magasin d’entités sur la page **Connexions de données** dans Finance (**Administration du système \> Paramètres système \> Connexions des données**).

### <a name="manual-setup"></a>Configuration manuelle

#### <a name="add-applications-to-the-azure-ad-tenant"></a>Ajouter des applications au locataire Azure AD

1. Dans le [portail Azure](https://portal.azure.com), accédez à **Azure Active Directory**.
2. Sélectionnez **Gérer \> Applications de l’entreprise**.
3. Recherchez les applications suivantes par ID d’application.

    | Demande                              | ID d’application                               |
    |------------------------------------------|--------------------------------------|
    | Microservices ERP Microsoft Dynamics     | 0cdb527f-a8d1-4bf8-9436-b352c68682b2 |
    | CDS Microservices ERP Microsoft Dynamics | 703e2651-d3fc-48f5-942c-74274233dba8 |
    | Service d’autorisation AI Builder         | ad40333e-9910-4b61-b281-e3aeeb8c3ef3 |

Si vous ne trouvez aucune des applications précédentes, essayez les étapes suivantes.

1. Sur votre ordinateur local, sélectionnez le menu **Démarrer** et recherchez **powershell**.
2. Sélectionnez et maintenez (ou cliquez avec le bouton droit) sur **Windows PowerShell**, puis sélectionnez **Exécuter en tant qu’administrateur**.
3. Exécutez la commande suivante pour installer le module **AzureAD**.

    `Install-Module -Name AzureAD`

4. Si un fournisseur NuGet doit continuer, sélectionnez **O** pour l’installer.
5. Si un message « Référentiel non approuvé » apparaît, sélectionnez **O** pour continuer.
6. Pour chaque application à ajouter, exécutez les commandes suivantes pour ajouter l’application à Azure AD. Lorsque vous y êtes invité, connectez-vous en tant qu’administrateur Azure AD.

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a>Créer des ressources Azure

> [!NOTE]
> Assurez-vous de créer les ressources suivantes dans la même instance Azure AD en tant qu’environnement Dataverse. Vous ne pouvez pas utiliser les ressources d’une autre instance Azure AD.

1. Création d’un compte de stockage :

    1. Dans le [portail Azure](https://portal.azure.com), créez un compte de stockage.
    2. Dans la boîte de dialogue **Créer un compte de stockage**, définissez les champs suivants :

        - **Emplacement** : sélectionnez le centre de données où se trouve votre environnement.
        - **Performance** : nous vous recommandons de sélectionner **Standard**.
        - **Type de compte** : vous devez sélectionner **StorageV2**.

    3. Dans la boîte de dialogue **Options avancées**, pour l’option **Stockage Data Lake Gen2**, sélectionnez **Activer** sous la fonctionnalité **Espaces de noms hiérarchiques**. Si vous désactivez cette fonctionnalité, vous ne pouvez pas consommer de données que les applications Finance and Operations écrivent à l’aide de services tels que les flux de données Power BI.
    4. Sélectionnez **Réviser et créer**. Une fois le déploiement terminé, la nouvelle ressource sera affichée dans le portail Azure.
    5. Accédez au compte de stockage que vous avez créé.
    6. Dans le menu de gauche, sélectionnez **Clés d’accès**.
    7. Copiez et enregistrez la chaîne de connexion pour **Key1** ou **Key2**.
    8. Copiez et enregistrez le nom du compte de stockage.

2. Créer un coffre de clés :

    1. Dans le [portail Azure](https://portal.azure.com), créez un coffre de clés.
    2. Dans la boîte de dialogue **Créer un coffre de clés**, dans le champ **Emplacement**, sélectionnez le centre de données dans lequel se trouve votre environnement.
    3. Une fois le coffre de clés créé, sélectionnez-le dans la liste, puis sélectionnez **Secrets**.
    4. Sélectionnez **Générer/Importer**.
    5. Dans la boîte de dialogue **Créer un secret**, dans le champ **Options de téléchargement**, sélectionnez **Manuel**.
    6. Permet d’entrer un nom pour le secret. Notez le nom, car vous devrez le fournir ultérieurement.
    7. Dans le champ **Valeur**, saisissez la chaîne de connexion que vous avez obtenue du compte de stockage dans la procédure précédente.
    8. Sélectionnez **Activé**, puis sélectionnez **Créer**. Le secret est créé et ajouté à Key Vault.
    9. Accédez à **Vue d’ensemble de Key Vault**, et notez le nom DNS.

3. Créer et enregistrer une application Azure AD :

    1. Dans le [portail Azure](https://portal.azure.com), accédez à **Azure Active Directory**, puis sélectionnez **Inscriptions d’applications**.
    2. Sélectionnez **Inscription d’une nouvelle application** et définissez les champs suivants :

        - **Nom** : saisissez le nom de l’application.
        - **Type d’application** : sélectionnez **API Web**.
        - **Rediriger la configuration de l’URI** : saisissez l’URL de votre instance Dynamics 365, par exemple, `https://yourdynamicsinstance.dynamics.com/auth`.

    3. Accédez à l’application que vous venez de créer, copiez et enregistrez sa valeur **ID de l’application (client)**. Vous devrez fournir cette valeur ultérieurement, lors de la configuration du coffre de clés.
    4. Accédez à **Autorisations API** et suivez ces étapes :

        1. Sélectionnez **Ajouter une autorisation**.
        2. Sélectionnez **Azure Key Vault**.
        3. Après avoir sélectionné les autorisations déléguées, sélectionnez **utilisateur\_emprunt d’identité**.
        4. Sélectionnez **Ajouter des autorisations**.

    5. Dans le menu de l’application, sélectionnez **Certificats \& secrets**, puis suivez ces étapes pour créer des secrets Key Vault :

        1. Sélectionnez **Nouvelle clé secrète client**.
        2. Entrez un nom dans le champ **Description clé**.
        3. Sélectionnez une durée, puis **Ajouter**. Un secret est généré dans le champ **Valeur**.
        4. Copiez et enregistrez la valeur secrète.

4. Créer des secrets Key Vault :

    1. Accédez au coffre de clés que vous avez créé précédemment et sélectionnez **Secrets**.
    2. Pour chaque nom de secret dans le tableau suivant, procédez comme suit :

        1. Sélectionnez **Générer/Importer**.
        2. Dans la boîte de dialogue **Créer un secret**, dans le champ **Options de téléchargement**, sélectionnez **Manuel**.
        3. Créez le nom et la valeur du secret à partir du tableau suivant.
        4. Sélectionnez **Activé**, puis sélectionnez **Créer**. Le secret est créé et ajouté à Key Vault.

        | Nom du secret                       | Valeur secrète                                                                                |
        |-----------------------------------|---------------------------------------------------------------------------------------------|
        | app-id                            | L’ID d’application de l’application que vous avez créée précédemment                                      |
        | app-secret                        | Le secret client que vous avez enregistré précédemment                                                    |
        | storage-account-name              | Le nom du compte de stockage que vous avez créé précédemment, tel que **storageaccount1**       |
        | storage-account-connection-string | La chaîne de connexion que vous avez copiée à partir de la page **Clés d’accès** pour le compte de stockage |

5. Autorisez l’application à accéder au coffre de clés :

    1. Dans le [portail Azure](https://portal.azure.com), ouvrez le coffre de clés que vous avez créé précédemment.
    2. Sélectionnez les politiques d’accès.
    3. Pour chaque application dans le tableau suivant, procédez comme suit :

        1. Pour créer une stratégie d’accès, sélectionnez **Ajouter une stratégie d’accès**.
        2. Dans le champ **Autorisations secrètes**, sélectionnez les autorisations dans le tableau suivant.
        3. Dans le champ **Sélectionner le principal**, recherchez le nom d’affichage de l’application dans le tableau suivant.
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

        1. Sélectionnez le rôle depuis la table suivante.
        2. Laissez le champ **Affecter l’accès** défini sur **Utilisateur, groupe ou service principal Azure AD**.
        3. Dans le champ **Sélectionner**, saisissez l’application dans le tableau suivant.
        4. Sélectionnez **Enregistrer**.

        | Demande                                              | Rôle                        |
        |----------------------------------------------------------|-----------------------------|
        | Le nom d’affichage de la nouvelle application que vous avez créée | Propriétaire                       |
        | Le nom d’affichage de la nouvelle application que vous avez créée | Contributeur                 |
        | Le nom d’affichage de la nouvelle application que vous avez créée | Contributeur de compte de stockage |
        | Le nom d’affichage de la nouvelle application que vous avez créée | Propriétaire des données de l’objet blob de stockage     |
        | **Service d’autorisation AI Builder**                     | Lecteur de données de l’objet blob de stockage    |

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

## <a name="configure-the-entity-store"></a>Configurer le magasin des entités

Suivez ces étapes pour configurer le magasin des entités dans votre environnement Finance.

1. Accédez à **Administration système \> Paramétrage \> Paramètres système \> Connexions des données**.
2. Définissez l’option **Activer l’intégration de Data Lake** sur **Oui**.
3. Définissez les champs Key Vault suivants :

    - **ID de l’application (client)**  : saisissez l’ID client d’application que vous avez créé précédemment.
    - **Secret d’application** : entrez le secret que vous avez enregistré pour l’application que vous avez créée précédemment.
    - **Nom DNS** : vous pouvez trouver le nom DNS (Domain Name System) sur la page des détails de l’application que vous avez créée précédemment.
    - **Nom secret** : saisissez **storage-account-connection-string**.

## <a name="configure-the-data-lake"></a>Configurer le lac de données

Suivez ces étapes pour utiliser LCS pour ajouter le complément Azure Data Lake à l’environnement.

1. Connectez-vous à LCS, puis, sous le nom de l’environnement sur le côté droit de la page, sélectionnez **Tous les détails**.
2. Dans la section **Compléments de l’environnement**, sélectionnez **Installer un nouveau complément**.
3. Sélectionnez le complément **Exporter vers Data Lake**.
4. Saisissez les valeurs suivantes.

    | Valeur                                                              | Description |
    |--------------------------------------------------------------------|-------------|
    | ID de locataire de l’abonnement Azure où se trouve le coffre de clés | ID de locataire où se trouvent le compte de stockage, les applications et les coffres de clés. Pour trouver cette valeur, ouvrez le [Portail Azure](https://portal.azure.com), accédez à **Azure Active Directory**, et copiez la valeur **ID du locataire**. |
    | Fournir le nom DNS de votre Key Vault                             | Nom DNS du coffre de clés, tel que `https://customkeyvault.vault.azure.net/`. (Cette valeur correspond au nom DNS utilisé dans le magasin d’entités.) |
    | Fournir le secret contenant le nom du compte de stockage   | **storage-account-name** |
    | Nom secret de l’ID d’application à utiliser pour accéder à Data Lake          | **app-id** |
    | Nom secret à utiliser avec l’ID de l’application                                 | **app-secret** |

5. Acceptez les conditions et sélectionnez **Installer**.

Le complément sera installé dans quelques minutes.

## <a name="configure-ai-builder"></a>Configurer AI Builder

1. Connectez-vous à LCS, et ouvrez la page **Détails de l’environnement**.
2. Faites défiler jusqu’à la section **Compléments d’environnement**. Vous devriez voir les compléments qui sont déjà installés dans cet environnement. Si le complément **Exporter vers Data Lake** n’est pas parmi eux, configurez ce complément.
3. Sélectionnez le complément **Obtenir des informations**.
4. Sur la page des détails du complément **Obtenir des informations**, entrez les valeurs suivantes.

    | Valeur                                                    | Description |
    |----------------------------------------------------------|-------------|
    | URL de l’organisation CDS                                     | L’URL de l’organisation Dataverse de l’instance Dataverse. Pour trouver cette valeur, ouvrez le [portail Power Apps](https://make.powerapps.com), sélectionnez le bouton **Réglages** (symbole d’engrenage) dans le coin supérieur droit, sélectionnez **Paramètres avancés** et copiez l’URL. (L’URL se termine par « dynamics.com ».) |
    | ID org. CDS                                               | L’ID d’environnement de l’instance Dataverse. Pour trouver cette valeur, ouvrez le [portail Power Apps](https://make.powerapps.com), sélectionnez le bouton **Paramètres** (symbole d’engrenage) dans le coin supérieur droit, sélectionnez **Personnalisations \> Ressources du développeur \> Informations de référence de l’instance** et copiez la valeur **ID**. |
    | ID de locataire CDS (ID d’annuaire d’AAD)               | L’ID de locataire de l’instance Dataverse. Pour trouver cette valeur, ouvrez le [Portail Azure](https://portal.azure.com), accédez à **Azure Active Directory**, et copiez la valeur **ID du locataire**. |
    | Fournissez l’ID objet utilisateur qui dispose du rôle d’administrateur système | ID d’objet d’utilisateur Azure AD dans Dataverse. Cet utilisateur doit être un administrateur système de l’instance Dataverse. Pour trouver cette valeur, ouvrez le [portail Azure](https://portal.azure.com), accédez à **Azure Active Directory\> Utilisateurs**, sélectionnez l’utilisateur, puis, dans la section **Identité**, copiez la valeur **ID d’objet**. |
    | S’agit-il de l’environnement CDS par défaut pour le locataire ?      | Si l’instance Dataverse a été la première instance de production créée, cochez cette case. Si l’instance Dataverse a été créée manuellement, décochez cette case. |

## <a name="feedback-and-support"></a>Commentaires et support

Veuillez envoyer un e-mail à [Informations sur les paiements des clients (aperçu)](mailto:fiap@microsoft.com) si vous souhaitez fournir des commentaires ou si vous avez besoin d’aide.

## <a name="privacy-notice"></a>Avis de confidentialité

Les versions préliminaires (1) peuvent utiliser moins de mesures de confidentialité et de sécurité que le service Dynamics 365 Finance and Operations, (2) ne sont pas inclus dans le contrat de niveau de service (SLA) pour ce service, (3) ne doivent pas être utilisés pour traiter des données personnelles ou autres données soumises à des exigences de conformité juridique ou réglementaire, et (4) bénéficient d’un support limité.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]