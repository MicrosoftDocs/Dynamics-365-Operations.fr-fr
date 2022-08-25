---
title: Déclaration de TVA (Belgique)
description: Cet article fournit des informations sur la déclaration de TVA pour la Belgique.
author: AdamTrukawka
ms.date: 06/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Belgium
ms.author: atrukawk
ms.search.validFrom: 2019-01-04
ms.dyn365.ops.version: 10.0.1
ms.search.form: ''
ms.openlocfilehash: c0e3bca70ecfc28a4e34ef9a77c3474043775931
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269453"
---
# <a name="vat-declaration-belgium"></a>Déclaration de TVA (Belgique)

[!include [banner](../includes/banner.md)]


Cet article décrit comment configurer la déclaration de taxe sur la valeur ajoutée (TVA) pour la Belgique au format XML et comment afficher l’aperçu de la déclaration de TVA et des transactions de vente et d’achat dans Microsoft Excel.

Pour générer automatiquement les rapports, commencez par créer suffisamment de codes de taxe afin de conserver une comptabilité TVA distincte pour chaque case de la déclaration de TVA. De plus, dans les paramètres spécifiques à l’application du format de gestion des états électroniques (ER) pour la déclaration de TVA, vous devez associer des codes de taxe avec le résultat des recherches des cases de déclaration de TVA.

Pour la Belgique, vous devez configurer les éléments suivants :

- Recherche de champ de rapport
- Nature
- Avances concernant les acquisitions intracommunautaires

Pour plus d’informations sur la configuration des paramètres spécifiques à l’application, consultez la section [Configurer les paramètres spécifiques à l’application pour les champs de déclaration de TVA](#set-up-application-specific-parameters-for-vat-declaration-fields) plus loin dans cet article.

Dans les tableaux suivants, la colonne « Résultat de la recherche » affiche le résultat de la recherche préconfiguré pour une ligne de déclaration de TVA spécifique dans le format de déclaration de TVA. Utilisez ces informations pour associer correctement les codes de taxe avec le résultat de la recherche, puis avec la ligne de déclaration de TVA.

## <a name="vat-declaration-overview"></a>Aperçu de la déclaration de TVA

La déclaration de TVA en Belgique contient les informations suivantes.

**SECTION II OPÉRATIONS À LA SORTIE**

Vous pouvez utiliser le tableau suivant pour déterminer comment un résultat de recherche préconfiguré dans le format est associé à une zone de déclaration de TVA.

Un résultat de recherche peut générer un montant dans plusieurs cases. Ces cases sont indiquées entre parenthèses. Par exemple, pour le résultat de la recherche **01_SalesLowerReducedRate**, « (01/54) » signifie que le montant de base de la TVA de la transaction est indiqué dans la case 01, et que le montant de la TVA de la transaction est indiqué dans la case 54.

| Description   | Boîte | Résultat de la recherche de champ de rapport (Base TVA)   |
|---------------|-----|---------------------------------------------------|
| A. Opérations soumises à un régime particulier    | 00  | 00_ExemptSalesSpecialScheme    |
| B. Transactions pour lesquelles la TVA est due par le déclarant :              | &nbsp;    |   &nbsp;  |
| \- au taux de 6 %.     | 01  | 01_SalesLowerReducedRate (01/54)   |
| \- au taux de 12 %.    | 02  | 02_SalesHigherReducedRate (02/54)  |
| \- au taux de 21 %.    | 03  | 03_SalesStandardRate (03/54)       |
| C. Services pour lesquels la TVA étrangère est due par le cocontractant | 44  | 44_ForeignSalesServicesReverseCharge  |
| D. Transactions pour lesquelles la TVA est due par le cocontractant     | 45  | 45_SalesReverseCharge  |
| E. Livraisons intracommunautaires exemptées effectuées en Belgique et ventes ABC        | 46  | 46_EUSales  |
| F. Autres opérations exemptées et autres opérations effectuées à l’étranger        | 47  | 47_OtherExemptSales  |
| G. Montant des avoirs émis et des corrections négatives :              | &nbsp;    | &nbsp;     |
| \- en ce qui concerne les opérations inscrites dans les grilles 44 et 46          | 48  | **Résultats de la recherche pour les notes de crédit :** 48_ForeignSalesServicesReverseChargeCreditNoteCorr</br> 48_EUSalesCreditNoteCorr    |
| \- relatives aux autres opérations de la Section II    | 49  | **Résultats de la recherche pour les notes de crédit :** 49_ExemptSalesSpecialSchemeCreditNoteCorr</br> 49_SalesStandardRateCreditNote (49/64)</br> 49_SalesHigherReducedRateCreditNote (49/64)</br> 49_SalesLowerReducedRateCreditNote (49/64)</br> 49_SalesLowerReducedRateNegativeCorrection (49/62)</br> 49_SalesHigherReducedRateNegativeCorrection (49/62)</br> 49_SalesStandardRateNegativeCorrection (49/62)</br> 49_SalesReverseChargeCreditNoteCorr</br> 49_OtherExemptSalesCreditNoteCorr |

**SECTION III OPÉRATIONS À L’ENTRÉE**

Vous pouvez utiliser le tableau suivant pour déterminer comment un résultat de recherche préconfiguré dans le format est associé à une zone de déclaration de TVA.

Un résultat de recherche peut générer un montant dans plusieurs cases, et les montants peuvent avoir des signes différents. Ces cases et ces signes sont indiqués entre parenthèses. Par exemple, pour le résultat de la recherche **8185_PurchasesGoodsCreditNote**, « (-81 +85/63) » signifie que le montant de base de la TVA de la transaction est indiqué dans la case 81 comme une valeur négative et dans la case 85 comme une valeur positive, et le montant de la TVA de la transaction est indiqué dans case 63 comme une valeur positive.

> [!NOTE]
> Les cases 81, 82 et 83 contiennent toujours le montant de base de la TVA plus le montant de la TVA non déductible. Les autres cases de cette section contiennent le montant de base de la TVA.

| Description    | Boîte | Résultat de la recherche de champ de rapport |
|----------------|-----|--------------------------------------|
| A. Montant des opérations à l’entrée compte tenu des avoirs reçus et des autres corrections :</br>  \- marchandises, matières premières et consommables    | 81  | 81_PurchasesGoods (81/59)</br> 81_PurchasesGoodsRegularizations (-81 +61)</br> **Résultat de la recherche pour les notes de crédit :**</br> 8185_PurchasesGoodsCreditNote (-81 +85/63)</br> **Résultats de la recherche pour la taxe d’utilisation :**</br> 8681_EUPurchasesGoodsUseTax (86/81 55/59)</br> 8781_OtherPurchasesDomesticReverseChargeGoodsUseTax (87/81 56/59)</br> 8781_OtherPurchasesImportsDeferredTaxGoodsUseTax (87/81 57/59)</br> **Résultats de la recherche pour les notes de crédit avec taxe d’utilisation :**</br> 868184_EUPurchasesGoodsCreditNoteUseTax (-86/81 +84/61/62)</br> 878185_OtherPurchasesDomesticReverseChargeGoodsCNUseTax (-87/81 +85/61/62)</br> 878185_OtherPurchasesImportsDeferredTaxGoodsCNUseTax (-87/81 +85/61/62)  |
| \- services et biens divers  | 82  | 82_PurchasesServicesMisc (82/59)</br>  82_PurchasesServicesRegularizations (-82 +61)</br> **Résultat de la recherche pour les notes de crédit :**</br> 8285_PurchasesServicesMiscCreditNote (-82 +85/63)</br> **Résultats de la recherche pour la taxe d’utilisation :**</br> 8682_EUPurchasesMiscUseTax (86/82 55/59)</br> 8782_OtherPurchasesDomesticReverseChargeMiscUseTax (87/82 56/59)</br> 8782_OtherPurchasesImportsDeferredTaxMiscUseTax (87/82 57/59)</br> 8882_EUPurchasesServicesUseTax (88/82 55/59)</br> **Résultats de la recherche pour les notes de crédit avec taxe d’utilisation :**</br> 868284_EUPurchasesMiscCreditNoteUseTax (-86/82 +84/61/62)</br> 878285_OtherPurchasesDomesticReverseChargeMiscCNUseTax (-87/82 +85/61/62)</br> 878285_OtherPurchasesImportsDeferredTaxMiscCNUseTax (-87/82 +85/61/62)</br> 888284_EUPurchasesServicesCreditNoteUseTax (-88/82 +84/61/62)  |
| \- actifs de la société   | 83  | 83_PurchasesCapitalGoods (83/59)</br>  83_PurchasesCapitalGoodsRegularizations (-83 +61)</br>  **Résultat de la recherche pour les notes de crédit :**</br>  8385_PurchasesCapitalGoodsCreditNote (-83 +85/63)</br>  **Résultats de la recherche pour la taxe d’utilisation :**</br>  8683_EUPurchasesCapitalGoodsUseTax (86/83 55/59)</br>  8783_OtherPurchasesDomesticReverseChargeCapitalGoodsUseTax (87/83 56/59) </br> 8783_OtherPurchasesImportsDeferredTaxCapitalGoodsUseTax (87/83 57/59)</br>  **Résultats de la recherche pour les notes de crédit avec taxe d’utilisation :**</br>  868384_EUPurchasesCapitalGoodsCreditNoteUseTax (-86/83 +84/61/62)</br>  878385_OtherPurchasesDomesticReverseChargeCapitalGoodsUseTax (-87/83 +85/61/62) </br> 878385_OtherPurchasesImportsDeferredTaxCapitalGoodsUseTax (-87/83 +85/61/62)  |
| B. Montant des avoirs reçus et des corrections négatives :  |  &nbsp;   |  &nbsp;  |
| \- relatives aux opérations enregistrées dans les cases 86 et 88   | 84  | **Résultats de la recherche pour les notes de crédit :**</br>  8684_EUPurchasesCreditNoteRC (-86 +84/62)</br>  8884_EUPurchasesServicesCreditNoteRC (-88 +84/62)</br>  **Résultats de la recherche pour les notes de crédit avec taxe d’utilisation :**</br>  868184_EUPurchasesGoodsCreditNoteUseTax (-86/81 +84/61/62)</br>  868284_EUPurchasesMiscCreditNoteUseTax (-86/82 +84/61/62)</br>  868384_EUPurchasesCapitalGoodsCreditNoteUseTax (-86/83 +84/61/62)</br>  888284_EUPurchasesServicesCreditNoteUseTax (-88/82 +84/61/62)  |
| \- relatives aux autres opérations de la case III   | 85  | **Résultats de la recherche pour les notes de crédit :**</br>  8185_PurchasesGoodsCreditNote (-81 +85/63)</br>  8285_PurchasesServicesMiscCreditNote (-82 +85/63)</br>  8785_OtherPurchasesImportsDeferredTaxCreditNote (-87 +85/62)</br>  **Résultats de la recherche pour les notes de crédit avec taxe d’utilisation :**</br>  878185_OtherPurchasesDomesticReverseChargeGoodsCNUseTax (-87/81 +85/61/62)</br>  878285_OtherPurchasesDomesticReverseChargeMiscCNUseTax (-87/82 +85/61/62)</br>  878385_OtherPurchasesDomesticReverseChargeCapitalGoodsUseTax (-87/83 +85/61/62)</br>  878185_OtherPurchasesImportsDeferredTaxGoodsCNUseTax (-87/81 +85/61/62)</br>  878285_OtherPurchasesImportsDeferredTaxMiscCNUseTax (-87/82 +85/61/62)</br>  878385_OtherPurchasesImportsDeferredTaxCapitalGoodsUseTax (-87/83 +85/61/62)   |
| C. Acquisitions intracommunautaires effectuées en Belgique et ventes ABC   | 86  | 86_EUPurchasesRC (86/55)</br>  **Résultat de la recherche pour les notes de crédit :**</br>  8684_EUPurchasesCreditNoteRC (-86 +84/62)</br>  **Résultats de la recherche pour la taxe d’utilisation :**</br>  8681_EUPurchasesGoodsUseTax (86/81 55/59)</br>  8682_EUPurchasesMiscUseTax (86/82 55/59)</br>  8683_EUPurchasesCapitalGoodsUseTax (86/83 55/59)</br>  **Résultats de la recherche pour les notes de crédit avec taxe d’utilisation :** </br> 868184_EUPurchasesGoodsCreditNoteUseTax (-86/81 +84/61/62)</br>  868284_EUPurchasesMiscCreditNoteUseTax (-86/82 +84/61/62) </br> 868384_EUPurchasesCapitalGoodsCreditNoteUseTax (-86/83 +84/61/62)   |
| D. Autres opérations à l’entrée pour lesquelles la TVA est due par le déclarant    | 87  | 87_OtherPurchasesDomesticReverseCharge (87/56) </br> 87_OtherPurchasesImportsDeferredTax (87/57)</br>  **Résultats de la recherche pour les notes de crédit :**</br>  8785_OtherPurchasesDomesticReverseChargeCreditNote (-87 +85/62) </br> 8785_OtherPurchasesImportsDeferredTaxCreditNote (-87 +85/62)</br>  **Résultats de la recherche pour la taxe d’utilisation :**</br>  8781_OtherPurchasesImportsDeferredTaxGoodsUseTax (87/81 57/59)</br>  8782_OtherPurchasesImportsDeferredTaxMiscUseTax (87/82 57/59)</br>  8783_OtherPurchasesImportsDeferredTaxCapitalGoodsUseTax (87/83 57/59) </br> 8781_OtherPurchasesDomesticReverseChargeGoodsUseTax (87/81 56/59)</br>  8782_OtherPurchasesDomesticReverseChargeMiscUseTax (87/82 56/59) </br> 8783_OtherPurchasesDomesticReverseChargeCapitalGoodsUseTax (87/83 56/59)</br>  **Résultats de la recherche pour les notes de crédit avec taxe d’utilisation :** </br> 878185_OtherPurchasesImportsDeferredTaxGoodsCNUseTax (-87/81 +85/61/62)</br>  878285_OtherPurchasesImportsDeferredTaxMiscCNUseTax (-87/82 +85/61/62) </br> 878385_OtherPurchasesImportsDeferredTaxCapitalGoodsUseTax (-87/83 +85/61/62)</br>  878185_OtherPurchasesDomesticReverseChargeGoodsCNUseTax (-87/81 +85/61/62) </br> 878285_OtherPurchasesDomesticReverseChargeMiscCNUseTax (-87/82 +85/61/62)</br>  878385_OtherPurchasesDomesticReverseChargeCapitalGoodsUseTax (-87/83 +85/61/62) |
| E. Services intracommunautaires avec taxe au preneur    | 88  | 88_EUPurchasesServicesRC (88/55)</br>  **Résultat de la recherche pour les notes de crédit :**</br>  8884_EUPurchasesServicesCreditNoteRC (-88 +84/62)</br>  **Résultat de la recherche pour la taxe d’utilisation :**</br>  8882_EUPurchasesServicesUseTax (88/82 55/59) </br> **Résultat de la recherche pour les notes de crédit avec taxe d’utilisation :**</br>  888284_EUPurchasesServicesCreditNoteUseTax (-88/82 +84/61/62)    |

**SECTION IV TAXE À PAYER**

Vous pouvez utiliser le tableau suivant pour déterminer comment un résultat de recherche préconfiguré dans le format est associé à une zone de déclaration de TVA.

| Description   | Boîte    | Résultat de la recherche de champ de rapport   |
|---------------|--------|----------------------------------------|
|A. TVA sur les opérations indiquées dans :</br>  \- les cases 01, 02 et 03     | 54    | 01_SalesLowerReducedRate (01/54)</br> 02_SalesHigherReducedRate (02/54)</br> 03_SalesStandardRate (03/54)   |
| \- les cases 86 et 88  | 55  | 86_EUPurchasesRC (86/55)</br> 88_EUPurchasesServicesRC (88/55)</br> **Résultats de la recherche pour la taxe d’utilisation :**</br> 8681_EUPurchasesGoodsUseTax (86/81 55/59)</br> 8682_EUPurchasesMiscUseTax (86/82 55/59)</br> 8882_EUPurchasesServicesUseTax (88/82 55/59) </br>8683_EUPurchasesCapitalGoodsUseTax (86/83 55/59) |
| \- case 87, à l’exception des importations avec taxe au preneur | 56   | 87_OtherPurchasesDomesticReverseCharge (87/56)</br> **Résultats de la recherche pour la taxe d’utilisation :** </br>8781_OtherPurchasesDomesticReverseChargeGoodsUseTax (87/81 56/59)</br> 8782_OtherPurchasesDomesticReverseChargeMiscUseTax (87/82 56/59) </br>8783_OtherPurchasesDomesticReverseChargeCapitalGoodsUseTax (87/83 56/59)  |
| B. TVA sur les importations avec taxe au preneur  | 57   | 87_OtherPurchasesImportsDeferredTax (87/57)</br> **Résultats de la recherche pour la taxe d’utilisation :** </br>8781_OtherPurchasesImportsDeferredTaxGoodsUseTax (87/81 57/59)</br> 8782_OtherPurchasesImportsDeferredTaxMiscUseTax (87/82 57/59) </br>8783_OtherPurchasesImportsDeferredTaxCapitalGoodsUseTax (87/83 57/59)   |
| C. Régularisations de TVA diverses en faveur de l’État   | 61   | 61_VATRegularizationsDue</br> 81_PurchasesGoodsRegularizations (-81 +61)</br> 82_PurchasesServicesRegularizations (-82 +61)</br> 83_PurchasesCapitalGoodsRegularizations (-83 +61)</br> **Résultats de la recherche pour les notes de crédit avec taxe d’utilisation :** </br>868184_EUPurchasesGoodsCreditNoteUseTax (-86/81 +84/61/62)</br> 868284_EUPurchasesMiscCreditNoteUseTax (-86/82 +84/61/62)</br> 868384_EUPurchasesCapitalGoodsCreditNoteUseTax (-86/83 +84/61/62)</br> 878185_OtherPurchasesDomesticReverseChargeGoodsCNUseTax (-87/81 +85/61/62)</br> 878285_OtherPurchasesDomesticReverseChargeMiscCNUseTax (-87/82 +85/61/62)</br> 878385_OtherPurchasesDomesticReverseChargeCapitalGoodsUseTax (-87/83 +85/61/62) </br>878185_OtherPurchasesImportsDeferredTaxGoodsCNUseTax (-87/81 +85/61/62)</br> 878285_OtherPurchasesImportsDeferredTaxMiscCNUseTax (-87/82 +85/61/62) </br>878385_OtherPurchasesImportsDeferredTaxCapitalGoodsUseTax (-87/83 +85/61/62)</br> 888284_EUPurchasesServicesCreditNoteUseTax (-88/82 +84/61/62)</br> |
| D. TVA à reverser mentionnée sur les avoirs reçus   | 63  | **Résultats de la recherche pour les notes de crédit :**</br> 8185_PurchasesGoodsCreditNote (-81 +85/63) </br>8285_PurchasesServicesMiscCreditNote (-82 +85/63)</br> 8385_PurchasesCapitalGoodsCreditNote (-83 +85/63)     |
| **Total des cases 54, 55, 56, 57, 61 et 63**    | **XX** | **54 + 55 + 56 + 57 + 61 + 63**    |

**SECTION V TAXE DÉDUCTIBLE**

Vous pouvez utiliser le tableau suivant pour déterminer comment un résultat de recherche préconfiguré dans le format est associé à une zone de déclaration de TVA.

| Description  | Boîte    | Résultat de la recherche de champ de rapport  |
|--------------|--------|---------------------------------------|
| A. TVA déductible  | 59  | 81_PurchasesGoods (81/59)</br> 82_PurchasesServicesMisc (82/59)</br> 83_PurchasesCapitalGoods (83/59)</br> **Résultats de la recherche pour la taxe d’utilisation :**</br> 8681_EUPurchasesGoodsUseTax (86/81 55/59)</br> 8682_EUPurchasesMiscUseTax (86/82 55/59) </br>8683_EUPurchasesCapitalGoodsUseTax (86/83 55/59)</br> 8781_OtherPurchasesDomesticReverseChargeGoodsUseTax (87/81 56/59) </br>8782_OtherPurchasesDomesticReverseChargeMiscUseTax (87/82 56/59)</br> 8783_OtherPurchasesDomesticReverseChargeCapitalGoodsUseTax (87/83 56/59) </br>8781_OtherPurchasesImportsDeferredTaxGoodsUseTax (87/81 57/59)</br> 8782_OtherPurchasesImportsDeferredTaxMiscUseTax (87/82 57/59) </br>8783_OtherPurchasesImportsDeferredTaxCapitalGoodsUseTax (87/83 57/59)</br> 8882_EUPurchasesServicesUseTax (88/82 55/59) |
| B. Régularisations de TVA diverses en faveur du déclarant | 62  | 62_VATRegularizationsDeduction</br> **Résultats de la recherche pour les notes de crédit et les corrections :** </br>49_SalesLowerReducedRateNegativeCorrection (49/62)</br> 49_SalesHigherReducedRateNegativeCorrection (49/62)</br> 49_SalesStandardRateNegativeCorrection (49/62) </br>8684_EUPurchasesCreditNoteRC (-86 +84/62)</br> 8884_EUPurchasesServicesCreditNoteRC (-88 +84/62)</br> 8785_OtherPurchasesImportsDeferredTaxCreditNote (-87 +85/62) </br>8785_OtherPurchasesDomesticReverseChargeCreditNote (-87 +85/62)</br> 8884_EUPurchasesServicesCreditNoteRC (-88 +84/62)</br> **Résultats de la recherche pour les notes de crédit avec taxe d’utilisation :**</br>868184_EUPurchasesGoodsCreditNoteUseTax (-86/81 +84/61/62)</br> 868284_EUPurchasesMiscCreditNoteUseTax (-86/82 +84/61/62) </br>868384_EUPurchasesCapitalGoodsCreditNoteUseTax (-86/83 +84/61/62)</br> 878185_OtherPurchasesDomesticReverseChargeGoodsCNUseTax (-87/81 +85/61/62) </br>878285_OtherPurchasesDomesticReverseChargeMiscCNUseTax (-87/82 +85/61/62)</br> 878385_OtherPurchasesDomesticReverseChargeCapitalGoodsUseTax (-87/83 +85/61/62)</br> 878185_OtherPurchasesImportsDeferredTaxGoodsCNUseTax (-87/81 +85/61/62)</br> 878285_OtherPurchasesImportsDeferredTaxMiscCNUseTax (-87/82 +85/61/62) </br>878385_OtherPurchasesImportsDeferredTaxCapitalGoodsUseTax (-87/83 +85/61/62)</br> 888284_EUPurchasesServicesCreditNoteUseTax (-88/82 +84/61/62) |
| C. TVA à récupérer mentionnée sur les avoirs émis   | 64   | **Résultats de la recherche pour les notes de crédit :**</br> 49_SalesStandardRateCreditNote (49/64)</br> 49_SalesHigherReducedRateCreditNote (49/64)</br> 49_SalesLowerReducedRateCreditNote (49/64)  |
| **Total des cases 59, 62 et 64**    | **AA** | **59 + 62 + 64**  |

**SECTION VI SOLDE**

| Description                                           | Boîte | Calcul           |
|-------------------------------------------------------|-----|-----------------------|
| Une seule des deux cases suivantes peut être remplie : |     |                       |
| Taxe due à l’État : case XX - case YY                 | 71  | XX – YY, si XX \>= YY |
| Montants dus par l’État : case YY - case XX            | 72  | YY – XX, si YY \> XX  |

**SECTION VII DÉPÔT**

| Description  | Boîte | Calcul   |
|--------------|-----|---------------|
| TVA réelle due pour la période du 1er décembre au 20 décembre dans la déclaration mensuelle, ou pour la période du 1er octobre au 20 décembre dans la déclaration trimestrielle | 91  | Le paramètre d’entrée **91 Montant du dépôt à payer en décembre** dans la boîte de dialogue utilisateur |

## <a name="purchase-reverse-charge-vat"></a>Taxe au preneur Achat

Si vous configurez des codes de taxe pour valider la taxe au preneur entrante en utilisant la taxe d’utilisation, associez vos codes de taxe avec le résultat de la recherche **Recherche de champ d’état** qui contient « UseTax » dans le nom.

Vous pouvez également configurer deux codes de taxe distincts : un pour la TVA due et un pour la déduction de la TVA. Associez ensuite chaque code avec l’état de recherche correspondant de la recherche **Champ d’état**.

Par exemple, pour les acquisitions intracommunautaires taxables au taux standard, vous devez configurer le code TVA **UT_S_EU** avec la taxe d’utilisation et l’associer au résultat de la recherche **8681_EUPurchasesGoodsUseTax (86/81 55/59)** du champ **Recherche de champ d’état**. Dans ce cas, les montants de taxe qui utilisent le code taxe **UT_S_EU** sont reflétés dans les cases 59 (« TVA déductible ») et 55 (« TVA sur les opérations indiquées dans les cases 86, 88 »). Les bases d’imposition sont reprises dans les cases 81 (« Montant des opérations entrantes : biens, matières premières et consommables ») et 86 (« Acquisitions intracommunautaires effectuées en Belgique et ventes ABC »).

Vous pouvez également configurer deux codes de taxe :

- **VAT_S_EU**, qui a une valeur de taux de taxe de -25 %
- **InVAT_S_EU**, qui a une valeur de taux de taxe de 25 %

Associez ensuite les codes avec les résultats de recherche du champ **Recherche de champ d’état** de la manière suivante :

- Associez **AT_S_EU** avec le résultat de la recherche **EUPurchaseStandard (86/55)**.
- Associez **InVAT_S_EU** avec le résultat de la recherche **EUPurchaseStandardDeduction (81/59)**.

Dans ce cas, les montants qui utilisent le code taxe **VAT_S_EU** sont repris dans les cases 55 (« TVA sur les opérations indiquées dans les cases 86, 88 ») et 86 (« Acquisitions intracommunautaires effectuées en Belgique et ventes ABC »). Les montants qui utilisent le code taxe **InVAT_S_EU** sont reflétés dans les cases 59 (« TVA déductible ») et 81 (« Montant des opérations entrantes : biens, matières premières et consommables »).

Pour plus d’informations sur la configuration de la taxe au preneur, consultez [Taxes au preneur](emea-reverse-charge.md).

## <a name="credit-notes-and-negative-corrections"></a>Notes de crédit et corrections négatives

En Belgique, les montants des notes de crédit et des corrections négatives sont indiqués dans des cases séparées sur la déclaration de TVA. Par conséquent, dans les tableaux précédents, des résultats de recherche spécifiques pour **Recherche de champ de rapport** sont dédiés aux notes de crédit et aux corrections négatives.

**Exemple : Ventes**

Une vente de biens (Facture 1) a une base TVA de 1 000,00 euros (EUR) et un montant de TVA de 210,00 euros. Cette vente peut apparaître dans les cases suivantes :

- **Case 03 (« Transactions pour lesquelles la TVA est due par le déclarant : au taux de 21 %. »):** 1 000,00
- **Case 54 (« TVA sur les opérations indiquées dans les cases 01, 02 et 03 ») :** 210,00

Un avoir (Avoir 1) émis ou une correction négative pour la facture précédente a une base TVA de -300,00 euros et un montant de TVA de -63,00 euros. Cette avoir ou cette correction peut apparaître dans les cases suivantes :

- **Case 49 (« Montant des avoirs émis et corrections négatives relatives aux autres opérations de la section II ») :** 300,00
- **Case 64 (« TVA à récupérer mentionnée sur les avoirs émis ») :** 63,00

**Exemple : Achats**

Un achat de marchandises (Facture 2) a une base TVA de 1 000,00 euros et un montant de TVA de 210,00 euros. Cet achat peut apparaître dans les cases suivantes :

- **Case 81 (« Montant des opérations à l’entrée compte tenu des avoirs reçus et des autres corrections : marchandises, matières premières et consommables ») :** 1 000,00
- **Case 59 (« TVA déductible ») :** 210,00

Un avoir (Avoir 2) reçu ou une correction négative pour la facture précédente a une base TVA de -400 euros et un montant de TVA de -84 euros. Cette avoir ou cette correction peut apparaître dans les cases suivantes :

- **Case 81 (« Montant des opérations à l’entrée compte tenu des avoirs reçus et des autres corrections : marchandises, matières premières et consommables ») :** - 400,00
- **Case 85 (« Montant des avoirs émis et corrections négatives relatives aux autres opérations de la section III ») :** 400,00
- **Case 63 (« TVA à reverser mentionnée sur les avoirs reçus ») :** 84,00

## <a name="sales-transaction-and-purchase-transaction-overview"></a>Aperçu des transactions de vente et d’achat

En Belgique, vous pouvez générer une liste des transactions de vente et d’achat.

Les exemples suivants montrent à quoi ressemblent ces états pour les exemples de la section précédente.

**Exemple : Transactions de vente**

| Numéro de référence | Zone 03   | Zone 54 | Zone 49 | Zone 64 |
|-----------------|----------|--------|--------|--------|
| Facture 1       | 1,000.00 | 210.00 | 00h00  | 00h00  |
| Avoir 1   | 00h00    | 00h00  | 300,00 | 63.00  |

**Exemple : Transactions d’achat**

| Numéro de référence | Zone 81   | Zone 59 | Zone 85 | Zone 63 |
|-----------------|----------|--------|--------|--------|
| Facture 2       | 1,000.00 | 210.00 | 00h00  | 00h00  |
| Avoir 2   | \-400.00 | 00h00  | 400,00 | 84.00  |

## <a name="set-up-a-vat-declaration-for-belgium"></a>Paramétrer une déclaration de TVA pour la Belgique

### <a name="configure-system-parameters"></a>Configuration des paramètres système

Pour générer une déclaration de TVA, vous devez configurer le numéro fiscal de l’entreprise.

1. Accédez à **Administration d’organisation** > **Organisations** > **Entités juridiques**.
2. Sélectionnez l’entité juridique, puis sélectionnez **ID enregistrement**.
3. Sélectionnez ou créez l’adresse en Belgique, puis, sur le raccourci **ID d’enregistrement**, sélectionnez **Ajouter**.
4. Dans le champ **Type d’enregistrement**, sélectionnez le type d’enregistrement dédié à la Belgique, et qui utilise la catégorie d’enregistrement **ID entreprise (COID)**.
5. Dans le champ **Numéro d’enregistrement**, saisissez le numéro fiscal au format suivant : *BTW BE 1234.567.890*.
6. Sur l’onglet **Général**, dans le champ **Date d’effet**, entrez la date à laquelle le numéro entre en vigueur.

Pour plus d’informations sur la configuration des catégories d’inscription et des types d’inscription, voir [Identifiants d’enregistrement](emea-registration-ids.md).

### <a name="import-er-configurations"></a>Importer les configurations ER

- Ouvrez l’espace de travail **Gestion des états électroniques** et importez les formats ER suivants :
- Déclaration de TVA XML (BE)
- Déclaration de TVA Excel (BE)

Pour plus d’informations, voir [Télécharger les configurations des états électroniques (ER) à partir du référentiel global de Configuration Service](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

### <a name="set-up-application-specific-parameters-for-vat-declaration-fields"></a>Configurer les paramètres spécifiques à l’application pour les champs de déclaration de TVA

> [!NOTE]
> Nous vous recommandons d’activer la fonctionnalité **Utiliser les paramètres spécifiques à l’application des versions précédentes de formats de rapport électronique** dans l’espace de travail **Gestion des fonctionnalités**. Lorsque cette fonctionnalité est activée, les paramètres configurés pour les versions antérieures d’un format ER deviennent automatiquement applicables pour les versions ultérieures du même format. Si cette fonctionnalité n’est pas activée, vous devez explicitement configurer les paramètres spécifiques à l’application pour chaque version de format. La fonctionnalité, **Utiliser les paramètres spécifiques à l’application des versions précédentes de formats de rapport électronique** est disponible dans l’espace de travail **Gestion des fonctionnalités** à partir de la version Finance 10.0.23 de Dynamics 365 Finance. Pour plus d’informations sur la configuration des paramètres d’un format ER pour chaque entité juridique, voir [Définir les paramètres d’un format de gestion des états électroniques par entité juridique](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-set-up.md).

Pour générer automatiquement une déclaration de TVA, associez les codes de taxe dans l’application aux résultats de recherche dans la configuration ER.

#### <a name="set-up-application-specific-parameters-for-report-field-lookup"></a>Configurer les paramètres spécifiques à l’application pour la recherche de champ de rapport

Suivez ces étapes pour définir quels codes de taxe génèrent quelles cases sur la déclaration de TVA.

1. Accédez à **Espaces de travail** > **Gestion des états électroniques** et sélectionnez **Configurations des états**.
2.  Sélectionnez la configuration **Déclaration de TVA XML (BE)**, puis sélectionnez **Configurations \> Configuration des paramètres spécifiques à l’application**.
3.  Sur la page **Paramètres spécifiques à l’application**, dans le raccourci **Recherches**, sélectionnez **Recherche de champ d’état**.
4.  Dans le raccourci **Conditions**, définissez les champs suivants pour associer les codes de taxe et les champs d’état.

    | Champ     | Description   |
    |-----------|---------------|
    | Résultat de la recherche  | Sélectionnez la valeur du champ d’état. Pour plus d’informations sur les valeurs et leur affectation aux lignes de déclaration de TVA, consultez la section [Vue d’ensemble de la déclaration de TVA](#vat-declaration-overview) plus haut dans cet article.  |
    | Code de taxe   | Sélectionnez le code de taxe à associer au champ d’état. Les transactions de taxe validées qui utilisent le code de taxe sélectionné seront collectées dans la case de déclaration appropriée. Nous vous recommandons de séparer les codes de taxe de telle sorte qu’un code de taxe ne génère des montants que dans une seule case de déclaration. |
    | Classifieur de transactions | Sélectionnez un classifieur de transaction. Les classifieurs de transactions suivants sont disponibles : </br> - **Achat** (taxe déductible) </br> - **PurchaseExempt** (achat exonéré de taxe)  </br>- **PurchaseReverseCharge** (taxe déductible provenant d’une taxe au preneur sur achat)  </br> - **Vente** (taxe exigible) </br> -  **SalesExempt** (vente exonérée de taxe) </br>- **SalesReverseCharge** (taxe exigible provenant d’une taxe au preneur sur achat ou vente) </br>- **Utiliser la taxe** (utiliser la taxe) </br> Pour chaque classifieur de transaction, un classifieur pour l’avoir est également disponible. Par exemple, l’un de ces classifieurs est **PurchaseCreditNote** (avoir sur achat). Assurez-vous de créer deux lignes pour chaque code de : une avec la valeur du classifieur de transaction et une avec le classifieur de transaction pour la valeur de l’avoir.  |

> [!NOTE]
> Associez tous les codes de taxe aux résultats de recherche. Si des codes de taxe ne doivent pas générer de valeurs dans la déclaration de TVA, associez-les au résultat de recherche **Autre**. Il y a une valeur pour le résultat de la recherche **Privé**. Si vous associez un code de taxe au résultat de la recherche **Privé**, le montant de la transaction qui a le code de taxe sélectionné ne sera affiché dans aucune case de la déclaration de TVA. Au lieu de cela, il sera affiché dans la colonne **Privé** du rapport **Transactions d’achat**. Vous pouvez identifier les achats qui sont utilisés à des fins privées uniquement en définissant un code de taxe avec un champ % non déductible défini sur 100 %. Si les achats sont partiellement utilisés à des fins privées, vous devez avoir des codes de taxe distincts pour un usage normal et un usage privé.

##### <a name="credit-notes-and-negative-corrections"></a>Notes de crédit et corrections négatives

> [!IMPORTANT]
> Toute transaction fiscale négative est classée comme avoir dans le champ **Classifieur de transactions**. Avant de configurer des paramètres spécifiques à l’application, examinez attentivement tous les types de transactions négatives dans l’application qui sont liées aux avoirs, aux corrections négatives et aux annulations. Avant de valider des opérations, décidez si vous devez configurer des codes de taxe supplémentaires pour toutes ou certaines transactions négatives, ou si les mêmes codes de taxe que vous utilisez pour les factures peuvent être utilisés pour certaines transactions négatives.

Les exemples suivants montrent comment différents paramètres affectent les résultats sur la déclaration de TVA.

**Scénario 1 : Une facture et une facture négative sont validées en utilisant le même code de taxe**

Pour cet exemple, une facture a une base TVA de 1 000,00 euros et un montant de TVA de 210,00 euros. Une facture négative a une base TVA de -600,00 euros et un montant de TVA de -126,00 euros. Les deux sont validés en utilisant le code de taxe **VAT_S**.

**Cas 1 :** Les résultats de la recherche sont configurés de la manière suivante :

| Résultat de la recherche                  | Étiquette                                                                                 | Ligne | Code de taxe | Classifieur de transactions |
|--------------------------------|---------------------------------------------------------------------------------------|------|----------|------------------------|
| 03_SalesStandardRate           | 03/54 Transactions soumises au taux de 21 %                                        | 1    | VAT_S    | Vente                  |
| 49_SalesStandardRateCreditNote | 49/64 Avoirs émis concernant des transactions soumises au taux de 21 % [03] | 2    | VAT_S    | SalesCreditNote        |

Dans ce cas, la déclaration de TVA affiche les résultats suivants :

- **Case 03 :** 1 000,00
- **Case 54 :** 210,00
- **Case 49 :** 600,00
- **Case 64 :** 126,00

**Cas 2 :** Les résultats de la recherche sont configurés de la manière suivante :

| Résultat de la recherche | Étiquette    | Ligne | Code de taxe | Classifieur de transactions |
|---------------|----------|------|----------|------------------------|
| 03_SalesStandardRate  | 03/54 Transactions soumises au taux de 21 %   | 1   | VAT_S   | Vente |
| 49_SalesStandardRateNegativeCorrection (49/62) | 49/62 Corrections négatives concernant des transactions soumises au taux de 21 % [03] | 2  | VAT_S | SalesCreditNote  |

Dans ce cas, la déclaration de TVA affiche les résultats suivants :

- **Case 03 :** 1 000,00
- **Case 54 :** 210,00
- **Case 49 :** 600,00
- **Case 62 :** 126,00

**Cas 3 :** Les résultats de la recherche sont configurés de la manière suivante :

| Résultat de la recherche        | Étiquette                                          | Ligne | Code de taxe | Classifieur de transactions |
|----------------------|------------------------------------------------|------|----------|------------------------|
| 03_SalesStandardRate | 03/54 Transactions soumises au taux de 21 % | 1    | VAT_S    | Vente                  |
| 03_SalesStandardRate | 03/54 Transactions soumises au taux de 21 % | 2    | VAT_S    | SalesCreditNote        |

Dans ce cas, la déclaration de TVA affiche les résultats suivants :

- **Case 03 :** 400,00
- **Case 54 :** 84,00

**Scénario 2 : Une facture et une facture négative sont validées en utilisant le même code de taxe, mais une autre facture négative est validée en utilisant un code de taxe spécialement défini**

Pour cet exemple, une facture a une base TVA de 1 000,00 euros et un montant de TVA de 210,00 euros. La facture négative 1 a une base TVA de +600,00 euros et un montant de TVA de 126,00 euros. La facture négative 2 a une base TVA de -100,00 euros et un montant de TVA de -21,00 euros.

La facture et la facture négative 1 sont validées en utilisant le même code de taxe **VAT_S**, mais une autre facture négative 2 est validée en utilisant un code de taxe spécialement défini, **VAT_S_CN**.

Les résultats de la recherche sont configurés de la manière suivante :

| Résultat de la recherche  | Étiquette | Ligne | Code de taxe | Classifieur de transactions |
|----------------|-------|------|----------|------------------------|
| 03_SalesStandardRate | 03/54 Transactions soumises au taux de 21 %   | 1  | VAT_S  | Vente  |
| 49_SalesStandardRateNegativeCorrection (49/62) | 49/62 Corrections négatives concernant des transactions soumises au taux de 21 % [03] | 2  | VAT_S | SalesCreditNote |
| 49_SalesStandardRateCreditNote | 49/64 Avoirs émis concernant des transactions soumises au taux de 21 % [03]  | 3  | VAT_S_CN | SalesCreditNote |

Dans ce cas, la déclaration de TVA affiche les résultats suivants :

- **Case 03 :** 1 000,00
- **Case 54 :** 210,00
- **Case 49 :** 700,00 (= 600,00 + 100,00)
- **Case 64 :** 126,00
- **Case 62 :** 21,00

#### <a name="set-up-application-specific-parameters-for-advances-related-to-intra-community-acquisitions"></a>Configurer les paramètres spécifiques à l’application pour les avances liées aux acquisitions intracommunautaires

En Belgique, les états **Opérations à la sortie** et **Opérations à l’entrée** comprennent une colonne qui doit indiquer le montant des avances liées aux acquisitions intracommunautaires. Vous devriez avoir un code de taxe distinct pour ces types d’avances.

Suivez ces étapes pour définir les codes de taxe qui génèrent le montant des avances liées aux acquisitions intracommunautaires. Ces étapes s’inscrivent dans la continuité des étapes de la section [Configurer les paramètres spécifiques à l’application pour la recherche de champ de rapport](#set-up-application-specific-parameters-for-report-field-lookup).

1. Sur la page **Paramètres spécifiques à l’application**, dans le raccourci **Recherches**, sélectionnez **Avances concernant les acquisitions intracommunautaires**.
2. Sur le raccourci **Conditions**, créez une ligne et définissez les champs suivants :

    - **Résultat de la recherche** : Sélectionnez **Oui** si le code de taxe est utilisé pour les avances liées à des acquisitions intracommunautaires.
    - **Code de taxe** : Sélectionnez un code de taxe.

3. Sur le raccourci **Conditions**, créez une ligne et définissez les champs suivants :

    - **Résultat de la recherche** : Sélectionnez **Non**
    - **Code de taxe** : Sélectionnez **Non vide** pour définir que tous les autres codes de taxe ne sont pas liés aux acquisitions intracommunautaires.

#### <a name="set-up-application-specific-parameters-for-nature"></a>Configurer les paramètres spécifiques à l’application pour la colonne Nature

L’état **Opérations à l’entrée** comprend une colonne **Nature** qui peut afficher une description des biens et services.

Suivez ces étapes pour définir quels groupes de taxe d’articles génèrent quelle description de la nature sur l’état. Ces étapes sont la suite des étapes de la section précédente.

1. Sur la page **Paramètres spécifiques à l’application**, dans le raccourci **Recherches**, sélectionnez **Nature**.
2. Dans le raccourci **Conditions**, définissez les champs suivants :

    - **Résultat de la recherche** : Définissez le texte de la nature.
    - **Groupe de taxes d’article** : Sélectionnez un groupe de taxes d’article.

3. Dans le champ **État**, changez la valeur sur **Terminé**.
4. Dans le volet Actions, sélectionnez **Exporter** pour exporter les paramètres dans un fichier XML. Fermez ensuite la page.
5. Sélectionnez la configuration **Déclaration de TVA Excel (BE)**, puis sélectionnez **Configurations** \> **Configuration des paramètres spécifiques à l’application**.
6. Sélectionnez **Importer**, puis sélectionnez le fichier que vous exporté précédemment.

### <a name="set-up-the-vat-reporting-format-for-preview-amounts-in-excel"></a>Configurer le format de déclaration de TVA pour les montants d’aperçu dans Excel

1. Dans l’espace de travail **Gestion des fonctionnalités**, recherchez et sélectionnez la fonction intitulée **États au format de déclaration de TVA** dans la liste, puis sélectionnez **Activer maintenant**.
2. Accédez à **Comptabilité \> Paramétrage \> Paramètres de comptabilité**.
3. Sur l’onglet **Taxe de vente**, dans le raccourci **Options de taxe**, dans le champ **Mappage des formats de déclaration de TVA**, sélectionnez le format ER **Déclaration de TVA Excel (BE)**.

   Ce format est imprimé lorsque vous exécutez l’état **État de la taxe pour la période de règlement**. Il sera également imprimé lorsque vous sélectionnerez **Imprimer** sur la page **Paiements de la taxe**.

4. Sur la page **Autorités fiscales**, sélectionnez l’administration fiscale, puis, dans le champ **Présentation d’état**, sélectionnez **Par défaut**.

Si vous configurez la déclaration de TVA dans une entité juridique qui a [plusieurs immatriculations à la TVA](emea-reporting-for-multiple-vat-registrations.md), procédez comme suit.

1. Accédez à **Comptabilité** > **Paramétrage** > **Paramètres de comptabilité**.
2. Dans l’onglet **Taxe de vente**, dans le raccourci **Gestion des états électroniques pour les pays/régions**, sur la ligne **DNK**, sélectionnez le format ER **Déclaration de TVA Excel (BE)**.

## <a name="set-up-electronic-messages"></a>Paramétrer des messages électroniques

### <a name="download-and-import-the-data-package-that-has-example-settings-for-electronic-messages"></a>Télécharger et importer le package de données ayant un exemple de paramètres pour les messages électroniques

Le package de données contient des paramètres de message électronique utilisés pour générer et prévisualiser la déclaration de TVA au format Excel. Vous pouvez développer ces paramètres ou créer les vôtres. Pour plus d’informations sur l’utilisation de la messagerie électronique et la création de vos propres paramètres, consultez [Messagerie électronique](../general-ledger/electronic-messaging.md).

1. Dans [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/v2), dans la bibliothèque d’actifs partagés, sélectionnez **Package de données** comme type d’actif, puis téléchargez le **Package EM Déclaration de TVA BE**. Le fichier téléchargé se nomme **BE VAT declaration package.zip**.
2. Dans Finance, dans l’espace de travail **Gestion des données**, sélectionnez **Importer**.
3. Dans le raccourci **Importer**, dans le champ **Nom de groupe**, entrez un nom pour la tâche.
4. Dans le raccourci **Entités sélectionnées**, sélectionnez **Ajouter un fichier**.
5. Dans la boîte de dialogue **Ajouter un fichier**, vérifiez que le champ **Format des données source** est défini sur **Package**, sélectionnez **Charger et ajouter**, puis sélectionnez le fichier .zip que vous avez précédemment téléchargé.
6. Sélectionnez **Fermer**.
7. Une fois les entités de données chargées, dans le volet Actions, sélectionnez **Importer**.
8. Accédez à **Ta** x \> **Recherches et états** \> **Messages électroniques** \> **Messages électronique**, puis validez le traitement des messages électroniques que vous avez importé (**Déclaration de TVA BE**).

### <a name="configure-electronic-messages"></a>Configurer les messages électroniques

1. Accédez à **Taxe** \> **Paramétrage** \> **Messages électroniques** \> **Actions Renseignement des enregistrements**.
2. Sélectionnez la ligne **Remplir les enregistrement de retour TVA BE**, puis sélectionnez **Modifier la requête**.
3. Utilisez le filtre pour spécifier les périodes de règlement à inclure dans l’état.
4. Si vous devez déclarer les transactions fiscales d’autres périodes de règlement dans une déclaration différente, créez une action **Remplir les enregistrements** et sélectionnez les périodes de règlement appropriées.

## <a name="preview-the-vat-declaration-incoming-transactions-and-outgoing-transactions-in-excel"></a>Afficher un aperçu de la déclaration de TVA, des transactions entrantes et sortantes dans Excel

### <a name="preview-the-vat-declaration-in-excel-from-the-report-sales-tax-for-settlement-period-periodic-task"></a>Prévisualisez la déclaration de TVA dans Excel à partir de la tâche périodique État de la taxe pour la période de règlement

1. Accédez à **Taxe** \> **Tâches périodiques** \> **Déclarations** \> **Taxe de vente** \> **État de la taxe pour la période de règlement**.
2. Définisse les champs suivants.

    | Champ                     | Description                                    |
    |---------------------------|------------------------------------------------|
    | Période de règlement         | Sélectionnez la période de règlement.                  |
    | Date de début                 | Permet de sélectionner la date de début de la période de reporting.|

3. Cliquez sur **OK**, puis dans la boîte de dialogue **Paramètres des états électroniques**, définissez les champs suivants :

    | Champ   | Description  |
    |---------|--------------|
    | 91 Montant du dépôt à payer en décembre | Entrez le montant, le cas échéant. |
    | Générer des états  | Sélectionnez les états à générer :</br> - Opérations à l’entrée </br>- Opérations à la sortie</br>- Aperçu de la déclaration de TVA  |
    | Inclure les champs  | Sélectionnez les colonnes qui doivent être visibles sur les états **Opérations à l’entrée** et **Opérations à la sortie**, en plus des colonnes **Date**, **Fournisseur**, et **Nom du client** : </br> - Date de document</br>- Numéro de document </br>   - Compte </br> - Justificatif </br> - N° de T.V.A.|

4. Sélectionnez **OK** et passez en revue la déclaration Excel.

### <a name="settle-and-post-sales-tax"></a>Régler et valider la taxe

1. Accédez à **Taxe** \> **Tâches périodiques** \> **Déclarations** \> **Taxe de vente** \> **Régler et valider la taxe**.
2. Définisse les champs suivants.

    | Champ                     | Description                                    |
    |---------------------------|------------------------------------------------|
    | Période de règlement         | Sélectionnez la période de règlement.                  |
    | Date de début                 | Permet de sélectionner la date de début de la période de reporting. |

3. Cliquez sur **OK**.

### <a name="preview-the-vat-declaration-incoming-operations-and-outgoing-operations-in-excel-from-a-sales-tax-payment"></a>Affichez un aperçu de la déclaration de TVA, des opérations entrantes et des opérations sortantes dans Excel à partir d’un paiement de taxe

1. Accédez à **Taxe** \> **Recherches et états** \> **Taxe (recherches)** \> **Paiements de la taxe**, puis sélectionnez une ligne de paiement de taxe.
2. Sélectionnez **Imprimer un état**, puis **OK**.
3. Examinez ensuite le fichier Excel généré pour la ligne de paiement de taxe sélectionnée.

> [!NOTE]
> L’état est généré uniquement pour la ligne sélectionnée du paiement de taxe. Si vous devez générer, par exemple, une déclaration rectificative contenant toutes les corrections pour la période, ou une déclaration de remplacement qui contient les données d’origine et toutes les corrections, utilisez la tâche périodique **État de la taxe pour la période de règlement**.

## <a name="generate-a-vat-declaration-incoming-operations-and-outgoing-operations-from-electronic-messages"></a>Générer une déclaration de TVA, des opérations entrantes et des opérations sortantes à partir de messages électroniques

Lorsque vous utilisez des messages électroniques pour générer l’état, vous pouvez collecter les données fiscales auprès de plusieurs entités juridiques. Pour plus d’informations, consultez la section [Exécuter une déclaration de TVA pour plusieurs entités juridiques](#run-a-vat-declaration-for-multiple-legal-entities) plus loin dans cet article.

La procédure suivante s’applique à l’exemple de traitement de message électronique que vous avez importé précédemment à partir de la bibliothèque d’actifs partagés LCS.

1. Accédez à **Taxe \> Recherches et états \> Messages électroniques \> Messages électroniques**.
2. Dans le volet de navigation à gauche, sélectionnez **Déclaration de TVA BE**.
3. Dans le raccourci **Messages**, sélectionnez **Nouveau**, puis, dans la boîte de dialogue **Exécuter le traitement**, cliquez sur **OK**.
4. Sélectionnez la ligne de message créée, saisissez une description, puis spécifiez les dates de début et de fin de la déclaration.

> [!NOTE]
> Les étapes 5 à 7 sont facultatives.

5. Facultatif : Dans le raccourci **Messages**, sélectionnez **Collecter des données**, puis cliquez sur **OK**. Les paiements de taxe qui ont été générés précédemment sont ajoutés au message. Pour plus d’informations, voir la section [Régler et valider la taxe](#settle-and-post-sales-tax) plus haut dans cet article. Si vous ignorez cette étape, vous pouvez toujours générer une déclaration de TVA en utilisant le champ **Version de la déclaration fiscale** dans la boîte de dialogue **Déclaration**.
6. Facultatif : Dans le raccourci **Éléments du message**, passez en revue les paiements de taxe qui sont transférés pour traitement. Par défaut, tous les paiements de taxe de la période sélectionnée qui n’étaient inclus dans aucun autre message du même traitement sont inclus.
7. Facultatif : Sélectionnez **Document d’origine** pour examiner les paiements de taxe, ou sélectionnez **Supprimer** pour exclure les paiements de taxe du traitement. Si vous ignorez cette étape, vous pouvez toujours générer une déclaration de TVA en utilisant le champ **Version de la déclaration fiscale** dans la boîte de dialogue **Déclaration**.
8. Dans le raccourci **Messages**, sélectionnez **Mettre à jour le statut**. Dans la boîte de dialogue **Mettre à jour le statut**, sélectionnez **Prêt à générer**, puis cliquez sur **OK**. Vérifiez que l’état du message est modifié en **Prêt à générer**.
9. Sélectionnez **Générer l’état**. Pour prévisualiser les montants de la déclaration de TVA, dans la boîte de dialogue **Exécuter le traitement**, sélectionnez **Aperçu de l’état**, puis cliquez sur **OK**.
10. Dans la boîte de dialogue **Paramètres de gestion des états électroniques**, définissez les champs comme décrit dans la section [Aperçu de la déclaration de TVA dans Excel à partir de la tâche périodique État de la taxe pour la période de règlement](#preview-the-vat-declaration-in-excel-from-the-report-sales-tax-for-settlement-period-periodic-task) plus haut dans cet article, puis sélectionnez **OK**.
11. Cliquez sur le bouton **Pièces jointes** (le symbole du trombone) dans l’angle supérieur droit de la page, puis sélectionnez **Ouvrir** pour ouvrir le fichier. Vérifiez les montants dans les documents Excel.
12. Sélectionnez **Générer l’état**.
13. Pour générer un état au format XML, dans la boîte de dialogue **Exécuter le traitement**, sélectionnez **Générer l’état**, puis cliquez sur **OK**.
14. Définisse les champs suivants.

    | Champ                       | Description                  |
    |-----------------------------|------------------------------|
    | Périodicité de l’état          | Sélectionnez **Mensuel** ou **Trimestriel**.  |
    | 61 Montant dû de régularisations de TVA reporté</br> 62 Montant de déduction de régularisations de TVA reporté</br> 81 Montant des achats de marchandises reporté</br> 82 Montant des achats de services reporté</br> 83 Montant des achats de biens d’équipement reporté</br> 86 Montant des achats de marchandises de l’UE reporté</br> 87 Autres achats avec montant de TVA à payer reporté</br> 88 Montant des achats de services de l’UE reporté | Dans ces champs, vous pouvez saisir un montant qui sera ajouté au montant de la case suivante. Vous pouvez entrer un montant négatif. Par exemple, vous devrez peut-être définir ces champs si le montant d’une case était négatif au cours de la période précédente et si vous deviez indiquer 0 (zéro) car les montants négatifs ne sont pas autorisés pour la case. Cependant, vous pouvez reporter le montant de la période précédente à la période en cours. |
    | 91 Montant du dépôt à payer en décembre   | Entrez le montant, le cas échéant.  |
    | Remplacement de la déclaration de TVA  | Entrez le numéro de la déclaration que vous remplacez, si vous déclarez des corrections.   |
    | Demande de remboursement | Sélectionnez **Oui**, ou laissez la valeur définie sur **Non**.    |
    | Demande de formulaires de paiement | Sélectionnez **Oui**, ou laissez la valeur définie sur **Non**.    |
    | Liste annuelle nulle        | Sélectionnez **Oui**, ou laissez la valeur définie sur **Non**.    |

15. Cliquez sur **OK**. 
16. Cliquez sur le bouton **Pièces jointes** (le symbole du trombone) dans l’angle supérieur droit de la page, puis téléchargez le fichier électronique généré. Vous devez ensuite télécharger manuellement ce fichier sur le portail de l’administration.

## <a name="run-a-vat-declaration-for-multiple-legal-entities"></a>Exécuter une déclaration de TVA pour plusieurs entités juridiques

Pour utiliser les formats pour générer un état sur la déclaration de TVA pour un groupe d’entités juridiques, vous devez d’abord configurer les paramètres spécifiques à l’application des formats ER pour les codes de taxe de toutes les entités juridiques requises.

### <a name="set-up-electronic-messages-to-collect-tax-data-from-several-legal-entities"></a>Configurer des messages électroniques pour collecter des données fiscales auprès de plusieurs entités juridiques

Suivez les étapes suivantes pour configurer des messages électroniques pour collecter des données fiscales auprès de plusieurs entités juridiques.

1. Accédez à **Espaces de travail \> Gestion des fonctionnalités**.
2. Recherchez et sélectionnez la fonctionnalité **Requêtes inter-sociétés pour les actions de remplissage des enregistrements** dans la liste, puis sélectionnez **Activer maintenant**.
3. Accédez à **Taxe \> Paramétrage \> Messages électroniques \> Actions Renseignement des enregistrements**.
4. Sur la page **Action Renseigner des enregistrements**, sélectionnez la ligne **Remplir les enregistrement de retour TVA BE**.

   Dans la grille **Configuration des sources de données**, un nouveau champ **Société** est disponible. Pour les enregistrements existants, ce champ affiche l’identificateur de l’entité juridique actuelle.

5. Dans la grille **Configuration des sources de données**, ajoutez une ligne pour chaque entité juridique supplémentaire qui doit être incluse dans la génération des états. Pour chaque nouvelle ligne, définissez les champs suivants.

    | Champ                  | Description                                                                                                                   |
    |------------------------|-------------------------------------------------------------------------------------------------------------------------------|
    | Nom                   | Entrez une valeur qui vous aidera à comprendre d’où vient cet enregistrement. Par exemple, entrez **Paiement TVA de la Filiale 1**. |
    | Type d’élément de message      | Sélectionnez **Retour TVA**. Cette valeur est la seule valeur disponible pour tous les enregistrements.                                    |
    | Type de compte           | Sélectionnez **Tout**.                                                                                                               |
    | Nom de la table principale      | Spécifiez **TaxReportVoucher** pour tous les enregistrements.                                                                             |
    | Champ Numéro du document  | Spécifiez **Voucher** pour tous les enregistrements.                                                                                      |
    | Champ Date du document    | Spécifiez **TransDate** pour tous les enregistrements.                                                                                    |
    | Champ Compte du document | Spécifiez **TaxPeriod** pour tous les enregistrements.                                                                                    |
    | Société                | Sélectionnez l’ID de l’entité juridique.                                                                                            |
    | Requête utilisateur             | Cette case est automatiquement cochée lorsque vous définissez des critères en sélectionnant **Modifier la requête**.                                 |

6. Pour chaque nouvelle ligne, sélectionnez **Modifier la requête** et spécifiez une période de règlement associée pour l’entité juridique qui est spécifiée dans le champ **Société** sur la ligne.

Une fois la configuration terminée, la fonction **Collecter des données** sur la page **Messages électroniques** collecte les paiements de taxe auprès de toutes les entités juridiques que vous avez définies.

## <a name="migrating-a-setup-of-reporting-codes-to-a-setup-of-application-specific-parameters"></a>Migration d’une configuration de codes déclaration vers une configuration de paramètres spécifiques à l’application

Cette section fournit des recommandations sur la façon de migrer votre configuration de la déclaration INTERVAT basée sur le cadre des codes de déclaration vers la configuration de la déclaration de TVA (BE) basée sur des paramètres spécifiques à l’application dans l’espace de travail **Gestion des états électroniques**.

> [!NOTE]
> Dans les exemples qui suivent, le même code de taxe de vente est utilisé pour différents types de transactions : ventes intérieures, ventes intracommunautaires, achats intérieurs, achats intracommunautaires, etc. Cette approche n’a été utilisée qu’à des fins d’illustration. Pour faciliter le rapprochement de vos taxes, nous vous recommandons de créer autant de codes de taxe de vente que possible, afin que chaque code de taxe de vente puisse identifier de manière unique un type de transaction spécifique. Ensuite, lors d’un audit fiscal, vous pourrez expliquer la source de chaque transaction en fonction du code de taxe et vous n’aurez à utiliser que des états de rapprochement de taxe de vente standard.
> 
> De plus, dans les exemples, toutes les transactions de taxe négative sont configurées de manière à être considérées comme des avoirs. Cette approche a aussi été utilisée uniquement à des fins d’illustration. Pour configurer les paramètres corrects, vous devez tenir compte des informations contenues dans la section [Notes de crédit et corrections négatives](#credit-notes-and-negative-corrections-1) plus haut dans cet article.

Les tableaux de cette section utilisent les abréviations suivantes :

- **ICA** : Acquisitions intracommunautaires
- **ICS** : Livraisons intracommunautaires

### <a name="commercial-goods-and-services-at-a-standard-rate"></a>Biens et services commerciaux à un tarif standard

Par exemple, pour le code de taxe suivant :

| Code taxe de vente | Pourcentage | Commentaire                                                                                  |
|----------------|------------|------------------------------------------------------------------------------------------|
| CommGoods      | 21         | Biens et services commerciaux commercialisés en Belgique et dans l’Union européenne (UE) |

Vous avez la configuration de codes déclaration suivante.

| **Transaction**       | **Ventes soumises à taxe** | **Taxe due** | **Vente détaxée (ICS)** | **Achats soumis à taxe** | **Taxe déductible** | **Achats en franchise** | **Importation soumise à taxe** | **Contrepartie des importations soumises à taxe** | **Taxe d’utilisation** | **Contrepartie taxe d’utilisation** |
|-------------|-------------------|-----------------------|--------------------------|-----------------------|--------------------------|------------------------|--------------------|---------------------------|-------------|--------------------|
| Facture     | 03   | 54    | 46     | 81   | 59    |    &nbsp;     | 81     | 86   | 59          | 55   |
| Avoir | 49                | 64                    | 48                       | \-81 +85               | 63                       |    &nbsp;                     | \-81 +84           | \-86                      | 61          | 62                 |

Dans ce cas, les paramètres spécifiques à l’application suivants peuvent être configurés.

| Résultat de la recherche  | Étiquette  | Ligne | Code taxe  | Classifieur de transactions |
|----------------|--------|------|-----------|------------------------|
| 03_SalesStandardRate  | 03/54 Transactions soumises au taux de 21 %  | 1    | CommGoods | Vente  |
| 49_SalesStandardRateCreditNote   | 49/64 Avoirs émis concernant des transactions soumises au taux de 21 % [03]  | 2    | CommGoods | SalesCreditNote  |
| 46_EUSales  | 46 Livraisons intracommunautaires exemptées effectuées en Belgique et ventes ABC | 3    | CommGoods | SalesExempt  |
| 48_EUSalesCreditNoteCorr  | 48 Avoirs émis et corrections négatives concernant les livraisons intracommunautaires exemptées effectuées en Belgique et ventes ABC [46] | 4    | CommGoods | SalesExemptCreditNote  |
| 81_PurchasesGoods   | 81/59 Achats de marchandises commerciales, de matières premières et de consommables (pour la base d’imposition, compte tenu des avoirs reçus et des autres corrections) | 5 | CommGoods | Achat  |
| 8185_PurchasesGoodsCreditNote   | \-81 +85/63 Avoirs reçus et corrections négatives concernant les achats de marchandises commerciales, de matières premières et de consommables | 6  | CommGoods | PurchaseCreditNote  |
| 8681_EUPurchasesGoodsUseTax  | 86/81 55/59 Acquisitions intracommunautaires de marchandises commerciales, de matières premières et de consommables effectuées en Belgique et ventes ABC : UseTax  | 7  | CommGoods | UseTax                 |
| 868184_EUPurchasesGoodsCreditNoteUseTax | \-86/81 +84/61/62 Avoirs reçus et corrections négatives concernant les achats de marchandises commerciales, de matières premières et de consommables : taxe d’utilisation | 8  | CommGoods | UseTaxCreditNote   |

### <a name="commercial-goods-and-services-at-a-reduced-rate"></a>Biens et services commerciaux à un tarif réduit

Par exemple, pour le code de taxe suivant :

| Code taxe de vente | Pourcentage | Commentaire                                                                                               |
|----------------|------------|-------------------------------------------------------------------------------------------------------|
| RedComGood     | 6          | Articles/biens (mais pas les services) qui ont une taxe réduite et qui sont commercialisés en Belgique et dans l’UE |

Vous avez la configuration de codes déclaration suivante.

| **Transaction**   | **Ventes soumises à taxe** | **Taxe due** | **Vente détaxée (ICS)** | **Achats soumis à taxe** | **Taxe déductible** | **Achats en franchise** | **Importation soumise à taxe** | **Contrepartie des importations soumises à taxe** | **Taxe d’utilisation** | **Contrepartie taxe d’utilisation** |
|-------------|-------------------|-----------------------|--------------------------|-----------------------|--------------------------|------------------------|--------------------|---------------------------|-------------|--------------------|
| Facture     | 01                | 54                    | 46                       | 81                    | 59                       |     &nbsp;                    | 81                 | 86                        | 59          | 55                 |
| Avoir | 49                | 64                    | 48                       | \-81 +85              | 63                       |      &nbsp;                   | \-81 +84           | \-86                      | 61          | 62                 |

Dans ce cas, les paramètres spécifiques à l’application suivants peuvent être configurés.

| Résultat de la recherche  | Étiquette  | Ligne | Code taxe  | Classifieur de transactions |
|----------------|--------|------|------------|------------------------|
| 01_SalesLowerReducedRate  | 01/54 Transactions soumises au taux de 6 %  | 1  | RedComGood | Vente   |
| 49_SalesLowerReducedRateCreditNote  | 49/64 Avoirs émis concernant des transactions soumises au taux de 6 % [01]  | 2  | RedComGood | SalesCreditNote   |
| 46_EUSales  | 46 Livraisons intracommunautaires exemptées effectuées en Belgique et ventes ABC | 3    | RedComGood | SalesExempt  |
| 48_EUSalesCreditNoteCorr  | 48 Avoirs émis et corrections négatives concernant les livraisons intracommunautaires exemptées effectuées en Belgique et ventes ABC [46] | 4  | RedComGood | SalesExemptCreditNote  |
| 81_PurchasesGoods  | 81/59 Achats de marchandises commerciales, de matières premières et de consommables (pour la base d’imposition, compte tenu des avoirs reçus et des autres corrections) | 5   | RedComGood | Achat    |
| 8185_PurchasesGoodsCreditNote  | \-81 +85/63 Avoirs reçus et corrections négatives concernant les achats de marchandises commerciales, de matières premières et de consommables  | 6   | RedComGood | PurchaseCreditNote  |
| 8681_EUPurchasesGoodsUseTax  | 86/81 55/59 Acquisitions intracommunautaires de marchandises commerciales, de matières premières et de consommables effectuées en Belgique et ventes ABC : UseTax  | 7  | RedComGood | UseTax                 |
| 868184_EUPurchasesGoodsCreditNoteUseTax | \-86/81 +84/61/62 Avoirs reçus et corrections négatives concernant les achats de marchandises commerciales, de matières premières et de consommables : taxe d’utilisation      | 8    | RedComGood | UseTaxCreditNote  |

### <a name="commercial-goods-for-trade-outside-the-eu"></a>Marchandises destinées au commerce hors UE

Par exemple, pour le code de taxe suivant :

| Code taxe de vente | Pourcentage | Commentaire                                                                |
|----------------|------------|------------------------------------------------------------------------|
| ComGood-3      | 21         | Marchandises commerciales importées ou exportées vers des pays tiers |

Vous avez la configuration de codes déclaration suivante.

|  **Transaction**  | **Ventes soumises à taxe** | **Taxe due**                        | **Vente détaxée (ICS)**       | **Achats soumis à taxe** | **Taxe déductible** | **Achats en franchise** | **Importation soumise à taxe** | **Contrepartie des importations soumises à taxe** | **Taxe d’utilisation** | **Contrepartie taxe d’utilisation** |
|-------------|-------------------|----------------------------------------------|--------------------------------|-----------------------|--------------------------|------------------------|--------------------|---------------------------|-------------|--------------------|
| Facture     |     &nbsp;               |             &nbsp;                                  | 47                             | 81                    | 59                       | 81                     | 81                 | 87                        | 59          | 57                 |
| Avoir |       &nbsp;             |      &nbsp;                                         | 49                             | \-81 +85              | 63                       | \-81 +85               | \-81 +85           | \-87                      | 61          | 62                 |

Dans ce cas, les paramètres spécifiques à l’application suivants peuvent être configurés.

| Résultat de la recherche  | Étiquette | Ligne | Code taxe  | Classifieur de transactions   |
|----------------|-------|------|-----------|--------------------------|
| 47_OtherExemptSales   | 47 Autres transactions exemptées et autres transactions effectuées à l’étranger | 1   | ComGood-3 | SalesExempt   |
| 49_ExemptSalesSpecialSchemeCreditNoteCorr  | 49 Avoirs émis et corrections négatives concernant des transactions soumises à un régime particulier [00]  | 2  | ComGood-3 | SalesExemptCreditNote  |
| 81_PurchasesGoods  | 81/59 Achats de marchandises commerciales, de matières premières et de consommables (pour la base d’imposition, compte tenu des avoirs reçus et des autres corrections)  | 3    | ComGood-3 | Achat  |
| 8185_PurchasesGoodsCreditNote  | \-81 +85/63 Avoirs reçus et corrections négatives concernant les achats de marchandises commerciales, de matières premières et de consommables   | 4  | ComGood-3 | PurchaseCreditNote  |
| 81_PurchasesGoods  | 81/59 Achats de marchandises commerciales, de matières premières et de consommables (pour la base d’imposition, compte tenu des avoirs reçus et des autres corrections)  | 5    | ComGood-3 | PurchaseExempt  |
| 8185_PurchasesGoodsCreditNote  | \-81 +85/63 Avoirs reçus et corrections négatives concernant les achats de marchandises commerciales, de matières premières et de consommables | 6  | ComGood-3 | PurchaseExemptCreditNote |
| 8781_OtherPurchasesImportsDeferredTaxGoodsUseTax | 87/81 57/59 Autres achats de marchandises commerciales, de matières premières et de consommables pour lesquels la TVA est due par le déclarant (importations avec report de perception) : taxe d’utilisation  | 7    | ComGood-3 | UseTax   |
| 878185_OtherPurchasesImportsDeferredTaxGoodsCNUseTax | \-87/81 +85/61/62 Avoirs reçus et corrections négatives concernant d’autres achats de marchandises commerciales, de matières premières et de consommables pour lesquels la TVA est due par le déclarant (importations avec report de perception) : taxe d’utilisation | 8  | ComGood-3 | UseTaxCreditNote    |

### <a name="services-at-a-standard-rate-and-goods-purchased-for-internal-use"></a>Services au tarif standard et marchandises achetées pour un usage interne

Par exemple, pour le code de taxe suivant :

| Code taxe de vente | Pourcentage | Commentaire                                                                                        |
|----------------|------------|------------------------------------------------------------------------------------------------|
| Service21      | 21         | Services et marchandises utilisées en interne commercialisés en Belgique, dans l’Union européenne (UE) et des pays tiers |

Vous avez la configuration de codes déclaration suivante.

| **Transaction**   | **Ventes soumises à taxe**       | **Taxe due**       | **Vente détaxée (ICS)**                                                           | **Achats soumis à taxe** | **Taxe déductible** | **Achats en franchise** | **Importation soumise à taxe** | **Contrepartie des importations soumises à taxe** | **Taxe d’utilisation** | **Contrepartie taxe d’utilisation** |
|-------------|-------------------------|-----------------------------|------------------------------------------------------------------------------------|-----------------------|--------------------------|------------------------|--------------------|---------------------------|-------------|--------------------|
| Facture     | 03                      | 54                          | 47                                                                                 | 82                    | 59                       | 82                     | 82                 |    &nbsp;                        |    &nbsp;          |     &nbsp;                |
| Avoir | 49                      | 64                          | 49                                                                                 | \-82 +85              | 63                       | \-82 +85               | \-82 +85           |      &nbsp;                      |     &nbsp;         |    &nbsp;                 |

Dans ce cas, les paramètres spécifiques à l’application suivants peuvent être configurés.

| Résultat de la recherche    | Étiquette     | Ligne | Code taxe  | Classifieur de transactions   |
|------------------|-----------|------|-----------|--------------------------|
| 03_SalesStandardRate   | 03/54 Transactions soumises au taux de 21 %  | 1  | Service21 | Vente  |
| 49_SalesStandardRateCreditNote  | 49/64 Avoirs émis concernant des transactions soumises au taux de 21 % [03]  | 2 | Service21 | SalesCreditNote  |
| 47_OtherExemptSales | 47 Autres transactions exemptées et autres transactions effectuées à l’étranger  | 3  | Service21 | SalesExempt  |
| 49_ExemptSalesSpecialSchemeCreditNoteCorr | 49 Avoirs émis et corrections négatives concernant des transactions soumises à un régime particulier [00]  | 4  | Service21 | SalesExemptCreditNote  |
| 82_PurchasesServicesMisc  | 82/59 Achats de services et de biens divers (pour la base d’imposition, compte tenu des avoirs reçus et des autres corrections) | 5   | Service21 | Achat  |
| 8285_PurchasesServicesMiscCreditNote  | \-82 +85/63 Avoirs reçus et corrections négatives concernant les achats de services et de biens divers | 6  | Service21 | PurchaseCreditNote  |
| 82_PurchasesServicesMisc  | 82/59 Achats de services et de biens divers (pour la base d’imposition, compte tenu des avoirs reçus et des autres corrections) | 7  | Service21 | PurchaseExempt  |
| 8285_PurchasesServicesMiscCreditNote   | \-82 +85/63 Avoirs reçus et corrections négatives concernant les achats de services et de biens divers | 8    | Service21 | PurchaseExemptCreditNote |

> [!NOTE]
> Dans cet exemple, ne validez pas l’achat UseTax et ne configurez pas **UseTax** dans les paramètres spécifiques à l’application. Utilisez la transaction **achats imposables** ou **achats détaxés** pour l’achat de services en dehors de la Belgique.

### <a name="capital-goods"></a>Biens d’équipement

Par exemple, pour le code de taxe suivant :

| Code taxe  | Pourcentage | Commentaire                                                 |
|-----------|------------|---------------------------------------------------------|
| Capital21 | 21         | Biens d’investissement commercialisés en Belgique et dans l’UE |

Vous avez la configuration de codes déclaration suivante.

| **Transaction**            | **Ventes soumises à taxe** | **Taxe due**       | **Vente détaxée (ICS)**             | **Achats soumis à taxe** | **Taxe déductible** | **Achats en franchise** | **Importation soumise à taxe** | **Contrepartie des importations soumises à taxe** | **Taxe d’utilisation** | **Contrepartie taxe d’utilisation** |
|-------------|-------------------|-----------------------------|--------------------------------------|-----------------------|--------------------------|------------------------|--------------------|---------------------------|-------------|--------------------|
| Facture     | 03                | 54                          | 46                                   | 83                    | 59                |     &nbsp;   | 83                 | 86                        | 59          | 55                 |
| Avoir | 49                | 64                          | 48                                   | \-83 +85              | 63      |        &nbsp;            | \-83 +84           | \-86                      | 61          | 62                 |

Dans ce cas, les paramètres spécifiques à l’application suivants peuvent être configurés.

| Résultat de la recherche  | Étiquette  | Ligne | Code taxe  | Classifieur de transactions |
|----------------|--------|------|-----------|------------------------|
| 03_SalesStandardRate   | 03/54 Transactions soumises au taux de 21 %  | 1    | Capital21 | Vente  |
| 49_SalesStandardRateCreditNote | 49/64 Avoirs émis concernant des transactions soumises au taux de 21 % [03] | 2    | Capital21 | SalesCreditNote   |
| 46_EUSales | 46 Livraisons intracommunautaires exemptées effectuées en Belgique et ventes ABC  | 3    | Capital21 | SalesExempt  |
| 48_EUSalesCreditNoteCorr  | 48 Avoirs émis et corrections négatives concernant les livraisons intracommunautaires exemptées effectuées en Belgique et ventes ABC [46] | 4    | Capital21 | SalesExemptCreditNote  |
| 83_PurchasesCapitalGoods  | 83/59 Achats de services et de biens d’équipement (pour la base d’imposition, compte tenu des avoirs reçus et des autres corrections) | 5  | Capital21 | Achat  |
| 8385_PurchasesCapitalGoodsCreditNote| \-83 +85/63 Avoirs reçus et corrections négatives  | 6    | Capital21 | PurchaseCreditNote   |
| 8683_EUPurchasesCapitalGoodsUseTax   | 86/83 55/59 Acquisitions intracommunautaires de biens d’équipement effectuées en Belgique et ventes ABC : taxe d’utilisation  | 7  | Capital21 | UseTax   |
| 868384_EUPurchasesCapitalGoodsCreditNoteUseTax | \-86/83 +84/61/62 Avoirs reçus et corrections négatives concernant les achats de biens d’équipement : UseTax  | 8  | Capital21 | UseTaxCreditNote  |

### <a name="special-services"></a>Services spéciaux

Par exemple, pour le code de taxe suivant :

| Code taxe de vente | Pourcentage | Commentaire                                                         |
|----------------|------------|-----------------------------------------------------------------|
| SpecServ       | 0          | Services spéciaux, où la taxe sera payée par le destinataire |

Vous avez la configuration de codes déclaration suivante.

| **Transaction**   | **Ventes soumises à taxe** | **Taxe due** | **Vente détaxée (ICS)** | **Achats soumis à taxe** | **Taxe déductible** | **Achats en franchise** | **Importation soumise à taxe** | **Contrepartie des importations soumises à taxe** | **Taxe d’utilisation** | **Contrepartie taxe d’utilisation** |
|-------------|-------------------|-----------------------|--------------------------|-----------------------|--------------------------|------------------------|--------------------|---------------------------|-------------|--------------------|
| Facture     |     &nbsp;               |       &nbsp;                 | 45         |   &nbsp;     |     &nbsp;        |      &nbsp;     | 82                 | 87                        |   &nbsp;  |     &nbsp;    |
| Avoir |    &nbsp;       |    &nbsp;      | 49           |      &nbsp;     |      &nbsp;    |      &nbsp;       | \-82 +85           | \-87             |   &nbsp;    |    &nbsp;     |

Dans ce cas, les paramètres spécifiques à l’application suivants peuvent être configurés.

| Résultat de la recherche   | Étiquette   | Ligne | Code taxe  | Classifieur de transactions |
|-----------------|---------|------|-----------|------------------------|
| 46_EUSales   | 46 Livraisons intracommunautaires exemptées effectuées en Belgique et ventes ABC  | 3    | Capital21 | SalesExempt    |
| 48_EUSalesCreditNoteCorr  | 48 Avoirs émis et corrections négatives concernant les livraisons intracommunautaires exemptées effectuées en Belgique et ventes ABC [46]  | 4    | Capital21 | SalesExemptCreditNote  |
| 8782_OtherPurchasesDomesticReverseChargeMiscUseTax     | 87/82 56/59 Autres achats de biens divers pour lesquels la TVA est due par le déclarant (autoliquidation nationale) : taxe d’utilisation    | 7    | Capital21 | UseTax  |
| 878285_OtherPurchasesDomesticReverseChargeMiscCNUseTax | \-87/82 +85/61/62 Avoirs reçus et corrections négatives concernant d’autres achats de biens divers pour lesquels la TVA est due par le déclarant (autoliquidation nationale) : UseTax | 8    | Capital21 | UseTaxCreditNote  |


## <a name="examples-of-posting-and-reporting"></a>Exemples de validation et de génération d’états

Les exemples de cette section sont fournis pour la configuration des paramètres spécifiques à l’application pour la section [Biens et services commerciaux à un tarif standard](#commercial-goods-and-services-at-a-standard-rate) plus haut dans cet article.

### <a name="example-1-sale-in-belgium"></a>Exemple 1 : Vente en Belgique

Cet exemple montre une vente en Belgique, où le montant net de la facture est de 1 000 euros plus 21 % de TVA.

**Validation**

| Compte            | Débit    | Crédit   |
|--------------------|----------|----------|
| Client           | 1,210.00 |  &nbsp;         |
| Vente               |    &nbsp;       | 1,000.00 |
| Taxe à l’exportation |   &nbsp;        | 210.00   |

**Génération d’états**

| Champ de la déclaration de taxe | Montant   |
|---------------------------|----------|
| Champ 03                  | 1,000.00 |
| Champ 54                  | 210.00   |

### <a name="example-2-credit-note-for-a-sale-in-belgium"></a>Exemple 2 : Avoir pour une vente en Belgique

Cet exemple montre un avoir pour une vente en Belgique, où le montant net est de 1 000 euros plus 21 % de TVA.

**Validation**

| Compte            | Débit    | Crédit   |
|--------------------|----------|----------|
| Client           |   &nbsp;        | 1,210.00 |
| Vente               | 1,000.00 |   &nbsp;        |
| Taxe à l’exportation | 210.00   |    &nbsp;       |

**Génération d’états**

| Champ de la déclaration de taxe | Montant   |
|---------------------------|----------|
| Champ 49                  | 1,000.00 |
| Champ 64                  | 210.00   |

### <a name="example-3-purchase-in-belgium"></a>Exemple 3 : Achat en Belgique

Cet exemple montre un achat en Belgique, où le montant net de la facture est de 1 000 euros plus 21 % de TVA.

**Validation**

| Compte            | Débit    | Crédit   |
|--------------------|----------|----------|
| Fournisseur             |  &nbsp;         | 1,210.00 |
| Charge               | 1,000.00 |  &nbsp;         |
| Taxe à l’importation | 210.00   |    &nbsp;       |

**Génération d’états**

| Champ de la déclaration de taxe | Montant   |
|---------------------------|----------|
| Champ 81                  | 1,000.00 |
| Champ 59                  | 210.00   |

### <a name="example-4-credit-note-for-a-purchase-in-belgium"></a>Exemple 4 : Avoir pour un achat en Belgique

Cet exemple montre un avoir pour un achat en Belgique, où le montant net est de 1 000 euros plus 21 % de TVA.

**Validation**

| Compte            | Débit    | Crédit   |
|--------------------|----------|----------|
| Fournisseur             | 1,210.00 |  &nbsp;         |
| Charge               |  &nbsp;         | 1,000.00 |
| Taxe à l’importation |   &nbsp;        | 210.00   |

**Génération d’états**

| Champ de la déclaration de taxe | Montant     |
|---------------------------|------------|
| Champ 81                  | \-1,000.00 |
| Champ 85                  | 1,000.00   |
| Champ 63                  | 210.00     |

### <a name="example-5-intra-community-acquisition"></a>Exemple 5 : Acquisition intracommunautaire

Cet exemple montre une acquisition intracommunautaire (c’est-à-dire une acquisition auprès d’un fournisseur qui se trouve dans l’UE mais en dehors de la Belgique), où le montant net de la facture est de 1 000 euros. La TVA belge de 21 % devra être auto-comptabilisée.

**Validation**

| Compte                                  | Débit    | Crédit   |
|------------------------------------------|----------|----------|
| Fournisseur                                   |   &nbsp;        | 1,000.00 |
| Charge                                     | 1,000.00 |   &nbsp;        |
| Taxe à l’importation (auto-comptabilisée)        | 210.00   |   &nbsp;        |
| Contrepartie taxe à l’importation (auto-comptabilisée) |  &nbsp;         | 210.00   |

**Génération d’états**

| Champ de la déclaration de taxe | Montant   |
|---------------------------|----------|
| Champ 81                  | 1,000.00 |
| Champ 86                  | 1,000.00 |
| Champ 59                  | 210.00   |
| Champ 55                  | 210.00   |

### <a name="example-6-credit-note-for-an-intra-community-acquisition"></a>Exemple 6 : Avoir pour une acquisition intracommunautaire

Cet exemple montre un avoir pour une acquisition intracommunautaire (c’est-à-dire une acquisition auprès d’un fournisseur qui se trouve dans l’UE mais en dehors de la Belgique), où le montant net de l’avoir est de 1 000 euros. La TVA belge de 21 % devra être auto-comptabilisée.

**Validation**

| Compte                                   | Débit    | Crédit   |
|-------------------------------------------|----------|----------|
| Fournisseur                                    | 1,000.00 | &nbsp;          |
| Charge                                      | &nbsp;          | 1,000.00 |
| Taxe à l’importation (auto-comptabilisée)         |   &nbsp;        | 210.00   |
| Déduction de taxe à l’importation (auto-comptabilisée) | 210.00   |     &nbsp;      |

**Génération d’états**

| Champ de la déclaration de taxe | Montant     |
|---------------------------|------------|
| Champ 81                  | \-1,000.00 |
| Champ 86                  | \-1,000.00 |
| Champ 84                  | 1,000.00   |
| Champ 61                  | 210.00     |
| Champ 62                  | 210.00     |

### <a name="example-7-intra-community-supply"></a>Exemple 7 : Approvisionnement intracommunautaire

Cet exemple montre un approvisionnement intracommunautaire (c’est-à-dire un approvisionnement à un client qui se trouve dans un autre état membre de l’UE et qui possède un numéro d’enregistrement fiscal dans cet état membre), où le montant net de la facture est de 1 000 euros et est hors taxe.

**Validation**

| Compte  | Débit    | Crédit   |
|----------|----------|----------|
| Client | 1,000.00 | &nbsp;          |
| Vente     |   &nbsp;        | 1,000.00 |

**Génération d’états**

| Champ de la déclaration de taxe | Montant   |
|---------------------------|----------|
| Champ 46                  | 1,000.00 |

### <a name="example-8-credit-note-for-intra-community-supply"></a>Exemple 8 : Avoir pour un approvisionnement intracommunautaire

Cet exemple montre un avoir pour un approvisionnement intracommunautaire (c’est-à-dire un approvisionnement à un client qui se trouve dans un autre état membre de l’UE et qui possède un numéro d’enregistrement fiscal dans cet état membre), où le montant net de l’avoir est de 1 000 euros.

**Génération d’états**

| Champ de la déclaration de taxe | Montant   |
|---------------------------|----------|
| Champ 48                  | 1,000.00 |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
