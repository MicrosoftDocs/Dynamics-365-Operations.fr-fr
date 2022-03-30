---
title: Différence inattendue entre les données de requête et de session lors des tests
description: Une différence inattendue se produit entre les données de demande et de session dans les résultats de validation des tâches de l’application d’entrepôt.
author: mamuszal
ms.date: 03/11/2022
ms.topic: troubleshooting
ms.search.form: WHSValidatorRunInstance_executeRun
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mamuszal
ms.search.validFrom: 2022-03-11
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: da8f0506a76b0d0cc02bfc2e1bff01b4ddccb578
ms.sourcegitcommit: 941119133be1765f653d5d5270dfdf58466e1d07
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/17/2022
ms.locfileid: "8456937"
---
# <a name="unexpected-difference-between-request-and-session-data-during-testing"></a>Différence inattendue entre les données de requête et de session lors des tests

Code d’erreur : WarehouseMobileDeviceRequestInputValidationError

## <a name="symptoms"></a>Symptômes

Lorsque vous utilisez la [structure de validation des tâches de l’application d’entrepôt](/dynamics365-release-plan/2019wave2/dynamics365-supply-chain-management/warehouse-app-task-validation-rsat), le validateur renvoie le message d’erreur suivant :

> Différence inattendue entre les données de requête et de session. Violation du protocole XML des appareils mobiles d’entrepôt.REQUEST_XML_TAMPERING

## <a name="cause"></a>Cause

L’erreur se produit lorsque la sortie de la dernière étape exécutée avec succès dans le test ne correspond pas à l’entrée enregistrée pour l’étape suivante. Cette situation peut survenir parce que le validateur de tâche n’utilise pas la sortie d’une étape précédente comme entrée pour une étape suivante. Au lieu de cela, il utilise XML enregistré comme entrée pour chaque étape.

Dans la plupart des cas, l’erreur se produit lorsque vous réexécutez une tâche, mais le test nécessite certains enregistrements qui ont été modifiés ou supprimés par une exécution précédente de la même tâche.

## <a name="resolution"></a>Résolution

L’exécution du test de validation de tâche d’application d’entrepôt n’est pas une opération idempotente, mais modifie les données sous-jacentes. Par conséquent, avant de réexécuter une tâche, vous devrez peut-être réinitialiser les données pertinentes.

1. Examinez le XML de sortie de la dernière étape de test réussie pour déterminer où votre test s’est arrêté.
1. Inspectez votre test et assurez-vous que toutes les commandes client, tous les ordres de transfert, en-têtes de travail et autres enregistrements requis sont toujours présents et dans l’état attendu.
1. Recréez ou modifiez les enregistrements manquants ou modifiés. Vous pouvez également créer une nouvelle configuration de test et concevoir le test pour utiliser des enregistrements existants valides.
