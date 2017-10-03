--- 
title: "Créer et affecter une stratégie de comportement des coûts à une unité de contrôle des coûts"
description: "Le comportement de coûts est la classification des coûts comme fixe ou variable."
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
ms.openlocfilehash: 4190fde8c587475f34e5e3fdf6e2d32d59a26022
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="create-and-assign-a-cost-behavior-policy-to-a-cost-control-unit"></a>Créer et affecter une stratégie de comportement des coûts à une unité de contrôle des coûts

[!include[task guide banner](../../includes/task-guide-banner.md)]

Le comportement de coûts est la classification des coûts comme fixe ou variable. Une stratégie et les règles correspondantes doivent être affectées à une unité de contrôle des coûts pour que la stratégie prenne effet. Utilisez cette procédure pour créer une stratégie et l'affecter à une unité de contrôle des coûts.


## <a name="create-a-cost-behavior-hierarchy"></a>Créer une hiérarchie de comportement de coûts
1. Accédez à Contrôle de gestion > Dimensions > Hiérarchies des dimensions.
2. Cliquez sur Nouveau.
3. Cliquez sur Créer.
4. Dans le champ Nom de la hiérarchie des dimensions, tapez « Hiérarchie de comportement de coûts ».
5. Dans le champ Dimension, entrez ou sélectionnez une valeur.
    * Sélectionnez Éléments de coût.  
6. Cliquez sur Enregistrer.
7. Cliquez sur Afficher la hiérarchie.
8. Cliquez sur Nouveau.
9. Dans le champ Nom du nœud, tapez une valeur.
    * Entrez le coût fixe.  
10. Dans l'arborescence, sélectionnez « Hiérarchie de comportement de coûts ».
11. Cliquez sur Nouveau.
12. Dans le champ Nom du nœud, tapez une valeur.
    * Entrez le coût variable.  
13. Cliquez sur Enregistrer.
14. Dans l'arborescence, sélectionnez « Hiérarchie de comportement de coûts\Coût fixe ».
15. Cliquez sur Nouveau.
16. Dans la liste, marquez la ligne sélectionnée.
17. Dans le champ Membre de la dimension de départ, entrez ou sélectionnez une valeur.
    * La plage des membres de dimension peut contenir des écarts, mais les membres ne peuvent pas se chevaucher.  
18. Dans le champ Membre de la dimension de fin, entrez ou sélectionnez une valeur.
    * La plage des membres de dimension peut contenir des écarts, mais les membres ne peuvent pas se chevaucher.  
19. Dans l'arborescence, sélectionnez « Hiérarchie de comportement de coûts\Coût variable ».
20. Cliquez sur Nouveau.
21. Dans la liste, marquez la ligne sélectionnée.
22. Dans le champ Membre de la dimension de départ, entrez ou sélectionnez une valeur.
    * La plage des membres de dimension peut contenir des écarts, mais les membres ne peuvent pas se chevaucher.  
23. Dans le champ Membre de la dimension de fin, entrez ou sélectionnez une valeur.
    * La plage des membres de dimension peut contenir des écarts, mais les membres ne peuvent pas se chevaucher.  
24. Cliquez sur Enregistrer.

## <a name="create-the-policy-and-rules"></a>Créer la stratégie et les règles
1. Accédez à Contrôle de gestion > Stratégies > Stratégies de comportement de coûts.
2. Cliquez sur Nouveau.
3. Dans le champ Nom de la stratégie, tapez une valeur.
4. Dans le champ Hiérarchie des dimensions d'élément de coût, entrez ou sélectionnez une valeur.
    * Sélectionnez la hiérarchie de stratégie que vous venez de créer.  
5. Dans le champ Hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.
    * Sélectionnez Organisation.  
6. Cliquez sur Enregistrer.
7. Cliquez sur Nouveau.
8. Dans la liste, marquez la ligne sélectionnée.
9. Dans le champ Nœud de hiérarchie des dimensions d'élément de coût, entrez ou sélectionnez une valeur.
    * Développez la hiérarchie pour sélectionner Coût variable.  
10. Dans le champ Nœud de hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.
    * Par défaut, le pourcentage variable est 100 %.  
11. Cliquez sur Affectations de stratégie pour l'unité de contrôle des coûts.
12. Cliquez sur Nouveau.
13. Dans la liste, marquez la ligne sélectionnée.
14. Dans le champ Valide à partir de la date comptable, entrez une date.
    * Les règles ont une date d'effet, et un utilisateur ou le système peut faire expirer une règle si une version plus récente est créée.  
15. Dans le champ Unité de contrôle des coûts, entrez ou sélectionnez une valeur.
16. Cliquez sur Enregistrer.

