---
title: "Paramétrage de la prévision de la demande"
description: "Cette rubrique décrit les tâches de paramétrage que vous devez effectuer pour préparer la prévision de la demande."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
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
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: f629329f4f50bd7c8edcfd70641bace01a1c53aa
ms.lasthandoff: 03/31/2017


---

# <a name="demand-forecasting-setup"></a>Paramétrage de la prévision de la demande

Cette rubrique décrit les tâches de paramétrage que vous devez effectuer pour préparer la prévision de la demande.  

Les tâches de paramétrage incluent notamment la définition des données et des paramètres suivants.

## <a name="item-allocation-key"></a>Clé de répartition par article
Une prévision de la demande est calculée pour un article et ses dimensions uniquement si l'article fait partie d'une clé de répartition par article. Cette règle est appliquée de regrouper un grand nombre d'articles, de sorte que les prévisions de la demande puissent être créées plus rapidement. Pourcentage de clé de répartition par article est ignoré lorsque des prévisions de la demande sont générées. Les prévisions sont créées en fonction des données historiques uniquement. 

Un article et ses dimensions doivent faire partie d'une seule clé de répartition par article si la clé de répartition par article est utilisée lors de la création de la prévision. 

Pour ajouter une unité de stockage (SKU) à une clé de répartition par article, passez ** planification ** &gt; ** au paramétrage ** &gt; ** prévision de la demande ** &gt; ** des clés de répartition par article **. La page **Affecter des articles** permet d'affecter un article à une clé de répartition.

## <a name="intercompany-planning-groups"></a>Groupes de planification intersociétés
La prévision de demande génère des prévisions de société croisée. Dans Microsoft Dynamics 365 pour des opérations, des sociétés qui sont planifiées ensemble sont regroupées dans un groupe de planification intersociétés. Pour spécifier, par société, clés de répartition par article doivent être prises en compte pour la prévision de la demande, associez une clé de répartition par article avec le membre intersociétés du groupe de planification en allant ** planification ** &gt; ** au paramétrage ** &gt; ** les groupes de planification intersociétés **. 

Par défaut, si aucune clé de répartition par article n'est affectée aux membres intersociétés du groupe de planification, une prévision de la demande est calculée pour tous les articles affectés à toutes les clés de répartition par article du Dynamics 365 pour les sociétés d'opérations. Des options de filtrage supplémentaires pour les sociétés et les clés de répartition par article sont disponibles dans la page **Générer des prévisions de base statistiques**. 

Examinez le nombre d'articles qui sont prévus. Les articles inutiles peuvent entraîner des coûts augmentés lorsque vous utilisez Microsoft Azure Machine Learning.

## <a name="demand-forecasting-parameters"></a>Paramètres de prévision de la demande
Pour définir les paramètres de prévision de la demande, passez ** planification ** &gt; ** au paramétrage ** &gt; ** des paramètres de prévision de la demande **. Comme la prévisions de demande fonctionne sur toutes les sociétés, le paramétrage est global. Autrement dit, le paramétrage s'applique à toutes les sociétés. 

La prévision de la demande génère la prévision en quantités. Par conséquent, l'unité de mesure dans laquelle la quantité doit être exprimée doit être spécifiée dans le champ **Unité de prévision de la demande**. L'unité de mesure doit être unique, pour garantit que l'agrégation et la distribution de pourcentage soient cohérentes. Pour plus d'informations sur l'agrégation et la distribution de pourcentage, voir [Effectuer des ajustements manuels de la prévision de base](manual-adjustments-baseline-forecast.md). Pour chaque unité de mesure utilisée pour les SKU inclus dans une prévision de la demande, assurez-vous qu'il existe une règle de conversion pour l'unité de mesure et l'unité de mesure de la prévision générale. Lorsque la génération de prévision est effectuée, la liste des articles qui n'ont pas une conversion d'unités de mesure est enregistrée, afin de corriger facilement le paramétrage. 

La prévision de la demande peut être utilisée pour prévoir à la fois la demande dépendante et indépendante. Par exemple, si seule la case à cocher **Commande client** est activée, et si tous les articles qui sont considérés pour la prévision de la demande sont des articles vendus, le système calcule une demande indépendante. Toutefois, des sous-composants critiques peuvent être ajoutés aux clés de répartition par article et être inclus dans une prévision de la demande. Dans ce cas, si la case à cocher **Ligne de production** est activée, une prévision dépendante est calculée. 

Il existe deux méthodes pour créer une prévision de base dans Dynamics 365 pour les opérations. Vous pouvez utiliser les modèles de prévision sur des données historiques, ou vous pouvez juste copier les données historiques dans la prévision. Le champ **Stratégie de génération de prévision** permet de choisir entre ces deux méthodes. Pour utiliser les modèles de prévision, sélectionnez **Azure Machine Learning**. 

En cliquant sur **Dimensions de prévision** dans le volet gauche de la page **Paramètres de prévision de la demande**, vous pouvez également sélectionner l'ensemble de dimensions de prévision à utiliser lorsque la prévision de la demande est générée. Une dimension de prévision indique le niveau de détail pour lequel la prévision est définie. Société, site, et clé de répartition par article sont des dimensions de prévision obligatoires, mais vous pouvez également générer des prévisions aux niveaux de l'entrepôt, du statut du stock, du groupe de clients, du compte client, du pays/de la région, de l'état, et de l'article plus tous les niveaux de dimension d'article. 

À tout moment, vous pouvez ajouter des dimensions de prévision à la liste des dimensions utilisées pour les prévisions de la demande. Vous pouvez également supprimer des dimensions de prévision de la liste. Toutefois, les ajustements manuels sont perdus si vous ajoutez ou supprimez une dimension de prévision. 

Seuls certains articles se comportent de la même manière du point de vue de la prévision de la demande. Les articles similaires peuvent être regroupés dans une seule clé de répartition par article, et des paramètres tels que des types de transactions et des paramètres de méthode de prévision peuvent être définis par clé de répartition par article. Cliquez sur **Clés de répartition par article** dans le volet gauche de la page **Paramètres de prévision de la demande**. 

Pour générer une prévision, Dynamics 365 pour les opérations utilise un service Web de Machine Learning. Pour se connecter au service, vous devez fournir Dynamics 365 pour les opérations les informations suivantes si vous vous connectez au Studio azuré de Machine Learning Microsoft :

-   Clé de l'interface de programmation d'applications (API) du service Web
-   URL du point de terminaison du service Web
-   Nom du compte de stockage Azure
-   Clé du compte de stockage Azure

**Remarque :** le nom et la clé du compte de stockage Azure sont obligatoires uniquement si vous utilisez un compte personnalisé de stockage. Si vous déployez les marchandises locaux version, vous devez avoir un compte spécifié de stockage sur l'azur, de sorte que le service de Machine Learning puisse accéder aux données historiques. 

Pour créer une prévision de la demande, vous pouvez déployer votre propre service à l'aide de le Studio de Machine Learning ou Dynamics 365 pour les expériences de prévision de la demande d'opérations. Les instructions pour déployer Dynamics 365 pour la prévision de la demande d'opérations expérimente comme un service Web sont Dynamics disponible 365 pour les opérations. Dans la page **Paramètres de prévision de la demande**, cliquez sur l'onglet **Azure Machine Learning**.

## <a name="settings-for-the-dynamics-365-for-operations-demand-forecasting-machine-learning-service"></a>Paramètres pour Dynamics 365 pour le service d'enseignement machine de prévision de la demande d'opérations
Pour afficher les paramètres peuvent être configurés pour Dynamics 365 pour le service de prévision de la demande d'opérations, passez ** planification ** &gt; ** au paramétrage ** &gt; ** prévision de la demande ** &gt; ** les paramètres d'algorithme de prévisions **. ** Paramètres d'algorithme de prévisions ** page indique les valeurs par défaut des paramètres. Vous pouvez remplacer ces paramètres sous ** des paramètres de prévision de la demande ** la page. Utilisez l'onglet **Général** pour remplacer les paramètres globalement ou utilisez l'onglet **Clés de répartition par article** pour remplacer les paramètres par clé de répartition par article. Les paramètres qui sont remplacés pour une clé de répartition par article n'affectent que la prévision des articles associés à cette clé de répartition par article.

<a name="see-also"></a>Voir également :
--------

[Introduction to demand forecasting](introduction-demand-forecasting.md)

[Generating a statistical baseline forecast](generate-statistical-baseline-forecast.md)

[Making manual adjustments to the baseline forecast](manual-adjustments-baseline-forecast.md)


