---
title: "Écritures de coût"
description: "Cet article fournit des informations sur les entrées de coût et à quel moment elles sont créées. Une entrée de coût est un enregistrement qui enregistre la quantité et le coût d'un événement donné."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19131
ms.assetid: dd2663d8-bcc0-47b1-b36d-57433143487c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 8df830b54d578ed9be4f34c8f52986aca16dc5dc
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="cost-entries"></a>Écritures de coût

[!include[banner](../includes/banner.md)]


Cet article fournit des informations sur les entrées de coût et à quel moment elles sont créées. Une entrée de coût est un enregistrement qui enregistre la quantité et le coût d'un événement donné.

Les entrées de coût sont des agrégations des mouvements de stock qui sont enregistrés sur les dimensions de stock financier actives.

## <a name="examples"></a>Exemples
### <a name="example-1-no-cost-entries-are-created"></a>Exemple 1 : aucune écriture de coût n'est créée

Un événement de journal de transfert est enregistré. L'événement transfère une pièce de l'article A de l'emplacement A à l'emplacement B. La dimension de stock d'emplacement n'est pas prise en considération dans l'objet de coût. Par conséquent, l'événement crée deux mouvements de stock et aucune écriture de coût.

### <a name="example-2-cost-entries-are-created"></a>Exemple 2 : des écritures de coût sont créées

Un événement de journal de transfert est enregistré. L'événement transfère une pièce de l'article A du site 1 au site 2. La dimension de stock de site est prise en considération dans l'objet de coût. Par conséquent, l'événement crée deux mouvements de stock et deux écritures de coût.

### <a name="example-3-one-cost-entry-is-created"></a>Exemple 3 : une écriture de coût est créée

Un événement d'accusé de réception de marchandises est enregistré pour une commande fournisseur. L'événement enregistre 100 pièces de l'article A à un coût unitaire de 10.00 dollars américain (USD). Étant donné que l'article A utilise un numéro de série aux fins du suivi de la Gestion des stocks, un numéro de série unique est créé pour chaque article reçu. Par conséquent, l'événement crée 100 mouvements de stock et une écriture de coût.

## <a name="cost-entries-page"></a>Page des écritures de coût
La nouvelle page **Écritures de coût** permet d'afficher et contrôler les enregistrements des quantités et des coûts. Cette page complète les pâges**Mouvement de stock** et **Lettrage de stock**. Les enregistrements sont enregistrés dans l'ordre chronologique pour un événement. Par conséquent, vous pouvez rapidement trouver et contrôler les coûts cumulés d'un événement spécifique ou de tous les événements liés à un document. Voici un exemple :

-   Un événement d'accusé de réception de marchandises est enregistré pour l'article A. Cent pièces sont reçues à un coût unitaire de 10,00 USD chacune.
-   Quelques jours après que l'événement de facture a été enregistré, le coût grimpe à 11,00 USD. Par conséquent, le montant total est de 1 100 €. Un deuxième N° document est créé pour expliquer la différence de 100 USD.
-   Quelques jours plus tard, les frais divers de 15,00 USD pour couvrir le coût du transport sont enregistrés sur la commande fournisseur.

| Pièce justificative | date ;       | Référence      | Nombre | N° de traitement  | Quantité | Montant  |
|---------|------------|----------------|--------|---------|---------------|----|
| 00001   | 01-01-2015 | Commande fournisseur | 100001 | 0000101 | 100,00   | 1 000,00 |
| 00002   | 20-01-2015 | Commande fournisseur | 100001 | 0000101 |          | 100,00  |
| 00003   | 31-01-2015 | Ajustement     | 100001 | 0000101 |          | 15,00   |

La page **Écritures de coût** active le filtrage par ID et date de document. 

> [!NOTE]
> Ls écritures de coût sont disponibles uniquement pour les [objets de coût](cost-object.md) ou les produits lancés.

<a name="see-also"></a>Voir également :
--------

[Objets de coût](cost-object.md)




