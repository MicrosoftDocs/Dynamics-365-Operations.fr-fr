---
title: "Contenu Power BI Perfectionnement de l'employé"
description: "Cette rubrique décrit le contenu Power BI Perfectionnement de l'employé. Elle explique également comment accéder aux états, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu."
author: jcart1106
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, UnifiedOperations, Talent, Core
ms.search.region: Global
ms.author: JCart
ms.search.validFrom: 2017-06-30T00:00:00.000Z
ms.dyn365.ops.version: July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: d25f3be5821a02ea618a2356878bf2904765a6f7
ms.contentlocale: fr-fr
ms.lasthandoff: 06/13/2017

---

# <a name="employee-development-power-bi-content"></a>Contenu Power BI Perfectionnement de l'employé

[!include[banner](../includes/banner.md)]

Cette rubrique décrit le contenu Microsoft Power BI **Perfectionnement de l'employé**. Elle explique également comment accéder aux états, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.

## <a name="accessing-the-power-bi-content"></a>Accès au contenu Power BI

Si vous utilisez Microsoft Dynamics 365 for Finance and Operations, Enterprise edition - mise à jour Juillet 2017, vous pouvez trouver le pack de contenu **Perfectionnement de l'employé** dans la bibliothèque Actifs partagés dans Microsoft Dynamics Lifecycle Services (LCS). Pour savoir comment télécharger le pack de contenu et le connecter à vos données, voir [Contenu Power BI dans LCS de Microsoft et de vos partenaires](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-power-bi-content"></a>États inclus dans le contenu Power BI
Les états inclus dans le contenu Power BI **Perfectionnement de l'employé** contiennent des graphiques et des tables qui fournissent des informations supplémentaires. Le tableau suivant décrit ces états.

| Etat                        | Sommaire |
|-------------------------------|----------|
| Vue d'ensemble Perfectionnement de l'employé | Synthèse des autres états |
| Analyse des qualifications de l'employé       | Types de qualification de l'employé et qualifications de l'employé par type |
| Analyse des niveaux de qualification de l'employé | Niveaux de qualification des employés par département, employés par niveau de qualification et type de qualification, niveaux le plus élevé et le plus bas par qualification |
| Profil de qualification                 | Profil de qualification pour l'employé sélectionné |
| Analyse des qualifications                | Qualification par type et classement |
| Analyse des évaluations de performances   | Employés par classement le plus bas et le plus élevé par tâche, classement des employés par département, employés selon le classement et le type de poste, et classement le plus élevé et le moins élevé par poste  |
| Analyses des performances des employés | Classements des employés pour le classement sélectionné par le responsable |

Vous pouvez filtrer les graphiques et les vignettes affichés sur ces états et les épingler au tableau de bord. Pour savoir comment filtrer et épingler dans Power BI, voir [Créer et configurer un tableau de bord](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités
| Entité                   | Sommaire                                                                                                   | Relations avec d'autres entités |
|--------------------------|------------------------------------------------------------------------------------------------------------|-----------------------------------|
| Décalage de calendrier          | Décalages de calendrier pour diviser les états                                                                          | Affectation antérieure de postes, Tendance du poste, Tendance de l'employé, Employé dont le contrat est terminé 
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
| Mission                      | Fonction, type et titre                                                                                      | Employé actuel, Poste actuel, Tendance de l'employé, Qualification préférée par tâche, Affectation antérieure de postes, Tendance du poste, Employé dont le contrat est terminé |
| Qualification préférée pour la tâche      | Importance, classement, qualification et niveau de qualification                                                                 | Mission |
| Analyse des qualifications de l'employé  | Certifié, niveau, date du niveau et qualification                                                                    | Nom de l'employé, Qualification |  
| Performances              | Classement, description et modèle de classement                                                                      | Employé actuel, Poste actuel, Tendance de l'employé, Qualification préférée par tâche, Affectation antérieure de postes, Tendance du poste, Employé dont le contrat est terminé |
|  Qualification                   | Qualification, type de qualification et évaluation                                                                              | Analyse des qualifications de l'employé, Qualification préférée pour la tâche |                                                                                                                        

Ces entités ont été utilisées pour créer des mesures calculées dans le modèle de données. Ces entités calculées sont ensuite utilisées pour calculer les indicateurs de performance clés (KPI) et les états utilisés dans le contenu Power BI. Si vous souhaitez inclure des calculs supplémentaires dans vos rapports et tableaux de bord, vous pouvez télécharger et modifier le fichier .pbix de LCS. Ce fichier est le modèle de données par défaut utilisé pour créer le contenu Power BI. Une fois que vous avez apporté vos modifications, vous pouvez créer un pack de contenu et un tableau de bord de l'organisation contenant les informations que vous avez ajoutées.
