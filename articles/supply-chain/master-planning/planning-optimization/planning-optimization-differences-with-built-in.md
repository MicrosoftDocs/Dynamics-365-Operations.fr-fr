---
title: Différences entre l’optimisation de la planification et le moteur de planification générale déprécié
description: Cet article répertorie les fonctionnalités que l’optimisation de la planification ne prend pas encore en charge et qui ne sont pas répertoriées sur la page d’analyse de concordance pour l’optimisation de la planification.
author: t-benebo
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 6e1671a508b85a94ac9687af15e898d885ea94c1
ms.sourcegitcommit: 55e440e30490b2d36d86b22aa1263d5da97633aa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2022
ms.locfileid: "9745359"
---
# <a name="differences-between-planning-optimization-and-the-deprecated-master-planning-engine"></a>Différences entre l’optimisation de la planification et le moteur de planification générale déprécié

[!include [banner](../../includes/banner.md)]

Les résultats de l’optimisation de la planification peuvent différer des résultats du moteur de planification générale déprécié. Ces différences peuvent être dûes à des fonctionnalités en attente. Cet article répertorie les fonctionnalités que l’optimisation de la planification ne prend pas encore en charge et qui ne sont pas répertoriées sur la page **[Analyse de concordance pour l’optimisation de la planification](planning-optimization-fit-analysis.md)**.

| Fonctionnalité | Comportement actuel dans l’optimisation de la planification |
|---|---|
| Produits en poids variable | Les produits en poids variable sont considérés comme des produits habituels.|
| Dimensions extensibles | Les dimensions extensibles ne sont pas prises en charge par Planning Optimization. Lorsque vous utilisez l’optimisation de la planification, les dimensions extensibles sont vides sur les ordres prévisionnels, même quand la case **Plan de couverture par dimension** est cochée sur la page **Groupes de dimensions de stockage** ou **Groupes de dimensions de suivi**. |
| Cycles de production filtrés | Pour plus de détails, voir [Planification de la production - Filtres](production-planning.md#filters). |
| Planification prévisionnelle | La planification prévisionnelle n’est pas prise en charge. Nous vous recommandons d’utiliser la planification générale dans laquelle un modèle de prévision est affecté au plan général. |
| Souches de numéros pour les ordres prévisionnels | Les souches de numéros pour les ordres prévisionnels ne sont pas prises en charge. Les numéros des ordres prévisionnels sont générés côté service. Le numéro de commande planifiée est normalement affiché avec 10 chiffres, mais la séquence est en fait construite sur 20 caractères, avec 10 chiffres alloués pour le nombre de cycles de planification et les 10 autres chiffres pour le nombre de commandes planifiées. |
| Copie de plan, suppression de plan et le nettoyage de version de plan | <p>Les éléments suivants sont désactivés sous **Planification \> Planification \> Tenir à jour les plans** dans le volet de navigation :</p><ul><li>Copier un plan</li><li>Suppression de programme</li><li>Nettoyage de la version du plan</li></ul> |
| Ordres de retour | Les ordres de retour ne sont pas pris en compte. |
| Fonctionnalités liées à la planification | Pour plus de détails, voir [Planification avec une capacité infinie](infinite-capacity-planning.md#limitations). |
| Traitement du stock de sécurité | L’optimisation de la planification utilise toujours l’option *Date du jour + heure d’approvisionnement* pour le champ **Exécuter le minimum** sur la page **Couverture de l’article**. Cela évite les commandes planifiées indésirables et d’autres problèmes, car si le délai d’approvisionnement n’est pas inclus pour le stock de sécurité, les commandes planifiées qui sont créées pour le stock disponible actuellement bas seront toujours retardées en raison du délai de livraison. |
| Origine des besoins du stock de sécurité et besoins nets | Le besoin de type *Stock de Sécurité* n’est pas inclus et n’est pas affiché sur la page **Besoins nets**. Le stock de sécurité ne représente pas la demande et n’a pas de date de besoin associée. Au lieu de cela, il définit une contrainte sur la quantité de stock qui doit être présente à tout moment. Cependant, la valeur du champ **Minimum** est toujours prise en compte au moment du calcul des commandes planifiées dans le cadre de la planification générale. Nous vous suggérons d’inspecter la colonne **Quantité accumulée** sur la page **Besoins nets** pour voir que cette valeur a été prise en compte. Parce que l’origine des besoins est différente, différentes actions peuvent être suggérées. |
| Calendriers de transport | La valeur dans la colonne **Calendrier de transport** sur la page **Modes de livraison** est ignorée. |
| Code de couverture min/max sans valeur| Avec le moteur de planification générale déprécié, quand vous utilisez un code de couverture min/max où aucune valeur minimale ou maximale n’est définie, le moteur de planification traite le code de couverture comme une exigence et crée une commande pour chaque exigence. Avec l’optimisation de la planification, le système créera une commande par jour pour couvrir le montant total de cette journée.  |
| Besoins nets et ordres planifiés créés manuellement | Avec le moteur de planification générale déprécié, les commandes d’approvisionnement créées manuellement pour un article apparaissent automatiquement parmi les besoins nets pour cet article. Par exemple, à la création d’une commande fournisseur à partir d’une commande client, la commande client apparaît sur la page **Besoins nets** sans nécessiter aucune action préalable. En effet, le moteur de planification générale déprécié enregistre les transactions de stock dans la table `inventLogTTS` et montre les changements sur la page **Besoins nets** pour les plans dynamiques. Cependant, avec l’optimisation de la planification, les commandes créées manuellement n’apparaissent pas parmi les besoins nets d’un article tant que l’optimisation de la planification n’est pas exécutée (à l’aide d’un plan qui inclut l’article) ou tant que vous n’avez pas sélectionné **Mise à jour \> Planification** dans le volet Actions de la page **Besoins nets** qui exécutera la planification de l’article. Pour plus d’informations sur l’utilisation de la page **Besoins nets**, consultez [Besoins nets et informations sur l’origine des besoins](net-requirements.md). |
| Affectation de ressources | Lorsque vous travaillez avec une capacité infinie, le moteur de planification générale déprécié affecte tous les ordres planifiés à la même ressource sur un groupe de ressources donné. L’optimisation de la planification améliore cela en sélectionnant des ressources au hasard afin que différents ordres de fabrication puissent utiliser différentes ressources. Si vous souhaitez utiliser la même ressource pour tous les ordres planifiés, vous devez spécifier cette ressource dans la gamme. |
| Extended data types (EDT) | Optimisation de la planification ne prend pas en charge les modifications de la précision des EDT. Cela signifie que ce processus n’est pas officiellement pris en charge et son fonctionnement n’est pas garanti. |
| Traitement du stock de sécurité | L’Optimisation de la planification utilise toujours un **Minimum d’exécution** de *Date du jour + heure d’achat*. Cela prépare le système à utiliser une configuration de planification simplifiée à l’avenir et fournit un résultat exploitable. Si le délai d’approvisionnement n’est pas inclus pour le stock de sécurité, les commandes planifiées qui sont créées pour le stock disponible bas seront toujours retardées en raison du délai de livraison. Ce comportement peut provoquer des perturbations importantes et des ordres prévisionnels indésirables. La meilleure pratique consiste à modifier le paramètre pour utiliser *Date du jour + heure d’achat*. Mettez à jour les données principales pour éviter les avertissements. |
| Copie du plan statique vers le plan dynamique | L’Optimisation de la planification ne copie pas les plans statiques dans les plans dynamiques, quel que soit le paramètre sur la page **Paramètres de planification générale**. En général, cette opération est moins pertinente en raison de la vitesse et de la régénération complète fournies par l’Optimisation de la planification. Si deux plans ou plus sont utilisés, la planification principale doit être déclenchée pour chaque plan. |

## <a name="additional-resources"></a>Ressources supplémentaires

- [Analyse de concordance pour l'optimisation de la planification](planning-optimization-fit-analysis.md)
- [Paramètres non utilisés par l’optimisation de la planification](not-used-parameters.md)
- [Paramètres de date et d’heure utilisés par l’optimisation de la planification](date-time-used.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
