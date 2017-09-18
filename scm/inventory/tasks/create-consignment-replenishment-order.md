---
title: "Créer une commande de réapprovisionnement avec consignation"
description: "Cette procédure indique comment créer une commande de réapprovisionnement avec consignation pour vous permettre de suivre la livraison prévue d'un fournisseur dans le stock de consignation."
author: mkirknel
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 5e268f640be11b0905457ff6b7697c90411f53e5
ms.contentlocale: fr-fr
ms.lasthandoff: 07/28/2017

---
# <a name="create-a-consignment-replenishment-order"></a>Créer une commande de réapprovisionnement avec consignation

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure indique comment créer une commande de réapprovisionnement avec consignation pour vous permettre de suivre la livraison prévue d'un fournisseur dans le stock de consignation. Elle décrit également comment enregistrer une réception de produits afin que le stock de consignation soit enregistré comme stock disponible appartenant au fournisseur. Cette procédure est généralement effectuée par un professionnel de l'approvisionnement. Vous pouvez utiliser ce guide dans les données de démonstration de la société fictive USMF. Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.




## <a name="create-a-consignment-replenishment-order"></a>Créer une commande de réapprovisionnement avec consignation
1. Allez dans Approvisionnements > Consignation > Commandes de réapprovisionnement avec consignation.
2. Cliquez sur Nouveau.
3. Dans le champ Compte fournisseur, sélectionnez le fournisseur US-104.
    * Vous devez sélectionner un fournisseur qui est enregistré comme propriétaire dans la page Propriétaires du stock.  
4. Cliquez sur OK.
5. Cliquez sur Ajouter une ligne.
6. Dans le champ Numéro d'article, tapez M9211CI.
    * Vous devez sélectionner un article qui est paramétré pour le stock de consignation.  
7. Dans le champ Quantité, entrer un numéro.
8. Dans le champ Date de livraison demandée, entrez une date.
    * Les dates demandées et confirmées sont utilisées par le moteur MRP pour l'arrivée prévue des marchandises.  
9. Dans le champ Date de livraison confirmée, entrez une date.
10. Développez la section Détails de ligne.
11. Cliquez sur l'onglet Dimensions de stock.
12. Pour afficher le propriétaire dans le champ Propriétaire des dimensions de stock, actualisez la page.
    * Le fournisseur US-104 est à présent répertorié comme propriétaire.  

## <a name="check-the-inventory-transaction-status"></a>Vérifier le statut du mouvement de stock
1. Cliquez sur Stock.
2. Cliquez sur Transactions.
3. Dans la liste, marquez la ligne sélectionnée.
    * Notez que le champ Réception est défini sur Commandé.  
4. Fermez la page.

## <a name="receive-items"></a>Recevoir articles
1. Cliquez sur Accusé de réception de marchandises.
2. Dans le champ Accusé de réception de marchandises externe, tapez une valeur.
3. Dans le champ Quantité, entrez un nombre inférieur au nombre indiqué ici.
4. Cliquez sur OK.

## <a name="check-the-on-hand-inventory"></a>Vérifier le stock disponible
1. Cliquez sur Stock.
2. Cliquez sur Disponible.
3. Cliquez sur Vue d'ensemble.
    * Les articles reçus comme stock de consignation appartenant au fournisseur sont disponibles. La quantité restante sur la commande de réapprovisionnement avec consignation est affichée dans le champ Total commandé.  
4. Fermez la page.
5. Cliquez sur Fermer.
