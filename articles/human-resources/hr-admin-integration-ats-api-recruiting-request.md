---
title: Demande de recrutement
description: Cette rubrique décrit l'entité Demande de recrutement pour Dynamics 365 Human Resources.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 572ee0755e331d19b41442e3614effb92db95a92
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125423"
---
# <a name="recruiting-request"></a>Demande de recrutement

Cette rubrique décrit l'entité Demande de recrutement pour Dynamics 365 Human Resources.

Nom physique : mshr_hcmrecruitingrequestentity

### <a name="description"></a>Description 

Décrit une demande de recrutement pour un emploi.

### <a name="json-representation"></a>Représentation JSON

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_hiringmanagerpersonnelnumber": "String",
    "mshr_recruiterpartynumber": "String",
    "mshr_status": Int,
    "mshr_description": "String",
    "mshr_recruitingrequestlocationid": "String",
    "mshr_comments": "String",
    "mshr_jobid": "String",
    "mshr_titleid": "String",
    "mshr_jobfunctionid": "String",
    "mshr_defaultfulltimeequivalency": Decimal,
    "mshr_regulatoryjobcategory": Int,
    "mshr_jobtypeid": "String",
    "mshr_exemptstatus": Int,
    "mshr_estimatedstartdate": "Date",
    "mshr_externaldescription": "String",
    "mshr_compensationlevelid": "String",
    "mshr_compensationlowthreshold": Decimal,
    "mshr_compensationcontrolpoint": Decimal,
    "mshr_compensationhighthreshold": Decimal,
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "_mshr_fk_hiringmanager_id_value": "Guid",
    "_mshr_fk_recruiter_id_value": "Guid",
    "_mshr_fk_job_id_value": "Guid",
    "_mshr_fk_title_id_value": "Guid",
    "_mshr_fk_jobtype_id_value": "Guid",
    "_mshr_fk_compensationlevel_id_value": "Guid",
    "mshr_hcmrecruitingrequestentityid": "Guid",
    "_mshr_fk_recruitingrequestlocation_id_value": “Guid”
}
```

### <a name="properties"></a>Propriétés

| Propriété<br>**Nom physique**<br>**_Type_** | Cas d’emploi | Description  |
| --- | --- | --- |
| **ID demande de recrutement**<br>mshr_recruitingrequestid<br>*Chaîne* | Lecture seule<br>Requis<br>Généré par le système | Identifiant unique lisible par l'utilisateur pour la demande affichée dans l'application HR. Souche de numéros. |
| **ID de l'entité Demande de recrutement**<br>mshr_hcmrecruitingrequestentityid<br>*GUID* | Lecture seule<br>Requis<br>Généré par le système | Valeur GUID générée par le système pour identifier la demande de recrutement de manière unique. |
| **ID zone de données**<br>mshr_dataareaid<br>*Chaîne* | Lecture/écriture<br>Facultatif<br> | Spécifie l'entité juridique (société) pour la demande de recrutement. |
| **Valeur de l'ID zone de données**<br>_mshr_dataareaid_id_value<br>*GUID*<br> | Lecture seule<br>Facultatif<br>Clé étrangère : cdm_companyid de l'entité cdm_company entity | Valeur GUID générée par le système identifiant l'entité juridique (société) pour la demande de recrutement. |
| **Matricule du responsable de l’embauche**<br>mshr_hiringmanagerpersonnelnumber<br>*Chaîne* | Lecture/écriture<br>Facultatif | Matricule du responsable du recrutement associé à cette demande de recrutement. |
| **Valeur de l'ID du responsable du recrutement**<br>_mshr_fk_hiringmanager_id_value<br>*GUID* | Lecture seule<br>Facultatif<br>Clé étrangère : mshr_hcmworkerbaseentityid de l'entité mshr_hcmworkerbaseentity | Valeur GUID générée par le système pour identifier le responsable associé à la demande de recrutement. |
| **Numéro tiers du recruteur**<br>mshr_recruiterpartynumber<br>*Chaîne* | Lecture/écriture<br>Facultatif | Le numéro tiers (personne) du recruteur sélectionné pour la demande. |
| **Valeur de l'identifiant du recruteur**<br>_mshr_fk_recruiter_id_value<br>*GUID* | Lecture seule<br>Facultatif<br>Clé étrangère : mshr_dirpersonentityid de l'entité mshr_dirpersonentity | Valeur GUID générée par le système pour identifier le recruteur associé à la demande de recrutement. |
| **État**<br>mshr_status<br>Jeu d'options *RecruitingRequestStatus* | Lecture/écriture<br>Requis<br> | Indique le statut de la demande de recrutement. |
| **Description**<br>mshr_description<br>*Chaîne* | Lecture/écriture<br>Requis | Décrit la demande. |
| **ID emplacement de la demande de recrutement**<br>mshr_recruitingrequestlocationid<br>*Chaîne* | Lecture/écriture<br>Facultatif | Identificateur unique lisible par l'utilisateur de l'emplacement de la tâche associée à cette demande. |
| **Valeur de l'ID de l'emplacement de recrutement**<br>_mshr_fk_recruitinglocation_id_value<br>*GUID* | Lecture seule<br>Facultatif<br>Clé étrangère : mshr_hcmrecruitingrequestlocationentityid de l'entité mshr_hcmrecruitingrequestlocationentity | Valeur GUID générée par le système pour identifier l'emplacement de la demande de recrutement sélectionné pour la demande. |
| **Commentaires**<br>mshr_comments<br>*Chaîne* | Lecture/écriture<br>Facultatif | Commentaires sur la demande à utiliser par les responsables du recrutement et les recruteurs. |
| **ID tâche**<br>mshr_jobid<br>*Chaîne* | Écriture unique<br>Requis |   Identificateur unique lisible par l'utilisateur de la tâche partagée par tous les postes associés à cette demande. |
| **Valeur de l'ID de tâche**<br>_mshr_fk_job_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_hcmjobentityid de l'entité mshr_hcmjobentity | Identifiant unique généré par le système de la tâche partagée par tous les postes associés à la demande de recrutement. |
| **ID de la fonction**<br>mshr_titleid<br>*Chaîne* | Lecture seule<br>Requis | Identificateur unique lisible par l'utilisateur du poste associé à cette demande. |
| **Valeur de l'ID de la fonction**<br>_mshr_fk_title_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_hcmtitleid de l'entité mshr_hcmtitleentity | Identifiant unique généré par le système de la fonction du poste sélectionné pour la demande de recrutement. |
| **ID de la fonction du poste**<br>mshr_jobfunctionid<br>*Chaîne* | Lecture seule<br>Requis<br>Clé étrangère : mshr_jobfunctionid de l'entité mshr_hcmjobfunctionentity | Identificateur unique lisible par l'utilisateur du poste associé à cette demande. |
| **Équivalence temps plein par défaut**<br>mshr_defaultfulltimeequivalency<br>*Double* | Lecture seule<br>Requis | Valeur équivalente à temps plein pour l'emploi, où 1,0 représente un travailleur à temps plein. |
| **Catégorie d'emploi réglementaire**<br>mshr_regulatoryjobcategory<br>Jeu d'options *RegulatoryJobCategory* | Lecture seule<br>Facultatif | Catégorie d'emploi EEO de la fonction de tâche sélectionnée pour le travail. Valeurs valides incluses dans l'ensemble d'options HcmRegulatoryJobCatetory (mshr_hcmregulatoryjobcategory). |
| **ID de type de poste**<br>mshr_jobtypeid<br>*Chaîne* | Lecture seule<br>Facultatif | Type de tâche associée au poste. Les types de tâche sont des valeurs définies par l'utilisateur, disponibles dans l'entité mshr_hcmjobtypeentity. |
| **Valeur de l'ID du type de tâche**<br>_mshr_fk_jobtype_id_value<br>*GUID* | Lecture seule<br>Facultatif<br>Clé étrangère : mshr_hcmjobtypeentityid de l'entité mshr_hcmjobtypenentity | Identifiant unique généré par le système du type de tâche associée à la tâche de la demande de recrutement. |
| **Statut de l'exemption**<br>mshr_exemptstatus<br>Jeu d'options *JobExemptStatus* | Lecture seule<br>Facultatif | Statut d'exemption FLSA basé sur le type de tâche. |
| **Date de début estimée**<br>mshr_estimatedstartdate<br>*Date* | Lecture/écriture<br>Requis | Estimation de la date à laquelle un candidat commencerait à travailler. |
| **Description externe**<br>mshr_externaldescription<br>*Chaîne* | Lecture/écriture<br>Facultatif | Description du poste côté candidat. | Seuil bas de rémunération<br>mshr_compensationlowthreshold<br>*Double* | Lecture/écriture<br>Facultatif | Limite inférieure du niveau de rémunération. |
| **Point de contrôle de la rémunération**<br>mshr_compensationcontrolpoint<br>*Double* | Lecture/écriture<br>Facultatif | Point de contrôle pour le niveau de rémunération. |
| **Seuil élevé de rémunération**<br>mshr_compensationhighthreshold<br>*Double* | Lecture/écriture<br>Facultatif | Limite supérieure du niveau de rémunération. |
| **Niveau de rémunération**<br>mshr_compensationlevelid<br>*Chaîne* | Lecture/écriture<br>Facultatif | Niveau de rémunération du travail. Un travail peut être configuré avec plusieurs niveaux de rémunération. Cet attribut indique le niveau de rémunération de l'emploi sélectionné pour cette demande. |
| **ID de rémunération du travail**<br>_mshr_fk_jobcompensation_id_value<br>*GUID* | Lecture seule<br>Facultatif<br>Clé étrangère : mshr_hcmjobcompensationentityid de l'entité mshr_hcmjobcompensationentity | Identifiant unique généré par le système pour le niveau de rémunération associé au poste de la demande de recrutement. |

## <a name="see-also"></a>Voir également :

[Introduction à l'API d'intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour une demande de recrutement](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]