---
title: Gestion du cycle de vie des modèles (version préliminaire)
description: Cette rubrique décrit les moyens de gérer les modèles d’apprentissage automatique de votre organisation afin d’optimiser les prédictions qu’ils génèrent.
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 3daec03b7ba349d8f72863317e2d601a83417d58
ms.sourcegitcommit: e42c7dd495829b0853cebdf827b86a7cf655cf86
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/17/2021
ms.locfileid: "6638390"
---
# <a name="model-management-lifecycle-preview"></a>Gestion du cycle de vie des modèles (version préliminaire)

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les moyens de gérer les modèles d’apprentissage automatique de votre organisation afin d’optimiser les prédictions qu’ils génèrent.

Nous vous recommandons de former le modèle d’IA dans un environnement sandbox, puis d’utiliser des solutions gérées pour le déployer dans un environnement de production. Cette approche permet de garantir que les contrôles appropriés sont en place pour gérer le cycle de vie du modèle.

Étant donné que le modèle d’IA est basé sur la facture disponible et les données client, il est important que l’environnement sandbox dispose d’une copie récente des données de production. Vous pouvez commencer à entraîner votre modèle en suivant les étapes de [Utiliser les prédictions de paiement du client](use-customer-payment-predictions.md). Une fois le modèle recyclé, évaluez les résultats comme décrit dans [Évaluer le modèle de prédiction de paiement initial du client](evaluate-payment-prediction.md). Utilisez les informations dans [Améliorer le modèle de prédiction](improve-model.md) pour expérimenter des combinaisons de fonctionnalités et de filtres qui peuvent aider à améliorer le modèle.

Lorsque vous êtes satisfait des résultats de l’entraînement, suivez les étapes de [Distribuer votre modèle d’IA](https://docs.microsoft.com/ai-builder/distribute-model) pour faire passer le modèle dans votre environnement de production.
