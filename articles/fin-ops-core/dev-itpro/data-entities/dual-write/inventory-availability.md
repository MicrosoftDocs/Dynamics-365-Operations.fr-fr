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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: 4d1022eec633bf0a9edb4d5b26982853cec836d7
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997890"
---
# <a name="inventory-availability-in-dual-write"></a>Disponibilité du stock en double écriture

[!include [banner](../../includes/banner.md)]

Grâce à la disponibilité du stock, vous pouvez consulter le stock avant d'ajouter un produit dans les formulaires **Devis** , **Commandes** ou **Factures** dans Microsoft Dynamics 365 Sales. Par exemple, la consultation du stock et la détermination d'une date de réalisation est une tâche clé du processus [prospects en disponibilités](dual-write-prospect-to-cash.md).

Si vous ne disposez pas d'un stock suffisant, vous pouvez estimer une date de livraison en fonction des entrées et sorties de stock prévues. Vous pouvez également vérifier les informations de disponibilité à la vente du produit (DAV), où vous pouvez trouver la quantité DAV dans la plage de temps prédéfinie.

## <a name="on-hand-inventory"></a>Stock disponible

Dans Dynamics 365 Sales, un nouveau bouton **Stock disponible** a été ajouté à l'en-tête des pages **Devis** , **Commandes** et **Factures**. Lorsque vous sélectionnez ce bouton, une boîte de dialogue apparaît et vous pouvez spécifier la société et le produit pour lesquels vous souhaitez vérifier le stock disponible. Cette boîte de dialogue affiche les mêmes informations que [Stock disponible](../../../../supply-chain/inventory/tasks/check-availability-stock.md).

La boîte de dialogue renvoie les informations de stock de Dynamics 365 Supply Chain Management. Ces informations incluent les quantités suivantes :

- Quantité disponible
- Quantité disponible réservée
- Quantité disponible à disposition
- Quantité commandée
- Quantité en commande
- Quantité commandée réservée
- Quantité totale disponible

## <a name="atp-information"></a>Informations sur DAV

Dans Sales, un nouveau bouton **Informations ATP** a été ajouté aux lignes dans les pages **Devis** , **Commandes** et **Factures**. Lorsque vous sélectionnez ce bouton, une boîte de dialogue apparaît et vous pouvez spécifier la société, le produit, le site de stockage, l'entrepôt et la quantité en commande. Cette boîte de dialogue a les mêmes paramètres que ceux décrits dans [Promesse de commande](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).

La boîte de dialogue renvoie les informations ATP de Supply Chain Management. Ces informations incluent les quantités suivantes :

- Quantité DAV
- Quantité de réception
- Quantité de sortie
- Quantité disponible
