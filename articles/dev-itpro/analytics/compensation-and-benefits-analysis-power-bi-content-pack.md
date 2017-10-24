---
title: "Contenu Power BI des rémunérations et avantages"
description: "Cette rubrique décrit le contenu Power BI des rémunérations et avantages dans Finance and Operations. Elle explique également comment accéder aux états inclus dans le pack de contenu, et fournit des informations sur le modèle de données et les entités qui permettent de créer le pack de contenu."
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, UnifiedOperations
ms.custom: 263914
ms.assetid: 18634bb5-3341-42f2-9cc9-7b04708b506b
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fbffad24350ae4650cd0d4142799c5e641dcdbe3
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="compensation-and-benefits-power-bi-content"></a>Contenu Power BI des rémunérations et avantages

[!include[banner](../includes/banner.md)]


Cette rubrique décrit le contenu Power BI des rémunérations et avantages dans Finance and Operations. Elle explique également comment accéder aux états inclus dans le pack de contenu, et fournit des informations sur le modèle de données et les entités qui permettent de créer le pack de contenu.

<a name="accessing-the-content-pack"></a>Accès au pack de contenu
--------------------------

Vous trouverez le pack de contenu Rémunération et avantages dans la bibliothèque Actifs partagés de Microsoft Dynamics Lifecycle Services (LCS). Pour savoir comment télécharger le pack de contenu et le connecter à vos données Microsoft Dynamics 365 for Finance and Operations, voir [Contenu Power BI dans LCS de Microsoft et de vos partenaires](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>États inclus dans le pack de contenu
Après avoir connecté le pack de contenu à vos données Finance and Operations, les données de votre organisation s'affichent dans les états. Si vous n'avez jamais utilisé Microsoft Power BI auparavant, consultez la [Page d'apprentissage guidé pour Power BI](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData) pour en savoir plus. Les états inclus dans le pack de contenu contiennent des graphiques et des tables qui fournissent des informations supplémentaires. Le tableau suivant décrit ces états.

| Etat                     | Sommaire                                                                                                                              |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| Analyse de la rémunération et des avantages | Les employés à tarif horaire et salariés par société, le salaire horaire moyen, le salaire moyen, les employés par type d'emploi et l'inscription au régime |
| Avantages de l'employé          | Inscription de l'employé par avantage sélectionné                                                                                               |

Vous pouvez filtrer les graphiques et les vignettes affichés sur ces états et les épingler au tableau de bord. Pour savoir comment filtrer et épingler dans Power BI, voir [Créer et configurer un tableau de bord](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités
Les données Finance and Operations sont utilisées pour remplir les états du pack de contenu Rémunération et avantages. Le tableau suivant indique les entités sur lesquelles le pack de contenu est basé.

| Entité                            | Sommaire                                                                                                   | Relations avec d'autres entités                                                                                                                                                                                                                                                                                                |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Workforce\_CalendarOffset         | Décalages de calendrier pour diviser les états                                                                          | Workforce\_PastPositionAssignment Workforce\_PositionTrend Workorce\_WorkerTrend Workforce\_TerminatedWorker                                                                                                                                                                                                                     |
| Workforce\_Company                | Sociétés selon lesquelles filtrer les états                                                                             | Workforce\_CurrentCompensation Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                        |
| Workforce\_Compensation           | Taux de salaire et fréquence dans le temps                                                                           | Workforce\_CurrentCompensation Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                        |
| Workforce\_CurrentCompensation    | Taux de salaire et fréquence à compter de la date actuelle                                                              | Workforce\_Company Workforce\_Compensation Workforce\_Demographics Workforce\_Job Workforce\_Position                                                                                                                                                                                                                            |
| Workforce\_CurrentPosition        | Postes à compter de la date actuelle, postes équivalents à temps plein, postes vacants et postes vacants à pourvoir | Workforce\_Job Workforce\_Position                                                                                                                                                                                                                                                                                               |
| Workforce\_CurrentWorker          | Collaborateurs à compter de la date actuelle, âge et effectif                                                         | Workforce\_Company Workforce\_Compensation Workforce\_GeographicLocation Workforce\_Performance Workforce\_WorkerName Workforce\_ReportsToWorkerName Workforce\_WorkerTitle Workforce\_Demographics Workforce\_Job Workforce\_Employment Workforce\_Position Workforce\_WorkerBenefit                                            |
| Workforce\_Date                   | Jours, semaines, mois et années                                                                             | Workforce\_PastPositionAssignment Workforce\_PositionTrend Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                     |
| Workforce\_Demographics           | Date de naissance, sexe, origine ethnique et état civil                                                   | Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Workforce\_Employment             | Date de début, date de fin et date de transition                                                                  | Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Workforce\_GeographicLocation     | Ville, département, code postal et région ou province                                                           | Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Workforce\_Job                    | Fonction, type et titre                                                                                  | Workforce\_CurrentPosition Workforce\_CurrentWorker                                                                                                                                                                                                                                                                              |
| Workforce\_PastPositionAssignment | Motif d'affectation, date de début, date de fin et tâche                                                           | Workforce\_CalendarOffset Workforce\_Date Workforce\_Job Workforce\_Position                                                                                                                                                                                                                                                     |
| Workforce\_Performance            | Classement, description et modèle de classement                                                                      | Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Workforce\_Position               | Département, ETP, poste, type de poste et titre                                                        | Workforce\_CurrentPosition Workforce\_CurrentWorker                                                                                                                                                                                                                                                                              |
| Workforce\_PositionTrend          | Postes dans le temps, ETP et tâche                                                                          | Workforce\_CalendarOffset Workforce\_Date Workforce\_Job Workforce\_Position                                                                                                                                                                                                                                                     |
| Workforce\_ReportsToWorkerName    | Prénom, nom et nom complet                                                                       | Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Workforce\_Skill                  | Qualification, type de qualification et évaluation                                                                              |                                                                                                                                                                                                                                                                                                                                  |
| Workforce\_TerminatedWorker       | Collaborateurs dont le contrat est terminé, date de fin du contrat, titre, poste et tâche                                             | Workforce\_Company Workforce\_Compensation Workforce\_GeographicLocation Workforce\_Performance Workforce\_WorkerName Workforce\_ReportsToWorkerName Workforce\_CalendarOffset Workforces\_Date Workforce\_WorkerTitle Workforce\_Demographics Workforce\_Employment Workforce\_Job Workforce\_Position Workforce\_WorkerBenefit |
| Workforce\_WorkerBenefit          | Date d'effet, option d'avantage, régime d'avantages et type d'avantage                                             | Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Workforce\_WorkerName             | Prénom, nom et nom complet                                                                       | Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Workforce\_WorkerTitle            | Titre et date d'ancienneté                                                                                   | Workforce\_CurrentWorker Workforce\_TerminatedWorker Workorce\_WorkerTrend                                                                                                                                                                                                                                                       |
| Workorce\_WorkerTrend             | Collaborateurs dans le temps, effectif, société et poste                                                        | Workforce\_Company Workforce\_Compensation Workforce\_GeographicLocation Workforce\_Performance Workforce\_WorkerName Workforce\_ReportsToWorkerName Workforce\_CalendarOffset Workforces\_Date Workforce\_WorkerTitle Workforce\_Demographics Workforce\_Employment Workforce\_Job Workforce\_WorkerBenefit                     |

Ces entités ont été utilisées pour créer des mesures calculées dans le modèle de données. Ces entités calculées sont ensuite utilisées pour calculer les indicateurs de performance clés (KPI) et les états utilisés dans le pack de contenu. Si vous souhaitez inclure des calculs supplémentaires dans vos rapports et tableaux de bord, vous pouvez télécharger et modifier le fichier CompensationandBenefits.pbix de LCS. Ce fichier est le modèle de données par défaut utilisé pour créer le pack de contenu. Une fois que vous avez apporté vos modifications, vous pouvez créer un pack de contenu et un tableau de bord de l'organisation contenant les informations que vous avez ajoutées.

## <a name="additional-resources"></a>Ressources supplémentaires
Voici quelques liens utiles liés aux entités et à la création du contenu Power BI :

-   [Entités de données](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Création de packs de contenu d'organisation](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modélisation de données à l'aide de Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Ajout de vignettes Power BI aux espaces de travail](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)





