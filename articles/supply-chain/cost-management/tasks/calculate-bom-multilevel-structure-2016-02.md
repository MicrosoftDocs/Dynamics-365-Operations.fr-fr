--- 
title: "Calculer une nomenclature à l'aide d'une structure à plusieurs niveaux (février 2016 uniquement)"
description: "Cette procédure montre comment calculer le coût d'un produit fini à l'aide d'un éclatement à plusieurs niveaux basé sur la feuille de coûts."
author: YuyuScheller
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 16c2cacaf70df5455c3ed49b8dcb5756e89f8cb8
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="calculate-a-bom-by-using-a-multilevel-structure-february-2016-only"></a>Calculer une nomenclature à l'aide d'une structure à plusieurs niveaux (février 2016 uniquement)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure montre comment calculer le coût d'un produit fini à l'aide d'un éclatement à plusieurs niveaux basé sur la feuille de coûts. Il s'agit de la septième tâche de la série de calculs des nomenclatures. Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.

1. Allez à Gestion des informations sur les produits > Produits > Produits lancés.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Sélectionnez le produit BOM_1.  
3. Cliquez sur Gérer les coûts dans le volet Actions.
4. Cliquez sur Prix de l'article.
5. Cliquez sur Calculer le coût de l'article.
    * Il vous faudra peut-être cliquer sur les points de suspension (…) pour afficher cette option du menu supérieur.  
6. Dans le champ Version d'évaluation des coûts, saisissez ou sélectionnez une valeur.
    * Sélectionnez Version d'évaluation des coûts 20, car elle est de type Coût prévu et le mode Éclatement est Plusieurs niveaux.   Le mode Éclatement à plusieurs niveaux est pour les coûts planifiés et les simulations. Il n'est pas utilisé pour le coût standard.  
7. Cliquez sur OK.
8. Cliquez sur Afficher les détails du calcul.
    * Il vous faudra peut-être cliquer sur les points de suspension (…) pour afficher cette option du menu supérieur.  Dans ce cas, notez la façon dont BOM_2 a été calculé, en prenant en compte la matière première, le processus, et les frais généraux avec un total de 29,40 au lieu du coût standard de 10 qui a été activé dans le premier Guide de tâche de cette série.  
9. Cliquez sur l'onglet Feuille de coûts.
    * Dans l'onglet Feuille de coûts, les totaux par groupe de coûts sont différents comparés au calcul effectué dans le Guide de tâche précédent.  
10. Dans le champ Niveau, sélectionnez Multi.
    * En sélectionnant Multi, les coûts sont classés selon la composition de BOM_2, où 10 est dérivé du groupe de coûts M1 (ITEM_C), et 15,60 est dérivé de sa fabrication dans lequel le groupe de coûts est L2. Les coûts indirects varient également.  
11. Fermez la page.
12. Fermez la page.


