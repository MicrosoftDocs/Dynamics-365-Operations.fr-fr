---
title: Codes d’erreur pour la vérification de l’état de la carte de table
description: Cette rubrique décrit les codes d’erreur pour la vérification de l’état du mappage de table.
author: nhelgren
ms.date: 10/04/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: nhelgren
ms.search.validFrom: 2021-10-04
ms.openlocfilehash: c2d1f1e39a5ddccddf6fbbf524ff7eb0945b3c32
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2021
ms.locfileid: "7782234"
---
# <a name="errors-codes-for-the-table-map-health-check"></a>Codes d’erreur pour la vérification de l’état de la carte de table

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique décrit les codes d’erreur pour la vérification de l’état du mappage de table.

## <a name="error-100"></a>Erreur 100

Le message d’erreur est "Le minimum requis pour la version de plateforme Finance and Operations est PU 43 afin d’exécuter les recommandations Finance and Operations."

La fonctionnalité nécessite des mises à jour de la plateforme pour la version 10.0.19 ou ultérieure des applications Finance and Operations.

## <a name="error-400"></a>Erreur 400

Le message d’erreur est : "Aucune donnée d’enregistrement d’événements commerciaux trouvée pour l’entité \{Finance and Operations UniqueEntityName\} ce qui signifie que la carte n’est pas en cours d’exécution ou que tous les mappages de champs sont unidirectionnels."

## <a name="error-500"></a>Erreur 500

Le message d’erreur est : "Aucune configuration de projet trouvée pour le projet \{nom du projet\}. Cela peut être soit le projet n’est pas activé ou tous les mappages de champs sont unidirectionnels de l’engagement client à Finance and Operations."

Vérifiez les mappages pour le mappage de la table. S’ils sont unidirectionnels des applications d’engagement client vers les applications Finance and Operations, aucun trafic n’est généré pour la synchronisation en direct à partir des applications Finance and Operations vers Dataverse.

## <a name="error-900"></a>Erreur 900

Le message d’erreur est "Filtre source non valide \{sourceFilter\} format pour l’entité \{Finance and Operations UniqueEntityName\}."

Le filtre source qui est spécifié sur la carte de table pour les applications Finance and Operations n’est pas syntaxiquement correct. Pour valider les critères de filtrage, voir [Résoudre les problèmes de synchronisation en direct](dual-write-troubleshooting-live-sync.md#live-synchronization-issues-that-are-caused-by-incorrect-query-filter-syntax-on-the-dual-write-maps).

## <a name="error-1000"></a>Erreur 1000

Le message d’erreur est la requête "Entité \{Finance and Operations UniqueEntityName\} pour la synchronisation en direct à double écriture est \{Finance and Operations EntityFilterQueryString\}. Les enregistrements qui répondent aux critères de la requête seront récupérés pour une synchronisation en direct."

La requête d’entité qui a été renvoyée est la requête SQL de sauvegarde pour l’entité. Vérifiez les jointures internes ou les filtres sur la requête qui déterminent les données métier qui sont récupérées pour la synchronisation en direct. Les jointures internes et les filtres sont des conditions obligatoires qui doivent être remplies pour chaque enregistrement sélectionné pour la synchronisation en direct à double écriture.

## <a name="error-1300"></a>Erreur 1300

Le message d’erreur est "Champs virtuels \{s.EntityFieldName\} pour l’entité \{Finance and Operations EntityMetadata.EntityProperties.LogicalEntityName\} peut ne pas être suivi pour la double écriture."

Les champs virtuels des tables Finance and Operations ne sont pas activés pour le suivi. La synchronisation en direct peut synchroniser les données, mais elle ne pourra pas récupérer les modifications apportées aux colonnes.

## <a name="error-1500"></a>Erreur 1500

Le message d’erreur est : "Il doit y avoir au moins un champ mappé sur un champ de non-recherche sur l’engagement client pour permettre le suivi sur la source de données \{datasource.DataSourceName\} ."

La source de données de l’entité n’a aucun champ mappé pour la double écriture. Les modifications apportées à la table sous-jacente ne seront pas suivies pour la double écriture.

## <a name="error-1600"></a>Erreur 1600

Le message d’erreur est : "Source de données : \{datasource.DataSourceName\} pour l’entité \{Finance and Operations EntityMetadata.EntityProperties.LogicalEntityName\} a une plage. Seuls les enregistrements qui satisfont à la condition de plage sont récupérés pour l’envoi."

Entités dans les applications Finance and Operations peuvent avoir des sources de données où les plages de filtres sont activées. Ces plages définissent les enregistrements qui sont récupérés dans le cadre de la synchronisation en direct. Si certains enregistrements sont ignorés des applications Finance and Operations vers Dataverse, vérifiez si les enregistrements répondent aux critères de plage sur l’entité. Un moyen simple d’effectuer cette vérification consiste à exécuter une requête SQL qui ressemble à l’exemple suivant.

```sql
select * from <EntityName> where <filter criteria for the records> on SQL.
```

## <a name="error-1700"></a>Erreur 1700

Le message d’erreur est "La table : \{datasourceTable.Key.subscribedTableName\} for entity \{datasourceTable.Key.entityName\} est suivie pour l’entité \{origTableToEntityMaps.EntityName\}. Les mêmes tables suivies pour plusieurs entités peuvent avoir un impact sur les performances du système pour les transactions de synchronisation en direct."

Si la même table est suivie par plusieurs entités, toute modification de la table déclenchera une évaluation en double écriture pour les entités liées. Bien que les clauses de filtrage n’enverront que les enregistrements valides, l’évaluation peut entraîner un problème de performances s’il existe des requêtes de longue durée ou des plans de requête non optimisés. Ce problème pourrait ne pas être évitable du point de vue commercial. Cependant, s’il existe de nombreuses tables qui se croisent dans plusieurs entités, vous devez envisager de simplifier l’entité ou de vérifier les optimisations pour les requêtes d’entité.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
