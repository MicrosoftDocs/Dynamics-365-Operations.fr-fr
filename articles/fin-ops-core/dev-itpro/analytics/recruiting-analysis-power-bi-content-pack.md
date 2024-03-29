---
title: Contenu Power BI Recrutement
description: Cet article décrit le contenu Power BI Recrutement.
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
ms.custom: 263934
ms.assetid: 38e6827b-0819-473c-bc47-821a1ec482b8
ms.search.form: HcmRecruitmentWorkspace
ms.openlocfilehash: 412a1225544bb73649c9f0e703ec7b9a0d2613e0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276594"
---
# <a name="recruiting-power-bi-content"></a>Contenu Power BI Recrutement

[!include [banner](../includes/banner.md)]

Cet article décrit le contenu **Recrutement** de Microsoft Power BI. Elle explique également comment accéder aux états Power BI, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.

## <a name="accessing-the-power-bi-content"></a>Accès au contenu Power BI
Le contenu Power BI **Recrutement** s’affiche dans l’espace de travail **Gestion des recrutements**.

## <a name="reports-and-visuals-in-the-recruitment-management-workspace"></a>États et éléments visuels de l’espace de travail Gestion des recrutements
L’espace de travail **Gestion des recrutements** contient un onglet **Analyses**. Cet onglet contient le contenu Power BI intégré pour le recrutement. Le contenu se compose d’un onglet Vue d’ensemble et d’onglets supplémentaires contenant des détails. Le tableau suivant décrit les états de chaque onglet.

| Etat               | Sommaire |
|----------------------|----------|
| Vue d’ensemble du recrutement | Résume d’autres états |
| Analyse du candidat   | Nombre total de candidats, candidats par tâche, sources de candidat, candidats femme et homme et candidats par emplacement |
| Statut du candidat     | Candidats par type et statut, et statut du candidat |
| Analyse de recrutement  | Taux net d’embauche, jours moyens d’embauche, pourcentage de mauvaises embauches, coûts de recrutement, nombre de projets de recrutement, d’embauches sur candidature, de candidats et d’ouvertures par projet de recrutement |

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités
Vous pouvez filtrer les graphiques et les vignettes affichés sur ces états et les épingler au tableau de bord. Pour savoir comment filtrer et épingler dans Power BI, voir [Créer et configurer un tableau de bord](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

Le tableau suivant indique les entités sur lesquelles le pack de contenu Power BI **Recrutement** est basé.

| Entité               | Sommaire                                                         | Relations avec d’autres entités |
|----------------------|------------------------------------------------------------------|-----------------------------------|
| Candidat            | Candidats, candidats engagés, Taux net d’embauche et coûts          | Nom du candidat, société, décalage de calendrier, date, emplacement géographique, démographie, tâche, support, projet de recrutement |
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
