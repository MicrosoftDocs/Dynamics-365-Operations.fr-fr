---
title: Paramétrage de la prévision de la demande
description: Cette rubrique décrit les tâches de paramétrage que vous devez effectuer pour préparer la prévision de la demande.
author: roxanadiaconu
ms.date: 08/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanDefaultAlgorithmParameters, ReqDemPlanForecastParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72653
ms.assetid: c5fa4b09-512d-4349-ac51-cc13da69a160
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 81fec20130a1621d4cb55394db75a7ac0a16fdf3
ms.sourcegitcommit: 4fbf031319109660c0462a800f85848571eb040d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2021
ms.locfileid: "7471333"
---
# <a name="demand-forecasting-setup"></a>Paramétrage de la prévision de la demande

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les tâches de paramétrage que vous devez effectuer pour préparer la prévision de la demande.  

Les tâches de paramétrage incluent notamment la définition des données et des paramètres suivants.

## <a name="item-allocation-keys"></a>Clés de répartition par article

Une prévision de la demande est calculée pour un article et ses dimensions uniquement si l’article fait partie d’une clé de répartition par article. Cette règle s’applique pour regrouper un grand nombre d’articles, de sorte que les prévisions de la demande puissent être créées plus rapidement. Le pourcentage de clé de répartition par article est ignoré lorsque des prévisions de la demande sont générées. Les prévisions sont créées en fonction des données historiques uniquement.

Un article et ses dimensions doivent faire partie d’une seule clé de répartition par article si la clé de répartition par article est utilisée lors de la création de la prévision.

Pour ajouter une unité de stockage (SKU) à une clé de répartition par article, accédez à **Planification générale \> Paramétrage \> Prévision de la demande \> Clés de répartition par article**. La page **Affecter des articles** permet d’affecter un article à une clé de répartition.

## <a name="intercompany-planning-groups"></a>Groupes de planification intersociétés

La prévision de demande génère des prévisions de société croisée. Dans Dynamics 365 Supply Chain Management, les sociétés qui sont planifiées ensemble sont regroupées dans un groupe de planification intersociétés. Pour indiquer, par société, les clés de répartition par article qui doivent être considérées pour la prévision de la demande, associez une clé de répartition par article au membre du groupe de planification intersociétés en accédant à **Planification générale \> Paramétrage \> Groupes de planification intersociétés**.

Par défaut, si aucune clé de répartition par article n’est affectée aux membres du groupe de planification intersociétés, une prévision de la demande est calculée pour tous les articles affectés à toutes les clés de répartition par article de toutes les sociétés. Des options de filtrage supplémentaires pour les sociétés et les clés de répartition par article sont disponibles dans la page **Générer des prévisions de base statistiques**.

Examinez le nombre d’articles qui sont prévus. Les articles inutiles peuvent entraîner des coûts augmentés lorsque vous utilisez Microsoft Azure Machine Learning.

## <a name="demand-forecasting-parameters"></a>Paramètres de prévision de la demande

Pour paramétrer des paramètres de prévision de la demande, accédez à **Planification générale \> Paramétrage \> \> Prévision de la demande \> Paramètres de prévision de la demande**. Comme la prévisions de demande fonctionne sur toutes les sociétés, le paramétrage est global. Cela signifie que le paramétrage s’applique à toutes les sociétés.

La prévision de la demande génère la prévision en quantités. Par conséquent, l’unité de mesure dans laquelle la quantité doit être exprimée doit être spécifiée dans le champ **Unité de prévision de la demande**. L’unité de mesure doit être unique afin de garantir que l’agrégation et la distribution de pourcentage soient cohérentes. Pour plus d’informations sur l’agrégation et la distribution de pourcentage, voir [Effectuer des ajustements manuels de la prévision de base](manual-adjustments-baseline-forecast.md). Pour chaque unité de mesure utilisée pour les SKU inclus dans une prévision de la demande, assurez-vous qu’il existe une règle de conversion pour l’unité de mesure et l’unité de mesure de la prévision générale. Lorsque la génération de prévision est effectuée, la liste des articles qui n’ont pas une conversion d’unités de mesure est enregistrée, afin de corriger facilement le paramétrage.

La prévision de la demande peut être utilisée pour prévoir à la fois la demande dépendante et indépendante. Par exemple, si seule la case à cocher **Commande client** est activée, et si tous les articles qui sont considérés pour la prévision de la demande sont des articles vendus, le système calcule une demande indépendante. Toutefois, des sous-composants critiques peuvent être ajoutés aux clés de répartition par article et être inclus dans une prévision de la demande. Dans ce cas, si la case à cocher **Ligne de production** est activée, une prévision dépendante est calculée.

Il existe deux méthodes pour créer une ligne de prévision de base. Vous pouvez utiliser les modèles de prévision sur des données historiques, ou vous pouvez juste copier les données historiques dans la prévision. Le champ **Stratégie de génération de prévision** permet de choisir entre ces deux méthodes. Pour utiliser les modèles de prévision, sélectionnez **Azure Machine Learning**.

En sélectionnant **Dimensions de prévision** dans le volet gauche de la page **Paramètres de prévision de la demande**, vous pouvez également sélectionner l’ensemble de dimensions de prévision à utiliser lorsque la prévision de la demande est générée. Une dimension de prévision indique le niveau de détail pour lequel la prévision est définie. Société, site, et clé de répartition par article sont des dimensions de prévision requises, mais vous pouvez également générer des prévisions aux niveaux de l’entrepôt, du statut du stock, du groupe de clients, du compte client, du pays/de la région, de l’état, et de l’article plus tous les niveaux de dimension d’article.

À tout moment, vous pouvez ajouter des dimensions de prévision à la liste des dimensions utilisées pour les prévisions de la demande. Vous pouvez également supprimer des dimensions de prévision de la liste. Toutefois, les ajustements manuels sont perdus si vous ajoutez ou supprimez une dimension de prévision.

Seuls certains articles se comportent de la même manière du point de vue de la prévision de la demande. Les articles similaires peuvent être regroupés dans une seule clé de répartition par article, et des paramètres tels que des types de transactions et des paramètres de méthode de prévision peuvent être définis par clé de répartition par article. Sélectionnez **Clés de répartition par article** dans le volet gauche de la page **Paramètres de prévision de la demande**.

Pour générer la prévision, Supply Chain Management utilise un service web de Machine Learning. Pour vous connecter au service, vous devez fournir les informations suivantes si vous vous connectez à Microsoft Azure Machine Learning Studio (classique) :

- Clé de l’interface de programmation d’applications (API) du service Web
- URL du point de terminaison du service Web
- Nom du compte de stockage Azure
- Clé du compte de stockage Azure

> [!NOTE]
> Le nom et la clé du compte de stockage Azure sont obligatoires uniquement si vous utilisez un compte personnalisé de stockage. Si vous déployez la version sur site, vous devez posséder un compte personnalisé de stockage sur Azure, afin que Machine Learning puisse accéder aux données historiques.

Pour créer des prévisions de la demande, vous pouvez déployer votre propre service à l’aide de Machine Learning Studio ou des expériences de prévision de la demande de Supply Chain Management. Des instructions pour déployer les expériences de prévision de demande sous forme de service Web sont disponibles dans Supply Chain Management. Dans la page **Paramètres de prévision de la demande**, ouvrez l’onglet **Azure Machine Learning**.

## <a name="settings-for-the-demand-forecasting-machine-learning-service"></a>Paramètres du service Machine Learning de prévision de la demande

Pour afficher les paramètres qui peuvent être configurés pour le service de prévision de la demande, accédez à **Planification générale\> Paramétrage \> Prévision de la demande \> Paramètres de l’algorithme de prévision**. La page **Paramètres par défaut de l’algorithme de prévision** indique les valeurs par défaut des paramètres. Vous pouvez remplacer ces paramètres en allant à **Planification générale \> Paramétrage \> Prévision de la demande \> Paramètres de prévision de la demande**, où vous pouvez effectuer les opérations suivantes :

- Utiliser l'onglet **Général** pour écraser les paramètres globalement.
- Utiliser l'onglet **Clés de répartition par article** pour écraser les paramètres par clé de répartition par article. Les paramètres qui sont remplacés pour une clé de répartition par article n’affectent que la prévision des articles associés à cette clé de répartition par article.

### <a name="forecast-algorithm-parameters"></a>Paramètres de l'algorithme de prévision

Sur l'onglet **Clés de répartition par article** de la page **Paramètres de prévision de la demande**, vous pouvez utiliser le raccourci **Paramètres de l'algorithme de prévision** pour affecter les paramètres de l'algorithme de prévision à la clé de répartition par article actuellement sélectionnée dans la grille de gauche. Utilisez les bouton **Ajouter** et **Supprimer** de la barre d'outils pour établir la collection de paramètres requise. Pour chaque paramètre de la liste, sélectionnez l'une des valeurs suivantes dans le champ **Nom**, puis saisissez une valeur appropriée dans le champ **Valeur** :

- **Pourcentage du niveau de confiance** : un intervalle de confiance comporte une plage de valeurs qui constitue une bonne estimation des prévisions de la demande. Un pourcentage de niveau de confiance à 95 % indique qu’il existe un risque de 5 % que la demande future se trouve en dehors de l’intervalle de confiance.
- **Forcer le caractère saisonnier** : indique s’il convient de forcer le modèle pour utiliser un certain type de caractère saisonnier. S’applique à ARIMA et ETS uniquement. Options : AUTOMATIQUE (par défaut), AUCUN, ADDITIF, MULTIPLICATIF.
- **Modèle de prévision** : Options : ARIMA, ETS, STL, ETS+ARIMA, ETS+STL, TOUT. Pour sélectionner le modèle le mieux adapté, utilisez **TOUT**.
- **Valeur maximale prévue** : indique la valeur maximale à utiliser pour les prévisions. Format : +1E [n] ou constante numérique.
- **Valeur minimale prévue** : indique la valeur minimale à utiliser pour les prévisions. Format : -1E[n] ou constante numérique.
- **Substitution de valeur manquante** : indique comment les trous dans les données historiques sont comblés. Options : valeur numérique, MOYENNE, PRÉCÉDENTE, INTERPOLATION LINÉAIRE, INTERPOLATION POLYNOMIALE.
- **Étendue de substitution de valeur manquante** : indique si la valeur de substitution s’applique uniquement à la plage de dates de chaque attribut individuel granulaire, ou à l’intégralité de l’ensemble de données. Les options suivantes sont disponibles pour établir la plage de dates que le système utilise pour combler les lacunes dans les données historiques :

  - GLOBAL : le système utilise toute la plage de dates de tous les attributs granulaires.
  - HISTORY_DATE_RANGE : le système utilise une plage de dates spécifique définie par les champs **Date de début** et **Date de fin** sur le groupe de champs **Horizon historique** dans la boîte de dialogue **Générer des prévisions de base statistiques**.
  - GRANULARITY_ATTRIBUTE : le système utilise la plage de dates de l'attribut de granularité actuellement traité.

  > [!NOTE]
  > Un attribut de granularité est une combinaison de dimensions de prévision par rapport auxquelles la prévision est effectuée. Vous pouvez définir les dimensions de prévision dans la page **Paramètres de prévision de la demande**.

- **Conseil sur la saisonnalité** : pour les données saisonnières, fournissez un conseil au modèle de prévisions pour améliorer la précision des prévisions. Format : le nombre entier, représentant le nombre de plages selon lequel le modèle de demande se répète. Par exemple, entrez « 6 » pour les données qui se répètent tous les 6 mois.
- **Tester le pourcentage de taille défini** : pourcentage des données historiques à utiliser dans le cadre d’un test défini pour le calcul de la précision des prévisions.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble de la prévision de la demande](introduction-demand-forecasting.md)
- [Générer des prévisions de base statistiques](generate-statistical-baseline-forecast.md)
- [Effectuer des ajustements manuels sur la prévision de base](manual-adjustments-baseline-forecast.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
