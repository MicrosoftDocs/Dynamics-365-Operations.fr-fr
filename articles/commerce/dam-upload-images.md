---
title: Importer des images
description: Cette rubrique décrit comment charger des images dans le générateur de site Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.openlocfilehash: 51571ce221714598b2e2d39c76cb69dcb57cc52b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213792"
---
# <a name="upload-images"></a>Importer des images

[!include [banner](includes/banner.md)]

Cette rubrique décrit comment charger des images dans le générateur de site Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

La bibliothèque multimédia du générateur de site Commerce vous permet de télécharger des images, individuellement ou en bloc, à l'aide de dossiers. Vous devez toujours télécharger la version de l'image avec la résolution et la qualité les plus élevées, car le composant du redimensionneur d'image optimisera automatiquement l'image pour différentes fenêtres d'affichage et leurs points d'arrêt.

### <a name="image-information-specified-during-upload"></a>Informations d'image spécifiées lors du téléchargement

Lors du téléchargement d'une image, les informations suivantes peuvent être spécifiées.

- **Titre, texte alternatif, description, mots-clés** : métadonnées de l'image ou des images. Le titre et le texte alternatif sont des valeurs obligatoires.
- **Sélectionner une catégorie** :
    - **Aucun** : Utilisé pour une ou plusieurs images de narration de commerce électronique.
    - **Produit, catégorie, client, employé, catalogue** : Utilisé pour l'image ou les images omnicanal Dynamics 365 Commerce.
- **Publier les actifs après chargement** : lorsque cette case est cochée, la ou les images sont publiées immédiatement après le chargement.

> [!NOTE]
> Les actifs d'image auxquels une catégorie a été affectée sont également automatiquement étiquetés avec la catégorie en tant que mot clé pour faciliter la recherche d'éléments de catégorie spécifique.

### <a name="naming-conventions-for-omni-channel-images"></a>Conventions de dénomination des images omnicanal 

Si vous avez configuré la bibliothèque multimédia comme processus d'arrière-plan d'image omnicanal, vous pouvez utiliser des catégories d'images pour indiquer à quelle catégorie l'image téléchargée appartient. Il convient également de suivre une convention de dénomination pour garantir que les images sont correctement récupérées par d'autres canaux, tels que le point de vente (PDV).

La convention de dénomination par défaut varie en fonction de la catégorie :
- Les images du catalogue doivent être intitulées "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"
- Les images de catégorie doivent être intitulées "**/Categories/\{CategoryName\}.png**"
- Les images de client doivent être intitulées "**/Customers/\{CustomerNumber\}.jpg**"
- Les images d'employé doivent être intitulées "**/Workers/\{WorkerNumber\}.jpg**"
- Les images de produit doivent être intitulées "**/Products/\{ProductNumber\}_000_001.png**"
    - 001 est la séquence de l'image et peut être 001, 002, 003, 004 ou 005
- Les images de variante de produit doivent être intitulées "**/Products/\{ProductNumber\}\_\{Size\}\_\{Color\}\_\{Style\}\_000_001.png**"

## <a name="upload-an-image"></a>Télécharger une image

Pour télécharger une image dans le générateur de site, procédez comme suit.

1. Dans le volet de navigation de gauche, cliquez sur **Bibliothèque multimédia**.
1. Dans la barre de commandes, sélectionnez **Télécharger \> Télécharger des éléments multimédias**.
1. Dans la fenêtre de l'Explorateur de fichiers, recherchez et sélectionnez un ou plusieurs fichiers image à télécharger, puis sélectionnez **Ouvrir**.
1. Dans la boîte de dialogue **Télécharger un élément multimédia**, entrez le titre et le texte de remplacement requis.
1. Entrez une description et des mots clés facultatifs et sélectionnez une catégorie si vous le souhaitez. 
1. Si vous souhaitez publier les images immédiatement après le téléchargement, sélectionnez la case à cocher **Publier les éléments multimédia après le téléchargement**.
1. Cliquez sur **OK**.

## <a name="upload-a-folder-of-images"></a>Télécharger un dossier d'images

Pour télécharger en bloc un dossier d'images dans le générateur de site, procédez comme suit.

1. Dans le volet de navigation de gauche, cliquez sur **Bibliothèque multimédia**.
1. Dans la barre de commandes, sélectionnez **Télécharger \> Télécharger le dossier**.
1. Dans la fenêtre de l'Explorateur de fichiers, recherchez et sélectionnez un dossier à télécharger, puis sélectionnez **Ouvrir**.
1. Dans la boîte de dialogue **Télécharger des éléments multimédia**, entrez des mots clés facultatifs et sélectionnez une catégorie si vous le souhaitez. 
1. Si vous souhaitez publier les images dans le dossier immédiatement après le téléchargement, sélectionnez la case à cocher **Publier les éléments multimédia après le téléchargement**.
1. Cliquez sur **OK**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble de la gestion des actifs numériques](dam-overview.md)

[Télécharger une vidéo](dam-upload-video.md)

[Télécharger des fichiers](dam-upload-files.md)

[Rogner les images](dam-crop-images.md)

[Personnaliser les points focaux de l’image](dam-custom-focal-point.md)

[Charger et diffuser des fichiers statiques](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]