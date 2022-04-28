---
title: Déployer des unités d’échelle de périphérie sur du matériel personnalisé à l’aide de LBD
description: Cette rubrique explique comment provisionner des unités d’échelle périphériques locales à l’aide d’un matériel personnalisé et d’un déploiement basé sur les données métier locales (LBD).
author: cabeln
ms.date: 01/24/2022
ms.topic: article
ms.prod: dynamics-365
ms.service: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: cabeln
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 37bc8678d4e04afebbebaaa893a484866a8643ce
ms.sourcegitcommit: 23588e66e25c05e989f3212ac519d7016820430a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2022
ms.locfileid: "8565545"
---
# <a name="deploy-edge-scale-units-on-custom-hardware-using-lbd"></a>Déployer des unités d’échelle de périphérie sur du matériel personnalisé à l’aide de LBD

[!include [banner](../includes/banner.md)]

Les unités d’échelle périphériques jouent un rôle important dans la topologie hybride distribuée pour la gestion de la chaîne d’approvisionnement. Dans la topologie hybride, vous pouvez répartir les charges de travail entre votre hub cloud Supply Chain Management et des unités d’échelle supplémentaires dans le cloud ou périphériques.

Les unités d’échelle périphériques peuvent être déployées en créant un [environnement local](../../fin-ops-core/dev-itpro/deployment/on-premises-deployment-landing-page.md) de données métier locales (LBD), puis en le configurant pour qu’il fonctionne comme une unité d’échelle dans votre topologie hybride distribuée pour la gestion de la chaîne d’approvisionnement. Pour cela, il convient d’associer l’environnement LBD local à un environnement Supply Chain Management dans le cloud, qui a été configuré pour fonctionner comme un hub.  

Cette rubrique décrit comment configurer un environnement LBD sur site en tant qu’unité d’échelle périphérique, puis l’associer à un hub.

## <a name="infrastructure-considerations"></a>Considérations de l’infrastructure

Les unités d’échelle périphériques s’exécutent sur des environnements sur site, de sorte que les exigences en matière d’infrastructure sont assez similaires. Cependant, certaines différences sont à noter :

- Les unités d’échelle périphériques n’utilisent pas Financial Reporting, elles ne nécessitent donc pas de nœuds Financial Reporting.
- Les charges de travail de fabrication et d’entreposage ne sont pas intensives en calcul, pensez donc à dimensionner votre puissance de calcul pour les nœuds AOS en conséquence.

## <a name="deployment-overview"></a>Vue d’ensemble du déploiement

Voici une vue d’ensemble des étapes de déploiement.

1. **Activer un emplacement LBD dans votre projet LBD dans Microsoft Dynamics Lifecycle Services (LCS).**

1. **Configurer et déployer un environnement LBD avec une base de données *vide*.**

    Utilisez LCS pour déployer l’environnement LBD avec la topologie la plus récente et une base de données vide. Pour plus d’informations, consultez la section [Configurer et déployer un environnement LBD avec une base de données vide](#set-up-deploy) plus loin dans cette rubrique. Vous devez utiliser Supply Chain Management version 10.0.21 ou versions ultérieures dans les environnements de hub et d’unités d’échelle.

1. **Charger les packages cibles dans les actifs de projet LBD dans LCS.**

    Préparez les packages d’application, de plateforme et de personnalisation que vous utilisez sur le hub et l’unité d’échelle périphérique. Pour plus d’informations, consultez la section [Charger les packages cibles dans les actifs de projet LBD dans LCS](#upload-packages) plus loin dans cette rubrique.

1. **Utiliser les packages cibles pour assurer le service de l’environnement LBD.**

    Cette étape garantit que la même build et les mêmes personnalisations sont déployées sur le hub et le spoke. Pour plus d’informations, consultez la section [Utiliser les packages cibles pour assurer le service de l’environnement LBD](#service-target-packages) plus loin dans cette rubrique.

1. **Terminer la configuration de l’unité d’échelle et l’affectation de la charge de travail.**

    Pour plus d’informations, consultez la section [Affecter votre unité d’échelle périphérique LBD à un hub](#assign-edge-to-hub) plus loin dans cette rubrique.

Les autres sections de cette rubrique fournissent plus de détails sur ces étapes.

## <a name="set-up-and-deploy-an-lbd-environment-with-an-empty-database"></a><a name="set-up-deploy"></a>Configurer et déployer un environnement LBD avec une base de données vide

Cette étape crée un environnement LBD fonctionnel. Cependant, l’environnement n’a pas nécessairement les mêmes versions d’application et de plateforme que l’environnement hub. De plus, les personnalisations n’y figurent pas et il n’a pas encore été activé pour fonctionner en tant qu’unité d’échelle.

1. Suivez les instructions de [Paramétrer et déployer les environnements locaux (mise à jour de la plateforme 41 et ultérieures)](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md). Vous devez utiliser Supply Chain Management version 10.0.21 ou versions ultérieures dans les environnements de hub et d’unités d’échelle. De plus, vous devez utiliser la version 2.12.0 ou ultérieure des scripts d’infrastructure. 

    > [!IMPORTANT]
    > Lisez le reste de cette section **avant** de terminer les étapes de cette rubrique.

1. Avant de décrire votre configuration dans le fichier infrastructure\\ConfigTemplate.xml, exécutez le script suivant :

    ```powershell
    .\Configure-ScriptsForEdgeScaleUnits.ps1 -ConfigurationFilePath .\ConfigTemplate.xml
    ```

    > [!NOTE]
    > Ce script supprimera toute configuration qui n’est pas nécessaire pour déployer des unités d’échelle périphériques.

1. Configurez une base de données contenant des données vides, comme décrit dans [Configurer les bases de données](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb). Utilisez le fichier data.bak vide pour cette étape.
1. Après avoir terminé l’étape [Configurer les bases de données](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb), exécutez le script suivant pour configurer la base de données Scale Unit Alm Orchestrator.

    > [!NOTE]
    > Ne configurez pas la base de données Financial Reporting pendant l’étape [Configurer les bases de données](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb).

    ```powershell
    .\Initialize-Database.ps1 -ConfigurationFilePath .\ConfigTemplate.xml -ComponentName EdgeScaleUnit
    ```

    Le script Initialize-Database.ps1 effectue les actions suivantes :

    1. Créez une base de données vide nommée **ScaleUnitAlmDb**.
    2. Mappez les utilisateurs aux rôles de base de données, en fonction du tableau suivant.

        | Utilisateur            | Type | Rôle de la base de données |
        |-----------------|------|---------------|
        | svc-LocalAgent$ | gMSA | db\_owner     |

1. Continuez de suivre les instructions de [Paramétrer et déployer les environnements locaux (mise à jour de la plateforme 41 et ultérieures)](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md).
1. Après avoir terminé l’étape [Configurer AD FS](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb), suivez ces étapes :

    1. Créez une application Active Directory Federation Services (AD FS) qui permettra au service Alm Orchestration de communiquer avec votre Application Object Server (AOS).

        ```powershell
        # Host URL is your DNS record\host name for accessing the AOS
        .\Create-ADFSServerApplicationForEdgeScaleUnits.ps1 -ConfigurationFilePath .\ConfigTemplate.xml -HostUrl 'https://ax.d365ffo.onprem.contoso.com'
        ```

    1. Créer une application Azure Active Directory (Azure AD) qui permettra au service Alm Orchestration de communiquer avec le service Gestion des unités d’échelle.

        ```powershell
        # Example .\Create-SumAADApplication.ps1 -ConfigurationFilePath ..\ConfigTemplate.xml -TenantId '6240a19e-86f1-41af-91ab-dbe29dbcfb95' -ApplicationDisplayName 'EdgeAgent-SUMCommunication-EN01'
        .\Create-SumAADApplication.ps1 -ConfigurationFilePath '<Path of the ConfigTemplate.xml file>' `
                                       -TenantId '<ID of the tenant where your cloud hub is deployed>' `
                                       -ApplicationDisplayName '<Whichever name you want the Azure AD app to have>'
        ```

1. Continuez de suivre les instructions de [Paramétrer et déployer les environnements locaux (mise à jour de la plateforme 41 et ultérieures)](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md). Lorsque vous devez entrer la configuration de l’agent local, assurez-vous d’activer les fonctionnalités d’unité d’échelle périphérique et de fournir tous les paramètres requis.

    ![Activation des fonctionnalités d’unité d’échelle périphérique.](media/EnableEdgeScaleUnitFeatures.png "Activation des fonctionnalités d’unité d’échelle périphérique.")

1. Avant de déployer votre environnement à partir de LCS, configurez le script de pré-déploiement. Pour plus d’informations, consultez [Pré-déploiement d’agent local et scripts de post-déploiement](../../fin-ops-core/dev-itpro/lifecycle-services/pre-post-scripts.md).

    1. Copiez le script Configure-CloudAndEdge.ps1 du dossier **ScaleUnit** situé dans **Scripts d’infrastructure** dans le dossier **Scripts** dans le partage de stockage de fichiers de l’agent qui a été configuré dans l’environnement. \\\\lbdiscsi01\\agent\\Scripts est un chemin type.
    2. Créez le script **PreDeployment.ps1** qui invoquera les scripts en utilisant les paramètres requis. Le script de pré-déploiement doit être placé dans le dossier **Scripts** dans le partage de stockage de fichiers de l’agent. Sinon, il ne peut pas être exécuté. \\\\lbdiscsi01\\agent\\Scripts\\PreDeployment.ps1 est un chemin type.

        Le contenu du script PreDeployment.ps1 ressemblera à l’exemple suivant.

        ```powershell
        $agentShare = '\\lbdiscsi01\agent'
        
        Write-Output "AgentShare is set to $agentShare" 
        . $PSScriptRoot\Configure-CloudAndEdge.ps1 -AgentShare $agentShare -InstanceId '@A'
        ```

        > [!NOTE]
        > Le paramètre InstanceId ne doit contenir que deux caractères. Le premier caractère est @ et le second peut être n’importe quelle lettre majuscule de l’alphabet anglais.
        >
        > - Valeurs valides :
        >   - @D
        >   - @X
        > - Valeurs non valides :
        >   - @a
        >   - @4
        >   - @#

1. Déployez l’environnement en utilisant la dernière topologie de base disponible.
1. Une fois votre environnement déployé, procédez comme suit :

    1. Exécutez les commandes SQL suivantes sur votre base de données métier (AXDB).

        ```sql
        ALTER TABLE dbo.NUMBERSEQUENCETABLE ENABLE CHANGE_TRACKING WITH (TRACK_COLUMNS_UPDATED = ON)
        delete from NumberSequenceTable
        delete from NumberSequenceReference
        delete from NumberSequenceScope
        delete from FeatureManagementMetadata
        delete from FeatureManagementState
        delete from SysFeatureStateV0
        ```

    1. Augmentez le nombre maximal de sessions par lots simultanées à une valeur supérieure à 4.

        ```sql
        Update batchserverconfig set maxbatchsessions = '<Replace with number of concurrent batch tasks you want>'
        ```

    1. Vérifiez que le suivi des modifications a été activé sur votre base de données métier (AXDB).

        1. Ouvrez SQL Server Management Studio (SSMS).
        1. Sélectionnez et maintenez la sélection (ou cliquez avec le bouton droit) sur votre base de données commerciale (AXDB), puis sélectionnez **Propriétés**.
        1. Dans la fenêtre qui s’affiche, sélectionnez **Suivi des modifications**, puis définissez les valeurs suivantes :

            - **Suivi des modifications :** *True*
            - **Période de rétention :** *7*
            - **Unités de rétention :** *Jours*
            - **Nettoyage automatique :** *True*

    1. Ajoutez l’ID d’application AD FS que vous avez créé précédemment (à l’aide du script Create-ADFSServerApplicationForEdgeScaleUnits.ps1) à la table des applications Azure AD dans votre unité d’échelle. Vous pouvez effectuer manuellement cette étape via l’interface utilisateur (UI). Vous pouvez également l’effectuer via la base de données en utilisant le script suivant.

        ```sql
        DECLARE @ALMOrchestratorId NVARCHAR(76) = '<Replace with the ADFS Application ID created in a previous step>';

        IF NOT EXISTS (SELECT TOP 1 1 FROM SysAADClientTable WHERE AADClientId = @ALMOrchestratorId)
        BEGIN
            INSERT INTO SysAADClientTable (AADClientId, UserId, Name, ModifiedBy, CreatedBy)
            VALUES (@ALMOrchestratorId, 'ScaleUnitManagement', 'Scale Unit Management', 'Admin', 'Admin');
        END
        ```

## <a name="set-up-an-azure-key-vault-and-an-azure-ad-application-to-enable-communication-between-scale-units"></a><a name="set-up-keyvault"></a>Configurer un coffre de clés Azure et une application Azure AD pour permettre la communication entre les unités d’échelle

1. Une fois votre environnement déployé, créez une application Azure AD pour permettre une communication sécurisée entre votre hub et l’unité d’échelle.

    ```powershell
    .\Create-SpokeToHubAADApplication.ps1 -ConfigurationFilePath '<Path of the ConfigTemplate.xml file>' `
                                          -TenantId '<ID of the tenant where your cloud hub is deployed>' `
                                          -ApplicationDisplayName '<Whichever name you want the Azure AD app to have>'
    ```

1. Après avoir créé l’application, vous devez créer un clé secrète client et enregistrer les informations dans un coffre de clés Azure. De plus, vous devez autoriser l’accès à l’application Azure AD qui a été créée, afin qu’elle puisse récupérer les secrets stockés dans le coffre de clés. Pour votre commodité, le script suivant effectuera automatiquement toutes les actions requises.

    ```powershell
    .\Create-SpokeToHubAADAppSecrets.ps1 -ConfigurationFilePath '<Path of the ConfigTemplate.xml file>' `
                                         -TenantId '<ID of the tenant where your cloud hub is deployed>' `
                                         -SubscriptionName '<Any subscription within your tenant>' `
                                         -ResourceGroupName '<Any resource group within your subscription>' `
                                         -KeyVaultName '<Any key vault within your resource group>' `
                                         -Location '<Any Azure location where Azure Key Vault is available>' `
                                         -LCSEnvironmentId '<The LCS environment ID of your deployed scale unit>' `
    ```

    > [!NOTE]
    > Si aucun coffre de clés avec la valeur **KeyVaultName** n’existe, le script en crée un automatiquement.

1. Ajouter l’ID d’application Azure AD que vous venez de créer (lors de l’utilisation du script Create-SpokeToHubAADApplication.ps1) à la table des applications Azure AD dans votre hub. Vous pouvez effectuer manuellement cette étape via l’UI.

## <a name="upload-target-packages-into-lbd-project-assets-in-lcs"></a><a name="upload-packages"></a>Charger les packages cibles dans les actifs de projet LBD dans LCS

Cette étape prépare la version de l’application, la version de la plateforme et les personnalisations qui seront transférées vers votre environnement d’unité d’échelle LBD.

1. Chargez le même package combiné application/plateforme qui a été appliqué à l’environnement du hub dans la bibliothèque d’actifs du projet local LCS.
1. Obtenez une copie du package déployable personnalisé qui a été appliqué à l’environnement du hub et chargez-le dans la bibliothèque d’actifs du projet local LCS.

## <a name="service-the-lbd-environment-with-target-packages"></a><a name="service-target-packages"></a>Utiliser les packages cibles pour assurer le service de l’environnement LBD

Cette étape aligne la version de l’application, la version de la plateforme et les personnalisations de votre environnement d’unité d’échelle LBD avec le hub.

1. Assurez le service de l’environnement LBD avec le package combiné application/plateforme que vous avez chargé à l’étape précédente.
1. Assurez le service de l’environnement LBD avec le package déployable personnalisé que vous avez chargé à l’étape précédente.

    ![Application des mises à jour dans LCS.](media/cloud_edge-LBD-LCS-ServiceLBDEnv1.png "Application des mises à jour dans LCS")

    ![Sélection de votre package de personnalisation.](media/cloud_edge-LBD-LCS-ServiceLBDEnv2.png "Sélection de votre package de personnalisation")

## <a name="assign-your-lbd-edge-scale-unit-to-a-hub"></a><a name="assign-edge-to-hub"></a>Affectez votre unité d’échelle périphérique LBD à un hub

Vous configurez et gérez votre unité d’échelle périphérique via le portail de gestion des unités d’échelle. Pour plus d’informations, voir [Gérer les unités d’échelle et les charges de travail à l’aide du portail de gestionnaire d’unité d’échelle](./cloud-edge-landing-page.md#scale-unit-manager-portal).

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
