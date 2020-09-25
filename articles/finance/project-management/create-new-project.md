---
title: Créer un nouveau projet
description: Cette rubrique fournit des informations sur la manière de créer un projet.
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
ms.openlocfilehash: c8c52b8c1c86ea2f6e03cf439ba5930f1006ab4f
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760543"
---
# <a name="create-a-new-project"></a>Créer un nouveau projet

[!include [banner](../includes/banner.md)]

Procédez comme suit pour créer un projet.

1. Sur la page **Gestion de projets**, sélectionnez **Nouveau projet**, puis entrez les valeurs suivantes :

    - **Type de projet :** Régie
    - **Nom du projet :** Phase 2 de mise à niveau de XYZ
    - **Groupe de projets :** TM\_WIP
    - **ID contrat de projet :** 00000002

2. Sélectionnez **Créer un projet**.

## <a name="assign-a-resource-to-a-project"></a>Affectez une ressource à un projet

1. Sur la page **Collaborateurs**, dans la liste **Collaborateurs**, sélectionnez l’enregistrement pour le collaborateur dont vous avez précédemment paramétré les compétences et ouvrez l’enregistrement de collaborateur.
2. Dans le volet Actions, sous l’onglet **Projet**, dans le groupe **Paramétrage**, sélectionnez **Affecter des projets**.
3. Sur la page **Affectations du projet de contrôle des ressources**, sous l’onglet **Projet**, dans le champ **Ajoutez le projet aux projets sélectionnés**, filtrez sur le projet **Phase 2 de mise à niveau de XYZ**.
4. Dans le volet **Projets restants**, sélectionnez un projet, puis sélectionnez le bouton fléché pour l’ajouter au volet **Projets sélectionnés**.

Vous pouvez également affecter des catégories à une ressource en fonction de vos besoins. Le type de catégorie est **Coût** ou **Produit**. Le type de catégorie est déterminé par votre organisation. Si aucune catégorie n’est affectée à une ressource, Finance recherche la catégorie par défaut dans les prix horaires en matière de coût et de produit.

## <a name="set-up-project-resource-and-role-characteristics"></a>Configurer des ressources de projet et les caractéristiques du rôle

Un chef de projet peut utiliser la fonctionnalité de ressources de projet pour créer les rôles requis pour le projet. Les rôles peuvent être utilisés lorsque les ressources confirmées sont encore inconnues lors de la réservation des ressources. Les rôles peuvent être réservés temporairement en tant que ressources planifiées pour que vous puissiez poursuivre les stades de planification du projet.

[![Exemple de rôle](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg) 

**Scénario :** Contoso a été engagé pour réaliser un projet en régie avec une charte de projet approuvée. Le chef de projet junior termine toujours la portée du projet. Le gestionnaire de ressources identifie actuellement les ressources spécifiques qui seront réservées pour travailler sur le nouveau projet. En raison de la nature critique du projet, le commanditaire du projet a demandé le rôle de chef de projet senior. Le gestionnaire de ressources doit acquérir la nouvelle ressource et définit le rôle dans le système, au cas où le chef de projet junior aurait besoin des informations de ressource lors de la planification des projets.

Les étapes suivantes indiquent comment le gestionnaire de ressources peut paramétrer le rôle de chef de projet senior et lui associer caractéristiques de la ressource. Ensuite, le rôle peut être utilisé pour rechercher des ressources disponibles correspondant aux compétences de ressource requises.

1. Sur la page **Paramétrer les rôles**, sélectionnez **Nouveau**, puis entrez les valeurs suivantes :

    - **ID rôle :** Chef de projet senior
    - **Description :** Chef de projet senior

2. Sélectionnez **Créer**.
3. Sélectionnez le rôle **Chef de projet senior**, puis sélectionnez **Configurer les caractéristiques**.
4. Dans le champ **Type de caractéristiques**, sélectionnez **Qualification**.
5. Dans le champ **Caractéristiques disponibles**, entrez la compétence que vous recherchez.
6. Dans le champ **Type de caractéristiques**, sélectionnez **Certificat**.
7. Dans le champ **Caractéristiques disponibles**, entrez le type de certificat que vous recherchez.

## <a name="assign-a-project-resource-to-a-project"></a>Affectez une ressource de projet à un projet

1. Sur la page **Tous les projets**, sélectionnez le projet **Phase 2 de mise à niveau de XYZ**.
2. Sous l’onglet **Équipe de projet et planification**, sélectionnez **Ajouter**.
3. Dans le champ **Rôle**, sélectionnez **Membre de l’équipe**.
4. Sélectionnez **Réserver à partir du calendrier**.
5. Sur la page **Disponibilité des ressources**, sélectionnez **Afficher les paramètres**.
6. Dans la page **Régler les paramètres de la vue**, entrez des valeurs suivantes :

    - **Format pour la vue de la plage de dates :** Jour
    - **Afficher les descriptions disponibles :** Oui
    - **Afficher la capacité restante :** Oui

7. Dans la liste des ressources, sélectionnez une ressource.
8. Sélectionnez **Effectuer une réservation fixe** et **Capacité totale**.

## <a name="assign-a-resource-to-a-default-role"></a>Affectez une ressource à un rôle par défaut

Pour aider les responsables de ressources ou de projet, ils peuvent zoomer en avant sur les ressources qui peuvent être réservées à un projet. Vous pouvez associer un rôle par défaut à une ressource existante ou une ressource récemment acquise. Par exemple, lorsque Daniel a été embauché, il avait l’expérience et les qualifications requises pour remplir le rôle d’analyste d’entreprise. Le gestionnaire de ressources a affecté ce rôle comme rôle par défaut de Daniel. Par conséquent, le responsable des ressources a ajouté Daniel à un groupe d’analystes d’entreprise qui sont disponibles pour les projets.

Lors de la réservation des ressources, les chefs de projet peuvent filtrer les ressources de rôles disponibles pour travailler sur des projets. Ils peuvent utiliser ces informations comme un critère lorsqu’ils exécutent une analyse de décision multi-critères au cours du traitement des ressources. Ils peuvent également ajouter d’autres caractéristiques de ressource au filtre pour rechercher des ressources possédant des qualifications spécifiques, une formation et de l’expérience pour un projet donné.

**Scénario :** Un projet approuvé a démarré et le rôle de chef de projet senior a été réservé en tant que ressource planifiée lors du stade de planification du projet. Le gestionnaire de ressources a désormais acquis une ressource pour traiter le rôle de gestionnaire de projet senior.

1. Sur la page **Liste des ressources**, sélectionnez **Daniel Goldschmidt**.
2. Sur la page **Rôle de la ressource**, sélectionnez **Nouveau**, puis entrez les valeurs suivantes :

    - **Date d’effet :** Saisissez la date actuelle.
    - **Expiration :** Définissez **Jamais**.
    - **ID rôle :** Définissez **Chef de projet senior**.

3. Sélectionnez **Sauvegarder**, puis fermez la page.
4. Sous l’onglet **Compétences**, ajoutez la qualification **ProjectMgmt** et le certificat **PMP**.
