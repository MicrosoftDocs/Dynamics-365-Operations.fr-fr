---
title: Installer le complément de visibilité de stock
description: Cette rubrique décrit comment installer le module complémentaire de visibilité des stocks pour Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: b2b85f533a3318701ed08857b899cf9bdd103863
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7474818"
---
# <a name="install-and-set-up-inventory-visibility"></a>Installer et configurer la visibilité des stocks

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Cette rubrique décrit comment installer le module complémentaire de visibilité des stocks pour Microsoft Dynamics 365 Supply Chain Management.

Vous devez utiliser Microsoft Dynamics Lifecycle Services (LCS) pour installer le module complémentaire de visibilité des stocks. LCS est un portail de collaboration qui fournit un environnement et un ensemble de services régulièrement mis à jour qui vous aident à gérer le cycle de vie des applications de vos applications Finance and Operations.

Pour plus d’informations, voir [Ressources Lifecycle Services](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

## <a name="inventory-visibility-prerequisites"></a>Conditions préalables pour la visibilité des stocks

Avant de pouvoir installer la Visibilité des stocks, vous devez effectuer les tâches suivantes :

- Obtenez un projet d’implémentation LCS où au moins un environnement est déployé.
- Assurez-vous que les conditions préalables à la configuration de modules complémentaires ont été remplies. Pour plus d'informations sur ces conditions préalables, voir [Présentation des modules complémentaires](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). La visibilité de l’inventaire ne nécessite pas de liaison en double écriture.
- Contactez l’équipe produit de la visibilité des stocks à [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) pour obtenir les fichiers requis suivants :

    - `InventoryServiceApplication.PackageDeployer.zip`
    - `Inventory Visibility Integration.zip` (si la version de Supply Chain Management que vous exécutez est antérieure à la version 10.0.18)

> [!NOTE]
> Les pays et régions actuellement pris en charge sont le Canada (CCA, ECA), les États-Unis (WUS, EUS), l'Union européenne (NEU, WEU), le Royaume-Uni (SUK, WUK), l'Australie (EAU, SEAU), le Japon (EJP, WJP) et le Brésil (SBR, SCUS).

Si vous avez des questions sur ces conditions préalables, contactez l’équipe produit de visibilité des stocks.

## <a name="set-up-dataverse"></a><a name="setup-microsoft-dataverse"></a>Paramétrer Dataverse

Pour installer Dataverse afin qu'il puisse être utilisé avec la visibilité des stocks, utilisez l'outil Package Deployer pour déployer le package de visibilité des stocks. Les sous-sections suivantes décrivent comment effectuer chaque tâche.

> [!NOTE]
> Actuellement, seuls les environnements Dataverse créés à l'aide de LCS sont pris en charge. Si votre environnement Dataverse a été créé d'une autre manière (par exemple, en utilisant le centre d'administration Power Apps) et s'il est lié à votre environnement Supply Chain Management, vous devez d'abord contacter l'équipe produit de visibilité des stocks pour résoudre le problème de mappage. Ensuite, vous pouvez installer le module complémentaire de visibilité des stocks.

### <a name="migrate-from-an-old-version-of-the-dataverse-solution"></a>Migrer à partir d'une ancienne version de la Solution Dataverse

Si vous avez installé une ancienne version de la solution Dataverse de visibilité des stocks, utilisez ces instructions pour mettre à jour votre version. Deux cas sont disponibles :

- **Cas 1 :** Si vous configurez manuellement Dataverse en important la solution `Inventory Visibility Dataverse Solution_1_0_0_2_managed.zip`, procédez comme suit :

    1. Téléchargez les trois fichiers suivants :

        - `Inventory Visibility Dataverse Solution_1_0_0_3_managed.zip`
        - `InventoryServiceBase_managed.cab`
        - `InventoryServiceApplication.PackageDeployer.zip`

    1. Importez manuellement `Inventory Visibility Dataverse Solution_1_0_0_3_managed.zip` et `InventoryServiceBase_managed.cab` dans Dataverse en suivant ces étapes :

        1. Ouvrez l’URL de votre environnement Dataverse.
        1. Ouvrez la page **Solutions**.
        1. Sélectionnez **Importer**.

    1. Utilisez l'outil Package Deployer pour déployer le package `InventoryServiceApplication.PackageDeployer.zip`. Pour obtenir des instructions, consultez la section [Utiliser l'outil Package Deployer pour déployer le package](#deploy-package) plus loin dans cette rubrique.

- **Cas 2 :** Si vous configurez Dataverse en utilisant l'outil Package Deployer avant l'installation de l'ancien package `.*PackageDeployer.zip`, téléchargez `InventoryServiceApplication.PackageDeployer.zip`, et faites une mise à jour. Pour obtenir des instructions, consultez la section [Utiliser l'outil Package Deployer pour déployer le package](#deploy-package).

### <a name="use-the-package-deployer-tool-to-deploy-the-package"></a><a name="deploy-package"></a>Utiliser l'outil Package Deployer pour déployer le package

1. Installez les outils de développement comme décrit dans [Télécharger les outils depuis NuGet](/dynamics365/customerengagement/on-premises/developer/download-tools-nuget).
1. Débloquez le fichier `InventoryServiceApplication.PackageDeployer.zip` que vous avez téléchargé à partir du groupe Teams en suivant ces étapes :

    1. Sélectionnez et maintenez la sélection (ou cliquez avec le bouton droit) sur le fichier, puis sélectionnez **Propriétés**.
    1. Dans la boîte de dialogue **Propriétés**, sur l'onglet **Général**, trouvez la section **Sécurité**, sélectionnez **Débloquer**, et appliquez la modification. S'il n'y a pas de section **Sécurité** sur l'onglet **Général**, le fichier n'est pas bloqué. Dans ce cas, passez à l’étape suivante.

    ![Déblocage du fichier téléchargé](media/unblock-file.png "Déblocage du fichier téléchargé")

1. Décompressez `InventoryServiceApplication.PackageDeployer.zip` pour trouver les éléments suivants :

    - Dossier `InventoryServiceApplication`
    - Fichier `[Content_Types].xml`
    - Fichier `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll`

1. Copiez chacun de ces éléments dans le répertoire `.\Tools\PackageDeployment`. (Ce répertoire a été créé lorsque vous avez installé les outils de développement.)
1. Exécutez `.\Tools\PackageDeployment\PackageDeployer.exe` et suivez les instructions sur votre écran pour importer les solutions.

## <a name="install-the-inventory-visibility-add-in"></a><a name="install-add-in"></a>Installer le complément de visibilité de stock

Avant d'installer le module complémentaire, enregistrez une application et ajoutez une clé secrète client à Azure Active Directory (Azure AD) sous votre abonnement Azure. Pour les instructions, voir [Enregistrer une application](/azure/active-directory/develop/quickstart-register-app) et [Ajouter une clé secrète client](/azure/active-directory/develop/quickstart-register-app#add-a-certificate). Assurez-vous de noter des valeurs des **ID de l'application (client)** , **Clé secrète client**, et **ID du locataire**, car vous en aurez besoin plus tard.

Après avoir enregistré une application et ajouté un clé secrète client à Azure AD, suivez ces étapes pour installer le module complémentaire de visibilité des stocks.

1. Connectez-vous à [LCS](https://lcs.dynamics.com/Logon/Index).
1. Sur la page d’accueil, sélectionnez le projet dans lequel votre environnement est déployé.
1. Sur la page du projet, sélectionnez l’environnement dans lequel vous souhaitez installer le complément.
1. Sur la page d’environnement, faites défiler vers le bas jusqu’à ce que vous trouviez la section **Compléments d’environnement** dans la section **Intégration Power Platform**. Là, vous pouvez trouver le nom de l'environnement Dataverse.
1. Dans la section **Compléments de l’environnement**, sélectionnez **Installer un nouveau complément**.

    ![Page de l’environnement dans LCS](media/inventory-visibility-environment.png "Page de l’environnement dans LCS")

1. Sélectionnez le lien **Installer un nouveau complément**. Une liste des compléments disponibles s’ouvre.
1. Dans la liste, sélectionnez **Visibilité des stocks**.
1. Définissez les champs suivants pour votre environnement :

    - **ID de l’application AAD (client)**  : saisissez l’ID d’application Azure AD que vous avez créé et noté précédemment.
    - **ID locataire AAD** : saisissez l’ID de locataire que vous avez noté précédemment.

    ![Page de configuration de module complémentaire](media/inventory-visibility-setup.png "Page de configuration de module complémentaire")

1. Acceptez les termes et conditions en cochant la case **Termes et conditions**.
1. Sélectionnez **Installer**. Le statut du complément s’affiche comme **Installation en cours**. Lorsque l’installation est terminée, actualisez la page. Le statut devrait changer pour **Installé**.

> [!IMPORTANT]
> Si vous avez plusieurs environnements LCS, créez une application Azure AD différente pour chaque environnement. Si vous utilisez le même ID d'application et le même ID de locataire pour installer le complément de visibilité des stocks pour différents environnements, un problème de jeton se produira pour les environnements plus anciens. Seul le dernier installé sera valide.

## <a name="uninstall-the-inventory-visibility-add-in"></a><a name="uninstall-add-in"></a>Désinstaller le complément de visibilité des stocks

Pour désinstaller le complément de visibilité des stocks, sélectionnez **Désinstaller** sur la page LCS. Le processus de désinstallation met fin au complément de visibilité des stocks, annule l'enregistrement du complément de LCS et supprime toutes les données temporaires stockées dans le cache de données du complément de visibilité des stocks. Cependant, les données de stock principales qui sont stockées dans votre abonnement Dataverse ne sont pas supprimées.

Pour désinstaller les données de stock stockées dans votre abonnement Dataverse, ouvrez [Power Apps](https://make.powerapps.com), sélectionnez **Environnement** dans la barre de navigation et sélectionnez l'environnement Dataverse lié à votre environnement LCS. Ensuite allez dans **Solutions**, et supprimez les cinq solutions suivantes :

- Ancrer la solution pour l’application Inventory Visibility dans les solutions Dynamics 365
- Solution d’application Dynamics 365 FNO SCM Inventory Visibility
- Configuration du service de stock
- Visibilité des stocks autonome
- Solution de base Dynamics 365 FNO SCM Inventory Visibility

Après avoir supprimé ces solutions, les données stockées dans les tables seront également supprimées.

## <a name="set-up-inventory-visibility-in-supply-chain-management"></a><a name="setup-dynamics-scm"></a>Configurer la visibilité des stocks dans Supply Chain Management

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a>Déployer le package d’intégration de la visibilité d’inventaire

Si vous exécutez la version 10.0.17 ou antérieure de Supply Chain Management, contactez l’équipe d’assistance intégrée de la visibilité d’inventaire à l’adresse [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) pour obtenir le fichier de package. Déployez ensuite le package dans LCS.

> [!NOTE]
> Si une erreur de non-concordance de version se produit pendant le déploiement, vous devez importer manuellement le projet X++ dans votre environnement de développement. Créez ensuite le package déployable dans votre environnement de développement et déployez-le dans votre environnement de production.
>
> Le code est inclus dans la version 10.0.18 de Supply Chain Management. Si vous exécutez cette version ou une version ultérieure, le déploiement n’est pas requis.

Assurez-vous que les fonctionnalités suivantes sont activées dans votre environnement Supply Chain Management. (Par défaut, ils sont identiques.)

| Description de fonctionnalité | Version du code | Basculer la classe |
|---|---|---|
| Activer ou désactiver l’utilisation des dimensions d’inventaire sur le tableau InventSum      | 10.0.11 | InventUseDimOfInventSumToggle      |
| Activer ou désactiver l’utilisation des dimensions d’inventaire sur le tableau InventSumDelta | 10.0.12 | InventUseDimOfInventSumDeltaToggle |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a>Configurer l’intégration de la visibilité du stock

Une fois que vous avez installé le complément, préparez votre système Supply Chain Management pour l'utiliser en procédant comme suit.

1. Dans Supply Chain Management, ouvrez l’espace de travail **[Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** et activez les fonctionnalités suivantes :
    - *Intégration de la visibilité des stocks* : requis.
    - *Intégration de la visibilité des stocks avec compensation des réservations* : recommandé mais facultatif. Nécessite la version 10.0.22 ou ultérieure. Pour plus d’informations, voir [Réservation dans la visibilité des stocks](inventory-visibility-reservations.md).

1. Allez dans **Gestion des stocks \> Configuration \> Paramètres de l'intégration de la visibilité des stocks**.
1. Ouvrez l'onglet **Général** et effectuez les réglages suivants :
    - **Point de terminaison de la visibilité des stocks** : saisissez l'URL de l'environnement dans lequel vous exécutez la visibilité des stocks. Pour plus d’informations, voir [Rechercher le point de terminaison de service](inventory-visibility-configuration.md#get-service-endpoint).
    - **Nombre maximal d'enregistrements dans une seule requête** : définissez le nombre maximal d'enregistrements à inclure dans une seule requête. Vous devez saisir un nombre entier positif inférieur ou égal à 1000. La valeur par défaut est 512. Nous vous recommandons fortement de conserver la valeur par défaut, à moins que vous n'ayez reçu des conseils du support Microsoft ou que vous soyez par ailleurs certain de devoir la modifier.

1. Si vous avez activé l'option *Intégration de la visibilité des stocks avec compensation des réservations*, ouvrez l'onglet **Compensation des réservations** et effectuez les réglages suivants :
    - **Activer la compensation des réservations** : définissez-le sur *Oui* pour activer cette fonctionnalité.
    - **Modificateur de la compensation des réservations** : sélectionnez le statut de la transaction de stock qui compensera les réservations effectuées sur la visibilité des stocks. Ce paramètre détermine l'étape de traitement de la commande qui déclenche les compensations. L'étape est tracée par le statut du mouvement de stock de la commande. Choisissez l’une des méthodes suivantes :
        - *Sur commande* - Pour le statut *Sur transaction*, une commande enverra une demande de compensation lors de sa création. La quantité de compensation sera la quantité de la commande créée.
        - *Réserve* - Pour le statut *Réserver la transaction commandée*, une commande enverra une demande de compensation lorsqu'elle est réservée, prélevée, validée par bon de livraison ou facturée. La demande ne sera déclenchée qu'une seule fois, pour la première étape lorsque le processus mentionné se produit. La quantité de compensation sera la quantité pour laquelle le statut de la transaction de stock sera passé de *En commande* à *Réservé commandé* (ou statut ultérieur) sur la ligne de commande correspondante.

1. Aller à **Gestion de l’inventaire \> Périodique \> Intégration de la visibilité de l’inventaire** et activez le travail. Tous les événements de changement d’inventaire de Supply Chain Management seront désormais publiés dans la visibilité des stocks.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
