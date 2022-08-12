---
title: Contenu Power BI Formation dans l’organisation
description: Cet article décrit les applications de finances et d’opérations – Contenu Power BI de formation dans l’organisation.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom:
- "263874"
ms.assetid: 45dbba14-aba6-4571-be0d-5d1aba3515d9
ms.openlocfilehash: 7b8f6c1b32876af3a6992ff73c6898ce5307c5a2
ms.sourcegitcommit: 3c4dd125ed321af8a983e89bcb5bd6e5ed04a762
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206753"
---
# <a name="organizational-training-power-bi-content"></a>Contenu Power BI Formation dans l’organisation

[!include [banner](../includes/banner.md)]

Cet article décrit les applications de finances et d’opérations – Contenu Power BI de formation dans l’organisation.

## <a name="reports-that-are-included-in-the-content-pack"></a>États inclus dans le pack de contenu
Après avoir connecté le pack de contenu à vos données, les données de votre organisation s’affichent dans les états. Si vous n’avez jamais utilisé Microsoft Power BI auparavant, consultez la [Page d’apprentissage guidé pour Power BI](https://powerbi.microsoft.com/guided-learning/?WT.mc_id=PBIService_GetData) pour en savoir plus. Les états inclus dans le pack de contenu contiennent des graphiques et des tables qui fournissent des informations supplémentaires. Le tableau suivant décrit ces états.

| Etat          | Sommaire                                                                    |
|-----------------|-----------------------------------------------------------------------------|
| Analyse de cours | Enregistrement par emplacement, participants du cours par statut et liste d’enregistrements |
| Types de cours    | Types de cours par qualification                                                       |

Vous pouvez filtrer les graphiques et les vignettes affichés sur ces états et les épingler au tableau de bord. Pour savoir comment filtrer et épingler dans Power BI, voir [Créer et configurer un tableau de bord](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités
Les données de l’application sont utilisées pour remplir les états du pack de contenu Formation dans l’organisation. Le tableau suivant indique les entités sur lesquelles le pack de contenu est basé.

| Entité                    | Sommaire                                                         | Relations avec d’autres entités |
|---------------------------|------------------------------------------------------------------|-----------------------------------|
| Training\_CalendarOffset  | Décalages de calendrier pour diviser les états                                | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_Company         | Sociétés selon lesquelles filtrer les états                                   | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_Course          | Cours, description, nom de l’instructeur, emplacement, salle et statut | Training\_CourseAgenda, Training\_CourseAttendees, Training\_CourseSkill |
| Training\_CourseAgenda    | Emploi du temps, cours et heures de début et de fin                          | Training\_Company, Training\_CalendarOffset, Training\_Date, Training\_Course |
| Training\_CourseAttendees | Nom, statut, tâche et date d’enregistrement                         | Training\_Company, Training\_CalendarOffset, Training\_Date, Training\_Demographics, Training\_Employment, Training\_Course, Training\_WorkerName, Training\_WorkerTitle, Training\_Job, Training\_Position |
| Training\_CourseSkill     | Qualification, type et niveau de qualification                                     | Training\_Course |
| Training\_Date            | Jours, semaines, mois et années                                   | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_Demographics    | Date de naissance, sexe, origine ethnique et état civil         | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_Employment      | Date de début, date de fin et date de transition                        | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_Job             | Fonction, type et titre                                        | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_Position        | Poste, fonction et équivalent du temps plein                  | Training\_CourseAgenda, Training\_CourseAttendees |
| Training\_WorkerName      | Prénom, nom et nom complet                             | Training\_CourseAttendees |
| Training\_WorkerTitle     | Titre et date d’ancienneté                                         | Training\_CourseAttendees |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
