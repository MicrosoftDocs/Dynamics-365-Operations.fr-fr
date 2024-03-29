---
title: Modéliser le cycle de vie de gestion
description: Cet article décrit les moyens de gérer les modèles d’apprentissage automatique de votre organisation afin d’optimiser les prédictions qu’ils génèrent.
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 526916929e4bc079f9cea82d8ea9f80813e89b83
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880872"
---
# <a name="model-management-lifecycle"></a>Modéliser le cycle de vie de gestion

[!include [banner](../includes/banner.md)]

Cet article décrit les moyens de gérer les modèles d’apprentissage automatique de votre organisation afin d’optimiser les prédictions qu’ils génèrent.

Nous vous recommandons de former le modèle d’IA dans un environnement sandbox, puis d’utiliser des solutions gérées pour le déployer dans un environnement de production. Cette approche permet de garantir que les contrôles appropriés sont en place pour gérer le cycle de vie du modèle.

Étant donné que le modèle d’IA est basé sur la facture disponible et les données client, il est important que l’environnement sandbox dispose d’une copie récente des données de production. Vous pouvez commencer à entraîner votre modèle en suivant les étapes de [Utiliser les prédictions de paiement du client](use-customer-payment-predictions.md). Une fois le modèle recyclé, évaluez les résultats comme décrit dans [Évaluer le modèle de prédiction de paiement initial du client](evaluate-payment-prediction.md). Utilisez les informations dans [Améliorer le modèle de prédiction](improve-model.md) pour expérimenter des combinaisons de fonctionnalités et de filtres qui peuvent aider à améliorer le modèle.

Lorsque vous êtes satisfait des résultats de l’entraînement, suivez les étapes de [Distribuer votre modèle d’IA](/ai-builder/distribute-model) pour faire passer le modèle dans votre environnement de production.
