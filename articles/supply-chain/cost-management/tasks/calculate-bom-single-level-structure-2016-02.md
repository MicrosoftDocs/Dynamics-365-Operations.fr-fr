---
title: Calculer une nomenclature à l’aide d’une même structure de niveaux (février 2016)
description: Cette procédure montre comment calculer le coût d’un produit fini à l’aide d’un éclatement à un seul niveau basé sur la feuille de coûts.
author: AndersGirke
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventItemPrice, BOMCalcDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8c5968631f5fed8a43cd63165a4ddff86e8cb4b4
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572095"
---
# <a name="calculate-a-bom-by-using-a-single-level-structure-february-2016"></a>Calculer une nomenclature à l’aide d’une même structure de niveaux (février 2016)

[!include [banner](../../includes/banner.md)]

Cette procédure montre comment calculer le coût d’un produit fini à l’aide d’un éclatement à un seul niveau basé sur la feuille de coûts. Il s’agit de la sixième tâche de la série de calculs des nomenclatures. Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.

1. Allez dans Produits lancés.
2. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
    * Sélectionnez le produit BOM_1.  
3. Cliquez sur Gérer les coûts dans le volet Actions.
4. Cliquez sur Prix de l’article.
5. Cliquez sur Calculer le coût de l’article.
    * Il vous faudra peut-être cliquer sur les points de suspension (…) pour afficher cette option du menu supérieur.  
6. Dans le champ Version d’évaluation des coûts, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Pour cette démonstration, sélectionnez 10. Il s’agit de la même version d’évaluation des coûts utilisée pour ajouter le prix de revient aux composants.  
7. Cliquez sur OK.
8. Cliquez sur Afficher les détails du calcul.
    * Il vous faudra peut-être cliquer sur les points de suspension (…) pour afficher cette option du menu supérieur.    Voici la composition du coût :  *    10 est dérivé d’ITEM_A, 10 d’ITEM_B, 10 de BOM_2. Dans ce cas, il n’existe aucun détail pour BOM_2, car il a été entré comme coût standard de 10 mais n’a pas été obtenu via le calcul.  *    7 est dérivé du temps de réglage, qui est un coût constant, et le chiffre 7 supplémentaire est dérivé de l’opération d’exécution (processus).  *    Il existe également d’autres montants qui correspondent aux coûts indirects.  
9. @SysTaskRecorder:_RequestClose



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]