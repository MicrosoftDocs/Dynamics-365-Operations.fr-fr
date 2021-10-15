---
title: Adresse du collaborateur avec paie
description: Cette rubrique fournit des détails et un exemple de requête pour l’entité Adresse du collaborateur avec paie dans Dynamics 365 Human Resources.
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
ms.openlocfilehash: bf3fc5f333333b9a832ecb9c185473e476ac231d
ms.sourcegitcommit: 12e26ef25c492e5032260733b50cd642cbd6164d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/28/2021
ms.locfileid: "7559507"
---
# <a name="payroll-worker-address"></a>Adresse du collaborateur avec paie

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’entité de l’adresse du collaborateur de la paie pour Dynamics 365 Human Resources.

Nom physique : mshr_payrollworkeraddressentity.

### <a name="description"></a>Description 

Cette entité fournit le lieu de résidence de la paie et le lieu de travail de la paie pour un employé donné.

## <a name="properties"></a>Propriétés

| Propriété</br>**Nom physique**</br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **Numéro personnel**</br>mshr_personnelnumber</br>*Chaîne* | Lecture seule | Numéro personnel unique du collaborateur. |
| **ID emplacement**</br>mshr_locationidbr>*Chaîne* | Lecture seule | ID de l’adresse. |
| **Adresse de résidence**</br>mshr_islivedinaddressbr </br> *[Ensemble d’options mshr_NoYes](hr-admin-integration-payroll-api-no-yes.md)* | Lecture seule | Une valeur qui indique si l'adresse est celle du lieu de résidence de l'employé. |
| **Adresse de travail** </br> mshr_isworkedinaddressbr </br>*[Ensemble d’options mshr_NoYes](hr-admin-integration-payroll-api-no-yes.md)* | Lecture seule | Une valeur qui indique si l'adresse est celle du lieu de travail de l'employé. |
| **Pays ou région**</br>mshr_countryregionid</br>*Chaîne* | Lecture seule</br>Requis | Pays ou région qui est défini.e pour l’adresse. |
| **Code postal**</br>mshr_zipcode<br>*Chaîne* | Lecture seule | Le numéro d’identification qui est défini pour le collaborateur. |
| **Rue**</br>mshr_street</br>*Chaîne* | Lecture seule | Rue qui est définie pour l’adresse. |
| **Ville**</br>mshr_city</br>*Chaîne* | Lecture seule | Ville qui est définie pour l’adresse. |
| **Région**</br>mshr_state</br>*Chaîne* | Lecture seule | État ou province qui est défini.e pour l’adresse. |
| **Département**</br>mshr_county</br>*Chaîne* | Lecture seule | Département qui est défini pour l’adresse. |
| **Valide à partir du**</br>mshr_postaladdressvalidfrom</br>*Décalage de date et heure* | Lecture seule | Date à partir de laquelle l’adresse est valide. |
| **Valide jusqu’au**</br>mshr_postaladdressvalidto</br>*Décalage de date et heure* | Lecture seule | Date jusqu'à laquelle l’adresse est valide. |
| **Champ principal**</br>mshr_primaryfield</br>*Chaîne* | Lecture seule | Champ principal. |
| **ID de l’adresse du collaborateur avec paie**</br>mshr_payrollworkeraddressentityid</br>*GUID* | Généré par le système | Une valeur d'identificateur global unique (GUID) générée par le système pour identifier de manière unique l'adresse. |

## <a name="relations"></a>Relations

| Valeur de propriété  | Entité liée | Propriété de navigation | Type de collection |
| --- | --- | --- | --- |
| _mshr_fk_worker_id_value | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | mshr_FK_Worker_id | mshr_FK_PayrollEmployeeEntity_Address |

## <a name="example-query"></a>Exemple de requête

**Demande**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollworkeraddressentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_postaladdressvalidfrom le @asofdate and mshr_postaladdressvalidto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

**Réponse**

```json
{
    "mshr_personnelnumber": "000041",
    "mshr_locationid": "000000538",
    "mshr_islivedinaddress": 200000001,
    "mshr_isworkedinaddress": 200000000,
    "mshr_countryregionid": "USA",
    "mshr_zipcode": "99025",
    "mshr_street": "6543 Cypress Ave",
    "mshr_city": "Tacoma",
    "mshr_state": "WA",
    "mshr_county": "KING",
    "mshr_postaladdressvalidfrom": "2012-09-20T20:14:27Z",
    "mshr_postaladdressvalidto": "2154-12-31T23:59:59Z",
    "mshr_primaryfield": "000041 | 000000538 | 9/20/2012 08:14:27 pm",
    "_mshr_fk_worker_id_value": "00000d3c-0000-0000-d5ff-004105000000",
    "mshr_payrollworkeraddressentityid": "000006f0-0000-0000-f90f-014105000000"

}
```

## <a name="see-also"></a>Voir également :

[Présentation de l’API d’intégration de la paie](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
