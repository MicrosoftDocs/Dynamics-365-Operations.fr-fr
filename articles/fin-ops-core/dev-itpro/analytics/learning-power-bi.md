---
title: Contenu Power BI Apprentissage
description: Cet article décrit le contenu Apprentissage de Power BI.
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
ms.openlocfilehash: a7aca9e47ed26dcb4ef7f4b9aee72987e2d8fdd2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273957"
---
# <a name="learning-power-bi-content"></a>Contenu Power BI Apprentissage

[!include [banner](../includes/banner.md)]

Cet article décrit le contenu **Apprentissage** de Microsoft Power BI.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>États inclus dans le pack de contenu Power BI

Les états inclus dans le contenu Power BI **Apprentissage** contiennent des graphiques et des tables qui fournissent des informations supplémentaires. Le tableau suivant décrit ces états.

| Etat                | Sommaire |
|-----------------------|----------|
| Vue d’ensemble Apprentissage     | Synthèse des autres états |
| Analyse de cours       | Enregistrement par emplacement, participant par statut, cours par type par société et présence aux cours par tâche |
| Analyse de l’enregistrement | Liste des inscriptions |
| Types de cours          | Types de cours par qualification |
| Analyse de l’instructeur   | Ratio cours/instructeurs, nombre d’instructeurs, cours par instructeur et emploi du temps par instructeur |
| Cours proposés       | Listes des cours |
| Conception des cours        | Emploi du temps du cours |

Vous pouvez filtrer les graphiques et les vignettes affichés sur ces états et les épingler au tableau de bord. Pour savoir comment filtrer et épingler dans Power BI, voir [Créer et configurer un tableau de bord](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités

Les données suivantes sont utilisées pour remplir les états dans le contenu Power BI **Apprentissage**. Ce tableau indique les entités sur lesquelles le contenu est basé.

| Entité           | Sommaire                                                         | Relations avec d’autres entités |
|------------------|------------------------------------------------------------------|-----------------------------------|
| Décalage de calendrier  | Décalages de calendrier pour diviser les états                                | Emploi du temps du cours, Participants aux cours |
| Société          | Sociétés selon lesquelles filtrer les états                                   | Emploi du temps du cours, Participants aux cours |
| Cours           | Cours, description, nom de l’instructeur, emplacement, salle et statut | Emploi du temps du cours, Participants aux cours, Compétences du cours |
| Emploi du temps du cours    | Emploi du temps, cours et heures de début et de fin                          | Société, Décalage de calendrier, Date, Cours |
| Participants aux cours | Nom, statut, tâche et date d’enregistrement                         | Société, Décalage de calendrier, Date, Cours, Démographie, Emploi, Cours, Nom de l’employé, Titre de l’employé, Emploi, Poste |
| Compétences de cours     | Qualification, type et niveau de qualification                                     | Cours |
| Date             | Jours, semaines, mois et années                                   | Emploi du temps du cours, Participants aux cours |
| Démographie     | Date de naissance, sexe, origine ethnique et état civil         | Emploi du temps du cours, Participants aux cours |
| Emploi       | Date de début, date de fin et date de transition                        | Emploi du temps du cours, Participants aux cours |
| Mission              | Fonction, type et titre                                        | Emploi du temps du cours, Participants aux cours |
| Poste         | Poste, fonction et équivalent du temps plein                  | Emploi du temps du cours, Participants aux cours |
| Nom de l’employé    | Prénom, nom et nom complet                             | Participants aux cours |
| Titre de l’employé   | Titre et date d’ancienneté                                         | Participants aux cours |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
