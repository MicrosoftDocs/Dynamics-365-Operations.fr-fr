---
title: Vous ne pouvez pas confirmer une expédition, car le client est en attente
description: Vous ne pouvez pas confirmer une expédition, car le client est en attente.
author: GalynaFedorova
ms.date: 07/30/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 801778fc8f04b106bf168a3dcd5a89767a837740
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2021
ms.locfileid: "7344262"
---
# <a name="you-cant-confirm-a-shipment-because-the-customer-is-on-hold"></a>Vous ne pouvez pas confirmer une expédition, car le client est en attente

Code d’erreur : WAX:CustomerOnHoldShipmentCannotBeConfirmed

## <a name="symptoms"></a>Symptômes

Lorsque vous essayez de confirmer une expédition, le système affiche le message d’erreur suivant :

> L’expédition %1 ne peut pas être confirmée, car le client est en attente pour %2.

Par conséquent, vous ne pouvez pas confirmer l’expédition pour le chargement.

## <a name="cause"></a>Cause

Le compte client du chargement ou de l’expédition est en attente. Par conséquent, le statut du client empêche la confirmation de l’expédition.

## <a name="resolution"></a>Résolution

Utilisez la procédure suivante pour débloquer le compte client.

1. Allez dans **Comptabilité client \> Clients \> Tous les clients**.
1. Ouvrez le compte client pour lequel l’expédition ne peut pas être confirmée.
1. Sur le raccourci **Crédit et recouvrement**, définissez le champ **Facturation et livraison en attente** sur *Non*.
1. Répétez cette procédure pour tous les clients bloqués pour le chargement.
