---
title: "Les compétences et le développement d&quot;employé actionnent le contenu BI"
description: "Cette rubrique décrit Dynamics 365 pour les opérations - Les compétences des employés et le contenu BI de courant de développement. Elle explique comment accéder aux états inclus dans le pack de contenu, et fournit des informations sur le modèle de données et des entités utilisés pour établir Feature Pack de contenu."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 263894
ms.assetid: 7d375d8a-b2de-4bec-b575-93d1d4521b79
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 1fd6f978b6a871f9f7d3d5e91ab3e0aac789ae88
ms.lasthandoff: 03/31/2017


---

# <a name="employee-competencies-and-development-power-bi-content"></a>Les compétences et le développement d'employé actionnent le contenu BI

Cette rubrique décrit Dynamics 365 pour les opérations - Les compétences des employés et le contenu BI de courant de développement. Elle explique comment accéder aux états inclus dans le pack de contenu, et fournit des informations sur le modèle de données et des entités utilisés pour établir Feature Pack de contenu.

<a name="accessing-the-content-pack"></a>Accéder Feature Pack de contenu
--------------------------

Vous pouvez pack trouver d'employé de compétences et de développement contenu de la bibliothèque partagé d'immobilisations dans Microsoft Dynamics Lifecycle Services (LCS). Pour plus d'informations sur le chargement le contenu comprimez- et connectez- le à votre Microsoft Dynamics 365 pour les données d'opérations, voir [contenu BI expérimentés dans des lettres de crédit Microsoft et de vos partenaires] (power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>Les rapports inclus dans le pack de contenu
Après avoir connecté Feature Pack de contenu à votre Dynamics 365 pour les données d'opérations, des données organisation d'états l'affichage de votre. Si ce n'est jamais utilisé le projet BI de courant de Microsoft péremption, vous souhaitez plus {{à:about}} {{son:about}} sujet sous l'onglet [page guidée d'enseignement pour BI de courant] (https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Les états inclus dans le pack de contenu ont des graphiques et des tables contenant les informations supplémentaires. Le tableau suivant décrit ces états.

| Etat                            | Sommaire                                               |
|-----------------------------------|--------------------------------------------------------|
| Analyse de compétence et de développement | Types de qualification membres de l'équipe et qualifications membres de l'équipe par type |
| Profil de qualification                     | Profil de qualification pour l'employé sélectionné                |
| Analyse des compétences                    | Qualifications par le type et le classement                              |

Vous pouvez filtrer les graphiques et les vignettes dans ces états, et épinglez les graphiques et les vignettes du tableau de bord. Pour plus d'informations sur le filtrage et épingler en BI de courant, voir [créez et configurez un tableau de bord] (https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités
Dynamics 365 pour les données d'opérations est utilisé pour remplir états pack dans des employés de compétences et de développement contenu. Le tableau suivant indique les entités qui Feature Pack de contenu est basée.

| Entité                            | Sommaire                                                                                                   | Relations avec d'autres entités                                                                                                                                                                                                                                                                       |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Personnel\_CalendarOffset         | Compense de calendrier aux états des parts                                                                          |                                                                                                                                                                                                                                                                                                         |
| Société d'\_de personnel                | Sociétés pour filtrer les états par                                                                             |                                                                                                                                                                                                                                                                                                         |
| Rémunération d'\_de personnel           | Taux de salaire et fréquence au fil du temps                                                                           |                                                                                                                                                                                                                                                                                                         |
| Personnel\_CurrentCompensation    | Taux de salaire et fréquence à la date actuelle                                                              | Poste\_de personnel de tâche\_de personnel de démographie\_de personnel\_CurrentCompensation de personnel de société\_de personnel                                                                                                                                                                                            |
| Personnel\_CurrentPosition        | Postes par rapport à la date actuelle, à temps plein (FTE) équivalent, permet d'ouverture, postes et en cours-à- remplis | Poste d'\_de personnel de tâche d'\_de personnel                                                                                                                                                                                                                                                                      |
| Personnel\_CurrentWorker          | Travailleurs à la date actuelle, de l'âge, et du effectifs                                                         | Poste\_de personnel\_emploi\_de personnel de tâche\_de personnel de démographie\_de personnel\_WorkerTitle de personnel\_ReportsToWorkerName de personnel\_WorkerName de personnel\_PersonSkill de personnel de résultats à\_de personnel\_GeographicLocation de personnel de rémunération\_de personnel de société\_de personnel                     |
| Date d'\_de personnel                   | Jours, semaines, mois, années et                                                                             |                                                                                                                                                                                                                                                                                                         |
| Démographie d'\_de personnel           | Date de naissance, le sexe, l'origine ethnique, et l'état civil                                                   |                                                                                                                                                                                                                                                                                                         |
| Emploi d'\_de personnel             | Date de début, Date de fin, et date de transition                                                                  |                                                                                                                                                                                                                                                                                                         |
| Personnel\_GeographicLocation     | Ville, département, le code postal, puis état ou cette province                                                           |                                                                                                                                                                                                                                                                                                         |
| Tâche d'\_de personnel                    | Fonction, type, et titre                                                                                  |                                                                                                                                                                                                                                                                                                         |
| Personnel\_JobPreferredSkill      | Importance, classement, qualification, puis niveau de qualification                                                                 | Tâche\_de personnel de compétence\_de personnel                                                                                                                                                                                                                                                                         |
| Personnel\_PastPositionAssignment | Motif, date de début, Date de fin, et tâches d'affectation                                                           | Poste\_de personnel de tâche\_du personnel par date\_de personnel\_ClaendarOffset de personnel                                                                                                                                                                                                                            |
| Performances\_de personnel            | Classement, description, et modèle de classement                                                                      |                                                                                                                                                                                                                                                                                                         |
| Personnel\_PersonSkill            | Niveau, date du niveau, et qualification                                                                               | Qualification d'\_de personnel                                                                                                                                                                                                                                                                                        |
| Personnel\_PersonSkillAnalysis    | Date certifiée, de niveau, de niveau, et qualification                                                                    | Qualification d'\_de personnel d'\_WorkerName de personnel                                                                                                                                                                                                                                                                  |
| Poste d'\_de personnel               | Département, celui, poste, type de poste, et titre                                                        |                                                                                                                                                                                                                                                                                                         |
| Personnel\_PositionTrend          | Postes sur du temps, de celui, et de tâche                                                                          | Poste\_de personnel de tâche\_du personnel par date\_de personnel\_CalendarOffset de personnel                                                                                                                                                                                                                            |
| Personnel\_ReportsToWorkerName    | Prénom, nom de famille, et nom complet                                                                       |                                                                                                                                                                                                                                                                                                         |
| Qualification d'\_de personnel                  | Qualification, type de qualification, et classement                                                                              |                                                                                                                                                                                                                                                                                                         |
| Personnel\_TerminatedWorker       | Travailleurs, date de fin du contrat, titre, poste, et tâche terminés                                             | Poste\_de personnel de tâche\_de personnel\_emploi\_de personnel de démographie\_de personnel\_WorkerTitle de personnel de date\_personnels\_CalendarOffset de personnel\_ReportsToWorkerName de personnel\_WorkerName de personnel de résultats à\_de personnel\_GeographicLocation de personnel de rémunération\_de personnel de société\_de personnel |
| Personnel\_WorkerName             | Prénom, nom de famille, et nom complet                                                                       |                                                                                                                                                                                                                                                                                                         |
| Personnel\_WorkerTitle            | Date de titre et d'ancienneté                                                                                   |                                                                                                                                                                                                                                                                                                         |
| Workorce\_WorkerTrend             | Travailleurs sur du temps, des effectifs, d'entreprise, et de poste                                                        | Tâche\_de personnel\_emploi\_de personnel de démographie\_de personnel\_WorkerTitle de personnel de date\_personnels\_CalendarOffset de personnel\_ReportsToWorkerName de personnel\_WorkerName de personnel de résultats à\_de personnel\_GeographicLocation de personnel de rémunération\_de personnel de société\_de personnel                     |

Ces entités a été utilisée pour créer des mesures calculées dans le modèle de données. Ces mesures calculées sont ensuite utilisées pour calculer les indicateurs de performance clé (KPIs) et les états utilisés dans l'établissement du pack de contenu. Si vous souhaitez inclure les calculs supplémentaires dans vos rapports et tableau de bord, vous pouvez télécharger et modifier le fichier de CompetenciesandDevelopment.pbix du crédit. Ce fichier est le modèle de données par défaut utilisé pour créer le pack de contenu. Après avoir apporté des modifications, vous pouvez créer un pack et un tableau de bord organisation de contenu contenant des informations que vous avez ajoutée.

## <a name="additional-resources"></a>Ressources supplémentaires
Voici quelques liens utiles liés aux entités et à la création du contenu Power BI :

-   [Entités de données](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Création de packs de contenu d'organisation](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modélisation de données à l'aide de Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Ajout de vignettes Power BI aux espaces de travail](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)



