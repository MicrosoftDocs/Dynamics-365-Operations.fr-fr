---
title: Disponibilité du stock en double écriture
description: Cette rubrique fournit des informations sur la consultation de la disponibilité du stock en double écriture.
author: yijialuan
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: dd0995eb8c70ed06cdc3c0f6a28b13b117297533
ms.sourcegitcommit: be7e4378c8122c6e7cfc4e7991efbdffee45e006
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2020
ms.locfileid: "3426980"
---
# <a name="inventory-availability"></a>Disponibilité du stock

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Grâce à la disponibilité du stock, vous pouvez consulter le stock avant d'ajouter un produit dans les formulaires **Devis**, **Commandes** ou **Factures** dans les applications pilotées par modèles dans Dynamics 365. Par exemple, la consultation du stock et la détermination d'une date de réalisation est une tâche clé du processus [prospects en disponibilités](dual-write-prospect-to-cash.md). Si vous ne disposez pas d'un stock suffisant, vous pouvez estimer une date de livraison en fonction des entrées et sorties de stock prévues. Vous pouvez également vérifier les informations de disponibilité à la vente du produit (DAV), où vous pouvez trouver la quantité DAV dans la plage de temps prédéfinie.

## <a name="on-hand-inventory"></a>Stock disponible 

Dans l'en-tête des formulaires **Devis**, **Commandes** ou **Factures** de Dynamics 365 Sales, un nouveau bouton **Stock disponible** a été ajouté. Lorsque vous cliquez sur le bouton, une boîte de dialogue apparaît et vous pouvez spécifier la société et le produit pour lesquels vous souhaitez vérifier le stock disponible. Il renvoie les informations de stock de Dynamics 365 Supply Chain Management et affiche les mêmes informations que [Stock disponible](../../../../supply-chain/inventory/tasks/check-availability-stock.md). Ces informations comprennent ces quantités :

- **Quantité disponible**
- **Quantité disponible réservée**
- **Quantité disponible à disposition**
- **Quantité commandée**
- **Quantité en commande**
- **Quantité commandée réservée**
- **Quantité totale disponible**

## <a name="atp-information"></a>Informations sur DAV

Dans les articles de ligne des formulaires **Devis**, **Commandes** ou **Factures** de Dynamics 365 Sales, un nouveau bouton **Informations DAV** a été ajouté. Lorsque vous cliquez sur le bouton, une boîte de dialogue apparaît et vous pouvez spécifier la société, le produit, le site de stockage, l'entrepôt et la quantité en commande. Il renvoie les **Informations DAV** de Supply Chain Management et affiche les paramètres décrits dans [Promesse de commande](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations). Les informations comprennent **Quantité DAV**, **Quantité de réception**, **Quantité de sortie** et **Quantité disponible**.
