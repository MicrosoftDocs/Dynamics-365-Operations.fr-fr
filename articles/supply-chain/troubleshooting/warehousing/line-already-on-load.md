---
title: L'une des lignes se trouve déjà sur un chargement
description: Cette page explique pourquoi vous avez peut-être reçu l'erreur « L'une des lignes se trouve déjà sur un chargement ». Lancement vers l'entrepôt impossible, et résolution du problème.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0bdfaed005b9c58f7bd5f87dd6dffe648de47261
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476386"
---
# <a name="one-of-the-lines-is-already-on-a-load"></a>L'une des lignes se trouve déjà sur un chargement

## <a name="symptoms"></a>Symptômes

Lorsque vous utilisez des opérations de création de chargement et d'expédition, le message d’erreur suivant peut s’afficher :

> L'une des lignes se trouve déjà sur un chargement. Lancement vers l'entrepôt impossible.

Si vous créez manuellement des chargements, ou si vous configurez le processus de sorte que les chargements soient déjà créés avant la saisie de la ligne de commande client, on suppose que la publication suivante sera effectuée manuellement et que l’itinéraire et le classement du chargement seront utilisés.

Dans un autre scénario possible, vous essayez d’effectuer une libération automatique dans l’entrepôt, mais le processus de vague n’a pas réussi à créer du travail. Par conséquent, une expédition ou un chargement en cours est toujours créé. Cet envoi ou chargement en cours bloque ensuite les tentatives ultérieures de validation automatique de la commande jusqu’à ce que vous supprimiez l’envoi ou le chargement en cours, ou que vous retraitez manuellement la vague.

## <a name="resolution"></a>Résolution

Vous pouvez effectuer le lancement à partir de la page de commande client, ou un lancement automatique peut être effectué à partir de la page de lancement de commande client, uniquement s’il n’y a pas de chargement avant le lancement vers l’entrepôt. Le chargement sera automatiquement créé après le traitement de la vague.
