---
title: FAQ sur les recommandations produit
description: Cette rubrique fournit des informations sur les processus et les outils que vous pouvez utiliser pour résoudre les problèmes liés aux recommandations de produit ou à leurs résultats.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, Core, Operations
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8eaebaf605cd53ce6848624169c3bbbd2a4281a5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009897"
---
# <a name="product-recommendations-faq"></a>FAQ sur les recommandations produit


[!include [banner](includes/banner.md)]

Cette rubrique fournit des informations sur les processus et les outils que vous pouvez utiliser pour résoudre les problèmes liés aux [recommandations de produit](product-recommendations.md) ou à leurs résultats.

## <a name="best-practices"></a>Utilisation optimale
Il est primordial d'utiliser le concept des produits génériques et des variantes. Le regroupement raisonnable des variantes en un produit générique parent aide les algorithmes et le service de liste à créer de meilleurs modèles. En outre, le service peut servir simplement une instance d'un produit au lieu de mettre toutes les variantes étroitement liées dans une liste. Lorsque toutes les variantes étroitement liées sont mises dans une liste, des résultats incorrects ou en double peuvent se produire.

## <a name="why-are-products-missing-from-my-recommendation-lists"></a>Pourquoi des produits manquent-ils de mes listes de recommandations ?

Généralement, si un article est absent d'une liste de recommandations de produit, il peut y a un problème de configuration de produit. Par exemple, il peut y avoir une date de début ou une date de fin du produit incorrecte, une dimension a peut-être été mal configurée, ou le produit peut ne pas être dans l'assortiment de canal adéquat, et ainsi de suite.

Si un article est manquant d'une liste des recommandations basée sur le Machine Learning et l'Intelligence artificielle (ML et IA), l'article peut ne pas correspondre aux critères de la liste des recommandations, ou il peut ne pas avoir suffisamment de transactions d'achat pour que la liste des recommandations l'affiche.

Nous vous recommandons de vérifier ces étapes :
1. **Assurez-vous que les recommandations de produit ont été activées dans le siège.** Pour plus d'informations sur l'activation de ce service, voir [Activer les recommandations de produits](enable-product-recommendations.md).
1. **Assurez-vous que les propriétés de produit clés sont définies.** Par exemple, les assortiments de produits doivent être définis sur **Inclure**.
1. **Pour les produits récemment assortis, cela peut prendre quelques heures jusqu'à 3 heures avant que le produit commence à apparaître dans la nouvelle liste.**
1. **Si un produit n'apparaît toujours pas dans Tendance, Meilleures ventes, D'autres clients aiment également ou Fréquemment achetés ensemble, ce produit peut ne pas avoir suffisamment de transactions.** Dans ce cas, vous pouvez attendre que plus de transactions se produisent, mettre à jour les paramètres de la liste de recommandations par défaut ou utiliser l'intervention manuelle pour modifier les résultats de la liste des recommandation de produits. Pour plus d'informations sur les paramètres de recommandation, voir [Gérer les résultats de recommandation produit fondées sur l'IA et le ML](modify-product-recommendation-results.md).
1. **Assurez-vous que le produit répond aux critères de recommandation pour la liste.** Pour plus d'informations sur les paramètres de recommandation de produits, voir [Gérer les résultats de recommandation produit fondées sur l'IA et le ML](modify-product-recommendation-results.md).

## <a name="how-can-i-prevent-poor-recommendation-results-from-being-returned"></a>Comment empêcher que des résultats de recommandation médiocres soient retournés ?

Les listes de recommandations exigent un grand nombre de transactions afin de produire des résultats. Par conséquent, il est important que les utilisateurs fournissent des données de transaction historiques complètes.

En outre, les produits sans transactions ou peu de transactions généralement n'ont pas de résultats **D'autres clients aiment également** ou **Fréquemment achetés ensemble**, et n'apparaissent pas dans les listes des recommandations **Tendance** ou **Meilleures ventes**. Cette situation peut souvent se produire pour les produits très nouveaux, ou pour les anciens produits qui ont un nombre limité d'achats. Les nouveaux articles populaires surmonteront facilement ce problème.

Nous vous recommandons de suivre ces étapes :
1. **Assurez-vous que le produit répond aux critères de recommandation pour cette liste.** Pour plus d'informations sur les paramètres de recommandation de produits, voir Modifier les résultats de recommandation produit fondées sur l'IA et le ML.
1. **Si le produit est nouveau, envisagez de modifier une liste des recommandations jusqu'à ce que ce produit ait davantage de transaction.** Pour plus d'informations sur la modification des résultats de la liste des recommandations, voir [Gérer les résultats de recommandation produit fondées sur l'IA et le ML](modify-product-recommendation-results.md).


- **Assurez-vous que le produit répond aux critères de recommandation pour cette liste.** Pour plus d'informations sur les paramètres de recommandation de produits, voir [Gérer les résultats de recommandation produit fondées sur l'IA et le ML](modify-product-recommendation-results.md).
- **Si le produit est nouveau, envisagez de modifier une liste des recommandations jusqu'à ce que ce produit ait davantage de transaction**. Pour plus d'informations sur la modification des résultats de la liste des recommandations, voir [Gérer les résultats de recommandation produit fondées sur l'IA et le ML](modify-product-recommendation-results.md).

## <a name="can-i-remove-a-product-but-still-see-it-in-the-store"></a>Puis-je supprimer un produit et continuer de le voir dans le magasin ?

Vous pouvez ajuster les listes qui sont algorithmiquement générées si un besoin commercial se fait sentir. Toutefois, si un produit est supprimé de la liste des recommandations, le produit reste découvrable dans le magasin. Pour plus d'informations sur la modification des résultats des recommandations de produits, voir [Gérer les résultats de recommandation produit fondées sur l'IA et le ML](modify-product-recommendation-results.md).

Si vous devez bloquer un article de la découverte dans le magasin, vous devez modifier la valeur **Assortiments d'articles** sur **Exclure**.

## <a name="how-do-i-add-a-list-to-an-e-commerce-page"></a>Comment ajouter une liste à une page de commerce électronique ?

Pour plus d'informations sur l'ajout de pages de recommandations de produits à votre site web de commerce électronique, voir [Ajouter des listes de recommandation produit aux pages](add-reco-list-to-page.md).

## <a name="how-do-i-enable-recommendations-on-pos"></a>Comment activer les recommandations dans le PDV ?

Après avoir activé les recommandations de produits, vous devez ajouter le panneau de recommandations à l'écran du PDV de contrôle. Pour en savoir plus, voir [Ajouter un contrôle de recommandations à l'écran de transaction sur les périphériques de PDV](add-recommendations-control-pos-screen.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble des recommandations produit](product-recommendations.md)

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
