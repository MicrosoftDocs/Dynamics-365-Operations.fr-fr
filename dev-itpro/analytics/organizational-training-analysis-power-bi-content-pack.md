---
title: Contenu Power BI Formation dans l&quot;organisation
description: "Cette rubrique décrit le contenu Power BI Formation dans l&quot;organisation dans Dynamics 365 for Operations. Elle explique également comment accéder au pack de contenu, et décrit le modèle de données et les entités qui permettent de créer le pack de contenu."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 263874
ms.assetid: 45dbba14-aba6-4571-be0d-5d1aba3515d9
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 104164f8ffd0d2bc3a64bf15d2fb5213234046ce
ms.lasthandoff: 03/31/2017


---

# <a name="organizational-training-power-bi-content"></a>Contenu Power BI Formation dans l'organisation

[!include[banner](../includes/banner.md)]


Cette rubrique décrit le contenu Power BI Formation dans l'organisation dans Dynamics 365 for Operations. Elle explique également comment accéder au pack de contenu, et décrit le modèle de données et les entités qui permettent de créer le pack de contenu.

<a name="accessing-the-content-pack"></a>Accès au pack de contenu
--------------------------

Vous trouverez le pack de contenu Formation dans l'organisation dans la bibliothèque Actifs partagés de Microsoft Dynamics Lifecycle Services (LCS). Pour savoir comment télécharger le pack de contenu et le connecter à vos données Microsoft Dynamics 365 for Operations, voir [Contenu Power BI dans LCS de Microsoft et de vos partenaires](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>États inclus dans le pack de contenu
Après avoir connecté le pack de contenu à vos données Dynamics 365 for Operations, les données de votre organisation s'affichent dans les états. Si vous n'avez jamais utilisé Microsoft Power BI auparavant, consultez la [Page d'apprentissage guidé pour Power BI](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData) pour en savoir plus. Les états inclus dans le pack de contenu contiennent des graphiques et des tables qui fournissent des informations supplémentaires. Le tableau suivant décrit ces états.

| Etat          | Sommaire                                                                    |
|-----------------|-----------------------------------------------------------------------------|
| Analyse de cours | Enregistrement par emplacement, participants du cours par statut et liste d'enregistrements |
| Types de cours    | Types de cours par qualification                                                       |

Vous pouvez filtrer les graphiques et les vignettes affichés sur ces états et les épingler au tableau de bord. Pour savoir comment filtrer et épingler dans Power BI, voir [Créer et configurer un tableau de bord](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités
Les données Dynamics 365 for Operations sont utilisées pour remplir les états du pack de contenu Formation dans l'entreprise. Le tableau suivant indique les entités sur lesquelles le pack de contenu est basé.

| Entité                    | Sommaire                                                         | Relations avec d'autres entités                                                                                                                                                                  |
|---------------------------|------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Training\_CalendarOffset  | Décalages de calendrier pour diviser les états                                | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_Company         | Sociétés selon lesquelles filtrer les états                                   | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_Course          | Cours, description, nom de l'instructeur, emplacement, salle et statut | Training\_CourseAgenda Training\_CourseAttendees Training\_CourseSkill                                                                                                                             |
| Training\_CourseAgenda    | Emploi du temps, cours et heures de début et de fin                          | Training\_Company Training\_CalendarOffset Training\_Date Training\_Course                                                                                                                         |
| Training\_CourseAttendees | Nom, statut, tâche et date d'enregistrement                         | Training\_Company Training\_CalendarOffset Training\_Date Training\_Demographics Training\_Employment Training\_Course Training\_WorkerName Training\_WorkerTitle Training\_Job Training\_Position |
| Training\_CourseSkill     | Qualification, type et niveau de qualification                                     | Training\_Course                                                                                                                                                                                   |
| Training\_Date            | Jours, semaines, mois et années                                   | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_Demographics    | Date de naissance, sexe, origine ethnique et état civil         | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_Employment      | Date de début, date de fin et date de transition                        | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_Job             | Fonction, type et titre                                        | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_Position        | Poste, fonction et équivalent du temps plein                  | Training\_CourseAgenda Training\_CourseAttendees                                                                                                                                                   |
| Training\_WorkerName      | Prénom, nom et nom complet                             | Training\_CourseAttendees                                                                                                                                                                          |
| Training\_WorkerTitle     | Titre et date d'ancienneté                                         | Training\_CourseAttendees                                                                                                                                                                          |

Ces entités ont été utilisées pour créer des mesures calculées dans le modèle de données. Ces entités calculées sont ensuite utilisées pour calculer les indicateurs de performance clés (KPI) et les états utilisés dans le pack de contenu. Si vous souhaitez inclure des calculs supplémentaires dans vos rapports et tableaux de bord, vous pouvez télécharger et modifier le fichier Training.pbix de LCS. Ce fichier est le modèle de données par défaut utilisé pour créer le pack de contenu. Une fois que vous avez apporté vos modifications, vous pouvez créer un pack de contenu et un tableau de bord de l'organisation contenant les informations que vous avez ajoutées.

## <a name="additional-resources"></a>Ressources supplémentaires
Voici quelques liens utiles liés aux entités et à la création du contenu Power BI :

-   [Entités de données](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Création de packs de contenu d'organisation](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modélisation de données à l'aide de Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Ajout de vignettes Power BI aux espaces de travail](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)





