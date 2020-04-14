---
title: Module Panier
description: Cette rubrique couvre les modules de panier et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 03/19/2020
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
ms.openlocfilehash: 598b35b1bd365e761d8d4c5ef214935e60b971f4
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154015"
---
# <a name="cart-module"></a>Module Panier

[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de panier et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Un module de panier affiche les articles qui ont été ajoutés au panier avant que le client ne passe à la caisse. Le module montre également un résumé de la commande et permet au client d'appliquer ou de supprimer des codes promotionnels.

Le module de panier prend en charge la caisse connectée et la caisse d'invité. Il prend également en charge un lien **Revenir aux achats**. Vous pouvez configurer l'itinéraire pour ce lien sous **Paramètres du site \> Extensions \> Itinéraires**.

Le module de panier affiche les données selon l'ID du panier, qui est un cookie de navigateur disponible sur tout le site.

## <a name="cart-module-properties-and-slots"></a>Propriétés et emplacements du module de panier

Le module panier a une propriété **En-tête** qui peut être définie sur des valeurs telles que **Panier d'achat** et **Articles dans votre panier**. 

## <a name="modules-that-can-be-used-in-a-cart-module"></a>Modules qui peuvent être utilisés dans un module de panier

- **Bloc de texte** – Ce module prend en charge la messagerie personnalisée dans le module de panier. Les messages sont pilotés par le système de gestion de contenu (CMS). Tous les messages peuvent être ajoutés, tels que « Pour tout problème avec votre commande, contactez le 1-800-Fabrikam ».
- **Sélecteur de magasins** – Ce module affiche une liste de magasins voisins où un article est disponible pour le prélèvement. Il permet aux utilisateurs d'entrer un emplacement pour trouver des magasins à proximité. Pour plus d'informations sur ce module, voir [Module du sélecteur de magasins](store-selector.md).

## <a name="cart-module-settings"></a>Paramètres du module de panier

Les modules de panier ont les paramètres suivants qui peuvent être configurés sur **Paramètres du site \> Extensions** :

- **Quantité maximale** – Cette propriété est utilisé pour spécifier le nombre maximal de chaque article qui peut être ajouté au panier. Par exemple, un détaillant peut décider que seuls 10 % de chaque produit peuvent être vendus en une seule transaction.
- **Contrôle de stock** – Lorsque la valeur est définie sur **Vrai**, un article est ajouté au panier uniquement une fois que le module zone d'achat garantit qu'il est en stock. Ce contrôle de stock est réalisé en cas d'expédition de l'article ou en cas de prélévement de l'article au magasin. Si la valeur est définie sur **Faux**, aucun contrôle de stock n'est effectué avant qu'un article soit ajouté au panier et la commande est passée.
- **Tampon quantité disponible** - Cette propriété est utilisée pour spécifier un numéro de tampon pour le stock. Le stock est tenu à jour en temps réel, et lorsque plusieurs clients passent des commandes, il peut être difficile de tenir à jour un volume de stock exact. Lorsqu'un contrôle de stock est réalisé, si le stock est inférieur au montant de marge, le produit est traité comme épuisé. Par conséquent, lorsque des ventes se produisent rapidement sur plusieurs canaux, et que le volume de stock n'est pas complètement synchronisé, il y a moins de risque qu'un article qui épuisé soit vendu.
- **Revenir aux achats** - Cette propriété est utilisée pour spécifier l'itinéraire pour le lien **Revenir aux achats**. L'itinéraire peut être configuré au niveau du site, permettant aux détaillants de ramener le client à la page d'accueil ou vers toute autre page du site.

## <a name="commerce-scale-unit-interaction"></a>Interaction avec l'unité d'échelle commerciale

Le module de panier extrait les informations sur le produit à l'aide des API d'unité d'échelle commerciale. L'ID panier du cookie du navigateur permet de récupérer toutes les informations sur le produit auprès de l'unité d'échelle commerciale.

## <a name="add-a-cart-module-to-a-page"></a>Ajouter un module de panier à une page

Pour ajouter un module de panier à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Créez un fragment nommé **Fragment de panier**, puis ajoutez un module de panier au nouveau fragment.
1. Ajoutez un en-tête au module de panier.
1. Ajoutez un module de sélecteur de magasins au module de panier.
1. Enregistrez le fragment, terminez de le modifier et publiez-le.
1. Créez un modèle **Modèle de panier**, puis ajoutez le fragment de panier que vous venez de créer.
1. Enregistrez le modèle, terminez de le modifier et publiez-le.
1. Créez une page qui utilise le nouveau modèle.
1. Enregistrez et affichez un aperçu de la page.
1. Terminez de modifier la page, puis publiez-la.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du kit de démarrage](starter-kit-overview.md)

[Module Conteneur](add-container-module.md)

[Module du sélecteur de magasins](store-selector.md)

[Module de zone d'achat](add-buy-box.md)

[Module de validation](add-checkout-module.md)

[Module de confirmation de commande](order-confirmation-module.md)

[Module En-tête](author-header-module.md)

[Module Pied de page](author-footer-module.md)
