---
title: Ajouter des recommandations produit sur PDV
description: Cette rubrique décrit l’utilisation de recommandations de produit sur un appareil de PDV.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7afe9225b8fc966ca154a5eb7421e8d4cc7c3023
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412378"
---
# <a name="add-product-recommendations-on-pos"></a>Ajouter des recommandations produit sur PDV

[!include [banner](includes/banner.md)]

Les recommandations de produit sont essentiellement une application métier transformative qui s’étend dans tous les espaces commerciaux pour créer des expériences de découverte de produit taillées sur mesure, stimulantes et riches. Pour implémenter cette fonctionnalité au PDV, suivez les étapes [comment ajouter des recommandations à vos périphériques de PDV.](add-recommendations-control-pos-screen.md) 

Pour en savoir plus sur les fonctionnalités de recommandations produit, consultez la [vue d’ensemble des recommandations produit.](../commerce/product-recommendations.md) 

## <a name="scenarios"></a>Scénarios

Les recommandations de produit sont activées pour les scénarios de PDV suivants. Elles sont disponibles dans le Cloud POS ou Modern POS (MPOS).

1. Sur la page **Détails de produit** :

    - Si un associé du magasin visite une page **Détails de produit** lorsque vous regardez des transactions antérieures sur différents canaux, le service de recommandation propose des éléments supplémentaires susceptibles d’être achetés ensemble.

    [![Recommandations sur la page de Détails du produit](./media/proddetails.png)](./media/proddetails.png)

2. Sur la page **Transaction** :

    - Le moteur de recommandation suggère des articles selon la liste entière d’articles du panier qui sont fréquemment achetés ensemble.

    > [!NOTE]
    > Pour afficher les recommandations sur la page **Transaction**, le détaillant doit actualiser la mise en page de l’écran dans Dynamics 365 Commerce. Le contrôle **Recommandations** doit être déposé sur la page **Transaction**.

    [![Recommandations sur la page Transaction](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

## <a name="configure-commerce-to-enable-pos-recommendations"></a>Configurer Commerce pour activer les recommandations de PDV

Pour paramétrer les recommandations de produit, procédez comme suit :

1. Veillez à ce que votre service ait été mis à jour avec la **version 10.0.6.**
2. Suivez les instructions sur la procédure pour [activer les recommandations de produit](../commerce/enable-product-recommendations.md) pour votre entreprise.
3. Facultatif : Pour afficher les recommandations dans l’écran de transaction, allez dans **Mise en page de l’écran**, choisissez une mise en page d’écran, lancez le **Concepteur de mise en page de l’écran**, puis faites glisser-déplacer le contrôle de **recommandations** à l’emplacement souhaité.
4. Accédez à **Paramètres de commerce**, sélectionnez **Apprentissage machine**, sélectionnez **Oui** sous **Activer les recommandations de PDV**.
5. Pour afficher les recommandations sur le PDV, exécutez une tâche de configuration globale **1110**. Pour refléter les modifications effectuées dans le concepteur de mise en page de l’écran du PDV, exécutez la tâche de configuration des canaux **1070**.

## <a name="troubleshoot-issues-where-you-have-product-recommendations-already-enabled"></a>Résoudre les problèmes que vous rencontrez lorsque vous avez des recommandations produit déjà activées

- Accédez à **Paramètres de commerce** \> **Listes de recommandation** \> **Désactiver les recommandations produit** et exécutez **Tâche de configuration globale \[9999\]**. 
- Si vous avez ajouté le **Contrôle de recommandations** à votre écran de transaction à l’aide du **Concepteur de mise en page de l’écran**, supprimez-le également.
- Si vous avez des questions supplémentaires, vérifiez [FAQ de recommandations du produit](../commerce/faq-recommendations.md) pour plus d’informations.

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