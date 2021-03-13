---
title: Prévisions, ordres de travail et projets
description: Cette rubrique explique comment intégrer les prévisions et les ordres de travail avec le module Gestion et comptabilité du projet dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderProjCostInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f062b5463b54e9bcf32ed6f17263811c4bb24138
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021020"
---
# <a name="forecasts-work-orders-and-projects"></a>Prévisions, ordres de travail et projets

[!include [banner](../../includes/banner.md)]

 

Dans le module Gestion des actifs, l'intégration au module **Gestion et comptabilité du projet** permet d'optimiser le contrôle des coûts, de telle sorte que les utilisateurs sont en mesure de suivre les coûts pour les prévisions du type de tâche de maintenance et les tâches de l'ordre de travail.

Le suivi des prévisions du type de tâche de maintenance exige deux paramètres :

1. Sélectionnez un projet dans **Gestion des actifs** > **Configuration** > **Paramètres de gestion des actifs**, puis, dans l'onglet **Actifs** > sur l'organisateur **Projet**, dans le champ **Projet de prévision de maintenance**, sélectionnez un projet.

2. Lorsque vous créez une ligne de valeur par défaut pour le type de tâche de maintenance, un numéro d'activité est automatiquement créé pour la ligne sur la page **Type de tâche de maintenance par défaut** (**Gestion des actifs** > **Configuration** > **Tâches** > **Type de tâche de maintenance par défaut**).

Les prévisions du type de tâches de maintenance ont deux objectifs : 

- Vous pouvez suivre les coûts sur les prévisions de type de tâche de maintenance dans le module **Gestion de projets et comptabilité**. 
- Les prévisions sont automatiquement transférées à un projet de tâche de l'ordre de travail lorsque vous sélectionnez un type de tâche de maintenance.

Pour suivre les coûts sur les tâches de l'ordre de travail, vous devez d'abord paramétrer les projets de l'ordre de travail. Pour plus d'informations, voir [Configuration du projet de l'ordre de travail](../setup-for-work-orders/work-order-project-setup.md).

## <a name="work-order-job-projects"></a>Projets de tâche d'ordre de travail

Lorsque vous créez une tâche sur un ordre de travail, le projet est déterminé par le paramétrage du projet parent pour les ordres de travail sur la page **Configuration du projet de l'ordre de travail** (**Gestion des actifs** > **Configuration** > **Ordres de travail** > **Configuration du projet**).

Les projets de tâche d'ordre de travail sont créés à l'aide d'une combinaison des informations d'ordres de travail suivantes :

- Le type d'ordre de travail sélectionné sur l'ordre de travail 
- L'emplacement fonctionnel lié à l'actif sur la tâche de l'ordre de travail
- Le type d'actif lié à l'actif sur la tâche de l'ordre de travail  
- L'heure de début et l'heure de fin prévues définies sur l'ordre de travail  

Certaines de ces informations pourraient rester introuvables sur un ordre de travail. Par conséquent, la recherche d'un projet d'ordre de travail parent s'effectue à l'aide de la combinaison de données disponibles et la sélection de l'ID de projet qui correspond aux données de l'ordre de travail.

Par exemple, dans l'illustration suivante, en raison de la façon dont le type d'actif **Moteur de camion** est configuré, chaque tâche de l'ordre de travail est créée avec le type d'actif **Moteur de camion** comme sous-projet de l'ID de projet 000186.

![Figure 1](media/01-integration-to-pma.png)

L'objectif de l'ID de projet sur la tâche de l'ordre de travail, et le numéro d'activité associé, consiste à suivre les coûts associés à la tâche de l'ordre de travail, et l'actif qui y est sélectionné, dans le module **Gestion de projet et comptabilité**. (Pour afficher l'ID du projet et le numéro d'activité, sélectionnez **Gestion des actifs** > **Commun** > **Ordres de travail** > **Tous les ordres de travail**, puis sélectionnez l'ordre de travail. Dans l'organisateur **Détails de ligne**, le champ **ID de projet** indique l'ID du projet et le champ **Numéro d'activité** précise le numéro de l'activité.) Pour plus d'informations sur le contrôle des coûts dans Gestion des actifs, voir [Contrôle de date et de coût](../controlling-and-reporting/cost-and-date-control.md).

L'illustration suivante présente une vue d'ensemble graphique des projets d'ordre de travail et des activités de projet associées.

![Figure 2](media/02-integration-to-pma.png)

Lorsqu'une nouvelle tâche d'ordre de travail est créée sur un ordre de travail, un projet est automatiquement créé pour la tâche. Les dimensions financières pour l'actif associé à la tâche de l'ordre de travail sont automatiquement transférées au projet de l'ordre de travail.

L'activité du projet qui est créée pour une tâche de l'ordre de travail a des informations associées qui y sont rattachées. Ces informations concernent le type de tâche de maintenance, la variante du type de tâche de maintenance et le commerce. Elles sont utiles si, par exemple, vous créez une commande fournisseur à partir d'un ordre de travail (voir [Approvisionnement](../work-orders/procurement.md)) ou si vous utilisez le module **Gestion et comptabilité du projet** pour l'enregistrement des heures.

Si l'actif a été installé sur un poste technique et qu'il est installé ensuite sur un autre poste technique, les dimensions financières liées au nouveau poste technique sont automatiquement mises à jour sur l'actif. Ensuite, lorsque vous créez une tâche de l'ordre de travail pour l'actif, le projet associé se voit automatiquement attribuer les dimensions financières qui sont désormais associées à l'actif. Par conséquent, lorsque vous utilisez des postes techniques, les coûts peuvent toujours faire l'objet d'un suivi dans les postes techniques sur lesquels un actif a été installé à un moment donné. La mise à jour automatique des dimensions financières garantit la traçabilité complète des coûts pour le contrôle et la génération des états du projet.

## <a name="work-order-projects-work-order-lifecycle-states-project-stages-and-project-types"></a>Projets d'ordre de travail, états du cycle de vie de l'ordre de travail, stades de projet et types de projet

Pour garantir l'utilisation appropriée des états de cycle de vie des ordres de travail et des stades de projet associés, tenez compte des dépendances liées au module **Gestion et comptabilité du projet** :

- Dans le module **Gestion et comptabilité du projet**, les stades de projet sont paramétrés sur les types de projet sur la page **Paramètres de gestion et comptabilité des projets**.  
- Sur la page **Paramètres de gestion et comptabilité des projets**, utilisez les cases à cocher pour sélectionner les stades de projet appropriés pour tous les types de projets que vous allez utiliser. Dans les illustrations suivantes, cinq stades (**Créé**, **Estimé**, **Prévu**, **En cours** et **Terminé**) sont marqués pour les types de projet **Régie** et **Interne**. Ces cinq stades conviennent à la fois pour les tâches de maintenance de service et de maintenance interne.
- Dans le module **Gestion des actifs**, les types de projets sont définis par les groupes de projets que vous paramétrez sur la page **Configuration du projet de l'ordre de travail** > onglet **Groupe de projets** (**Gestion des actifs** > **Configuration** > **Ordre de travail** > **Configuration du projet**).  
- Les groupes de projets configurés sur la page **Configuration du projet de l'ordre de travail** sont utilisés lorsque vous créez des ordres de travail. Lorsqu'un ordre de travail est créé, un projet est automatiquement créé.  
- Chaque état du cycle de vie d'ordres de travail doit avoir un stade de projet associé.  
- Le stade de projet lié à un état du cycle de vie de l'ordre de travail doit être défini comme stade actif pour le groupe de projets défini dans le projet de l'ordre de travail. Le projet de l'ordre de travail est créé automatiquement sur un ordre de travail.
- Lorsque vous créez un ordre de travail, l'attribution automatique d'un projet est basée sur le paramétrage sur la page **Configuration du projet de l'ordre de travail**.  

Les illustrations suivantes présentent les associations entre les groupes de projets de l'ordre de travail, les types de projets associés, les stades de projet, les états du cycle de vie de l'ordre de travail.

![Figure 3](media/03-integration-to-pma.png)

![Figure 4](media/04-integration-to-pma.png)

![Figure 5](media/05-integration-to-pma.png)

Pour plus d'informations sur la configuration des projets de l'ordre de travail, voir [Configuration du projet de l'ordre de travail](../setup-for-work-orders/work-order-project-setup.md). Pour plus d'informations sur la manière de créer des états du cycle de vie de l'ordre de travail, consultez [États du cycle de vie de l'ordre de travail](../setup-for-work-orders/work-order-lifecycle-states.md).

L'illustration suivante présente une vue d'ensemble graphique des différents projets créés dans le module **Gestion des actifs** pour activer l'intégration avec le module **Gestion de projets et comptabilité**. Elle présente également les processus de travail auxquels les projets sont liés.

![Figure 6](media/06-integration-to-pma.png)

