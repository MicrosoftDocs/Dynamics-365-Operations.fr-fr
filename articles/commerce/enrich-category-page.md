---
title: Enrichir une page d’arrivée de catégorie
description: Cette rubrique couvre l’enrichissement des pages de catégorie dans Dynamics 365 Commerce.
author: v-chgri
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5bb28c3b5fbb1133d32219b9c47dd1477ae2ac982ee035321dafd77c53dc910b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6771005"
---
# <a name="enrich-a-category-landing-page"></a>Enrichir une page d’arrivée de catégorie

[!include [banner](includes/banner.md)]

Cette rubrique couvre l’enrichissement des pages de catégorie dans Dynamics 365 Commerce.

Commerce fournit une page de destination de catégorie par défaut utilisée lorsque les données de catégorie sont affichées. Une page de catégorie par défaut contient des éléments nécessaires, comme les raffineurs, le placement de produit catégorisé, les options de tri, une synthèse des choix, et des contrôles pagination. 

Toutefois, au lieu d’utiliser la page par défaut de catégorie, vous pouvez utiliser une page de destination de catégorie « enrichie » avec plus de contenu et autres éléments spécifiques. Un enrichissement standard pourrait impliquer d’ajouter du contenu marketing spécifique à la catégorie sur la page de catégorie. Ce contenu peut inclure un placement de produit entre les catégories à des fins de vente croisée, listes éditoriales, images, vidéos, et autre texte. Vous pouvez modifier la page par défaut de catégorie ou définir une autre page de catégorie pour une catégorie spécifique.

![Page d’arrivée de catégorie enrichie.](./media/CategoryLandingPages.png)

Dans le générateur de site Commerce, la page **Produits** inclut une liste de catégories du canal qui sont affectées au site. Si le statut **Enrichi** est sélectionné pour une page de catégorie, cette page de catégorie a été enrichie. Sinon, la page de catégorie et le contenu par défaut sont utilisés pour la catégorie. Vous pouvez prévisualiser les pages de catégorie enrichies et non enrichies pour une catégorie en sélectionnant le nom de la catégorie.

Pour enrichir une page de catégorie, procédez comme suit.

1. Dans la page **Produits**, sélectionnez le nom de la catégorie pour laquelle vous souhaitez enrichir la page de catégorie. La page de catégorie par défaut pour la catégorie sélectionnée est ouverte dans l’éditeur de page.
2. Sélectionnez **Enrichir la page de catégorie**.
3. Sélectionnez un modèle pour la page de catégorie enrichie. Si vous n’apportez que de petites modifications, vous pouvez sélectionner la page par défaut de catégorie. Sinon, vous pouvez sélectionner un modèle spécifique de la page de catégorie. Lorsque vous sélectionnez le modèle, l’éditeur de page est ouvert, et le modèle sélectionné permet de créer une page de catégorie pour la catégorie sélectionnée. La page est extraite pour vous, et vous pouvez désormais effectuer vos modifications.

> [!NOTE]
> Les modules qui utilisent des données de spécification de catégorie utilisent les données de votre catégorie sélectionnée. Les paramètres du modèle que vous sélectionnez détermine les modifications que vous pouvez apporter.

## <a name="additional-resources"></a>Ressources supplémentaires

[Modifier une page de site existante](modify-existing-page.md)

[Ajouter une nouvelle page de site](add-new-page.md)

[Sélectionner des dispositions de page](select-page-layouts.md)

[Gestion des métadonnées SEO](manage-seo-metadata.md)

[Enregistrer, afficher un aperçu et publier une page](save-preview-publish-page.md)

[Enrichir une page de produit](enrich-product-page.md)

[Vérifier l’accessibilité du contenu de la page](verify-accessibility.md)

[Créer des pages e-commerce dynamiques basées sur des paramètres d’URL](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
