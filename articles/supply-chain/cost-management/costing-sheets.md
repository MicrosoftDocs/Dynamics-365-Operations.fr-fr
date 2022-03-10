---
title: Feuilles de coûts
description: Le paramétrage de la feuille d’évaluation des coûts a deux objectifs. Premièrement, vous définissez le format d’affichage des informations des prix des marchandises vendues sur un article fabriqué ou un ordre de fabrication. L’affichage formaté est appelé feuille de coûts. Deuxièmement, vous définissez la base de calcul des coûts indirects. Le paramétrage de la feuille d’évaluation des coûts se base sur la fonctionnalité de groupe de coûts pour l’affichage d’informations et pour les formules de calcul des coûts indirects. Les deux objectifs du paramétrage de la feuille d’évaluation des coûts sont décrits dans cet article.
author: AndersGirke
ms.date: 11/18/2021
ms.topic: article
ms.search.form: CostSheetDesigner, CostSheetCalculationFactor
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53201
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 64b8a9b8b29193f25e706e52424de2af3454aec8
ms.sourcegitcommit: f11ad8d7ee8a4d2ee1a1bb601622b50e14955c4a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/18/2021
ms.locfileid: "7825356"
---
# <a name="costing-sheets"></a>Feuilles de coûts

[!include [banner](../includes/banner.md)]

Le paramétrage de la feuille d’évaluation des coûts a deux objectifs. Premièrement, vous définissez le format d’affichage des informations des prix des marchandises vendues sur un article fabriqué ou un ordre de fabrication. L’affichage formaté est appelé feuille de coûts. Deuxièmement, vous définissez la base de calcul des coûts indirects. Le paramétrage de la feuille d’évaluation des coûts se base sur la fonctionnalité de groupe de coûts pour l’affichage d’informations et pour les formules de calcul des coûts indirects. Les deux objectifs du paramétrage de la feuille d’évaluation des coûts sont décrits dans cet article. 

Le tableau suivant répertorie les rôles de sécurité prêts à l’emploi qui peuvent accéder aux feuilles de calcul des coûts, y compris le niveau d’accès accordé à chaque rôle par les paramètres par défaut.

| Rôle | Accès
|---|---|
| Responsable comptabilité | Modifier |
| Commis comptable de stock | Afficher |
| Comptable de stock | Afficher |

Une feuille de coûts est l’affichage formaté des informations sur le prix des marchandises vendues pour un article fabriqué ou un ordre de fabrication. Lorsque vous paramétrez une feuille de coûts, vous définissez le format des informations ainsi que la base de calcul des coûts indirects. Le paramétrage de la feuille de coûts se base sur les fonctionnalités de groupe de coûts pour l’affichage d’informations et pour les formules utilisées pour calculer les coûts indirects. Vous trouverez ci-dessous plus d’informations sur les deux objectifs du paramétrage de la feuille de coûts :

- **Définir le format pour la feuille d’évaluation des coûts.** Le format défini par l’utilisateur pour une feuille d’évaluation des coûts identifie la segmentation des coûts qui comprend le coût des marchandises vendues pour un article fabriqué. Par exemple, les informations sur le coût des marchandises vendues pour un article peuvent être segmentées en matière, en main-d’œuvre et en frais généraux, sur la base des groupes de coûts. Ces groupes de coûts sont affectés aux formules de calcul des articles, catégories de coûts (pour les opérations d’acheminement) et coûts indirects. Le format de la feuille de coûts nécessite généralement des totaux intermédiaires lorsque plusieurs groupes de coûts ont été définis. Par exemple, plusieurs groupes de coûts liés au matériel peuvent être agrégés. La définition d’un format de feuille de coûts est facultative mais un format de feuille de coûts doit être défini si les coûts indirects sont calculés.
- **Définir la base pour le calcul des coûts indirects.** Les coûts indirects reflètent les frais généraux de fabrication associés à la production d’un article fabriqué. Une formule de calcul des coûts indirects peut être exprimée comme une surcharge ou un taux. Une surcharge représente un pourcentage de valeur, alors qu’un taux représente un montant par heure pour une opération de gamme. Un groupe de coûts définit la base de la formule de calcul, comme une surcharge de 100 pour cent pour un groupe de coûts de main-d’œuvre ou un taux horaire de 50,00 EUR pour un groupe de coûts machine. Si vous souhaitez définir une formule de calcul et sa base de groupe de coûts, le paramétrage de la feuille de coûts nécessite l’identification du groupe de coûts qui représente les frais généraux et la sélection d’une approche surcharge ou taux.

Chaque formule de calcul doit être entrée comme un enregistrement de coût. L’enregistrement de coûts consiste en une version d’évaluation des coûts spécifique, un pourcentage de surcharge (ou un montant de taux), la base du groupe de coûts, un statut et une date d’effet. La première fois qu’un enregistrement de coûts est saisi, il est doté du statut **En attente** et d’une date d’effet. Lorsque vous activez l’enregistrement des coûts, le statut est mis à jour de manière à ce qu’il soit défini comme enregistrement actif actuel et que la date d’effet soit mise à jour sur la date d’activation. L’enregistrement des coûts peut également spécifier un site pour une formule de calcul spécifique au site. Vous pouvez également laisser le champ **Site** vide pour indiquer que la formule de calcul est une formule à l’échelle de l’entreprise. L’enregistrement de coûts peut éventuellement consister en un article ou un groupe d’articles spécifié lorsque la formule de calcul a été marquée comme formule par article. 

Les enregistrements des coûts actifs actuels pour les formules de calcul des coûts indirects sont utilisés pour estimer les coûts des ordres de fabrication. Ils sont également utilisés pour calculer les coûts réels liés à la consommation réelle de temps et de matériel. Les enregistrements de coûts en attente servent dans les calculs de nomenclature pour une date future. 

Deux stratégies de blocage pour une version d’évaluation des coûts déterminent si les coûts en attente peuvent être mis à jour et s’ils peuvent être activés. Les stratégies de blocage permettent d’autoriser la mise à jour des données, puis d’empêcher la mise à jour des données pour les données de coûts dans une version d’évaluation des coûts. 

Après avoir défini le format de la feuille de coûts et les calculs des coûts indirects, vous devez effectuer une étape séparée pour vérifier et enregistrer les informations. La feuille de coûts représente un format à l’échelle de la société pour afficher de façon cohérente les informations sur le coût des marchandises vendues. 

La feuille de coûts s’affiche dans la page **Calculer le coût de l’article**. La feuille de coûts peut être affichée pour l’enregistrement des coûts calculés d’un article fabriqué dans la page **Prix de l’article** ou pour un enregistrement de calcul spécifique à l’ordre dans la page **Résultats du calcul de nomenclature**. Elle peut également être affichée dans le cadre de la page **Calcul de prix** pour un ordre de fabrication.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
