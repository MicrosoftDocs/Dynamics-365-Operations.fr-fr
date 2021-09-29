---
title: Suivi des mises à jour pour rangement
description: Cette rubrique décrit comment configurer et exécuter le suivi des mises à jour pour la tâche périodique de rangement.
author: sherry-zheng
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: d8e2a42d8e12a5a9cf18e876b6f9e45ecb877881
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500021"
---
# <a name="update-tracking-for-put-away"></a>Suivi des mises à jour pour rangement

[!include [banner](../includes/banner.md)]

La tâche périodique *Suivi des mises à jour pour le rangement* est conçue pour être exécutée comme un lot récurrent nocturne. Elle identifie quels trajets ont reçu toutes les transactions d’inventaire et quels trajets n’ont pas de valeur pour la date de fin réelle. Elle définit ensuite la date de fin réelle à la date du jour selon les besoins.

Les *Activités de conteneur* sont créées pour chaque *étape* d’un parcours pour chaque *conteneur de livraison*. Ces valeurs sont définies par le modèle de parcours sélectionné lors de la création d’un trajet. Pour chaque enregistrement d’activités de conteneur, des valeurs peuvent être définies pour les champs **Date de début**, **Date de fin estimée** et **Date de fin réelle**. Ces champs peuvent être mis à jour lorsque la confirmation est reçue qu’une étape a commencé ou s’est terminée.

En règle générale, les informations relatives aux dates confirmées sont fournies par un tiers, tel qu’un transitaire, car ces actions sont gérées en dehors de Microsoft Dynamics 365 Supply Chain Management. Cependant, les informations d’un tiers ne sont pas nécessaires pour suivre l’arrivée des marchandises d’un trajet jusqu’à l’entrepôt (comme indiqué par l’entrée des marchandises). Par conséquent, le suivi peut être déterminé sur la base des informations contenues dans Dynamics 365 Supply Chain Management.

Pour configurer et exécuter la tâche périodique *suivi des mises à jour pour le rangement*, procédez comme suit :

1. Aller à **Prix au débarquement \> Tâches périodiques \> Suivi des mises à jour pour le rangement**.
1. Dans la boîte de dialogue **Suivi des mises à jour pour le rangement**, dans la section **Paramètres**, définissez les champs suivants :

    - **Étape** – Sélectionnez le nom/numéro d’identification unique pour la partie d’un parcours pour laquelle vous souhaitez mettre à jour le suivi. La valeur sélectionnée doit représenter l’arrivée du voyage à l’entrepôt.
    - **Activité** – Sélectionnez l’activité qui a été entreprise au cours de l’étape sélectionnée. Ces valeurs sont attribuées par ligne de modèle de parcours dans le centre de contrôle de suivi.

1. Pour limiter l’ensemble de lignes à inclure dans la mise à jour, sélectionnez le raccourci **Enregistrements à inclure** sur le bouton **Filtrer**. Une boîte de dialogue de requête standard apparaît, dans laquelle vous pouvez définir des critères de sélection, des critères de tri et des jointures. Les champs fonctionnent comme pour d’autres types de requêtes dans Supply Chain Management. Les champs ici sont en lecture seule et affichent les valeurs liées à votre requête.
1. Sur l’organisateur **Exécuter à l’arrière-plan**, configurez les options de traitement par lots et de planification selon vos besoins, comme vous le feriez pour d’autres types de tâches dans Supply Chain Management.
1. Sélectionnez **OK** pour appliquer vos paramètres et pour exécuter ou planifier la mise à jour.
