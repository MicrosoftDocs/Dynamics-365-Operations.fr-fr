---
title: Erreur de calcul de la comptabilité à rebours lors de la clôture des stocks
description: Dans les versions antérieures, vous avez peut-être rencontré une erreur de calcul de la comptabilité à rebours lors de la clôture des stocks. Ce problème a été résolu.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ae92b7121998d6b1ba2f08ea5736c55637867fbf
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476321"
---
# <a name="backflush-costing-calculation-error-during-inventory-closing"></a>Erreur de calcul de la comptabilité à rebours lors de la clôture des stocks

## <a name="symptoms"></a>Symptômes

Dans les versions antérieures à la version 10.0.13, si vous n’utilisez pas le flux de coûts de production allégé, vous recevez le message d’avertissement erroné suivant lors de la clôture des stocks :

> Vous êtes sur le point d’exécuter une clôture de stock avec une date %1. Aucune exécution d’un calcul de comptabilité à rebours avec une date %1 correspondant à la fin de la période a été enregistrée. N’oubliez pas d’exécuter un calcul de comptabilité à rebours avec une date de %1 correspondant à la fin de la période. L’évaluation des stocks, le coût des marchandises vendues et les écarts peuvent ne pas être corrects dans la comptabilité auxiliaire ou la comptabilité tant que cela n’a pas été exécuté.

## <a name="resolution"></a>Résolution

Ce problème a été résolu dans la version 10.0.13 et ultérieure. Pour plus d’informations, voir [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296).
