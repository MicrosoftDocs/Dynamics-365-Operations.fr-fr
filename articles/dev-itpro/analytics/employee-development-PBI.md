---
title: Contenu Power BI Perfectionnement de l'employé
description: Cette rubrique décrit le contenu Power BI Perfectionnement de l'employé.
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 2e13b43812e0d6f8b50cb3fcf65f277afbe9e806
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1849761"
---
# <a name="employee-development-power-bi-content"></a>Contenu Power BI Perfectionnement de l'employé

[!include [banner](../includes/banner.md)]

Cette rubrique décrit le contenu Power BI **Perfectionnement de l'employé**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>États inclus dans le pack de contenu Power BI
Les états inclus dans le contenu Power BI **Perfectionnement de l'employé** contiennent des graphiques et des tables qui fournissent des informations supplémentaires. Le tableau suivant décrit ces états.

| Etat                        | Sommaire |
|-------------------------------|----------|
| Vue d'ensemble Perfectionnement de l'employé | Synthèse des autres états |
| Analyse des qualifications de l'employé       | Types de qualification de l'employé et qualifications de l'employé par type |
| Analyse des niveaux de qualification de l'employé | Niveaux de qualification des employés par département, employés par niveau de qualification et type de qualification, niveaux le plus élevé et le plus bas par qualification |
| Profil de qualification                 | Profil de qualification pour l'employé sélectionné |
| Analyse des qualifications                | Qualification par type et classement |
| Analyse des évaluations de performances   | Employés par classement le plus bas et le plus élevé par tâche, classement des employés par département, employés selon le classement et le type de poste, et classement le plus élevé et le moins élevé par poste |
| Analyses des performances des employés | Classements des employés pour le classement sélectionné par le responsable |

Vous pouvez filtrer les graphiques et les vignettes affichés sur ces états et les épingler au tableau de bord. Pour savoir comment filtrer et épingler dans Power BI, voir [Créer et configurer un tableau de bord](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités

| Entité                   | Sommaire                                                                                                   | Relations avec d'autres entités |
|--------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Décalage de calendrier          | Décalages de calendrier pour diviser les états                                                                          | Affectation antérieure de postes, Tendance du poste, Tendance de l'employé, Employé dont le contrat est terminé |
| Société                  | Sociétés selon lesquelles filtrer les états                                                                             | Employé actuel, Employé dont le contrat est terminé, Tendance de l'employé |
| Poste actuel         | Postes à compter de la date actuelle, postes équivalents à temps plein, postes vacants et postes vacants à pourvoir | Tâche, Poste |
| Employé actuel         | Collaborateurs à compter de la date actuelle, âge et effectif                                                         | Société, Emplacement géographique, Nom de l'employé, Génère un état pour, Titre de l'employé, Démographie, Tâche, Emploi, Poste |
| Date                     | Jours, semaines, mois et années                                                                             | Affectation antérieure de postes, Tendance du poste, Tendance de l'employé, Employé dont le contrat est terminé, Tendance de l'employé |
| Démographie             | Date de naissance, sexe, origine ethnique et état civil                                                   | Employé actuel, Employé dont le contrat est terminé, Tendance de l'employé |
| Emploi               | Date de début, date de fin et date de transition                                                                  | Employé actuel, Employé dont le contrat est terminé, Tendance de l'employé |
| Emplacement géographique      | Ville, département, code postal et région ou province                                                           | Employé actuel, Employé dont le contrat est terminé, Tendance de l'employé |
| Mission                      | Fonction, type et titre                                                                                  | Poste actuel, Employé actuel |
| Affectation antérieure de postes | Motif d'affectation, date de début, date de fin et tâche                                                           | Décalage de calendrier, Date, Tâche, Poste |
| Poste                 | Département, ETP, poste, type de poste et titre                                                        | Poste actuel, Employé actuel |
| Tendance du poste           | Postes dans le temps, ETP et tâche                                                                          | Décalage de calendrier, Date, Tâche, Poste |
| Génère un état pour               | Prénom, nom et nom complet                                                                       | Employé actuel, Employé dont le contrat est terminé, Tendance de l'employé |
| Employé dont le contrat est terminé      | Collaborateurs dont le contrat est terminé, date de fin du contrat, titre, poste et tâche                                             | Société, Emplacement géographique, Nom de l'employé, Génère un état pour, Décalage de calendrier, Date, Titre de l'employé, Démographie, Emploi, Tâche, Poste |
| Nom de l'employé            | Prénom, nom et nom complet                                                                       | Collaborateur actuel, Employé dont le contrat est terminé, Tendance de l'employé |
| Titre de l'employé           | Titre et date d'ancienneté                                                                                   | Employé actuel, Employé dont le contrat est terminé, Tendance de l'employé |
| Tendance de l'employé           | Collaborateurs dans le temps, effectif, société et poste                                                        | Société, Emplacement géographique, Nom de l'employé, Génère un état pour, Décalage de calendrier, Date, Titre de l'employé, Démographie, Emploi, Tâche |
| Mission                      | Fonction, type et titre                                                                                  | Employé actuel, Poste actuel, Tendance de l'employé, Qualification préférée par tâche, Affectation antérieure de postes, Tendance du poste, Employé dont le contrat est terminé |
| Qualification préférée pour la tâche      | Importance, classement, qualification et niveau de qualification                                                                 | Mission |
| Analyse des qualifications de l'employé  | Certifié, niveau, date du niveau et qualification                                                                    | Nom de l'employé, Qualification |
| Performances              | Classement, description et modèle de classement                                                                      | Employé actuel, Poste actuel, Tendance de l'employé, Qualification préférée par tâche, Affectation antérieure de postes, Tendance du poste, Employé dont le contrat est terminé |
| Qualification                    | Qualification, type de qualification et évaluation                                                                              | Analyse des qualifications de l'employé, Qualification préférée pour la tâche |
