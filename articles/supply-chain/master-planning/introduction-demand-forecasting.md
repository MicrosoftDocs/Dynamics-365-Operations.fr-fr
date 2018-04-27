---
title: "Vue d'ensemble de la prévision de la demande"
description: "La prévision de la demande est utilisée pour prévoir une demande indépendante des commandes client et une demande dépendante à n'importe quel point de découplage pour les commandes client. Les règles améliorées de réduction de prévision de la demande fournissent une solution idéale pour la personnalisation collective."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 72004
ms.assetid: 916707c9-1333-460f-a0fa-4e95f6fda2ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 18ed011fa1c1aa35b4a401d51bffc6af19395577
ms.openlocfilehash: 6a0455c5d86f953e270501a7f1648f7700f717d0
ms.contentlocale: fr-fr
ms.lasthandoff: 02/13/2018

---

# <a name="demand-forecasting-overview"></a>Vue d'ensemble de la prévision de la demande

[!INCLUDE [banner](../includes/banner.md)]

La prévision de la demande est utilisée pour prévoir une demande indépendante des commandes client et une demande dépendante à n'importe quel point de découplage pour les commandes client. Les règles améliorées de réduction de prévision de la demande fournissent une solution idéale pour la personnalisation collective.

Pour générer la prévision de base, une synthèse des transactions d'historique est transmise à un service Microsoft Azure Machine Learning qui est hébergé sur Azure. Comme ce service n'est pas partagé entre les utilisateurs, il peut être facilement personnalisé pour répondre aux exigences propres au secteur. Vous pouvez utiliser Finance and Operations pour visualiser la prévision, régler la prévision, et afficher des indicateurs de performance clés (KPI) sur la précision de la prévision.

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

-   **Modularité** – La prévision de la demande est modulaire et facile à configurer. Vous pouvez activer ou désactiver la fonctionnalité en modifiant la clé de configuration dans **Commerce** &gt; **Prévision de stock** &gt; **Prévision de la demande**.
-   **Réutilisation de la pile Microsoft** – Microsoft a lancé la plateforme Machine Learning en février 2015. Machine Learning, qui fait désormais partie de Microsoft Cortana Analytics Suite, vous permet de créer rapidement et facilement des expériences d'analyse prévisionnelles, telles que des expériences d'estimation de la demande, à l'aide des langages de programmation d'algorithmes R ou Python et d'une interface de glisser-déplacer simple.
    -   Vous pouvez télécharger les expériences de prévision de la demande de Finance and Operations, les modifier pour répondre à vos exigences métier, les publier comme service Web sur Azure, puis les utiliser pour générer des prévisions de la demande. Les expériences sont téléchargeables si vous avez acheté un abonnement à Finance and Operations pour un responsable de production utilisateur au niveau de l'entreprise.
    -   Vous pouvez télécharger les expériences de prévision de la demande actuellement disponibles à partir de [Cortana Analytics Gallery](https://gallery.cortanaanalytics.com/). Étant donné que les expériences de prévision de la demande de Finance and Operations sont automatiquement intégrées à Finance and Operations, les partenaires et clients doivent gérer l'intégration des expériences qu'ils téléchargent à partir de [Cortana Analytics Gallery](https://gallery.cortanaanalytics.com/). Par conséquent, les expériences de [Cortana Analytics Gallery](https://gallery.cortanaanalytics.com/) ne sont pas aussi simples à utiliser que les expériences de prévision de la demande de Finance and Operations. Vous devez modifier le code des expériences de sorte qu'elles utilisent l'interface de programmation d'applications (API) de Finance and Operations.
    -   Vous pouvez créer vos propres expériences dans Microsoft Azure Machine Learning Studio, les publier comme services sur Azure, puis les utiliser pour générer des prévisions de la demande.
    -   Si vous n'avez pas besoin d'une haute performance, ou de traiter un grand nombre de données, vous pouvez utiliser la rangée gratuite de Machine Learning. Il est recommandé de toujours démarrer à partir de cette rangée, en particulier lors des phases de mise en œuvre et de test. Si vous avez besoin d'une plus haute performance et d'un stockage supplémentaire, vous pouvez utiliser la rangée standard de Machine Learning. Cette rangée nécessite un abonnement à Azure et entraîne des frais supplémentaires. Pour plus d'informations sur la tarification de Machine Learning, voir <http://aka.ms/machine-learning-price-info>.
-   **Réduction des prévisions à n'importe quel point de découplage** – La prévision de la demande dans Finance and Operations s'appuie sur cette fonction, qui vous permet de prévoir à la fois la demande dépendante et indépendante à n'importe quel point de découplage.

## <a name="basic-flow-in-demand-forecasting"></a>Flux de base dans une prévision de la demande
Le diagramme suivant illustre le flux de base dans une prévision de la demande. 

[![diagramme d'introduction de la prévision de la demande](./media/demand-forecasting-introduction.png)](./media/demand-forecasting-introduction.png)

La génération de la prévision de la demande commence dans Finance and Operations. Les données transactionnelles historiques de la base de données transactionnelle de Finance and Operations sont collectées et remplissent une table intermédiaire. Cette table intermédiaire est ultérieurement fournie à un service Machine Learning. En effectuant une personnalisation minimale, vous pouvez raccorder diverses sources de données à la table intermédiaire. Les sources de données peuvent inclure des fichiers Microsoft Excel, des fichiers de valeurs séparées par des virgules (CSV) et des données de Microsoft Dynamics AX 2009 et Microsoft Dynamics AX 2012. Par conséquent, vous pouvez générer des prévisions de la demande qui considèrent un historique des données réparti entre plusieurs systèmes. Toutefois, les données principales, telles que les noms d'article et les unités de mesure, doivent être identiques entre les différentes sources de données.

Si vous utilisez les expériences de prévision de demande Finance and Operations de Machine Learning, elles recherchent un ajustement entre cinq méthodes de prévision de l'algorithme pour calculer une prévision de base. Les paramètres pour ces modes de prévision sont gérés dans Finance and Operations. 

Les prévisions, les données historiques et toutes les modifications apportées aux prévisions de la demande dans des itérations précédentes sont ensuite disponibles dans Finance and Operations. 

Vous pouvez utiliser Finance and Operations pour visualiser et modifier les prévisions de base. Les ajustements manuels doivent être autorisés pour pouvoir utiliser les prévisions pour la planification.

## <a name="limitations"></a>Limites
La prévision de la demande dans Finance and Operations est un outil qui permet aux clients de l'industrie de fabrication de créer des processus de prévision. Elle offre les principales fonctionnalités d'une solution de prévision de la demande et est conçue de façon à pouvoir être facilement étendue. Il se peut que la prévision de la demande ne convienne pas aux clients des secteurs tels que la vente au détail, la vente en gros, le stockage, le transport ou d'autres services professionnels.

<a name="see-also"></a>Voir également :
--------

[Paramétrage de la prévision de la demande](demand-forecasting-setup.md)

[Génération de prévisions de base statistiques](generate-statistical-baseline-forecast.md)

[Effectuer des ajustements manuels sur la prévision de base](manual-adjustments-baseline-forecast.md)

[Autorisation de la prévision ajustée](authorize-adjusted-forecast.md)

[Surveillance de la précision de la prévision](monitor-forecast-accuracy.md)

[Supprimer les valeurs hors norme des données de transaction historiques lors du calcul d'une prévision de la demande](remove-historical-outliers-calculating-demand-forecast.md)

[Prolonger la fonctionnalité de prévision de la demande](https://www.youtube.com/watch?v=4OIKIXLiNjI&feature=youtu.be)




