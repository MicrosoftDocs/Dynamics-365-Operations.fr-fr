---
title: Ajouter une icône de favori
description: Cette rubrique explique comment ajouter une icône de favori à votre site.
author: bicyclingfool
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 9268bc74a4131256f5a2e88df833104db271b56a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797717"
---
# <a name="add-a-favicon"></a>Ajouter une icône de favori

[!include [banner](includes/banner.md)]

Cette rubrique explique comment ajouter une icône de favori à votre site.

Une icône de favori est un petit fichier graphique affiché sous un onglet du navigateur web, dans la barre d’adresse, dans l’historique de navigation, et dans les signets ou les favoris, entre autres. Nous vous recommandons d’ajouter une icône de favori à votre site, car elle représente et renforce votre marque, et aide à distinguer votre site d’autres sites que vos clients visitent.

Bien que vous puissiez ajouter plusieurs icônes de favori de différentes tailles et types de fichiers à votre site, cette rubrique explique comment ajouter une icône de favori unique. Toutefois, les mêmes processus et emplacement sont utilisés pour ajouter des une icônes de favori.

## <a name="upload-a-favicon-to-your-sites-asset-collection"></a>Chargement de l’icône de favori dans la collection d’actifs du site

Pour charger l’icône de favori dans la collection d’actifs du site, procédez comme suit.

1. Dans le volet de navigation de gauche, cliquez sur **Bibliothèque multimédia**.
1. Dans la barre de commandes, sélectionnez **Télécharger \> Télécharger des éléments multimédias**.
1. Dans la fenêtre de l’Explorateur de fichiers, accédez au fichier image favicon que vous souhaitez télécharger, sélectionnez-le, puis sélectionnez **Ouvrir**.
1. Dans la boîte de dialogue **Télécharger un élément multimédia**, entrez le titre et le texte de remplacement requis.
1. Si vous souhaitez publier l’image immédiatement après le téléchargement, sélectionnez la case à cocher **Publier les éléments multimédia après le téléchargement**.

    > [!NOTE]
    > Si vous ne sélectionnez pas la case à cocher **Publier les éléments multimédia après le téléchargement**, vous devez retourner à la page **Éléments multimédia** et publier manuellement l’icône de favori ultérieurement.

1. Cliquez sur **OK**.
1. Dans le volet de propriété de droite, copiez l’URL publique de l’icône de favori. Vous utiliserez cette URL ultérieurement.

## <a name="create-the-html-for-your-favicon"></a>Créer l’HTML pour l’icône de favori

Pour créer le fichier HTML pour l’icône de favori, utilisez la chaîne HTML suivante. Pour l’attribut **href**, remplacez **Public\_URL\_for\_your\_favicon** par l’URL publique copiée précédemment.

`<link rel="shortcut icon" href="Public_URL_for_your_favicon">`

## <a name="create-a-fragment-that-contains-a-metatag-for-your-favicon"></a>Créer un fragment contenant une balise META pour votre icône de favori

Pour créer un fragment contenant une balise META pour votre icône de favori, suivez cette procédure.

1. Accédez à **Fragments**, et sélectionnez **Nouveau**.
1. Dans la boîte de dialogue **Nouveau fragment**, sélectionnez **Métabalises** comme module sur lequel le fragment est basé.
1. Entrez un nom pour le fragment, puis sélectionnez **OK**.
1. Dans l’arborescence de la hiérarchie des fragments, sélectionnez l’enfant **Metatags par défaut**.
1. Dans le volet droit, sous **Balises Meta**, sélectionnez **Ajouter**, puis entrez la chaîne HTML que vous avez créée précédemment pour l’icône de favori. 
1. Sélectionnez **Terminer la modification**, puis **Publier** pour publier le fragment.

## <a name="add-the-metatag-fragment-to-the-html-head-section-of-your-pages"></a>Ajouter le fragment de métabalise à la section d’en-tête HTML de vos pages

Pour ajouter le fragment de métabalise à la section d’**en-tête** HTML de vos pages, suivez cette procédure.

1. Accédez à **Modèles**, puis ouvrez le modèle pour les pages dans lesquelles vous souhaitez ajouter votre icône de favori, puis sélectionnez **Modifier**.
1. Dans l’arborescence de la hiérarchie des modèles, sélectionnez les points de suspension (**...**) à droite du conteneur **En-tête HTML**, puis sélectionnez **Ajouter un fragment**.
1. Dans la boîte de dialogue **Sélectionner un fragment**, sélectionnez le fragment de métabalise que vous avez créé au préalable, puis sélectionnez **OK**.
1. Sélectionnez **Terminer la modification**, puis **Publier** pour publier le modèle.

> [!NOTE]
> Si votre site utilise plusieurs modèles, vous devez ajouter le fragment de métabalises à chacun d’eux.

Lorsque vous prévisualisez des pages basées sur le modèle auquel vous avez ajouté le fragment de métabalises, vous devriez maintenant voir l’icône de favori dans l’onglet du navigateur.

## <a name="additional-resources"></a>Ressources supplémentaires

[Ajouter un logo](add-logo.md)

[Sélectionner un thème pour le site](select-site-theme.md)

[Utilisation de fichiers de remplacement CSS](css-override-files.md)

[Ajouter un message de bienvenue](add-welcome-message.md)

[Ajouter un avis de droits d’auteur](add-copyright-notice.md)

[Ajouter des langues à votre site](add-languages-to-site.md)

[Ajout d’un code de script aux pages de site pour prendre en charge la télémétrie](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
