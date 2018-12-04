---
title: "Gérer des mises à jour des coûts standard"
description: "Les mises à jour des données de coût standard peuvent être gérées à l'aide de deux approches : l'approche à une version ou l'approche à deux versions."
author: AndersGirke
manager: AnnBe
ms.date: 10/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 69992
ms.assetid: 468de7af-c7b5-4345-bd5a-ba3aa5a900cc
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: b64d9e53736fd3b81ee997ed28ccfa62ed7e9ce6
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="manage-standard-cost-updates"></a>Gérer des mises à jour des coûts standard

[!include [banner](../includes/banner.md)]

Les mises à jour des données de coût standard peuvent être gérées à l'aide de deux approches : l'approche à une version ou l'approche à deux versions. 

La première approche utilise une seule version d'évaluation des coûts qui contient tous les enregistrements de coûts. Ces enregistrements incluent les coûts d'origine et les mises à jour des coûts.

La deuxième approche utilise une version qui contient les enregistrements des coûts originaux et une autre version qui contient les enregistrements de toutes les mises à jour des coûts. Elle présente l'avantage de délimiter et suivre clairement les mises à jour des coûts au sein d'une version d'évaluation des coûts distincte, sans affecter la version d'évaluation des coûts d'origine. Elle peut être utilisée pour identifier plusieurs mises à jour incrémentielles, chaque mise à jour incrémentielle ayant une version d'évaluation des coûts distincte qui contient les enregistrements de coûts incrémentiels. 

**Exemple** 

L'exemple suivant illustre l'utilisation des approches à une version et à deux versions pour mettre à jour les coûts standard dans un environnement de fabrication (par exemple, mises à jour reflétant de nouveaux articles ou des corrections d'erreur). Supposons qu'une version d'évaluation des coûts représente les coûts standard pour l'année en cours. L'identificateur de cette version est 2016-STD. La version 2016-STD contient les coûts actifs actuels pour tous les articles. Elle contient également les catégories de coûts associées aux gammes et les formules de calcul des frais généraux connues au début de l'année 2016. 2016-STD est la version d'évaluation des coûts d'origine.

-   **Approche à une version des mises à jour de données de coûts** − Dans l'approche à une version, la version d'évaluation des coûts d'origine 2016-STD contient tous les enregistrements de coûts. Les mises à jour des coûts sont enregistrées dans 2016-STD et sont définies sur le statut « En attente ». Les coûts en cours peuvent être entrés manuellement pour les nouveaux articles ou être calculés pour un article fabriqué pour refléter les corrections. Lorsque l'approche à une version est utilisée, les calculs de nomenclature ne nécessitent pas de source de données de secours car tous les coûts actifs sont contenus dans la version d'évaluation des coûts. Une fois les coûts en cours activés, la version d'évaluation des coûts d'origine 2016-STD contient de nouveau tous les coûts actifs actuels.
-   **Approche à deux versions des mises à jour de données de coûts** − L'approche à deux versions nécessite une version d'évaluation des coûts supplémentaire qui contient uniquement les mises à jour des coûts. L'identificateur de cette version est 2016-STD-CHANGES. Les mises à jour des coûts sont enregistrées dans 2016-STD-CHANGES et sont définies sur le statut « En attente ». Avec l'approche à deux versions, les calculs de nomenclature des coûts en attente pour les articles fabriqués nécessitent une source de données de secours. En effet, la version d'évaluation des coûts supplémentaire 2016-STD-CHANGES contient uniquement un sous-ensemble de données de coûts. Le secours peut être exprimé comme coûts actifs ou comme version d'évaluation des coûts 2016-STD car les deux identifient la source des données de coûts lorsqu'elle n'est pas incluse dans 2016-STD-CHANGES. Une fois les coûts en attente activés, la version d'évaluation des coûts 2016-STD-CHANGES contient les coûts actifs actuels qui reflètent les mises à jour, alors que la version d'évaluation des coûts d'origine 2016-STD reste inchangée. Lorsque l'approche à deux versions est utilisée, les stratégies de blocage pour la version d'évaluation des coûts d'origine doivent être définies de façon à empêcher les mises à jour. Des stratégies de blocage identiques doivent être définies pour la version d'évaluation des coûts supplémentaire, à l'exception de la date de début spécifiée et de l'utilisation sélective des stratégies de blocage pour permettre les mises à jour. La date de début spécifiée doit être mise à jour avec chaque lot de modifications pour refléter la date d'activation prévue.

L'exemple utilise une version d'évaluation des coûts supplémentaire pour la gestion des mises à jour au cours de l'année 2016. Plusieurs versions d'évaluation des coûts supplémentaires peuvent être utilisées, telles qu'une version distincte pour chaque lot de mises à jour. Dans ce cas, le secours doit être exprimé comme les coûts actifs car ils pourraient être dispersés entre plusieurs versions d'évaluation des coûts.






