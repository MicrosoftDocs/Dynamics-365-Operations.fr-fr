---
title: Télécharger des vidéos
description: Cet article décrit comment charger des vidéos dans le générateur de site Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 06/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: a48c6cbdd5898a2156f60dada40e94cd402df9c5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890539"
---
# <a name="upload-videos"></a>Télécharger des vidéos

[!include [banner](includes/banner.md)]

Cet article décrit comment charger des vidéos dans le générateur de site Microsoft Dynamics 365 Commerce.

La bibliothèque multimédia du générateur de site Commerce vous permet de télécharger des vidéos. Vous devez toujours télécharger la version d’une vidéo avec le bitrate et la résolution les plus élevés, car la vidéo sera automatiquement convertie pour être appropriée aux différentes fenêtres d’affichage et leurs points d’arrêt.

### <a name="video-information-specified-during-upload"></a>Informations vidéo spécifiées lors du téléchargement

Lors du téléchargement d’une vidéo, les informations suivantes peuvent être spécifiées.

- **Titre, description, mots clés** : Métadonnées de la vidéo.
- **Générer automatiquement des sous-titres codés** : spécifie si les sous-titres doivent être générés automatiquement pour la vidéo (seule la langue anglaise est prise en charge). 
- **Sous-titrage** : spécifie les sous-titres codés à utiliser.
- **Audio régulier** : spécifie la piste audio standard à utiliser.
- **Vignette** : spécifie la vignette de la vidéo. Si non spécifié, elle sera générée automatiquement.
- **Audio descriptif** : spécifie la piste audio descriptive à utiliser.

## <a name="upload-a-video"></a>Télécharger une vidéo

Pour télécharger une vidéo dans le générateur de site, procédez comme suit.

1. Dans le volet de navigation de gauche, cliquez sur **Bibliothèque multimédia**.
1. Dans la barre de commandes, sélectionnez **Télécharger \> Télécharger des éléments multimédias**.
1. Dans la fenêtre de l’Explorateur de fichiers, recherchez et sélectionnez un ou plusieurs fichiers vidéo à télécharger, puis sélectionnez **Ouvrir**.
1. Dans la boîte de dialogue **Télécharger un élément multimédia**, entrez le titre et le texte de remplacement requis.
1. Entrez une description et des mots clés facultatifs et sélectionnez une catégorie si vous le souhaitez. 
1. Si vous souhaitez publier les images immédiatement après le téléchargement, sélectionnez la case à cocher **Publier les éléments multimédia après le téléchargement**.
1. Cliquez sur **OK**.

Si vous importez plusieurs types d’actifs simultanément (par exemple, des images et des vidéos), dans la boîte de dialogue **Télécharger un élément multimédia**, vous ne pourrez spécifier que des mots clés, si les fichiers doivent être publiés immédiatement après le téléchargement et si les sous-titres codés doivent être générés automatiquement pour les fichiers vidéo. Tous les actifs partageront les mêmes mots clés.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la gestion des actifs numériques](dam-overview.md)

[Importer des images](dam-upload-images.md)

[Télécharger des fichiers](dam-upload-files.md)

[Rogner les images](dam-crop-images.md)

[Personnaliser les points focaux de l’image](dam-custom-focal-point.md)

[Charger et diffuser des fichiers statiques](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
