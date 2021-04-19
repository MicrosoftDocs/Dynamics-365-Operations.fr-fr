---
title: Espace de travail de clôture de période comptable
description: Cet article fournit une vue d’ensemble de l’espace de travail de clôture de période comptable et la configuration associée.
author: ShylaThompson
ms.date: 11/29/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerPeriodCloseProjectWorkspace
audience: Application User
ms.reviewer: roschlom
ms.custom: 13791
ms.assetid: 6ee51758-639b-448e-9cb2-56cf1d804273
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 388cf90221f04014ebced7b322fda14558769127
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811335"
---
# <a name="financial-period-close-workspace"></a>Espace de travail de clôture de période comptable

[!include [banner](../includes/banner.md)]

Cet article fournit une vue d’ensemble de l’espace de travail de clôture de période comptable et la configuration associée.

Espace de travail de clôture de période comptable

L’espace de travail **Clôture de période comptable** permet de suivre les processus de clôture de période comptable sur plusieurs sociétés, secteurs et personnes. Selon votre affichage de l’espace de travail **Clôture de période comptable**, vous verrez l’ensemble des tâches et statuts d’un programme de clôture, ou seulement les tâches qui vous sont affectées. 

Vous devez commencer par sélectionner un programme de clôture en haut de l’espace de travail. Toutes les données qui figurent sur l’espace de travail sont ensuite filtrées pour le programme de clôture sélectionné.

### <a name="summary-tiles"></a>Vignettes récapitulatives

Les vignettes **Synthèse** fournissent une vue d’ensemble du processus, et les indicateurs vous aident à maintenir le processus de clôture sur la bonne voie. Vous pouvez voir les tâches en retard, les tâches restantes pour aujourd’hui, les tâches qui sont dues aujourd’hui mais qui sont bloquées en raison des dépendances et toutes les tâches restantes pour le processus. Ces informations sont destinées à toutes les sociétés incluses dans le programme de clôture sélectionné.

### <a name="tasks-and-status-section"></a>Section Tâches et statuts

Dans la section **Tâches et statuts**, le statut du programme de clôture global est décomposé de différentes manières : statut par société, statut par zone et statut par personne responsable. Vous pouvez afficher le statut de toutes les tâches du programme de clôture, seulement les tâches dues aujourd’hui ou les tâches en retard en modifiant le filtre en haut de la liste des cartes. Vous pouvez également sélectionner le filtre de la société pour afficher le statut d’une société spécifique. Chaque onglet de statut donne une répartition en pourcentage terminé et en nombre de tâches restantes. Cliquez sur la carte ou sur l’action **Afficher les détails** pour filtrer la liste des tâches détaillée en fonction de la carte sélectionnée. 

Le dernier onglet concerne la liste des tâches détaillée. Cette liste affiche la liste complète des tâches et peut être filtrée afin d’afficher uniquement les tâches qui vous intéressent. Vous pouvez filtrer la liste des tâches de plusieurs manières. Par exemple, vous pouvez filtrer par date d’échéance de la tâche, société associée et secteur associé. Vous pouvez également choisir d’afficher ou de masquer les tâches terminées dans la liste des tâches. 

Deux indicateurs sont utilisés pour les tâches :

-   Une icône de point d’exclamation indique que la tâche est en retard. Pour les tâches en retard, la date d’échéance est également mise en surbrillance en rouge.
-   Une icône de verrou indique que la tâche dépend d’autres tâches qui ne sont pas terminées. Une tâche qui est bloquée par des dépendances ne peut pas être marquée comme terminée. Vous pouvez définir des dépendances pour une tâche à l’aide de l’action **Définir la dépendance**.

Le nom de la tâche est un lien hypertexte vers la page où l’utilisateur doit aller pour terminer le travail. Vous pouvez définir ce lien hypertexte à l’aide du champ **Lien des tâches** lorsque vous modifiez ou créez une tâche. 

Vous pouvez joindre des fichiers, des notes, des images et des URL à une tâche à l’aide de l’action **Documents joints**. Par exemple, vous pouvez indiquer les numéros de journal utilisés dans le cadre d’une tâche, ajouter des commentaires sur une tâche spécifique ou joindre un fichier d’état qui a été imprimé pour une tâche. Une icône apparaît dans la colonne **Pièce jointe** concernant la tâche si une pièce jointe est présente. 

L’option **Tâche terminée** doit être sélectionnée manuellement une fois la tâche terminée. Lorsqu’une tâche est marquée comme terminée, le champ **Date de fin** est automatiquement mis à jour avec la date et l’heure actuelles. Les indicateurs de dépendance sont également mis à jour en conséquence.

## <a name="all-financial-period-close-tasks-list-page"></a>Page de liste Toutes les tâches de clôture de période comptable
Vous pouvez afficher toutes les tâches de clôture de période comptable précédentes et actuelles dans la page de liste **Toutes les tâches de clôture de période comptable**. Cette page de liste est optimale pour l’analyse historique de votre processus de clôture, car elle inclut des informations sur la date d’échéance planifiée, la date de fin réelle et la personne qui a effectué la tâche. Vous pouvez facilement exporter les informations de cette page de liste vers Microsoft Excel à des fins d’audit et de génération d’états.

## <a name="financial-period-close-configuration-page"></a>Page Configuration de clôture de période comptable
Avant d’utiliser l’espace de travail **Clôture de période comptable**, vous devez configurer le processus à l’aide de la page **Configuration de clôture de période comptable**. (Cliquez sur **Comptabilité** &gt; **Clôturer la période** &gt; **Configuration de clôture de période comptable**).

### <a name="resources"></a>Ressources

Sous l’onglet **Ressources**, définissez les personnes impliquées dans les processus de clôture. Tout employé responsable d’une tâche de clôture doit d’abord être affecté ici. Vous devez également spécifier l’affichage de l’espace de travail de l’employé. Les options suivantes sont disponibles :

-   **Uniquement les tâches attribuées** : l’utilisateur verra uniquement les tâches qui lui sont affectées.
-   **Toutes les tâches et tous les statuts** : l’utilisateur verra toutes les tâches de clôture et le statut du processus global.

Les utilisateurs disposant des autorisations permettant d’afficher uniquement les tâches qui leur sont attribuées ne pourront pas ajouter de tâches à la liste des tâches, modifier des tâches ou supprimer des tâches de la liste des tâches.

### <a name="task-areas"></a>Zones des tâches

Les zones de tâches permettent de regrouper les tâches de clôture en zones logiques de propriété au sein de votre organisation. Par exemple, la Comptabilité fournisseur, la Comptabilité client ou la Comptabilité peuvent être utilisées comme des zones de tâches.

### <a name="calendars"></a>Calendriers

Créez et modifiez les calendriers de clôture financière à l’aide de l’onglet Calendriers. Sous cet onglet, vous définirez les jours de travail pour les processus de clôture et vous les utiliserez pour planifier les tâches de clôture.  Créez un calendrier et indiquez les jours ouvrables à utiliser pour la planification des tâches.  Il est recommandé de créer un calendrier pour une longue période, par exemple une ou plusieurs années, car il peut être modifié après sa création.  Après la création du calendrier, cliquez sur le bouton Modifier pour mettre à jour le calendrier pour des jours spécifiques, tels que les congés.  Les tâches de clôture sont planifiées pour les jours où la valeur de contrôle est définie sur Ouvert.  Si les tâches de clôture ne doivent pas être programmées un jour spécifique, la valeur de contrôle de ce jour doit être définie sur Fermé.

### <a name="templates"></a>Modèles

Vous utilisez un modèle de clôture financière pour définir toutes les tâches qui font partie d’un processus de clôture. Une tâche de clôture est un travail récurrent affecté à une personne afin qu’elle l’effectue dans le cadre de chaque processus de clôture. Dans le modèle, une date d’échéance relative doit être définie pour chaque tâche de clôture. La date d’échéance relative correspond au nombre de jours avant ou après la date de fin de la période définie où la tâche arrive à échéance à chaque période. Une heure d’échéance est également affectée à chaque tâche. L’heure d’échéance est définie en fonction de votre fuseau horaire et est convertie en fonction du fuseau horaire correspondant à chaque utilisateur. 

Vous pouvez affecter une tâche dans le modèle à une ou plusieurs sociétés dans lesquelles cette tâche s’applique. Si une personne différente est affectée à la réalisation de ce travail dans chaque société, il peut être utile de créer plusieurs tâches pour le même travail. Créez une tâche pour chaque société. 

L’option de menu **Lien des tâches** est associée au travail correspondant à la tâche et peut être utilisée pour accéder directement à la page associée à partir du lien de tâche dans l’espace de travail. Par exemple, une tâche de clôture destinée à exécuter le processus de réévaluation de la devise pour la Comptabilité fournisseur peut être liée à la page **Réévaluation des comptes en devises**. Vous pouvez également lier à une URL externe. 

> [!TIP]
> Si vous souhaitez lier un état Management Reporter spécifique à une tâche de clôture de période comptable, vous pouvez utiliser l’URL de l’état. Pour accéder à l’URL de l’état, ouvrez l’état dans le concepteur d’état, puis cliquez sur **Fichier** &gt; **Afficher l’état** pour ouvrir l’état dans un navigateur Web. Vous pouvez ensuite copier l’URL dans la barre d’adresse du navigateur et la coller dans le champ **Lien des tâches** **URL**. 

Vous pouvez définir les dépendances des tâches dans le modèle. Si une tâche a été paramétrée pour dépendre d’une ou de plusieurs tâches, elle ne peut pas être marquée comme terminée jusqu’à ce que toutes les dépendances soient terminées. 

Vous pouvez créer plusieurs modèles de clôture financière. Vous pouvez ensuite utiliser les différents modèles pour suivre les processus de clôture pour différents types de périodes, tels que la fin du mois ou la fin d’exercice, ou pour suivre les sociétés qui utilisent différents processus de clôture. Une fois un modèle créé, vous pouvez le copier vers un nouveau modèle et apporter les modifications requises. Vous pouvez affecter un seul modèle à chaque programme de clôture.

### <a name="closing-schedules"></a>Clôture des programmes

Vous utilisez un programme de clôture pour affecter un modèle de clôture financière à une période financière spécifique qui doit être clôturée. Les tâches du modèle sont ensuite automatiquement générées pour la période spécifiée, et le nouveau programme de clôture est ajouté à l’espace de travail. Lorsque vous créez un nouveau programme de clôture, le champ **Date de fin de la période** est utilisé pour déterminer les dates d’échéance réelles pour les tâches de clôture, en fonction de la date d’échéance relative affectée dans le modèle de clôture financière. 

Affectez le calendrier approprié pour le programme de clôture, pour indiquer les jours ouvrables à utiliser dans la planification des tâches. Si vous ne définissez pas de calendrier spécifique, les dates d’échéance des tâches utiliseront tous les jours de la semaine. 

Vous devez également définir les sociétés qui seront associées au programme de clôture. Si des tâches de modèle sont affectées à plusieurs sociétés, des tâches distinctes seront créées pour chaque société du programme de clôture assignée à la tâche du modèle. 

Une fois qu’un programme de clôture est terminé, sélectionnez l’option **Clôturé** pour ce programme. L’historique des tâches sera toujours disponible dans la page de liste **Toutes les tâches de clôture de période comptable**, mais le programme de clôture sera supprimé de l’espace de travail. Une fois qu’un programme de clôture a été marqué comme **Clôturé**, vous ne pourrez pas lui ajouter de tâches, modifier des tâches ou lui supprimer des tâches.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]