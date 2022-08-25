---
title: Gérer les utilisateurs de partenaires commerciaux sur les sites e-commerce B2B
description: Cet article décrit comment ajouter, supprimer et modifier des utilisateurs de partenaires commerciaux sur les sites e-commerce interentreprises (B2B) Microsoft Dynamics 365 Commerce et au Commerce Headquarters.
author: josaw1
ms.date: 04/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.search.industry: retail
ms.search.form: ''
ms.openlocfilehash: a59220c16e195ff36980517baec6fb8246a18115
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281170"
---
# <a name="manage-business-partner-users-on-b2b-e-commerce-websites"></a>Gérer les utilisateurs de partenaires commerciaux sur les sites e-commerce B2B

[!include [banner](../../includes/banner.md)]

Cet article décrit comment ajouter, supprimer et modifier des utilisateurs de partenaires commerciaux sur les sites e-commerce interentreprises (B2B) Microsoft Dynamics 365 Commerce et au Commerce Headquarters.

> [!NOTE]
> - L'article [Gérer les partenaires commerciaux B2B à l’aide des hiérarchies de clients](partners-customer-hierarchies.md) est un prérequis pour ce document.
> - Assurez-vous d’avoir initialisé l’entité des types de documents au Commerce headquarters en ouvrant le formulaire **Types de documents** dans **Administration de l’organisation \> Gestion de documents \> Types de documents**.

Les sites e-commerce B2B exigent que les organisations s’inscrivent pour devenir des partenaires commerciaux. Une fois qu’une organisation a soumis les détails d’inscription à un site e-commerce B2B, la requête d’inscription passe par un processus de qualification. Si l’organisation est qualifiée avec succès, elle est intégrée en tant que partenaire commercial.

Une fois qu’une organisation est intégrée comme un partenaire commercial, l’utilisateur de l'organisation qui a initié la requête de devenir un partenaire commercial est identifié comme l'utilisateur administrateur et se voit accorder des privilèges pour intégrer d’autres utilisateurs autorisés du site e-commerce B2B. Ces utilisateurs autorisés peuvent ensuite placer des commandes au nom du partenaire commercial.

## <a name="set-up-the-administrator-user-for-a-new-business-partner"></a>Configurer l’utilisateur administrateur pour un nouveau partenaire commercial

Les partenaires commerciaux potentiels peuvent initier le processus d’intégration à un site e-commerce B2B en soumettant une requête d’intégration via un lien sur le site Web B2B. Ils peuvent ensuite utiliser le formulaire personnalisable pour fournir les détails nécessaires à l’intégration et à l’inscription. Une fois la requête soumise, une page de confirmation de soumission apparaît. Si la soumission est approuvée, la société pour laquelle la requête a été soumise devient un partenaire commercial et le demandeur (l’utilisateur qui a lancé la requête d’intégration) devient l’utilisateur administrateur du partenaire commercial.

Pour approuver une requête de partenaire commercial au Commerce headquarters, suivez ces étapes.

1. Accédez au **Programme de distribution des TI \> de détail et de commerce**.
1. Exécutez la tâche **P-0001** pour transférer toutes les requête d’intégration de partenaire commercial au Commerce Headquarters.
1. Une fois que la tâche **P-0001** a été exécutée avec succès, accédez au **Client des TI de détail \> et de commerce**, et exécutez la tâche **Synchroniser les clients et les requêtes de canal**. Une fois cette tâche exécutée avec succès, les requêtes d’intégration sont créées en tant que prospects de type **Prospect B2B** au Commerce Headquarters. 
1. Accédez à **Tous les prospects \> clients**, et sélectionnez l’enregistrement de prospect du nouveau partenaire commercial pour ouvrir la page des détails du prospect.
1. Sur l’onglet **Général**, sélectionnez **Convertir \> Approuver/Rejeter** pour approuver la requête d’intégration. Quand un message de confirmation apparaît, confirmez que vous souhaitez poursuivre le processus et approuvez la requête. L’approbation change le champ **Statut** de l’enregistrement du prospect à **Approuvé**. Un e-mail est ensuite envoyé à l’adresse e-mail du demandeur pour confirmer que son organisation a été approuvée en tant que partenaire commercial. Une hiérarchie client est également créée, dans laquelle le demandeur est ajouté comme un administrateur pour le partenaire commercial.

    > [!NOTE]
    > Actuellement, l’e-mail de confirmation est envoyé immédiatement après approbation. Cependant, la future fonctionnalité Commerce permettra à l’administrateur de déclencher manuellement les e-mails.

1. Accédez au **Programme de distribution des TI \> de détail et de commerce**, et exécutez la tâche **1010 (Clients)** pour transférer les nouveaux enregistrements de clients et de hiérarchie de clients vers la base de données du canal.

> [!NOTE]
> Pour s’assurer que les nouveaux enregistrements client sont envoyés à la base de données du canal, au moins un des carnets d’adresses associés au client doit être inclus dans le carnet d’adresses client associé au magasin en ligne. Vous pouvez automatiser ce processus en configurant le carnet d’adresses sur le client par défaut du magasin en ligne afin que le système copie la valeur du carnet d’adresses pour chaque nouveau client.

Une fois les enregistrements de la hiérarchie client synchronisés avec la base de données du canal, le demandeur peut se connecter au site e-commerce B2B en utilisant l’adresse e-mail qu’il a fournie au moment de la soumission de la requête d'intégration. Les utilisateurs peuvent utiliser le flux d’inscription pour définir le mot de passe de leur compte. Pour plus d’informations sur la façon d’activer l’enregistrement du fournisseur d’identité B2C Azure Active Directory (Azure AD) à lier à l’enregistrement client B2B qui a été créé au moment de l’approbation du prospect, voir [Activer la liaison automatique](../identity-record-linking.md).

## <a name="notify-b2b-prospects-when-they-are-approved-or-rejected"></a>Notifier les prospects B2B quand ils sont approuvés ou rejetés

Quand vous approuvez ou rejetez une demande d’intégration de prospect B2B, une notification par e-mail peut être envoyée automatiquement au prospect.

Pour configurer des notifications par e-mail dans Commerce Headquarters pour les événements du type de notification **Prospect B2B approuvé** ou **Prospect B2B rejeté**, suivez ces étapes.

1. Créez des modèles d’e-mail pour les e-mails qui seront envoyés aux prospects quand le type de notification **Prospect B2B approuvé** ou **Prospect B2B rejeté** est déclenché. Pour plus d’informations sur les espaces réservés pris en charge par ces types de notification, voir [Types de notifications](../email-templates-transactions.md#notification-types). Pour plus d’informations sur la création de modèles d’e-mail, voir [Créer un modèle d’e-mail](../email-templates-transactions.md#create-an-email-template).
1. Ajoutez les types de notification **Prospect B2B approuvé** et **Prospect B2B rejeté** à votre profil de notification par e-mail et puis mappez-les aux modèles d’e-mail que vous avez créés. Pour plus d’informations sur les profils de notification, voir [Configurer un profil de notification par e-mail](../email-notification-profiles.md).

## <a name="onboard-additional-business-partner-users"></a>Intégrer des utilisateurs partenaires commerciaux supplémentaires

L’utilisateur administrateur du partenaire commercial peut intégrer des utilisateurs partenaires commerciaux supplémentaires au site e-commerce B2B si nécessaire.

Pour intégrer des utilisateurs partenaires commerciaux supplémentaires à un site e-commerce B2B, suivez ces étapes.

1. Connectez-vous au site e-commerce B2B en tant qu’administrateur.
1. Accédez às **Mon compte \> Utilisateurs de l’organisation \> Afficher les détails** et sélectionnez **Ajouter un utilisateur**.
1. Entrez les informations demandées, puis cliquez sur **Enregistrer**. Le statut du nouvel utilisateur est défini sur **En attente**.

Après l’exécution des tâches **P-0001** et **Synchroniser les clients et les requêtes de canal**, un enregistrement client de type **Personne** est créé pour le nouvel utilisateur dans Commerce Headquarters. Cet enregistrement client est également associé à l’enregistrement de hiérarchie client du partenaire commercial concerné. En outre, un e-mail est envoyé à l’adresse e-mail du nouvel utilisateur pour l’informer qu’il a été ajouté en tant qu’utilisateur de l’organisation du partenaire commercial et peut désormais se connecter au site e-commerce B2B.

Ensuite, exécutez la tâche **1010 (Clients)** pour synchroniser le nouvel utilisateur du partenaire commercial avec la base de données du canal.

Une fois l’enregistrement client synchronisé, le statut de l’utilisateur sur le site e-commerce B2B est défini sur **Actif** et le nouvel utilisateur peut se connecter au site e-commerce B2B en utilisant son adresse e-mail. Les utilisateurs peuvent utiliser le flux d’inscription pour définir le mot de passe de leur compte. Pour plus d’informations sur la façon d’activer l’enregistrement du fournisseur d’identité B2C Azure AD à lier à l’enregistrement client B2B qui a été créé dans Commerce Headquarters, voir [Activer la liaison automatique](/dynamics365/commerce/identity-record-linking.md).

## <a name="edit-business-partner-user-details"></a>Modifier les détails de l’utilisateur du partenaire commercial

Pour modifier les détails des utilisateurs partenaires commerciaux, suivez ces étapes.

1. Connectez-vous au site e-commerce B2B en tant qu’administrateur.
1. Accédez à **Mon compte \> Utilisateurs de l’organisation \> Afficher les détails**, sélectionnez le bouton **Modifier** (symbole de crayon), effectuez les modifications requises, puis cliquez sur **Enregistrer**. Les modifications ne prennent effet qu’après l’exécution des tâches **P-0001**, **Synchroniser les clients et les requêtes de canaux**, et **1010 (Clients)**.

## <a name="remove-a-business-partner-user"></a>Supprimer un utilisateur partenaire commercial

Au besoin, un administrateur peut supprimer les utilisateurs existants d’une organisation partenaire commerciale de la liste des utilisateurs qui peuvent accéder au site e-commerce B2B.
Pour supprimer un utilisateur partenaire commercial, suivez ces étapes.
- Connectez-vous au site e-commerce B2B en tant qu’administrateur.
- Accédez à **Mon compte > Utilisateurs de l’organisation \> Afficher les détails** et sélectionnez le bouton **Supprimer** (symbole "X"). Quand un message de confirmation apparaît, confirmez que vous souhaitez supprimer l’utilisateur. Les modifications ne prennent effet qu’après l’exécution des tâches **P-0001**, **Synchroniser les clients et les requêtes de canaux**, et **1010 (Clients)**.

> [!NOTE]
> Quand vous supprimez un utilisateur de la liste des utilisateurs qui peuvent accéder au site e-commerce B2B, l’enregistrement client correspondant est supprimé de l’enregistrement de hiérarchie client du partenaire commercial. Cependant, l’enregistrement client lui-même n’est pas supprimé de Commerce Headquarters.

## <a name="onboard-existing-customers-as-business-partners-on-the-b2b-e-commerce-website"></a>Intégrer des clients existants en tant que partenaires commerciaux sur le site e-commerce B2B

Les administrateurs peuvent intégrer des partenaires commerciaux et des utilisateurs directement dans Commerce Headquarters. Cette fonctionnalité est utile pour intégrer vos partenaires commerciaux existants sur le site e-commerce B2B.

Pour intégrer des partenaires commerciaux et des utilisateurs directement dans Commerce Headquarters, suivez ces étapes.

1. Créez ou sélectionnez un client du type **Organisation** pour l’ajouter en tant que partenaire commercial.
1. Créer ou sélectionner un client du type **Personne** à ajouter en tant qu’administrateur ou utilisateur pour le partenaire commercial. Assurez-vous que les adresses e-mail principales sont associées aux clients. Ces adresses e-mail sont utilisées pour se connecter au site Web. 

    > [!NOTE]
    > Le système doit être en mesure de trouver un enregistrement client unique pour les utilisateurs qui doivent pouvoir se connecter au site Web. Si le système trouve plusieurs clients ayant la même adresse e-mail principale dans l’entité juridique, l’utilisateur ne pourra pas se connecter au site Web.

1. Créez un ID de hiérarchie client.
1. Dans le champ **Nom**, entrez un nom.
1. Dans le champ **Organisation**, entrez le client de l’organisation partenaire commercial.
1. Dans l’organisateur **Hiérarchie**, sélectionnez **Ajouter**.
1. Dans le champ **Nom**, sélectionnez un client du type **Personne**.
1. Sélectionnez le rôle **Administrateur** pour le client qui doit être désigné comme administrateur.
1. Répétez ce processus pour ajouter plus de clients à la hiérarchie.

## <a name="additional-information"></a>Informations supplémentaires

- Toutes les tâches mentionnées dans cet article peuvent être configurées pour s’exécuter selon une planification dans un format de lot. On s’attend à ce que les partenaires commerciaux configurent les travaux par lots selon les besoins.
- Actuellement, un seul enregistrement utilisateur/client peut être désigné en tant qu’utilisateur administrateur, et ce rôle ne peut être modifié que dans Commerce Headquarters. Il n’y a pas de prise en charge des fonctionnalités en libre service qui permettent aux partenaires commerciaux de désigner plusieurs administrateurs ou de changer d’administrateur à partir de sites e-commerce B2B.
- Bien que des limites de dépenses puissent être définies pour les utilisateurs, l’application des limites de dépenses pendant le processus de saisie des commandes n’a pas encore été mise en œuvre.
- Toute la logique métier et la validation de l’expérience d’un utilisateur sur un site e-commerce B2B sont basées sur la configuration de l’enregistrement client qui est mappé à l’utilisateur dans Commerce Headquarters.

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer un site e-commerce B2B](set-up-b2b-site.md)

[Gérer les partenaires commerciaux B2B à l’aide des hiérarchies clients](partners-customer-hierarchies.md)

[Configurer le mode de paiement du compte client pour les sites e-commerce B2B](payment-method.md)

[Définir des limites de quantité de produits pour les sites e-commerce B2B](quantity-limits.md)

[Vue d’ensemble des souches de numéros](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
