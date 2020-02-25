---
title: Module Lecteur vidéo
description: Cette rubrique couvre les modules de lecteur vidéo et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: e94658eed12b12d6666e63d2c06b86646c81a120
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025644"
---
# <a name="video-player-module"></a>Module Lecteur vidéo


[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de lecteur vidéo et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Le module de lecteur vidéo permet de prendre en charge la lecture de vidéos. Il peut être ajouté à n'importe quelle page, à condition que le contenu vidéo soit téléchargé et disponible dans le système de gestion de contenu (CMS). Le module lecteur vidéo prend en charge le type de média .mp4.

## <a name="video-player-module"></a>Module de lecture vidéo

Le module de lecteur vidéo peut être utilisé pour présenter des vidéos sur un site de commerce électronique. Il prend en charge toutes les fonctionnalités de lecture, telles que la lecture, la pause, le mode plein écran, les descriptions audio et les sous-titres codés. Le module de lecteur vidéo prend également en charge la personnalisation des sous-titres codés pour satisfaire aux normes d'accessibilité Microsoft. Par exemple, vous pouvez personnaliser la taille de police et la couleur d'arrière-plan.

Le module lecteur vidéo prend également en charge les pistes audio secondaires. Lorsqu'une vidéo est téléchargée vers le CMS, une piste audio secondaire peut également être téléchargée. Le module lecteur vidéo peut ensuite lire la piste audio secondaire si un utilisateur la sélectionne.

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
| Lecture plein écran       | **Vrai** ou **Faux**               | Si la valeur est définie sur **Vrai**, la vidéo est lue en mode plein écran. |
| Activer le déclencheur de pause    | **Vrai** ou **Faux**               | Si la valeur est définie sur **Vrai**, un bouton lecture/pause s'affiche dans la vidéo. |
| Contrôles du lecteur vidéo | **Vrai** ou **Faux**               | Si la valeur est définie sur **Vrai**, tous les contrôles du lecteur vidéo sont affichés. Ceux-ci incluent les boutons de lecture et de pause, un indicateur de progression et des options de sous-titres codés. |
| Masquer l’affiche     | **Vrai** ou **Faux**               | Une vidéo peut avoir un contour de poster. Lorsque la valeur de cette propriété est définie sur **Vrai**, le cadre du poster est masqué. |
| Niveau du masque            | Nombre de **0** à **100** | Masque qui est appliqué à la vidéo pour le style. |

## <a name="add-a-video-player-module-to-a-page"></a>Ajouter un module de lecture vidéo à une page

> [!NOTE] 
> Avant de créer un module de lecteur vidéo, vous devez d'abord télécharger une vidéo dans la bibliothèque multimédia.

Pour ajouter un module de lecteur vidéo à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Créez un modèle de page nommé **modèle de lecteur vidéo**.
1. À l'emplacement **Principal** de la page par défaut, ajoutez un module de conteneur.
1. Dans le module de conteneur, ajoutez le lecteur vidéo et les modules de lecteur de vidéo d'ambiance.
1. Terminez la modification du modèle et publiez-le.
1. Utilisez le modèle de lecteur vidéo que vous avez créé pour générer une page qui s'appelle **page Lecteur vidéo**.
1. À l'emplacement **Principal** de la nouvelle page, ajoutez un module de lecteur de vidéo.
1. Dans le volet des propriétés du module lecteur vidéo, sélectionnez **Ajouter une vidéo**.
1. Dans la boîte de dialogue **Sélecteur multimédia**, sélectionnez une vidéo, puis sélectionnez **Importer un nouvel élément multimédia**.
1. Enregistrez et affichez un aperçu de la page. Vous devez voir le module vidéo sur la page. Vous pouvez modifier des paramètres supplémentaires pour personnaliser le comportement du module.
1. Terminez la modification de la page et publiez-la.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du kit de démarrage](starter-kit-overview.md)

[Module de bannière promotionnelle](add-alert.md)

[Module de carrousel](add-carousel.md)

[Module de bloc de texte](add-content-rich-block.md)

[Module de bloc de contenu](add-hero-module.md)
