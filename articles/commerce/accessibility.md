---
title: Fonctionnalités d’accessibilité
description: Cette rubrique fournit des informations sur les fonctionnalités d’accessibilité dans Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 77c5b2e40c3dd16b95afe421d4515c45af0e81358940c29a14c03754c39a076e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716274"
---
# <a name="accessibility-features-and-capabilities"></a>Fonctionnalités d’accessibilité

[!include [banner](includes/banner.md)]

Cette rubrique fournit des informations sur les fonctionnalités d’accessibilité dans Microsoft Dynamics 365 Commerce.

Les fonctionnalités d’accessibilité fournissent à tous les utilisateurs les moyens fonctionnels d’accéder et d’effectuer des actions afin qu’ils puissent atteindre leurs objectifs. Ce large éventail d’utilisateurs peut nécessiter des outils d’assistance pour l’audition, la vision, la mobilité ou la neurodiversité.

Diverses fonctionnalités de Dynamics 365 Commerce vous permettent de créer votre site afin qu’il comprenne des fonctionnalités d’assistance. Lorsque vous concevez votre site, vous devez tenir compte des domaines de fonctionnalité d’accessibilité mentionnés dans le [Centre d’accessibilité Microsoft](https://www.microsoft.com/accessibility). 

Cette rubrique décrit certains domaines supplémentaires de la fonctionnalité d’accessibilité que vous devez prendre en compte lorsque vous utilisez Dynamics 365 Commerce.

## <a name="image-alt-text"></a>Texte alternatif de l’image

Dynamics 365 Commerce dispose d’un système de gestion des actifs numériques intégré pour suivre les actifs d’images et de vidéos utilisés sur votre site. Des légendes d’image, des descriptions et du texte alternatif peuvent être ajoutés dans le volet des propriétés d’une image lorsqu’elle est sélectionnée ou téléchargée.

## <a name="video-accessibility"></a>Accessibilité vidéo

Le système de gestion des actifs numériques Dynamics 365 Commerce prend en charge plusieurs fonctionnalités d’accessibilité pour le contenu vidéo. Des exemples sont répertoriés dans le tableau suivant.

| Fonctionnalité vidéo               | Description |
|-----------------------------|-------------|
| Sous-titres codés (CC)      | Texte pouvant être affiché pour les éléments audio et descriptifs audio d’une vidéo, pour aider les utilisateurs sourds ou malentendants |
| Sous-titres                   | Fichiers de sous-titres qui affichent le texte des indices de contexte ou des dialogues à l’écran |
| Transcriptions audio           | Transcription textuelle de mots prononcés générée à partir de l’audio d’un actif vidéo |
| Audio descriptif           | Canal audio non principal qui décrit le contenu ou le contexte de ce qui se produit à l’écran |
| Limite d’âge minimum            | Attribut qui peut stocker l’âge minimal qu’un spectateur doit avoir pour visionner une vidéo (métadonnées uniquement) |

### <a name="configure-video-accessibility-elements"></a>Configurer les éléments d’accessibilité vidéo

Dans la section **Bibliothèque multimédia** Commerce de votre site, vous pouvez télécharger des actifs vidéo qui ont des fichiers distincts pour les sous-titres codés, l’audio normal et l’audio descriptif. Les sous-titres peuvent également être générés automatiquement lors du téléchargement d’un actif vidéo.

#### <a name="generate-or-upload-closed-caption-files-during-video-asset-upload"></a>Générez ou téléchargez des fichiers de sous-titres pendant le téléchargement des actifs vidéo

Pour générer automatiquement un fichier de sous-titres lorsque vous téléchargez une vidéo, procédez comme suit.

- Dans la boîte de dialogue **Téléchargement des actifs**, cochez la case **Générer automatiquement des sous-titres codés**. Si vous générez un fichier de sous-titres, le sélecteur de fichiers pour les fichiers de sous-titres ne sera pas disponible dans la boîte de dialogue.

Pour charger manuellement un fichier de sous-titres lorsque vous téléchargez une vidéo, procédez comme suit.

- Dans la boîte de dialogue **Téléchargement des actifs**, décochez la case **Générer automatiquement des sous-titres codés**.

Pour charger des fichiers audio normaux ou audio descriptifs pour la vidéo, utilisez le sélecteur de fichiers dans la boite de dialogue **Téléchargement des actifs**.

> [!NOTE]
> Les sous-titres codés, les fichiers audio standard et les fichiers audio descriptifs peuvent également être ajoutés après le téléchargement d’un fichier vidéo. Accédez à **Bibliothèque multimédia**, sélectionnez l’actif vidéo, puis cliquez sur **Modifier** pour le consulter. Ensuite, dans le volet des propriétés de l’actif vidéo, téléchargez les actifs supplémentaires.

#### <a name="edit-cc-and-audio-transcript-files"></a>Modifier les fichiers de transcription CC et audio

Les fichiers de transcription CC et audio peuvent être modifiés directement dans l’outil de création. La lecture vidéo est disponible pendant l’édition.

Pour modifier les fichiers de transcription CC et audio, procédez comme suit.

1. Accédez à **Bibliothèque multimédia** et sélectionnez le nom de fichier de l’actif vidéo. L’éditeur de sous-titres et de transcriptions apparaît.
1. Sélectionnez **Modifier**.
1. Modifiez les sous-titres codés ou le texte de la transcription.
1. Lorsque vous avez terminé, cliquez sur **Enregistrer**, puis sur **Terminer la modification**.
1. Lorsque vous êtes prêt à publier, sélectionnez **Publier**.

#### <a name="set-the-minimum-age-attribute"></a>Définir l’attribut Âge minimal

Un attribut de métadonnées **Âge minimal** peut être associé aux actifs vidéo.

Pour définir l’attribut **Âge minimal** pour un actif vidéo, procédez comme suit.

1. Accédez à **Bibliothèque multimédia** et sélectionnez l’actif vidéo.
1. Sélectionnez **Modifier**.
1. Dans le volet des propriétés de l’actif vidéo, définissez l’attribut **Âge minimal**.

> [!NOTE]
> Le volet des propriétés est utilisé uniquement pour définir et stocker la valeur d’attribut de métadonnées. Des modules personnalisés doivent être créés pour utiliser cet attribut pour le déclenchement de la lecture.

## <a name="additional-resources"></a>Ressources supplémentaires

[Accessibilité dans les écrans, les produits et les contrôles](/dynamics365/unified-operations/dev-itpro/user-interface/enable-accessibility)

[Centre d’accessibilité Microsoft](https://www.microsoft.com/accessibility)

[Centre d’accessibilité Dynamics 365](/dynamics365/get-started/accessibility/index)

[Vue d’ensemble de la conformité](compliance-overview.md)

[Conformité des cookies](cookie-compliance.md)

[Ajouter une page de stratégie de confidentialité](add-privacy-page.md)

[Remplacer les ID utilisateur associés aux modifications de contenu suivies](replace-IDs-tracked-changes.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]