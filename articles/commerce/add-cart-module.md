---
title: Module Panier
description: Cette rubrique couvre les modules de panier et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1c910f08e5999ec586b5cb656d5769e9d4abd069
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2696759"
---
# <a name="cart-module"></a>Module Panier

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de panier et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Un module de panier est le conteneur utilisé pour héberger tous les modules nécessaires pour présenter les articles présents dans le panier. Par exemple, il inclut tous les articles ajoutés au panier, à la synthèse de commande, et aux codes promotionnels.

Le module de panier affiche des données sur l'ID panier. L'ID panier est un cookie du navigateur dans le site.

## <a name="cart-module-properties-and-slots"></a>Propriétés et emplacements du module de panier

Comme conteneur, un module de panier contrôle certaines propriétés de bases, telles que l'en-tête et la largeur. L'en-tête est généralement un texte tel que **Panier d'achat**, **Votre panier**, ou **Articles dans votre panier**. Le paramètre de largeur détermine si les modules à l'intérieur de conteneur doivent entrer dans ce conteneur, ou s'ils peuvent remplir l'écran.

La page du panier est divisée en les régions multiples : articles de ligne de panier, synthèse et le paiement de commande, et la fonctionnalité « Rechercher dans le magasin ». Chaque région est mappée à un emplacement dans le module de panier, et chaque emplacement accepte un ensemble prédéfini de modules.

## <a name="modules-that-can-be-used-in-a-cart-module"></a>Modules qui peuvent être utilisés dans un module de panier

- **Articles de lignes de panier** – Ce module affiche une synthèse de chaque article qui a été ajouté au panier. Ces informations incluent le titre de produit, les dimensions sélectionnées, le prix, la quantité, et les remises. Ce module prend également en charge les actions tels que « suppression du panier » et « ajouter à la liste de souhaits ». Pour chaque ligne, il existe une option pour expédier l'article ou le prélever en magasin. Cette option doit être configurée de manière distincte dans le module de prélèvement en magasin.
- **Synthèse de la commande** – Ce module affiche une synthèse de commande. Ces informations incluent le sous-total, l'expédition, les taxes, ainsi que les économies réalisées. Un en-tête peut être configuré pour ce module.
- **Code promo** – Ce module permet au client d'utiliser des codes promotionnels. Un code promotionnel peut être appliqué ou supprimé.
- **Caisse** – Ce module initialise l'action de paiement et redirige l'utilisateur à la page de paiment. Trois liens doivent être configurés pour ce module :

    - **Caisse** – Ce lien force les clients à se connecter s'ils ne le sont pas déjà.
    - **Caisse Invité** – Ce lien permet aux clients anonymes de passer des commandes. Il s'affiche uniquement lorsque des clients ne sont pas connectés.
    - **Revenir aux achats** – Ce lien permet aux clients accéder à la page d'accueil ou à toute autre page, afin de pouvoir continuer à effectuer des achats.

- **Bloc de contenu riche** – Ce module prend en charge la messagerie personnalisée dans le module de panier. Les messages sont pilotés par le système de gestion de contenu (CMS). Tous les messages peuvent être ajoutés, tel que « Pour tout problème avec la commande, contactez le 1-800-Fabrikam ».
- **Prélèvement en magasin** – Ce module affiche une liste des magasins voisins où un article est disponible pour le prélèvement. Par défaut, ce module montre les magasins dans un rayon de 50 km de l'emplacement du client. Toutefois, le rayon de recherche peut être personnalisée dans le module. Pour chaque magasin, un contrôle de stock réalisé, si la fonctionnalité de contrôle de stock est activée, et qu'un message en stock ou épuisé s'affiche.
- **Stocker la recherche dans Bing Maps** – Ce module peut être utilisé à l'intérieur du module Récupérer en magasin. Il permet au clients de rechercher des magasins en entrant un emplacement. L'interface de programmation d'application (API) de géocodage Bing Maps permet de convertir l'emplacement entré par le client en latitude et en longitude. Si ce module n'est pas utilisé, seuls les magasins près de l'emplacement actuel du client sont affichés, et le client ne peut pas rechercher d'autre emplacement.

## <a name="cart-module-settings"></a>Paramètres du module de panier

Les modules de panier ont trois paramètres qui peuvent être configurés :

- **Quantité maximale** – Nombre maximal de chaque article qui peut être ajouté au panier. Par exemple, un détaillant peut décider que seuls 10 % de chaque produit peuvent être vendus en une seule transaction.
- **Contrôle de stock** – Lorsque la valeur est définie sur **Vrai**, un article est ajouté au panier uniquement une fois que le module zone d'achat garantit qu'il est en stock. Ce contrôle de stock est réalisé pour les cas où l'article sera expédié et pour les cas où il sera prélevé en magasin. Si la valeur est définie sur **Faux**, aucun contrôle de stock n'est effectué avant qu'un article soit ajouté au panier et la commande est passée.
- **Marge de stock** – Le stock est tenu à jour en temps réel, et lorsque plusieurs clients passent des commandes, il peut être difficile de tenir à jour un volume de stock exact. Par conséquent, une marge peut être définie pour le stock. Lorsqu'un contrôle de stock est réalisé, si le stock est inférieur au montant de marge, le produit est traité comme épuisé. Par conséquent, lorsque les ventes se produisent rapidement sur plusieurs canaux, de sorte que le volume de stock n'est pas complètement synchronisé, il y a moins de risque qu'un article qui épuisé soit vendu.

## <a name="retail-server-interaction"></a>Interaction du serveur de vente au détail

Le module de panier extrait les informations sur le produit à l'aide des API du serveur de vente au détail. L'ID panier du cookie du navigateur permet de récupérer toutes les informations sur le produit du serveur de vente au détail.

## <a name="add-a-cart-module-to-a-page"></a>Ajouter un module de panier à une page

Pour ajouter un module de panier à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Créez un fragment nommé **fragment de panier**, puis ajoutez un module de panier à celui-ci.
1. À l'emplacement **Articles de lignes de panier** du module de panier, ajoutez un module d'articles de lignes de panier.
1. À l'emplacement **Synthèse de la commande**, ajoutez un module de synthèse de commande.
1. À l'emplacement **Code promo**, ajoutez un module de codes promo.
1. À l'emplacement **Caisse**, ajoutez un module de paiement.
1. À l'emplacement **Rechercher dans le magasin**, ajoutez un module de prélèvement en magasin.
1. Dans le module Récupérer en magasin, sélectionnez l'emplacement **Recherche en magasin**, et ajoutez une recherche de magasin avec le module Bing Maps.
1. Archivez le fragment, et publiez-le.
1. Créez un modèle **modèle de panier**, puis ajoutez le fragment de panier que vous venez de créer à celui-ci.
1. Enregistrez le modèle, archivez-le, et publiez-le.
1. Créez une page qui utilise le nouveau modèle.
1. Enregistrez et affichez un aperçu de la page.
1. Archivez la page, et publiez-la.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du kit de démarrage](starter-kit-overview.md)

[Module Container](add-container-module.md)

[Module Zone d'achat](add-buy-box.md)

[Module Paiement](add-checkout-module.md)

[Module Confirmation de commande](order-confirmation-module.md)

[Module En-tête](author-header-module.md)

[Module Pied de page](author-footer-module.md)
