---
title: Impossible de sélectionner le changement de statut du stock comme Type de travail
description: Vous ne pouvez pas créer de ligne de modèle de travail pour le changement de statut du stock car le type de travail est utilisé uniquement par les processus système. Sélectionnez un autre type de travail.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ad7f26f3235d15779583f9cdadeb4e6dca16242a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476370"
---
# <a name="cant-select-inventory-status-change-in-the-work-type-column"></a>Impossible de sélectionner le changement de statut du stock dans la colonne Type de travail

## <a name="symptoms"></a>Symptômes

Lors de la configuration de Microsoft Dynamics 365 Supply Chain Management, le message d'erreur suivant peut s'afficher :

> Vous ne pouvez pas créer de ligne de modèle de travail pour le changement de statut du stock car le type de travail n'est pas valide. Sélectionnez un autre type de travail.

## <a name="resolution"></a>Résolution

Ce comportement est fait exprès. Le type de travail *Changement du statut du stock* est utilisé uniquement par les processus système. Cette valeur peut être configurée. Étant donné que la liste des types de travail est fixée comme une énumération, les entrées supplémentaires ne peuvent pas être filtrées en dehors du menu déroulant **Type de travail**.
