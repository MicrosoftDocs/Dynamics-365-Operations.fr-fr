---
title: Un numéro de document de réception de produit est consommé même sans génération de document
description: Un numéro document d’accusé de réception de marchandises est consommé même si aucun document financier n’est généré lors de la réception de produit
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 0556969950c45e80d177a0e96096c4157d690ae3
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476330"
---
# <a name="a-product-receipt-voucher-number-is-consumed-even-when-not-generating-a-voucher"></a>Un numéro de document de réception de produit est consommé même sans génération de document

## <a name="symptoms"></a>Symptômes

Un numéro document d’accusé de réception de marchandises est consommé même si aucun document financier n’est généré lors de la réception de produit.

## <a name="resolution"></a>Résolution

Si l’option **Provisionner le passif sur l’accusé de réception de marchandises** est définie sur *Non* pour le groupe de modèles d’article, aucune validation dans la comptabilité n’aura lieu. Cependant, un événement physique sera enregistré à des fins de comptabilisation dans une comptabilité auxiliaire, et cet événement nécessite un numéro de document. Ce numéro de document est le numéro de document qui est référencé dans les mouvements de stock.

Nous vous recommandons de définir l’option **Provisionner le passif sur l’accusé de réception de marchandises** sur *Oui*, comme décrit dans l’article de blog suivant : [Valider des frais divers au moment de la réception des produits](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).
