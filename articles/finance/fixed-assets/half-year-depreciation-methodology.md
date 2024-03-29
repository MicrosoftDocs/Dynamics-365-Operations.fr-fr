---
title: Méthodologie de la convention d’amortissement semestriel
description: Cet article décrit la méthode utilisée par les immobilisations pour calculer l’amortissement à l’aide de la convention semestrielle, qui calcule six mois d’amortissement au cours de la première et de la dernière année de service d’un actif.
author: moaamer
ms.date: 08/17/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2019-08-17
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: fac20f7a31eca7922ed079f9554437f28448620d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879593"
---
# <a name="half-year-depreciation-convention-methodology"></a>Méthodologie de la convention d’amortissement semestriel

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cet article décrit la méthode utilisée dans les immobilisations pour calculer l’amortissement à l’aide de la convention semestrielle. La convention semestrielle calcule six mois d’amortissement pendant la première et la dernière année de service d’un actif. Pour plus d’informations sur les conventions d’amortissement, voir [Méthodes et conventions d’amortissement](Fixed-asset-depreciation-conventions.md). 

Lorsque vous utilisez la convention d’amortissement sur six mois, le système utilise l’année d’acquisition ou l’année de mise en service de l’immobilisation, puis calcule cinq années d’amortissement à partir de cette année, puis ajoute six mois. Pour illustrer ce processus, considérons un actif acquis au prix de 50 000 et mis en service en avril 2020. Supposons également que l’actif a une durée de vie de cinq ans.

La première année de service se terminera en décembre 2020, ce qui signifie que la fin de la durée de vie de cinq ans de l’actif sera décembre 2024. La convention d’amortissement semestrielle ajoutera six mois à la durée de vie de l’actif, ce qui signifie que sa durée de vie se terminera en juin 2025. 

> Amortissement annuel 50 000/5 = 10 000 amortissement mensuel 10 000/12 = 833,33 <br>
> Amortissement de la première année 10 000/2 = 5 000 et amortissement mensuel suivant 5 000/9 = 555,56

   [![Plan d’amortissement pour la convention d’amortissement semestrielle.](./media/half-yr-dprectn-cnvntn.png)](./media/half-yr-dprectn-cnvntn.png)

Les périodes d’amortissement prolongées ajoutées par la convention semestrielle permettent une répartition plus précise de l’amortissement. La convention de six mois représente les dépenses d’amortissement de manière plus égale, ce qui est utile pour la présentation du compte de résultat.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
