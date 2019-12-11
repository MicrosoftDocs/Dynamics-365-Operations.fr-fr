---
title: Module Carrousel
description: Cette rubrique couvre les modules Carrousel et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: c2c5adc8ab2e0330f7b07e5153fd8332ab0203e5
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785235"
---
# <a name="carousel-module"></a>Module Carrousel

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules Carrousel et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Un module Carrousel sert à mettre des plusieurs articles publicitaires dans un carrousel auquel les clients peuvent accéder. Il s'agit d'un module spécial de conteneur qui héberge d'autres modules. Par exemple, un détaillant peut utiliser un module Carrousel sur une page d'accueil pour présenter plusieurs nouveaux produits ou promotions.

Vous pouvez ajouter des modules Bannière et Fonctionnalités dans un module Carrousel. Les propriétés du module Carrousel définissent la manière dont ces modules sont affichés.

## <a name="examples-of-carousel-modules-in-e-commerce"></a>Exemples de modules Carrousel dans le commerce électronique

- Carrousel contenant plusieurs modules publicitaires qui peut être utilisé sur une page d'accueil.
- Carrousel contenant plusieurs modules publicitaires qui peut être utilisé sur une page de détails du produit.
- Un carrousel peut être utilisé sur n'importe quelle page marketing qui permet de mettre en valeur plusieurs promotions ou produits.

## <a name="carousel-module-properties"></a>Propriétés du module Carrousel

| Nom de la propriété             | Valeur                                | Description |
|---------------------------|--------------------------------------|-------------|
| Lire automatiquement                  | **Vrai** ou **Faux**                | Si la valeur est définie sur **Vrai**, la transition entre les articles à l'intérieur du carrousel survient automatiquement. Si la valeur est définie **Faux**, aucune transition ne se produit si le client utilise le clavier ou une souris pour passer d'un article à l'autre. |
| Intervalle de transition entre les diapositives | Valeur en secondes                   | Intervalle des transitions entre les articles. |
| Animation de la transition      | **Diapositive** ou **Fondu**                | Effet de transition. |
| Largeur                     | **Adapter le conteneur** ou **Remplir l'écran** | Si la valeur est définie sur **Adapter le conteneur**, les articles à l'intérieur du carrousel sont limités à la largeur du carrousel. Si la valeur est définie **Plein écran**, les articles ne sont pas soumis à la largeur du carrousel mais peuvent entrer dans le mode pleine page. Vous pouvez modifier la valeur pour obtenir la disposition appropriée. |

## <a name="add-a-carousel-module-to-a-page"></a>Ajouter un module de carrousel à une page

Pour ajouter un module de carrousel à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Créez un modèle de page nommé **modèle de carrousel**.
1. À l'emplacement **Principal** de la page par défaut, ajoutez un module de carrousel.
1. Ajoutez un module de bannière au module de carrousel.
1. Ajoutez un module de fonctionnalité au module de carrousel.
1. Archivez le modèle, et publiez-le. 
1. Utilisez le modèle de carrousel que vous venez de créer pour créer une page qui s'appelle **page de carrousel**.
1. À l'emplacement **Principal** de la nouvelle page, ajoutez un module de carrousel.
1. Définissez la propriété **Largeur** du module de carrousel sur **Plein écran**. 
1. Définissez la propriété **Animation de transition** sur **Diapositive**.
1. Ajoutez un module de bannière au module de carrousel.
1. Dans le module de bannière, ajoutez une image et un en-tête, puis sélectionnez **Enregistrer**.
1. Ajoutez un module de fonctionnalité au module de carrousel.
1. Dans le module de fonctionnalité, ajoutez une image, un en-tête, et un paragraphe de texte.
1. Enregistrez et affichez un aperçu de la page. La page doit afficher un carrousel avec deux modules à l'intérieur (un module de bannière et un module de fonctionnalité). Vous pouvez modifier les propriétés supplémentaires pour les modules de carrousel, de bannière, et de fonctionnalités pour obtenir l'effet souhaité.
1. Archivez la page, et publiez-la.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du kit de démarrage](starter-kit-overview.md)

[Module Alerte](add-alert.md)

[Module de bloc de contenu riche](add-content-rich-block.md)

[Module Placement de contenu](add-content-placement-modules.md)

[Module Fonctionnalité](add-feature-module.md)

[Module Bannière](add-hero-module.md)

[Module Lecteur vidéo](add-video-player.md)
