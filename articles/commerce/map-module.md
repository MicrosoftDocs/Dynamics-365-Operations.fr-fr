---
title: Module Carte
description: Cette rubrique couvre les modules Carte et décrit comment les configurer dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 659211f3a74c38389f991cd2385366d175b0c7c0
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020257"
---
# <a name="map-module"></a>Module Carte

[!include [banner](includes/banner.md)]


Cette rubrique couvre les modules Carte et décrit comment les configurer dans Microsoft Dynamics 365 Commerce.

Un module Carte affiche les emplacements des magasins sur une carte interactive affichée à l’aide du [Contrôle web Bing Maps V8](/bingmaps/v8-web-control/). Une clé API Bing Cartes est requise et doit être ajoutée à la page des paramètres partagés dans les sièges Commerce. Les modules Carte fournissent différentes vues, telles que Route, Aérien et Rue, que les utilisateurs peuvent sélectionner pour afficher des emplacements sur la carte. Ils permettent également des interactions telles que le zoom et l’utilisation de l’emplacement de l’utilisateur.

Un module Carte fonctionne conjointement avec le module Sélection de magasin pour déterminer les emplacements géographiques des magasins qui doivent être affichés sur une carte. Les modules Sélection de magasin et Carte interagissent lorsqu’un utilisateur sélectionne un magasin dans l’un de ces modules sur une page de site. Les modules Carte peuvent être étendus pour d’autres scénarios, au-delà de l’interaction avec les modules Sélection de magasin. Cependant, la personnalisation du module est nécessaire.

> [!NOTE]
> Le module Carte est disponible dans Dynamics 365 Commerce version 10.0.13.

L’image suivante montre un exemple de module Carte utilisé sur une page d’emplacements de magasin.

![Exemple d’un module du sélecteur de magasins](./media/ecommerce-Storelocator.PNG)

## <a name="module-properties"></a>Propriétés du module

| Nom de la propriété             | Valeur                 | Description |
|---------------------------|-----------------------|-------------|
| Titre | Détails | En-tête du module. |
| Options de punaise : icône par défaut | Image | Image du symbole de punaise à utiliser pour les magasins affichés sur une carte. |
| Options de punaise : icône active | Image | Image du symbole de punaise à utiliser pour un magasin sélectionné sur une carte. |
| Options de punaise : couleur de l’icône par défaut | Chaîne de caractères | Valeur texte ou hexadécimale de la couleur des symboles de punaise sur une carte. |
| Options de punaise : couleur de l’icône active | Chaîne de caractères | Valeur texte ou hexadécimale de la couleur des symboles de punaise sélectionnés sur une carte. |
| Afficher l’index | **Vrai** ou **Faux** | Si cette propriété est définie sur **Vrai**, chaque symbole de punaise indiquant un magasin affiche un index. Cet index correspond à l’index dans la vue de liste affichée par le module Sélection de magasin. |

## <a name="add-allowed-mapping-urls-to-a-sites-content-security-policy-directives"></a>Ajouter des URL de mappage autorisées aux instructions de la stratégie de sécurité du contenu d’un site

Pour que le module Carte interagisse avec Bing Cartes, vous devez vous assurer que les URL de mappage suivantes sont autorisées conformément à la stratégie de sécurité du contenu (CSP) de votre site. Ce paramétrage est effectué dans le générateur de site Commerce, en ajoutant des URL autorisées à différentes instructions CSP du site (par exemple, **img-src**). Pour plus d’informations, voir [Stratégie de sécurité du contenu](manage-csp.md). 

- À la directive **connect-src**, ajoutez **&#42;.bing.com**.
- À la directive **img-src**, ajoutez **&#42;.virtualearth.net**.
- Dans l’instruction **script-src**, ajoutez **&#42;.bing.com, &#42;.virtualearth.net**.
- Dans l’instruction **script style-src**, ajoutez **&#42;.bing.com**.

## <a name="add-a-map-module-to-a-page"></a>Ajouter un module Carte à une page

Pour des informations détaillées sur la configuration d’un module Carte sur une page, voir [Module Sélection de magasin](store-selector.md). 
 
## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation de la bibliothèque de modules](starter-kit-overview.md)

[Module Zone d’achat](add-buy-box.md)

[Module Panier](add-cart-module.md)

[Module Sélection de magasin](store-selector.md)

[Gérer Bing Cartes pour votre organisation](./dev-itpro/manage-bing-maps.md)

[Contrôle web Bing Maps V8](/bingmaps/v8-web-control/)


[!INCLUDE[footer-include](../includes/footer-banner.md)]