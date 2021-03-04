---
title: Créer des recommandations avec des données de démonstration
description: Cette rubrique fournit des instructions sur la manière d'optimiser les recommandations de produit omnicanal dans les environnements de type Onebox de niveau 1 à l'aide de données de démonstration personnalisables et pré-renseignées.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: cca6913375eec2565852676f3c1da5a67f71e14f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412140"
---
# <a name="create-recommendations-with-demo-data"></a>Créer des recommandations avec des données de démonstration

[!include [banner](includes/banner.md)]

Cette rubrique fournit des instructions sur la manière d'optimiser les recommandations de produit omnicanal dans les environnements de type Onebox de niveau 1 à l'aide de données de démonstration personnalisables et pré-renseignées.

Les recommandations de produit omnicanal offrent un ensemble de listes de produits générées de manière programmée ou traitées de manière éditoriale. Ces listes peuvent être utilisées dans différents scénarios, selon les besoins de l'entreprise. Pour en savoir plus sur les listes de recommandation de produit, consultez [Vue d'ensemble des recommandations produit.](product-recommendations.md).

Les recommandations de produit des environnements de niveau 2 ou Dynamics 365 supérieurs sont automatiquement calculées selon les données client. L'utilisation des données de démonstration des recommandations produit ne désactive pas les solutions de recommandations produit déjà fournies dans l'environnement et les coûts associés à cet usage.

Pour les environnements de niveau 1, les recommandations de produit sont basées uniquement sur les données de démonstration statiques stockées dans un fichier .csv.

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a>Activation des données de démonstration des recommandations de produit dans un environnement
Pour activer les données de démonstration de produit, vous devez déployer la version préliminaire de l'extension de démonstration de Dynamics 365 Commerce vers l'environnement respectif. Cela active automatiquement les données de démonstration de recommandations de produit.

## <a name="default-demo-data"></a>Données de démonstration par défaut
Chaque environnement de type Onebox est fourni avec un jeu préchargé de données de démonstration (recommandations de produit) stockées dans le fichier reco_demo_data.csv qui se trouve dans Commerce Scale Unit.

Les données sont structurées selon les colonnes suivantes.

| Nom de la colonne         | Obligatoire          | Description                                                                                                                                 | Valeurs possibles                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| RecoList            | :heavy_check_mark: | Le type de liste de recommandation produit spécifique que le point de données de démonstration est sur le point de générer.                                                    | <ul><li>RecoBestSelling</li><li>RecoNew</li><li>RecoTrending</li><li>RecoCart</li><li>RecoPeopleAlsoBuy</li></ul> |
| OperatingUnitNumber | :heavy_check_mark: | Le nombre d'unité opérationnelle spécifique où les recommandations produit sont prévues.                                        |                                                                              |
| Catégorie            |                    |    La catégorie pour laquelle la liste spécifique doit être retournée. Si aucune catégorie n'est spécifiée, la liste est destinée uniquement pour le haut de la hiérarchie de navigation.    |                                                                              |
| SeedItemId          |                    |    Pour les listes nécessitant une valeur initiale (RecoPeopleAlsoBuy et RecoCart), le produit pour lequel ces listes doivent présenter des produits supplémentaires.            |                                                                              |
| CustomerId          |                    |    Pour les listes qui nécessitent un identifiant client (RecoPicks).  La valeur par défaut « 0 » s'applique à tous les clients.          |                                                                              |
| ItemIds             | :heavy_check_mark: | Un ou plusieurs produits à renvoyer en retour, séparés par ’;’.                                                                  |                                                                              |

## <a name="customize-demo-data"></a>Données de démonstration personnalisées
Vous pouvez modifier les données de démonstration par défaut avec toute information de catégorie ou de produit configurée au siège. Une fois le fichier CSV mis à jour, les recommandations de produit qui sont renvoyées aux clients reflèteront immédiatement les modifications.

L'extension contient un fichier de données appelé 'RecoMockDataset.csv' qui vous permet de contrôler le jeu de données utilisé pour activer les résultats d'imitations de recommandations. Le nom de fichier peut être contrôlé via la configuration d'extension à l'aide du paramètre **ext.Recommendations.DemoFilePath**. Cela vous permet d'avoir plusieurs jeux de données disponibles entre lesquels basculer pour une configuration plus simple.


```xml
<settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
</settings>
```

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

[FAQ sur les recommandations produit](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]