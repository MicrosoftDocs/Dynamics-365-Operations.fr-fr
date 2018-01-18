---
title: "Contenu Power BI des compétences et du développement des employés"
description: "Cette rubrique décrit le contenu Power BI Compétences et développement des employés dans Finance and Operations."
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 263894
ms.assetid: 7d375d8a-b2de-4bec-b575-93d1d4521b79
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: cb43245afe578341251b140383a3b03ba2abd962
ms.openlocfilehash: 99fa6e396989e6e204d84cc776f627c7c4baf1d1
ms.contentlocale: fr-fr
ms.lasthandoff: 12/19/2017

---

# <a name="employee-competencies-and-development-power-bi-content"></a>Contenu Power BI des compétences et du développement des employés

[!include[banner](../includes/banner.md)]


Cette rubrique décrit le contenu Power BI Compétences et développement des employés dans Finance and Operations. 

## <a name="reports-that-are-included-in-the-content-pack"></a>États inclus dans le pack de contenu
Après avoir connecté le pack de contenu à vos données Finance and Operations, les données de votre organisation s'affichent dans les états. Si vous n'avez jamais utilisé Microsoft Power BI auparavant, consultez la [Page d'apprentissage guidé pour Power BI](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData) pour en savoir plus. Les états inclus dans le pack de contenu contiennent des graphiques et des tables qui fournissent des informations supplémentaires. Le tableau suivant décrit ces états.

| Etat                            | Sommaire                                               |
|-----------------------------------|--------------------------------------------------------|
| Analyse des compétences et du développement | Types de qualification des membres de l'équipe et qualifications des membres de l'équipe par type |
| Profil de qualification                     | Profil de qualification pour l'employé sélectionné                |
| Analyse des qualifications                    | Qualification par type et classement                              |

Vous pouvez filtrer les graphiques et les vignettes affichés sur ces états et les épingler au tableau de bord. Pour savoir comment filtrer et épingler dans Power BI, voir [Créer et configurer un tableau de bord](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités
Les données Finance and Operations sont utilisées pour remplir les états du pack de contenu Compétences et développement des employés. Le tableau suivant indique les entités sur lesquelles le pack de contenu est basé.

| Entité                            | Sommaire                                                                                                   | Relations avec d'autres entités                                                                                                                                                                                                                                                                       |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Workforce\_CalendarOffset         | Décalages de calendrier pour diviser les états                                                                          |                                                                                                                                                                                                                                                                                                         |
| Workforce\_Company                | Sociétés selon lesquelles filtrer les états                                                                             |                                                                                                                                                                                                                                                                                                         |
| Workforce\_Compensation           | Taux de salaire et fréquence dans le temps                                                                           |                                                                                                                                                                                                                                                                                                         |
| Workforce\_CurrentCompensation    | Taux de salaire et fréquence à compter de la date actuelle                                                              | Workforce\_Company Workforce\_CurrentCompensation\_Demographics Workforce\_Job Workforce\_Position                                                                                                                                                                                            |
| Workforce\_CurrentPosition        | Postes à compter de la date actuelle, postes équivalents à temps plein, postes vacants et postes vacants à pourvoir | Workforce\_Job Workforce\_Position                                                                                                                                                                                                                                                                      |
| Workforce\_CurrentWorker          | Collaborateurs à compter de la date actuelle, âge et effectif                                                         | Workforce\_Company Workforce\_Compensation Workforce\_GeographicLocation Workforce\_Performance Workforce\_PersonSkill Workforce\_WorkerName Workforce\_ReportsToWorkerName Workforce\_WorkerTitle Workforce\_Demographics Workforce\_Job Workforce\_Employment Workforce\_Position                     |
| Workforce\_Date                   | Jours, semaines, mois et années                                                                             |                                                                                                                                                                                                                                                                                                         |
| Workforce\_Demographics           | Date de naissance, sexe, origine ethnique et état civil                                                   |                                                                                                                                                                                                                                                                                                         |
| Workforce\_Employment             | Date de début, date de fin et date de transition                                                                  |                                                                                                                                                                                                                                                                                                         |
| Workforce\_GeographicLocation     | Ville, département, code postal et région ou province                                                           |                                                                                                                                                                                                                                                                                                         |
| Workforce\_Job                    | Fonction, type et titre                                                                                  |                                                                                                                                                                                                                                                                                                         |
| Workforce\_JobPreferredSkill      | Importance, classement, qualification et niveau de qualification                                                                 | Workforce\_Skill Workforce\_Job                                                                                                                                                                                                                                                                         |
| Workforce\_PastPositionAssignment | Motif d'affectation, date de début, date de fin et tâche                                                           | Workforce\_ClaendarOffset Workforce\_Date Workforce\_Job Workforce\_Position                                                                                                                                                                                                                            |
| Workforce\_Performance            | Classement, description et modèle de classement                                                                      |                                                                                                                                                                                                                                                                                                         |
| Workforce\_PersonSkill            | Niveau, date du niveau et qualification                                                                               | Workforce\_Skill                                                                                                                                                                                                                                                                                        |
| Workforce\_PersonSkillAnalysis    | Certifié, niveau, date du niveau et qualification                                                                    | Workforce\_WorkerName Workforce\_Skill                                                                                                                                                                                                                                                                  |
| Workforce\_Position               | Département, ETP, poste, type de poste et titre                                                        |                                                                                                                                                                                                                                                                                                         |
| Workforce\_PositionTrend          | Postes dans le temps, ETP et tâche                                                                          | Workforce\_CalendarOffset Workforce\_Date Workforce\_Job Workforce\_Position                                                                                                                                                                                                                            |
| Workforce\_ReportsToWorkerName    | Prénom, nom et nom complet                                                                       |                                                                                                                                                                                                                                                                                                         |
| Workforce\_Skill                  | Qualification, type de qualification et évaluation                                                                              |                                                                                                                                                                                                                                                                                                         |
| Workforce\_TerminatedWorker       | Collaborateurs dont le contrat est terminé, date de fin du contrat, titre, poste et tâche                                             | Workforce\_Company Workforce\_Compensation Workforce\_GeographicLocation Workforce\_Performance Workforce\_WorkerName Workforce\_ReportsToWorkerName Workforce\_CalendarOffset Workforces\_Date Workforce\_WorkerTitle Workforce\_Demographics Workforce\_Employment Workforce\_Job Workforce\_Position |
| Workforce\_WorkerName             | Prénom, nom et nom complet                                                                       |                                                                                                                                                                                                                                                                                                         |
| Workforce\_WorkerTitle            | Titre et date d'ancienneté                                                                                   |                                                                                                                                                                                                                                                                                                         |
| Workorce\_WorkerTrend             | Collaborateurs dans le temps, effectif, société et poste                                                        | Workforce\_Company Workforce\_Compensation Workforce\_GeographicLocation Workforce\_Performance Workforce\_WorkerName Workforce\_ReportsToWorkerName Workforce\_CalendarOffset Workforces\_Date Workforce\_WorkerTitle Workforce\_Demographics Workforce\_Employment Workforce\_Job                     |






