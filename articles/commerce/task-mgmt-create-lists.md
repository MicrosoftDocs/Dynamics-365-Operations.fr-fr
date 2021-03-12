---
title: Créer des listes de tâches et ajouter des tâches
description: Cette rubrique décrit comment créer des listes de tâches et y ajouter des tâches dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: cca5e0efd6516d02c372e8a616b6bb0c39f3088c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006208"
---
# <a name="create-task-lists-and-add-tasks"></a>Créer des listes de tâches et ajouter des tâches

[!include [banner](includes/banner.md)]

Cette rubrique décrit comment créer des listes de tâches et y ajouter des tâches dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Une *tâche* définit un travail spécifique ou une action qu'une personne doit effectuer au plus tard à la date d'échéance spécifiée. Dans Dynamics 365 Commerce, une tâche peut inclure des instructions détaillées et des informations sur la personne à contacter. Elle peut également inclure des liens vers des opérations du back-office, des opérations PDV ou des pages de site, pour aider à améliorer la productivité et fournir le contexte dont le propriétaire de la tâche a besoin pour effectuer efficacement la tâche.

Une *liste de tâches* est un ensemble de tâches qui doivent être effectuées dans le cadre d'un processus métier. Par exemple, il peut s'agir d'une liste de tâches qu'un nouveau employé doit effectuer pendant l'intégration, d'une liste de tâches pour les caissiers qui travaillent le soir ou d'une liste de tâches qui doit être effectuée pour préparer le magasin pour la période des fêtes à venir. Dans Commerce, chaque liste de tâches ayant une date cible peut être affectée à plusieurs magasins ou employés, et elle peut être configurée pour se reproduire.

Les responsables et les employés peuvent créer des listes de tâches dans le back-office Commerce, puis les affecter à un ensemble de magasins.

## <a name="create-a-task-list"></a>Créer une liste de tâches

Pour créer une liste de tâches, procédez comme suit.

1. Accédez à **Commerce et vente au détail \> Gestion des tâches \> Administration de la gestion des tâches**.
1. Sélectionnez **Nouveau**, puis entrez des valeurs dans les champs **Nom**, **Description** et **Propriétaire**.
1. Sélectionnez **Enregistrer**.

## <a name="add-tasks-to-a-task-list"></a>Ajouter des tâches à une liste de tâches

Pour ajouter des tâches à une liste de tâches, procédez comme suit.
 
1. Dans le raccourci **Tâches** d'une liste de tâches existante, sélectionnez **Nouveau** pour ajouter une tâche.
1. Dans la boîte de dialogue **Créer une tâche**, dans le champ **Nom**, entrez un nom pour la tâche.
1. Dans le champ **Décalage des données d'échéance par rapport à la date cible**, entrez une valeur entière positive ou négative. Par exemple, entrez **-2** si la tâche doit être terminée deux jours avant la date d'échéance de la liste de tâches.
1. Dans le champ **Notes**, entrez des instructions détaillées.
1. Dans le champ **Personne à contacter**, entrez le nom d'un expert en la matière que le propriétaire de la tâche peut contacter en cas de besoin.
1. Dans le champ **Lien de la tâche**, entrez un lien en fonction de la nature de la tâche.

> [!TIP]
> Bien qu'il soit possible d'utiliser le champ **Affecté à** pour affecter des tâches à une personne tout en créant une liste de tâches, il est déconseillé d'affecter des tâches pendant la création d'une liste de tâches. À la place, affectez les tâches une fois la liste instanciée pour des magasins individuels.

## <a name="use-task-links-to-help-improve-worker-productivity"></a>Utiliser les liens de tâche pour aider à améliorer la productivité des employés

Commerce vous permet de lier des tâches à des opérations PDV spécifiques, comme l'exécution d'un rapport de vente, l'affichage d'une vidéo de formation en ligne pour l'orientation des nouveaux employés ou l'exécution d'une opération du back-office. Cette fonctionnalité aide les propriétaires de tâche à obtenir les informations nécessaires pour effectuer efficacement une tâche.

Pour ajouter des liens de tâche lorsque vous créez une tâche, procédez comme suit.

1. Dans le raccourci **Tâches** d'une liste de tâches existante, sélectionnez **Modifier**.
1. Dans la boîte de dialogue **Modifier la tâche**, dans le champ **Lien de la tâche**, sélectionnez une ou plusieurs des options suivantes :

    - Sélectionnez **Option de menu** pour configurer une opération du back-office, par exemple « Kits de produits ».
    - Sélectionnez **Opération PDV** pour configurer une opération PDV, par exemple « Rapports de vente ».
    - Sélectionnez **URL** pour configurer une URL absolue.

L'illustration suivante présente la sélection de liens de tâche dans la boite de dialogue **Modifier la tâche**.

![Sélection de liens de tâche dans la boîte de dialogue Modifier la tâche](media/HQ-POS-Tasks-Linking.png)

### <a name="configure-a-pos-operation-so-that-it-can-be-linked-to-a-task"></a>Configurer une opération PDV pour pouvoir la lier à une tâche

Pour configurer une opération PDV afin qu'elle puisse être liée à une tâche, procédez comme suit.

1. Accédez à **Commerce et vente au détail \> Paramétrage du canal \> Paramétrage du PDV \> PDV \> Opérations PDV**.
1. Sélectionnez **Modifier**, recherchez l'opération PDV, puis activez la case à cocher **Activer la gestion des tâches** correspondante.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d'ensemble de la gestion des tâches](task-mgmt-overview.md)

[Configurer la gestion des tâches](task-mgmt-configure.md)

[Affecter des listes de tâches à des magasins ou des employés](task-mgmt-assign-lists.md)

[Gestion des tâches dans le PDV](task-mgmt-POS.md)
