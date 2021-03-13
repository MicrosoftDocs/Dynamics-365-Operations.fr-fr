---
title: Enrichir une page de produit
description: Cette rubrique décrit comment enrichir une page de produit dans Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: fcb8eda188a6796282a7a800b87a68dfef9d7d62
ms.sourcegitcommit: 872600103d2a444d78963867e5e0cdc62e68c3ec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2021
ms.locfileid: "5097336"
---
# <a name="enrich-a-product-page"></a>Enrichir une page de produit


[!include [banner](includes/banner.md)]

Cette rubrique décrit comment enrichir une page de produit dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Par défaut, votre site utilise une page générique pour afficher les données de produit. Cette page inclut des informations de base sur le produit et les contrôles qui sont requis pour le vendre. Toutefois, vous pouvez compléter les informations provenant de l'unité d'échelle commerciale avec des images ou du texte supplémentaire pour un produit spécifique. Ce processus est identifié comme un enrichissement de la page de produit.

Dans de nombreux cas, vous souhaiterez utiliser du contenu supplémentaire spécifique pour vos produits. Lorsque vous accédez à **Commerce et vente au détail** dans l'outil de création, vous obtenez une liste des produits du canal affecté au site. Dans cette liste, la colonne **Enrichi** indique si la page de produit pour un produit a été enrichie. Si une coche apparaît dans la colonne, une page enrichie de produit existe pour le produit. Si aucun coche ne s'affiche, la page et le contenu par défaut du produit sont utilisés pour le produit. Vous pouvez prévisualiser les pages de produits enrichies et non enrichies en sélectionnant un nom de produit dans la liste.

## <a name="enrich-a-product-page"></a>Enrichir une page de produit

Pour enrichir une page de produit, procédez comme suit.

1. Sous **Sites**, sélectionnez **Fabrikam** (ou le nom de votre site).
1. Dans le volet de navigation sur la gauche, sélectionnez **Produits**.
1. Sélectionnez tout produit qui n'a pas de page de produit enrichie.
1. Dans le volet Actions, sélectionnez **Page de produit enrichie**.
1. Sélectionnez **Modèle PDF**, puis sélectionnez **OK**.
1. Dans l'arborescence d'ensemble de page à gauche, développez l'emplacement **Principal**.
1. Sélectionnez le bouton représentant des points de suspension (**...**) en regard de l'emplacement **Principale**, et sélectionnez **Ajouter un module**.
1. Sélectionnez **Conteneur 2**, puis sélectionnez **OK**.
1. Sélectionnez le bouton représentant des points de suspension pour **Conteneur 2**, puis sélectionnez **Ajouter un module**.
1. Sélectionnez **Fonctionnalité**, puis sélectionnez **OK**.
1. Dans le volet de propriétés de droite, dans le champ **Texte enrichi**, entrez la description mise à jour du produit.
1. Dans le champ **En-tête**, entrez le texte d'en-tête, puis sélectionnez **OK**.
1. Sélectionnez **Enregistrer**, puis **Terminer la modification**.
1. Dans le champ **Commentaires**, entrez **A enrichi un produit**, puis sélectionnez **OK**.
1. Sélectionnez **Aperçu** pour afficher un aperçu de la page de produit enrichie. Lorsque vous avez terminé, fermez l'onglet d'aperçu pour revenir à l'outil d'édition.
1. Sélectionnez **Publier**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Modifier une page de site existante](modify-existing-page.md)

[Ajouter une nouvelle page de site](add-new-page.md)

[Sélectionner des dispositions de page](select-page-layouts.md)

[Gestion des métadonnées SEO](manage-seo-metadata.md)

[Enregistrer, afficher un aperçu et publier une page](save-preview-publish-page.md)

[Enrichir une page d’arrivée de catégorie](enrich-category-page.md)

[Vérifier l’accessibilité du contenu de la page](verify-accessibility.md)

[Créer des pages e-commerce dynamiques basées sur des paramètres d'URL](create-dynamic-pages.md)
