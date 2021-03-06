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
ms.openlocfilehash: 3407128b0172f0e253d51bcfa23a894f981e21e2
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052287"
---
# <a name="payroll-worker-address"></a>Adresse du collaborateur avec paie

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique fournit des détails et un exemple de requête pour l’entité Adresse du collaborateur avec paie dans Dynamics 365 Human Resources.

## <a name="properties"></a>Propriétés

| Propriété<br>**Nom physique**<br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **Ville**<br>mshr_city<br>*Chaîne* | Lecture seule<br>Requis | Ville définie pour l'adresse.   |
| **Numéro personnel**<br>mshr_personnelnumber<br>*Chaîne* | Lecture seule<br>Requis | Numéro personnel unique du collaborateur.  |
| **Pays ou région**<br>mshr_countryregionid<br>*Chaîne* | Lecture seule<br>Requis | Le pays/région défini pour l'adresse.  |
| **Valide à partir du**<br>mshr_postaladdressvalidfrom<br>*Décalage de date et heure* | Lecture seule <br>Requis | Date à partir de laquelle l'adresse est valide. |
| **Adresse de travail**<br>mshr_isworkedinaddressbr>*Int32* | Lecture seule<br>Requis | Indique si l'adresse est le lieu de travail du collaborateur. |
| **Département**<br>mshr_county<br>*Chaîne* | Lecture seule<br>Requis | Département défini pour l'adresse.  |
| **ID de l'adresse du collaborateur avec paie**<br>mshr_payrollworkeraddressentityid<br>*GUID* | Requis<br>Généré par le système | Valeur GUID générée par le système pour identifier l'adresse de manière unique.  |
| **Champ principal**<br>mshr_primaryfield<br>*Chaîne* | Lecture seule<br>Requis |  |
| **Rue**<br>mshr_street<br>*Chaîne* | Lecture seule<br>Requis | Rue définie pour l'adresse. |
| **Valide jusqu’au**<br>mshr_postaladdressvalidto<br>*Décalage de date et heure* | Lecture seule <br>Requis | Date jusqu'à laquelle l'adresse est valide.  |
| **ID emplacement**<br>mshr_locationidbr>*Chaîne* | Lecture seule <br>Requis | ID de l'adresse.  |
| **Code postal**<br>mshr_zipcode<br>*Chaîne* | Lecture seule <br>Requis |Le numéro d'identification défini pour le collaborateur.  |
| **Adresse de résidence**<br>mshr_islivedinaddressbr>*Chaîne* | Lecture seule<br>Requis | Indique si l'adresse est le lieu de résidence du collaborateur. |
| **État**<br>mshr_state<br>*Chaîne* | Lecture seule<br>Requis | État défini pour l'adresse.  |

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
