---
title: Contenu Power BI Mesures de main d’œuvre
description: Cet article décrit le contenu Power BI Mesures de la main-d’œuvre.
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
ms.custom: 264084
ms.assetid: 8e700583-3a7d-4f5f-9ac8-58c4feed1a02
ms.search.form: HcmWorkforceWorkspace
ms.openlocfilehash: 9d5c156eda3559394cb2723f0492b0ab575d815d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289814"
---
# <a name="workforce-metrics-power-bi-content"></a>Contenu Power BI Mesures de main d’œuvre

[!include [banner](../includes/banner.md)]

Cet article décrit le contenu **Mesures de la main-d’œuvre** de Microsoft Power BI. Elle explique également comment accéder aux états Power BI, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.

## <a name="accessing-the-power-bi-content"></a>Accès au contenu Power BI
Le contenu Power BI **Mesures de la main d’œuvre** s’affiche dans l’espace de travail **Gestion du personnel** si vous utilisez l’un des produits suivants :

- Microsoft Dynamics 365 Finance
- Microsoft Dynamics 365 Human Resources

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Mesures incluses dans le pack de contenu Power BI
Le tableau suivant répertorie les mesures affichées dans chaque état.

| Etat                                           | Métriques |
|--------------------------------------------------|---------|
| Mesures des employés                                   | Synthèse des autres états |
| Analyse des effectifs Société, Service, Site | Comptage des effectifs par société, comptage des effectifs par service, comptage des effectifs par site et comptage des effectifs totaux |
| Comptage des effectifs Poste, Échelon, Responsable            | Comptage des effectifs par poste, comptage des effectifs par échelon, comptage des effectifs par responsable et comptage des effectifs totaux |
| Analyse de tendance des effectifs                         | Comptage des effectifs cette année par rapport à l’année dernière et roulement des effectifs pour les 12 derniers mois |
| Analyse FTE                                     | Nombre total d’employés équivalents temps plein, nombre total d’employés équivalents temps plein affectés, employés équivalents temps plein par département, employés équivalents temps plein pour les 12 derniers mois et employés équivalents temps plein par tâche |
| Démographie de la main-d’œuvre                           | Comptage des effectifs par âge et sexe, effectifs par origine ethnique, effectifs par statut de vétéran, effectifs par situation familiale, nombre d’étudiants à temps plein, ancienneté moyenne, âge moyen, rapport nombre de femmes/nombre d’hommes chez les employés et langues parlées par les employés |
| Analyse des postes                                | Postes vacants par service, postes vacants à pourvoir, postes actifs à inactifs et postes par service |
| Analyse de la réduction naturelle des effectifs                               | Réduction naturelle des effectifs cette année par rapport à l’année dernière, employés sur le départ par âge et sexe, ancienneté moyenne des employés sur le départ, employés sur le départ ce mois-ci et employés sur le départ par motif |
| Personnes par département                             | Employés avec un matricule par service, poste et dates de début et de fin d’affectation |
| Analyse d’ancienneté                               | Ancienneté moyenne, nombre moyen d’années de service par société et liste d’ancienneté |
| Anniversaires des employés                           | Anniversaires ce mois-ci, anniversaires le mois suivant, employés par années de service et anniversaires, années de service par département |
| Anniversaires des employés                               | Anniversaires ce mois-ci, anniversaires le mois suivant, anniversaires des employés et anniversaires par mois et service |
| Projets d’embauche collective                               | Nombre total de projets d’embauche collective, projets d’embauche collective par statut, projets d’embauche collective par département et propriétaire, projets d’embauche collective par tâche et projets d’embauche collective |

Vous pouvez filtrer les graphiques et les vignettes affichés sur ces états et les épingler au tableau de bord. Pour savoir comment filtrer et épingler dans Power BI, voir [Créer et configurer un tableau de bord](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

Veillez à télécharger le contenu Power BI **Mesures de la main œuvre** qui s’applique à la version de Microsoft Dynamics 365 que vous utilisez.

> [!NOTE]
> Les fichiers .pbix disponibles dans Lifecycle Services s’appliquent uniquement aux applications de finances et d’opérations.

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités
Le tableau suivant indique les entités sur lesquelles le contenu est basé.

| Entité                   | Sommaire                                                                            | Relations avec d’autres entités |
|--------------------------|-------------------------------------------------------------------------------------|-----------------------------------|
| Décalage de calendrier          | Décalages de calendrier pour diviser les états                                                   | Affectation antérieure de postes, Tendance du poste, Tendance de l’employé, Employé dont le contrat est terminé |
| Société                  | Sociétés selon lesquelles filtrer les états                                                      | Employé actuel, Employé dont le contrat est terminé, Tendance de l’employé |
| Poste actuel         | Postes à compter de la date actuelle, postes équivalents à temps plein, postes vacants et postes vacants à pourvoir | Tâche, Poste |
| Employé actuel         | Collaborateurs à compter de la date actuelle, âge et effectif                                  | Société, Emplacement géographique, Nom de l’employé, Génère un état pour, Titre de l’employé, Démographie, Tâche, Emploi, Poste |
| Date                     | Jours, semaines, mois et années                                                      | Affectation antérieure de postes, Tendance du poste, Tendance de l’employé, Employé dont le contrat est terminé, Tendance de l’employé |
| Démographie             | Date de naissance, sexe, origine ethnique et état civil                            | Employé actuel, Employé dont le contrat est terminé, Tendance de l’employé |
| Emploi               | Date de début, date de fin et date de transition                                           | Employé actuel, Employé dont le contrat est terminé, Tendance de l’employé |
| Emplacement géographique      | Ville, département, code postal et région ou province                                    | Employé actuel, Employé dont le contrat est terminé, Tendance de l’employé |
| Mission                      | Fonction, type et titre                                                           | Poste actuel, Employé actuel |
| Affectation antérieure de postes | Motif d’affectation, date de début, date de fin et tâche                                    | Décalage de calendrier, Date, Tâche, Poste |
| Poste                 | Département, ETP, poste, type de poste et titre                                 | Poste actuel, Employé actuel |
| Tendance du poste           | Postes dans le temps, ETP et tâche                                                   | Décalage de calendrier, Date, Tâche, Poste |
| Génère un état pour               | Prénom, nom et nom complet                                                | Employé actuel, Employé dont le contrat est terminé, Tendance de l’employé |
| Employé dont le contrat est terminé      | Collaborateurs dont le contrat est terminé, date de fin du contrat, titre, poste et tâche                      | Société, Emplacement géographique, Nom de l’employé, Génère un état pour, Décalage de calendrier, Date, Titre de l’employé, Démographie, Emploi, Tâche, Poste |
| Nom de l’employé            | Prénom, nom et nom complet                                                | Collaborateur actuel, Employé dont le contrat est terminé, Tendance de l’employé |
| Titre de l’employé           | Titre et date d’ancienneté                                                            | Employé actuel, Employé dont le contrat est terminé, Tendance de l’employé |
| Tendance de l’employé           | Collaborateurs dans le temps, effectif, société et poste                                 | Société, Emplacement géographique, Nom de l’employé, Génère un état pour, Décalage de calendrier, Date, Titre de l’employé, Démographie, Emploi, Tâche |
| Projet d’embauche collective        | Nombre de projets d’embauche collective, propriétaire du projet et statut du projet                     | Société, ligne d’embauche collective |
| Ligne d’embauche collective           | Département, type d’emploi et poste                                           | Date, tâche, projet d’embauche collective |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
