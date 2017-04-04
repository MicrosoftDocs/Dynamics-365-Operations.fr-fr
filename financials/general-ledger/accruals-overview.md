---
title: "Vue d&quot;ensemble des régularisations"
description: "Cet article décrit les régularisations, et fournit des informations sur leur paramétrage pour créer des transactions."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerAccuralTable
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14131
ms.assetid: 0489b59a-37a7-4a78-87bf-4b597e9efad9
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 328a4a7bef32ee8634e4a9f4854ebe78fcc99f6d
ms.lasthandoff: 03/31/2017


---

# <a name="accruals-overview"></a>Vue d'ensemble des régularisations

Cet article décrit les régularisations, et fournit des informations sur leur paramétrage pour créer des transactions.

Les régularisations sont utilisées dans la comptabilité d'exercice pour suivre le produit identifié dans la période à laquelle il a été acquis, et non lorsque le paiement est reçu, et pour suivre les dépenses (coûts) identifiées lorsqu'ils surviennent, et non lors du paiement.

## <a name="accrual-schemes"></a>Plans de régularisation
Des plans de régularisation permettent de paramétrer le produit et les coûts différés, et le même plan de régularisation peut être utilisé pour le produit et les coûts. La régularisation des comptes redistribue les coûts ou le produit d'une ligne de journal à reconnaître dans les périodes appropriées. Dans la page **Plan de régularisation**, spécifiez les comptes débiteurs et créditeurs qui seront utilisés lors de l'application du plan de régularisation.

-   **Débit** – Le compte principal que vous définissez remplace le compte principal de débit dans la ligne de N° document de journal. Ce compte est également utilisé pour la contrepassation des différés, selon les transactions de régularisation des comptes.
-   **Crédit** – Le compte principal que vous définissez remplace le compte principal de crédit dans la ligne de N° document de journal. Ce compte est également utilisé pour la contrepassation des différés, selon les transactions de régularisation des comptes.

Après avoir déterminé les comptes à utiliser, vous pouvez spécifier comment le n° document est créé lorsque des transactions de régularisation sont créées. Vous pouvez également spécifier la fréquence à laquelle les transactions ont lieu, le nombre de fois que des transactions sont créées, et le moment où les transactions sont validées. Une fois le plan de régularisation créé, vous pouvez l'utiliser dans certains journaux à l'aide de la fonction de régularisation des comptes.

## <a name="ledger-accruals"></a>Charges et produits constatés d'avance
Lorsque vous entrez un journal, vous pouvez cliquer sur **Régularisation des comptes** dans le menu **Fonctions**. Puis, lorsque vous sélectionnez le plan de régularisation, vous verrez le montant de base du journal qui sera réparti sur la période, comme déterminé par le plan de régularisation. Par exemple, si vous payez l'assurance d'un employé pour l'année en janvier, et le montant est 12.000, vous devez identifier cette dépense chaque mois. Vous pouvez sélectionner la date de début. Vous pouvez également indiquer si le montant qui est à recevoir est basée sur le compte ou le compte de contrepartie. Après avoir effectué vos sélections, cliquez sur ** des transactions ** pour afficher toutes les transactions créées selon le plan de régularisation. Par exemple, si vous étalez les 12.000 dans des dépenses d'assurance intangibles sur l'année, vous obtenez 1.000 pour chaque mois. Après avoir validé le journal, vous pouvez afficher les transactions à l'aide ** les transactions de N° document ** de la page de recherche. Si un plan de régularisation ne peut pas être appliqué (par exemple, lorsqu'une facture de commande client ou une facture de commande fournisseur est impliquée), vous pouvez créditer le montant et le débit prépayés le montant des dépenses. Vous pouvez ensuite sélectionner **Contrepartie** lorsque vous appliquez le plan de régularisation.


