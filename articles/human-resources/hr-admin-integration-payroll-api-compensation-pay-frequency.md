---
title: Fréquence de paiement de la rémunération
description: Cette rubrique fournit des détails un exemple de requête pour l’entité Fréquence de paiement de la rémunération dans Dynamics 365 Human Resources.
author: marcelbf
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 171b7fb7b361bd1fe2e7e637cd555c88a81a8bcf
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066141"
---
# <a name="compensation-pay-frequency"></a>Fréquence de paiement de la rémunération


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’entité Fréquence de paiement de la rémunération dans Dynamics 365 Human Resources.

Nom physique : mshr_hcmpayrateconversionentity.

### <a name="description"></a>Description

Cette entité fournit des informations sur la conversion du taux de rémunération pour une fréquence de rémunération donnée.

## <a name="properties"></a>Propriétés

| Propriété</br>**Nom physique**</br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **Conversion des taux de rémunération annuels**</br>mshr_annualconversionfactor</br>*Décimal* | Lecture seule | Facteur de conversion annuel pour la fréquence de rémunération. |
| **Description**</br>mshr_description</br>*Chaîne* | Lecture seule | Description du taux de conversion. |
| **Conversion des taux de rémunération horaires**</br>mshr_hourlyconversionfactor</br>*Décimal* | Lecture seule | Facteur de conversion horaire pour la fréquence de rémunération. |
| **Conversion des taux de rémunération mensuels**</br>mshr_monthlyconversionfactor</br>*Décimal* | Lecture seule | Facteur de conversion mensuel pour la fréquence de rémunération. |
| **Fréquence de paiement**</br>mshr_payrateconversion</br>*Chaîne* | Lecture seule | Une chaîne unique pour identifier le taux de conversion. |
| **Période**</br>mshr_period</br>*ensemble d’options de période* | Lecture seule | La période principale pour la conversion de taux de rémunération donnée. |
| **Conversion des taux de rémunération hebdomadaires**</br>mshr_weeklyconversionfactor</br>*Décimal* | Lecture seule | Facteur de conversion hebdomadaire pour la fréquence de rémunération. |
| **ID zone de données**</br>mshr_dataareaid</br>*Chaîne* | Lecture seule | Entité juridique (société). |
| **ID de l’entité Fréquence de paiement de la rémunération**</br>mshr_dirpersonnamehistoricalentityid</br>*GUID* | Généré par le système | Une valeur d’identificateur global unique (GUID) générée par le système pour identifier de manière unique l’enregistrement. |

## <a name="example-query-for-payroll-employee"></a>Exemple de requête pour un Collaborateur avec paie

**Demande**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_hcmpayrateconversionentities?$filter=mshr_payrateconversion eq 'Annual' and mshr_dataareaid eq 'usmf'
```

**Réponse**

```json
{
    "mshr_annualconversionfactor": 1,
    "mshr_description": "Annual",
    "mshr_hourlyconversionfactor": 0.0004807692,
    "mshr_monthlyconversionfactor": 0.0833333333,
    "mshr_payrateconversion": "Annual",
    "mshr_period": 200000000,
    "mshr_weeklyconversionfactor": 0.0192307692,
    "mshr_dataareaid": "usmf",
    "mshr_hcmpayrateconversionentityid": "0000056e-0000-0000-b027-fef003000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Voir également :

[Présentation de l’API d’intégration de la paie](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
