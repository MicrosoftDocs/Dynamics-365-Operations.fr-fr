---
title: Vue d'ensemble de la prévision de la demande
description: La prévision de la demande est utilisée pour prévoir une demande indépendante des commandes client et une demande dépendante à n'importe quel point de découplage pour les commandes client. Les règles améliorées de réduction de prévision de la demande fournissent une solution idéale pour la personnalisation collective.
author: roxanadiaconu
manager: tfehr
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72004
ms.assetid: 916707c9-1333-460f-a0fa-4e95f6fda2ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 27aa2b7a3d595fadfc1af969e45975e95322812f
ms.sourcegitcommit: 3895279cc5c1cf4826143d2ccb95ccceccb0a3c2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2021
ms.locfileid: "5081365"
---
# <a name="demand-forecasting-overview"></a>Vue d'ensemble de la prévision de la demande

[!include [banner](../includes/banner.md)]

La prévision de la demande est utilisée pour prévoir une demande indépendante des commandes client et une demande dépendante à n'importe quel point de découplage pour les commandes client. Les règles améliorées de réduction de prévision de la demande fournissent une solution idéale pour la personnalisation collective.

Pour générer la prévision de base, une synthèse des transactions d'historique est transmise à Microsoft Azure Machine Learning hébergé sur Azure. Comme ce service n'est pas partagé entre les utilisateurs, il peut être facilement personnalisé pour répondre aux exigences propres au secteur. Vous pouvez utiliser Supply Chain Management pour visualiser la prévision, régler la prévision, et afficher des indicateurs de performance clés (KPI) sur la précision de la prévision.

> [!NOTE]
> Microsoft Azure Machine Learning Studio (classique) est nécessaire pour la génération de prévisions avec Machine Learning. À compter de janvier 2021, il est disponible à l'Est du Japon, au centre-sud des États-Unis, en Asie du Sud-Est, au centre-ouest des États-Unis et en Europe de l'Ouest. Pour obtenir des informations mises à jour sur la disponibilité actuelle, voir [Produits Azure par région.](https://azure.microsoft.com/global-infrastructure/services/?regions=all&products=machine-learning-studio)

## <a name="key-features-of-demand-forecasting"></a>Fonctions clé de la prévision de la demande

Voici certaines fonctionnalités principales de la prévisions de la demande :

- Générer une prévision de base statistique basée sur des données historiques.
- Utiliser un ensemble dynamique de dimensions de prévision.
- Visualiser les tendances de la demande, les intervalles de confiance, et les ajustements de la prévision.
- Autoriser l'utilisation de la prévision ajustée dans les processus de planification.
- Supprimer les valeurs hors norme.
- Créer des mesures de la précision de la prévision.

## <a name="major-themes-in-demand-forecasting"></a>Sujets principaux dans une prévision de la demande

Trois sujets principaux sont implémentés dans une prévision de la demande :

- **Modularité** – La prévision de la demande est modulaire et facile à configurer. Vous pouvez activer ou désactiver la fonctionnalité en modifiant la clé de configuration dans **Commerce** &gt; **Prévision de stock** &gt; **Prévision de la demande**.
- **Réutilisation de la pile Microsoft** – Le Machine Learning, qui fait désormais partie de Microsoft Cortana Analytics Suite, vous permet de créer rapidement et facilement des expériences d'analyse prévisionnelles, telles que des expériences d'estimation de la demande, à l'aide des langages de programmation d'algorithmes R ou Python et d'une interface de glisser-déplacer simple.
  - Vous pouvez télécharger les expériences de prévision de la demande, les modifier pour répondre à vos exigences métier, les publier comme service Web sur Azure, puis les utiliser pour générer des prévisions de la demande. Les expériences sont téléchargeables si vous avez acheté un abonnement à Supply Chain Management pour un responsable de production utilisateur au niveau de l'entreprise.
  - Vous pouvez télécharger les expériences de prévision de la demande actuellement disponibles à partir de [Cortana Analytics Gallery](https://gallery.cortanaanalytics.com/). Étant donné que les expériences de prévision de la demande sont automatiquement intégrées à Supply Chain Management, les partenaires et clients doivent gérer l'intégration des expériences qu'ils téléchargent à partir de [Cortana Analytics Gallery](https://gallery.cortanaanalytics.com/). Par conséquent, les expériences de [Cortana Analytics Gallery](https://gallery.cortanaanalytics.com/) ne sont pas aussi simples à utiliser que les expériences de prévision de la demande de Finance and Operations. Vous devez modifier le code des expériences de sorte qu'elles utilisent l'interface de programmation d'applications (API) de l'application Finance and Operations.
  - Vous pouvez créer vos propres expériences dans Microsoft Azure Machine Learning Studio (classique), les publier comme services sur Azure, puis les utiliser pour générer des prévisions de la demande.
  - Si vous n'avez pas besoin d'une haute performance, ou de traiter un grand nombre de données, vous pouvez utiliser la rangée gratuite de Machine Learning. Il est recommandé de toujours démarrer à partir de cette rangée, en particulier lors des phases de mise en œuvre et de test. Si vous avez besoin d'une plus haute performance et d'un stockage supplémentaire, vous pouvez utiliser la rangée standard de Machine Learning. Cette rangée nécessite un abonnement à Azure et entraîne des frais supplémentaires. Pour plus d'informations sur la tarification de Machine Learning, voir [Tarifs de Machine Learning Studio](https://aka.ms/machine-learning-price-info).
- **Réduction des prévisions à n'importe quel point de découplage** – La prévision de la demande s'appuie sur cette fonction, qui vous permet de prévoir à la fois la demande dépendante et indépendante à n'importe quel point de découplage.

## <a name="basic-flow-in-demand-forecasting"></a>Flux de base dans une prévision de la demande

Le diagramme suivant illustre le flux de base dans une prévision de la demande.

[![diagramme d'introduction de la prévision de la demande](./media/demand-forecasting-introduction.png)](./media/demand-forecasting-introduction.png)

La génération de la prévision de la demande commence dans Supply Chain Management. Les données transactionnelles historiques de la base de données transactionnelle de Supply Chain Management sont collectées et remplissent une table intermédiaire. Cette table intermédiaire est ultérieurement fournie à un service Machine Learning. En effectuant une personnalisation minimale, vous pouvez raccorder diverses sources de données à la table intermédiaire. Les sources de données peuvent inclure des fichiers Microsoft Excel, les fichiers CSV et les données Microsoft Dynamics AX 2009 et Microsoft Dynamics AX 2012. Par conséquent, vous pouvez générer des prévisions de la demande qui considèrent un historique des données réparti entre plusieurs systèmes. Toutefois, les données principales, telles que les noms d'article et les unités de mesure, doivent être identiques entre les différentes sources de données.

Si vous utilisez les expériences de prévision de demande de Machine Learning, elles recherchent un ajustement entre cinq méthodes de prévision de l'algorithme pour calculer une prévision de base. Les paramètres pour ces modes de prévision sont gérés dans Supply Chain Management.

Les prévisions, les données historiques et toutes les modifications apportées aux prévisions de la demande dans des itérations précédentes sont ensuite disponibles dans Supply Chain Management.

Vous pouvez utiliser Supply Chain Management pour visualiser et modifier les prévisions de base. Les ajustements manuels doivent être autorisés pour pouvoir utiliser les prévisions pour la planification.

## <a name="limitations"></a>Limites

La prévision de la demande est un outil qui permet aux clients de l'industrie de fabrication de créer des processus de prévision. Elle offre les principales fonctionnalités d'une solution de prévision de la demande et est conçue de façon à pouvoir être facilement étendue. Il se peut que la prévision de la demande ne convienne pas aux clients des secteurs tels que le commerce, la vente en gros, le stockage, le transport ou d'autres services professionnels.

### <a name="demand-forecast-variant-conversion-limitation"></a>Limitation de la conversion de variante de prévision de la demande

La conversion d'unité de mesure (UdM) par variante n'est pas entièrement prise en charge lors de la génération d'une prévision de la demande si l'UdM du stock est différente de l'UdM de prévision de la demande.

La génération de prévisions ( **UdM de stock > UdM de prévision de la demande**) utilise la conversion UdM du produit. Lors du chargement des données d'historique pour la génération de la prévision de la demande, la conversion UdM au niveau du produit sera toujours utilisée lors de la conversion entre l'UdM de stock et l'UdM de prévision de la demande, même si des conversions sont définies au niveau de la variante.

La première partie de l'autorisation des prévisions (**UdM de prévision de la demande > udM de stock**) utilise la conversion UdM du produit. La deuxième partie de l'autorisation des prévisions (**UdM de stock > udM de vente**) utilise la conversion UdM de variante. Lorsque la prévision de la demande générée est autorisée, la conversion entre l'UdM de prévision de la demande et l'UdM de stock est effectuée à l'aide de la conversion d'UdM au niveau du produit. Dans le même temps, la conversion entre l'unité de stock et l'UdM de vente respectera les conversions définies au niveau de la variante.

Notez que l'UdM de prévision de la demande ne doit pas nécessairement avoir de signification spécifique. Elle peut être définie comme « Unité de prévision de la demande ». Pour chacun des produits, vous pouvez définir la conversion comme 1 : 1 avec l'UdM de stock.

## <a name="additional-resources"></a>Ressources supplémentaires

[Paramétrage de la prévision de la demande](demand-forecasting-setup.md)

[Générer des prévisions de base statistiques](generate-statistical-baseline-forecast.md)

[Effectuer des ajustements manuels sur la prévision de base](manual-adjustments-baseline-forecast.md)

[Autoriser un ajustement de la prévision de demande](authorize-adjusted-forecast.md)

[Contrôler la précision de la prévision](monitor-forecast-accuracy.md)

[Supprimer les valeurs hors norme des données de transaction historiques lors du calcul d'une prévision de la demande](remove-historical-outliers-calculating-demand-forecast.md)

[Prolonger la fonctionnalité de prévision de la demande](https://www.youtube.com/watch?v=4OIKIXLiNjI&feature=youtu.be)
