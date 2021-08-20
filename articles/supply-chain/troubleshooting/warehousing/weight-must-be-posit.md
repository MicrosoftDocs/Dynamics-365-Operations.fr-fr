---
title: Le poids doit être positif
description: Le poids doit être positif
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSContainerCloseDiag_canClose
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 27ec37e0c0644ff10ece4626d5c136bca3c52ef12f1c6de947afd03003a5368a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6776774"
---
# <a name="weight-must-be-positive"></a>Le poids doit être positif

Code d'erreur : WeightMustBePositive

## <a name="symptoms"></a>Symptômes

Le système affiche le message d'erreur suivant :

> Le poids doit être positif.

## <a name="cause"></a>Cause

Le champ **Poids brut** est défini sur *0* (zéro) ou une valeur négative.

## <a name="resolution"></a>Résolution

Pour spécifier un poids, suivez l’une des étapes suivantes :

- Définissez une valeur dans le champ **Poids brut**. Sélectionnez ensuite une unité dans la liste déroulante.
- Sélectionnez **Obtenir le poids système** pour calculer la valeur **Poids brut**.
