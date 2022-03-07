---
title: Personnaliser et utiliser le portail client
description: Cette rubrique explique comment personnaliser le portail client une fois qu’il a été ajouté à votre système.
author: Henrikan
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 02ad0470b7886b2e9b259682a7f8c8150d656cfb
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8063491"
---
# <a name="customize-and-use-the-customer-portal"></a>Personnaliser et utiliser le portail client

[!include [banner](../includes/banner.md)]


Cette rubrique décrit les différentes pages disponibles et prêtes à l’emploi dans le portail client. Elle explique ce que font les pages et comment les personnaliser.

Le portail client propose quelques pages web et actions prêtes à l’emploi. Le plan de site suivant donne un aperçu de ces pages web et actions, ainsi que des rôles pouvant effectuer les actions.

![Plan de site du portail client.](media/customer-portal-site-map.png "Plan de site du portail client")

## <a name="typical-customizations"></a>Personnalisations typiques

Les rubriques suivantes vous aideront à apprendre les bases des portails Power Apps et de leur personnalisation :

- [Utiliser des modèles](/powerapps/maker/portals/work-with-templates) – Cette rubrique fournit un aperçu général du fonctionnement des portails Power Apps et de la manière d’y apporter des personnalisations simples.
- [Gérer le contenu du portail](/dynamics365/portals/manage-portal-content) – Cette rubrique explique comment gérer et personnaliser le contenu que vous faites apparaître dans votre portail.
- [Éditer le CSS](/powerapps/maker/portals/edit-css) – Cette rubrique vous aide à effectuer des personnalisations plus complexes de l’interface utilisateur (IU) de votre portail.
- [Créer un thème pour votre portail](/dynamics365/portals/create-theme) – Cette rubrique vous aide à créer un thème d’interface utilisateur pour votre portail.
- [Créer et exposer facilement du contenu dans le portail](/dynamics365/portals/create-expose-portal-content) : cette rubrique vous aide à gérer les données et tables sous-jacentes que vous utilisez pour votre portail.
- [Configurer un contact à utiliser dans un portail](/powerapps/maker/portals/configure/configure-contacts) – Cette rubrique explique comment créer et personnaliser les rôles d’utilisateur et comment fonctionnent la sécurité et l’authentification dans les portails Power Apps.
- [Configurer des notes pour les formulaires de table et les formulaires web dans les portails](/powerapps/maker/portals/configure-notes) : cette rubrique explique comment ajouter des documents et du stockage supplémentaire à votre portail.
- [Gestion des erreurs pour le site web du portail](/powerapps/maker/portals/admin/view-portal-error-log) – Cette rubrique explique comment afficher les journaux d’erreurs du portail et les stocker dans votre compte de stockage d’objets blob Microsoft Azure.

## <a name="customize-the-order-creation-process"></a>Personnaliser le processus de création de commande

Lorsqu’un utilisateur soumet une commande en utilisant le portail client, la commande est automatiquement synchronisée avec l’environnement Dynamics 365 Supply Chain Management correspondant. Étant donné que l’utilisateur est un client externe, certaines informations requises lui sont intentionnellement cachées. Ces informations seront automatiquement renseignées lors de l’envoi du formulaire.

Cette section montre comment configurer les contacts pour éviter les erreurs. Elle explique les champs qui sont définis automatiquement et comment modifier leur valeur si nécessaire.

### <a name="the-out-of-box-order-creation-process"></a>Le processus de création de commande prêt à l’emploi

Voici les étapes standard pour soumettre une commande à partir du portail client.

1. Sur la page d’accueil, sélectionnez la vignette **Créer une commande** pour ouvrir l’assistant **Créer une commande**.
1. Sur la page **Informations de commande**, définissez les champs suivants :

    - **Date de réception demandée** – Précisez la date de livraison.
    - **Adresse de livraison** – Saisissez l’adresse à laquelle la commande doit être livrée.
    - **Société** – Sélectionnez le nom de l’entreprise cliente. Ce champ est automatiquement défini pour les utilisateurs non administrateurs.
    - **Numéro de la demande** – Saisissez le numéro de demande de la commande. Ce champ n’est pas obligatoire.
    - **Expédier vers le pays/ la région** – Entrez le pays ou la région où les articles seront livrés. Ce champ est automatiquement défini pour les utilisateurs non administrateurs.

    ![Page Informations sur la commande.](media/customer-portal-order-information.png "Page Informations sur la commande")

1. Sélectionnez **Suivant**.
1. Sur la page **Articles**, sélectionnez **Ajouter un article**.

    ![Page Articles.](media/customer-portal-items.png "Page Articles")

1. Dans la boîte de dialogue **Informations sur l’article**, définissez les champs suivants :

    - **Nom du produit** – Recherchez et sélectionnez un produit à ajouter à la commande.
    - **Quantité** – Entrez la quantité du produit sélectionné.
    - **Unité** – Spécifiez l’unité de mesure (par exemple, **unité**, **kg**, ou **caisse**).
    - **Montant net estimé** – La valeur est calculée comme le prix estimé de l’article × la quantité pour l’unité sélectionnée.

    ![Boîte de dialogue Informations sur l’article.](media/customer-portal-item-information.png "Boîte de dialogue Informations sur l’article")

1. Sélectionnez **Soumettre** pour ajouter l’article à la commande.
1. Répétez les étapes 4 à 6 jusqu’à ce que vous ayez ajouté tous les articles que vous souhaitez commander.
1. Lorsque vous avez terminé d’ajouter des articles, sélectionnez **Suivant** dans la page **Articles**.
1. La page **Informations sur la commande** fournit un résumé de la commande. Vérifiez le contenu de la commande et les détails de livraison. Si tout semble correct, sélectionnez **Soumettre** pour soumettre la commande.

    ![Page Informations sur la commande terminée.](media/customer-portal-order-submit.png "Page Informations sur la commande terminée")

### <a name="standard-data-setup"></a>Configuration des données standard

Pour garantir une expérience utilisateur fluide, le portail client remplit automatiquement les valeurs de plusieurs champs obligatoires. Ces valeurs sont basées sur les informations contenues dans l’enregistrement de contact du client qui soumet la commande.

Pour chaque [ligne de contact](/powerapps/maker/portals/configure/configure-contacts) appartenant à un client qui utilisera le portail client pour soumettre des commandes, des valeurs doivent être spécifiées pour les champs obligatoires suivants. Sinon, des erreurs se produiront.

- **Société** – L’entité juridique à laquelle appartient la commande
- **Client potentiel** – Le compte client associé à la commande
- **Liste des prix** – La liste de prix personnalisée pour le client
- **Devise** – La devise du prix
- **Expédier vers le pays/ la région** – Le pays ou la région où les articles seront livrés

Les champs suivants sont automatiquement définis pour la table de commande client :

- **Langue** – La langue de la commande (Par défaut, la valeur est tirée de l’enregistrement du contact.)
- **Expédier vers le pays/ la région** – Le pays ou la région où les articles seront livrés (par défaut, la valeur est tirée de l’enregistrement du contact.)
- **Personne à contacter** – L’utilisateur qui peut être contacté pour des informations sur la commande (Par défaut, la valeur est tirée de l’enregistrement du contact.)
- **Société** – L’entité juridique à laquelle appartient la commande (Par défaut, la valeur est tirée de l’enregistrement du contact.)
- **Client potentiel** – Le compte client associé à la commande (Par défaut, la valeur est tirée de l’enregistrement du contact.)
- **Facturer le client** – Le compte de facturation de la commande (Par défaut, la valeur est le client potentiel tiré de l’enregistrement du contact.)
- **Nom de la commande client** – Le nom de la commande client (la valeur par défaut est **commande client**.)
- **Devise** – La devise du prix (Par défaut, la valeur est tirée de l’enregistrement du contact.)
- **Liste des prix** – La liste de prix personnalisée pour le client (Par défaut, la valeur est tirée de l’enregistrement de contact.)
- **Description de l’adresse de livraison** – L’adresse de livraison de la commande client (la valeur par défaut est **description de l’adresse de livraison**.)

### <a name="modify-the-order-creation-process"></a>Modifier le processus de création de commande

Vous pouvez modifier librement l’apparence et l’interface utilisateur du portail client si vous ne modifiez pas le processus de création de commande de base. Si vous souhaitez modifier le processus de création de commande, vous devez garder à l’esprit quelques considérations.

Ne supprimez pas les colonnes suivantes de la table de commande client dans Microsoft Dataverse, car ils sont obligatoires pour créer une commande client en double écriture :

- **Société** – L’entité juridique à laquelle appartient la commande
- **Nom** – Le nom de la commande client
- **Devise** – La devise du prix
- **Liste des prix** – La liste de prix personnalisée pour le client
- **Expédier vers le pays/ la région** – Le pays ou la région où les articles seront livrés
- **Client potentiel** – Le compte client associé à la commande
- **Langue** – La langue de la commande (Typiquement, cette langue est la langue du client potentiel.)
- **Description de l’adresse de livraison** – L’adresse de livraison de la commande client

Pour les articles, les colonnes suivantes sont obligatoires :

- **Produit** – Le produit à commander
- **Quantité** – La quantité du produit sélectionné
- **Unité** – L’unité de mesure (par exemple, **unité**, **kg**, ou **caisse**)
- **Expédier vers le pays/ la région** – Le pays ou la région de livraison
- **Description de l’adresse de livraison** – L’adresse de livraison de la commande

Vous devez vous assurer que votre portail client envoie des valeurs pour toutes ces colonnes.

Si vous souhaitez ajouter des colonnes à la page, ou supprimer des colonnes, consultez [Créer ou modifier des formulaires de création rapide pour faciliter la saisie des données](/dynamics365/customerengagement/on-premises/customize/create-edit-quick-create-forms).

Si vous souhaitez modifier la façon dont les colonnes sont prédéfinies et la façon dont les valeurs sont définies lors de l’enregistrement de la page, consultez les informations suivantes dans la documentation des portails Power Apps :

- [Préremplir les champs](/powerapps/maker/portals/configure/configure-web-form-metadata#prepopulate-field)
- [Définir une valeur lors de l’enregistrement](/powerapps/maker/portals/configure/configure-web-form-metadata#set-value-on-save)

## <a name="customize-the-home-page"></a>Personnaliser la page d’accueil

Tous les contrôles du portail client sont intégrés dans les contrôles des portails Power Apps. Vous pouvez les personnaliser en suivant les étapes de [Composer une page](/powerapps/maker/portals/compose-page) dans la documentation des portails Power Apps.

Le seul contrôle personnalisé inclus dans le modèle de portail client est utilisé pour créer les vignettes sur la page d’accueil.

![Vignettes sur la page d’accueil.](media/customer-portal-home-page-tiles.png "Vignettes sur la page d’accueil")

Pour modifier les vignettes, procédez comme suit.

1. Ouvrez l’[Application de gestion de portail](/powerapps/maker/portals/configure/configure-portal).
1. Dans le volet de navigation sur la gauche, sélectionnez **Modèles de page**.

    ![Volet de navigation de la gestion du portail.](media/customer-portal-nav.png "Volet de navigation de la gestion du portail")

1. Sélectionnez le modèle de page intitulé **Accueil**.
1. Dans le champ **Modèle web**, sélectionnez le lien **Accueil** pour ouvrir le code source de cette page.

    ![Champ Modèle web.](media/customer-portal-web-template.png "Champ Modèle web")

1. Vous devez maintenant voir tout le code source de la page d’accueil et pouvez le modifier selon vos besoins.

## <a name="resources"></a>Ressources

Pour en savoir plus sur la configuration et la personnalisation du portail client, consultez les ressources suivantes :

- [Documentation des portails Power Apps](/powerapps/maker/portals/overview)
- [Documentation de la double écriture](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)
- [À propos du cycle de vie des portails](/powerapps/maker/portals/admin/portal-lifecycle)
- [Mettre à niveau un portail](/powerapps/maker/portals/admin/upgrade-portal)
- [Migrer la configuration d’un portail](/powerapps/maker/portals/admin/migrate-portal-configuration)
- [Gestion du cycle de vie des solutions : applications Dynamics 365 for Customer Engagement](https://www.microsoft.com/download/details.aspx?id=57777)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]