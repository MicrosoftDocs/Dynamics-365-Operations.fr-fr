---
title: Enregistrer, afficher un aperçu et publier une page
description: Cette rubrique décrit comment enregistrer, prévisualiser et publier une page dans Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 593c68e0934fa62d09c64b8d5d681697c3fb053ae6f4641ce2ae3104a03e0fba
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718671"
---
# <a name="save-preview-and-publish-a-page"></a>Enregistrer, afficher un aperçu et publier une page

[!include [banner](includes/banner.md)]

Cette rubrique décrit comment enregistrer, prévisualiser et publier une page dans Microsoft Dynamics 365 Commerce.

## <a name="save-a-page"></a>Enregistrer une page

Pour enregistrer une page, vous devez la faire extraire vers vous et l’ouvrir dans l’éditeur de page. Pour extraire une page, sélectionnez **Modifier** sur la barre de commandes. Après avoir modifié une page, vous devez l’enregistrer immédiatement, afin de s’assurer que vos modifications sont enregistrées.

Lorsque vous enregistrez une page, les modifications sont visibles uniquement à vous. L’opération d’enregistrement est prévue principalement pour enregistrer les modifications tant que la page n’est pas encore prête à être archivée. Lorsque vous avez terminé de modifier la page, nous vous recommandons de l’archiver, de sorte que les modifications deviennent visibles pour d’autres. À ce stade, la page peut également être extraite par d’autres utilisateurs qui doivent la modifier.

## <a name="preview-a-page"></a>Prévisualiser une page

L’outil de création offre deux types de fonctionnalités d’aperçu : le générateur de page visuel, qui est un volet d’aperçu « Tel écrit, tel écran » dans l’éditeur de page, et une fenêtre de prévisualisation distincte.

Lorsque vous utilisez l’éditeur de page, l’aperçu « Tel écrit, tel écran » apparaît dans le volet central. Cet aperçu est automatiquement mis à jour chaque fois que vous enregistrez la page. Vous pouvez également manuellement le mettre à jour en sélectionnant **Actualiser** dans la barre de commande. L’aperçu affiche la page comme les utilisateurs du site la verront, mais les applications d’assistance sont affichées en haut.

Lorsque vous avez terminé de modifier la page, vous souhaitez peut-être la prévisualiser pour voir ce que les clients verront. Pour obtenir un aperçu de la page, sélectionnez **Aperçu** dans la barre de commande. L’aperçu apparaît dans une fenêtre du navigateur séparée. La page dans la fenêtre d’aperçu est affichée comme l’utilisateur du site la verra. Vous pouvez redimensionner la fenêtre pour vous assurer que les modules réactifs sont correctement affichés dans tous les ports d’affichage.

> [!NOTE]
> L’authentification et les autorisations adéquates sont nécessaires pour prévisualiser le contenu non publié en aperçu. Par conséquent, si vous partagez l’URL de l’aperçu avec quelqu’un, cette personne doit disposer des autorisations appropriées pour accéder au contenu.

## <a name="publish-a-page"></a>Publier une page

Lorsque votre page est prête, l’étape suivante consiste à la publier, afin que les utilisateurs externes puissent afficher le contenu. Avant de publier une page, vous devez l’archiver en sélectionnant **Terminer la modification** dans la barre de commandes.

Vous pouvez publier et annuler la publication des pages à partir de l’inspecteur de page ou de l’éditeur de page. L’inspecteur de page affiche une liste des pages et autorise les opérations en bloc. L’éditeur de page permet de publier ou d’annuler la publication uniquement de la page seule qui est ouverte dans celui-ci.

Pour publier une ou plusieurs pages de l’inspecteur de page, sélectionnez les pages, assurez-vous qu’elles soient archivées, puis sélectionnez **Publier** dans la barre de commande. Les pages sont publiées, et vous recevez une notification sur l’opération dans l’outil de création.

Pour publier une seule page dans l’éditeur de page, la procédure est similaire. Lorsque de la page est ouverte dans l’éditeur de page, assurez-vous qu’elle a été archivée, puis sélectionnez **Publier** dans la barre de commande. La page est publiée, et vous recevez une notification sur l’opération.

Lorsque vous publiez une page, tout le contenu de la page s’affiche. Vous et d’autres utilisateurs pouvez accéder à la page et l’afficher uniquement après qu’une URL est associé. URL doit être publié séparément.

> [!IMPORTANT]
> Avant de publier une page, toutes les images ou fragments auxquels la page fait référence doivent déjà être publiées.

## <a name="save-preview-and-publish-a-home-page"></a>Enregistrer, afficher un aperçu et publier une page d’aéccueil

Pour enregistrer, prévisualiser, et publier une page d’accueil, procédez comme suit.

1. Sous **Sites**, sélectionnez **Fabrikam** (ou le nom de votre site).
1. Dans le volet de navigation sur la gauche, sélectionnez **Pages**.
1. Recherchez et sélectionnez la page d’accueil pour l’ouvrir dans l’éditeur de page.
1. Sélectionnez **Modifier**.
1. Modifiez la page comme vous le souhaitez.
1. Sélectionnez **Enregistrer**, puis **Terminer la modification**.
1. Dans le champ **Commentaires**, entrez une note sur les modifications que vous avez effectuées, puis sélectionnez **OK**.
1. Sélectionnez **Aperçu** pour prévisualiser votre page avant impression. Lorsque vous avez terminé, fermez l’onglet d’aperçu pour revenir à l’outil d’édition.
1. Sélectionnez **Publier**.

## <a name="publish-a-url"></a>Publier une URL

Pour publier une URL, procédez comme suit.

1. Sous **Sites**, sélectionnez **Fabrikam** (ou le nom de votre site).
1. Dans le volet de navigation sur la gauche, sélectionnez **URL**.
1. Recherchez et sélectionnez l’URL à publier.
1. Dans la barre de commande, sélectionnez **Publier**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Modifier une page de site existante](modify-existing-page.md)

[Ajouter une nouvelle page de site](add-new-page.md)

[Sélectionner des dispositions de page](select-page-layouts.md)

[Gestion des métadonnées SEO](manage-seo-metadata.md)

[Enrichir une page de produit](enrich-product-page.md)

[Enrichir une page d’arrivée de catégorie](enrich-category-page.md)

[Vérifier l’accessibilité du contenu de la page](verify-accessibility.md)

[Créer des pages e-commerce dynamiques basées sur des paramètres d’URL](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]