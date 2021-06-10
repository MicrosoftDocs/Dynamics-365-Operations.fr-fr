---
title: Impossible de filtrer les éléments de planification générale selon leurs valeurs de groupe de couverture associées
description: Impossible de filtrer les éléments de planification générale selon leurs valeurs de groupe de couverture associées.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: fa0b614b6710c65811add8725a0e255ce2c34b88
ms.sourcegitcommit: 3c15a26e9708adc9a75082dc551f0a3a0a7d89f4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049467"
---
# <a name="you-cant-filter-master-planning-items-by-their-related-coverage-group-values"></a>Impossible de filtrer les éléments de planification générale selon leurs valeurs de groupe de couverture associées

Numéro de la base de connaissances : 4612572

## <a name="symptoms"></a>Symptômes

Vous souhaitez filtrer les articles qui seront inclus dans une tâche de traitement par lots de la planification générale, selon les valeurs des enregistrements associés dans la table de couverture des articles. (Par exemple, vous souhaitez filtrer des articles selon leur valeur **Fournisseur** et/ou **Groupe de couverture**). La configuration du filtre pour la tâche de traitement par lots vous permet de créer une jointure entre la table **Articles** et la table **Couverture des articles**, puis de spécifier les valeurs de champ dans la table de couverture des articles de votre requête. Cependant, une fois cette configuration terminée, le système crée toujours des ordres planifiés pour l’ensemble de la couverture des articles, et pas seulement pour les articles correspondant aux valeurs de champ spécifiées dans la table de couverture des articles.

## <a name="resolution"></a>Résolution

Le filtre de la tâche de traitement par lots ne peut filtrer que les articles. Bien que vous puissiez ajouter une jointure à la table **Couverture des articles**, les paramètres de filtre que vous définissez sur cette table n’affecteront pas la sortie de la requête. Au moment de l’exécution, le système exécute la planification pour tous les groupes de couverture et toutes les variantes des articles filtrés. Lorsqu’un article est déjà inclus dans l’exécution, les groupes de couverture inclus dans le filtre de l’article n’affecteront pas la sortie de la planification.
