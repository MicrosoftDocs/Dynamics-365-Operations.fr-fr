---
title: Module Placement de contenu
description: Cette rubrique couvre les modules de placement de contenu et d'article de placement de contenu et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 1b64e930628c969334ff6e643ba23b77445e6e4c
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785298"
---
# <a name="content-placement-module"></a>Module Placement de contenu

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de placement de contenu et d'article de placement de contenu et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Un module de placement de contenu est un conteneur spécial dans lequel d'autres modules peuvent être mis pour une disposition spécifique. Les modules de placement de contenu prennent en charge les types de modules suivants comme modules enfants : article de placement de contenu, article de bienvenue du compte, article de commande de compte, article de liste de souhaits de compte, et article de profil de compte.

Les modules de placement de contenu dérivent les données des modules enfants qu'ils prennent en charge. Par conséquent, les modules de placement de contenu peuvent être utilisés dans différentes manières, en fonction des modules qui sont ajoutés.

Les modules d'article de placement de contenu utilisent des images et du texte pour présenter des promotions, des stratégies, et des fonctionnalités de produit. Par exemple, un module d'article de placement de contenu peut être utilisé sur une page d'accueil pour afficher des stratégies ou des informations sur l'expédition. Les modules de placement de contenu sont pilotés par les données du système de gestion de contenu (CMS) et peuvent être placés dans n'importe quelle page. Toutefois, ils peuvent être utilisés uniquement dans un module de placement de contenu.

## <a name="examples-of-content-placement-modules-in-e-commerce"></a>Exemples de modules de placement de contenu dans le commerce électronique

* Les modules de placement de contenu qui contiennent des modules d'article de placement de contenu peuvent être utilisés sur une page d'accueil ou une page marketing pour présenter des fonctionnalités de produit, des promotions, des stratégies de magasin, des informations sur l'expédition, et d'autres informations via des images et du texte.
* Les modules de placement de contenu qui contiennent les modules d'article de placement de contenu peuvent être utilisés dans les pages de détails de produit pour présenter des fonctionnalités de produit.
* Les modules de placement de contenu qui contiennent des modules d'article de bienvenue de compte ou des article de commande de compte peuvent être utilisés par les pages de gestion du compte.

## <a name="content-placement-module-properties"></a>Propriétés du module de placement de contenu

| Nom de la propriété | Valeur | Description |
|---------------|-------|-------------|
| Largeur         | **Adapter le conteneur** ou **Remplir l'écran** | Si la valeur est définie sur **Adapter le conteneur**, les articles à l'intérieur du module de placement de contenu sont limités à la largeur du module de placement de contenu. Si la valeur est définie **Plein écran**, les articles ne sont pas soumis à la largeur du module de placement de contenu mais peuvent entrer dans le mode pleine page. |

## <a name="content-placement-item-module-properties"></a>Propriétés du module d'article de placement de contenu

| Nom de la propriété | Valeur | Description |
|---------------|-------|-------------|
| En-tête       | Texte d'en-tête et balises d'en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Chaque module d'article de placement de contenu peut avoir un en-tête. La propriété **En-tête** prend en charge les balises d'en-tête. Par défaut, la balise d'en-tête **H2** est utilisée, mais la balise d'en-tête peut être modifiée pour répondre aux besoins en accessibilité. |
| Paragraphe     | Texte du paragraphe | Les modules d'article de placement de contenu prennent en charge le texte de paragraphe dans en format de texte enrichi. Certains capacités de texte enrichi de base sont prises en charge, telles que gras, souligné, et italiques, et des liens hypertexte. Certaines de ces fonctionnalités peuvent être remplacées par le thème de la page qui s'applique au module. |
| Image         | Fichier image | Une image peut être associée au texte. |
| Lien          | Texte de l'URL de lien et du lien | Un lien peut être ajouté au texte pour rediriger les utilisateurs vers une page spécifique. |
| Taille de la vignette     | Un numéro de **1** à **12** | Pour chaque article de placement de contenu, cette propriété définit le nombre d'emplacements auxquels l'article doit remplir le module de placement de contenu. La taille maximale du module de placement de contenu est de 12 emplacements. Si la taille totale de vignette pour les premiers *n* articles dans le module de placement de contenu dépasse 12 emplacements, les articles sont encapsulés à la ligne suivante. |

## <a name="add-a-content-placement-module-that-contains-a-content-placement-item-module-to-a-page"></a>Ajouter un module de placement de contenu qui contient un module d'article de placement de contenu à une page

Pour ajouter un module de placement de contenu qui contient un module d'article de placement de contenu dans une nouvelle page et définit les propriétés requises, procédez comme suit.

1. Créez un modèle nommé **modèle de placement de contenu**.
1. À l'emplacement **Principal** de la page par défaut, ajoutez un module de placement de contenu.
1. Dans le module de placement de contenu, ajoutez un module d'article de placement de contenu.
1. Archivez le modèle, et publiez-le.
1. Utilisez le modèle de placement de contenu que vous venez de créer pour créer une page qui s'appelle **page Placement de contenu**.
1. À l'emplacement **Principal** de la nouvelle page, ajoutez un module de placement de contenu.
1. Dans le module de placement de contenu, ajoutez un module d'article de placement de contenu.
1. Dans le volet des propriétés du module d'article de placement de contenu, sélectionnez une image, ajoutez un en-tête, ajoutez un paragraphe, ajoutez un lien, définissez l'URL du lien, et définissez la taille de la vignette sur **6**.
1. Répétez les étapes 7 et 8 pour ajouter un autre module d'article de placement de contenu avec la même taille de vignette.
1. Enregistrez et affichez un aperçu de la page. Vous devez voir deux articles de placement de contenu qui apparaissent côte à côte. Vous pouvez ajuster la propriété **Taille de la vignette** de chaque module d'article de placement de contenu ou ajouter des modules pour obtenir la disposition souhaitée.
1. Archivez la page, et publiez-la.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du kit de démarrage](starter-kit-overview.md)

[Module Alerte](add-alert.md)

[Module Carrousel](add-carousel.md)

[Module de bloc de contenu riche](add-content-rich-block.md)

[Module Fonctionnalité](add-feature-module.md)

[Module Bannière](add-hero-module.md)

[Module Lecteur vidéo](add-video-player.md)
