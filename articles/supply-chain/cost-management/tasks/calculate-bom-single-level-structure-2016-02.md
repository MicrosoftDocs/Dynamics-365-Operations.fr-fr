---
title: Calculer une nomenclature à l'aide d'une même structure de niveaux (février 2016)
description: Cette procédure montre comment calculer le coût d'un produit fini à l'aide d'un éclatement à un seul niveau basé sur la feuille de coûts.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventItemPrice, BOMCalcDialog
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c1968703c7e9662b5cccdb71d049010bb4bd4534
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1836502"
---
# <a name="calculate-a-bom-by-using-a-single-level-structure-february-2016"></a>Calculer une nomenclature à l'aide d'une même structure de niveaux (février 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure montre comment calculer le coût d'un produit fini à l'aide d'un éclatement à un seul niveau basé sur la feuille de coûts. Il s'agit de la sixième tâche de la série de calculs des nomenclatures. Les données fictives utilisées pour créer cette tâche correspondent à la société USMF.

1. Allez dans Produits lancés.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Sélectionnez le produit BOM_1.  
3. Cliquez sur Gérer les coûts dans le volet Actions.
4. Cliquez sur Prix de l'article.
5. Cliquez sur Calculer le coût de l'article.
    * Il vous faudra peut-être cliquer sur les points de suspension (…) pour afficher cette option du menu supérieur.  
6. Dans le champ Version d'évaluation des coûts, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Pour cette démonstration, sélectionnez 10. Il s'agit de la même version d'évaluation des coûts utilisée pour ajouter le prix de revient aux composants.  
7. Cliquez sur OK.
8. Cliquez sur Afficher les détails du calcul.
    * Il vous faudra peut-être cliquer sur les points de suspension (…) pour afficher cette option du menu supérieur.    Voici la composition du coût : •    10 est dérivé d'ITEM_A, 10 d'ITEM_B, 10 de BOM_2. Dans ce cas, il n'existe aucun détail pour BOM_2, car il a été entré comme coût standard de 10 mais n'a pas été obtenu via le calcul.  •  7 est dérivé du temps de réglage, qui est un coût constant, et le chiffre 7 supplémentaire est dérivé de l'opération d'exécution (processus).  •   Il existe également d'autres montants qui correspondent aux coûts indirects.  
9. @SysTaskRecorder:_RequestClose

