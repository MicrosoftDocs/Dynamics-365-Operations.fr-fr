---
title: Contrôler le stock de consignation à l'aide de la collaboration fournisseur
description: Cette procédure indique comment utiliser la collaboration du fournisseur pour afficher des informations sur le niveau de stock du produit que vous avez placé en consignation auprès d'un client.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentProductReceiptLines, PurchVendorPortalConfirmedOrders, DefaultDashboard, ConsignmentVendorPortalOnhand
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f2e782bed4cd9f2f13e2ee45afffaef277279131
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020127"
---
# <a name="monitor-consignment-inventory-using-vendor-collaboration"></a>Contrôler le stock de consignation à l'aide de la collaboration fournisseur

[!include [banner](../../includes/banner.md)]

Cette procédure indique comment utiliser la collaboration du fournisseur pour afficher des informations sur le niveau de stock du produit que vous avez placé en consignation auprès d'un client. Vous pouvez également contrôler la consommation du stock lorsque le client s'approprie le stock. Vous pouvez utiliser cette procédure dans les données fictives de la société USMF. Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.


## <a name="view-consumed-inventory"></a>Afficher le stock consommé
1. Allez dans Collaborateur du fournisseur > Stock de consignation > Produits reçus à partir du stock de consignation.
    * La liste affiche les lignes d'accusé de réception de marchandises qui ont été générées lorsque la propriété du stock de consignation est passée du fournisseur au client. Vous devrez peut-être faire défiler vers la droite pour afficher les quantités et d'autres informations. Vous pouvez utiliser les informations de cette liste pour générer des factures pour votre client. Vous pouvez également exporter les données de produit vers Microsoft Excel.   
2. Cliquez sur Afficher la commande fournisseur.
3. Développez la section Détails de ligne.
    * La ligne est marquée comme consignation, et la section d'en-tête indique que la commande fournisseur a le statut Reçu.  
4. Fermez la page.

## <a name="view-on-hand-inventory"></a>Affichage du stock disponible
1. Allez dans Collaborateur du fournisseur > Stock de consignation > Stock de consignation disponible.
    * La page Stock de consignation disponible indique le stock que vous possédez dans l'entrepôt du client. Vous pouvez afficher des dimensions supplémentaires, telles que le site et l'entrepôt, en cliquant sur l'onglet Afficher les dimensions.   

