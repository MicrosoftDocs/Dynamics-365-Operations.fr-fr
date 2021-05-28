---
title: Paramètres de champ manquants lorsque les groupes de modèles d'élément sont copiés dans une autre entité juridique
description: Paramètres de champ manquants lorsque les groupes de modèles d'élément sont copiés dans une autre entité juridique.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6f6fdfef0bc377418ed8a9c8830e74526a0b95eb
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026502"
---
# <a name="missing-field-settings-when-item-model-groups-are-copied-to-another-legal-entity"></a>Paramètres de champ manquants lorsque les groupes de modèles d'élément sont copiés dans une autre entité juridique

Numéro de la base de connaissances : 4612800

## <a name="symptoms"></a>Symptômes

Lorsque vous copiez des groupes de modèles d'élément vers une autre entité juridique (société) à l'aide de l'entité *Politiques de stock des groupes de modèles d'articles*, certains paramètres de champ (par exemple, le modèle de stock et la description) sont manquants dans le nouveau groupe de modèles de l'entité juridique de destination.

## <a name="resolution"></a>Résolution

Pour créer une copie complète d'un groupe de modèles d'articles dans une autre entité juridique, vous devez également sélectionner les deux stratégies de stock de groupe de modèles d'articles (`InventInventoryPolicyEntity`) et les politiques d'hypothèses de flux de coûts (`InventCostFlowAssumptionPolicyEntity`) associés au groupe de modèles d'article.
