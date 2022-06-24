---
title: Solde des congés
description: Cet article fournit des détails et un exemple de requête pour l’entité de solde des congés dans Dynamics 365 Human Resources.
author: marcelbf
ms.date: 06/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4792c316b8b7af3e86b097029eb281af4a10d113
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899699"
---
# <a name="leave-balance"></a>Solde des congés


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article décrit l’entité de solde des congés pour Dynamics 365 Human Resources.

### <a name="description"></a>Description

Cette entité fournit le solde des congés par type de congé pour un employé donné.

Nom physique : mshr_essleavebalanceentities.

## <a name="properties"></a>Propriétés

| Propriété</br>**Nom physique**</br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **Numéro personnel**</br>mshr_personnelnumber</br>*Chaîne* | Lecture seule | Numéro personnel unique du collaborateur. |
| **Solde actuel**</br>mshr_balanceavailable</br>*Décimal* | Lecture seule | Solde actuel de l’employé. |
| **Type**</br>mshr_balanceavailable</br>*Chaîne* | Lecture seule | ID de type de congé. |
| **Taux de régularisation**</br>mshr_accrualratedescription</br> | Lecture seule | Le taux d’accumulation. |
| **Dernier montant reporté**</br>mshr_lastcarryforwardamount</br>*Décimal* | Lecture seule | Montant du Dernier report. |
| **Pris cette année**</br>mshr_takenthisyear</br>*Décimal* | Lecture seule | Nombre de congés pris cette année. |
| **Total de cette année**</br>mshr_totalthisyear</br>*Décimal* | Lecture seule | Montant total pour cette année. |
| **ID zone de données**</br>mshr_dataareaid_id</br>*Chaîne* | Lecture seule | Spécifie l’entité juridique (société). |
| **Champ principal**</br>mshr_primaryfield</br>*GUID* | Lecture seule</br>Généré par le système | |
| **ID type de congé**</br>_mshr_fk_leavetype_id_value</br>*GUID* | Lecture seule</br>Entité de clé étrangère : mshr_essleavetypeentityid of mshr_essleavetypeentity entity  | ID type de congé |
| **Entité de solde des congés**</br>mshr_essleavebalanceentityid</br>*GUID* | Généré par le système | Valeur GUID générée par le système pour identifier le solde. |

## <a name="example-query"></a>Exemple de requête

**Demande**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_essleavebalanceentities?$filter=mshr_personnelnumber eq '000013'
```

**Réponse**

```json
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 67.76,
    "mshr_leavetypeid": "PTO",
    "mshr_accrualratedescription": "6.16 hrs / Semimonthly",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 67.76,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | PTO",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-0000-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-2703-005001000000",
    "_mshr_dataareaid_id_value": null
},
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 80,
    "mshr_leavetypeid": "Sick",
    "mshr_accrualratedescription": "80.00 hrs / Annually",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 80,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | Sick",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-ee02-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-3003-005001000000",
    "_mshr_dataareaid_id_value": null
},
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 0,
    "mshr_leavetypeid": "Bereavement",
    "mshr_accrualratedescription": "0.00 hrs / Annually",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 0,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | Bereavement",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-f402-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-4403-005001000000",
    "_mshr_dataareaid_id_value": null
},
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 66.65,
    "mshr_leavetypeid": "Vacation",
    "mshr_accrualratedescription": "13.33 hrs / Monthly",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 66.65,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | Vacation",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-f502-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-1009-005001000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Voir également :

[Présentation de l’API d’intégration de la paie](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
