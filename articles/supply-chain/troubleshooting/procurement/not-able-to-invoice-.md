---
title: Vous ne pouvez pas facturer une commande client adressée au client
description: Vous ne pouvez plus facturer la commande client d'origine et la commande d'achat de livraison directe d'origine après avoir activé l'option Enregistrer automatiquement la facture.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: SalesEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ab18a2a1dec4b70c55a55637b087c6b11023aa40
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026503"
---
# <a name="you-cant-invoice-a-customer-facing-sales-order"></a>Vous ne pouvez pas facturer une commande client adressée au client

Numéro de la base de connaissances : 4611793

## <a name="symptoms"></a>Symptômes

Vous ne pouvez plus facturer la commande client d'origine et la commande d'achat de livraison directe d'origine après avoir activé l'option **Enregistrer automatiquement la facture** sur la page **Intersociétés** pour un fournisseur.

## <a name="resolution"></a>Résolution

Le comportement de synchronisation des factures intersociétés et des bons de livraison directe est contrôlé et forcé par les paramètres décrits dans [Configurer les paramètres pour valider une commande intersociétés](/dynamicsax-2012/appuser-itpro/set-up-parameters-to-post-an-intercompany-order).

Après avoir défini ces paramètres, vous devez d'abord facturer la commande client intersociétés. Les bons de commande et les bons de commande d'origine seront alors synchronisés.
