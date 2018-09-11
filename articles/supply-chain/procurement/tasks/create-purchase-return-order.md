--- 
title: "Créer une commande fournisseur de retour"
description: "Cette procédure vous montre comment créer une commande fournisseur retournée à l'aide de l'action Avoir pour copier des lignes d'un document de facturation fournisseur à une nouvelle CF."
author: FrankDahl
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchCreateOrder, PurchCopying, InventMarking, PurchEditLines
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b9124100f84afb13acc2ac9dda7b9483afb01754
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-a-purchase-return-order"></a>Créer une commande fournisseur de retour

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure vous montre comment créer une commande fournisseur retournée à l'aide de l'action Avoir pour copier des lignes d'un document de facturation fournisseur à une nouvelle CF. Elle montre également comment confirmer la commande et traiter l'expédition des marchandises au fournisseur. L'exemple indiqué dans cette procédure peut être utilisé dans les données fictives de la société USMF. Cette tâche est généralement effectuée par un agent des achats.


## <a name="create-a-new-purchase-return-order"></a>Créer une commande fournisseur retournée
1. Accédez à Approvisionnements > Commandes fournisseur > Toutes les commandes fournisseur.
    * La première étape consiste à créer une commande fournisseur à utiliser comme commande fournisseur retournée.  
2. Cliquez sur Nouveau.
3. Tapez US-102 dans le champ Compte fournisseur.
4. Cliquez sur OK.
5. Cliquez sur Achats dans le volet Actions.
6. Cliquez sur Avoir.
    * Il s'agit de la page à partir de laquelle vous pouvez copier une facture fournisseur existante dans votre ordre de retour. C'est la même page qui est employée pour d'autres actions de copie. Mais comme nous l'avons ouverte à partir de l'action Avoir, la page est configurée pour prendre en charge la création d'un ordre de retour qui compense des factures fournisseur.  
7. Développez la section Paramètres.
    * L'option Inverser le signe est automatiquement choisie, et ne peut pas être changée. Ceci assure que le signe est changé pour les quantités, et que les lignes de commande qui sont ajoutées compenseront la facture fournisseur.  
    * L'option Copier les frais est automatiquement choisie, et ne peut pas être changée. Ceci signifie que des frais de la facture fournisseur sont ajoutés à la commande fournisseur retournée pour compenser les frais d'origine. Il est possible de modifier les changements sur l'en-tête et les lignes de la commande plus tard.  
    * L'option Copier précisément est automatiquement choisie, et ne peut pas être changée. Ceci assure qu'une copie précise des valeurs de tous les champs est effectuée sur l'en-tête et les lignes de la commande fournisseur. Ceci signifie qu'une commande fournisseur retournée est créée avec des valeurs qui correspondent à tous les termes utilisés avec le document de facturation fournisseur.  
    * L'option Supprimer des lignes d'achat supprime toutes les lignes de commandes fournisseur qui existent déjà sur la commande fournisseur avant d'ajouter les nouvelles lignes. Dans cet exemple, nous n'avons pas encore ajouté de lignes à la commande fournisseur retournée, cela n'a donc aucun effet. Utilisez cette option avec prudence, en effet elle supprime toutes les lignes existantes sans que vous en soyez averti.  
    * L'option Copier l'en-tête de commande est automatiquement choisie, et ne peut pas être changée. Cela garantit que les informations sont copiées à partir de la facture fournisseur et qu'elles sont appliquées à l'en-tête de la commande fournisseur retournée. C'est utile parce que cela aide à s'assurer que la commande fournisseur retournée compense la facture à l'aide des termes semblables.  
8. Réduisez la section Paramètres.
9. Développer la section Factures.
    * La page a été ouverte à partir de l'action Avoir, ainsi la seule option disponible est de copier les informations à partir des factures fournisseur. Cet onglet montre toutes les factures disponibles pour le compte fournisseur qui est spécifié sur une commande fournisseur retournée que vous avez créée plus tôt.   Les factures sont identifiées par le N° document de facture ou les ID de commande fournisseur.  
10. Localisez la facture fournisseur identifiée par le numéro de facture AP-0006, mettez en surbrillance cette ligne en cliquant sur n'importe quel champ dans cette ligne.
11. Sélectionnez la ligne en cliquant dans la case à cocher correspondante. 
    * Notez que les lignes disponibles sur la facture fournisseur sont automatiquement choisies avec la commande. Cette facture fournisseur particulière a 2 lignes de commande. Pour cet exemple, nous renverrons une partie de la quantité à partir de la deuxième ligne.  
12. Mettez en surbrillance la deuxième ligne (celle avec l'article M0006) en cliquant sur n'importe quel champ dans cette ligne.
13. Dans le champ Quantité, sélectionnez la quantité de 10. Il s'agit de la quantité que nous renverrons au fournisseur. 
14. Mettez en surbrillance la première ligne (celle avec l'article M0005) en cliquant sur n'importe quel champ dans cette ligne.
15. Désactivez la case à cocher pour la ligne.
    * Seules les lignes que vous avez choisies seront copiées dans votre commande.  
16. Réduisez la section Factures.
17. Augmentez l'en-tête ou les lignes sélectionnées pour être la section copiée.
    * Cette vue montre un résumé de tous les documents et des lignes sélectionnés pour être copiés dans votre commande.  
18. Réduisez l'en-tête ou les lignes sélectionnées pour être la section copiée.
19. Cliquez sur OK.
    * La ligne que vous avez choisie a été copiée sur votre commande fournisseur retournée. Le champ Quantité indique -10.   
20. Cliquez sur Stock.
21. Cliquez sur Marquage.
    * La ligne d'ordre qui a été créée est marquée par rapport à la transaction de stock à partir de la facture fournisseur. Ceci garantit que le stock qui est retourné au fournisseur est identique à celui qui a été reçu plus tôt. Il y a quelques situations où le marquage ne se produit pas, par exemple, si le stock a été déjà marqué comme Consommé, ou si le produit n'emploie pas de marquage.  
22. Cliquez sur OK.

## <a name="confirm-and-record-the-shipment-of-goods"></a>Confirmer et enregistrer l'expédition des marchandises
1. Cliquez sur Confirmer.
2. Dans le volet Actions, cliquez sur Recevoir.
3. Cliquez sur Accusé de réception de marchandises.
    * Cette page permet d'enregistrer l'accusé de réception de marchandises pour des commandes fournisseur et également pour traiter le retour des marchandises au fournisseur. Les lignes de commande avec une quantité négative signifient que des marchandises doivent être retournées au fournisseur, et le document qui peut être produit de cette page peuvent être utilisé comme bon de livraison pour cet usage.   
    * Dans le champ Quantité, choisissez Quantité commandée pour cet exemple.   Ceci garantit que l'expédition sera traitée pour toute la quantité commandée pour laquelle les lignes d'ordre ont été créées.   
4. Tapez une valeur dans le champ Accusé de réception de marchandises.
    * Ce champ permet d'entrer une référence qui sera utilisée comme N° document pour le journal de réception de marchandises.  
5. Cliquez sur OK.
    * Les marchandises sont désormais enregistrées comme expédiées sur la commande fournisseur retournée et un journal des accusés de réception de marchandises est créé. Vous pouvez utiliser l'action Accusé de réception de marchandises pour passer en revue les journaux créés avec la commande fournisseur, et voir ce qui a été reçu ou retourné, et quand.  


