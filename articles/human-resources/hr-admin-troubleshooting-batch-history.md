---
title: Optimiser les performances grâce aux tâches automatiques de nettoyage
description: Cet article décrit la procédure de résolution des problèmes de performances avec Microsoft Dynamics 365 Human Resources en nettoyant l'historique des traitements par lots.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: a983fde8ba393ab25f2b330014e04a1379f0e4d0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418448"
---
# <a name="optimize-performance-with-auto-cleanup-tasks"></a>Optimiser les performances avec des tâches de nettoyage automatique

**Sortie**

Microsoft Dynamics 365 Human Resources peut faire l'expérience de problèmes de performances si l'historique des traitements par lots se développe de trop.

**Cause**

Les traitements par lots qui fonctionnent souvent peuvent entraîner la croissance insoutenable de l'historique des traitements par lots. Cela peut entraîner des problèmes de performances. 

**Résolution**

Planifiez une tâche automatique pour nettoyer votre historique des traitements par lots. Nous vous recommandons de paramétrer la tâche à exécuter chaque semaine, mais vous devez exécuter le nettoyage plus ou moins souvent, selon votre environnement. La procédure suivante contient nos paramètres recommandés, mais vous pouvez les modifier selon vos besoins.

1. Dans Human Resources, sélectionnez **Administration du système**.

2. Dans la barre **Recherche**, entrez **Nettoyage de l'historique des traitements par lots**.

   ![Rechercher le nettoyage de l'historique des traitements par lots](media/talent-batch-history-cleanup-search-bar.png)

3. Dans **Limite de l'historique (jours)**, saisissez **30**.

   ![Définir la limite de l'historique sur 30](media/talent-batch-history-cleanup-history-limit.png)

4. Sélectionnez **Exécuter en arrière-plan**, puis sélectionnez **Récurrence**.

   ![Définir la récurrence](media/talent-batch-history-cleanup-recurrence.png)

5. Sous **Définir la récurrence**, définissez **Date de début** et **Heure de début** pour qu'elles se produisent pendant les heures creuses ou le week-end, puis sélectionnez **PAS DE DATE DE FIN**. 

   ![Définir la date et heure de début de la récurrence](media/talent-batch-history-cleanup-define-recurrence.png)

6. Sous **PÉRIODICITÉ**, sélectionnez **Jours** et définissez **RÉPÉTER APRÈS L'INTERVALLE SPÉCIFIÉ** sur **7**.

   ![Définir le nettoyage afin qu'il se répète de manière hebdomadaire](media/talent-batch-history-cleanup-recurrence-pattern.png)

7. Cliquez sur **OK**.

8. Modifiez les autres paramètres sous **Exécuter en arrière-plan** au besoin, et sélectionnez **OK**.

