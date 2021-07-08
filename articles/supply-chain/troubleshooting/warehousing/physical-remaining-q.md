---
title: La quantité physique restante dans l’unité ne doit pas être nulle
description: Lorsque vous générez un bon de livraison, les données qui lui sont fournies ont une quantité de stock non nulle mais une quantité de vente nulle.
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
ms.openlocfilehash: bfd381160bcfd1e6e5489e16cc22178b8a5142ee
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/14/2021
ms.locfileid: "6248780"
---
# <a name="physical-remaining-quantity-in-the-unit-must-not-be-zero"></a>La quantité physique restante dans l’unité ne doit pas être nulle

Code d’erreur : SYS19591

## <a name="symptoms"></a>Symptômes

Lorsque vous générez un bon de livraison, les données qui lui sont fournies ont une quantité de stock non nulle mais une quantité de vente nulle.

Lorsque vous essayez de générer le bon de livraison, le système affiche le message d’erreur suivant :

> La quantité physique restante dans l’unité %1 doit être différente de zéro.

Par conséquent, vous ne pouvez pas générer le bon de livraison pour le chargement.

## <a name="cause"></a>Cause

Le système évalue la quantité physique restante dans l’unité de stock et la quantité physique restante dans l’unité d’expédition. Si le système constate que la quantité physique restante dans l’unité d’expédition est 0 (zéro), mais que la quantité physique restante dans l’unité de stock n’est pas 0, vous ne pouvez pas générer le bon de livraison. Par exemple, ce problème peut se produire si l’unité de vente et l’unité de stock de l’article sont différentes, et que la conversion entre les unités n’est pas précise.

## <a name="resolution"></a>Résolution

Le chargement ou l’expédition est actuellement dans un état où la génération du bon de livraison échoue. Pour résoudre ce problème, effectuez une ou plusieurs des tâches suivantes :

- Examiner vos lignes de chargement et vous assurer que tous les travaux connexes ont été effectués à l’emplacement d’expédition finale et que les quantités correspondent.
- Examiner vos lignes de chargement et effectuer des ajustements pour vous assurer que la quantité peut être convertie proprement sans problème d’arrondi.
- Examiner vos lignes de chargement et effectuer des ajustements pour vous assurer que l’unité et la quantité sont conformes à la précision décimale de l’unité.
- Vous assurer que l’unité de mesure du stock est inférieure à l’unité de mesure de vente.

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Examiner vos lignes de chargement et vous assurer que tous les travaux connexes ont été effectués à l’emplacement d’expédition finale et que les quantités correspondent

Procédez comme suit pour examiner vos lignes de chargement et vous assurer que tous les travaux connexes ont été effectués à l’emplacement d’expédition finale et que les quantités correspondent.

1. Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.
1. Sélectionnez le chargement pour lequel l’expédition ne peut pas être confirmée.
1. Dans l’organisateur **Lignes de chargement**, sélectionnez la ligne de chargement.
1. Notez la valeur du champ **Quantité créée**.
1. Dans le volet Actions, sous l’onglet **Chargements**, dans le groupe **Informations associées**, cliquez sur **Travail**.
1. Vérifiez que le travail a été terminé à l’emplacement d’expédition finale et que la quantité retirée correspond à celle créée sur la ligne de chargement.
1. Répétez cette procédure pour toutes les lignes de chargement afin de vous assurer que tous les critères sont remplis.

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-rounding-issues"></a>Examiner vos lignes de chargement et effectuer des ajustements pour vous assurer que la quantité peut être convertie proprement sans problème d’arrondi

Procédez comme suit pour examiner vos lignes de chargement et effectuer des ajustements pour vous assurer que la quantité peut être convertie proprement sans problème d’arrondi.

1. Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.
1. Sélectionnez le chargement pour lequel le bon de livraison ne peut pas être généré.
1. Dans le volet Actions, dans l’onglet  **Expédier et recevoir**, dans le groupe  **Annuler**, sélectionnez  **Annuler la confirmation de livraison**.
1. Sur l’onglet  **Lignes de chargement**, sélectionnez la ligne de chargement de l’article qui dépasse la livraison excédentaire.
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

### <a name="make-sure-that-the-inventory-unit-of-measure-is-smaller-than-the-sales-unit-of-measure"></a>Vous assurer que l’unité de mesure du stock est inférieure à l’unité de mesure de vente

Vous assurer que l’unité de mesure du stock est inférieure à l’unité de mesure de vente. Envisagez de reconfigurer l’unité de mesure de l’article selon les besoins.
