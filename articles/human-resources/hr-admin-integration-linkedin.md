---
title: Intégration avec LinkedIn Talent Hub
description: Cette rubrique explique comment paramétrer l’intégration entre Microsoft Dynamics 365 Human Resources et LinkedIn Talent Hub.
author: jaredha
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 208998b5c09416407612352da7a8ef5dd9491914
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5889978"
---
# <a name="integrate-with-linkedin-talent-hub"></a>Intégration avec LinkedIn Talent Hub

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [banner](includes/preview-feature.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

[LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub) est une plateforme de système de suivi des candidats (ATS). Elle vous permet de trouver, gérer et embaucher des employés en un seul endroit. En intégrant Microsoft Dynamics 365 Human Resources avec LinkedIn Talent Hub, vous pouvez facilement créer des enregistrements d’employés dans Human Resources pour les candidats qui ont été embauchés pour un poste.

## <a name="setup"></a>Paramétrage

Un administrateur système doit effectuer les tâches de configuration pour permettre l’intégration avec LinkedIn Talent Hub. Premièrement, dans l’environnement Power Apps, vous devez configurer un utilisateur et un rôle de sécurité pour accorder à LinkedIn Talent Hub les autorisations appropriées pour écrire des données dans Human Resources.

### <a name="link-your-environment-to-linkedin-talent-hub"></a>Lier votre environnement à LinkedIn Talent Hub

1. Ouvrez [LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub).

2. Dans le menu déroulant de l’utilisateur, sélectionnez **Paramètres du produit**.

3. Dans le volet de navigation de gauche, dans la section **Avancés**, sélectionnez **Intégrations**.

4. Sélectionnez **Autoriser** pour l’intégration de Microsoft Dynamics 365 Human Resources.

5. Sur la page **Dynamics 365 Human Resources**, sélectionnez l’environnement auquel lier LinkedIn Talent Hub, puis sélectionnez **Lien**.

    ![Intégration de LinkedIn Talent Hub](./media/hr-admin-integration-talent-hub-onboarding.jpg)

    > [!NOTE]
    > Vous pouvez créer un lien uniquement vers les environnements dans lesquels votre compte utilisateur dispose d’un accès administrateur à la fois à l’environnement Human Resources et à l’environnement Power Apps associé. Si aucun environnement n’est répertorié sur la page de liens Human Resources, assurez-vous que vous disposez d’environnements Human Resources sous licence sur le client et que l’utilisateur que vous avez connecté à la page de liens dispose des autorisations d’administrateur sur l’environnement Human Resources et sur l’environnement Power Apps.

### <a name="create-a-power-apps-security-role"></a>Création d’un rôle de sécurité Power Apps

1. Ouvrez le [Centre d’administration Power Platform](https://admin.powerplatform.microsoft.com).

2. Dans la liste **Environnements**, sélectionnez l’environnement associé à l’environnement Human Resources auquel vous souhaitez lier votre instance de LinkedIn Talent Hub.

3. Sélectionnez **Paramètres**.

4. Développez le nœud **Utilisateurs + autorisations**, et sélectionnez **Rôles de sécurité**.

5. Sur la page **Rôles de sécurité**, dans la barre d’outils, sélectionnez **Nouveau rôle**.

6. Sur l’onglet **Détails**, entrez un nom pour le rôle, tel que **Intégration SIRH LinkedIn Talent Hub**.

7. Sur l’onglet **Personnalisation**, sélectionnez l’autorisation de **Lecture** au niveau de l’organisation pour les entités suivantes :

    - Entité
    - Champ
    - Relation

8. Enregistrez et fermez le rôle de sécurité.

### <a name="create-a-power-apps-application-user"></a>Créer un utilisateur d’application Power Apps

Un utilisateur d’application doit être créé pour l’adaptateur LinkedIn Talent Hub, pour accorder des autorisations à l’adaptateur pour écrire des enregistrements de candidats dans l’environnement Power Apps.

1. Ouvrez le [Centre d’administration Power Platform](https://admin.powerplatform.microsoft.com).

2. Dans la liste **Environnements**, sélectionnez l’environnement associé à l’environnement Human Resources auquel vous souhaitez lier votre instance de LinkedIn Talent Hub.

3. Sélectionnez **Paramètres**.

4. Développez le nœud **Utilisateurs + autorisations**, et sélectionnez **Utilisateurs**.

5. Sélectionnez **Gérer les utilisateurs dans Dynamics 365**.

6. Utilisez le menu déroulant au-dessus de la liste pour changer la vue de la vue par défaut **Utilisateurs activés** à **Utilisateurs de l’application**.

    ![Vue Utilisateurs de l’application](./media/hr-admin-integration-power-apps-application-users.jpg)

7. Dans la barre d’outils, sélectionnez **Nouveau**.

8. Sur la page **Nouvel utilisateur**, procédez comme suit :

    1. Changer la valeur du champ **Type d’utilisateur** sur **Utilisateur de l’application**.
    2. Définissez le champ **Nom d’utilisateur** sur **Intégration Dynamics365 HR SIRH LinkedIn**.
    3. Définissez le champ **ID application** sur **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.
    4. Entrez une valeur dans les champs **Prénom**, **Nom de famille** et **Adresse e-mail principale**.
    5. Dans la barre d’outils, sélectionnez **Enregistrer \& Fermer**.

### <a name="assign-a-security-role-to-the-new-user"></a>Attribuer un rôle de sécurité à un nouvel utilisateur

Après avoir enregistré et fermé le nouvel utilisateur de l’application dans la section précédente, vous revenez à la page **Liste des utilisateurs**.

1. Sur la page **Liste des utilisateurs**, changez la vue en **Utilisateurs de l’application**.

2. Sélectionnez l’utilisateur de l’application créé dans la section précédente.

3. Dans la barre d’outils, sélectionnez **Gérer les rôles**.

4. Sélectionnez le rôle de sécurité que vous avez créé précédemment pour l’intégration.

5. Cliquez sur **OK**.

### <a name="add-an-azure-active-directory-app-in-human-resources"></a>Ajouter une application Azure Active Directory dans Human Resources

1. Dans Dynamics 365 Human Resources, ouvrez la page **Applications Azure Active Directory**.
2. Ajoutez un nouvel enregistrement à la liste et définissez les champs suivants :

    - **ID client** : Entrez **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.
    - **Nom** : Saisissez le nom du rôle de sécurité Power Apps que vous avez créé précédemment, tel que **Intégration SIRH LinkedIn Talent Hub**.
    - **Identifiant utilisateur** : Sélectionnez un utilisateur autorisé à écrire des données dans Gestion du personnel.

### <a name="create-the-table-in-dataverse"></a>Créer la table dans Dataverse

> [!IMPORTANT]
> L’intégration avec LinkedIn Talent Hub dépend des tables virtuelles dans Dataverse pour Human Resources. Comme condition préalable à cette étape de la configuration, vous devez configurer des tables virtuelles. Pour plus d’informations sur la configuration des tables virtuelles, voir [Configurer des tables virtuelles Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md).

1. Dans Human Resources, ouvrez la page **Intégration Dataverse**.

2. Sélectionnez l’onglet **Tables virtuelles**.

3. Filtrez la liste d’entités par étiquette d’entité pour trouver **Candidat exporté par LinkedIn**.

4. Sélectionnez l’entité, puis sélectionnez **Générer/actualiser**.

## <a name="exporting-candidate-records"></a>Exporter les enregistrements de candidats

Une fois la configuration terminée, les recruteurs et les professionnels des ressources humaines (RH) peuvent utiliser la fonction **Exporter vers SIRH** dans LinkedIn Talent Hub pour exporter les enregistrements des candidats embauchés de LinkedIn Talent Hub vers Human Resources.

### <a name="export-records-from-linkedin-talent-hub"></a>Exporter des enregistrements depuis LinkedIn Talent Hub

Une fois qu’un candidat a franchi le processus de recrutement et a été embauché, vous pouvez exporter l’enregistrement du candidat de LinkedIn Talent Hub vers Human Resources.

1. Dans LinkedIn Talent Hub, ouvrez le projet pour lequel vous avez embauché le nouvel employé.

2. Sélectionnez un enregistrement de candidat.

3. Sélectionnez **Modifier le stade**, puis sélectionnez **Embauché**.

4. Dans le menu de points de suspension (**...**) du candidat, sélectionnez **Exporter vers SIRH**.

5. Dans le volet **Exporter vers SIRH**, saisissez les informations à exporter :

    - Dans le champ **Fournisseur de SIRH**, sélectionnez **Microsoft Dynamics 365 Human Resources**.
    - Dans le champ **Date de début**, sélectionnez une valeur pour le nouvel employé.
    - Dans le champ **Poste**, entrez le titre du poste du nouvel employé.
    - Dans le champ **Emplacement**, entrez le lieu où sera basé l’employé.
    - Saisissez ou vérifiez l’adresse e-mail de l’employé.

![Volet Exporter vers SIRH dans LinkedIn Talent Hub](./media/hr-admin-integration-linkedin-talent-hub-export.jpg)

## <a name="complete-onboarding-in-human-resources"></a>Terminer l’intégration dans Human Resources

Les enregistrements de candidats exportés de LinkedIn Talent Hub vers Human Resources apparaissent dans la section **Candidats à embaucher** de la page **Gestion du personnel**.

1. Dans Human Resources, ouvrez la page **Gestion du personnel**.

2. Dans la section **Candidats à embaucher**, sélectionnez **Embaucher** pour le candidat sélectionné.

3. Dans la boîte de dialogue **Embaucher un nouveau collaborateur**, vérifiez l’enregistrement et ajoutez les informations requises. Vous pouvez également sélectionner le numéro de poste pour lequel le candidat a été embauché.

Une fois les informations requises saisies, vous pouvez poursuivre vos processus standard de création d’enregistrements d’employés et d’intégration des employés.

Les détails suivants sont importés et inclus dans l’enregistrement d’un nouvel employé :

- Prénom
- Nom
- Date de début de l’emploi
- Adresse de messagerie
- Numéro de téléphone

## <a name="see-also"></a>Voir également :

[Configurer des tables virtuelles Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Qu’est-ce que Microsoft Dataverse ?](/powerapps/maker/common-data-service/data-platform-intro)


[!INCLUDE[footer-include](../includes/footer-banner.md)]