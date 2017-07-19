---
title: "Contenu Power BI des compétences et du développement des employés"
description: "Cette rubrique décrit le contenu Power BI Compétences et développement des employés dans Finance and Operations. Elle explique également comment accéder aux états inclus dans le pack de contenu, et fournit des informations sur le modèle de données et les entités qui permettent de créer le pack de contenu."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, UnifiedOperations
ms.custom: 263894
ms.assetid: 7d375d8a-b2de-4bec-b575-93d1d4521b79
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: f5b3c180f0a9d60fa5d4d8398daf79a14da2d6f4
ms.contentlocale: fr-fr
ms.lasthandoff: 06/13/2017

---

# <a name="employee-competencies-and-development-power-bi-content"></a>Contenu Power BI des compétences et du développement des employés

[!include[banner](../includes/banner.md)]


Cette rubrique décrit le contenu Power BI Compétences et développement des employés dans Finance and Operations. Elle explique également comment accéder aux états inclus dans le pack de contenu, et fournit des informations sur le modèle de données et les entités qui permettent de créer le pack de contenu.

<a name="accessing-the-content-pack"></a>Accès au pack de contenu
--------------------------

Vous trouverez le pack de contenu Compétences et développement des employés dans la bibliothèque Actifs partagés de Microsoft Dynamics Lifecycle Services (LCS). Pour savoir comment télécharger le pack de contenu et le connecter à vos données Microsoft Dynamics 365 for Finance and Operations, voir [Contenu Power BI dans LCS de Microsoft et de vos partenaires](power-bi-content-microsoft-partners.md).

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

Ces entités ont été utilisées pour créer des mesures calculées dans le modèle de données. Ces entités calculées sont ensuite utilisées pour calculer les indicateurs de performance clés (KPI) et les états utilisés dans le pack de contenu. Si vous souhaitez inclure des calculs supplémentaires dans vos états et tableaux de bord, vous pouvez télécharger et modifier le fichier CompetenciesandDevelopment.pbix de LCS. Ce fichier est le modèle de données par défaut utilisé pour créer le pack de contenu. Une fois que vous avez apporté vos modifications, vous pouvez créer un pack de contenu et un tableau de bord de l'organisation contenant les informations que vous avez ajoutées.

## <a name="additional-resources"></a>Ressources supplémentaires
Voici quelques liens utiles liés aux entités et à la création du contenu Power BI :

-   [Entités de données](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Création de packs de contenu d'organisation](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modélisation de données à l'aide de Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Ajout de vignettes Power BI aux espaces de travail](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)





