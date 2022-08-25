---
title: Synchroniser le paramétrage des taxes entre le service de calcul de la taxe et Dynamics 365 Finance
description: Cet article explique comment synchroniser les données principales de configuration des taxes du service de calcul des taxes avec Microsoft Dynamics 365 Finance.
author: EricWangChen
ms.date: 01/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.21
ms.custom: intro-internal
ms.search.form: TaxIntegration, TaxServiceParameters
ms.openlocfilehash: 315f2b27a64906ca0fc404d704d0b170dbfa48c5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283851"
---
# <a name="sync-the-tax-setup-from-the-tax-calculation-service-to-dynamics-365-finance"></a>Synchroniser le paramétrage des taxes entre le service de calcul de la taxe et Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

Cet article explique comment synchroniser les données principales de configuration des taxes du service de calcul des taxes avec Microsoft Dynamics 365 Finance.

Après avoir accompli les étapes de configuration requises dans [Mise en route du calcul de la taxe](global-get-started-with-tax-calculation-service.md), les données de configuration des taxes suivantes sont automatiquement synchronisées entre le service de calcul des taxes et Finance.

## <a name="sales-tax-code"></a>Code taxe de vente

| Service de calcul de la taxe           | Finance                             |
| --------------------------------- | ----------------------------------- |
| Code taxe                          | Code taxe de vente                      |
| Description                       | Name                                |
| Entrée utilisateur                        | Période de règlement                   |
| Entrée utilisateur                        | Groupe de validations dans la comptabilité                |
| Entrée utilisateur                        | Devise de taxe                  |
| Un taux de taxe négatif est configuré | Autoriser les pourcentages de taxe négatifs |

## <a name="tax-value"></a>Valeur de la taxe

| Service de calcul de la taxe | Finance                   |
| ----------------------- | ------------------------- |
| Date de début de la transaction   | Date de début                 |
| Date de fin de la transaction     | Au                   |
| Montant minimum          | Limite inférieure             |
| Montant maximal          | Limite maximale             |
| Taux de taxe                | Valeur                     |
| Taux non déductible     | Pourcentage non déductible |

## <a name="tax-limits"></a>Limites de taxe

| Service de calcul de la taxe | Finance           |
| ----------------------- | ----------------- |
| Date de début de la transaction   | Date de début         |
| Date de fin de la transaction     | Au           |
| Montant minimum de la taxe      | taxe minimum |
| Montant maximum de la taxe      | Taxe maximum |

## <a name="sales-tax-group"></a>Groupe de taxe de vente

| Service de calcul de la taxe                         | Finance                                    |
| ----------------------------------------------- | ------------------------------------------ |
| Groupe de taxes                                       | Groupe de taxe de vente                            |
| Codes taxe sous ce groupe de taxes                  | Codes taxe de vente sous ce groupe de taxes de vente |
| Le code taxe est marqué comme **Est exonéré**         | Exempté                                     |
| Le code taxe est marqué comme **Est exonéré**         | Code d’exonération                                |
| Le code taxe est marqué comme **Est une taxe au preneur** | Taxe au preneur                             |
| Le code taxe est marqué comme **Est une taxe d’utilisation**        | Taxe d’utilisation                                    |

## <a name="item-sales-tax-group"></a>Groupe de taxe d’article

| Service de calcul de la taxe             | Finance                                         |
| ----------------------------------- | ----------------------------------------------- |
| Groupe de taxe d’article                      | Groupe de taxe d’article                            |
| Codes taxe sous ce groupe de taxes d’article | Codes taxe de vente sous ce groupe de taxes de vente d’article |

Une fois la synchronisation terminée, continuez à gérer les paramètres restants dans Finance à des fins de validation et de génération d’états.

> [!NOTE]
> La synchronisation de la configuration des taxes entre Finance et le service de calcul des taxes n’est pas prise en charge. Pour un environnement Finance existant, créez d’abord la configuration des taxes dans le service de calcul des taxes. Ensuite, synchronisez les données de configuration avec l’environnement Finance.
