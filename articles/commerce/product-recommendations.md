---
title: Vue d'ensemble des recommandations produit
description: Cette rubrique fournit des informations générales sur les recommandations de produit. Les recommandations de produit permettent aux clients de rechercher facilement et rapidement les produits qu'ils souhaitent, et même les produits qu'il n'ont pas initialement prévu à acheter.
author: Moonma
manager: AnnBe
ms.date: 10/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: moonma
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: eb369e6d1356ba13a2310d523b671ac57b9642bf
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770044"
---
# <a name="product-recommendations-overview"></a>Vue d'ensemble des recommandations produit

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Microsoft Dynamics 365 Commerce peut être utilisé pour afficher les recommandations de produit sur le site web de commerce électronique et l'appareil du point de vente (PDV). Les recommandations de produit sont des articles qu'un client peut être intéressé dans. Les recommandations sont basés sur les tendances d'achat d'autres clients dans les magasins en ligne et traditionnels.

Les recommandations de produit permettent aux clients de rechercher facilement et rapidement les produits qu'ils souhaitent tout en ayant une expérience qui les sert bien. La vente croisée et la vente incitative peuvent même être utilisées pour aider les clients à trouver des produits supplémentaires qu'ils n'avaient pas initialement prévu à acheter. Lorsque des recommandations sont utilisées pour aider à la découverte de produit, elles peuvent créer des opportunités de conversion supplémentaires, aider à augmenter le produit des ventes, et même à améliorer la satisfaction la rétention des clients.

Dans Commerce, les recommandations de produit sont optimisées par les technologies de Machine Learning de recommandations Microsoft à une grande échelle.


## <a name="scenarios"></a>Scénarios

Les recommandations de produit sont disponibles pour les scénarios suivants :

- **Sur n'importe quelle page de magasin pour naviguer ou page de destination dans le commerce électronique :** Si les clients ou les vendeurs visitent une page de magasin, le moteur de recommandations peut proposer des produits dans les listes **Nouveau**, **Meilleure vente**, et **Tendance**.
- **Sur la page de détails de produit :** Si les clients ou les vendeurs visitent une page **Détails de produit**, le moteur de recommandations suggère des articles supplémentaires qui sont susceptibles d'être achetés. Ces articles figurent dans la liste **D'autres clients aiment également**.
- **Sur la page de transaction ou la page d'extraction :** Le moteur de recommandations suggère des articles, selon la liste entière d'articles dans le panier. Ces articles figurent dans la liste **Fréquemment achetés ensemble**.

## <a name="recommendation-service"></a>Service de recommandation

Les recommandations de produit utilisent les technologies de Machine Learning de recommandations de la façon suivante :

- Les données au format requis par le service de recommandation sont extraites de la base de données opérationnelle de Commerce et envoyées au magasin Entité.
- Le service de recommandation utilise les données pour former des modèles de recommandation pour les listes **D'autres client aiment également**, **Fréquemment achetés ensemble**, **Nouveau**, **Meilleure vente**, et **Tendance**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Activer les recommandations produit](enable-product-recommendations.md)

[Créer des listes de recommandations produit éditées](create-editorial-recommendation-lists.md)

[Gérer les résultats de recommandation produit fondées sur l'IA et le ML](modify-product-recommendation-results.md)

[Ajouter des listes de recommandation produit aux pages](add-reco-list-to-page.md)
