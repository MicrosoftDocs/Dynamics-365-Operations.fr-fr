---
title: Créer des budgets de maintenance
description: Cette rubrique explique comment créer un budget de maintenance dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetBudgetLineAdjust, EntAssetBudget, EntAssetBudgetRecalc, EntAssetBudgetCopy, EntAssetBudgetLine, EntAssetBudgetCreate, EntAssetBudgetApprove, EntAssetBudgetCalculateActualCost
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 593a03e3317de5759427dfc61093530c4b7ef7e9
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253492"
---
# <a name="create-maintenance-budgets"></a>Créer des budgets de maintenance

[!include [banner](../../includes/banner.md)]

 



Les budgets de maintenance sont utilisés pour fournir une vue d’ensemble des coûts prévus pour la maintenance préventive. Les lignes de budget sont calculées en fonction des lignes du programme de maintenance ayant une date de début prévue pendant la période de budget.

Les budgets de maintenance sont basés sur les types de coûts utilisés dans le module Gestion des actifs : **Préventif**, **Correctif** et **Investissement**. Les coûts budgétaires pour la maintenance d’investissement sont inclus pour les actifs actifs qui ont une date de remplacement au cours de la période budgétaire et une valeur de remplacement associée. Les coûts budgétaires pour la maintenance corrective sont inclus si une ancienne date de correction est incluse dans le calcul du budget. Dans ce cas, les coûts correctifs d’une période précédente sont calculés pour la même période future que celle pour laquelle vous calculez le budget de maintenance.

## <a name="create-a-maintenance-budget"></a>Créer un budget de maintenance

1. Sélectionnez **Gestion des actifs** \> **Recherches** \> **Budget de maintenance** \> **Budget**.
2. Sélectionnez **Créer un budget**.
3. Entrez un ID de budget dans le champ **Budget de maintenance**.
4. Entrez une description dans le champ **Description**.
4. Dans le raccourci **Période**, entrez les dates de début et de fin de la période budgétaire dans les champs **Date de début** et **Date de fin**.
5. Pour inclure les coûts budgétaires correctifs calculés sur la base des coûts réels d’une période précédente, entrez la date de début de la période dans laquelle ces coûts doivent être inclus dans le champ **Date de début corrective**.
6. En fonction du niveau de détail requis dans le budget, définissez les options appropriées sur les cinq raccourcis **Grouper par**.
7. Cliquez sur **OK**.
8. Sélectionnez **Lignes de budget** pour ouvrir la page **Lignes de budget de maintenance**, où vous pouvez afficher toutes les lignes de budget qui ont été créées pour la période.
9. Pour approuver le budget, sélectionnez-le dans la page **Budgets de maintenance**, puis sélectionnez **Approuver**. Puis, dans la boîte de dialogue **Approuver le budget**, sélectionnez **OK**. Votre nom est alors entré dans le champ **Approuvé par** sur la page **Budgets de maintenance**.

    > [!NOTE]
    > Après avoir approuvé un budget de maintenance, vous ne pouvez pas recalculer ou ajuster les lignes associées sur la page **Lignes de budget de maintenance** à moins de supprimer d’abord l’approbation. Pour supprimer l’approbation d’un budget de maintenance, sélectionnez-le dans la page **Budgets de maintenance**, puis sélectionnez **Approuver**. Puis, dans la boîte de dialogue **Approuver le budget**, sélectionnez **OK**.

![Budgets de maintenance](media/01-maintenance-budgets.png)

Vous pouvez également créer un budget de maintenance en copiant un budget existant. Sur la page **Budgets de maintenance**, sélectionnez le budget à copier, puis sélectionnez **Copier**. Cette approche est utile si, par exemple, vous avez créé un budget pour un mois et que vous souhaitez le copier sur d’autres mois.

> [!NOTE]
> Le budget de maintenance calcule seulement les coûts budgétaires selon les lignes du programme de maintenance. Pour calculer les coûts réels pour la même période, vous pouvez effectuer ce calcul dans la page **Contrôle des coûts d’actif**. 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]