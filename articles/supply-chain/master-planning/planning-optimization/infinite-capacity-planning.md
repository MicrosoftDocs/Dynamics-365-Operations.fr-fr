---
title: Planification avec une capacité infinie
description: Cet article fournit des informations sur la planification de la capacité infinie. Elle décrit également les limitations actuelles des fonctionnalités.
author: t-benebo
ms.date: 08/09/2022
ms.topic: article
ms.search.form: RouteInventProd
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 7249734e5d2644145a36276dbc818a40b5962805
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740003"
---
# <a name="scheduling-with-infinite-capacity"></a>Programmation avec une capacité infinie

[!include [banner](../../includes/banner.md)]

La fonctionnalité *Planification de capacité infinie pour Planning Optimization* introduit une planification basée sur les informations d’itinéraire. Elle vous permet de planifier des tâches en fonction d’un large éventail de configurations d’itinéraires. La planification couvre les paramètres d’itinéraire fréquemment utilisés, y compris la séquence d’opérations d’itinéraire ou les exigences pour les ressources d’opérations d’itinéraire.

## <a name="turn-the-infinite-capacity-scheduling-feature-on-or-off"></a>Activer ou désactiver la fonction de planification de capacité infinie

Pour pouvoir utiliser cette fonctionnalité, il doit être activé pour votre système. Depuis la version 10.0.29 de Supply Chain Management, la fonctionnalité est activée par défaut. Les administrateurs peuvent activer ou désactiver cette fonctionnalité en recherchant la fonctionnalité *Planification de capacité infinie pour l'optimisation de la planification* dans l'espace de travail [Gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Pour plus d’informations sur cette fonctionnalité, voir [Planification avec sélection des ressources en fonction des capacités](capability-based-scheduling.md).

## <a name="added-functionality"></a>Fonctionnalité ajoutée

La fonctionnalité *Planification des capacités infinies pour Planning Optimization* introduit une planification basée sur les informations d’itinéraire. Par conséquent, une configuration d’itinéraire peut être utilisée pour planifier les processus de production. Bien que cette fonctionnalité présente certaines limitations que le moteur de planification générale déprécié n’a pas, elle prend en charge la fonctionnalité la plus courante requise pour les scénarios de fabrication.

La fonctionnalité considère à la fois les *itinéraires simples* et les *réseaux d’itinéraires*. En utilisant le champ **Suivant** sur une opération d’itinéraire, vous pouvez configurer des itinéraires complexes qui ont plusieurs points de départ et plusieurs opérations qui s’exécutent en parallèle. Le système prendra en compte les structures d’itinéraires complexes de ce type lors de la planification.

De plus, la fonctionnalité prend en charge les *opérations parallèles* dans les itinéraires. En utilisant les options *Principal* et *Secondaire* dans le champ **Priorité** sur les opérations d’itinéraire, vous pouvez définir une structure d’itinéraire dans laquelle une opération d’itinéraire est l’opération principale et une autre opération est secondaire. Dans ce cas, le système prendra en compte la structure d’itinéraire lors de la planification.

Au cours du processus de planification, le système prend également en compte les *besoins en ressources* qui sont spécifiés pour une opération. Le système utilise les besoins en ressources pour déterminer quelles ressources sont requises pour effectuer l’opération. Actuellement, la fonctionnalité *Planification des capacités infinies pour l’optimisation de la planification* prend en charge les types de besoins en ressources suivants :

- Type de ressource
- Ressource
- Groupe de ressources
- Capacité (Pour plus d’informations, voir [Planification avec sélection des ressources en fonction des capacités](capability-based-scheduling.md).)

> [!NOTE]
>
> - Si la ressource et/ou le groupe de ressources sont définis sur une capacité infinie, la planification générale les considérera comme une capacité infinie.
> - Les exigences liées aux ressources humaines, telles que les compétences ou les exigences de certificat, ne sont pas encore prises en charge.

La fonctionnalité prend également en charge les propriétés opérationnelles **Temps de configuration** et **Durée**. Lorsque vous définissez ces propriétés sur une opération d’itinéraire, le processus de planification crée les tâches de configuration et de traitement appropriées.

En résumé, la planification prend en charge les scénarios les plus fréquemment utilisés. Vous pouvez créer l’itinéraire, ajouter des opérations principales et secondaires, définir les opérations suivantes, ajouter des besoins en ressources et ajouter une durée de configuration et une durée d’exécution. Le système prendra alors en compte ces informations lors de la planification.

## <a name="limitations"></a>Limitations

Les limitations suivantes s’appliquent lorsque vous utilisez la fonctionnalité *Planification de la capacité infinie pour l’optimisation de la planification* :

- La fonctionnalité ne prend en charge qu’une capacité infinie.
- La fonctionnalité ne prend pas en charge la fonctionnalité de chargement de ressources.
- La fonctionnalité ne prend pas en compte les rebuts d’itinéraire.
- La fonctionnalité prend en charge la *Durée* uniquement comme sélection de ressource principale.
