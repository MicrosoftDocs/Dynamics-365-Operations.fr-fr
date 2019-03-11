---
title: Livraison directe
description: Cet article fournit des informations sur les livraisons directes. Les livraisons directes sont des livraisons expédiées directement du fournisseur au client.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchCreateFromSalesOrder, SalesTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 9704
ms.assetid: 64c51384-8a4e-45d0-83c1-12cea22902f9
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9c4a695c591865c52ad5ee6d37a515139f58bf8
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "312276"
---
# <a name="direct-deliveries"></a>Livraison directe

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur les livraisons directes. Les livraisons directes sont des livraisons expédiées directement du fournisseur au client.

La livraison directe représente un gain en matière de délai de livraison et réduit les coûts associés au transport de stock car vous n'entreposez pas les produits dans votre entrepôt avant de les expédier au client.  

Vous pouvez réer des livraisons directes à partir de la page **Commande client**. Tout d'abord, créez une commande client et des lignes de commande. Ensuite, dans le volet Actions, sous l'onglet **Commande client**, sélectionnez **Livraison directe**. Enfin, spécifiez les lignes qui doivent être traitées comme livraison directe. Un lien existe à présent entre les lignes de commandes client pour la livraison directe et les lignes de la commande fournisseur correspondantes.  

**Remarque :** si une partie de la quantité commandée a déjà été livrée, vous devez fractionner la quantité restante. Créez une ligne pour la quantité qui doit être livrée directement, et soustrayez cette quantité de la quantité de la ligne d'origine. Par exemple, si la quantité originale était 15, et si cinq articles ont été livrés, vous devez créer une ligne pour la quantité restante (10), puis déduire cette quantité de la quantité d'origine.  

Après avoir créé le lien de la livraison directe entre les lignes de commande client et les lignes de commande fournisseur, vous pouvez mettre à jour la commande client à l'aide d'un bon de livraison. Exécutez une mise à jour du bon de livraison ou d'une facture à partir de la commande fournisseur. Vous devez mettre à jour la facture de la commande client depuis la page **Commande client**. Une mise à jour de la facture ne peut pas avoir pour effet que la quantité sur la commande client dépasse la quantité enregistrée comme reçue. Par exemple, une ligne de commande client inclut 10 pièces, mais seulement 5 pièces de la ligne de commande client ont été mises à jour à l'aide d'un bon de livraison. Si vous sélectionnez **Tout**dans la liste **Quantité** lorsque vous mettez à jour la facture de la commande client, seuls les articles reçus physiquement, ou mis à jour à l'aide d'un bon de livraison, font l'objet d'une mise à jour de facture. La totalité de la ligne de commande client n'est pas mise à jour.

## <a name="delivery-date"></a>Date de livraison
Lorsque vous mettez à jour le champ **Date de réception demandée** dans la ligne de commande client, le champ **Date de livraison** de la ligne de commande fournisseur correspondante est également mise à jour. De la même manière, lorsque vous mettez à jour le champ **Confirmé** dans la ligne de commande client, les champs **Date de livraison demandée** et **Date d'expédition confirmée**de la ligne de commande fournisseur correspondante sont également mis à jour.

## <a name="delivery-address"></a>Adresse de livraison
En général, l'adresse de livraison d'une commande fournisseur est l'adresse de la société. Toutefois, lorsque vous créez une livraison directe, l'adresse du client est entrée comme adresse de livraison. Si vous modifiez l'adresse de livraison d'une ligne de commande fournisseur avec le type de livraison **Livraison directe**, l'adresse de livraison de la ligne de commande client correspondante est également mise à jour. De même, si vous modifiez la date de livraison de la ligne de commande client, l'adresse de livraison de la ligne de commande fournisseur est également mise à jour.

## <a name="deleting-order-lines"></a>Suppression des lignes de commande
Si vous tentez de supprimer une ligne de commande client avec le type de livraison **Livraison directe**, un message s'affiche et indique que des lignes de commande fournisseur sont associées à la ligne. Si la ligne de commande client a été partiellement livrée, vous ne pouvez pas supprimer la ligne de commande client ou les lignes de commande fournisseur associées.

## <a name="warehouse"></a>Entrepôt
Lorsque vous créez une livraison directe, les articles que vous vendez n'arrivent jamais physiquement à votre entrepôt. Toutefois, vous devez toujours spécifier un entrepôt dans la ligne de commande client. De même, les besoins en matière de prélèvement peuvent être spécifiés dans le groupe de modèles d'article pour l'article. Toutefois, comme les articles n'arrivent jamais physiquement à votre entrepôt, ces besoins sont ignorés lorsque la commande client est une livraison directe.



