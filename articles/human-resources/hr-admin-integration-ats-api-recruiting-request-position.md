---
title: Poste de la demande de recrutement
description: Cette rubrique décrit l'entité Poste de la demande de recrutement pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: 01d73d390f72343c7498ccbb99838d38be45a19e
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2021
ms.locfileid: "5126024"
---
# <a name="recruiting-request-position"></a>Poste de la demande de recrutement

Cette rubrique décrit l'entité Poste de la demande de recrutement pour Dynamics 365 Human Resources.

Nom physique : mshr_hcmrecruitingrequestpositionentity

### <a name="description"></a>Description 

Décrit le ou les postes à pourvoir pour une demande de recrutement. L'ajout d'un poste à la demande de recrutement est facultatif. Les propriétés du poste sont en lecture seule, car elles doivent être identiques sur la demande de recrutement et sur la fiche de poste. Si des changements de propriétés sont nécessaires, ils doivent être faits sur la fiche de poste avant d'ajouter le poste à la demande de recrutement.

### <a name="json-representation"></a>Représentation JSON
```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_positionid": "String",
    "mshr_description": "String",
    "mshr_positiontypeid": "String",
    "mshr_status": Int,
    "mshr_departmentnumber": "String",
    "mshr_reportstopositionid": "String",
    "mshr_reportstopersonnelnumber": "String",
    "mshr_financialdimension": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_position_id_value": "Guid",
    "_mshr_fk_positiontype_id_value": "Guid",
    "_mshr_fk_department_id_value": "Guid",
    "_mshr_fk_reportstoposition_id_value": "Guid",
    "_mshr_fk_reportstoworker_id_value": "Guid",
    "mshr_hcmrecruitingrequestpositionentityid": "Guid"
}
```

### <a name="properties"></a>Propriétés

| Propriété<br>**Nom physique**<br>**_Type_** | Cas d’emploi | Description  |
| --- | --- | --- |
| **ID de l'entité Poste de la demande de recrutement**<br>mshr_hcmrecruitingrequestpositionentityid<br>*GUID* | Lecture seule<br>Requis |    Identificateur généré par le système pour le dossier du poste de la demande de recrutement. |
| **ID demande de recrutement**<br>mshr_recruitingrequestid<br>*Chaîne* | Écriture unique<br>Requis | Identificateur unique lisible par l'utilisateur de la demande de recrutement. |
| **Valeur de l'ID demande de recrutement**<br>_mshr_fk_recruitingrequest_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_hcmrecruitingrequestentityid de l'entité mshr_hcmrecruitingrequestentity | Identificateur généré par le système pour la demande de recrutement à laquelle le poste est affecté. |
| **ID poste**<br>mshr_positionid<br>*Chaîne* | Écriture unique<br>Requis | Identificateur unique lisible par l'utilisateur pour le poste. |
| **Valeur d'ID de position**<br>_mshr_fk_position_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_hcmpositionv2entityid de l'entité mshr_hcmpositionv2entity | Identifiant généré par le système pour le poste. |
| **Description**<br>mshr_description<br>*Chaîne* | Lecture seule<br>Requis | Description du poste. |
| **ID du type de poste**<br>mshr_positiontypeid<br>*Chaîne* | Lecture seule<br>Facultatif | Identificateur unique lisible par l'utilisateur pour le type de ce poste. |
| **Valeur de l'ID du type de poste**<br>_mshr_fk_positiontype_id_value<br>*GUID* | Lecture seule<br>Facultatif<br>Clé étrangère : mshr_hcmpositiontypeentityid de l'entité mshr_hcmpositiontypeentity | Identificateur unique généré par le système pour le type de ce poste. |
| **État**<br>mshr_status<br>*Jeu d'options RecruitingRequestPositionStatus* | Lecture/écriture<br>Requis | Statut du poste pour la demande de recrutement. |
| **Numéro du département**<br>mshr_departmentnumber<br>*Chaîne* | Lecture seule<br>Facultatif<br> | Numéro du département du poste. |
| **Valeur de l'ID de département**<br>_mshr_fk_department_id_value<br>*GUID* | Lecture seule<br>Facultatif<br>Clé étrangère : mshr_omdepartmententityid de l'entité mshr_omdepartmententity | Identificateur unique généré par le système pour le département du poste. |
| **ID Poste de référence**<br>mshr_reportstopositionid<br>*Chaîne* | Lecture seule<br>Requis | ID lisible par l'utilisateur du poste auquel la personne recrutée est affectée dans la hiérarchie organisationnelle. |
| **Valeur de l'ID Poste de référence**<br>_mshr_fk_reportstoposition_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_hcmpositionv2entityid de l'entité mshr_hcmpositionv2entity | ID généré par le système du poste auquel la personne recrutée est affectée. |
| **Matricule du responsable hiérarchique**<br>mshr_reportstopersonnelnumber<br>*Chaîne* | Lecture seule<br>Requis | ID du collaborateur auquel la personne recrutée sera affectée. |
| **Valeur de l'ID collaborateur du poste de référence**<br>_mshr_fk_reportstoworker_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_hcmworkerbaseentityid de l'entité mshr_hcmworkerbaseentity | ID généré par le système du collaborateur auquel la personne recrutée sera affectée. |
| **Dimension financière**<br>mshr_financialdimension<br>*Chaîne* | Lecture seule<br>Facultatif | Dimension financière (par exemple, le centre de coûts) affectée au poste. La dimension financière est attribuée pour chaque poste par entité juridique. Les centres de coûts définis dans les dimensions sont accessibles via l'entité mshr_dimattributeomcostcenterentity. |
| **ID zone de données**<br>mshr_dataareaid<br>*Chaîne* | Lecture/écriture<br>Facultatif | Spécifie l'entité juridique (société) pour le poste faisant l'objet de la demande de recrutement. |
| **Valeur de l'ID zone de données**<br>_mshr_dataareaid_id_value<br>*GUID* | Lecture seule<br>Facultatif<br>Clé étrangère : cdm_companyid de l'entité cdm_company entity | Valeur GUID générée par le système identifiant l'entité juridique (société) pour le poste faisant l'objet de la demande de recrutement. |
| **Champ primaire**<br>mshr_primaryfield<br>*Chaîne* | Lecture seule<br>Requis | Concaténation de la valeur de la demande de recrutement et de l'ID de poste comme une autre méthode pour identifier le dossier de manière unique. |

## <a name="see-also"></a>Voir également :

[Introduction à l'API d'intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour une demande de recrutement](hr-admin-integration-ats-api-recruiting-request-example-query.md)

