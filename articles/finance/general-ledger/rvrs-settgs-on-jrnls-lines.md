---
title: Paramètres de contrepassation sur les journaux et les lignes
description: Cette rubrique explique pourquoi une écriture de contrepassation qui a été saisie dans un journal des opérations diverses peut ne pas être incluse dans la transaction validée.
author: kweekley
ms.date: 04/29/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-05
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ff8c0bda8e750e95261039b373cfb96a76034f6f
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8724443"
---
# <a name="reverse-settings-on-journals-and-lines"></a>Paramètres de contrepassation sur les journaux et les lignes

[!include [banner](../includes/banner.md)]

Cette rubrique explique pourquoi une écriture de contrepassation qui a été saisie dans un journal des opérations diverses peut ne pas être incluse dans la transaction validée.  

## <a name="symptom"></a>Problème

Un journal des opérations diverses comprend une écriture de contrepassation et une date de contrepassation. Lorsque vous validez le journal, aucun des justificatifs n’est contrepassé. Pourquoi ?

## <a name="resolution"></a>Résolution

Lorsque le journal est validé, le processus de contrepassation examine uniquement les paramètres des champs **Écriture de contrepassation** et **Date de contrepassation** sur la section **Lignes** du justificatif. Cette approche permet à un journal d’inclure certains justificatifs qui sont marqués pour contrepassation et d’autres qui ne le sont pas.

Les valeurs du journal sont utilisées par défaut uniquement lors de l’ajout de *nouvelles* lignes. La modification des valeurs dans le journal n’affecte pas les lignes existantes. Dans cet exemple, les lignes du justificatif ont été saisies en premier. Lorsque vous saisissez le détail de la ligne avant de désigner le journal comme contrepassation, la désignation comme écriture et date de contrepassation n’est appliquée à aucune ligne existante.

La modification de l’écriture ou de la date de contrepassation sur une ligne existante propage cette modification sur d’autres lignes du même document. Pour optimiser les performances, la grille n’est pas actualisée après la propagation des modifications vers d’autres lignes. Vous pouvez afficher les valeurs mises à jour en actualisant la grille.


