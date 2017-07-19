---
title: Contenu Power BI Recrutement
description: "Cette rubrique décrit le contenu Power BI Recrutement. Elle explique également comment accéder aux états, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu."
author: jcart1106
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 263934
ms.assetid: 38e6827b-0819-473c-bc47-821a1ec482b8
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 49cfd0f1ed645f1980b21b6d4f453cb7a8957a1a
ms.contentlocale: fr-fr
ms.lasthandoff: 06/13/2017

---

# <a name="recruiting-power-bi-content"></a>Contenu Power BI Recrutement

[!include[banner](../includes/banner.md)]

Cette rubrique décrit le contenu Microsoft Power BI **Recrutement**. Elle explique également comment accéder aux états Power BI, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.

## <a name="accessing-the-power-bi-content"></a>Accès au contenu Power BI
Si vous utilisez la mise à jour de juillet 2017 de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, le contenu Power BI **Recrutement** s'affiche dans l'espace de travail **Gestion des recrutements**. 

## <a name="reports-and-visuals-in-the-recruitment-management-workspace"></a>États et éléments visuels de l'espace de travail Gestion des recrutements
L'espace de travail **Gestion des recrutements** contient un onglet **Analyses**. Cet onglet contient le contenu Power BI intégré pour le recrutement. Le contenu se compose d'un onglet Vue d'ensemble et d'onglets supplémentaires contenant des détails. Le tableau suivant décrit les états de chaque onglet.

| Etat               | Sommaire |
|----------------------|----------|
| Vue d'ensemble du recrutement | Résume d'autres états |
| Analyse du candidat   | Nombre total de candidats, candidats par tâche, sources de candidat, candidats femme et homme et candidats par emplacement |
| Statut du candidat     | Candidats par type et statut, et statut du candidat |
| Analyse de recrutement  | Taux net d'embauche, jours moyens d'embauche, pourcentage de mauvaises embauches, coûts de recrutement, nombre de projets de recrutement, d'embauches sur candidature, de candidats et d'ouvertures par projet de recrutement |

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités
Vous pouvez filtrer les graphiques et les vignettes affichés sur ces états et les épingler au tableau de bord. Pour savoir comment filtrer et épingler dans Power BI, voir [Créer et configurer un tableau de bord](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

Le tableau suivant indique les entités sur lesquelles le contenu Power BI **Recrutement** est basé.

| Entité               | Sommaire                                                         | Relations avec d'autres entités |
|----------------------|------------------------------------------------------------------|-----------------------------------|
| Candidat            | Candidats, candidats engagés, Taux net d'embauche et coûts          | Nom du candidat, société, décalage de calendrier, date, emplacement géographique, démographie, tâche, support, projet de recrutement |
| Nom du candidat       | Prénom, nom et nom complet du candidat                   | Candidat, candidat employé, candidat dont le contrat est terminé |
| Décalage de calendrier      | Décalages de calendrier pour diviser les états                                | Candidat, candidat employé, candidat dont le contrat est terminé |
| Société              | Sociétés selon lesquelles filtrer les états                                   | Candidat, candidat employé, candidat dont le contrat est terminé |
| Date                 | Jours, semaines, mois et années                                   | Candidat, candidat employé, candidat dont le contrat est terminé |
| Démographie         | Date de naissance, sexe, origine ethnique et état civil         | Candidat, candidat employé, candidat dont le contrat est terminé |
| Candidat employé   | Candidat, performances, date de début et type de candidat           | Société, décalage de calendrier, date, emplacement géographique, nom du candidat, emploi, performances, tâche, support, projet de recrutement |
| Emploi           | Date de début, date de fin et date de transition                        | Candidat, candidat employé, candidat dont le contrat est terminé |
| Emplacement géographique  | Ville, département, code postal et région ou province                 | Candidat, candidat employé, candidat dont le contrat est terminé |
| Mission                  | Fonction, type et titre                                        | Candidat, candidat employé, candidat dont le contrat est terminé |
| Supports                | Source de candidats                                             | Candidat, candidat employé, candidat dont le contrat est terminé |
| Performances          | Classement, description et modèle de classement                            | Candidat, candidat employé, candidat dont le contrat est terminé |
| Projet de recrutement  | Description, statut du projet, et ouvertures de projet                | Candidat, candidat employé, candidat dont le contrat est terminé |
| Candidat dont le contrat est terminé | Candidats terminés, motif, performances et date de fin de contrat | Société, décalage de calendrier, date, emplacement géographique, performances, démographie, emploi, support, projet de recrutement, nom du candidat |

Ces entités ont été utilisées pour créer des mesures calculées. Ces entités calculées sont ensuite utilisées pour calculer les indicateurs de performance clés (KPI) et les états utilisés dans le contenu. Si vous souhaitez inclure des calculs supplémentaires dans vos rapports et tableaux de bord, vous pouvez télécharger et modifier le fichier Recruiting.pbix de Microsoft Dynamics Lifecycle Services (LCS). Ce fichier est le modèle de données par défaut utilisé pour créer le contenu. Une fois que vous avez apporté vos modifications, vous pouvez créer un pack de contenu et un tableau de bord de l'organisation contenant les informations que vous avez ajoutées.

