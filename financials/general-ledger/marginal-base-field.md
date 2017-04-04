---
title: La taxe estime selon la base et les modes de calcul marginaux
description: "Cet article décrit comment les valeurs des champs Base marginale et Mode de calcul déterminent les taux de taxe dans les transactions de vente et d&quot;achat."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: TaxTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 7171
ms.assetid: 381fc309-b32a-4927-b5b8-fa1c31b0bd72
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 114dee90b0fe525f0b3efabbf651d2804a22dd7d
ms.openlocfilehash: ad731401fe553cdc50665cc87aaac64dc48813f2
ms.lasthandoff: 03/31/2017


---

# <a name="sales-tax-rates-based-on-the-marginal-base-and-calculation-methods"></a>La taxe estime selon la base et les modes de calcul marginaux

Cet article décrit comment les valeurs des champs Base marginale et Mode de calcul déterminent les taux de taxe dans les transactions de vente et d'achat.

La base marginale dans l'organisateur Calcul de la page Codes taxe détermine le montant utilisé pour le choix appropriés du (des) taux de taxe à partir des taux de la page Valeur de code taxe. Le type de montant dans le champ Base marginale, combinée avec la méthode du champ Mode de calcul détermine la logique permettant de rechercher le (les) taux de taxe corrects pour une transaction. 

Diverses combinaisons de valeurs dans ces champs produisent des calculs de la taxe très différents, comme le montrent les exemples suivants. Les exemples utilisent les mêmes valeurs d'intervalle de taxe qui sont paramétrées pour chaque code taxe sur la page Valeurs de codes taxe. Pour ouvrir cette page, les valeurs de code &gt; taxe de cliquez sur dans la page de codes taxe.

> [!Important]                                                                                                                  
> Si la base marginale sur un ou plusieurs de vos codes taxe est basée sur des montants de ligne ou des unités, la valeur du champ Mode de calcul de la page Paramètres de comptabilité doit être définie à Ligne. |

## <a name="net-amount-per-line"></a>Montant HT par ligne
Cette option permet de déterminer les taux de taxe sur la base du montant HT des lignes de facture, à l'exclusion de toute autre taxe.

### <a name="example"></a>Exemple

Les taux de taxe sont paramétrés dans les intervalles suivants :

| Intervalle de montant    | Taux de la taxe |
|--------------------|----------|
| 0 à 50             | 30 %      |
| 50 à 100           | 20 %      |
| 100 - 0 (&gt; 100) | 10 %      |

> [!NOTE]                                                                                                             
> La limite supérieure 0 (zéro) dans le dernier intervalle signifie que tous les montants supérieurs à 100 sont inclus dans l'intervalle.

Base marginale : ** Montant HT par ligne ** 

Mode de calcul : ** Intervalle ** 

Vous achetez 8 lampes à 25,00 pièce. 

Le montant HT de la ligne de facture est de 200 euros. 

La taxe est calculée comme suit : 

Taxe totale = 50 x 30 % + 50 x 20 % + 100 x 10 % = 15 + 10 + 10 = 35,00 euros 

Montant total de la facture = 200,00 + 35,00 = 235,00 euros 

**Variation** 

Si la facture a deux lignes avec quatre articles chacune, le montant net sur chaque ligne est 100,00 et la taxe est calculée comme suit : 

Ligne de taxe 1 = 50 x 30 % + 50 x 20 % = 15 + 10 = 25,00 euros 

Ligne de taxe 2 = 50 x 30 % + 50 x 20 % = 15 + 10 = 25,00 euros 

Taxe totale = 25,00 + 25,00 = 50,00 

Montant total de la facture = 200,00 + 50,00 = 250,00 euros

## <a name="net-amount-per-unit"></a> Montant HT par unité
Cette option permet de déterminer les taux de taxe en fonction de la valeur de chaque unité, à l'exclusion de toute autre taxe. Lorsqu'une base marginale basée sur les unités est sélectionnée, alors une unité doit également être spécifiée pour le code taxe.

### <a name="example"></a>Exemple

Les taux de taxe sont paramétrés dans les intervalles suivants :

| Montant             | Taux de la taxe |
|--------------------|----------|
| 0 à 50             | 30 %      |
| 50 à 100           | 20 %      |
| 100 - 0 (&gt; 100) | 10 %      |

Base marginale : ** Montant net par unité ** 

Mode de calcul : ** Montant entier ** 

Vous achetez 8 lampes à 25,00 pièce. 

Le montant HT de la ligne de facture est de 200 euros. 

La taxe est calculée comme suit : Taxe par unité = 25,00 = 30 % x 7,50 Taxe totale = 7,50 x 8 unités = 60,00 Montant total facturé = 200,00 + 60,00 = 260,00

## <a name="net-amount-of-invoice-balance"></a> Montant HT du solde de la facture

Cette option permet de déterminer les taux de taxe en fonction de la valeur totale de la facture, à l'exclusion de toute autre taxe.

### <a name="example"></a>Exemple

Les taux de taxe sont paramétrés dans les intervalles suivants :

| Montant            | Taux de la taxe |
|-------------------|----------|
| 0 à 50            | 30 %      |
| 50 à 100          | 20 %      |
| 100 -0 (&gt; 100) | 10 %      |

Base marginale : ** Montant HT du solde de la facture ** 

Mode de calcul : ** Intervalle ** une facture client est 2 lignes de 4 lampes sur chaque des lignes pour 25,00. Le montant HT du solde de facture est 4 x 25,00 + 4 x 25,00 = 200,00. La taxe est calculée comme suit : Taxe totale = 50 x 0,30 + 50 x 0,20 + 100 x 0,10 = 15 + 10 + 10 = 35,00 Montant total facturé = 200,00 + 35,00 = 235,00

## <a name="gross-amount-per-line"></a> Montant brut par ligne

Cette option permet de déterminer les taux de taxe en fonction de la valeur de la ligne, en incluant toute autre taxe pour cette ligne.

> [!NOTE]
> Dans un groupe de taxe, vous ne pouvez avoir qu'un seul code taxe avec cette sélection dans le champ Base marginale.

### <a name="example"></a>Exemple

Les taux de taxe sont paramétrés dans les intervalles suivants :

| Montant             | Taux de la taxe |
|--------------------|----------|
| 0 à 50             | 30 %      |
| 50 à 100           | 20 %      |
| 100 - 0 (&gt; 100) | 10 %      |

Base marginale : **Montant brut par ligne** Mode de calcul : **Intervalle** En outre, il existe un autre code taxe calculé pour un droit de douane spécial de 5,00 sur chaque lampe. Le droit est ajouté au montant HT avant le calcul de la taxe. Vous achetez 8 lampes à 25,00 pièce. Le montant HT de la ligne de facture est de 200 euros. Le montant brut de la ligne de facture est 8 x 25,00 + 8 x 5,00 = 240,00. La taxe est calculée comme suit : Taxe totale = de douanes 50 x 0,30 + 50 x 0,20 + 140 x 0,10 % = 15 + 20 + 14 = 39,00 € au total = 5,00 x 8 = 40,00 montants totaux de la facture = 200,00 + 39,00 + 40,00 = 279,00

**Variation** 

Si la facture est créée à l'aide de 2 lignes de facture de 4 articles chacune, le montant HT par ligne de facture est 100,00. Le montant brut (y compris le droit de douane de 4 x 5,00) par ligne de facture est 120,00, et la taxe est créée comme suit : Ligne de facture de taxe 1 = 50 x 0,30 + 50 x 0,20 + 20 x 0,10 = 15 + 10 + 2 = 27,00 Ligne de facture de taxe 2 50 x 0,30 + 50 x 0,20 + 20 x 0,10 = 15 + 10 + 2 = 27,00 Taxe totale = 27,00 + 27,00 = 54,00 Total des droits de douane = 5,00 x 8 = 40,00 Montant total facturé = 200,00 + 54,00 + 40,00 = 294,00

## <a name="gross-amount-per-unit"></a> Montant brut par unité

Cette option permet de déterminer les taux de taxe en fonction de la valeur de l'unité, en incluant toute autre taxe.

> [!NOTE]
> Dans un groupe de taxe, vous ne pouvez avoir qu'un seul code taxe avec cette sélection dans le champ Base marginale.

### <a name="example"></a>Exemple

Les taux de taxe sont paramétrés dans les intervalles suivants :

| Montant             | Taux de la taxe |
|--------------------|----------|
| 0 à 50             | 30 %      |
| 50 à 100           | 20 %      |
| 100 - 0 (&gt; 100) | 10 %      |

Base marginale : **Montant brut par unité** Il existe un droit de douane spécial de 5,00 sur chaque lampe. Le droit est ajouté au montant HT avant le calcul de la taxe. Vous achetez 8 lampes à 25,00 pièce. Le montant brut par unité est 30,00. La taxe est calculée comme suit : Taxe par unité = 30 x 30 % = 9,00 Taxe totale = 9,00 x 8 = 72,00 Total des droits de douane = 5,00 x 8 = 40,00 Montant total facturé = 200,00 + 72,00 + 40,00 = 312,00

## <a name="invoice-total-incl-other-sales-tax-amounts"></a> Facture totale, autres taxe incluses

Cette option permet de déterminer les taux de taxe en fonction de la valeur totale de la facture, en incluant toute autre taxe.
> [!NOTE]
> Dans un groupe de taxe, vous pouvez avoir qu'une seul code taxe avec cette sélection dans le champ Base marginale

### <a name="example"></a>Exemple

Les taux de taxe sont paramétrés dans les intervalles suivants :

| Montant             | Taux de la taxe |
|--------------------|----------|
| 0 à 50             | 30 %      |
| 50 à 100           | 20 %      |
| 100 - 0 (&gt; 100) | 10 %      |

Base marginale : ** Total de la facture avec d'autres montants de taxe ** mode de calcul : ** Intervalle **   
Il y a un droit de douane spécial de 5,00 euros sur chaque lampe. Le droit est ajouté au montant HT avant le calcul de la taxe. Vous achetez 8 lampes à 25,00 pièce. Le montant HT de la facture est 200,00. Le montant TTC de la facture est 200,00 + (8 x 5,00) = 240,00. La taxe est calculée comme suit : Taxe totale = 50 x 0,30 + 50 x 0,20 + 140 x 0,10 = 15 + 10 + 14 = 39,00 Total des droits de douane = 5,00 x 8 = 40,00 Montant total facturé = 200,00 + 39,00 + 40,00 = 279,00

Pour plus d'informations, voir [des options montant et de calcul entiers d'intervalle pour les codes taxe] (whole-amount-interval-options-sales-tax-codes.md) et [des méthodes de calcul de la taxe dans le champ Origine] (sales-tax-calculation-methods-origin-field.md).


