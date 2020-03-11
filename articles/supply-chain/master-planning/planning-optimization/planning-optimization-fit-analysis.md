---
title: Analyse de concordance d'optimisation de la planification
description: Cette rubrique explique comment vérifier votre configuration et vos données par rapport aux fonctionnalités de la fonction d'optimisation de la planification.
author: ChristianRytt
manager: AnnBe
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 25f3b39d0e6e88eb3f042ab93773e9724528ab0f
ms.sourcegitcommit: a688c864fc609e35072ad8fd2c01d71f6a5ee7b9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/20/2020
ms.locfileid: "3076176"
---
# <a name="planning-optimization-fit-analysis"></a>Analyse de concordance d'optimisation de la planification

[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

Pour voir la compatibilité de votre configuration actuelle et des données avec la fonction d'optimisation de la planification, accédez à **Planification** \> **Configuration** \> **Analyse de concordance de l'optimisation de la planification**, puis sélectionnez **Exécuter l'analyse**. Si l'analyse permet de trouver des incohérences, elles sont répertoriées sur la même page. (L'exécution de l'analyse peut prendre quelques minutes.)

> [!NOTE]
> Si des incohérences sont détectées, vous pouvez utiliser l'optimisation de la planification. Les résultats de l'analyse de concordance indiquent simplement les endroits où le service de planification n'honorera pas votre configuration actuelle. En d'autres termes, ils affichent les endroits où certains processus pourraient être ignorés ou ne pourraient pas être pris en charge.

## <a name="analysis-results-example-1"></a>Résultats d'analyse : Exemple 1

- **Fonctionnalité :** Production
- **Problème :** les articles au niveau de la nomenclature supérieure à zéro : 56
- **Explication :** l'analyse de concordance a trouvé 56 articles avec une configuration de nomenclature pour la production. Puisque la version actuelle de l'optimisation de la planification en prend pas en charge la production, l'optimisation de la planification génèrera les commandes fournisseur planifiées plutôt que les ordres de production planifiés. Elle affichera également un avertissement qui répertorie les articles concernés.

### <a name="analysis-results-example-2"></a>Résultats d'analyse : Exemple 2

- **Fonctionnalité :** Actions
- **Problème :** Groupes de couverture avec calcul des actions activé : 6
- **Explication :** l'analyse de concordance a trouvé six groupes de couverture où le calcul des actions est activé. Puisque la version actuelle de l'optimisation de la planification ne prend pas en charge les actions, aucune action ne sera générée pendant la planification.

## <a name="related-resources"></a>Ressources associées

[Vue d'ensemble de l'optimisation de la planification](planning-optimization-overview.md)

[Prise en main de l'Optimisation de la planification](get-started.md)

[Afficher l'historique du plan et les journaux de planification](plan-history-logs.md)

[Appliquer les filtres à un plan](plan-filters.md)

[Annuler une tâche de planification](cancel-planning-job.md)
