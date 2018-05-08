---
title: "Transférer du stock physique au sein de l'entrepôt"
description: "Cette procédure vous accompagne dans le processus de création et de validation d'un journal de transfert de stock en vue d'enregistrer le mouvement d'un article à partir d'un emplacement dans un entrepôt vers un autre."
author: MarkusFogelberg
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: bfba69731a4897906d08ff9fb9ce69e79121efeb
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="transfer-physical-inventory-within-the-warehouse"></a>Transférer du stock physique au sein de l'entrepôt

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure vous accompagne dans le processus de création et de validation d'un journal de transfert de stock en vue d'enregistrer le mouvement d'un article à partir d'un emplacement dans un entrepôt vers un autre. Avant de commencer, vous devez avoir configuré un nom de journal de stock pour les transferts de stock. Vous pouvez suivre cette procédure avec les données de démonstration de la société fictive USMF à l'aide des valeurs d'exemple affichées, ou utiliser vos propres données si vous avez des produits et des emplacements configurés. Ces tâches sont normalement effectuées par un employé de l'entrepôt.


## <a name="create-an-inventory-transfer-journal"></a>Créer un journal de transfert de stock
1. Accédez à Transférer.
2. Cliquez sur Nouveau.
3. Saisissez ou sélectionnez une valeur dans le champ Nom.
4. Cliquez sur OK.
    * Il existe l'option pour spécifie les dimensions « À partir de » et « Vers » pour chaque ligne de journal. Ce sont des éléments essentiels pour ce type de journal. Vous pouvez transférer des articles à des emplacements en utilisant des règles différentes. Dans cet exemple nous allons transférer un article au sein du même entrepôt, à partir d'un emplacement contrôlé par contenant vers un emplacement qui ne fait pas l'objet d'un contrôle de contenant.   

## <a name="create-journal-lines"></a>Créer des lignes de journal
1. Cliquez sur Nouveau.
2. Entrez ou sélectionnez une valeur dans le champ Numéro d'article.
    * Si vous utilisez USMF, vous pouvez sélectionner A0001.  
3. Dans le champ Site d'origine, saisissez ou sélectionnez une valeur.
    * Si vous utilisez USMF, vous pouvez sélectionner 2.  
4. Dans le champ Site de destination, saisissez ou sélectionnez une valeur.
    * Si vous utilisez USMF, vous pouvez sélectionner 2.  
5. Dans le champ Entrepôt d'origine, saisissez ou sélectionnez une valeur.
    * Si vous utilisez USMF, vous pouvez sélectionner 24.  
6. Dans le champ Entrepôt de destination, saisissez ou sélectionnez une valeur.
    * Si vous utilisez USMF, vous pouvez sélectionner 24.  
7. Saisissez ou sélectionnez une valeur dans le champ Emplacement d'origine.
    * Si vous utilisez USMF, vous pouvez sélectionner FL-001.  
8. Saisissez ou sélectionnez une valeur dans le champ Emplacement de destination.
    * Si vous utilisez USMF, vous pouvez sélectionner BULK-001.  
9. Dans le champ Quantité, entrer un numéro.
10. Cliquez sur l'onglet Dimensions de stock.
11. Saisissez ou sélectionnez une valeur dans le champ Contenant.
    * Si vous utilisez USMF, vous pouvez sélectionner 24.  
12. Cliquez sur Enregistrer.

## <a name="post-the-inventory-transfer-journal"></a>Valider le journal de transfert de stock
1. Cliquez sur Valider.
2. Cliquez sur OK.

## <a name="view-inventory-transactions"></a>Afficher les mouvements de stock
1. Cliquez sur Stock.
2. Cliquez sur Transactions.
    * Ici vous pouvez afficher les transactions créées lorsque vous avez validé votre journal.  

