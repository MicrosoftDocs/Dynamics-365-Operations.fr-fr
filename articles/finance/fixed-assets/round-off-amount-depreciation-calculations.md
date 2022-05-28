---
title: Montant arrondi pour les calculs d’amortissement
description: Cette rubrique présente le champ Arrondir l’amortissement qui est indiqué dans les pages de paramétrage du registre.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, AssetDepBookTable
audience: Application User
ms.reviewer: kfend
ms.custom: 13931
ms.assetid: faf7db87-046f-41d1-9baf-0df66e373e97
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 98d6a21bea4688d6f258a98eab174485ceee2cfc
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8726723"
---
# <a name="round-off-amount-for-depreciation-calculations"></a>Montant arrondi pour les calculs d’amortissement

[!include [banner](../includes/banner.md)]

Cette rubrique présente le champ **Arrondir l’amortissement** qui est indiqué dans les pages de  **Paramétrage du registre**.

Les montants d’amortissement arrondis sont définis pour chaque registre. Les montants d’amortissement arrondis sont utilisés dans le profil d’amortissement des immobilisations qui indique le prochain amortissement et la valeur de l’immobilisation, ainsi que dans les propositions d’amortissement. Entrez le montant minimal de l’amortissement autorisé pour le registre. 

Indépendamment de l’arrondi paramétré, le montant d’amortissement de la dernière période d’amortissement n’est pas arrondi. À la fin de la dernière période d’amortissement, la valeur de l’immobilisation doit être nulle ou égale à la valeur de mise au rebut, si cette valeur est utilisée.

### <a name="example"></a>Exemple

Un amortissement sans arrondi est calculé comme égal à 2 444,44. Selon la manière dont l’arrondi est paramétré, différents montants sont suggérés, comme indiqué dans le tableau suivant.

| Méthode d’arrondi | Montant d’amortissement |
|-----------------|---------------------|
| Arrondi 0,1    | 2 444,40            |
| Arrondi 1,00   | 2 444,00            |
| Arrondi 10,00  | 2 440,00            |
| Arrondi 100,00 | 2 400,00            |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
