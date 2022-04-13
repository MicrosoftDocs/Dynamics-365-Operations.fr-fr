---
title: Historique du nom de la personne
description: Cette rubrique fournit des détails un exemple de requête pour l’entité Historique du nom de la personne dans Dynamics 365 Human Resources.
author: twheeloc
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: db22a602c782cef15b6e5769b9c0726dff158160
ms.sourcegitcommit: d67f7edaf1a50077c2a7dd105e774f86fc586495
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2022
ms.locfileid: "8533596"
---
# <a name="person-name-history"></a>Historique du nom de la personne


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’entité Historique du nom de la personne dans Dynamics 365 Human Resources.

Nom physique : mshr_dirpersonnamehistoricalentity.

### <a name="description"></a>Description

Cette entité fournit des informations sur l’historique des noms pour une personne donnée.

> [!IMPORTANT] 
> Les champs **FirstName**, **MiddleName**, **LastName**, **NameValidFrom** et **NameValidTo** ne sont plus disponibles sur l’entité Employé avec paie. Ils ont été supprimés pour garantir qu’une seule source de données à date d’effet soutient cette entité.

## <a name="properties"></a>Propriétés

| Propriété</br>**Nom physique**</br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **Prénom**</br>mshr_firstname</br>*Chaîne* | Lecture seule | Prénom. |
| **Préfixe du nom**</br>mshr_lastnameprefix</br>*Chaîne*) | Lecture seule | Préfixe du nom. |
| **Nom**</br>mshr_lastname</br>*Chaîne*) | Lecture seule | Nom. |
| **Autres prénoms**</br>mshr_middlename</br>*Chaîne*) | Lecture seule | Deuxième prénom. |
| **Valide jusqu’au**</br>mshr_validto</br>*Chaîne*) | Lecture seule | Date jusqu’à laquelle le nom est valide. |
| **Numéro de partie**</br>mshr_partynumber</br>*Chaîne* | Lecture seule | Identificateur unique généré par le système, lisible par l’utilisateur pour la personne. |
| **Champ principal**</br>mshr_primaryfield</br>*Chaîne* | Lecture seule | Identificateur unique de l’enregistrement. |
| **ID de l’entité Historique du nom de la personne**</br>mshr_dirpersonnamehistoricalentityid</br>*GUID* | Généré par le système | Une valeur d’identificateur global unique (GUID) générée par le système pour identifier de manière unique l’enregistrement. |

## <a name="relations"></a>Relations

| Valeur de propriété | Entité liée | Propriété de navigation | Type de collection |
| --- | --- | --- | --- |
| Non applicable | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | Non applicable | mshr_FK_PayrollEmployeeEntity_Name |

## <a name="example-query-for-payroll-employee"></a>Exemple de requête pour un Collaborateur avec paie

**Demande**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_dirpersonnamehistoricalentities?$filter=mshr_partynumber eq 'HR000001606'
```

**Réponse**

```json
{
    "mshr_firstname": "Agustina",
    "mshr_lastnameprefix": "",
    "mshr_lastname": "Fierro",
    "mshr_middlename": "middle",
    "mshr_validto": "2021-09-10T21:23:53Z",
    "mshr_partynumber": "HR000001606",
    "mshr_primaryfield": "HR000001606 | ",
    "mshr_dirpersonnamehistoricalentityid": "00000832-0000-0000-c12b-014105000000",
    "mshr_validfrom": null
},
{
    "mshr_firstname": "Agustina",
    "mshr_lastnameprefix": "",
    "mshr_lastname": "Fierro",
    "mshr_middlename": "",
    "mshr_validto": "2154-12-31T23:59:59Z",
    "mshr_partynumber": "HR000001606",
    "mshr_primaryfield": "HR000001606 | 9/10/2021 09:23:54 pm",
    "mshr_dirpersonnamehistoricalentityid": "00000832-0000-0000-d20b-000010000000",
    "mshr_validfrom": "2021-09-10T21:23:54Z"
}
```

## <a name="see-also"></a>Voir également :

[Présentation de l’API d’intégration de la paie](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
