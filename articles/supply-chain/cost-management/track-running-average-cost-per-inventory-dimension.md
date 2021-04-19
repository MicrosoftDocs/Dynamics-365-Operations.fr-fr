---
title: Suivi du coût moyen en vigueur par dimension de stock
description: Un groupe de dimensions de stock est associé à chaque article en stock. Par conséquent, le prix de revient moyen en vigueur d’un article est calculé à partir des dimensions de stock sélectionnées qui sont suivies au niveau financier.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 75053
ms.assetid: 68cc00f4-0f7a-4a7d-be90-8f2e0d0563d3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8da13a01b28ca09ce9c29ecd3a9342dfb9eaa4bd
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834311"
---
# <a name="track-running-average-cost-per-inventory-dimension"></a>Suivi du coût moyen en vigueur par dimension de stock

[!include [banner](../includes/banner.md)]

Un groupe de dimensions de stock est associé à chaque article en stock. Par conséquent, le prix de revient moyen en vigueur d’un article est calculé à partir des dimensions de stock sélectionnées qui sont suivies au niveau financier.

Il existe trois types de dimensions de stock : produit, stockage et suivi. Les dimensions de produit comprennent une configuration, une taille et une couleur. Leur suivi financier est toujours assuré. Les dimensions de stockage et de suivi comprennent un site, un entrepôt, un emplacement, un statut de stock, un contenant, un numéro de lot et un numéro de série. Vous pouvez choisir quelles dimensions de stockage et de suivi sont suivies au niveau financier. 

**Exemple 1** 

Si le groupe de dimensions de stockage associé à l’article est suivi financièrement par entrepôt, le prix moyen actuel est calculé pour chaque entrepôt. Les commandes fournisseur suivantes ont été facturées :

-   Une commande fournisseur comportant deux articles à un prix de revient de 10,00 EUR a été facturée pour l’entrepôt EG.
-   Une commande fournisseur comportant trois articles à un prix de revient de 12,00 EUR a été facturée pour l’entrepôt EG.
-   Une commande fournisseur comportant cinq articles à un prix de revient de 15,00 EUR a été facturée pour l’entrepôt EG.

Le prix de revient moyen en vigueur pour l’entrepôt EG est de 11,20 EUR, et le prix de revient moyen en vigueur pour l’entrepôt EP est de 15,00 EUR. Une facture de commande client est validée pour l’entrepôt EG. La valeur du stock et du coût des marchandises vendues (avant clôture du stock et sans marquage) est de 11,20 EUR. Une autre commande client est validée pour l’entrepôt EP. La valeur du stock et du coût des marchandises vendues (avant clôture du stock et sans marquage) est de 15,00 EUR. 

**Exemple 2** Si le groupe de dimensions de stockage associé à l’article est suivi financièrement par entrepôt, et le groupe de dimensions de suivi est suivi financièrement par numéro de lot, le prix de revient moyen en vigueur est calculé pour chaque lot. 

**Remarque :** nous vous recommandons de toujours afficher le prix de revient pour toutes les dimensions financières suivies actuellement. Les commandes fournisseur suivantes ont été facturées :

-   Une commande fournisseur comportant deux articles à un prix de revient de 10,00 EUR a été facturée pour l’entrepôt EG et le lot AAA.
-   Une commande fournisseur comportant trois articles à un prix de revient de 12,00 EUR a été facturée pour l’entrepôt EG et le lot AAA.
-   Une commande fournisseur comportant deux articles à un prix de revient de 15,00 EUR a été facturée pour l’entrepôt EG et le lot BBB.

Le prix de revient moyen en vigueur pour l’entrepôt EG et le lot AAA est de 11,20 EUR, et le prix de revient moyen en vigueur pour l’entrepôt EP et le lot BBB est de 15,00 EUR.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]