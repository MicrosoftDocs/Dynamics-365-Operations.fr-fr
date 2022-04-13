---
title: Demandes d’achat
description: Cette rubrique décrit comment les demandes d’achat sont prises en charge dans Optimisation de la planification.
author: t-benebo
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqPlanSched, ReqGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 0328342fbe322225a5ecb095d3b0165caa6d18d3
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469643"
---
# <a name="purchase-requisitions"></a>Demandes d’achat

[!include [banner](../../includes/banner.md)]

La planification générale peut réapprovisionner les demandes d’achat approuvées. Par conséquent, pour couvrir les demandes d’achat, les utilisateurs n’ont pas besoin d’utiliser un workflow pour créer des commandes fournisseur À la place, les demandes d’achat peuvent être couvertes par la planification générale. En raison de cette fonctionnalité, une demande d’achat peut produire une commande fournisseur, un ordre de transfert ou un ordre de fabrication, selon la valeur de **Type d’ordre prévisionnel** définie pour le produit associé.

## <a name="enable-master-plans-to-include-requisitions"></a>Activer les plans généraux pour inclure des demandes

Pour inclure des demandes lors du calcul de la couverture pour un plan général, procédez comme suit.

1. Accédez à **Planification générale** \> **Paramétrage** \> **Plans** \> **Plans généraux**.
1. Créez ou sélectionnez un plan général.
1. Dans le raccourci **Général**, définissez l’option **Inclure les demandes** sur *Oui*.
1. Répétez les étapes 2 et 3 pour chaque plan général supplémentaire dans lequel vous souhaitez inclure des demandes.

## <a name="approved-requisitions-time-fence"></a>Plage de gestion des demandes approuvées

La *plage de gestion des demandes approuvées* établit jusqu’où dans le temps (en jours) un plan général inclura la demande des demandes de réapprovisionnement approuvées. Vous pouvez définir une plage de gestion des demandes approuvées à la fois au niveau du groupe de couverture et au niveau du plan général.

### <a name="set-the-approved-requisitions-time-fence-for-a-coverage-group"></a>Définir la plage de gestion des demandes approuvées pour un groupe de couverture

1. Accédez à **Planification** \> **Paramétrage** \> **Couverture** \> **Groupes de couverture**.
1. Créez ou sélectionnez un groupe de couverture.
1. Dans le raccourci **Autre**, définissez le champ **Plage de gestion des demandes approuvées (jours)** sur le nombre de jours à inclure dans la plage de gestion.
1. Répétez les étapes 2 et 3 pour chaque groupe de couverture supplémentaire dans lequel vous souhaitez définir une plage de gestion des demandes approuvées.

### <a name="set-the-approved-requisitions-time-fence-for-individual-master-plans"></a>Définir la plage de gestion des demandes approuvées pour des plans généraux individuels

Lorsque vous définissez une plage de gestion des demandes approuvées pour un plan général individuel, le paramètre remplace le paramètre de plage de gestion pour tout groupe de couverture applicable.

1. Accédez à **Planification générale** \> **Paramétrage** \> **Plans** \> **Plans généraux**.
1. Créez ou sélectionnez un plan général.
1. Dans le raccourci **Plages de gestion en jours**, définissez le champ **Plage de gestion des demandes approuvées (jours)** sur le nombre de jours à inclure dans la plage de gestion.
1. Répétez les étapes 2 et 3 pour chaque plan général supplémentaire dans lequel vous souhaitez définir une plage de gestion des demandes approuvées.

> [!IMPORTANT]
> **Prochainement :** les plages de gestion des demandes approuvées ne sont pas encore prises en charge pour l’optimisation de la planification. Jusqu’à ce qu’elles soient prises en charge, toutes les valeurs que vous entrez dans le champ **Plage de gestion des demandes approuvées (jours)** seront ignorées.

## <a name="independent-supply-regardless-of-coverage-code"></a>Approvisionnement indépendant, indépendamment du code de couverture

Les demandes d’achat sont toujours couvertes par les ordres prévisionnels indépendants, quel que soit le code de couverture. Ce comportement garantit une traçabilité et des workflows précis entre les demandes d’achat et les ordres de réapprovisionnement.

### <a name="example-1"></a>Exemple 1

Un produit est configuré pour avoir une valeur de **Code de couverture** de *Min/max*. Il a les statuts de stock et de demande suivants :

- Quantité de stock disponible= 10.
- Quantité de stock minimale = 15.
- Quantité de stock maximale = 20.
- Il existe une demande d’achat pour une pièce. La date demandée est Aujourd’hui.

Lors de l’exécution de la planification générale, deux ordres prévisionnels sont créés : un pour 10 pièces pour réapprovisionner le stock à la quantité maximale et un pour une pièce pour réapprovisionner la demande d’achat.

### <a name="example-2"></a>Exemple 2

Un produit est configuré pour avoir une valeur de **Code de couverture** de *Min/max*. Il a les statuts de stock et de demande suivants :

- Quantité de stock disponible= 17.
- Quantité de stock minimale = 15.
- Quantité de stock maximale = 20.
- Il existe une demande d’achat pour une pièce. La date demandée est Aujourd’hui.

Lors de l’exécution de la planification générale, un ordre prévisionnel pour une pièce est créé pour réapprovisionner la demande d’achat.

### <a name="example-3"></a>Exemple 3

Un produit est configuré pour avoir une valeur de **Code de couverture** de *Période* et une période de sept jours. Il a les statuts de stock, de commande client et de demande suivants :

- Quantité de stock disponible= 0.
- Il existe une commande client de cinq pièces. La date d’expédition prévue est Aujourd’hui plus un jour.
- Il existe une demande d’achat pour trois pièces. La date demandée est Aujourd’hui plus trois jours.

Lors de l’exécution de la planification générale, deux ordres prévisionnels sont créés : un pour trois pièces pour réapprovisionner la demande d’achat et un pour cinq pièces pour réapprovisionner la demande de commande client.

> [!NOTE]
> Une fois qu’un ordre prévisionnel lié à une demande d’achat est confirmé, le moteur de planification conserve le lien avec la demande d’achat. S’il s’avère par la suite que l’ordre confirmé n’indique pas une quantité nécessaire pour traiter la demande d’achat, le système crée un nouvel ordre prévisionnel pour la différence.

Pour plus d’informations sur les demandes d’achat, voir [Présentation générale de la demande d’achat](../../procurement/purchase-requisitions-overview.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]