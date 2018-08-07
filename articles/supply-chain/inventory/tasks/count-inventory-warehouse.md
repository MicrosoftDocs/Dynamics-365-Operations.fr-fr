---
title: "Énumérer le stock dans un entrepôt"
description: "Cette procédure vous accompagne au long du processus de création et de validation d'un journal de comptage du stock en vue de compter un article particulier à un emplacement dans l'entrepôt."
author: MarkusFogelberg
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fa72cb0d651f5e60797fa41f6e2b2cf1891730b5
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="count-inventory-in-a-warehouse"></a>Énumérer le stock dans un entrepôt

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure vous accompagne au long du processus de création et de validation d'un journal de comptage du stock en vue de compter un article particulier à un emplacement dans l'entrepôt. Cette procédure s'applique à la fonctionnalité « entreposage de base », disponible dans le module Gestion des stocks, et pas à la fonctionnalité d'entreposage disponible dans le module Gestion des entrepôts. Vous pouvez parcourir cette procédure dans la société fictive USMF ou utiliser vos propres données. Si vous utilisez vos propres données, vérifiez que vous avez des produits et des emplacements configurés, et que vous avez créé un nom de journal de stock pour les journaux de comptage. Le comptage de stock est normalement effectué par un employé de l'entrepôt.


## <a name="create-an-inventory-counting-journal"></a>Créer un journal de comptage du stock
1. Accédez à Gestion des stocks > Entrées de journal > Inventaire des articles > Comptage.
2. Cliquez sur Nouveau.
3. Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, cliquez sur le nom du journal de comptage du stock que vous souhaitez utiliser.
    * Certains autres champs seront remplis en fonction du paramétrage du nom du journal de comptage du stock que vous avez sélectionné.  
5. Dans le champ Collaborateur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
6. Dans la liste, sélectionnez le collaborateur que vous souhaitez utiliser.
7. Cliquez sur Sélectionner.
8. Cliquez sur OK.

## <a name="create-journal-lines"></a>Créer des lignes de journal
1. Cliquez sur Nouveau.
2. Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
3. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Si vous utilisez les données de démonstration de la société USMF, sélectionnez « A0001 ».  
4. Dans le champ Site, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Si vous utilisez les données de démonstration de la société USMF, sélectionnez le site « 2 ».  
6. Dans le champ Entrepôt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
7. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Si vous utilisez les données de démonstration de la société USMF, sélectionnez l'entrepôt « 24 ».  
8. Dans le champ Emplacement, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
9. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Si vous utilisez les données de démonstration de la société USMF, sélectionnez l'emplacement « BULK-001 ».  
10. Dans le champ Compté, entrer un nombre.
    * Si vous entrez un nombre compté local différent du nombre indiqué dans le champ Disponible, le champ Quantité est mis à jour pour indiquer l'écart.  
11. Cliquez sur Enregistrer.

## <a name="post-the-inventory-counting-journal"></a>Valider le journal de comptage du stock
1. Cliquez sur Valider.
    * Lorsque vous validez un journal de comptage du stock, si la quantité comptée diffère de la quantité déclarée dans le champ Disponible quand un bon de réception ou de sortir du stock est validé, le niveau et la valeur du stock sont modifiés et les transactions comptables sont générées.  
2. Cliquez sur OK.

## <a name="view-inventory-transactions"></a>Afficher les mouvements de stock
1. Cliquez sur Stock.
2. Cliquez sur Transactions.
    * Voici que vous pouvez afficher toutes les transactions associées qui seront créées lorsque vous validerez votre journal de comptage du stock.   

