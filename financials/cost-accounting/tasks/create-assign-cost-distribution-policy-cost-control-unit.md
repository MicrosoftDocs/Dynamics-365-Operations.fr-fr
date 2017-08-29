--- 
title: "Créer et affecter une stratégie de distribution des coûts à une unité de contrôle des coûts"
description: "Les règles de distribution des coûts sont utilisées pour distribuer les coûts qui ont été financièrement comptabilisés sur un centre de coût collectif."
author: YuyuScheller
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 492e4a94ec0caef8c51a691043a1ffb9e6a04758
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="create-and-assign-a-cost-distribution-policy-to-a-cost-control-unit"></a>Créer et affecter une stratégie de distribution des coûts à une unité de contrôle des coûts

[!include[task guide banner](../../includes/task-guide-banner.md)]

Les règles de distribution des coûts sont utilisées pour distribuer les coûts qui ont été financièrement comptabilisés sur un centre de coût collectif. Le comptable s'assure que le coût est distribué sur les centres de coût, selon la base de répartition sélectionnée. Une stratégie et les règles correspondantes sont affectées à une unité de contrôle des coûts. Ce guide de tâche utilise un exemple pour indiquer comment créer une stratégie de distribution des coûts et les règles correspondantes.


## <a name="create-a-policy"></a>Créer une stratégie
1. Accédez à Contrôle de gestion > Stratégies > Stratégies de distribution des coûts.
2. Cliquez sur Nouveau.
3. Dans le champ Nom de la stratégie, tapez une valeur.
4. Dans le champ Description, entrez une valeur.
5. Dans le champ Hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.
    * Sélectionnez Organisation.  
6. Dans le champ Hiérarchie des dimensions d'élément de coût, entrez ou sélectionnez une valeur.
    * Sélectionnez CDS P/L.  
7. Dans le champ Dimension statistique, entrez ou sélectionnez une valeur.
    * Sélectionnez Éléments statistiques.  
8. Cliquez sur Enregistrer.

## <a name="create-rules-for-the-policy"></a>Créer des règles pour la stratégie
1. Cliquez sur Nouveau.
2. Dans la liste, marquez la ligne sélectionnée.
3. Dans le champ Nœud de hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.
    * Développez la hiérarchie pour sélectionner 094.  
4. Dans le champ Nœud de hiérarchie des dimensions d'élément de coût, entrez ou sélectionnez une valeur.
    * Sélectionnez Autres dépenses d'exploitation, puis sélectionnez 605110 Nettoyage.  
5. Dans le champ Comportement de coûts, sélectionnez une option.
    * Sélectionnez Coût fixe.  
6. Dans le champ Base de répartition, entrez ou sélectionnez une valeur.
7. Cliquez sur Nouveau.
8. Dans la liste, marquer la ligne sélectionnée.
9. Dans le champ Nœud de hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.
    * Développez la hiérarchie pour sélectionner 094.  
10. Dans le champ Nœud de hiérarchie des dimensions d'élément de coût, entrez ou sélectionnez une valeur.
    * Sélectionnez Autres dépenses d'exploitation, puis sélectionnez 605150 Loyer.  
11. Dans le champ Comportement de coûts, sélectionnez une option.
    * Sélectionnez Coût fixe.  
12. Dans le champ Base de répartition, entrez ou sélectionnez une valeur.
13. Cliquez sur Enregistrer.

## <a name="assign-rules-to-a-cost-control-unit"></a>Affecter des règles à une unité de contrôle des coûts
1. Cliquez sur Affectations de stratégie pour l'unité de contrôle des coûts.
2. Cliquez sur Nouveau.
3. Dans la liste, marquez la ligne sélectionnée.
4. Dans le champ Valide à partir de la date comptable, entrez une date.
    * Sélectionnez le 1er septembre dans l'exercice valide.  
5. Dans le champ Unité de contrôle des coûts, entrez ou sélectionnez une valeur.
6. Cliquez sur Enregistrer.


