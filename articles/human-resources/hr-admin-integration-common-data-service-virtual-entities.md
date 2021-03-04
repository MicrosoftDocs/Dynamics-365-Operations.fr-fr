---
title: Configurer les entités virtuelles de Common Data Service
description: Cette rubrique montre comment configurer des entités virtuelles pour Dynamics 365 Human Resources. Générez et mettez à jour des entités virtuelles existantes et analysez les entités générées et disponibles.
author: andreabichsel
manager: tfehr
ms.date: 11/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2b590faeab600d04c9d5303693ec1e9ac682250d
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645599"
---
# <a name="configure-common-data-service-virtual-entities"></a>Configurer les entités virtuelles de Common Data Service

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Dynamics 365 Human Resources est une source de données virtuelle dans Common Data Service. Il fournit des opérations de création, de lecture, de mise à jour et de suppression (CRUD) complètes à partir de Common Data Service et Microsoft Power Platform. Les données des entités virtuelles ne sont pas stockées dans Common Data Service, mais dans la base de données de l'application. 

Pour activer les opérations CRUD sur les entités Ressources humaines à partir de Common Data Service, vous devez rendre les entités disponibles en tant qu'entités virtuelles dans Common Data Service. Cela vous permet d'effectuer des opérations CRUD à partir de Common Data Service et Microsoft Power Platform sur les données contenues dans les ressources humaines. Les opérations prennent également en charge les validations complètes de la logique métier de Human Resources pour garantir l'intégrité des données lors de l'écriture des données dans les entités.

## <a name="available-virtual-entities-for-human-resources"></a>Entités virtuelles disponibles pour Human Resources

Toutes les entités Open Data Protocol (OData) dans Human Resources sont disponibles en tant qu'entités virtuelles dans Common Data Service. Elles sont également disponibles dans Power Platform. Vous pouvez désormais créer des applications et des expériences avec des données directement à partir de Human Resources avec une capacité CRUD complète, sans copier ni synchroniser les données vers Common Data Service. Vous pouvez utiliser des portails Power Apps pour créer des sites Web externes qui permettent des scénarios de collaboration pour les processus métier dans Human Resources.

Vous pouvez afficher la liste des entités virtuelles activées dans l'environnement et commencer à travailler avec les entités dans [Power Apps](https://make.powerapps.com), dans la solution **Entités virtuelles Dynamics 365 HR**.

![Entités virtuelles Dynamics 365 HR dans Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-entities-versus-natural-entities"></a>Entités virtuelles et entités naturelles

Les entités virtuelles pour Human Resources ne sont pas les mêmes que les entités Common Data Service créées pour Human Resources. Les entités naturelles de Human Resources sont générées séparément et gérées dans la solution HCM Common dans Common Data Service. Avec les entités naturelles, les données sont stockées dans Common Data Service et elles nécessitent une synchronisation avec la base de données applicative de Human Resources.

> [!NOTE]
> Pour une liste des entités naturelles Common Data Service pour Human Resources, voir [Entités Common Data Service](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).

## <a name="setup"></a>Paramétrage

Suivez ces étapes de configuration pour activer les entités virtuelles dans votre environnement.

### <a name="enable-virtual-entities-in-human-resources"></a>Activer des entités virtuelles dans Human Resources

Tout d'abord, vous devez activer les entités virtuelles dans l'espace de travail **Gestion des fonctionnalités**.

1. Dans Human Resources, sélectionnez **Administration du système**.

2. Sélectionnez la vignette **Gestion des fonctionnalités**.

3. Sélectionnez **Prise en charge d'entités virtuelles dans HR/CDS**, puis sélectionnez **Activer**.

Pour plus d’informations sur l’activation et la désactivation des fonctionnalités en version préliminaire, consultez [Gérer les fonctionnalités](hr-admin-manage-features.md).

### <a name="register-the-app-in-microsoft-azure"></a>Enregistrez l'application dans Microsoft Azure

Vous devez inscrire votre instance de Human Resources dans le portail Azure afin que la plateforme d'identité Microsoft puisse fournir des services d'authentification et d'autorisation pour l'application et les utilisateurs. Pour plus d'informations sur l'enregistrement des applications dans Azure, voir [Démarrage rapide : enregistrer une application avec la plate-forme d'identité Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

1. Ouvrez le portail [Microsoft Azure](https://portal.azure.com).

2. Dans la liste de services Azure, cliquez sur **Enregistrements d'application**.

3. Sélectionnez **Nouvelle inscription**.

4. Dans le champ **Nom**, entrez un nom descriptif pour l'application. Par exemple, **Entités virtuelles Dynamics 365 Human Resources**.

5. Dans le champ **URI de redirection**, saisissez l'URL de l'espace de noms de votre instance Human Resources.

6. Sélectionnez **Enregistrer**.

7. Une fois l'inscription terminée, le portail Azure affiche le volet **Aperçu** d'inscription de l'application, qui comprend son **ID d'application (client)**. Prenez note de l'**ID d'application (client)** à ce stade. Vous saisirez ces informations lorsque vous [Configurerez la source de données d'entité virtuelle](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).

8. Dans le volet de navigation de gauche, sélectionnez **Certificats et secrets**.

9. Dans la section **Clés secrètes client** de la page, sélectionnez **Nouvelle clé secrète client**.

10. Fournissez une description, sélectionnez une durée et sélectionnez **Ajouter**.

11. Enregistrez la valeur du secret. Vous saisirez ces informations lorsque vous [Configurerez la source de données d'entité virtuelle](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).

    > [!IMPORTANT]
    > Assurez-vous de prendre note de la valeur du secret à ce stade. Le secret n'est plus jamais affiché une fois que vous avez quitté cette page.

### <a name="install-the-dynamics-365-hr-virtual-entity-app"></a>Installez l'application Dynamics 365 HR Virtual Entity

Installez l'application Dynamics 365 HR Virtual Entity dans votre environnement Power Apps pour déployer le package de solution d'entité virtuelle dans Common Data Service.

1. Ouvrez le [Centre d'administration Power Platform](https://admin.powerplatform.microsoft.com).

2. Dans la liste **Environnements**, sélectionnez l'environnement Power Apps associé à votre instance Human Resources.

3. Dans la section **Ressources** de la page, sélectionnez **Applications Dynamics 365**.

4. Sélectionnez l'option **Installer l'application**.

5. Sélectionnez **Dynamics 365 HR Virtual Entity** et sélectionnez **Suivant**.

6. Passez en revue et acceptez les conditions d’utilisation du service.

7. Sélectionnez **Installer**.

L'installation prend quelques minutes. Lorsqu'elle est terminée, passez aux étapes suivantes.

![Installez l'application Dynamics 365 HR Virtual Entity à partir du Centre d'administration Power Platform](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-entity-data-source"></a>Configurer la source de données d'entité virtuelle 

L'étape suivante consiste à configurer la source de données d'entité virtuelle dans l' environnement Power Apps. 

1. Ouvrez le [Centre d'administration Power Platform](https://admin.powerplatform.microsoft.com).

2. Dans la liste **Environnements**, sélectionnez l'environnement Power Apps associé à votre instance Human Resources.

3. Sélectionnez l'**URL d'environnement** dans la section **Détails** de la page.

4. Dans **Hub état solution**, sélectionnez l'icône **Recherche avancée** en haut à droite de la page de l'application.

5. Sur la page **Recherche avancée**, dans la liste déroulante **Rechercher**, sélectionnez Configurations de source de données virtuelle **Finance and Operations**.

6. Sélectionnez **Résultats**.

7. Sélectionnez l'enregistrement **Source de données Microsoft HR**.

8. Entrez les informations requises pour la configuration de la source de données :

   - **URL cible** : URL de votre espace de noms Human Resources. Le format de l'URL cible est :
     
     https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/

     Par exemple :
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     >Assurez-vous d'inclure le caractère "**/**" à la fin de l'URL pour éviter de recevoir une erreur.

   - **ID du locataire** : ID du locataire Azure Active Directory (Azure AD).

   - **ID d'application AAD** : ID d'application (client) créé pour l'application enregistrée dans le portail Microsoft Azure. Vous avez reçu ces informations plus tôt au cours de l'étape [Enregistrer l'application dans Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).

   - **Secret d'application AAD** : clé secrète client créée pour l'application enregistrée dans le portail Microsoft Azure. Vous avez reçu ces informations plus tôt au cours de l'étape [Enregistrer l'application dans Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).

   ![Source de données Microsoft HR](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. Sélectionnez **Enregistrer et Fermer**.

### <a name="grant-app-permissions-in-human-resources"></a>Accorder des autorisations d'application dans Human Resources

Accordez des autorisations pour les deux applications Azure AD dans Human Resources :

- L'application créée pour votre locataire dans le portail Microsoft Azure
- L'application Dynamics 365 HR Virtual Entity installée dans l'environnement Power Apps 

1. Dans Human Resources, ouvrez la page **Azure Active Directory applications**.

2. Sélectionnez **Nouveau** pour créer un nouvel enregistrement d'application :

    - Dans le champ **ID client**, entrez l'ID client de l'application que vous avez enregistrée dans le portail Microsoft Azure.
    - Dans le champ **Nom**, entrez le nom de l'application que vous avez enregistrée dans le portail Microsoft Azure.
    - Dans le champ **ID utilisateur**, sélectionnez l'ID utilisateur d'un utilisateur avec des autorisations d'administrateur dans Human Resources et l'environnement Power Apps.

3. Sélectionnez **Nouveau** pour créer un second enregistrement d'application :

    - **ID client** : f9be0c49-aa22-4ec6-911a-c5da515226ff
    - **Nom** : Dynamics 365 HR Virtual Entity
    - Dans le champ **ID utilisateur**, sélectionnez l'ID utilisateur d'un utilisateur avec des autorisations d'administrateur dans Human Resources et l'environnement Power Apps.

## <a name="generate-virtual-entities"></a>Générer des entités virtuelles

Une fois la configuration terminée, vous pouvez sélectionner les entités virtuelles que vous souhaitez générer et activer dans votre instance Common Data Service.

1. Dans Human Resources, ouvrez la page **Intégration Common Data Service (CDS)**.

2. Sélectionnez l'onglet **Entités virtuelles**.

> [!NOTE]
> La bascule **Activer l'entité virtuelle** sera définie sur **Oui** automatiquement lorsque toute la configuration requise est terminée. Si la bascule est définie sur **Non**, passez en revue les étapes des sections précédentes de ce document pour vous assurer que toutes les configurations préalables sont terminées.

3. Sélectionnez l'entité ou les entités que vous souhaitez générer dans Common Data Service.

4. Sélectionnez **Générer/actualiser**.

![Intégration de Common Data Service](./media/hr-admin-integration-common-data-service-integration.jpg)

## <a name="check-entity-generation-status"></a>Vérifier le statut de la génération d'entité

Les entités virtuelles sont générées dans Common Data Service via un processus d'arrière-plan asynchrone. Les mises à jour sur le processus s'affichent dans le centre d'actions. Les détails du processus, y compris les journaux d'erreurs, apparaissent dans la page **Automatisations de processus**.

1. Dans Human Resources, ouvrez la page de liste **Automatisations de processus**.

2. Sélectionnez l'onglet **Processus en arrière-plan**.

3. Sélectionnez **Processus d'arrière-plan d'opération asynchrone d'interrogation d'entité virtuelle**.

4. Sélectionnez **Afficher les résultats les plus récents**.

Le volet coulissant affiche les résultats d'exécution les plus récents du processus. Vous pouvez afficher le journal du processus, y compris les erreurs renvoyées par Common Data Service.

## <a name="see-also"></a>Voir également :

[Qu'est-ce que Common Data Service ?](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[Vue d'ensemble d'entité](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[Vue d'ensemble des relations d'entité](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[Créer et modifier des entités virtuelles qui contiennent des données provenant d'une source de données externe](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[Que sont les portails Power Apps ?](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[Présentation de la création d'applications dans Power Apps](https://docs.microsoft.com/powerapps/maker/)


[!INCLUDE[footer-include](../includes/footer-banner.md)]