--- 
title: "Créer et affecter une stratégie d'affectation des coûts à une unité de contrôle des coûts"
description: "Cette procédure permet de créer et d'affecter une stratégie de répartition des coûts et les règles correspondantes à une unité de contrôle des coûts."
author: YuyuScheller
manager: AnnBe
ms.date: 06/28/2017
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
ms.openlocfilehash: 82319d8d9c7b567f98dfd0e591cb99079fb577b7
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a>Créer et affecter une stratégie d'affectation des coûts à une unité de contrôle des coûts

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure permet de créer et d'affecter une stratégie de répartition des coûts et les règles correspondantes à une unité de contrôle des coûts. Cet enregistrement utilise la société fictive USP2.


## <a name="create-a-policy"></a>Créer une stratégie
1. Accédez à Contrôle de gestion > Stratégies > Stratégies de répartition des coûts.
2. Cliquez sur Nouveau.
3. Dans le champ Nom de la stratégie, tapez une valeur.
4. Dans le champ Hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.
    * Sélectionnez Organisation.  
5. Dans le champ Dimension statistique, entrez ou sélectionnez une valeur.
6. Cliquez sur Enregistrer.

## <a name="create-allocation-rules"></a>Créer des règles de répartition
1. Cliquez sur Nouveau.
2. Dans la liste, marquez la ligne sélectionnée.
3. Dans le champ Nœud de hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.
4. Dans le champ Comportement de coût, sélectionnez « Total ».
5. Dans le champ Base de répartition, entrez ou sélectionnez une valeur.
6. Cliquez sur Nouveau.
7. Dans la liste, marquer la ligne sélectionnée.
8. Dans le champ Nœud de hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.
9. Dans le champ Comportement de coût, sélectionnez « Total ».
10. Dans le champ Base de répartition, entrez ou sélectionnez une valeur.
11. Cliquez sur Nouveau.
12. Dans la liste, marquer la ligne sélectionnée.
13. Dans le champ Nœud de hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.
14. Dans le champ Comportement de coût, sélectionnez « Total ».
15. Dans le champ Base de répartition, entrez ou sélectionnez une valeur.
    * Continuez jusqu'à ce que vous ayez créé toutes les règles.  
16. Cliquez sur Enregistrer.

## <a name="assign-the-policy-to-a-cost-control-unit"></a>Affecter la stratégie à une unité de contrôle des coûts
1. Cliquez sur Affectations de stratégie pour l'unité de contrôle des coûts.
2. Cliquez sur Nouveau.
3. Dans la liste, marquez la ligne sélectionnée.
4. Dans le champ Valide à partir de la date comptable, entrez une date.
    * Les règles ont une date d'effet. Un utilisateur ou le système peut faire expirer les règles si une version plus récente est créée.  
5. Dans le champ Unité de contrôle des coûts, entrez ou sélectionnez une valeur.
6. Cliquez sur Enregistrer.

