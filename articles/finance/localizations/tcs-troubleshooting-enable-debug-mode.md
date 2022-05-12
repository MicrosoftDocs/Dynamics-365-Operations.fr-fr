---
title: Activer le mode débogage dans le service de calcul des taxes
description: Cette rubrique explique comment activer le mode débogage dans le service de calcul des taxes pour étudier les problèmes.
author: hangwan
ms.date: 03/25/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: ''
ms.search.region: Global
ms.author: hangwan
ms.search.validFrom: 03/23/2022
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 2f526a2341c7ef682209ed979fe686e31ad62a37
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645433"
---
# <a name="enable-debug-mode-in-the-tax-calculation-service"></a>Activer le mode débogage dans le service de calcul des taxes

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment activer le mode débogage dans le service de calcul des taxes pour étudier les problèmes.

1. Ajouter **&debug=vs%2CconfirmExit&** à l’URL du Serveur d’objets d’application (AOS), puis actualisez la page.
2. Quand vous sélectionnez **Taxe de vente** pour calculer la taxe de vente, un fichier texte nommé **TaxServiceTroubleshootingLog.txt** est ouvert. Le fichier **TaxServiceTroubleshootingLog.txt** contient **TaxableDocument** et le paramètre de calcul. Ces résultats sont renvoyés par le service fiscal et les informations sur les exceptions pour le dépannage.

## <a name="sample"></a>Exemple

```json
===============================Tax service calculation input JSON:=====================================
{
    "TaxableDocument": {
    "Header": [
        {
        "Lines": [
            {
            "Transaction Line ID": "5816,68719677391",
            ...
            }
        ],
        "Transaction Header ID": "2022,68719506302",
        ...
        }
    ]
    },
    "Parameter": {
    "ContinueOnErrors": true,
    ...
    },
    "Adjustment": {
    "Lines": {}
    }
}
===========================Tax service calculation result JSON:=================================
{
    "taxDocument": {
    "Header": [
        {
        "Lines": [
            {
            "Tax Codes": {
                ...
            }
        ],
        "Measures": {
            "List Code": "EUTrade"
        },
        "Tax Registration ID": null,
        "Transaction Header ID": "2022,68719506302",
        "Errors": null
        }
    ]
    },
    "solutionId": "b51e0025-cbbe-4d37-bf0b-90d7be4f214d|1",
    "isPartialSuccess": false
}
=============================CorrelationId:==============================
"21f3a8a1-ee9a-477b-b44e-b8ec79e74d16"
```

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
