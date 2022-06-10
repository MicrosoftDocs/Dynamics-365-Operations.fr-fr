---
title: Module Lecteur vidéo
description: Cette rubrique couvre les modules de lecteur vidéo et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b7ec2ea0f8360bbf1dffa023e4546e4deadb5ff9
ms.sourcegitcommit: ccb39767bd3430c24f4653c26560bba2cd66553c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/19/2022
ms.locfileid: "8780762"
---
# <a name="video-player-module"></a>Module de lecture vidéo

[!include [banner](includes/banner.md)]

Cette rubrique couvre les modules de lecteur vidéo et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

Le module de lecteur vidéo permet de prendre en charge la lecture de vidéos. Il peut être ajouté à n’importe quelle page, à condition que le contenu vidéo soit téléchargé et disponible dans le système de gestion de contenu (CMS). Le module lecteur vidéo prend en charge le type de média .mp4.

## <a name="video-player-module"></a>Module de lecture vidéo

Le module de lecteur vidéo peut être utilisé pour présenter des vidéos sur un site de commerce électronique. Il prend en charge toutes les fonctionnalités de lecture, telles que la lecture, la pause, le mode plein écran, les descriptions audio et les sous-titres codés. Le module de lecteur vidéo prend également en charge la personnalisation des sous-titres codés pour satisfaire aux normes d’accessibilité Microsoft. Par exemple, vous pouvez personnaliser la taille de police et la couleur d’arrière-plan.

Le module lecteur vidéo prend également en charge les pistes audio secondaires. Lorsqu’une vidéo est téléchargée vers le CMS, une piste audio secondaire peut également être téléchargée. Le module lecteur vidéo peut ensuite lire la piste audio secondaire si un utilisateur la sélectionne.

### <a name="examples-of-video-player-modules-in-e-commerce"></a>Exemples de modules de lecteur vidéo dans le commerce électronique

- Vidéos de formation sur les pages de détails des produits ou des pages marketing
- Vidéos publicitaires ou vidéos sur les stratégies sur une page marketing
- Vidéos marketing qui mettent en avant des fonctionnalités du produit sur les pages de détails des produits ou des pages marketing

L’image suivante montre un exemple de module de lecture vidéo sur une page d’accueil.

![Exemple de module de lecture vidéo.](./media/ecommerce-videoplayer.PNG)

### <a name="video-player-module-properties"></a>Propriétés du module de lecture vidéo

| Nom de la propriété         | Valeur                               | Description |
|-----------------------|-------------------------------------|-------------|
| Titre               | Texte d’en-tête et balise d’en-tête (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Par défaut, la balise d’en-tête **H2** est utilisée pour le titre, mais la balise peut être modifiée pour répondre aux besoins en accessibilité. |
| Texte enrichi             | Texte du paragraphe | Les modules prennent en charge le texte de paragraphe dans en format de texte enrichi. Certains capacités de texte enrichi de base sont prises en charge, telles que les liens hypertexte, le gras, le souligné, et l’italique. Certaines de ces fonctionnalités peuvent être remplacées par le thème de la page qui s’applique au module. |
| Lien                  | Texte du lien, URL du lien, étiquette ARIA (Applications Internet enrichie accessibles), et sélecteur **Ouvrir le lien dans le nouvel onglet** | Le module prend en charge un ou plusieurs liens d’« appels à l’action ». Si un lien est ajouté, un texte de lien, une URL, et une étiquette ARIA sont requis. Les étiquettes ARIA doivent être descriptives pour satisfaire aux exigences d’accessibilité. Les liens peuvent être configurés de sorte qu’ils sont ouverts sur un nouvel onglet. |
| Sous-texte              | Titre, texte ou liens | Un contexte supplémentaire pour le module de lecture vidéo peut être ajouté, tel qu’un nom d’auteur ou de concepteur, ou des liens vers des blogs personnels. |
| Lecture automatique             | **Vrai** ou **Faux**               | Si la valeur est définie sur **Vrai**, la vidéo est automatiquement lue. |
| Sourdine                  | **Vrai** ou **Faux**               | Si la valeur est définie sur **Vrai**, l’audio est automatiquement mis en sourdine. Pour ce lecteur, la valeur par défaut est **Faux**. Dans le navigateur Chrome, les vidéos en lecture automatique sont mises en sourdine par défaut, et l’audio est joué si l’utilisateur lit manuellement le vidéo. |
| Boucle                  | **Vrai** ou **Faux**               | Si la valeur est définie sur **Vrai**, la vidéo est répétée en boucle. |
| Supports                 | Chemin d’accès et nom du fichier vidéo | Fichier vidéo lu dans le lecteur vidéo. |
| Lecture plein écran       | **Vrai** ou **Faux**               | Si la valeur est définie sur **Vrai**, la vidéo est lue en mode plein écran. |
| Activer le déclencheur de pause    | **Vrai** ou **Faux**               | Si la valeur est définie sur **Vrai**, un bouton lecture/pause s’affiche dans la vidéo. |
| Contrôles du lecteur vidéo | **Vrai** ou **Faux**               | Si la valeur est définie sur **Vrai**, tous les contrôles du lecteur vidéo sont affichés. Ceux-ci incluent les boutons de lecture et de pause, un indicateur de progression et des options de sous-titres codés. |
| Masquer l’affiche     | **Vrai** ou **Faux**               | Une vidéo peut avoir un contour de poster. Lorsque la valeur de cette propriété est définie sur **Vrai**, le cadre du poster est masqué. |
| Niveau du masque            | Nombre de **0** à **100** | Masque qui est appliqué à la vidéo pour le style. |

> [!IMPORTANT]
> Les propriétés **Titre**, **Texte enrichi**, **Lien** et **Sous-texte** sont disponibles à partir de la version 10.0.20 de Dynamics 365 Commerce.

## <a name="add-a-video-player-module-to-a-page"></a>Ajouter un module de lecture vidéo à une page

> [!NOTE] 
> Avant de créer un module de lecteur vidéo, vous devez d’abord télécharger une vidéo dans la bibliothèque multimédia.

Pour ajouter un module de lecteur vidéo à une nouvelle page et définir les propriétés requises, procédez comme suit.

1. Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un nouveau modèle.
1. Dans la boîte de dialogue **Nouveau modèle**, sous **Nom du modèle**, entrez **Modèle de lecture vidéo**, puis cliquez sur **OK**.
1. Dans l’emplacement **Corps**, sélectionnez le bouton représentant des points de suspension (**…**), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Page par défaut**, puis cliquez sur **OK**.
1. Dans l’emplacement **Principal** du module **Page par défaut**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.
1. Dans l’emplacement **Conteneur**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Lecture vidéo**, puis cliquez sur **OK**.
1. Sélectionnez **Enregistrer**, **Terminer la modification** pour archiver le modèle de fragment, puis **Publier** pour le publier. 
1. Accédez à **Pages**, puis sélectionnez **Nouveau** pour créer une page.
1. Dans la boîte de dialogue **Créer une page**, sous **Nom de la page**, entrez **Page de lecteur vidéo**, puis cliquez sur **Suivant**.
1. Sous **Choisir un modèle**, sélectionnez le **Modèle de lecture vidéo** que vous avez créé, puis sélectionnez **Suivant**.
1. Sous **Choisir une mise en page**, sélectionnez une mise en page (par exemple, **Disposition flexible**), puis sélectionnez **Suivant**.
1. Sous **Revoir et terminer**, vérifiez la configuration de la page. Si vous devez modifier les informations de la page, sélectionnez **Précédent**. Si les informations de la page sont correctes, sélectionnez **Créer une page**.
1. Dans l’emplacement **Principal** de la nouvelle page, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.
1. Dans l’emplacement **Conteneur**, sélectionnez le bouton représentant des points de suspension (**...**), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Lecture vidéo**, puis cliquez sur **OK**.
1. Dans le volet des propriétés du module de lecture vidéo, sélectionnez **Ajouter une vidéo**.
1. Dans la boîte de dialogue **Sélecteur multimédia**, sélectionnez une vidéo, puis sélectionnez **Importer un nouvel élément multimédia**.
1. Dans l’Explorateur de fichiers, sélectionnez un fichier vidéo, puis sélectionnez **Ouvrir**.
1. Dans la boîte de dialogue **Télécharger un élément multimédia**, entrez un titre et d’autres informations selon vos besoins, puis sélectionnez **OK**.
1. Dans la boîte de dialogue **Sélecteur multimédia**, sélectionnez **Fermer**.
1. Cliquez sur **Enregistrer**, puis sur **Aperçu** pour afficher un aperçu de la page. Vous devez voir le module vidéo sur la page. Vous pouvez modifier des paramètres supplémentaires pour personnaliser le comportement du module.
1. Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier. 

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation de la bibliothèque de modules](starter-kit-overview.md)

[Module Bannière promotionnelle](add-alert.md)

[Module Carrousel](add-carousel.md)

[Module de bloc de texte](add-content-rich-block.md)

[Module de bloc de contenu](add-hero-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
