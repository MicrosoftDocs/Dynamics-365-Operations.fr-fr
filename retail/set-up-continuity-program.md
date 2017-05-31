---
title: "Paramétrez un programme de continuité pour un centre d&quot;appels"
description: "Cet article décrit le paramétrage d&quot;un programme périodique pour un centre d&quot;appels."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 16081
ms.assetid: 426a9be7-a931-4780-b372-e06f6083dd60
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: c0a9eec6bdf67deca885b30082b958869e64aae2
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="set-up-a-continuity-program-for-a-call-center"></a>Paramétrez un programme de continuité pour un centre d'appels

[!include[banner](includes/banner.md)]


Cet article décrit le paramétrage d'un programme périodique pour un centre d'appels.

Dans un programme périodique, qui est également appelé programme de commande récurrent, des clients reçoivent régulièrement des expéditions de produits selon un programme prédéfini. Chaque expédition peut contenir un produit différent, comme dans le cas d'un club « Livre du mois », ou le même produit peut être envoyé à plusieurs reprises. Pour paramétrer un programme périodique, effectuez les tâches suivantes.

1.  Définissez les paramètres périodiques dans la page **Paramètres du centre d'appels**.
2.  Créez un programme périodique qui spécifie des détails tels que l'échéancier de paiement, l'échéance des expéditions, et si la facturation est immédiate. Vous devez également ajouter une liste des produits inclus dans le programme périodique. Chaque produit reçoit un numéro d'identité d'événement qui est affecté de manière séquentielle, en commençant par 1. Les ID d'événement déterminent la commande où sont envoyés les produits.
    -   Lorsque les clients reçoivent un produit différent dans chaque expédition, les produits sont envoyés selon un ordre séquentiel, basé sur leurs ID événement, en commençant par l'événement actuel.
    -   Si les clients reçoivent le même produit dans chaque expédition, la liste contient un seul produit ayant un ID événement. Le même événement se produit à plusieurs reprises. Vous pouvez spécifier le nombre de répétitions de chaque événement.

3.  Créez un produit parent qui représente le programme de périodicité créé à la tâche 2. Si vous ajoutez ce produit à une commande client, la page **Périodicité** s'ouvre. Vous pouvez ensuite utiliser cette page pour créer la commande périodique réelle. Le produit parent ne spécifie pas les produits individuels que le client reçoit dans chaque expédition.

Après avoir paramétré un programme périodique comme décrit ci-dessus, vous pouvez créer une commande périodique pour un client. Vous devrez également peut-être effectuer les tâches de maintenance supplémentaires suivantes.

-   **Mise à jour de la période de l'événement périodique actuel** – Permet de paramétrer un traitement par lots qui indique au système quelle est la période de l'événement actuel.
-   **Créer des commandes enfant périodiques** – Permet de créer des commandes enfant à partir de la commande périodique parent.
-   **Traiter les paiements périodiques** – Permet de traiter la facturation et les notifications pour les paiements associés aux commandes client périodiques.
-   **Étendre les lignes périodiques** (le cas échéant) – Permet de prolonger le nombre de répétitions possibles d'un événement périodique. La récurrence des expéditions peut ensuite s'étendre au-delà de la limite qui a été définie dans le champ **Seuil de répétition de la périodicité** dans les paramètres du centre d'appels.
-   **Réaliser une mise à jour périodique** (le cas échéant) – Permet de synchroniser les modifications entre le programme périodique et des commandes client parentes périodiques.
-   **Clôturer les commandes et lignes parentes périodiques** – Permet de clôturer les commandes périodiques.





