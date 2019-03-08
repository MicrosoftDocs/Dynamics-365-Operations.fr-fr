---
title: Amortissement dégressif fiscal
description: La méthode d'amortissement dégressif fiscal est une méthode d'amortissement utilisée en France. Les montants d'amortissement sont calculés à l'aide de la méthode d'amortissement dégressif et de la méthode d'amortissement linéaire. Le plus grand des deux montants d'amortissement calculés est ensuite utilisé comme montant d'amortissement dégressif fiscal.
author: Anasyash
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetRBSLFactorTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 30271
ms.search.region: France
ms.author: anasyash
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f4375fb247b47ddca04e92a61ed24ea4a8d75581
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "370662"
---
# <a name="rbsl-depreciation"></a>Amortissement dégressif fiscal

[!include [banner](../includes/banner.md)]

La méthode d'amortissement dégressif fiscal est une méthode d'amortissement utilisée en France. Les montants d'amortissement sont calculés à l'aide de la méthode d'amortissement dégressif et de la méthode d'amortissement linéaire. Le plus grand des deux montants d'amortissement calculés est ensuite utilisé comme montant d'amortissement dégressif fiscal.

La méthode d'amortissement dégressif fiscal (France) utilise toujours la période d'amortissement mensuelle dans le profil d'amortissement. Lorsque vous créez une immobilisation et affectez un modèle de valeur à l'aide de la méthode d'amortissement dégressif fiscal (France), la date de début de l'amortissement est toujours le premier jour du mois, et la date de fin est toujours la fin de l'exercice. Le montant d'amortissement dégressif est calculé à l'aide du pourcentage d'amortissement dégressif, qui est calculé en fonction des facteurs d'amortissement dégressif fiscal. Vous pouvez paramétrer les facteurs d'amortissement dégressif fiscal en fonction de la durée de vie de l'immobilisation sur la page **Facteurs dégressif fiscal**. Par exemple, vous pouvez définir les facteurs suivants :

| Du       | Années | Mois | Facteur dégressif fiscal | Commentaire                                                                                                                     |
|-----------------|-------|--------|--------------|-----------------------------------------------------------------------------------------------------------------------------|
| 1er janvier 2016 | 1     | 0      | 1,00         | Pour une immobilisation avec une durée de vie égale ou supérieure à un an, le facteur dégressif fiscal est de 1,00.                 |
| 1er janvier 2016 | 3     | 0      | 1,25         | Pour une immobilisation avec une durée de vie égale ou supérieure à trois ans, le facteur dégressif fiscal est de 1,25.              |
| 1er janvier 2016 | 5     | 0      | 1,75         | Pour une immobilisation avec une durée de vie égale ou supérieure à cinq ans, le facteur dégressif fiscal est de 1,75.                 |
| 1er janvier 2016 | 6     | 8      | 2,25         | Pour une immobilisation avec une durée de vie égale ou supérieure à six ans et huit mois, le facteur dégressif fiscal est de 2,25. |

Lorsque vous créez une configuration **Groupe d'immobilisations/modèle de valeur**, vous spécifiez le nombre d'années et le nombre de mois de la durée de vie de l'immobilisation. Par défaut, ces valeurs seront utilisées pour certains modèles de valeur d'immobilisation, et utilisées pour calculer le facteur dégressif fiscal pour l'immobilisation. Pour chaque immobilisation, le pourcentage d'amortissement dégressif est calculé sur la durée de vie de l'immobilisation et le facteur dégressif fiscal approprié : amortissement dégressif % = facteur dégressif fiscal ÷ Durée de vie × 100 % En outre, les montants de l'amortissement dégressif et de l'amortissement linéaire restant sont calculés et comparés, et le montant le plus élevé est utilisé comme montant d'amortissement dégressif fiscal. Par exemple, supposons qu'une immobilisation avec un prix d'acquisition de 1 000,00 soit mise en service le 10 février 2016 et amortie en cinq ans à l'aide de la méthode du dégressif fiscal. Voici le calcul du pourcentage d'amortissement dégressif : % de l'amortissement dégressif = 1,75 ÷ 5 × 100 % = 35 % Le tableau suivant affiche les montants d'amortissement et la valeur comptable de l'immobilisation pour chaque année.

| Année      | Durée de vie linéaire restante           | Dégressif                    | Dégressif fiscal (le montant le plus élevé sur les deux) | Valeur comptable         |
|-----------|-----------------------------------|-------------------------------------|---------------------------------------|--------------------|
| 2016      | 183,33 (= 1 000,00 ÷ 5 × 11 ÷ 12) | 320,83 (= 1 000,00 × 35 % × 11 ÷ 12) | 320.83                                | 679.17             |
| 2017      | 169,79 (= 679,17 ÷ 4)             | 237,71 (= 679,17 × 35 %)             | 237.71                                | 441.46             |
| 2018      | 147.15                            | 154.51                              | 154.51                                | 286.95             |
| 2019      | 143.48                            | 100.43                              | 143.48                                | 143.47             |
| 2020      | 143.47                            | 50.21                               | 143.47                                | 0,00               |
| **Total** | **Non applicable**                | **Non applicable**                  | **1 000,00**                          | **Non applicable** |

**Remarque :** Si vous avez amorti une immobilisation à l'aide d'un logiciel d'immobilisation différent de Microsoft Dynamics 365 for Finance and Operations, vous devez valider l'acquisition et l'amortissement cumulé dans Finance and Operations pour la période antérieure à l'utilisation de Finance and Operations. Par exemple, si vous avez commencé à utiliser Finance and Operations le 1er janvier 2016, vous devez valider l'acquisition et l'amortissement cumulé dans Finance and Operations pour la période se terminant le 31 décembre 2015. Après la validation de l'acquisition, vous devez modifier la date d'acquisition par la date correcte à partir de votre logiciel précédent et entrer la durée de vie restante de l'immobilisation. Vous pouvez ensuite amortir l'immobilisation normalement, à partir du 1er janvier 2016.



