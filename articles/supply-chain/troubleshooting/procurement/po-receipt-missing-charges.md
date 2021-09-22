---
title: Un accusé de réception de commande fournisseur n’inclut pas tous les frais
description: Un accusé de réception de commande fournisseur n’inclut pas tous les frais
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: bb567e00ef52269db0dc866148a37c73f0a9827c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476294"
---
# <a name="a-purchase-order-receipt-doesnt-include-all-charges"></a>Un accusé de réception de commande fournisseur n’inclut pas tous les frais

## <a name="symptoms"></a>Symptômes

Lorsque vous recevez une commande fournisseur, tous les frais ne sont pas inclus dans l'accusé de réception.

### <a name="reproduce-the-issue"></a>Reproduire le problème

La procédure suivante montre comment reproduire le problème.

1. Sur la page **Paramètres d’approvisionnements**, sur l’onglet **Livraison**, assurez-vous que l’option **Générer des frais sur l’accusé de réception de marchandises** est définie sur *Oui*.
1. Créez une commande fournisseur qui inclut des frais.
1. Confirmez la commande fournisseur.
1. Recevez la commande fournisseur.
1. Regardez le total de l’accusé de réception et comparez-le au total attendu.
1. Notez que tous les frais ne sont pas inclus sur l’accusé de réception de la commande.

## <a name="resolution"></a>Résolution

La résolution dépend de la manière dont les frais divers ont été configurés. Pour plus d’informations sur la configuration des frais divers pour répondre à vos besoins, consultez l’article de blog suivant : [Valider des frais divers au moment de la réception des produits](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).
