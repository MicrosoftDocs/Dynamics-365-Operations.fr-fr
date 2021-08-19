---
title: Complément de visibilité de stock
description: Cette rubrique décrit comment installer et configurer le complément de visibilité de stock pour Dynamics 365 Supply Chain Management.
author: sherry-zheng
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 8faae53f66c069c53609dee72fa30ca18a22c9eb8a86b4669c745c00976af34d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742702"
---
# <a name="inventory-visibility-add-in"></a>Complément de visibilité de stock

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Le complément de visibilité de stock est un microservice indépendant et hautement évolutif qui permet un suivi des stocks en temps réel, offrant ainsi une vue globale de la visibilité du stock.

Toutes les informations relatives à l’inventaire disponible sont exportées vers le service en temps quasi réel via une intégration SQL de bas niveau. Les systèmes externes accèdent au service via des API RESTful pour interroger les informations disponibles sur des ensembles de dimensions donnés, récupérant ainsi une liste des positions disponibles.

La visibilité du stock est un microservice basé sur Microsoft Dataverse, ce qui signifie que vous pouvez l’étendre en créant des Power Apps et en appliquant Power BI pour fournir des fonctionnalités personnalisées pour répondre aux besoins de votre entreprise. Il est également possible de mettre à niveau l’index pour effectuer des requêtes d’inventaire.

La visibilité du stock fournit des options de configuration qui lui permettent de s’intégrer à plusieurs systèmes tiers. Il prend en charge la dimension de stock normalisée, l’extensibilité personnalisée et les quantités calculées normalisées et configurables.

Cette rubrique décrit comment installer et configurer le complément de visibilité de stock pour Dynamics 365 Supply Chain Management, et comment utiliser son interface de programmation d’application (API).

## <a name="install-the-inventory-visibility-add-in"></a>Installer le complément de visibilité de stock

Vous devez installer le complément de visibilité de stock à l’aide de Microsoft Dynamics Lifecycle Services (LCS). LCS est un portail de collaboration qui fournit un environnement et un ensemble de services régulièrement mis à jour qui vous aident à gérer le cycle de vie des applications de vos applications Dynamics 365 Finance and Operations.

Pour plus d’informations, voir [Ressources Lifecycle Services](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

### <a name="inventory-visibility-add-in-prerequisites"></a>Conditions préalables pour le complément de visibilité de stock

Avant de pouvoir installer le complément Visibilité du stock, vous devez procéder comme suit :

- Obtenez un projet d’implémentation LCS avec au moins un environnement déployé.
- Assurez-vous que les conditions préalables à la configuration des compléments fournies dans la [Présentation des compléments](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) ont été remplies. La visibilité de l’inventaire ne nécessite pas de liaison en double écriture.
- Contactez l’équipe de visibilité de l’inventaire à [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) pour obtenir les trois fichiers requis suivants :
  - `Inventory Visibility Dataverse Solution.zip`
  - `Inventory Visibility Configuration Trigger.zip`
  - `Inventory Visibility Integration.zip` (si la version de Supply Chain Management que vous exécutez est antérieure à la version 10.0.18)
- Vous pouvez également contacter l’équipe de visibilité de l’inventaire à [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) pour obtenir les packages de Package Deployer. Ces packages peuvent être utilisés par un outil Package Deployer officiel.
  - `InventoryServiceBase.PackageDeployer.zip`
  - `InventoryServiceApplication.PackageDeployer.zip` (ce package contient toutes les modifications apportées au package `InventoryServiceBase`, ainsi que des composants d’application d’interface utilisateur supplémentaires)
- Suivez les instructions données dans [Démarrage rapide : enregistrer une application avec la plateforme d’identité Microsoft](/azure/active-directory/develop/quickstart-register-app) pour inscrire une application et ajouter un secret client à AAD dans le cadre de votre abonnement Azure.
  - [Inscrire une application](/azure/active-directory/develop/quickstart-register-app)
  - [Ajouter un secret client](/azure/active-directory/develop/quickstart-register-app#add-a-certificate)
  - Les valeurs **Identifiant de l’application (client)**, **Secret client** et **ID du locataire** seront utilisées dans les étapes suivantes.

> [!NOTE]
> Les régions actuellement pris en charge comprennent le Canada, les États-Unis et l’Union européenne (UE).

Si vous avez des questions sur ces conditions préalables, contactez l’équipe produit de visibilité du stock.

### <a name="set-up-dataverse"></a><a name="setup-microsoft-dataverse"></a>Paramétrer Dataverse

Pour configurer Dataverse pour une utilisation avec la visibilité du stock, vous devez d’abord préparer les prérequis, puis décider si vous souhaitez configurer Dataverse à l’aide de l’outil Package Deployer ou en important manuellement les solutions (vous n’avez pas à faire les deux). Ensuite installez le complément de visibilité de stock. Les sous-sections suivantes décrivent comment effectuer chacune de ces tâches.

#### <a name="prepare-dataverse-prerequisites"></a>Préparer les conditions préalables Dataverse

Avant de commencer la configuration de Dataverse, ajoutez un principe de service à votre locataire en procédant comme suit :

1. Installer Azure AD PowerShell Module v2 comme décrit dans [Installer Azure Active Directory PowerShell pour Graph](/powershell/azure/active-directory/install-adv2).

1. Exécutez la commande suivante PowerShell :

    ```powershell
    Connect-AzureAD # (open a sign in window and sign in as a tenant user)
    
    New-AzureADServicePrincipal -AppId "3022308a-b9bd-4a18-b8ac-2ddedb2075e1" -DisplayName "d365-scm-inventoryservice"
    ```

#### <a name="set-up-dataverse-using-the-package-deployer-tool"></a>Configurer Dataverse à l’aide de l’outil Package Deployer

Une fois les conditions préalables en place, utilisez la procédure suivante si vous préférez configurer Dataverse à l’aide de l’outil Package Deployer. Consultez la section suivante pour plus de détails sur la façon d’importer les solutions manuellement (ne faites pas les deux).

1. Installez les outils de développement comme décrit dans [Télécharger les outils depuis NuGet](/dynamics365/customerengagement/on-premises/developer/download-tools-nuget).

1. En fonction des besoins de votre entreprise, choisissez le package `InventoryServiceBase` ou `InventoryServiceApplication`.

1. Importer les solutions :
    1. Pour le package `InventoryServiceBase` :
        - Décompressez `InventoryServiceBase.PackageDeployer.zip`
        - Recherchez le dossier `InventoryServiceBase`, le fichier `[Content_Types].xml`, le fichier `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll`, le fichier `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config` et le fichier `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config`. 
        - Copiez chacun de ces dossiers et fichiers dans le répertoire `.\Tools\PackageDeployment`, qui a été créé lorsque vous avez installé les outils de développement.
    1. Pour le package `InventoryServiceApplication` :
        - Décompressez `InventoryServiceApplication.PackageDeployer.zip`
        - Recherchez le dossier `InventoryServiceApplication`, le fichier `[Content_Types].xml`, le fichier `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll`, le fichier `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config` et le fichier `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config`.
        - Copiez chacun de ces dossiers et fichiers dans le répertoire `.\Tools\PackageDeployment`, qui a été créé lorsque vous avez installé les outils de développement.
    1. Exécutez `.\Tools\PackageDeployment\PackageDeployer.exe`. Suivez les instructions sur votre écran pour importer les solutions.

1. Attribuez les rôles de sécurité à l’utilisateur de l’application.
    1. Ouvrez l’URL de votre environnement Dataverse.
    1. Accédez à **Paramètres avancés \> Système \> Sécurité \> Utilisateurs**, et recherchez l’utilisateur nommé **# InventoryVisibility**.
    1. Sélectionner **Attribuer un rôle**, puis **Administrateur système**. S’il y a un rôle nommé **Utilisateur Common Data Service**, sélectionnez-le aussi.

#### <a name="set-up-dataverse-manually-by-importing-solutions"></a>Configurer Dataverse manuellement en important des solutions

Une fois les conditions préalables en place, utilisez la procédure suivante si vous préférez configurer Dataverse en important manuellement des solutions. Consultez la section précédente pour plus de détails sur l’utilisation de l’outil Package Deployer (ne faites pas les deux).

1. Créer un utilisateur d’application pour la visibilité de l’inventaire dans Dataverse :

    1. Ouvrez l’URL de votre environnement Dataverse.
    1. Aller à **Paramètre avancé \> Système \> Sécurité \> Utilisateurs** et créez un utilisateur d’application. Utilisez le menu de la vue pour changez la vue de la page sur **Utilisateurs de l’application**.
    1. Sélectionnez **Nouveau**. Définissez l’ID application sur *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*. (L’ID d’objet sera automatiquement chargé lorsque vous enregistrez vos modifications.) Vous pouvez personnaliser le nom. Par exemple, vous pouvez le changer en *Visibilité de l’inventaire*. Lorsque vous avez terminé, sélectionnez **Enregistrer**.
    1. Sélectionner **Attribuer un rôle**, puis **Administrateur système**. S’il y a un rôle nommé **Utilisateur Common Data Service**, sélectionnez-le aussi.

    Pour plus d’informations, voir [Créer un utilisateur d’application](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).

1. Si la langue par défaut de votre Dataverse n’est pas **l’Anglais** :

    1. Accédez à **Paramètres avancés \> Administration \> Langues**,
    1. Sélectionnez **Anglais (LanguageCode = 1033)** et sélectionnez **Appliquer**.

1. Importez le fichier `Inventory Visibility Dataverse Solution.zip`, qui comprend entités liées à la configuration Dataverse et Power Apps :

    1. Allez sur la page **Solutions**.
    1. Sélectionnez **Importer**.

1. Importez le flux de déclenchement de la mise à niveau de la configuration :

    1. Allez sur la page Microsoft Flow.
    1. Assurez-vous que la connexion nommée *Dataverse (héritée)* existe. (S’il n’existe pas, créez-le.)
    1. Importer le fichier `Inventory Visibility Configuration Trigger.zip`. Une fois importé, le déclencheur apparaîtra sous **Mes flux**.
    1. Initialisez les quatre variables suivantes, en fonction des informations d’environnement :

        - ID de locataire Azure
        - ID client application Azure
        - Clé secrète client application Azure
        - Point de terminaison de la visibilité du stock

            Pour plus d’informations sur cette variable, consultez la section [Configurer l’intégration de la visibilité de l’inventaire](#setup-inventory-visibility-integration) plus loin dans cette rubrique.

        ![Déclencheur de configuration.](media/configuration-trigger.png "déclencheur de configuration")

    1. Sélectionnez **Activer**.

### <a name="install-the-add-in"></a><a name="install-add-in"></a>Installer le complément

Pour pouvoir installer le complément Visibilité du stock, procédez comme suit :

1. Connectez-vous au portail [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).
1. Sur la page d’accueil, sélectionnez le projet dans lequel votre environnement est déployé.
1. Sur la page du projet, sélectionnez l’environnement dans lequel vous souhaitez installer le complément.
1. Sur la page d’environnement, faites défiler vers le bas jusqu’à ce que vous voyiez la section **Compléments d’environnement** dans la section **Intégration Power Platform**, où vous pouvez trouver le nom de l’environnement Dataverse.
1. Dans la section **Compléments de l’environnement**, sélectionnez **Installer un nouveau complément**.

    ![Page de l’environnement dans LCS.](media/inventory-visibility-environment.png "Page de l’environnement dans LCS")

1. Sélectionnez le lien **Installer un nouveau complément**. Une liste des compléments disponibles s’ouvre.
1. Dans la liste, sélectionnez **visibilité de stock**.
1. Saisissez des valeurs pour les champs suivants pour votre environnement :

    - **ID application AAD (client)**
    - **ID locataire AAD**

    ![Ajouter dans la page de configuration.](media/inventory-visibility-setup.png "Page de configuration de complément")

1. Acceptez les termes et conditions en cochant la case **Termes et conditions**.
1. Sélectionnez **Installer**. Le statut du complément s’affichera comme **Installation en cours**. Une fois terminé, actualisez la page pour voir le statut changer en **Installé**.

### <a name="uninstall-the-add-in"></a><a name="uninstall-add-in"></a>Désinstaller le complément

Pour désinstaller le complément, sélectionnez **Désinstaller**. Lorsque vous actualisez LCS et le complément de visibilité de stock seront supprimés. Le processus de désinstallation supprime l’inscription du complément et lance également une tâche pour nettoyer toutes les données d’entreprise stockées dans le service.

## <a name="consume-on-hand-inventory-data-from-supply-chain-management"></a>Consommez les données d’inventaire disponibles à partir de Supply Chain Management

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a>Déployer le package d’intégration de la visibilité d’inventaire

Si vous exécutez la version 10.0.17 ou antérieure de Supply Chain Management, contactez l’équipe d’assistance intégrée de la visibilité d’inventaire à l’adresse [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) pour obtenir le fichier de package. Déployez ensuite le package dans LCS.

> [!NOTE]
> Si une erreur de non-concordance de version se produit pendant le déploiement, vous devez importer manuellement le projet X++ dans votre environnement de développement. Créez ensuite le package déployable dans votre environnement de développement et déployez-le dans votre environnement de production.
> 
> Le code est inclus dans la version 10.0.18 de Supply Chain Management. Si vous exécutez cette version ou une version ultérieure, le déploiement n’est pas requis.

Assurez-vous que les fonctionnalités suivantes sont activées dans votre environnement Supply Chain Management. (Par défaut, ils sont identiques.)

| Description de fonctionnalité | Version du code | Basculer la classe |
|---|---|---|
| Activer ou désactiver l’utilisation des dimensions d’inventaire sur le tableau InventSum | 10.0.11 | InventUseDimOfInventSumToggle |
| Activer ou désactiver l’utilisation des dimensions d’inventaire sur le tableau InventSumDelta | 10.0.12 | InventUseDimOfInventSumDeltaToggle |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a>Configurer l’intégration de la visibilité du stock

1. Dans Supply Chain Management, ouvrez l’espace de travail **[Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** et activez la fonctionnalité **Intégration de la visibilité de l’inventaire**.
1. Aller à **Gestion de l’inventaire \> Installation \> Paramètres d’intégration de la visibilité de l’inventaire** et entrez l’URL de l’environnement dans lequel vous exécutez la visibilité de l’inventaire.

    Recherchez la région Azure de votre environnement LCS, puis entrez l’URL. L’URL a le format suivant :

    `https://inventoryservice.<RegionShortName>-il301.gateway.prod.island.powerapps.com`

    Par exemple, si vous êtes en Europe, votre environnement aura l’une des URL suivantes :

    - `https://inventoryservice.neu-il301.gateway.prod.island.powerapps.com`
    - `https://inventoryservice.weu-il301.gateway.prod.island.powerapps.com`

    Les régions suivantes sont disponibles actuellement.

    | Région Azure | Nom abrégé de la région |
    |---|---|
    | Est de l’Australie | eau |
    | Sud-est de l’Australie | seau |
    | Centre du Canada | cca |
    | Canada Est | eca |
    | Nord de l’Europe | neu |
    | Ouest de l’Europe | weu |
    | Est des États-Unis | eus |
    | Ouest des États-Unis | wus |

1. Aller à **Gestion de l’inventaire \> Périodique \> Intégration de la visibilité de l’inventaire** et activez le travail. Tous les événements de changement d’inventaire de Supply Chain Management seront désormais publiés dans la visibilité des stocks.

## <a name="the-inventory-visibility-add-in-public-api"></a><a name="inventory-visibility-public-api"></a>L’API publique du complément de visibilité de stock

L’API REST publique du complément de visibilité de stock présente plusieurs points de terminaison d’intégration spécifiques. Elle prend en charge trois types d’interactions principaux :

- Publication des modifications de stock disponibles du complément à partir d’un système externe
- Interrogation des quantités en stock actuelles à partir d’un système externe
- Synchronisation automatique avec le stock Supply Chain Management à portée de main

La synchronisation automatique ne fait pas partie de l’API publique. Au lieu de cela, il est géré en arrière-plan pour les environnements dans lesquels le complément de visibilité d’inventaire est activé.

### <a name="authentication"></a><a name="inventory-visibility-authentication"></a>Authentification

Le jeton de sécurité de la plateforme est utilisé pour appeler le complément de visibilité d’inventaire. Par conséquent, vous devez générer un jeton *Azure Active Directory (Azure AD)* en utilisant votre application Azure AD. Vous devez ensuite utiliser le jeton Azure AD pour obtenir le *jeton d’accès* du service de sécurité.

Obtenez un jeton de service de sécurité en procédant comme suit :

1. Connectez-vous au portail Azure et utilisez-le pour trouver le `clientId` et le `clientSecret` de votre application Supply Chain Management.
1. Récupérez un jeton Azure Active Directory (`aadToken`) en envoyant une requête HTTP avec les propriétés suivantes :
    - **URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`
    - **Méthode** - `GET`
    - **Contenu du corps (données du formulaire)**  :

        | clé | valeur |
        | --- | --- |
        | client_id | ${aadAppId} |
        | client_secret | ${aadAppSecret} |
        | grant_type | client_credentials |
        | resource | 0cdb527f-a8d1-4bf8-9436-b352c68682b2 |
1. Vous devriez recevoir un `aadToken` en réponse, qui ressemble à l’exemple suivant.

    ```json
    {
        "token_type": "Bearer",
        "expires_in": "3599",
        "ext_expires_in": "3599",
        "expires_on": "1610466645",
        "not_before": "1610462745",
        "resource": "0cdb527f-a8d1-4bf8-9436-b352c68682b2",
        "access_token": "eyJ0eX...8WQ"
    }
    ```

1. Formulez une requête JSON qui ressemble à ce qui suit :

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{Your_AADToken}",
        "scope":"https://inventoryservice.operations365.dynamics.com/.default",
        "context": "5dbf6cc8-255e-4de2-8a25-2101cd5649b4",
        "context_type": "finops-env"
    }
    ```

    Où :
    - La valeur `client_assertion` doit être le `aadToken` que vous avez reçu à l’étape précédente.
    - La valeur `context` doit être l’ID d’environnement dans lequel vous souhaitez déployer le complément.
    - Définissez toutes les autres valeurs comme indiqué dans l’exemple.

1. Envoyez une requête HTTP avec les propriétés suivantes :
    - **URL** - `https://securityservice.operations365.dynamics.com/token`
    - **Méthode** - `POST`
    - **En-tête HTTP** : incluez la version de l’API (la clé est `Api-Version` et la valeur est `1.0`)
    - **Contenu du corps** : incluez la requête JSON que vous avez créée à l’étape précédente.

1. Vous obtiendrez un `access_token` en réponse. C’est ce dont vous avez besoin en tant que jeton de support pour appeler l’API de visibilité de stock. Voici un exemple :

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="sample-request"></a><a name="inventory-visibility-sample-request"></a>Exemple de requête

Pour votre référence, voici un exemple de requête http ; vous pouvez utiliser n’importe quel outil ou langage de code pour envoyer cette requête, tel que ``Postman``.

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand

# Method
Post

# Header
# replace {access_token} with the one get from security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "quantities": {
        "pos": {
            "inbound": 5
        }  
    },
    "dimensions": {
        "SizeId": "Small",
        "ColorId": "Red",
        "SiteId": "1",
        "LocationId": "11"
    }
}
```

### <a name="configure-the-inventory-visibility-api"></a><a name="inventory-visibility-configuration"></a>Configurer l’API de visibilité de stock

Avant d’utiliser le service, vous devez effectuer les configurations décrites dans les sous-sections suivantes. La configuration peut varier en fonction des détails de votre environnement. Il comprend principalement quatre parties :

- [Partitionnement](#partitioning)
- [Configurations des dimensions](#dimension-configurations)
- [Indexation](#indexing)
- [Mesure personnalisée](#custom-measurement)

#### <a name="partitioning"></a>Partitionnement

Le partitionnement peut influencer considérablement les performances de l’API de visibilité d’inventaire. C’est une bonne idée de définir un schéma qui permet de petits regroupements de données tout en permettant des requêtes de données significatives.

L’`organizationId` (`dataAreaId` dans Supply Chain Management) fera toujours partie du partitionnement et, par défaut, la visibilité du stock est définie pour partitionner par dimensions comme *Site + Localisation*. Cela signifie que le service doit toujours être interrogé avec ces dimensions définies sur les filtres.

> [!NOTE]
> *Site* et *Emplacement* sont deux dimensions générales par défaut dans la visibilité du stock. Dans Supply Chain Management, ces dimensions sont appelées *Site* (`InventSiteId`) et *Entrepôt* (`InventLocationId`)

### <a name="dimension-configurations"></a>Configurations des dimensions

La visibilité du stock fournira une liste de dimensions générales par défaut pour permettre l’intégration du système source multiple.

Le tableau suivant répertorie les dimensions d’inventaire qui seront les noms de dimension par défaut dans la visibilité du stock.

| Type de dimension | Nom de dimension |
|---|---|
| Produit | `ColorId` |
| Produit | `SizeId` |
| Produit | `StyleId` |
| Produit | `ConfigId` |
| Suivi | `BatchId` |
| Suivi | `SerialId` |
| Entrepôt | `LocationId` |
| Entrepôt | `SiteId` |
| Statut du stock | `StatusId` |
| Spécifique à l’entrepôt | `WMSLocationId` |
| Spécifique à l’entrepôt | `WMSPalletId` |
| Spécifique à l’entrepôt | `LicensePlateId` |

> [!NOTE]
> Le type de dimension répertorié dans le tableau précédent est à titre indicatif uniquement. Vous n’avez pas besoin de définir le type de dimension dans la visibilité du stock.

Si une dimension personnalisée existe et doit passer à une valeur par défaut lorsqu’elle est utilisée par la visibilité du stock, vous pouvez configurer le nom **Dimension personnalisée** dans la visibilité du stock.

Les systèmes externes accèdent à la visibilité du stock via des API RESTful qui permettent d’interroger des informations disponibles sur des ensembles de dimensions donnés. Pour l’intégration, la visibilité du stock vous permet de configurer la *source de données de canal externe* et la dimension source des *dimensions cibles* dans la visibilité du stock.

Les dimensions cibles doivent être l’une des suivantes :

- Dimensions par défaut dans la visibilité du stock
- Dimensions personnalisées

Le but de la configuration des dimensions est de standardiser l’intégration multi-système pour la requête sur les dimensions et l’événement de publication avec les dimensions.

#### <a name="indexing"></a>Indexation

La plupart du temps, la requête de stock disponible sera non seulement au niveau "total" le plus élevé, mais vous souhaiterez peut-être voir les résultats agrégés en fonction des dimensions de stock.

La visibilité du stock offre une certaine flexibilité en vous permettant de configurer les index, qui sont basés sur la dimension ou la combinaison des dimensions.

> [!NOTE]
> Actuellement, vous ne pouvez configurer les index que jusqu’à un maximum de cinq. Vous devez examiner attentivement la dimension ou la combinaison de dimensions que vous utiliserez avant la mise en œuvre pour vous assurer qu’elle répondra aux besoins de votre entreprise. Par exemple, si vous souhaitez interroger les produits comme suit :

- Recherchez le produit agrégé disponible par les dimensions *Couleur* et *Taille*.
- Dans certains cas, vous souhaitez simplement interroger le produit au total.

Vous auriez deux index définis comme suit :

- `["ColorId", "SizeId"]`
- `[]`

Le crochet vide sera agrégé en fonction de l’ID de produit dans la partition.

L’indexation définit comment vous pouvez regrouper vos résultats en fonction du paramètre de requête `groupBy`. Dans ce cas, si vous ne définissez aucune valeur `groupBy`, vous obtiendrez les totaux par `productid`. Sinon, si vous définissez `groupBy` comme `groupBy=ColorId&groupBy=SizeId`, vous obtiendrez plusieurs lignes renvoyées, en fonction des différentes combinaisons de couleurs et de tailles du système.

Vous pouvez mettre vos critères de requête dans le corps de la requête.

Voici un exemple de requête sur le produit avec une combinaison de couleur et de taille.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct1", "MyProduct2"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

Pour le champ `filters`, actuellement seul `ProductId` prend en charge plusieurs valeurs. Si `ProductId` est un tableau vide, tous les produits seront interrogés.

#### <a name="custom-measurement"></a>Mesure personnalisée

Les quantités de mesure par défaut sont liées à Supply Chain Management. Cependant, vous souhaiterez peut-être avoir une quantité composée d’une combinaison des mesures par défaut. Pour ce faire, vous pouvez avoir une configuration de quantités personnalisées, qui seront ajoutées à la sortie des requêtes en main.

La fonctionnalité vous permet simplement de définir un ensemble de mesures qui seront ajoutées, et/ou un ensemble de mesures qui seront soustraites, afin de la mesure personnalisée.

Par exemple, avec la condition de requête suivante, vous configurerez la quantité de mesure personnalisée comme `MyCustomAvailableforReservation` à consommer par le système de consommation.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]

```



| Système de consommation | Mesures calculées | Source de données | Modificateur | Type de calcul du modificateur |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | Addition |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | Addition |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | Soustraction |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | Addition |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | Soustraction |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | Addition |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | Addition |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | Soustraction |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | Soustraction |

Avec cela, la requête sur la quantité de mesure personnalisée renverra la sortie suivante.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

La sortie `MyCustomAvailableforReservation` est basée sur le paramètre de calcul dans les mesures personnalisées comme :  
 *100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*

### <a name="posting-on-hand-changes"></a>Publication des modifications en stock

L’URL exacte sur laquelle l’événement sera publié dépendra de votre région géographique. Il prendra la forme :

`https://{serviceURL}/api/environment/{environmentId}/onhand`

Une fois authentifiée, cette URL peut être utilisée avec la méthode HTTP `POST` pour envoyer des événements de modification en main au service.

Un en-tête spécial est utilisé pour communiquer avec les services Dynamics 365 via des requêtes HTTP, indiquant l’ID d’environnement de l’instance Supply Chain Management à laquelle les données sont liées. Par exemple :

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a>Exemple de requête de publication de modifications en main 1

Cet exemple montre un scénario dans lequel vous allez configurer la configuration de dimension dans Power Apps.

Utilisez la requête suivante pour configurer le mappage de dimension dans Power Apps :

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

Vous pouvez maintenant spécifier la `dimensionDataSource` et utilisez des dimensions personnalisées dans vos requêtes. Le système convertira automatiquement les dimensions personnalisées en dimensions de base.

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensionDataSource": "pos",
    "dimensions": {
        "PosSizeId": "Large",
        "PosColorId": "Red",
        "PosSiteId": "2",
        "PosLocationId": "21"
    }
}
```

#### <a name="posting-on-hand-changes-query-example-2"></a>Exemple de requête de publication de modifications en main 2

Cet exemple montre un scénario dans lequel aucun mappage n’est configuré pour la configuration de dimension dans Power Apps, donc la publication doit également utiliser les dimensions de base. Toutes les dimensions doivent être des dimensions de base lorsque le champ `dimensionDataSource` est nul, vide ou espace.

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensions": {
        "SizeId": "Large",
        "ColorId": "Red",
        "SiteId": "2",
        "LocationId": "21"
    }
}
```

#### <a name="json-document-field-properties"></a>Propriétés du champs de documents JSON

Les champs des exemples de requête JSON fournis précédemment ont les propriétés répertoriées dans le tableau suivant.

| ID champ | Description |
|---|---|
| `id` | Un ID unique pour l’événement de modification spécifique. Cet ID est utilisé pour garantir qu’en cas d’échec de la communication avec le service pendant la comptabilisation, la soumission à nouveau de l’événement n’entraînerait pas le comptage du même événement deux fois dans le système. |
| `organizationId` | L’identificateur de l’organisation liée à l’événement. Cela correspond aux organisations de gestion de Supply Chain Management ou aux ID de zone de données. |
| `productId` | Identificateur du produit en question. |
| `quantity` | La quantité dont le stock doit être changé. Si, par exemple, 10 nouveaux bagels étaient ajoutés à une étagère, cette valeur serait de 10. Si 3 bagels étaient ensuite retirés de l’étagère ou vendus, cette valeur serait de -3. |
| `dimensionDataSource` | Source de données des dimensions utilisées dans l’événement et la requête de modification de publication. Si vous spécifiez la source de données, vous pouvez utiliser les dimensions personnalisées de la source de données spécifiée. Avec la configuration des dimensions, la visibilité du stock peut mapper les dimensions personnalisées aux dimensions générales par défaut. Si la `dimensionDataSource` n’est pas spécifié, vous ne pouvez utiliser que les dimensions générales par défaut dans vos requêtes.   |
| `dimensions` | Un sac dynamique de paires clé/valeur. Celles-ci correspondront à certaines des dimensions de Supply Chain Management, mais vous pouvez également ajouter des dimensions personnalisées (comme *Source*) qui peut indiquer si l’événement provenait de Supply Chain Management ou d’un système externe. |

### <a name="querying-current-on-hand"></a>Interrogation actuellement disponible

Le point de terminaison pour interroger le stock actuel aura une URL similaire :

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

Il sera interrogé avec la méthode HTTP `POST`.

#### <a name="current-on-hand-query-example-1"></a>Exemple de requête en main actuel 1

Cet exemple montre un scénario dans lequel vous disposez déjà d’une configuration de dimension terminée dans Power Apps.

Utilisez la requête suivante pour configurer le mappage de dimension dans Power Apps :

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

Vous pouvez maintenant spécifier la `dimensionDataSource` et utilisez des dimensions personnalisées dans vos requêtes. Le système convertira automatiquement les dimensions personnalisées en dimensions de base. Vous pouvez spécifier la `DimensionDataSource` dans `filters` et spécifiez des dimensions personnalisées dans `filters` et `groupByValues`. Le système convertira automatiquement les dimensions personnalisées en dimensions de base.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "DimensionDataSource": ["Pos"],
        "PosLocationId": ["21"],
        "PosSiteId": ["2"],
        "PosColorId": ["Red"]
    },
    "groupByValues": [
        "PosSizeId",
        "PosColorId"
    ],
    "returnNegative": true
}
```

#### <a name="current-on-hand-query-example-2"></a>Exemple de requête en main actuel 2

Cet exemple montre un scénario dans lequel aucun mappage n’est configuré pour la configuration de dimension dans Power Apps, donc la publication doit également utiliser les dimensions de base. Toutes les dimensions doivent être des dimensions de base lorsque le champ `dimensionDataSource`, sous `filters`, est nul, vide ou espace.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="example-return-result"></a>Exemple de résultat de retour

Les requêtes présentées dans les exemples précédents peuvent renvoyer un résultat comme celui-ci.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

Notez que les champs de quantités sont structurés comme un dictionnaire de mesures et de leurs valeurs associées.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
