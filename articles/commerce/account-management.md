---
title: Pages et modules de gestion de compte
description: Cette rubrique couvre les pages et les modules de gestion de compte dans Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 09/15/2020
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
ms.openlocfilehash: b0f963bcf65ae622522fe52fd59996c6ec0ecf17
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412188"
---
# <a name="account-management-pages-and-modules"></a>Pages et modules de gestion de compte

[!include [banner](includes/banner.md)]

Cette rubrique couvre les pages et les modules de gestion de compte dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

La gestion de compte fait référence à un groupe de pages qui permet de gérer des informations liées à un compte utilisateur dans Dynamics 365 Commerce. Les pages de gestion de compte incluent la page de destination de la gestion de compte, la page de profil utilisateur, la page d'adresse de l'utilisateur, la page historique de commande, la page des détails de commande, la page de fidélité, et la page de liste de souhaits.

### <a name="account-management-landing-page"></a>Page de destination de gestion de compte

La page de destination de gestion de compte utilise les modules suivants :

- **Conteneur** - Tous les modules de page de destination de gestion de compte doivent être placés dans un conteneur. 
- **Vignette de bienvenue de compte** – Ce module permet de fournir un message de bienvenue dans la page de gestion de compte. Il inclut des propriétés pour l'en-tête.
- **Vignette générique de compte** - Ce module peut être utilisé pour fournir des en-têtes et des liens vers des pages de gestion de compte, telles que les pages « Historique des commandes » ou « Mon profil ». Le module de vignette générique peut être utilisé pour configurer une vignette pour n'importe quelle page. Dans Fabrikam, ce module est utilisé pour les liens vers la page « Historique des commandes » et « Mon profil » sur la page de destination de la gestion des comptes.
- **Vignette de liste de souhaits du compte** – Ce module permet de fournir une synthèse des articles de la liste de souhaits du client. Par exemple, il peut indiquer, « vous avez 10 articles dans votre liste de souhaits ». Elle inclut des propriétés pour l'en-tête et le lien « Afficher les détails ». Le lien « Afficher les détails » doit être configuré pour rediriger vers la page de liste de souhaits. 
- **Vignette d'adresse du compte** – Ce module permet de fournir une synthèse des adresses de l'utilisateur. Par exemple, il peut indiquer, « vous avez 2 adresses ajoutées à votre compte. » Elle inclut des propriétés pour l'en-tête et le lien « Afficher les détails ». Le lien « Afficher les détails » doit être configuré pour rediriger à la page d'adresse.
- **Vignette de fidélité du compte** – Ce module permet d'afficher et de lier vers les informations du programme de fidélité. Cette vignette a deux états : un état affiche des liens pour rejoindre un programme de fidélité si l'utilisateur n'est pas déjà membre. L'autre état affiche des liens pour afficher la page des détails de fidélité lorsque l'utilisateur est déjà membre. Les propriétés incluent l'en-tête, le lien « S'inscrire » et le lien « Afficher la fidélité ». Le lien « Afficher la fidélité » doit être configuré pour rediriger vers la page de fidélité. Le lien « S'inscrire » doit être configuré pour rediriger vers une page où les utilisateurs peuvent rejoindre le programme de fidélité. 

### <a name="order-history-page"></a>Page Historique des commandes

La page Historique des commandes utilise le module Historique des commandes pour afficher toutes les commandes récentes que l'utilisateur a passées.

### <a name="order-details-page"></a>Page de détails de la commande

La page de détails de la commande fournit des informations détaillées pour chaque commande et est accessible depuis de la page Historique des commandes. Elle utilise le module Détails de la commande, qui nécessite l'ID ventes ou de l'ID transaction pour récupérer les détails de la commande.

### <a name="user-profile-page"></a>Page Profil utilisateur

La page Profil utilisateur affiche les détails du profil utilisateur, tels qu'un nom d'utilisateur et l'adresse e-mail. Il utilise les détails du profil utilisateur et les modules de modification du profil utilisateur. Bien que l'adresse e-mail ne puisse pas être supprimée, elle peut être désactivée. La page du profil utilisateur affiche également les préférences de l'utilisateur qui permettent à un utilisateur d'activer ou de désactiver certaines fonctionnalités, telles que la personnalisation des listes de recommandations. 

### <a name="user-address-page"></a>Page Adresse de l'utilisateur

Les page d'adresse de l'utilisateur affiche la liste des adresses associées au compte d'utilisateur. L'utilisateur fournit ces adresses lors du contrôle ou les a ajoutées directement dans cette page. Le module d'adresse de l'utilisateur permet d'ajouter et de modifier des adresses, définir l'adresse principale, et afficher des adresses existantes dans la page.

### <a name="wish-list-page"></a>Page Liste de souhaits

La page de liste de souhaits affichent les articles ajoutés à la liste de souhaits du client. Elle utilise le module de liste de souhaits pour afficher des articles de la liste de souhaits.

### <a name="loyalty-page"></a>Page du programme de fidélité

La page de fidélité permet aux clients d'afficher les détails de leur programme s'ils sont déjà des membres du programme de fidélité. Ils peuvent également afficher les points qu'il a acquis ou remboursés dans des transactions récentes. La page utilise le module de détails du programme de fidélité pour présenter les détails de ce dernier. 

Pour rejoindre le programme de fidélité, une page marketing peut être créée avec des modules d'inscription et de conditions de fidélité. Si l'utilisateur n'est pas membre d'un programme de fidélité, ces modules permettront à l'utilisateur de s'inscrire.

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation de la bibliothèque de modules](starter-kit-overview.md)

[Module Conteneur](add-container-module.md)

[Module Zone d’achat](add-buy-box.md)

[Module Panier](add-cart-module.md)

[Module Validation](add-checkout-module.md)

[Module Confirmation de commande](order-confirmation-module.md)

[Module En-tête](author-header-module.md)

[Module Pied de page](author-footer-module.md)
