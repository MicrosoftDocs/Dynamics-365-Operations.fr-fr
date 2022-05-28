---
title: Création de relations de tâches de service
description: Vous pouvez associer des tâches de service à des accords de service ou des commandes de service afin de décrire la tâche de service à exécuter pour l’accord ou la commande.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 80980d83248612037999c665b6058c4d0bbf6a7c
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8678232"
---
# <a name="create-service-task-relations"></a>Création de relations de tâches de service    

[!include [banner](../includes/banner.md)]

Vous pouvez associer des tâches de service à des accords de service ou des commandes de service afin de décrire la tâche de service à exécuter pour l’accord ou la commande. Les techniciens de service et les clients ont accès à ces informations.

## <a name="create-a-relation-with-a-service-agreement"></a>Création d’une relation avec un accord de service

1.  Accédez à **Gestion des services** \> **Commun** \> **Accords de service** \> **Accords de service**.

2.  Sélectionnez un accord de service ou créez-en un.

3.  Dans le volet Actions, cliquez sur le bouton **Tâches de service**.

4.  Dans l’écran **Tâches de service**, cliquez sur **Nouveau** pour créer une ligne, puis sélectionnez une tâche de service dans la liste **Tâche de service** pour lier la tâche de service à l’accord de service.

5.  Sous l’onglet **Description**, entrez les descriptions de note internes ou externes dans les champs à texte libre.

6.  Fermez l’écran pour sauvegarder l’enregistrement.

Répétez cette procédure jusqu’à ce que vous ayez créé toutes les relations de tâches de service nécessaires pour l’accord de service. Vous pouvez désormais spécifier ces tâches de service pour toutes les lignes d’accord associées.

Une relation de tâches de service créée dans une commande de service est disponible à partir de toutes les commandes de service associées à l’accord de service.

## <a name="create-a-relation-with-a-service-order"></a>Création d’une relation avec une commande de service

1.  Accédez à **Gestion des services** \> **Commun** \> **Commandes de service** \> **Commandes de service**.

2.  Sélectionnez une commande de service ou créez-en une.

3.  Dans le volet Actions, cliquez sur le bouton **Tâches de service**.

4.  Dans le formulaire **Tâches de service**, cliquez sur **Nouveau** pour créer une ligne, puis sélectionnez une tâche de service dans la liste **Tâche de service** pour lier les tâches de service à l’ordre de service.

5.  Sous l’onglet **Description**, entrez les descriptions de note internes ou externes dans les champs à texte libre.

6.  Fermez l’écran pour sauvegarder l’enregistrement.

Répétez cette procédure jusqu’à ce que vous ayez créé toutes les relations de tâches de service nécessaires pour la commande de service. Vous pouvez désormais sélectionner la tâche de service pour laquelle vous avez créé une relation lors de la création des lignes de commande de service.

Les relations de tâches de service créées dans une commande de service sont disponibles dans la commande de service spécifique.

## <a name="see-also"></a>Voir également :

[Vue d’ensemble des tâches de service](service-tasks.md)


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]