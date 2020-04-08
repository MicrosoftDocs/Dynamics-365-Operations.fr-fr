---
title: Module du sélecteur de magasins
description: Cette rubrique couvre le module du sélecteur de magasins et décrit comment l'ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
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
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8efc2345ded52bfaee2d400815795906f326f4fd
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/21/2020
ms.locfileid: "3157338"
---
# <a name="store-selector-module"></a>Module du sélecteur de magasins

[!include [banner](includes/banner.md)]

Cette rubrique couvre le module du sélecteur de magasins et décrit comment l'ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Un module du sélecteur de magasins est utilisé pour le scénario client « Acheter en ligne, retirer en magasin » (BOPIS). Il affiche une liste des magasins où un produit est disponible pour retrait, ainsi que les heures d'ouverture et l'inventaire des produits pour chaque magasin.

Le module du sélecteur de magasins nécessite le contexte d'un produit et un emplacement de recherche pour trouver des magasins. En l'absence d'un emplacement de recherche, il s'agit par défaut de l'emplacement du navigateur du client, à condition que le client donne son consentement. Le module a une boîte de saisie qui permet au client d'entrer un emplacement (code postal, ou ville et état) pour trouver des magasins à proximité.

Le module du sélecteur de magasins est intégré avec l'interface de programmation d'application (API) de géocodage Bing Cartes pour convertir l'emplacement en une latitude et une longitude. Une clé API Bing Cartes est requise et doit être ajoutée à la page des paramètres partagés Commerce dans Dynamics 365 Commerce.

Le module du sélecteur de magasins peut être ajouté à un module de zone d'achat sur la page de détails du produit (PDP) pour afficher les magasins où un produit est disponible pour retrait. Il peut également être ajouté à un module de panier. Lorsqu'il est ajouté à un module de panier, le module du sélecteur de magasins affiche les options de retrait pour chaque élément de ligne de panier. De plus, avec un codage personnalisé, ce module peut être ajouté à d'autres pages ou modules via des extensions et des personnalisations.

Pour que le scénario BOPIS fonctionne, les produits doivent être configurés avec le mode de livraison « retrait client ». Sinon, le module ne sera pas affiché sur les pages respectives. Pour plus d'informations sur la configuration du mode de livraison, consultez [Configurer les modes de livraison](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

L'image suivante montre un exemple de module du sélecteur de magasins utilisé sur un PDP.

![Exemple d'un module du sélecteur de magasins](./media/BOPIS.PNG)

## <a name="store-selector-module-usage-in-e-commerce"></a>Utilisation du module de sélecteur de magasins dans le commerce électronique

- Un module de sélecteur de magasins peut être utilisé sur une page de détails du produit (PDP) pour trouver les magasins à proximité où un produit est disponible pour retrait.
- Un module de sélecteur de magasins peut être utilisé sur une page de panier pour trouver les magasins à proximité où un produit dans le panier est disponible pour retrait.

## <a name="store-selector-module-properties"></a>Propriétés du module de sélecteur de magasins

| Nom de la propriété             | Valeur                  | Description  |
|---------------------------|-----------------------|-------------|
| Rayon de recherche | Nombre | Définit le rayon de recherche des magasins, en kilomètres. Si aucune valeur n'est spécifiée, le rayon de recherche par défaut, 50 kilomètres, est utilisé.|
|Conditions d'utilisation du service | URL    |  L'URL des conditions de service est requis pour le service Bing Cartes. |

## <a name="add-a-store-selector-module-to-a-page"></a>Ajouter un module de sélecteur de magasins à une page

Un module de sélecteur de magasins a besoin du contexte d'un produit, il ne peut donc être utilisé que dans les modules de zone d'achat et de panier. Les modules de sélecteur de magasins ne fonctionnent pas en dehors de ces modules.

- Pour plus d'informations sur l'ajout d'un module de sélecteur de magasins à un module de zone d'achat, consultez [Module de zone d'achat](add-buy-box.md). 
- Pour plus d'informations sur l'ajout d'un module de sélecteur de magasins à un module de panier, consultez [Module de panier](add-cart-module.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du kit de démarrage](starter-kit-overview.md)

[Module de zone d'achat](add-buy-box.md)

[Module de chariot](add-cart-module.md)

[Visite rapide de PDP](quick-tour-pdp.md)

[Visite rapide du panier et du paiement](quick-tour-cart-checkout.md)

[Paramétrer des modes de livraison](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)
