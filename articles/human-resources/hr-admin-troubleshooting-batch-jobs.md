---
title: Optimiser les performances en planifiant des traitements par lots après les heures de travail
description: Cette rubrique explique comment résoudre les problèmes de performances avec Microsoft Dynamics 365 Human Resources en planifiant des traitements par lots de longue durée après les heures de travail.
author: andreabichsel
manager: AnnBe
ms.date: 06/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: f67b4b4c20345297f186c792fe2766c686e2ddbf
ms.sourcegitcommit: bdfc84aa7f607511981c0b2f20f03fabcb773510
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "3500503"
---
# <a name="optimize-performance-by-scheduling-batch-jobs-after-hours"></a>Optimiser les performances en planifiant des traitements par lots après les heures de travail

## <a name="issue"></a>Sortie

Microsoft Dynamics 365 Human Resources peut rencontrer des problèmes de performances si des traitements par lots de longue durée s'exécutent pendant les heures de bureau normales.

## <a name="resolution"></a>Résolution

Planifiez les traitements par lots suivants pendant les heures creuses. Nous vous recommandons également de revoir la fréquence des traitements par lots qui s'exécutent souvent. Si possible, réduisez la périodicité du traitement par lots. Dans de nombreux cas, la fréquence par défaut est suffisante.

Les traitements par lots suivants doivent s'exécuter la nuit ou après les heures de travail. Assurez-vous de vérifier le fuseau horaire de ces traitements par lots périodiques. Certains traitements par lots peuvent utiliser l'heure standard du Pacifique (PST).

| Traitement par lots | Occurrence par défaut |
| --- | --- |
| Nettoyage de l'historique des traitements par lots | 1 fois par mois |
| Exporter le nettoyage intermédiaire | 1 fois par jour |
| Sync de demande d'intégration manquée Common Data Service | 1 fois par jour |
| Tâche système de compression de la base de données qui doit s'exécuter régulièrement pendant les heures creuses | 1 fois par jour |
| Tâche système de recréation de l'index de la base de données qui doit s'exécuter régulièrement pendant les heures creuses | 1 fois par jour |

1. Dans Human Resources, sélectionnez **Administration du système**.

2. Dans la barre de **Recherche**, recherchez l'un des traitements par lots ci-dessus.

3. Sélectionnez **Exécuter à l'arrière-plan**, puis sélectionnez **Récurrence**.

   ![Définir la récurrence](media/talent-batch-history-cleanup-recurrence.png)

4. Sous **Définir la récurrence**, définissez **Date de début** et **Heure de début** pour qu'elles se produisent pendant les heures creuses ou le week-end. Sélectionnez **Aucune date de fin**. 

   ![Définir la date et heure de début de la récurrence](media/talent-batch-history-cleanup-define-recurrence.png)

5. Cliquez sur **OK**.

6. Si nécessaire, modifiez les autres paramètres sous **Exécuter à l'arrière-plan**, puis cliquez sur **OK**.

## <a name="additional-resources"></a>Ressources supplémentaires

[Optimiser les performances grâce aux tâches automatiques de nettoyage](hr-admin-troubleshooting-batch-history.md)