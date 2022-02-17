---
title: Formation de la personne
description: Cette rubrique décrit l’entité Formation de la personne pour Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6334467de488ed24ce684a2a059a5ffd0cf04959
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8064964"
---
# <a name="person-education"></a>Formation de la personne


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’entité Formation de la personne pour Dynamics 365 Human Resources.

Nom physique : mshr_hcmpersoneducationentity

## <a name="description"></a>Description

Cette entité contient l’historique de formation du candidat. La formation est liée au dossier du candidat, ce qui permet de l’associer à toute autre fonction créée en plus de ce dossier du candidat (collaborateur, entrepreneur, etc.)

## <a name="json-representation"></a>Représentation JSON

```json
{
    "mshr_creditbasis": Int,
    "mshr_creditscompleted": Decimal,
    "mshr_creditsearned": Decimal,
    "mshr_creditsneeded": Decimal,
    "mshr_description": "String",
    "mshr_duration": Decimal,
    "mshr_durationunit": Int,
    "mshr_educationdisciplineid": "String",
    "mshr_educationinstitutionid": "String",
    "mshr_educationlevelid": "String",
    "mshr_enddate": "Date",
    "mshr_gradepointaverage": Decimal,
    "mshr_gradescale": "String",
    "mshr_notes": "String",
    "mshr_secondaryemphasis": "String",
    "mshr_startdate": "Date",
    "mshr_partynumber": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_educationdiscipline_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_educationinstitution_id_value": "Guid",
    "_mshr_fk_educationlevel_id_value": "Guid",
    "mshr_hcmpersoneducationentityid": "Guid"
}
```

## <a name="properties"></a>Propriétés

| Propriété<br>**Nom physique**<br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **ID d’entité de formation de la personne**<br>mshr_hcmpersoneducationentityid<br>*GUID* | Lecture seule<br>Requis | Identificateur unique généré par le système pour le dossier d’entité de formation de la personne. |
| **Numéro tiers**<br>mshr_partynumber<br>*Chaîne* | Lecture/écriture<br>Requis | Identificateur unique du dossier du tiers (personne) pour le candidat. |
| **Valeur de l’ID de personne**<br>_mshr_fk_person_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_dirpersonentityid de l’entité mshr_dirpersonentity | Identificateur unique généré par le système pour le dossier du candidat. |
| **Base de crédit**<br>mshr_creditbasis<br>*Jeu d’options mshr_hcmeducationcreditbasis* | Lecture/écriture<br>Facultatif | Base de crédit du niveau d’étude. |
| **Crédits effectués**<br>mshr_creditscompleted<br>*Décimal* | Lecture/écriture<br>Facultatif | Le nombre de crédits obtenus pour la formation. |
| **Crédits obtenus**<br>mshr_creditsearned<br>*Décimal* | Lecture/écriture<br>Facultatif | Nombre de crédits gagnés pour le dossier de formation pour un diplôme en cours. |
| **Crédits nécessaires**<br>mshr_creditsneeded<br>*Décimal* | Lecture/écriture<br>Facultatif | Nombre de crédits requis pour un diplôme en cours. |
| **Description**<br>mshr_description<br>*Chaîne* | Lecture/écriture<br>Facultatif | Description du diplôme du candidat. |
| **ID de niveau de formation**<br>mshr_educationlevelid<br>*Chaîne* | Lecture/écriture<br>Facultatif | ID du niveau de formation. | 
| **Valeur de l’ID du niveau de formation**<br>_mshr_fk_educationlevel_id_value<br>*GUID* | Lecture seule<br>Facultatif<br>Clé étrangère : mshr_hcmeducationdegreeentityid de l’entité mshr_hcmeducationdegreeentity | Identificateur généré par le système pour le dossier de formation. Cet identifiant fournit les diplômes et les niveaux de formation définis pour l’organisation. |
| **ID de discipline de formation**<br>mshr_educationdisciplineid<br>*Chaîne* | Lecture/écriture<br>Requis<br>Clé étrangère : EducationDiscipline | ID de la discipline de formation. |
| **Valeur de l’ID de discipline de formation**<br>_mshr_fk_educationdiscipline_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_hcmeducationdisciplineentityid de l’entité mshr_hcmeducationdisciplineentity | Identificateur unique généré par le système de la discipline de formation pour le dossier de formation. |
| **Spécialisation secondaire**<br>mshr_secondaryemphasis<br>*Chaîne* | Lecture/écriture<br>Facultatif | Spécialisation secondaire du diplôme obtenu. |
| **ID de l’établissement d’enseignement**<br>mshr_educationinstitutionid<br>*Chaîne* | Lecture/écriture<br>Facultatif | L’identifiant de l’établissement d’enseignement fréquenté. |
| **Valeur de l’ID de l’établissement d’enseignement**<br>_mshr_fk_educationinstitution_id_value<br>*GUID* | Lecture seule<br>Facultatif<br>Clé étrangère : mshr_hcmeducationinstitutionentityid de l’entité mshr_hcmeducationinstitutionentity | Identifiant généré par le système de l’établissement d’enseignement. |
| **Date de début**<br>mshr_startdate<br>*DateHeure* | Lecture/écriture<br>Facultatif | Date de début de la formation pour le diplôme obtenu. |
| **Date de fin**<br>mshr_enddate<br>*DateHeure* | Lecture/écriture<br>Requis | Date à laquelle les informations d’identification ont été délivrées. |
| **Durée**<br>mshr_duration<br>*Décimal* | Lecture/écriture<br>Facultatif | La durée du dossier de formation. |
| **Unité de durée**<br>mshr_durationunit<br>*Jeu d’options mshr_periodunit* | Lecture/écriture<br>Facultatif | Unité de temps associée à la durée du dossier de formation. |
| **Moyenne pondérée cumulative**<br>mshr_gradepointaverage<br>*Décimal* | Lecture/écriture<br>Facultatif | Moyenne pondérée obtenue pour le diplôme. |
| **Échelle de qualité**<br>mshr_gradescale<br>*Chaîne* | Lecture/écriture<br>Facultatif | Échelle utilisée pour la moyenne pondérée. |
| **Notes**<br>mshr_notes<br>*Chaîne* | Lecture/écriture<br>Facultatif | Notes à l’intention du recruteur ou du responsable du recrutement. |
| **Champ primaire**<br>mshr_primaryfield<br>*Chaîne* | Lecture seule<br>Requis | Champ utilisé comme autre identifiant principal de l’enregistrement d’entité. Combinaison du numéro de tiers, de l’ID de discipline de formation, de l’ID de l’établissement d’enseignement et de l’ID du niveau de formation. |

## <a name="see-also"></a>Voir également :

[Introduction à l’API d’intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour l’entité Candidat à l’embauche](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
