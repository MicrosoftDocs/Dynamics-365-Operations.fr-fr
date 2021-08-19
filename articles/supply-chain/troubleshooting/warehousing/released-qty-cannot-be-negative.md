---
title: Impossible de mettre à jour une ligne de chargement car la quantité libérée serait négative
description: Ce problème se produit lorsque la mise à jour ou la suppression d’une ligne de chargement entraînerait une quantité libérée négative.
author: GalynaFedorova
ms.date: 6/30/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningListPage_WHSLoadLineUnShipQty,WHSLoadTable_WHSLoadLineUnShipQty,WHSLoadPlanningWorkbench_WHSLoadLineUnShipQty,WHSShipmentDetails_WHSLoadLineUnShipQty,WHSLoadPlanningListPage_DeleteButtonLoadLine,WHSLoadTable_DeleteButtonLoadLine,WHSLoadPlanningWorkbench_DeleteButtonLoadLine,WHSShipmentDetails_DeleteButtonShipment
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a6325a632e1f68a0a3a9cb6b6091c48da014a405e8ce9ad69ea841f5cceb216f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6728457"
---
# <a name="cant-update-a-load-line-because-the-released-quantity-would-be-negative"></a>Impossible de mettre à jour une ligne de chargement car la quantité libérée serait négative

Code d’erreur : @WAX:ReleasedQtyCannotBeNegative

## <a name="symptoms"></a>Symptômes

Ce problème se produit lorsque la mise à jour ou la suppression d’une ligne de chargement entraînerait une quantité libérée négative. Dans ce cas, lorsque vous essayez de mettre à jour ou de supprimer la ligne de charge, le système affiche le message d’erreur suivant :

> La quantité libérée ne peut pas être négative pour l’article %1, le lot %2.

Par conséquent, vous ne pouvez pas mettre à jour ou supprimer la ligne de charge.

## <a name="cause"></a>Cause

Après avoir mis à jour ou supprimé une ligne de chargement, le système met à jour la quantité lancée de la ligne de vente associée (*whsSalesLine.ReleaseQty*). Le système évalue la quantité lancée et s’il constate que la quantité lancée de la ligne serait négative après la mise à jour, il ne vous permettra pas de mettre à jour ou de supprimer la ligne. Cette validation se produit chaque fois que vous essayez de mettre à jour la quantité de la ligne de chargement ou l’unité de mesure via diverses actions, telles que la suppression d’une ligne de chargement, la suppression d’une expédition, la modification de la quantité d’une ligne de chargement, la réduction de la quantité prélevée et le prélèvement court.

La cause principale la plus courante de ce problème est une modification de la conversion d’unité utilisée pour les lignes de charge ouvertes. Par exemple, la conversion d’unités lors du lancement d’une commande client était *50 ch = 1 PL*. Cependant, avant que l’expédition du chargement connexe ne soit finalisée, la conversion d’unité a été modifiée en *100 ch = 1 pl*.

## <a name="resolution"></a>Résolution

La solution consiste à annuler les modifications de conversion d’unité, à mettre à jour ou à supprimer la ligne de charge, puis à réimplémenter la conversion. Vous devez empêcher le traitement d’autres chargements incluant l’élément à l’origine du problème jusqu’à ce que le problème soit résolu. Sinon, les nouvelles conversions peuvent être utilisées pour d’autres chargements déjà ouverts.

Pour résoudre ce problème, effectuez les tâches suivantes :

1. Examinez la conversion d’unité qui a été utilisée pour la ligne de charge.
2. Examinez la conversion d’unité actuelle pour l’article et effectuez les ajustements qui permettront de mettre à jour ou de supprimer la ligne de charge.
3. Mettez à jour ou supprimez la ligne de charge et annulez les ajustements de conversion d’unité.

### <a name="review-the-unit-conversion-that-was-used-for-the-load-line"></a>Examinez la conversion d’unité qui a été utilisée pour la ligne de charge

Utilisez la procédure suivante pour examiner vos lignes de charge et notez la conversion d’unité qui a été utilisée pour la ligne de charge.

1. Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.
1. Sélectionnez la charge qui inclut la ligne de charge qui ne peut pas être supprimée ou mise à jour.
1. Dans le volet Actions, sous l’onglet **Chargements**, dans le groupe **Informations associées**, cliquez sur **Travail**.
1. Dans la grille supérieure, sélectionnez l’ID de travail pertinent.
1. Sur l’onglet **Général** en bas de page, calculez le taux de conversion entre la valeur **Quantité de travail d’inventaire** et la valeur **Quantité de travail**. Notez le taux.
1. Répétez cette procédure pour tous les ID de travail pertinents pour vous assurer que la même conversion a été utilisée.

### <a name="review-the-current-unit-conversion-for-the-item-and-make-adjustments"></a>Examinez la conversion d’unité actuelle pour l’article et effectuez des ajustements

Procédez comme suit pour examiner la conversion d’unités de votre produit et effectuer des ajustements pour vous assurer que la conversion de l’unité est conformes à la ligne de chargement.

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Ouvrez le produit correspondant pour accéder à la page **Détails du produit libéré**.
1. Sur le volet Actions, sous l’onglet **Produit**, dans le groupe **Paramétrer**, cliquez sur **Conversions d’unités**.
1. Sélectionnez la conversion entre les unités et effectuez les ajustements en utilisant la conversion que vous avez trouvée dans la section précédente.

### <a name="update-or-delete-the-load-line-and-revert-the-unit-conversion-adjustments"></a>Mettez à jour ou supprimez la ligne de charge et annulez les ajustements de conversion d’unité

Utilisez la procédure suivante pour traiter la ligne de charge selon les besoins et rétablir les conversions d’unités.

1. Accédez à **Gestion des entrepôts \> Chargements \> Tous les chargements**.
1. Ouvrez la charge qui inclut la ligne de charge qui ne peut pas être supprimée ou mise à jour.
1. Dans l’organisateur **Lignes de chargement**, sélectionnez la ligne de chargement.
1. Continuez avec les actions requises au besoin. (Par exemple, supprimez la ligne de charge ou modifiez sa quantité.)
1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Ouvrez le produit correspondant pour accéder à la page **Détails du produit libéré**.
1. Sur le volet Actions, sous l’onglet **Produit**, dans le groupe **Paramétrer**, cliquez sur **Conversions d’unités**.
1. Sélectionnez la conversion entre les unités et restaurer les ajustements effectués dans la section précédente.
