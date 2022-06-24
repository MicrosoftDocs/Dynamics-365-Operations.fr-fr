---
title: Télécharger et diffuser des fichiers statiques
description: Cet article décrit comment charger un fichier statique dans le générateur de site Microsoft Dynamics 365 Commerce et comment créer une URL et un nom de fichier personnalisés pouvant être utilisés pour demander ce fichier.
author: StuHarg
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: a1b14feba1466c3a5efc3b0ea66f20e9e818a8a5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885320"
---
# <a name="upload-and-serve-static-files"></a>Télécharger et diffuser des fichiers statiques

[!include [banner](includes/banner.md)]

Cet article décrit comment charger un fichier statique dans le générateur de site Microsoft Dynamics 365 Commerce et comment créer une URL et un nom de fichier personnalisés pouvant être utilisés pour demander ce fichier.

Certains connecteurs tiers nécessitent qu’un fichier soit hébergé et diffusé à partir du site d’e-commerce. Ces connecteurs s’attendent à ce que le fichier soit renvoyé par des requêtes adressées à un chemin d’URL de rappel et à un nom de fichier spécifiques. Par conséquent, cet article explique comment charger et diffuser un fichier statique qui a une URL et un nom de fichier définissables par l’utilisateur sur un site d’e-commerce Dynamics 365 Commerce.

## <a name="create-a-site-url-that-returns-a-static-file"></a>Créer une URL de site qui renvoie un fichier statique

Pour créer une URL de site qui renvoie un fichier statique dans le générateur de site Commerce, procédez comme suit.

1. Accédez à la médiathèque de votre site et chargez le fichier qui doit être servi par les requêtes à l’URL que vous définirez. Si vous avez déjà chargé le fichier, vous pouvez ignorer cette étape.
1. Aller à **URL** pour votre site.
1. Sélectionnez **Nouveau \> Nouvelle URL**.
1. Dans la boîte de dialogue **Nouvelle URL**, sélectionnez **Élément de bibliothèque multimédia**.
1. Dans le champ **Chemin de l’URL**, entrez le chemin de l’URL. Incluez le nom du fichier dans le chemin.
1. Sélectionnez **Suivant**. La médiathèque s’ouvre et affiche tous les éléments multimédias de type **document** qui ont été chargés.
1. Sélectionnez le fichier qui doit être servi pour les demandes à l’URL que vous avez définie à l’étape 5.
1. Sélectionnez **Enregistrer**.

À ce stade, l’URL créée est dans un état de brouillon. Le fichier vers lequel pointe l’URL ne sera pas renvoyé tant que vous n’aurez pas publié l’URL. Avant de publier l’URL, vous pouvez valider qu’elle renvoie les données correctes.

## <a name="validate-and-publish-a-url"></a>Validation et publication d’une URL

Pour valider une URL avant de la oublier, procédez comme suit.

1. Aller à **URL** pour votre site et sélectionnez l’URL à prévisualiser.
2. Dans le volet des propriétés à droite, sous le bouton **Modifier**, sélectionnez le lien URL correct. Une nouvelle fenêtre de navigateur s’ouvre et vous devriez recevoir une erreur 404.
3. Ajouter la chaîne de requête **?preview=inprogress** à l’URL (par exemple, `https://yoursite.com/callback.html?preview=inprogress`) et rechargez la page. Le fichier que vous avez chargé dans la médiathèque doit être renvoyé dans la réponse.

Après avoir validé l’URL, vous pouvez la publier.

1. Aller à **URL** pour votre site et sélectionnez l’URL.
2. Sélectionnez **Publier** dans la barre de commande.

## <a name="update-the-file-that-a-url-points-to"></a>Mettre à jour le fichier vers lequel pointe une URL

Une fois l’URL publiée, vous pouvez la mettre à jour afin qu’elle pointe vers un autre fichier. Vous pouvez également mettre à jour l’URL afin qu’elle pointe vers un autre type de ressource, comme décrit dans la section suivante. Par exemple, vous pouvez pointer l’URL vers une page interne ou une redirection.

Pour mettre à jour le fichier vers lequel pointe une URL, procédez comme suit.

1. Aller à **URL** pour votre site et sélectionnez l’URL à mettre à jour.
1. Dans le volet de propriétés de droite, sélectionnez **Modifier**.
1. Sous **Attribution d’URL**, sélectionnez la zone **Étape 2**, puis sélectionnez un nouveau document dans la bibliothèque multimédia.
1. Sélectionnez **Appliquer**.

## <a name="update-the-asset-type-that-a-url-points-to"></a>Mettre à jour le type d’actif vers lequel pointe une URL

Vous pouvez également mettre à jour une URL afin qu’elle pointe vers un autre type d’actif (ressource), tel qu’une page interne ou une redirection.

Pour mettre à jour le type d’actif vers lequel pointe une URL, procédez comme suit.

1. Aller à **URL** pour votre site et sélectionnez l’URL à mettre à jour.
1. Dans le volet de propriétés de droite, sélectionnez **Modifier**.
1. Sous **Attribution d’URL**, sous **Étape 1**, sélectionnez un autre type d’actif.
1. Sélectionnez la zone **Étape 2**, puis sélectionnez le nouvel actif.
1. Sélectionnez **Appliquer**.

## <a name="change-the-url-path"></a>Changer le chemin de l’URL

Une fois l’URL créée, son chemin ne peut pas être modifié. Si vous devez modifier le chemin d’URL qui sert un fichier ou tout autre type de ressource, vous devez créer une URL, la mapper au fichier existant ou à une autre ressource, puis annuler la publication et supprimer l’ancienne URL.

Pour modifier le chemin de l’URL, procédez comme suit.

1. Pour créer une URL et la mapper au fichier existant ou à une autre ressource, suivez les instructions de la section précédente [Créer une URL de site qui renvoie un fichier statique](#create-a-site-url-that-returns-a-static-file) dans cet article.
1. Sélectionnez la nouvelle URL, puis sélectionnez **Publier** sur la barre de commandes. La nouvelle URL est publiée.
1. Pour annuler la publication de l’ancienne URL, sélectionnez-la, puis sélectionnez **Annuler la publication** sur la barre de commandes. Vous pouvez à présent supprimer l’ancienne URL si nécessaire.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la gestion des actifs numériques](dam-overview.md)

[Importer des images](dam-upload-images.md)

[Télécharger des vidéos](dam-upload-video.md)

[Télécharger des fichiers autres que des images et des vidéos](dam-upload-files.md)

[Rogner les images](dam-crop-images.md)

[Personnaliser les points focaux de l’image](dam-custom-focal-point.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]