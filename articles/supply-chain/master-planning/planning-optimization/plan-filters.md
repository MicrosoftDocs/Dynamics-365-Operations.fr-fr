---
title: Appliquer les filtres à un plan
description: Cet article explique comment utiliser des filtres sur un plan lorsque la fonctionnalité Optimisation de la planification est utilisée.
author: t-benebo
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: c2df379be0876225bc7b0301d21f4e6660b04eb6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875302"
---
# <a name="apply-filters-to-a-plan"></a>Appliquer les filtres à un plan

[!include [banner](../../includes/banner.md)]

Lorsque la fonctionnalité d’Optimisation de la planification est utilisée, vous pouvez appliquer un filtre à un plan. Le **filtre de plan** est toujours appliqué lors d’une exécution de planification. Un **filtre de plan** est utile si vous souhaitez limiter un plan à un groupe d’articles spécifique et veiller à ce qu’aucun autre article ne soit inclus dans le cadre de la planification obtenue.

Si un **filtre de plan** est appliqué et si un filtre de runtime est également appliqué pendant l’exécution de la planification, seule l’intersection des deux filtres est comprise dans l’exécution de la planification.

Le **Filtre de plan** peut être accessible depuis **Plans généraux** lorsque l’Optimisation de la planification est utilisée.

## <a name="example-scenario"></a>Exemple de scénario

Un filtre de plan est configuré. Il inclut des éléments A, B et C. Les exécutions de la planification ont ensuite lieu pour le même plan, mais différents filtres de runtime s’appliquent :

- **Filtre de runtime qui inclut l’article D :** aucun article n’est planifié, car il n’existe aucune intersection entre le filtre de plan et le filtre de runtime.
- **Filtre de runtime qui inclut l’article A et D :** seul l’article A est inclus dans l’exécution de la planification, car l’article D ne fait pas partie du filtre de plan.
- **Filtre de runtime qui inclut l’article B :** seul l’article B est inclus dans l’exécution de la planification et le résultat de planification précédent pour l’article A est conservé.
- **Filtre de runtime qui inclut tous les articles (filtre vierge) :** les articles A, B et C sont inclus dans l’exécution de la planification et le résultat de la planification précédente pour les articles A et B est remplacé.

> [!NOTE]
> Si vous définissez un filtre de plan sur le plan sélectionné comme **Schéma directeur dynamique actuel** sur la page **Paramètres de planification principale**, alors la fonctionnalité de plan directeur dynamique sera limitée aux éléments filtrés. Par exemple, si les exigences nettes sont mises à jour pour un article qui ne fait pas partie du filtre de plan, aucun résultat ne sera généré.

## <a name="related-resources"></a>Ressources associées

[Vue d’ensemble de l’optimisation de la planification](planning-optimization-overview.md)

[Prise en main de l’Optimisation de la planification](get-started.md)

[Analyse de concordance d’optimisation de la planification](planning-optimization-fit-analysis.md)

[Afficher l’historique du plan et les journaux de planification](plan-history-logs.md)

[Annuler une tâche de planification](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
