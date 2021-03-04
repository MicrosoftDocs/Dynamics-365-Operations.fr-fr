---
title: Clés de configuration et entités de données
description: Cette rubrique décrit la relation entre les clés de configuration et les entités de données.
author: Sunil-Garg
manager: AnnBe
ms.date: 05/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.custom: 25341
ms.assetid: 8e214c95-616b-4ee1-b5a4-fa5ce5147f2c
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Platform update 13
ms.openlocfilehash: e6145a2f6925932361851735df55374dda8ca03d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679378"
---
# <a name="configuration-keys-and-data-entities"></a>Clés de configuration et entités de données

[!include [banner](../includes/banner.md)]

Avant d’utiliser les entités de données pour importer ou exporter des données, nous vous recommandons de déterminer au préalable l’impact des clés de configuration sur les entités de données que vous comptez utiliser.

Pour en savoir plus sur les clés de configuration, voir [État des codes licence et des clés de configuration](../sysadmin/license-codes-configuration-keys-report.md).

### <a name="configuration-key-assignments"></a>Affectations des clés de configuration
Des clés de configuration peuvent être affectées à un ou tous les artefacts suivants.

- Entités de données
- Tables utilisées comme sources de données
- Champs de table
- Champs d’entité de données

Le tableau suivant résume la façon dont les valeurs de la clé de configuration sur les différents artefacts qui sous-tendent un objet modifient le comportement attendu de l’objet.

| Paramétrage de la clé de configuration dans l’entité de données | Paramétrage de la clé de configuration dans la table | Paramétrage de la clé de configuration dans le champ de table | Paramétrage de la clé de configuration dans le champ d’entité de données | Comportement attendu |
|-----------------------------------------|------------------------------------|------------------------------------------|----------------------------------------|------------------|
| Désactivé                                | Non évalué                      | Non évalué                            | Non évalué                          | Si la clé de configuration de l’entité de données est désactivée, l’entité de données n’est pas fonctionnelle. Il importe peu que les clés de configuration des tables et champs sous-jacents soient activées ou désactivées. |
| Activé                                 | Désactivé                           | Non évalué                            | Non évalué                          | Si la clé de configuration d’une entité de données est activée, l’infrastructure de gestion des données vérifie la clé de configuration dans chaque table sous-jacente. Si la clé de configuration d’une table est désactivée, cette table n’est pas disponible dans l’entité de données pour une utilisation fonctionnelle. Si la clé de configuration d’une table est désactivée, les paramètres de la clé de configuration de la table et de l’entité de données ne sont pas évalués. Si la clé de configuration de la table principale de l’entité est désactivée, le système agit comme si la clé de configuration de l’entité était désactivée. |
| Activé                                 | Activé                            | Désactivé                                 | Non évalué                          | Si la clé de configuration d’une entité de données est activée et les clés de configuration des tables sous-jacentes sont activées, l’infrastructure de gestion des données vérifie la clé de configuration des champs des tables. Si la clé de configuration d’un champ est désactivée, ce champ n’est pas disponible dans l’entité de données pour une utilisation fonctionnelle même si la clé de configuration du champ d’entité de données correspondant est activée. |
| Activé                                 | Activé                            | Activé                                  | Désactivé                               | Si la clé de configuration est activée à tous les autres niveaux, mais la clé de configuration du champ d’entité n’est pas activée, le champ n’est pas disponible dans l’entité de données. |

> [!NOTE]
> Si une entité a une autre entité comme source de données, la sémantique ci-dessus est appliquée de manière récursive.

### <a name="entity-list-refresh"></a>Actualisation de la liste des entités
Lorsque la liste des entités est actualisée, l’infrastructure de gestion des données crée les métadonnées de la clé de configuration qui seront utilisées au moment de l’exécution. Ces métadonnées sont créées à l’aide de la logique décrite ci-dessus. Il est vivement recommandé d’attendre la fin de l’actualisation de la liste des entités avant d’utiliser les tâches et les entités de l’infrastructure de gestion des données. Sinon, les métadonnées de la clé de configuration peuvent ne pas être mises à jour et des résultats inattendus peuvent être générés. Lorsque la liste des entités est en cours d’actualisation, le message suivant s’affiche sur la page Liste des entités.

![Actualisation de la liste des entités](./media/Entity_refresh_list.png)

### <a name="data-entity-list-page"></a>Page Liste des entités de données
La page Liste des entités de données de l’espace de travail Gestion des données affiche les paramètres de la clé de configuration pour les entités. Commencez à partir de cette page pour comprendre l’impact des clés de configuration sur l’entité de données.

Ces informations s’affichent à l’aide des métadonnées créées pendant l’actualisation de l’entité. La colonne Clé de configuration affiche le nom de la clé de configuration associée à l’entité de données. Si cette colonne est vide, cela signifie qu’aucune clé de configuration n’est associée à l’entité de données. La colonne Statut de la clé de configuration affiche l’état de la clé de configuration. Si elle est cochée, cela signifie que la clé est activée. Si elle est vide, cela signifie que la clé est désactivée ou qu’aucune clé n’est associée.

![Page Liste des entités](./media/Data_entity_list_page.png)

### <a name="target-fields"></a>Champs cibles
L’étape suivante consiste à explorer l’entité de données pour déterminer l’impact des clés de configuration sur les tables et les champs. L’écran Champs cibles d’une entité de données affiche la clé de configuration et les informations sur le statut de la clé pour les tables et champs associés de l’entité de données. Si la clé de configuration de l’entité de données proprement dite est désactivée, un message d’avertissement s’affiche pour indiquer que les tables et les champs de l’écran Champs cibles de cette entité ne sont pas disponibles, quel que soit le statut de la clé de configuration.

![Champs cibles](./media/Target_fields_1.png)

### <a name="child-entities"></a>Entités enfants 
Certaines entités ont d’autres entités comme sources de données, ou sont des entités de données composites : les informations sur la clé de configuration de ces entités s’affichent dans l’écran Entités enfants. Utilisez cet écran de la même manière que la page Liste des entités décrite ci-dessus. L’écran Champs cibles de l’entité enfant se comporte également comme indiqué ci-dessus.

![Champs cibles](./media/Target_fields_2.png)

### <a name="using-data-entities"></a>Utilisation des entités de données
Une fois que vous avez pleinement compris l’impact, le cas échéant, des clés de configuration sur les entités de données que vous souhaitez utiliser, vous pouvez à présent utiliser les entités de données en les ajoutant à des projets de données. 

### <a name="run-time-validations-for-configuration-keys"></a>Validations des temps d’exécution des clés de configuration
Les validations des temps d’exécution sont effectuées dans les cas d’utilisation ci-après à l’aide des métadonnées de la clé de configuration créées pendant l’actualisation de la liste des entités.

- Lorsqu’une entité de données est ajoutée à une tâche
- Lorsque l’utilisateur clique sur « valider » dans la liste des entités
- Lorsque l’utilisateur charge un package de données dans un projet de données
- Lorsque l’utilisateur charge un modèle dans un projet de données
- Lorsqu’un projet de données existant est chargé
- Lorsqu’un modèle est chargé dans un projet de données
- Avant l’exécution de la tâche d’exportation/importation (lot, sans lot, récurrente, OData)
- Lorsque l’utilisateur génère la mise en correspondance
- Lorsque l’utilisateur met en correspondance les champs de l’interface utilisateur de mise en correspondance
- Lorsque l’utilisateur ajoute uniquement des « champs importables »

### <a name="managing-configuration-key-changes"></a>Gestion des modifications de la clé de configuration
Lorsque vous mettez à jour les clés de configuration au niveau de l’entité, de la table ou du champ, la liste des entités de l’infrastructure de gestion des données doit être actualisée. Ce processus garantit que l’infrastructure sélectionne les paramètres de la clé de configuration les plus récents. Tant que la liste des entités n’est pas actualisée, l’avertissement suivant s’affiche sur la page Liste des entités. Les modifications de la clé de configuration prennent effet immédiatement après l’actualisation de la liste des entités. Nous vous recommandons de valider les tâches et les projets de données existants pour vous assurer qu’ils fonctionnent comme prévu une fois que les modifications des clés de configuration sont appliquées.

![Champs cibles](./media/Target_fields_3.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]