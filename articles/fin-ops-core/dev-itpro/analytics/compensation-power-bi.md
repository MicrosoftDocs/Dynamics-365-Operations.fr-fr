---
title: Contenu Power BI Rémunération
description: Cet article décrit le contenu Power BI Rémunération. Elle explique comment accéder aux rapports et fournit des informations sur le modèle de données utilisé.
author: jcart1106
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.search.form: HcmCompensationWorkspace
ms.openlocfilehash: 58d78dede753d8ed81a0e815b9ea02c69b70121f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291826"
---
# <a name="compensation-power-bi-content"></a>Contenu Power BI Rémunération

[!include [banner](../includes/banner.md)]

Cet article décrit le contenu Microsoft Power BI **Rémunération**. Elle explique également comment accéder aux états, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.

## <a name="accessing-the-power-bi-content"></a>Accès au contenu Power BI
Le contenu Power BI **Rémunération** s’affiche dans l’espace de travail **Gestion des rémunérations** si vous utilisez l’un des produits suivants :

- applications de finances et d’opérations
- Microsoft Dynamics 365 Human Resources

## <a name="reports-that-are-included-in-the-power-bi-content"></a>États inclus dans le pack de contenu Power BI
Les états inclus dans le contenu Power BI **Rémunération** contiennent des graphiques et des tables qui fournissent des informations supplémentaires. Le tableau suivant décrit ces états.

| Etat                     | Sommaire |
|----------------------------|----------|
| Vue d’ensemble Rémunération      | Synthèse des autres états |
| Analyse de rémunération      | Employés à tarif horaire et salariés par société, Nombre total pour les employés, Employés masculins et féminins par régime de rémunération et Rémunération d’employé par département |
| Analyse des rémunérations par poste      | La rémunération horaire et salariale la plus élevée et la moins élevée, les postes avec le salaire le plus élevé et le plus bas et les postes à temps plein et à temps partiel |
| Analyse des régimes de rémunération | Inscription de l’employé par avantage sélectionné |

Vous pouvez filtrer les graphiques et les vignettes affichés sur ces états et les épingler au tableau de bord. Pour savoir comment filtrer et épingler dans Power BI, voir [Créer et configurer un tableau de bord](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités
Les données suivantes sont utilisées pour remplir les états dans le contenu Power BI **Rémunération**. Ce tableau indique les entités sur lesquelles le contenu est basé.

| Entité                   | Sommaire                                                                                                   | Relations avec d’autres entités |
|--------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Décalage de calendrier          | Décalages de calendrier pour diviser les états                                                                          | Affectation antérieure de postes, Tendance du poste, Tendance de l’employé, Employé dont le contrat est terminé |
| Société                  | Sociétés selon lesquelles filtrer les états                                                                             | Rémunération actuelle, Employé actuel, Employé dont le contrat est terminé, Tendance de l’employé |
| Rémunération             | Taux de salaire et fréquence dans le temps                                                                           | Rémunération actuelle, Employé actuel, Employé dont le contrat est terminé, Tendance de l’employé |
| Rémunération actuelle     | Taux de salaire et fréquence à compter de la date actuelle                                                              | Société, Compensation, Démographie, Tâche, Poste |
| Poste actuel         | Postes à compter de la date actuelle, postes équivalents à temps plein, postes vacants et postes vacants à pourvoir | Tâche, Poste |
| Employé actuel         | Collaborateurs à compter de la date actuelle, âge et effectif                                                         | Société, Rémunération, Emplacement géographique, Nom de l’employé, Génère un état pour, Titre de l’employé, Démographie, Tâche, Emploi, Poste, Avantages |
| Date                     | Jours, semaines, mois et années                                                                             | Affectation antérieure de postes, Tendance du poste, Tendance de l’employé, Employé dont le contrat est terminé, Tendance de l’employé |
| Démographie             | Date de naissance, sexe, origine ethnique et état civil                                                   | Employé actuel, Employé dont le contrat est terminé, Tendance de l’employé |
| Emploi               | Date de début, date de fin et date de transition                                                                  | Employé actuel, Employé dont le contrat est terminé, Tendance de l’employé |
| Emplacement géographique      | Ville, département, code postal et région ou province                                                           | Employé actuel, Employé dont le contrat est terminé, Tendance de l’employé |
| Mission                      | Fonction, type et titre                                                                                  | Poste actuel, Employé actuel |
| Affectation antérieure de postes | Motif d’affectation, date de début, date de fin et tâche                                                           | Décalage de calendrier, Date, Tâche, Poste |
| Poste                 | Département, ETP, poste, type de poste et titre                                                        | Poste actuel, Employé actuel |
| Tendance du poste           | Postes dans le temps, ETP et tâche                                                                          | Décalage de calendrier, Date, Tâche, Poste |
| Génère un état pour               | Prénom, nom et nom complet                                                                       | Collaborateur actuel, Employé dont le contrat est terminé, Tendance de l’employé |
| Employé dont le contrat est terminé      | Employés dont le contrat est terminé, date de fin du contrat, titre, poste et tâche                                           | Société, Rémunération, Emplacement géographique, Nom de l’employé, Génère un état pour, Décalage de calendrier, Date, Titre de l’employé, Démographie, Emploi, Tâche, Poste, Avantages |
| Avantages                 | Date d’effet, option d’avantage, régime d’avantages et type d’avantage                                             | Nom actuel, Employé dont le contrat est terminé, Tendance de l’employé |
| Nom de l’employé            | Prénom, nom et nom complet                                                                       | Employé actuel, Employé dont le contrat est terminé, Tendance de l’employé |
| Titre de l’employé           | Titre et date d’ancienneté                                                                                   | Employé actuel, Employé dont le contrat est terminé, Tendance de l’employé |
| Tendance de l’employé           | Collaborateurs dans le temps, effectif, société et poste                                                        | Société, Rémunération, Emplacement géographique, Nom de l’employé, Génère un état pour, Décalage de calendrier, Date, Titre de l’employé, Démographie, Emploi, Tâche, Avantages |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
