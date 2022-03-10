---
title: Créer une stratégie de repositionnement des coûts
description: Cette procédure indique comment créer une stratégie de repositionnement des coûts et créer des règles pour la stratégie.
author: ShylaThompson
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fd7a390ced7b7b4997d9c86b9218f1fa83ee14729e450e1ae1cb53dbbd605edb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755664"
---
# <a name="create-a-cost-rollup-policy"></a>Créer une stratégie de repositionnement des coûts

[!include [banner](../../includes/banner.md)]

Cette procédure indique comment créer une stratégie de repositionnement des coûts et créer des règles pour la stratégie. Les données de démonstration utilisées pour créer cette procédure sont USP2.


## <a name="create-a-policy"></a>Créer une stratégie
1. Accédez à Contrôle de gestion > Stratégies > Stratégies de repositionnement des coûts.
2. Cliquez sur Nouveau.
3. Dans le champ Nom de la stratégie, tapez une valeur.
4. Dans le champ Description, entrez une valeur.
5. Dans le champ Hiérarchie des dimensions d’objet de coût, entrez ou sélectionnez une valeur.
    * Sélectionnez le centre de coût Repositionnement des coûts.  
6. Dans le champ Hiérarchie des dimensions d’élément de coût, entrez ou sélectionnez une valeur.
    * Sélectionnez le centre de coût Repositionnement des coûts.  
7. Cliquez sur Enregistrer.

## <a name="create-rules-for-the-cost-rollup-policy"></a>Créer des règles pour la stratégie de repositionnement des coûts
1. Cliquez sur Nouveau.
2. Dans la liste, marquez la ligne sélectionnée.
3. Dans le champ Nœud de hiérarchie des dimensions d’objet de coût, entrez ou sélectionnez une valeur.
    * Sélectionnez 007.  
4. Dans le champ Nœud de hiérarchie des dimensions d’élément de coût, entrez ou sélectionnez une valeur.
    * Sélectionnez le CE Repositionnement des coûts.  
5. Dans le champ Élément de coût secondaire, entrez ou sélectionnez une valeur.
    * Pour cet exemple, mettez en correspondance l’élément de coût secondaire CC-007 avec le centre de coût.  
6. Cliquez sur Nouveau.
7. Dans la liste, marquez la ligne sélectionnée.
8. Dans le champ Nœud de hiérarchie des dimensions d’objet de coût, entrez ou sélectionnez une valeur.
    * Sélectionnez 008.  
9. Dans le champ Nœud de hiérarchie des dimensions d’élément de coût, entrez ou sélectionnez une valeur.
    * Sélectionnez le CE Repositionnement des coûts.  
10. Dans le champ Élément de coût secondaire, entrez ou sélectionnez une valeur.
    * Pour cet exemple, mettez en correspondance l’élément de coût secondaire CC-008 avec le centre de coût.  
11. Cliquez sur Nouveau.
12. Dans la liste, marquez la ligne sélectionnée.
13. Dans le champ Nœud de hiérarchie des dimensions d’objet de coût, entrez ou sélectionnez une valeur.
    * Sélectionnez 009.  
14. Dans le champ Nœud de hiérarchie des dimensions d’élément de coût, entrez ou sélectionnez une valeur.
    * Sélectionnez le CE Repositionnement des coûts.  
15. Dans le champ Élément de coût secondaire, entrez ou sélectionnez une valeur.
    * Pour cet exemple, mettez en correspondance l’élément de coût secondaire CC-009 avec le centre de coût.  
    * Continuez jusqu’à ce que tous les centres de coût soient mis en correspondance avec leurs éléments de coût secondaires correspondants.  
16. Cliquez sur Enregistrer.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]