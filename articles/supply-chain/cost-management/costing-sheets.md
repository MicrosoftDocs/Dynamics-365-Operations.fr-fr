---
title: "Feuilles de coûts"
description: "Le paramétrage de la feuille d'évaluation des coûts a deux objectifs. Premièrement, vous définissez le format d'affichage des informations des prix des marchandises vendues sur un article fabriqué ou un ordre de fabrication. L'affichage formaté est appelé feuille de coûts. Deuxièmement, vous définissez la base de calcul des coûts indirects. Le paramétrage de la feuille d'évaluation des coûts se base sur la fonctionnalité de groupe de coûts pour l'affichage d'informations et pour les formules de calcul des coûts indirects. Les deux objectifs du paramétrage de la feuille d'évaluation des coûts sont décrits dans cet article."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostSheetDesigner
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 53201
ms.assetid: e7d72b43-3892-49ae-8821-9eede3f4d24a
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ff9bde25a2e1785d7063f8c69f673d87abbd948b
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017

---

# <a name="costing-sheets"></a>Feuilles de coûts

[!include[banner](../includes/banner.md)]


Le paramétrage de la feuille d'évaluation des coûts a deux objectifs. Premièrement, vous définissez le format d'affichage des informations des prix des marchandises vendues sur un article fabriqué ou un ordre de fabrication. L'affichage formaté est appelé feuille de coûts. Deuxièmement, vous définissez la base de calcul des coûts indirects. Le paramétrage de la feuille d'évaluation des coûts se base sur la fonctionnalité de groupe de coûts pour l'affichage d'informations et pour les formules de calcul des coûts indirects. Les deux objectifs du paramétrage de la feuille d'évaluation des coûts sont décrits dans cet article. 

Une feuille de coûts est l'affichage formaté des informations sur le prix des marchandises vendues pour un article fabriqué ou un ordre de fabrication. Lorsque vous paramétrez une feuille de coûts, vous définissez le format des informations ainsi que la base de calcul des coûts indirects. Le paramétrage de la feuille de coûts se base sur les fonctionnalités de groupe de coûts pour l'affichage d'informations et pour les formules utilisées pour calculer les coûts indirects. Vous trouverez ci-dessous plus d'informations sur les deux objectifs du paramétrage de la feuille de coûts :
-   **Définir le format pour la feuille d'évaluation des coûts.** Le format défini par l'utilisateur pour une feuille d'évaluation des coûts identifie la segmentation des coûts qui comprend le coût des marchandises vendues pour un article fabriqué. Par exemple, les informations sur le coût des marchandises vendues pour un article peuvent être segmentées en matière, en main-d'œuvre et en frais généraux, sur la base des groupes de coûts. Ces groupes de coûts sont affectés aux formules de calcul des articles, catégories de coûts (pour les opérations d'acheminement) et coûts indirects. Le format de la feuille de coûts nécessite généralement des totaux intermédiaires lorsque plusieurs groupes de coûts ont été définis. Par exemple, plusieurs groupes de coûts liés au matériel peuvent être agrégés. La définition d'un format de feuille de coûts est facultative mais un format de feuille de coûts doit être défini si lés coûts indirects sont calculés.
-   **Définir la base pour le calcul des coûts indirects.** Les coûts indirects reflètent les frais généraux de fabrication associés à la production d'un article fabriqué. Une formule de calcul des coûts indirects peut être exprimée comme une surcharge ou un taux. Une surcharge représente un pourcentage de valeur, alors qu'un taux représente un montant par heure pour une opération de gamme. Un groupe de coûts définit la base de la formule de calcul, comme une surcharge de 100 pour cent pour un groupe de coûts de main-d'œuvre ou un taux horaire de 50,00 EUR pour un groupe de coûts machine. Si vous souhaitez définir une formule de calcul et sa base de groupe de coûts, le paramétrage de la feuille de coûts nécessite l'identification du groupe de coûts qui représente les frais généraux et la sélection d'une approche surcharge ou taux.

Chaque formule de calcul doit être entrée comme un enregistrement de coût. L'enregistrement de coûts consiste en une version d'évaluation des coûts spécifique, un pourcentage de surcharge (ou un montant de taux), la base du groupe de coûts, un statut et une date d'effet. La première fois qu'un enregistrement de coûts est saisi, il est doté du statut **En attente** et d'une date d'effet. Lorsque vous activez l'enregistrement des coûts, le statut est mis à jour de manière à ce qu'il soit défini comme enregistrement actif actuel et que la date d'effet soit mise à jour sur la date d'activation. L'enregistrement des coûts peut également spécifier un site pour une formule de calcul spécifique au site. Vous pouvez également laisser le champ **Site** vide pour indiquer que la formule de calcul est une formule à l'échelle de l'entreprise. L'enregistrement de coûts peut éventuellement consister en un article ou un groupe d'articles spécifié lorsque la formule de calcul a été marquée comme formule par article. 

Les enregistrements des coûts actifs actuels pour les formules de calcul des coûts indirects sont utilisés pour estimer les coûts des ordres de fabrication. Ils sont également utilisés pour calculer les coûts réels liés à la consommation réelle de temps et de matériel. Les enregistrements de coûts en attente servent dans les calculs de nomenclature pour une date future. 

Deux stratégies de blocage pour une version d'évaluation des coûts déterminent si les coûts en attente peuvent être mis à jour et s'ils peuvent être activés. Les stratégies de blocage permettent d'autoriser la mise à jour des données, puis d'empêcher la mise à jour des données pour les données de coûts dans une version d'évaluation des coûts. 

Après avoir défini le format de la feuille de coûts et les calculs des coûts indirects, vous devez effectuer une étape séparée pour vérifier et enregistrer les informations. La feuille de coûts représente un format à l'échelle de la société pour afficher de façon cohérente les informations sur le coût des marchandises vendues. 

La feuille de coûts s'affiche dans la page **Calculer le coût de l'article**. La feuille de coûts peut être affichée pour l'enregistrement des coûts calculés d'un article fabriqué dans la page **Prix de l'article** ou pour un enregistrement de calcul spécifique à l'ordre dans la page **Résultats du calcul de nomenclature**. Elle peut également être affichée dans le cadre de la page **Calcul de prix** pour un ordre de fabrication.






