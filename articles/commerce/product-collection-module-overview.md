---
title: Modules de collecte de produits
description: Cette rubrique fournit une vue d'ensemble des modules de collecte de produits dans Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 01/07/2020
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
ms.openlocfilehash: 31307035014f2fae6146f33bc23e3e06103f82eb
ms.sourcegitcommit: c237123ad94d9418994ac095fbd8634c05a927b1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "2943261"
---
# <a name="product-collection-modules"></a>Modules de collecte de produits

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique fournit une vue d'ensemble des modules de collecte de produits dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

La découverte de produit est un outil principal que les détaillants utilisent pour communiquer avec leurs clients sur un site web de commerce électronique. Les modules de collecte de produits aident les détaillants à générer des expériences d'achat attrayantes en fournissant une interface visuelle intuitive pouvant être utilisée pour créer rapidement des collectes de produits.

Les modules de collecte de produits représentent les produits et services physiques sur le site web. Un module de collecte de produits est généralement lié à une page de détails dans laquelle les clients peuvent acheter un produit ou service, ou en savoir plus. 

Les sources de collecte de produits peuvent être des listes des quatre types suivants :

- Les listes éditoriales de produits qui sont définies manuellement dans Dynamics 365 Retail en tant que produits associés pour un produit, ou des listes de produits
- Les listes d'algorithmiques, telles que des listes de produits nouveaux, des meilleures ventes ou les tendances
- Les listes des recommandations qui sont basées sur le Machine Learning
- Listes de personnalisations qui prennent en charge des résultats personnalisés pour un client. Les clients doivent être connectés au site de commerce électronique pour voir des résultats personnalisés. Les utilisateurs invités ne voient pas de résultats personnalisés. Les clients peuvent désactiver la personnalisation à partir de la [page de gestion de compte](account-management.md).

L'illustration suivante présente les différents types de collectes de produits utilisés sur un site de commerce électronique.

![Exemples de différents types de collectez de produits sur un site de commerce électronique](./media/ProductCollectionsAcrossTheSiteUseProductPlacement.png)

> [!NOTE]
> Utilisez toujours les modules de collecte de produits pour afficher un groupe de produits d'un type similaire.

## <a name="product-collection-modules-and-types"></a>Modules et types de collectes de produits

Le tableau suivant décrit les différents types de modules de collecte de produits dans Dynamics 365 Commerce.

| Module de collecte de produits  | Type | Description |
|----------------------------|------|-------------|
| Catégorie                   | Catégorie | Ce module affiche une liste de produits dans une catégorie, telle que définie par la hiérarchie de catégories de navigation que le détaillant a créée pour un canal de vente au détail. |
| Produits associés           | Éditorial | Ce module affiche une liste de produits qu'un responsable de la commercialisation a configurés en tant que produits liés dans la vente au détail, pour le type de relation que l'auteur a sélectionnée. |
| Listes des produits éditées      | Éditorial | Ce module affiche des listes personnalisées que les spécialistes de la commercialisation et les éditeurs ont créée dans la vente au détail. |
| Nouveau                        | Algorithmique | Ce module affiche une liste des nouveaux produits qui ont été mis en correspondance avec les canaux et les catalogues. Cette liste peut afficher des résultats personnalisés pour un utilisateur connecté si l'auteur du site choisit cette option. |
| Meilleures ventes               | Algorithmique | Ce module affiche une liste des produits qui sont classés selon le nombre de ventes le plus élevé. Cette liste peut afficher des résultats personnalisés pour un utilisateur connecté si l'auteur du site choisit cette option. |
| Tendances                   | Algorithmique | Ce module affiche une liste des produits les plus performances pendant une période donnée. Cette liste peut afficher des résultats personnalisés pour un utilisateur connecté si l'auteur du site choisit cette option. |
| Fréquemment achetés ensemble | Intelligence artificielle/Machine Learning | Ce module utilise le Machine Learning pour analyser des modèles d'achat des consommateurs et pour recommander des articles associés qui sont fréquemment achetés avec un produit donné. Cette liste peut afficher des résultats personnalisés pour un utilisateur connecté si l'auteur du site choisit cette option. |
| Les personnes aiment également           | Intelligence artificielle/Machine Learning | Ce module utilise le Machine Learning pour analyser des modèles d'achat des consommateurs et pour recommander des articles associés à produit donné. Cette liste peut afficher des résultats personnalisés pour un utilisateur connecté si l'auteur du site choisit cette option. |
| Nos choix pour vous              | Intelligence artificielle/Machine Learning | Ce module utilise le Machine Learning pour analyser les modèles d'achat de l'utilisateur connecté et fournir des recommandations personnalisées basées sur ces modèles d'achat. Pour un utilisateur invité, cette liste sera réduite. |

## <a name="add-a-product-collection-module-to-a-category-page"></a>Ajout d'un module de collecte de produits à une page de catégorie

Pour ajouter un module de collecte de produits à une page de catégorie, procédez comme suit.

1. Dans Dynamics 365 Commerce, accédez à votre site, puis créez une page qui utilise les mêmes modèles que votre page par défaut de catégorie.
1. Dans le contour de page, sélectionnez l'emplacement **Sous-pied de page**, sélectionnez le bouton représentant des points de suspension (**...**), puis le sélectionnez **Ajoutez le module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez **Conteneur**, puis sélectionnez **OK**.
1. Dans le module de conteneur, sélectionnez le bouton représentant des points de suspension, puis sélectionnez **Ajoutez le module**.
1. Dans la boîte de dialogue **Ajouter un module**, sélectionnez **Collecte de produit**, puis sélectionnez **OK**.  
![Exemple de flux de l'Assistant Module de collecte de produits](./media/productCollectionModule.png)
1. Configuration des paramètres en sélectionnant une source de données appropriée et des entrées pour la collecte de produit.
1. Dans le volet de propriétés du module de collecte de produit, sélectionnez **Ajouter une liste de produit**.
1. Dans la boîte de dialogue **Sélectionner la configuration de liste de produit**, sélectionnez le type de liste, entrez le nombre d'articles, puis sélectionnez tout autre option disponible pour ce type de liste. Pour plus d'informations sur ces types de listes, voir le tableau suivant. 
1. Cliquez sur **OK**.
1. Enregistrez la page, et archivez-la.

Le tableau suivant indique les types de listes disponibles pour la sélection dans la boîte de dialogue **Sélectionner la configuration de liste de produit**.

| Type                       | Description | Utilisation | Contexte de la page | Contexte spécifique | Personnalisation |
|----------------------------|-------------|-------|--------------|------------------|-----------------|
| Produits par catégorie       | Liste des produits appartenant à une catégorie donnée. Cette catégorie est déterminée par le contexte de page ou le contexte que l'auteur fournit. | Ce type de liste peut être utilisé sur n'importe quelle page (par exemple, une page d'accueil, une page de catégorie, une page de marketing ou une page de détails de produit \[PDP\]) pour promouvoir une catégorie spécifique de produits. | Catégorie à partir du contexte de la page, le cas échéant (par exemple, une page de catégorie) | L'auteur peut fournir une catégorie spécifique comme contexte pour la liste. | Non applicable |
| Produits associés           | Liste des produits qu'un responsable de la commercialisation a configurés en tant que produits liés pour le type de relation dans la vente au détail. | Ce type de liste est utilisé principalement sur les PDP, mais il peut être utilisé sur n'importe quelle page si un produit parent est fourni. | Produit de la page, type de relation (obligatoire) | Le produit peut être sélectionné dans le sélecteur et le type de relation est utilisé. | Non applicable |
| Organisé                    | Liste personnalisées que les commercialisateurs et les éditeurs ont créée dans la vente au détail. | Enrichir la page de catégorie, la page d'accueil, les pages de caisse et de panier, et les pages de produit | Non applicable | Non applicable | Non applicable |
| Algorithmique                | <ul><li>**Nouveau** – Liste des nouveaux produits qui ont été mis en correspondance avec les canaux et les catalogues.</li><li>**Meilleures ventes** – Liste des produits qui sont classés selon le nombre de ventes le plus élevé.</li><li>**Tendance** – Liste des produits les plus performances pendant une période donnée.</li></ul> | Page d'accueil, enrichir la page de catégorie, et les pages de caisse et de panier | Catégorie à partir du contexte de la page (par exemple, une page de catégorie) | Catégorie déterminée par l'auteur du site | Prise en charge |
| Fréquemment achetés ensemble | Liste qui utilise le Machine Learning pour analyser des modèles d'achat des consommateurs et pour recommander des articles associés qui sont fréquemment achetés avec un produit donné. | Ce type de liste ne s'applique qu'à la page du panier. | Chariot | Non applicable | Prise en charge |
| Les personnes aiment également           | Liste qui utilise le Machine Learning pour analyser des modèles d'achat des consommateurs et pour recommander des articles associés à produit donné. | Ce type de liste est utilisé sur les PDP pour montrer les produits que d'autres clients ont achetés. | Contexte du produit à partir de la page | Produit fourni par l'auteur du site | Prise en charge |
| Nos choix pour vous              | Liste qui utilise le Machine Lerning pour déterminer les préférences des clients. | Ce type de liste peut être utilisé sur n'importe quelle page. | Non applicable| Non applicable | Prise en charge | 

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble du kit de démarrage](starter-kit-overview.md)

[Module de carrousel](add-carousel.md)

[Module de bloc de contenu enrichi](add-content-rich-block.md)

[Module de placement de contenu](add-content-placement-modules.md)

[Module Container](add-container-module.md)

[Module de zone d'achat](add-buy-box.md)

[Vue d'ensemble des recommandations produit](product-recommendations.md)
