---
title: "Règles de configuration"
description: "Cet article fournit des informations générales sur les règles de configuration. Les règles de configuration définissent les relations entre les articles dans une nomenclature (BOM) pour les produits qui utilisent la technologie de configuration basée sur les dimensions."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMConfigRule
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19761
ms.assetid: e4c6622d-1e2d-4a4d-8047-c553a25d4f87
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 37f70d2620023915b23425d41dfb0043ef856492
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="configuration-rules"></a>Règles de configuration

[!include[banner](../includes/banner.md)]


Cet article fournit des informations générales sur les règles de configuration. Les règles de configuration définissent les relations entre les articles dans une nomenclature (BOM) pour les produits qui utilisent la technologie de configuration basée sur les dimensions.

Les règles de configuration sont disponibles lorsque vous définissez des modèles de configuration basés sur les dimensions. Les règles de configuration sont utilisées pour appliquer ou interdire des combinaisons d'article spécifiques dans une nomenclature. Une fois qu'une nomenclature a été créée et que les articles appropriés ont été affectés à leurs groupes de configuration respectifs, une ou plusieurs règles de configuration peuvent être définies. Si deux articles sont liés, l'opérateur **Sélectionner** est utilisé pour assurer l'inclusion. Si deux articles s'excluent mutuellement, l'opérateur **Désélectionner** est utilisé pour assurer l'exclusion.  

**Remarque :** ces informations s'appliquent uniquement aux produits génériques qui utilisent la technologie de configuration basée sur les dimensions.  

Les configurations existantes ne sont pas concernées par les modifications ultérieures apportées aux règles de configuration. Cependant, il est important de définir les règles avant de définir une nouvelle configuration et de les vérifier si vous pensez qu'elles ont été modifiées.  

**Remarque :** pour la méthode **Sélectionner**, le groupe de configurations déduit, le numéro d'article et la configuration sont automatiquement sélectionnés. Pour la méthode **Désélectionner**, le groupe de configurations déduit, le numéro d'article et la configuration ne peuvent pas être sélectionnés.

<a name="see-also"></a>Voir également :
--------

[Configuration de produit basée dur les dimensions](dimension-based-product-configuration.md)




