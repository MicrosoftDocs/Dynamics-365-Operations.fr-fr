---
title: Montant arrondi pour les calculs d&quot;amortissement
description: "Cet article présente le champ Arrondir l&quot;amortissement qui est indiqué dans les pages de paramétrage du registre."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBookTable, AssetDepBookTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13931
ms.assetid: faf7db87-046f-41d1-9baf-0df66e373e97
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 8d5a9d9267c14ee045388c3b3b42b26f2fff45ea
ms.contentlocale: fr-fr
ms.lasthandoff: 05/25/2017


---

# <a name="round-off-amount-for-depreciation-calculations"></a>Montant arrondi pour les calculs d'amortissement

[!include[banner](../includes/banner.md)]


Cet article présente le champ Arrondir l'amortissement qui est indiqué dans les pages de paramétrage du registre.

Les montants d'amortissement arrondis sont définis pour chaque registre. Les montants d'amortissement arrondis sont utilisés dans le profil d'amortissement des immobilisations qui indique le prochain amortissement et la valeur de l'immobilisation, ainsi que dans les propositions d'amortissement. Entrez le montant minimal de l'amortissement autorisé pour le registre. 

Indépendamment de l'arrondi paramétré, le montant d'amortissement de la dernière période d'amortissement n'est pas arrondi. À la fin de la dernière période d'amortissement, la valeur de l'immobilisation doit être nulle ou égale à la valeur de mise au rebut, si cette valeur est utilisée.

### <a name="example"></a>Exemple

Un amortissement sans arrondi est calculé comme égal à 2 444,44. Selon la manière dont l'arrondi est paramétré, différents montants sont suggérés, comme indiqué dans le tableau suivant.

| Méthode d'arrondi | Montant d'amortissement |
|-----------------|---------------------|
| Arrondi 0,1    | 2 444,40            |
| Arrondi 1,00   | 2 444,00            |
| Arrondi 10,00  | 2 440,00            |
| Arrondi 100,00 | 2 400,00            |






