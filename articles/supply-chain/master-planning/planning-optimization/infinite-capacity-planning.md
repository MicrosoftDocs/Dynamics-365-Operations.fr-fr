---
title: Planification avec une capacité infinie
description: Cette rubrique fournit des informations sur la planification de capacité infinie pour Planning Optimization. Elle décrit également les limitations actuelles des fonctionnalités.
author: crytt
ms.date: 6/9/2021
ms.topic: article
ms.search.form: RouteInventProd
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fc40dc2bcf1969e4c566b624a9425638e69ab2a17892f035aeabb74068aadd14
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718970"
---
# <a name="scheduling-with-infinite-capacity"></a>Planification avec une capacité infinie

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

La fonctionnalité *Planification de capacité infinie pour Planning Optimization* introduit une planification basée sur les informations d’itinéraire. Elle vous permet de planifier des tâches en fonction d’un large éventail de configurations d’itinéraires. La planification de Planning Optimization couvre les paramètres d’itinéraire fréquemment utilisés, y compris la séquence d’opérations d’itinéraire ou les exigences pour les ressources d’opérations d’itinéraire.

## <a name="turn-on-the-infinite-capacity-scheduling-feature"></a>Activer la fonction de planification de capacité infinie

Si votre système n’inclut pas déjà la fonctionnalité décrite dans cette rubrique, ouvrez l’espace de travail [Gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) et activez la fonctionnalité *Planification de capacité infinie pour Planning Optimization*.

## <a name="added-functionality"></a>Fonctionnalité ajoutée

La fonctionnalité *Planification des capacités infinies pour Planning Optimization* introduit une planification basée sur les informations d’itinéraire. Par conséquent, une configuration d’itinéraire peut être utilisée pour planifier les processus de production. Bien que cette fonctionnalité présente certaines limitations que la planification principale intégrée n’a pas, elle prend en charge la fonctionnalité la plus courante requise pour les scénarios de fabrication.

La fonctionnalité considère à la fois les *itinéraires simples* et les *réseaux d’itinéraires*. En utilisant le champ **Suivant** sur une opération d’itinéraire, vous pouvez configurer des itinéraires complexes qui ont plusieurs points de départ et plusieurs opérations qui s’exécutent en parallèle. Le système prendra en compte les structures d’itinéraires complexes de ce type lors de la planification.

De plus, la fonctionnalité prend en charge les *opérations parallèles* dans les itinéraires. En utilisant les options *Principal* et *Secondaire* dans le champ **Priorité** sur les opérations d’itinéraire, vous pouvez définir une structure d’itinéraire dans laquelle une opération d’itinéraire est l’opération principale et une autre opération est secondaire. Dans ce cas, le système prendra en compte la structure d’itinéraire lors de la planification.

Au cours du processus de planification, le système prend également en compte les *besoins en ressources* qui sont spécifiés pour une opération. Le système utilise les besoins en ressources pour déterminer quelles ressources sont requises pour effectuer l’opération. Actuellement, la fonctionnalité *Planification des capacités infinies pour l’optimisation de la planification* prend en charge les types de besoins en ressources suivants :

- Type de ressource
- Ressource
- Groupe de ressources
- Capacité

> [!NOTE]
> Les exigences liées aux ressources humaines, telles que les compétences ou les exigences de certificat, ne sont pas encore prises en charge.

La fonctionnalité prend également en charge les propriétés opérationnelles **Temps de configuration** et **Durée**. Lorsque vous définissez ces propriétés sur une opération d’itinéraire, le processus de planification crée les tâches de configuration et de traitement appropriées.

En résumé, la planification de Planning Optimization prend en charge les scénarios les plus fréquemment utilisés. Vous pouvez créer l’itinéraire, ajouter des opérations principales et secondaires, définir les opérations suivantes, ajouter des besoins en ressources et ajouter une durée de configuration et une durée d’exécution. Le système prendra alors en compte ces informations lors de la planification.

## <a name="limitations"></a>Limitations

Les limitations suivantes s’appliquent lorsque vous utilisez la planification pour Planning Optimization :

- La fonctionnalité prend uniquement en charge la planification des tâches. Les paramètres liés à la planification des opérations ne sont pas pris en compte lors de la planification, quelle que soit la méthode de planification sur les plans directeurs.
- La fonctionnalité ne prend en charge qu’une capacité infinie.
- La fonctionnalité ne prend pas en charge la fonctionnalité de chargement de ressources.
- La fonctionnalité ne prend pas en compte les rebuts d’itinéraire.
- La fonctionnalité prend en charge la *Durée* uniquement comme sélection de ressource principale.

Notez que la fonctionnalité *Planification de capacité infinie pour Planning Optimization* est constamment améliorée. Microsoft prévoit d’introduire la prise en charge de paramètres de planification supplémentaires dans les prochaines versions.
