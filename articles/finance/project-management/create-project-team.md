---
title: Créer une équipe de projet
description: Cette rubrique fournit des informations sur la manière de créer et de gérer des équipes de projet.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 834a6c0a4fcc32a955c1feddf0a6cbbb1f16b869
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760544"
---
# <a name="create-a-project-team"></a>Créer une équipe de projet

[!include [banner](../includes/banner.md)]

Pour utiliser les rôles qui ont été précédemment paramétrés dans un projet, un chef de projet doit associer les rôles au projet. Plusieurs rôles peuvent être affectés pour un projet. Pour éviter toute confusion, ces rôles sont automatiquement intitulés lors de la réservation. Par exemple, si le chef de projet a besoin de trois ingénieurs logiciel, ces derniers sont automatiquement générés sous les libellés **ingénieur logiciel 1**, **ingénieur logiciel 2** et **ingénieur logiciel 3**. Si des caractéristiques de rôle ont été définis précédemment pour le rôle, elles sont appliquées comme filtre lors des recherches pour une ressource. Des caractéristiques supplémentaires peuvent être ajoutées au besoin pour affiner la recherche.

L’affichage des paramètres peut également être personnalisé pour donner une meilleure vue de la disponibilité des ressources. Il existe des options pour afficher les disponibilités horaire, hebdomadaire, mensuelle, trimestrielle et annuelle. Il existe également une option pour indiquer les capacités disponible et restante de ressources. Cette option est utile pour la gestion du temps lorsque vous estimez le temps disponible pour des activités ou la disponibilité des ressources.

Le chef de projet peut sélectionner un rôle dans la page puis, si une ressource disponible correspond au besoin, opérer une sélection pour réserver une ressource pour remplir le rôle. Notez que les ressources ne doivent pas être réservées à ce stade lors de la phase de planification. Lorsque vous créez une structure WBS, vous pouvez remplacer les rôles par des ressources avec personnel pour le projet. Si les rôles sont remplacés par des ressources avec personnel dans la structure WBS, le paramétrage des ressources met automatiquement à jour la liste et la planification de l’équipe du projet.

[![Liste de l’équipe de projet qui inclut des rôles et des ressources réelles](./media/projectresourcing03-1024x368.jpg)](./media/projectresourcing03.jpg) 

Le chef de projet a diverses options pour réserver une ressource pour un projet, telles que **Capacité restante**, **Capacité totale**, **Pourcentage de la capacité** et **Spécifier des heures**. Ces options de réservations peuvent être annulées à tout moment si les affectations de ressources sont modifiées. Deux types de réservation sont pris en charge :

- **Réservation fixe** – La réservation de ressource a été approuvée et confirmée pour travailler sur l’engagement pour la durée spécifiée.
- **Réservation provisoire** – Les réservations de ressource a été définie pour travailler à titre d’essai sur l’engagement pour la durée spécifiée.

Les procédures suivantes expliquent comment créer une équipe de projet.

## <a name="create-a-project-team"></a>Créer une équipe de projet

1. Dans la page de liste **Tous les projets**, sélectionnez un projet, puis sélectionnez **Modifier**.
2. Sous l’onglet **Équipe projet et planification**, dans le champ **Date de fin de planification**, entrez la date de début de la planification plus un mois. Par exemple, si la date de début de la planification est le 24 juin 2017 (24/06/2017), entrez **24/07/2017**.
3. Sélectionnez **Ajouter**.
4. Dans le volet **Ajouter des rôles au projet**, dans le champ **Rôle**, sélectionnez **Chef de projet senior**.
5. Sélectionnez **Compétences requises**.
6. Dans la page **Sélectionner les caractéristiques**, les caractéristiques que vous aviez précédemment définies pour le rôle de chef de projet senior sont sélectionnées par défaut. Sélectionnez **OK**.
7. Dans la page **Ajouter des rôles au projet**, dans le champ **Nombre de ressources**, entrez **1**.
8. Dans le champ **Ressource**, la recherche affiche toutes les ressources possédant les qualifications requises. Sélectionnez **Daniel Goldschmidt**, puis sélectionnez **Créer**.
9. Sur la page **Projet**, sélectionnez **Ajouter**.
10. Dans le volet **Ajouter des rôles au projet**, dans le champ **Rôle**, sélectionnez **Membre de l’équipe**. Dans le champ **Nombre de ressources**, entrez **5**.
11. Sélectionnez **Créer**.
12. Sur la page **Projets**, sélectionnez **Traiter la ressource**.

## <a name="monitor-project-teams"></a>Contrôler les équipes de projet
1. Sur la page **Tous les projets**, sélectionnez le lien **ID projet** pour le projet **Phase 2 de mise à niveau de XYZ**.
2. Dans l’organisateur **Équipe de projet et planification**, vérifiez que les ressources de projet répertoriées sont correctes.
