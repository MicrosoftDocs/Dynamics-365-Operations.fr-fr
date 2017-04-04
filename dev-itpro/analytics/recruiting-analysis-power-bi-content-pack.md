---
title: Contenu recrutement BI de courant
description: "Cette rubrique décrit Dynamics 365 pour les opérations - contenu recrutement BI de courant. Elle explique comment accéder aux états inclus dans le pack de contenu, et fournit des informations sur le modèle de données et des entités utilisés pour établir Feature Pack de contenu."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 263934
ms.assetid: 38e6827b-0819-473c-bc47-821a1ec482b8
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: d307733193b388149f83dd420cc7003edcf7749a
ms.lasthandoff: 03/31/2017


---

# <a name="recruiting-power-bi-content"></a>Contenu recrutement BI de courant

Cette rubrique décrit Dynamics 365 pour les opérations - contenu recrutement BI de courant. Elle explique comment accéder aux états inclus dans le pack de contenu, et fournit des informations sur le modèle de données et des entités utilisés pour établir Feature Pack de contenu.

<a name="accessing-the-content-pack"></a>Accéder Feature Pack de contenu
--------------------------

Recevez un pack recrutement de contenu de la bibliothèque partagé d'immobilisations dans Microsoft Dynamics Lifecycle Services (LCS). Pour plus d'informations sur le chargement le contenu comprimez- et connectez- le à votre Microsoft Dynamics 365 pour les données d'opérations, voir [contenu BI expérimentés dans des lettres de crédit Microsoft et de vos partenaires] (power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>Les rapports inclus dans le pack de contenu
Après avoir connecté Feature Pack de contenu à votre Dynamics 365 pour les données d'opérations, des données organisation d'états l'affichage de votre. Si ce n'est jamais utilisé le projet BI de courant de Microsoft péremption, vous souhaitez plus {{à:about}} {{son:about}} sujet sous l'onglet [page guidée d'enseignement pour BI de courant] (https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Les états inclus dans le pack de contenu ont des graphiques et des tables contenant les informations supplémentaires. Le tableau suivant décrit ces états.

| Etat                       | Sommaire                                                                                               |
|------------------------------|--------------------------------------------------------------------------------------------------------|
| Analyse du candidat           | Candidats par tâche, sources de candidat, candidats par emplacement, et nombre total de candidats           |
| Statut du candidat             | Candidats par le type et le statut, et le statut du candidat                                                    |
| Démographie du candidat       | Candidats par âge et sexe, et candidats par niveau et le statut de formation                             |
| Analyse Recrutement          | Taux net d'embauche, jours moyen à embaucher, pourcentage de mauvaises embauches, et coûts de recrutement                    |
| Analyse de projet de recrutement | Numéro de projets de recrutement, d'ouvertures par projet de recrutement, et de candidats par projet de recrutement |

Vous pouvez filtrer les graphiques et les vignettes dans ces états, et épinglez les graphiques et les vignettes du tableau de bord. Pour plus d'informations sur le filtrage et épingler en BI de courant, voir [créez et configurez un tableau de bord] (https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités
Dynamics 365 pour les données d'opérations est utilisé pour remplir états du pack recrutement de contenu. Le tableau suivant indique les entités qui Feature Pack de contenu est basée.

| Entité                          | Sommaire                                                         | Relations avec d'autres entités                                                                                                                                                                                                                 |
|---------------------------------|------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Candidat recrutement\_           | Candidats, candidats engagés, Taux net d'embauche, et coûts          | \_recrutement ApplicantName recrutant la société\_recrutant\_CalendarOffset Recuriting\_tôt\_recrutement GeographicLocation recrutant la démographie\_recrutant la tâche\_recrutant le support\_recrutant\_RecruitmentProject                                |
| \_recrutement ApplicantName       | De candidat autres prénoms, nom, le nom complet                   | Candidat recrutement\_recrutant\_EmployedApplicant recrutant\_TerminatedApplicant                                                                                                                                                               |
| \_recrutement CalendarOffset      | Compense de calendrier aux états des parts                                | Candidat recrutement\_recrutant\_EmployedApplicant recrutant\_TerminatedApplicant                                                                                                                                                               |
| Société Recrutement\_             | Sociétés pour filtrer les états par                                   | Candidat recrutement\_recrutant\_EmployedApplicant recrutant\_TerminatedApplicant                                                                                                                                                               |
| Date Recrutement\_                | Jours, semaines, mois, années et                                   | Candidat recrutement\_recrutant\_EmployedApplicant recrutant\_TerminatedApplicant                                                                                                                                                               |
| Démographie\_Recrutement        | Date de naissance, le sexe, l'origine ethnique, et l'état civil         | Candidat recrutement\_recrutant\_EmployedApplicant recrutant\_TerminatedApplicant                                                                                                                                                               |
| \_recrutement EmployedApplicant   | Candidat, performances, date de début, et type de candidat           | Société Recrutement\_recrutant\_CalendarOffset recrutant la date\_recrutant\_GeographicLocation recrutant\_ApplicantName recrutant l'emploi\_recrutant les performances\_recrutant la tâche\_recrutant le support\_recrutant\_RecruitmentProject          |
| Emploi recrutement\_          | Date de début, Date de fin, et date de transition                        | Candidat recrutement\_recrutant\_EmployedApplicant recrutant\_TerminatedApplicant                                                                                                                                                               |
| \_recrutement GeographicLocation  | Ville, département, le code postal, puis état ou cette province                 | Candidat recrutement\_recrutant\_EmployedApplicant recrutant\_TerminatedApplicant                                                                                                                                                               |
| Tâche Recrutement\_                 | Fonction, type, et titre                                        | Candidat recrutement\_recrutant\_EmployedApplicant recrutant\_TerminatedApplicant                                                                                                                                                               |
| Support de recrutement\_               | Source de candidats                                             | Candidat recrutement\_recrutant\_EmployedApplicant recrutant\_TerminatedApplicant                                                                                                                                                               |
| Performances Recrutement\_         | Classement, description, et modèle de classement                            | Candidat recrutement\_recrutant\_EmployedApplicant recrutant\_TerminatedApplicant                                                                                                                                                               |
| \_recrutement RecruitmentProject  | Description, statut du projet, et ouvertures de projet                | Candidat recrutement\_recrutant\_EmployedApplicant recrutant\_TerminatedApplicant                                                                                                                                                               |
| \_recrutement TerminatedApplicant | Candidats terminés, motif, performances, et date de fin de contrat | Société Recrutement\_recrutant\_CalendarOffset recrutant la date\_recrutant\_GeographicLocation recrutant les performances\_recrutant la démographie\_recrutant l'emploi\_recrutant le support\_recrutant\_RecruitmentProject recrutant\_ApplicantName |

Ces entités a été utilisée pour créer des mesures. Ces mesures calculées sont ensuite utilisées pour calculer les indicateurs de performance clé (KPIs) et les états utilisés dans l'établissement du pack de contenu. Si vous souhaitez inclure les calculs supplémentaires dans vos rapports et tableau de bord, vous pouvez télécharger et modifier le fichier de Recruiting.pbix du crédit. Ce fichier est le modèle de données par défaut utilisé pour créer le pack de contenu. Après avoir apporté des modifications, vous pouvez créer un pack et un tableau de bord organisation de contenu contenant des informations que vous avez ajoutée.

## <a name="additional-resources"></a>Ressources supplémentaires
Voici quelques liens utiles liés aux entités et à la création du contenu Power BI :

-   [Entités de données](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Création de packs de contenu d'organisation](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modélisation de données à l'aide de Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Ajout de vignettes Power BI aux espaces de travail](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)



