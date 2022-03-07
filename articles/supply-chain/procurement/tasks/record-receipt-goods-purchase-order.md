---
title: Enregistrer la réception de marchandises sur la commande fournisseur
description: Cette rubrique explique comment enregistrer la réception des marchandises directement sur une commande fournisseur.
author: RichardLuan
manager: tfehr
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d016df08850c75858c50b7f9a97b11b566d26cb0
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5022656"
---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a>Enregistrer la réception de marchandises sur la commande fournisseur

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment enregistrer la réception des marchandises directement sur une commande fournisseur. Il est également possible d'enregistrer l'accusé de réception de marchandises dans l'entrepôt, puis de l'enregistrer ultérieurement dans la commande fournisseur. Cette tâche est généralement effectuée par un agent des achats ou un coordinateur de Comptabilité fournisseur. L'exemple indiqué dans ce guide peut être utilisé dans les données fictives de la société USMF. L'exemple inclut des étapes pour créer une commande fournisseur simple de sorte que vous puissiez suivre la procédure comme un guide de tâche. Si vous suiviez cette procédure sur vos propres données, vous commenceriez par la sous-tâche **Enregistrer la réception de marchandises**.


## <a name="prepare-a-new-purchase-order-for-receipt-of-goods"></a>Préparer une nouvelle commande fournisseur pour la réception des marchandises
1. Allez dans **Volet de navigation > Modules > Approvisionnements > Commandes fournisseur > Toutes les commandes fournisseur**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Compte fournisseur**, saisissez `US-101`.
4. Cliquez sur **OK**.
5. Dans le champ **Numéro d'article**, entrez `M0001`.
6. Entrez `5` dans le champ **Quantité**.
7. Dans le volet Action, sélectionnez **Achat**.
8. Sélectionnez **Confirmer**.

## <a name="record-receipt-of-goods"></a>Enregistrer la réception de marchandises
1. Dans le volet Actions, sélectionnez **Recevoir**.
2. Sélectionnez **Accusé de réception de marchandises**. Le champ **Quantité** vous permet de choisir différentes options pour la quantité que vous voulez recevoir. Par exemple, si une quantité a été précédemment enregistrée dans l'entrepôt, vous pouvez sélectionner **Quantité enregistrée**. Pour cet exemple, utilisez la valeur **Quantité commandée**.
3. Développez la section **Vue d'ensemble**.
4. Tapez une valeur quelconque dans le champ **Accusé de réception de marchandises**. Ce champ permet d'entrer une référence qui sera utilisée comme N° document pour le journal de réception de marchandises.  
5. Développez la section **Lignes**.
6. Définissez le champ **Quantité** sur « 4 ». Ici vous pouvez spécifier manuellement la quantité reçue pour chaque ligne de la commande.  
7. Cliquez sur **OK**. Les marchandises sont désormais enregistrées comme reçues sur la commande fournisseur, et un journal des accusés de réception de marchandises est créé comme document pour refléter ceci. Vous pouvez utiliser l'action Accusé de réception de marchandises pour passer en revue les journaux créés avec la commande fournisseur, et voir ce qui a été reçu, et quand.  

