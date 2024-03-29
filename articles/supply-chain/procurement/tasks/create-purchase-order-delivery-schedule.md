---
title: Créer une commande fournisseur avec un plan de livraison
description: Cet article illustre comment créer un calendrier de livraison pour une commande fournisseur.
author: GalynaFedorova
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, InventItemIdLookupPurchase, PurchDeliverySchedule, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e13103f374be838a5ea0fb5e08c449b419905cab
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875244"
---
# <a name="create-a-purchase-order-with-a-delivery-schedule"></a>Créer une commande fournisseur avec un plan de livraison

[!include [banner](../../includes/banner.md)]

Cet article illustre comment créer un calendrier de livraison pour une commande fournisseur. Un plan de livraison est utilisé lorsqu’une quantité sur une commande ou un journal doit être livré dans le cadre de plusieurs expéditions. L’exemple indiqué dans ce guide peut être utilisé dans les données fictives de la société USMF. Cette procédure est généralement effectuée par un agent des achats.

## <a name="create-a-delivery-schedule"></a>Créer un plan de livraison
1. Dans le volet de navigation, accédez à **Modules > Approvisionnements > Commandes fournisseur > Toutes les commandes fournisseur**.
2. Dans le volet Actions, sélectionnez **Nouveau**.
3. Dans le champ **Compte fournisseur**, saisissez `US-101`.
4. Cliquez sur **OK**.
5. Dans le champ **Numéro d’article**, entrez `M0001`.
6. Entrez `10` dans le champ **Quantité**.
7. Sélectionnez **Ligne de commande fournisseur**.
8. Sélectionnez **Plan de livraison**.
- La page **Plan de livraison** vous permet de spécifier le nombre d’expéditions pour lesquelles la quantité totale de la ligne de commande sera livrée à partir du fournisseur.  
- Par défaut, le système copie la quantité totale et d’autres détails de livraison à partir de la ligne d’achat d’origine dans la première ligne du plan de livraison. Dans cet exemple, nous allons créer un programme pour deux expéditions, la date de la deuxième expédition étant décalée d’une semaine par rapport à la première expédition.  
9. Dans le champ **Quantité**, sélectionnez la quantité de `4`.
10. Sélectionnez **Nouveau**.
11. Dans le champ **Quantité**, entrez la quantité `6`.
- Dans le champ Date de livraison, choisissez une date située une semaine après la date sur la première ligne de livraison.  
- Vous pouvez suivre la quantité totale répartie sur les lignes du plan de livraison en regardant les champs **Total** et **Restant**. Lorsque la quantité restante est nulle cela signifie que la quantité totale de la ligne d’origine a été affectée au plan.  
12. Développez la section **Conversion de frais**.
- Les options ici vous permettent de contrôler la façon dont vous voulez répartir les frais entre les lignes du plan de livraison. Si vous sélectionnez **Copier les montants bruts**, le montant de la ligne de commande d’origine est copié dans chaque ligne de livraison. L’option **Allouer aux lignes de livraison** répartit les frais de la ligne originale selon la quantité sur chaque ligne de livraison.  
13. Réduisez la section **Conversion de frais**.
14. Cliquez sur **OK**.
- Le plan de livraison est alors appliqué à la commande.  
- La ligne de commande d’origine (appelée Ligne commerciale) a été convertie en une ligne de commande contenant plusieurs livraisons. Elle est identifiée par une icône distincte et fait office d’en-tête pour les lignes de livraison.  
15. Sélectionnez la deuxième ligne de commande qui est la première des deux lignes de livraison.
- Les deux nouvelles lignes (appelées Lignes de livraison) constituent un plan de livraison. La commande sera traitée par rapport à ces lignes et non la ligne d’origine. Si des documents tels que des confirmations, des journaux d’accusés de réception de marchandises ou des factures sont imprimés, seules les lignes de livraison sont affichées.  

## <a name="change-the-delivery-schedule"></a>Modifier le plan de livraison
Vous pouvez modifier la quantité sur les lignes de livraison. Dans ce cas, la ligne commerciale est automatiquement mise à jour en fonction de la quantité totale des lignes de livraison.  
1. Dans le champ **Quantité** de la première ligne de livraison, remplacez la quantité de `4` par `5`.
2. Choisissez la première ligne de commande (la ligne commerciale).  
- La quantité sur la ligne commerciale a été remplacée par 11.  

## <a name="process-product-receipt-using-delivery-schedules"></a>Traiter l’accusé de réception de marchandises à l’aide des plans de livraison
La commande fournisseur doit être confirmée avant que l’accusé de réception de marchandises puisse être traité. Dans cet exemple, l’accusé de réception est enregistré directement sur la commande fournisseur. L’accusé de réception pourrait également avoir été enregistré quand les marchandises sont arrivées dans l’entrepôt.  
1. Dans le volet Action, sélectionnez **Achat**.
2. Sélectionnez **Confirmer**.
3. Dans le volet Actions, sélectionnez **Recevoir**.
4. Sélectionnez **Accusé de réception de marchandises**. Tapez une valeur quelconque dans le champ **Accusé de réception de marchandises**.
- Ce champ permet d’entrer une référence qui sera utilisée comme N° document pour le journal de réception de marchandises.  
- Dans le champ **Quantité**, choisissez **Quantité commandée**. Cette option signifie que l’accusé de réception traitera la quantité pour laquelle les lignes de commande ont été créées.  
- Assurez-vous que le champ **Imprimer l’accusé de réception de marchandises** est défini sur **Non**. L’impression n’est pas nécessaire dans cet exemple.  
5. Développez la section **Lignes**.
- Notez comment l’accusé de réception de marchandises est créé pour les deux lignes de livraison et pas la ligne de commande d’origine. Si l’accusé de réception de marchandises avait été enregistré dans l’entrepôt, il aurait également été enregistré sur les lignes du plan de livraison.  
6. Réduisez la section **Lignes**.
7. Sélectionnez **OK** pour valider la réception.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]