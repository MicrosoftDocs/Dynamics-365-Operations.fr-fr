---
title: Page d’accueil de Finance Insights
description: Informations financières fournit des modèles configurables et extensibles pour vous aider à prédire avec précision et intelligemment le flux de trésorerie de votre entreprise, à prédire quand vous recevrez le paiement des créances impayées et à générer une proposition de budget qui peut accélérer votre processus de budgétisation. Toutes ces fonctionnalités sont basées sur des modèles Machine Learning intelligents.
author: ShivamPandey-msft
ms.date: 01/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 05b0de8b0104238a33f006234d4a0e8ba9fcdb2a
ms.sourcegitcommit: 7893ffb081c36838f110fadf29a183f9bdb72dd3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/02/2022
ms.locfileid: "8087291"
---
# <a name="finance-insights-home-page"></a>Page d’accueil de Finance Insights

[!include [banner](../includes/banner.md)]

Finance Insights fournit des solutions configurables et extensibles pour vous aider à prédire avec précision et intelligemment le flux de trésorerie de votre entreprise, à prédire quand vous recevrez le paiement des créances impayées et à générer une proposition de budget qui peut accélérer votre processus de budgétisation. Ces fonctionnalités utilisent des modèles d’apprentissage automatique intelligents pour créer des modèles à l’aide des données que vous fournissez (y compris les données d’un tiers telles que les informations de rapport sur les consommateurs d’un bureau). Ces capacités intelligentes éclairent la prise de décision et vous aident à prendre des mesures pour répondre efficacement aux défis commerciaux actuels et futurs. Vous êtes responsable de toutes les données utilisées avec ou issues de Finance Insights.

> [!NOTE]
> Finance Insights est disponible pour le déploiements aux États-Unis, au Canada, au Royaume-Uni, en Europe, en Asie-Pacifique, au Japon, en Australie et en Nouvelle-Zélande. Microsoft ajoute progressivement la prise en charge de plusieurs régions.

## <a name="prerequisites"></a>Conditions préalables

Cette section répertorie les conditions requises pour utiliser Informations financières. Dans la mesure du possible, des liens vers des sources d’informations supplémentaires sont fournis.

### <a name="system-requirements"></a>Configuration requise

Un environnement de niveau 2 (multi-box) est requis pour la version préliminaire de Finance Insights. Pour plus d’informations générales sur les environnements, voir [Planification de l’environnement](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

### <a name="version-requirements"></a>Exigences relatives à la version

Cette rubrique s’applique à Microsoft Dynamics 365 Finance version 10.0.21 et versions ultérieures.

### <a name="license-requirements"></a>Conditions préalables requises pour les licences

Finance Insights utilise les crédits AI Builder pour créer des prévisions financières. Toutes les licences nécessaires pour cela sont incluses avec la licence client. Chaque client Dynamics 365 Finance se voit recevoir 20 000 crédits AI Builder chaque mois. Si des crédits supplémentaires sont nécessaires pour les besoins de l’entreprise, ils peuvent être achetés directement auprès d’AI Builder.

### <a name="historical-data-requirements"></a>Exigences en matière de données historiques

Au moins un an de factures client est nécessaire pour entraîner correctement le modèle Machine Learning utilisé pour la fonction de prédiction de paiement client. Trois ans de données historiques sont recommandés pour les prévisions de trésorerie. Trois ans de budget historique et/ou de chiffres réels sont recommandés pour des propositions de budget intelligentes.

## <a name="configure-finance-insights"></a>Configurer Informations financières

Vous devez effectuer les étapes de configuration avant de pouvoir utiliser Finance Insights. Pour plus d’informations sur la configuration de Finance Insights, voir [Configuration de Finance Insights](configure-for-fin-insites.md).

## <a name="create-a-data-integrator-project"></a>Créer un projet d’intégrateur de données

Vous devrez créer un projet d’intégrateur de données afin que les données générées par le modèle Machine Learning puissent circuler Dynamics 365 Finance. Pour connaître les étapes de création de ce projet, voir [Créer un projet d’intégrateur de données](create-data-integrate-project.md).

## <a name="enable-finance-insights-capabilities"></a>Activer les fonctionnalités de Informations financières

Lorsque vous avez terminé les étapes de configuration et configuré les données de démonstration, vous devez activer et configurer chaque fonctionnalité que vous prévoyez d’utiliser : prévisions de paiement client, prévision de flux de trésorerie et propositions de budget.

### <a name="enable-customer-payment-predictions"></a>Activer les prédictions de paiement des clients
Si vous utilisez des données de démonstration pour tester les prédictions de paiement des clients, vous devrez peut-être importer des données de démonstration supplémentaires pour créer votre modèle d’IA avec succès. 

Pour activer les prédictions de paiement des clients, vous devez suivre un ensemble d’étapes pour créer un modèle Machine Learning qui utilise les données de votre organisation pour générer des prédictions sur le moment où les clients sont susceptibles de payer des factures impayées et sur le moment où des factures spécifiques sont susceptibles d’être payées. Pour plus d’informations et les étapes spécifiques à suivre, voir [Activer les prédictions de paiement des clients](enable-cust-paymnt-prediction.md). 

### <a name="enable-cash-flow-forecasting"></a>Activer la prévision des flux de trésorerie
Pour activer les prévisions de flux de trésorerie, vous devez suivre un ensemble d’étapes pour créer un modèle Machine Learning qui utilise les données de votre organisation pour générer des prévisions de flux de trésorerie. Pour plus d’informations et les étapes spécifiques à suivre, voir [Activer la prévision de trésorerie](enable-cash-flow-forecasting.md).

### <a name="enable-budget-proposals"></a>Activer les propositions de budget

La fonctionnalité de propositions de budget utilise un modèle Machine Learning avec les données historiques de votre organisation pour générer une proposition de budget. La proposition générée peut vous aider à démarrer un processus de budgétisation qui est plus efficace et efficient qu’un processus manuel. Pour connaître les étapes spécifiques permettant d’activer cette fonctionnalité, voir [Activer les propositions de budget](enable-budget-proposal.md). 

## <a name="using-finance-insights-features"></a>Utilisation des fonctionnalités de Informations financières

### <a name="using-customer-payment-predictions"></a>Utilisation des prédictions de paiement des clients

- Pour savoir comment les prédictions de paiement des clients peuvent fournir les informations obligatoires pour commencer des activités de collecte proactives, voir [Utiliser les prédictions de paiement des clients](use-customer-payment-predictions.md).
- Pour obtenir des informations qui peuvent vous aider à évaluer l’efficacité du modèle de prédiction une fois que vous avez commencé à utiliser la fonctionnalité, voir [Évaluer le modèle de prédiction de paiement client initial](evaluate-payment-prediction.md).
- Pour obtenir des informations qui peuvent vous aider à ajuster les données utilisées pour créer la prédiction et ainsi améliorer son efficacité, voir [Améliorer le modèle de prédiction](improve-model.md).
- Pour en savoir plus sur les résultats des modèles de prédiction IA, voir [Résultats des modèles Machine Learning](confusion-matrix.md).

### <a name="using-cash-flow-forecasts"></a>Utilisation des prévisions des flux de trésorerie

La fonction de prévision des flux de trésorerie peut vous aider à estimer plus précisément votre position de trésorerie. La prévision intelligente des flux de trésorerie est basée sur la fonctionnalité de prévision des flux de trésorerie existante dans Dynamics 365 Finance. Pour revoir la capacité existante, voir [Prévisions de flux de trésorerie](../cash-bank-management/cash-flow-forecasting.md).

- Pour en savoir plus sur les nouvelles fonctionnalités des prévisions de flux de trésorerie, voir [Prévisions de flux de trésorerie](cash-flow-forecast-intro.md).
- Pour plus d’informations sur l’importation de données externes à inclure dans vos prévisions de trésorerie, voir [Utiliser des données externes dans les prévisions de flux de trésorerie](external-data-in-cash-flow.md). 
- Pour plus d’informations sur l’utilisation d’un modèle d’IA pour projeter des flux de trésorerie à court terme, voir [Emplacement des disponibilités](cash-position.md).
- Pour plus d’informations sur l’enregistrement des positions de flux de trésorerie et des prévisions de flux de trésorerie sous forme d’instantanés, et pour comparer un instantané aux chiffres réels, voir [Présentation des instantanés](payment-snapshots.md).

### <a name="using-budget-proposal"></a>Utilisation de propositions de budget

Pour plus d’informations sur l’accélération de la création d’un budget, voir [Propositions budgétaires](budget-proposals.md). 

## <a name="feedback-and-support"></a>Commentaires et support

Si vous souhaitez fournir des commentaires ou si vous avez besoin d’aide, envoyez un e-mail à [Finance Insights](mailto:fiap@microsoft.com).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
