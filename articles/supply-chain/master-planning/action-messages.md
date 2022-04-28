---
title: Messages d’action
description: Un message d’action est une suggestion générée par le système visant à modifier un ordre prévisionnel ou confirmé existant.
author: t-benebo
ms.date: 03/18/2022
ms.topic: article
ms.search.form: ReqGroup, MCRSalesOrderMessages, MCRSalesTableDetailedStatus, TAMItemVendRebateGroup, TAMVendRebate, TAMVendRebateAgreementLineInfoPart, TAMVendRebateGroup, TAMVendRebateTable, TAMVendRebateTrans, ReqTransActionListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19411
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: e6df6cfd038383b3eeaa3659e0af3e469429f81e
ms.sourcegitcommit: 197e6ddee84522fd587c6e4ee4f9089101e301c2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2022
ms.locfileid: "8570252"
---
# <a name="action-messages"></a>Messages d’action

[!include [banner](../includes/banner.md)]

Un message d’action est une suggestion générée par le système visant à modifier un ordre prévisionnel, approuvé ou confirmé existant.

Les messages d’action sont générés par le calcul de planification principal en réponse à la modification des demandes. Il est par exemple possible que la date d’expédition ou la quantité ait été modifié sur une commande client après que vous avez déjà créé une commande fournisseur pour honorer la demande de cette commande client. Dans ce cas, la planification générale génère un ou plusieurs messages d’action qui vous suggèrent de mettre la commande fournisseur à jour. Vous devez décider d’apporter ou non les modifications suggérées.

Vous pouvez configurer le mode de calcul des messages d’action pour un groupe de couverture que vous liez à un article.

## <a name="select-action-messages"></a>Sélection des messages d’action

Sur la page **Groupes de couverture**, vous pouvez sélectionner les messages d’action que vous voulez que le système génère, et les groupes de couverture ou les articles auxquels les messages s’appliquent. Le tableau suivant répertorie les messages d'action que vous pouvez sélectionner.

| Message | Description |
|---|---|
| Avance | Le système génèrera des messages d’action, si nécessaire, pour déplacer les commandes à une date plus rapprochée. Dans le champ **Marge d’avance**, vous pouvez également spécifier le nombre maximal de jours qu'il peut s'écouler entre une réception et une sortie sans avance. |
| Ajourner | Le système génèrera des messages d’action, si nécessaire, pour déplacer les commandes à une date plus lointaine. Dans le champ **Marge d’ajournement**, vous pouvez également spécifier le nombre maximal de jours qu'il peut s'écouler entre une réception et une sortie sans ajournement. |
| Diminution | Le système générera des messages d'action lorsque des ordres de fabrication, des commandes fournisseur et d’autres transactions de réception doivent être diminués afin d’éviter des dépassements de niveaux de stock. |
| Augmentation | Le système générera des messages d'action lorsque des ordres de fabrication, des commandes fournisseur et d’autres transactions de réception doivent être augmentés afin d’éviter des pénuries de niveaux de stock. |
| Actions déduites | Les messages d'action créés pour les transactions de réception seront propagés à tous les besoins dérivés, et les messages d'action nécessaires seront générés pour les transactions de réception qui satisfont à ces exigences. |

Les sections suivantes fournissent quelques scénarios détaillés.

## <a name="increase-and-decrease-actions-with-product-default-order-quantities"></a>Actions d'augmentation ou de diminution avec les quantités de commande par défaut du produit

Sur la page **Paramètres de commande par défaut** d'un article, vous pouvez configurer une quantité minimum de commande, une quantité maximum de commande et plusieurs valeurs. Le système prend ensuite ces paramètres en compte lorsqu'il suggère des actions, pour s'assurer que les suggestions n'entraîneront jamais de sous-approvisionnement.

Par exemple, vous avez un article qui a les paramètres suivants sur sa page **Paramètres de commande par défaut** :

- **Quantité de commande minimale :** *0*
- **Quantité de commande maximale :** *90*
- **Multiple :** *20*

S'il existe une demande pour une quantité de 60 de cet article, la planification générale créera une commande fournisseur prévisionnelle pour une quantité de 60. Si la demande est augmentée de 30, la planification générale proposera une augmentation de 40, car elle respectera le multiple de 20 et ne provoquera jamais de sous-approvisionnement.

## <a name="action-messages-for-orders-related-to-safety-stock"></a>Messages d'action pour les commandes liées au stock de sécurité

Les messages d'action pour les commandes qui fournissent un stock de sécurité ne suggéreront jamais de diminuer la quantité en dessous de la quantité nécessaire pour le stock de sécurité. En d'autres termes, s'il existe une commande qui fournit le stock de sécurité et la demande client, et que la demande est diminuée ou annulée, la planification générale suggérera de diminuer la commande planifiée de la demande diminuée. Cependant, elle ne suggérera jamais une valeur inférieure au stock de sécurité nécessaire.

Le système ne proposera pas de reporter les actions d'approvisionnement du stock de sécurité, car il est supposé que le stock de sécurité doit être approvisionné à l'heure et à la date requises.

### <a name="advance-and-postpone-actions-related-to-boms"></a>Avancer et ajourner les actions liées aux nomenclatures

Les actions liées aux composants des nomenclatures (BOM) doivent être appliquées avant les actions de leurs articles parents, car d'autres commandes liées à des nomenclatures de niveau supérieur peuvent être affectées. Vous devez alors relancer la planification générale pour recalculer et suggérer les actions appropriées.

Par exemple, vous avez la situation suivante :

- Le bien final *FG* de type *fabrication* a une nomenclature qui inclut la matière première *RM*.
- La date d'aujourd'hui est le 21 janvier.
- Un ordre de fabrication existant et lancé pour *FG* est prévu pour le 25 janvier.
- Pour prendre en charge l'ordre de fabrication existant, la planification générale a créé une commande fournisseur prévisionnelle pour la matière première requise *RM*. Cette commande a une date de besoin au 25 janvier.
- Une nouvelle commande client du produit *FG* est créée aujourd'hui. Sa date de besoin est aujourd'hui (le 21 janvier).
- Le 21 janvier est fermé pour la livraison sur le calendrier *RM*, mais le 22 janvier est ouvert.

Lorsque la planification générale est exécutée, elle génère des messages d'action anticipée qui suggèrent d'augmenter la production précédemment planifiée afin que vous puissiez satisfaire la commande du jour.

- Pour répondre à la nouvelle demande, elle propose de déplacer l'ordre de fabrication de *FG* au 21 janvier. (Elle fait cette suggestion sans tenir compte de la date de clôture de *RM* .)
- Comme *RM* est toujours nécessaire pour l'ordre de fabrication, elle propose également d'avancer la commande fournisseur prévisionnelle. Cependant, cette fois, elle consulte le calendrier *RM*. Par conséquent, elle suggère de déplacer la commande fournisseur prévisionnelle de *RM* au 22 janvier (car le 21 janvier est fermé).

Comme vous pouvez le voir, la matière première nécessaire *RM* arrivera maintenant trop tard pour la fabrication prévue de *FG*. Par conséquent, vous devez d'abord appliquer l'action anticipée à la commande fournisseur prévisionnelle pour *RM*, puis réexécuter la planification générale. À ce stade, la planification générale générera un nouveau message d'action suggérant de déplacer l'ordre de fabrication de *FG* au 22 janvier.
