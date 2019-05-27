---
title: Accords de service
description: Les accords de service permettent de définir les ressources utilisées dans une visite de service classique et leur mode de facturation au client.
author: ShylaThompson
manager: AnnBe
ms.date: 02/19/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c6425dcf1c89f625d997be0dd4a52aaecb6e6d65
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568279"
---
# <a name="service-agreements"></a>Accords de service

[!include [banner](../includes/banner.md)]

Les accords de service permettent de définir les ressources utilisées dans une visite de service classique et leur mode de facturation au client.

Chaque accord de service est associé à un projet, via lequel des transactions sont validées et facturées. Toutefois, vous pouvez également facturer des transactions de commande de service directement via le projet sans associer au préalable la commande de service à l'accord de service. Cette option est envisageable si la commande de service correspond à une visite de service unique et si la nécessité d'un traitement rapide des transactions de service prend rapidement le pas sur la nécessité de mettre à jour des informations d'accord de service détaillées sur le client pour une période donnée.

## <a name="service-agreement"></a>Accord de service

Dans chaque accord de service, vous devez spécifier un projet, un ID accord de service et un groupe d'accords de service. Vous pouvez utiliser ce dernier pour trier et organiser les accords de service.

L'en-tête de l'accord de service contient des paramètres qui s'appliquent à toutes les lignes d'accord associées :

-  Si l'accord de service est suspendu. Dans ce cas, vous ne pouvez pas générer de commandes de service à partir d'un accord de service.
-  La durée de l'accord de service.
-  La manière dont les lignes de commande de service doivent être combinées dans les commandes de service.
-  Si l'accord de service est un modèle.

Dans l'en-tête d'accord de service, vous pouvez également définir tous les objets de service et tâches de service qui peuvent être utilisés dans l'accord de service en entrant les tâches ou objets de service spécifiques à associer aux lignes de l'accord.

À partir de l'en-tête d'accord de service, vous pouvez également copier les lignes d'accord de service ou de modèle de service dans l'accord de service en cours.

Vous pouvez suspendre des accords de service et bloquer des lignes d'accord de service spécifiques.

Si vous activez la case à cocher **En suspens** pour une ligne d'accord de service, vous ne pouvez pas :

-    créer des commandes de service automatiquement ou manuellement à partir de l'accord de service.

Si vous activez la case à cocher **Arrêté** pour une ligne d'accord de service, vous ne pouvez pas :

-    créer des commandes de service automatiquement ou manuellement à partir de la ligne d'accord de service ;
-    copier la ligne d'accord de service dans un autre accord de service ou une autre commande de service.


> [!NOTE]
> Si un accord de service est suspendu, toutes les lignes associées sont bloquées quel que soit leur statut.

## <a name="service-agreement-lines"></a>Lignes d'accord de service

Chaque ligne d'accord de service décrit précisément le contenu de la tâche de service proposée. Elles contiennent les paramètres suivants :

-  le type de transaction et la description correspondante ;
-  l'employé qui exécute la tâche de service ;
-  les objets sur lesquels le service doit être exécuté pour l'accord de service ;
-  la fréquence d'exécution de la tâche et d'enregistrement des articles, dépenses et transactions de frais ;
-  la fenêtre Délai dans laquelle les lignes de commande de service peuvent être regroupées dans une commande de service ;
-  les tâches de service permettant de regrouper un ensemble de lignes d'accord en tâches et de résumer aux techniciens et aux clients la tâche de service qui doit être fournie ;
-  si la ligne est interrompue. Dans ce cas, vous ne pouvez pas créer de commande de service pour cette ligne individuelle ;
-  les paramètres du projet, tels que la catégorie et la propriété de ligne.

## <a name="related-topics"></a>Rubriques connexes

[Création d'accords de service](create-service-agreements.md)
