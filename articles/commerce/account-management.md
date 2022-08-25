---
title: Pages et modules Gestion des comptes
description: Cet article couvre les pages et les modules de gestion de compte dans Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 2db9a1218802234297e9d027691e5887d6a5c808
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274453"
---
# <a name="account-management-pages-and-modules"></a>Pages et modules Gestion des comptes

[!include [banner](includes/banner.md)]

Cet article couvre les pages et les modules de gestion de compte dans Microsoft Dynamics 365 Commerce.

La gestion de compte fait référence à un groupe de pages qui permet de gérer des informations liées à un compte utilisateur dans Dynamics 365 Commerce. Les pages de gestion de compte incluent la page de destination de la gestion de compte, la page de profil utilisateur, la page d’adresse de l’utilisateur, la page historique de commande, la page des détails de commande, la page de fidélité, et la page de liste de souhaits.

### <a name="account-management-landing-page"></a>Page de destination de gestion de compte

La page de destination de gestion de compte utilise les modules suivants :

- **Conteneur** - Tous les modules de page de destination de gestion de compte doivent être placés dans un conteneur. 
- **Vignette de bienvenue de compte** – Ce module permet de fournir un message de bienvenue dans la page de gestion de compte. Il inclut des propriétés pour l’en-tête.
- **Vignette générique de compte** - Ce module peut être utilisé pour fournir des en-têtes et des liens vers des pages de gestion de compte, telles que les pages « Historique des commandes » ou « Mon profil ». Le module de vignette générique peut être utilisé pour configurer une vignette pour n’importe quelle page. Dans Fabrikam, ce module est utilisé pour les liens vers la page « Historique des commandes » et « Mon profil » sur la page de destination de la gestion des comptes.
- **Vignette de liste de souhaits du compte** – Ce module permet de fournir une synthèse des articles de la liste de souhaits du client. Par exemple, il peut indiquer, « vous avez 10 articles dans votre liste de souhaits ». Elle inclut des propriétés pour l’en-tête et le lien « Afficher les détails ». Le lien « Afficher les détails » doit être configuré pour rediriger vers la page de liste de souhaits. 
- **Vignette d’adresse du compte** – Ce module permet de fournir une synthèse des adresses de l’utilisateur. Par exemple, il peut indiquer, « vous avez 2 adresses ajoutées à votre compte. » Elle inclut des propriétés pour l’en-tête et le lien « Afficher les détails ». Le lien « Afficher les détails » doit être configuré pour rediriger à la page d’adresse.
- **Vignette de fidélité du compte** – Ce module permet d’afficher et de lier vers les informations du programme de fidélité. Cette vignette a deux états : un état affiche des liens pour rejoindre un programme de fidélité si l’utilisateur n’est pas déjà membre. L’autre état affiche des liens pour afficher la page des détails de fidélité lorsque l’utilisateur est déjà membre. Les propriétés incluent l’en-tête, le lien « S’inscrire » et le lien « Afficher la fidélité ». Le lien « Afficher la fidélité » doit être configuré pour rediriger vers la page de fidélité. Le lien « S’inscrire » doit être configuré pour rediriger vers une page où les utilisateurs peuvent rejoindre le programme de fidélité. 

### <a name="order-history-page"></a>Page Historique des commandes

La page Historique des commandes utilise le module Historique des commandes pour afficher toutes les commandes récentes que l’utilisateur a passées.

### <a name="order-details-page"></a>Page de détails de la commande

La page de détails de la commande fournit des informations détaillées pour chaque commande et est accessible depuis de la page Historique des commandes. Elle utilise le module Détails de la commande, qui nécessite l’ID ventes ou de l’ID transaction pour récupérer les détails de la commande.

### <a name="my-profile-page"></a>Page Mon profil

La page Mon profil affiche les détails du profil de compte de l’utilisateur à l’aide du module de profil de compte. La page affiche l’adresse e-mail associée au compte de l’utilisateur, ainsi que les préférences définies pour le compte. Si vous configurez des attributs client personnalisés, une section « Informations supplémentaires » affichera également ces attributs. Les utilisateurs peuvent modifier leur nom, leurs préférences ou des informations supplémentaires (si disponibles).

### <a name="user-address-page"></a>Page Adresse de l’utilisateur

Les page d’adresse de l’utilisateur affiche la liste des adresses associées au compte d’utilisateur. L’utilisateur fournit ces adresses lors du contrôle ou les a ajoutées directement dans cette page. Le module d’adresse de l’utilisateur permet d’ajouter et de modifier des adresses, définir l’adresse principale, et afficher des adresses existantes dans la page.

### <a name="wish-list-page"></a>Page Liste de souhaits

La page de liste de souhaits affichent les articles ajoutés à la liste de souhaits du client. Elle utilise le module de liste de souhaits pour afficher des articles de la liste de souhaits.

### <a name="loyalty-page"></a>Page du programme de fidélité

La page de fidélité permet aux clients d’afficher les détails de leur programme s’ils sont déjà des membres du programme de fidélité. Ils peuvent également afficher les points qu’il a acquis ou remboursés dans des transactions récentes. La page utilise le module de détails du programme de fidélité pour présenter les détails de ce dernier. 

Pour rejoindre le programme de fidélité, une page marketing peut être créée avec des modules d’inscription et de conditions de fidélité. Si l’utilisateur n’est pas membre d’un programme de fidélité, ces modules permettront à l’utilisateur de s’inscrire.

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation de la bibliothèque de modules](starter-kit-overview.md)

[Module Conteneur](add-container-module.md)

[Module Zone d’achat](add-buy-box.md)

[Module Panier](add-cart-module.md)

[Module Validation](add-checkout-module.md)

[Module Confirmation de commande](order-confirmation-module.md)

[Module En-tête](author-header-module.md)

[Module Pied de page](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
