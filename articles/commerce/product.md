---
title: Ajouter des recommandations produit sur PDV
description: Cet article décrit l’utilisation de recommandations de produit sur un appareil de PDV.
author: bebeale
ms.date: 09/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 170e2bf18aefc79a796620818c7100ff8e6e689a
ms.sourcegitcommit: f88273627ba105ede27f28fe67ccec2d7f78261c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460054"
---
# <a name="add-product-recommendations-on-pos"></a>Ajouter des recommandations produit sur PDV

[!include [banner](includes/banner.md)]

Les recommandations de produit sont essentiellement une application métier transformative qui s’étend dans tous les espaces commerciaux pour créer des expériences de découverte de produit taillées sur mesure, stimulantes et riches. Pour implémenter cette fonctionnalité au PDV, suivez les étapes [comment ajouter des recommandations à vos périphériques de PDV.](add-recommendations-control-pos-screen.md) 

Pour en savoir plus sur les fonctionnalités de recommandations produit, consultez la [vue d’ensemble des recommandations produit.](../commerce/product-recommendations.md) 

## <a name="scenarios"></a>Scénarios

Les recommandations de produit sont activées pour les scénarios de PDV suivants. Elles sont disponibles dans le Cloud POS ou Modern POS (MPOS).

1. Sur la page **Détails de produit** :

    - Si un associé du magasin visite une page **Détails de produit** lorsque vous regardez des transactions antérieures sur différents canaux, le service de recommandation propose des éléments supplémentaires susceptibles d’être achetés ensemble. Selon les modules complémentaires du service, les détaillants peuvent afficher les recommandations de produits **Acheter des looks similaires** et **Acheter une description similaire**, en plus des recommandations personnalisées pour les utilisateurs qui ont un historique d’achats antérieurs.

    [![Recommandations sur la page de Détails du produit.](./media/proddetails.png)](./media/proddetails.png)

2. Sur la page **Transaction** :

    - Le moteur de recommandation suggère des articles selon la liste entière d’articles du panier qui sont fréquemment achetés ensemble.

    > [!NOTE]
    > Pour afficher les recommandations sur la page **Transaction**, le détaillant doit actualiser la mise en page de l’écran dans Dynamics 365 Commerce. Le contrôle **Recommandations** doit être déposé sur la page **Transaction**.

    [![Recommandations sur la page Transaction.](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

## <a name="configure-commerce-to-enable-pos-recommendations"></a>Configurer Commerce pour activer les recommandations de PDV 

Pour configurer des recommandations de produits, confirmez que vous avez terminé le processus d’approvisionnement pour les recommandations de produits Commerce en suivant les étapes décrites dans [Activer les recommandations de produits](../commerce/enable-product-recommendations.md). Par défaut, les recommandations apparaissent sur les deux pages **Détails du produit** et **Détails du client** une fois que vous avez terminé les étapes de d’approvisionnement et que les données ont été préparées avec succès. 

## <a name="add-recommendations-to-the-transaction-screen"></a>Ajouter des recommandations à l’écran de transaction

1. Pour ajouter des recommandations à l’écran de transaction, suivez les étapes de la section [Ajouter des recommandations à l’écran de transaction](add-recommendations-control-pos-screen.md).
1. Pour refléter les modifications apportées dans le concepteur de mise en page de l’écran du point de vente, exécutez la tâche de configuration du canal **1070** de Commerce headquarters.

> [!NOTE] 
> Si vous souhaitez activer les recommandations du PDV à l’aide du fichier de valeurs séparées par des virgules (CSV) RecoMock, vous devez déployer le fichier CSV sur la bibliothèque de ressources Microsoft Dynamics Lifecycle Services (LCS) avant de configurer le gestionnaire de disposition. Si vous utilisez le fichier RecoMock CSV, vous n’avez pas besoin d’activer les recommandations. Le fichier CSV est disponible uniquement à des fins de démonstration. Il est recommandé aux clients ou aux architectes de solutions qui souhaitent imiter l’apparence des listes de recommandations à des fins de démonstration sans avoir à acheter une unité de gestion des stocks (SKU) complémentaire.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des recommandations produit](product-recommendations.md)

[Activer Azure Data Lake Storage dans un environnement Dynamics 365 Commerce](enable-adls-environment.md)

[Activer les recommandations produit](enable-product-recommendations.md)

[Activer les recommandations personnalisées](personalized-recommendations.md)

[Désactiver les recommandations personnalisées](personalization-gdpr.md)

[Activer les recommandations « acheter des aspects similaires »](shop-similar-looks.md)

[Ajouter des recommandations à l’écran de transaction](add-recommendations-control-pos-screen.md)

[Ajuster des résultats des recommandations AI-ML](modify-product-recommendation-results.md)

[Créer manuellement des recommandations sélectionnées](create-editorial-recommendation-lists.md)

[Créer des recommandations avec des données de démonstration](product-recommendations-demo-data.md)

[FAQ sur les recommandations produit](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
