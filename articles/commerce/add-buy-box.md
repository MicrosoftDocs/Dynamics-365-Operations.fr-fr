---
title: Module Zone d'achat
description: Cette rubrique couvre les modules de zone d'achat et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 03/19/2020
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
ms.openlocfilehash: 3417156cbf3cb20a5190e5e51b61b3423816895a
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154061"
---
# <a name="buy-box-module"></a>Module Zone d'achat


[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de zone d'achat et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Le terme *zone d'achat* désigne généralement la zone d'une page de détails de produit « au-dessus du volet », et qui héberge toutes les principales informations requises pour effectuer un achat de produit. (Une zone qui est « au-dessus du volet » n'est visible que si la page est d'abord chargée, afin que les utilisateurs n'aient pas à faire défiler l'écran pour la voir.)

Un module Zone d'achat est un conteneur spécial utilisé pour héberger tous les modules qui sont affichés dans la zone de la zone d'achat d'une page de détails des produits.

L'URL d'une page de détails de produit inclut l'ID produit. Toutes les informations requises pour afficher un module de zone d'achat sont dérivées de cet ID produit. Si aucun ID produit n'est fourni, le module de zone d'achat ne s'affiche pas correctement sur une page. Par conséquent, un module de zone d'achat ne peut être utilisé que sur des pages qui ont un contexte de produit. Pour l'utiliser sur une page qui n'a pas de contexte de produit (par exemple, une page d'accueil ou une page marketing), vous devez effectuer des personnalisations supplémentaires.

## <a name="buy-box-module-properties-and-slots"></a>Propriétés et emplacements des modules de zone d'achat 

Dans une page de détails des produits, une zone d'achat est divisée en deux espaces : un espace multimédia à gauche et un espace de contenu à droite. Par défaut, le rapport entre la largeur de la colonne de l'espace multimédia et la largeur de la colonne de l'espace de contenu est de 2:1. Sur les appareils mobiles, les deux espaces sont empilés, afin que les espaces apparaissent l'un en dessous de l'autre. Les thèmes peuvent être utilisés pour personnaliser les largeurs des colonnes et le rang d'empilement.

Un module de zone d'achat affiche le titre, la description, le prix et les notes d'un produit. Il permet également aux clients de sélectionner des variantes de produit ayant des attributs de produit différents, tels que la taille, le style et la couleur. Lorsqu'une variante de produit est sélectionnée, d'autres propriétés de la zone d'achat (par exemple, la description du produit et ses images) sont mises à jour pour refléter les informations variables. 

Un sélecteur de quantité est fourni, afin que les clients puissent spécifier la quantité d'articles à acheter. La quantité maximale pouvant être achetée peut être définie dans les paramètres du site.
 
À partir de la zone d'achat, les clients peuvent également effectuer des actions telles que l'ajout d'un produit au panier, l'ajout d'un produit à leur liste de souhaits et la sélection d'un lieu de prélèvement. Ces actions peuvent être effectuées sur un produit ou une variante de produit. Pour ajouter un produit à une liste de souhaits, le client doit être connecté.

Les thèmes peuvent être utilisés pour supprimer ou modifier l'ordre des commandes d'action et des propriétés produit de zone d'achat. 

## <a name="module-properties"></a>Propriétés du module

- **Balise de titre** - Cette propriété définit la balise d'en-tête du titre du produit. Si la zone d'achat se trouve en haut de la page, cette propriété doit être définie sur **h1** pour répondre aux normes d'accessibilité. 

## <a name="modules-that-can-be-used-in-a-buy-box-module"></a>Modules qui peuvent être utilisés dans un module de zone d'achat

- **Galerie multimédia** – Ce module permet de présenter des images d'un produit sur une page de détails des produits. Il peut prendre en charge une à plusieurs d'images. Il prend également en charge des images miniatures. Les images miniatures peuvent être organisées horizontalement (alignées sous l'image) ou verticalement (sous forme de colonne en regard de l'image). Le module de galerie multimédia peut être ajouté à l'emplacement **Multimédia** du module de zone d'achat. Il prend en charge actuellement uniquement les images. 
- **Sélecteur de magasins** – Ce module affiche une liste de magasins voisins où un article est disponible pour le prélèvement. Il permet aux utilisateurs d'entrer un emplacement pour trouver des magasins à proximité. Pour plus d'informations sur ce module, voir [Module du sélecteur de magasins](store-selector.md).

## <a name="buy-box-module-settings"></a>Paramètres du module Zone d'achat

Les modules de zone d'achat ont trois paramètres qui peuvent être configurés sur **Paramètres du site \> Extensions** :

- **Quantité maximale** – Cette propriété est utilisé pour spécifier le nombre maximal de chaque article qui peut être ajouté au panier. Par exemple, un détaillant peut décider que seuls 10 % de chaque produit peuvent être vendus en une seule transaction.
- **Contrôle de stock** – Lorsque la valeur est définie sur **Vrai**, un article est ajouté au panier uniquement une fois que le module zone d'achat garantit qu'il est en stock. Ce contrôle de stock est réalisé pour les cas où l'article sera expédié et pour les cas où il sera prélevé en magasin. Si la valeur est définie sur **Faux**, aucun contrôle de stock n'est effectué avant qu'un article soit ajouté au panier et la commande est passée.
- **Tampon quantité disponible** - Cette propriété est utilisée pour spécifier un numéro de tampon pour le stock. Le stock est tenu à jour en temps réel, et lorsque plusieurs clients passent des commandes, il peut être difficile de tenir à jour un volume de stock exact. Lorsqu'un contrôle de stock est réalisé, si le stock est inférieur au montant de marge, le produit est traité comme épuisé. Par conséquent, lorsque des ventes se produisent rapidement sur plusieurs canaux, et que le volume de stock n'est pas complètement synchronisé, il y a moins de risque qu'un article qui épuisé soit vendu.

## <a name="commerce-scale-unit-interaction"></a>Interaction avec l'unité d'échelle commerciale

Le module de zone d'achat extrait les informations sur le produit à l'aide des API d'unité d'échelle commerciale. L'ID produit de la page de détails de produit est utilisée pour récupérer toutes les informations.

## <a name="add-a-buy-box-module-to-a-page"></a>Ajouter un module de zone d'achat à une page

Pour ajouter un module de zone d'achat à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Créez un fragment nommé **fragment de zone d'achat**, puis ajoutez un module de zone d'achat à celui-ci.
1. À l'emplacement **Multimédia** du module de zone d'achat, ajoutez un module de galerie multimédia.
1. Dans l'emplacement **Sélecteur de magasins** du module de zone d'achat, ajoutez un module de sélecteur de magasins.
1. Archivez la page, et publiez-la.
1. Créez un modèle pour une page de détails des produits, puis nommez-le **Modèle PDF**.
1. Ajoutez une page par défaut.
1. À l'emplacement **Principal** de la page par défaut, ajoutez un fragment de zone d'achat.
1. Enregistrez le modèle, terminez de le modifier et publiez-le.
1. Utilisez le modèle que vous venez de créer pour créer une page qui s'appelle **page PDF**.
1. À l'emplacement **Principal** de la nouvelle page, ajoutez un fragment de zone d'achat.
1. Enregistrez et affichez un aperçu de la page. Ajoutez le paramètre de chaîne de requête **?productid=&lt;product id&gt;** à l'URL de la page d'aperçu. Ainsi, le contexte de produit est utilisé pour charger et afficher la page d'aperçu.
1. Enregistrez la page, terminez de la modifier et publiez-la. Un zone d'achat doit figurer sur la page de détails des produits.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du kit de démarrage](starter-kit-overview.md)

[Module du sélecteur de magasins](store-selector.md)

[Module Conteneur](add-container-module.md)

[Module de chariot](add-cart-module.md)

[Module de validation](add-checkout-module.md)

[Module de confirmation de commande](order-confirmation-module.md)

[Module En-tête](author-header-module.md)

[Module Pied de page](author-footer-module.md)
