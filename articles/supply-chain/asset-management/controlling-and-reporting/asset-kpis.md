---
title: Indicateurs de performance clé de l’actif
description: Cette rubrique explique les indicateurs de performance clés d’actif dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectKPI
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 90759931fcbdb1e5acbd62f8a40e5b37b918f31a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813867"
---
# <a name="asset-kpis"></a>Indicateurs de performance clé de l’actif

[!include [banner](../../includes/banner.md)]

 

Dans le module Gestion des actifs, vous pouvez calculer plusieurs indicateurs de performance clé (KPI) pour les actifs et les types d’actifs. Vous pouvez utiliser des KPI pour avoir une vue d’ensemble des performances des actifs en termes, par exemple, de temps de fonctionnement, d’interruption, de temps de réparation et de temps moyen de bon fonctionnement.

1. Cliquez sur **Gestion des actifs** > **Recherches** > **Actifs** > **Indicateurs de performance clés de l’actif**.

2. Dans la boîte de dialogue **Calculer les indicateurs de performance clé de l’actif**, sélectionnez l’**Échelle de temps** à utiliser dans le calcul et une période dans les champs **Date de début** et **Date de fin**. 

3. Dans l’organisateur **Enregistrements à inclure**, sélectionnez des actifs spécifiques et des types d’actifs à inclure dans le calcul, si nécessaire.

4. Cliquez sur **OK** pour démarrer le calcul.

5. Dans l’organisateur **Vue d’ensemble**, les résultats du calcul sont affichés dans la vue Grille. Chaque actif est affiché sur une ligne distincte.

6. Dans l’organisateur **KPI pour la ligne sélectionnée**, vous pouvez afficher des calculs pour l’actif sélectionné sous l’organisateur **Vue d’ensemble**. Les valeurs de KPI sont classées par catégorie : **Heure**, **Disponibilité**, **Ordres de travail**, **Maintenance**, **Défaillances**, **Temps d’arrêt pour maintenance** et **Coût**.

Le tableau ci-dessous présente une description des champs de la page **Indicateurs de performance clés de l’actif**.

| Champ                   | Description                                                                                                                                                                                                                                                                                           |
|-------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Actif                   | ID actif.                                                                                                                                                                                                                                                                                             |
| Durée totale              | Paramétrage de durée totale dans le calendrier utilisé dans le calcul. Si l’actif est associé à une ressource, le calendrier de la ressource associée est utilisé. Si l’actif n’est pas lié à une ressource, le calendrier sélectionné dans le champ **Calendrier standard** dans **Paramètres de gestion des actifs** est utilisé. |
| Durée active                  | Temps total moins l’interruption.                                                                                                                                                                                                                                                                            |
| Temps d’arrêt                | Enregistrements de temps d’arrêt pour maintenance effectués sur l’actif dans la période sélectionnée.                                                                                                                                                                                                                              |
| Heure de réparation             | Nombre total d’heures de travail passées sur les ordres de travail de réparation.                                                                                                                                                                                                                                            |
| Disponibilité en %          | Temps de fonctionnement divisé par la durée totale et multiplié par 100.                                                                                                                                                                                                                                                   |
| Nombre de problèmes        | Numéro de causes de défaillance enregistrées sur les symptômes de défaillance sur l’actif dans la période sélectionnée.                                                                                                                                                                                                             |
| MTBF                    | Temps moyen de bon fonctionnement, à savoir la durée totale divisée par le nombre de défaillances enregistrées pour l’actif dans la période sélectionnée. Si le nombre de défaillances est de zéro, le temps moyen de bon fonctionnement est défini sur la durée totale.                                                                                                                   |
| Taux de défaillance               | 1 divisé par le temps moyen de bon fonctionnement,                                                                                                                                                                                                                                                                                    |
| MRT                     | Temps moyen de réparation, à savoir le temps de réparation divisé par le nombre de défaillances enregistrées pour l’actif dans la période sélectionnée. Si le nombre de défaillances est de zéro, le temps moyen de réparation est défini sur le temps de réparation.                                                                                                                           |
| Nombre d’arrêts         | Nombre d’enregistrements de temps d’arrêt de maintenance créés sur l’actif.                                                                                                                                                                                                                                     |
| MTBS                    | Temps moyen entre les arrêts, à savoir la durée totale divisée par le nombre d’enregistrements de temps d’arrêt de maintenance. Si le nombre d’enregistrements de temps d’arrêt de maintenance est de zéro dans la période sélectionnée, la valeur du temps moyen entre les arrêts est définie sur la durée totale.                                                                                      |
| Coût préventif         | Coûts validés sur l’actif associé au type de coût « Préventif » dans la période sélectionnée. Les types de coûts sont définis sur les types d’ordres de travail.                                                                                                                                                                       |
| Coût correctif         | Coûts validés sur l’actif associé au type de coût « Correctif » dans la période sélectionnée. Les types de coûts sont définis sur les types d’ordres de travail.                                                                                                                                                                       |
| Valeur de remplacement       | Valeur définie sur l’actif comme coût de remplacement.                                                                                                                                                                                                                                                  |
| Type d’actif             | Identification du type d’actif sélectionné sur l’actif.                                                                                                                                                                                                                                             |
| Fabricant           | Identification du fabricant sélectionné sur l’actif.                                                                                                                                                                                                                                                 |
| Modèle                   | Identification du modèle de fabricant sélectionné sur l’actif.                                                                                                                                                                                                                                           |
| Date de début               | Date de début du calcul de KPI. Si l’immobilisation a été créée après la date de début indiquée pour le calcul, la date de début de l’actif est affichée dans ce champ.                                                                                                                                  |
| Au                 | Date de fin du calcul de KPI. Si l’actif a été enregistré comme inactif avant la date de fin sélectionnée pour le calcul, la date à partir de laquelle l’actif n’est plus actif est affichée dans ce champ.                                                                                               |
| Durée              | Lors du calcul des KPI, vous devez sélectionner une échelle de temps à utiliser : Heures, Jours, ou Semaines.                                                                                                                                                                                                            |
| Disponibilité            | Temps de fonctionnement divisé par la durée totale.                                                                                                                                                                                                                                                                         |
| Ordres de travail             | Nombre total d’ordres de travail inclus dans le calcul de KPI.                                                                                                                                                                                                                                          |
| Temps d’ordre de travail         | Nombre total d’heures de travail passées sur les ordres de travail.                                                                                                                                                                                                                                               |
| Ordres de travail principaux     | Nombre d’ordres de travail principaux inclus dans le calcul de KPI.                                                                                                                                                                                                                                        |
| Ordres de travail secondaires   | Nombre d’ordres de travail secondaires inclus dans le calcul de KPI.                                                                                                                                                                                                                                      |
| Ordres de travail de maintenance | Nombre d’ordres de travail de maintenance inclus dans le calcul de KPI. Un ordre de travail de maintenance est un ordre de travail sans causes de défaillance associées.                                                                                                                                                             |
| Temps de maintenance        | Nombre total d’heures de travail passées sur les ordres de travail de maintenance.                                                                                                                                                                                                                                       |
| Ordres de travail de réparation      | Nombre d’ordres de travail de réparation inclus dans le calcul de KPI. Un ordre de travail de réparation est un ordre de travail avec une cause de défaillance associée.                                                                                                                                                                        |
| Fiabilité en %           | Calcul basé sur le développement exponentiel prévu dans les enregistrements de défaillance sur un actif, ce qui signifie que, dans le temps, l’actif devient moins fiable en raison de l’usure. Le calcul de ce KPI est basé sur le temps moyen de bon fonctionnement et la durée totale.                                                            |
| MTPS                    | Durée moyenne des arrêts de fabrication, à savoir le temps d’arrêt pour maintenance divisé par le nombre d’enregistrements de temps d’arrêt de maintenance. Si le nombre d’enregistrements de temps d’arrêt de maintenance est de zéro dans la période sélectionnée, la valeur du temps moyen entre les arrêts est définie sur zéro.                                                                               |
| Coût total              | Coûts totaux validés sur l’actif dans la période sélectionnée.                                                                                                                                                                                                                                              |
| Coût de l’investissement         | Coûts validés sur l’actif associé au type de coût « Investissement » dans la période sélectionnée. Les types de coûts sont définis sur les types d’ordres de travail.                                                                                                                                                                       |

L’illustration suivante présente une capture d’écran d’un calcul de KPI pour quatre actifs.

![Capture d’écran d’un calcul d’indicateur de performance clé pour quatre actifs](media/11-controlling-and-reporting.png)

- Vous pouvez choisir plusieurs actifs dans **Tous les actifs** et cliquer sur le bouton **Indicateurs de performance clés de l’actif** sur l’onglet **Général**. Ensuite, cliquez sur **Ajouter** dans la boîte de dialogue **Calculer les indicateurs de performance clé de l’actif** pour calculer des indicateurs de performance clé pour les actifs sélectionnés.  
- Les résultats d’un calcul de KPI peuvent inclure ou pas des [enregistrements de temps d’arrêt de maintenance](../work-orders/maintenance-downtime.md), selon le paramétrage et l’utilisation des codes motif de temps d’arrêt pour maintenance. 



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]