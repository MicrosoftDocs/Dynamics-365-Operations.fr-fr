---
title: Règles de configuration
description: Cet article fournit des informations générales sur les règles de configuration. Les règles de configuration définissent les relations entre les articles dans une nomenclature (BOM) pour les produits qui utilisent la technologie de configuration basée sur les dimensions.
author: cvocph
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMConfigRule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19761
ms.assetid: e4c6622d-1e2d-4a4d-8047-c553a25d4f87
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 70aff927dfea602ee6c4ad5c195274248f831bcb
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6190182"
---
# <a name="configuration-rules"></a>Règles de configuration

[!include [banner](../includes/banner.md)]

Cet article fournit des informations générales sur les règles de configuration. Les règles de configuration définissent les relations entre les articles dans une nomenclature (BOM) pour les produits qui utilisent la technologie de configuration basée sur les dimensions.

Les règles de configuration sont disponibles lorsque vous définissez des modèles de configuration basés sur les dimensions. Les règles de configuration sont utilisées pour appliquer ou interdire des combinaisons d’article spécifiques dans une nomenclature. Une fois qu’une nomenclature a été créée et que les articles appropriés ont été affectés à leurs groupes de configuration respectifs, une ou plusieurs règles de configuration peuvent être définies. Si deux articles sont liés, l’opérateur **Sélectionner** est utilisé pour assurer l’inclusion. Si deux articles s’excluent mutuellement, l’opérateur **Désélectionner** est utilisé pour assurer l’exclusion.  

**Remarque :** ces informations s’appliquent uniquement aux produits génériques qui utilisent la technologie de configuration basée sur les dimensions.  

Les configurations existantes ne sont pas concernées par les modifications ultérieures apportées aux règles de configuration. Cependant, il est important de définir les règles avant de définir une nouvelle configuration et de les vérifier si vous pensez qu’elles ont été modifiées.  

**Remarque :** pour la méthode **Sélectionner**, le groupe de configurations déduit, le numéro d’article et la configuration sont automatiquement sélectionnés. Pour la méthode **Désélectionner**, le groupe de configurations déduit, le numéro d’article et la configuration ne peuvent pas être sélectionnés.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la configuration des produits basée sur les dimensions](dimension-based-product-configuration.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]