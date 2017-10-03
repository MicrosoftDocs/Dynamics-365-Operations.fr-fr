--- 
title: "Créer une stratégie de repositionnement des coûts"
description: "Cette procédure indique comment créer une stratégie de repositionnement des coûts et créer des règles pour la stratégie."
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
ms.openlocfilehash: 51fabc8fe17a45d104be5da806d7076bcf9c5dbb
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-cost-rollup-policy"></a>Créer une stratégie de repositionnement des coûts

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure indique comment créer une stratégie de repositionnement des coûts et créer des règles pour la stratégie. Les données de démonstration utilisées pour créer cette procédure sont USP2.


## <a name="create-a-policy"></a>Créer une stratégie
1. Accédez à Contrôle de gestion > Stratégies > Stratégies de repositionnement des coûts.
2. Cliquez sur Nouveau.
3. Dans le champ Nom de la stratégie, tapez une valeur.
4. Dans le champ Description, entrez une valeur.
5. Dans le champ Hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.
    * Sélectionnez le centre de coût Repositionnement des coûts.  
6. Dans le champ Hiérarchie des dimensions d'élément de coût, entrez ou sélectionnez une valeur.
    * Sélectionnez le centre de coût Repositionnement des coûts.  
7. Cliquez sur Enregistrer.

## <a name="create-rules-for-the-cost-rollup-policy"></a>Créer des règles pour la stratégie de repositionnement des coûts
1. Cliquez sur Nouveau.
2. Dans la liste, marquez la ligne sélectionnée.
3. Dans le champ Nœud de hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.
    * Sélectionnez 007.  
4. Dans le champ Nœud de hiérarchie des dimensions d'élément de coût, entrez ou sélectionnez une valeur.
    * Sélectionnez le CE Repositionnement des coûts.  
5. Dans le champ Élément de coût secondaire, entrez ou sélectionnez une valeur.
    * Pour cet exemple, mettez en correspondance l'élément de coût secondaire CC-007 avec le centre de coût.  
6. Cliquez sur Nouveau.
7. Dans la liste, marquez la ligne sélectionnée.
8. Dans le champ Nœud de hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.
    * Sélectionnez 008.  
9. Dans le champ Nœud de hiérarchie des dimensions d'élément de coût, entrez ou sélectionnez une valeur.
    * Sélectionnez le CE Repositionnement des coûts.  
10. Dans le champ Élément de coût secondaire, entrez ou sélectionnez une valeur.
    * Pour cet exemple, mettez en correspondance l'élément de coût secondaire CC-008 avec le centre de coût.  
11. Cliquez sur Nouveau.
12. Dans la liste, marquez la ligne sélectionnée.
13. Dans le champ Nœud de hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.
    * Sélectionnez 009.  
14. Dans le champ Nœud de hiérarchie des dimensions d'élément de coût, entrez ou sélectionnez une valeur.
    * Sélectionnez le CE Repositionnement des coûts.  
15. Dans le champ Élément de coût secondaire, entrez ou sélectionnez une valeur.
    * Pour cet exemple, mettez en correspondance l'élément de coût secondaire CC-009 avec le centre de coût.  
    * Continuez jusqu'à ce que tous les centres de coût soient mis en correspondance avec leurs éléments de coût secondaires correspondants.  
16. Cliquez sur Enregistrer.

