---
title: Principes d’effacement
description: Cet article décrit les quatre principes d’effacement utilisés pour la consommation de matières premières.
author: johanhoffmann
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgShopSupervisorReleaseOrders
audience: Application User
ms.reviewer: kamaybac
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 89fd38ea6d2c1635e9d8974ab99c2e4cdae4d6be
ms.sourcegitcommit: 8d072505f66f507aafbaae65bedf3b530eb6cb7b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9266426"
---
# <a name="flushing-principles"></a>Principes d’effacement

[!include [banner](../includes/banner.md)]

Les principes d’effacement reflètent différents stratégies de consommation des matières premières utilisées dans les processus de production. La consommation est le processus qui déduit le matériel du stock disponible et définit la valeur des matières consommées sur **Travail en cours** pour les ordres de fabrication et des lots de commandes. Les matières premières sont consommées généralement à un emplacement qui est configuré pour le processus qui consomme les matières. Cet emplacement est appelé l’emplacement d’entrée en production.

Avant la consommation de matières, celles-ci sont déplacées vers l’emplacement d’entrée. L’illustration suivante présente le processus.

[![scenario4a.](./media/scenario4a.png)](./media/scenario4a.png)

1. Entrepôt des matières
2. Prélèvement de matières premières
3. Emplacement de l’entrée en production
4. Consommation de matières premières
5. Processus de production

La consommation de matières est contrôlée à l’aide des quatre principes d’effacement suivants :

- Manuel
- Commencement
- Terminer
- Disponible à l’emplacement

Les principes d’effacement sont configurés dans une hiérarchie de valeurs par défaut. La hiérarchie commence au produit lancé, où le principe d’effacement est défini sur **Début**. Dans la nomenclature ou ligne de formule, le principe d’effacement du produit peut être remplacé. Le principe d’effacement par défaut sur les lignes de nomenclature de production ou les lignes de formule du lot de commandes est issu du produit ou de la valeur remplacée sur la nomenclature ou les formules.

## <a name="description-of-the-flushing-principles"></a>Description des principes d’effacement

### <a name="manual"></a>Manuel
Le principe d’effacement manuel indique que l’enregistrement de la consommation de matières est une opération manuelle. Ce principe est utile si, par exemple, vous voulez pouvoir suivre l’heure, et la quantité de numéros de lot ou de numéros de série consommés doit être comptabilisée à des fins de suivi. La consommation manuelle est enregistrée dans un journal des prélèvements en production. Pour les articles activés pour les processus de gestion des entrepôts, un flux portable peut être appliqué.

### <a name="start"></a>Début
Le principe d’effacement de début indique que le matériel est automatiquement consommé lorsque l’ordre de fabrication démarre. La quantité de matériel consommé est proportionnelle à la quantité lancée. Lorsque le principe d’effacement de début est utilisé avec le système d’exécution de la production, il permet également d’effacer des matières lorsqu’une opération ou une tâche de traitement est lancée. Ce principe est utile si, par exemple, l’écart dans la consommation est faible, les matières sont des matériaux à faible valeur, il est inutile d’effectuer un suivi, ou les opérations nécessitent un délai d’exécution court. 

### <a name="finish"></a>Terminer
La principe d’effacement de fin indique que le matériel est automatiquement consommé lorsque l’ordre de fabrication est déclaré terminé, ou lorsqu’une opération paramétrée pour consommer les matières est enregistrée comme terminée. La quantité de matériel consommé est proportionnelle à la quantité désignée comme terminée. Lorsque le principe d’effacement de fin est utilisé avec le système d’exécution de la production, il permet également d’effacer des matières lorsqu’une opération ou une tâche de traitement est terminée. Ce principe est utile dans les mêmes situations que le principe de début. Toutefois, le principe de fin est pour les opérations avec un délai d’exécution plus long, au cours duquel les matières ne devraient pas être définies sur Travaux en cours avant que l’opération soit terminée.

> [!NOTE]
> Vous ne pouvez pas utiliser le principe d’effacement de fin avec des éléments de planification. Nous vous recommandons plutôt d’utiliser le principe d’effacement de début. Les éléments de planification ont un type de production d’*élément de planification*, et seuls les coproduits et les sous-produits peuvent être déclarés comme finis sur les commandes de lots qui sont créées pour les éléments de planification.

### <a name="available-at-location"></a>Disponible à l’emplacement
Le principe d’effacement sur site disponible indique que les matières sont automatiquement consommées lorsqu’elles sont enregistrées comme prélevées pour la production. Les matières sont enregistrées comme prélevées de l’emplacement lorsque le prélèvement de matières premières est terminé, ou lorsque la matière est disponible à l’emplacement d’entrée en production et que la ligne de matière est lancée à l’entrepôt. Les prélèvements générés lors du processus sont validés dans un traitement par lots. Ce principe est utile si, par exemple, vous avez plusieurs activités de prélèvement pour un ordre de fabrication. Dans ce cas, vous ne devez pas mettre les prélèvements à jour manuellement, et vous pouvez obtenir une vue actuelle du solde des travaux en cours.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
