---
title: Programmer un ordre de fabrication
description: Cette procédure indique comment planifier un ordre de fabrication.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdSchedule, ProdRouteJob, WrkCtrCapResSum, ProdRouteJobSched, ProductionOrderScheduleDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 43d183764def1b1bea7bbe140c25e0eec0b692b1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580574"
---
# <a name="schedule-a-production-order"></a>Programmer un ordre de fabrication

[!include [banner](../../includes/banner.md)]

Cette procédure indique comment planifier un ordre de fabrication. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Il s’agit de la troisième des sept procédures expliquant le cycle de vie de l’ordre de fabrication.


## <a name="schedule-a-production-order"></a>Programmer un ordre de fabrication
1. Accédez à Contrôle de la production > Ordres de fabrication > Tous les ordres de fabrication.
    * Sélectionnez un ordre de fabrication ayant le statut Estimé.  
2. Dans le volet Actions, cliquez sur Planification.
3. Cliquez sur Planifier les tâches.
    * Les paramètres de planification sont configurés sur cette page. Vous pouvez configurer les paramètres pour des utilisateurs spécifiques ou pour tous les utilisateurs.  
4. Dans le champ Direction de la planification, sélectionnez « En avant à partir d’aujourd’hui ».
5. Dans le champ Date de planification, entrez une date.
6. Cochez ou décochez la case Capacité finie.
7. Cochez ou décochez la case Matières limitées.
8. Cliquez sur OK.

## <a name="view-the-scheduling-results"></a>Afficher les résultats de la planification
1. Cliquez sur Ordre de fabrication dans le volet Actions.
2. Cliquez sur Toutes les tâches.
    * Cette page affiche les tâches planifiées que vous venez de générer.  
3. Développez ou réduisez la section Planification.
    * Dans l’organisateur Planification, vous pouvez afficher la date et l’heure planifiées.  
4. Cliquez sur Recherches.
5. Cliquez sur Charge de la capacité.
    * La page Charge de la capacité affiche la capacité réservée via la planification des tâches, le nombre total d’heures qui sont actuellement réservées pour la ressource, et le nombre d’heures encore disponibles pour la planification des tâches de la ressource.  
6. Fermez la page.
7. Fermez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]