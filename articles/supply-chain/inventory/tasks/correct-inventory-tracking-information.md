---
title: Corriger les informations de suivi de stock
description: Cette procédure vous guide dans le processus de création et de validation d’un journal de transfert de stock afin de corriger les informations de suivi de stock.
author: yufeihuang
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventBatchIdLookup, InventLocationIdLookup, InventDimTracking, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 69921651ecd0969e9cdd3cdd3740db212a1953e1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573799"
---
# <a name="correct-inventory-tracking-information"></a>Corriger les informations de suivi de stock

[!include [banner](../../includes/banner.md)]

Cette procédure vous guide dans le processus de création et de validation d’un journal de transfert de stock afin de corriger les informations de suivi de stock. Dans cet exemple, nous allons mettre à jour les informations d’un article contrôlé via le traitement par lots en modifiant un traitement par lots incorrectement enregistré vers un autre traitement par lots. Vous pouvez parcourir cette procédure dans la société fictive de démonstration USPI ou en utilisant vos propres données. Si vous utilisez vos propres données, vous devez posséder un article pour lequel le traitement par lots est activé, et qui ne doit pas être contrôlé par emplacement. Vous devez également avoir configuré un nom de journal de stock pour les transferts de stock. Ces tâches sont normalement effectuées par un employé de l’entrepôt.


## <a name="create-an-inventory-transfer-journal"></a>Créer un journal de transfert de stock
1. Accédez à Transférer.
2. Cliquez sur Nouveau.
3. Saisissez ou sélectionnez une valeur dans le champ Nom.
4. Cliquez sur OK.

## <a name="create-journal-lines"></a>Créer des lignes de journal
1. Cliquez sur Nouveau.
2. Entrez ou sélectionnez une valeur dans le champ Numéro d’article.
    * Si vous utilisez USPI, sélectionnez l’article M5003.  
3. Dans le champ Quantité, entrer un numéro.
4. Cliquez sur l’onglet Dimensions de stock.
5. Dans le champ Numéro de lot, entrez ou sélectionnez une valeur.
6. Saisissez ou sélectionnez une valeur dans le champ Site.
7. Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.
8. Dans le champ Numéro de lot, entrez ou sélectionnez une valeur.

## <a name="post-the-journal"></a>Valider le journal
1. Cliquez sur Valider.
2. Cliquez sur OK.

## <a name="check-tracing-information"></a>Vérifier les informations de suivi
1. Cliquez sur Stock.
2. Cliquez sur Traçabilité.
3. Cliquez sur OK.
    * À l’aide de ces informations de suivi, vous pouvez effectuer un suivi à rebours du traitement par lots à partir duquel vous avez corrigé le stock.  Vous pouvez également utiliser la page Suivi des articles pour afficher ces informations.  
4. Fermez la page.

## <a name="check-inventory-transactions"></a>Vérifier les mouvements de stock
1. Cliquez sur Stock.
2. Cliquez sur Transactions.
    * Ici vous pouvez afficher les transactions créées lorsque vous avez validé votre journal.   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]