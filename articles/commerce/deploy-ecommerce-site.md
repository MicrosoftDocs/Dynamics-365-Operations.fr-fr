---
title: Déploiement d'un nouveau client de commerce électronique
description: Cette rubrique décrit la procédure de déploiement d'un client de commerce électronique à l'aide de Microsoft Dynamics Lifecycle Services (LCS).
author: psimolin
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 00f35b516dbf6ab4d4d9171c84a16b89f6afe832
ms.sourcegitcommit: adf196c51e2b6f532d99c177b4c6778cea8a2efc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2020
ms.locfileid: "3533273"
---
# <a name="deploy-a-new-e-commerce-tenant"></a>Déploiement d'un nouveau client de commerce électronique


[!include [banner](includes/banner.md)]

Cette rubrique décrit la procédure de déploiement d'un site de commerce électronique à l'aide de Microsoft Dynamics Lifecycle Services (LCS).

## <a name="overview"></a>Vue d'ensemble

Microsoft Dynamics Lifecycle Services (LCS) est un espace de travail de collaboration basé sur le cloud que les partenaires et les clients peuvent utiliser pour gérer leurs projets et environnements, afficher les dernières informations sur les produits et les fonctionnalités Microsoft Dynamics, et créer, effectuer le suivi, et consulter les incidents de support. Les fonctionnalités de gestion de commerce électronique sont intégrées à LCS.

Pour en savoir plus sur LCS, voir [Guide de l'utilisateur de Lifecycle Services](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).
    
## <a name="get-started"></a>Mise en route

Avant d'initialiser le commerce électronique, vous devez initialiser un projet, un environnement, et une Retail Cloud Scale Unit (RCSU). Pour effectuer l'initialisation dans LCS, vous devez disposer des autorisations du rôle de Propriétaire du projet ou de Gestionnaire de l'environnement. Les topologies d'environnement de production et bac à sable sont prises en charge.

Pour plus d'informations sur les environnements, voir [Planification de l'environnement](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning). Pour plus d'informations sur la conformité RCSU, voir [Initialiser Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).

## <a name="initialize-e-commerce"></a>Initialiser e-Commerce

Cette procédure permet d'initialiser la fonctionnalité de commerce électronique dans un environnement existant.

Avant de commencer, vérifiez que vous avez les informations requises suivantes :

- La RCSU qui sera utilisée.
- Le groupe de sécurité Microsoft Azure Active Directory qui sera utilisé pour les administrateurs système de commerce électronique.
- Le groupe de sécurité Microsoft Azure Active Directory qui sera utilisé pour les modérateurs des classements et évaluations.
- Les domaines qui seront associés à l'environnement.

En outre, vous pouvez collecter les informations facultatives suivantes :

- Informations entreprise-client (B2C) Azure AD :

    - Nom du client.
    - ID client.
    - Domaine personnalisé de connexion.
    - URL de réponse.
    - ID stratégie Inscription Connexion.
    - ID stratégie de réinitialisation du mot de passe.
    - Modifiez l'ID stratégie de profil.

> [!NOTE]
> Ces informations peuvent être ajoutées ultérieurement, via une demande de service.

Après avoir collecté les informations requises, procédez comme suit pour initialiser le commerce électronique.

1. Connectez-vous à [LCS](https://lcs.dynamics.com).
1. Ouvrir le projet contenant l'environnement dans lequel vous souhaitez initialiser le commerce électronique.
1. Dans la section **Environnements**, sélectionnez l'environnement.
1. Sous **Fonctionnalités de l'environnement**, sélectionnez le lien **Gestion de la vente au détail**.
1. Dans l'onglet **commerce électronique**, sélectionnez **Paramétrage**. Une boîte de dialogue s'affiche, dans laquelle vous devez entrer les informations requises pour la mise en service.
1. Entrez les informations requises, puis passez à la page suivante.
1. Sur la page suivante, entrez les informations requises, puis envoyez le formulaire. Vous êtes redirigé vers l'onglet **Commerce électronique**, sous lequel vous devez vérifier que l'initialisation a commencé.
1. Pour afficher le statut de l'initialisation, **Actualisez** ou revenez à l'onglet **commerce électronique** ultérieurement.
    
Lorsque le commerce électronique est initialisé par LCS, le système met en service plusieurs composants requis pour le commerce électronique et les associe à l'environnement. Après la mise en service, l'onglet **Commerce électronique** sur la page **Gestion de la vente au détail** est mis à jour pour refléter la mise en service. La page présente les derniers déploiements de personnalisation et le statut de tout autre déploiements en cours. Elle contient également des liens vers le site de commerce électronique et le générateur de site de commerce électronique où les sites sont créés.

## <a name="access-site-builder"></a>Accéder au générateur de site

Pour accéder au générateur de site, accédez à l'onglet **Commerce électronique** dans la page **Gestion de vente au détail** dans LCS et sélectionnez le lien **Outil de gestion de site de commerce électronique**. La page de destination du générateur de site affiche une vue au niveau du client. Depuis cette page, vous pouvez effectuer les actions suivantes :

- Modifier les paramètres au niveau du client.
- Accéder à n'importe quel site que vous avez créé et avoir la permission de l'afficher. 
- Accéder aux fonctionnalités d'évaluation telles que la modération et le compte-rendu.
- Créer un site. Pour plus d'informations sur la création d'un site, voir [Création d'un site de commerce électronique](create-ecommerce-site.md). 

## <a name="additional-resources"></a>Ressources supplémentaires

[Configuration du nom de domaine](configure-your-domain-name.md)

[Création d'un site de commerce électronique](create-ecommerce-site.md)

[Association d'un site en ligne avec un canal](associate-site-online-store.md)

[Gérer les fichiers robots.txt](manage-robots-txt-files.md)

[Importer des redirections d'URL en bloc](upload-bulk-redirects.md)

[Configurer un client B2C dans Commerce](set-up-B2C-tenant.md)

[Paramétrer des pages personnalisées pour les ouvertures de session utilisateur](custom-pages-user-logins.md)

[Configurer plusieurs locataires B2C dans un environnement Commerce](configure-multi-B2C-tenants.md)

[Ajouter la prise en charge d'un réseau de diffusion de contenu (CDN)](add-cdn-support.md)

[Activation de la détection du magasin selon l’emplacement](enable-store-detection.md)
