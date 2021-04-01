---
title: Mettre à jour des coûts standard pour un nouvel article fabriqué
description: Cet article fournit des instructions pour mettre à jour les coûts standard pour un nouvel article fabriqué.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79693
ms.assetid: ba64b70f-3f4c-4373-9a7d-8fd07c45a8cf
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 03b5fb1311f5a483914c83563d989e1732d431ad
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5219459"
---
# <a name="update-standard-costs-for-a-new-manufactured-item"></a>Mettre à jour des coûts standard pour un nouvel article fabriqué

[!include [banner](../includes/banner.md)]

Cet article fournit des instructions pour mettre à jour les coûts standard pour un nouvel article fabriqué. 

Les instructions suivantes supposent que vous utilisez une approche à deux versions pour mettre à jour les coûts standard. Dans cette approche, une première version d’évaluation des coûts contient les premiers coûts standard définis à l’origine pour la période bloquée et une deuxième version d’évaluation des coûts contient les mises à jour incrémentielles qui appartiennent aux nouveaux articles fabriqués. Les mises à jour incrémentielles sont entrées comme des enregistrements de coûts dans la deuxième version d’évaluation des coûts, avant d’être activées. L’approche à deux versions demande que vous définissiez une deuxième version d’évaluation des coûts. Voici les instructions pour définir cette version d’évaluation des coûts :

-   Affecter un type d’évaluation des **Coûts standard**.
-   Affectez un identificateur pertinent qui communique le contenu de la version d’évaluation des coûts, tel que **2016-UPDATES**.
-   Dans le groupe de champs **Autoriser les types de prix**, assurez-vous que le **Prix de revient** est défini sur **Oui**.
-   Autorisez les enregistrements de coûts à être entrés pour tous les sites (autrement dit, laissez le champ **Site** vide). Si vous entrez un site, les enregistrements de coûts peuvent être entrés uniquement pour ce site.
-   Utiliser un principe de secours des coûts **Actifs**.

Pour ajouter de nouveaux articles de fabrication au cours de la période bloquée, procédez comme suit.

1.  Utilisez la page **Paramétrage de la version d’évaluation des coûts** pour activer les enregistrements de coût à entrer dans la deuxième version d’évaluation des coûts contenant les mises à jour incrémentielles. Cela permet d’éviter l’activation des coûts en attente, alors que l’activation est autorisée après que les coûts en attente ont été complètement et précisément définis. Indiquez une date de début vierge comme stratégie dans la version d’évaluation des coûts, puis entrez une date de début lorsque vous entrez chaque enregistrement de coûts. La date de début doit représenter une date avant que les nouveaux articles soient achetés ou fabriqués.
2.  Utilisez la page **Prix de l’article** pour entrer les enregistrements de coûts pour les nouveaux articles achetés. Pour chaque enregistrement de coûts, entrez la version d’évaluation des coûts qui contient des mises à jour incrémentielles et utilisez la date de début qui précède la date de fabrication prévue pour les nouveaux articles fabriqués.
3.  Calculez le coût des nouveaux articles fabriqués à l’aide de la page **Calcul**. Ouvrez la page **Calcul** à partir de la page **Mise à jour de la version d’évaluation des coûts**, puis sélectionnez la version d’évaluation des coûts qui contient les mises à jour incrémentielles. Utilisez les critères de sélection pour spécifier le nouvel article fabriqué et tous ses composants fabriqués. Dans une structure de produit à plusieurs niveaux, il peut être également nécessaire de spécifier les articles parents qui contiennent les nouveaux articles fabriqués comme un composant. Entrez une date de début pour le calcul de nomenclature qui correspond au début de la fabrication des nouveaux articles fabriqués. La date de début doit s’inscrire dans les dates effectives pour la version de nomenclature et la version de gamme de l’article. **Remarque :** Un enregistrement de coût manquant peut indiquer un nouvel article fabriqué. Les calculs de nomenclature peuvent être limités aux articles comportant des coûts manquants.
4.  Vérifiez l’intégralité et l’exactitude des coûts calculés pour les nouveaux articles fabriqués. Utilisez la page **Terminé** pour vérifier les coûts calculés pour chaque enregistrement de coût d’article et réviser tous les messages d’information ou d’avertissement. Vous pouvez également utiliser la page **Calcul** pour réviser une liste des coûts calculés.
5.  Utilisez la page **Paramétrage de la version d’évaluation des coûts** pour modifier la balise de blocage afin d’autoriser l’activation des enregistrements de coûts en attente inclus dans la deuxième version d’évaluation des coûts.
6.  Utilisez la page **Activer les prix** (que vous pouvez ouvrir à partir de la page **Mise à jour de la version d’évaluation des coûts**) pour activer tous les enregistrements de coût d’article en attente inclus dans la deuxième version d’évaluation des coûts. Vous pouvez également activer les enregistrements des coûts en attente pour des articles individuels en cliquant sur le bouton **Activer** dans la page **Prix de l’article**.
7.  Utilisez la page **Paramétrage de la version d’évaluation des coûts** pour modifier les balises de blocage incluses dans la deuxième version d’évaluation des coûts afin d’empêcher toute maintenance des données supplémentaire. Les stratégies de blocage empêchent la saisie de nouveaux coûts en attente et l’activation de coûts en attente.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]