---
title: Impossible de faire des réservations d’inventaire, car 0,00 sont disponibles
description: Vous recevez une erreur indiquant que le système ne peut pas effectuer de réservation, car seulement 0,00 sont disponibles dans l’inventaire. Ce problème est probablement dû à un travail ouvert.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 75d72f7ee1bdecca5a087b75b1de9907b9d244ab
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476367"
---
# <a name="system-cant-make-reservations-because-000-are-available-in-the-inventory"></a>Le système ne peut pas faire de réservations, car 0,00 sont disponibles dans l’inventaire.

## <a name="symptoms"></a>Symptômes

Ce problème peut se produire si le système ne peut pas mettre à jour une quantité de stock car il n’y a pas suffisamment de transactions de stock qui ont les dimensions spécifiées. Vous recevrez le message d’erreur suivant :

> Site physique disponible=%1, Entrepôt=%2, Statut du stock=Disponible, Numéro de lot=%3, Propriétaire=%4 :%5 ne peut pas être réservé car seuls 0,00 sont disponibles dans le stock.

## <a name="resolution"></a>Résolution

Ce problème est probablement dû à un travail ouvert. Soit terminer le travail, soit recevez sans création de travail. Assurez-vous qu’aucune transaction de stock ne réserve physiquement la quantité. Par exemple, ces transactions peuvent être des commandes de qualité ouvertes, des enregistrements de blocage des stocks ou des commandes de sortie.
