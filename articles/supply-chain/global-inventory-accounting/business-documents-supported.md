---
title: Documents commerciaux pris en charge par la comptabilité globale des stocks
description: Cette rubrique répertorie les documents commerciaux pris en charge par la comptabilité globale des stocks. Elle fournit également un exemple détaillé de documents de commande fournisseur.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 311c894d709985d0d053b0ec3a317142aa582c39
ms.sourcegitcommit: eceae470f4ae58000ec33fea34db34b7a7a1af43
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/18/2021
ms.locfileid: "6273157"
---
# <a name="business-documents-supported-by-global-inventory-accounting"></a>Documents commerciaux pris en charge par la comptabilité globale des stocks

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Une fois que le complément Comptabilité globale des stocks est entièrement configuré, il est prêt à traiter les documents liés aux stocks qui sont saisis dans Microsoft Dynamics 365 Supply Chain Management.

## <a name="supported-business-documents"></a>Documents commerciaux pris en charge

Il existe deux types de documents commerciaux :

- **Documents ayant un journal** : ces documents comprennent le reçu de produit, la facture d’achat, le bon de livraison et les documents de facture de vente.
- **Documents n’ayant pas de journal** : ces documents comprennent les documents de comptage, de mouvement et d’ajustement des stocks.

Plus loin dans cette rubrique, nous utiliserons des commandes fournisseur pour illustrer le processus.

Le tableau suivant répertorie les documents pris en charge par la version actuelle.

| Type de document      | Document        |
|--------------------|-----------------|
| Commande fournisseur     | Accusé de réception de marchandises |
| Commande fournisseur     | Facture         |
| Commande client        | Bon de livraison    |
| Commande client        | Facture         |
| Journaux de stock | Mouvement        |
| Journaux de stock | Ajustement      |
| Journaux de stock | Comptage        |
| Journaux de stock | Transférer        |
| Ordre de transfert     | Expédition        |
| Ordre de transfert     | Recevoir         |

> [!IMPORTANT]
> La comptabilité globale des stocks traite de manière asynchrone les documents saisis dans Supply Chain Management. Aucun message d’erreur ne s’affichera pour les documents problématiques.

## <a name="example-purchase-order"></a>Exemple : commandes fournisseur

### <a name="product-receipt"></a>Réception des produits

Validez les reçus de produits de la manière habituelle. Sur la page **Toutes les commandes fournisseur**, sélectionnez une commande fournisseur puis, dans le volet Actions, sur l’onglet **Recevoir**, sélectionnez **Accusé de réception des produits** pour ouvrir la page **Journal des réceptions de produits**. Un événement d’opération et un événement de comptabilité globale des stocks sont générés pour chaque ligne. Par conséquent, sélectionnez l’onglet **Lignes**, puis sélectionnez **Stock \> Événements et mesures** pour ouvrir la page **Événements et mesures**.

La comptabilité globale des stocks est un système comptable basé sur des événements et des mesures. La grille des lignes de mesure sur la page **Événements et mesures** affiche une liste de mesures. Chaque mesure comporte une liste de dimensions.

Pour chaque événement d’opération, il existe deux types de mesure :

- **Mesures des opérations** : ces mesures décrivent les documents commerciaux en termes génériques. Une mesure est la quantité de produit utilisant l’unité de mesure utilisée dans le document. Il existe également des mesures qui affectent la valeur du stock, telles que le prix global, la remise, le pourcentage de remise et les frais de ligne.
- **Mesures comptables des ressources** : ces mesures sont du point de vue du registre de stock. Elles décrivent l’impact du document sur le stocke dans l’unité de mesure du stock. S’il existe plusieurs inscriptions de stock, il existe plusieurs lignes de mesures comptables des ressources.

Les dimensions sont organisées de la manière suivante :

- **Dualité** : la dualité décrit les agents qui participent aux événements économiques. Pour les documents commerciaux externes, les dimensions principales décrivent l’entité juridique dans laquelle le document est saisi, tandis que les dimensions doubles décrivent le fournisseur, le client, etc. Pour les documents commerciaux internes (par exemple, les ordres de transfert), les dimensions doubles décrivent l’entrepôt de contrepartie.
- **Type de dimension** : les types de dimension catégorisent les dimensions.
- **Dimension** : nom de la dimension.
- **Valeur de dimension** : valeur de la dimension.

### <a name="global-inventory-accounting-event"></a>Événement de comptabilité global des stocks

La comptabilité globale des stocks prend en entrée les événements opérationnels et les mesures. Elle effectue ensuite la comptabilité appropriée pour chaque registre associé, en fonction de la devise et de la convention associées. Vous pouvez sélectionner **Événements et mesures de la comptabilité globale des stocks** pour afficher l’événement de comptabilité globale des stocks. L’événement de comptabilité globale des stocks suit la même méthodologie que les événements d’opération, mais utilise des mesures différentes. Il existe trois principaux types de mesure : la quantité du coût du produit, le coût du produit et la variance.

Les comptes auxiliaires sont utilisés pour classer davantage les mesures. Il peut exister plusieurs registres. Ces registres sont liés à l’entité juridique dans laquelle le document est saisi. Vous pouvez afficher les événements et les mesures pour chaque registre en modifiant la valeur du champ **Registre**.

### <a name="cost-element"></a>Élément de coût

Sur la base de la politique d’élément de coût qui est attachée au registre, le système affecte un élément de coût à chaque mesure d’événement d’opération comptabilisée qui affecte le coût du stock. Ces mesures incluent le prix global, la remise, le pourcentage de remise et les frais de ligne.

### <a name="measurement-line-details"></a>Détails de la ligne de mesure

L’onglet **Vue d’ensemble** affiche les détails des politiques jointes. Les dimensions de l’objet de coût affichent l’objet de coût, en fonction de la politique d’objet de coût. Les dimensions d’identification spécifiques indiquent le numéro de lot si l’hypothèse du flux des coûts est *Spécifique – Lot*.

### <a name="purchase-invoice"></a>Facture d’achat

Validez la facture de la manière habituelle. Ensuite, dans le volet Actions, sur l’onglet **Facture**, dans le groupe **Journaux**, sélectionnez **Facture** pour ouvrir le journal des factures. Un événement d’opération et un événement de comptabilité globale des stocks sont générés pour chaque ligne. Par conséquent, sélectionnez l’onglet **Lignes**, puis sélectionnez **Stock \> Événements et mesures** pour ouvrir la page **Événements et mesures**. La page **Événements et mesures** affiche le même type de mesure. Cependant, étant donné que la page affiche un rôle de mesure et un modificateur de mesure différents, l’impact sur l’agent (entité juridique) diffère.

Sélectionnez **Événements et mesures de la comptabilité globale des stocks** pour afficher l’événement de comptabilité globale des stocks. La quantité de stock et le coût sortent maintenant du compte auxiliaire *Marchandises reçues stock non facturé* et entrent dans le compte auxiliaire *Coût des marchandises achetées*.
