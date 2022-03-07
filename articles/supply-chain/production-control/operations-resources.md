---
title: Ressources Operations
description: Les ressources opérationnelles réalisent les activités d’un projet ou d’un processus de production. Elles peuvent être de différents types et avoir différentes capacités.
author: johanhoffmann
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: OpResLifecycleManagementWorkspace, WrkCtrCapability, WrkCtrResourceGroup, WrkCtrResourceAbilityMap, OpResCapacityPlanningWorkspace, WrkCtrCapResGraph, WrkCtrResourceRequirementPart, WrkCtrCapResGraphDialog, WrkCtrResourceCopy, WrkCtrCapResStatistic
audience: Application User
ms.reviewer: kamaybac
ms.custom: 61943
ms.assetid: a3847f07-fca4-4140-a26f-d83c6ac68dde
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9296ea874acece9af6be58ccfe777f8713a4d279
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7566717"
---
# <a name="operations-resources"></a>Ressources Operations

[!include [banner](../includes/banner.md)]

Les ressources opérationnelles réalisent les activités d’un projet ou d’un processus de production. Elles peuvent être de différents types et avoir différentes capacités. 

## <a name="operations-resources"></a>Ressources Operations

Les ressources opérationnelles sont les machines, outils, collaborateurs, installations, zones physiques ou fournisseurs qui exécutent les activités d’un projet ou d’un processus de production. Elles peuvent être de différents types et avoir différentes capacités.

-   **Fournisseur** – Ressource externe qui réalise des activités de projet ou des opérations de production. Il peut s’agir par exemple d’un sous-traitant. En liant les ressources fournisseur à un compte fournisseur, vous pouvez générer des achats pour les sous-traitants, selon les lignes de nomenclature ou les lignes de production.
-   **Ressources humaines** – Collaborateur à un projet ou à la production qui réalise une activité, seul ou en tant qu’opérateur d’un outil ou d’une machine. Si vous utilisez la fonctionnalité Ressources humaines, vous pouvez lier des ressources humaines à un collaborateur. Le moteur de planification peut ensuite répartir les ressources, en fonction des compétences définies pour le collaborateur correspondant.
-   **Machine** – Machine ou autre équipement de production nécessaire dans la production.
-   **Outil** – Instrument ou appareil qui est généralement utilisé avec une autre ressource pour réaliser une activité dans un projet ou dans la production.
-   **Emplacement** – Emplacement physique de taille spécifique nécessaire pour réaliser une activité. Il peut s’agir par exemple d’une zone d’assemblage.
-   **Installation** – Bâtiment ou structure fixe nécessaire pour réaliser une activité.

## <a name="calendars"></a>Calendriers
Un calendrier peut être affecté à une ressource opérationnelle et décrit la capacité (en heures) de cette ressource. Les temps de travail de la ressource opérationnelle sont déterminés par le calendrier affecté au groupe de ressources auquel la ressource opérationnelle appartient. Vous pouvez définir une date d’effet et une date d’expiration pour le calendrier affecté. Vous pouvez ensuite affecter plusieurs calendriers à une ressource opérationnelle. Toutefois, les dates des calendriers affectés ne peuvent pas se chevaucher, et la ressource opérationnelle ne peut être affectée qu’à un calendrier à la fois. **Remarque :** à défaut de calendrier de travail effectif pour un groupe de ressources, par exemple si le dernier ou le seul calendrier affecté a expiré, vous ne pouvez plus accéder aux ressources opérationnelles affectées au groupe de ressources pour la planification de la production et l’ordonnancement. Vous pouvez également affecter un calendrier à un groupe de ressources pour spécifier les temps de travail du groupe de ressources et de toutes les ressources opérationnelles affectées au groupe de ressources. La capacité du groupe de ressources est calculée comme étant la somme des capacités de chaque ressource opérationnelle affectée à ce groupe de ressources. Le calendrier affecté à un groupe de ressources peut changer dans le temps.

## <a name="resource-capabilities"></a>Capacités de ressources
Une capacité est la capacité d’une ressource opérationnelle à réaliser une activité spécifique. Vous pouvez affecter une ou plusieurs capacités à une ressource opérationnelle. Le moteur de planification alloue ensuite les ressources en faisant correspondre les demandes de ressources de chaque activité aux capacités des ressources opérationnelles disponibles. Des capacités peuvent être affectées à tous les types de ressources opérationnelles (**Outil**, **Fournisseur**, **Machine**, **Ressources humaines**, **Emplacement** ou **Installation**). Pour affecter des capacités aux ressources opérationnelles pour une durée limitée, définissez une date de début et une date d’expiration pour l’affectation de capacités. Pour plus d’informations, voir [Capacités de ressources](resource-capabilities.md).

## <a name="resource-groups"></a>Groupes de ressources
Un groupe de ressources est un ensemble de ressources opérationnelles qui représente la granularité à laquelle vous souhaitez planifier les ressources lorsque vous utilisez la méthode d’ordonnancement. Par conséquent, les groupes de ressources correspondent à l’organisation physique des cellules de travail, démarquée par des lignes jaunes dans l’atelier de production. Le groupe de ressources définit le site, l’unité de production et le contexte d’entrepôt pour les ressources opérationnelles affectées au groupe. Lorsque vous affectez une ressource opérationnelle à un groupe de ressources, la ressource peut être planifiée sur le site où se trouve le groupe de ressources. Il n’est pas nécessaire d’affecter les ressources opérationnelles que vous créez à un groupe de ressources. Toutefois, une ressource opérationnelle doit être affectée à un groupe de ressources avant de pouvoir être planifiée pour effectuer la tâche. Une ressource opérationnelle peut être affectée à un groupe de ressources pendant une durée limitée. Vous pouvez également affecter une ressource opérationnelle à plusieurs groupes de ressources, afin de pouvoir partager la ressource sur plusieurs sites. Toutefois, les dates d’effet et d’expiration ne peuvent pas se chevaucher. En d’autres termes, vous ne pouvez pas affecter une ressource opérationnelle à deux groupes de ressources en même temps. Les modifications des affectations de groupes de ressources sont effectives uniquement pour les nouvelles répartitions de ressources. Les réservations de capacités pour les tâches, les opérations et les prévisions en heures du projet déjà planifiées ne sont pas affectées. **Remarque :** lorsque vous affectez des ressources opérationnelles de type **Fournisseur** à un groupe de ressources, toutes les ressources opérationnelles affectées à ce groupe de ressources doivent avoir le type **Fournisseur** et être liées au même compte fournisseur.

## <a name="production-units"></a>Unités de production
Une unité de production est une unité administrative qui combine des groupes de ressources. Une unité de production peut inclure plusieurs groupes de ressources. Un groupe de ressources peut toutefois être affecté à une seule unité de production. Une unité de production reflète la présentation physique des ressources de production et n’a aucun effet sur les transactions ni sur leur traitement. Vous devez associer une unité de production à un site. Vous pouvez également affecter un entrepôt de prélèvement et un entrepôt de stockage à une unité de production. Vous pouvez utiliser une unité de production pour regrouper et filtrer les données liées à la production. Par exemple, un gestionnaire d’atelier peut afficher une vue d’ensemble pratique de la charge de travail en cours et de la capacité disponible d’une unité de production donnée. Vous pouvez modifier l’unité de production affectée à un groupe de ressources. Vous pouvez également supprimer une unité de production. Cependant, ces modifications de l’unité de production sont effectives uniquement pour les nouvelles commandes créées après l’exécution du calcul PDP/MRP. Pour appliquer les modifications de l’unité de production aux commandes existantes, vous devez procéder manuellement.

## <a name="resource-scheduling"></a>Planification des ressources
Les ressources opérationnelles sont affectées aux activités lorsqu’un projet ou une production est planifié. Deux méthodes de planification sont disponibles : ordonnancement et planification des tâches. Lorsque vous utilisez l’ordonnancement, chaque opération ou activité de projet est planifiée sur le groupe de ressources qui contient les ressources opérationnelles correspondant aux demandes de ressources spécifiées pour l’opération. Si une ressource opérationnelle spécifique est requise pour l’opération, la planification réserve de la capacité uniquement pour une ressource opérationnelle spécifique du groupe. La planification des tâches est une forme de planification plus détaillée que l’ordonnancement. Elle décompose chaque opération en tâches individuelles. Ces tâches sont ensuite affectées aux ressources opérationnelles qui les effectueront. La planification réserve de la capacité sur les groupes de ressources en fonction des durées d’opération définies pour la gamme de production ou les activités du projet. Si vous travaillez avec une capacité finie, la planification dépend de la disponibilité des ressources opérationnelles requises pour réaliser l’activité. Pour l’ordonnancement, la capacité du groupe de ressources est la somme de la capacité disponible des ressources opérationnelles qui font partie de ce groupe. Les réservations de capacité existantes pour les ressources opérationnelles sont considérées comme capacité non disponible. Si la capacité disponible est insuffisante pour la production, les ordres de fabrication peuvent être retardés ou arrêtés. Dans la page **Ressources**, vous pouvez définir plusieurs propriétés qui contrôlent comment les réservations de capacités sont effectuées :

-   **Capacité** – Spécifiez la capacité horaire de la ressource opérationnelle en termes d’unité de mesure de la capacité.
-   **Capacité du traitement par lots** – Spécifiez le nombre maximal de pièces que la ressource opérationnelle peut traiter par passage.
-   **Pourcentage de rendement** – Spécifiez le rendement attendu de la ressource opérationnelle. Le pourcentage d’efficacité règle le débit de la ressource opérationnelle et affecte le temps réservé pour celle-ci. Le délai des opérations qui utilisent la ressource opérationnelle est également ajusté en conséquence. Voici la formule utilisée pour le calcul : Temps de planification = Temps x 100 ÷ Pourcentage de rendement. *Temps* comprend à la fois la durée d’exécution et le temps de réglage.
-   **Pourcentage d’ordonnancement** – Spécifiez le pourcentage maximal de capacité de la ressource opérationnelle à utiliser dans l’ordonnancement. Pour permettre une certaine flexibilité de capacité lors de la planification de tâches, vous devez définir ce pourcentage sur une valeur inférieure à 100 %.
-   **Capacité finie** – Définissez cette option sur **Oui** si la ressource opérationnelle est planifiée en fonction de la capacité réelle disponible, et si les réservations de capacité existantes sont prises en compte. Si cette option est définie sur **Non**, la ressource opérationnelle est supposée avoir une capacité infinie, et elle peut donc être surréservée.
-   **Propriété limitée** – Définissez cette option sur **Oui** si vous souhaitez planifier la ressource opérationnelle en fonction de la capacité réelle disponible par rapport aux propriétés de planification du temps de travail requises.
-   **Réservation exclusive** – Définissez cette option sur **Oui** si vous ne souhaitez pas que la ressource opérationnelle soit utilisée pour une autre tâche ou opération jusqu’à ce que la production actuelle soit achevée. Dans ce cas, la ressource opérationnelle ne peut pas être utilisée, même s’il y a des écarts dans son temps d’exécution.
-   **Ressource critique** – Définissez la ressource opérationnelle comme ressource critique. Une ressource critique est planifiée à l’aide de la capacité finie si les options **Capacité finie** et **Planification critique** de la page **Plans généraux** sont sélectionnées.

Pour planifier plusieurs ressources opérationnelles simultanément pour exécuter, par exemple, une opération en production, vous devez définir les besoins des différentes ressources à l’aide des opérations principales et secondaires. Vous pouvez également contrepasser plusieurs ressources opérationnelles ayant une capacité différente. Les ressources opérationnelles planifiées pour l’opération principale déterminent la durée de l’activité.

## <a name="lean-work-cells"></a>Cellules de travail au plus juste
Vous pouvez spécifier qu’un groupe de ressources est une cellule de travail au plus juste. Le groupe de ressources peut ensuite faire partie d’un flux de production. En définissant un groupe de ressources comme cellule de travail au plus juste, le groupe de ressources et les ressources opérationnelles affectées ne peuvent pas être allouées aux opérations d’un ordre de fabrication ou d’une prévision en heures de projet. Pour chaque groupe de ressources qui sert de cellule de travail au plus juste, vous devez spécifier les informations suivantes :

-   **Calendrier** – Calendrier de travail de la cellule de travail, qui doit avoir la propriété d’un jour de travail standard.
-   **Entrepôt et emplacement d’entrée** – Emplacement par défaut utilisé pour prélever le matériel pour une activité.
-   **Entrepôt et emplacement de sortie** – Emplacement par défaut où est stockée toute la sortie de la cellule de travail.
-   **Catégorie de coûts d’exécution** – Cette catégorie doit être définie pour la cellule de travail si la main-d’œuvre directe est suivie dans l’évaluation des coûts.

Lorsqu’un groupe de ressources est utilisé comme cellule de travail au plus juste, la capacité de la cellule de travail est spécifiée directement dans le groupe de ressources. Par conséquent, il n’est pas nécessaire d’affecter des ressources opérationnelles au groupe de ressources. Une ressource opérationnelle de type **Fournisseur** doit être affectée à la cellule de travail uniquement si la cellule de travail est gérée par un sous-traitant. Si vous affectez une ressource opérationnelle à un groupe de ressources marqué comme cellule de travail, la capacité de la cellule de travail n’est pas affectée.

## <a name="costing-resources"></a>Ressources d’évaluation des coûts
Lorsque vous définissez une activité telle qu’une opération de gamme ou une prévision en heures de projet, vous pouvez définir les besoins d’une ressource opérationnelle ou d’un groupe de ressources spécifique. Toutefois, vous pouvez également spécifier les besoins d’une ressource opérationnelle d’un type spécifique, ou d’une ressource opérationnelle ayant une capacité ou une compétence spécifique. Pour cette raison, l’affectation de ressources réelle n’est pas effectuée jusqu’à ce que l’activité soit planifiée et la capacité réservée. Par conséquent, sur une opération de gamme, vous pouvez spécifier que l’estimation et le calcul de nomenclature doivent être basés sur une ressource opérationnelle spécifique. Cette ressource opérationnelle est appelée ressource d’évaluation des coûts. Vous pouvez également transférer les catégories de coûts et les durées d’opération de la ressource d’évaluation des coûts vers l’activité. Lorsque l’opération est planifiée, l’estimation et le calcul de nomenclature sont effectués à l’aide de la ressource opérationnelle réellement planifiée.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]