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
ms.openlocfilehash: ecda571a356c6968196d09cc19923105cf4544ab
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770137"
---
# <a name="enable-product-recommendations"></a>Activer les recommandations produit

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cette rubrique explique comment faire des recommandations de produit basées sur le Machine Learning et l'Intelligence artificielle disponible pour les clients Microsoft Dynamics 365 Commerce. Pour en savoir plus sur les listes de recommandation de produit, consultez [Vue d'ensemble des recommandations produit.](product-recommendations.md).

## <a name="recommendations-pre-check"></a>Recommandations avant contrôle
Avant l'activation, notez-vous que les recommandations de produit sont uniquement prises en charge par les clients de F&O prenant en charge la version 10.0.6 et ayant migré leur stockage pour utiliser BDL. 

En outre, assurez-vous que les mesures RetailSale ont été activées. Pour en savoir plus sur ce processus de paramétrage, allez [ici.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)


## <a name="turn-on-recommendations"></a>Activer les recommandations

Pour activer les recommandations de produit, procédez comme suit.

1. Accédez à **Vente au détail** &gt; **Recommandations de produits** &gt; **Paramètres des recommandations**.
1. Dans la liste des paramètres partagés de vente au détail, sélectionnez **Listes des recommandations**.
1. Définissez l'option **Activer les recommandations** sur **Oui**.

![activer les recommandations produit](./media/enableproductrecommendations.png)

> [!NOTE]
> Cette procédure démarre le processus de génération de listes de recommandations de produit. Cette opération peut nécessiter jusqu'à plusieurs heures avant que les listes soient disponibles et puissent s'affichent sur point de vente (PDV) ou dans Dynamics 365 for Commerce.

## <a name="configure-recommendation-list-parameters"></a>Configuration des paramètres de la liste des recommandations
Par défaut, la liste des recommandations de produit basée sur Machine Learning - Intelligence artificielle fournit des valeurs suggérées. Vous pouvez modifier les valeurs suggérées par défaut pour les adapter au flux de votre entreprise. Pour en savoir plus sur la manière de modifier les paramètres par défaut, accédez à [Gérer les résultats de recommandation produit fondées sur l'IA et le ML](modify-product-recommendation-results.md).

## <a name="show-recommendations-on-pos-devices"></a>Afficher les recommandations sur les appareils PDV
Après avoir activé les recommandations dans back-office, le panneau de recommandations doit être ajouté à l'écran du PDV de contrôle via l'outil de disposition. Pour en savoir plus sur ce processus, allez [ici.](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)


## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble des recommandations produit](product-recommendations.md)

[Ajouter des listes de recommandation produit aux pages](add-reco-list-to-page.md)

[Ajouter le panneau de recommandations aux appareils PDV](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)


