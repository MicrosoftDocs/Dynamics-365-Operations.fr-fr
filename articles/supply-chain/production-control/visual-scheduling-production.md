---
title: Diagramme de Gantt pour la planification des tâches
description: Les gestionnaires de production peuvent contrôler et optimiser les plans de production à l'aide des diagrammes de Gantt.
author: johanhoffmann
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgShopSupervisorWorkspace, ProdTable, ProdTableListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 301db69fce18c2ed32e201e7418e628ac57db543
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "335230"
---
# <a name="gantt-chart-for-job-scheduling"></a>Diagramme de Gantt pour la planification des tâches

[!include [banner](../includes/banner.md)]

Le diagramme de Gantt est conçu pour permettre aux gestionnaires de production de contrôler et d'optimiser le plan de production. Le diagramme de Gantt assure la transparence du flux d'opérations et facilite l'ajustement de la planification de la production tout en tenant compte des pénuries de matières ou de ressources. Les gestionnaires de production peuvent ainsi optimiser les ressources disponibles, réduire les travaux en cours et optimiser les délais d'exécution des ordres de fabrication.

Un diagramme de Gantt est une représentation visuelle des activités planifiées dans un intervalle de temps défini. Les activités sont planifiées sur les ressources dont la capacité est définie par un calendrier de capacité. Les types d'activités suivants peuvent être affichés dans le diagramme de Gantt.

-   Tâches issues des ordres de fabrication qui sont planifiés par tâche.
-   Tâches issues des ordres de fabrication planifiés.
-   Activités de projet planifiées par tâche de type Prévisions en heures.

Le diagramme de Gantt peut être ouvert dans deux vues différentes, la **Vue Commande** et la **Vue Ressource**[](https://authoring.help.dynamics.com/en/?post_type=incsub_wiki&p=1665154&preview=true). Dans la **Vue Commande**, les activités sont regroupés sous des ordres de fabrication. Cela peut être utile, par exemple, si vous souhaitez avoir une vue d'ensemble de toutes les tâches appartenant aux mêmes ordres de fabrication. Dans la **Vue Ressource**, toutes les tâches sont regroupées sous des ressources individuelles. Cette vue peut être utile lors l'optimisation du plan au niveau d'une ressource, par exemple, un ordinateur ou un groupe d'ordinateurs. Les diagrammes de Gantt présentés dans les illustrations ci-dessous affichent la **Vue Commande** et la **Vue Ressource** avec les éléments clés suivants :

1.  Activité du diagramme de Gantt
2.  Icône de pénurie de matières
3.  Icône de disponibilité des matières
4.  Icône de date de livraison de la commande
5.  Barre de capacité

## <a name="order-view"></a>Vue Commande

[![Vue Commande](./media/orderview.png)](./media/orderview.png)

## <a name="resource-view"></a>Vue Ressource
[![Vue Ressource](./media/resview.png)](./media/resview.png)

## <a name="activities"></a>Activités
Les activités s'affichent sous forme de barres et sont organisées dans une grille de durée avec une heure de début et de fin planifiée, de sorte que la longueur des barres est proportionnelle au temps nécessaire pour effectuer l'activité. Les activités sont affichées en fonction d'une échelle de temps. Vous pouvez ajuster l'échelle de temps dans le menu en sélectionnant une date de début et de fin et une unité de temps, par exemple, heures ou jours. En ajustant l'échelle de temps, vous pouvez définir le focus sur l'intervalle de temps dans lequel vous souhaitez gérer les activités. 

Pour obtenir une meilleure vue d'ensemble, différentes options sont disponibles pour contrôler la couleur des activités. Vous pouvez configurer une couleur individuelle pour les activités, utiliser la couleur de thème qui est le paramètre de couleur général utilisé pour l'application ou paramétrer la couleur de manière à ce qu'elle soit contrôlée par le code couleur des ordres de fabrication. 

L'intervalle de temps des activités a une ombre en arrière-plan. Les périodes avec une ombre blanche indiquent un intervalle de temps avec une capacité définie sur la ressource pour l'activité, alors que les périodes avec une ombre grise indiquent des intervalles de temps sans capacité définie. 

À gauche du graphique, des informations supplémentaires sur l'activité sont disponibles, par exemple, la ressource sur laquelle l'activité est planifiée et le numéro de l'ordre de fabrication. La connexion entre les tâches appartenant au même ordre est indiquée par une flèche. 

Vous pouvez obtenir plus d'informations sur une activité dans la boîte de dialogue correspondante. Pour ouvrir la boîte de dialogue, double-cliquez sur l'activité ou sélectionnez le menu **Informations**. Dans la boîte de dialogue de l'activité, vous pouvez afficher la date de début et de fin planifiée, ainsi que les informations sur les matières que l'activité prévoit de consommer. 

Les activités peuvent être regroupées en niveaux de regroupement. Les niveaux de regroupement sont hiérarchiques et permettent d'effectuer un regroupement logique des activités. Par exemple, si vous avez une disposition dans laquelle les activités de fabrication sont regroupées par site, unité de production, groupe de ressources et ressource, vous pouvez utiliser les niveaux de regroupement pour regrouper les activités en fonction de cette disposition. Les niveaux de regroupement peuvent être développés et réduits pour un niveau de regroupement individuel ou pour tous les niveaux du graphique à l'aide des boutons **Développer tout** et **Réduire tout** du menu. Vous pouvez également configurer les niveaux de regroupement pour qu'ils soient développés ou réduits lorsque le graphique est ouvert.

### <a name="material-availability"></a>Disponibilité des matières

Le diagramme de Gantt peut être paramétré pour fournir au planificateur des informations détaillées sur le statut des matières pour les activités individuelles. Par exemple, cela peut être utile si les matières sont retardées et affectent le plan de production. Dans ce cas, les problèmes de matières sont mis en surbrillance dans le diagramme de Gantt pour aider le planificateur à comprendre les conséquences et à effectuer les ajustements nécessaires. 

Une tâche s'affiche avec une icône de pénurie de matières si la date de début planifiée de la tâche est postérieure à la date de disponibilité des matières pour les matières consommées par la tâche. La date de disponibilité des matières est calculée en fonction des informations sur l'origine des besoins dans le plan général dynamique. L'icône de pénurie de matières s'affiche par exemple sur une tâche qui consomme une matière associée à une commande fournisseur dont la réception est postérieure à la date de début planifiée de la tâche.

### <a name="indicator-of-material-availability-date"></a>Indicateur de date de disponibilité des matières

Lorsque vous paramétrez le graphique pour afficher les tâches présentant des pénuries de matières, une icône indiquant la date de disponibilité des matières pour la tâche peut également s'afficher. L'icône n'est visible que si la date de disponibilité des matières est comprise dans l'intervalle de temps défini dans le graphique. Si la date de disponibilité des matières est comprise dans l'intervalle de temps défini, des informations plus détaillées sur la disponibilité des matières peuvent être récupérées à partir de la liste des matières dans la boîte de dialogue de la tâche. La liste contient également une icône indiquant les matières en retard pour la tâche. Vous pouvez replanifier une tâche en utilisant la date de disponibilité des matières comme date de début.

### <a name="indicator-of-order-delivery-date"></a>Indicateur de date de livraison de la commande

Cette icône indique la date de livraison d'un ordre de fabrication. L'icône n'est visible que dans la vue Commande.

### <a name="capacity-bar"></a>Barre de capacité

Vous pouvez configurer le diagramme pour afficher une barre de capacité des ressources. Cette barre donne une vue d'ensemble de la capacité de ressources pour une activité dans l'intervalle de temps défini dans le graphique. La barre de capacité ne s'affiche pas pour les périodes dans lesquelles la ressource n'est pas réservée. Dans les périodes où la ressource est réservée pour la capacité, la barre de capacité apparaît comme une barre pleine. Dans les périodes où la ressource est surréservée, la barre est plus épaisse et de couleur rouge. Par exemple, si deux tâches se chevauchent, la barre de capacité indique une surréservation dans l'intervalle de temps où un chevauchement se produit. La barre de capacité est mise à jour de façon dynamique lorsque vous planifiez une tâche. Vous pouvez activer la barre de capacité dans le menu **Afficher la barre de capacité**. Elle n'est visible que dans la **Vue Ressource**. Si vous souhaitez obtenir une vue plus détaillée de la charge de capacité d'une ressource, utilisez le graphique **Charge de la capacité**, qui peut être ouvert à partir du menu ou du menu contextuel pour une activité sélectionnée.

## <a name="job-scheduling-in-the-gantt-chart"></a>Planification de tâches dans le diagramme de Gantt
Le diagramme de Gantt offre différentes options d'ajustement du plan de production. Dans le diagramme de Gantt, vous pouvez replanifier des activités comme une interaction de glisser-déplacer ou à partir d'un menu de planification. Dans le processus de planification, vous pouvez prendre en compte les capacités des ressources et les contraintes de matières.

### <a name="schedule-a-job-as-a-drag-and-drop-interaction"></a>Planifier une tâche comme une interaction de glisser-déplacer

Vous pouvez replanifier une tâche dans l'intervalle de temps défini comme une interaction de glisser-déplacer. Vous pouvez uniquement replanifier la tâche sur la même ressource, et il n'est possible de planifier qu'une tâche à la fois.

### <a name="schedule-a-job-from-the-menu"></a>Planifier une tâche à partir du menu

Dans le menu **Planifier les tâches**, vous pouvez planifier une ou plusieurs tâches sélectionnées dans le diagramme selon une direction de planification et une date et heure de planification. Trois directions de planification sont disponibles.

-   En avant à partir de la date de planification
-   En arrière à partir de la date de planification
-   En avant à partir de la date de disponibilité du matériel

Il est impossible de planifier une tâche en dehors de l'intervalle de temps défini dans le diagramme de Gantt. Si vous le faites, la tâche restera non planifiée et vous recevrez le message d'erreur, « Impossible de planifier la tâche dans la période de chargement ».

### <a name="schedule-previous-jobs"></a>Planifier les tâches précédentes

Dans un réseau d'activités, par exemple des tâches appartenant au même ordre de fabrication, vous pouvez utiliser la fonction **Planifier les tâches précédentes** pour planifier les tâches précédentes relatives à une tâche sélectionnée dans le réseau. Dans l'exemple suivant, l'activité mise en surbrillance est la tâche sélectionnée. Le diagramme s'affiche avant la planification d'un travail précédent et après la planification du travail précédent. 

[![Planifier une tâche précédente](./media/schprevjob3.png)](./media/schprevjob3.png)

### <a name="schedule-next-jobs"></a>Planifier les tâches suivantes

Vous pouvez utiliser la fonction **Planifier les tâches suivantes** pour planifier les tâches suivantes relatives à une tâche sélectionnée dans un réseau d'activités. Dans l'exemple suivant, l'activité mise en surbrillance est la tâche sélectionnée. Le diagramme s'affiche avant la planification du travail suivant et après la planification du travail suivant. 

[![Planifier la tâche suivante](./media/schnxtjob.png)](./media/schnxtjob.png)

### <a name="schedule-around-job"></a>Planifier autour de la tâche

Vous pouvez utiliser la fonction **Planifier autour de la tâche** pour planifier les tâches suivante et précédente relatives à une tâche sélectionnée dans un réseau d'activités. Dans l'exemple suivant, l'activité mise en surbrillance est la tâche sélectionnée. Le diagramme s'affiche avant et après la planification d'un travail. 

[![Planifier autour de la tâche](./media/scharoundjob1.png)](./media/scharoundjob1.png)

### <a name="arrange-jobs"></a>Réorganiser les tâches

Vous pouvez utiliser la fonction **Réorganiser** pour réorganiser les activités sélectionnées sur la même ressource. Ces activités peuvent appartenir au même réseau d'activités, mais peuvent également appartenir à différents réseaux. Lorsque vous utilisez la fonction de réorganisation, les écarts de temps entre les activités sélectionnées sont éliminés. Vous pouvez utiliser cette fonction pour optimiser l'utilisation de capacité des ressources. Le diagramme s'affiche avant et après la planification d'un travail. 

[![Réorganiser la tâche](./media/arrangejobs1.png)](./media/arrangejobs1.png)

### <a name="reassign-activities-from-one-resource-to-another"></a>Réaffecter des activités d'une ressource à une autre

Vous pouvez réaffecter une tâche d'une ressource à une autre. Cela peut être utile dans les cas où une machine est hors service ou surréservée et, vous devez trouver une autre ressource disponible pour effectuer la tâche.

### <a name="reassigning-an-activity-as-a-drag-and-drop-interaction"></a>Réaffectation d'une activité comme interaction de glisser-déplacer

Dans la vue **Ressource**, vous pouvez réaffecter une activité à une autre ressource dans le diagramme de Gantt en tant qu'interaction de glisser-déplacer. Pour ce faire, sélectionnez la ligne dans laquelle l'activité est planifiée. Une fois la ligne sélectionnée, vous pouvez la faire glisser vers la ressource du diagramme regroupée sous un autre niveau de regroupement des ressources.

### <a name="reassigning-an-activity-from-the-schedule-jobs-menu"></a>Réaffectation d'une activité à partir du menu Planifier les tâches

Vous pouvez réaffecter une tâche à partir de la boîte de dialogue **Planifier la tâche** ouverte à partir du menu **Planifier la tâche**. Dans ce menu, vous pouvez uniquement réaffecter une tâche à une ressource qui est déjà chargée dans le diagramme de Gantt. Si vous sélectionnez une seule tâche, le menu déroulant associé à la ressource est trié en fonction des ressources applicables. Si vous sélectionnez plusieurs tâches, aucune information sur les ressources applicables de la liste de ressources ne s'affiche.

## <a name="load-additional-resources-to-the-gantt-chart"></a>Charger des ressources supplémentaires dans le diagramme de Gantt
Dans la **Vue Ressource**, une option permet de charger des ressources supplémentaires dans le diagramme de Gantt. Cela peut être utile si vous souhaitez rechercher une ressource de remplacement pour une tâche planifiée sur une machine surréservée ou en panne. Dans la page **Charger des ressources supplémentaires**, vous obtenez une liste de ressources disponibles à compter de la date d'ouverture de la liste. Les ressources applicables associées à une tâche sélectionnée dans le diagramme de Gantt sont répertoriées en premier. Si plusieurs tâches sont sélectionnées, avant l'ouverture de la liste, aucune indication sur les ressources applicables ne s'affiche. Dans la page **Charger des ressources supplémentaires**, vous pouvez sélectionner une ou plusieurs ressources, qui sont chargées dans le diagramme de Gantt lorsque vous confirmez votre sélection. Si aucune tâche n'est planifiée sur la ressource sélectionnée dans l'intervalle de temps défini dans le diagramme de Gantt, la ressource est placée sous un niveau de regroupement de ressources en bas de la liste des activités dans le diagramme de Gantt.

### <a name="access-the-gantt-chart"></a>Accéder au diagramme de Gantt

Le diagramme de Gantt peut être ouvert à partir des pages suivantes.


|                                                 <strong>Page</strong>                                                  |                                                                                                                                                                                                                                                            <strong>Description</strong>                                                                                                                                                                                                                                                            |
|------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                   <strong>Liste et détails des ordres de fabrication</strong>                                    | Dans la page <strong>Liste et détails des ordres de fabrication</strong>, vous pouvez ouvrir le diagramme de Gantt à partir d'une ou de plusieurs commandes sélectionnées. L'ouverture du diagramme à partir de l'option de menu <strong>Diagramme de Gantt</strong> charge toutes les tâches associées aux ordres de fabrication sélectionnés, mais aussi les tâches des autres ordres de fabrication planifiés sur les mêmes ressources. L'ouverture du diagramme à partir de l'option de menu <strong>Diagramme de Gantt – Vue rapide</strong> charge uniquement les tâches associées aux ordres de fabrication sélectionnés. Dans cette vue, il est impossible de planifier des tâches. |
|                                               <strong>Ressource</strong>                                                |                                                                                                                                                        Dans la page <strong>Ressource</strong>, vous pouvez ouvrir le diagramme de Gantt à partir de l'option de menu <strong>Diagramme de Gantt</strong>. Lorsque cette option est sélectionnée, toutes les tâches planifiées sur la ressource dans un intervalle de temps sélectionné sont chargées dans le diagramme.                                                                                                                                                         |
|                                            <strong>Groupe de ressources</strong>                                             |                                                                                                                                                 Dans la page <strong>Groupe de ressources</strong>, vous pouvez ouvrir le diagramme de Gantt à partir de l'option de menu <strong>Diagramme de Gantt</strong>. Lorsque cette option est sélectionnée, toutes les tâches planifiées sur les ressources du groupe de ressources s'affichent dans l'intervalle de temps sélectionné.                                                                                                                                                 |
|                                             <strong>Diagrammes de Gantt</strong>                                              |                                                                                 Dans la page <strong>Diagrammes de Gantt</strong>, vous pouvez configurer les diagrammes de Gantt par ressource et groupe de ressources. Par exemple, si vous souhaitez contrôler les activités de production pour des ensembles de ressources spécifiques ou des groupes de ressources, vous pouvez créer des configurations individuelles dans la page <strong>Diagrammes de Gantt</strong>. Vous pouvez ensuite ouvrir le diagramme de Gantt à partir de chaque configuration.                                                                                 |
|                                       <strong>Prévisions en heures</strong> (projet)                                        |                                                                                                                              Les activités de projet de type <strong>Prévision en heures</strong> peuvent être planifiées par tâche sur les ressources. Dans la page <strong>Prévision en heures</strong>, dans le menu <strong>Planification</strong>, vous pouvez ouvrir le diagramme de Gantt d'un ordre de fabrication pour afficher les activités de projet planifiées par tâche de type Prévision en heures.                                                                                                                               |
|           <strong>Tâches à effectuer</strong> (liste dans l'espace de travail <strong>Gestion de l'atelier de production</strong>)            |                                                                                               L'espace de travail <strong>Liste des tâches à effectuer dans la gestion de l'atelier de production</strong> affiche les tâches de production et les lots de commandes en cours sur les ressources sélectionnées pour l'espace de travail. Dans l'option de menu <strong>Diagramme de Gantt</strong>, vous pouvez ouvrir le diagramme de Gantt, où toutes les tâches sélectionnées dans la liste sont chargées dans le diagramme.                                                                                               |
| <strong>Ordres de fabrication à lancer</strong> (ouvert à partir de l'espace de travail <strong>Gestion de l'atelier de production</strong>) |                                                                                                                                         La page Ordres de fabrication à lancer est ouverte partir de l'espace de travail <strong>Gestion de l'atelier de production</strong>. Cette page affiche les ordres de fabrication planifiés et les lots de commandes en attente de lancement. Dans cette page, vous pouvez ouvrir le diagramme de Gantt pour les ordres de fabrication sélectionnés.                                                                                                                                          |

## <a name="additional-resources"></a>Ressources supplémentaires  
[Planification visuelle avec le diagramme de Gantt pour les ordres de fabrication et les lots de commandes (vidéo)](https://youtu.be/BtbuShkGj4I)

[Planification visuelle pour la production (script de démonstration)](https://mbs.microsoft.com/customersource/northamerica/365Enterprise/learning/documentation/how-to-articles/365finoptvisschep)

