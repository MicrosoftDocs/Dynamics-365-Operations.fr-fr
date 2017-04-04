---
title: Commandes client hybrides
description: "Une commande client hybride est un ordre unique, qui contient les produits qui peuvent être exécutés du magasin pour le client, ainsi que les produits qui sont prélevés ou ultérieurement expédiés."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261164
ms.assetid: 9d99a5b9-4662-499a-bece-3ea1d6092934
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 1ddfc050cef94f4a31f5858b84c89eadfa726b95
ms.lasthandoff: 03/31/2017


---

# <a name="hybrid-customer-orders"></a>Commandes client hybrides

Une commande client hybride est un ordre unique, qui contient les produits qui peuvent être exécutés du magasin pour le client, ainsi que les produits qui sont prélevés ou ultérieurement expédiés.

Dans Microsoft Dynamics 365 pour les opérations - au détail, vous pouvez sélectionner effectuez tous les produits ou d'effectuer des produits sélectionnés pour une commande client. Les lignes de produit marquées comme effectuent sont automatiquement validées après l'ordre créé, de la même façon qu'il est identique pour une commande qui doit être ramassé une fois l'ordre créé. Le montant dû sur les ordres hybrides est déterminé en ajoutant le pourcentage de dépôt prélèvement en fonction et les lignes de produits d'expédition et le montant total des lignes de mise en œuvre. Pour les ordres hybrides, le système passe du mode de commande client et le mode de paiement comptant sans livraison comme suit :

-   Si tous les produits du chariot sont définis ** effectuez la livraison **, l'ordre est géré comme transaction cash-and-carry.
-   Si tout ou partie des lignes dans le chariot sont définies sur ou ** prélevez ** ou ** la livraison d'expédition **, l'ordre est géré comme transaction de commande client.

Si une ligne de chariot est activée et ** Pick sélectionné **, ** l'expédition est sélectionné **, ou ** Carry out sélectionnée ** est sélectionné, seule la ligne spécifique de chariot est définie avec ce mode de livraison. Dans ce cas, le flux en aval de l'opération continue normalement. Toutefois, si ** Pick a sélectionné **, ** l'expédition est sélectionné **, ou ** Carry out sélectionnée ** est sélectionné sans ligne de chariot est activée, une nouvelle page s'ouvre qui répertorie toutes les lignes de chariot. Dans cet écran, vous pouvez sélectionner plusieurs lignes immédiatement pour définir le mode de livraison. Lorsque vous utilisez cette méthode pour sélectionner les lignes, tout mode de livraison précédent affecté à la ligne sera remplacé.

<a name="see-also"></a>Voir également :
--------

[Vue d'ensemble des commandes client] (customer-orders-overview.md)


