---
title: Modules de collecte de produits
description: Cette rubrique fournit une vue d'ensemble des modules de collecte de produits dans Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 44f78b55b8e67b7358be75aa63c40a0147507e26
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785465"
---
# <a name="product-collection-modules"></a>Modules de collecte de produits  

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique fournit une vue d'ensemble des modules de collecte de produits dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

La découverte de produit est un outil principal que les détaillants utilisent pour communiquer avec leurs clients sur un site web de commerce électronique. Les modules de collecte de produits aident les détaillants à générer des expériences d'achat attrayantes en fournissant une interface visuelle intuitive pouvant être utilisée pour créer rapidement des collectes de produits.

Les modules de collecte de produits représentent les produits et services physiques sur le site web. Un module de collecte de produits est généralement lié à une page de détails dans laquelle les clients peuvent acheter un produit ou service, ou en savoir plus. 

Les sources de collecte de produits peuvent être des listes des trois types suivants :

- Les listes éditoriales de produits qui sont définies manuellement dans Dynamics 365 Retail en tant que produits associés pour un produit, ou des listes de produits
- Les listes d'algorithmiques, telles que des listes de produits nouveaux, des meilleures ventes ou les tendances
- Les listes des recommandations qui sont basées sur le Machine Learning

L'illustration suivante présente les différents types de collectes de produits utilisés sur un site de commerce électronique.

![Exemples de différents types de collectez de produits sur un site de commerce électronique](./media/ProductCollectionsAcrossTheSiteUseProductPlacement.png)

> [!NOTE]
> Utilisez toujours les modules de collecte de produits pour afficher un groupe de produits d'un type ou d'un thème similaire.

## <a name="product-collection-modules-and-types"></a>Modules et types de collectes de produits

Le tableau suivant décrit les différents types de modules de collecte de produits dans Dynamics 365 Commerce.

| Module de collecte de produits  | Type | Description |
|----------------------------|------|-------------|
| Parcours de catégories            | Éditorial | Ce type de module de collecte de produits utilise la hiérarchie des catégories de navigation que le détaillant a créé pour un canal de vente au détail pour afficher un flux parcourant les produits proposés dans une catégorie spécifique du site. |
| Résultats de la recherche             | Requête de recherche | Ce type de module de collecte de produits affiche une liste de produits qui correspondent le mieux à la requête de recherche que le client a entrée. |
| Produits associés           | Éditorial | Ce type de module de collecte de produits affiche une liste de produits qu'un responsable de la commercialisation a configurés en tant que produits liés dans la vente au détail, pour le type de relation que l'auteur a sélectionnée. |
| Listes des produits éditées      | Éditorial | Ce type de module de collecte de produits affiche des listes personnalisées que les spécialistes de la commercialisation et les éditeurs ont créées dans la vente au détail. |
| Nouveau                        | Algorithmique | Ce type de module de collecte de produits affiche une liste des produits les plus récents qui ont été mis en correspondance avec les canaux et les catalogues. |
| Meilleures ventes               | Algorithmique | Ce type de module de collecte de produits affiche une liste de produits qui sont classés selon le nombre de ventes le plus élevé. |
| Tendances                   | Algorithmique | Ce type de module de collecte de produits affiche une liste des produits les plus performants pendant une période donnée. |
| Fréquemment achetés ensemble | Intelligence artificielle/Machine Learning | Ce type de module de collecte de produits utilise le Machine Learning pour analyser des modèles d'achat des consommateurs et pour recommander des articles associés qui sont fréquemment achetés avec un produit donné. |
| Les personnes aiment également           | Intelligence artificielle/Machine Learning | Ce type de module de collecte de produits utilise le Machine Learning pour analyser des modèles d'achat des consommateurs et pour recommander des articles associés à un produit donné. |

## <a name="add-a-product-collection-module-to-a-category-page"></a>Ajout d'un module de collecte de produits à une page de catégorie

Pour ajouter un module de collecte de produits à une page de catégorie, procédez comme suit.

1. Dans Dynamics 365 Commerce, accédez à votre site, puis créez une page qui utilise les mêmes modèles que votre page par défaut de catégorie.
1. Dans le contour de page, sélectionnez l'emplacement **Sous-pied de page**, sélectionnez le bouton représentant des points de suspension (**...**), puis le sélectionnez **Ajoutez le module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez **Conteneur**, puis sélectionnez **OK**.
1. Dans le module de conteneur, sélectionnez le bouton représentant des points de suspension, puis sélectionnez **Ajoutez le module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez **Collecte de produit**, puis sélectionnez **OK**.
1. Configuration des paramètres en sélectionnant une source de données appropriée et des entrées pour la collecte de produit.
1. Dans le volet de propriétés du module de collecte de produit, sélectionnez **Ajouter une liste de produit**.
1. Dans la boîte de dialogue **Sélectionner la configuration de liste de produit**, sélectionnez le type de liste, entrez le nombre d'articles, puis sélectionnez tout autre option disponible pour ce type de liste. Pour plus d'informations sur ces types de listes, voir le tableau suivant. 
1. Cliquez sur **OK**.
1. Enregistrez la page, et archivez-la.

Le tableau suivant indique les types de listes disponibles pour la sélection dans la boîte de dialogue **Sélectionner la configuration de liste de produit**.
   
| Type                       | Description | Pratique générale | Contexte qui peut être dérivé du contexte de page | Contexte avec lequel l'auteur peut remplacer le contexte de page |
|----------------------------|-------------|------------------|-------------------------------------|-----------------------------------------------|
| Produits par catégorie       | Liste des produits appartenant à une catégorie donnée. Cette catégorie est déterminée par le contexte de page ou le contexte que l'auteur fournit. | Enrichir la page de catégorie, la page d'accueil, les pages de caisse et de panier, et les pages de produit | Catégorie | Catégorie déterminée par l'auteur |
| Produits associés           | Liste des produits qu'un responsable de la commercialisation a configurés en tant que produits liés dans la vente au détail pour le type de relation. | Pages de produits, pages de caisse et de panier, page de liste de souhaits et page de compte client | Produit, type de relation (obligatoire)  | Produit, type de relation |
| Organisé                    | Liste personnalisées que les commercialisateurs et les éditeurs ont créée dans la vente au détail. | Enrichir la page de catégorie, la page d'accueil, les pages de caisse et de panier, et les pages de produit | Non applicable | Sélecteur de liste |
| Algorithmique                | <ul><li>**Nouveau** – Liste des nouveaux produits qui ont été mis en correspondance avec les canaux et les catalogues.</li><li>**Meilleures ventes** – Liste des produits qui sont classés selon le nombre de ventes le plus élevé.</li><li>**Tendance** – Liste des produits les plus performances pendant une période donnée.</li></ul> | Page d'accueil, enrichir la page de catégorie, et les pages de caisse et de panier | Catégorie | Catégorie déterminée par l'auteur |
| Fréquemment achetés ensemble | Liste qui utilise le Machine Learning pour analyser des modèles d'achat des consommateurs et pour recommander des articles associés qui sont fréquemment achetés avec un produit donné. | Pages de produits, et pages de caisse et de panier | Produit, panier | Inclure le panier |
| Les personnes aiment également           | Liste qui utilise le Machine Learning pour analyser des modèles d'achat des consommateurs et pour recommander des articles associés à produit donné. | Pages de produits, et pages de caisse et de panier | Produit, panier | Non applicable |

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du kit de démarrage](starter-kit-overview.md)

[Module Carrousel](add-carousel.md)

[Module de bloc de contenu riche](add-content-rich-block.md)

[Module Placement de contenu](add-content-placement-modules.md)

[Module Container](add-container-module.md)

[Module Zone d'achat](add-buy-box.md)

