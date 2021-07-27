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
ms.openlocfilehash: 842c459acd8b5e1a8b6074243b3afa18dc6a13c5
ms.sourcegitcommit: 89bb2a7f402deed32998eddc1e56e75250e3d15e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314235"
---
# <a name="payroll-position-job"></a>Tâche du poste de paie

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’entité de postes de paie pour Dynamics 365 Human Resources.

### <a name="description"></a>Description 

Cette entité fournit la relation entre un poste et un emploi pour un plan de rémunération fixe.

Nom physique : mshr_payrollpositionjobentity.

## <a name="properties"></a>Propriétés

| Propriété<br>**Nom physique**<br>**_Type_** | Cas d’emploi | Description  |
| --- | --- | --- |
| **ID tâche**<br>mshr_jobid<br>*Chaîne* | Lecture seule<br>Requis |ID de la tâche. |
| **Valide à partir du**<br>mshr_validto<br>*Décalage de date et heure* | Lecture seule <br>Requis | Date à partir de laquelle la relation entre le poste et la tâche sont valides. |
| **Valide jusqu’au**<br>mshr_validto<br>*Décalage de date et heure* | Lecture seule <br>Requis | Date jusqu’à laquelle la relation entre le poste et la tâche sont valides.  |
| **ID poste**<br>mshr_positionid<br>*Chaîne* | Lecture seule<br>Requis | ID du poste. |
| **Champ principal**<br>mshr_primaryfield<br>*Chaîne* | Requis<br>Généré par le système |  |
| **Valeur d’ID du poste**<br>_mshr_fk_positionjob_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_PayrollPositionJobEntity de mshr_payrollpositionjobentity |ID du travail associé au poste.|
| **Valeur de l’ID du régime de rémunération fixe**<br>_mshr_fk_fixedcompplan_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_FixedCompPlan_id de mshr_payrollfixedcompensationplanentity  | ID du régime de rémunération fixe associé au poste. |
| **ID de l’entité Tâche du poste de paie**<br>mshr_payrollpositionjobentityid<br>*Guid* | Requis<br>Généré par le système. | Valeur GUID générée par le système pour identifier la tâche de manière unique.  |

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
