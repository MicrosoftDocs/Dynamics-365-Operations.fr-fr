---
title: Employé avec paie
description: Cette rubrique fournit des détails et un exemple de requête pour l’entité Collaborateur avec paie dans Dynamics 365 Human Resources.
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
ms.openlocfilehash: 0cd37a7323c0dd0dc6e60ff0495f827e9a8582c1
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019368"
---
# <a name="payroll-employee"></a>Employé avec paie

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique fournit des détails et un exemple de requête pour l’entité Collaborateur avec paie dans Dynamics 365 Human Resources.

## <a name="properties"></a>Propriétés

| Propriété<br>**Nom physique**<br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **Numéro personnel**<br>mshr_personnelnumber<br>*Chaîne* | Lecture seule<br>Requis | Numéro personnel unique du collaborateur. |
| **Champ principal**<br>mshr_primaryfield<br>*Chaîne* | Requis<br>Généré par le système |  |
| **Nom**<br>mshr_lastname<br>*Chaîne* | Lecture seule<br>Requis | Nom de famille du collaborateur. |
| **ID entité juridique**<br>mshr_legalentityID<br>*Chaîne* | Lecture seule<br>Requis | Spécifie l’entité juridique (société). |
| **Valide à partir du**<br>mshr_namevalidfrom<br>*Décalage de date et heure* | Lecture seule <br>Requis | Date à partir de laquelle les informations relatives au collaborateur sont valides.  |
| **Sexe**<br>mshr_gender<br>*Int32* | Lecture seule<br>Requis | Genre du collaborateur. |
| **ID d'entité Collaborateur avec paie**<br>mshr_payrollemployeeentityid<br>*GUID* | Requis<br>Généré par le système | Valeur GUID générée par le système pour identifier le collaborateur de manière unique. |
| **Date de début de l'emploi**<br>mshr_employmentstartdate<br>*Décalage de date et heure* | Lecture seule<br>Requis | Date de début de l’emploi du collaborateur. |
| **ID du type d’identification**<br>mshr_identificationtypeid<br>*Chaîne* |Lecture seule<br>Requis | Le type d'identification défini pour le collaborateur. |
| **Date de fin de l'emploi**<br>mshr_employmentenddate<br>*Décalage de date et heure* | Lecture seule<br>Requis |Date de fin de l’emploi du collaborateur.  |
| **ID zone de données**<br>mshr_dataareaid_id<br>*GUID* | Requis <br>Généré par le système | Valeur GUID générée par le système identifiant l’entité juridique (société). |
| **Valide jusqu’au**<br>mshr_namevalidto<br>*Décalage de date et heure* |  Lecture seule<br>Requis | Date jusqu'à laquelle les informations relatives au collaborateur sont valides. |
| **Date de naissance**<br>mshr_birthdate<br>*Décalage de date et heure* | Lecture seule <br>Requis | La date de naissance du collaborateur. |
| **Numéro d’identification**<br>mshr_identificationnumber<br>*Chaîne* | Lecture seule <br>Requis |Le numéro d'identification défini pour le collaborateur.  |
| **Prénom**<br>mshr_firstname<br>*Chaîne* | Lecture seule<br>Requis | Prénom du collaborateur. |
| **Autres prénoms**<br>mshr_middlename<br>*Chaîne* | Lecture seule<br>Requis |Deuxième prénom du collaborateur.  |

## <a name="example-query-for-payroll-employee"></a>Exemple de requête pour un Collaborateur avec paie

**Demande**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollemployeeentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_identificationtypeid eq @idtype and mshr_namevalidfrom le @asofdate and mshr_namevalidto ge @asofdate&@personnelnumber='000041'&@idtype='SSN'&@asofdate=2021-04-01
```

**Réponse**

```json
{
         "mshr_legalentityid": "USMF",
            "mshr_personnelnumber": "000041",
            "mshr_employmentstartdate": "2011-04-05T07:00:00Z",
            "mshr_employmentenddate": "2154-12-31T23:59:59Z",
            "mshr_firstname": "Cassie",
            "mshr_middlename": "Lassie",
            "mshr_lastname": "Hicks",
            "mshr_namevalidfrom": "2021-03-12T20:34:25Z",
            "mshr_namevalidto": "2154-12-31T23:59:59Z",
            "mshr_birthdate": "1987-09-12T00:00:00Z",
            "mshr_gender": 200000002,
            "mshr_identificationtypeid": "SSN",
            "mshr_identificationnumber": "888-99-9342",
            "mshr_dataareaid": "USMF",
            "mshr_primaryfield": "000041 | USMF | 4/5/2011 07:00:00 am",
            "_mshr_fk_worker_id_value": "000000ad-0000-0000-d5ff-004105000000",
            "_mshr_fk_employment_id_value": "00000d0d-0000-0000-0600-014105000000",
            "_mshr_fk_fixedcompplan_id_value": "0000029f-0000-0000-d5ff-004105000000",
            "mshr_payrollemployeeentityid": "00000d3c-0000-0000-d5ff-004105000000",
            "_mshr_dataareaid_id_value": null
}
```
