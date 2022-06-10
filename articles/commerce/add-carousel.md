---
title: Module Carrousel
description: Cette rubrique couvre les modules de carrousel et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 219e497653c6ec5d65cd7c89e2ebb9fc85c2f440
ms.sourcegitcommit: ccb39767bd3430c24f4653c26560bba2cd66553c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/19/2022
ms.locfileid: "8780562"
---
# <a name="carousel-module"></a>Module Carrousel

[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de carrousel et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

Un module Carrousel sert à mettre des plusieurs articles publicitaires (dont des images enrichies) dans une bannière de carrousel tournante à laquelle les clients peuvent accéder. Par exemple, un détaillant peut utiliser un module Carrousel sur une page d’accueil pour présenter plusieurs nouveaux produits ou promotions.

Vous pouvez ajouter des modules de bloc de contenu dans un module carrousel. Les propriétés du module Carrousel définissent la manière dont ces modules sont affichés.

## <a name="examples-of-carousel-modules-in-e-commerce"></a>Exemples de modules Carrousel dans le commerce électronique

- Carrousel contenant plusieurs modules publicitaires qui peut être utilisé sur une page d’accueil.
- Carrousel contenant plusieurs modules publicitaires qui peut être utilisé sur une page de détails du produit.
- Un carrousel peut être utilisé sur n’importe quelle page marketing qui permet de mettre en valeur plusieurs promotions ou produits.

L’image suivante montre un exemple de module de carrousel utilisé sur une page d’accueil. Ce module de carrousel contient plusieurs éléments de bloc de contenu.

![Exemple d’un module de carrousel.](./media/Hero.PNG)

## <a name="carousel-module-properties"></a>Propriétés du module Carrousel

| Nom de la propriété             | Valeur                 | Description |
|---------------------------|-----------------------|-------------|
| Lire automatiquement                  | **Vrai** ou **Faux** | Si la valeur est définie sur **Vrai**, la transition entre les articles à l’intérieur du carrousel survient automatiquement. Si la valeur est définie **Faux**, aucune transition ne se produit si le client utilise le clavier ou une souris pour passer d’un article à l’autre. |
| Intervalle de transition entre les diapositives | Valeur en secondes    | Intervalle des transitions entre les articles. |
| Type de transition           | **Diapositive** ou **Fondu** | L’effet de transition entre les articles. |
| Masquer le flipper du carrousel     | **Vrai** ou **Faux** | Si la valeur est définie sur **Vrai**, le flipper du carrousel et l’indicateur de séquence sont masqués. |
| Autoriser le rejet du carrousel    | **Vrai** ou **Faux** | Si la valeur est définie sur **Vrai**, les utilisateurs peuvent ignorer le caroussel. |

## <a name="add-a-carousel-module-to-a-page"></a>Ajouter un module de carrousel à une page

Pour ajouter un module de carrousel à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un nouveau modèle.
1. Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez **Modèle de carrousel**, puis cliquez sur **OK**.
1. Dans l’emplacement **Corps**, ajoutez un module de **Page par défaut**.
1. Sélectionnez **Terminer la modification** pour archiver le modèle, puis **Publier** pour le publier.  
1. Utilisez le modèle de carrousel que vous venez de créer pour créer une page qui s’appelle **Page de carrousel**.
1. À l’emplacement **Principal** de la nouvelle page, ajoutez un module de conteneur. 
1. Dans le volet de droite, définissez la valeur **Largeur** sur **Remplir l’écran**.
1. Dans **Contour de la page**, ajoutez un module carrousel au module conteneur.
1. Ajouter un module de bloc de contenu au module caroussel. Définissez les propriétés du module de bloc de contenu en fournissant **En-tête**, **Lien**, **Disposition** et d’autres propriétés.
1. Ajoutez et configurez un autre module de bloc de contenu.
1. Définissez des propriétés supplémentaires pour le module carrousel selon vos besoins.
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page. La page doit afficher un carrousel avec deux modules à l’intérieur (un module de bannière et un module de fonctionnalité). Vous pouvez modifier les propriétés supplémentaires pour les modules de carrousel, de bannière, et de fonctionnalités pour obtenir l’effet souhaité.
1. Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation de la bibliothèque de modules](starter-kit-overview.md)

[Module Bannière promotionnelle](add-alert.md)

[Module de bloc de texte](add-content-rich-block.md)

[Module de bloc de contenu](add-hero-module.md)

[Module de lecture vidéo](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
