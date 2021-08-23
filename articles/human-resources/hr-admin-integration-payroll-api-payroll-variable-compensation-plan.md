---
title: Régime de rémunération variable avec paie
description: Cette rubrique fournit des détails un exemple de requête pour l’entité Régime de rémunération variable dans Dynamics 365 Human Resources.
author: marcelbf
ms.date: 06/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-15
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 96a644bf129de6dd3f78098bcb6415d17058d6decbd7d904a99bb6f050d3a9e0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730440"
---
# <a name="payroll-variable-compensation-plan"></a>Régime de rémunération variable avec paie

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’entité du plan de rémunération variable de la paie pour Dynamics 365 Human Resources.

### <a name="description"></a>Description 

Cette entité fournit le plan de rémunération variable attribué pour un poste donné d’un employé.

Nom physique : mshr_payrollvariablecompensationawardentity.

## <a name="properties"></a>Propriétés

| Propriété</br>**Nom physique**</br>**_Type_** | Cas d’emploi | Description  |
| --- | --- | --- |
| **Numéro personnel**</br>mshr_personnelnumber</br>*Chaîne* | Lecture seule</br>Requis |Numéro personnel unique du collaborateur.  |
| **Date de la prime**</br>mshr_awarddate</br>*Décalage de date et heure* | Lecture seule</br>Requis | Date de la prime. |
| **Type de prime**</br>mshr_awardtype</br>*[Ensemble d’options mshr_HrmCompVarAwardEmplType](hr-admin-integration-payroll-api-award-type.md)* | Lecture seule</br>Requis | Type de prime défini pour le régime de rémunération variable. |
| **Devise**</br>mshr_unitcurrencycode</br>*Chaîne* | Lecture seule </br>Requis |La devise définie pour le régime de rémunération variable.   |
| **ID de régime de rémunération fixe**</br>mshr_fixedplanid</br>*Chaîne* | Lecture seule | Régime de rémunération fixe utilisé comme base de calcul de la prime. |
| **Valeur unitaire**</br>mshr_awardamount</br>*Décimal* | Lecture seule | Valeur de l’unité |
| **Type de processus**</br>mshr_processtype</br>*[Ensemble d’options mshr_hrmCompProcessType](hr-admin-integration-payroll-api-process-type.md)* | Lecture seule | Type de processus. |
| **Type de régime variable de rémunération**</br>Chaîne</br>*mshr_typeid* | Lecture seule | Type de régime de rémunération variable. |
| **ID de régime variable de rémunération**</br>Chaîne</br>*mshr_planid* | Lecture seule | ID de régime de rémunération variable. |
| **Champ principal**</br>mshr_primaryfield</br>*GUID* | Lecture seule</br>Généré par le système. | |
| **ID employé**</br>mshr_fk_employee_id_value</br>*GUID* | Lecture seule</br>Requis</br>Clé étrangère : Foreign key:mshr_Employee_id de mshr_payrollemployeeentity entity  | ID employé. |
| **Entité de régime de rémunération variable de la paie**</br>mshr_payrollvariablecompensationawardentityid</br>*GUID* | Requis</br>Généré par le système | Valeur GUID générée par le système pour identifier le rémunération fixe de manière unique. |


## <a name="example-query"></a>Exemple de requête

**Demande**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollvariablecompensationawardentities?$filter=mshr_personnelnumber eq '000001'
```

**Réponse**

```json
{
    "mshr_personnelnumber": "000001",
    "mshr_awarddate": "2015-01-15T00:00:00Z",
    "mshr_awardtype": 200000000,
    "mshr_unitcurrencycode": "USD",
    "mshr_fixedplanid": "",
    "mshr_awardamount": 1,
    "mshr_processtype": 200000003,
    "mshr_typeid": "Bonus",
    "mshr_planid": "MgBonus",
    "mshr_primaryfield": "000001 | MgBonus | Bonus | 1/15/2015",
    "_mshr_fk_employee_id_value": "00000655-0000-0000-adff-004105000000",
    "mshr_payrollvariablecompensationawardentityid": "000001a1-0000-0000-adff-004105000000",
    "_mshr_fk_fixedcomp_id_value": null
}
```

## <a name="see-also"></a>Voir également :

[Présentation de l’API d’intégration de la paie](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
