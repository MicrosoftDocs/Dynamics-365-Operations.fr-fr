---
title: Entités de données de produit
description: Cette rubrique fournit des informations sur les différentes entités pouvant être utilisées pour importer et exporter des données produit.
author: cvocph
manager: AnnBe
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: conradv
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2019-12-1
ms.openlocfilehash: 83191ea3d07ec9e2ed6261ee997e06b802ee7645
ms.sourcegitcommit: b806f0c94d703bec39680fead827733361d47045
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/07/2020
ms.locfileid: "2935937"
---
# <a name="product-data-entities"></a>Entités de données de produit

[!include [banner](../includes/banner.md)]

Pour importer et exporter des données de produit, vous devez utiliser des entités de données. Le tableau suivant fournit des détails sur les entités de données liées au produit et décrit le but de chacune.

| Entité | Nom de l'arbre d'objets d'application (AOT) (type) | Notes |
|--------|-------------------------------------------|-------|
| Produits V2 | EcoResProductV2Entity | Cette entité est utilisée pour importer et exporter des produits distincts des produits partagés et des produits génériques. Elle permet des mises à jour. Elle ne prend pas en charge les opérations SQL basées sur un ensemble. Elle este activé pour le protocole OData (Open Data Protocol). |
| Produits lancés V2 | EcoResReleasedProductV2Entity | Cette entité est utilisée pour importer et exporter des produits distincts des produits lancés et des produits génériques. Elle permet des mises à jour. Cela nécessite que le produit partagé soit déjà créé. Lorsqu'un nouveau produit commercialisé est importé, une version du produit partagé est créée. Il existe également des entités distinctes qui peuvent être utilisées pour importer et exporter des produits génériques lancés et des variantes distinctes lancées. Cette entité ne prend pas en charge les opérations SQL basées sur un ensemble ni les opérations de suppression. Elle est activée pour OData. |
| Création de produit lancé V2 | EcoResReleasedProductCreationV2Entity | Cette entité est utilisée pour importer des produits partagés et des produits lancés en une seule étape. Bien qu'elle prenne en charge les exportations, cette utilisation n'est pas recommandée, car le but de l'entité est la création de produits. Elle ne prend pas en charge les mises à jour. Elle prend en charge un ensemble limité de champs (champs disponibles dans la boîte de dialogue de création de produit). Elle ne prend pas en charge les opérations SQL basées sur un ensemble. Elle n'est pas exposé via OData. |
| Variantes de produit | EcoResProductVariantEntity | Cette entité est utilisée pour importer et exporter des variantes de produit partagées. Elle permet des mises à jour. Cela nécessite que des valeurs de dimension soient déjà créées. La clé d'intégration correspond au produit générique plus les dimensions du produit. Cette entité ne prend pas en charge les opérations SQL basées sur un ensemble. Elle est activée pour OData. Elle prend en charge les opérations de suppression. Elle ne peut pas être étendue par l'ajout de nouvelles dimensions de produit. |
| Variantes de produit par identification du numéro de produit | EcoResProductNumberIdentifiedProductVariantEntity | Cette entité est utilisée pour importer et exporter des variantes de produit partagées. Elle permet des mises à jour. Cela nécessite que des valeurs de dimension soient déjà créées. La clé d'intégration est le numéro de produit (alors que la clé d'intégration pour l'entité **Variantes de produits** est le produit générique plus les dimensions du produit). |
| Variantes de produit lancé | EcoResReleasedProductVariantEntity | Cette entité est utilisée pour importer et exporter des variantes de produit lancées. Elle permet des mises à jour. Cela nécessite que les variantes de produit partagées soit déjà créées. Lorsqu'une nouvelle variante de produit commercialisé est importée, une variante du produit partagé est créée. Cette entité ne prend pas en charge les opérations SQL basées sur un ensemble. Elle est activée pour OData. Bien qu'elle prenne en charge les opérations de suppression, cette utilisation entraîne actuellement une corruption des données en raison d'un bogue dans la plateforme actuelle. Cette entité ne peut pas être étendue par l'ajout de nouvelles dimensions de produit. |
| Variantes de produit lancé par identification du numéro de produit | EcoResProductNumberIdentifiedReleasedProductVariantEntity | Cette entité ressemble à l'entité **Variantes de produit lancé**, mais la clé d'intégration est le numéro de produit au lieu du produit générique plus les dimensions du produit. Elle ne peut pas être étendue par l'ajout de nouvelles dimensions de produit. |
| Produits lancés vendables | EcoResSellableReleasedProductEntity | Cette entité est utilisée pour exporter uniquement des produits vendables. Les produits vendables sont des produits ayant toutes les informations requises pour être utilisés dans une commande client. Les mêmes règles s'appliquent lorsqu'un produit est validé avec la fonction **Valider** sur la page **Produits lancés**. |
| Produits distincts lancés V2 | EcoResDistinctProductV2Entity | Cette entité est utilisée pour exporter uniquement des produits distincts. Ces produits distincts peuvent être des produits, des produits de sous-types et des variantes de produit. |
| Produits génériques lancés V2 | EcoResProductMasterV2Entity | Cette entité est utilisée pour importer et exporter des produits génériques. Elle n'est pas activée pour la gestion des données. |
| Article - Code-barres | EcoResProductBarcodeEntity | Cette entité est utilisée pour exporter des produits et des codes-barres. |
| États du cycle de vie des produits | EcoResProductLifecycleSateEntity | Cette entité est utilisée pour importer et exporter les différents états du cycle de vie du produit qui peuvent être attribués à un produit. |

> [!NOTE]
> Vous pouvez utiliser l'entité de données **Produits lancés V2** pour importer des produits dans le système uniquement si le produit partagé a déjà été créé. Sinon, pour importer des produits dans le système, vous devez utiliser l'entité de données **Création de produit**.
