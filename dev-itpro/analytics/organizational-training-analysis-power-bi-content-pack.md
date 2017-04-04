---
title: "Contenu hiérarchique BI de courant de formation"
description: "Cette rubrique décrit Dynamics 365 pour les opérations - contenu hiérarchique BI de courant de formation. Elle décrit comment naviguer Feature Pack de contenu, et décrit le modèle de données et les entités qui ont été utilisés pour établir Feature Pack de contenu."
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

# <a name="organizational-training-power-bi-content"></a>Contenu hiérarchique BI de courant de formation

Cette rubrique décrit Dynamics 365 pour les opérations - contenu hiérarchique BI de courant de formation. Elle décrit comment naviguer Feature Pack de contenu, et décrit le modèle de données et les entités qui ont été utilisés pour établir Feature Pack de contenu.

<a name="accessing-the-content-pack"></a>Accéder Feature Pack de contenu
--------------------------

Recevez un pack hiérarchique de contenu de formation dans la bibliothèque partagé d'immobilisations dans Microsoft Dynamics Lifecycle Services (LCS). Pour plus d'informations sur le chargement le contenu comprimez- et connectez- le à votre Microsoft Dynamics 365 pour les données d'opérations, voir [contenu BI expérimentés dans des lettres de crédit Microsoft et de vos partenaires] (power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>Les rapports inclus dans le pack de contenu
Après avoir connecté Feature Pack de contenu à votre Dynamics 365 pour les données d'opérations, des données organisation d'états l'affichage de votre. Si ce n'est jamais utilisé le projet BI de courant de Microsoft péremption, vous souhaitez plus {{à:about}} {{son:about}} sujet sous l'onglet [page guidée d'enseignement pour BI de courant] (https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Les états inclus dans le pack de contenu ont des graphiques et des tables contenant les informations supplémentaires. Le tableau suivant décrit ces états.

| Etat          | Sommaire                                                                    |
|-----------------|-----------------------------------------------------------------------------|
| Analyse de cours | Enregistrement par emplacement, participants du cours par statut, et liste d'enregistrements |
| Types de cours    | Types de cours par qualification                                                       |

Vous pouvez filtrer les graphiques et les vignettes dans ces états, et épinglez les graphiques et les vignettes du tableau de bord. Pour plus d'informations sur le filtrage et épingler en BI de courant, voir [créez et configurez un tableau de bord] (https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités
Dynamics 365 pour les données d'opérations est utilisé pour remplir états du pack hiérarchique de contenu de formation. Le tableau suivant indique les entités qui Feature Pack de contenu est basée.

| Entité                    | Sommaire                                                         | Relations avec d'autres entités                                                                                                                                                                  |
|---------------------------|------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Formation\_CalendarOffset  | Compense de calendrier aux états des parts                                | Formation\_CourseAgenda formations\_CourseAttendees                                                                                                                                                   |
| Société d'\_de formation         | Sociétés pour filtrer les états par                                   | Formation\_CourseAgenda formations\_CourseAttendees                                                                                                                                                   |
| Cours d'\_de formation          | Cours, description, nom de l'instructeur, emplacement, pièce, et statut | Formation\_CourseAgenda formations\_CourseAttendees formations\_CourseSkill                                                                                                                             |
| Formation\_CourseAgenda    | Emploi du temps, cours, et début et heures de fin                          | Société\_de formation formations\_CalendarOffset constituant la date\_constituant le cours\_                                                                                                                         |
| Formation\_CourseAttendees | Nom, statut, tâches, et date d'enregistrement                         | Société\_de formation formations\_CalendarOffset constituant la date\_constituant la démographie\_formations l'emploi\_constituant le cours\_formations\_WorkerName formations\_WorkerTitle constituant\_de formation à un emploi\_ |
| Formation\_CourseSkill     | Qualification, type de qualification, et de niveau                                     | Cours d'\_de formation                                                                                                                                                                                   |
| Date d'\_de formation            | Jours, semaines, mois, années et                                   | Formation\_CourseAgenda formations\_CourseAttendees                                                                                                                                                   |
| Démographie d'\_de formation    | Date de naissance, le sexe, l'origine ethnique, et l'état civil         | Formation\_CourseAgenda formations\_CourseAttendees                                                                                                                                                   |
| Emploi d'\_de formation      | Date de début, Date de fin, et date de transition                        | Formation\_CourseAgenda formations\_CourseAttendees                                                                                                                                                   |
| Tâche d'\_de formation             | Fonction, type, et titre                                        | Formation\_CourseAgenda formations\_CourseAttendees                                                                                                                                                   |
| Poste d'\_de formation        | Poste, titre, et à temps plein (FTE) équivalent                  | Formation\_CourseAgenda formations\_CourseAttendees                                                                                                                                                   |
| Formation\_WorkerName      | Prénom, nom de famille, et nom complet                             | Formation\_CourseAttendees                                                                                                                                                                          |
| Formation\_WorkerTitle     | Date de titre et d'ancienneté                                         | Formation\_CourseAttendees                                                                                                                                                                          |

Ces entités a été utilisée pour créer des mesures calculées dans le modèle de données. Ces mesures calculées sont ensuite utilisées pour calculer les indicateurs de performance clé (KPIs) et les états utilisés dans l'établissement du pack de contenu. Si vous souhaitez inclure les calculs supplémentaires dans vos rapports et tableau de bord, vous pouvez télécharger et modifier le fichier de Training.pbix du crédit. Ce fichier est le modèle de données par défaut utilisé pour créer le pack de contenu. Après avoir apporté des modifications, vous pouvez créer un pack et un tableau de bord organisation de contenu contenant des informations que vous avez ajoutée.

## <a name="additional-resources"></a>Ressources supplémentaires
Voici quelques liens utiles liés aux entités et à la création du contenu Power BI :

-   [Entités de données](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Création de packs de contenu d'organisation](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modélisation de données à l'aide de Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Ajout de vignettes Power BI aux espaces de travail](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)



