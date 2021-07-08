---
title: Les accusés de réception de produits annulés ne mettent pas à jour le statut de la transaction sur Enregistré
description: Après avoir annulé des accusés de réception de produits sur un chargement entrant, le système met automatiquement à jour le statut de la transaction de stock de Reçu à Commandé.
author: GalynaFedorova
ms.date: 06/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 9c86457d50a7a9ac2a699a0e0a9c7bdf4cd7c67b
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294072"
---
# <a name="canceled-product-receipts-dont-update-transaction-status-to-registered"></a>Les accusés de réception de produits annulés ne mettent pas à jour le statut de la transaction sur Enregistré

## <a name="symptoms"></a>Symptômes

Après avoir exécuté l’action **Annuler des accusés de réception de produits** sur un chargement entrant, le système met automatiquement à jour le statut des transactions de stock de *Reçu* à *Commandé*.

## <a name="resolution"></a>Résolution

Lorsque des bons de livraison sont annulés pour des chargements sortants, le statut des transactions de stock demeure *Prélevé*. Cependant, lorsque d accusés de réception de produits d’un chargement entrant sont annulés, le statut des transactions de stock n’est pas restauré sur *Enregistré*. Par conséquent, après l’annulation d’un accusé de réception de produit d’un chargement entrant, le magasinier doit réenregistrer les quantités d’articles pour les chargements.

Pour plus d’informations, consultez [Enregistrer les quantités d’articles qui arrivent dans un chargement entrant](/dynamics365/supply-chain/warehousing/inbound-load-handling#register-item-quantities-arriving).
