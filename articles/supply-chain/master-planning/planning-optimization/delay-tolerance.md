---
title: Tolérance de retard (jours négatifs)
description: Cet article fournit des informations sur le calcul de la tolérance de retard et son impact sur la création d’ordres planifiés dans l’optimisation de la planification.
author: t-benebo
ms.date: 08/09/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 78ba4236705f1a200d9fe796eb80d0241b0fa537
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740466"
---
# <a name="delay-tolerance-negative-days"></a>Tolérance de retard (jours négatifs)
<!-- KFM: Split topic into PO and classic -->

[!include [banner](../../includes/banner.md)]

La fonctionnalité de tolérance de retard permet à l’optimisation de la planification de prendre en compte la valeur **Jours négatifs** définie pour les groupes de couverture, la couverture des éléments et/ou les plans principaux. Elle sert à prolonger la période de tolérance de retard qui est appliquée lors de la planification générale. De cette façon, vous pouvez éviter de créer de nouvelles commandes d’approvisionnement si l’approvisionnement existant peut couvrir la demande après un court délai. Le but de cette fonctionnalité est de déterminer s’il est judicieux de créer un nouvel ordre d’approvisionnement pour une demande donnée.

## <a name="turn-delay-tolerance-features-on-or-off"></a>Activer ou désactiver les fonctionnalités de délai de tolérance.

Pour rendre la fonctionnalité de tolérance de retard disponible dans votre système, accédez à [Gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), et activez les fonctionnalités suivantes :

- *Jours négatifs pour l’optimisation de la planification* – Cette fonctionnalité active les paramètres de jours négatifs pour les groupes de couverture et la couverture des articles. Depuis la version 10.0.29 de Supply Chain Management, la fonctionnalité est obligatoire et ne peut pas être désactivée.
- *Automatisation de l’approvisionnement sur commande* – Cette fonctionnalité active les paramètres de jours négatifs pour les plans principaux. (Pour plus d’informations, voir [Automatisation de l’approvisionnement sur commande](../make-to-order-supply-automation.md).)

## <a name="delay-tolerance-in-planning-optimization"></a>Tolérance de retard dans l’optimisation de la planification

La tolérance de retard représente le nombre de jours au-delà du délai que vous êtes prêt à attendre avant de commander un nouveau réapprovisionnement lorsqu’un approvisionnement existant est déjà planifié. La tolérance de retard est définie en fonction des jours calendaires et non des jours ouvrables.

Au moment de la planification générale, lorsque le système calcule la tolérance de retard, il prend en compte le paramètre **Jours négatifs**. Vous pouvez définir la valeur **Jours négatifs** sur la page **Groupes de couverture** ou sur la page **Couverture de l’article** ou sur la page **Plans principaux**. Si des jours négatifs sont affectés à plusieurs niveaux, le système applique la hiérarchie suivante pour décider du paramètre à utiliser :

- Si les jours négatifs sont activés sur les **Plans principaux**, ce paramètre remplace tous les autres paramètres de jours négatifs lors de l’exécution du plan.
- Si des jours négatifs sont configurés sur la page **Couverture des éléments**, ce paramètre remplace le paramètre du groupe de couverture.
- Les jours négatifs qui sont configurés sur la page **Groupes de couverture** s’appliquent uniquement si les jours négatifs n’ont pas été configurés pour un article ou un plan pertinent.

Le système lie le calcul de la tolérance de retard à la *date de réapprovisionnement la plus proche*, qui est égale à la date du jour plus le délai. La tolérance de retard est calculée en utilisant la formule suivante, où *max()* trouve la plus grande des deux valeurs :

*max(Date de réapprovisionnement la plus proche, Date d’échéance de la demande)*  – *Date d’échéance de la demande* + *Jours négatifs*

Cette formule garantit que la planification générale ne crée pas de nouvelles commandes d’approvisionnement lorsqu’il existe suffisamment d’approvisionnement pendant le délai d’approvisionnement du produit.

> [!NOTE]
> Le calcul de la tolérance de retard dans l’optimisation de la planification utilise toujours le calcul dynamique des jours négatifs du moteur de planification générale déprécié. Le paramètre **Utiliser des jours négatifs dynamiques** de la page **Paramètres de la planification générale** n’a aucun effet sur ce comportement.

Si l’approvisionnement existant implique un retard de demande inférieur ou égal à la tolérance de retard calculée, l’optimisation de la planification rattache l’approvisionnement existant à la demande. Dans certains cas, il vaut mieux retarder la demande que de se retrouver avec une offre excédentaire.

Les sous-sections suivantes illustrent qui montrent comment la tolérance de retard affecte la création d’ordres planifiés dans l’optimisation de la planification.

### <a name="example-1"></a>Exemple 1

Un produit a la configuration suivante :

- **Délai :** *10*
- **Jours négatifs :** *2*

L’offre et la demande suivantes existent pour le produit :

- **Demande pour aujourd’hui :** une commande client pour une quantité de 10
- **Approvisionnement dans 12 jours :** une commande fournisseur pour une quantité de 10

L’approvisionnement existant peut couvrir la demande dans les 12 jours, et cette période est égale à la tolérance de retard. Par conséquent, lors de l’exécution de la planification générale, aucune commande planifiée n’est créé.

### <a name="example-2"></a>Exemple 2

Un produit a la configuration suivante :

- **Délai :** *10*
- **Jours négatifs :** *0*

L’offre et la demande suivantes existent pour le produit :

- **Demande pour aujourd’hui :** une commande client pour une quantité de 10
- **Approvisionnement dans 12 jours :** une commande fournisseur pour une quantité de 10

L’approvisionnement existant ne peut couvrir la demande qu’après 12 jours. Cependant, la tolérance de retard est de 10 jours. Par conséquent, lors de l’exécution de la planification générale, une commande planifiée pour une quantité de 10 est créé.

### <a name="example-3"></a>Exemple 3

Un produit a la configuration suivante :

- **Délai :** *10*
- **Jours négatifs :** *2*

L’offre et la demande suivantes existent pour le produit :

- **Demande dans 11 jours :** une commande client pour une quantité de 10
- **Approvisionnement dans 14 jours :** une commande fournisseur pour une quantité de 10

L’approvisionnement existant ne peut couvrir la demande qu’après trois jours. Cependant, la tolérance de retard est de deux jours. (Dans ce cas, la tolérance de retard ne comprend que les deux jours négatifs. La date de demande n’est pas incluse car elle est postérieure au délai de livraison du produit.) Par conséquent, lors de l’exécution de la planification générale, une commande planifiée pour une quantité de 10 est créé.
