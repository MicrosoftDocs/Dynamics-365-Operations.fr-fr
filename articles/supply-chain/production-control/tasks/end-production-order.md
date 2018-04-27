---
title: Terminer un ordre de fabrication
description: "Cette procédure permet d'indiquer comment mettre fin à un ordre de fabrication."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: dadf0e87eac8522f61bb094c146e37f46a21fc09
ms.openlocfilehash: 1cc586f804a072ca5499c73ecdf7d37778cbf067
ms.contentlocale: fr-fr
ms.lasthandoff: 02/06/2018

---
# <a name="end-a-production-order"></a>Terminer un ordre de fabrication

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure permet d'indiquer comment mettre fin à un ordre de fabrication. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Il s'agit de la dernière des sept procédures expliquant le cycle de vie de l'ordre de fabrication.


## <a name="end-a-production-order"></a>Terminer un ordre de fabrication
1. Accédez à Contrôle de la production > Ordres de fabrication > Tous les ordres de fabrication.
    * Sélectionnez un ordre de fabrication dont le statut est Déclaré terminé.  
2. Cliquez sur Ordre de fabrication dans le volet Actions.
3. Cliquez sur Fin.
    * Dans cette page, vous pouvez confirmer que vous voulez mettre fin à l'ordre de fabrication.  
4. Cliquez sur l'onglet Général.
5. Entrez une date dans le champ Date.
6. Dans le champ Mode de mise au rebut, sélectionnez « Répartition ».
    * Lorsque vous sélectionnez la méthode de répartition, les coûts des matières mises au rebut sont ajoutés à ceux des produits finis.  
7. Cliquez sur OK.

## <a name="validate-calculation-results"></a>Valider les résultats du calcul
1. Cliquez sur Gérer les coûts dans le volet Actions.
2. Cliquez sur Afficher la comparaison du coût.
    * Après avoir terminé l'ordre de fabrication, vous pouvez comparer le prix de revient estimé par rapport au prix de revient réel afin d'obtenir une vue d'ensemble des écarts de production.  

