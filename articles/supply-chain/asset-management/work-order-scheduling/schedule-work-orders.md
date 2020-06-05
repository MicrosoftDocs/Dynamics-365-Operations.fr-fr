---
title: Planifier des ordres de travail
description: Cette rubrique explique comment planifier des ordres de travail dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
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
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e98a30a03856f5532d420e516cb35d66acffb278
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383480"
---
# <a name="schedule-work-orders"></a>Planifier des ordres de travail

[!include [banner](../../includes/banner.md)]

 

Cette rubrique explique comment planifier des ordres de travail dans le module Gestion des actifs. 

Le nombre d'heures requises pour un ordre de travail est défini par la somme des heures prévues moins les heures validées. Si plus de temps est nécessaire, les prévisions doivent être ajustées en conséquence. Dans **Gestion des actifs** > **Commun** > **Ordres de travail** > **Tous les ordres de travail** ou **Ordres de travail actifs**, vous pouvez afficher ou modifier des prévisions sur un ordre de travail en sélectionnant l'ordre de travail et en cliquant sur **Prévisions** sur l'onglet **Ordre de travail** . Lorsque les ordres de travail ont été créés et estimés, l'étape suivante d'exécution des ordres de travail consiste à répartir les agents et les outils nécessaires de maintenance.

Seuls les ordres de travail avec un état du cycle de vie de l'ordre de travail qui permet la planification peuvent être planifiés. Autoriser la planification est configuré dans **Gestion des actifs** > **Paramétrage** > **Ordres de travail** > **États du cycle de vie** > **Général** organisateur > bouton à bascule **Autoriser la planification**.

1. Cliquez sur **Gestion des actifs** > **Commun** > **Ordres de travail** > **Tous les ordres de travail**.

2. Sélectionnez les ordres de travail que vous souhaitez planifier dans la liste. Par exemple, vous pouvez trier la liste par **État du cycle de vie actuel**.

3. Sous l'onglet **Général**, cliquez sur **Planifier**.

4. Dans la boîte de dialogue **Planifier les ordres de travail**, vous pouvez ajouter des sélections concernant la date de début prévue et le niveau de service, le cas échéant. Si le processus de planification doit respecter des limites de capacité pour les ressources déjà planifiées avec d'autres tâches, assurez-vous que les boutons à bascule **Actif**, **Outil** et **Collaborateur** sont définis sur « Oui ».

    [!NOTE]
    Si vous définissez les boutons à bascule **Actif**, **Outil** et **Agent** sur « Non », les réservations existantes seront ignorées. Dans la fenêtre Infos, une liste des planifications des ordres de travail se chevauchant s'affiche, et vous pouvez cliquer sur les messages pour ouvrir un ordre de travail et replanifier, le cas échéant.

5. Pour afficher des informations détaillées sur le processus de planification, sélectionnez « Oui » sur le bouton à bascule **Détaillé**. Cela signifie que des informations détaillées sur les scores calculés sur les ordres de travail et les agents de maintenance sont affichées dans la fenêtre Infos.

6. Cliquez sur **OK** pour démarrer le processus de planification.

7. Lorsque la planification est terminée, une fenêtre Infos affiche le nombre d'ordres de travail planifiés, ainsi que des informations plus détaillées si le bouton à bascule **Détaillé** a été défini « Oui ».

>[!NOTE]
>Les ordres de travail sont planifiés dans un cycle par ordre de travail, et non par tâche d'ordre de travail. Vous pouvez également ouvrir la boîte de dialogue **Planifier les ordres de travail** directement dans **Gestion des actifs** > **Périodique** > **Ordres de travail** > **Planifier les ordres de travail**. Effectuez vos sélections et cliquez sur **OK** pour commencer la planification des ordres de travail. Il est possible de paramétrer une planification des ordres de travail comme traitement par lots dans la boîte de dialogue **Planifier les ordres de travail** > organisateur **Exécuter à l'arrière-plan**.

*Exemple :* Dans la figure ci-dessous, la formule insérée dans le champ **Début prévu** génère la planification des ordres de travail pour tous les ordres de travail avec la date de début prévue à compter d'une semaine à partir de maintenant et ultérieurement. Cette formule peut s'avérer utile lorsque vous exécutez la planification des ordres de travail sur une base actuelle, mais que vous souhaitez vous assurer que les ordres de travail pour les 5-6 prochains jours ne sont pas replanifiés.

![Figure 1](media/03-work-order-scheduling.png)

Le type d'ordre de travail associé aux ordres de travail peut configurer la planification pour un agent de maintenance (bouton à bascule **Gestion des actifs** > **Paramétrage** > **Ordres de travail** > **Types d'ordre de travail** > **Un agent de maintenance** défini sur « Oui »). Cela signifie que si le type d'ordre de travail est utilisé sur un ordre de travail, le bouton à bascule **Un agent de maintenance** est automatiquement défini sur « Oui » sur la page des détails **Tous les ordres de travail** > vue **En-tête** > organisateur **Planifier**. Lors de la planification des ordres de travail, toutes les tâches des ordres de travail créées sur l'ordre de travail sont ensuite planifiées au même agent de maintenance. Le cas échéant, vous pouvez modifier la sélection sur le bouton à bascule **Un agent de maintenance** dans **Tous les ordres de travail** pour autoriser la planification de plusieurs agents ou un agent sur les tâches de l'ordre de travail.

Le processus de planification dans le module Gestion des actifs inclut plusieurs facteurs dans le calcul de la planification :

- Calculer les scores pour les ordres de travail et des agents de maintenance. Les scores pour les ordres de travail et des agents de maintenance sont paramétrés dans **Paramètres de gestion des actifs**. 
- En vérifiant la correspondance des compétences, à savoir les aptitudes et les certificats, nécessaires pour exécuter la tâche. Les compétences et les certificats sont paramétrés sur les agents de maintenance dans le module **Ressources humaines** (**Ressources humaines** > **Agents** > **Agents** > sélectionnez l'agent dans la liste > onglet **Agent** > section **Compétences** > **Qualifications** et les boutons **Certificats** ). En outre, les qualifications et les certificats peuvent être ajoutés aux types de tâches de maintenance et aux opérations de tâches de maintenance. En savoir plus sur les compétences et les types de tâche de maintenance dans [Catégories de type de tâche de maintenance et types de tâches de maintenance, variantes de type de tâche de maintenance, opérations de tâches de maintenance et listes de contrôle de maintenance](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).  

## <a name="scores-used-in-work-order-scheduling"></a>Scores utilisés dans la planification des ordres de travail

Calcul des scores pour une tâche des ordres de travail selon la date de début prévue et le niveau de service de l'ordre de travail.

Calcul **Date de début** : pour chaque future date calculée à partir de la date de début prévue, le score de la date de début est soustrait et multiplié par le score, qui est « 10 » dans les exemples ci-dessous.

Calcul de l'**Élément critique** : le score de l'élément critique multiplié par l'élément critique sur l'ordre de travail.

Calcul du **Niveau de service** : le score de niveau de service est divisé par le niveau de service sur l'ordre de travail.

Dans les exemples ci-dessous, le score de l'élément critique est « 2 », et les scores du niveau de service sont « 5 » et « 100 ».

**Exemple 1 :**

| ID d'ordre de travail | Date de début prévue | Élément critique des ordres de travail | Niveau de service de l'ordre de travail | Calcul               | Score      |
|---------------|---------------------|------------------------|--------------------------|---------------------------|------------|
| WO-00010816   | Demain            | 2                      | 20              | (-1 \* 10) + (2 \* 2) + 5 / 20     | \- 5.75    |
| WO-00010817   | Deux jours à partir de maintenant   | 2                      | 20              | (-2 \* 10) + (2 \* 2) + 5 / 20     | \- 15.75   |
| WO-00010818   | Deux jours à partir de maintenant   | 3                      | 5               | (-2 \* 10) + (2 \* 3) + 5 / 5      | \- 13      |

Les ordres de travail sont planifiés dans l'ordre suivant : WO-000108**16**, WO-000108**18**, WO-000108**17**.

**Exemple 2 :**

| ID d'ordre de travail | Date de début prévue | Élément critique des ordres de travail | Niveau de service de l'ordre de travail | Calcul                 | Score    |
|---------------|---------------------|------------------------|---------------------|----------------------------------|----------|
| WO-00010816   | Demain            | 2                      | 20                  | (-1 \* 10) + (2 \* 2) + 100 / 20 | \- 1     |
| WO-00010817   | Deux jours à partir de maintenant   | 2                      | 20                  | (-2 \* 10) + (2 \* 2) + 100 / 20 | \- 11    |
| WO-00010818   | Deux jours à partir de maintenant   | 3                      | 5                   | (-2 \* 10) + (2 \* 3) + 100 / 5  | 6        |

Si le score du niveau de service est augmenté à « 100 » au lieu de « 5 », l'ordre de planification est : WO-000108**18**, WO-000108**16**, WO-000108**17**.

Les scores concernant le calcul du travail des agents de maintenance sur les ordres de travail sont tous configurés comme nombres, qui sont ajoutés à chaque calcul d'agent de maintenance pendant la planification des ordres de travail. L'agent de maintenance avec le score le plus élevé est sélectionné sur l'ordre de travail. Voici une courte description des scores de l'agent de maintenance :

| Score de l'agent de maintenance| Description |
|---|---|
| Collaborateur responsable | Si l'agent de maintenance est sélectionné comme agent responsable sur l'ordre de travail, le score est ajouté. |
| Groupe d'agents de maintenance responsables | Si l'agent de maintenance fait partie du groupe d'agents de maintenance responsable sur l'ordre de travail, le score est ajouté. |
| Agent de maintenance préféré         | Si l'agent est sélectionné comme agent de maintenance préféré sur l'actif, le score est ajouté. |
| Groupe d'agents de maintenance préféré   | Si l'agent fait partie du groupe d'agents de maintenance préférés sur l'actif, le score est ajouté.  |
| Emplacement  | Si votre société utilise des postes techniques, les agents de maintenance reçoivent le score total s'ils sont situés au poste technique lié à l'actif. Si le poste technique de l'actif a un emplacement parent, les agents de maintenance à ce poste technique obtiennent le score de 1/2. Si cet emplacement a également un parent, les agents de maintenance sous cet emplacement obtiennent un score de 1/3. Si cet emplacement a également un parent, les agents de maintenance sous cet emplacement obtiennent un score de 1/4, etc. Si votre société utilise l'emplacement de l'actif, ce que nous ne recommandons pas, le lieu, la zone, et la région sont utilisés pour calculer les scores du lieu. Les collaborateurs reçoivent le score total s'ils sont situés au lieu, dans la zone et dans la région liés à l'actif. Si le lieu du collaborateur correspond uniquement au lieu et à la région, le score de l'agent de maintenance est de 2/3 du score total. Si le lieu de l'agent de maintenance correspond uniquement au lieu, le score de l'agent de maintenance est de 1/3 du score total. |
| Date de début du collaborateur  | Pour chaque date à laquelle la date de début prévue est ultérieure à la date de début prévue, le score est soustrait.  |

>[!NOTE]
>Si un score est défini sur « 0 », ce score n'est pas calculé. Cela est utile si, par exemple, si vous ne voulez pas inclure d'agent responsable dans votre planification.

## <a name="competencies-used-in-work-order-scheduling"></a>Compétences utilisées dans la planification des ordres de travail

Les exigences en matière de qualifications et de certificat peuvent être paramétrés sur les types de tâches de maintenance (**Gestion des actifs** > **Paramétrage** > **Tâches** > **Types de tâches de maintenance**) et les opérations des tâches de maintenance (**Gestion des actifs** > **Paramétrage** > **Tâches** > **Opération de tâche de maintenance**). 

Les types de tâche de maintenance et les opérations de tâche de maintenance sont sélectionnées sur les tâches de l'ordre de travail. Si des qualifications ou des certificats ont été sélectionnés sur un type de tâche de maintenance ou sur une opération de tâche de maintenance, et si ce type de tâche de maintenance ou cette opération de tâche de maintenance est utilisé(e) sur une tâche de tâche de maintenance, seuls les agents de maintenance avec des qualifications et des certificats correspondants sont prévus pour travailler sur l'ordre de travail.

<a name="gantt"></a>

## <a name="work-with-scheduled-work-orders-using-a-gantt-chart"></a>Utiliser des ordres de travail planifiés à l'aide d'un diagramme de Gantt

Le **Diagramme de Gantt des ordres de travail planifiés** fournit une interface graphique où vous pouvez afficher et replanifier vos ordres de travail.

Pour afficher et utiliser le diagramme de Gantt :

1. Aller à **Gestion des actifs > Ordres de travail > Diagramme de Gantt des ordres de travail planifiés**.

1. Utilisez les listes déroulantes et les champs de la section **Paramètres** pour définir l'emplacement fonctionnel, la durée et l'échelle de temps à afficher dans le diagramme de Gantt.

1. Sélectionnez **Appliquer**.

    - Le diagramme de Gantt est mis à jour pour afficher les ordres de travail planifiés qui correspondent à vos paramètres. Chaque ordre de travail est représenté par un rectangle bleu.
    - Pour replanifier un ordre de travail affiché, sélectionnez-le, puis faites-le glisser vers les nouvelles date et heure appropriées.

1. Si vous avez apporté des modifications, cliquez sur **Enregistrer** dans le volet Actions pour les enregistrer.
