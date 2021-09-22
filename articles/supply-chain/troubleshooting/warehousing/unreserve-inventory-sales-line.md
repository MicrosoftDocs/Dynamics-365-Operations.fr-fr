---
title: Impossible d’annuler la réservation de l’inventaire sur une ligne de commande client
description: S’il y a du travail en cours sur une ligne de vente et que vous essayez d’annuler la réservation de l’inventaire sur la ligne, vous recevez une erreur. Complétez ou supprimez des travaux pour libérer la réservation.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 1a042065dc4cd637aff58e55cf16179b7022f6ca
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476345"
---
# <a name="cant-unreserve-inventory-on-a-sales-order-line"></a>Impossible d’annuler la réservation de l’inventaire sur une ligne de commande client

## <a name="symptoms"></a>Symptômes

S’il y a du travail en cours sur une ligne de vente et que vous essayez d’annuler la réservation de l’inventaire sur cette ligne, vous recevez le message d’erreur suivant :

> Impossible de supprimer les réservations, car un travail qui a été créé repose sur celles-ci.

## <a name="resolution"></a>Résolution

Vérifiez s’il existe un travail de groupe d’emballage ouvert pour amener l’article d’une station d’emballage à un autre emplacement (tel que *Baydoor*). Passez en revue les enregistrements sur les pages **Journal de l’historique de création de travail** et **Détails du travail** pour déterminer ce qui réserve physiquement le stock, puis terminer ou supprimer le travail pour libérer la réservation.
