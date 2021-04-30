---
title: Afficher les transactions de passif, d’actifs et de dépenses
description: Cette rubrique explique comment afficher les transactions pour un actif loué. Ces transactions comprennent les transactions de passif locatif et les transactions de frais exécutoires qui ont été comptabilisées.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 55b8019db6abdb3bd5ecdb6eadc4f7443f2bf071
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881636"
---
# <a name="view-liability-asset-and-expense-transactions"></a>Afficher les transactions de passif, d’actifs et de dépenses

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment afficher les transactions pour un actif loué. Ces transactions comprennent les transactions de passif locatif et les transactions de frais exécutoires qui ont été comptabilisées. Les valeurs comptables du passif et droit d’utilisation de l’actif sont utilisées dans plusieurs rapports. Ils sont également utilisés pour calculer les valeurs d’ajustement.

## <a name="liability-transactions"></a>Opérations de passif

Pour afficher les transactions de passif de location, sélectionnez un contrat de location dans la page **Résumé du bail**, puis sélectionnez **Registres** pour ouvrir les registres joints à l’enregistrement de bail. Après une reconnaissance initiale, une facture ou un journal des intérêts a été validée, sélectionnez **transactions de passif**.

La page **transactions de passif** montre les transactions qui augmentent ou diminuent le passif locatif. Les montants négatifs sur cette page représentent les transactions de crédit dans l’application standard. Tous les intérêts courus sont présentés comme des valeurs négatives et augmentent le total du passif locatif. Les éventuels ajustements de location sont présentés sous forme de valeurs positives ou négatives, selon la nature et l’impact du registre de location. Le solde total net actuel du passif locatif pour le bail sélectionné est affiché en bas à gauche de la page.

## <a name="asset-transactions"></a>Transactions d’actifs

Pour afficher les transactions d’actif de location, sélectionnez un contrat de location dans la page **Résumé du bail**, puis sélectionnez **Registres** pour ouvrir les registres de locations joints à l’enregistrement de bail. Sélectionnez ensuite **Transactions d’actifs**.

La page **Transaction d’actifs** affiche les transactions qui augmentent ou diminuent l’actif de location et les comptes d’amortissement cumulé. Les débits sont affichés sous forme de valeurs positives et les crédits sont affichés sous forme de valeurs négatives, comme sur la page **Transactions de passif**. La reconnaissance initiale enregistrée et la suivante de l’amortissement cumulé sont affichées en bas à gauche de la page en tant que solde de l’actif. 

## <a name="expenses-transactions"></a>Transactions de dépenses

Pour afficher les transactions de dépenses de location, sélectionnez un contrat de location dans la page **Résumé du bail**, puis sélectionnez **Registres** pour ouvrir les registres de locations joints à l’enregistrement de bail. Sélectionnez ensuite **Transactions de dépenses**.

La page **Transactions de dépenses** affiche toutes les dépenses qui ont été imputées au contrat de location, telles que les frais d’intérêt, les frais d’amortissement et les frais exécutoires.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
