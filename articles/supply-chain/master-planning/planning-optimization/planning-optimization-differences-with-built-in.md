---
title: Différences entre la planification générale intégrée et l’optimisation de la planification
description: Cette rubrique répertorie les fonctionnalités que l’optimisation de la planification ne prend pas encore en charge et qui ne sont pas répertoriées sur la page d’analyse de concordance pour l’optimisation de la planification.
author: crytt
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 63f3bc6cb7563ee6ff719272a0795efffcb40bc8
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500194"
---
# <a name="differences-between-built-in-master-planning-and-planning-optimization"></a>Différences entre la planification générale intégrée et l’optimisation de la planification

[!include [banner](../../includes/banner.md)]

Les résultats de l’optimisation de la planification peuvent différer des résultats du moteur de planification générale intégrée. Ces différences peuvent être dûes à des fonctionnalités en attente. Cette rubrique répertorie les fonctionnalités que l’optimisation de la planification ne prend pas encore en charge et qui ne sont pas répertoriées sur la page **[Analyse de concordance pour l’optimisation de la planification](planning-optimization-fit-analysis.md)**.

| Fonctionnalité | Comportement actuel dans l’optimisation de la planification |
|---|---|
| Produits en poids variable | Les produits en poids variable sont considérés comme des produits habituels.|
| Dimensions extensibles | Les dimensions extensibles sont vides sur les ordres prévisionnels, même lorsque la case **Plan de couverture par dimension** est cochée sur la page **Groupes de dimensions de stockage** ou **Groupes de dimensions de suivi**. |
| Cycles de production filtrés | Pour plus de détails, voir [Planification de la production - Filtres](production-planning.md#filters). |
| Planification prévisionnelle | La planification prévisionnelle n’est pas prise en charge. Nous vous recommandons d’utiliser la planification générale dans laquelle un modèle de prévision est affecté au plan général. |
| Souches de numéros pour les ordres prévisionnels | Les souches de numéros pour les ordres prévisionnels ne sont pas prises en charge. Les numéros des ordres prévisionnels sont générés côté service. |
| Copie de plan, suppression de plan et le nettoyage de version de plan | <p>Les éléments suivants sont désactivés sous **Planification \> Planification \> Tenir à jour les plans** dans le volet de navigation :</p><ul><li>Copier un plan</li><li>Suppression de programme</li><li>Nettoyage de la version du plan</li></ul> |
| Ordres de retour | Les ordres de retour ne sont pas pris en compte. |
| Fonctionnalités liées à la planification | Pour plus de détails, voir [Planification avec une capacité infinie](infinite-capacity-planning.md#limitations). |
| Traitement du stock de sécurité | L’optimisation de la planification utilise toujours l’option *Date du jour + heure d’approvisionnement* pour le champ **Exécuter le minimum** sur la page **Couverture de l’article**. Cela évite les commandes planifiées indésirables et d’autres problèmes, car si le délai d’approvisionnement n’est pas inclus pour le stock de sécurité, les commandes planifiées qui sont créées pour le stock disponible actuellement bas seront toujours retardées en raison du délai de livraison. |
| Origine des besoins du stock de sécurité et besoins nets | Le besoin de type *Stock de Sécurité* n’est pas inclus et n’est pas affiché sur la page **Besoins nets**. Le stock de sécurité ne représente pas la demande et n’a pas de date de besoin associée. Au lieu de cela, il définit une contrainte sur la quantité de stock qui doit être présente à tout moment. Cependant, la valeur du champ **Minimum** est toujours prise en compte lors du calcul des commandes planifiées dans le cadre de la planification générale. Nous vous suggérons d’inspecter la colonne **Quantité accumulée** sur la page **Besoins nets** pour voir que cette valeur a été prise en compte. |
| Calendriers de transport | La valeur dans la colonne **Calendrier de transport** sur la page **Modes de livraison** est ignorée. |

## <a name="additional-resources"></a>Ressources supplémentaires

- [Analyse de concordance pour l’optimisation de la planification](planning-optimization-fit-analysis.md)
- [Paramètres non utilisés par l’optimisation de la planification](not-used-parameters.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]