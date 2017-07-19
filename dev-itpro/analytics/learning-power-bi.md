---
title: Contenu Power BI Apprentissage
description: "Cette rubrique décrit le contenu Power BI Apprentissage. Elle explique également comment accéder aux états, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu."
author: jcart1106
manager: AnnBe
ms.date: 06/16/2017
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
ms.openlocfilehash: a3f28d21a7e73d3ad462c5cc37198dd2b6f5f8af
ms.contentlocale: fr-fr
ms.lasthandoff: 06/13/2017

---

# <a name="learning-power-bi-content"></a>Contenu Power BI Apprentissage

[!include[banner](../includes/banner.md)]

Cette rubrique décrit le contenu Microsoft Power BI **Apprentissage**. Elle explique également comment accéder au contenu, et décrit le modèle de données et les entités qui permettent de créer le contenu.

## <a name="accessing-the-power-bi-content"></a>Accès au contenu Power BI

Si vous utilisez Microsoft Dynamics 365 for Finance and Operations, Enterprise edition - mise à jour Juillet 2017, vous pouvez trouver le contenu Power BI **Apprentissage** dans la bibliothèque Actifs partagés dans Microsoft Dynamics Lifecycle Services (LCS). Pour savoir comment télécharger le contenu et l'implémenter dans votre organisation, voir [Contenu Power BI dans LCS de Microsoft et de vos partenaires](power-bi-content-microsoft-partners.md). Pour visionner une démonstration sur l'implémentation du contenu Power BI, voir la présentation Office Mix [Contenu Power BI de Microsoft et de vos partenaires dans Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office Mix.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>États inclus dans le contenu Power BI

Les états inclus dans le contenu Power BI **Apprentissage** contiennent des graphiques et des tables qui fournissent des informations supplémentaires. Le tableau suivant décrit ces états.

| Etat                | Sommaire |
|-----------------------|----------|
| Vue d'ensemble Apprentissage     | Synthèse des autres états |
| Analyse de cours       | Enregistrement par emplacement, participant par statut, cours par type par société et présence aux cours par tâche |
| Analyse de l'enregistrement | Liste des inscriptions |
| Types de cours          | Types de cours par qualification |
| Analyse de l'instructeur   | Ratio cours/instructeurs, nombre d'instructeurs, cours par instructeur et emploi du temps par instructeur |
| Cours proposés       | Listes des cours |
| Conception des cours        | Emploi du temps du cours |

Vous pouvez filtrer les graphiques et les vignettes affichés sur ces états et les épingler au tableau de bord. Pour savoir comment filtrer et épingler dans Power BI, voir [Créer et configurer un tableau de bord](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités

Les données suivantes sont utilisées pour remplir les états dans le contenu Power BI **Apprentissage**. Ce tableau indique les entités sur lesquelles le contenu est basé.

| Entité           | Sommaire                                                         | Relations avec d'autres entités |
|------------------|------------------------------------------------------------------|-----------------------------------|
| Décalage de calendrier  | Décalages de calendrier pour diviser les états                                | Emploi du temps du cours, Participants aux cours |
| Société          | Sociétés selon lesquelles filtrer les états                                   | Emploi du temps du cours, Participants aux cours |
| Cours           | Cours, description, nom de l'instructeur, emplacement, salle et statut | Emploi du temps du cours, Participants aux cours, Compétences du cours |
| Emploi du temps du cours    | Emploi du temps, cours et heures de début et de fin                          | Société, Décalage de calendrier, Date, Cours |
| Participants aux cours | Nom, statut, tâche et date d'enregistrement                         | Société, Décalage de calendrier, Date, Cours, Démographie, Emploi, Cours, Nom de l'employé, Titre de l'employé, Emploi, Poste |
| Compétences de cours     | Qualification, type et niveau de qualification                                     | Cours |
| Date             | Jours, semaines, mois et années                                   | Emploi du temps du cours, Participants aux cours |
| Démographie     | Date de naissance, sexe, origine ethnique et état civil         | Emploi du temps du cours, Participants aux cours |
| Emploi       | Date de début, date de fin et date de transition                        | Emploi du temps du cours, Participants aux cours |
| Mission              | Fonction, type et titre                                        | Emploi du temps du cours, Participants aux cours |
| Poste         | Poste, fonction et équivalent du temps plein                  | Emploi du temps du cours, Participants aux cours |
| Nom de l'employé    | Prénom, nom et nom complet                             | Participants aux cours |
| Titre de l'employé   | Titre et date d'ancienneté                                         | Participants aux cours |

Ces entités ont été utilisées pour créer des mesures calculées dans le modèle de données. Ces entités calculées sont ensuite utilisées pour calculer les indicateurs de performance clés (KPI) et les états utilisés dans le contenu. Si vous souhaitez inclure des calculs supplémentaires dans vos rapports et tableaux de bord, vous pouvez télécharger et modifier le fichier .pbix de LCS. Ce fichier est le modèle de données par défaut utilisé pour créer le contenu. Une fois que vous avez apporté vos modifications, vous pouvez créer un pack de contenu et un tableau de bord de l'organisation contenant les informations que vous avez ajoutées.

