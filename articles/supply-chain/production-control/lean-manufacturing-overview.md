---
title: Présentation de lean manufacturing
description: Cet article fournit une vue d'ensemble et la description des fonctionnalités de lean manufacturing dans Dynamics 365 Supply Chain Management.
author: ChristianRytt
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardTransferJob, KanbanBoardWorkCell, KanbanJobSchedulingListPage, LeanProductionFlow, Kanban, KanbanQuantityOverview, KanbanAssignCard, KanbanCirculatingCards, KanbanRules, WHSKanbanWaveTableManagePickingListPool
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19371
ms.assetid: 026c5605-6be7-4fdb-a6f2-8e37a806796c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ba514a6af360074696814278b51ba41327a294d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006989"
---
# <a name="lean-manufacturing-overview"></a>Vue d'ensemble du Lean manufacturing

[!include [banner](../includes/banner.md)]

Cet article fournit une vue d'ensemble et la description des fonctionnalités de lean manufacturing dans Dynamics 365 Supply Chain Management.

Le lean manufacturing offre des outils que vous pouvez utiliser pour modéliser des opérations de production au plus juste. Ces outils prennent en charge et encouragent les concepts et des activités économiques suivants :
-   Création d'une base de lean manufacturing en modélisant les processus de fabrication et logistiques comme flux de production.
-   Mise en œuvre d'un système d'approvisionnement sur demande au plus juste à l'aide de kanbans pour signaler les besoins des demandes.
-   Surveillez et mettez à jour des tâches de kanban.

L'architecture de lean manufacturing est constituée de flux de production, d'activités, et de règles de kanban. Ces structures sont totalement intégrées aux processus Supply Chain Management. Vous pouvez utiliser le lean manufacturing dans un environnement de fabrication en mode mixte combinant différentes stratégies d'approvisionnement et de production. Ces dernières incluent des ordres de fabrication, des lots de commandes pour les secteurs de traitement, des commandes fournisseur, et des ordres de transfert.

| **Important**                                                                                                                                                                                                                                                                |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Supply Chain Management vous permet de prendre en charge la mise en œuvre du concept de lean manufacturing avec des kanbans. Toutefois, une implémentation réussie des principes de production au plus juste dépend des processus entreprise internes que vous utilisez, et des conditions et de l'environnement de production réels. |

## <a name="modeling-manufacturing-and-logistics-processes-as-production-flows"></a>Processus de fabrication et logistiques de modélisation comme flux de production
Pour créer une base de lean manufacturing, modélisez les processus de fabrication et logistiques comme flux de production. Cette activité inclut les tâches suivantes :
1.  Identification des processus pour lesquels vous souhaitez mettre en œuvre une stratégie de réapprovisionnement au plus juste, puis modélisation de ces processus comme flux de production. Vous pouvez ensuite analyser et simplifier les processus. Un des objectifs d'une implémentation de production au plus juste est de réduire les déchets en améliorant le flux des matières et d'informations.
2.  Définition d'un flux de production comme séquence d'activités qui décrit le flux des matières. Une activité de transfert définit le mouvement d'un produit ou de produits d'un emplacement vers un autre. Une activité de processus définit une opération à valeur ajoutée appliquée à un produit.
3.  Création d'une version du flux de production qui définit les exigences du takt time. Ces exigences permettent de calculer les durées de cycle de chaque activité du flux de production. Vous pouvez créer plusieurs versions des flux de production, puis utiliser ces versions pour améliorer les processus.

## <a name="using-kanbans-to-signal-demand-requirements"></a>Utilisation des kanbans pour signaler les besoins de demande
Un système de traction ne produit des marchandises que lorsqu'elles sont nécessaires. Cette pratique réduit les délais de livraison et le stock excédentaire. Vous pouvez utiliser des kanbans pour planifier, suivre et traiter les demandes basées sur les flux de production. Pour créer une structure de kanbans, créez des règles de kanban qui définissent le moment de création des kanbans, ainsi que la façon dont les besoins sont satisfaits. Vous pouvez créer deux types de règles de kanban. Les règles de fabrication créent des tâches de kanban de traitement, et les règles de kanban de prélèvement créent des tâches de kanban de transfert. Vous pouvez définir les stratégies de réapprovisionnement suivantes :
-   Les règles de kanban **Quantité fixe** sont liées à un nombre fixe d'unités de manutention, ce qui signifie que le nombre de kanbans actifs est constant. Lorsque tous les produits d'un kanban sont consommés et que les unités de manutention sont manuellement vidées, un nouveau kanban du même type est créé. Lorsque vous créez des règles de kanban de quantité fixe, vous pouvez calculer les quantités optimales de kanban et de produit utilisées. Le calcul prend en compte la prévision, la demande réelle des commandes en cours, le délai de réapprovisionnement des articles et les demandes historiques.
-   **Prévu** Les règles de kanban réapprovisionnent les besoins qui sont calculés par la planification. La planification génère des kanbans planifiés qui peuvent être confirmés comme kanbans.
-   Les règles de kanban **Événement** réapprovisionnent les besoins émanant des lignes de commande, des lignes de nomenclature de production, des lignes de kanban ou des paramètres de stock minimal. Lorsque des kanbans d'événement sont générés, ils sont liés aux demandes source.

Lorsque des kanbans sont créés, une ou plusieurs tâches de kanban sont générées en fonction des activités du flux kanban définies dans les règles de kanban.

## <a name="monitoring-and-maintaining-kanban-jobs"></a> Surveillance et mise à jour des tâches de kanban
Le lean manufacturing fournit une visibilité vis-à-vis du statut actuel des activités de fabrication et logistiques qui sont régies par les règles de kanban. Par conséquent, vous pouvez planifier et octroyer une priorité aux tâches suivantes :

-   Obtention d'une vue d'ensemble du programme actuel des tâches de kanban.
-   Planification et replanification des tâches de kanban.
-   Effectuez le suivi et l'enregistrement des tâches de kanban.

La liste suivante décrit les tableaux kanban spécialisés :
-   Planification des tâches de kanban : fournit une vue d'ensemble des tâches de kanban. Le tableau affiche les tâches de kanban et leur statut pour une ou plusieurs cellules de travail. Les tâches sont répertoriées selon les périodes de planification (jours ou semaines) définies dans le modèle de flux de production. Le tableau affiche également la consommation de capacité pour chaque période de planification, afin de pouvoir surveiller la charge prévue. Vous pouvez modifier le statut des tâches de kanban, replanifier des opérations kanban dans différentes périodes de planification, et effectuer d'autres tâches.
-   Tableau kanban pour les tâches de transfert – Ce tableau fournit une vue d'ensemble des tâches de transfert en cours. Vous pouvez mettre à jour et enregistrer les listes de prélèvements, débuter et terminer des tâches de transfert, et effectuer d'autres tâches.
-   Tableau kanban pour les opérations de traitement – cette carte est conçue pour prendre en charge le flux de production normal et pour donner une vue d'ensemble de la situation actuelle dans une ou plusieurs cellules de travail. À partir de ce tableau, les kanbans peuvent être classés par ordre de priorité, prélevés ou fabriqués. Le tableau est également conçu pour prendre en charge la lecture des codes-barres pour la génération d'états de kanban.

## <a name="kanban-jobs-and-integration-with-supply-chain-management-processes"></a>Tâches de kanban et intégration avec les processus Supply Chain Management
Les tâches de kanban sont totalement intégrées aux processus actuels pour les mouvements de stock dans Supply Chain Management.
-   Vous pouvez effectuer des activités de prélèvement pour réapprovisionner la matière utilisée pour répondre aux conditions des tâches de kanban.
-   Vous pouvez imprimer des cartes kanban, les cartes kanban en circulation, et les listes de prélèvements pour prendre en charge l'utilisation des kanbans. Ces documents sont utilisés pour représenter, suivre et enregistrer les tâches de kanban dans l'entrepôt et la production.
-   Vous pouvez enregistrer le prélèvement et les activités de transfert dans le stock en scannant les codes-barres.

En outre, le lean manufacturing prend en charge les processus d'achat et de facturation pour les services référencés par des activités sous-traitées.
-   Vous pouvez affecter des lignes de contrat d'achat et des services aux activités sous-traitées.
-   Vous pouvez créer des commandes fournisseur et des avis de réception périodiques pour prendre en charge l'achat et la facturation des services.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]