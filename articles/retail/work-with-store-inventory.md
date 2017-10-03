---
title: "Gérer le stock de magasin"
description: "Cet article décrit les types de documents qui peuvent être utilisés pour gérer le stock."
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 42091a5ec94bae3015fd9afca3ddcf1ef24f6eb4
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---

# <a name="manage-store-inventory"></a>Gérer le stock de magasin

[!include[banner](includes/banner.md)]


Cet article décrit les types de documents qui peuvent être utilisés pour gérer le stock.

Les types de documents suivants peuvent être utilisés pour gérer le stock de votre organisation.

## <a name="purchase-orders"></a>Commandes fournisseur
Les commandes fournisseur sont créées au siège social. Si un entrepôt de détail est indiqué dans l'en-tête de la commande fournisseur, la commande peut être reçue au magasin à l'aide de Modern POS (MPOS) ou de Cloud POS dans Microsoft Dynamics 365 for Retail. Une fois entrées, les quantités reçues au magasin peuvent être sauvegardées localement pour des modifications ultérieures. Les quantités peuvent aussi être validées et envoyées au siège social. Au siège social, les quantités qui ont été reçues au magasin sont affichées dans Dynamics 365 for Retail, dans le champ **Recevoir maintenant** de la commande fournisseur.

## <a name="transfer-orders"></a>Ordres de transfert
Un ordre de transfert peut spécifier qu'un magasin particulier est un emplacement à partir duquel les articles peuvent être expédiés. Dans ce cas, l'ordre de transfert s'affiche au magasin comme une requête de prélèvement dans MPOS ou Cloud POS. Après avoir été prélevées, les quantités demandées sont validées et envoyées au siège social. Au siège social, les quantités qui ont été prélevées au magasin sont affichées dans Microsoft Dynamics 365 for Retail, dans le champ **Expédier maintenant** de l'ordre de transfert. Un ordre de transfert peut spécifier qu'un magasin particulier est un emplacement vers lequel les articles peuvent être expédiés. Dans ce cas, l'ordre de transfert s'affiche au magasin comme une requête de réception dans MPOS ou Cloud POS. Une fois entrées, les quantités reçues au magasin peuvent être sauvegardées localement pour des modifications ultérieures. Les quantités peuvent aussi être validées et envoyées au siège social. Au siège social, les quantités qui ont été reçues au magasin sont affichées dans Dynamics 365 for Retail, dans le champ **Recevoir maintenant** de l'ordre de transfert.

## <a name="stock-counts"></a>Inventaires
Les inventaires peuvent être planifiés ou non planifiés. Les inventaires planifiés sont engagés par le siège social, qui spécifie les articles à inventorier. Le siège social crée un document d'inventaire qui peut être reçu au magasin, où les quantités du stock réel et disponible sont entrées dans MPOS ou Cloud POS. Les inventaires non planifiés sont effectués dans un magasin et les quantités de stock disponible réelles sont mises à jour dans MPOS ou Cloud POS. Contrairement aux inventaires planifiés, les inventaires non planifiés n'ont pas de liste prédéfinie d'articles. Lorsqu'un inventaire de l'un ou l'autre type est terminé, il est validé et envoyé au siège social. Au siège social, le nombre est contrôlé et validé.

## <a name="inventory-lookup"></a>Recherche de stock
La quantité actuelle disponible de produits pour plusieurs magasins et entrepôts peut être affichée dans la page Recherche de stock. En plus de la quantité actuelle disponible, les futures quantités disponibles à la vente peuvent être affichées pour chaque magasin individuel. Pour ce faire, sélectionnez le magasin dont vous souhaitez afficher les quantités disponibles à la vente, puis cliquez sur **Afficher la disponibilité du magasin**.




