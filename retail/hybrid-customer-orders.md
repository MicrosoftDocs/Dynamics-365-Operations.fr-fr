---
title: Commandes client hybrides
description: "Une commande client hybride est une commande unique, qui contient les produits qui peuvent être exécutés hors du magasin par le client, ainsi que les produits qui sont prélevés ou expédiés par la suite."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Operations, Core, UnifiedOperations
ms.custom: 261164
ms.assetid: 9d99a5b9-4662-499a-bece-3ea1d6092934
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 52a16be4b07eafb493c7fd7ad52a6d9d1bb9ee89
ms.openlocfilehash: e748c6fb788f4ec00ab2a0ef62e139a6180089be
ms.contentlocale: fr-fr
ms.lasthandoff: 06/20/2017

---

# <a name="hybrid-customer-orders"></a>Commandes client hybrides

[!include[banner](includes/banner.md)]


Une commande client hybride est une commande unique, qui contient les produits qui peuvent être exécutés hors du magasin par le client, ainsi que les produits qui sont prélevés ou expédiés par la suite.

Dans Microsoft Dynamics 365 for Retail, vous pouvez choisir d'exécuter tous les produits ou des produits sélectionnés pour une commande client. Les lignes de produit marquées comme exécutées sont automatiquement facturées après la création de la commande, de la même façon que pour une commande qui doit être traitée une fois la commande créée. Le montant dû sur les commandes hybrides est déterminé en ajoutant le pourcentage de dépôt lors du traitement et de l'expédition des lignes de produits avec le montant total des lignes d'exécution. Pour les commandes hybrides, le système bascule entre le mode de commande client et le mode paiement comptant sans livraison comme suit :

-   Si tous les produits du chariot sont définis sur **Exécuter le mode de livraison**, la commande sera gérée comme une transaction avec paiement comptant sans livraison.
-   Si tout ou partie des lignes du chariot sont définies sur **Prélever** ou **Expédier la livraison**, la commande sera gérée comme une transaction de commande client.

Si une ligne de chariot est sélectionnée et que l'option **Prélever la sélection**, **Expédition sélectionnée** ou **Exécuter la sélection** est sélectionnée, seule la ligne de chariot spécifique est définie avec ce mode de livraison. Dans ce cas, le flux en aval de l'opération continue normalement. Toutefois, si l'option **Prélever la sélection**, **Expédition sélectionnée** ou **Exécuter la sélection** est sélectionnée sans ligne de chariot sélectionnée, une nouvelle page s'ouvre qui répertorie toutes les lignes de chariot. Dans cet écran, vous pouvez sélectionner plusieurs lignes en une seule fois pour définir le mode de livraison. Lorsque vous utilisez cette méthode pour sélectionner les lignes, le mode de livraison précédent affecté à la ligne sera remplacé.

<a name="see-also"></a>Voir également :
--------

[Vue d'ensemble des commandes client](customer-orders-overview.md)




