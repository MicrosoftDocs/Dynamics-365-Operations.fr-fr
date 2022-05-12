---
title: Aucun résultat correspondant n’a pu être trouvé
description: Cette rubrique explique comment résoudre l’erreur « Aucun résultat correspondant n’a pu être trouvé » dans le service de calcul des taxes.
author: hangwan
ms.date: 03/25/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: hangwan
ms.search.validFrom: 03/23/2022
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: c1a343b0b74645d40b0a2582749968cc0a56afd7
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645417"
---
# <a name="no-matching-result-could-be-found"></a>Aucun résultat correspondant n’a pu être trouvé

[!include [banner](../includes/banner.md)]

Cette rubrique explique la procédure de résolution si vous recevez l’erreur « Aucun résultat correspondant n’a pu être trouvé » dans le service de calcul des taxes.

## <a name="symptom"></a>Problème

Vous recevez le message d’erreur suivant : "En-tête/Lignes – 1, Groupe de taxes, aucun résultat correspondant n’a pu être trouvé. »

```json
======================Tax service calculation result JSON:===========================
{
    "taxDocument": {
        "Header": [
            {
                "Lines": [
                    {
                        ...
                        "Errors": [
                            {
                                "Code": "TaxSetup20000",
                                "Message": "Header/Lines - 1, Tax group applicability, no matching result could be found."
                            }
                        ],
                        "Adjustment": null
                    }
                ],
                "Measures": {
                    ...
                },
                ...
            }
        ]
    },
    ...
}
```

## <a name="cause"></a>Cause

Le problème surviens quand la configuration de la fonctionnalité dans Regulatory Configuration Service (RCS) est incorrecte.

## <a name="troubleshoot"></a>Résolution des problèmes

1. Téléchargez le fichier de résolution des problèmes. Pour plus d’informations, voir la [Activation du mode débogage pour la résolution des problèmes](tcs-troubleshooting-enable-debug-mode.md).
2. Comparez l’entrée de calcul du service fiscal avec la configuration de la fonctionnalité pour résoudre le problème de configuration.

    L’exemple suivant montre l’entrée Calcul du service fiscal.

    ```json
    ===============================Tax service calculation input JSON:=====================================
    {
        "TaxableDocument": {
            "Header": [
                {
                    "Lines": [
                        {
                            ...
                        }
                    ],
                    "Business Process": "Sales",
                    "Ship From Zip Code": "30159",
                }
            ]
        },
        "Parameter": {
            ...
        },
        "Adjustment": {
            "Lines": {}
        }
    }
    ```

    Le tableau suivant répertorie l’applicabilité du groupe de taxes dans le RCS.

    | Processus Header.Business | Unité Lines.Business | Header.Ship En provenance du code postal | Groupe de taxes |
    |-------------------------|---------------------|---------------------------|-----------|
    | Journal                 |                     |                           | Groupe A   |
    | Vente                   |                     | 30160                     | Groupe B   |

    Selon l’entrée Calcul du service fiscal, la valeur **Processus commercial** sur l’en-tête est **Ventes**, et la valeur **Expédier depuis le code postal** sur l’en-tête est **30159**. Cette entrée est basée sur la configuration des règles d’applicabilité dans RCS. Parce qu’il n’y a pas de ligne correspondante, l’erreur se produit.

    > [!NOTE]
    > Si la valeur de la règle d’applicabilité est vide, la règle s’applique à n’importe quelle valeur.

## <a name="mitigation"></a>Atténuation

Pour résoudre l’erreur, procédez comme suit.

1. Dans RCS, accédez à **Fonctionnalités de mondialisation** \> **Calcul de la taxe**.
2. Créer une version de la fonctionnalité.
3. Ajoutez une ligne pour les informations correspondantes.

    | Processus Header.Business | Unité Lines.Business | Header.Ship En provenance du code postal| Groupe de taxes |
    |-------------------------|---------------------|--------------------------|-----------|
    | Journal                 |                     |                          | Groupe A   |
    | Vente                   |                     | 30160                    | Groupe B   |
    | Vente                   |                     | 30159                    | Groupe B   |

4. Publiez la version de configuration des fonctionnalités.
5. Dans Microsoft Dynamics 365 Finance, accédez à **Taxes** \> **Paramétrage** \> **Configuration de taxe** \> **Paramètres du calcul des taxes** et sélectionnez la nouvelle version.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
