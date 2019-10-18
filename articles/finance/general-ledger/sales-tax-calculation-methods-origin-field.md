---
title: Méthodes de calcul de la taxe dans le champ Origine
description: Cet article décrit les options du champ Origine dans la page de codes taxe et la manière dont la taxe est calculée selon l'option sélectionnée pour un code taxe.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8ec6144599e9bb74333a663a56bdbf07b1999669
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177671"
---
# <a name="sales-tax-calculation-methods-in-the-origin-field"></a>Méthodes de calcul de la taxe dans le champ Origine

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

Cet article décrit les options du champ Origine dans la page de codes taxe et la manière dont la taxe est calculée selon l'option sélectionnée pour un code taxe.

Pour chaque code taxe créé dans la page Codes taxe, vous devez sélectionner la méthode de calcul à appliquer au montant de base de la taxe dans le champ Origine.

## <a name="percentage-of-net-amount"></a>Pourcentage du montant HT
La méthode de calcul Pourcentage du montant HT est la valeur par défaut dans le champ Origine. La taxe est calculée comme un pourcentage du montant d'achat ou de vente (hors taxe).
### <a name="example"></a>Exemple

Le taux de taxe est de 25 %. La ligne de facture affiche une quantité de 10 articles à 1 € pièce et le client peut prétendre à 10 % de remise ligne. Montant HT : (10 x 1,00) - 10 % = 9,00 Taxe : 9,00 x 25 % = 2,25 Montant total : 9,00 + 2,25 = 11,25

## <a name="percentage-of-gross-amount"></a> Pourcentage du montant brut
Si vous sélectionnez la méthode Pourcentage du montant brut, la taxe est calculée comme un pourcentage du chiffre d'affaires brut. Le montant brut est le montant HT de la ligne plus l'ensemble des taxes et frais pour la ligne à l'exception de la taxe indiquant Origine = Pourcentage du montant brut.
### <a name="example"></a>Exemple

L'administration fiscale impose des droits de douanes spéciaux sur un article. Le montant des droits de douanes est ajouté au montant HT avant le calcul de la taxe. Prenons les codes taxe suivants :
-   DROITS DE DOUANE 1 = 10 %, à l'aide de la méthode de calcul Pourcentage du montant HT
-   DROITS DE DOUANE 2 = 20 %, à l'aide de la méthode de calcul Pourcentage du montant HT
-   TAXE = 25 %, à l'aide de la méthode de calcul Pourcentage du montant brut

Si le montant HT = 10,00, alors les DROITS DE DOUANE 1 = 1,00 (10,00 x 10 %) et les DROITS DE DOUANE 2 = 2,00 (10,00 x 20 %). Les montants sont les suivants : Montant brut = Montant HT + montant DROITS DE DOUANE 1 + montant DROITS DE DOUANE 2 (10,00 + 1,00 + 2,00) = 13,00 TAXE = 13,00 x 25 % = 3,25 Total DROITS DE DOUANE et TAXE = 1,00 + 2,00 + 3,25 = 6,25 Montant total = 10,00 + 6,25 = 16,25

| **Remarque**                                                                                                                                                                                                                 |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Un seul code taxe avec Origine = Pourcentage du montant brut peut être utilisé pour une transaction. Si plusieurs codes taxe sont déterminés pour une transaction, une erreur s'affiche pour indiquer que la taxe ne peut pas être calculée. |


<a name="percentage-of-sales-tax"></a>Pourcentage de taxe
-----------------------

Lorsque vous sélectionnez Pourcentage de taxe dans le champ Origine, la taxe est calculée comme un pourcentage de la taxe sélectionnée dans le champ Taxe sur taxe. La taxe sélectionnée dans le champ Taxe sur taxe est d'abord calculée. La deuxième taxe est ensuite calculée en fonction du montant de la première taxe.
### <a name="example"></a>Exemple

Prenons les codes taxe suivants :
-   DROITS DE DOUANE 1 = 10 %, à l'aide de la méthode Pourcentage du montant HT
-   DROITS DE DOUANE 2 = 20 %, à l'aide de la méthode Pourcentage de taxe, avec Droits de douane 1 dans le champ Taxe sur taxe
-   TAXE = 25 %, à l'aide de la méthode Pourcentage du montant brut

Montant HT = 10,00 DROITS DE DOUANE 1 = 10,00 x 10 % = 1,00 DROITS DE DOUANE 2 = 1,00 x 20 % = 0,20 Montant brut = 10,00 + 1,00 + 0,20 = 11,20 TAXE = 11,20 x 25 % = 2,80 Total DROITS DE DOUANE et TAXE = 1,00 + 0,20 + 2,80 = 4,00 Montant total = 10,00 + 4,00 = 14,00

| **Remarque**                                                                                                                                                                                                                    |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Les calculs de taxe sur taxe à plusieurs niveaux ne sont pas possibles. Une taxe ne peut pas être calculée sur la base d'une taxe qui est déjà calculée sur la base d'une autre taxe. Plusieurs codes de taxe sur taxe à niveau unique peuvent être calculés sur une transaction. |

## <a name="amount-per-unit"></a> Montant par unité
Lorsque vous sélectionnez Montant par unité dans le champ Origine, la taxe est calculée comme un montant fixe par unité multiplié par la quantité entrée dans la ligne de document. Une unité doit être sélectionnée dans le champ Unité. Le montant par unité est spécifié dans la page Valeurs de code taxe.
### <a name="example"></a>Exemple

Le code taxe est paramétré comme suit : 1,20 EUR par unité = boîte Sur une ligne de facture client, 25 boîtes d'un article sont vendues La taxe est calculée comme suit = 25 x 1,20 = 30,00

| **Remarque**                                                                                                                                                                                                 |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Si la transaction est entrée dans une unité autre que l'unité spécifiée sur le code taxe, elle est automatiquement convertie en fonction des conversions d'unités paramétrées dans la page Conversion d'unités. |

###  <a name="amount-per-unit-additional-option"></a> Montant par unité, option supplémentaire

Sous l'onglet Calcul, vous pouvez choisir si une taxe calculée Montant par unité est calculée avant d'autres codes taxe et ajoutée au montant HT avant que d'autres codes taxe avec Origine = Pourcentage du montant HT soient calculés.

### <a name="examples"></a>Exemples

Supposons que nous calculions 2 codes taxe sur une transaction :

-   DROITS DE DOUANE : Origine = Montant par unité et une taxe, la valeur est définie sur 5,00 par unité = pcs
-   TAXE : Origine = comme indiqué dans les exemples ci-dessous, la valeur est définie sur 25 %

Nous vendons 1 article à un prix unitaire de 10,00
#### <a name="example-1"></a>Exemple 1

TAXE : Origine = Méthode Pourcentage du montant brut L'option Calculer avant la taxe n'a aucun effet, car la TAXE est calculée comme un pourcentage du montant brut. DROITS DE DOUANE = 1 x 5,00 = 5,00 Montant brut = 10,00 + 5,00 = 15,00 TAXE = 15,00 x 25 % = 3,75 Taxe totale = 5,00 + 3,75 = 8,75 Montant total = 10,00 + 8,75 = 18,75

#### <a name="example-2"></a>Exemple 2

TAXE : Origine = Pourcentage du montant HT L'option Calculer avant la taxe n'est pas sélectionnée pour le calcul des DROITS DE DOUANE. Montant HT = 10,00 DROITS DE DOUANE = 1 x 5,00 = 5,00 TAXE = 10,00 x 25 % = 2,50 Taxe totale = 5,00 + 2,50 = 7,50 Montant total = 10,00 + 7,50 = 17,50

#### <a name="example-3"></a>Exemple 3

TAXE : Origine = Pourcentage du montant HT L'option Calculer avant la taxe est sélectionnée pour le calcul des DROITS DE DOUANE. Montant HT = 10,00 DROITS DE DOUANE = 1 x 5,00 = 5,00 TAXE = (10,00 + 5,00) x 25 % = 3,75 Taxe totale = 5,00 + 3,75 = 8,75 Montant total = 10,00 + 8,75 = 18,75

#### <a name="example-4"></a>Exemple 4

Les résultats des exemples 1 et 3 sont les mêmes car il n'impliquent pas plusieurs droits de douanes. Supposez que vous ayez deux DROITS DE DOUANE et un seul est inclus dans le montant HT pour le calcul de la taxe : DROITS DE DOUANE 1 = 5,00, à l'aide de la méthode Montant par unité, et l'option Calculer avant la taxe est sélectionnée DROITS DE DOUANE 2 = 2,50, à l'aide de la méthode Montant par unité, et l'option Calculer avant la taxe n'est pas sélectionnée Taxe = 25 %, à l'aide de la méthode Pourcentage du montant HT Montant HT = 10,00 DROITS DE DOUANE 1 = 1 x 5,00 = 5,00 DROITS DE DOUANE 2 = 1 x 2,50 = 2,50 Montant HT soumis à la taxe = 10,00 + 5,00 = 15,00 TAXE = 15,00 x 25 % = 3,75 Taxes totales, droits de douanes inclus = 5,00 + 2,50 + 3,75 = 11,25 Montant total = 10,00 + 11,25 = 21,25 La TAXE de 25 % est calculée pour la somme du montant HT (10,00) + DROITS DE DOUANE 1 (5,00) = 15,00. Les DROITS DE DOUANE 2 sont ajoutés au montant de la taxe après le calcul de la taxe.

## <a name="calculated-percentage-of-net-amount"></a> Pourcentage calculé du montant HT
Le pourcentage calculé du montant HT gère le calcul de la taxe différemment selon la définition du paramètre Montants, taxe incluse pour le document ou le journal.
### <a name="example-1"></a>Exemple 1

Le document ou journal est défini sur Montants, taxe incluse = Oui Montant de la ligne de transaction = 10,00 Taux de taxe = Taxe de 25 % Montant de la ligne de transaction x taux de taxe (10,00 x 25 %) = 2,50 Montant de base de la taxe (montant d'origine) = Montant de la ligne de transaction - Taxe (10,00 - 2,50) = 7,50

### <a name="example-2"></a>Exemple 2

Le document ou journal est défini sur Montants, taxe incluse = Non Montant de la ligne de transaction = 10,00 Taux de taxe = Taxe de 25 % (Montant de la ligne de transaction x taux de taxe) / (100 - taux de taxe) (10,00 x 25 %) / (100 % - 25 %) = 3,33 Montant de base de la taxe (montant d'origine) = Montant de la ligne de transaction = 10,00



<a name="additional-resources"></a>Ressources supplémentaires
--------

[Détermination des taux de taxe en fonction des champs Base marginale et Mode de calcul](marginal-base-field.md)

[Options de calcul Montant entier et Intervalle pour les codes taxe](whole-amount-interval-options-sales-tax-codes.md)



