---
title: Module Carrousel
description: Cette rubrique couvre les modules Carrousel et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: f279d7db0a92df9e64b1d3f6ca01c65ca1478d79
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025779"
---
# <a name="carousel-module"></a>Module Carrousel


[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules Carrousel et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Un module Carrousel sert à mettre des plusieurs articles publicitaires (dont des images enrichies) dans une bannière de carrousel tournante à laquelle les clients peuvent accéder. Par exemple, un détaillant peut utiliser un module Carrousel sur une page d'accueil pour présenter plusieurs nouveaux produits ou promotions.

Vous pouvez ajouter des modules de bloc de contenu dans un module carrousel. Les propriétés du module Carrousel définissent la manière dont ces modules sont affichés.

## <a name="examples-of-carousel-modules-in-e-commerce"></a>Exemples de modules Carrousel dans le commerce électronique

- Carrousel contenant plusieurs modules publicitaires qui peut être utilisé sur une page d'accueil.
- Carrousel contenant plusieurs modules publicitaires qui peut être utilisé sur une page de détails du produit.
- Un carrousel peut être utilisé sur n'importe quelle page marketing qui permet de mettre en valeur plusieurs promotions ou produits.

## <a name="carousel-module-properties"></a>Propriétés du module Carrousel

| Nom de la propriété             | Valeur                 | Description |
|---------------------------|-----------------------|-------------|
| Lire automatiquement                  | **Vrai** ou **Faux** | Si la valeur est définie sur **Vrai**, la transition entre les articles à l'intérieur du carrousel survient automatiquement. Si la valeur est définie **Faux**, aucune transition ne se produit si le client utilise le clavier ou une souris pour passer d'un article à l'autre. |
| Intervalle de transition entre les diapositives | Valeur en secondes    | Intervalle des transitions entre les articles. |
| Type de transition           | **Diapositive** ou **Fondu** | L'effet de transition entre les articles. |
| Masquer le flipper du carrousel     | **Vrai** ou **Faux** | Si la valeur est définie sur **Vrai**, le flipper du carrousel et l'indicateur de séquence sont masqués. |
| Autoriser le rejet du carrousel    | **Vrai** ou **Faux** | Si la valeur est définie sur **Vrai**, les utilisateurs peuvent ignorer le caroussel. |

## <a name="add-a-carousel-module-to-a-page"></a>Ajouter un module de carrousel à une page

Pour ajouter un module de carrousel à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Créez un modèle de page nommé **modèle de carrousel**.
1. Dans l'emplacement **Corps**, ajoutez un module de **Page par défaut**.
1. Archivez le modèle, et publiez-le. 
1. Utilisez le modèle de carrousel que vous venez de créer pour créer une page qui s'appelle **page de carrousel**.
1. À l'emplacement **Principal** de la nouvelle page, ajoutez un module de conteneur. 
1. Dans le volet de droite, définissez la valeur **Largeur** sur **Remplir l'écran**.
1. Dans **Contour de la page**, ajoutez un module carrousel au module conteneur.
1. Ajouter un module de bloc de contenu au module caroussel. Définissez les propriétés du module de bloc de contenu en fournissant **En-tête**, **Lien**, **Disposition**et d'autres propriétés.
1. Ajoutez et configurez un autre module de bloc de contenu.
1. Définissez des propriétés supplémentaires pour le module carrousel selon vos besoins.
1. Enregistrez et affichez un aperçu de la page. La page doit afficher un carrousel avec deux modules à l'intérieur (un module de bannière et un module de fonctionnalité). Vous pouvez modifier les propriétés supplémentaires pour les modules de carrousel, de bannière, et de fonctionnalités pour obtenir l'effet souhaité.
1. Terminez la modification de la page et publiez-la.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du kit de démarrage](starter-kit-overview.md)

[Module de bannière promotionnelle](add-alert.md)

[Module de bloc de texte](add-content-rich-block.md)

[Module de bloc de contenu](add-hero-module.md)

[Module de lecture vidéo](add-video-player.md)
