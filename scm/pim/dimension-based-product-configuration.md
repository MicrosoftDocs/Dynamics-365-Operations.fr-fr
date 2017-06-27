---
title: "Configuration de produit basée dur les dimensions"
description: "la configuration de produit basée sur les dimensions représente une solution simple pour créer plusieurs variantes de produit à partir d'un produit générique unique et de sa nomenclature."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMConfigRule, BOMTable, ConfigChooseFromRoute, ConfigGroup, ConfigHierarchy, EcoResDimensionBasedConfiguration
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19821
ms.assetid: 4db9890b-306b-4be7-ba98-3be2094d561f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: d13fc55342030d96d38f264f6bff9586832b4ab5
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="dimension-based-product-configuration"></a>Configuration de produit basée dur les dimensions

[!include[banner](../includes/banner.md)]


la configuration de produit basée sur les dimensions représente une solution simple pour créer plusieurs variantes de produit à partir d'un produit générique unique et de sa nomenclature.

La configuration de produit basée sur les dimensions est l'une des trois technologies intégrées de configuration de produit. Les deux autres technologies sont les variantes prédéfinies et la configuration basée sur les contraintes. Les trois technologies utilise un produit générique comme point de départ et permettent à l'utilisateur de créer plusieurs variantes de produit pour un produit générique.

## <a name="key-concepts"></a>Concepts clés
La configuration de produit basée sur les dimensions repose sur les concepts clés suivants :

-   Produits génériques
-   Dimension de produit de configuration
-   Groupes de configurations
-   Nomenclature
-   Gamme de configuration
-   Règles de configuration

### <a name="product-masters"></a>Produits génériques

Un produit générique est le point de départ de tout processus de configuration de produit. Pour la configuration de produit basée sur les dimensions, vous avez besoin d'un produit générique avec cette technologie de configuration et un groupe de dimensions de produit qui inclut la dimension de produit de configuration.

### <a name="configuration-product-dimension"></a>Dimension de produit de configuration

La dimension de produit de configuration sert à identifier les variantes de produit d'un produit générique avec la technologie de configuration basée sur les dimensions. La valeur de la dimension de configuration est entrée par l'utilisateur et doit aider à identifier les différentes variantes de produit.

### <a name="configuration-groups"></a>Groupes de configurations

Les groupes de configurations sont définis dans un référentiel central et peuvent être utilisés pour tous les modèles de configuration de produit basés sur les dimensions. Les groupes de configurations sont associés aux lignes de nomenclature individuelles et lient un groupe de lignes qui s'excluent mutuellement. Cela signifie qu'une seule ligne par groupe peut être activée pour une seule variante de produit.

### <a name="bill-of-materials-bom"></a>Nomenclature

La nomenclature représentent les éléments constitutifs pour une configuration de produit basée sur les dimensions. Elle doit inclure tous les différents produits qui peuvent être utilisés dans n'importe quelle variante de produit. Chaque ligne de la nomenclature peut faire référence à un groupe de configurations. Si une ligne ne fait pas référence à un groupe de configurations, elle est incluse dans toutes les variantes de produit.

### <a name="configuration-route"></a>Gamme de configuration

La gamme de configuration détermine l'ordre des groupes de configurations, tels qu'ils seront affichés à l'utilisateur au cours du processus de configuration de produit.

### <a name="configuration-rules"></a>Règles de configuration

Les règles de configuration sont un mécanisme qui garantit qu'un produit inclus dans un groupe de configurations dans une nomenclature applique soit une inclusion soit une exclusion d'un produit dans un groupe de configurations différent dans la même nomenclature.

## <a name="product-modeling-process"></a>Processus de modélisation de produits
La séquence naturelle pour générer un modèle de produit basé sur les dimensions commence par définir les groupes de configurations pertinents. Il est important de vérifier que tous les produits qui seront utilisés dans la nomenclature ont été lancés vers la société pour laquelle le modèle de produit est établi. Avec ces éléments constitutifs en place, l'utilisateur peut créer la nomenclature et affecter des groupes de configurations à toutes les lignes de nomenclature appropriées. Lorsque la nomenclature est terminée, une gamme de configuration peut être définie pour organiser les groupes de configurations dans l'ordre approprié. \[caption id="attachment\_282671" align="alignnone" width="1187"\][![Processus de modélisation de produit basé sur les dimensions](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) Processus de modélisation de produit basé sur les dimensions\[/caption\] Si certains produits issus de différents groupes de configuration doivent être utilisés ensemble ou pas, vous pouvez créer des règles de configuration qui feront appliquer ces relations entre les produits. Une fois la nomenclature liée avec un produit générique basé sur les dimensions par l'intermédiaire d'une version de nomenclature et que les deux ont été approuvés et activés, vous pouvez créer des configurations de produit et entrer un nom pour chaque configuration. Les configurations peuvent être définies avant qu'une transaction quelconque soit générée, ou avant qu'une certaine configuration devienne nécessaire.

### <a name="suggested-use"></a>Suggestion d'utilisation

La technologie de configuration basée sur les dimensions est optimale pour les produits à variabilité limitée et quand la combinaison des dimensions de produit standard (taille, couleur, style, et configuration) est inappropriée pour identifier une variante de produit spécifique. Un exemple peut être une bicyclette avec une hauteur de cadre, une taille de roue, des types de frein, et différents dérailleurs.




