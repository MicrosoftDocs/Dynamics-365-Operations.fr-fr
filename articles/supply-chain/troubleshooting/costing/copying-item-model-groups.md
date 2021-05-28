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
# <a name="missing-field-settings-when-item-model-groups-are-copied-to-another-legal-entity"></a><span data-ttu-id="a3c97-103">Paramètres de champ manquants lorsque les groupes de modèles d'élément sont copiés dans une autre entité juridique</span><span class="sxs-lookup"><span data-stu-id="a3c97-103">Missing field settings when item model groups are copied to another legal entity</span></span>

<span data-ttu-id="a3c97-104">Numéro de la base de connaissances : 4612800</span><span class="sxs-lookup"><span data-stu-id="a3c97-104">KB number: 4612800</span></span>

## <a name="symptoms"></a><span data-ttu-id="a3c97-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="a3c97-105">Symptoms</span></span>

<span data-ttu-id="a3c97-106">Lorsque vous copiez des groupes de modèles d'élément vers une autre entité juridique (société) à l'aide de l'entité *Politiques de stock des groupes de modèles d'articles*, certains paramètres de champ (par exemple, le modèle de stock et la description) sont manquants dans le nouveau groupe de modèles de l'entité juridique de destination.</span><span class="sxs-lookup"><span data-stu-id="a3c97-106">When you copy item model groups to another legal entity (company) by using the *Item model group inventory policies* entity, some field settings (for example, the inventory model and description) are missing in the new model group in the destination legal entity.</span></span>

## <a name="resolution"></a><span data-ttu-id="a3c97-107">Résolution</span><span class="sxs-lookup"><span data-stu-id="a3c97-107">Resolution</span></span>

<span data-ttu-id="a3c97-108">Pour créer une copie complète d'un groupe de modèles d'articles dans une autre entité juridique, vous devez également sélectionner les deux stratégies de stock de groupe de modèles d'articles (`InventInventoryPolicyEntity`) et les politiques d'hypothèses de flux de coûts (`InventCostFlowAssumptionPolicyEntity`) associés au groupe de modèles d'article.</span><span class="sxs-lookup"><span data-stu-id="a3c97-108">To create a complete copy of an item model group to another legal entity, you must also select both the item model group inventory policies (`InventInventoryPolicyEntity`) and the cost flow assumption policies (`InventCostFlowAssumptionPolicyEntity`) that are associated with the item model group.</span></span>
