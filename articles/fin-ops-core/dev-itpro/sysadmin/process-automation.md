---
title: Automatisation des processus
description: Cette rubrique fournit des détails sur la façon dont l’automatisation des processus permet une planification simple des processus qui seront exécutés par le serveur de traitement par lots.
author: RyanCCarlson2
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProcessScheduleSeries
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2020-06-30
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: a8722adfe410f15bc379f9b550f0618c881f067d
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920827"
---
# <a name="process-automation"></a>Automatisation des processus

[!include[banner](../includes/banner.md)]

L’automatisation des processus permet une planification simple des processus qui seront exécutés par le serveur de traitement par lots. La vue calendrier mise à jour du travail planifié permet aux utilisateurs finaux d’afficher le travail planifié et terminé et de prendre des mesures appropriées.

## <a name="administration"></a>Administration

La page d’administration centrale de toutes les automatisations de processus se trouve dans le module Administration système sous le menu **Paramétrage**. Cette page répertoriera tous les processus automatisés (séries) configurés dans le système. Elle vous permettra également d’ajouter de nouvelles automatisations de processus directement à partir de cette page. Une fois une série configurée, vous pouvez gérer chaque série à partir de cette liste. Vous pouvez choisir de modifier toute la série, de la supprimer, d’afficher toutes les occurrences dans une vue liste ou de désactiver la série si vous souhaitez interrompre le travail planifié pendant un certain temps. 

Les processus désactivés dans la gestion des fonctionnalités ne s’afficheront pas lorsque la fonctionnalité est désactivée. De plus, le moteur de planification de l’automatisation des processus ne planifiera aucune occurrence ou processus d’arrière-plan pour une fonction désactivée. La réactivation de la fonction entraînera l’exécution immédiate de toutes les occurrences planifiées ou processus d’arrière-plan du passé. Le moteur de planification de l'automatisation des processus repose sur le traitement par lots du système, **Tâche système d'interrogation de l'automatisation des processus** pour s'exécuter. La tâche ne doit être ni modifiée ni falsifiée à aucun moment. 

## <a name="calendar-view"></a>Vue calendrier

L’un des principaux avantages de l’automatisation des processus est la possibilité d’afficher le travail planifié dans une simple vue de calendrier.  Cette vue vous permet d’afficher le travail pour une semaine à la fois. Cette vue est disponible sur le côté droit de la page **Automatisation des processus**. Elle sera remplie avec le travail planifié pour la série sélectionnée. 

[![Calendrier d’automatisation des processus](./media/CalendarView2.png)](./media/CalendarView2.png)

## <a name="occurrence-changes"></a>Modifications d’occurrence

Chaque occurrence peut être modifiée sans avoir d’incidence sur les autres occurrences définies par la série d’origine. Les occurrences du travail planifié peuvent être modifiées dans la vue calendrier en sélectionnant le bouton **Afficher/Modifier** et en sélectionnant **Occurrence**. Cette page vous permet d’accéder à tous les paramètres affichés initialement dans l’assistant de configuration de série tout en vous offrant la possibilité d’effectuer une modification unique pour l’occurrence sélectionnée. Une occurrence du travail planifié peut également être désactivée en sélectionnant le bouton **Désactiver** dans la vue calendrier.

## <a name="developer-documentation"></a>Documentation du développeur

Le cadre d’automatisation des processus permet aux développeurs d’étendre le cadre d’automatisation des processus. La documentation sur le [Cadre d’automatisation des processus](../process-automation/process-automation-framework.md) fournira des informations sur la façon dont vous pouvez créer des processus personnalisés qui doivent être exécutés par le serveur de traitement par lots planifié avec l’assistant d’automatisation des processus et qui apparaissent automatiquement dans la vue calendrier.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
