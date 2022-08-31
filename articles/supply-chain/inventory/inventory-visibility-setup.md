---
title: Installer le complément de visibilité de stock
description: Cet article décrit comment installer le module complémentaire de visibilité des stocks pour Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 42c2c287e2a813f8bb07ce0c7f21f4224a217946
ms.sourcegitcommit: f2175fe5e900d39f34167d671aab5074b09cc1b8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/17/2022
ms.locfileid: "9306052"
---
# <a name="install-and-set-up-inventory-visibility"></a>Installer et configurer Inventory Visibility

[!include [banner](../includes/banner.md)]

Cet article décrit comment installer le module complémentaire de visibilité des stocks pour Microsoft Dynamics 365 Supply Chain Management.

Vous devez utiliser Microsoft Dynamics Lifecycle Services (LCS) pour installer le module complémentaire de visibilité des stocks. LCS est un portail de collaboration qui fournit un environnement et un ensemble de services régulièrement mis à jour qui vous aident à gérer le cycle de vie des applications de vos applications Finances et Opérations. Pour plus d’informations, voir [Ressources Lifecycle Services](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

> [!TIP]
> Nous vous recommandons de rejoindre le groupe d’utilisateurs du complément de visibilité du stock, où vous pouvez trouver des guides utiles, obtenir nos dernières mises à jour et poster toutes les questions que vous pourriez avoir sur l’utilisation de la visibilité du stock. Pour vous inscrire, envoyez un e-mail à l’équipe produit de Visibilité du stock à l’adresse [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) et incluez votre ID d’environnement Supply Chain Management.

## <a name="inventory-visibility-prerequisites"></a>Conditions préalables pour la visibilité des stocks

Avant de pouvoir installer la Visibilité des stocks, vous devez effectuer les tâches suivantes :

- Obtenez un projet d’implémentation LCS où au moins un environnement est déployé.
- Assurez-vous que les conditions préalables à la configuration de modules complémentaires ont été remplies. Pour plus d’informations sur ces conditions préalables, voir [Présentation des modules complémentaires](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). La visibilité de l’inventaire ne nécessite pas de liaison en double écriture.

> [!NOTE]
> Les pays et régions actuellement pris en charge sont le Canada (CCA, ECA), les États-Unis (WUS, EUS), l’Union européenne (NEU, WEU), le Royaume-Uni (SUK, WUK), l’Australie (EAU, SEAU), le Japon (EJP, WJP) et le Brésil (SBR, SCUS).

Si vous avez des questions sur ces conditions préalables, contactez l’équipe produit de visibilité du stock à [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com).

## <a name="install-the-inventory-visibility-add-in"></a><a name="install-add-in"></a>Installer le complément de visibilité de stock

Avant d’installer le module complémentaire, enregistrez une application et ajoutez une clé secrète client à Azure Active Directory (Azure AD) sous votre abonnement Azure. Pour les instructions, voir [Enregistrer une application](/azure/active-directory/develop/quickstart-register-app) et [Ajouter une clé secrète client](/azure/active-directory/develop/quickstart-register-app#add-a-certificate). Assurez-vous de noter les valeurs de **ID de l’application (client)** , **Clé secrète client**, et **ID du tenant**, car vous en aurez besoin plus tard.

> [!IMPORTANT]
> Si vous avez plusieurs environnements LCS, créez une application Azure AD différente de ces derniers. Si vous utilisez le même ID d’application et le même ID de locataire pour installer le complément de visibilité des stocks pour différents environnements, un problème de jeton se produira pour les environnements plus anciens. En tant que résultat, seule la dernière installation est valide.

Après avoir enregistré une application et ajouté un clé secrète client à Azure AD, suivez ces étapes pour installer le module complémentaire de visibilité des stocks.

1. Connectez-vous à [LCS](https://lcs.dynamics.com/Logon/Index).
1. Sur la page d’accueil, sélectionnez le projet dans lequel votre environnement est déployé.
1. Sur la page du projet, sélectionnez l’environnement dans lequel vous souhaitez installer le complément.
1. Sur la page d’environnement, faites défiler vers le bas jusqu’à ce que vous trouviez la section **Compléments d’environnement** dans la section **Intégration Power Platform**. Là, vous pouvez trouver le nom de l’environnement Dataverse. Confirmez que le nom de l’environnement Dataverse est celui que vous souhaitez utiliser pour la visibilité de l’inventaire.

    > [!NOTE]
    > Actuellement, seuls les environnements Dataverse créés à l’aide de LCS sont pris en charge. Si votre environnement  Dataverse a été créé d’une autre manière (par exemple, en utilisant le centre d’administration Power Apps) et s’il est lié à votre environnement Supply Chain Management, vous devez d’abord contacter l’équipe produit de visibilité des stocks à [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) pour résoudre le problème de mappage. Ensuite, vous pouvez installer le module complémentaire de visibilité des stocks.

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
1. Dans Dataverse, sélectionnez la section **Applications** dans la navigation de gauche et vérifiez que **Visibilité de l’inventaire** Power Apps est installé avec succès. Si la section **Apps** n’existe pas, contactez l’équipe produit de la visibilité des stocks à [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) pour obtenir les fichiers requis suivants.

> [!NOTE]
> Si l'installation à partir de la page LCS prend plus d'une heure, votre compte d'utilisateur n'a probablement pas l'autorisation d'installer des solutions dans l'environnement Dataverse. Procédez comme suit pour résoudre le problème :
>
> 1. Annulez le processus d'installation du complément de visibilité des stocks à partir de la page LCS.
> 1. Connectez-vous au [centre d'administration Microsoft 365](https://admin.microsoft.com) et assurez-vous que le compte d'utilisateur que vous souhaitez utiliser pour installer le complément dispose de la licence "Plan Dynamics 365 Unified Operations" qui lui est attribuée. Attribuez la licence si nécessaire.
> 1. Connectez-vous au [centre d'administration Power Platform](https://admin.powerplatform.microsoft.com) à l'aide du compte utilisateur correspondant. Ensuite installez le complément Visibilité des stocks en procédant comme suit :
>     1. Sélectionnez l'environnement où vous souhaitez installer le complément.
>     1. Sélectionnez **Applications Dynamics 365**.
>     1. Sélectionnez **Installer l'application**.
>     1. Sélectionnez **Visibilité des stocks**
>
> 1. Une fois l'installation terminée, revenez à la page LCS et réessayez de réinstaller le complément **Visibilité des stocks**.

## <a name="set-up-inventory-visibility-in-supply-chain-management"></a><a name="setup-dynamics-scm"></a>Configurer la visibilité des stocks dans Supply Chain Management

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a>Déployer le package d’intégration de la visibilité d’inventaire

Si vous exécutez la version 10.0.17 ou antérieure de Supply Chain Management, contactez l’équipe d’assistance intégrée de la visibilité d’inventaire à l’adresse [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) pour obtenir le fichier de package. Déployez ensuite le package dans LCS.

> [!NOTE]
> Si une erreur de non-concordance de version se produit pendant le déploiement, vous devez importer manuellement le projet X++ dans votre environnement de développement. Créez ensuite le package déployable dans votre environnement de développement et déployez-le dans votre environnement de production.
>
> Le code est inclus dans la version 10.0.18 de Supply Chain Management. Si vous exécutez cette version ou une version ultérieure, le déploiement n’est pas requis.

Assurez-vous que les fonctionnalités suivantes sont activées dans votre environnement Supply Chain Management. (Par défaut, ils sont activés.)

| Description de fonctionnalité | Version du code | Basculer la classe |
|---|---|---|
| Activer ou désactiver l’utilisation des dimensions d’inventaire sur le tableau InventSum      | 10.0.11 | InventUseDimOfInventSumToggle      |
| Activer ou désactiver l’utilisation des dimensions d’inventaire sur le tableau InventSumDelta | 10.0.12 | InventUseDimOfInventSumDeltaToggle |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a>Configurer l’intégration de la visibilité du stock

Une fois que vous avez installé le complément, préparez votre système Supply Chain Management pour l’utilisation en procédant comme suit.

1. Dans Supply Chain Management, ouvrez l’espace de travail **[Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** et activez les fonctionnalités suivantes :
    - *Intégration de la visibilité des stocks* : requis.
    - *Intégration de la visibilité des stocks avec compensation des réservations* : recommandé mais facultatif. Nécessite la version 10.0.22 ou ultérieure. Pour plus d’informations, voir [Réservation dans la visibilité des stocks](inventory-visibility-reservations.md).

1. Allez dans **Gestion des stocks \> Configuration \> Paramètres de l’intégration de la visibilité des stocks**.
1. Ouvrez l’onglet **Général** et effectuez les réglages suivants :
    - **Point de terminaison de la visibilité des stocks** : saisissez l’URL de l’environnement dans lequel vous exécutez la visibilité des stocks. Pour plus d’informations, voir [Rechercher le point de terminaison de service](inventory-visibility-configuration.md#get-service-endpoint).
    - **Nombre maximal d’enregistrements dans une seule requête** : définissez le nombre maximal d’enregistrements à inclure dans une seule requête. Vous devez saisir un nombre entier positif inférieur ou égal à 1000. La valeur par défaut est 512. Nous vous recommandons fortement de conserver la valeur par défaut, à moins que vous n’ayez reçu des conseils du support Microsoft ou que vous soyez par ailleurs certain de devoir la modifier.

1. Si vous avez activé l’option *Intégration de la visibilité des stocks avec compensation des réservations*, ouvrez l’onglet **Compensation des réservations** et effectuez les réglages suivants :
    - **Activer la compensation des réservations** : définissez-le sur *Oui* pour activer cette fonctionnalité.
    - **Modificateur de la compensation des réservations** : sélectionnez le statut de la transaction de stock qui compensera les réservations effectuées sur la visibilité des stocks. Ce paramètre détermine l’étape de traitement de la commande qui déclenche les compensations. L’étape est tracée par le statut du mouvement de stock de la commande. Choisissez l’une des options suivantes :
        - *Sur commande* – Pour le statut *Sur transaction*, une commande enverra une demande de compensation lors de sa création. La quantité de compensation sera la quantité de la commande créée.
        - *Réserve* – Pour le statut *Réserver la transaction commandée*, une commande enverra une demande de compensation lorsqu’elle est réservée, prélevée, validée par bon de livraison ou facturée. La demande ne sera déclenchée qu’une seule fois, pour la première étape lorsque le processus mentionné se produit. La quantité de compensation sera la quantité pour laquelle le statut de la transaction de stock sera passé de *En commande* à *Réservé commandé* (ou statut ultérieur) sur la ligne de commande correspondante.

1. Aller à **Gestion de l’inventaire \> Périodique \> Intégration de la visibilité de l’inventaire** et activez le travail. Tous les événements de changement d’inventaire de Supply Chain Management seront désormais publiés dans la visibilité des stocks.

## <a name="uninstall-the-inventory-visibility-add-in"></a><a name="uninstall-add-in"></a>Désinstaller le complément de visibilité des stocks

Pour installer le complément Inventory Visibility, procédez comme suit :

1. Connectez-vous à Supply Chain Management.
1. Aller à **Gestion de l’inventaire \> Périodique \> Intégration de Inventory Visibility** et désactivez la tâche.
1. Accédez à LCS et ouvrez la page de l’environnement dans lequel vous souhaitez désinstaller le complément (voir aussi [Installer le complément de Inventory Visibility](#install-add-in)).
1. Sélectionnez **Désinstaller**.
1. Le processus de désinstallation met fin au complément de Inventory Visibility, annule l’enregistrement du complément de LCS et supprime toutes les données temporaires stockées dans le cache de données du complément de Inventory Visibility. Cependant, les données d'inventaire principales qui sont synchronisées à votre abonnement Dataverse ne sont pas supprimées. Pour supprimer ces données, terminez le reste de cette procédure.
1. Ouvrez [Power Apps](https://make.powerapps.com).
1. Sélectionnez **Environnement** sur la barre de navigation
1. Sélectionnez l'environnement Dataverse lié à votre environnement LCS.
1. Allez dans **Solutions**, et supprimez les solutions suivantes dans cet ordre :
    1. Ancrer la solution pour l’application Inventory Visibility dans les solutions Dynamics 365
    1. Solution d’application Dynamics 365 FNO SCM Inventory Visibility
    1. Configuration du service de stock
    1. Visibilité des stocks autonome
    1. Solution de base Dynamics 365 FNO SCM Inventory Visibility

    Après avoir supprimé ces solutions, les données stockées dans les tables seront également supprimées.

> [!NOTE]
> Si vous restaurez une base de données Supply Chain Management après avoir désinstallé le complément de Inventory Visibility, et souhaitez réinstaller le complément, assurez-vous que vous avez supprimé les anciennes données de Inventory Visibility qui sont stockées dans votre abonnement Dataverse (comme décrit dans la procédure précédente) avant de réinstaller le complément. Cela évitera les problèmes d’incohérence des données qui pourraient autrement se produire.

## <a name="clean-inventory-visibility-data-from-dataverse-before-restoring-the-supply-chain-management-database"></a><a name="restore-environment-database"></a>Nettoyez les données de Inventory Visibility de Dataverse avant de restaurer la base de données de Supply Chain Management.

Si vous étiez entrain d'utiliser Inventory Visibility et vous restaurez la base de données de Supply Chain Management, votre base de données restaurée peut contenir des données qui ne sont plus cohérentes avec les données précédemment synchronisées par Inventory Visibility sur Dataverse. Cette incohérence des données peut entraîner des erreurs système et d’autres problèmes. Par conséquent, il est important que vous nettoyiez toujours toutes les données liées à Inventory Visibility de Dataverse avant toute restauration d'une base de données de Supply Chain Management.

Si vous devez restaurer une base de données Supply Chain Management, utilisez la procédure suivante :

1. Désinstallez le complément Inventory Visibility et supprimez toutes les données y relatives dans Dataverse, comme décrit dans [Désinstallez le complément Inventory Visibility](#uninstall-add-in)
1. Restaurez votre base de données Supply Chain Management, par exemple comme décrit dans [restauration à un instant dans le passé de la base de données (PITR)](../../fin-ops-core/dev-itpro/database/database-point-in-time-restore.md) ou [restauration à un instant dans le passé de la base de données de production à un environnement bac à sable](../../fin-ops-core/dev-itpro/database/database-pitr-prod-sandbox.md).
1. Si vous souhaitez toujours l’utiliser, réinstallez et configurez le complément Inventory Visibility comme décrit dans [Installer le complément de Inventory Visibility](#install-add-in) et [Configurez l’intégration de Inventory Visibility](#setup-inventory-visibility-integration)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
