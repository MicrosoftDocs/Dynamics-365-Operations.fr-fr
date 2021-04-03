---
title: Créer une commande fournisseur répétée
description: Cette rubrique vous montre comment créer une commande fournisseur répétée (CF) en copiant des lignes d’un document de commande fournisseur précédent dans un nouveau CF ou un CF existant.
author: RichardLuan
manager: tfehr
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, PurchCopying
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ab669e393690867c1887ddcd982e20b5166bba2e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5262235"
---
# <a name="create-a-repeat-purchase-order"></a>Créer une commande fournisseur répétée

[!include [banner](../../includes/banner.md)]

Cette rubrique vous montre comment créer une commande fournisseur répétée (CF) en copiant des lignes d’un document de commande fournisseur précédent dans un nouveau CF ou un CF existant. Il y a deux méthodes pour créer des commandes répétées. Vous pouvez utiliser les actions disponibles au niveau du document à partir du volet Actions ou vous pouvez utiliser les actions de détails de ligne. Les actions de niveau du document sont principalement prévues pour créer une commande fournisseur en ajoutant des lignes et des informations d’en-tête à partir d’une autre commande, alors que l’action de détails de ligne sert principalement à ajouter des lignes à une commande existante. L’exemple indiqué dans ce guide peut être utilisé dans les données fictives de la société USMF. Cette tâche est généralement effectuée par un agent des achats.


## <a name="create-a-new-repeat-purchase-order"></a>Créer une commande fournisseur répétée
1. Dans le volet de navigation, accédez à **Modules > Approvisionnements > Commandes fournisseur > Toutes les commandes fournisseur**. D’abord, nous essayerons l’option pour copier les informations dans une nouvelle commande.  
2. Sélectionnez **Nouveau**.
3. Dans le champ **Compte fournisseur**, saisissez `US-101`.
4. Cliquez sur **OK**.
5. Cliquez sur **Commande fournisseur** dans le volet Actions.
6. Sélectionnez **À partir de tous**. Il s’agit de la page à partir de laquelle vous pouvez copier à partir des commandes existantes dans votre commande. Il y a différentes options pour copier les lignes et différents types de documents à partir desquels vous pouvez copier. Nous verrons les options pour copier les lignes en premier. 
7. Développez la section **Paramètres**.

    - Le champ **Facteur de quantité** est utile si vous devez utiliser une quantité qui est différente de celle qui est sur la commande à partir de laquelle vous copiez. Par exemple, si vous voulez commander deux fois la quantité qui est dans les lignes à partir desquelles vous copiez, vous devez taper « 2 » dans ce champ et le système ajoutera alors des lignes où la quantité originale a été doublée.  
    - Le champ **Inverser le signe** prend aussi en charge la quantité commandée en changeant le signe de la quantité pour les lignes de commande qui sont ajoutées. Ceci peut être utile si vous devez contrepasser une transaction, en créant des lignes de commande qui annulent la transaction. Cette option est automatiquement choisie quand la page est ouverte à partir de l’action **Créer un avoir**.  
    - L’option **Copier les frais** vous permet de copier des frais dans la nouvelle commande à partir du document à partir duquel vous copiez les lignes de commande.  
    - L’option **Recalcul des prix** utilise les prix actuels et les remises plutôt que de les copier à partir du document à partir duquel vous copiez d’autres informations.  
    - L’option **Copier précisément** crée une copie précise des valeurs de tous les champs sur l’en-tête et les lignes du document de commande. Si cette option n’est pas choisie, des valeurs par défaut sont utilisées pour plusieurs champs concernant le fournisseur et les produits, comme si vous créiez la nouvelle commande manuellement. Par exemple, si la commande à partir de laquelle vous copiez a remplacé le compte de facturation par défaut du fournisseur, le même compte de facturation sera copié dans votre commande. Si vous ne choisissez pas l’option **Copier précisément**, le compte de facturation par défaut du fournisseur sera utilisé à la place sur votre commande.  
    - L’option **Supprimer des lignes d’achat** supprime toutes les lignes de commandes fournisseur qui existent déjà sur la commande fournisseur dans laquelle vous copiez, avant d’appliquer les nouvelles lignes. Utilisez cette option avec prudence, en effet elle supprime toutes les lignes existantes sans que vous en soyez averti.  
    - Si vous utilisez l’option **Copier l’en-tête de commande**, vous n’avez pas besoin de créer manuellement les informations d’en-tête sur votre nouvelle commande. Notez que cette option entraîne l’utilisation de valeurs par défaut pour les champs liés au fournisseur. Si le document à partir duquel vous copiez contient des valeurs non définies par défaut que vous voulez copier, utilisez également l’option **Copier précisément**.   
    - Il y a des sources de documents différentes à partir desquelles vous pouvez copier, chacune contient une section distincte sur cette page. Par exemple, la section **Commandes fournisseur** vous permet de copier à partir de commandes fournisseur existantes.  

8. Dans la section **Commandes fournisseur**, sélectionnez les lignes que vous voulez copier dans le Presse-papiers. Il est possible de choisir des lignes de commande fournisseur supplémentaires à partir d’autres commandes fournisseur et de les copier également sur votre commande. Il est également possible d’ajouter des lignes à partir d’autres types de documents d’achat. Les quelques étapes suivantes passent en revue les différentes options.  
9. Développez la section **Confirmation**. Vous pouvez sélectionner ici des confirmations de commandes fournisseur à partir desquelles copier. Les confirmations de commandes fournisseur sont identifiées par l’ID journal d’achat ou l’ID commande fournisseur.  
10. Développez la section **Accusés de réception de marchandises**. Vous pouvez sélectionner ici des journaux d’accusés de réception de marchandises à partir desquels copier. Les journaux d’accusés de réception de marchandises sont identifiés par le N° document d’accusé de réception de marchandises ou l’ID commande fournisseur.   
11. Développez la section **Factures**. Ici vous pouvez choisir des factures fournisseur à partir desquelles copier. Ces factures sont identifiées par le N° document de facture ou l’ID commande fournisseur.   
12. Développez la section **Lignes ou en-têtes sélectionnés à copier**. Cette vue montre un résumé de tous les documents et des lignes qui ont été sélectionnés pour être copiés dans votre commande.   
13. Cliquez sur **OK**. Les 4 lignes que vous avez choisies ont été copiées sur votre nouvelle commande fournisseur.   

## <a name="copy-lines-to-an-existing-purchase-order"></a>Copier les lignes dans une commande fournisseur existante  

Au lieu de copier une commande complète, il est plus courant de créer une nouvelle CF et de renseigner les informations sur l’en-tête de la CF, puis de copier chaque ligne à partir des commandes existantes.  

1. Sélectionnez la ligne **Commande fournisseur**.
2. Sélectionnez **À partir de tous**. La page qui s’ouvre est identique à celle montrée avant, mais différentes options sont choisies quand elle s’ouvre à partir de la vue des lignes de commande. Examinons les paramètres.   
3. Développez la section **Paramètres**.

    - L’option **Supprimer les lignes d’achat** n’est pas sélectionnée. Ceci signifie que vous pouvez copier de nouvelles lignes dans votre commande sans supprimer les lignes existantes.   
    - L’option **Copier l’en-tête de commande** n’est pas choisie non plus, car nous ajoutons seulement des lignes supplémentaires à la commande.   
    - Pour cet exemple, nous copierons des lignes d’une commande fournisseur existante.   

4. Sélectionnez la ligne pour la ligne de commande fournisseur souhaitée. Notez que la ligne de commande unique qui est sur cette commande fournisseur est également sélectionnée.  
5. Cliquez sur **OK**. La ligne de commande supplémentaire a été ajoutée à votre commande fournisseur.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]