---
title: Résoudre les problèmes de traitement de la production
description: Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l'utilisation du traitement de la production.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 63993fca2164301d31dbfa1474a4cf5eb16273e6
ms.sourcegitcommit: 8eefb4e14ae0ea27769ab2cecca747755560efa3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2020
ms.locfileid: "4516779"
---
# <a name="troubleshoot-process-manufacturing"></a>Résoudre les problèmes de traitement de la production

Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l'utilisation du traitement de la production.

## <a name="when-i-use-the-job-card-device-to-report-a-partial-quantity-on-the-last-job-in-a-production-order-all-the-previous-jobs-on-that-order-that-have-a-status-of-in-progress-are-automatically-ended"></a>Lorsque j'utilise le périphérique des bons de travail pour signaler une quantité partielle sur le dernier travail d'un ordre de fabrication, tous les travaux précédents de cet ordre qui ont un statut En cours sont automatiquement terminés.

Ce comportement est fait exprès. Sur la page **Valeurs par défaut de l'ordre de fabrication**, sur l'onglet **Signaler comme terminé**, il existe une option nommée **Déclarer la gamme finie**. Si cette rubrique est définie sur *Oui*, un journal de fiches production est publié lorsqu'un collaborateur utilise le périphérique des bons de travail ou le terminal de bons de travail pour signaler la dernière opération. Ce journal marque toutes les opérations comme terminées et met fin à tous les travaux de production. Quand l'option **Déclarer la gamme finie** est définie sur *Oui*, le système ne prend pas en compte le statut du travail que le collaborateur a sélectionné lorsqu'il a signalé la dernière opération. Le système ne considère pas non plus si le collaborateur déclare une quantité totale ou partielle.

## <a name="when-i-attempt-a-stock-closing-i-receive-the-following-warning-message-no-execution-of-backflush-costing-calculation-with-a-date-1-matching-period-end-has-been-registered"></a>Lorsque je tente une clôture de stock, je reçois le message d'avertissement suivant : "Aucune exécution du calcul des coûts de comptabilité à rebours avec une date %1 la fin de la période correspondante a été enregistrée. »

Dans les versions antérieures à la version 10.0.13, si vous n'utilisez pas le flux de coûts de production allégé, vous recevez le message d'avertissement erroné suivant lors de la clôture des stocks :

> Vous êtes sur le point d'exécuter une clôture de stock avec une date %1. Aucune exécution d'un calcul de comptabilité à rebours avec une date %1 correspondant à la fin de la période a été enregistrée. N'oubliez pas d'exécuter un calcul de comptabilité à rebours avec une date de %1 correspondant à la fin de la période. L'évaluation des stocks, le coût des marchandises vendues et les écarts peuvent ne pas être corrects dans la comptabilité auxiliaire ou la comptabilité tant que cela n'a pas été exécuté.

Ce problème a été résolu dans la version 10.0.13 et ultérieure. Pour plus d'informations, voir [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296).
