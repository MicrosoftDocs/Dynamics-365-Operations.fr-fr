---
title: Module Zone d'achat
description: Cette rubrique couvre les modules de zone d'achat et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/11/2019
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e86b1881e6829ccc33f36ada453af20c1815a2fa
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/18/2019
ms.locfileid: "2811139"
---
# <a name="buy-box-module"></a>Module Zone d'achat

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de zone d'achat et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Le terme *zone d'achat* désigne généralement la zone d'une page de détails de produit « au-dessus du volet », et qui héberge toutes les principales informations requises pour effectuer un achat de produit. (Une zone qui est « au-dessus du volet » n'est visible que si la page est d'abord chargée, afin que les utilisateurs n'aient pas à faire défiler l'écran pour la voir.)

Un module Zone d'achat est un conteneur spécial utilisé pour héberger tous les modules qui sont affichés dans la zone de la zone d'achat d'une page de détails des produits.

L'URL d'une page de détails de produit inclut l'ID produit. Toutes les informations requises pour afficher un module de zone d'achat sont dérivées de cet ID produit. Si aucun ID produit n'est fourni, le module de zone d'achat ne s'affiche pas correctement sur une page. Par conséquent, un module de zone d'achat ne peut pas être utilisé sur une page qui ne présente pas le contexte du produit (par exemple, une page d'accueil ou une page marketing).

## <a name="buy-box-module-properties-and-slots"></a>Propriétés et emplacements des modules de zone d'achat 

Comme conteneur, un module de zone d'achat contrôle certaines propriétés de bases, telles que la largeur. Le paramètre de largeur détermine si les modules à l'intérieur de conteneur doivent entrer dans ce conteneur, ou s'ils peuvent remplir l'écran.

Dans une page de détails des produits, une zone d'achat est divisée en deux espaces : un espace multimédia à gauche et un espace de contenu à droite. Ces deux espaces sont représentés par les emplacements dans le module de zone d'achat. Chaque emplacement est préconfiguré pour accepter uniquement des modules spécifiques pris en charge par l'emplacement. Par exemple, un emplacement **Multimédia** prend uniquement en charge le module de galerie multimédia.

Par défaut, le ratio des largeurs de colonnes pour l'espace multimédia et l'espace de contenu est de 2:1. Toutefois, les largeurs de colonnes peuvent être remplacées par le thème. En outre, sur les appareils mobiles, les deux espaces sont empilés, afin que les espaces apparaissent l'un en dessous de l'autre.

## <a name="modules-that-can-be-used-in-a-buy-box-module"></a>Modules qui peuvent être utilisés dans un module de zone d'achat

- **Galerie multimédia** – Ce module permet de présenter des images d'un produit sur une page de détails des produits. Il peut prendre en charge une à plusieurs d'images. Il prend également en charge des images miniatures. Les images miniatures peuvent être organisées horizontalement (alignées sous l'image) ou verticalement (sous forme de colonne en regard de l'image). Le module de galerie multimédia peut être ajouté à l'emplacement **Multimédia** du module de zone d'achat. Il prend en charge actuellement uniquement les images et les vidéos.
- **Titre du produit** – Ce module affiche le titre du produit sur la page des détails des produits. Par défaut, la balise d'en-tête **H1** est utilisée, mais la balise d'en-tête peut être modifiée au besoin.
- **Classement de produit** – Ce module affiche les classements par étoiles, selon les classements des clients pour un produit. Le module de zone d'achat récupère les classements de produit pour chaque produit auprès du service d'évaluations.
- **Prix du produit** – Ce module affiche le prix du produit. Le prix comprend des prix et des remises barrés.
- **Description du produit** – Ce module affiche la description du produit.
- **Configuration du produit** – Ce module affiche la taille, le style, et les dimensions du produit. Les sélecteurs de dimensions peuvent être empilés verticalement, ou ils peuvent s'afficher côte à côte. Lorsqu'une variante de produit est sélectionnée, d'autres propriétés de la zone d'achat (par exemple, la description du produit et ses images) sont mises à jour pour refléter les informations variables.
- **Quantité de produits** – Ce module permet de configurer la quantité du produit. Un paramètre limite la quantité d'un produit ou d'une variante qui peuvent être ajoutés au chariot.
- **Ajouter au panier** – Ce module permet d'exécuter l'action « Ajouter au panier ». Seul un produit ou une variante peut être ajouté au chariot. Autrement dit, un produit principal ne peut pas être ajouté au chariot. Le module possède une propriété **Accéder au panier** que l'auteur de site peut définir. Lorsque cette propriété est définie **Vrai**, l'utilisateur est dirigé vers la page du panier chaque fois qu'une action « Ajouter au panier » est déclenchée. Lorsqu'elle est définie sur **Faux**, le client peut continuer à accéder à la page de détails du produit après que les articles ont été ajoutés au panier.
- **Ajouter à la liste de souhaits** – Ce module permet d'ajouter un article à la liste de souhaits du client. Seul un produit ou une variante peut être ajouté à une liste de souhaits. En outre, le client doit être inscrit sur le site. Le module inclut la logique de traitement des erreurs pour vous assurer que ces deux conditions sont réunies.
- **Rechercher dans le magasin** – Ce module déclenche un flux « acheter en ligne, récupérer en magasin ».
- **Prélèvement en magasin** – Ce module affiche une liste des magasins voisins où un article est disponible pour le prélèvement. Par défaut, ce module montre les magasins dans un rayon de 50 km de l'emplacement du client. Toutefois, le rayon de recherche peut être personnalisée dans le module. Pour chaque magasin, un contrôle de stock réalisé, si la fonctionnalité de contrôle de stock est activée, et qu'un message en stock ou épuisé s'affiche.
- **Stocker la recherche dans Bing Maps** – Ce module peut être utilisé à l'intérieur du module Récupérer en magasin. Il permet au clients de rechercher des magasins en entrant un emplacement. L'interface de programmation d'application (API) de géocodage Bing Maps permet de convertir l'emplacement spécifié en latitude et en longitude. Si ce module est utilisé, seuls les magasins près de l'emplacement actuel du client sont affichés, et le client ne peut pas rechercher d'autre emplacement.
- **Bloc de contenu riche** – Ce module peut afficher un message que l'auteur du site ou le détaillant souhaite promouvoir dans la zone d'achat « En cas de problème avec la commande, contactez le 1-800-FABRIKAM » ou « Expédition gratuite pour les commandes de plus de 100 $. » Les messages sont pilotés par le système de gestion de contenu (CMS).

## <a name="buy-box-module-settings"></a>Paramètres du module Zone d'achat

Les modules de zone d'achat ont trois paramètres qui peuvent être configurés :

- **Quantité maximale** – Nombre maximal de chaque article qui peut être ajouté au panier. Par exemple, un détaillant peut décider que seuls 10 % de chaque produit peuvent être vendus en une seule transaction.
- **Contrôle de stock** – Lorsque la valeur est définie sur **Vrai**, un article est ajouté au panier uniquement une fois que le module zone d'achat garantit qu'il est en stock. Ce contrôle de stock est réalisé pour les cas où l'article sera expédié et pour les cas où il sera prélevé en magasin. Si la valeur est définie sur **Faux**, aucun contrôle de stock n'est effectué avant qu'un article soit ajouté au panier et la commande est passée.
- **Marge de stock** – Le stock est tenu à jour en temps réel, et lorsque plusieurs clients passent des commandes, il peut être difficile de tenir à jour un volume de stock exact. Par conséquent, une marge peut être définie pour le stock. Lorsqu'un contrôle de stock est réalisé, si le stock est inférieur au montant de marge, le produit est traité comme épuisé. Par conséquent, lorsque les ventes se produisent rapidement sur plusieurs canaux, de sorte que le volume de stock n'est pas complètement synchronisé, il y a moins de risque qu'un article qui épuisé soit vendu.

## <a name="retail-server-interaction"></a>Interaction du serveur de vente au détail

Le module de zone d'achat extrait les informations sur le produit à l'aide des API du serveur de vente au détail. L'ID produit de la page de détails de produit est utilisée pour récupérer toutes les informations.

## <a name="add-a-buy-box-module-to-a-page"></a>Ajouter un module de zone d'achat à une page

Pour ajouter un module de zone d'achat à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Créez un fragment nommé **fragment de zone d'achat**, puis ajoutez un module de zone d'achat à celui-ci.
1. À l'emplacement **Multimédia** du module de zone d'achat, ajoutez un module de galerie multimédia.
1. À l'emplacement **Contenu** du module de zone d'achat, ajoutez les modules suivants : titre de produit, classement de produit, prix du produit, description du produit, configuration du produit, ajouter au panier, ajouter à la liste de souhaits, puis rechercher dans le magasin. Vous pouvez réorganiser les modules dans l'emplacement **Contenu** pour obtenir la disposition appropriée.
1. Sélectionnez le module de recherche en magasin. Dans l'emplacement à l'intérieur de ce module, ajoutez un module Récupérer en magasin.
1. À l'emplacement à l'intérieur du module Récupérer en magasin, ajoutez une recherche de magasin avec le module Bing Maps.
1. Archivez la page, et publiez-la.
1. Créez un modèle pour une page de détails des produits, puis nommez-le **Modèle PDF**.
1. Ajoutez une page par défaut.
1. À l'emplacement **Principal** de la page par défaut, ajoutez un fragment de zone d'achat.
1. Enregistrez le modèle, archivez-le, et publiez-le.
1. Utilisez le modèle que vous venez de créer pour créer une page qui s'appelle **page PDF**.
1. À l'emplacement **Principal** de la nouvelle page, ajoutez un fragment de zone d'achat.
1. Enregistrez et affichez un aperçu de la page. Ajoutez le paramètre de chaîne de requête **?productid=&lt;product id&gt;** à l'URL de la page d'aperçu. Ainsi, le contexte de produit est utilisé pour charger et afficher la page d'aperçu.
1. Archivez la page, et publiez-la. Un zone d'achat doit figurer sur la page de détails des produits.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du kit de démarrage](starter-kit-overview.md)

[Module Container](add-container-module.md)

[Module Panier](add-cart-module.md)

[Module Paiement](add-checkout-module.md)

[Module Confirmation de commande](order-confirmation-module.md)

[Module En-tête](author-header-module.md)

[Module Pied de page](author-footer-module.md)
