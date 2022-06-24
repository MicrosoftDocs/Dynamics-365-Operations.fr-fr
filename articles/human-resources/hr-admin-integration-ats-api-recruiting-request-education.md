---
title: Formation pour la demande de recrutement
description: Cet article décrit l’entité Formation pour la demande de recrutement pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: bcdb5e2cc61ce551af21401ea34d8e85bc21fc6c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893843"
---
# <a name="recruiting-request-education"></a>Formation pour la demande de recrutement


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article décrit l’entité Formation pour la demande de recrutement pour Dynamics 365 Human Resources.

Nom physique : mshr_hcmrecruitingrequesteducationentity

### <a name="description"></a>Description

Décrit les exigences en matière de formation pour une demande de recrutement.

### <a name="json-representation"></a>Représentation JSON

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_educationdisciplineid": "String",
    "mshr_educationdisciplinedescription": "String",
    "mshr_educationlevelid": "String",
    "mshr_educationleveldescription": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_educationdiscipline_id_value": "Guid",
    "_mshr_fk_educationlevel_id_value": "Guid",
    "mshr_hcmrecruitingrequesteducationentityid": "Guid"
}
```

### <a name="properties"></a>Propriétés

| Propriété<br>**Nom physique**<br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **ID de l’entité Formation pour la demande de recrutement**<br>mshr_hcmrecruitingrequesteducationentityid<br>*GUID* | Lecture seule<br>Requis | Identificateur unique généré par le système pour le dossier de formation pour la demande de recrutement. |
| **ID demande de recrutement**<br>mshr_recruitingrequestid<br>*Chaîne* | Écriture unique<br>Requis | Identificateur unique lisible par l’utilisateur de la demande de recrutement associée. |
| **Valeur de l’ID demande de recrutement**<br>_mshr_fk_recruitingrequest_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_hcmrecruitingrequestentityid de l’entité mshr_hcmrecruitingrequestentity | Identificateur unique généré par le système de la demande de recrutement associée. |
| **ID de niveau de formation**<br>mshr_educationlevelid<br>*Chaîne* | Écriture unique<br>Requis | Niveau de formation requis. |
| **Valeur de l’ID de niveau de formation**<br>_mshr_fk_educationlevel_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_hcmeducationlevelentityid de l’entité mshr_hcmeducationlevelentity | Identifiant unique généré par le système du niveau de formation requis. |
| **Description du niveau de formation**<br>mshr_educationleveldescription<br>*Chaîne* | Lecture seule<br>Requis | Description du niveau requis pour la compétence. |
| **ID de discipline de formation**<br>mshr_educationdisciplinedescription<br>*Chaîne* | Écriture unique<br>Requis | Domaine de la discipline de formation. |
| **Valeur de l’ID de discipline de formation**<br>_mshr_fk_educationdiscipline_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_hcmeducationdisciplineentityid de l’entité mshr_hcmeducationdisciplineentity | Identifiant unique généré par le système du domaine de la discipline de formation. |
| **Description de la discipline de formation**<br>mshr_educationdisciplinedescription<br>Chaîne | Lecture seule<br>Requis | Description du domaine de la discipline de formation. |
| **ID zone de données**<br>mshr_dataareaid<br>*Chaîne* | Lecture/écriture<br>Facultatif | Spécifie l’entité juridique (société).|
| **Valeur de l’ID zone de données**<br>_mshr_dataareaid_id_value<br>*GUID* | Lecture seule<br>Facultatif<br>Clé étrangère : cdm_companyid de l’entité cdm_company entity | Valeur GUID générée par le système identifiant l’entité juridique (société). |
| **Champ primaire**<br>mshr_primaryfield<br>*Chaîne* | Lecture seule<br>Requis | Concaténation de la valeur de la demande de recrutement, de l’ID de niveau de formation et de l’ID de discipline de formation comme une autre méthode pour identifier le dossier de manière unique. |

## <a name="see-also"></a>Voir également :

[Introduction à l’API d’intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour une demande de recrutement](hr-admin-integration-ats-api-recruiting-request-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
