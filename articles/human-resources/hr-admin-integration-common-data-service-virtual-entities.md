---
title: Configurer des tables virtuelles Dataverse
description: Cette rubrique montre comment configurer des tables virtuelles pour Dynamics 365 Human Resources. Générez et mettez à jour des tables virtuelles existantes et analysez les tables générées et disponibles.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f0dac25ede6c9b9dfcfa1be1f1a5f4d7a7752112
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6344712"
---
# <a name="configure-dataverse-virtual-tables"></a>Configurer des tables virtuelles Dataverse

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Dynamics 365 Human Resources est une source de données virtuelle dans Microsoft Dataverse. Il fournit des opérations de création, de lecture, de mise à jour et de suppression (CRUD) complètes à partir de Dataverse et Microsoft Power Platform. Les données des tables virtuelles ne sont pas stockées dans Dataverse, mais dans la base de données de l’application.

Pour activer les opérations CRUD sur les entités Ressources humaines à partir de Dataverse, vous devez rendre les entités disponibles en tant que tables virtuelles dans Dataverse. Cela vous permet d’effectuer des opérations CRUD à partir de Dataverse et Microsoft Power Platform sur les données contenues dans les ressources humaines. Les opérations prennent également en charge les validations complètes de la logique métier de Human Resources pour garantir l’intégrité des données lors de l’écriture des données dans les entités.

> [!NOTE]
> Les entités Human Resources correspondent aux tables Dataverse. Pour plus d’informations sur Dataverse (auparavant Common Data Service) et les mises à jour terminologiques, voir [Qu’est-ce que Microsoft Dataverse ?](/powerapps/maker/data-platform/data-platform-intro)

## <a name="available-virtual-tables-for-human-resources"></a>Tables virtuelles disponibles pour Human Resources

Toutes les entités Open Data Protocol (OData) dans Human Resources sont disponibles en tant que tables virtuelles dans Dataverse. Elles sont également disponibles dans Power Platform. Vous pouvez désormais créer des applications et des expériences avec des données directement à partir de Human Resources avec une capacité CRUD complète, sans copier ni synchroniser les données vers Dataverse. Vous pouvez utiliser des portails Power Apps pour créer des sites Web externes qui permettent des scénarios de collaboration pour les processus métier dans Human Resources.

Vous pouvez afficher la liste des tables virtuelles activées dans l’environnement et commencer à travailler avec les tables dans [Power Apps](https://make.powerapps.com), dans la solution **Tables virtuelles Dynamics 365 HR**.

![Tables virtuelles Dynamics 365 HR dans Power Apps.](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-tables-versus-native-tables"></a>Tables virtuelles et tables natives

Les tables virtuelles pour Human Resources ne sont pas les mêmes que les tables Dataverse créées pour Human Resources. 

Les tables natives de Human Resources sont générées séparément et gérées dans la solution HCM Common dans Dataverse. Avec les tables natives, les données sont stockées dans Dataverse et elles nécessitent une synchronisation avec la base de données applicative de Human Resources.

> [!NOTE]
> Pour obtenir la liste des tables Dataverse natives pour Human Resources, voir [Tables Dataverse](./hr-developer-entities.md).

## <a name="setup"></a>Paramétrage

Suivez ces étapes de configuration pour activer les tables virtuelles dans votre environnement.

### <a name="enable-virtual-tables-in-human-resources"></a>Activer des tables virtuelles dans Human Resources

Tout d’abord, vous devez activer les tables virtuelles dans l’espace de travail **Gestion des fonctionnalités**.

1. Dans Human Resources, sélectionnez **Administration du système**.

2. Sélectionnez la vignette **Gestion des fonctionnalités**.

3. Sélectionnez **Prise en charge de tables virtuelles pour HR dans Dataverse**, puis sélectionnez **Activer**.

Pour plus d’informations sur l’activation et la désactivation des fonctionnalités en version préliminaire, consultez [Gérer les fonctionnalités](hr-admin-manage-features.md).

### <a name="register-the-app-in-microsoft-azure"></a>Enregistrez l’application dans Microsoft Azure

Vous devez inscrire votre instance de Human Resources dans le portail Azure afin que la plateforme d’identité Microsoft puisse fournir des services d’authentification et d’autorisation pour l’application et les utilisateurs. Pour plus d’informations sur l’enregistrement des applications dans Azure, voir [Démarrage rapide : enregistrer une application avec la plate-forme d’identité Microsoft](/azure/active-directory/develop/quickstart-register-app).

1. Ouvrez le portail [Microsoft Azure](https://portal.azure.com).

2. Dans la liste de services Azure, cliquez sur **Enregistrements d’application**.

3. Sélectionnez **Nouvelle inscription**.

4. Dans le champ **Nom**, entrez un nom descriptif pour l’application. Par exemple, **Tables virtuelles Dynamics 365 Human Resources**.

5. Dans le champ **URI de redirection**, saisissez l’URL de l’espace de noms de votre instance Human Resources.

6. Sélectionnez **Enregistrer**.

7. Une fois l’inscription terminée, le portail Azure affiche le volet **Aperçu** d’inscription de l’application, qui comprend son **ID d’application (client)**. Prenez note de l’**ID d’application (client)** à ce stade. Vous devez saisir ces informations lorsque vous [Configurez la source de données de table virtuelle](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).

8. Dans le volet de navigation de gauche, sélectionnez **Certificats et secrets**.

9. Dans la section **Clés secrètes client** de la page, sélectionnez **Nouvelle clé secrète client**.

10. Fournissez une description, sélectionnez une durée et sélectionnez **Ajouter**.

11. Enregistrez la valeur du secret à partir de la propriété **Valeur** de la table. Vous devez saisir ces informations lorsque vous [Configurez la source de données de table virtuelle](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).

    > [!IMPORTANT]
    > Assurez-vous de prendre note de la valeur du secret à ce stade. Le secret n’est plus jamais affiché une fois que vous avez quitté cette page.

### <a name="install-the-dynamics-365-hr-virtual-table-app"></a>Installer l’application Tables virtuelles Dynamics 365 HR

Installez l’application Tables virtuelles Dynamics 365 HR dans votre environnement Power Apps pour déployer le package de solution de table virtuelle dans Dataverse.

1. Dans Human Resources, ouvrez la page **Intégration Microsoft Dataverse**.

2. Sélectionnez l’onglet **Tables virtuelles**.

3. Sélectionnez **Installer l’application de table virtuelle**.

### <a name="configure-the-virtual-table-data-source"></a>Configurer la source de données de table virtuelle

L’étape suivante consiste à configurer la source de données de table virtuelle dans l’environnement Power Apps.

1. Ouvrez le [Centre d’administration Power Platform](https://admin.powerplatform.microsoft.com).

2. Dans la liste **Environnements**, sélectionnez l’environnement Power Apps associé à votre instance Human Resources.

3. Sélectionnez l’**URL d’environnement** dans la section **Détails** de la page.

4. Dans **Hub état solution**, sélectionnez l’icône **Recherche avancée** en haut à droite de la page de l’application.

5. Sur la page **Recherche avancée**, dans la liste déroulante **Rechercher**, sélectionnez Configurations de source de données virtuelle **Finance and Operations**.

   > [!NOTE]
   > L’installation de l’application de table virtuelle à partir de l’étape de configuration précédente peut prendre quelques minutes. Si **Configurations de source de données virtuelle Finance and Operations** n’est pas disponible dans la liste, attendez une minute et actualisez la liste.

6. Sélectionnez **Résultats**.

7. Sélectionnez l’enregistrement **Source de données Microsoft HR**.

8. Entrez les informations requises pour la configuration de la source de données :

   - **URL cible** : URL de votre espace de noms Human Resources. Le format de l’URL cible est :
     
     https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/

     Par exemple :
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     >Assurez-vous d’inclure le caractère "**/**" à la fin de l’URL pour éviter de recevoir une erreur.

   - **ID du locataire** : ID du locataire Azure Active Directory (Azure AD).

   - **ID d’application AAD** : ID d’application (client) créé pour l’application enregistrée dans le portail Microsoft Azure. Vous avez reçu ces informations plus tôt au cours de l’étape [Enregistrer l’application dans Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).

   - **Secret d’application AAD** : clé secrète client créée pour l’application enregistrée dans le portail Microsoft Azure. Vous avez reçu ces informations plus tôt au cours de l’étape [Enregistrer l’application dans Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).

   ![Source de données Microsoft HR.](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. Sélectionnez **Enregistrer et Fermer**.

### <a name="grant-app-permissions-in-human-resources"></a>Accorder des autorisations d’application dans Human Resources

Accordez des autorisations pour les deux applications Azure AD dans Human Resources :

- L’application créée pour votre locataire dans le portail Microsoft Azure
- L’application Tables virtuelles Dynamics 365 HR installée dans l’environnement Power Apps 

1. Dans Human Resources, ouvrez la page **Azure Active Directory applications**.

2. Sélectionnez **Nouveau** pour créer un nouvel enregistrement d’application :

    - Dans le champ **ID client**, entrez l’ID client de l’application que vous avez enregistrée dans le portail Microsoft Azure.
    - Dans le champ **Nom**, entrez le nom de l’application que vous avez enregistrée dans le portail Microsoft Azure.
    - Dans le champ **ID utilisateur**, sélectionnez l’ID utilisateur d’un utilisateur avec des autorisations d’administrateur dans Human Resources et l’environnement Power Apps.

3. Sélectionnez **Nouveau** pour créer un second enregistrement d’application :

    - **ID client** : f9be0c49-aa22-4ec6-911a-c5da515226ff
    - **Nom** : Tables virtuelles Dynamics 365 HR
    - Dans le champ **ID utilisateur**, sélectionnez l’ID utilisateur d’un utilisateur avec des autorisations d’administrateur dans Human Resources et l’environnement Power Apps.

## <a name="generate-virtual-tables"></a>Générer des tables virtuelles

Une fois la configuration terminée, vous pouvez sélectionner les tables virtuelles que vous souhaitez générer et activer dans votre instance Dataverse.

1. Dans Human Resources, ouvrez la page **Intégration Microsoft Dataverse**.

2. Sélectionnez l’onglet **Tables virtuelles**.

> [!NOTE]
> La bascule **Activer les tables virtuelles** sera définie sur **Oui** automatiquement lorsque toute la configuration requise est terminée. Si la bascule est définie sur **Non**, passez en revue les étapes des sections précédentes de ce document pour vous assurer que toutes les configurations préalables sont terminées.

3. Sélectionnez la table ou les tables que vous souhaitez générer dans Dataverse.

4. Sélectionnez **Générer/actualiser**.

![Intégration de Dataverse.](./media/hr-admin-integration-dataverse-integration.png)

## <a name="check-table-generation-status"></a>Vérifier le statut de la génération de la table

Les tables virtuelles sont générées dans Dataverse via un processus d’arrière-plan asynchrone. Les mises à jour sur le processus s’affichent dans le centre d’actions. Les détails du processus, y compris les journaux d’erreurs, apparaissent dans la page **Automatisations de processus**.

1. Dans Human Resources, ouvrez la page de liste **Automatisations de processus**.

2. Sélectionnez l’onglet **Processus en arrière-plan**.

3. Sélectionnez **Processus d’arrière-plan d’opération asynchrone d’interrogation de table virtuelle**.

4. Sélectionnez **Afficher les résultats les plus récents**.

Le volet coulissant affiche les résultats d’exécution les plus récents du processus. Vous pouvez afficher le journal du processus, y compris les erreurs renvoyées par Dataverse.

## <a name="see-also"></a>Voir également :

[Qu’est-ce que Dataverse ?](/powerapps/maker/common-data-service/data-platform-intro)<br>
[Tables dans Dataverse](/powerapps/maker/common-data-service/entity-overview)<br>
[Vue d’ensemble des relations de table](/powerapps/maker/common-data-service/relationships-overview)<br>
[Créer et modifier des tables virtuelles qui contiennent des données provenant d’une source de données externe](/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[Que sont les portails Power Apps ?](/powerapps/maker/portals/overview)<br>
[Présentation de la création d’applications dans Power Apps](/powerapps/maker/)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
