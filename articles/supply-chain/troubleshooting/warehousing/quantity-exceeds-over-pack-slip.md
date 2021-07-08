---
title: La quantité dépasse le pourcentage de livraison excédentaire lors de la génération du bon de livraison
description: Lorsque vous générez un bon de livraison, le chargement sortant contient une quantité qui dépasse le pourcentage de livraison excédentaire.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSSalesPackingSlipPost,WHSLoadPlanningListPage_WHSSalesPackingSlipPost,WHSLoadPlanningWorkbench_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1106322cc3772c1b671b7fa82fb74039c028ba35
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249100"
---
# <a name="quantity-exceeds-over-delivery-percentage-during-packing-slip-generation"></a>La quantité dépasse le pourcentage de livraison excédentaire lors de la génération du bon de livraison

Code d’erreur : SYS24920

## <a name="symptoms"></a>Symptômes

Lorsque vous générez un bon de livraison, le chargement sortant contient une quantité qui dépasse le pourcentage de livraison excédentaire.

Lorsque vous essayez de générer un bon de livraison, le système affiche le message d’erreur suivant :

> La livraison excessive de la ligne est de %1 %, mais celle autorisée n’est que de %2 %.

Par conséquent, vous ne pouvez pas générer le bon de livraison pour le chargement.

## <a name="cause"></a>Cause

La quantité prélevée pour le chargement ou l’expédition est supérieure à la quantité commandée et n’est pas comprise dans la plage du pourcentage de livraison excédentaire.

## <a name="resolution"></a>Résolution

Le chargement ou l’expédition est actuellement dans un état où la génération du bon de livraison échoue. Pour résoudre ce problème, effectuez une ou plusieurs des tâches suivantes :

- Ajustez la quantité de la ligne de chargement.
- Ajustez le pourcentage de livraison excédentaire.
- Annuler et effectuer des ajustements.

### <a name="adjust-the-load-line-quantity"></a>Ajuster la quantité de la ligne de chargement

Suivez la procédure suivante pour ajuster la quantité de la ligne de chargement.

1. Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.
1. Sélectionnez le chargement pour lequel le bon de livraison ne peut pas être généré.
1. Dans le volet Actions, dans l’onglet  **Expédier et recevoir**, dans le groupe  **Annuler**, sélectionnez  **Annuler la confirmation de livraison**.
1. Sur l’onglet  **Lignes de chargement**, sélectionnez la ligne de chargement de l’article qui dépasse le pourcentage de livraison excédentaire.
1. Sélectionnez **Réduire la quantité prélevée** pour ajuster la quantité prélevée.
1. Sur l’onglet  **Détails de ligne**, sélectionnez **Commande**.
1. Définissez le champ **Quantité** sur la quantité prélevée (c’est-à-dire sur la valeur du champ **Quantité créée par le travail**), afin que la génération du bon de livraison soit possible.

### <a name="adjust-the-over-delivery-percentage"></a>Ajuster le pourcentage de livraison excédentaire

Suivez la procédure suivante pour ajuster le pourcentage de livraison excédentaire.

1. Accédez à **Comptabilité client \> Commandes \> Toutes les commandes**.
1. Sélectionnez la commande client pour laquelle vous ne pouvez pas valider un bon de livraison pour le chargement.
1. Sur l’onglet  **Lignes de commande client**, sélectionnez la ligne de commande client de l’article qui dépasse le pourcentage de livraison excédentaire.
1. Sur l’onglet  **Détails de ligne**, sélectionnez **Livraison**.
1. Définissez le champ **Livraison excédentaire** sur un pourcentage plus élevé qui tient compte de la quantité prélevée par rapport à la quantité de chargement, afin que la génération du bon de livraison soit possible.

### <a name="reverse-and-make-adjustments"></a>Annuler et effectuer des ajustements

Annulez tout ce qui a été validé pour le chargement (par exemple, le bon de livraison, la confirmation d’expédition et le travail), effectuez des ajustements de la commande client, relancez la commande vers l’entrepôt et terminez la procédure d’expédition.

Utilisez la procédure suivante pour annuler un bon de livraison.

1. Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.
1. Dans le volet Actions, dans l’onglet  **Expédier et recevoir**, dans le groupe  **Annuler**, sélectionnez  **Annuler les bons de livraison**.

Utilisez la procédure suivante pour annuler une confirmation d’expédition.

1. Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.
1. Dans le volet Actions, dans l’onglet  **Expédier et recevoir**, dans le groupe  **Annuler**, sélectionnez  **Annuler la confirmation de livraison**.

Utilisez la procédure suivante pour annuler le travail.

1. Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.
1. Dans le volet Actions, sous l’onglet  **Chargements**, dans le groupe  **Travail**, sélectionnez  **Annuler le travail**.
