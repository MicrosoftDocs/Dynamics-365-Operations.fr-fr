---
title: Candidat à l’embauche
description: Cet article décrit l’entité Candidat à l’embauche pour Dynamics 365 Human Resources.
author: jaredha
ms.date: 12/05/2021
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
ms.openlocfilehash: 7c243bdf81beabe9e1ee429227a6edf4d4864bfb
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831991"
---
# <a name="candidate-to-hire"></a>Candidat à l’embauche


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article décrit l’entité Candidat à l’embauche pour Dynamics 365 Human Resources.

Nom physique : mshr_hcmcandidatetohireentity

## <a name="description"></a>Description

Cette entité fournit les détails du candidat utilisés pour créer un collaborateur dans Dynamics 365 Human Resources. Elle est utilisée pour lire tous les enregistrements de candidats et créer des enregistrements de candidats internes et externes, vous permettant de créer des détails personnels pour le nouveau candidat.

Lorsque vous créez un enregistrement de candidat externe qui sera un nouvel enregistrement dans le système, vous ne devez pas définir de numéro de partie (personne) pour lequel vous publiez un nouvel enregistrement de candidat. Le nouvel enregistrement d’entité de personne est créé avec le nouveau dossier de candidature.

Lorsque vous créez un dossier de candidature interne (une candidature pour le poste qui a déjà un enregistrement d’employé dans l’entreprise), définissez le numéro de partie (personne) de l’enregistrement qui existe déjà pour la personne pour la propriété mshr_partynumber sur l’enregistrement de candidat plutôt que de définir les informations personnelles (telles que le nom, le sexe ou la date de naissance) qui seraient utilisées pour créer un nouvel enregistrement de personne.

## <a name="json-representation"></a>Représentation JSON

```json
        {
            "mshr_candidateid": "String",
            "mshr_partynumber": "String",
            "mshr_partytype": "String",
            "mshr_recruitingrequestid": "String",
            "mshr_positionid": "String",
            "mshr_firstname": "String",
            "mshr_middlename": "String",
            "mshr_lastnameprefix": "String",
            "mshr_lastname": "String",
            "mshr_gender": Int,
            "mshr_birthdate": "Date",
            "mshr_citizenshipcountrycode": "String",
            "mshr_veteranstatusid": "String",
            "mshr_isdisabledveteran": Int,
            "mshr_availabilitydate": "Date",
            "mshr_iswillingtorelocate": Int,
            "mshr_comments": "String",
            "mshr_applicantintegrationresult": Int,
            "mshr_donothirereasoncodeid": "String",
            "mshr_dataareaid": "String",
            "_mshr_dataareaid_id_value": "Guid",
            "_mshr_fk_person_id_value": "Guid",
            "_mshr_fk_recruitingrequest_id_value": "Guid",
            "_mshr_fk_position_id_value": "Guid",
            "mshr_hcmcandidatetohireentityid": "Guid",
            "_mshr_fk_veteranstatus_id_value": "Guid",
            "_mshr_fk_reasoncode_id_value": "Guid",
            "mshr_militaryserviceenddate": "Guid",
            "mshr_militaryservicestartdate": "Guid"
            "mshr_militaryserviceenddate": "Date",
            "mshr_militaryservicestartdate": "Date"
        }
```

## <a name="properties"></a>Propriétés

| Propriété<br>**Nom physique**<br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **ID d’entité du candidat à l’embauche**<br>mshr_hcmcandidatetohireentityid<br>GUID | Lecture seule<br>Requis<br>Généré par le système | Identificateur unique généré par le système pour l’enregistrement d’entité. |
| **ID candidat**<br>mshr_candidateid<br>Chaîne | Lecture seule<br>Requis<br>Généré par le système | Identificateur unique pour l’entité. |
| **Numéro tiers**<br>mshr_partynumber<br>Chaîne | Lecture seule<br>Requis | Le numéro de tiers (personne) du dossier du candidat. |
| **Valeur de l’ID de personne**<br>_mshr_fk_person_id_value<br>GUID | Lecture seule<br>Requis<br>Clé étrangère : mshr_dirpersonentityid de mshr_direpersonentity | Identificateur unique généré par le système pour l’enregistrement de tiers (personne) du candidat. |
| **Type de tiers**<br>mshr_partytype<br>Jeu d’options mshr_dirpartytype | Lecture seule<br>Requis | Le type de tiers de l’enregistrement, tel que défini dans le jeu d’options mshr_dirpartytype. Pour cette entité, le type sera toujours « Personne ». |
| **ID demande de recrutement**<br>mshr_recruitingrequestid<br>Chaîne | Écrire une fois<br>Facultatif | Références à la demande de recrutement remplie par ce candidat. |
| **Valeur de l’ID demande de recrutement**<br>_mshr_fk_recruitingrequest_id_value<br>GUID | Lecture/écriture<br>Facultatif<br>Clé étrangère : mshr_hcmrecruitingrequestentityid de l’entité mshr_hcmrecruitingrequestentity | Identificateur unique généré par le système de la demande de recrutement remplie par ce candidat. |
| **ID poste**<br>mshr_positionid<br>Chaîne | Lecture/écriture<br>Facultatif | L’ID du poste pour lequel le candidat est considéré. |
| **Valeur d’ID de position**<br>_mshr_fk_position_if_value<br>GUID | Lecture seule<br>Facultatif<br>Clé étrangère : mshr_hcmpositionv2entityid of mshr_hcmpositionv2entity | Identificateur généré par le système du poste pour lequel le candidat fait l’objet d’une étude. |
| **Prénom**<br>mshr_firstname<br>Chaîne | Lecture/écriture<br>Requis | Prénom du candidat. |
| **Deuxième prénom**<br>mshr_middlename<br>Chaîne | Lecture/écriture<br>Facultatif | Deuxième prénom du candidat. |
| **Préfixe du nom**<br>mshr_lastnameprefix<br>Chaîne | Lecture/écriture<br>Facultatif | Préfixe du nom du candidat. |
| **Nom**<br>mshr_lastname<br>Chaîne | Lecture/écriture<br>Facultatif | Nom du candidat. |
| **Sexe**<br>mshr_gender<br>Jeu d’options mshr_hcmpersongender | Lecture/écriture<br>Facultatif | Sexe du candidat. |
| **Date de naissance**<br>mshr_birthdate<br>Date et heure | Lecture/écriture<br>Facultatif | La date de naissance du candidat. |
| **Code de pays de citoyenneté**<br>mshr_citizenshipcountrycode<br>Chaîne | Lecture/écriture<br>Facultatif | Spécifie le pays où le candidat a la citoyenneté. Les codes de pays valides sont dans mshr_logisticaddresscountryregionentity. |
| **ID de statut d’ancien combattant**<br>mshr_veteranstatusid<br>Chaîne | Lecture/écriture<br>Facultatif | Indique le statut d’ancien combattant du candidat. |
| **Valeur de l’ID de statut d’ancien combattant**<br>_mshr_fk_veteranstatus_id_value<br>GUID | Lecture seule<br>Facultatif<br>Clé étrangère : mshr_hcmveteranstatusentityid de l’entité mshr_hcmveteranstatusentity | Identificateur unique généré par le système pour le dossier d’entité de statut d’ancien combattant. |
| **Date de début du service militaire**<br>mshr_militaryservicestartdate<br>Date et heure | Lecture/écriture<br>Facultatif | Date de début du service militaire du candidat. |
| **Date de fin du service militaire**<br>mshr_militaryserviceenddate<br>Date et heure | Lecture/écriture<br>Facultatif | Date de fin du service militaire du candidat. |
| **Est un invalide de guerre**<br>mshr_isdisabledveteran<br>Jeu d’options mshr_noyes | Lecture/écriture<br>Facultatif | Indique si le candidat a désactivé le statut d’ancien combattant. |
| **Date de disponibilité**<br>mshr_availabilitydate<br>Date et heure | Lecture/écriture<br>Facultatif | Date la plus proche à laquelle le candidat serait disponible pour travailler. |
| **Déménagement souhaité**<br>mshr_iswillingtorelocate<br>Jeu d’options mshr_noyes | Lecture/écriture<br>Facultatif | Indique si le candidat est prêt à déménager pour le poste. |
| **Commentaires**<br>mshr_comments<br>Chaîne | Lecture/écriture<br>Facultatif | Commentaires à utiliser par le recruteur ou le responsable du recrutement. |
| **Résultat d’intégration de candidature**<br>mshr_applcantintegrationresult<br>Jeu d’options mshr_applicantintegrationresult | Lecture/écriture<br>Requis | Le statut du candidat dans le processus d’embauche lié à l’intégration. |
| **ID du code motif Ne pas embaucher**<br>mshr_donothirereasoncodeid<br>Chaîne | Lecture/écriture<br>Facultatif | Code motif fourni en option lorsque le statut (résultat de l’intégration de l’application) est défini sur « Pas embauché ». |
| **Valeur de l’ID du code motif**<br>_mshr_fk_reasoncode_id_value<br>GUID | Lecture seule<br>Facultatif<br>Clé étrangère : mshr_hcmreasoncodeentityid de l’entité mshr_hcmreasoncodeentity | Identificateur unique généré par le système pour le code motif **Ne pas embaucher**. |
| **ID zone de données**<br>mshr_dataareaid<br>Chaîne | Lecture/écriture<br>Facultatif |  Spécifie l’entité juridique (société). |
| **Valeur de l’ID zone de données**<br>_mshr_dataareaid_id_value<br>GUID | Lecture seule<br>Facultatif<br>Clé étrangère : cdm_companyid de l’entité cdm_company entity | Valeur GUID générée par le système identifiant l’entité juridique (société). |

## <a name="see-also"></a>Voir également :

[Introduction à l’API d’intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour l’entité Candidat à l’embauche](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
