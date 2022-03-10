---
title: Prédictions de paiement des clients
description: Cette rubrique décrit la fonctionnalité de prédiction de paiement qui peut vous aider à mieux comprendre les pratiques de paiement typiques d’un client. Cette fonctionnalité peut également vous aider à identifier les circonstances qui devraient vous amener à démarrer les processus de collecte plus tôt que vous ne pourriez les démarrer autrement.
author: ShivamPandey-msft
ms.date: 11/03/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 04897e3a7765264ab2e664422caa928c49b9cc61
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2022
ms.locfileid: "7982035"
---
# <a name="customer-payment-predictions"></a>Prédictions de paiement des clients

[!include [banner](../includes/banner.md)]

Cette rubrique décrit la fonctionnalité de prédiction de paiement qui peut vous aider à mieux comprendre les pratiques de paiement typiques d’un client. Cette fonctionnalité peut également vous aider à identifier les circonstances qui devraient vous amener à démarrer les processus de collectes plus tôt que vous ne pourriez les démarrer autrement.

## <a name="overview"></a>Vue d’ensemble

Les organisations trouvent souvent difficiles de prévoir quand les clients paieront leurs factures. Ce manque d’informations peut entraîner les problèmes suivants :

- Prévisions de flux de trésorerie moins précises
- Processus de collectes qui commencent trop tard
- Commandes qui sont validées pour les clients qui pourraient manquer à leur paiement

Les prédictions de paiement client aident les organisations à prédire quand une facture client sera payée. Par conséquent, ils peuvent créer des stratégies de recouvrement qui contribuent à augmenter la probabilité qu’ils soient payés à temps.

## <a name="predictions"></a>Prédictions

Les prévisions de paiement permettent aux entreprises d’améliorer leurs processus d’entreprise en les aidant à identifier les factures susceptibles d’être payées en retard. L’organisation peut utiliser ces informations pour prendre des mesures qui améliorent les chances d’être payé à temps.

La fonctionnalité de prédiction de paiement client utilise un modèle Machine Learning pour prédire plus précisément quand un client paiera une facture impayée. Ce modèle Machine Learning comprend des factures historiques, des paiements et des données client.

Pour chaque facture ouverte, la fonctionnalité attribue trois probabilités de paiement :

- La probabilité que le paiement soit effectué à temps
- La probabilité que le paiement soit effectué tard
- La probabilité que le paiement soit effectué très tard

La fonction fournit également une vue agrégée des paiements attendus.

[![Vue cumulée des prévisions de paiement.](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)

Chaque facture se voit attribuer une probabilité de paiement dans les temps. Les factures dont la probabilité de paiement dans les temps est inférieure à 50 pourcent sont marquées avec un cercle rouge pour indiquer qu’elles peuvent nécessiter de l’attention de la part de l’agent de recouvrement.

[![Liste des probabilités de paiement.](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)

La fonction de prédiction de paiement client fournit également des informations contextuelles pour expliquer la prédiction. Ces informations comprennent les principaux facteurs qui ont influencé la prévision, l’état actuel des affaires avec le client et des détails sur le comportement de paiement historique du client.

Dans de nombreuses entreprises, le processus de recouvrement a été une activité réactive. En d’autres termes, le processus de recouvrement ne démarre que lorsque les factures sont dues. Les prédictions de paiement du client permet aux organisations d’être plus proactives en matière de recouvrement. Elles ne doivent plus avoir à attendre qu’une transaction soit échue pour lancer le processus de recouvrement. Au contraire, elles peuvent utiliser la fonctionnalité de prévisions de paiement afin de déterminer si le recouvrement proactif améliorera la probabilité d’être payées dans les temps.

## <a name="methodology"></a>Méthodologie

Dans le passé, il était généralement difficile de développer et de déployer une solution d’intelligence artificielle (IA). Le processus nécessitait une équipe incluant des scientifiques des données, des experts en la matière et des ingénieurs, collaborant pendant un temps donné pour formuler, développer, déployer et mettre à jour une solution IA utilisable. Les prédictions de paiement client facilitent le déploiement et l’utilisation d’une solution d’IA dans Microsoft Dynamics 365 Finance. Microsoft pré-emballe des solutions IA dans Finance qui sont intégrées dans Microsoft AI Builder. Par conséquent, les utilisateurs peuvent déployer la solution d’IA en un seul clic pour profiter des avantages des prédictions intelligentes. Si vous n’êtes pas satisfait de la précision des prévisions, un utilisateur autorisé (à nouveau d’un simple clic) peut saisir l’expérience d’extension AI Builder et sélectionner ou effacer les champs utilisés pour générer les prévisions. Lorsque vous êtes prêt, vous pouvez "entraîner" le modèle et publier les modifications. Le modèle nouvellement formé sera automatiquement sélectionné pour générer les prédictions dans Dynamics 365 Finance.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
