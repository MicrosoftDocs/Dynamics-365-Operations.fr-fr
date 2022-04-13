---
title: Régime des avantages sociaux pour les collaborateurs de la paie
description: Cette rubrique fournit des détails et un exemple de requête pour l’entité Régime des avantages sociaux pour les collaborateurs de la paie dans Dynamics 365 Human Resources.
author: twheeloc
ms.date: 07/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ade1c789716ea5f559a73c8551b7c1adf030b806
ms.sourcegitcommit: d67f7edaf1a50077c2a7dd105e774f86fc586495
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2022
ms.locfileid: "8533794"
---
# <a name="payroll-worker-benefit-plan"></a>Régime des avantages sociaux pour les collaborateurs de la paie


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’entité Régime des avantages sociaux pour les collaborateurs de la paie pour Dynamics 365 Human Resources.

Nom physique : mshr_payrollworkerbenefitplanentities.

### <a name="description"></a>Description

Cette entité fournit des informations sur le régime des avantages sociaux pour un collaborateur donné.

## <a name="properties"></a>Propriétés

| Propriété</br>**Nom physique**</br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **Numéro personnel**</br>mshr_personnelnumber</br>*Chaîne* | Lecture seule</br>Requis | Numéro personnel unique du collaborateur. |
| **ID entité juridique**</br>mshr_legalentityID</br>*Chaîne* | Lecture seule | Spécifie l’entité juridique (société). |
| **ID période**</br>mshr_periodid</br>*Chaîne* | Lecture seule | Identificateur de la période. |
| **ID plan**</br>mshr_planid</br>*Chaîne* | Lecture seule | Identificateur du régime. |
| **Option de couverture**</br>mshr_coverageoptionid</br>*Chaîne* | Lecture seule | Identification de l’option de couverture. |
| **Date de début de la déduction**</br>mshr_deductionstartdatetime</br>*Décalage de date et heure* | Lecture seule | Date de début de la déduction. |
| **Date de fin de la déduction**</br>mshr_deductionenddatetime</br>*Décalage de date et heure* | Lecture seule | Date de fin de la déduction. |
| **État**</br>mshr_status</br>*[Groupe d’options Statut du régime des avantages sociaux des employés](hr-admin-integration-payroll-api-benefit-employee-plan-status.md)* | Lecture seule | Statut du régime des avantages sociaux. |
| **Valide à partir du**</br>mshr_validfrom</br>*Décalage de date et heure* | Lecture seule | Heure de début de validité de l’enregistrement. |
| **Valide jusqu’au**</br>mshr_validto</br>*Décalage de date et heure* |  Lecture seule | Heure de fin de validité de l’enregistrement. |
| **ID du type de régime**</br>mshr_plantypeid</br>*Chaîne* | Lecture seule | Identificateur du type de régime. |
| **Code de type de plan**</br>mshr_plantypecode</br>*[Groupe d’options Couverture du type de régime des avantages sociaux](hr-admin-integration-payroll-api-benefit-plan-type-cover.md)* | Lecture seule | Spécification du type de régime. |
| **Nombre de périodes de paiement :**</br>mshr_payperiod</br>*Entier* | Lecture seule | Nombre de périodes de paiement qui représente la fréquence de paiement du fournisseur ou des employés. Ce montant sera utilisé pour calculer le montant du salaire des avantages annuels de l’employé. |
| **Montant de l’employé**</br>mshr_amountemployee</br>*Décimal* | Lecture seule | Montant ou pourcentage de l’employé. |
| **Montant de l’employeur**</br>mshr_amountemployer</br>*Décimal* | Lecture seule | Montant ou pourcentage de l’employeur. |
| **Champ principal**</br>mshr_primaryfield</br>*Chaîne* | Généré par le système | Champ principal. |
| **Valeur de l’ID du collaborateur** </br>_mshr_fk_worker_id_value</br>*GUID* | Clé étrangère : mshr_hcmworkerbaseentityid of mshr_hcmworkerbaseentity entity. | Identificateur unique généré par le système pour le collaborateur. |
| **Valeur de l’ID de période**</br> _mshr_fk_period_id_value</br>*GUID* | Clé étrangère : mshr_benefitperiodentityid of mshr_benefitperiodentity entity. | Identificateur unique généré par le système pour la période. |
| **Valeur de l’ID du régime**</br> _mshr_fk_plan_id_value</br>*GUID* | Clé étrangère : mshr_benefitplanentityid of mshr_benefitplanentity entity. | Identificateur unique généré par le système pour le régime. |
| **Valeur de l’ID du type de régime**</br> _mshr_fk_plantype_id_value</br>*GUID* | Clé étrangère : mshr_benefitplantypeentityid of mshr_benefitplantypeentity entity. | Identificateur unique généré par le système pour le régime. |
| **Valeur de l’ID de l’option de couverture**</br> _mshr_fk_coverageoption_id_value</br>*GUID* | Clé étrangère : mshr_benefitcoverageoptionentityid of mshr_benefitcoverageoptionentity entity. | Identificateur unique généré par le système pour le régime. |
| **Valeur de l’ID de l’entité Régime des avantages sociaux pour les collaborateurs de la paie**</br> mshr_payrollworkerbenefitplanentityid</br>*GUID* | Lecture seule </br> Généré par le système | Identificateur unique généré par le système pour l’enregistrement. |

## <a name="example-query-for-payroll-worker-benefit-plan"></a>Exemple de requête pour le régime des avantages sociaux pour les collaborateurs de la paie

**Demande**

```http
GET [Organization URI]/api/data/v9.1/mshr_payrollworkerbenefitplanentities?$filter=mshr_personnelnumber eq '000020'
```

**Réponse**

```json
{
    "mshr_personnelnumber": "000020",
    "mshr_legalentityid": "USMF",
    "mshr_periodid": "2021",
    "mshr_planid": "Dental plan",
    "mshr_coverageoptionid": "Emp Only",
    "mshr_deductionstartdatetime": "2021-01-01T06:00:00Z",
    "mshr_deductionenddatetime": "2021-12-31T06:00:00Z",
    "mshr_status": 200000001,
    "mshr_validfrom": "2021-01-01T06:00:00Z",
    "mshr_validto": "2021-12-31T06:00:00Z",
    "mshr_plantypeid": "Dental",
    "mshr_plantypecode": 200000001,
    "mshr_payperiod": 12,
    "mshr_amountemployee": 47,
    "mshr_amountemployer": 57,
    "mshr_primaryfield": "000020 | USMF | 2021 | Dental plan",
    "_mshr_fk_worker_id_value": "000000ae-0000-0000-bfff-004105000000",
    "_mshr_fk_period_id_value": "00000807-0000-0000-ee02-005001000000",
    "_mshr_fk_plan_id_value": "00000c61-0000-0000-0200-005001000000",
    "_mshr_fk_plantype_id_value": "0000057c-0000-0000-0200-005001000000",
    "_mshr_fk_coverageoption_id_value": "00000391-0000-0000-0b00-005001000000",
    "mshr_payrollworkerbenefitplanentityid": "000006c4-0000-0000-bfff-004105000000"
}
```
## <a name="see-also"></a>Voir également :

[Présentation de l’API d’intégration de la paie](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
