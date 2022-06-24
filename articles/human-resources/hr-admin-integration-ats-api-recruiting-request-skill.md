---
title: Compétence de la demande de recrutement
description: Cet article décrit l’entité Compétence de la demande de recrutement pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: b17bbdfbc977112344302deada085681ceca9bb6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856394"
---
# <a name="recruiting-request-skill"></a>Compétence de la demande de recrutement


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article décrit l’entité Compétence de la demande de recrutement pour Dynamics 365 Human Resources.

Nom physique : mshr_hcmrecruitingrequestskillentity

### <a name="description"></a>Description

Décrit les exigences en matière de compétence pour une demande de recrutement.

### <a name="json-representation"></a>Représentation JSON

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_skillid": "String",
    "mshr_skilldescription": "String",
    "mshr_ratinglevelid": "String",
    "mshr_ratingmodelid": "String",
    "mshr_ratingleveldescription": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_skill_id_value": "Guid",
    "_mshr_fk_ratinglevel_id_value": "Guid",
    "_mshr_fk_ratingmodel_id_value": "Guid",
    "mshr_hcmrecruitingrequestskillentityid": "Guid"
}
```

### <a name="properties"></a>Propriétés

| Propriété<br>**Nom physique**<br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **ID de l’entité Compétence de la demande de recrutement**<br>mshr_hcmrecruitingrequestskillentityid<br>*GUID* | Lecture seule<br>Requis | Identificateur unique généré par le système pour le dossier **Compétence de la demande de recrutement**. |
| **ID demande de recrutement**<br>mshr_recruitingrequestid<br>*Chaîne* | Écriture unique<br>Requis | Identificateur unique lisible par l’utilisateur de la demande de recrutement associée. |
| **Valeur de l’ID demande de recrutement**<br>_mshr_fk_recruitingrequest_id_value<br>*GUID* | Lecture seule<br>Requis<br> Clé étrangère : mshr_hcmrecruitingrequestentityid de l’entité mshr_hcmrecruitingrequestentity | Identificateur unique généré par le système de la demande de recrutement associée. |
| **ID de compétence**<br>mshr_skillid<br>*Chaîne*<br> | Écriture unique<br>Requis | Identificateur unique lisible par l’utilisateur de la compétence requise. |
| **Valeur de l’ID de compétence**<br>_mshr_fk_skill_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_hcmskillentityid de l’entité mshr_hcmskillentity | Identifiant unique généré par le système de la compétence requise. |
| **ID de niveau de classement**<br>mshr_ratinglevelid<br>*Chaîne* | Écriture unique<br>Facultatif | Valeur du niveau de compétence requis sélectionné pour l’emploi, en fonction du modèle de notation attribué à la compétence. |
| **Valeur de l’ID du niveau de classement**<br>_mshr_fk_ratinglevel_id_value<br>*GUID* | Lecture seule<br>Facultatif<br>Clé étrangère : mshr_hcmratinglevelentityid de l’entité mshr_hcmratinglevelentity | Identificateur unique généré par le système pour le niveau. |
| **Description des compétences**<br>mshr_skilldescription<br>*Chaîne* | Lecture seule<br>Requis | Description des compétences. |
| **Description du niveau de classement**<br>mshr_ratingleveldescription<br>*Chaîne* | Lecture seule<br>Facultatif | Description du niveau de compétence sélectionné. |
| **ID zone de données**<br>mshr_dataareaid<br>*Chaîne* | Lecture/écriture<br>Facultatif | Spécifie l’entité juridique (société). |
| **Valeur de l’ID zone de données**<br>_mshr_dataareaid_id_value<br>*GUID* | Lecture seule<br>Facultatif<br>Clé étrangère : cdm_companyid de l’entité cdm_company entity | Valeur GUID générée par le système identifiant l’entité juridique (société). |
| **Champ primaire**<br>mshr_primaryfield<br>*Chaîne* | Lecture seule<br>Requis | Concaténation de la valeur de la demande de recrutement et de l’ID de compétence comme une autre méthode pour identifier le dossier de manière unique. |
| **ID de modèle de classement**<br>mshr_ratingmodelid<br>*Chaîne* | Lecture/écriture<br>Requis | Modèle de classement utilisé pour évaluer la compétence. |
| **Valeur de l’ID du modèle de classement**<br>_mshr_fk_hcmratingmodel_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_hcmratingmodelentityid de l’entité mshr_hcmratingmodelentity | Identifiant unique généré par le système du modèle d’évaluation utilisé pour évaluer la compétence. |

## <a name="see-also"></a>Voir également :

[Introduction à l’API d’intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour une demande de recrutement](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
