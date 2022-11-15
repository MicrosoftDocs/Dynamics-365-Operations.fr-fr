---
title: Planification pilotée par la demande
description: L’article décrit comment générer des ordres planifiés pour les articles configurés en tant que points de découplage.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 8ba9a6d24923b66259bc8b6cc688ec667cb000de
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740300"
---
# <a name="demand-driven-planning"></a>Planification pilotée par la demande

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

L’article décrit comment générer des ordres planifiés pour les articles configurés en tant que points de découplage.

## <a name="net-flow-and-qualified-demand"></a>Flux net et demande qualifiée

Lors de la planification générale, le système applique le concept de *débit net* pour établir la quantité en stock effective en fonction du stock disponible réel, plus le stock en commande (commandes d’approvisionnement existantes qui n’ont pas encore été reçues), moins ce que l’on appelle la *demande qualifiée* (ventes à venir qualifiées), comme indiqué dans l’illustration suivante. Lorsque le système détermine à quelle zone tampon appartient un article et quelle doit être la quantité commandée, il évalue le flux net, et non le stock disponible réel.

![Exemple de graphique de calcul du débit net.](media/ddmrp-net-flow-example.png "Exemple de graphique de calcul du débit net")

Lorsqu’un ordre planifié est déclenché lors d’un cycle de planification, la quantité commandée correspond au niveau maximum moins le flux net. Pour affecter une priorité de commande, le système utilise la fonctionnalité de [planification axée sur les priorités](priority-based-planning.md) au lieu des dates de besoin. La planification des besoins en matériaux basée sur la demande (DDMRP) attribue la priorité d’une commande planifiée en fonction de la quantité commandée en pourcentage du stock maximal. Dans l’illustration précédente, la quantité commandée correspond à 53 % de la quantité maximale. Par conséquent, la priorité de commande pour le réapprovisionnement sera 53. (Pour le contexte, 0 est la priorité la plus élevée et 100 est la priorité la plus basse.)

*Demande qualifiée* est la demande en retard, plus la demande du jour, plus les pics de commandes qualifiés à l’avenir. L’illustration suivante montre un exemple de niveaux de demande pour aujourd’hui (12 juin) et les trois prochains jours. La DDMRP vous permet de définir un seuil de pic de commande pour identifier la demande qui dépasse les attentes normales. Si le seuil est fixé à 25 pièces, deux des dates futures indiquées dans l’illustration seront considérées comme des pics de commande. Vous devez attribuer un seuil de pic de commande pour chaque produit individuellement en utilisant sa page **Couverture de l’article**, comme décrit dans [Configurer des tampons pour un élément de point de découplage](ddmrp-buffer-profile-and-levels.md#set-up-buffers).

![Exemple de graphique de calcul de demande qualifiée.](media/ddmrp-net-qualified-demand-example.png "Exemple de graphique de calcul de demande qualifiée")

À condition qu’il n’y ait pas de demande en retard, vous pouvez maintenant ajouter la demande du jour (18) aux quantités des deux pics de commande (29 et 26) pour obtenir une demande qualifiée de 73. Même s’il existe une demande pour le 23 juin, notez qu’elle n’est pas incluse dans le calcul du flux net, car DDMRP déclenche l’ordre planifié différemment des groupes de couverture de planification traditionnels.

## <a name="generating-planned-orders-with-ddmrp"></a>Génération d’ordres planifiés avec DDMRP

Au cours d’un cycle de planification, le système crée un nouvel ordre planifié si le flux net d’un article tombe en dessous du point de réapprovisionnement. Lorsque vous utilisez la DDMRP, vous effectuez généralement une exécution de planification tous les jours. Par conséquent, vous vérifiez essentiellement vos niveaux de stock une fois par jour pour déterminer quels articles doivent être réapprovisionnés.

L’illustration suivante montre un exemple d’une situation où vous avez une commande de 18 pièces le 20 juin, 29 pièces le 21 juin, 26 pièces le 22 juin et 20 pièces le 23 juin. Étant donné que le seuil du pic est fixé à 25 pièces, deux de ces commandes sont signalées comme des pics. Il y a 220 pièces de cet article en main.

![Exemple de planification 1.](media/ddmrp-planning-example-1.png "Exemple de planification 1")

Si vous exécutez la planification générale maintenant, cela générera une commande planifiée si le flux net tombe en dessous du point de réapprovisionnement (219 pièces dans cet exemple).

![Exemple de planification 2.](media/ddmrp-planning-example-2.png "Exemple de planification 2")

Cet exemple produit une commande fournisseur planifiée pour une quantité de 130, qui est égale au niveau maximum moins le flux net. L’ordre planifié se voit attribuer une priorité de 53,07, en fonction de son pourcentage de la quantité maximale. Étant donné que ces valeurs ont été trouvées le 20 juin, le système crée un ordre planifié daté du 20 juin plus le délai découplé pour l’article (cinq jours ouvrables dans cet exemple). Par conséquent, étant donné que cinq jours ouvrables correspondent à une semaine à compter d’aujourd’hui, la commande planifiée est datée du 27 juin.

> [!NOTE]
> La planification générale calcule uniquement les éléments découplés à l’aide de la DDMRP. Tous les autres articles sont calculés à l’aide de la planification des besoins en matériaux standard (MRP).
