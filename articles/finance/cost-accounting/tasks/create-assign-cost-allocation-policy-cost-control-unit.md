---
title: Créer et affecter une stratégie d’affectation des coûts à une unité de contrôle des coûts
description: Cette procédure permet de créer et d’affecter une stratégie de répartition des coûts et les règles correspondantes à une unité de contrôle des coûts.
author: ShylaThompson
manager: AnnBe
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostAccountingLedgerPolicyAssignment
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b22dba0106721c095e6ce2e9b76cb9f5267e1c28
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208725"
---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a>Créer et affecter une stratégie d’affectation des coûts à une unité de contrôle des coûts

[!include [banner](../../includes/banner.md)]

Cette procédure permet de créer et d’affecter une stratégie de répartition des coûts et les règles correspondantes à une unité de contrôle des coûts. Cet enregistrement utilise la société fictive USP2.


## <a name="create-a-policy"></a>Créer une stratégie
1. Accédez à Contrôle de gestion > Stratégies > Stratégies de répartition des coûts.
2. Cliquez sur Nouveau.
3. Dans le champ Nom de la stratégie, tapez une valeur.
4. Dans le champ Hiérarchie des dimensions d’objet de coût, entrez ou sélectionnez une valeur.
    * Sélectionnez Organisation.  
5. Dans le champ Dimension statistique, entrez ou sélectionnez une valeur.
6. Cliquez sur Enregistrer.

## <a name="create-allocation-rules"></a>Créer des règles de répartition
1. Cliquez sur Nouveau.
2. Dans la liste, marquez la ligne sélectionnée.
3. Dans le champ Nœud de hiérarchie des dimensions d’objet de coût, entrez ou sélectionnez une valeur.
4. Dans le champ Comportement de coût, sélectionnez « Total ».
5. Dans le champ Base de répartition, entrez ou sélectionnez une valeur.
6. Cliquez sur Nouveau.
7. Dans la liste, marquer la ligne sélectionnée.
8. Dans le champ Nœud de hiérarchie des dimensions d’objet de coût, entrez ou sélectionnez une valeur.
9. Dans le champ Comportement de coût, sélectionnez « Total ».
10. Dans le champ Base de répartition, entrez ou sélectionnez une valeur.
11. Cliquez sur Nouveau.
12. Dans la liste, marquer la ligne sélectionnée.
13. Dans le champ Nœud de hiérarchie des dimensions d’objet de coût, entrez ou sélectionnez une valeur.
14. Dans le champ Comportement de coût, sélectionnez « Total ».
15. Dans le champ Base de répartition, entrez ou sélectionnez une valeur.
    * Continuez jusqu’à ce que vous ayez créé toutes les règles.  
16. Cliquez sur Enregistrer.

## <a name="assign-the-policy-to-a-cost-control-unit"></a>Affecter la stratégie à une unité de contrôle des coûts
1. Cliquez sur Affectations de stratégie pour l’unité de contrôle des coûts.
2. Cliquez sur Nouveau.
3. Dans la liste, marquez la ligne sélectionnée.
4. Dans le champ Valide à partir de la date comptable, entrez une date.
    * Les règles ont une date d’effet. Un utilisateur ou le système peut faire expirer les règles si une version plus récente est créée.  
5. Dans le champ Unité de contrôle des coûts, entrez ou sélectionnez une valeur.
6. Cliquez sur Enregistrer.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]