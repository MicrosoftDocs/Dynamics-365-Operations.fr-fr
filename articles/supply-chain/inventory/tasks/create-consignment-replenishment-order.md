---
title: Créer une commande de réapprovisionnement avec consignation
description: Cette rubrique explique comment créer une commande de réapprovisionnement avec consignation pour vous permettre de suivre la livraison prévue d'un fournisseur dans le stock de consignation.
author: RichardLuan
manager: tfehr
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentReplenishmentOrder, ConsignmentReplenishmentOrderCreate, InventTrans, ConsignmentDraftReplenishmentOrderJournal, InventOnhandMovement, InventOnhandItem, InventItemIdLookupSimple, ConsignmentProductReceiptJournal, ConsignmentReplenishmentOrderLineQuantity
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b27b4d87add38fac29c9eba4ace08af91f9faca1
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020152"
---
# <a name="create-a-consignment-replenishment-order"></a>Créer une commande de réapprovisionnement avec consignation

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment créer une commande de réapprovisionnement avec consignation pour vous permettre de suivre la livraison prévue d'un fournisseur dans le stock de consignation. Elle décrit également comment enregistrer une réception de produits afin que le stock de consignation soit enregistré comme stock disponible appartenant au fournisseur. Cette procédure est généralement effectuée par un professionnel de l'approvisionnement. Vous pouvez utiliser ce guide dans les données de démonstration de la société fictive USMF. Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.

## <a name="create-a-consignment-replenishment-order"></a>Créer une commande de réapprovisionnement avec consignation
1. Dans le volet de navigation, accédez à **Modules > Approvisionnements > Consignation > Commandes de réapprovisionnement avec consignation**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Compte fournisseur**, sélectionnez le fournisseur **US-104** (vous devez sélectionner un fournisseur qui est enregistré comme propriétaire dans la page **propriétaires du stock**). 
4. Cliquez sur **OK**.
5. Sélectionnez **Ajouter la ligne**.
6. Dans le champ **Numéro d’article**, tapez `M9211CI` (vous devez sélectionner un article qui est paramétré pour un stock de consignation).
7. Entrez un nombre dans le champ **Quantité**.
8. Entrez une date dans le champ **Date de livraison demandée**. Les dates demandées et confirmées sont utilisées par le moteur MRP pour l'arrivée prévue des marchandises.  
9. Entrez une date dans le champ **Date de livraison confirmée**.
10. Développez la section **Détails de ligne**.
11. Cliquez sur l'onglet **Dimensions de stock**.
12. Actualisez la page pour afficher le propriétaire dans le champ **Propriétaire des dimensions de stock**. Le fournisseur US-104 est à présent répertorié comme propriétaire.  

## <a name="check-the-inventory-transaction-status"></a>Vérifier le statut du mouvement de stock
1. Sélectionnez le **stock**.
2. Sélectionnez les **transactions**.
3. Dans la ligne souhaitée, notez que le champ **Réception** est défini sur **Commandé**.  
4. Fermez la page.

## <a name="receive-items"></a>Recevoir articles
1. Sélectionnez **Accusé de réception de marchandises**.
2. Tapez une valeur dans le champ **Accusé de réception de marchandises externe**.
3. Dans le champ **Quantité**, entrez un nombre inférieur au nombre indiqué ici. 
4. Cliquez sur **OK**.

## <a name="check-the-on-hand-inventory"></a>Vérifier le stock disponible
1. Sélectionnez le **stock**.
2. Sélectionner **Disponible**.
3. Sélectionnez **Vue d'ensemble**. Les articles reçus comme stock de consignation appartenant au fournisseur sont disponibles. La quantité restante sur la commande de réapprovisionnement avec consignation est affichée dans le champ **Total commandé**.  
4. Fermez la page.

