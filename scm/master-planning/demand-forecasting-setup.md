---
title: "Paramétrage de la prévision de la demande"
description: "Cette rubrique décrit les tâches de paramétrage que vous devez effectuer pour préparer la prévision de la demande."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanDefaultAlgorithmParameters, ReqDemPlanForecastParameters
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72653
ms.assetid: c5fa4b09-512d-4349-ac51-cc13da69a160
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: f9b0930ac8d26f83be077fe0e6edf917e8fb0f58
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="demand-forecasting-setup"></a>Paramétrage de la prévision de la demande

[!include[banner](../includes/banner.md)]


Cette rubrique décrit les tâches de paramétrage que vous devez effectuer pour préparer la prévision de la demande.  

Les tâches de paramétrage incluent notamment la définition des données et des paramètres suivants.

## <a name="item-allocation-key"></a>Clé de répartition par article
Une prévision de la demande est calculée pour un article et ses dimensions uniquement si l'article fait partie d'une clé de répartition par article. Cette règle s'applique pour regrouper un grand nombre d'articles, de sorte que les prévisions de la demande puissent être créées plus rapidement. Le pourcentage de clé de répartition par article est ignoré lorsque des prévisions de la demande sont générées. Les prévisions sont créées en fonction des données historiques uniquement. 

Un article et ses dimensions doivent faire partie d'une seule clé de répartition par article si la clé de répartition par article est utilisée lors de la création de la prévision. 

Pour ajouter une unité de stockage (SKU) à une clé de répartition par article, accédez à **Planification** &gt; **Paramétrage** &gt; **Prévision de la demande** &gt; **Clés de répartition par article**. La page **Affecter des articles** permet d'affecter un article à une clé de répartition.

## <a name="intercompany-planning-groups"></a>Groupes de planification intersociétés
La prévision de demande génère des prévisions de société croisée. Dans Microsoft Dynamics 365 for Operations, les sociétés qui sont planifiées ensemble sont regroupées dans un groupe de planification intersociétés. Pour indiquer, par société, les clés de répartition par article qui doivent être considérées pour la prévision de la demande, associez une clé de répartition par article au membre du groupe de planification intersociétés en allant sur **Planification** &gt; **Paramétrage** &gt; **Groupes de planification intersociétés**. 

Par défaut, si aucune clé de répartition par article n'est affectée aux membres du groupe de planification intersociétés, une prévision de la demande est calculée pour tous les articles affectés à toutes les clés de répartition par article de toutes les sociétés Dynamics 365 for Operations. Des options de filtrage supplémentaires pour les sociétés et les clés de répartition par article sont disponibles dans la page **Générer des prévisions de base statistiques**. 

Examinez le nombre d'articles qui sont prévus. Les articles inutiles peuvent entraîner des coûts augmentés lorsque vous utilisez Microsoft Azure Machine Learning.

## <a name="demand-forecasting-parameters"></a>Paramètres de prévision de la demande
Pour paramétrer des paramètres de prévision de la demande, accédez à **Planification** &gt; **Paramétrage** &gt; **Paramètres de prévision de la demande**. Comme la prévisions de demande fonctionne sur toutes les sociétés, le paramétrage est global. Autrement dit, le paramétrage s'applique à toutes les sociétés. 

La prévision de la demande génère la prévision en quantités. Par conséquent, l'unité de mesure dans laquelle la quantité doit être exprimée doit être spécifiée dans le champ **Unité de prévision de la demande**. L'unité de mesure doit être unique, pour garantit que l'agrégation et la distribution de pourcentage soient cohérentes. Pour plus d'informations sur l'agrégation et la distribution de pourcentage, voir [Effectuer des ajustements manuels de la prévision de base](manual-adjustments-baseline-forecast.md). Pour chaque unité de mesure utilisée pour les SKU inclus dans une prévision de la demande, assurez-vous qu'il existe une règle de conversion pour l'unité de mesure et l'unité de mesure de la prévision générale. Lorsque la génération de prévision est effectuée, la liste des articles qui n'ont pas une conversion d'unités de mesure est enregistrée, afin de corriger facilement le paramétrage. 

La prévision de la demande peut être utilisée pour prévoir à la fois la demande dépendante et indépendante. Par exemple, si seule la case à cocher **Commande client** est activée, et si tous les articles qui sont considérés pour la prévision de la demande sont des articles vendus, le système calcule une demande indépendante. Toutefois, des sous-composants critiques peuvent être ajoutés aux clés de répartition par article et être inclus dans une prévision de la demande. Dans ce cas, si la case à cocher **Ligne de production** est activée, une prévision dépendante est calculée. 

Il existe deux méthodes pour créer une ligne de prévision de base dans Dynamics 365 for Operations. Vous pouvez utiliser les modèles de prévision sur des données historiques, ou vous pouvez juste copier les données historiques dans la prévision. Le champ **Stratégie de génération de prévision** permet de choisir entre ces deux méthodes. Pour utiliser les modèles de prévision, sélectionnez **Azure Machine Learning**. 

En cliquant sur **Dimensions de prévision** dans le volet gauche de la page **Paramètres de prévision de la demande**, vous pouvez également sélectionner l'ensemble de dimensions de prévision à utiliser lorsque la prévision de la demande est générée. Une dimension de prévision indique le niveau de détail pour lequel la prévision est définie. Société, site, et clé de répartition par article sont des dimensions de prévision obligatoires, mais vous pouvez également générer des prévisions aux niveaux de l'entrepôt, du statut du stock, du groupe de clients, du compte client, du pays/de la région, de l'état, et de l'article plus tous les niveaux de dimension d'article. 

À tout moment, vous pouvez ajouter des dimensions de prévision à la liste des dimensions utilisées pour les prévisions de la demande. Vous pouvez également supprimer des dimensions de prévision de la liste. Toutefois, les ajustements manuels sont perdus si vous ajoutez ou supprimez une dimension de prévision. 

Seuls certains articles se comportent de la même manière du point de vue de la prévision de la demande. Les articles similaires peuvent être regroupés dans une seule clé de répartition par article, et des paramètres tels que des types de transactions et des paramètres de méthode de prévision peuvent être définis par clé de répartition par article. Cliquez sur **Clés de répartition par article** dans le volet gauche de la page **Paramètres de prévision de la demande**. 

Pour générer la prévision, Dynamics 365 for Operations utilise un service Web Machine Learning. Pour se connecter au service, vous devez fournir à Dynamics 365 for Operations les informations suivantes si vous vous connectez à Microsoft Azure Machine Learning Studio :

-   Clé de l'interface de programmation d'applications (API) du service Web
-   URL du point de terminaison du service Web
-   Nom du compte de stockage Azure
-   Clé du compte de stockage Azure

**Remarque :** le nom et la clé du compte de stockage Azure sont obligatoires uniquement si vous utilisez un compte personnalisé de stockage. Si vous déployez la version sur site, vous devez posséder un compte personnalisé de stockage sur Azure, afin que le service Machine Learning puisse accéder aux données historiques. 

Pour créer des prévisions de la demande, vous pouvez déployer votre propre service à l'aide de Machine Learning Studio ou des expériences de prévision de la demande de Dynamics 365 for Operations. Des instructions pour déployer les expériences de prévision de demande de Dynamics 365 for Operations sous forme de service Web sont disponibles dans Dynamics 365 for Operations. Dans la page **Paramètres de prévision de la demande**, cliquez sur l'onglet **Azure Machine Learning**.

## <a name="settings-for-the-dynamics-365-for-operations-demand-forecasting-machine-learning-service"></a>Paramètres du service Machine Learning de prévision de la demande de Dynamics 365 for Operations
Pour afficher les paramètres qui peuvent être configurés pour le service de prévision de la demande de Dynamics 365 for Operations, accédez à **Planification** &gt; **Paramétrage** &gt; **Prévision de la demande** &gt; **Paramètres de l'algorithme de prévision**. La page **Paramètres de l'algorithme de prévision** indique les valeurs par défaut des paramètres. Vous pouvez remplacer ces paramètres dans la page **Paramètres de prévision de la demande**. Utilisez l'onglet **Général** pour remplacer les paramètres globalement ou utilisez l'onglet **Clés de répartition par article** pour remplacer les paramètres par clé de répartition par article. Les paramètres qui sont remplacés pour une clé de répartition par article n'affectent que la prévision des articles associés à cette clé de répartition par article.

<a name="see-also"></a>Voir également :
--------

[Présentation de la prévision de la demande](introduction-demand-forecasting.md)

[Génération de prévisions de base statistiques](generate-statistical-baseline-forecast.md)

[Effectuer des ajustements manuels sur la prévision de base](manual-adjustments-baseline-forecast.md)




