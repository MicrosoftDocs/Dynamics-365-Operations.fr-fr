---
title: Gérer les partenaires commerciaux sur les sites Web de commerce électronique B2B
description: Cette rubrique décrit comment les administrateurs peuvent ajouter, modifier et supprimer des utilisateurs partenaires sur des sites Web de commerce électronique interentreprises (B2B).
author: josaw1
ms.date: 10/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 090dc9af49840e559b4c1ad1500718fde9764aa2
ms.sourcegitcommit: 6bf9e18989e6d77497a9dda1c362f324b3c2fbf2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2021
ms.locfileid: "7713691"
---
# <a name="manage-business-partner-users-on-b2b-e-commerce-websites"></a>Gérer les partenaires commerciaux sur les sites Web de commerce électronique B2B

[!include [banner](../../includes/banner.md)]

Cette rubrique décrit comment les administrateurs peuvent ajouter, modifier et supprimer des utilisateurs partenaires sur des sites Web de commerce électronique interentreprises (B2B).

Les sites Web de commerce électronique B2B exigent que les organisations s’inscrivent pour devenir des partenaires commerciaux. Une fois qu’une organisation a soumis les détails d’inscription à un site Web de commerce électronique B2B, elle passe par un processus de qualification. Si l’organisation est qualifiée avec succès, elle est intégrée en tant que partenaire commercial.

Une fois qu’une organisation est intégrée en tant que partenaire commercial, l’utilisateur qui a initié la demande de partenariat est identifié en tant qu’utilisateur administrateur et se voit accorder des privilèges pour intégrer d’autres utilisateurs autorisés du site Web de commerce électronique B2B. Ces utilisateurs autorisés peuvent ensuite passer des commandes au nom du partenaire commercial.

## <a name="turn-on-the-b2b-e-commerce-capabilities-feature-in-commerce-headquarters"></a>Activer la fonctionnalité de capacités de commerce électronique B2B dans Commerce Headquarters

La fonctionnalité de capacités de commerce électronique B2B dans Commerce Headquarters permet aux organisations d’intégrer des partenaires commerciaux et de définir des utilisateurs administrateurs. Cette fonctionnalité permet également aux administrateurs de créer et de gérer des utilisateurs et des équipes de partenaires commerciaux, et de leur attribuer des rôles spécifiques. Enfin, elle permet aux utilisateurs partenaires commerciaux de créer des modèles de commande et d’utiliser les commandes existantes pour réapprovisionner les produits.

Pour activer la fonctionnalité de capacités de commerce électronique B2B dans Commerce Headquarters, procédez comme suit :

1. Accédez à **Espaces de travail \> Gestion des fonctionnalités**.
1. Sur l’onglet **Tout**, filtrez sur le champ **Module** en utilisant le terme **Commerce et vente au détail**.
1. Recherchez et sélectionnez la fonction nommée **Permettre l’utilisation des fonctionnalités de commerce électronique B2B**, puis sélectionnez **Activer maintenant**.

## <a name="create-a-number-sequence-and-add-it-to-commerce-shared-parameters"></a>Créez une souche de numéros et ajoutez-la aux paramètres partagés de Commerce

Les souches de numéros permettent de générer des identificateurs uniques et consultables pour les enregistrements de données principales et de transactions qui en exigent. Pour plus d’informations sur les souches de numéros, voir [Vue d’ensemble des souches de numéros](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).

Pour créer une souche de numéros et l’ajouter aux paramètres partagés de Commerce Headquarters, procédez comme suit :

1. Allez dans **Retail et Commerce \> Configuration du siège  \> Souches de numéros \> Souches de numéros**, puis créez une souche de numéros.
1. Allez dans **Retail et Commerce \> Configuration du siège \> Paramètres \> Paramètres commerciaux partagés**, et ajoutez la nouvelle souche de numéros à la référence **ID de la hiérarchie client**.

## <a name="set-up-the-administrator-user-for-a-new-business-partner"></a>Configurer l’utilisateur administrateur pour un nouveau partenaire commercial

Les partenaires commerciaux potentiels peuvent lancer le processus d’intégration sur un site Web de commerce électronique B2B en soumettant une demande d’intégration via un lien sur le site. Une fois qu’un utilisateur partenaire potentiel a sélectionné le lien, il peut fournir les détails nécessaires à l’intégration et à l’inscription. Une fois la demande soumise, une page de confirmation de soumission apparaît. Si la soumission est approuvée, le demandeur (c’est-à-dire l’utilisateur qui a lancé la demande d’intégration) devient l’utilisateur administrateur du partenaire.

Pour approuver et configurer un utilisateur administrateur de partenaire dans Commerce Headquarters, procédez comme suit :

1. Accédez à **Retail et Commerce IT \> Programme de distribution**.
1. Exécutez la tâche **P-0001** pour transférer toutes les demandes d’intégration des partenaires commerciaux dans Commerce Headquarters.
1. Une fois que la tâche **P-0001** a été exécutée, accédez à **Retail et Commerce IT \> Client**, et exécutez la tâche **Synchroniser les clients et les partenaires commerciaux à partir du mode asynchrone**. Une fois cette tâche exécutée avec succès, les demandes d’intégration sont créées en tant qu’enregistrements de prospects dans Commerce Headquarters. Le champ **ID de type** de ces enregistrements est défini sur **Prospect B2B**.
1. Allez dans **Clients \> Tous les prospects** et ouvrez la page des prospects.
1. Sélectionnez le dossier de prospect pour le nouveau partenaire commercial pour ouvrir la page des détails du prospect.
1. Sur l’onglet **Général**, sélectionnez **Convertir \> Approuver/Rejeter** pour approuver ou rejeter la demande d’intégration. Lorsqu’un message de confirmation apparaît, confirmez que vous souhaitez poursuivre le processus et approuvez la demande. Un e-mail est ensuite envoyé à l’adresse e-mail du demandeur pour confirmer que son organisation a été approuvée en tant que partenaire commercial.

    Après avoir approuvé la demande, le champ **Statut** de l’enregistrement du prospect est défini sur **Approuvé**. En outre, deux nouveaux dossiers client sont créés dans le système : un dossier client **Type d’organisation** pour l’organisation partenaire et un dossier client **Type de personne** pour le demandeur (c’est-à-dire l’utilisateur partenaire qui a soumis la demande). Un dossier de hiérarchie client pour le partenaire est également créé. <!--(Please refer to the Org modeling of B2B customer section in this document for more information)-->

1. Allez dans **Retail et Commerce IT \> Programme de distribution**, et exécutez la tâche **1010** (**Clients**) pour transférer les dossiers client et les dossiers de la hiérarchie des clients nouvellement créés vers la base de données des canaux.

Une fois la demande approuvée et les enregistrements de la hiérarchie des clients et des clients synchronisés avec la base de données des canaux, le demandeur peut se connecter au site Web de commerce électronique B2B en utilisant l’adresse e-mail qu’il a fournie lors de la soumission de la demande. Les utilisateurs peuvent utiliser le flux d’inscription pour définir le mot de passe de leur compte. Pour permettre que l'enregistrement du fournisseur d'identité (Azure AD B2C) soit lié à l'enregistrement client B2B qui a été créé lors de l'inscription ou de la connexion, suivez les instructions de la rubrique [Activer la liaison automatique des enregistrements d’identité avec les comptes client](../identity-record-linking.md).

## <a name="notify-b2b-prospects-when-they-are-approved-or-rejected"></a>Notifier les prospects B2B lorsqu’ils sont approuvés ou rejetés

Lorsque vous approuvez ou rejetez une demande d’intégration de prospect B2B, vous pouvez automatiquement envoyer une notification par e-mail au prospect. 

Pour configurer des notifications par e-mail dans Commerce Headquarters pour les événements du type de notification Prospect B2B approuvé ou Prospect B2B rejeté, procédez comme suit.

1. Créez des modèles d’e-mails pour les e-mails qui seront envoyés aux prospects lorsque le type de notification Prospect B2B approuvé ou Prospect B2B rejeté est déclenché.

    Pour plus d’informations sur les espaces réservés pris en charge par les types de notification Prospect B2B approuvé et Prospect B2B rejeté, voir [Types de notifications](../email-templates-transactions.md#notification-types). Pour plus d’informations sur la création de modèles d’e-mails, voir [Créer un modèle d’e-mail](../email-templates-transactions.md#create-an-email-template). 

1. Ajoutez les types de notification Prospect B2B approuvé et Prospect B2B rejeté à votre profil de notification par e-mail et mettez-les en correspondance avec les modèles d’e-mail que vous avez créés. Pour plus d’informations sur les profils de notification, voir [Configurer un profil de notification par e-mail](../email-notification-profiles.md). 

## <a name="onboard-additional-business-partner-users"></a>Intégrer des utilisateurs partenaires supplémentaires

L’utilisateur administrateur du partenaire commercial peut intégrer des utilisateurs partenaires supplémentaires au site Web de commerce électronique B2B si nécessaire.

Pour intégrer des utilisateurs partenaires supplémentaires à un site Web de commerce électronique B2B, procédez comme suit :

1. Connectez-vous au site e-commerce B2B en tant qu’administrateur.
1. Allez dans **Mon compte \> Utilisateurs de l’organisation \> Afficher les détails** et sélectionnez **Ajouter un utilisateur**.
1. Entrez les informations demandées, puis cliquez sur **Enregistrer**. Le statut du nouvel utilisateur est défini sur **En attente**.

    Après l’exécution des tâches **P-0001** et **Synchroniser les clients et les partenaires commerciaux à partir du mode asynchrone**, un dossier client **Type de personne** pour le nouvel utilisateur est créé dans Commerce Headquarters. Cet enregistrement client est également associé à l’enregistrement de hiérarchie client du partenaire concerné. En outre, un e-mail est envoyé à l’adresse e-mail du nouvel utilisateur pour l’informer qu’il a été ajouté en tant qu’utilisateur de l’organisation partenaire et peut désormais se connecter au site Web de commerce électronique B2B.

1. Exécutez la tâche **1010** (**Clients**) pour synchroniser le nouvel utilisateur du partenaire commercial avec la base de données des canaux.

Une fois l’enregistrement client synchronisé, le statut de l’utilisateur sur le site Web de commerce électronique B2B est défini sur **Actif** et le nouvel utilisateur peut se connecter au site Web de commerce électronique B2B en utilisant son adresse e-mail. Les utilisateurs peuvent utiliser le flux d’inscription pour définir le mot de passe de leur compte. Pour permettre que l'enregistrement du fournisseur d'identité (Azure AD B2C) soit lié à l'enregistrement client B2B qui a été créé lors de l'inscription ou de la connexion, suivez les instructions de la rubrique [Activer la liaison automatique des enregistrements d’identité avec les comptes client](../identity-record-linking.md).

## <a name="edit-business-partner-user-details"></a>Modifier les détails de l’utilisateur du partenaire commercial

Pour modifier les détails des utilisateurs partenaires, procédez comme suit :

1. Connectez-vous au site e-commerce B2B en tant qu’administrateur.
1. Allez dans **Mon compte \> Utilisateurs de l’organisation \> Afficher les détails**, cliquez sur le bouton **Modifier** (symbole de crayon), effectuez les modifications requises, puis cliquez sur **Enregistrer**. Les modifications ne prennent effet qu’après l’exécution des tâches **P-0001**, **Synchroniser les clients et les partenaires commerciaux à partir du mode asynchrone**, et **1010** (**Clients**).

## <a name="remove-a-business-partner-user"></a>Supprimer un utilisateur partenaire commercial

Au besoin, un administrateur peut supprimer les utilisateurs existants d’une organisation partenaire commerciale de la liste des utilisateurs qui peuvent accéder au site Web de commerce électronique B2B.

Pour supprimer un utilisateur partenaire, procédez comme suit :

1. Connectez-vous au site e-commerce B2B en tant qu’administrateur.
1. Allez dans **Mon compte \> Utilisateurs de l’organisation \> Afficher les détails** et cliquez sur le bouton **Supprimer** (symbole X). Lorsqu’un message de confirmation apparaît, confirmez que vous souhaitez supprimer l’utilisateur. Les modifications ne prennent effet qu’après l’exécution des tâches **P-0001**, **Synchroniser les clients et les partenaires commerciaux à partir du mode asynchrone**, et **1010** (**Clients**).

> [!NOTE]
> Lorsque vous supprimez un utilisateur de la liste des utilisateurs qui peuvent accéder au site Web de commerce électronique B2B, l’enregistrement client correspondant est supprimé de l’enregistrement de hiérarchie client du partenaire. Cependant, l’enregistrement client lui-même n’est pas supprimé de Commerce Headquarters.

## <a name="onboard-business-partner-and-users-in-commerce-headquarters"></a>Intégrer des partenaires commerciaux et des utilisateurs dans Commerce Headquarters

Les administrateurs peuvent intégrer des partenaires commerciaux et des utilisateurs directement dans Commerce Headquarters.

Pour intégrer des partenaires commerciaux et des utilisateurs directement dans Commerce Headquarters, procédez comme suit :

1. Créez un dossier client **Type d’organisation** pour l’organisation partenaire.
1. Créez des dossiers client **Type de personne** pour les utilisateurs partenaires. Assurez-vous qu’une adresse e-mail principale est spécifiée pour chaque client.
1. Pour chaque dossier client **Type de personne** qui doit être désigné comme utilisateur administrateur de l’organisation partenaire, sur l'organisateur **Retail**, définissez l’option **Administrateur B2B** sur **Oui**.
1. Créez un ID de hiérarchie client. Dans le champ **Nom**, entrez un nom.
1. Dans le champ **Organisation**, entrez le client pour l’organisation partenaire.
1. Sélectionnez **Ajouter**, puis sélectionnez un client dans le champ **Nom**.
1. Répétez ce processus pour ajouter des clients supplémentaires à la hiérarchie.

## <a name="additional-information"></a>Informations supplémentaires

- Toutes les tâches mentionnées dans cette rubrique peuvent être configurées pour s’exécuter selon une planification dans un format de lot. On s’attend à ce que les partenaires commerciaux configurent les travaux par lots selon les besoins.
- Actuellement, un seul enregistrement utilisateur/client peut être désigné en tant qu’utilisateur administrateur, et ce rôle ne peut être modifié que dans Commerce Headquarters. Il n’y a pas de prise en charge des fonctionnalités en libre service qui permettent aux partenaires commerciaux de désigner plusieurs administrateurs ou de changer d’administrateur à partir de sites Web de commerce électronique B2B.
<!--- The modules and labels of the different fields referenced in the screenshots for e-commerce are only for illustration purposes. Customers have complete control on the placement of the B2B related modules and the labels.-->
- Bien que des limites de dépenses puissent être définies pour les utilisateurs, l’application des limites de dépenses pendant le processus de saisie des commandes n’a pas encore été mise en œuvre.
- Toute la logique métier et la validation de l’expérience d’un utilisateur sur un site Web de commerce électronique B2B sont basées sur la configuration de l’enregistrement client qui est mappé à l’utilisateur dans Commerce Headquarters.

## <a name="additional-resources"></a>Ressources supplémentaires

[Configurer un site d’e-commerce B2B](set-up-b2b-site.md)

[Créer des hiérarchies de modélisation organisationnelle pour les organisations B2B](org-model.md)

[Configurer le mode de paiement du compte client pour les sites de commerce électronique B2B](payment-method.md)

[Définir des limites de quantité de produits pour les sites de commerce électronique B2B](quantity-limits.md)

[Vue d’ensemble des souches de numéros](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
