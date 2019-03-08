---
title: Création de relations de tâches de service
description: Vous pouvez associer des tâches de service à des accords de service ou des commandes de service afin de décrire la tâche de service à exécuter pour l'accord ou la commande.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2aa0e5200ff2a6822e631c72124335e2dc556c14
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "317198"
---
# <a name="create-service-task-relations"></a>Création de relations de tâches de service    

[!include [banner](../includes/banner.md)]

Vous pouvez associer des tâches de service à des accords de service ou des commandes de service afin de décrire la tâche de service à exécuter pour l'accord ou la commande. Les techniciens de service et les clients ont accès à ces informations.

## <a name="create-a-relation-with-a-service-agreement"></a>Création d'une relation avec un accord de service

1.  Cliquez sur **Gestion des services** \> **Commun** \> **Accords de service** \> **Accords de service**.

2.  Sélectionnez un accord de service ou créez-en un.

3.  Dans le volet Actions, cliquez sur le bouton **Tâches de service**.

4.  Dans l'écran **Tâches de service**, appuyez sur Ctrl+N pour créer une ligne, puis sélectionnez une tâche de service dans la liste **Tâche de service** pour lier la tâche de service à l'accord de service.

5.  Sous l'onglet **Description**, entrez les descriptions de note internes ou externes dans les champs à texte libre.

6.  Fermez l'écran pour sauvegarder l'enregistrement.

Répétez cette procédure jusqu'à ce que vous ayez créé toutes les relations de tâches de service nécessaires pour l'accord de service. Vous pouvez désormais spécifier ces tâches de service pour toutes les lignes d'accord associées.

Une relation de tâches de service créée dans une commande de service est disponible à partir de toutes les commandes de service associées à l'accord de service.

## <a name="create-a-relation-with-a-service-order"></a>Création d'une relation avec une commande de service

1.  Cliquez sur **Gestion des services** \> **Commun** \> **Commandes de service** \> **Commandes de service**.

2.  Sélectionnez une commande de service ou créez-en une.

3.  Dans le volet Actions, cliquez sur le bouton **Tâches de service**.

4.  Dans l'écran **Tâches de service**, appuyez sur Ctrl+N pour créer une ligne, puis sélectionnez une tâche de service dans la liste **Tâche de service** pour lier les tâches de service à la commande de service.

5.  Sous l'onglet **Description**, entrez les descriptions de note internes ou externes dans les champs à texte libre.

6.  Fermez l'écran pour sauvegarder l'enregistrement.

Répétez cette procédure jusqu'à ce que vous ayez créé toutes les relations de tâches de service nécessaires pour la commande de service. Vous pouvez désormais sélectionner la tâche de service pour laquelle vous avez créé une relation lors de la création des lignes de commande de service.

Les relations de tâches de service créées dans une commande de service sont disponibles dans la commande de service spécifique.

## <a name="see-also"></a>Voir également :

[Tâches de service](service-tasks.md)


  


