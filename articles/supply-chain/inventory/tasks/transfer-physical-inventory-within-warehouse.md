---
title: Transférer du stock physique au sein de l’entrepôt
description: Cette procédure vous accompagne dans le processus de création et de validation d’un journal de transfert de stock en vue d’enregistrer le mouvement d’un article à partir d’un emplacement dans un entrepôt vers un autre.
author: MarkusFogelberg
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a298f05185f3c81f2fde995e4d731b95a5f8d870
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832104"
---
# <a name="transfer-physical-inventory-within-the-warehouse"></a>Transférer du stock physique au sein de l’entrepôt

[!include [banner](../../includes/banner.md)]

Cette procédure vous accompagne dans le processus de création et de validation d’un journal de transfert de stock en vue d’enregistrer le mouvement d’un article à partir d’un emplacement dans un entrepôt vers un autre. Avant de commencer, vous devez avoir configuré un nom de journal de stock pour les transferts de stock. Vous pouvez suivre cette procédure avec les données de démonstration de la société fictive USMF à l’aide des valeurs d’exemple affichées, ou utiliser vos propres données si vous avez des produits et des emplacements configurés. Ces tâches sont normalement effectuées par un employé de l’entrepôt.


## <a name="create-an-inventory-transfer-journal"></a>Créer un journal de transfert de stock
1. Dans le **Volet de navigation**, accédez à **Gestion des stocks > Entrées de journal > Articles > Transfert**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Nom**, saisissez ou sélectionnez une valeur.
4. Cliquez sur **OK**. Il existe l’option pour spécifie les dimensions « À partir de » et « Vers » pour chaque ligne de journal. Ce sont des éléments essentiels pour ce type de journal. Vous pouvez transférer des articles à des emplacements en utilisant des règles différentes. Dans cet exemple nous allons transférer un article au sein du même entrepôt, à partir d’un emplacement contrôlé par contenant vers un emplacement qui ne fait pas l’objet d’un contrôle de contenant.   

## <a name="create-journal-lines"></a>Créer des lignes de journal
1. Dans l’**organisateur Lignes du journal**, cliquez sur **Nouveau**.
2. Entrez ou sélectionnez une valeur dans le champ **Numéro d’article**. Si vous utilisez USMF, vous pouvez sélectionner A0001.  
3. Dans le champ **Site d’origine**, saisissez ou sélectionnez une valeur. Si vous utilisez USMF, vous pouvez sélectionner 2.  
4. Dans le champ **Site de destination**, saisissez ou sélectionnez une valeur. Si vous utilisez USMF, vous pouvez sélectionner 2.  
5. Dans le champ **Entrepôt d’origine**, saisissez ou sélectionnez une valeur. Si vous utilisez USMF, vous pouvez sélectionner 24.  
6. Dans le champ **Entrepôt de destination**, saisissez ou sélectionnez une valeur. Si vous utilisez USMF, vous pouvez sélectionner 24.  
7. Saisissez ou sélectionnez une valeur dans le champ **Emplacement d’origine**. Si vous utilisez USMF, vous pouvez sélectionner FL-001.  
8. Saisissez ou sélectionnez une valeur dans le champ **Emplacement de destination**. Si vous utilisez USMF, vous pouvez sélectionner BULK-001.  
9. Entrez un nombre dans le champ **Quantité**.
10. Dans l’organisateur **Détails de ligne**, cliquez sur l’onglet **Dimensions de stock**.
11. Dans **Des dimensions de stock**, dans le champ **Contenant**, entrez ou sélectionnez une valeur. Si vous utilisez USMF, vous pouvez sélectionner 24.  
12. Cliquez sur **Enregistrer**.

## <a name="post-the-inventory-transfer-journal"></a>Valider le journal de transfert de stock
1. Cliquez sur **Valider** dans le volet **Actions**.
2. Cliquez sur **OK**.

## <a name="view-inventory-transactions"></a>Afficher les mouvements de stock
1. Cliquez sur **Stock**.
2. Cliquez sur **Transactions**. Ici vous pouvez afficher les transactions créées lorsque vous avez validé votre journal.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]