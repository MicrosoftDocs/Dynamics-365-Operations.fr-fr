---
title: Vue d’ensemble des régularisations
description: Cet article décrit les régularisations, et fournit des informations sur leur paramétrage pour créer des transactions.
author: aprilolson
ms.date: 11/21/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerAccuralTable
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "14131"
- intro-internal
ms.assetid: 0489b59a-37a7-4a78-87bf-4b597e9efad9
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 022d6574895d3263ce1e21a2f04985c418f45b61
ms.sourcegitcommit: fb9b6969218f2b82f0a4c72bfad75387fe00395c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/22/2022
ms.locfileid: "9799404"
---
# <a name="accruals-overview"></a>Vue d’ensemble des régularisations

[!include [banner](../includes/banner.md)]

Cet article décrit les régularisations, et fournit des informations sur leur paramétrage pour créer des transactions.

Les régularisations sont utilisées dans la comptabilité d’exercice pour suivre le produit identifié dans la période à laquelle il a été acquis, et non lorsque le paiement est reçu, et pour suivre les dépenses (coûts) identifiées lorsqu’ils surviennent, et non lors du paiement.

## <a name="accrual-schemes"></a>Plans de régularisation
Des plans de régularisation permettent de paramétrer le produit et les coûts différés, et le même plan de régularisation peut être utilisé pour le produit et les coûts. La régularisation des comptes redistribue les coûts ou le produit d’une ligne de journal à reconnaître dans les périodes appropriées. Dans la page **Plan de régularisation**, spécifiez les comptes débiteurs et créditeurs qui seront utilisés lors de l’application du plan de régularisation.

-   **Débit** – Le compte principal que vous définissez remplace le compte principal de débit dans la ligne de justificatif de journal. Ce compte est également utilisé pour la contrepassation des différés, selon les transactions de régularisation des comptes.
-   **Crédit** – Le compte principal que vous définissez remplace le compte principal de crédit dans la ligne de justificatif de journal. Ce compte est également utilisé pour la contrepassation des différés, selon les transactions de régularisation des comptes.

Après avoir déterminé les comptes à utiliser, vous pouvez spécifier comment le n° de justificatif est créé lorsque des transactions de régularisation sont créées. Vous pouvez également spécifier la fréquence à laquelle les transactions ont lieu, le nombre de fois que des transactions sont créées, et le moment où les transactions sont validées. Une fois le plan de régularisation créé, vous pouvez l’utiliser dans certains journaux à l’aide de la fonction de régularisation des comptes.

## <a name="ledger-accruals"></a>Charges et produits constatés d’avance
Lorsque vous entrez un journal, vous pouvez cliquer sur **Régularisation des comptes** dans le menu **Fonctions**. Puis, lorsque vous sélectionnez le plan de régularisation, vous verrez le montant de base du journal qui sera réparti sur la période, comme déterminé par le plan de régularisation. 

Par exemple, si vous payez l’assurance de l’employé pour toute l’année en janvier, et le montant est 12 000, vous devez identifier cette dépense chaque mois. Vous pouvez sélectionner la date de début. Vous pouvez également indiquer si le montant qui est à recevoir est basée sur le compte ou le compte de contrepartie. Après avoir effectué vos sélections, cliquez sur **Transactions** pour afficher toutes les transactions créées selon le plan de régularisation. Par exemple, si vous étalez les 12 000 dans des dépenses d’assurance au cours de l’année, vous verrez 1 000 pour chaque mois. Après avoir validé le journal, vous pouvez afficher les transactions à l’aide de la page de recherche **Pièces comptables**. Si un plan de régularisation ne peut pas être appliqué (par exemple, lorsqu’une facture de commande client ou une facture de commande fournisseur est impliquée), vous pouvez créditer le montant payé d’avance et débiter le montant des dépenses. Vous pouvez ensuite sélectionner **Contrepartie** lorsque vous appliquez le plan de régularisation.


Pour plus d’informations, voir [Créer des plans de régularisation](tasks/create-accrual-schemes.md) et [Créer des transactions de régularisation des comptes](tasks/create-ledger-accrual-transactions.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
