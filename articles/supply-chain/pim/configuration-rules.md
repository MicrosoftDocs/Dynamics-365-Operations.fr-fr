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
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: bc8e606cdc0bc5a45321c67ce9b089059f226df2
ms.contentlocale: fr-fr
ms.lasthandoff: 02/07/2018

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




