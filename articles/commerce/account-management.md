---
title: Pages et modules de gestion de compte
description: Cette rubrique couvre les pages et les modules de gestion de compte dans Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 12/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: f9fc3731cd9d21294b0161e1d419f255096d7790
ms.sourcegitcommit: 96bfc20eb748f4090a2b5e1ff9f54997d5a5d359
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/04/2019
ms.locfileid: "2885807"
---
# <a name="account-management-pages-and-modules"></a>Pages et modules de gestion de compte

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique couvre les pages et les modules de gestion de compte dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

La gestion de compte fait référence à un groupe de pages qui permet de gérer des informations liées à un compte utilisateur dans Dynamics 365 Commerce. Les pages de gestion de compte incluent la page de destination de la gestion de compte, la page de profil utilisateur, la page d'adresse de l'utilisateur, la page historique de commande, la page des détails de commande, la page de fidélité, et la page de liste de souhaits.

### <a name="account-management-landing-page"></a>Page de destination de gestion de compte

La page de destination de gestion de compte utilise les modules suivants :

- **Emplacement de contenu** – Ce module est un module de conteneur contenant tous les modules sur la page de destination de gestion de compte.
- **Article de bienvenue de compte** – Ce module permet de fournir un message de bienvenue dans la page de gestion de compte. Il inclut des propriétés pour l'en-tête et la taille de vignette. La propriété **Taille de vignette** définit la largeur du module dans le module de placement de contenu. La plage de valeurs de **1** à **12**, où **12** représente la largeur totale du conteneur de placement de contenu.
- **Article de placement de commande de compte** – Ce module permet de fournir une synthèse du nombre de commandes passées par compte d'utilisateur. Il inclut des propriétés pour l'en-tête, la taille de vignette et le lien « détails de la vue ». Le lien « détails de la vue » doit être configuré pour rediriger à la page Historique de l'ordre.
- **Article de placement de profil de compte** – Ce module permet de fournir une synthèse du profil utilisateur. Il inclut des propriétés pour l'en-tête, la taille de vignette et le lien « détails de la vue ». Le lien « détails de la vue » doit être configuré pour rediriger à la page de profil utilisateur.
- **Article de liste de souhaits du compte** – Ce module permet de fournir une synthèse des articles de la liste de souhaits du client. Par exemple, il peut indiquer, « vous avez 10 articles dans votre liste de souhaits ». Il inclut des propriétés pour l'en-tête, la taille de vignette et le lien « détails de la vue ». Le lien « détails de la vue » doit être configuré pour rediriger à la page de liste de souhaits.
- **Article d'adresse du compte** – Ce module permet de fournir une synthèse des adresses de l'utilisateur. Par exemple, il peut indiquer, « vous avez 2 adresses ajoutées à votre compte. » Il inclut des propriétés pour l'en-tête, la taille de vignette et le lien « détails de la vue ». Le lien « détails de la vue » doit être configuré pour rediriger à la page d'adresse.
- **Article de fidélité du compte** – Ce module permet d'afficher et de lier vers les informations du programme de fidélité. Il inclut des propriétés pour l'en-tête, la taille de vignette et le lien « détails de la vue » et le lien « devenir membre ». Le lien « détails de la vue » doit être configuré pour rediriger à la page de fidélité. Le lien « devenir membre » doit être configuré pour redirection vers une page où les utilisateurs peuvent rejoindre le programme de fidélité.

### <a name="order-history-page"></a>Page Historique des commandes

La page Historique des commandes utilise le module Historique des commandes pour afficher toutes les commandes récentes que l'utilisateur a passées.

### <a name="order-details-page"></a>Page de détails de la commande

La page de détails de la commande fournit des informations détaillées pour chaque commande et est accessible depuis de la page Historique des commandes. Elle utilise le module Détails de la commande, qui nécessite l'ID ventes ou de l'ID transaction pour récupérer les détails de la commande.

### <a name="user-profile-page"></a>Page Profil utilisateur

La page Profil utilisateur affiche les détails du profil utilisateur, tels qu'un nom d'utilisateur et l'adresse e-mail. Elle utilise le module de profil utilisateur. Bien que l'adresse e-mail ne puisse pas être supprimée, elle peut être désactivée. La page du profil utilisateur affiche également les préférences de l'utilisateur qui permettent à un utilisateur d'activer ou de désactiver certaines fonctionnalités, telles que la personnalisation des listes de recommandations. 

### <a name="user-address-page"></a>Page Adresse de l'utilisateur

Les page d'adresse de l'utilisateur affiche la liste des adresses associées au compte d'utilisateur. L'utilisateur fournit ces adresses lors du contrôle ou les a ajoutées directement dans cette page. Le module d'adresse de l'utilisateur permet d'ajouter et de modifier des adresses, définir l'adresse principale, et afficher des adresses existantes dans la page.

### <a name="wish-list-page"></a>Page Liste de souhaits

La page de liste de souhaits affichent les articles ajoutés à la liste de souhaits du client. Elle utilise le module de liste de souhaits pour afficher des articles de la liste de souhaits.

### <a name="loyalty-page"></a>Page du programme de fidélité

La page de fidélité permet aux clients de rejoindre un programme de fidélité ou, s'ils sont déjà des membres du programme de fidélité, affiche les détails du programme. Ils peuvent également afficher les points qu'il a acquis ou remboursés dans des transactions récentes.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du kit de démarrage](starter-kit-overview.md)

[Module Container](add-container-module.md)

[Module Zone d'achat](add-buy-box.md)

[Module Panier](add-cart-module.md)

[Module Paiement](add-checkout-module.md)

[Module Confirmation de commande](order-confirmation-module.md)

[Module En-tête](author-header-module.md)

[Module Pied de page](author-footer-module.md)
