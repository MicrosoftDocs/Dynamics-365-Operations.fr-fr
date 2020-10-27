---
title: Mettre à jour des bons de livraison pour les retours
description: Pour pouvoir recevoir des retours marchandises dans le stock, il faut mettre à jour le bon de livraison relatif à la commande dont les articles font partie.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPackingSlipJournalHistory, SalesParmPackingSlipTrackingInformation
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e7f5bf5adb603d7edb40960b70cb71e25a2f0456
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3983865"
---
# <a name="packing-slip-updates-for-returns"></a>Mettre à jour des bons de livraison pour les retours  

[!include [banner](../includes/banner.md)]


Pour pouvoir recevoir des retours marchandises dans le stock, il faut mettre à jour le bon de livraison relatif à la commande dont les articles font partie. Toute comme le processus de mise à jour de facture consiste à mettre à jour la transaction financière, le processus de mise à jour de bon de livraison consiste à mettre à jour physiquement l'enregistrement de stock, ce qui signifie qu'il valide les modifications apportées au stock. En cas de retour, les opérations affectées à l'action de disposition sont exécutées durant la mise à jour du bon de livraison.

Il est possible de traiter la mise à jour du bon de livraison dans le journal des arrivées d'articles ou l'ordre de retour.

Dans le cadre du traitement de validation des bons de livraison, il est possible d'associer le numéro de référence du bon de livraison figurant sur les documents d'expédition du client aux lignes de commande. Cette association est purement indicative. Elle n'entraîne pas de mises à jour de transactions.

Si les retours marchandises ne sont pas tous arrivés, incluez uniquement la quantité reçue dans la mise à jour du bon de livraison. Laissez les autres articles sur la commande jusqu'à ce que le reste de l'expédition de retour arrive.

Si un article est retourné par le contrôle au département d'expédition et de réception, par exemple, si le contrôleur ne sait pas où placer l'article dans le stock, il convient de mettre à jour le bon de livraison correspondant pour enregistrer et traiter correctement le code disposition spécifié comme résultat du contrôle.

Lorsque vous mettez à jour un bon de livraison pour un article retourné dans le cadre d'un contrat de vente, l'engagement de contrat de vente pour cet article est automatiquement mis à jour pour refléter les modifications de quantité ou de montant. 

## <a name="see-also"></a>Voir également :

[Exécution de mises à jour de factures pour les retours](perform-invoice-updates-for-returns.md)

  


