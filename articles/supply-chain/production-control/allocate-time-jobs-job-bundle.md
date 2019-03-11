---
title: Répartir du temps aux tâches figurant dans un regroupement de tâches
description: Dans Contrôle et suivi de la production, vous pouvez regrouper des tâches. Vous pouvez ensuite démarrer plusieurs tâches simultanément dans la page Liste de tâches.
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgBundleSlize, JmgProdParameters, JmgRegistration
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 55591
ms.assetid: 358efce7-73c8-4d2a-a7f7-cb99b88ab6ee
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 33d6bab9beb28d18e2094d7fb5e670e9425aac39
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "329112"
---
# <a name="allocate-time-to-jobs-in-a-job-bundle"></a>Répartir du temps aux tâches figurant dans un regroupement de tâches

[!include [banner](../includes/banner.md)]

Dans Contrôle et suivi de la production, vous pouvez regrouper des tâches. Vous pouvez ensuite démarrer plusieurs tâches simultanément dans la page Liste de tâches.

Si vous regroupez des tâches, vous devez définir de quelle manière le total des heures enregistrées pour toutes les tâches doit être affecté à chaque tâche. Vous pouvez définir la répartition en sélectionnant l'une des options suivantes dans le champ **Type d'offre groupée** sur la page **Clés de répartition** :

-   **Estimation** – Division des heures entre les tâches sur la base de leur durée estimée.
-   **Tâches** – Division des heures en fonction du nombre total de tâches groupées et du temps passé à leur accomplissement.
-   **Temps net** – Division égale des heures entre les tâches.
-   **Temps réel** – Répartition de la durée réelle de la tâche. Le coût peut être calculé sur la base du coût réel des salaires. **Remarque :** La clé de répartition **Temps réel** est disponible uniquement si votre société utilise la fonctionnalité Paie dans le module Pointage.

Les résultats des différentes clés de répartition sont illustrés dans les exemples suivants.

## <a name="example-scenario"></a>Exemple de scénario
Trois tâches de votre file d'attente des tâches doivent être effectuées. Vous entamez la première tâche, puis la deuxième et la troisième pendant que la première est en cours. Vous regroupez ainsi les trois tâches. Le tableau suivant indique le délai de production estimé pour chaque tâche.

| tâche   | Délai de production |
|-------|-----------------|
| Tâche 1 | 1 heure          |
| Tâche 2 | 3 heures         |
| Tâche 3 | 4 heures         |
| Total | 8 heures         |

Le tableau suivant indique les heures de travail consacrées à chaque tâche.

| tâche    | Heure de début | Échéance | Temps groupé |
|--------|------------|----------|-------------|
| Tâche 1  | 09h00      | 11h00    | 2 heures     |
| Tâche 2  | 10h00      | 13h00    | 3 heures     |
| Tâche 3  | 10h00      | 15h00    | 5 heures     |
| Groupe | 09h00      | 15h00    | 6 heures     |

Les sections suivantes décrivent les résultats du temps calculé pour chaque clé de répartition.

## <a name="estimation-allocation-key"></a>Clé de répartition de l'estimation
Le tableau suivant illustre la formule de calcul du délai imparti. Voici la formule : Temps par tâche = Temps groupé total × (Temps de la tâche estimé ÷ Temps total estimé)

| Mission   | Formule           | Temps réparti |
|-------|-------------------|----------------|
| Tâche 1 | 6 × (1 ÷ 8) heures | 0,75 heure      |
| Tâche 2 | 6 × (3 ÷ 8) heures | 2,25 heures     |
| Tâche 3 | 6 × (4 ÷ 8) heures | 3,00 heures     |

## <a name="jobs-allocation-key"></a>Clé de répartition des tâches
Le tableau suivant illustre la formule de calcul du délai imparti. Voici la formule : Temps par tâche = Temps total groupé ÷ Nombre de tâches

| Mission   | Formule | Temps réparti |
|-------|---------|----------------|
| Tâche 1 | 6 ÷ 3   | 2 heures        |
| Tâche 2 | 6 ÷ 3   | 2 heures        |
| Tâche 3 | 6 ÷ 3   | 2 heures        |

## <a name="net-time-allocation-key"></a>Clé de répartition du temps net
Le tableau suivant illustre la formule de calcul du délai imparti. Voici la formule : Temps calculé par déclaration = Temps groupé ÷ Nombre de tâches

|                              | 09h00-10h00 (1 heure) | 10h00-11h00 (1 heure) | 11h00-13h00 (2 heures) | 13h00-15h00 (2 heures) | Temps réparti |
|------------------------------|----------------------|----------------------|-----------------------|-----------------------|----------------|
| Nombre de tâches du regroupement. | 1                    | 3                    | 2                     | 1                     | Non applicable |
| Tâche 1                        | 1 ÷ 1 = 1 heure       | 1 ÷ 3 = 0,33 heure    | Non applicable        | Non applicable        | 1,33 heure     |
| Tâche 2                        | Non applicable       | 1 ÷ 3 = 0,33 heure    | 2 ÷ 2 = 1 heure        | Non applicable        | 1,33 heure     |
| Tâche 3                        | Non applicable       | 1 ÷ 3 = 0,33 heure    | 2 ÷ 2 = 1 heure        | 2 ÷ 1 = 2 heures       | 3,33 heures     |

## <a name="real-time-allocation-key"></a>Clé de répartition en temps réel
Si vous souhaitez autoriser le calcul des coûts de production en fonction des coûts réels, vous devez désactiver l'option **Catégorie de coûts** sur la page **Valeurs par défaut de l'ordre de fabrication**. Le tableau suivant illustre la formule de calcul du délai imparti. Voici la formule : Temps réel par tâche = Temps réel de l'offre groupée

| Mission   | Heure réelle |
|-------|-------------|
| Tâche 1 | 2 heures     |
| Tâche 2 | 3 heures     |
| Tâche 3 | 5 heures     |

Supposons que les 3 tâches sont réalisées par un collaborateur dont le salaire horaire a la valeur 12,00 EUR. Aucune prime ni aucun bonus pour heures supplémentaires n'est versé pour les tâches. Le collaborateur a travaillé sur ces 3 tâches groupées pour un total de 6 heures. Le coût du salaire est alors 6 × 12,00 EUR = 72,00 EUR. En utilisant une répartition en temps réel, le coût horaire est recalculé à l'aide du facteur de la formule Temps net. Le temps réel consacré à chaque tâche est ensuite transféré avec le prix de revient horaire corrigé. Dans l'exemple, 6 heures sont dépensées alors que 10 heures ont été réparties. Le tableau suivant illustre la formule de calcul du coût. Voici la formule : Coût horaire = (Temps total groupé par tâche (Temps net) ÷ Temps réel par tâche) × Coût horaire standard

| Mission   | Calcul du coût horaire corrigé | Coût horaire corrigé | Temps réparti | Coût total de la tâche |
|-------|----------------------------------------|-------------------------|----------------|-------------------|
| Tâche 1 | (1,33 ÷ 2) × 12,00 EUR                 | 8,00 EUR                | 2 heures        | 16,00 EUR         |
| Tâche 2 | (1,33 ÷ 3) × 12,00 EUR                 | 5,33 EUR                | 3 heures        | 16,00 EUR         |
| Tâche 3 | (3,33 ÷ 5) × 12,00 EUR                 | 8,00 EUR                | 5 heures        | 40,00 EUR         |

Le coût horaire corrigé et le temps de tâche sont validés dans le journal de production. **Remarque :** Si vous sélectionnez l'option **Catégorie de coûts** de l'onglet **Général** sur la page **Valeurs par défaut de l'ordre de fabrication**, le temps réel pour chaque tâche est transféré vers un journal de production, où le coût est appliqué à la catégorie de coûts de la tâche spécifique.



