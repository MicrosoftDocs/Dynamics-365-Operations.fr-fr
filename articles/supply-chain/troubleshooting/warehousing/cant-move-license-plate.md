---
title: Impossible de déplacer le contenant si Sortie nulle et Réception nulle sont autorisés
description: Vous ne pouvez pas déplacer de contenant si les options Sortie nulle et Réception nulle sont autorisées pour le numéro de série. Cela est corrigé en rendant le champ du numéro de série facultatif.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0047f79aa417c8fc910447505f07963d014f54e7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476328"
---
# <a name="cant-move-license-plate-if-serial-number-has-blank-issue-and-blank-receipt-allowed"></a>Impossible de déplacer le contenant si Sortie nulle et Réception nulle sont autorisés pour le numéro de série

## <a name="symptoms"></a>Symptômes

Vous ne pouvez pas déplacer un contenant à l’aide d’un élément de menu **Mouvement** si le numéro de série comporte des paramètres *Sortie nulle autorisée* et *Réception nulle autorisée* sur le groupe de dimensions de suivi, et s’il y a plusieurs contenants au même emplacement, dont certains ont des numéros de série et d’autres n'en ont pas.

## <a name="resolution"></a>Résolution

Ce problème sera résolu par les modifications déployées dans [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687). Ces changements rendront le champ **Numéro de série** facultatif lorsque Sortie nulle et Réception nulle sont autorisés.
