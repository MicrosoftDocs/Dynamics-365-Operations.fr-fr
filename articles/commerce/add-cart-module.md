---
title: Module Panier
description: Cette rubrique couvre les modules de panier et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: f6dd8fb56f7342eb9c877eda503a92f4a31e5863
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025434"
---
# <a name="cart-module"></a>Module Panier


[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de panier et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Un module de panier est utilisé pour afficher les articles qui ont été ajoutés au panier avant que le client ne passe à la caisse. Par exemple, il inclut tous les articles qui ont été ajoutés au panier et une synthèse de commande. Il permet également au client d'appliquer ou de supprimer des codes promotionnels.

Le module de panier prend en charge la caisse connectée et la caisse d'invité. Il prend également en charge un lien **Revenir aux achats**. Vous pouvez configurer l'itinéraire pour ce lien sous **Paramètres du site \> Extensions \> Itinéraires**.

Le module de panier affiche des données sur l'ID panier. L'ID panier est un cookie du navigateur dans le site.

## <a name="cart-module-properties-and-slots"></a>Propriétés et emplacements du module de panier

Le module panier a une propriété **En-tête** qui peut être définie sur des valeurs telles que **Panier d'achat** et **Articles dans votre panier**. 

## <a name="modules-that-can-be-used-in-a-cart-module"></a>Modules qui peuvent être utilisés dans un module de panier

- **Bloc de texte** – Ce module prend en charge la messagerie personnalisée dans le module de panier. Les messages sont pilotés par le système de gestion de contenu (CMS). Tous les messages peuvent être ajoutés, tels que « Pour tout problème avec votre commande, contactez le 1-800-Fabrikam ».
- **Sélecteur de magasins** – Ce module affiche une liste de magasins voisins où un article est disponible pour le prélèvement. Il permet aux utilisateurs d'entrer un emplacement pour trouver des magasins à proximité. Le module du sélecteur de magasins est intégré avec l'interface de programmation d'application (API) de géocodage Bing Cartes pour convertir l'emplacement en une latitude et une longitude. Une clé API Bing Cartes est requise et doit être ajoutée à la page des paramètres partagés Vente au détail dans Dynamics 365 Retail. Ce module prend en charge deux propriétés : **Rayon de recherche** et **Lien vers les conditions d'utilisation**. La propriété **Rayon de recherche** définit le rayon de recherche des magasins, en miles. Si aucune valeur n'est spécifiée, le rayon de recherche par défaut, 50 miles, est utilisé. Si Bings Cartes ou tout autre service externe est utilisé, la propriété **Lien vers les conditions d'utilisation** peut être utilisée pour fournir un lien vers les conditions d'utilisation. Un lien vers les conditions d'utilisation est requis pour le service Bing Cartes. 

## <a name="cart-module-settings"></a>Paramètres du module de panier

Les modules de panier ont les paramètres suivants qui peuvent être configurés sur **Paramètres du site \> Extensions** :

- **Quantité maximale** – Cette propriété est utilisé pour spécifier le nombre maximal de chaque article qui peut être ajouté au panier. Par exemple, un détaillant peut décider que seuls 10 % de chaque produit peuvent être vendus en une seule transaction.
- **Contrôle de stock** – Lorsque la valeur est définie sur **Vrai**, un article est ajouté au panier uniquement une fois que le module zone d'achat garantit qu'il est en stock. Ce contrôle de stock est réalisé pour les cas où l'article sera expédié et pour les cas où il sera prélevé en magasin. Si la valeur est définie sur **Faux**, aucun contrôle de stock n'est effectué avant qu'un article soit ajouté au panier et la commande est passée.
- **Tampon quantité disponible** - Cette propriété est utilisée pour spécifier un numéro de tampon pour le stock. Le stock est tenu à jour en temps réel, et lorsque plusieurs clients passent des commandes, il peut être difficile de tenir à jour un volume de stock exact. Lorsqu'un contrôle de stock est réalisé, si le stock est inférieur au montant de marge, le produit est traité comme épuisé. Par conséquent, lorsque des ventes se produisent rapidement sur plusieurs canaux, et que le volume de stock n'est pas complètement synchronisé, il y a moins de risque qu'un article qui épuisé soit vendu.
- **Revenir aux achats** - Cette propriété est utilisée pour spécifier l'itinéraire pour le lien **Revenir aux achats**. Cet itinéraire peut être configuré au niveau du site. Cette configuration permet aux détaillants de ramener le client à la page d'accueil ou à toute autre page du site.

## <a name="commerce-scale-unit-interaction"></a>Interaction avec l'unité d'échelle commerciale

Le module de panier extrait les informations sur le produit à l'aide des API d'unité d'échelle commerciale. L'ID panier du cookie du navigateur permet de récupérer toutes les informations sur le produit auprès de l'unité d'échelle commerciale.

## <a name="add-a-cart-module-to-a-page"></a>Ajouter un module de panier à une page

Pour ajouter un module de panier à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Créez un fragment nommé **Fragment de panier**, puis ajoutez un module de panier à celui-ci.
1. Ajoutez un en-tête au module de panier.
1. Ajoutez un module de sélecteur de magasins au module de panier.
1. Enregistrez le fragment, terminez de le modifier et publiez-le.
1. Créez un modèle **Modèle de panier**, puis ajoutez le fragment de panier que vous venez de créer à celui-ci.
1. Enregistrez le modèle, terminez de le modifier et publiez-le.
1. Créez une page qui utilise le nouveau modèle.
1. Enregistrez et affichez un aperçu de la page.
1. Terminez la modification de la page et publiez-la.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du kit de démarrage](starter-kit-overview.md)

[Module Container](add-container-module.md)

[Module Zone d'achat](add-buy-box.md)

[Module Paiement](add-checkout-module.md)

[Module Confirmation de commande](order-confirmation-module.md)

[Module En-tête](author-header-module.md)

[Module Pied de page](author-footer-module.md)
