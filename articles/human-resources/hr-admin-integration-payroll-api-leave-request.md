---
title: Demande de congés
description: Cette rubrique fournit des détails et un exemple de requête pour l’entité de demande de congés dans Dynamics 365 Human Resources.
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
ms.openlocfilehash: c6c772c26e8a789a54c9eeb36c1cab576a7f94cb3ede547db46fe18a2e89c8ce
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6762020"
---
# <a name="leave-request"></a>Demande de congés

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’entité de demande de congés pour Dynamics 365 Human Resources.

### <a name="description"></a>Description 

Cette entité fournit des informations pour une demande de congé.

Nom physique : mshr_essleaverequestentity.

## <a name="properties"></a>Propriétés

| Propriété</br>**Nom physique**</br>**_Type_** | Cas d’emploi | Description  |
| --- | --- | --- |
| **ID demande**</br>mshr_requestid</br>*Chaîne* | Lecture seule | ID de la demande. |
| **ID type de congé**</br>mshr_leavetypeid</br>*Chaîne* | Lecture seule | ID de type de congé. |
| **Date**</br>mshr_leavedate</br>*Décalage de date et heure* | Lecture seule | Date de la demande de congé. |
| **Montant**</br>mshr_amount</br>*Décimal* | Lecture seule | Montant de la demande de congé. |
| **Type demi-journée**</br>mshr_halfdaydefinition</br>*Ensemble d’options mshr_LeaveHalfDayDefinition* | Lecture seule | Type de congé d’une demi-journée. |
| **Commentaire**</br>mshr_comment</br>*Chaîne* | Lecture seule | Commentaire de la demande. |
| **État**</br>mshr_status</br>*Ensemble d’options mshr_status* | Lecture seule | Statut de la demande. |
| **Date**</br>mshr_requestdate</br>*Décalage de date et heure* | Lecture seule | Date de la demande. |
| **Numéro personnel**</br>mshr_personnelnumber</br>*Chaîne* | Lecture seule | Numéro personnel unique du collaborateur. |
| **ID du code de motif**</br>mshr_reasoncodeid</br>*Chaîne* | Lecture seule | ID du code de motif. |
| **ID zone de données**</br>mshr_dataareaid</br>*Chaîne* | Lecture seule | Spécifie l’entité juridique (société). |
| **Champ principal**</br>mshr_primaryfield</br>*GUID* | Lecture seule</br>Généré par le système | |
| **Entité de type de congé**</br>mshr_essleaverequestentityid</br>*GUID* | Généré par le système | Valeur GUID générée par le système pour identifier la demande de congé de manière unique. |

## <a name="example-query"></a>Exemple de requête

**Demande**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_essleaverequestentities?$filter=mshr_personnelnumber eq '000020'
```

**Réponse**

```json
{
    "mshr_requestid": "USMF-000001",
    "mshr_leavetype": "PTO",
    "mshr_leavedate": "2017-01-02T00:00:00Z",
    "mshr_amount": 8,
    "mshr_halfdaydefinition": 200000000,
    "mshr_comment": "Taking a week off to relax",
    "mshr_status": 200000009,
    "mshr_requestdate": "2017-07-31T00:00:00Z",
    "mshr_personnelnumber": "000020",
    "mshr_reasoncodeid": "",
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "USMF-000001 | PTO | 1/2/2017",
    "mshr_essleaverequestentityid": "000004dd-0000-0000-0f00-005001000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Voir également :

[Présentation de l’API d’intégration de la paie](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
