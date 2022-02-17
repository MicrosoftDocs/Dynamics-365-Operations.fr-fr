---
title: Introduction à l’API d’intégration du système de suivi des candidats
description: Cette rubrique décrit l’API d’intégration du système de suivi des candidats Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e16c781a6e51c57db8ae76dcfe0d28ec709428eb
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8069930"
---
# <a name="applicant-tracking-system-integration-api-introduction"></a>Introduction à l’API d’intégration du système de suivi des candidats


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’API d’intégration du système de suivi des candidats Dynamics 365 Human Resources. Cette API a pour but de permettre des intégrations rationalisées entre Dynamics 365 Human Resources et les ATS partenaires.

![Flux d’intégration ATS.](media/hr-admin-integration-ats-api-introduction-flow.png)

L’expérience intégrée débute dans Human Resources lorsqu’un responsable du recrutement crée une demande de recrutement. Lorsque la demande est activée, l’ATS extrait le détail de la demande pour créer un projet de recrutement. Ensuite, il suit le processus de recrutement pour sélectionner et embaucher un candidat. Enfin, l’ATS complète l’intégration complète en envoyant le dossier du candidat sélectionné dans Human Resources. Le dossier de candidature peut ensuite passer par d’autres validations d’intégration et flux de travail pour créer la fiche de l’employé.

Pour permettre l’intégration, Human Resources a ajouté les composants suivants :

1.  Fonctionnalité pour créer une demande de recrutement.
2.  Un profil de candidat étendu et les flux de travail associés.
3.  Une API d’intégration ouvrant la nouvelle fonctionnalité à l’intégration d’applications.

Pour plus d’informations sur la configuration et l’utilisation de la demande de recrutement et de la fonctionnalité de candidature, voir [Recruter des candidats à un poste](hr-personnel-recruit.md).

## <a name="microsoft-dataverse"></a>Microsoft Dataverse

Cette API repose sur Microsoft Dataverse (auparavant Common Data Service). Toutes les interactions RESTful avec cette API se font via l’API Web Microsoft Dataverse, qui utilise OData. Cette API est un sous-ensemble de l’API Web Dataverse. L’API Web Dataverse définit des caractéristiques telles que l’authentification, les SLA, les lots, le contrôle de la concurrence et la gestion des erreurs.

Pour plus d’informations générales sur l’API Web Microsoft Dataverse :

- [Qu’est-ce que Microsoft Dataverse ?](/powerapps/maker/data-platform/data-platform-intro)
- [Utiliser l’API Web Microsoft Dataverse](/powerapps/developer/data-platform/webapi/overview)
- [Guide du développeur Microsoft Dataverse](/powerapps/developer/data-platform)

La documentation ci-dessus comprend des détails et des conseils pour les développeurs sur l’utilisation de l’API Web Dataverse, comme [gérer l’authentification](/powerapps/developer/data-platform/webapi/authenticate-web-api), [effectuer des opérations](/powerapps/developer/data-platform/webapi/perform-operations-web-api), [ utiliser Postman avec l’API](/powerapps/developer/data-platform/webapi/use-postman-web-api), et [utiliser le suivi des modifications ou des jetons delta](/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems) avec l’API.

### <a name="option-sets"></a>Jeux d’options

Le modèle de données pour l’API d’intégration ATS décrit dans ce document comprend des ensembles d’options qui fournissent des valeurs énumérées associées aux propriétés d’entité. Pour plus de détails sur l’utilisation des jeux d’options dans l’API Web Dataverse, voir [Créer et mettre à jour des ensembles d’options à l’aide de l’API Web](/powerapps/developer/data-platform/webapi/create-update-optionsets). Des ensembles d’options sont définis pour chaque environnement Dataverse.

### <a name="virtual-tables-for-human-resources-in-dataverse"></a>Tables virtuelles pour Human Resources dans Dataverse

Les points de terminaison de l’API d’intégration ATS utilisent les capacités de la plateforme de table virtuelle de Microsoft Dataverse. Par défaut, les tables virtuelles et leurs points de terminaison d’API associés ne sont pas déployés pour les environnements Human Resources, ce qui permet aux organisations de déterminer quels points de terminaison OData seront exposés pour l’environnement. Pour utiliser l’API, les tables virtuelles des entités Ressources humaines doivent être générées pour l’environnement. 

Pour plus d’informations sur la génération des tables virtuelles pour l’API, consultez [Configurer les tables virtuelles Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md).

## <a name="data-model"></a>Modèle de données

Le modèle de données est centré autour de deux entités principales :

- **RecruitingRequest** représente une demande adressée à un ATS pour recruter un ou plusieurs candidats. Pour obtenir un exemple de requête, voir [Exemple de requête pour une demande de recrutement](hr-admin-integration-ats-api-recruiting-request-example-query.md).
- **CandidateToHire** représente les détails d’un candidat qui a accepté une offre de poste. **Personne** représente l’individu qui est le candidat. Une personne peut avoir plusieurs rôles dans l’entreprise, tels que candidat, travailleur, employé ou sous-traitant. Pour un exemple de requête, voir [Exemple de requête pour l’entité Candidat à l’embauche](hr-admin-integration-ats-api-candidate-to-hire-example-query.md).

Le diagramme suivant illustre les relations au sein de l’API. Plusieurs types ont des clés étrangères vers d’autres entités préexistantes dans Human Resources qui ne sont pas illustrées ici. Ce document fournit des informations sur les entités spécifiques aux scénarios d’intégration de recrutement. Cependant, il existe de nombreuses autres entités dans l’API Web Dataverse pour Dynamics 365 Human Resources qui peuvent également être pertinentes pour votre intégration. Par exemple, vous pouvez également avoir besoin de détails sur les travailleurs, les emplois, les postes ou d’autres entités non définies ici. Beaucoup de ces entités sont référencées dans des relations de clé étrangère ou des propriétés de navigation.

![Modèle de données de l’API d’intégration ATS.](media/hr-admin-integration-ats-api-data-model.png)

## <a name="recruiting-request-and-related-entities-and-option-sets"></a>Demande de recrutement et entités et ensembles d’options associés

Exemple de requête : 

- [Exemple de requête pour une demande de recrutement](hr-admin-integration-ats-api-recruiting-request-example-query.md)

Entités :

- [Demande de recrutement](hr-admin-integration-ats-api-recruiting-request.md)
- [Poste de la demande de recrutement](hr-admin-integration-ats-api-recruiting-request-position.md)
- [Compétence de la demande de recrutement](hr-admin-integration-ats-api-recruiting-request-skill.md)
- [Formation de la demande de recrutement](hr-admin-integration-ats-api-recruiting-request-education.md)
- [Emplacement de la demande de recrutement](hr-admin-integration-ats-api-recruiting-request-location.md)

Jeux d’options :

- [Statut d’exonération d’un travail](hr-admin-integration-ats-api-job-exempt-status.md)
- [Statut du poste de demande de recrutement](hr-admin-integration-ats-api-recruiting-request-position-status.md)
- [Statut de la demande de recrutement](hr-admin-integration-ats-api-recruiting-request-status.md)
- [Catégorie d’emploi réglementaire](hr-admin-integration-ats-api-regulatory-job-category.md)

## <a name="candidate-to-hire-and-related-entities-and-option-sets"></a>Candidat à l’embauche et entités connexes et ensembles d’options

Exemple de requête :

- [Exemple de requête pour l’entité Candidat à l’embauche](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

Entités :

- [Candidat à l’embauche](hr-admin-integration-ats-api-candidate-to-hire.md)
- [Personne](hr-admin-integration-ats-api-person.md)
- [Formation de la personne](hr-admin-integration-ats-api-person-education.md)
- [Expérience professionnelle de la personne](hr-admin-integration-ats-api-person-professional-experience.md)
- [Adresse de la personne](hr-admin-integration-ats-api-person-address.md)
- [Contact du tiers](hr-admin-integration-ats-api-party-contact.md)
- [Compétence de la personne](hr-admin-integration-ats-api-person-skill.md)
- [Niveau de classement](hr-admin-integration-ats-api-rating-level.md)
- [Certificat de la personne](hr-admin-integration-ats-api-person-certificate.md)
- [Type de certificat](hr-admin-integration-ats-api-certificate-type.md)
- [Présélection](hr-admin-integration-ats-api-person-screening.md)
- [Types de présélection](hr-admin-integration-ats-api-screening-types.md)
- [Numéro d’identification de la personne](hr-admin-integration-ats-api-person-identification-number.md)

Jeux d’options :

- [Résultat de l’intégration du candidat](hr-admin-integration-ats-api-applicant-integration-result.md)
- [Vide Oui Non](hr-admin-integration-ats-api-blank-yes-no.md)
- [État d’achèvement](hr-admin-integration-ats-api-completion-status.md)
- [Type de contact](hr-admin-integration-ats-api-contact-type.md)
- [Base des crédits de formation](hr-admin-integration-ats-api-education-credit-basis.md)
- [Sexe](hr-admin-integration-ats-api-gender.md)
- [Situation de famille](hr-admin-integration-ats-api-marital-status.md)
- [Mois de l’année](hr-admin-integration-ats-api-months-of-year.md)
- [Non Oui](hr-admin-integration-ats-api-no-yes.md)
- [Unité de période](hr-admin-integration-ats-api-period-unit.md)
- [Fréquence de présélection](hr-admin-integration-ats-api-screening-frequency.md)
- [Date de début pour le calcul de la fréquence de présélection](hr-admin-integration-ats-api-screening-frequency-generate-from.md)
- [Type de niveau de compétence](hr-admin-integration-ats-api-skill-level-type.md)

## <a name="see-also"></a>Voir également :

[Recruter des candidats à un poste](hr-personnel-recruit.md)<br>
[Qu’est-ce que Microsoft Dataverse ?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Utiliser l’API Web Microsoft Dataverse](/powerapps/developer/data-platform/webapi/overview)<br>
[Créer et mettre à jour des ensembles d’options à l’aide de l’API Web](/powerapps/developer/data-platform/webapi/create-update-optionsets)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
