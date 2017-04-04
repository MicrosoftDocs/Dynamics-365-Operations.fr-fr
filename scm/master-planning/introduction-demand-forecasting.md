---
title: "Vue d&quot;ensemble de prévision de la demande"
description: "La prévision de la demande est utilisée pour prévoir une demande indépendante des commandes client et une demande dépendante à n&quot;importe quel point de découplage pour les commandes client. Les règles avancées de réduction de prévision de la demande fournissent une solution idéale pour la personnalisation en masse."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72004
ms.assetid: 916707c9-1333-460f-a0fa-4e95f6fda2ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 9152616b81e7873426f296376b5e57c94439379d
ms.lasthandoff: 03/31/2017


---

# <a name="demand-forecasting-overview"></a>Vue d'ensemble de prévision de la demande

La prévision de la demande est utilisée pour prévoir une demande indépendante des commandes client et une demande dépendante à n'importe quel point de découplage pour les commandes client. Les règles avancées de réduction de prévision de la demande fournissent une solution idéale pour la personnalisation en masse.

Pour générer la prévision de base, une synthèse des transactions d'historique est transmise à un service Microsoft Azure Machine Learning qui est hébergé sur Azure. Comme ce service n'est pas partagé entre les utilisateurs, il peut être facilement personnalisé pour répondre aux exigences propres au secteur. Vous pouvez utiliser Dynamics 365 pour les opérations visualisent la prévision, permet d'ajuster la prévision, et afficher des indicateurs de performance clé (KPIs) sur la précision prévue.

## <a name="key-features-of-demand-forecasting"></a>Fonctions clé de la prévision de la demande
Voici certaines fonctionnalités principales de la prévisions de la demande :

-   Générer une prévision de base statistique basée sur des données historiques.
-   Utiliser un ensemble dynamique de dimensions de prévision.
-   Visualiser les tendances de la demande, les intervalles de confiance, et les ajustements de la prévision.
-   Autoriser l'utilisation de la prévision ajustée dans les processus de planification.
-   Supprimer les valeurs hors norme.
-   Créer des mesures de la précision de la prévision.

## <a name="major-themes-in-demand-forecasting"></a>Sujets principaux dans une prévision de la demande
Trois sujets principaux sont implémentés dans une prévision de la demande :

-   **Modularité** – La prévision de la demande est modulaire et facile à configurer. Vous pouvez faire tourner la fonctionnalité de commencer et en arrêt en modifiant la clé de configuration ** le commerce ** &gt; ** à la prévision de stock ** &gt; ** prévision de la demande **.
-   ** La réutilisation de la pile Microsoft ** – Microsoft a généré la plateforme de Machine Learning en février 2015. La Machine Learning, qui est désormais une partie de la Business Suite Analytique Microsoft Cortana, vous pouvez rapidement et facilement crée des expériences prévisionnelles d'analyse, telles que les expériences d'estimation de la demande, à l'aide de algorithmes R du ou python programmation des langues et une interface seul glisser-déplacer.
    -   Vous pouvez charger Dynamics 365 pour les expériences de prévision de la demande d'opérations, les modifier pour répondre aux besoins de l'entreprise, les publier en tant que service Web dans l'azur, et les utiliser pour générer des prévisions de la demande. Les expériences sont disponibles pour le téléchargement si vous avez acheté Dynamics 365 pour l'abonnement des opérations pour le responsable de production comme utilisateur au niveau de la société.
    -   Vous pouvez télécharger les expériences de prévision de la demande actuellement disponibles à partir de [Cortana Analytics Gallery](https://gallery.cortanaanalytics.com/). Bien que Dynamics 365 pour les expériences de prévision de la demande d'opérations sont automatiquement intégrés à Dynamics 365 pour les opérations, des clients et partenaires doivent gérer l'intégration des expériences qu'ils de téléchargement du [galerie d'Analytique de Cortana] (https://gallery.cortanaanalytics.com/). Par conséquent, expérience de [galerie d'Analytique de Cortana] (https://gallery.cortanaanalytics.com/) ne sont pas aussi simple à utiliser comme Dynamics 365 pour les expériences de prévision de la demande d'opérations. Vous devez modifier le code expériences de sorte qu'elles utilisent Dynamics 365 pour l'application Opérations (TAPI (API).
    -   Vous pouvez créer vos propres expériences dans Microsoft Azure Machine Learning Studio, les publier comme services sur Azure, puis les utiliser pour générer des prévisions de la demande.
    -   Si vous n'avez pas besoin d'une haute performance, ou de traiter un grand nombre de données, vous pouvez utiliser la rangée gratuite de Machine Learning. Il est recommandé de toujours démarrer à partir de cette rangée, en particulier lors des phases de mise en œuvre et de test. Si vous avez besoin d'une plus haute performance et d'un stockage supplémentaire, vous pouvez utiliser la rangée standard de Machine Learning. Cette rangée nécessite un abonnement à Azure et entraîne des frais supplémentaires. Pour plus d'informations sur la tarification de Machine Learning, voir <http://aka.ms/machine-learning-price-info>.
-   ** La réduction prévisionnelle au découplage pointent ** – La prévision de la demande dans Dynamics 365 pour les versions des opérations sur cette fonctionnalité, que vous pouvez prévoir la personne à charge et une demande indépendante au découplage pointent.

## <a name="basic-flow-in-demand-forecasting"></a>Flux de base dans une prévision de la demande
Le diagramme suivant illustre le flux de base dans une prévision de la demande. 

[Diagramme d'introduction de prévision de la demande![] (. /media/demand-forecasting-introduction.png)](. /media/demand-forecasting-introduction.png)

Démarre de génération de prévision de la demande dans Dynamics 365 pour les opérations. Les données transactionnelles historiques de Dynamics 365 pour la base de données transactionnelles d'opérations sont collectées et remplir table intermédiaire. Cette table intermédiaire ultérieurement est accordé à un service de Machine Learning. En effectuant la personnalisation minimale, vous pouvez de branche différentes sources de données à la table intermédiaire. Les sources de données peuvent inclure des fichiers Microsoft Excel, des fichiers virgule- séparés de (CSV) de valeur, puis des données de Microsoft Dynamics AX 2009 et Microsoft Dynamics AX 2012. Par conséquent, vous pouvez générer les prévisions de la demande qui considèrent les données historiques qui sont étalées entre les systèmes multiples. Toutefois, les données principales, telles que les noms d'article et les unités de mesure, doivent être identiques entre les différentes sources de données.

Si vous utilisez Dynamics 365 pour les expériences de Machine Learning de prévision de la demande d'opérations, ils recherchent un de l'ajustement normal parmi quatre méthodes de prévision de série chronologique pour calculer une prévision de base. Les paramètres pour ces méthodes de prévision sont gérés dans Dynamics 365 pour les opérations. 

Les prévisions, les données historiques, et toutes les modifications apportées aux prévisions de la demande dans des itérations précédentes sont alors disponibles dans Dynamics 365 pour les opérations. 

Vous pouvez utiliser Dynamics 365 pour les opérations visualisent et de modifier les prévisions de base. Les ajustements manuels doivent être autorisés pour pouvoir utiliser les prévisions pour la planification.

## <a name="limitations"></a>Limites
La prévision de la demande dans Dynamics 365 pour les opérations est un outil qui aide les clients dans le secteur de fabrication à créer des processus de prévisions. Elles permettent la fonctionnalité du noyau d'une solution de prévision de la demande et sont conçues pour qu'elles puissent être facilement étendues. La prévision de la demande ne peut pas être celle de l'ajustement normal pour les clients dans Secteurs tels que Vente au détail, Vente en gros, le stockage, le transport, ou d'autres services professionnels.

<a name="see-also"></a>Voir également :
--------

[Demand forecasting setup](demand-forecasting-setup.md)

[Generating a statistical baseline forecast](generate-statistical-baseline-forecast.md)

[Making manual adjustments to the baseline forecast](manual-adjustments-baseline-forecast.md)

[Authorizing the adjusted forecast](authorize-adjusted-forecast.md)

[Monitoring forecast accuracy](monitor-forecast-accuracy.md)

[Remove outliers from historical transaction data when calculating a demand forecast](remove-historical-outliers-calculating-demand-forecast.md)


