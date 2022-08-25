---
title: Déclaration de TVA (France)
description: Cet article explique comment configurer et générer un état pour la France, qui peut être utilisé pour effectuer une déclaration de taxe sur la valeur ajoutée (TVA).
author: AdamTrukawka
ms.date: 03/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: France
ms.author: atrukawk
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: AX 10.0.21
ms.openlocfilehash: f0617a2850ead91782006ff5a9a10c3058c4c000
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275899"
---
# <a name="vat-declaration-france"></a>Déclaration de TVA (France)

[!include [banner](../includes/banner.md)]

Cet article décrit comment configurer et générer un état pour la France, qui peut être utilisé pour effectuer une déclaration de taxe sur la valeur ajoutée (TVA) dans le portail en ligne [www.impots.gouv.fr](http://www.impots.gouv.fr) en utilisant le canal d’échange de formulaires informatisés (EFI).

Pour générer automatiquement l’état, vous devez d’abord créer suffisamment de codes de taxe afin de conserver une comptabilité TVA distincte pour chaque case de la déclaration de TVA. De plus, dans les paramètres spécifiques à l’application du format de gestion des états électroniques (ER) pour la déclaration de TVA, vous devez associer des codes de taxe avec le résultat des recherches des cases de déclaration de TVA.

Pour la France, vous devez configurer trois recherches :

- Recherche d’opérations
- Recherche de champ d’état
- Recherche pour Monaco

Pour plus d’informations sur la configuration des paramètres spécifiques à l’application, consultez la section [Configurer les paramètres spécifiques à l’application pour les champs de déclaration de TVA](#set-up-application-specific-parameters-for-vat-declaration-fields) plus loin dans cet article.

Dans les tableaux suivants, la colonne **Résultat de la recherche** affiche le résultat de la recherche préconfiguré pour une ligne de déclaration de TVA spécifique dans le format de déclaration de TVA. Utilisez ces informations pour associer correctement les codes de taxe avec le résultat de la recherche, puis avec la ligne de déclaration de TVA.

### <a name="vat-declaration-preview-overview"></a><a name="vat-declaration-preview-overview"></a>Vue d’ensemble de l’aperçu de la déclaration de TVA

L’aperçu de la déclaration de TVA en France contient les informations suivantes.

**SECTION A - MONTANT DES OPÉRATIONS RÉALISÉES**

**OPÉRATIONS IMPOSABLES**

| Ligne | Boîte  | Description | Recherche | Résultat de la recherche |
|------|------|-------------|--------|---------------|
| A1   | 0979 | Ventes et services | Recherche d’opérations | TaxableSalesServices |
| A2   | 0981 | Autres transactions imposables | Recherche d’opérations | OtherTaxableTransactions |
| A3   | 0044 | Achats de services intracommunautaires | Recherche d’opérations | EUPurchaseServices |
| A4   | 0056 | Importations (autres que de produits pétroliers) | Recherche d’opérations | TaxableImports |
| A5   | 0051 | Prélèvements du régime fiscal suspensif (produits autres que pétroliers) | Recherche d’opérations | TaxableWithdrawalsSuspensiveTaxRegime |
| B1   | 0048 | Libérations pour la consommation des produits pétroliers | Recherche d’opérations | TaxablePetroleumProductsReleasesForConsumption |
| B2   | 0031 | Acquisitions intracommunautaires | Recherche d’opérations | EUPurchase (La ligne 17 est également affectée.) |
| B3   | 0030 | Fournitures d’électricité, de gaz naturel, de chaleur ou de froid soumises à taxes en France (taxe au preneur) | Recherche d’opérations | TaxableElectricityGasHeatCold |
| B4   | 0040 | Achats de biens ou de services auprès d’une personne soumise à taxe et non établie en France | Recherche d’opérations | PurchasesFromPersonNotEstablished |
| B5   | 0036 | Régularisations | Recherche d’opérations | TaxableRegularizations |

**OPÉRATIONS NON IMPOSABLES**

| Ligne | Boîte  | Description | Recherche | Résultat de la recherche |
|------|------|-------------|--------|---------------|
| E1   | 0032 | Exportations hors Union Européenne (UE) | Recherche d’opérations | ExportsOutsideEU |
| E2   | 0033 | Autres transactions non imposables | Recherche d’opérations | OtherNonTaxableTransactions |
| E3   | 0047 | Ventes à distance imposables dans un autre État membre au profit de personnes non soumises à taxe (ventes entreprise-client \[B2C\]) | Recherche d’opérations | EUDistanceB2CSales |
| E4   | 0052 | Importations (autres que de produits pétroliers) | Recherche d’opérations | NonTaxableImports |
| E5   | 0053 | Prélèvements du régime fiscal suspensif (produits autres que pétroliers) | Recherche d’opérations | WithdrawalsFromSuspensiveTaxRegime |
| E6   | 0054 | Importations placées sous un régime de taxe suspensif (autres que de produits pétroliers) | Recherche d’opérations | ImportsSuspensiveTaxRegime |
| F1   | 0055 | Acquisitions intracommunautaires | Recherche d’opérations | NonTaxableEUPurchase |
| F2   | 0034 | Livraisons intracommunautaires à une personne soumise à taxe (ventes interentreprises \[B2B\]) | Recherche d’opérations | EUSales |
| F3   | 0029 | Fournitures d’électricité, de gaz naturel, de chaleur ou de froid non soumises à taxe en France | Recherche d’opérations | ElectricityGasHeatColdNotTaxable |
| F4   | 0049 | Libérations pour la consommation des produits pétroliers | Recherche d’opérations | NonTaxablePetroleumProductsReleasesForConsumption |
| F5   | 0050 | Importations de produits pétroliers placés sous un régime de taxe suspensif | Recherche d’opérations | ImportsPetroleumProductsSuspensiveTaxRegime |
| F6   | 0037 | Achats détaxés | Recherche d’opérations | TaxFreePurchases |
| F7   | 0043 | Achats de biens ou de services auprès d’une personne soumise à taxe et non établie en France | Recherche d’opérations | SalesByPersonNotEstablished |
| F8   | 0039 | Régularisations | Recherche d’opérations | NotTaxableRegularizations |

**SECTION B - CALCUL DE LA TVA À PAYER**

**TVA BRUTE**

**Opérations réalisées en France hors produits pétroliers et importations**

| Ligne | Boîte  | Description | Recherche | Résultat de la recherche |
|------|------|-------------|--------|---------------|
| 08   | 0207 | Taux standard de 20 % | Recherche de champ de rapport | <p>TVADueFranceStandard</p><p>UseTaxFranceStandard (La ligne 20 est également affectée.)</p> |
| 09   | 0105 | Taux réduit de 5,5 % | Recherche de champ de rapport | <p>VATDueFranceReduced</p><p>UseTaxFranceReduced (La ligne 20 est également affectée.)</p> |
| 9B   | 0151 | Taux réduit de 10 % | Recherche de champ d’état | <p>VATDueFranceReduced2</p><p>UseTaxFranceReduced2 (La ligne 20 est également affectée.)</p> |

**Opérations réalisées dans les départements d’Outre-Mer hors produits pétroliers et importations**

| Ligne | Boîte  | Description | Recherche | Résultat de la recherche |
|------|------|-------------|--------|---------------|
| 10   | 0201 | Taux standard de 8,5 % | Recherche de champ de rapport | <p>VATDueOverseasStandard</p><p>UseTaxOverseasStandard (La ligne 20 est également affectée.)</p> |
| 11   | 0100 | Taux réduit de 2,1 % | Recherche de champ d’état | <p>VATDueOverseasReduced</p><p>UseTaxOverseasReduced (La ligne 20 est également affectée.</p> |

**Transactions soumises à un autre taux de taxe (France ou départements d’outre-mer) hormis les produits pétroliers et les importations**

| Ligne | Boîte  | Description | Recherche | Résultat de la recherche |
|------|------|-------------|--------|---------------|
| 13   | 0900 | Anciens taux | Recherche de champ de rapport | <p>VATDueOldRates</p><p>UseTaxOldRates (La ligne 20 est également affectée.)</p> |
| 14   | 0950 | Transactions soumises à un taux de taxe spécifique (La déclaration est faite au niveau de la note 3310 A.) | Recherche de champ d’état | <p>VATDueSpecificRate</p><p>UseTaxSpecificRate (La ligne 20 est également affectée.)</p> |

**Produits pétroliers**

| Ligne | Boîte  | Description | Recherche | Résultat de la recherche |
|------|------|-------------|--------|---------------|
| P1   | 0208 | Taux standard de 20 % sur les produits pétroliers | Recherche de champ de rapport | <p>VATDuePetroleumStandard</p><p>UseTaxPetroleumStandard (Les lignes 20 et 2E sont également affectées.)</p> |
| P2   | 0152 | Taux réduit de 13 % sur les produits pétroliers | Recherche de champ de rapport | <p>VATDuePetroleumReduced</p><p>UseTaxPetroleumReduced (Les lignes 20 et 2E sont également affectées.)</p> |

**Importations**

| Ligne | Boîte  | Description | Recherche | Résultat de la recherche |
|------|----- |-------------|--------|---------------|
| I1   | 0210 | Taux normal 20 % | Recherche de champ de rapport | <p>VATDueImportsFranceStandard</p><p>UseTaxImportsFranceStandard (Les lignes 20 et 24 sont également affectées.)</p> |
| I2   | 0211 | Taux réduit 10 % | Recherche de champ de rapport | <p>VATDueImportsFranceReduced2</p><p>UseTaxImportsFranceReduced2 (Les lignes 20 et 24 sont également affectées.)</p> |
| I3   | 0212 | Taux réduit 8,5 % | Recherche de champ de rapport | <p>VATDueImportsOverseasStandard</p><p>UseTaxImportsOverseasStandard (Les lignes 20 et 24 sont également affectées.)</p> |
| I4   | 0213 | Taux réduit 5,5 % | Recherche de champ de rapport | <p>VATDueImportsFranceReduced</p><p>UseTaxImportsFranceReduced (Les lignes 20 et 24 sont également affectées.)</p> |
| I5   | 0214 | Taux réduit 2,1 % | Recherche de champ de rapport | <p>VATDueImportsOverseasReduced</p><p>UseTaxImportsOverseasReduced (Les lignes 20 et 24 sont également affectées.)</p> |
| I6   | 0215 | Taux réduit 1,05 % | Recherche de champ de rapport | <p>VATDueImportsSpecificRate</p><p>UseTaxImportsSpecificRate (Les lignes 20 et 24 sont également affectées.)</p> |

**Calcul TVA**

| Ligne | Boîte  | Description | Recherche | Résultat de la recherche |
|------|----- |-------------|--------|---------------|
| 15   | 0600 | TVA précédemment déduite qui doit être restituée | Recherche de champ de rapport | <p>VATDeductedToBeReturned</p><p>VATDeductedToBeReturnedRegularizations</p><p>VATDeductedToBeReturnedPetroleum</p><p>VATDeductedToBeReturnedImports</p> |
| 15   | 0600 | (Y compris la TVA sur les produits pétroliers) | Recherche de champ de rapport | VATDeductedToBeReturnedPetroleum |
| 15   | 0600 | (y compris la TVA sur les produits importés, à l’exception des produits pétroliers) | Recherche de champ de rapport | VATDeductedToBeReturnedImports |
| 5B   | 0602 | Montants à ajouter, y compris les acomptes de vacances (exprimés en euros) | Recherche de champ de rapport | VATCorrectionAmountToBeAdded |
| 16   | Non applicable | Total TVA brute due (lignes 08 à 5B) | Total | Total du montant de la taxe des lignes 08 + 09 + 9B + 10 + 11 + 13 + 14 + P1 + P2 + I1 + I2 + I3 + I4 + I5 + I6 + 15 + 5B |
| 7C   | 0046 | TVA comprise sur les importations bénéficiant du régime de taxe au preneur | Total | Total du montant de la taxe des lignes I1 + I2 + I3 + I4 + I5 + I6 |
| 17   | 0035 | Dont TVA sur les acquisitions intracommunautaires | Recherche d’opérations | EUPurchase (La ligne B2 est également affectée.) |
| 18   | 0038 | Dont TVA sur transactions à destination de Monaco | Recherche pour Monaco | Monaco |

**TVA DÉDUCTIBLE**

| Ligne | Boîte  | Description | Recherche | Résultat de la recherche |
|------|------|-------------|--------|---------------|
| 19   | 0703 | Propriété constituant des immobilisations | Recherche de champ d’état | VATDeductionPropertyCapitalAssets |
| 20   | 0702 | Autres biens et services | Recherche de champ d’état | <p>VATDeductionOtherGoodsServices</p><p>VATDeductionOtherGoodsServicesImports (La ligne 24 est également affectée.)</p><p>VATDeductionOtherGoodsServicesPetroleum (La ligne 2E est également affectée.)</p><p>VATDeductionOtherGoodsServicesImportPetroleum (Les lignes 24 et 2E sont également affectées.)</p><p>UseTaxFranceStandard (La ligne 08 est également affectée.)</p><p>UseTaxFrancePetroleumStandard (Les lignes P1 et 2E sont également affectées.)</p><p>UseTaxFranceReduced (La ligne 09 est également affectée.)</p><p>UseTaxFranceReduced2 (La ligne P2 est également affectée.)</p><p>UseTaxFrancePetroleumReduced (Les lignes 9C et 2E sont également affectées.)</p><p>UseTaxOverseasStandard (La ligne 10 est également affectée.)</p><p>UseTaxOverseasReduced (La ligne 11 est également affectée.)</p><p>UseTaxOldRates (La ligne 13 est également affectée.)</p><p>UseTaxSpecificRate (La ligne 14 est également affectée.)</p><p>UseTaxPetroleumStandard (Les lignes P1 et 2E sont également affectées.)</p><p>UseTaxPetroleumReduced (Les lignes P2 et 2E sont également affectées.)</p><p>UseTaxImportsOverseasStandard (Les lignes I3 et 24 sont également affectées.)</p><p>UseTaxImportsFranceReduced (Les lignes I4 et 24 sont également affectées.)</p><p>UseTaxImportsOverseasReduced (Les lignes I5 et 24 sont également affectées.)</p><p>UseTaxImportsSpecificRate (Les lignes I6 et 24 sont également affectées.)</p> |
| 21   | 0059 | Autre TVA à déduire | Recherche de champ de rapport | VATDeductionTaxableRegularizations |
| 22   | 8001 | Crédit qui a été reporté et qui figurait en ligne 27 de la déclaration précédente | Non applicable | L’utilisateur définit la valeur dans une boîte de dialogue. |
| 2C   | 0603 | Montants à imputer, y compris les acomptes de vacances (exprimés en euros) | Recherche de champ de rapport | VATDeductionAmountsToBeCharged |
| 22A  | Non applicable | Coefficient de taxe unique applicable pour la période, si différent | Non applicable | L’utilisateur définit la valeur dans une boîte de dialogue. |
| 23   | Non applicable | Total TVA déductible (lignes 19 à 2C) | Non applicable | Total des lignes 19 + 20 + 21 + 22 + 2C |
| 24   | 0710 | Dont TVA déductible sur importations | Non applicable | <p>VATDeductionOtherGoodsServicesImports (La ligne 20 est également affectée.)</p><p>VATDeductionOtherGoodsServicesImportPetroleum (Les lignes 20 et 2E sont également affectées.)</p><p>UseTaxImportsOverseasStandard (Les lignes I3 et 20 sont également affectées.)</p><p>UseTaxImportsFranceReduced (Les lignes I4 et 20 sont également affectées.)</p><p>UseTaxImportsOverseasReduced (Les lignes I5 et 20 sont également affectées.)</p><p>UseTaxImportsSpecificRate (Les lignes I6 et 20 sont également affectées.)</p> |
| 2E   | 0711 | Dont TVA déductible sur les produits pétroliers | Non applicable | <p>VATDeductionOtherGoodsServicesImportPetroleum (Les lignes 20 et 24 sont également affectées.)</p><p>UseTaxFrancePetroleumReduced (Les lignes 9C et 20 sont également affectées.)</p><p>VATDeductionOtherGoodsServicesPetroleum (La ligne 20 est également affectée.)</p><p>UseTaxFrancePetroleumReduced (Les lignes 9C et 20 sont également affectées.)</p><p>UseTaxFrancePetroleumStandard (Les lignes 8A et 20 sont également affectées.)</p><p>UseTaxPetroleumStandard (Les lignes P1 et 20 sont également affectées.)</p><p>UseTaxPetroleumReduced (Les lignes P2 et 20 sont également affectées.)</p> |

**CRÉDIT/TAXE EXIGIBLE**

| Ligne | Boîte  | Description | Résultat de la recherche |
|------|------|-------------|---------------|
| 25   | 0705 | Crédit de TVA (ligne 23 - ligne 16) | Total : lignes 23 – 16 |
| 26   | 8002 | Remboursement de crédit demandé | L’utilisateur définit la valeur dans une boîte de dialogue. |
| AA   | 8005 | Crédit de TVA qui est transféré à la société mère du groupe | L’utilisateur définit la valeur dans une boîte de dialogue. |
| 27   | 8003 | Crédit à reporter (ligne 25 - ligne 26 - ligne AA). Ce montant est à reporter ligne 22 du prochain retour. | Total : lignes 25 – 26 – AA |
| 28   | Non applicable | TVA nette due (ligne 16 - ligne 23) | Total : lignes 16 – 23 |
| 29   | 9979 | Taxes assimilées | L’utilisateur définit une valeur dans une boîte de dialogue. |
| AB   | 9991 | Total exigible payé par la société mère du groupe sur la déclaration de synthèse | L’utilisateur définit une valeur dans une boîte de dialogue. |
| 32   | Non applicable | Total exigible (ligne 28 + ligne 29 – ligne AB) | Total : lignes 28 + 29 – AA |

### <a name="note-about-purchase-reverse-charge-vat"></a>Remarque concernant la taxe au preneur sur les achats

Si vous configurez des codes de taxe pour valider la taxe au preneur entrante en utilisant la taxe d’utilisation, associez vos codes de taxe avec le résultat de la recherche **Champ d’état** qui contient « UseTax » dans le nom.

Vous pouvez également configurer deux codes de taxe distincts : un pour la TVA due et un pour la déduction de la TVA. Associez ensuite chaque code avec l’état de recherche approprié de la recherche **Champ d’état**.

**Exemple**

Pour un achat soumis à taxe d’électricité, de gaz, de chaud ou de froid avec une taxe au preneur, configurez le code de taxe **UT\_S\_RC** avec la taxe d’utilisation. Associez ensuite le code avec le résultat de recherche **UseTaxTaxableElectricityGasHeatCold** de la recherche **Opération** et le résultat de recherche **UseTaxFranceStandard** de la recherche **Champ d’état**. Dans ce cas, les montants qui utilisent le code de taxe **UT\_S\_RC** sera reflété sur la ligne 3A (par le biais de la recherche **Opération**), et sur les lignes 08 et 20 (en utilisant la recherche **Champ d’état**).

Vous pouvez également configurer deux codes de taxe :

- **VAT\_S\_RC**, qui a une valeur de taux de taxe de -20 %
- **InVAT\_S\_RC**, qui a une valeur de taux de taxe de 20 %

Associez ensuite les codes avec les résultats de recherche de la manière suivante :

- Associez **VAT\_S\_RC** au résultat de recherche **TaxableElectricityGasHeatCold** de la recherche **Opération** et au résultat de recherche **VATDueFranceStandard** de la recherche **Champ d’état**.
- Associez **InVAT\_S\_RC** au résultat de recherche **VATDeductionOtherGoodsServices** de la recherche **Champ d’état**.

Dans ce cas, les montants qui utilisent le code de taxe **VAT\_S\_RC** seront reflétés sur les lignes 3A (par le biais de la recherche **Opération**), et 08 (par le biais de la recherche **Champ d’état**). Les montants qui utilisent le code de taxe **InVAT\_S\_RC** seront reflétés sur la ligne 20 (par le biais de la recherche **Champ d’état**).

Pour plus d’informations sur la configuration de la taxe au preneur, consultez [Taxes au preneur](emea-reverse-charge.md).

## <a name="set-up-a-vat-declaration-preview-for-france"></a>Paramétrer un aperçu de la déclaration de TVA pour la France

### <a name="import-er-configurations"></a>Importer les configurations ER

1. Ouvrez l’espace de travail **Gestion des états électroniques**.
2. Importez la version suivante ou ultérieure de ce format ER :

    - Déclaration de TVA Excel (FR) version 85.15

### <a name="set-up-application-specific-parameters-for-vat-declaration-fields"></a><a name="set-up-application-specific-parameters-for-vat-declaration-fields"></a>Configurer les paramètres spécifiques à l’application pour les champs de déclaration de TVA

Pour générer automatiquement un état d’aperçu de la déclaration de TVA dans Microsoft Excel, associez les codes de taxe dans l’application aux résultats de recherche dans la configuration ER.

> [!NOTE]
> Nous vous recommandons d’activer la fonctionnalité, **Utiliser les paramètres spécifiques à l’application des versions précédentes de formats de rapport électronique** dans l’espace de travail **Gestion des fonctionnalités**. Lorsque cette fonctionnalité est activée, les paramètres configurés pour la version antérieure d’un format ER deviennent automatiquement applicables pour la version ultérieure du même format. Si cette fonctionnalité n’est pas activée, vous devez configurer explicitement les paramètres spécifiques à l’application pour chaque version de format. La fonctionnalité, **Utiliser les paramètres spécifiques à l’application des versions précédentes de formats de rapport électronique** est disponible dans l’espace de travail **Gestion des fonctionnalités** à partir de la version Finance 10.0.23. Pour plus d’informations sur la configuration des paramètres d’un format ER pour chaque entité juridique, voir [Définir les paramètres d’un format de gestion des états électroniques par entité juridique](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-set-up.md).

#### <a name="set-up-operations"></a>Paramétrer des opérations

Suivez ces étapes pour définir quels codes de taxe génèrent quelles cases dans la section A « MONTANT DES OPÉRATIONS EFFECTUÉES ».

1. Accédez à **Espaces de travail** \> **Gestion des états électroniques** et sélectionnez **Configurations des états**.
2. Sélectionnez la configuration **Déclaration de TVA Excel (FR)**, puis sélectionnez **Configurations** \> **Configuration des paramètres spécifiques à l’application** pour ouvrir la page **Paramètres spécifiques à l’application**.
3. Sur la page **Paramètres spécifiques à l’application**, dans le raccourci **Recherches**, sélectionnez **Recherche d’opération**.
4. Dans le raccourci **Conditions**, définissez les champs suivants pour associer les codes de taxe et les opérations.

    | Champ | Description |
    |-------|-------------|
    | Résultat de la recherche | Sélectionnez l’opération à paramétrer. Pour plus d’informations sur les opérations et leur affectation aux lignes de déclaration de TVA, consultez la section [Vue d’ensemble de l’aperçu de la déclaration de TVA](#vat-declaration-preview-overview) plus haut dans cet article. |
    | Code de taxe | Permet de sélectionner le code de taxe à associer à l’opération. Les transactions de taxe validées qui utilisent le code de taxe sélectionné seront collectées dans la case de déclaration appropriée. Nous vous recommandons de séparer les codes de taxe de telle sorte qu’un code de taxe ne génère des montants que dans une seule case de déclaration. |
    | Classifieur de transactions | <p>Si vous avez créé suffisamment de codes de taxe pour déterminer une case de déclaration, sélectionnez **\*Non vide\***. Si vous n’avez pas créé suffisamment de codes de taxe pour qu’un code de taxe ne génère des montants que dans une seule case de déclaration, configurez un classifieur de transaction. Les classifieurs de transactions suivants sont disponibles :</p><ul><li>**Achats**</li><li>**PurchaseExempt** (achat exonéré de taxe)</li><li>**PurchaseReverseCharge** (taxe déductible provenant d’une taxe au preneur sur achat)</li><li>**Ventes**</li><li>**SalesExempt** (vente exonérée de taxe)</li><li>**SalesReverseCharge** (taxe exigible provenant d’une taxe au preneur sur achat ou vente)</li><li>**Taxe d’utilisation**</li></ul><p>Pour chaque classifieur de transaction, un classifieur pour l’avoir est également disponible. Par exemple, l’un de ces classifieurs est **PurchaseCreditNote** (avoir sur achat).</p> |

    > [!NOTE]
    > Assurez-vous d’associer tous les codes de taxe aux résultats de recherche. Si des codes de taxe ne doivent pas générer de valeurs dans la section A, associez-les au résultat de recherche **Autre**.

    ![Opérations des paramètres de l’application.](media/5121ad123182da7ffea8892f687fef34.png)

#### <a name="set-up-report-fields"></a>Paramétrer des champs d’état

Suivez ces étapes pour définir quels codes de taxe génèrent quelles cases dans la section B « CALCUL DE LA TVA À PAYER ».

1. Sur la page **Paramètres spécifiques à l’application**, dans le raccourci **Recherches**, sélectionnez **Recherche de champ d’état**.
2. Dans le raccourci **Conditions**, associez les codes de taxe et les champs d’état.

    > [!NOTE] 
    > Assurez-vous d’associer tous les codes de taxe aux résultats de recherche. Si des codes de taxe ne doivent pas générer de valeurs dans la section B, associez-les au résultat de recherche **Autre**.

    ![Champs de l’état des paramètres d’application.](media/54cd612e95ccd127c4de57c9281661e0.png)

#### <a name="set-up-sales-tax-codes-for-monaco"></a>Paramétrer des codes de taxe pour Monaco

Suivez ces étapes pour définir quels codes de taxe génèrent le montant dans la case 18 **TVA comprise sur les transactions vers Monaco**.

1. Sur la page **Paramètres spécifiques à l’application**, dans le raccourci **Recherches**, sélectionnez la **recherche Monaco**.
2. Dans le raccourci **Conditions**, associez les codes de taxe au résultat de recherche **Monaco**.

    > [!NOTE]
    > Comme dernière ligne de la configuration, créez une ligne où vous associez la valeur **\*Non vide\*** du champ **Code de taxe** au résultat de recherche **France**. Cette ligne indique que tous les autres codes de taxe sont liés à des opérations en France et ne doivent pas générer le montant de la case 18.

    ![Paramètre d’application Monaco.](media/19d301e4a786455234417faca00fe0ea.png)

### <a name="set-up-the-vat-reporting-format"></a>Paramétrer le format de déclaration de TVA

1. Dans l’espace de travail **Gestion des fonctionnalités**, activez la fonctionnalité **États de format de déclaration de TVA**.
2. Accédez à **Comptabilité** \> **Paramétrage** \> **Paramètres de comptabilité**.
3. Sur l’onglet **Taxe de vente**, dans le raccourci **Options de taxe**, dans le champ **Mise en correspondance des formats de déclaration de TVA**, sélectionnez le format ER **Déclaration de TVA Excel (FR)**.

    Ce format sera imprimé lorsque vous exécuterez l’état **État de la taxe pour la période de règlement**. Il sera également imprimé lorsque vous sélectionnerez **Imprimer** sur la page **Paiements de la taxe**.

4. Accédez à **Taxe** \> **Taxe de vente** \> **Administrations fiscales**. Sur la page **Autorités fiscales**, sélectionnez l’administration fiscale, puis, dans le champ **Présentation d’état**, sélectionnez **Par défaut**. Si vous avez configuré une déclaration de TVA dans une entité juridique qui a [plusieurs immatriculations à la TVA](emea-reporting-for-multiple-vat-registrations.md), accédez à **Comptabilité** \> **Paramétrage** \> **Paramètres de comptabilité**. Dans l’onglet **Taxe de vente**, dans le raccourci **Gestion des états électroniques pour les pays/régions**, sur la ligne **Pays/région FRA**, sélectionnez le format ER **Déclaration de TVA Excel (FR)**.

## <a name="preview-the-vat-declaration-in-excel"></a>Aperçu de la déclaration de TVA dans Excel

### <a name="preview-the-vat-declaration-in-excel-from-the-report-sales-tax-for-settlement-period-periodic-task"></a><a name="preview-the-vat-declaration-in-excel-from-the-report-sales-tax-for-settlement-period-periodic-task"></a> Prévisualisez la déclaration de TVA dans Excel à partir de la tâche périodique État de la taxe pour la période de règlement

1. Accédez à **Taxe** \> **Tâches périodiques** \> **Déclarations** \> **Taxe de vente** \> **État de la taxe pour la période de règlement**.
2. Définisse les champs suivants.

    | Champ                     | Description |
    |---------------------------|-------------|
    | Période de règlement         | Sélectionnez la période de règlement. |
    | Version de paiement de la taxe | <p>Vous devez sélectionner l’une des valeurs suivantes :</p><ul><li>**Original** : permet de générer un état pour les transactions de taxe du paiement de taxe d’origine ou avant que le paiement de taxe ne soit généré.</li><li>**Corrections** : permet de générer un état pour les transactions de taxe de tous les paiements de taxe ultérieurs pour la période</li><li>**Liste totale** : permet de générer un état pour toutes les transactions de taxe pour la période, y compris l’original et toutes les corrections.</li></ul> |
    | Date de début                 | Permet de sélectionner la date de début de la période de reporting. |

3. Cliquez sur **OK**.
4. Dans la boîte de dialogue **Paramètres des états électroniques**, définissez les champs suivants :

    | Champ                                                                          | Description                                                      |
    |--------------------------------------------------------------------------------|-----------------------------------------------------------------|
    | Report du crédit de la précédente déclaration                             | Inscrivez le montant à exporter sur la ligne 22 (case 8001) de l’état. |
    | Coefficient de taxation unique                                                         | Inscrivez le coefficient à exporter sur la ligne 22A de l’état.      |
    | Remboursement de crédit demandé                                                     | Inscrivez le montant à exporter sur la ligne 26 (case 8002) de l’état. |
    | Crédit de TVA transféré à la société tête de groupe sur la déclaration récapitulative    | Inscrivez le montant à exporter sur la ligne AA (case 8005) de l’état. |
    | Taxes assimilées                                                              | Inscrivez le montant à exporter sur la ligne 29 (case 9979) de l’état. |
    | Total à payer acquitté par la société tête de groupe sur la déclaration récapitulative | Inscrivez le montant à exporter sur la ligne AB (case 9991) de l’état. |

5. Cliquez sur **OK** et passez en revue l’état Excel.

### <a name="settle-and-post-sales-tax"></a><a name="settle-and-post-sales-tax"></a>Régler et valider la taxe

1. Accédez à **Taxe** \> **Tâches périodiques** \> **Déclarations** \> **Taxe de vente** \> **Régler et valider la taxe**.
2. Définisse les champs suivants.

    | Champ                     | Description |
    |---------------------------|-------------|
    | Période de règlement         | Sélectionnez la période de règlement. |
    | Version de paiement de la taxe | <p>Vous devez sélectionner l’une des valeurs suivantes :</p><ul><li>**Original** : permet de générer le paiement de la taxe d’origine pour la période de règlement.</li><li>**Dernières corrections** : permet de générer un paiement de taxe rectificatif après la création du paiement de taxe d’origine pour la période de règlement.</li></ul> |
    | Date de début                 | Permet de sélectionner la date de début de la période de reporting. |

3. Cliquez sur **OK**.

### <a name="preview-the-vat-declaration-in-excel-from-the-sales-tax-payments-inquiry"></a>Aperçu de la déclaration de TVA dans Excel à partir de la recherche Paiements de la taxe

1. Accédez à **Taxe** \> **Recherches et états** \> **Taxe (recherches)** \> **Paiements de la taxe**, puis sélectionnez une ligne de paiement de taxe.
2. Sélectionnez **Imprimer un état**.
3. Dans la boîte de dialogue **Paramètres des états électroniques**, définissez les champs comme expliqué dans la section [Aperçu de la déclaration de TVA dans Excel à partir de la tâche périodique État de la taxe pour la période de règlement](#preview-the-vat-declaration-in-excel-from-the-report-sales-tax-for-settlement-period-periodic-task) plus haut dans cet article. Vérifiez ensuite le fichier Excel généré pour la ligne de paiement de taxe sélectionnée.

> [!NOTE] 
> L’état est généré uniquement pour la ligne sélectionnée du paiement de taxe. Si vous devez générer, par exemple, une déclaration rectificative contenant toutes les corrections pour la période, ou une déclaration de remplacement qui contient les données d’origine et toutes les corrections, utilisez la tâche périodique **État de la taxe pour la période de règlement**.

## <a name="preview-the-vat-declaration-from-electronic-messages"></a>Aperçu de la déclaration de TVA à partir de messages électroniques

Si vous utilisez des messages électroniques pour générer l’état, vous pouvez collecter les données fiscales auprès de plusieurs entités juridiques. Pour plus d’informations, consultez la section [Exécuter une déclaration de TVA pour plusieurs entités juridiques](#run-a-vat-declaration-for-multiple-legal-entities) plus loin dans cet article.

### <a name="set-up-electronic-messages"></a>Paramétrer des messages électroniques

#### <a name="download-and-import-example-settings-for-electronic-messages"></a>Télécharger et importer des exemples de paramètres pour les messages électroniques

Le package de données incluant des exemples de paramètres contient des paramètres de messages électroniques qui sont utilisés pour générer l’état Excel pour la France. Vous pouvez développer ces paramètres ou créer les vôtres. Pour plus d’informations sur l’utilisation de la messagerie électronique et la création de vos propres paramètres, consultez [Messagerie électronique](../general-ledger/electronic-messaging.md).

1. Dans [LCS](https://lcs.dynamics.com/v2), dans la bibliothèque d’actifs partagés, sélectionnez **Package de données** comme type d’actif, puis téléchargez le package **Déclaration de TVA FR**. Le fichier téléchargé se nomme **FR VAT declaration package.zip**.
2. Dans Finance, dans l’espace de travail **Gestion des données**, sélectionnez **Importer**.
3. Dans le raccourci **Importer**, dans le champ **Nom de groupe**, entrez un nom pour la tâche.
4. Dans le raccourci **Entités sélectionnées**, sélectionnez **Ajouter un fichier**.
5. Dans la boîte de dialogue **Ajouter un fichier**, assurez-vous que le champ **Format des données source** est défini sur **Package**, sélectionnez **Charger et ajouter**, puis sélectionnez le fichier .zip que vous avez précédemment téléchargé. Sélectionnez **Fermer**.
6. Une fois les entités de données chargées, dans le volet Actions, sélectionnez **Importer**.
7. Accédez à **Taxe** \> **Recherches et états** \> **Messages électroniques** \> **Messages électroniques**, puis examinez le traitement des messages électroniques que vous avez importé (**Déclaration de TVA FR**).

#### <a name="configure-electronic-messages"></a>Configurer les messages électroniques

1. Accédez à **Taxe** \> **Paramétrage** \> **Messages électroniques** \> **Actions Renseignement des enregistrements**.
2. Sélectionnez la ligne **Remplir les enregistrement de retour TVA FR**, puis sélectionnez **Modifier la requête**.
3. Utilisez le filtre pour spécifier les périodes de règlement à inclure dans l’état.
4. Si vous devez déclarer les transactions fiscales d’autres périodes de règlement dans une déclaration différente, créez une action **Remplir les enregistrements** et sélectionnez les périodes de règlement appropriées.

### <a name="generate-a-vat-declaration-preview-from-electronic-messages"></a>Générer un aperçu de la déclaration de TVA à partir de messages électroniques

La procédure suivante s’applique à l’exemple de traitement de message électronique que vous avez importé précédemment à partir de la bibliothèque d’actifs partagés LCS.

1. Accédez à **Taxe** \> **Recherches et états** \> **Messages électroniques** \> **Messages électroniques**.
2. Dans le volet de gauche, sélectionnez le format d’état à générer. Par exemple, sélectionnez **Déclaration de TVA FR**.
3. Dans le raccourci **Messages**, sélectionnez **Nouveau**, puis, dans la boîte de dialogue **Exécuter le traitement**, cliquez sur **OK**.
4. Sélectionnez la ligne de message créée, saisissez une description, puis spécifiez les dates de début et de fin de la déclaration.

    > [!NOTE]
    > Les étapes 5 à 7 sont facultatives.

5. Facultatif : Dans le raccourci **Messages**, sélectionnez **Collecter des données**, puis cliquez sur **OK**. Les paiements de taxe qui ont été générés précédemment sont ajoutés au message. Pour plus d’informations, voir la section [Régler et valider la taxe](#settle-and-post-sales-tax) plus haut dans cet article. Si vous ignorez cette étape, vous pouvez toujours générer une déclaration de TVA en utilisant le champ **Version de la déclaration fiscale** dans la boîte de dialogue **Déclaration**.
6. Facultatif : Dans le raccourci **Éléments du message**, passez en revue les paiements de taxe qui sont transférés pour traitement. Par défaut, tous les paiements de taxe de la période sélectionnée qui n’étaient inclus dans aucun autre message du même traitement sont inclus.
7. Facultatif : Sélectionnez **Document d’origine** pour examiner les paiements de taxe, ou sélectionnez **Supprimer** pour exclure les paiements de taxe du traitement. Si vous ignorez cette étape, vous pouvez toujours générer une déclaration de TVA en utilisant le champ **Version de la déclaration fiscale** dans la boîte de dialogue **Déclaration**.
8. Dans le raccourci **Messages**, sélectionnez **Mettre à jour le statut**. Dans la boîte de dialogue **Mettre à jour le statut**, sélectionnez l’action **Prêt à générer**, puis cliquez sur **OK**. Vérifiez que l’état du message est modifié en **Prêt à générer**.
9. Sélectionnez **Générer l’état**. Pour prévisualiser les montants de la déclaration de TVA, dans la boîte de dialogue **Exécuter le traitement**, sélectionnez **Aperçu de l’état**, puis cliquez sur **OK**.
10. Dans la boîte de dialogue **Paramètres de gestion des états électroniques**, définissez les champs suivants, puis cliquez sur **OK**.

    | Champ | Description |
    |-------|-------------|
    | Période de règlement | Sélectionnez la période de règlement. Si vous avez sélectionné **Collecter des données** à l’étape 5, vous pouvez ignorer ce champ. L’état sera généré pour les transactions de taxe qui sont incluses dans les paiements de taxe collectés. |
    | Version de la déclaration de taxe | <p>Vous devez sélectionner l’une des valeurs suivantes :</p><ul><li>**Original** : permet de générer un état pour les transactions de taxe du paiement de taxe d’origine ou avant que le paiement de taxe ne soit généré.</li><li>**Corrections** : permet de générer un état pour les transactions de taxe de tous les paiements de taxe ultérieurs pour la période.</li><li>**Liste totale** : permet de générer un état pour toutes les transactions de taxe pour la période, y compris l’original et toutes les corrections.</li></ul> |
    | <p>Report du crédit de la précédente déclaration</p><p>Coefficient de taxation unique</p><p>Remboursement de crédit demandé Crédit de TVA transféré à la société mère du groupe sur la déclaration récapitulative</p><p>Taxes assimilées</p><p>Total à payer acquitté par la société tête de groupe sur la déclaration récapitulative</p> | Définissez ces champs comme expliqué dans la section [Aperçu de la déclaration de TVA dans Excel](#preview-the-vat-declaration-in-excel-from-the-report-sales-tax-for-settlement-period-periodic-task) plus haut dans cet article. |

    Si vous avez sélectionné **Collecter des données** à l’étape 5, vous pouvez ignorer ce champ. L’état sera généré pour les transactions de taxe qui sont incluses dans les paiements de taxe collectés.

11. Cliquez sur le bouton **Pièces jointes** (le symbole du trombone) dans l’angle supérieur droit de la page, puis sélectionnez **Ouvrir** pour ouvrir le fichier. Vérifiez les montants dans le document Excel.

## <a name="run-a-vat-declaration-for-multiple-legal-entities"></a><a name="run-a-vat-declaration-for-multiple-legal-entities"></a>Exécuter une déclaration de TVA pour plusieurs entités juridiques

Pour utiliser les formats pour générer un état sur la déclaration de TVA pour un groupe d’entités juridiques, vous devez d’abord configurer les paramètres spécifiques à l’application des formats ER pour les codes de taxe de toutes les entités juridiques requises.

### <a name="set-up-electronic-messages-to-collect-tax-data-from-multiple-legal-entities"></a>Configurer des messages électroniques pour collecter des données fiscales auprès de plusieurs entités juridiques

Suivez les étapes suivantes pour configurer des messages électroniques pour collecter des données fiscales auprès de plusieurs entités juridiques.

1. Accédez à **Espaces de travail** \> **Gestion des fonctionnalités**.
2. Recherchez et sélectionnez la fonctionnalité **Requêtes inter-sociétés pour les actions de remplissage des enregistrements** dans la liste, puis sélectionnez **Activer maintenant**.
3. Accédez à **Taxe** \> **Paramétrage** \> **Messages électroniques** \> **Actions Renseignement des enregistrements**.
4. Sur la page **Action Renseigner des enregistrements**, sélectionnez la ligne **Remplir les enregistrement de retour TVA FR**.

    Dans la grille **Configuration des sources de données**, un nouveau champ **Société** est disponible. Pour les enregistrements existants, ce champ affiche l’identificateur de l’entité juridique actuelle.

5. Dans la grille **Configuration des sources de données**, ajoutez une ligne pour chaque entité juridique supplémentaire qui doit être incluse dans la génération des états et définissez les champs suivants.

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
    | Requête utilisateur             | La case est automatiquement cochée lorsque vous définissez des critères en sélectionnant **Modifier la requête**.                                  |

6. Pour chaque nouvelle ligne, sélectionnez **Modifier la requête** et spécifiez une période de règlement associée pour l’entité juridique qui est spécifiée dans le champ **Société** sur la ligne.

    Une fois la configuration terminée, la fonction **Collecter des données** sur la page **Messages électroniques** collecte les paiements de taxe auprès de toutes les entités juridiques que vous avez définies.
