---
title: Activer les recommandations produit
description: Cette rubrique explique comment faire des recommandations de produit basées sur le Machine Learning et l'Intelligence artificielle disponible pour les clients Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 10/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2d3f1bc2526eeacb4bd6338a0679eadd95a75989
ms.sourcegitcommit: b5ecde955a69f577de46e7db10e89caaedeb2b49
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024954"
---
# <a name="enable-product-recommendations"></a>Activer les recommandations produit

[!include [banner](includes/banner.md)]

Cette rubrique explique comment faire des recommandations de produit basées sur le Machine Learning et l'Intelligence artificielle disponible pour les clients Microsoft Dynamics 365 Commerce. Pour en savoir plus sur les listes de recommandation de produit, consultez [Vue d'ensemble des recommandations produit.](product-recommendations.md).

## <a name="recommendations-pre-check"></a>Recommandations avant contrôle

Avant l'activation, notez que les recommandations de produit sont uniquement prises en charge pour les clients Commerce qui ont migré leur stockage pour utiliser Azure Data Lake Storage (ADLS). 

Pour connaître les étapes d'activation d'ADLS, consultez [Comment activer ADLS dans un environnement Dynamics 365](enable-ADLS-environment.md).

En outre, assurez-vous que les mesures RetailSale ont été activées. Pour en savoir plus sur ce processus de paramétrage, allez [ici.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)


## <a name="turn-on-recommendations"></a>Activer les recommandations

Pour activer les recommandations de produit, procédez comme suit.

1. Accédez à **Commerce et vente au détail &gt; Recommandations de produit &gt; Paramètres des recommandations**.
1. Dans la liste des paramètres partagés, sélectionnez **Listes des recommandations**.
1. Définissez l'option **Activer les recommandations** sur **Oui**.

![activer les recommandations produit](./media/enableproductrecommendations.png)

> [!NOTE]
> Cette procédure démarre le processus de génération de listes de recommandations de produit. Cette opération peut nécessiter jusqu'à plusieurs heures avant que les listes soient disponibles et puissent s'affichent sur point de vente (PDV) ou dans Dynamics 365 Commerce.

## <a name="configure-recommendation-list-parameters"></a>Configuration des paramètres de la liste des recommandations

Par défaut, la liste des recommandations de produit basée sur Machine Learning - Intelligence artificielle fournit des valeurs suggérées. Vous pouvez modifier les valeurs suggérées par défaut pour les adapter au flux de votre entreprise. Pour en savoir plus sur la manière de modifier les paramètres par défaut, accédez à [Gérer les résultats de recommandation produit fondées sur l'IA et le ML](modify-product-recommendation-results.md).

## <a name="show-recommendations-on-pos-devices"></a>Afficher les recommandations sur les appareils PDV

Après avoir activé les recommandations dans le back-office Commerce, le volet de recommandations doit être ajouté à l'écran du PDV de contrôle à l'aide de l'outil de disposition. Pour en savoir plus sur ce processus, voir [Ajouter un contrôle de recommandations à l'écran de transaction sur les périphériques de PDV](add-recommendations-control-pos-screen.md). 

## <a name="enable-personalized-recommendations"></a>Activer les recommandations personnalisées

Pour plus d'informations sur la manière de recevoir des recommandations personnalisées, voir [Activer les recommandations personnalisées](personalized-recommendations.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble des recommandations produit](product-recommendations.md)

[Activer les recommandations personnalisées](personalized-recommendations.md)

[Ajouter des listes de recommandation produit aux pages](add-reco-list-to-page.md)

[Ajouter le panneau de recommandations aux appareils PDV](add-recommendations-control-pos-screen.md)

[Vue d'ensemble du module de collecte de produits](product-collection-module-overview.md)

[Activer ADLS dans un environnement Dynamics 365](enable-ADLS-environment.md)

