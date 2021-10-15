---
title: Régime de rémunération fixe avec paie
description: Cette rubrique fournit des détails un exemple de requête pour l’entité Régime de rémunération fixe dans Dynamics 365 Human Resources.
author: jcart
ms.date: 08/25/2021
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
ms.openlocfilehash: a3cc431307d840d393a454e91f202c07c38d2512
ms.sourcegitcommit: 12e26ef25c492e5032260733b50cd642cbd6164d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/28/2021
ms.locfileid: "7559337"
---
# <a name="payroll-fixed-compensation-plan"></a>Régime de rémunération fixe avec paie

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’entité du plan de rémunération fixe de la paie pour Dynamics 365 Human Resources.

### <a name="description"></a>Description

Cette entité fournit le plan de rémunération fixe attribué pour un poste donné d’un employé.

Nom physique : mshr_payrollfixedcompensationplanentity.

## <a name="properties"></a>Propriétés

| Propriété</br>**Nom physique**</br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **ID plan**</br>mshr_planid</br>*Chaîne* | Lecture seule | Spécifie le régime de rémunération.  |
| **Numéro personnel**</br>mshr_personnelnumber</br>*Chaîne* | Lecture seule | Numéro personnel unique du collaborateur. |
| **Salaire**</br>mshr_payrate</br>*Décimal* | Lecture seule | Taux de rémunération défini dans le régime de rémunération fixe. |
| **ID poste**</br>mshr_positionid</br>*Chaîne* | Lecture seule | ID de poste associé à l’employé et à l’inscription au régime de rémunération fixe. |
| **Valide à partir du**</br>mshr_validfrom</br>*Décalage de date et heure* |  Lecture seule | Date à partir de laquelle les informations relatives à la rémunération fixe sont valides.  |
| **Valide jusqu’au**</br>mshr_validto</br>*Décalage de date et heure* | Lecture seule | Date jusqu’à laquelle les informations relatives à la rémunération fixe sont valides. |
| **Fréquence de paiement**</br>mshr_payfrequency</br>*Chaîne* | Lecture seule | L'identifiant de la [fréquence de rémunération](hr-admin-integration-payroll-api-compensation-pay-frequency.md) pour le taux de rémunération donné. |
| **Devise**</br>mshr_currency</br>*Chaîne* | Lecture seule | La devise définie pour le régime de rémunération fixe. |
| **Entité Régime de rémunération fixe avec paie**</br>mshr_payrollfixedcompensationplanentityid</br>*GUID* | Généré par le système | Valeur GUID générée par le système pour identifier le rémunération fixe de manière unique. |

## <a name="relations"></a>Relations

|Valeur de propriété | Entité liée | Propriété de navigation | Type de collection |
| --- | --- | --- | --- |
| _mshr_fk_employee_id_value | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | mshr_FK_Employee_id | mshr_FK_PayrollEmployeeEntity_FixedCompPlan |
| _mshr_fk_job_id_value | [mshr_payrollpositionjobentity](hr-admin-integration-payroll-api-payroll-position-job.md) | mshr_FK_Job_id | mshr_FK_PayrollPositionJobEntity_FixedCompPlan |
| _mshr_fk_payrollposition_id_value | [mshr_payrollpositionentity](hr-admin-integration-payroll-api-payroll-position.md) | mshr_FK_PayrollPosition_id | mshr_FK_PayrollPositionEntity_FixedCompPlan |
| _mshr_fk_plan_id_value | mshr_hcmcompfixedplantableentity | mshr_FK_Plan_id | - |
| _mshr_fk_variablecompaward_id_value | [mshr_payrollvariablecompensationawardentity](hr-admin-integration-payroll-api-payroll-variable-compensation-plan.md) | mshr_FK_VariableCompAward_id | mshr_FK_PayrollVariableCompensationAwardEntity_FixedComp |

## <a name="example-query"></a>Exemple de requête

**Demande**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollfixedcompensationplanentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

**Réponse**

```json
{
    "mshr_planid": "GradeC",
    "mshr_personnelnumber": "000041",
    "mshr_payrate": 75200,
    "mshr_positionid": "000276",
    "mshr_validfrom": "2011-04-05T00:00:00Z",
    "mshr_validto": "2154-12-31T00:00:00Z",
    "mshr_payfrequency": "Annual",
    "mshr_currency": "USD",
    "_mshr_fk_employee_id_value": "00000d3c-0000-0000-d5ff-004105000000",
    "_mshr_fk_plan_id_value": "0000070c-0000-0000-b328-fef003000000",
    "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
    "mshr_payrollfixedcompensationplanentityid": "0000029f-0000-0000-d5ff-004105000000",
    "_mshr_fk_payroll_id_value": null
}
```

## <a name="see-also"></a>Voir également :

[Présentation de l’API d’intégration de la paie](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
