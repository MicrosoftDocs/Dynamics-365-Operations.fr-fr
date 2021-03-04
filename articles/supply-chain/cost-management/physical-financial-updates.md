---
title: Mises à jour physiques et financières
description: Cette rubrique fournit une vue d'ensemble des types de transactions qui augmentent les quantités en stock ou de celles qui les diminuent.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTrans, InventTransVoucher
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 75023
ms.assetid: 128340e1-c573-48e6-b835-6c350d8dd0fb
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ea79bd9c6561c4e4f6fad2c177f44fe62bdea5b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4428074"
---
# <a name="physical-and-financial-updates"></a>Mises à jour physiques et financières

[!include [banner](../includes/banner.md)]

Cette rubrique fournit une vue d'ensemble des types de transactions qui augmentent les quantités en stock ou de celles qui les diminuent. 

Les transactions de stock peuvent être mises à jour physiquement et financièrement dans Dynamics 365 Supply Chain Management. Certains types de transactions physiques et financières augmentent les quantités en stock, tandis que d'autres les diminuent.

## <a name="physical-increases"></a>Augmentations physiques
Lorsqu'une transaction physique est validée, le statut de l'enregistrement de la transaction est **Reçu**. Les transactions suivantes sont considérées comme des augmentations physiques :

-   Réceptions de commande fournisseur
-   Retour de bon de livraison de commande client
-   Déclaration de fin d'ordres de fabrication
-   Sous-produit sur des prélèvements d'ordres de fabrication

## <a name="financial-increases"></a>Augmentations financières
Lorsqu'une transaction de réception financière est validée, le statut de l'enregistrement de la transaction qui augmente la quantité est **Acheté**. Les transactions suivantes sont considérées comme des augmentations financières :

-   Facture fournisseur
-   Facture de commande client pour un retour
-   Évaluation des coûts de l'ordre de fabrication
-   Journaux de stock de quantité positive, tels que mouvement, résultat, inventaire, nomenclatures et transferts

## <a name="transactions-that-increase-quantity"></a>Transactions qui augmentent la quantité
Les transactions qui augmentent la quantité sont validées au prix de revient moyen en vigueur. Le prix de revient moyen calculé en vigueur est basé sur le coût de chacune de ces transactions pour chaque dimension de stock suivie financièrement. Pour plus d'informations sur l'exécution d'un prix de revient moyen, voir [Prix de revient moyen en cours](running-average-cost-price.md).

## <a name="transactions-that-decrease-quantity"></a>Transactions qui diminuent la quantité
Le prix de revient moyen calculé est utilisé lorsqu'une transaction qui diminue la quantité est validée, quel que soit le modèle de stock associé au stock. Cela nécessite que la transaction qui diminue la quantité n'ait pas été marquée par rapport à une autre transaction avant la validation. Si le stock physique disponible devient négatif, le coût du stock défini pour l'article sur la page **Article** est utilisé. 

> [!NOTE]
> Si la fonctionnalité multisite est activée, ce coût sera alors le coût de stock défini pour un site sur la page **Paramètres de commande par défaut**.

## <a name="physical-issues-vs-financial-issues"></a>Comparatif Sorties physiques/Sorties financières
Lorsqu'une transaction de sortie physique est validée, le statut de l'enregistrement de la transaction est **Déduit**. Les transactions suivantes sont considérées comme des sorties physiques :

-   Journaux des prélèvements d'ordres de fabrication
-   Bon de livraison de commande client
-   Retour de bon de livraison de commande fournisseur

Lorsqu'une transaction financière est validée, le statut de l'enregistrement de la transaction est **Vendu**. Les transactions suivantes sont considérées comme des sorties financières :

-   Fin d'un ordre de fabrication
-   Facture de commande client
-   Retour de facture fournisseur
-   Journaux de stock de quantité négative, tels que mouvement, résultat, inventaire, nomenclatures et transferts

Les transactions qui diminuent la quantité sont validées au prix de revient moyen en vigueur. Aussi, la procédure de clôture du stock est requise pour régler les transactions de sorties en transactions de réception sur la base du modèle de stock affecté à chaque article.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]