---
title: Prévisions, ordres de travail et projets
description: Cette rubrique explique comment intégrer les prévisions et les ordres de travail avec le module Gestion et comptabilité du projet dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5e986d139ac9d0a7729bb9787f05332bcc09f59b
ms.sourcegitcommit: 109a6ef2d20758dc4a25c51b11e22dd2214a1cc4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1886814"
---
# <a name="forecasts-work-orders-and-projects"></a>Prévisions, ordres de travail et projets

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Dans le module Gestion des actifs, l'intégration au module **Gestion et comptabilité du projet** a été effectuée pour optimiser le contrôle des coûts, ce qui permet aux utilisateurs de suivre les coûts pour les prévisions du type de tâche de maintenance et les tâches d'ordre de travail.

Deux paramètres doivent être définis pour suivre les prévisions du type de tâche de maintenance :

1. Sélectionnez un projet dans le lien **Gestion des actifs** > **Configuration** > **Paramètres de gestion des actifs** > **Actifs** > le raccourci **Projet** > le champ **Projet de prévisions en matière de maintenance**.

2. Dans **Type de tâche de maintenance par défaut**, lorsque vous créez une ligne de valeur par défaut pour le type de tâche de maintenance, un numéro d'activité est automatiquement créé pour la ligne (**Gestion des actifs** > **Configuration** > **Tâches** > **Type de tâche de maintenance par défaut**).

Les prévisions de type de tâche de maintenance ont deux objectifs : permettre de suivre les coûts pour les prévisions de type de tâche de maintenance dans le module **Gestion et comptabilité du projet**. En outre, les prévisions sont automatiquement transférées à un projet de tâche de l'ordre de travail lorsque vous sélectionnez un type de tâche de maintenance.

Pour suivre les coûts sur les tâches de l'ordre de travail, vous devez d'abord paramétrer les projets de l'ordre de travail. Reportez-vous à la section [Configuration du projet de l'ordre de travail](../setup-for-work-orders/work-order-project-setup.md) pour obtenir une description de la procédure.

## <a name="work-order-job-projects"></a>Projets de tâche d'ordre de travail

Lorsque vous créez une tâche sur un ordre de travail, le projet est déterminé par le paramétrage du projet parent pour les ordres de travail dans **Gestion des actifs** > **Configuration** > **Ordres de travail** > **Configuration du projet**.

Les projets de tâche d'ordre de travail sont créés à l'aide d'une combinaison des informations d'ordres de travail suivantes :

- Le type d'ordre de travail sélectionné sur l'ordre de travail 
- L'emplacement fonctionnel lié à l'actif sur la tâche de l'ordre de travail
- Le type d'actif lié à l'actif sur la tâche de l'ordre de travail  
- L'heure de début et de fin prévue définie sur l'ordre de travail  

Toutes les informations mentionnées ci-dessous ne figurent pas forcément sur un ordre de travail. Par conséquent, la recherche d'un projet d'ordre de travail parent s'effectue à l'aide de la combinaison de données disponibles et la sélection de l'ID de projet qui correspond aux données de l'ordre de travail.

Exemple : dans le graphique ci-dessous, le paramétrage du type d'actif « Moteur de camion » signifie que chaque tâche de l'ordre de travail créée avec ce type d'actif sera un sous-projet de l'ID de projet « 000186 ».

![Figure 1](media/01-integration-to-pma.png)

L'objectif de l'ID de projet sur la tâche de l'ordre de travail et le numéro d'activité associé (**Gestion des actifs** > **Commun** > **Ordres de travail** > **Tous les ordres de travail** > sélectionnez l'ordre de travail dans la liste > raccourci **Détails de la ligne** > champ **ID de projet** et champ **Numéro d'activité**), est de suivre les coûts liés à la tâche de l'ordre de travail, et à l'actif sélectionné pour la tâche de l'ordre de travail, dans le module **Gestion et comptabilité du projet**. 

L'illustration ci-dessous contient une vue d'ensemble graphique des projets d'ordre de travail et des activités de projet associées.

![Figure 2](media/02-integration-to-pma.png)

Lorsqu'une nouvelle tâche d'ordre de travail est créée sur un ordre de travail, un projet est automatiquement créé pour la tâche. Les dimensions financières pour l'actif associé à la tâche de l'ordre de travail sont automatiquement transférées au projet de l'ordre de travail. Des informations sont associées à l'activité de projet créée pour une tâche d'ordre de travail concernant le type de tâche de maintenance, la variante du type de tâche de maintenance et la transaction. Ces données sont utiles si, par exemple, vous créez une commande fournisseur à partir d'un ordre de travail (voir [Approvisionnement](../work-orders/procurement.md)) ou si vous utilisez le module **Gestion et comptabilité du projet** pour l'enregistrement des heures.  

Si l'actif a été installé sur un poste technique et qu'il est installé ensuite sur un autre poste technique, les dimensions financières liées au nouveau poste technique sont automatiquement mises à jour sur l'actif. Ensuite, lorsque vous créez une tâche d'ordre de travail pour l'actif, le projet associé se voit automatiquement attribuer les dimensions financières qui sont désormais associées à l'actif. Cela signifie que lorsque vous utilisez des postes techniques, les coûts peuvent toujours faire l'objet d'un suivi dans les postes techniques sur lesquels un actif a été installé à un moment donné. La mise à jour automatique des dimensions financières garantit la traçabilité complète des coûts pour le contrôle et la génération des états du projet.  


## <a name="work-order-projects-work-order-lifecycle-states-project-stages-and-project-types"></a>Projets d'ordre de travail, états du cycle de vie de l'ordre de travail, stades de projet et types de projet

Pour garantir l'utilisation appropriée des états de cycle de vie des ordres de travail et des stades de projet associés, tenez compte des dépendances liées au module **Gestion et comptabilité du projet** :

- Dans le module **Gestion et comptabilité du projet**, les stades de projet sont paramétrés sur les types de projet dans **Paramètres de gestion et comptabilité des projets**.  
- Dans **Paramètres de gestion et comptabilité des projets**, n'oubliez pas de sélectionner les cases à cocher de stade de projet appropriées pour tous les types de projets que vous allez utiliser. Dans l'illustration ci-dessous, cinq stades **Créé** - **Estimé** - **Prévu** - **En cours** - **Terminé** sont marqués pour les types de projet « Régie » et « Interne ». Ces cinq stades conviennent à la fois pour les tâches de maintenance de service et de maintenance interne.  
- Dans **Gestion des actifs**, des types de projets sont définis par les groupes de projets que vous paramétrez dans l'écran **Configuration du projet de l'ordre de travail** > le lien **Groupe de projets**.  
- Le paramétrage de groupes de projets dans **Configuration du projet de l'ordre de travail** sont utilisés lorsque vous créez des ordres de travail. Lorsqu'un ordre de travail est créé, un projet est automatiquement créé.  
- Les états du cycle de vie d'ordres de travail doivent avoir chacun un stade de projet associé.  
- Le stade de projet lié à un état du cycle de vie d'ordres de travail doit être défini comme stade actif pour le groupe de projets défini dans le projet de l'ordre de travail. Le projet de l'ordre de travail est créé automatiquement sur un ordre de travail.  
- Lorsque vous créez un ordre de travail, l'attribution automatique d'un projet est basée sur le paramétrage dans **Configuration du projet de l'ordre de travail** (**Gestion des actifs** > **Configuration** > **Ordres de travail** > **Paramétrage de projet**).  

Les associations entre les groupes de projets de l'ordre de travail, les types de projets associés, les stades de projet, les états du cycle de vie de l'ordre de travail sont affichés ci-dessous.  

![Figure 3](media/03-integration-to-pma.png)

![Figure 4](media/04-integration-to-pma.png)

![Figure 5](media/05-integration-to-pma.png)

Reportez-vous à la section [Configuration du projet de l'ordre de travail](../setup-for-work-orders/work-order-project-setup.md) pour savoir comment configurer des projets d'ordre de travail et à la section [États du cycle de vie d'ordres de travail](../setup-for-work-orders/work-order-lifecycle-states.md) pour savoir comment créer des états du cycle de vie de l'ordre de travail.

L'illustration suivante présente une vue d'ensemble graphique des différents projets créés dans le module **Gestion des actifs** pour autoriser l'intégration avec le module **Gestion et comptabilité du projet**, ainsi que les processus de travail auxquels ces projets sont liés.

![Figure 6](media/06-integration-to-pma.png)

