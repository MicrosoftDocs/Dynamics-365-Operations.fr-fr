---
title: Tâche du poste de paie
description: Cette rubrique fournit des détails un exemple de requête pour l’entité Tâche du poste de paie dans Dynamics 365 Human Resources.
author: jcart
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c0b70411e6535b22d698545438dcb0b16935e731
ms.sourcegitcommit: 12e26ef25c492e5032260733b50cd642cbd6164d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/28/2021
ms.locfileid: "7559581"
---
# <a name="payroll-position-job"></a>Tâche du poste de paie

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’entité de postes de paie pour Dynamics 365 Human Resources.

### <a name="description"></a>Description 

Cette entité fournit la relation entre un poste et un emploi pour un plan de rémunération fixe.

Nom physique : mshr_payrollpositionjobentity.

## <a name="properties"></a>Propriétés

| Propriété</br>**Nom physique**</br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **ID poste**</br>mshr_positionid</br>*Chaîne* | Lecture seule | ID du poste. |
| **Valide à partir du**</br>mshr_validto</br>*Décalage de date et heure* | Lecture seule | Cette date à partir de laquelle la relation entre le poste et la tâche sont valides. |
| **Valide jusqu’au**</br>mshr_validto</br>*Décalage de date et heure* | Lecture seule | Date jusqu’à laquelle la relation entre le poste et la tâche sont valides. |
| **ID tâche**</br>mshr_jobid</br>*Chaîne* | Lecture seule | ID de la tâche. |
| **Champ principal**</br>mshr_primaryfield</br>*Chaîne* | Généré par le système | Champ principal. |
| **ID de l’entité Tâche du poste de paie**</br>mshr_payrollpositionjobentityid</br>*Guid* | Généré par le système. | Une valeur d'identificateur global unique (GUID) générée par le système pour identifier de manière unique la tâche. |

## <a name="relations"></a>Relations

| Valeur de propriété  | Entité liée | Propriété de navigation | Type de collection |
| --- | --- | --- | --- |
| _mshr_fk_fixedcompplan_id_value | mshr_payrollfixedcompensationplanentity | mshr_FK_FixedCompPlan_id | mshr_FK_PayrollFixedCompensationPlanEntity_Job |
| _mshr_fk_jobdetail_id_value | mshr_hcmjobdetailentity | mshr_FK_JobDetail_id | Non applicable |
| _mshr_fk_payroll_id_value | mshr_payrollpositionentity | mshr_FK_Payroll_id | mshr_FK_PayrollPositionEntity_Job |

## <a name="example-query"></a>Exemple de requête

**Demande**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionjobentities?$filter=mshr_positionid eq '000276'
```

**Réponse**

```json
{
    "mshr_positionid": "000276",
    "mshr_validfrom": "2016-07-06T18:11:33Z",
    "mshr_validto": "2154-12-31T23:59:59Z",
    "mshr_jobid": "Accountant",
    "mshr_primaryfield": "000276 | Accountant | 7/6/2016 06:11:33 pm",
    "_mshr_fk_jobdetail_id_value": "00000b8d-0000-0000-b0ff-004105000000",
    "_mshr_fk_fixedcompplan_id_value": "0000058a-0000-0000-d5ff-004105000000",
    "_mshr_fk_payroll_id_value": "00000427-0000-0000-df00-014105000000",
    "mshr_payrollpositionjobentityid": "00000906-0000-0000-df00-014105000000"
}
```

## <a name="see-also"></a>Voir également :

[Présentation de l’API d’intégration de la paie](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
