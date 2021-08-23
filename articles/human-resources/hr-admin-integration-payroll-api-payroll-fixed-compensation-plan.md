---
title: Régime de rémunération fixe avec paie
description: Cette rubrique fournit des détails un exemple de requête pour l’entité Régime de rémunération fixe dans Dynamics 365 Human Resources.
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
ms.openlocfilehash: f1e5345d9f27106bdf3a3a60cb0480a9b072e340c01236e4d48c5e2ae592ddbd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738389"
---
# <a name="payroll-fixed-compensation-plan"></a>Régime de rémunération fixe avec paie

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’entité du plan de rémunération fixe de la paie pour Dynamics 365 Human Resources.

### <a name="description"></a>Description 

Cette entité fournit le plan de rémunération fixe attribué pour un poste donné d’un employé.

Nom physique : mshr_payrollfixedcompensationplanentity.

## <a name="properties"></a>Propriétés

| Propriété<br>**Nom physique**<br>**_Type_** | Cas d’emploi | Description  |
| --- | --- | --- |
| **ID employé**<br>mshr_fk_employee_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : Foreign key:mshr_Employee_id de mshr_payrollemployeeentity entity  | ID employé |
| **Salaire**<br>mshr_payrate<br>*Décimal* | Lecture seule<br>Requis | Taux de rémunération défini dans le régime de rémunération fixe. |
| **ID plan**<br>mshr_planid<br>*Chaîne* | Lecture seule<br>Requis |Spécifie le régime de rémunération.  |
| **Valide à partir du**<br>mshr_validfrom<br>*Décalage de date et heure* |  Lecture seule<br>Requis |Date à partir de laquelle les informations relatives à la rémunération fixe sont valides.  |
| **Entité Régime de rémunération fixe avec paie**<br>mshr_payrollfixedcompensationplanentityid<br>*GUID* | Requis<br>Généré par le système | Valeur GUID générée par le système pour identifier le rémunération fixe de manière unique. |
| **Fréquence de paiement**<br>mshr_payfrequency<br>*Chaîne* | Lecture seule<br>Requis |La fréquence à laquelle l’employé sera payé.  |
| **Valide jusqu’au**<br>mshr_validto<br>*Décalage de date et heure* | Lecture seule <br>Requis | Date jusqu’à laquelle les informations relatives à la rémunération fixe sont valides. |
| **ID poste**<br>mshr_positionid<br>*Chaîne* | Lecture seule <br>Requis | ID de poste associé à l’employé et à l’inscription au régime de rémunération fixe. |
| **Devise**<br>mshr_currency<br>*Chaîne* | Lecture seule <br>Requis |La devise définie pour le régime de rémunération fixe   |
| **Numéro personnel**<br>mshr_personnelnumber<br>*Chaîne* | Lecture seule<br>Requis |Numéro personnel unique du collaborateur.  |

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
