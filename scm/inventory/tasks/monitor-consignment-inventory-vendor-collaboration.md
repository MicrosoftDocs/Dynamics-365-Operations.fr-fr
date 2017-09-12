---
title: "Contrôler le stock de consignation à l'aide de la collaboration fournisseur"
description: "Cette procédure indique comment utiliser la collaboration du fournisseur pour afficher des informations sur le niveau de stock du produit que vous avez placé en consignation auprès d'un client."
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
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: ad4868991226aef21a0410860e3f98d11901ffbb
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="monitor-consignment-inventory-using-vendor-collaboration"></a>Contrôler le stock de consignation à l'aide de la collaboration fournisseur

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure indique comment utiliser la collaboration du fournisseur pour afficher des informations sur le niveau de stock du produit que vous avez placé en consignation auprès d'un client. Vous pouvez également contrôler la consommation du stock lorsque le client s'approprie le stock. Vous pouvez utiliser cette procédure dans les données fictives de la société USMF. Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.


## <a name="view-consumed-inventory"></a>Afficher le stock consommé
1. Allez dans Collaborateur du fournisseur > Stock de consignation > Produits reçus à partir du stock de consignation.
    * La liste affiche les lignes d'accusé de réception de marchandises qui ont été générées lorsque la propriété du stock de consignation est passée du fournisseur au client. Vous devrez peut-être faire défiler vers la droite pour afficher les quantités et d'autres informations. Vous pouvez utiliser les informations de cette liste pour générer des factures pour votre client. Vous pouvez également exporter les données vers Microsoft Excel.   
2. Cliquez sur Afficher la commande fournisseur.
3. Développez la section Détails de ligne.
    * La ligne est marquée comme consignation, et la section d'en-tête indique que la commande fournisseur a le statut Reçu.  
4. Fermez la page.

## <a name="view-on-hand-inventory"></a>Affichage du stock disponible
1. Allez dans Collaborateur du fournisseur > Stock de consignation > Stock de consignation disponible.
    * La page Stock de consignation disponible indique le stock que vous possédez dans l'entrepôt du client. Vous pouvez afficher des dimensions supplémentaires, telles que le site et l'entrepôt, en cliquant sur l'onglet Afficher les dimensions.   

