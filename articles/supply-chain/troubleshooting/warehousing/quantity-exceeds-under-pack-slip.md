---
title: La quantité dépasse le pourcentage de sous-livraison lors de la génération du bon de livraison
description: Lorsque vous générez un bon de livraison, le chargement sortant contient une quantité qui dépasse le pourcentage de sous-livraison.
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
ms.openlocfilehash: ae02846c0ec937ebaff440dc5272a135e16c8aa7355ecc303929e760a54b6627
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760296"
---
# <a name="quantity-exceeds-under-delivery-percentage-during-packing-slip-generation"></a>La quantité dépasse le pourcentage de sous-livraison lors de la génération du bon de livraison

Code d’erreur : SYS24921

## <a name="symptoms"></a>Symptômes

Lorsque vous générez un bon de livraison, le chargement sortant contient une quantité qui dépasse le pourcentage de sous-livraison.

Lorsque vous essayez de générer un bon de livraison, le système affiche le message d’erreur suivant :

> La livraison incomplète de la ligne est de %1 %, mais celle autorisée n’est que de %2 %.

Par conséquent, vous ne pouvez pas générer le bon de livraison pour le chargement.

## <a name="cause"></a>Cause

La quantité prélevée pour le chargement ou l’expédition est inférieure à la quantité commandée et n’est pas comprise dans la plage du pourcentage de sous-livraison.

## <a name="resolution"></a>Résolution

Le chargement ou l’expédition est actuellement dans un état où la génération du bon de livraison échoue. Pour résoudre ce problème, effectuez une ou plusieurs des tâches suivantes :

- Ajuster le pourcentage de sous-livraison.
- Annuler et effectuer des ajustements.

### <a name="adjust-the-under-delivery-percentage"></a>Ajuster le pourcentage de sous-livraison

Suivez la procédure suivante pour ajuster le pourcentage de sous-livraison.

1. Accédez à **Comptabilité client \> Commandes \> Toutes les commandes**.
1. Sélectionnez la commande client pour laquelle vous ne pouvez pas valider un bon de livraison pour le chargement.
1. Sur l’onglet  **Lignes de commande client**, sélectionnez la ligne de commande client de l’article qui dépasse le pourcentage de sous-livraison.
1. Sur l’onglet  **Détails de ligne**, sélectionnez **Livraison**.
1. Définissez le champ **Sous-livraison** sur un pourcentage plus élevé qui tient compte de la quantité prélevée par rapport à la quantité de chargement, afin que la génération du bon de livraison soit possible.

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
