---
title: Nouveautés ou modifications dans Dynamics 365 Talent (31 janvier 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 01/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-01-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 8e8c11e460a4678efea81f8d3d1eec96b673d329
ms.sourcegitcommit: 53174ed4e7cc4e1ba07cdfc39207e7296ef87c1f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/07/2020
ms.locfileid: "4690050"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-31-2019"></a>Nouveautés ou modifications dans Dynamics 365 Talent (31 janvier 2019)

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Talent.

**Version 8.1.2128**

## <a name="core-hr-changes"></a>Modifications apportées à Core HR

### <a name="time-off-taken-on-leave-people-card-doesnt-consider-leave-plan-dates"></a>Les congés pris sur la fiche individuelle des congés ne tient pas compte des dates prévisionnelles de congés.
Pour tous les employés ayant des plans de congés qui ne sont pas exécutés sur une année civile, la fiche **Déduit** affiche maintenant les congés pris au cours de l'année définie dans le plan. Par exemple, si l'année de congés d'une organisation court du 1er juin au 30 mai, et si un employé a pris trois jours de congés en décembre, la fiche **Déduit** affichera le 15 janvier, 3 jours. 

### <a name="accrual-amounts-not-matching-tier-date-basis"></a>Montants réels ne correspondant pas à une base de date
De nouvelles options ont été ajoutées aux congés et absences (paramètres **Ressources humaines**) pour permettre aux clients de déterminer quand les mois de date de service des employés sont effectifs. Pour certaines organisations, la date est la fin du mois, mais pour d'autres, il peut s'agir du début du mois prochain. Par exemple, une organisation peut accorder un congé le 31 décembre, tandis qu'une autre peut en accorder un le 1er janvier. Cette option vous permettra de choisir quand doit survenir l'attribution. 

### <a name="worker-hire-actions-are-stuck-in-workflow-complete-state"></a>Les actions de recrutement d'employés sont répertoriées dans l'état « Workflow terminé ».
Des modifications ont été apportées pour corriger un problème lorsqu'un petit nombre de workflows sont terminés avec un statut « Workflow terminé ». Les nouveaux workflows doivent se déplacer vers un état « Terminé » une fois qu'il est terminé. Tous les workflows ayant le statut Terminé seront transférés vers un statut d'erreur pour permettre la mise à jour ou la suppression, le cas échéant. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]