---
title: Ajouter une nouvelle page de site
description: Cet article décrit comment ajouter une nouvelle page du site dans Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 02/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: f6714463c9d5dc844b03f78f0f6ff60c5f270da3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270316"
---
# <a name="add-a-new-site-page"></a>Ajouter une nouvelle page de site

[!include [banner](includes/banner.md)]

Cet article décrit comment ajouter une nouvelle page du site dans Microsoft Dynamics 365 Commerce.

Après avoir créé des modèles et des fragments pour votre site, l’étape suivante consiste à commencer à créer des pages qui les utilisent. Pour démarrer, vous devez sélectionner un modèle ou une disposition, un nom de page, et une URL de page.

## <a name="template-or-layout"></a>Modèle ou disposition

Vous pouvez utiliser un modèle ou une disposition pour votre nouvelle page. Pour plus d’informations, voir [Vue d’ensemble des modèles et des dispositions](templates-layouts-overview.md).

## <a name="specify-the-page-name"></a>Préciser le nom de la page

Le nom de la page doit être propre à votre site et descriptif, afin que vous puissiez facilement la trouver et que d’autres personnes sachent pour quoi la page est prévue. Vous pouvez renommer votre page ultérieurement en la modifiant, puis en sélectionnant le symbole du stylo à côté du nom de la page dans le volet des propriétés.

## <a name="specify-the-page-url"></a>Préciser l’URL de la page

Vous pouvez avoir l’option d’entrer une URL pour votre nouvelle page. Lorsque vous créez une page, vous pouvez entrer une chaîne à utiliser pour former une URL complète. Cette chaîne s’appelle URL relative ou URL slug. Une URL complète est ensuite générée selon le slug d’URL, et la nouvelle page lui est affectée. Vous pouvez modifier le slug URL ultérieurement, avant la publication de la page. Pour plus d’informations, voir [Création d’une URL de page](create-page-URL.md).

> [!NOTE]
> Dynamics 365 Commerce découple les URL et le contenu. En d’autres termes, vous pouvez créer une page qui n’est pas associée à une URL, et une URL peut être créée qui n’est pas associé à une page. Par conséquent, l’échange de contenu peut être effectuée pour une URL et n’a pas besoin d’interruption, et les redirections sont plus facile à gérer.

## <a name="add-a-new-page"></a>Ajouter une nouvelle page

Pour ajouter une nouvelle page de site à votre site, procédez comme suit.

1. Sous **Sites**, sélectionnez **Fabrikam** (ou le nom de votre site).
1. Sélectionnez **Nouvelle page**.
1. Dans la boîte de dialogue **Nouvelle page**, sélectionnez un modèle, puis sélectionnez **OK**.
1. Dans le champ **Nom de la page**, entrez un nom de page (par exemple, **Ma nouvelle page**).
1. Dans le champ **URL**, entrez une chaîne (slug d’URL) pour terminer l’URL (par exemple, **manouvellepage**).
1. Cliquez sur **OK**. L’éditeur de page s’affiche. Notez qu’un en-tête ou un pied de page sont automatiquement ajoutés à la page, selon le modèle sélectionné.
1. Dans le contour de page, sélectionnez l’emplacement **Principal**, sélectionnez le bouton représentant des points de suspension (**...**), puis le sélectionnez **Ajoutez le module**.
1. Sélectionnez **Conteneur**, puis sélectionnez **OK**
1. Sélectionnez **Conteneur fluide**, sélectionnez le bouton représentant des points de suspension, puis sélectionnez **Ajoutez le module**.
1. Sélectionnez **Bloc de contenu riche**, puis sélectionnez **Ajouter**.
1. Sélectionnez **Bloc de contenu riche**, sélectionnez le bouton représentant des points de suspension, puis sélectionnez **Ajoutez le module**.
1. Sélectionnez **Article de bloc de contenu riche**, puis sélectionnez **Ajouter**.
1. Dans le volet des propriétés de droite, sélectionnez **Paragraphe**, puis, dans le champ, **Mon texte de test**.
1. Sélectionnez **Enregistrer**, puis **Terminer la modification**.
1. Dans le champ **Commentaires**, entrez **Nouvelle page ajoutée**, puis sélectionnez **OK**.
1. Sélectionnez **Aperçu** pour prévisualiser votre page avant impression. Lorsque vous avez terminé, fermez l’onglet d’aperçu pour revenir à l’outil d’édition.
1. Sélectionnez **Publier**.
1. Dans le chemin de navigation (barres de navigation), sélectionnez **Fabrikam** (ou le nom de votre site).
1. Dans le volet de navigation sur la gauche, sélectionnez **URL**.
1. Recherchez et sélectionnez votre URL (**manouvellepage**) dans la liste.
1. Sélectionnez **Publier**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Modifier une page de site existante](modify-existing-page.md)

[Sélectionner des dispositions de page](select-page-layouts.md)

[Gestion des métadonnées SEO](manage-seo-metadata.md)

[Enregistrer, afficher un aperçu et publier une page](save-preview-publish-page.md)

[Enrichir une page de produit](enrich-product-page.md)

[Enrichir une page d’arrivée de catégorie](enrich-category-page.md)

[Vérifier l’accessibilité du contenu de la page](verify-accessibility.md)

[Créer des pages e-commerce dynamiques basées sur des paramètres d’URL](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
