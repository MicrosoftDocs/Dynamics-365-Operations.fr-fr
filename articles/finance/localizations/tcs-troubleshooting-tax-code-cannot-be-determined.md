---
title: Le code fiscal ne peut pas être déterminé
description: Cette rubrique explique comment résoudre l’erreur « Le code fiscal ne peut pas être déterminé » dans le service de calcul des taxes.
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
ms.openlocfilehash: 3c0914f0013ad2de61cd5a59e3092fef149742e4
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645402"
---
# <a name="tax-code-cannot-be-determined"></a>Le code fiscal ne peut pas être déterminé

[!include [banner](../includes/banner.md)]

Cette rubrique explique la procédure de résolution si vous recevez l’erreur « Le code fiscal ne peut pas être déterminé » dans le service de calcul des taxes.

## <a name="symptom"></a>Problème

Vous recevez le message d’erreur suivant : "En-tête/Lignes – 1, le code fiscal ne peut pas être déterminé". Vous pouvez également rechercher l’erreur dans le fichier de résolution des problèmes, comme illustré dans l’exemple suivant. Pour plus d’informations, voir la [Activation du mode débogage pour la résolution des problèmes](tcs-troubleshooting-enable-debug-mode.md).

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
                                "Code": "TaxSetup20001",
                                "Message": "Header/Lines - 1, tax code cannot be determined."
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

Le problème survient probablement parce que le groupe de taxe et le groupe de taxe de l’article ne se croisent pas.

## <a name="troubleshoot"></a>Résolution des problèmes

Pour résoudre des problèmes, procédez comme suit.

1. Dans le fichier de résolution des problèmes, vérifiez que le groupe de taxes et le groupe de taxes de l’article ont été déterminés. Si les valeurs de **Groupe fiscal** et **Groupe de taxe sur l’article** sont vides, le groupe de taxe et le groupe de taxe de l’article n’ont pas été déterminés. S’ils ont été déterminés, les résultats peuvent être incorrects.

    Voici un exemple d’un fichier de résolution des problèmes.

    ```json
    ======================Tax service calculation result JSON:===========================
    {
        "taxDocument": {
            "Header": [
                {
                    "Lines": [
                        {
                            "Tax Codes": {},
                            "Measures": {
                                "Tax Group": "Group A",
                                "Item Tax Group": "Group B"
                            },
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

2. Vérifiez que l’option **Remplacer la taxe de vente** sur l’onglet **Installer** des détails de ligne de commande client est activé.

    - S’il est activé, les codes de taxe sont déterminés par les valeurs **Groupe fiscal** et **Groupe de taxe de l’article** que vous entrez sur la ligne de transaction. Vérifiez que ces valeurs sont saisies correctement.
    - S’il n’est pas activé, vérifiez que les valeurs correctes ont été définies pour les champs **Applicabilité du groupe fiscal** et **Applicabilité du groupe de taxe de l’article**. Pour plus d’informations, voir [Aucun résultat correspondant n’a été trouvé](tcs-troubleshooting-no-matching-result.md).

3. Si le groupe de taxes et le groupe de taxes de l’article ont été déterminés correctement, déterminez s’il existe une intersection pour eux.

    1. Dans RCS, allez à **Fonctionnalités fiscales** \> **Codes fiscaux et groupes** \> **Groupe de taxe**.

        | Groupe Line.Tax | Codes taxe |
        |----------------|-----------|
        | Groupe A        | A         |

    2. Allez à **Fonctionnalités fiscales** \> **Codes fiscaux et groupes** \> **Groupe de taxe d’article**.

        | Groupe de taxe Line.Item | Codes taxe |
        |---------------------|-----------|
        | Groupe B             | B         |

    S’il n’y a pas d’intersection pour le groupe de taxe et le groupe de taxe de l’article, le code de taxe ne sera pas déterminé.

## <a name="mitigation"></a>Atténuation

1. Passez par chaque étape de la section [Résoudre des problèmes](#troubleshoot) de cette rubrique et corrigez la configuration si nécessaire. Si le groupe de taxe et le groupe de taxe de l’article n’ont pas été déterminés correctement, voir [Aucun résultat correspondant n’a été trouvé](tcs-troubleshooting-no-matching-result.md).
2. S’il n’y a pas d’intersection pour le groupe de taxes et le groupe de taxes de l’article, créez une version de fonctionnalité dans RCS et corrigez la configuration.

    - Allez à **Fonctionnalités fiscales** \> **Codes fiscaux et groupes** > **Groupe de taxe d’article**.

        | Groupe de taxe Line.Item | Codes taxe |
        |---------------------|-----------|
        | Groupe B             | A;B       |

    Le code fiscal sera déterminé comme **A**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
