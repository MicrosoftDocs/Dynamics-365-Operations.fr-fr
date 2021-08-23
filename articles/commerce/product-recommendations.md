---
title: Vue d’ensemble des recommandations produit
description: Cette rubrique fournit des informations générales sur les recommandations de produit. Les recommandations de produit permettent aux clients de rechercher facilement et rapidement les produits qu’ils souhaitent, et même les produits qu’il n’ont pas initialement prévu à acheter.
author: Moonma
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: moonma
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 667c26a8ab7665f9eb1e2cc91217338fc0eb00d6c9c21ba7b4a7e5a203e41410
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6763762"
---
# <a name="product-recommendations-overview"></a>Vue d’ensemble des recommandations produit

[!include [banner](includes/banner.md)]

Microsoft Dynamics 365 Commerce peut être utilisé pour afficher les recommandations de produit sur le site web d’e-Commerce et l’appareil du point de vente (PDV). Les recommandations de produit sont des articles qu’un client peut être intéressé dans. Les recommandations sont basés sur les tendances d’achat d’autres clients dans les magasins en ligne et traditionnels.

Les recommandations de produit permettent aux clients de rechercher facilement et rapidement les produits qu’ils souhaitent tout en ayant une expérience qui les sert bien. La vente croisée et la vente incitative peuvent même être utilisées pour aider les clients à trouver des produits supplémentaires qu’ils n’avaient pas initialement prévu à acheter. Lorsque des recommandations sont utilisées pour aider à la découverte de produit, elles peuvent créer des opportunités de conversion supplémentaires, aider à augmenter le produit des ventes, et même à améliorer la satisfaction la rétention des clients.

Dans e-Commerce, les recommandations de produit sont optimisées par les technologies de Machine Learning de recommandations Microsoft à une grande échelle.

Ce service est un complément à Dynamics 365 Commerce. Pour plus d’informations, téléchargez le dernier [Guide des licences Microsoft Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).


## <a name="recommendation-service"></a>Service de recommandation

Le service de recommandations des produits utilise les technologies d’intelligence artificielle et d’apprentissage automatique (AI-ML) de la manière suivante :

- Les données au format requis par le service de recommandation sont extraites de la base de données opérationnelle de Commerce et envoyées à Azure Data Lake Storage ou au magasin Entité.
- Le service de recommandations utilise les données stockées pour former des modèles de recommandation pour les listes **D’autres client aiment également**, **Fréquemment achetés ensemble**, **Nouveau**, **Meilleure vente**, et **Tendance**.

## <a name="scenarios"></a>Scénarios

Les recommandations de produit sont disponibles pour les scénarios suivants :

- **Sur n’importe quelle page de magasin pour naviguer ou page de destination dans le commerce électronique :** Si les clients ou les vendeurs visitent une page de magasin, le moteur de recommandations peut proposer des produits dans les listes **Nouveau**, **Meilleure vente**, et **Tendance**.
- **Sur la page de détails de produit :** Si les clients ou les vendeurs visitent une page **Détails de produit**, le moteur de recommandations suggère des articles supplémentaires qui sont susceptibles d’être achetés. Ces articles figurent dans la liste **D’autres clients aiment également**.
- **Sur la page de transaction ou la page d’extraction :** Le moteur de recommandations suggère des articles, selon la liste entière d’articles dans le panier. Ces articles figurent dans la liste **Fréquemment achetés ensemble**.
- **Recommandations personnalisées :** les spécialistes du marketing peuvent fournir aux clients connectés une liste personnalisée **Nos choix pour vous**, en plus des nouvelles fonctionnalités qui permettent de personnaliser les scénarios de liste existants en fonction du client. Pour en savoir plus, voir [Activer les recommandations personnalisées.](personalized-recommendations.md).

### <a name="types-of-product-recommendations"></a>Types de recommandations produit

Le tableau suivant décrit les différents types de recommandations de produits automatisés disponibles pour les détaillants à mettre en œuvre dans leur solution Dynamics 365 Commerce via le [module de collecte de produits](product-collection-module-overview.md). Les détaillants peuvent également afficher des résultats personnalisés pour un utilisateur connecté si l’auteur du site choisit cette option.

| Module de collecte de produits  | Type | Description |
|----------------------------|------|-------------|
| Nouveau                        | Algorithmique | Ce module affiche une liste des nouveaux produits qui ont été mis en correspondance récemment avec les canaux et les catalogues. |
| Meilleures ventes               | Algorithmique | Ce module affiche une liste des produits qui sont classés selon le nombre de ventes le plus élevé. |
| Tendances                   | Algorithmique | Ce module affiche une liste des produits les plus performants pendant une période donnée, classés selon le plus grand nombre de ventes.  |
| Fréquemment achetés ensemble | AI-ML | Ce module recommande une liste de produits qui sont couramment achetés avec le contenu du panier actuel du consommateur. |
| Les personnes aiment également           | AI-ML | Ce module recommande des produits pour un produit initial donné en fonction des habitudes d’achat des consommateurs. |
| Nos choix pour vous              | AI-ML | Ce module recommande une liste personnalisée de produits en fonction des modèles d’achat de l’utilisateur connecté. Pour un utilisateur invité, cette liste sera réduite. |

## <a name="additional-resources"></a>Ressources supplémentaires

[Activer Azure Data Lake Storage dans un environnement Dynamics 365 Commerce](enable-adls-environment.md)

[Activer les recommandations produit](enable-product-recommendations.md)

[Activer les recommandations personnalisées](personalized-recommendations.md)

[Désactiver les recommandations personnalisées](personalization-gdpr.md)

[Activer les recommandations « acheter des aspects similaires »](shop-similar-looks.md)

[Ajouter des recommandations produit sur PDV](product.md)

[Ajouter des recommandations à l’écran de transaction](add-recommendations-control-pos-screen.md)

[Ajuster des résultats des recommandations AI-ML](modify-product-recommendation-results.md)

[Créer manuellement des recommandations sélectionnées](create-editorial-recommendation-lists.md)

[Créer des recommandations avec des données de démonstration](product-recommendations-demo-data.md)

[FAQ sur les recommandations produit](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
