---
title: Résolution des problèmes de performances dans les configurations ER
description: Cette rubrique explique comment rechercher et résoudre les problèmes de performances dans les configurations d’états électroniques (ER).
author: NickSelin
ms.date: 06/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner, ERFormatMappingRunJobTable, ERParameters, ERSolutionTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: maximbel
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: b5f5308f171b6cd4224debec897dbde133e6d8424673aabfab51e6b83b9014e2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744384"
---
# <a name="troubleshooting-performance-issues-in-er-configurations"></a>Résolution des problèmes de performances dans les configurations ER

Cette rubrique explique comment rechercher et résoudre les problèmes de performances dans les [configurations](general-electronic-reporting.md#Configuration) [d’états électroniques](general-electronic-reporting.md) (ER).

En règle générale, l’enquête de performance se compose de plusieurs étapes.

1. [Collecter](#collecting-data) des données.
2. Analyser les données collectées.
3. Sur la base des résultats de l’analyse, utilisez les configurations ER pour [faire des modifications](#making-changes) ou décider de collecter plus de données.

## <a name="troubleshooting"></a>Résolution des problèmes

### <a name="analyze-execution-time"></a>Analyser le temps d’exécution

Le temps d’exécution peut dépendre de facteurs imprévisibles, tels que d’autres tâches qui s’exécutent dans le même environnement et la mise en cache qui utilise des données lorsqu’elles sont appelées pour la première fois. Par conséquent, vous devez répéter l’exécution et la mesure plusieurs fois.

Parfois, les problèmes de performances ne sont pas causés par une configuration de format ER utilisée pour la création de rapports. Au lieu de cela, ils sont causés par le code X++ utilisé pour ouvrir cette configuration de format ER.

1. Dans le [Centre d’action](#infolog-time) ou le [journal des événements](#event-log-time), regardez le temps d’exécution de l’état.
2. Comparez le temps d’exécution de l’état avec le temps d’exécution total dans le scénario.
3. Si le temps d’exécution de l’état est bien inférieur au temps d’exécution total, tenez compte de la quantité de données que traite l’état :

    - Si l’état rapport traite une petite quantité de données, le problème peut impliquer le temps de chargement de la configuration.
    - Si l’état traite une grande quantité de données, le problème peut impliquer le prétraitement X++. Utilisez [Trace Parser](#analyze-trace-parser-trace) pour analyser ce cas.

    Pour les autres cas, voir les sections suivantes.

4. Exécutez plusieurs tests impliquant différentes quantités de données pour déterminer comment le temps d’exécution dépend de la quantité de données.

### <a name="analyze-trace-parser-traces"></a><a name="analyze-trace-parser-trace"></a>Analyser les traces de Trace Parser

Préparez un petit exemple ou collectez plusieurs traces lors de parties aléatoires de la génération de l’état.

Ensuite, dans [Trace Parser](#trace-parser), effectuez une analyse ascendante standard et répondez aux questions suivantes :

- Quelles sont les meilleures méthodes en termes de consommation de temps ?
- Quelle partie du temps total ces méthodes utilisent-elles ?

Répondez aux mêmes questions pour les requêtes.

Si vous voyez que les méthodes portent le préfixe « ER », passez à la section suivante.

Si vous constatez que des méthodes ou des requêtes proviennent de la suite d’applications, envisagez des optimisations génériques (par exemple, créez des index).

Analysez le nombre d’appels. Si le nombre est nettement plus élevé que prévu, envisagez de mettre en cache les nœuds correspondants de la configuration.

### <a name="analyze-database-calls"></a><a name="analyze-database-calls"></a>Analyser les appels à la base de données

Préparez un exemple contenant une petite quantité de données, afin de pouvoir collecter une [trace ER](#electronic-reporting-traces).

Ouvrez ensuite la trace dans le concepteur de mappage de modèle ER et regardez en bas de la page. Répondre aux questions suivantes :

- Y a-t-il des duplications de requête ? Si tel est le cas, envisagez l’un des correctifs suivants :

    - [Utilisez la mise en cache](#use-caching) si vous pensez qu’il y a plusieurs appels dans un enregistrement parent.
    - [Utilisez un champ calculé paramétré en cache](#cached-parameterized) si vous pensez qu’il y a des appels au même enregistrement dans différents enregistrements.
    - [Utilisez une source de données **JOIN**](#use-join-datasource) si vous devez lire un nombre substantiel d’enregistrements différents à partir d’une base de données.

- Le nombre de requêtes et d’enregistrements récupérés correspond-il à la quantité totale de données ? Par exemple, si un document comporte 10 lignes, les statistiques montrent-elles que le rapport extrait 10 lignes ou 1 000 lignes ? Si vous avez un nombre important d’enregistrements récupérés, envisagez l’une des corrections suivantes :

    - [Utilisez la fonction **FILTER** au lieu de la fonction **WHERE**](#filter) pour traiter les données côté SQL Server.
    - Utilisez la mise en cache pour éviter de récupérer les mêmes données.
    - [Utilisez des fonctions de données collectées](#collected-data) pour éviter de récupérer les mêmes données pour le résumé.

### <a name="analyze-perfview-traces"></a>Analyser les traces PerfView

[PerfView](#perfview) est un outil destiné aux développeurs expérimentés. Pour plus d’informations sur les étapes suivantes, consultez [Bases de l’étude du temps passé](https://channel9.msdn.com/Series/PerfView-Tutorial/Tutorial-12-Wall-Clock-Time-Investigation-Basics).

1. Collectez une trace en utilisant le temps de thread.
2. N’incluez que les piles qui utilisent **runUnattended**, pour ne filtrer que le thread qui comporte une exécution de configuration. (Ajoutez **runUnattended** dans la zone de saisie **IncPats**.)
3. Pliez tous les temps CPU, réseau et bloqué.
4. Chargez les [Réglages ER prédéfinis pour PerfView](https://download.microsoft.com/download/2/d/0/2d037b0f-ffd1-4d65-b64f-fcdf51f2c81f/ER_PerfViewPresets.xml).
5. Sélectionnez **ER** \> **Autre réglage prédéfini**.
6. Regardez les noms :

    - Vous verrez probablement le code de la plateforme qui consomme le plus de temps.
    - Vous pouvez appuyer deux fois (ou double-cliquer) et remonter le fil des **appelés**.

        Si vous trouvez des classes portant le préfixe « ERExpression » et s’il s’agit de fonctions liées à des formules, vous pouvez deviner le nom de la fonction d’après le nom de la classe et consulter le référentiel ER pour afficher les attributs.

### <a name="fixes"></a>Correctifs

- Si vous constatez que la majeure partie du temps processeur est consommée par les requêtes, essayez de réduire le nombre de requêtes :

    - [Examinez la trace ER](#analyze-database-calls) à la recherche de requêtes en double.
    - Voyez combien d’enregistrements sont récupérés et évaluez la quantité de données qui devraient théoriquement être récupérées.

- Si vous constatez que l’essentiel du temps processeur est consommé par les fonctions qui sont utilisées, essayez de trouver l’endroit dans la configuration qui consomme le plus de ressources.
- Si vous constatez que la majeure partie du temps processeur est consommée par les fonctions de collecte de données, envisagez de les remplacer par un *Grouper par SQL* du côté du mappage du modèle.

### <a name="collecting-data"></a><a name="collecting-data"></a>Collecte des données

Selon votre environnement, il existe plusieurs manières de collecter les données disponibles :

- Obtenir le temps d’exécution total :

    - Depuis le Centre d’action
    - Depuis le journal des événements

- Profiler l’exécution :

    - En utilisant les outils ER
    - En utilisant Trace Parser
    - En utilisant PerfView

#### <a name="collecting-data-in-a-production-environment"></a>Collecte de données dans un environnement de production

Parfois, les problèmes ne peuvent être reproduits que dans un environnement de production. Les données peuvent être collectées de l’une des manières suivantes :

- En utilisant les traces [Trace Parser](../perf-test/trace-trace-tutorial.md)
- En utilisant les traces de l’[exécution ER](trace-execution-er-troubleshoot-perf.md)
- En utilisant le temps d’exécution total

#### <a name="collecting-data-in-a-development-environment"></a>Collecte de données dans un environnement de développement

En plus des outils utilisables dans un environnement de production, il existe plusieurs outils utilisables dans un environnement de développement :

- Journal des événements (Microsoft-Dynamics-ElectronicReporting). Ce journal peut vous donner le temps total d’exécution.
- Outils .NET courants, tels que PerfView.

De plus, un environnement de développement vous offre plus de flexibilité pour faire des expériences. Par exemple, vous pouvez désactiver des parties de l’état pour voir comment le temps d’exécution est affecté.

### <a name="tools"></a><a name="tools"></a>Outils

#### <a name="execution-time-in-the-action-center"></a><a name="infolog-time"></a>Temps d’exécution dans le Centre d’action

La génération d’états électroniques peut afficher le temps d’exécution de la configuration dans le Centre d’action. Cette option ne fonctionne que pour un utilisateur et une entreprise spécifiques, et uniquement pour les sessions interactives. Pour rendre cette fonctionnalité disponible, procédez comme suit.

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Dans la page **Configurations**, dans le volet Actions, sous l’onglet **Configurations**, dans le groupe **Paramètres avancés**, sélectionnez **Paramètres utilisateur**.
3. Dans la boîte de dialogue **Paramètres utilisateur**, définissez l’option **Afficher l’heure de génération du fichier** sur **Oui**.

#### <a name="execution-time-in-the-event-log"></a><a name="event-log-time"></a>Temps d’exécution dans le journal des événements

1. Ouvrez l’Observateur d’événements Windows.
2. En dessous de **Journaux des applications et des services**, ouvrez **Microsoft-Dynamics-ElectronicReporting/Operational**.
3. Recherchez les événements **FormatMapingRun** où **EventID=2**, car ces événements contiennent des informations sur le temps écoulé.

#### <a name="trace-parser-traces"></a><a name="trace-parser"></a>Traces de Trace Parser 

Étant donné que ER est implémenté en X++, vous pouvez utiliser des outils X++ courants pour analyser les performances. Pour plus d’informations, consultez [Relever des traces à l’aide Trace Parser](../perf-test/trace-trace-tutorial.md).

Cette approche présente quelques limites. Étant donné qu’une partie de la génération d’états électroniques est implémentée en C#, tous les détails ne seront pas disponibles. Cependant, vous pouvez afficher les détails de l’utilisation des données. De plus, les longues exécutions de rapports peuvent dépasser les limites de stockage de trace.

#### <a name="er-traces"></a><a name="electronic-reporting-traces"></a>Traces ER

La génération d’états électroniques peut collecter ses propres traces et dispose d’outils de visualisation et d’analyse pour ces traces. Pour plus d’informations, consultez [Suivre l’exécution des formats d’état électronique pour résoudre les problèmes de performances](trace-execution-er-troubleshoot-perf.md).

#### <a name="perfview"></a><a name="perfview"></a>PerfView

Étant donné que X++ et ER sont tous deux mise en œuvre sur la plateforme .NET, vous pouvez utiliser des outils .NET courants. Par exemple, vous pouvez utiliser gratuitement l’outil [PerfView](https://github.com/Microsoft/perfview).

Vous pouvez également collecter des données à partir de la ligne de commande. Par exemple, le script Windows PowerShell suivant collecte le temps d’exécution jusqu’à ce que toute exécution de format soit arrêtée sur la machine.

```powershell
c:\programs\PerfView collect "e:\traces\$(date -format "ddMMyyyy_hhmm").etl" `
    -CircularMB:20000 -ThreadTime `
    -NoNGenRundown `
    -StopOnEtwEvent:Microsoft-Dynamics-ElectronicReporting/FormatMappingRun/Stop
```

Cette approche présente quelques limites. Vous devez disposer de l’accès administrateur à la machine. De plus, vous devez être un développeur expérimenté, car la courbe d’apprentissage est abrupte.

### <a name="making-changes"></a><a name="making-changes"></a>Apporter des modifications

#### <a name="use-caching"></a><a name="use-caching"></a>Utiliser la mise en cache

Bien que la mise en cache réduise le temps nécessaire pour extraire à nouveau les données, elle coûte de la mémoire. Utilisez la mise en cache dans les cas où la quantité de données récupérées n’est pas très importante. Pour plus d’informations et un exemple montrant comment utiliser la mise en cache, consultez [Améliorer le mappage du modèle en fonction des informations de la trace d’exécution](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace).

#### <a name="use-a-cached-parameterized-calculated-field"></a><a name="cached-parameterized"></a>Utiliser un champ calculé paramétré en cache

Parfois, les valeurs doivent être consultées à plusieurs reprises. Il peut s’agir par exemple de noms de compte et de numéros de compte. Pour gagner du temps, vous pouvez créer un champ calculé avec des paramètres au niveau supérieur, puis ajouter le champ au cache.

Nous vous recommandons de n’utiliser cette approche que lorsque la taille des données mises en cache est petite. Pour plus d’informations, consultez [Améliorer les performances des solutions ER en ajoutant des sources de données de CHAMP CALCULÉ paramétré](er-calculated-field-ds-performance.md).

#### <a name="use-a-join-data-source"></a><a name="use-join-datasource"></a>Utiliser une source de données JOIN

Une source de données **JOIN** permet de récupérer plusieurs enregistrements connectés par une seule requête. Il n’est pas nécessaire d’utiliser une requête distincte pour récupérer chaque enregistrement connecté. Par exemple, si vous avez 1 000 lignes et que vous récupérez des données d’article pour chaque ligne par relation, vous aurez 1 001 requêtes (= 1 000 + 1). Si vous utilisez une source de données **JOIN**, vous n’utiliserez qu’une seule requête pour récupérer les mêmes données. Pour plus d’informations, voir [Utilisation des sources de données JOIN dans les mappages de modèle ER pour obtenir des données de plusieurs tables d’application](er-join-data-sources.md).

#### <a name="use-the-filter-function-instead-of-the-where-function"></a><a name="filter"></a>Utiliser la fonction FILTER au lieu de la fonction WHERE

La fonction **[FILTER](er-functions-list-filter.md)** exécute des conditions sur SQL Server, tandis que la fonction **WHERE** récupère toutes les données de la liste, un enregistrement à la fois, et applique la condition pour chaque enregistrement. Par exemple, vous souhaitez sélectionner un enregistrement sur 1 000 enregistrements. Si vous utilisez **WHERE**, les 1 000 enregistrements seront récupérés. Cependant, si vous utilisez **FILTER**, exactement un enregistrement sera récupéré. La fonction **FILTER** peut également utiliser des index côté base de données.

#### <a name="using-collected-data-functions-or-an-accumulated-data-data-source"></a><a name="collected-data"></a>Utilisation de fonctions de données collectées ou d’une source de données accumulées

Si votre configuration comporte un composant *grouper par* qui résume les données précédemment récupérées par état, le composant récupèrera à nouveau toutes les données. En utilisant les fonctions de données collectées, vous permettez à la génération d’états électroniques d’accumuler des données lors de la première récupération. Pour plus d’informations, voir [Configurer le format ER pour effectuer le comptage et la synthèse](tasks/er-format-counting-summing-2.md).

#### <a name="rewrite-parts-of-the-configuration-in-x"></a>Réécrire des parties de la configuration en X++

La génération d’états électroniques prend en charge les méthodes d’appel de tables et de classes, y compris les extensions. Envisagez de réécrire des parties du mappage du modèle en X++ pour améliorer les performances.

La génération d’états électroniques peut consommer des données provenant des sources suivantes :

- Classes (sources de données **objet** et **classe**)
- Tables (sources de données **table** et **enregistrements de table**)

L’[API ER](er-apis-app73.md#how-to-access-internal-x-objects-by-using-erobjectsfactory) fournit également un moyen d’envoyer des données précalculées à partir du code d’appel. La suite d’applications contient de nombreux exemples de cette approche.
