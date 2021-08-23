---
title: Type de congé
description: Cette rubrique fournit des détails et un exemple de requête pour l’entité de type de congé dans Dynamics 365 Human Resources.
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
ms.openlocfilehash: 5e64b533ad7be23060701e8826a25736a078b59d1ecf824bee0e2dd05c9c78f8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6713100"
---
# <a name="leave-type"></a>Type de congé

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’entité de type de congé pour Dynamics 365 Human Resources.

### <a name="description"></a>Description 

Cette entité fournit des informations pour un type de congé donné.

Nom physique : mshr_essleavetypeentity.

## <a name="properties"></a>Propriétés

| Propriété</br>**Nom physique**</br>**_Type_** | Cas d’emploi | Description  |
| --- | --- | --- |
| **ID type de congé**</br>mshr_leavetypeid</br>*Chaîne* | Lecture seule | ID de type de congé. |
| **Description**</br>mshr_description</br>*Chaîne* | Lecture seule | Description du type de congé. |
| **Catégorie**</br>mshr_category</br>*Ensemble d’options mshr_LeaveTypeCategory* | Lecture seule | Catégorie de type de congé. |
| **Code motif obligatoire**</br>mshr_isreasoncoderequired</br>*Ensemble d’options mshr_NoYes* | Lecture seule | Définit si un code de motif est obligatoire pour le type de congé. |
| **Unité de congé**</br>mshr_leaveamountunit</br>*Ensemble d’options mshr_LeaveAmountUnit* | Lecture seule | Unité de ce type de congé. |
| **Activer la demi-journée**</br>mshr_enablehalfdaydefinition</br>*Ensemble d’options mshr_NoYes* | Définit si la demi-journée est activée pour le type de congé. |
| **ID zone de données**</br>mshr_dataareaid_id</br>*Chaîne* | Lecture seule | Spécifie l’entité juridique (société). |
| **Entité de type de congé**</br>mshr_essleavetypeentityid</br>*GUID* | Généré par le système | Valeur GUID générée par le système pour identifier le type de congé de manière unique. |

## <a name="example-query"></a>Exemple de requête

**Demande**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_essleavetypeentities?$filter=mshr_leavetypeid eq 'PTO'
```

**Réponse**

```json
{
    "mshr_leavetypeid": "PTO",
    "mshr_description": "Paid time off",
    "mshr_category": 200000000,
    "mshr_isreasoncoderequired": 200000000,
    "mshr_leaveamountunit": 200000000,
    "mshr_enablehalfdaydefinition": 200000000,
    "mshr_dataareaid": "usmf",
    "mshr_essleavetypeentityid": "00000a6c-0000-0000-0000-005001000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Voir également :

[Présentation de l’API d’intégration de la paie](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
