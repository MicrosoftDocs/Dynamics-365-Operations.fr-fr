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
ms.openlocfilehash: 3e5142cf40a6c0d308e8e952bbe17e85b498826d
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924325"
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
