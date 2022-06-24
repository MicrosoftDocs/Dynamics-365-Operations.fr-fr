---
title: Compétence de la personne
description: Cet article décrit l’entité Compétence de la personne pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: 713fde6d05904f96f7b17721e15805e07159cf78
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891319"
---
# <a name="person-skill"></a>Compétence de la personne


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article décrit l’entité Compétence de la personne pour Dynamics 365 Human Resources.

Nom physique : mshr_hcmpersonskillentity

## <a name="description"></a>Description

Cette entité décrit les compétences d’un candidat.

## <a name="json-representation"></a>Représentation JSON

```json
{
    "mshr_certifier": "String",
    "mshr_partynumber": "String",
    "mshr_levelid": "String",
    "mshr_ratinglevelexaminer": "String",
    "mshr_skillid": "String",
    "mshr_ratingid": "String",
    "mshr_leveltype": Int,
    "mshr_yearsofexperience": Decimal,
    "mshr_verified": Int,
    "mshr_leveldate": "Date",
    "mshr_primaryfield": "String",
    "_mshr_fk_certifier_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_ratinglevel_id_value": "Guid",
    "_mshr_fk_ratinglevelexaminer_id_value": "Guid",
    "_mshr_fk_skill_id_value": "Guid",
    "mshr_hcmpersonskillentityid": "Guid"
}
```

## <a name="properties"></a>Propriétés

| Propriété<br>**Nom physique**<br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **ID d’entité Compétence de la personne**<br>mshr_hcmpersonskillentityid<br>*GUID* | Lecture seule<br>Requis | Identificateur unique généré par le système pour l’enregistrement d’entité. |
| **Numéro tiers**<br>mshr_partynumber<br>*Chaîne* | Lecture/écriture<br>Requis |   L’ID de l’enregistrement de tiers (personne) associé. |
| **Valeur de l’ID de personne**<br>_mshr_fk_person_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_dirpersonentityid de l’entité mshr_dirpersonentity | Identificateur généré par le système de l’enregistrement de l’entité de tiers (personne). |
| **Certificateur**<br>mshr_certifier<br>*Chaîne* | Lecture/écriture<br>Facultatif | Le matricule du collaborateur qui a certifié cette compétence. |
| **Valeur de l’ID certificateur**<br>_mshr_fk_certifier_id_value<br>*GUID* | Lecture seule<br>Facultatif<br>Clé étrangère : mshr_hcmworkerentityid de mshr_hcmworkerentity | Identificateur unique généré par le système du dossier du collaborateur qui a certifié la compétence. |
| **ID de compétence**<br>mshr_skillid<br>*Chaîne* | Lecture/écriture<br>Requis | Identifiant de la compétence définie dans Human Resources. |
| **Valeur de l’ID de compétence**<br>_mshr_fk_skill_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_hcmskillentityid de l’entité mshr_hcmskillentity | Identificateur généré par le système pour la compétence sélectionnée. |
| **Années d’expérience**<br>mshr_yearsofexperience<br>*Décimal* | Lecture/écriture<br>Facultatif | Années d’expérience du candidat dans cette compétence. |
| **ID de classement**<br>mshr_ratingid<br>*Chaîne* | Lecture/écriture<br>Requis | Type d’échelle de classement. Pour cette entité, la valeur est **Compétences**. |
| **Type de niveau**<br>mshr_leveltype<br>*Jeu d’options mshr_hrmskillleveltype* | Lecture/écriture<br>Requis | Une catégorisation du type pour le niveau attribué à la compétence. |
| **ID de niveau**<br>mshr_levelid<br>*Chaîne* | Lecture/écriture<br>Requis | ID du niveau de classement du candidat pour cette compétence. |
| **Valeur de l’ID du niveau de classement**<br>_mshr_fk_ratinglevel_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_hcmratinglevelentityid de l’entité mshr_hcmratinglevelentity | Identificateur généré par le système du niveau de classement. |
| **Date du niveau**<br>mshr_leveldate<br>*DateHeure* | Lecture/écriture<br>Requis | Date à laquelle le candidat a été évalué dans la compétence. |
| **Examinateur du niveau de classement**<br>mshr_ratinglevelexaminer<br>*Chaîne* | Lecture/écriture<br>Facultatif | Matricule du collaborateur qui a évalué le candidat. |
| **Valeur de l’ID de l’examinateur du niveau de classement**<br>_mshr_fk_ratinglevelexaminer_id_value<br>*GUID* | Lecture seule<br>Facultatif<br>Clé étrangère : mshr_hcmworkerentityid de mshr_hcmworkerentity | L’identifiant généré par le système du collaborateur qui a examiné le niveau de compétence du candidat. |
| **Vérifiée**<br>mshr_verified<br>*Jeu d’options mshr_noyes* | Lecture/écriture<br>Requis | Indique si le niveau de compétence a été vérifié. |
| **Champ primaire**<br>mshr_primaryfield<br>*Chaîne* | Lecture seule<br>Requis | Champ à utiliser comme identifiant principal de l’enregistrement d’entité. Combinaison du numéro de tiers, du type de niveau, de l’ID de compétence et de la date du niveau. |

## <a name="see-also"></a>Voir également :

[Introduction à l’API d’intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour l’entité Candidat à l’embauche](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
