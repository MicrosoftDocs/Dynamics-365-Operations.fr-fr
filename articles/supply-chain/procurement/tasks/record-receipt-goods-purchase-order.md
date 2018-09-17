--- 
title: "Enregistrer la réception de marchandises sur la commande fournisseur"
description: "Cette procédure vous montre comment enregistrer la réception des marchandises directement sur une commande fournisseur."
author: FrankDahl
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 9b2300a593c9e153ee598fa72e29907c82f2b79e
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a>Enregistrer la réception de marchandises sur la commande fournisseur

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure vous montre comment enregistrer la réception des marchandises directement sur une commande fournisseur. Il est également possible d'enregistrer l'accusé de réception de marchandises dans l'entrepôt, puis de l'enregistrer ultérieurement dans la commande fournisseur. Cette tâche est généralement effectuée par un agent des achats ou un coordinateur de Comptabilité fournisseur. L'exemple indiqué dans ce guide peut être utilisé dans les données fictives de la société USMF. L'exemple inclut des étapes pour créer une commande fournisseur simple de sorte que vous puissiez suivre la procédure comme un guide de tâche. Si vous suiviez cette procédure sur vos propres données, vous commenceriez par la sous-tâche Enregistrer la réception de marchandises.


## <a name="prepare-a-new-purchase-order-for-receipt-of-goods"></a>Préparer une nouvelle commande fournisseur pour la réception des marchandises
1. Accédez à Approvisionnements > Commandes fournisseur > Toutes les commandes fournisseur.
2. Cliquez sur Nouveau.
3. Tapez US-101 dans le champ Compte fournisseur.
4. Cliquez sur OK.
5. Entrez M0001 dans le champ Numéro d'article.
6. Entrez 5 dans le champ Quantité.
7. Cliquez sur Achats dans le volet Actions.
8. Cliquez sur Confirmer.

## <a name="record-receipt-of-goods"></a>Enregistrer la réception de marchandises
1. Dans le volet Actions, cliquez sur Recevoir.
2. Cliquez sur Accusé de réception de marchandises.
    * Le champ Quantité vous permet de choisir différentes options pour la quantité que vous voulez recevoir. Par exemple, si une quantité a été précédemment enregistrée dans l'entrepôt, vous pouvez sélectionner Quantité enregistrée.  Pour cet exemple, utilisez la valeur Quantité commandée.   
3. Tapez une valeur quelconque dans le champ Accusé de réception de marchandises.
    * Ce champ permet d'entrer une référence qui sera utilisée comme N° document pour le journal de réception de marchandises.  
4. Développez la section Lignes.
5. Définir la Quantité sur « 4 ».
    * Ici vous pouvez spécifier manuellement la quantité reçue pour chaque ligne de la commande.  
6. Réduisez la section Lignes.
7. Cliquez sur OK.
    * Les marchandises sont désormais enregistrées comme reçues sur la commande fournisseur, et un journal des accusés de réception de marchandises est créé comme document pour refléter ceci. Vous pouvez utiliser l'action Accusé de réception de marchandises pour passer en revue les journaux créés avec la commande fournisseur, et voir ce qui a été reçu, et quand.  


