---
title: Mettre à jour les budgets de maintenance
description: Cet article explique comment mettre à jour un budget de maintenance dans le module Gestion des actifs.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: a9333c9ad48c87159ed4071a8b4843fc0e55ceb5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860955"
---
# <a name="update-maintenance-budgets"></a>Mettre à jour les budgets de maintenance

[!include [banner](../../includes/banner.md)]

 

La page **Lignes du budget de maintenance** présente toutes les lignes du budget créées pour le budget sélectionné sur la page **Budgets de maintenance**. (Pour plus d’informations, voir [Créer des budgets de maintenance](create-maintenance-budget.md).) Vous pouvez recalculer et ajuster les lignes du budget de maintenance jusqu’à ce que le budget de maintenance soit approuvé. Une fois la période du budget écoulée, et si les coûts ont été validés dans le module Gestion des actifs, vous pouvez également mettre à jour les lignes du budget avec les coûts réels.

## <a name="recalculate-a-maintenance-budget"></a>Recalculer un budget de maintenance

Vous pouvez recalculer un budget de maintenance sur la page **Lignes du budget de maintenance**. Lorsque vous recalculez un budget de maintenance, les lignes de budget existantes sont supprimées et un nouveau calcul est effectué.

1. Sur la page **Lignes du budget de maintenance**, sélectionnez **Recalculer**.
2. Dans la boîte de dialogue **Recalculer le budget**, apportez les modifications requises pour le recalcul, puis sélectionnez **OK**.

De nouvelles lignes budgétaires sont créées conformément aux valeurs définies.

## <a name="adjust-budget-lines"></a>Ajuster les lignes budgétaires

Plutôt que de recalculer l’intégralité du budget de maintenance, vous pouvez ajuster les lignes sélectionnées associées aux coûts budgétaires.

1. Sur la page **Lignes du budget de maintenance**, sélectionnez les lignes pour mettre à jour le coût budgétaire.
2. Sélectionnez **Ajuster**.
3. Pour ajouter un montant sur les lignes sélectionnées, activez la case à cocher **Ajouter le coût**, puis entrez la valeur dans le champ **Ajouter une valeur**.
4. Pour multiplier le coût budgétaire sur les lignes de budget sélectionnées par un facteur, activez la case à cocher **Multiplier le coût**, puis entrez le facteur dans le champ **Multiplier la valeur**.

    Par exemple, si vous entrez **1,2** dans le champ **Multiplier la valeur**, vous augmentez le coût budgétaire sur les lignes sélectionnées par 20 %. Si vous entrez **0,7**, vous diminuez le coût budgétaire sur les lignes sélectionnées de 30 %.

5. Cliquez sur **OK**.

Les lignes de budget sélectionnées sont mises à jour selon les valeurs que vous définissez à l’étape 3 ou 4.

## <a name="update-actual-costs"></a>Mettre à jour les coûts réels

Une fois les dates des lignes budgétaires écoulées, et les coûts réels validés dans le module Gestion des actifs, vous pouvez mettre à jour les coûts réels sur le budget de la maintenance.

1. Sur la page **Lignes du budget de maintenance**, sélectionnez **Mettre à jour le coût**.
2. Dans la boîte de dialogue **Calculer le coût réel**, sélectionnez **OK**.

Les champs **Coût réel** sur les lignes du budget sont mis à jour si les coûts réels ont été validés. De nouvelles lignes budgétaires peuvent être générées si les nouveaux types d’actifs ont été créés depuis que vous avez créé le budget et si ces types d’actif ont été utilisés sur les actifs pour lesquels les ordres de travail ont été créés et pour lesquels les coûts associés ont été validés. Les nouvelles lignes budgétaires affichent uniquement les coûts réels, car aucun coût budgétaire n’a été calculé pour elles.

> [!NOTE]
> Pour afficher une vue d’ensemble des coûts réels répartis en coûts préventifs, correctifs et d’investissement, vous pouvez effectuer un calcul pour la même période sur la page **Contrôle des coûts d’actifs**. 

## <a name="manually-add-budget-lines"></a>Ajouter manuellement des lignes budgétaires

Sur la page **Lignes du budget de maintenance**, vous pouvez ajouter manuellement une nouvelle ligne de budget en sélectionnant **Nouveau**, puis en faisant des sélections sur la ligne. Voici quelques exemples de situations où cette approche peut être utile :

- Vous savez que le reconditionnement de certains actifs est actuellement en phase de planification, mais les tâches associées n’ont pas encore été créées dans le module Gestion des actifs. Toutefois, vous souhaitez que les coûts budgétaires pour ces tâches sont incluses dans le budget de maintenance.
- De nouveaux actifs ou types d’actifs ont été créés depuis la réalisation du budget de maintenance, mais les plans de maintenance n’ont pas encore été configurés sur ces actifs ou types d’actifs. Toutefois, vous souhaitez que les coûts budgétaires pour ces types d’actifs sont incluses dans le budget de maintenance.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]