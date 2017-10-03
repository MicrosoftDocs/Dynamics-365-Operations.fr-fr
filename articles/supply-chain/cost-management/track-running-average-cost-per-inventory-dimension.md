---
title: "Suivi du coût moyen en vigueur par dimension de stock"
description: "Un groupe de dimensions de stock est associé à chaque article en stock. Par conséquent, le prix de revient moyen en vigueur d'un article est calculé à partir des dimensions de stock sélectionnées qui sont suivies au niveau financier."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventOnhandItem
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 75053
ms.assetid: 68cc00f4-0f7a-4a7d-be90-8f2e0d0563d3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 4f5ca047835fcbb2567f0b97347b356e1b594980
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017

---

# <a name="tracking-running-average-cost-per-inventory-dimension"></a>Suivi du coût moyen en vigueur par dimension de stock

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


Un groupe de dimensions de stock est associé à chaque article en stock. Par conséquent, le prix de revient moyen en vigueur d'un article est calculé à partir des dimensions de stock sélectionnées qui sont suivies au niveau financier.

Il existe trois types de dimensions de stock : produit, stockage et suivi. Les dimensions de produit comprennent une configuration, une taille et une couleur. Leur suivi financier est toujours assuré. Les dimensions de stockage et de suivi comprennent un site, un entrepôt, un emplacement, un statut de stock, un contenant, un numéro de lot et un numéro de série. Vous pouvez choisir quelles dimensions de stockage et de suivi sont suivies au niveau financier. 

**Exemple 1** 

Si le groupe de dimensions de stockage associé à l'article est suivi financièrement par entrepôt, le prix moyen actuel est calculé pour chaque entrepôt. Les commandes fournisseur suivantes ont été facturées :

-   Une commande fournisseur comportant deux articles à un prix de revient de 10,00 EUR a été facturée pour l'entrepôt EG.
-   Une commande fournisseur comportant trois articles à un prix de revient de 12,00 EUR a été facturée pour l'entrepôt EG.
-   Une commande fournisseur comportant cinq articles à un prix de revient de 15,00 EUR a été facturée pour l'entrepôt EG.

Le prix de revient moyen en vigueur pour l'entrepôt EG est de 11,20 EUR, et le prix de revient moyen en vigueur pour l'entrepôt EP est de 15,00 EUR. Une facture de commande client est validée pour l'entrepôt EG. La valeur du stock et du coût des marchandises vendues (avant clôture du stock et sans marquage) est de 11,20 EUR. Une autre commande client est validée pour l'entrepôt EP. La valeur du stock et du coût des marchandises vendues (avant clôture du stock et sans marquage) est de 15,00 EUR. 

**Exemple 2** Si le groupe de dimensions de stockage associé à l'article est suivi financièrement par entrepôt, et le groupe de dimensions de suivi est suivi financièrement par numéro de lot, le prix de revient moyen en vigueur est calculé pour chaque lot. 

**Remarque :** nous vous recommandons de toujours afficher le prix de revient pour toutes les dimensions financières suivies actuellement. Les commandes fournisseur suivantes ont été facturées :

-   Une commande fournisseur comportant deux articles à un prix de revient de 10,00 EUR a été facturée pour l'entrepôt EG et le lot AAA.
-   Une commande fournisseur comportant trois articles à un prix de revient de 12,00 EUR a été facturée pour l'entrepôt EG et le lot AAA.
-   Une commande fournisseur comportant deux articles à un prix de revient de 15,00 EUR a été facturée pour l'entrepôt EG et le lot BBB.

Le prix de revient moyen en vigueur pour l'entrepôt EG et le lot AAA est de 11,20 EUR, et le prix de revient moyen en vigueur pour l'entrepôt EP et le lot BBB est de 15,00 EUR.



