---
title: La vague n'est pas éligible pour le nettoyage
description: La vague n'est pas éligible pour le nettoyage
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWaveTable_WHSWaveProcessingDataCleanup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 99d76b6a90045be7630785769b11e43abaf4b789b1c4a134050b6ee396c71199
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6778504"
---
# <a name="wave-isnt-eligible-for-cleanup"></a>La vague n'est pas éligible pour le nettoyage

Code d'erreur : WaveNotEligibleForCleanup

## <a name="symptoms"></a>Symptômes

Le système affiche le message d'erreur suivant :

> La vague %1 n'est pas éligible pour le nettoyage.

Les données de la vague ne peuvent pas être nettoyées.  

## <a name="cause"></a>Cause

La vague est en cours de traitement, comme l'indique l'une des conditions suivantes :

- Le champ **Statut de vague** est défini sur *En cours d’exécution*.
- Lorsque vous sélectionnez **Traitement par lots** dans le groupe **Vague** de l'onglet **Vague** du volet Actions, le champ **Statut** n'est pas défini sur *Terminé*, *Erreur*, ou alors *Annulé*. Par conséquent, un traitement par lots est en cours d'exécution.

## <a name="resolution"></a>Résolution

Dans le volet Actions, sur l'onglet **Vague**, dans le groupe **Vague**, sélectionnez **Traitement par lots**, puis suivez l'une de ces étapes :

- Si le champ **Statut** est défini sur *Exécution* : Dans le volet Actions, sur l'onglet **Traitement par lots**, dans le groupe **Traitement par lots**, sélectionnez **Afficher les tâches**. Vous pouvez suivre la progression en actualisant la page **Tâches des traitements par lots**.
- Si le champ **Statut** n'est pas défini sur *Exécution* : Dans le volet Actions, sur l'onglet **Traitement par lots**, dans le groupe **Fonction**, sélectionnez **Modifier le statut**. Dans le champ **Sélectionner un nouveau statut**, sélectionnez *En attente*. Puis sélectionnez **OK**.
