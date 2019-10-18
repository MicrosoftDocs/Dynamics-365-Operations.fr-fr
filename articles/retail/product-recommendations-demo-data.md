---
title: Données de démonstration des recommandations de produit omnicanal
description: Ce document vise à fournir des instructions sur la manière d'optimiser les recommandations de produit omnicanal dans les environnements de type Onebox de niveau 1 à l'aide de données de démonstration personnalisables et pré-renseignées.
author: bebeale
manager: AnnBe
ms.date: 10/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 81af4c1bb7828c9b346a3ef514d8657e853dcefb
ms.sourcegitcommit: c526cfd1f823df1ff33ded95e599a72f0a15cc5a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2225909"
---
# <a name="omni-channel-product-recommendations-demo-data"></a>Données de démonstration des recommandations de produit omnicanal

Ce document vise à fournir des instructions sur la manière d'optimiser les recommandations de produit omnicanal dans les environnements de type Onebox de niveau 1 à l'aide de données de démonstration personnalisables et pré-renseignées.

Les recommandations de produit omnicanal offrent un ensemble de listes de produits générées de manière programmée ou traitées de manière éditoriale. Ces listes peuvent être utilisées dans différents scénarios, selon les besoins de l'entreprise. Pour en savoir plus sur les listes de recommandation de produit, consultez [Vue d'ensemble des recommandations produit.](product-recommendaitons-overview.md)

Les recommandations de produit des environnements de niveau 2 ou Dynamics supérieurs sont automatiquement calculées selon les données client.
L'utilisation des données de démonstration des recommandations produit ne désactive pas les solutions de recommandations produit déjà fournies dans l'environnement et les coûts associés à cet usage.

Pour les environnements de niveau 1, les recommandations de produit sont basées uniquement sur les données de démonstration statiques stockées dans un fichier .csv.

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a>Activation des données de démonstration des recommandations de produit dans un environnement

Les clients doivent déployer l'**extension de démonstration de Dynamics 365 Commerce (version préliminaire)** vers l'environnement respectif, ce qui active automatiquement les données de démonstration des recommandations de produit.

## <a name="default-demo-data"></a>Données de démonstration par défaut
Chaque environnement de type Onebox est fourni avec un jeu préchargé de données de démonstration de recommandations produit stockées dans le fichier .csv à part **‘reco_demo_data.csv’**, situé dans le même dossier que ce document sur Retail Server.

Ces données sont structurées selon les colonnes suivantes

| Nom de la colonne         | Obligatoire          | Description                                                                                                                                 | Valeurs possibles                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| RecoList            | :heavy_check_mark: | Le type de liste de recommandation produit spécifique que le point de données de démonstration est sur le point de générer.                                                    | <ul><li>RecoBestSelling</li><li>RecoNew</li><li>RecoTrending</li><li>RecoCart</li><li>RecoPeopleAlsoBuy</li></ul> |
| OperatingUnitNumber | :heavy_check_mark: | Le nombre d'unité opérationnelle spécifique où les recommandations produit sont prévues.                                        |                                                                              |
| Catégorie            |                    |    La catégorie pour laquelle la liste spécifique doit être retournée. Si aucune catégorie n'est spécifiée, la liste est destinée uniquement pour le haut de la hiérarchie de navigation.    |                                                                              |
| SeedItemId          |                    |    Pour les listes nécessitant une valeur initiale (RecoPeopleAlsoBuy et RecoCart), le produit pour lequel ces listes doivent présenter des produits supplémentaires.            |                                                                              |
| ItemIds             | :heavy_check_mark: | Un ou plusieurs produits à renvoyer en retour, séparés par **« ;  »**.                                                                  |                                                                              |


## <a name="customize-demo-data"></a>Données de démonstration personnalisées
Les clients peuvent modifier les données de démonstration par défaut avec toute information de catégorie ou de produit configurée au siège. Une fois le fichier CSV mis à jour, les recommandations produit renvoyées aux clients reflèteront immédiatement les modifications.

L'extension contient un fichier de données appelé RecoMockDataset.csv qui permet au client de contrôler le jeu de données utilisé pour activer les résultats d'imitations de recommandations. Le nom de fichier peut être contrôlé via la configuration d'extension à l'aide du paramètre **ext.Recommendations.DemoFilePath**. Cela permet aux clients d'avoir plusieurs jeux de données disponibles entre lesquels basculer pour une configuration plus simple.

```
  <settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
  </settings>
```

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble des recommandations produit](product-recommendations-overview.md)

[Planification de l'environnement](environment-planning.md)
