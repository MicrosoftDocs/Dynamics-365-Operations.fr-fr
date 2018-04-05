---
title: "Contenu Power BI Rémunération"
description: "Cette rubrique décrit le contenu Power BI Rémunération. Elle explique également comment accéder aux états, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu."
author: jcart1106
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HcmCompensationWorkspace
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 93c005d4b85b56f77ddd488c91e477970f4ccd07
ms.contentlocale: fr-fr
ms.lasthandoff: 03/26/2018

---

# <a name="compensation-power-bi-content"></a>Contenu Power BI Rémunération

[!include[banner](../includes/banner.md)]

Cette rubrique décrit le contenu Microsoft Power BI **Rémunération**. Elle explique également comment accéder aux états, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.

## <a name="accessing-the-power-bi-content"></a>Accès au contenu Power BI
Le contenu Power BI **Rémunération** s'affiche dans l'espace de travail **Gestion des rémunérations** si vous utilisez l'un des produits suivants :

- Microsoft Dynamics 365 for Finance and Operations
- Microsoft Dynamics 365 for Talent

## <a name="reports-that-are-included-in-the-power-bi-content"></a>États inclus dans le contenu Power BI
Les états inclus dans le contenu Power BI **Rémunération** contiennent des graphiques et des tables qui fournissent des informations supplémentaires. Le tableau suivant décrit ces états.

| Etat                     | Sommaire |
|----------------------------|----------|
| Vue d'ensemble Rémunération      | Synthèse des autres états |
| Analyse de rémunération      | Employés à tarif horaire et salariés par société, Nombre total pour les employés, Employés masculins et féminins par régime de rémunération et Rémunération d'employé par département |
| Analyse des rémunérations par poste      | La rémunération horaire et salariale la plus élevée et la moins élevée, les postes avec le salaire le plus élevé et le plus bas et les postes à temps plein et à temps partiel |
| Analyse des régimes de rémunération | Inscription de l'employé par avantage sélectionné |

Vous pouvez filtrer les graphiques et les vignettes affichés sur ces états et les épingler au tableau de bord. Pour savoir comment filtrer et épingler dans Power BI, voir [Créer et configurer un tableau de bord](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).


## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités
Les données suivantes sont utilisées pour remplir les états dans le contenu Power BI **Rémunération**. Ce tableau indique les entités sur lesquelles le contenu est basé.

| Entité                   | Sommaire                                                                                                   | Relations avec d'autres entités |
|--------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Décalage de calendrier          | Décalages de calendrier pour diviser les états                                                                          | Affectation antérieure de postes, Tendance du poste, Tendance de l'employé, Employé dont le contrat est terminé |
| Société                  | Sociétés selon lesquelles filtrer les états                                                                             | Rémunération actuelle, Employé actuel, Employé dont le contrat est terminé, Tendance de l'employé |
| Rémunération             | Taux de salaire et fréquence dans le temps                                                                           | Rémunération actuelle, Employé actuel, Employé dont le contrat est terminé, Tendance de l'employé |
| Rémunération actuelle     | Taux de salaire et fréquence à compter de la date actuelle                                                              | Société, Compensation, Démographie, Tâche, Poste |
| Poste actuel         | Postes à compter de la date actuelle, postes équivalents à temps plein, postes vacants et postes vacants à pourvoir | Tâche, Poste |
| Employé actuel         | Collaborateurs à compter de la date actuelle, âge et effectif                                                         | Société, Rémunération, Emplacement géographique, Nom de l'employé, Génère un état pour, Titre de l'employé, Démographie, Tâche, Emploi, Poste, Avantages |
| Date                     | Jours, semaines, mois et années                                                                             | Affectation antérieure de postes, Tendance du poste, Tendance de l'employé, Employé dont le contrat est terminé, Tendance de l'employé |
| Démographie             | Date de naissance, sexe, origine ethnique et état civil                                                   | Employé actuel, Employé dont le contrat est terminé, Tendance de l'employé |
| Emploi               | Date de début, date de fin et date de transition                                                                  | Employé actuel, Employé dont le contrat est terminé, Tendance de l'employé |
| Emplacement géographique      | Ville, département, code postal et région ou province                                                           | Employé actuel, Employé dont le contrat est terminé, Tendance de l'employé |
| Mission                      | Fonction, type et titre                                                                                  | Poste actuel, Employé actuel |
| Affectation antérieure de postes | Motif d'affectation, date de début, date de fin et tâche                                                           | Décalage de calendrier, Date, Tâche, Poste |
| Poste                 | Département, ETP, poste, type de poste et titre                                                        | Poste actuel, Employé actuel |
| Tendance du poste           | Postes dans le temps, ETP et tâche                                                                          | Décalage de calendrier, Date, Tâche, Poste |
| Génère un état pour               | Prénom, nom et nom complet                                                                       | Collaborateur actuel, Employé dont le contrat est terminé, Tendance de l'employé |
| Employé dont le contrat est terminé      | Employés dont le contrat est terminé, date de fin du contrat, titre, poste et tâche                                             | Société, Rémunération, Emplacement géographique, Nom de l'employé, Génère un état pour, Décalage de calendrier, Date, Titre de l'employé, Démographie, Emploi, Tâche, Poste, Avantages |
| Avantages                 | Date d'effet, option d'avantage, régime d'avantages et type d'avantage                                             | Nom actuel, Employé dont le contrat est terminé, Tendance de l'employé |
| Nom de l'employé            | Prénom, nom et nom complet                                                                       | Employé actuel, Employé dont le contrat est terminé, Tendance de l'employé |
| Titre de l'employé           | Titre et date d'ancienneté                                                                                   | Employé actuel, Employé dont le contrat est terminé, Tendance de l'employé |
| Tendance de l'employé           | Collaborateurs dans le temps, effectif, société et poste                                                        | Société, Rémunération, Emplacement géographique, Nom de l'employé, Génère un état pour, Décalage de calendrier, Date, Titre de l'employé, Démographie, Emploi, Tâche, Avantages |



