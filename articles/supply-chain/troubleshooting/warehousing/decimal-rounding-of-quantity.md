---
title: L’arrondi décimal de la quantité physique de mise à jour est incorrect
description: Lorsque vous générez un bon de livraison, le chargement sortant contient une quantité qui ne correspond pas à la précision décimale définie dans l’unité.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningListPage_WHSSalesPackingSlipPost, WHSLoadTable_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1e63440834f516879aa8ad711bd789e62b0ee993
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/14/2021
ms.locfileid: "6248781"
---
# <a name="decimal-rounding-of-the-physical-updating-quantity-is-incorrect"></a>L’arrondi décimal de la quantité physique de mise à jour est incorrect

Code d’erreur : SYS19589

## <a name="symptoms"></a>Symptômes

Lorsque vous générez un bon de livraison, le chargement sortant contient une quantité qui ne correspond pas à la précision décimale définie dans l’unité.

Lorsque vous essayez de générer un bon de livraison, le système affiche le message d’erreur suivant :

> L’arrondi décimal de la quantité de mise à jour physique de l’unité %1 est incorrect.

Par conséquent, vous ne pouvez pas générer le bon de livraison pour le chargement.

## <a name="cause"></a>Cause

Le système évalue si l’arrondi décimal de la quantité d’expédition correspond à la précision décimale définie pour l’unité d’expédition. Lorsque le système arrondit la quantité d’expédition au nombre de décimales spécifié, s’il constate que la quantité d’expédition arrondie ne correspond pas à la quantité d’expédition réelle, vous ne pouvez pas générer le bon de livraison. Par exemple, ce problème peut se produire si la quantité vendue est de 1,75 kilogramme (kg), mais que la précision décimale est définie sur *1*.

## <a name="resolution"></a>Résolution

Le chargement ou l’expédition est actuellement dans un état où la génération du bon de livraison échoue. Pour résoudre ce problème, effectuez une ou plusieurs des tâches suivantes :

- Passez en revue vos lignes de chargement et effectuez des ajustements pour vous assurer que la quantité peut être convertie proprement sans problème de décimales ou autre problème d’arrondi.
- Examiner vos lignes de chargement et effectuer des ajustements pour vous assurer que l’unité et la quantité sont conformes à la précision décimale de l’unité.

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-decimal-numbers-and-any-other-rounding-issues"></a>Passer en revue vos lignes de chargement et effectuer des ajustements pour vous assurer que la quantité peut être convertie proprement sans problème de décimales ou autre problème d’arrondi

Suivez la procédure suivante pour passer en revue vos lignes de chargement et effectuer des ajustements pour vous assurer que la quantité peut être convertie proprement sans problème de décimales ou autre problème d’arrondi.

1. Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.
1. Sélectionnez le chargement pour lequel le bon de livraison ne peut pas être généré.
1. Dans le volet Actions, dans l’onglet  **Expédier et recevoir**, dans le groupe  **Annuler**, sélectionnez  **Annuler la confirmation de livraison**.
1. Sur l’onglet  **Lignes de chargement**, sélectionnez la ligne de chargement de l’article qui cause le problème.
1. Sélectionnez **Réduire la quantité prélevée** pour ajuster la quantité prélevée.
1. Sur l’onglet  **Détails de ligne**, sélectionnez **Commande**.
1. Définissez le champ **Quantité** sur la quantité prélevée (c’est-à-dire sur la valeur du champ **Quantité créée par le travail**), afin que la génération du bon de livraison soit possible.

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-unit-and-quantity-are-aligned-with-the-decimal-precision-of-the-unit"></a>Examiner vos lignes de chargement et effectuer des ajustements pour vous assurer que l’unité et la quantité sont conformes à la précision décimale de l’unité

Procédez comme suit pour examiner vos lignes de chargement et effectuer des ajustements pour vous assurer que l’unité et la quantité sont conformes à la précision décimale de l’unité.

1. Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.
1. Sélectionnez le chargement pour lequel le bon de livraison ne peut pas être généré.
1. Dans le raccourci **Lignes de chargement**, sélectionnez la ligne de chargement de l’article qui cause le problème. Notez la valeur des champs **Quantité** et **Unité**.
1. Accédez à **Administration d’organisation \> Unités \> Unités**.
1. Sélectionnez l’unité pour laquelle le bon de livraison ne peut pas être généré.
1. Ajustez la valeur du champ **Précision décimale** selon les besoins.
