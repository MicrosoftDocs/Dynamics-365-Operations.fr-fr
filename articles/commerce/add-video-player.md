---
title: Module Lecteur vidéo
description: Cette rubrique couvre les modules de lecteur vidéo et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 12/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1c78583f39dbacdc7b38e89c33e67ae23731bf8a
ms.sourcegitcommit: 96bfc20eb748f4090a2b5e1ff9f54997d5a5d359
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/04/2019
ms.locfileid: "2885899"
---
# <a name="video-player-module"></a>Module Lecteur vidéo

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de lecteur vidéo et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Les modules de lecteur vidéo permettent de prendre en charge la lecture de vidéos. Deux modules de lecteur de vidéo sont fournis dans le kit de démarrage du magasin : le module de lecteur vidéo d'ambiance et le module de lecteur vidéo. Les deux lecteurs prennent en charge le type de multimédia .mp4.

## <a name="ambient-video-player-module"></a>Module de lecture vidéo d'ambiance

Le module de lecteur vidéo d'ambiance prend en charge les courts vidéos d'information. Il doit être utilisé pour les vidéos de moins de cinq secondes. Ce lecteur prend en charge des fonctionnalités de lecture vidéo limitées, telles que la lecture et la pause.

### <a name="examples-of-ambient-video-player-modules-in-e-commerce"></a>Exemples de modules de lecteur vidéo d'ambiance dans le commerce électronique

- Courtes vidéos d'information qui mettent en avant de nouveaux produits sur la page d'accueil
- Courtes vidéos d'information qui mettent en avant des fonctionnalités de produit sur une page de détails des produits

### <a name="ambient-video-player-module-properties"></a>Propriétés du module de lecture vidéo d'ambiance

| Nom de la propriété     | Valeur                 | Description |
|-------------------|-----------------------|-------------|
| Lire automatiquement          | **Vrai** ou **Faux** | Si la valeur est définie sur **Vrai**, la vidéo est automatiquement lue. |
| Sourdine              | **Vrai** ou **Faux** | Si la valeur est définie sur **Vrai**, l'audio est automatiquement mis en sourdine. Pour ce lecteur, la valeur par défaut est **Vrai**. Dans le navigateur Google Chrome, les vidéos en lecture automatique sont mises en sourdine par défaut, et l'audio est joué si l'utilisateur lit manuellement le vidéo. |
| Boucle              | **Vrai** ou **Faux** | Si la valeur est définie sur **Vrai**, la vidéo est répétée en boucle. |
| Supports             |  Chemin d'accès et nom du fichier vidéo | Fichier vidéo lu par le lecteur vidéo. |
| Contrôles de lecture | **Vrai** ou **Faux** | Si la valeur est définie sur **Vrai**, un bouton lecture/pause s'affiche dans la vidéo. Si la valeur est définie sur **Faux**, le bouton lecture/pause n'est pas affiché, mais les utilisateurs peuvent mettre sur pause et reprendre la vidéo à l'aide du clavier. |

## <a name="video-player-module"></a>Module Lecteur vidéo

Le module de lecteur vidéo peut être utilisé pour présenter des vidéos sur un site de commerce électronique. Il prend en charge toutes les fonctionnalités de lecture, telles que la lecture, la pause, le mode plein écran, et les sous-titres codés. Le module de lecteur vidéo prend également en charge la personnalisation des sous-titres codés pour satisfaire aux normes d'accessibilité Microsoft. Par exemple, vous pouvez personnaliser la taille de police et la couleur d'arrière-plan.

Le module lecteur vidéo prend également en charge les pistes audio secondaires. Lorsqu'une vidéo est téléchargée, une piste audio secondaire peut également être téléchargée. Le module lecteur vidéo peut ensuite lire la piste audio secondaire si un utilisateur la sélectionne.

### <a name="examples-of-video-player-modules-in-e-commerce"></a>Exemples de modules de lecteur vidéo dans le commerce électronique

- Vidéos de formation sur les pages de détails des produits ou des pages marketing
- Vidéos publicitaires ou vidéos sur les stratégies sur une page marketing
- Vidéos marketing qui mettent en avant des fonctionnalités du produit sur les pages de détails des produits ou des pages marketing

### <a name="video-player-module-properties"></a>Propriétés du module de lecture vidéo

| Nom de la propriété         | Valeur                               | Description |
|-----------------------|-------------------------------------|-------------|
| Lecture automatique             | **Vrai** ou **Faux**               | Si la valeur est définie sur **Vrai**, la vidéo est automatiquement lue. |
| Sourdine                  | **Vrai** ou **Faux**               | Si la valeur est définie sur **Vrai**, l'audio est automatiquement mis en sourdine. Pour ce lecteur, la valeur par défaut est **Faux**. Dans le navigateur Chrome, les vidéos en lecture automatique sont mises en sourdine par défaut, et l'audio est joué si l'utilisateur lit manuellement le vidéo. |
| Boucle                  | **Vrai** ou **Faux**               | Si la valeur est définie sur **Vrai**, la vidéo est répétée en boucle. |
| Supports                 | Chemin d'accès et nom du fichier vidéo | Fichier vidéo lu dans le lecteur vidéo. |
| Contrôles de lecture     | **Vrai** ou **Faux**               | Si la valeur est définie sur **Vrai**, un bouton lecture/pause s'affiche dans la vidéo. Si la valeur est définie sur **Faux**, le bouton lecture/pause n'est pas affiché, mais les utilisateurs peuvent mettre sur pause et reprendre la vidéo à l'aide du clavier. |
| Lecture plein écran       | **Vrai** ou **Faux**               | Si la valeur est définie sur **Vrai**, la vidéo est lue en mode plein écran. |
| Contrôles              | **Vrai** ou **Faux**               | Si la valeur est définie sur **Vrai**, tous les contrôles sont affichés. Ceux-ci incluent les boutons de lecture et de pause, un indicateur de progression, et des sous-titres codés. |
| Masquer la bordure du poster     | **Vrai** ou **Faux**               | Une vidéo peut avoir un contour de poster. Lorsque la valeur de cette propriété est définie sur **Vrai**, le cadre du poster est masqué. |
| Niveau du masque            | Nombre de **0** à **100** | Masque qui est appliqué à la vidéo pour le style. |
| Style d'icône Plein écran | **Carré** ou **Flèche**             | Le style de l'icône Plein écran affiché dans le lecteur vidéo. |

## <a name="add-a-video-player-module-to-a-page"></a>Ajouter un module de lecture vidéo à une page

Pour ajouter un module de lecteur vidéo à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Créez un modèle de page nommé **modèle de lecteur vidéo**.
1. À l'emplacement **Principal** de la page par défaut, ajoutez un module de conteneur.
1. Dans le module de conteneur, ajoutez le lecteur vidéo et les modules de lecteur de vidéo d'ambiance.
1. Archivez le modèle, et publiez-le.
1. Utilisez le modèle de lecteur vidéo que vous venez de créer pour créer une page qui s'appelle **page Lecteur vidéo**.
1. À l'emplacement **Principal** de la nouvelle page, ajoutez un module de lecteur de vidéo d'ambiance.
1. Dans les paramètres du module de lecture vidéo d'ambiance, accédez à **Multimédia**, et téléchargez un fichier vidéo. Vous pouvez modifier **Lecture automatique**, **Boucle** et d'autres propriétés comme vous le souhaitez.
1. Enregistrez et affichez un aperçu de la page.
1. À l'emplacement **Principal** de la nouvelle page, ajoutez un module de lecteur de vidéo.
1. Dans les paramètres du module de lecture vidéo, accédez à **Multimédia**, et téléchargez un fichier vidéo.
1. Enregistrez et affichez un aperçu de la page. Vous devez voir les deux modules vidéo sur la page. Vous pouvez modifier des paramètres supplémentaires pour personnaliser le comportement de chaque module.
1. Archivez la page, et publiez-la.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du kit de démarrage](starter-kit-overview.md)

[Module Alerte](add-alert.md)

[Module Carrousel](add-carousel.md)

[Module de bloc de contenu riche](add-content-rich-block.md)

[Module Placement de contenu](add-content-placement-modules.md)

[Module Fonctionnalité](add-feature-module.md)

[Module Bannière](add-hero-module.md)
