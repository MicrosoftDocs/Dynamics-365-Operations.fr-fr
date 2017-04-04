---
title: "Espace de travail de clôture de période comptable"
description: "Cet article fournit une vue d&quot;ensemble de l&quot;espace de travail de clôture de période comptable et la configuration associée."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerPeriodCloseProjectWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13791
ms.assetid: 6ee51758-639b-448e-9cb2-56cf1d804273
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 114dee90b0fe525f0b3efabbf651d2804a22dd7d
ms.openlocfilehash: ba0d709d123f56edb2a5287376c06c1f41181b1c
ms.lasthandoff: 03/31/2017


---

# <a name="financial-period-close-workspace"></a>Espace de travail de clôture de période comptable

Cet article fournit une vue d'ensemble de l'espace de travail de clôture de période comptable et la configuration associée.

Espace de travail de clôture de période comptable

** Clôture financière de période ** l'espace de travail vous permet de suivre vos processus financiers de clôture dans les sociétés, les zones, et les personnes. Selon votre vue ** clôture financière de période ** de l'espace de travail, vous verrez de toutes les tâches et statuts en un programme de clôture, ou uniquement les tâches qui vous sont affectées. 

Vous devez d'abord sélectionner un programme de clôture en haut de l'espace de travail. Toutes les données affichées sous l'espace de travail sont ensuite filtrées par le programme sélectionné de clôture.

### <a name="summary-tiles"></a>Vignettes récapitulatives

Les vignettes **récapitulatives** donnent une vue d'ensemble du processus et les indicateurs permettent de s'assurer que le processus de clôture se déroule comme prévu. Vous pouvez afficher les tâches qui sont des tâches en retard et restantes de aujourd'hui, les tâches qui sont aujourd'hui dû mais qui sont bloqué en raison de les dépendances, et de toutes les tâches restantes pour le processus. Ces informations sont destinées à toutes les sociétés qui sont incluses dans le programme sélectionné de clôture.

### <a name="tasks-and-status-section"></a>Section Tâches et statuts

Dans ** des tâches et statut ** la section, le statut du plan général de clôture sont répartis de différentes manières : statut par la société, statut par zone, et statut par la personne responsable. Vous pouvez afficher le statut de toutes les tâches dans le programme de clôture, juste tâches qui sont aujourd'hui dû, ou tâches en retard en modifiant le filtre en haut de la liste de carte. Vous pouvez également sélectionner le filtre de la société pour afficher le statut d'une société spécifique. Chaque onglet de statut donne une répartition par pourcentage terminé et le nombre de tâches qui restent. Cliquez sur la carte ou ** afficher des détails ** l'action de filtrer la liste détaillée des tâches par carte sélectionnée. 

Le dernier onglet est de la liste détaillée des tâches. Affiche de cette liste de la liste complète des tâches et peuvent être filtrées afin qu'il indique que les tâches qui vous intéresse. Vous pouvez filtrer la liste des tâches de plusieurs façons. Par exemple, vous pouvez filtrer par date d'échéance de tâche, la société associée, et la zone associée. Vous pouvez également sélectionner pour afficher ou masquer des tâches terminées dans la tâche répertoriez. 

Deux indicateurs sont utilisés pour les tâches :

-   Une point d'exclamation l'icône indique que la tâche est en retard. Pour les tâches en retard, la date d'échéance est également mise en surbrillance en rouge.
-   Une icône du verrou indique que la tâche dépend d'autres tâches qui ne sont pas terminées. Une tâche qui est bloquée par les dépendances ne peut pas être marquée comme terminée. Vous pouvez définir des dépendances pour une tâche à l'aide ** dépendance réglée ** de l'action.

Nom de la tâche est un lien hypertexte à Microsoft Dynamics 365 de la page d'opérations ou tout autre page Web où l'utilisateur doit passer effectuent le travail. Vous pouvez définir cet lien hypertexte à l'aide ** lien de tâche ** du champ lorsque vous modifiez ou créez une tâche. 

Vous pouvez associer des fichiers, les notes, des images, et les URL à une tâche à l'aide ** des pièces jointes ** de l'action. Par exemple, vous pouvez indiquer les numéros de journaux utilisés dans le cadre d'une tâche, d'ajouter des commentaires sur une tâche spécifique, ou d'associer un fichier d'état imprimé pour une tâche. Une icône apparaît dans ** pièce jointe ** la colonne pour la tâche si une pièce jointe est définie. 

** Tâche complète ** l'option doit être sélectionnée manuellement une fois la tâche. Lorsqu'une tâche est marquée comme terminée, ** date de fin ** le champ est automatiquement mis à jour à la date actuelle et l'heure. Les indicateurs de dépendance sont également mis à jour comme requis.

## <a name="all-financial-period-close-tasks-list-page"></a>Page de liste Toutes les tâches de clôture de période comptable
Vous pouvez afficher tous les cours et tâches précédentes de clôture de période ** toutes les tâches financières de clôture de période ** de la page de liste. Cette page de liste est optimale pour l'analyse historique de votre processus de clôture, car elle contient des informations sur la date d'échéance prévue, la date de fin réelle, et la personne qui a effectué la tâche. Vous pouvez facilement exporter des informations sur cette page de liste vers Microsoft Excel pour déclarer et à des fins.

## <a name="financial-period-close-configuration-page"></a>Page Configuration de clôture de période comptable
Avant de pouvoir utiliser ** clôture financière de période ** l'espace de travail, vous devez configurer un processus dans Microsoft Dynamics 365 pour les opérations à l'aide ** configuration financière de clôture de période ** de la page. (Cliquez sur ** comptabilité ** &gt; ** clôture de période ** &gt; ** configuration financière de clôture de période **.)

### <a name="resources"></a>Ressources

Sous ** des ressources ** l'onglet, vous définissez les personnes impliquées dans les processus de clôture. Chaque employé qui sera responsable d'une tâche de clôture doit d'abord être affecté ici. Vous devez également spécifier la vue de l'employé de l'espace de travail. Les options suivantes sont disponibles :

-   **Uniquement les tâches attribuées** : l'utilisateur verra uniquement les tâches qui lui sont affectées.
-   **Toutes les tâches et tous les statuts** : l'utilisateur verra toutes les tâches de clôture et le statut du processus global.

Les utilisateurs disposant des autorisations permettant d'afficher uniquement les tâches qui leur sont attribuées ne pourront pas ajouter de tâches à la liste des tâches, modifier des tâches ou supprimer des tâches de la liste des tâches.

### <a name="task-areas"></a>Zones des tâches

Les zones de tâches permettent de regrouper les tâches de clôture en zones logiques de propriété au sein de votre organisation. Par exemple, la Comptabilité fournisseur, la Comptabilité client ou la Comptabilité peuvent être utilisées comme des zones de tâches.

### <a name="calendars"></a>Calendriers

Permet de créer et de modifier les calendriers financiers de clôture à l'aide de l'onglet de calendriers.  Champ dans lequel vous définirez les jours ouvrables pour clôturer les processus, et sera utilisé pour planifier des tâches de clôture.  Créez un calendrier, puis indiquez les jours ouvrables à utiliser pour la planification des tâches.  Il est recommandé de créer un calendrier de la longue période de temps, comme une année ou les années multiples, car elle peut être modifiée après avoir créé.  Après avoir créé le calendrier, cliquez sur le bouton de modifier pour mettre le calendrier à jour pour des jours spécifiques, tels que les congés.  Les tâches de clôture seront planifiées les jours où la valeur de contrôle est définie à ouvrir.  Si la clôture des tâches ne doit pas être programme un jour spécifique, ce jour doit avoir la valeur de contrôle définie sur Clôturé.

### <a name="templates"></a>Modèles

Vous utilisez un modèle financier de clôture pour définir toutes les tâches qui font partie d'un processus de clôture. Une tâche de clôture est un effort récurrent de travail affecté à une personne pour effectuer dans le cadre de chaque processus de clôture. Dans le modèle, une date d'échéance associée doit être définie pour chaque tâche de clôture. La date d'échéance associée est le nombre de jours avant ou après la date de fin définie de date à laquelle la tâche est due chaque période. Un temps dû est également affecté à chaque tâche. Heure dû est défini à l'aide de le contexte de votre fuseau horaire et convertir au fuseau horaire pour chaque utilisateur. 

Vous pouvez affecter une tâche dans le modèle à une ou plusieurs sociétés laquelle cette tâche s'applique. Si une autre personne est affectée à terminer l'effort de travail dans chaque société, vous pouvez la utile de créer plusieurs tâches pour le même effort de travail. Créez une tâche pour chaque société. 

** Lien de tâche ** l'option de menu est associée à l'effort de travail de tâche et peut être utilisée pour accéder directement à la page associée du lien de tâche de l'espace de travail. Par exemple, une tâche de clôture d'exécuter le processus de réévaluation de la devise pour Achats peut être liée à l'associé ** réévaluation des comptes en devises ** page dans Microsoft Dynamics 365 pour les opérations. Vous pouvez également lier à une URL externe. 

> [! Signe] si vous souhaitez lier un rapport spécifique de Management Reporter à une tâche financière de clôture de période, vous pouvez utiliser l'URL d'état. Pour accéder à l'URL de rapports, ouvrez le rapport dans le Concepteur de rapports, puis sur ** fichier ** &gt; ** l'état de vue ** pour l'ouvrir dans un navigateur Web. Vous pouvez ensuite copier l'URL dans la barre d'adresse du navigateur et la coller dans le champ **Lien des tâches** **URL**. 

Vous pouvez définir les dépendances des tâches dans le modèle. Si une tâche a été paramétrée de varient d'un ou plusieurs tâches, cette tâche ne peut pas être marquée comme terminée jusqu'à ce que toutes les dépendances ont été effectuées. 

Vous pouvez créer des modèles financiers multiples de clôture. Vous pouvez ensuite utiliser les différents modèles pour suivre les processus de clôture pour différents types de périodes, tels que la fin du mois ou la fin de l'année, ou pour suivre les sociétés qui utilisent différents processus de clôture. Une fois un modèle créé, vous pouvez les copier dans un nouveau modèle et apportez les modifications nécessaires. Vous pouvez affecter un seul modèle à chaque programme de clôture.

### <a name="closing-schedules"></a>Clôture des programmes

Vous utilisez un programme de clôture pour affecter un modèle financier de clôture à une période financière spécifique qui doit être clôturée. Les tâches du modèle sont ensuite automatiquement générées pour la période spécifiée, et le nouveau programme de clôture est ajouté à l'espace de travail. Lorsque vous créez un nouveau programme de clôture, ** date de fin de période ** le champ est utilisé pour déterminer les dates d'échéance réelles pour les tâches de clôture, selon la date d'échéance associée qui est affectée dans le modèle financier de clôture. 

Affectez le calendrier approprié pour le programme de clôture, pour indiquer les jours ouvrables à utiliser dans la planification des tâches. Si vous ne définissez pas un calendrier spécifique, dates d'échéance des tâches utiliseront des jours de la semaine. 

Vous devez également définir les sociétés qui sont associées au programme de clôture. Si des tâches de modèle sont affectées à plusieurs sociétés, les tâches distinctes sont créées pour chaque société qui est du programme de clôture et qui seront affectées à la tâche de modèle. 

Une fois le programme de clôture fait, sélectionnez ** clôturé ** l'option pour celle-ci. L'historique de tâche est toujours disponible dans ** toutes les tâches financières de clôture de période ** la page de liste, mais le programme de clôture est supprimé de l'espace de travail. Une fois le programme de clôture ait été marqué comme ** clôturé **, vous ne pourrez pas ajouter des tâches à celui-ci, ne modifiez pas des tâches, ou ne pas supprimer des tâches de celui-ci.


