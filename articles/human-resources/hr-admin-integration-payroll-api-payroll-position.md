---
title: Détails de la paie pour les postes
description: Cette rubrique fournit des détails et un exemple de requête pour l’entité Détails de la paie pour les postes dans Dynamics 365 Human Resources.
author: jcart
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7b23ac5d11b18c77109be21afe1570755dccba20
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019320"
---
# <a name="payroll-position"></a>Poste de paie

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique fournit des détails et un exemple de requête pour l’entité Détails de la paie pour les postes dans Dynamics 365 Human Resources.

## <a name="properties"></a>Propriétés

| Propriété<br>**Nom physique**<br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **Durée annuelle normale**<br>annualregularhours<br>*Décimal* | Lecture seule<br>Requis | Heures normales annuelles définies sur le poste.  |
| **ID de l'entité Détails du poste de paie**<br>payrollpositiondetailsentityid<br>*Guid* | Requis<br>Généré par le système. | Valeur GUID générée par le système pour identifier le poste de manière unique.  |
| **Champ principal**<br>mshr_primaryfield<br>*Chaîne* | Requis<br>Généré par le système |  |
| **Valeur d’ID du poste**<br>_mshr_fk_positionjob_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_PayrollPositionJobEntity de mshr_payrollpositionjobentity |ID du travail associé au poste.|
| **Valeur de l'ID du régime de rémunération fixe**<br>_mshr_fk_fixedcompplan_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_FixedCompPlan_id de mshr_payrollfixedcompensationplanentity  | ID du régime de rémunération fixe associé au poste. |
| **ID du cycle de paie**<br>mshr_primaryfield<br>*Chaîne* | Lecture seule<br>Requis | Le cycle de paie défini sur le poste. |
| **Rémunéré par l’entité juridique**<br>paidbylegalentity<br>*Chaîne* | Lecture seule<br>Requis | L'entité juridique définie sur le poste, responsable de l'émission du paiement. |
| **ID poste**<br>mshr_positionid<br>*Chaîne* | Lecture seule<br>Requis | ID du poste. |
| **Valide jusqu’au**<br>validto<br>*Décalage de date et heure* | Lecture seule<br>Requis |La date à partir de laquelle les détails du poste sont valides.  |
| **Valide à partir du**<br>validfrom<br>*Décalage de date et heure* | Lecture seule<br>Requis |La date jusqu'à laquelle les détails du poste sont valides.  |

**Requête**

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
