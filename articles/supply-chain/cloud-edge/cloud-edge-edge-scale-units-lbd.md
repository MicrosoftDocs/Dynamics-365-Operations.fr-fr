---
title: Déployer des unités d’échelle périphériques sur du matériel personnalisé à l’aide de données métier locales (LBD) (version préliminaire)
description: Cette rubrique explique comment provisionner des unités d’échelle périphériques locales à l’aide d’un matériel personnalisé et d’un déploiement basé sur les données métier locales (LBD).
author: cabeln
ms.date: 04/22/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: cabeln
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 0ebbdaab9d6f040497d3158db2712e102b6e9aa8
ms.sourcegitcommit: 1e5a46271bf7fae2f958d2b1b666a8d2583e04a8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/25/2021
ms.locfileid: "7678979"
---
# <a name="deploy-edge-scale-units-on-custom-hardware-using-lbd-preview"></a>Déployer des unités d’échelle périphériques sur du matériel personnalisé à l’aide de données métier locales (LBD) (version préliminaire)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)] <!--KFM: Until 11/1/2021 -->

Les unités d’échelle périphériques jouent un rôle important dans la topologie hybride distribuée pour la gestion de la chaîne d’approvisionnement. Dans la topologie hybride, vous pouvez répartir les charges de travail entre votre hub cloud Supply Chain Management et des unités d’échelle supplémentaires dans le cloud ou périphériques.

Les unités d’échelle périphériques peuvent être déployées en créant un [environnement local](../../fin-ops-core/dev-itpro/deployment/on-premises-deployment-landing-page.md) de données métier locales (LBD), puis en le configurant pour qu’il fonctionne comme une unité d’échelle dans votre topologie hybride distribuée pour la gestion de la chaîne d’approvisionnement. Pour cela, il convient d’associer l’environnement LBD local à un environnement Supply Chain Management dans le cloud, qui a été configuré pour fonctionner comme un hub.  

Les unités d’échelle périphériques sont actuellement en version préliminaire. Par conséquent, l’utilisation d’un environnement de ce type est soumise au respect des [conditions d’utilisation de la version préliminaire](https://aka.ms/scmcnepreviewterms).

Cette rubrique décrit comment configurer un environnement LBD sur site en tant qu’unité d’échelle périphérique, puis l’associer à un hub.

## <a name="deployment-overview"></a>Vue d’ensemble du déploiement

Voici une vue d’ensemble des étapes de déploiement.

1. **Activer un emplacement LBD dans votre projet LBD dans Microsoft Dynamics Lifecycle Services (LCS).**

    Lors de la phase de version préliminaire, les unités d’échelle périphériques LBD ciblent les clients LBD existants. Un emplacement de bac à sable LBD limité supplémentaire de 60 jours sera fourni uniquement dans certaines situations client spécifiques.

1. **Configurer et déployer un environnement LBD avec une base de données *vide*.**

    Utilisez LCS pour déployer l’environnement LBD avec la topologie la plus récente et une base de données vide. Pour plus d’informations, consultez la section [Configurer et déployer un environnement LBD avec une base de données vide](#set-up-deploy) plus loin dans cette rubrique. Vous devez utiliser Supply Chain Management version 10.0.19 avec la mise à jour de plateforme 43 ou ultérieure dans les environnements de hub et d’unités d’échelle.

1. **Charger les packages cibles dans les actifs de projet LBD dans LCS.**

    Préparez les packages d’application, de plateforme et de personnalisation que vous utilisez sur le hub et l’unité d’échelle périphérique. Pour plus d’informations, consultez la section [Charger les packages cibles dans les actifs de projet LBD dans LCS](#upload-packages) plus loin dans cette rubrique.

1. **Utiliser les packages cibles pour assurer le service de l’environnement LBD.**

    Cette étape garantit que la même build et les mêmes personnalisations sont déployées sur le hub et le spoke. Pour plus d’informations, consultez la section [Utiliser les packages cibles pour assurer le service de l’environnement LBD](#service-target-packages) plus loin dans cette rubrique.

1. **Terminer la configuration de l’unité d’échelle et l’affectation de la charge de travail.**

    Pour plus d’informations, consultez la section [Affecter votre unité d’échelle périphérique LBD à un hub](#assign-edge-to-hub) plus loin dans cette rubrique.

Les autres sections de cette rubrique fournissent plus de détails sur ces étapes.

## <a name="set-up-and-deploy-an-lbd-environment-with-an-empty-database"></a><a name="set-up-deploy"></a>Configurer et déployer un environnement LBD avec une base de données vide

Cette étape crée un environnement LBD fonctionnel. Cependant, l’environnement n’a pas nécessairement les mêmes versions d’application et de plateforme que l’environnement hub. De plus, les personnalisations n’y figurent pas et il n’a pas encore été activé pour fonctionner en tant qu’unité d’échelle.

1. Suivez les instructions de [Paramétrer et déployer les environnements locaux (mise à jour de la plateforme 41 et ultérieures)](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md). Vous devez utiliser Supply Chain Management version 10.0.19 avec la mise à jour de plateforme 43 ou ultérieure dans les environnements de hub et d’unités d’échelle.

    > [!IMPORTANT]
    > Lisez le reste de cette section **avant** de terminer les étapes de cette rubrique.

1. Avant de décrire votre configuration dans le fichier infrastructure\\ConfigTemplate.xml, exécutez le script suivant :

    ```powershell
    .\Configure-ScriptsForEdgeScaleUnits.ps1 -ConfigurationFilePath .\ConfigTemplate.xml
    ```

    > [!NOTE]
    > Ce script supprimera toute configuration qui n’est pas nécessaire pour déployer des unités d’échelle périphériques.

1. Configurez une base de données contenant des données vides, comme décrit dans [Configurer les bases de données](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb). Utilisez le fichier data.bak vide pour cette étape.
1. Configurez le script de pré-déploiement. Pour plus d’informations, consultez [Pré-déploiement d’agent local et scripts de post-déploiement](../../fin-ops-core/dev-itpro/lifecycle-services/pre-post-scripts.md).

    1. Copiez le contenu du dossier **ScaleUnit** situé dans **Scripts d’infrastructure** dans le dossier **Scripts** dans le partage de stockage de fichiers de l’agent qui a été configuré dans l’environnement. \\\\lbdiscsi01\\agent\\Scripts est un chemin type.
    2. Créez le script **PreDeployment.ps1** qui invoquera les scripts en utilisant les paramètres requis. Le script de pré-déploiement doit être placé dans le dossier **Scripts** dans le partage de stockage de fichiers de l’agent. Sinon, il ne peut pas être exécuté. \\\\lbdiscsi01\\agent\\Scripts\\PreDeployment.ps1 est un chemin type.

        Le contenu du script PreDeployment.ps1 ressemblera à l’exemple suivant.

        ```powershell
        $agentShare = '\\lbdiscsi01\agent'
        
        Write-Output "AgentShare is set to $agentShare" 
        & $agentShare\Scripts\Configure-CloudandEdge.ps1 -AgentShare $agentShare -InstanceId '@A' -DatabaseServer 'lbdsqla01.contoso.com' -DatabaseName 'AXDB'
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

## <a name="upload-target-packages-into-lbd-project-assets-in-lcs"></a><a name="upload-packages"></a>Charger les packages cibles dans les actifs de projet LBD dans LCS

Cette étape prépare la version de l’application, la version de la plateforme et les personnalisations qui seront transférées vers votre environnement d’unité d’échelle LBD.

1. Chargez le même package combiné application/plateforme qui a été appliqué à l’environnement du hub dans la bibliothèque d’actifs du projet local LCS.
1. Obtenez une copie du package déployable personnalisé qui a été appliqué à l’environnement du hub et chargez-le dans la bibliothèque d’actifs du projet local LCS.

## <a name="service-the-lbd-environment-with-target-packages"></a><a name="service-target-packages"></a>Utiliser les packages cibles pour assurer le service de l’environnement LBD

Cette étape aligne la version de l’application, la version de la plateforme et les personnalisations de votre environnement d’unité d’échelle LBD avec le hub.

1. Assurez le service de l’environnement LBD avec le package combiné application/plateforme que vous avez chargé à l’étape précédente.
1. Assurez le service de l’environnement LBD avec le package déployable personnalisé que vous avez chargé à l’étape précédente.

    ![Sélection de Maintenance > Appliquer les mises à jour dans LCS.](media/cloud_edge-LBD-LCS-ServiceLBDEnv1.png "Sélection de Maintenance > Appliquer les mises à jour dans LCS")

    ![Sélection de votre package de personnalisation.](media/cloud_edge-LBD-LCS-ServiceLBDEnv2.png "Sélection de votre package de personnalisation")

## <a name="assign-your-lbd-edge-scale-unit-to-a-hub"></a><a name="assign-edge-to-hub"></a>Affectez votre unité d’échelle périphérique LBD à un hub

Alors que les unités d’échelle périphériques sont toujours en version préliminaire, vous devez utiliser les [outils de déploiement et de configuration d’unité d’échelle](https://github.com/microsoft/SCMScaleUnitDevTools) qui sont disponibles sur GitHub pour affecter votre unité d’échelle périphérique LBD à un hub. Le processus permet à une configuration LBD de fonctionner comme unité d’échelle périphérique et de l’associer au hub. Le processus est similaire à la configuration d’un environnement de développement unique.

1. Téléchargez la dernière version de [SCMScaleUnitDevTools](https://github.com/microsoft/SCMScaleUnitDevTools/releases) et décompressez le contenu du fichier.
1. Créez une copie du fichier `UserConfig.sample.xml` et nommez-le `UserConfig.xml`.
1. Créez une application Microsoft Azure Active Directory (Azure AD) dans votre client Azure AD, comme indiqué dans le [Guide de déploiement de l’unité d’échelle et des charges de travail](https://github.com/microsoft/SCMScaleUnitDevTools/wiki/Step-by-step-usage-guide#aad-application-registrations).
    1. Une fois l’application créée, accédez au formulaire des applications Azure AD (SysAADClientTable) sur votre hub.
    1. Créez une nouvelle entrée et définissez l’**ID client** sur l’ID de l’application que vous avez créée. Définissez **Nom** sur *ScaleUnits* et **ID utilisateur** sur *Administrateur*.

1. Créez une application Active Directory Federation Service (AD FS) comme indiqué dans le [Guide de déploiement de l’unité d’échelle et des charges de travail](https://github.com/microsoft/SCMScaleUnitDevTools/wiki/Step-by-step-usage-guide#adfs-application-registrations).
    1. Une fois l’application créée, accédez au formulaire des applications Azure AD (SysAADClientTable) sur votre unité d’échelle périphérique.
    1. Créez une nouvelle entrée et définissez l’**ID client** sur l’ID de l’application que vous avez créée. Définissez l’**ID utilisateur** sur *Administrateur*.

1. Modifiez le fichier `UserConfig.xml`.
    1. Dans la section `InterAOSAADConfiguration`, entrez les informations de l’application Azure AD que vous avez créée précédemment.
        - Dans l’élément `AppId`, entrez l’ID d’application de l’application Azure.
        - Dans l’élément `AppSecret`, entrez le secret d’application de l’application Azure.
        - L’élément `Authority` doit contenir l’URL spécifiant l’autorité de sécurité de votre client.

        ```xml
        <InterAOSAADConfiguration>
            <AppId>8dab14f6-97b1-48e3-b51b-350b45f6ede5</AppId>
            <AppSecret>k6em-_7.lopty56TGUedDTVhtER-j_6anY1</AppSecret>
            <Authority>https://login.windows.net/contoso.onmicrosoft.com</Authority>
        </InterAOSAADConfiguration>
        ```

    1. Dans la section `ScaleUnitConfiguration`, pour le premier élément `ScaleUnitInstance`, modifiez la section `AuthConfiguration`.
        - Dans l’élément `AppId`, entrez l’ID d’application de l’application Azure.
        - Dans l’élément `AppSecret`, entrez le secret d’application de l’application Azure.
        - L’élément `Authority` doit contenir l’URL spécifiant l’autorité de sécurité de votre client.

        ```xml
        <AuthConfiguration>
            <AppId>8dab14f6-97b1-48e3-b51b-350b45f6ede5</AppId>
            <AppSecret>k6em-_7.lopdz.6d3DTVOtf9Lo-j_6anY1</AppSecret>
            <Authority>https://login.windows.net/contoso.onmicrosoft.com</Authority>
        </AuthConfiguration>
        ```

    1. En outre, pour ce même élément `ScaleUnitInstance`, définissez les valeurs suivantes :
        - Dans l’élément `Domain`, spécifiez l’URL de votre hub. Par exemple : `https://cloudhub.sandbox.operations.dynamics.com/`
        - Dans l’élément `EnvironmentType`, assurez-vous que la valeur `LCSHosted` est définie.

    1. Dans la section `ScaleUnitConfiguration`, pour le second élément `ScaleUnitInstance`, modifiez la section `AuthConfiguration`.
        - Dans l’élément `AppId`, entrez l’ID d’application de l’application AD FS.
        - Dans l’élément `AppSecret`, entrez le secret d’application de l’application ADFS.
        - L’élément `Authority` doit contenir l’URL de votre instance AD FS.

        ```xml
        <AuthConfiguration>
            <AppId>26b16f25-21d8-4d36-987b-62df292895aa</AppId>
            <AppSecret>iZFfObgI6lLtY9kEbBjEFV98NqI5_YZ0e5SBcWER</AppSecret>
            <Authority>https://adfs.contoso.com/adfs</Authority>
        </AuthConfiguration>
        ```

    1. En outre, pour ce même élément `ScaleUnitInstance`, définissez les valeurs suivantes :
        - Dans l’élément `Domain`, spécifiez l’URL de votre unité d’échelle périphérique. Par exemple : https://ax.contoso.com/
        - Dans l’élément `EnvironmentType`, assurez-vous que la valeur LBD est définie.
        - Dans l’élément `ScaleUnitId`, entrez la même valeur que celle spécifiée pour `InstanceId` lors de la configuration du script de pré-déploiement `Configure-CloudandEdge.ps1`.

        > [!NOTE]
        > Si vous n’utilisez pas l’ID par défaut (@A), assurez-vous de mettre à jour l’élément ScaleUnitId pour chaque ConfiguredWorkload dans la section Charges de travail.

1. Ouvrez PowerShell et accédez au dossier contenant le fichier `UserConfig.xml`.

1. Exécutez l’outil avec cette commande.

    ```powershell
    .\CLI.exe
    ```

    > [!NOTE]
    > Après chaque action, vous devrez redémarrer l’outil.

1. Dans l’outil, sélectionnez **2. Préparer les environnements pour l’installation de la charge de travail**. Exécutez ensuite les étapes suivantes :
    1. Sélectionnez **1. Préparer le hub**.
    1. Sélectionnez **2. Préparer l’unité d’échelle**.

    > [!NOTE]
    > Si vous n’exécutez pas cette commande à partir d’une nouvelle installation et qu’elle échoue, effectuez les actions suivantes :
    >
    > - Supprimez tous les dossiers du dossier `aos-storage` (sauf pour `GACAssemblies`).
    > - Exécutez la commande SQL suivante sur votre base de données métier (AXDB) :
    >
    > ```sql 
    > delete from storagefoler
    > ```

1. Exécutez les commandes SQL suivantes sur votre base de données métier (AXDB) :

    ```sql
    delete from FEATUREMANAGEMENTMETADATA
    delete from FEATUREMANAGEMENTSTATE
    delete from NUMBERSEQUENCESCOPE
    ```

1. Vérifiez que le suivi des modifications a été activé sur votre base de données métier (AXDB)
    1. Démarrez SQL Server Management Studio (SSMS).
    1. Cliquez avec le bouton droit sur votre base de données métier (AXDB) et sélectionnez Propriétés.
    1. Dans la fenêtre qui s’ouvre, sélectionnez **Suivi des modifications** et effectuez les réglages suivants :

        - **Suivi des modifications :** *True*
        - **Période de rétention :** *7*
        - **Unités de rétention :** *Jours*
        - **Nettoyage automatique :** *True*

1. Dans l’outil, sélectionnez **3. Installer des charges de travail**. Exécutez ensuite les étapes suivantes :
    1. Sélectionnez **1. Installer sur le hub**.
    1. Sélectionnez **2. Installer sur l’unité d’échelle**.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
