---
title: Détails de la paie pour les postes
description: Cette rubrique fournit des détails et un exemple de requête pour l’entité Détails de la paie pour les postes dans Dynamics 365 Human Resources.
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
ms.openlocfilehash: 2bbb234d2f51391ea65e3d6153d6cee250f3c6dc
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8069805"
---
# <a name="payroll-position"></a>Poste de paie


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’entité de postes de paie dans Dynamics 365 Human Resources.

Nom physique : mshr_payrollpositionentity.

### <a name="description"></a>Description 

Cette entité fournit des informations liées au poste pour un employé donné.

Nom physique : mshr_payrollpositionentity.

## <a name="properties"></a>Propriétés

| Propriété</br>**Nom physique**</br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **ID poste**</br>mshr_positionid</br>*Chaîne* | Lecture seule | ID du poste. |
| **ID du cycle de paie**</br>mshr_paycycleid</br>*Chaîne* | Lecture seule | Le cycle de paie qui est défini sur le poste. |
| **Durée annuelle normale**</br>annualregularhours</br>*Décimal* | Lecture seule | Les heures régulières annuelles qui sont définies sur le poste. |
| **Rémunéré par l’entité juridique**</br>paidbylegalentity</br>*Chaîne* | Lecture seule | L’entité juridique qui est définie sur le poste, et responsable de l’émission du paiement. |
| **Valide jusqu’au**</br>validto</br>*Décalage de date et heure* | Lecture seule | La date jusqu’à laquelle les détails du poste sont valides. |
| **Valide à partir du**</br>validfrom</br>*Décalage de date et heure* | Lecture seule | La date à partir de laquelle les détails du poste sont valides. |
| **Champ principal**</br>mshr_primaryfield</br>*Chaîne* | Généré par le système | Champ principal. |
| **ID de l’entité Détails du poste de paie**</br>payrollpositiondetailsentityid</br>*Guid* | Requis</br>Généré par le système. | Une valeur d’identificateur global unique (GUID) générée par le système pour identifier de manière unique le poste. |

## <a name="relations"></a>Relations

| Valeur de propriété  | Entité liée | Propriété de navigation | Type de collection |
| --- | --- | --- | --- |
| _mshr_fk_fixedcompplan_id_value | [mshr_payrollfixedcompensationplanentity](hr-admin-integration-payroll-api-payroll-fixed-compensation-plan.md) | mshr_FK_FixedCompPlan_id | mshr_FK_PayrollFixedCompensationPlanEntity_PayrollPosition |
| _mshr_fk_hcmpositionhierarchy_id_value | mshr_hcmpositionhierarchyentity | mshr_FK_HcmPositionHierarchy_id | Non applicable |
| _mshr_fk_job_id_value | mshr_payrollpositionjobentity | mshr_FK_Job_id | mshr_FK_PayrollPositionJobEntity_Payroll |
| _mshr_fk_positionassignmentv2_id_value | mshr_hcmpositionworkerassignmentv2entity | mshr_FK_PositionAssignmentV2_id | Non applicable |

## <a name="example-query"></a>Exemple de requête

**Demande**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionentities?$filter=mshr_positionid eq @positionid and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@positionid='000276'&@asofdate=2021-04-01
```

**Réponse**

```json
{
    "mshr_positionid": "000276",
    "mshr_paycycleid": "w",
    "mshr_annualregularhours": 3000,
    "mshr_paidbylegalentity": "USMF",
    "mshr_validfrom": "2021-03-14T00:00:00Z",
    "mshr_validto": "2154-12-31T00:00:00Z",
    "mshr_primaryfield": "000276 | 3/14/2021",
    "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
    "_mshr_fk_fixedcompplan_id_value": "0000029f-0000-0000-d5ff-004105000000",
    "mshr_payrollpositionentityid": "00010097-0000-0000-df00-014105000000"
}
```

## <a name="see-also"></a>Voir également :

[Présentation de l’API d’intégration de la paie](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
