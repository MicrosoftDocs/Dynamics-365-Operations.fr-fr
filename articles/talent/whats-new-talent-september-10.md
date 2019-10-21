---
title: Nouveautés ou modifications dans Dynamics 365 Talent - Core HR (10 septembre 2018)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 09/12/2018
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
ms.author: dkrame
ms.search.validFrom: 2018-09-06
ms.dyn365.ops.version: Talent September 10, 2018 update
ms.openlocfilehash: 59cb0203422b7d81b5ca0077370fd9cbdb4a7f89
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2019
ms.locfileid: "2010082"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-core-hr-september-10-2018"></a>Nouveautés ou modifications dans Dynamics 365 Talent: Core HR (10 septembre 2018)

[!include [banner](includes/banner.md)]

**Version 8.1.138.0**

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent: Core HR.

## <a name="allow-specific-time-of-day-on-time-off-requests-half-days"></a>Indiquer un moment spécifique de la journée dans les demandes de congés (demi-journées)

Si le plan de congé et d'absence est paramétré pour que les congés soient soumis en jours, vous pouvez maintenant activer une définition d'une demi-journée. Ensuite, lorsque les utilisateurs soumettent des demandes de congés, ils peuvent spécifier s'ils souhaitent prendre la matinée ou l'après-midi.

Par défaut, cette option est désactivée. Pour permettre aux employés de demander une matinée ou une après-midi de congé, vous devez activer cette option dans la zone **Congé et absence** des paramètres des ressources humaines.

Le privilège de sécurité pour cette fonction est Tenir à jour les paramètres de ressources humaines.

## <a name="validation-of-leave-and-absence-entries"></a>Validation des entrées de congé et d'absence

Selon la manière dont les congés sont configurés, les employés qui essaient de soumettre une demande de congés d'une durée plus longue que leur journée de travail reçoivent un message d'avertissement. Autrement dit, un avertissement leur est envoyé s'ils essaient de prendre plus qu'une journée entière à une date donnée.

Cette validaton est toujours activée. Chaque fois que les employés dépassent le seuil de jours défini, ils reçoivent un avertissement dans leur demande de congés.

## <a name="additional-fields-for-conditional-statements-in-workflows"></a>Champs supplémentaires des instructions conditionnelles des workflows

Des champs supplémentaires ont été ajoutés aux instructions conditionnelles et aux espaces réservés pour plusieurs workflows dans Core HR.

Les champs suivants ont été ajoutés aux workflows de rémunération, de résiliation et de transfert :

- EmploymentType
- LegalEntity
- AdjustedWorkerStartDate
- EmployerNoticeAmount
- EmployerUnitOfNotice
- TransitionDate
- WorkerNoticeAmount
- WorkerStartDate
- WorkerUnitOfNotice
- ProbationEndDate
- Poste
- Union
- Département
- PositionType
- CompLocation
- Fonction
- Poste
- JobType
- JobFamily
- JobFunction

Les champs suivants ont été ajoutés au workflow de position :

- Poste
- Union
- Département
- PositionType
- CompLocation
- Fonction
- Poste
- JobType
- JobFamily
- JobFunction

Les champs des instructions conditionnelles et des espaces réservés sont disponibles pour tous les utilisateurs qui disposent d'un accès pour configurer les workflows précédemment mentionnés.

## <a name="navigation-to-attract-from-personnel-management"></a>Accès à Attract à partir du module Gestion du personnel

Dans le module Gestion du personnel, si Attract n'a pas été paramétré, la section **Candidats à l'embauche** redirige les utilisateurs vers la page de mise en route d'Attract au lieu d'afficher le message « Nous n'avons rien trouvé à afficher ici ».

## <a name="other-changes"></a>Autres modifications

Cette version contient plusieurs correctifs de bogue supplémentaires :

- Lorsqu'un fournisseur est embauché, l'onglet **Rémunération** ne doit pas être disponible dans la page de demande/d'action.
- Au cours du processus de résiliation de la demande, vous ne pouvez pas continuer tant que tous les champs obligatoires ne contiennent pas des données.
- Les problèmes d'ordre de tri et d'affichage de la date dans le module Analyse de la gestion du personnel ont été résolus.
