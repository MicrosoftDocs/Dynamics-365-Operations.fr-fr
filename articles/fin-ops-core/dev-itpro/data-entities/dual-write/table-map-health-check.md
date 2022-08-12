---
title: Codes d’erreur pour la vérification de l’état de la carte de table
description: Cet article décrit les codes d’erreur pour la vérification de l’état du mappage de table.
author: RamaKrishnamoorthy
ms.date: 05/31/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-10-04
ms.openlocfilehash: 16c79a788b66830b77b2cdfb33fd2416c530f7d2
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111564"
---
# <a name="errors-codes-for-the-table-map-health-check"></a>Codes d’erreur pour la vérification de l’état de la carte de table

[!include [banner](../../includes/banner.md)]



Cet article décrit les codes d’erreur pour la vérification de l’état du mappage de table.

## <a name="error-100"></a>Erreur 100

Le message d’erreur est le suivant : « La version minimale requise de la plateforme de finances et d’opérations est PU 43 pour exécuter les recommandations de finances et d’opérations. »

La fonctionnalité nécessite des mises à jour de la plateforme pour la version 10.0.19 ou ultérieure des applications de finances et d’opérations.

## <a name="error-400"></a>Erreur 400

Le message d’erreur est : « Aucune donnée d’enregistrement d’événements commerciaux trouvée pour l’entité \{finance and operations UniqueEntityName\} ce qui signifie que la carte n’est pas en cours d’exécution ou que tous les mappages de champs sont unidirectionnels. »

## <a name="error-500"></a>Erreur 500

Le message d’erreur est : "Aucune configuration de projet trouvée pour le projet \{nom du projet\}. Cela peut être soit le projet n’est pas activé ou tous les mappages de champs sont unidirectionnels de l’engagement client aux applications de finances et d’opérations. »

Vérifiez les mappages pour le mappage de la table. S’ils sont unidirectionnels des applications d’engagement client vers les applications de finances et d’opérations, aucun trafic n’est généré pour la synchronisation en direct à partir des applications de finances et d’opérations vers Dataverse.

## <a name="error-900"></a>Erreur 900

Le message d’erreur est « Filtre source non valide \{sourceFilter\} pour l’entité \{finance and operations UniqueEntityName\}. »

Le filtre source qui est spécifié sur la carte de table pour les applications de finances et d’opérations n’est pas syntaxiquement correct. Pour valider les critères de filtrage, voir [Résoudre les problèmes de synchronisation en direct](dual-write-troubleshooting-live-sync.md#live-synchronization-issues-that-are-caused-by-incorrect-query-filter-syntax-on-the-dual-write-maps).

## <a name="error-1000"></a>Erreur 1000

Le message d’erreur est la requête « Entité \{finance and operations UniqueEntityName\} pour la synchronisation en direct à double écriture est \{finance and operations EntityFilterQueryString\}. Les enregistrements qui répondent aux critères de la requête seront récupérés pour une synchronisation en direct."

La requête d’entité qui a été renvoyée est la requête SQL de sauvegarde pour l’entité. Vérifiez les jointures internes ou les filtres sur la requête qui déterminent les données métier qui sont récupérées pour la synchronisation en direct. Les jointures internes et les filtres sont des conditions obligatoires qui doivent être remplies pour chaque enregistrement sélectionné pour la synchronisation en direct à double écriture.

## <a name="error-1300"></a>Erreur 1300

Le message d’erreur est « Champs virtuels \{s.EntityFieldName\} pour l’entité \{finance and operations EntityMetadata.EntityProperties.LogicalEntityName\} peut ne pas être suivi pour la double écriture. »

Les champs virtuels des tables de finances et d’opérations ne sont pas activés pour le suivi. La synchronisation en direct peut synchroniser les données, mais elle ne pourra pas récupérer les modifications apportées aux colonnes.

## <a name="error-1500"></a>Erreur 1500

Le message d’erreur est : "Il doit y avoir au moins un champ mappé sur un champ de non-recherche sur l’engagement client pour permettre le suivi sur la source de données \{datasource.DataSourceName\} ."

La source de données de l’entité n’a aucun champ mappé pour la double écriture. Les modifications apportées à la table sous-jacente ne seront pas suivies pour la double écriture.

## <a name="error-1600"></a>Erreur 1600

Le message d’erreur est : « Source de données : \{datasource.DataSourceName\} pour l’entité \{finance and operations EntityMetadata.EntityProperties.LogicalEntityName\} a une plage. Seuls les enregistrements qui satisfont à la condition de plage sont récupérés pour l’envoi."

Entités dans les applications de finances et d’opérations peuvent avoir des sources de données où les plages de filtres sont activées. Ces plages définissent les enregistrements qui sont récupérés dans le cadre de la synchronisation en direct. Si certains enregistrements sont ignorés des applications de finances et d’opérations vers Dataverse, vérifiez si les enregistrements répondent aux critères de plage sur l’entité. Un moyen simple d’effectuer cette vérification consiste à exécuter une requête SQL qui ressemble à l’exemple suivant.

```sql
select * from <EntityName> where <filter criteria for the records> on SQL.
```

## <a name="error-1700"></a>Erreur 1700

Le message d’erreur est "La table : \{datasourceTable.Key.subscribedTableName\} for entity \{datasourceTable.Key.entityName\} est suivie pour l’entité \{origTableToEntityMaps.EntityName\}. Les mêmes tables suivies pour plusieurs entités peuvent avoir un impact sur les performances du système pour les transactions de synchronisation en direct."

Si la même table est suivie par plusieurs entités, toute modification de la table déclenchera une évaluation en double écriture pour les entités liées. Bien que les clauses de filtrage n’enverront que les enregistrements valides, l’évaluation peut entraîner un problème de performances s’il existe des requêtes de longue durée ou des plans de requête non optimisés. Ce problème pourrait ne pas être évitable du point de vue commercial. Cependant, s’il existe de nombreuses tables qui se croisent dans plusieurs entités, vous devez envisager de simplifier l’entité ou de vérifier les optimisations pour les requêtes d’entité.

## <a name="error-1800"></a>Erreur 1800
Le message d’erreur est « Source de données :{} pour l’entité CustCustomerV3Entity inclut une valeur de plage. Les mises à jour des enregistrements entrants de Dataverse aux applications de finances et d’opérations peuvent être affectées par les valeurs de plage sur l’entité. Veuillez tester les mises à jour des enregistrements entre Dataverse et les applications de finances et d’opérations avec des enregistrements qui ne correspondent pas aux critères de filtre pour valider vos paramètres. »

Si une plage est spécifiée sur l’entité dans les applications Finance et Opérations, la synchronisation entrante entre Dataverse et les applications de finances et d’opérations doivent être testées pour le comportement de mise à jour sur les enregistrements qui ne correspondent pas à ces critères de plage. Tout enregistrement qui ne correspond pas à la plage est traité comme une opération d’insertion par l’entité. S’il existe un enregistrement existant dans la table sous-jacente, l’insertion échouera. Nous vous recommandons de tester ce scénario d’utilisation pour tous les scénarios avant le déploiement en production.

## <a name="error-1900"></a>Erreur 1900
Le message d’erreur est « Entité : a {} sources de données qui ne sont pas suivies pour la double écriture sortante. Cela peut affecter les performances des requêtes de synchronisation en direct. Veuillez remodeler l’entité dans les applications de finances et d’opérations pour supprimer les sources de données et les tables inutilisées, ou implémenter getEntityRecordIdsImpactedByTableChange pour optimiser les requêtes d’exécution. »

S’il existe de nombreuses sources de données qui ne sont pas utilisées pour le suivi dans la synchronisation en direct réelle à partir des applications de finances et d’opérations, il est possible que les performances de l’entité affectent la synchronisation en direct. Pour optimiser les tables suivies, utilisez la méthode getEntityRecordIdsImpactedByTableChange.

## <a name="error-5000"></a>Erreur 5000
Le message d’erreur est : « Les plug-ins synchrones sont enregistrés pour les événements de gestion des données pour les comptes d’entité. Ceux-ci peuvent avoir un impact sur les performances d’importation de la synchronisation initiale et de la synchronisation en direct dans Dataverse. Pour de meilleures performances, veuillez changer les plug-ins sur le traitement asynchrone. Liste des plug-ins enregistrés {}. »

Les plug-ins synchrones sur une entité Dataverse peuvent affecter les performances de synchronisation en direct et de synchronisation initiale, car ils ajoutent à la charge de transaction. L’approche recommandée consiste à désactiver les plug-ins ou à rendre ces plug-ins asynchrones si vous rencontrez des temps de chargement lents lors de la synchronisation initiale ou de la synchronisation en direct pour une entité particulière.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

