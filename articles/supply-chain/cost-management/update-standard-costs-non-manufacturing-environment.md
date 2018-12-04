---
title: "Mettre à jour des coûts standard dans un environnement hors fabrication"
description: "Cet article fournit des instructions pour mettre à jour les coûts standard dans un environnement hors fabrication."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 79723
ms.assetid: 7ba0c408-2450-4042-9542-6fdf83c12e6c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b428af5a694668ac161a7187d5a949f44e8ec2a2
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="update-standard-costs-in-a-non-manufacturing-environment"></a>Mettre à jour des coûts standard dans un environnement hors fabrication

[!include [banner](../includes/banner.md)]

Cet article fournit des instructions pour mettre à jour les coûts standard dans un environnement hors fabrication.

Les instructions suivantes supposent que vous utilisez une approche à deux versions pour mettre à jour les coûts standard. Dans cette approche, une version d'évaluation des coûts contient les coûts standard définis à l'origine pour la période bloquée et l'autre version d'évaluation des coûts contient les mises à jour incrémentielles. Chaque mise à jour est entrée comme un enregistrement de coûts inclus dans la deuxième version d'évaluation des coûts, avant d'être finalement activée. Une autre approche à une version consiste à utiliser les coûts standard définis à l'origine. L'approche à deux versions demande que vous définissiez une deuxième version d'évaluation des coûts. Voici les instructions pour définir cette version d'évaluation des coûts :

-   Affectez un type d'évaluation des **Coûts standard**.
-   Affectez un identificateur significatif qui communique le contenu de la version d'évaluation des coûts, tel que **2016-UPDATES**.
-   Vérifiez que le contenu comprend des enregistrements de coûts.
-   Autorisez la saisie d'enregistrements des coûts à entrer pour tous les sites. Si vous spécifiez un site, les enregistrements de coûts peuvent être entrés uniquement pour ce site.
-   Définissez le principe de secours sur **Aucun**. Le principe de secours s'applique uniquement aux calculs de coûts des articles fabriqués.

Pour corriger, ajuster ou mettre à jour les coûts standard de nouveaux articles, suivez ces étapes.

1.  Utilisez la page **Version d'évaluation des coûts** **paramétrage** pour activer les données de coût à entrer dans la deuxième version d'évaluation des coûts. Empêchez éventuellement l'activation de coûts en attente de manière à ce que l'activation soit autorisée lorsque les coûts en attente ont été entièrement et précisément définis. Vous pouvez également éventuellement entrer une date dans le champ **Date de début**. En général, utilisez la date qui correspond à la période à laquelle vous souhaitez activer les mises à jour incrémentielles. Vous pouvez également laisser le champ **Date de début** vide pour la version d'évaluation des coûts, puis entrez une date dans le champ **Date de début** pour chaque enregistrement de coûts.
2.  Utilisez la page **Prix de l'article** pour entrer des mises à jour comme les enregistrements de coûts d'article qui sont inclus dans la seconde version d'évaluation des coûts.
3.  Utilisez l'état **Prix de l'article** pour vérifier que les enregistrements de coûts d'article inclus dans la seconde version d'évaluation des coûts sont complets et exacts.
4.  Utilisez la page **Mise à jour de la version d'évaluation des coûts** pour modifier la balise de blocage afin d'autoriser l'activation des enregistrements de coûts en attente inclus dans la deuxième version d'évaluation des coûts.
5.  Utilisez la page **Activer les prix** (que vous pouvez ouvrir à partir de la page **Mise à jour de la version d'évaluation des coûts**) pour activer tous les enregistrements de coûts d'article en attente inclus dans la deuxième version d'évaluation des coûts. Vous pouvez également activer les enregistrements des coûts en attente pour des articles individuels en cliquant sur le bouton **Activer les coûts en attente** dans la page **Prix d'article**.
6.  Afin d'empêcher toute maintenance des données supplémentaire, utilisez la page **Paramétrage de la version d'évaluation des coûts** pour modifier les balises de blocage incluses dans la deuxième version d'évaluation des coûts. Les stratégies de blocage empêchent la saisie de nouveaux coûts en attente et l'activation de coûts en attente.





