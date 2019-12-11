---
title: Module de bloc de contenu riche
description: Cette rubrique couvre les modules de contenu riche et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 27dabb425b3c9a3015ffc54ff3c0e50b7ee11749
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785419"
---
# <a name="content-rich-block-module"></a>Module de bloc de contenu riche

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de contenu riche et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Un module de bloc de contenu riche est un conteneur spécial dans lequel un ou plusieurs articles de bloc de contenu riche peuvent être placés. Les modules en bloc de contenu riche sont utilisés pour le contenu textuel dans une page. Ce contenu peut être informationnel ou promotionnel.

Les modules de bloc de contenu riche sont pilotés par les données du système de gestion de contenu (CMS) et peuvent être placés dans n'importe quelle page. Ils sont autonomes et ne dépendent du contexte de page ou d'un autre module.

## <a name="examples-of-content-rich-block-modules-in-e-commerce"></a>Exemples de modules de bloc de contenu riche dans le commerce électronique

Les modules de bloc de contenu riche peuvent être utilisés comme suit :

* Pour présenter des fonctionnalités de produit sur une page de détails des produits.
* À titre indicatif sur n'importe quelle page. Par exemple, ils peuvent expliquer les avantages des programmes de fidélité, décrire les stratégies d'expédition et de retour, répondre aux questions fréquentes, ou offrir du contenu « À propos de nous ».
* Pour ajouter des messages personnalisés sur une page de détails des produits. (par exemple, « Expédition gratuite pour les commandes de plus de 50 $ »).
* Pour les exclusions de responsabilité et les détails de contact sur les pages de détails des produits, des pages de panier, les pages de caisse et d'autres pages (par exemple, « L'expédition et les retours sont soumis à des stratégies de magasin »).

## <a name="content-rich-block-module-properties"></a>Propriétés du module de bloc de contenu riche

| Nom de la propriété     | Valeur                                 | Propriété |
|-------------------|---------------------------------------|----------|
| Nombre de colonnes | Un numéro de **1** à **4**     | Nombre de colonnes dans le bloc de contenu riche. Il peut y avoir jusqu'à quatre colonnes. |
| Largeur             | **Remplir le conteneur** ou **Remplir l'écran** | Si la valeur est définie sur **Remplir le conteneur**, les articles à l'intérieur du conteneur sont limités à la largeur du conteneur. Si la valeur est définie **Plein écran**, les articles ne sont pas soumis à la largeur du conteneur mais peuvent entrer dans le mode pleine page. Vous pouvez modifier la valeur pour obtenir la disposition appropriée. |

## <a name="content-rich-block-item-module-properties"></a>Propriétés du module d'article de bloc de contenu riche

| Nom de la propriété | Valeur          | Description |
|---------------|----------------|-------------|
| Paragraphe     | Texte du paragraphe | Texte qui accompagne chaque article de bloc de contenu riche. Certains capacités de texte enrichi de base sont prises en charge, telles que gras, souligné, et italiques. |

## <a name="add-a-content-rich-block-module-to-a-page"></a>Ajouter un module de bloc de contenu riche à une page

Pour ajouter un module de bloc de contenu riche à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Créez un modèle de page nommé **modèle de contenu**.
1. À l'emplacement **Principal** de la page par défaut, ajoutez un module de bloc de contenu riche.
1. Archivez le modèle, et publiez-le.
1. Utilisez le modèle de contenu que vous venez de créer pour créer une page qui s'appelle **page Contenu**.
1. À l'emplacement **Principal** de la nouvelle page, ajoutez un module de bloc de contenu riche.
1. Dans les propriétés du module de bloc de contenu riche, définissez le nombre de colonnes sur **2**.
1. Dans le module de bloc de contenu riche, sélectionnez **Ajouter un module**, puis ajoutez un article de bloc de contenu riche (par exemple, **item1**).
1. Dans le nouvel article de bloc de contenu riche, ajoutez le texte du paragraphe.
1. Dans le module de bloc de contenu riche, sélectionnez **Ajouter un module**, puis ajoutez un article de bloc de contenu riche (par exemple, **item2**).
1. Dans le nouvel article de bloc de contenu riche, ajoutez le texte du paragraphe.
1. Enregistrer la page et affichez un aperçu des modifications. Vous devez voir deux blocs de texte riche dans une vue à deux colonne.
1. Archivez la page, et publiez-la.

> [!NOTE]
> Si vous ajoutez un troisième article de bloc de contenu riche, il sera empilé sous les deux articles que vous avez déjà ajoutés. En modifiant le nombre de colonnes et d'articles dans le conteneur, vous pouvez obtenir différentes dispositions pour le contenu textuel.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du kit de démarrage](starter-kit-overview.md)

[Module Alerte](add-alert.md)

[Module Carrousel](add-carousel.md)

[Module Placement de contenu](add-content-placement-modules.md)

[Module Fonctionnalité](add-feature-module.md)

[Module Bannière](add-hero-module.md)

[Module Lecteur vidéo](add-video-player.md)

