---
title: "Amortissement dégressif fiscal"
description: "Dégressif fiscal est une méthode d&quot;amortissement utilisée en France. Les montants sont calculés à l&quot;aide de la méthode d&quot;amortissement dégressif et de la méthode d&quot;amortissement restant linéaire. Le plus importante des deux montants d&quot;amortissement calculés est ensuite utilisé comme montant d&quot;amortissement dégressif dégressif fiscal."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 30271
ms.assetid: 25501947-dace-438f-9261-a4e9b3b10071
ms.search.region: France
ms.author: anasyash
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: ce9e7f2631b9ab5ebde44632ab43d80bb4b08066
ms.lasthandoff: 03/31/2017


---

# <a name="rbsl-depreciation"></a>Amortissement dégressif fiscal

Dégressif fiscal est une méthode d'amortissement utilisée en France. Les montants sont calculés à l'aide de la méthode d'amortissement dégressif et de la méthode d'amortissement restant linéaire. Le plus importante des deux montants d'amortissement calculés est ensuite utilisé comme montant d'amortissement dégressif dégressif fiscal.

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

** Remarque : ** Si vous dépréciiez une immobilisation à l'aide de le logiciel d'immobilisation autre que Microsoft Dynamics 365 pour les opérations, vous devez valider l'acquisition et l'amortissement cumulé dans Dynamics 365 pour les opérations pour la période antérieure avoir commencé en utilisant Dynamics 365 pour les opérations. Par exemple, si vous avez commencé à utiliser Dynamics 365 pour les opérations le 1er janvier 2016, vous devez valider l'acquisition et l'amortissement cumulé dans Dynamics 365 pour les opérations de la période terminé le 31 décembre 2015. Après la validation de l'acquisition, vous devez modifier la date d'acquisition par la date correcte à partir de votre logiciel précédent et entrer la durée de vie restante de l'immobilisation. Vous pouvez ensuite amortir l'immobilisation normalement, à partir du 1er janvier 2016.


