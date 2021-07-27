---
title: Page d’accueil Informations financières (version préliminaire)
description: Informations financières fournit des modèles configurables et extensibles pour vous aider à prédire avec précision et intelligemment le flux de trésorerie de votre entreprise, à prédire quand vous recevrez le paiement des créances impayées et à générer une proposition de budget qui peut accélérer votre processus de budgétisation. Toutes ces fonctionnalités sont basées sur des modèles Machine Learning intelligents.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
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
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: f0d709ef81fd43c009bf36aba2d4be949b1a737c
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/03/2021
ms.locfileid: "6338227"
---
# <a name="finance-insights-home-page-preview"></a>Page d’accueil Informations financières (version préliminaire)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Informations financières fournit des modèles configurables et extensibles pour vous aider à prédire avec précision et intelligemment le flux de trésorerie de votre entreprise, à prédire quand vous recevrez le paiement des créances impayées et à générer une proposition de budget qui peut accélérer votre processus de budgétisation. Toutes ces fonctionnalités sont basées sur des modèles Machine Learning intelligents. Lorsque ces nouvelles fonctionnalités sont combinées à l’automatisation des paiements et des recouvrements des fournisseurs, elles fournissent un système financier riche et intelligent qui stimule la prise de décision et vous aide à prendre des mesures pour répondre efficacement aux défis commerciaux actuels et futurs.

> [!NOTE]
> La version préliminaire publique de Finance Insights est disponible pour le déploiements aux États-Unis, au Canada et au Royaume-Uni. Microsoft ajoute progressivement la prise en charge de plusieurs régions. Pour activer Finance Insights sur les environnements de production, les capacités [Exporter vers Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md) doivent d’abord être activées sur l’environnement de production.

> [!NOTE]
> Cette fonctionnalité est proposée sous la forme d’un ensemble de fonctions en version préliminaire. En tant que fonction en version préliminaire, vous ne devez pas utiliser les modèles de Machine Learning résultants pour piloter ou influencer vos décisions commerciales ou vos propositions de budget. Votre utilisation de cette fonctionnalité est régie par les [Conditions d’utilisation supplémentaires](https://go.microsoft.com/fwlink/?linkid=2105274).

## <a name="prerequisites"></a>Conditions préalables

Cette section répertorie les conditions requises pour utiliser Informations financières. Dans la mesure du possible, des liens vers des sources d’informations supplémentaires sont fournis.

### <a name="legal-requirements"></a>Configurations requises légales

Pour postuler au programme de version préliminaire, remplissez [l’accord de version préliminaire de Informations financières pour Dynamics 365 Finance](https://forms.office.com/FormsPro/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR56j8lZs0FdAvwT75_WNFyxUM1c0Uzc1RFpaU1RVTEwxVTNWUERPRThUSy4u).

### <a name="system-requirements"></a>Configuration requise

Un environnement de niveau 2 (multi-box) est requis pour la version préliminaire de Finance Insights. Pour plus d’informations générales sur les environnements, voir [Planification de l’environnement](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

### <a name="version-requirements"></a>Exigences relatives à la version

Ce document s’applique à la version 10.0.11 des applications Finance and Operations (Platform update 35) et versions ultérieures.

### <a name="historical-data-requirements"></a>Exigences en matière de données historiques

Au moins un an de factures client est nécessaire pour entraîner correctement le modèle Machine Learning utilisé pour la fonction de prédiction de paiement client.

### <a name="role-and-permission-requirements"></a>Exigences de rôle et d’autorisation

Des modifications seront apportées à Microsoft Dynamics 365 Finance, Microsoft Dynamics Lifecycle Services (LCS), Power Apps et Azure. Des autorisations correctes sont requises dans ces environnements. Voici quelques-uns des exemples de modifications qui seront effectuées :

- Un environnement sera créé dans Microsoft Power Platform.
- Un compte de stockage, un coffre de clés et une application seront créés dans Azure.
- L’administrateur du client Active Directory devra autoriser l’application AI Builder à accéder au lac de données.
- La fonctionnalité sera activée dans Dynamics 365.

Une connaissance du processus de création et de gestion des ressources dans Azure, Microsoft Dataverse et LCS vous sera utile pendant que vous terminez ce processus.

## <a name="configure-finance-insights"></a>Configurer Informations financières

Vous devez effectuer certaines étapes de configuration avant de pouvoir utiliser Informations financières. Pour plus d’informations sur la configuration de Informations financières, voir :
  - Pour les versions jusqu’à 10.0.19 : [Configuration de Finance Insights (version préliminaire) – versions jusqu’à 10.0.19](configure-for-fin-insites.md).
  - Pour les versions 10.0.20 et ultérieures : [Configuration de Informations financières (version prliminaire) – versions 10.0.20 et ultérieures](configure-for-fin-insites-PubPrvw.md).

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

La prévision intelligente des flux de trésorerie est construite sur la fonctionnalité de prévision des flux de trésorerie existante dans Dynamics 365 Finance. Pour revoir la capacité existante, voir [Prévisions de flux de trésorerie](../cash-bank-management/cash-flow-forecasting.md).

- Pour savoir comment les prédictions de paiement des clients peuvent fournir les informations nécessaires à des activités de collecte proactives, voir [Utiliser les prédictions de paiement des clients](use-customer-payment-predictions.md).
- Pour obtenir des informations qui peuvent vous aider à évaluer l’efficacité du modèle de prédiction une fois que vous avez commencé à utiliser la fonctionnalité, voir [Évaluer le modèle de prédiction de paiement client initial](evaluate-payment-prediction.md).
- Pour obtenir des informations qui peuvent vous aider à ajuster les données utilisées pour créer la prédiction et ainsi améliorer son efficacité, voir [Améliorer le modèle de prédiction](improve-model.md).

Pour en savoir plus sur les résultats des modèles de prédiction IA, voir [Résultats des modèles Machine Learning](confusion-matrix.md).

### <a name="using-cash-flow-forecasts"></a>Utilisation des prévisions des flux de trésorerie

La fonction de prévision des flux de trésorerie peut vous aider à estimer plus précisément votre position de trésorerie. 

- Pour en savoir plus sur les nouvelles fonctionnalités des prévisions de flux de trésorerie, voir [Prévisions de flux de trésorerie](cash-flow-forecast-intro.md).
- Pour plus d’informations sur l’importation de données externes à inclure dans vos prévisions de trésorerie, voir [Utiliser des données externes dans les prévisions de flux de trésorerie](external-data-in-cash-flow.md). 
- Pour plus d’informations sur l’utilisation d’un modèle d’IA pour projeter des flux de trésorerie à court terme, voir [Emplacement des disponibilités](cash-position.md).
- Pour plus d’informations sur l’enregistrement des positions de flux de trésorerie et des prévisions de flux de trésorerie sous forme d’instantanés, et pour comparer un instantané aux chiffres réels, voir [Présentation des instantanés](payment-snapshots.md).

### <a name="using-budget-proposal"></a>Utilisation de propositions de budget

Pour plus d’informations sur l’accélération de la création d’un budget, voir [Propositions budgétaires](budget-proposals.md). 

## <a name="feedback-and-support"></a>Commentaires et support

Veuillez envoyer un e-mail à [Informations sur les paiements des clients (aperçu)](mailto:fiap@microsoft.com) si vous souhaitez fournir des commentaires ou si vous avez besoin d’aide.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
