---
title: Employé avec paie
description: Cette rubrique fournit des détails et un exemple de requête pour l’entité Collaborateur avec paie dans Dynamics 365 Human Resources.
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
ms.openlocfilehash: 7f43476cd044a9cc2e11412aac4af1cff2f9e511
ms.sourcegitcommit: 12e26ef25c492e5032260733b50cd642cbd6164d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/28/2021
ms.locfileid: "7559531"
---
# <a name="payroll-employee"></a>Employé avec paie

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’entité d’employé de la paie pour Dynamics 365 Human Resources.

Nom physique : mshr_payrollemployeeentity.

### <a name="description"></a>Description

Cette entité fournit des informations sur l’employé. Vous devez définir les [paramètres d’intégration de la paie](hr-admin-integration-payroll-api-parameters.md) avant d’utiliser cette entité.

>[!IMPORTANT] 
>Les champs **Prénom**, **Deuxième prénom**, **Nom de famille**, **NomValideApartirDe** et **NomValideJusqu** ne sont plus disponibles sur cette entité. Cela garantit qu’il n’y a qu’une seule source de données à date effective qui soutient cette entité.
>Ces champs seront disponibles sur l'entité **DirPersonNameHistoricalEntity**, qui a été publiée dans la mise à jour de plateforme 43. Il existe une relation OData entre **PayrollEmployeeEntity** et **DirPersonNameHistoricalEntity**. 

## <a name="properties"></a>Propriétés

| Propriété</br>**Nom physique**</br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **ID entité juridique**</br>mshr_legalentityid</br>*Chaîne* | Lecture seule | Spécifie l’entité juridique (société). |
| **Numéro personnel**</br>mshr_personnelnumber</br>*Chaîne* | Lecture seule | Numéro personnel unique du collaborateur. |
| **Date de début de l’emploi**</br>mshr_employmentstartdate</br>*Décalage de date et heure* | Lecture seule | Date de début de l’emploi du collaborateur. |
| **Date de fin de l'emploi**</br>mshr_employmentenddate</br>*Décalage de date et heure* | Lecture seule |Date de fin de l’emploi du collaborateur.  |
| **Date de naissance**</br>mshr_birthdate</br>*Décalage de date et heure* | Lecture seule | La date de naissance du collaborateur. |
| **Sexe**</br>mshr_gender</br>[Jeu d’options mshr_hcmpersongender](hr-admin-integration-payroll-api-gender.md) | Lecture seule | Genre du collaborateur. |
| **Type d'emploi**</br>mshr_employmenttype</br>[Jeu d'options mshr_hcmemploymenttype](hr-admin-integration-payroll-api-hcmemploymenttype.md) | Lecture seule | Le type d'emploi. |
| **ID du type d’identification**</br>mshr_identificationtypeid</br>*Chaîne* |Lecture seule | Le type d’identification défini pour le collaborateur. |
| **Numéro d’identification**</br>mshr_identificationnumber</br>*Chaîne* | Lecture seule |Le numéro d’identification défini pour le collaborateur. |
| **Prêt à payer**</br>mshr_readytopay</br>[Jeu d’options mshr_noyes](hr-admin-integration-payroll-api-no-yes.md) | Lecture seule | Indique si l'employé est marqué comme étant prêt à payer. |
| **ID d’entité Collaborateur avec paie**</br>mshr_payrollemployeeentityid</br>*GUID* | Généré par le système | Une valeur d'identificateur global unique (GUID) générée par le système pour identifier de manière unique l'employé. |

## <a name="relations"></a>Relations

|Valeur de propriété  | Entité liée | Propriété de navigation | Type de collection |
| --- | --- | --- | --- |
| _mshr_fk_employment_id_value | mshr_hcmemploymentdetailentity | mshr_FK_Employment_id | mshr_FK_HcmEmploymentDetailEntity_PayrollEmployee |
| _mshr_fk_fixedcompplan_id_value | [mshr_payrollfixedcompensationplanentity](hr-admin-integration-payroll-api-payroll-fixed-compensation-plan.md) | mshr_FK_FixedCompPlan_id | mshr_FK_PayrollFixedCompensationPlanEntity_Employee |
| _mshr_fk_name_id_value | mshr_dirpersonnamehistoricalentity | mshr_FK_Name_id | - |
| _mshr_fk_worker_id_value | mshr_hcmworkerbaseentity | mshr_FK_Worker_id | mshr_FK_HcmWorkerBaseEntity_PayrollEmployee |
| _mshr_fk_workerbankaccount_id_value | mshr_hcmworkerbankaccountentity | mshr_FK_WorkerBankAccount_id | mshr_FK_HcmWorkerBankAccountEntity_PayrollEmployee |
| _mshr_fk_variablecompaward_id_value | [mshr_payrollvariablecompensationawardentity](hr-admin-integration-payroll-api-payroll-variable-compensation-plan.md) | mshr_FK_VariableCompAward_id | mshr_FK_PayrollVariableCompensationAwardEntity_Employee |
| _mshr_fk_address_id_value | [mshr_payrollworkeraddressentity](hr-admin-integration-payroll-api-payroll-worker-address.md) | mshr_FK_Address_id | mshr_FK_PayrollWorkerAddressEntity_Worker |

## <a name="example-query-for-payroll-employee"></a>Exemple de requête pour un Collaborateur avec paie

**Demande**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollemployeeentities?$filter=mshr_personnelnumber eq '000041'
```

**Réponse**

```json
{
    "mshr_legalentityid": "USMF",
    "mshr_personnelnumber": "000041",
    "mshr_employmentstartdate": "2011-04-05T07:00:00Z",
    "mshr_employmentenddate": "2154-12-31T23:59:59Z",
    "mshr_birthdate": "1987-09-12T00:00:00Z",
    "mshr_gender": 200000002,
    "mshr_employmenttype": 200000000,
    "mshr_identificationtypeid": "SSN",
    "mshr_identificationnumber": "888-99-9342",
    "mshr_readytopay": 200000000,
    "mshr_dataareaid": "USMF",
    "mshr_primaryfield": "000041 | USMF | 4/5/2011 07:00:00 am",
    "_mshr_fk_employment_id_value": "00000d4e-0000-0000-0600-014105000000",
    "_mshr_fk_fixedcompplan_id_value": "00000598-0000-0000-4cd0-fda002000000",
    "_mshr_fk_name_id_value": "00000832-0000-0000-d700-014105000000",
    "_mshr_fk_worker_id_value": "000000af-0000-0000-d5ff-004105000000",
    "_mshr_fk_workerbankaccount_id_value": "000006f2-0000-0000-b7ff-004105000000",
    "mshr_payrollemployeeentityid": "00000666-0000-0000-d5ff-004105000000",
    "_mshr_fk_address_id_value": null,
    "_mshr_fk_variablecompaward_id_value": null,
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Voir également :

[Présentation de l’API d’intégration de la paie](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
