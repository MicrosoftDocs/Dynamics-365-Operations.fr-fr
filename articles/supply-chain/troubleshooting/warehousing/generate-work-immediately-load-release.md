---
title: Générer le travail de prélèvement immédiatement lorsque le chargement est lancé
description: Si le travail doit être généré immédiatement lorsque la charge est libérée, vous devez configurer le modèle de vague en conséquence. Cette page vous guide à travers les étapes.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: fdeb0b27f4d2c1a2cc9f8e0c4ba537cdce604bd2
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476354"
---
# <a name="picking-work-isnt-generated-immediately-when-outbound-load-is-released"></a>Le travail de prélèvement n'est pas généré immédiatement lorsque le chargement sortant est lancé

## <a name="symptoms"></a>Symptômes

Vous créez un chargement sortant à l'aide d'une commande client ou d'un ordre de transfert, et lancez le chargement vers l'entrepôt. Vous remarquez cependant qu’aucun travail de prélèvement n’a encore été généré.

## <a name="resolution"></a>Résolution

Si le travail doit être généré immédiatement lorsque la charge est libérée, vous devez configurer le modèle de vague en conséquence. Sur le modèle de vague, définissez les options suivantes sur *Oui* :

- Création automatique de vagues
- Traiter la vague au lancement vers l'entrepôt
- Sortie automatique de vagues
