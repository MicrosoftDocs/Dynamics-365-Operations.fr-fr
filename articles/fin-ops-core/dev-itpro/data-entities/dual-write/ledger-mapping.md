---
title: Comptabilité intégrée
description: Cet article décrit l’intégration des données de comptabilité entre les applications de finances et d’opérations et d’autres applications Dynamics 365 avec Dataverse.
author: RamaKrishnamoorthy
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 728c131c260586e7f1f787f22ccf02ed81c94c01
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289146"
---
# <a name="integrated-ledger"></a>Comptabilité intégrée

[!include [banner](../../includes/banner.md)]



Dans une application d’entreprise, les données de comptabilité définissent la configuration de base pour le mode de fonctionnement d’une entreprise. Par exemple, les données de comptabilité décrivent l’exercice que suit la société, les devises qu’elle traite et les comptes qu’elle utilise. Cet article décrit l’intégration de ces données financières de base.

## <a name="templates"></a>Modèles

Les données comptables comprennent un ensemble de mappages de tables financières de base qui fonctionnent ensemble pendant l’interaction des données client, comme indiqué dans le tableau suivant.

Applications de finances et d’opérations | Applications Customer Engagement     | Description
---------------------------------|----------------------------------|------------
[Taux de change CDS](mapping-reference.md#123) | msdyn_currencyexchangerates |
[Plan comptable](mapping-reference.md#121) | msdyn_chartofaccountses |
[Devises](mapping-reference.md#218) | transactioncurrencies |
[Taux de change entre les deux devises](mapping-reference.md#122) | msdyn_currencyexchangeratepairs |
[Type de taux de change](mapping-reference.md#129) | msdyn_exchangeratetypes |
[Format de dimension financière](mapping-reference.md#130) | msdyn_financialdimensionformats |
[Dimensions financières](mapping-reference.md#128) | msdyn_dimensionattributes |
[Entité Intégration du calendrier fiscal](mapping-reference.md#132) | msdyn_fiscalcalendars |
[Période de calendrier fiscal](mapping-reference.md#131) | msdyn_fiscalcalendarperiods |
[Entité Intégration de l’exercice de calendrier fiscal](mapping-reference.md#133) | msdyn_fiscalcalendaryears |
[Registre](mapping-reference.md#148) | msdyn_ledgers |
[Compte principal](mapping-reference.md#152) | msdyn_mainaccounts |
[Catégories de compte principal](mapping-reference.md#151) | msdyn_mainaccountcategories |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

