---
title: Contenu Power BI Gestionnaire de rémunération et avantages
description: Cet article décrit le contenu Power BI Rémunération et Avantages.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 263914
ms.assetid: 18634bb5-3341-42f2-9cc9-7b04708b506b
ms.openlocfilehash: 978aa4897c58518c430decd8570fa30c851349aa
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291856"
---
# <a name="compensation-and-benefits-power-bi-content"></a>Contenu Power BI Gestionnaire de rémunération et avantages

[!include [banner](../includes/banner.md)]

Cet article décrit le contenu Power BI Rémunération et Avantages. 

## <a name="reports-that-are-included-in-the-content-pack"></a>États inclus dans le pack de contenu
Après avoir connecté le pack de contenu à vos données, les données de votre organisation s’affichent dans les états. Si vous n’avez jamais utilisé Microsoft Power BI auparavant, consultez la [Page d’apprentissage guidé pour Power BI](https://powerbi.microsoft.com/guided-learning/?WT.mc_id=PBIService_GetData) pour en savoir plus. Les états inclus dans le pack de contenu contiennent des graphiques et des tables qui fournissent des informations supplémentaires. Le tableau suivant décrit ces états.

| Etat                     | Sommaire                                                                                                                              |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| Analyse de la rémunération et des avantages | Les employés à tarif horaire et salariés par société, le salaire horaire moyen, le salaire moyen, les employés par type d’emploi et l’inscription au régime |
| Avantages de l’employé          | Inscription de l’employé par avantage sélectionné                                                                                               |

Vous pouvez filtrer les graphiques et les vignettes affichés sur ces états et les épingler au tableau de bord. Pour savoir comment filtrer et épingler dans Power BI, voir [Créer et configurer un tableau de bord](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités
Les données de l’application sont utilisées pour remplir les états du pack de contenu Rémunération et avantages. Le tableau suivant indique les entités sur lesquelles le pack de contenu est basé.

| Entité                            | Sommaire                                                                                                   | Relations avec d’autres entités |
|-----------------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Workforce\_CalendarOffset         | Décalages de calendrier pour diviser les états                                                                          | Workforce\_PastPositionAssignment, Workforce\_PositionTrend, Workorce\_WorkerTrend, Workforce\_TerminatedWorker |
| Workforce\_Company                | Sociétés selon lesquelles filtrer les états                                                                             | Workforce\_CurrentCompensation, Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_Compensation           | Taux de salaire et fréquence dans le temps                                                                           | Workforce\_CurrentCompensation, Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_CurrentCompensation    | Taux de salaire et fréquence à compter de la date actuelle                                                              | Workforce\_Company, Workforce\_Compensation, Workforce\_Demographics, Workforce\_Job, Workforce\_Position |
| Workforce\_CurrentPosition        | Postes à compter de la date actuelle, postes équivalents à temps plein, postes vacants et postes vacants à pourvoir | Workforce\_Job, Workforce\_Position |
| Workforce\_CurrentWorker          | Collaborateurs à compter de la date actuelle, âge et effectif                                                         | Workforce\_Company, Workforce\_Compensation, Workforce\_GeographicLocation, Workforce\_Performance, Workforce\_WorkerName, Workforce\_ReportsToWorkerName, Workforce\_WorkerTitle, Workforce\_Demographics, Workforce\_Job, Workforce\_Employment, Workforce\_Position, Workforce\_WorkerBenefit |
| Workforce\_Date                   | Jours, semaines, mois et années                                                                             | Workforce\_PastPositionAssignment, Workforce\_PositionTrend, Workorce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_Demographics           | Date de naissance, sexe, origine ethnique et état civil                                                   | Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_Employment             | Date de début, date de fin et date de transition                                                                  | Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_GeographicLocation     | Ville, département, code postal et région ou province                                                           | Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_Job                    | Fonction, type et titre                                                                                  | Workforce\_CurrentPosition, Workforce\_CurrentWorker |
| Workforce\_PastPositionAssignment | Motif d’affectation, date de début, date de fin et tâche                                                           | Workforce\_CalendarOffset, Workforce\_Date, Workforce\_Job, Workforce\_Position |
| Workforce\_Performance            | Classement, description et modèle de classement                                                                      | Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_Position               | Département, ETP, poste, type de poste et titre                                                        | Workforce\_CurrentPosition, Workforce\_CurrentWorker |
| Workforce\_PositionTrend          | Postes dans le temps, ETP et tâche                                                                          | Workforce\_CalendarOffset, Workforce\_Date, Workforce\_Job, Workforce\_Position |
| Workforce\_ReportsToWorkerName    | Prénom, nom et nom complet                                                                       | Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_Skill                  | Qualification, type de qualification et évaluation                                                                              | |
| Workforce\_TerminatedWorker       | Collaborateurs dont le contrat est terminé, date de fin du contrat, titre, poste et tâche                                             | Workforce\_Company, Workforce\_Compensation, Workforce\_GeographicLocation, Workforce\_Performance, Workforce\_WorkerName, Workforce\_ReportsToWorkerName, Workforce\_CalendarOffset, Workforces\_Date, Workforce\_WorkerTitle, Workforce\_Demographics, Workforce\_Employment, Workforce\_Job, Workforce\_Position, Workforce\_WorkerBenefit |
| Workforce\_WorkerBenefit          | Date d’effet, option d’avantage, régime d’avantages et type d’avantage                                             | Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_WorkerName             | Prénom, nom et nom complet                                                                       | Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_WorkerTitle            | Titre et date d’ancienneté                                                                                   | Workforce\_CurrentWorker, Workforce\_TerminatedWorker, Workforce\_WorkerTrend |
| Workforce\_WorkerTrend            | Collaborateurs dans le temps, effectif, société et poste                                                        | Workforce\_Company, Workforce\_Compensation, Workforce\_GeographicLocation, Workforce\_Performance, Workforce\_WorkerName, Workforce\_ReportsToWorkerName, Workforce\_CalendarOffset, Workforces\_Date, Workforce\_WorkerTitle, Workforce\_Demographics, Workforce\_Employment, Workforce\_Job, Workforce\_WorkerBenefit |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
