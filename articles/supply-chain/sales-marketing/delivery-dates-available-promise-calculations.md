---
title: Promesse de commande
description: Cet article fournit des informations sur les promesses de commande. Les promesses de commandes vous permettent de promettre de manière fiable des dates de livraison à vos clients et vous offre une certaine flexibilité pour pouvoir respecter ces dates.
author: Henrikan
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SalesATP, SalesAvailableDlvDates, SalesCarrier
audience: Application User
ms.reviewer: kamaybac
ms.custom: 193933
ms.assetid: 676fc53a-fa25-4688-9f26-1005316763b8
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c835e25348b937c1dd68d8fa45b0264bd6815c23
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2022
ms.locfileid: "9228264"
---
# <a name="order-promising"></a>Promesse de commande

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur les promesses de commande. Les promesses de commandes vous permettent de promettre de manière fiable des dates de livraison à vos clients et vous offre une certaine flexibilité pour pouvoir respecter ces dates.

La promesse de commande calcule les premières dates d’expédition et de réception, et est basée sur la méthode de contrôle de la date de livraison et les jours de transport. Vous pouvez faire votre sélection parmi les méthodes de contrôle de la date de livraison :

- **Délai de vente** – Le délai de vente est le temps entre la création de la commande client et l’expédition des articles. Le calcul de la date de livraison est basé sur un nombre de jours par défaut, et ne prend pas en compte pas la disponibilité du stock, la demande connue ni l’approvisionnement prévu.
- **DAV (disponible à la vente)** –Le DAV correspond à la quantité d’un article qui est disponible et peut être promise à un client à une date spécifique. Le calcul de DAV inclut le stock non engagé, les délais, les réceptions et les sorties prévues.
- **DAV + Marge de sortie** – La date d’expédition correspond à la date DAV plus la marge de sortie de l’article. La marge de sortie est le temps nécessaire pour préparer les articles pour l’expédition.
- **CTP (capable-to-promise)** – La disponibilité est calculée par le biais de l’éclatement. Si vous utilisez l’Optimisation de la planification, la méthode de contrôle de la date de livraison *CTP* n’est pas autorisée et, si elle est sélectionnée, elle entraînera une erreur lors de l’exécution du calcul. Pour plus d’informations sur le paramétrage et l’utilisation de CTP, voir [Calculer les dates de livraison des commandes clients à l’aide de CTP](../master-planning/planning-optimization/calculate-delivery-dates-using-ctp.md).
- **CTP pour l’optimisation de la planification** – Utilisez le calcul CTP fourni par Optimisation de la planification. Cette option n’a aucun effet si vous utilisez le moteur de planification intégré. Pour plus d’informations sur le paramétrage et l’utilisation de CTP, voir [Calculer les dates de livraison des commandes clients à l’aide de CTP](../master-planning/planning-optimization/calculate-delivery-dates-using-ctp.md).

> [!NOTE]
> Lorsqu’une commande client est mise à jour, les informations de promesse de commande ne sont mises à jour que si la date de promesse de commande existante ne peut pas être remplie, comme illustré dans les exemples suivants :
>
> - **Exemple 1** : La date de promesse de la commande actuelle est le 20 juillet, mais en raison de l’augmentation de la quantité, vous ne pourrez pas livrer avant le 25 juillet. Comme la date actuelle ne peut plus être respectée, la promesse de commande est déclenchée.
> - **Exemple 2** : La date de promesse de la commande actuelle est le 20 juillet, mais en raison de baisse de la quantité, il est à présent possible de livrer le 15 juillet. Cependant, comme la date actuelle peut toujours être remplie, la promesse de commande n’est pas déclenchée et le 20 juillet reste la date de promesse de commande.

## <a name="atp-calculations"></a>Calculs DAV

La quantité DAV est calculée en utilisant la méthode « DAV cumulatif avec anticipation ». Le principal avantage de cette méthode de calcul du DAV est qu’elle peut gérer les cas où la somme des sorties entre les réceptions est supérieure à la dernière réception (par exemple lorsqu’une quantité d’une réception précédente doit être utilisée pour respecter une exigence). La méthode de calcul « DAV cumulatif avec anticipation » inclut toutes les sorties jusqu’à ce que la quantité cumulative à recevoir dépasse la quantité cumulative à sortir. Par conséquent, la méthode de calcul DAV évalue si une partie de la quantité d’une période antérieure peut être utilisée pour une période ultérieure.

La quantité DAV est le solde non engagé de stock de la première période. Généralement, elle est calculée pour chaque période pour laquelle une réception est prévue. Le programme calcule la période DAV en jours et la date actuelle comme la première date pour la quantité disponible à la vente. Au cours de cette première période, la quantité disponible à la vente inclut le stock disponible moins les commandes client qui sont dues et en retard.

DAC est calculé à l’aide des formules suivantes :

DAV = DAV pour la période précédente + les réceptions pour la période actuelle – les sorties pour la période actuelle – la quantité nette de sortie pour chaque future période jusqu’à la période au cours de laquelle la somme des réceptions pour toutes les futures périodes, jusqu’à la future période incluse, soit supérieure à la somme des sorties, jusqu’à la future période incluse.

Notez que le calcul de la quantité disponible à la vente (DAV) n’inclut pas les informations relatives à la date d’expiration et au-delà de la plage horaire DAV que le système attend lorsqu’une quantité peut être promise.

Lorsqu’il n’y a plus de sorties ou de réceptions à examiner, la quantité disponible à la vente pour les dates suivantes est la même que la dernière quantité disponible à la vente calculée.

Si toutes les dimensions utilisées pour un article ne sont pas données lorsque la vérification DAV est terminée, elles peuvent toujours être spécifiées sur les sorties et les réceptions. Dans ce cas, dans le calcul de la quantité disponible à la vente, les réceptions et les sorties doivent être regroupées dans les dimensions existantes, afin de réduire le nombre de lignes de réception et de sortie utilisées dans le calcul de la quantité disponible à la vente.

La quantité DAV indiquée est toujours supérieure ou égale à 0 (zéro). Si le calcul renvoie une quantité disponible à la vente négative (par exemple, si la quantité qui a été précédemment promise est supérieure à la quantité disponible), la quantité est définie automatiquement sur 0.

### <a name="example"></a>Exemple

Le champ **Plage de gestion de demande en arrière DAV** contrôle jusqu’où dans le temps la recherche doit remonter pour les commandes de demandes ou les sorties de stock retardées. Le champ **Plage de gestion d’approvisionnement en arrière DAV** contrôle jusqu’où dans le temps la recherche doit remonter pour les commandes d’approvisionnement ou les réceptions de stock retardées. Par exemple, si des commandes qui sont retardées de seulement sept jours doivent être prises en compte dans le calcul DAV, les deux champs doivent être définis à **7**.

Les champs **DAV a retardé le temps de compensation de la demande** et **DAV a retardé le temps de compensation d’approvisionnement** lorsque la demande ou l’approvisionnement retardé seront pris en compte dans le calcul DAV. Par exemple, si l’offre et la demande retardées doivent être prises en compte dans le calcul DAV après-demain, les deux champs doivent être définis sur **2**. Une valeur de **2** signifie que la quantité d’un article sur une commande fournisseur retardée qui doit être prise en compte dans le calcul DAV sera vue comme disponible deux jours après la date actuelle.

Pour l’exemple suivant, la valeur **7** est entrée dans les champs **Plage de gestion de demande en arrière DAV** et **Plage de gestion d’approvisionnement en arrière DAV**, et la valeur **1** est entrée dans les champs **DAV a retardé le temps de compensation de la demande** et **DAV a retardé le temps de compensation d’approvisionnement**.

Une commande fournisseur pour 200 pièces d’un produit qui aurait dû avoir été reçue il y a trois jours n’est pas encore arrivée. Par conséquent, une ligne de commande client pour 75 pièces du même produit qui aurait dû avoir été expédiée la veille n’a pas été expédiée.

Un client appelle et souhaite commander 150 pièces du même produit. Lorsque vous vérifiez la disponibilité du produit, vous constatez qu’une autre commande fournisseur pour 100 pièces du produit sera livrée 10 jours plus tard.

Vous créez une ligne de commande client pour le produit et entrez la valeur **150** pour la quantité.

Étant donné que le contrôle de la date de livraison est DAV, les données DAV sont calculées de sorte à rechercher la date d’expédition la plus proche possible. Selon les paramètres, la commande fournisseur et la commande client retardées sont prises en compte, et la quantité DAV qui en résulte pour la date actuelle est 0. Demain, lorsque la réception de la commande fournisseur retardée est prévue, la quantité DAV est calculée comme supérieure à 0 (dans ce cas, elle est calculée comme étant de 125). Toutefois, dans 10 jours à compter d’aujourd’hui, lorsque la réception de la commande fournisseur supplémentaire pour 100 pièces est prévue, la quantité DAV devient supérieure à 150.

Par conséquent, la date d’expédition est définie sur 10 jours à compter d’aujourd’hui, selon le calcul DAV. Vous devez donc informer le client que la quantité demandée peut être livrée dans 10 jours.

## <a name="ctp-calculations"></a>Calculs CTP

La fonctionnalité CTP vous permet de donner aux clients des dates réalistes auxquelles vous pouvez promettre des marchandises spécifiques. Pour chaque ligne de vente, vous pouvez fournir une date qui tient compte du stock disponible existant, de la capacité de production et des temps de transport.

Le CTP étend la fonctionnalité (ATP) en tenant compte des informations relatives aux capacités. Alors que l’ATP ne prend en compte que la disponibilité des matériaux et suppose des ressources de capacité infinies, le CTP tient compte à la fois la disponibilité des matériaux et de la capacité. Par conséquent, il permet de mieux déterminer si la demande peut être satisfaite dans un délai d’exécution donné.

Le CTP fonctionne de manière légèrement différente, selon le moteur de planification directeur que vous utilisez (Optimisation de la planification ou le moteur intégré). CTP pour Optimisation de la planification ne prend actuellement en charge qu’un sous-ensemble des scénarios CTP pris en charge par le moteur intégré.

Pour plus d’informations sur le paramétrage et l’utilisation de CTP pour chaque moteur, voir [Calculer les dates de livraison des commandes clients à l’aide de CTP](../master-planning/planning-optimization/calculate-delivery-dates-using-ctp.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
