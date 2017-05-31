---
title: Recrutement du contenu Power BI
description: "Cette rubrique décrit le contenu Recrutement Power BI dans Dynamics 365 for Operations. Elle explique également comment accéder aux états inclus dans le pack de contenu, et fournit des informations sur le modèle de données et les entités qui permettent de créer le pack de contenu."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 263934
ms.assetid: 38e6827b-0819-473c-bc47-821a1ec482b8
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 4b12a2c8983cf7bef770417f76df324293f06fb2
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="recruiting-power-bi-content"></a>Recrutement du contenu Power BI

[!include[banner](../includes/banner.md)]


Cette rubrique décrit le contenu Recrutement Power BI dans Dynamics 365 for Operations. Elle explique également comment accéder aux états inclus dans le pack de contenu, et fournit des informations sur le modèle de données et les entités qui permettent de créer le pack de contenu.

<a name="accessing-the-content-pack"></a>Accès au pack de contenu
--------------------------

Vous trouverez le pack de contenu Recrutement dans la bibliothèque Actifs partagés de Microsoft Dynamics Lifecycle Services (LCS). Pour savoir comment télécharger le pack de contenu et le connecter à vos données Microsoft Dynamics 365 for Operations, voir [Contenu Power BI dans LCS de Microsoft et de vos partenaires](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>États inclus dans le pack de contenu
Après avoir connecté le pack de contenu à vos données Dynamics 365 for Operations, les données de votre organisation s'affichent dans les états. Si vous n'avez jamais utilisé Microsoft Power BI auparavant, consultez la [Page d'apprentissage guidé pour Power BI](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData) pour en savoir plus. Les états inclus dans le pack de contenu contiennent des graphiques et des tables qui fournissent des informations supplémentaires. Le tableau suivant décrit ces états.

| Etat                       | Sommaire                                                                                               |
|------------------------------|--------------------------------------------------------------------------------------------------------|
| Analyse du candidat           | Candidats par tâche, sources de candidat, candidats par emplacement et nombre total de candidats           |
| Statut du candidat             | Candidats par type et statut, et statut du candidat                                                    |
| Démographie des candidats       | Candidats par âge et sexe, et candidats par niveau et statut de formation                             |
| Analyse de recrutement          | Taux net d'embauche, jours moyens d'embauche, pourcentage de mauvaises embauches, et coûts de recrutement                    |
| Analyse d'un projet de recrutement | Numéro de projets de recrutement, d'ouvertures par projet de recrutement, et de candidats par projet de recrutement |

Vous pouvez filtrer les graphiques et les vignettes affichés sur ces états et les épingler au tableau de bord. Pour savoir comment filtrer et épingler dans Power BI, voir [Créer et configurer un tableau de bord](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités
Les données Dynamics 365 for Operations sont utilisées pour remplir les états du pack de contenu Recrutement. Le tableau suivant indique les entités sur lesquelles le pack de contenu est basé.

| Entité                          | Sommaire                                                         | Relations avec d'autres entités                                                                                                                                                                                                                 |
|---------------------------------|------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Recruiting\_Applicant           | Candidats, candidats engagés, Taux net d'embauche et coûts          | Recruiting\_ApplicantName Recruiting\_Company Recruiting\_CalendarOffset Recuriting\_Date Recruiting\_GeographicLocation Recruiting\_Demographics Recruiting\_Job Recruiting\_Media Recruiting\_RecruitmentProject                                |
| Recruiting\_ApplicantName       | Prénom, nom et nom complet du candidat                   | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_CalendarOffset      | Décalages de calendrier pour diviser les états                                | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_Company             | Sociétés selon lesquelles filtrer les états                                   | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_Date                | Jours, semaines, mois et années                                   | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_Demographics        | Date de naissance, sexe, origine ethnique et état civil         | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_EmployedApplicant   | Candidat, performances, date de début et type de candidat           | Recruiting\_Company Recruiting\_CalendarOffset Recruiting\_Date Recruiting\_GeographicLocation Recruiting\_ApplicantName Recruiting\_Employment Recruiting\_Performance Recruiting\_Job Recruiting\_Media Recruiting\_RecruitmentProject          |
| Recruiting\_Employment          | Date de début, date de fin et date de transition                        | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_GeographicLocation  | Ville, département, code postal et région ou province                 | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_Job                 | Fonction, type et titre                                        | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_Media               | Source de candidats                                             | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_Performance         | Classement, description et modèle de classement                            | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_RecruitmentProject  | Description, statut du projet, et ouvertures de projet                | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_TerminatedApplicant | Candidats terminés, motif, performances et date de fin de contrat | Recruiting\_Company Recruiting\_CalendarOffset Recruiting\_Date Recruiting\_GeographicLocation Recruiting\_Performance Recruiting\_Demographics Recruiting\_Employment Recruiting\_Media Recruiting\_RecruitmentProject Recruiting\_ApplicantName |

Ces entités ont été utilisées pour créer des mesures calculées. Ces entités calculées sont ensuite utilisées pour calculer les indicateurs de performance clés (KPI) et les états utilisés dans le pack de contenu. Si vous souhaitez inclure des calculs supplémentaires dans vos rapports et tableaux de bord, vous pouvez télécharger et modifier le fichier Recruiting.pbix de LCS. Ce fichier est le modèle de données par défaut utilisé pour créer le pack de contenu. Une fois que vous avez apporté vos modifications, vous pouvez créer un pack de contenu et un tableau de bord de l'organisation contenant les informations que vous avez ajoutées.

## <a name="additional-resources"></a>Ressources supplémentaires
Voici quelques liens utiles liés aux entités et à la création du contenu Power BI :

-   [Entités de données](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Création de packs de contenu d'organisation](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modélisation de données à l'aide de Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Ajout de vignettes Power BI aux espaces de travail](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)





