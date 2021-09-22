---
title: Impossible de libérer à nouveau une charge partiellement expédiée vers l’entrepôt
description: Dans les versions précédentes, vous ne pouviez pas libérer à nouveau une charge partiellement expédiée lors de l’utilisation de certaines fonctionnalités avec des réservations incomplètes. Cela a été résolu.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0380e1963a38f2be55b31e06b3845f935661eed2
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476353"
---
# <a name="cant-re-release-a-partially-shipped-load-to-the-warehouse"></a>Impossible de libérer à nouveau une charge partiellement expédiée vers l’entrepôt

## <a name="symptoms"></a>Symptômes

Vous ne pouvez pas libérer une charge partiellement libérée vers l’entrepôt. Lorsque vous effectuez le lancement dans l’entrepôt, un message « Opération terminée » apparaît, mais rien ne se passe et aucun travail n’est créé pour la quantité restante. Ce problème se produit lorsque vous utilisez la fonctionnalité de chargement de transport et qu’il y a une réservation incomplète.

## <a name="resolution"></a>Résolution

Le [problème KB 470069](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) ("Les chargements partiellement expédiés peuvent être relancés et retraités") est corrigé dans la [version 10.0.15](/dynamics365/supply-chain/get-started/whats-new-scm-10-0-15).
