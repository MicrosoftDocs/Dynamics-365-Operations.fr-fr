---
title: Déployer un nouveau client e-commerce
description: Cette rubrique décrit la procédure de déploiement d’un nouveau site d’e-commerce Dynamics 365 Commerce à l’aide de Microsoft Dynamics Lifecycle Services (LCS).
author: psimolin
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6b228babfd32a4191eeed2a6d924a8b99f1a5311
ms.sourcegitcommit: 9eadc7ca08e2db3fd208f5fc835551abe9d06dc8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2021
ms.locfileid: "5936704"
---
# <a name="deploy-a-new-e-commerce-tenant"></a>Déployer un nouveau client e-commerce

[!include [banner](includes/banner.md)]

Cette rubrique décrit la procédure de déploiement d’un nouveau site d’e-commerce Dynamics 365 Commerce à l’aide de Microsoft Dynamics Lifecycle Services (LCS).

Microsoft Dynamics Lifecycle Services (LCS) est un espace de travail de collaboration basé sur le cloud que les partenaires et les clients peuvent utiliser pour gérer leurs projets et environnements, afficher les dernières informations sur les produits et les fonctionnalités Microsoft Dynamics, et créer, effectuer le suivi, et consulter les incidents de support. Les fonctionnalités de gestion d’e-commerce sont intégrées à LCS.

Pour en savoir plus sur LCS, voir [Guide de l’utilisateur de Lifecycle Services](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).
    
## <a name="get-started"></a>Mise en route

Avant d’initialiser l’e-commerce, vous devez initialiser un projet, un environnement, et une Retail Cloud Scale Unit (RCSU). Pour effectuer l’initialisation dans LCS, vous devez disposer des autorisations du rôle de Propriétaire du projet ou de Gestionnaire de l’environnement. Les topologies d’environnement de production et bac à sable sont prises en charge.

Pour plus d’informations sur les environnements, voir [Planification de l’environnement](/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning). Pour plus d’informations sur la conformité RCSU, voir [Initialiser Retail Cloud Scale Unit](/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).

## <a name="initialize-e-commerce"></a>Initialiser l’e-commerce

Cette procédure permet d’initialiser la fonctionnalité d’e-commerce dans un environnement existant.

Avant de commencer, vérifiez que vous avez les informations requises suivantes :

- La RCSU qui sera utilisée.
- Le groupe de sécurité Microsoft Azure Active Directory qui sera utilisé pour les administrateurs système d’e-commerce.
- Le groupe de sécurité Microsoft Azure Active Directory qui sera utilisé pour les modérateurs des classements et évaluations.
- Les domaines qui seront associés à l’environnement.

En outre, vous pouvez collecter les informations facultatives suivantes :

- Informations entreprise-client (B2C) Azure AD :

    - Nom du client.
    - ID client.
    - Domaine personnalisé de connexion.
    - URL de réponse.
    - ID stratégie Inscription Connexion.
    - ID stratégie de réinitialisation du mot de passe.
    - Modifiez l’ID stratégie de profil.

> [!NOTE]
> Ces informations peuvent être ajoutées ultérieurement, via une demande de service.

Après avoir collecté les informations requises, procédez comme suit pour initialiser l’e-commerce.

1. Connectez-vous à [LCS](https://lcs.dynamics.com).
1. Ouvrir le projet contenant l’environnement dans lequel vous souhaitez initialiser l’e-commerce.
1. Dans la section **Environnements**, sélectionnez l’environnement.
1. Sous **Fonctionnalités de l’environnement**, sélectionnez le lien **Gestion de la vente au détail**.
1. Dans l’onglet **commerce électronique**, sélectionnez **Paramétrage**. Une boîte de dialogue s’affiche, dans laquelle vous devez entrer les informations requises pour la mise en service.
1. Entrez les informations requises, puis passez à la page suivante.
1. Sur la page suivante, entrez les informations requises, puis envoyez le formulaire. Vous êtes redirigé vers l’onglet **Commerce électronique**, sous lequel vous devez vérifier que l’initialisation a commencé.
1. Pour afficher le statut de l’initialisation, **Actualisez** ou revenez à l’onglet **commerce électronique** ultérieurement.
    
Lorsque l’e-commerce est initialisé par LCS, le système met en service plusieurs composants requis pour l’e-commerce et les associe à l’environnement. Après la mise en service, l’onglet **Commerce électronique** sur la page **Gestion de la vente au détail** est mis à jour pour refléter la mise en service. La page présente les derniers déploiements de personnalisation et le statut de tout autre déploiements en cours. Elle contient également des liens vers le site d’e-commerce et le générateur de site d’e-commerce où les sites sont créés.

## <a name="access-commerce-site-builder"></a>Accéder au générateur de site Commerce

Pour accéder au générateur de site Commerce, accédez à l’onglet **e-Commerce** dans la page **Gestion de vente au détail** dans LCS et sélectionnez le lien **Outil de gestion de site d’e-commerce**. La page de destination du générateur de site affiche une vue au niveau du client. Depuis cette page, vous pouvez effectuer les actions suivantes :

- Modifier les paramètres au niveau du client.
- Accéder à n’importe quel site que vous avez créé et avoir la permission de l’afficher. 
- Accéder aux fonctionnalités d’évaluation telles que la modération et le compte-rendu.
- Créer un site. Pour plus d’informations sur la création d’un site, voir [Création d’un site d’e-commerce](create-ecommerce-site.md). 

## <a name="additional-resources"></a>Ressources supplémentaires

[Configuration du nom de domaine](configure-your-domain-name.md)

[Créer un site d’e-commerce](create-ecommerce-site.md)

[Associer un site Dynamics 365 Commerce avec un canal en ligne](associate-site-online-store.md)

[Gérer les fichiers robots.txt](manage-robots-txt-files.md)

[Importer des redirections d’URL en bloc](upload-bulk-redirects.md)

[Configurer un client B2C dans Commerce](set-up-B2C-tenant.md)

[Paramétrer des pages personnalisées pour les ouvertures de session utilisateur](custom-pages-user-logins.md)

[Configurer plusieurs locataires B2C dans un environnement Commerce](configure-multi-B2C-tenants.md)

[Ajouter la prise en charge d’un réseau de diffusion de contenu (CDN)](add-cdn-support.md)

[Activation de la détection du magasin selon l’emplacement](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]