---
title: Déclaration TVA (Suisse)
description: Cette rubrique fournit des informations sur la configuration et la génération d’une déclaration de TVA pour la Suisse.
author: anasyash
ms.date: 09/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPaymMode, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: kfend
ms.custom: 264584
ms.search.region: Switzerland
ms.author: anasyash
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 4c2d1e617743a1859f9b1b55387fc5f4b4afb408
ms.sourcegitcommit: 7a2001e4d01b252f5231d94b50945fd31562b2bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2021
ms.locfileid: "7487939"
---
# <a name="vat-declaration-switzerland"></a>Déclaration TVA (Suisse)

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Vue d’ensemble

Cette rubrique décrit comment configurer et générer une déclaration de taxe sur la valeur ajoutée (TVA) pour la Suisse au format XML officiel (norme eCH-0217 eMWST). Elle décrit également comment prévisualiser la déclaration de TVA dans Microsoft Excel.

Pour générer automatiquement l’état, vous devez d’abord créer suffisamment de codes de taxe afin de conserver une comptabilité TVA distincte pour chaque case de la déclaration de TVA. De plus, dans les paramètres spécifiques à l’application du format de gestion des états électroniques (ER) pour la déclaration de TVA, vous devez associer des codes de taxe avec le résultat des recherches des cases de déclaration de TVA.

Pour la Suisse, vous devez configurer trois recherches : **Recherche de chiffre d’affaires**, **Recherche de champ d’état** et **Autre recherche de flux de trésorerie**. Pour plus d’informations sur la configuration des paramètres spécifiques à l’application, consultez la section [Configurer les paramètres spécifiques à l’application pour les champs de déclaration de TVA](#set-up-application-specific-parameters-for-vat-declaration-fields) plus loin dans cette rubrique.

Dans les tableaux suivants, la colonne « Résultat de la recherche » affiche le résultat de la recherche préconfiguré pour une ligne de déclaration de TVA spécifique dans le format de déclaration de TVA. Utilisez ces informations pour associer correctement les codes de taxe avec le résultat de la recherche, puis avec la ligne de déclaration de TVA.

### <a name="vat-declaration-overview"></a>Aperçu de la déclaration de TVA

La déclaration de TVA en Suisse contient les informations suivantes.

**SECTION I - CHIFFRE D’AFFAIRES**

| Ligne           | Élément XML                   | Description                                                                                                                                                                                                                                                                | Recherche          | Résultat de la recherche                                                                                                                                    |
|----------------|-------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| 200            | totalConsidération            | Montant total de la contrepartie convenue ou perçue, y compris la contrepartie des livraisons pour lesquelles l’option de taxation a été exercée, les transferts de livraisons selon la procédure de notification et les livraisons effectuées à l’étranger (chiffre d’affaires mondial). | Recherche de chiffre d’affaires | TaxableSupplies TaxableSupplies22 SuppliesToForeignCountries SuppliesAbroad TransferNotificationProcedure SuppliesExemptFromTax VariousDeduction |
| 205            | opted                         | Contrepartie déclarée à la ligne 200 des fournitures exonérées de la taxe sans crédit (article 21), et pour lesquelles l’option de taxation selon l’article 22 a été exercée.                                                                          | Recherche de chiffre d’affaires | TaxableSupplies22                                                                                                                                |
| **Déductions** |                               |                                                                                                                                                                                                                                                                           |                 |                                                                                                                                                  |
| 220            | suppliesToForeignCountries    | Fournitures exonérées de la taxe, telles que les exportations (article 23), et les fournitures qui sont fournies à des bénéficiaires institutionnels et individuels qui sont exonérées de la taxe (article 107, alinéa 1, lit. a).                                              | Recherche de chiffre d’affaires | SuppliesToForeignCountries                                                                                                                       |
| 221            | suppliesAbroad                | Fournitures fournies à l’étranger (le lieu de fourniture est à l’étranger).                                                                                                                                                                                                        | Recherche de chiffre d’affaires | SuppliesAbroad                                                                                                                                   |
| 225            | transferNotificationProcedure | Transferts de fournitures selon la procédure de notification (article 38). Vous devez soumettre le formulaire 764.                                                                                                                                                                   | Recherche de chiffre d’affaires | TransferNotificationProcedure                                                                                                                    |
| 230            | suppliesExemptFromTax         | Fournitures proposées sur le territoire suisse exonérées de la taxe sans crédit (article 21), et pour lesquelles l’option de taxation selon l’article 22 n’a pas été exercée.                                                                                   | Recherche de chiffre d’affaires | SuppliesExemptFromTax                                                                                                                            |
| 235            | reductionOfConsideration      | Réduction de contrepartie, comme les remises et les rabais.                                                                                                                                                                                                                | Recherche de chiffre d’affaires | ReductionOfConsideration                                                                                                                         |
| 280            | variousDeduction              | Divers, tels que la valeur du terrain et les prix d’achat en cas de taxation de la marge.                                                                                                                                                                                    | Recherche de chiffre d’affaires | VariousDeduction                                                                                                                                 |
| 289            | Non applicable                | Total lines220 through280.                                                                                                                                                                                                                                                | Total           | 220 + 221 + 225 + 230 + 235 + 280                                                                                                                |
| 299            | Non applicable                | Chiffre d’affaires imposable (ligne 200 moins ligne 289).                                                                                                                                                                                                                               | Total           | 200 - 289                                                                                                                                        |

**SECTION II - CALCUL DE LA TAXE**

**Taxe due**

| Ligne | Élément XML                           | Description                                                  | Recherche              | Résultat de la recherche                                                                                                                                             |
|------|---------------------------------------|-------------------------------------------------------------|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| 302  | supplierTaxRate / tax rate tax amount | Fournitures à partir du 1er janvier 2018, à un taux standard.          | Recherche de champ d’état | SuppliesStandardRate                                                                                                                                      |
| 312  | supplierTaxRate / tax rate tax amount | Fournitures à partir du 1er janvier 2018, à un taux réduit.           | Recherche de champ d’état | SuppliesReducedRate                                                                                                                                       |
| 342  | supplierTaxRate / tax rate tax amount | Fournitures à partir du 1er janvier 2018, à un taux pour l’hébergement.    | Recherche de champ d’état | SuppliesAccomodationRate                                                                                                                                  |
| 382  | acquisitionTax / tax rate tax amount  | Taxe d’acquisition pour les fournitures à compter du 1er janvier 2018           | Recherche de champ d’état | SuppliesAcquisitionTax UseTaxAcquisitionTax (Ce résultat est également déclaré intégralement en ligne 400.) Montant de la taxe non déductible, le cas échéant est déclaré en ligne 415 |
| 301  | supplierTaxRate / tax rate tax amount | Fournitures jusqu’au 31 décembre 2017, au tarif standard.       | Recherche de champ d’état | SuppliesOldStandardRate                                                                                                                                   |
| 311  | supplierTaxRate / tax rate tax amount | Fournitures jusqu’au 31 décembre 2017, à un taux réduit.        | Recherche de champ d’état | SuppliesOldReducedRate                                                                                                                                    |
| 341  | supplierTaxRate / tax rate tax amount | Fournitures jusqu’au 31 décembre 2017, à un taux pour l’hébergement. | Recherche de champ d’état | SuppliesAccomodationOldRate                                                                                                                               |
| 381  | acquisitionTax / tax rate tax amount  | Taxe d’acquisition pour les fournitures jusqu’au 31 décembre 2017        | Recherche de champ d’état | SuppliesAcquisitionTaxOldRate                                                                                                                             |
| 399  | Non applicable                        | Montant total de la taxe due (lignes 301 à 382).            | Total               | 302 + 312 + 342 + 382 + 301 + 311 + 341 + 381                                                                                                             |

**Taxe d’entrée**

| Ligne | Élément XML                 | Description                                                                                                                                                          | Recherche              | Résultat de la recherche                                                                                                                                    |
|------|-----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| 400  | inputTaxMaterialAndServices | Taxe en amont sur le coût des matériaux et des prestations de services.                                                                                                        | Recherche de champ d’état | InputTaxMaterialAndServices (déclaré en entier) UseTaxAcquisitionTax (déclaré en entier) Montant de la taxe non déductible, le cas échéant, déclaré en ligne 415 |
| 405  | inputTaxInvestments         | Taxe déductible sur les investissements et les autres coûts d’exploitation.                                                                                                                 | Recherche de champ d’état | InputTaxInvestments (déclaré en totalité) Montant d’impôt non déductible, le cas échéant, déclaré en ligne 415                                                 |
| 410  | subsequentInputTaxDeduction | Détaxation (article 32). Vous devez joindre une liste détaillée.                                                                                                       | Recherche de champ d’état | SubsequentInputTaxDeduction                                                                                                                      |
| 415  | inputTaxCorrections         | Correction de la déduction de la taxe en amont, tant à usage mixte (article 30) qu’à usage propre (article 31).                                                                        | Recherche de champ d’état | InputTaxCorrections (rapporté en entier, mais avec le signe inversé)                                                                                |
| 420  | inputTaxReductions          | Réduction de la déduction de la taxe en amont : les flux de fonds qui ne sont pas réputés être pris en considération, tels que les subventions et les taxes de séjour (article 33, alinéa 2). | Recherche de champ d’état | InputTaxReductions (rapporté en entier, mais avec le signe inversé)                                                                                     |
| 479  | Non applicable              | Total des lignes 400 à 420.                                                                                                                                        | Total               | 400 + 405 + 410 – 415 – 420                                                                                                                      |
| 500  | Non applicable              | Montant dû.                                                                                                                                         | Total               | 399 – 479, si 399-479 est positif                                                                                                                |
| 510  | Non applicable              | Crédit en faveur de l’assujetti.                                                                                                                          | Total               | 479 – 399, si 479-399 est positif                                                                                                              |

**SECTION III - AUTRES FLUX DE TRÉSORERIE**

| Ligne | Élément XML | Description                                                                                                                                                                | Recherche                 | Résultat de la recherche |
|------|-------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|---------------|
| 900  | subsidies   | Subventions, fonds touristiques collectés par les offices de tourisme, contributions des eaux cantonales et fonds d’assainissement ou de déchets (article 18, al. 2, lit. a à c). | Autre recherche de flux de trésorerie | Subventions     |
| 910  | donations   | Dons, dividendes, versements de dommages-intérêts, etc. (article 18, paragraphe 2, lit. d à l).                                                                         | Autre recherche de flux de trésorerie | Subventions     |

#### <a name="purchase-reverse-charge-vat"></a>Taxe au preneur Achat

Si vous configurez des codes de taxe pour valider la taxe d’acquisition entrante en utilisant la taxe d’utilisation, associez vos codes de taxe avec le résultat de la recherche **Champ d’état** qui contient « UseTax » dans le nom.

Vous pouvez également configurer deux codes de taxe distincts : un pour la TVA due et un pour la déduction de la TVA. Associez ensuite chaque code avec l’état de recherche correspondant de la recherche **Champ d’état**.

Par exemple, pour les fournitures à partir du 1er janvier 2018 - taxe d’acquisition, vous configurez le code taxe de vente **UT_S_RC** avec la taxe d’utilisation, et l’associez au résultat de la recherche **UseTaxAcquisitionTax** de **Recherche de champ d’état**. Dans ce cas, les montants qui utilisent le code de taxe de vente **UT_S_RC** sont reflétés sur les lignes 382 et 400 avec le montant total, et en ligne 415 avec le montant non déductible, s’il y en a.

Vous pouvez également configurer deux codes de taxe :

- **VAT_S_RC**, qui a une valeur de taux de taxe de -7.7 %
- **InVAT_S_RC**, qui a une valeur de taux de taxe de 7.7 %

Associez ensuite les codes avec les résultats de recherche de la manière suivante :

- Associez **VAT_S_RC** au résultat de recherche **SuppliesAcquisitionTax** de la recherche **Champ d’état**.
- Associez **InVAT_S_RC** au résultat de recherche **InputTaxMaterialAndServices** de la recherche **Champ d’état**.

Dans ce cas, les montants qui utilisent le code de taxe de vente **VAT_S_RC** sera reflété en ligne 382. Les montants qui utilisent le code de taxe de vente **InVAT_S_RC** sera reflété en ligne 400 avec le montant total et en ligne 415 avec le montant non déductible.

Pour plus d’informations sur la configuration de la taxe au preneur, consultez [Taxes au preneur]emea-reverse-charge.md).

## <a name="configure-system-parameters"></a>Configuration des paramètres système

Pour générer une déclaration de TVA, configurez l’UID (numéro d’identification de l’entreprise).

1. Accédez à **Administration d’organisation** > **Organisations** > **Entités juridiques**.
2. Sélectionnez l’entité juridique, puis sélectionnez **ID enregistrement**.
3. Sélectionnez ou créez l’adresse en Suisse, puis, sur le raccourci **ID d’enregistrement**, sélectionnez **Ajouter**.
4. Dans le champ **Type d’enregistrement**, sélectionnez le type d’enregistrement dédié à la Suisse, et qui utilise la catégorie d’enregistrement **ID entreprise (COID)**.
5. Dans le champ **Numéro d’enregistrement**, saisissez le numéro UID au format suivant : CHE-123.456.789.
6. Sur l’onglet **Général**, dans le champ **Date d’effet**, entrez la date à laquelle le numéro entre en vigueur.
7. Répétez ces étapes pour configurer une ligne avec le numéro de TVA. Dans ce cas, sélectionnez le type d’enregistrement qui utilise la catégorie d’enregistrement **N° de TVA**, et entrez le numéro au format suivant : CHE-123.456.789 TVA/MWST/IVA.

Pour plus d’informations sur la configuration des catégories d’inscription et des types d’inscription, voir [Identifiants d’enregistrement](emea-registration-ids.md).

## <a name="set-up-a-vat-declaration-for-switzerland"></a>Paramétrer un aperçu de la déclaration de TVA pour la Suisse

### <a name="import-er-configurations"></a>Importer les configurations ER

Ouvrez l’espace de travail **Déclaration électronique** et importez les versions suivantes ou ultérieures de ces formats ER :

- Déclaration de TVA XML (CH) version 96.16
- Déclaration de TVA Excel (CH) version 96.16.9

### <a name=""></a><a name="set-up-application-specific-parameters-for-vat-declaration-fields">Configurer les paramètres spécifiques à l’application pour les champs de déclaration de TVA</a>

Pour générer automatiquement une déclaration de TVA, associez les codes de taxe dans l’application aux résultats de recherche dans la configuration ER.

#### <a name="set-up-turnover-lookup"></a>Configurer la recherche de chiffre d’affaires

Suivez ces étapes pour définir quels codes de taxe génèrent quelles cases dans la section I « Chiffre d’affaires ».

1. Accédez à **Espaces de travail** > **Gestion des états électroniques** et sélectionnez **Configurations des états**.
2. Sélectionnez la configuration **Déclaration de TVA XML (CH)**, puis sélectionnez **Configurations** > **Configuration des paramètres spécifiques à l’application**.
3. Sur la page **Paramètres spécifiques à l’application**, dans le raccourci **Recherches**, sélectionnez **Recherche de chiffre d’affaires**.
4. Dans le raccourci **Conditions**, définissez les champs suivants pour associer les codes de taxe et les opérations.

   | Champ                  | Description                                                                                                                                                                                                                                                                                                          |
   |------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | Résultat de la recherche          | Sélectionnez la valeur du chiffre d’affaires. Pour plus d’informations sur les valeurs de chiffre d’affaires et leur affectation aux lignes de déclaration de TVA, consultez la section [Vue d’ensemble de la déclaration de TVA](#vat-declaration-overview) plus haut dans cette rubrique.                                                                                         |
   | Code taxe               | Permet de sélectionner le code de taxe à associer à l’opération. Les transactions de taxe validées qui utilisent le code de taxe sélectionné seront collectées dans la case de déclaration appropriée. Nous vous recommandons de séparer les codes de taxe de telle sorte qu’un code de taxe ne génère des montants que dans une seule case de déclaration.   |
   | Classifieur de transactions | Si vous avez créé suffisamment de codes de taxe pour déterminer une case de déclaration, sélectionnez **\*Non vide\***. Si vous n’avez pas créé suffisamment de codes de taxe pour qu’un code de taxe ne génère des montants que dans une seule case de déclaration, configurez un classifieur de transaction. Les classifieurs de transactions suivants sont disponibles : <br>- **Achats**<br>- **PurchaseExempt** (achat exonéré de taxe) <br>- **PurchaseReverseCharge** (taxe déductible provenant d’une taxe au preneur sur achat) <br>- **Vente** <br>- **SalesExempt** (vente exonérée de taxe) <br>- **SalesReverseCharge** (taxe exigible provenant d’une taxe au preneur sur achat ou vente) <br>- **Taxe d’utilisation** <br> Pour chaque classifieur de transaction, un classifieur pour l’avoir est également disponible. Par exemple, l’un de ces classifieurs est **PurchaseCreditNote** (avoir sur achat).|



   > [!NOTE]
   > Associez tous les codes de taxe aux résultats de recherche. Si des codes de taxe ne doivent pas générer de valeurs dans la section I, associez-les au résultat de recherche **Autre**.

   ![Page des paramètres spécifiques à l’application pour la recherche du chiffre d’affaires ; page des paramètres spécifiques à l’application pour la recherche du chiffre d’affaires](media/f99d7ff6529a58623732e112cf864230.png)

#### <a name="set-up-report-field-lookup"></a>Configurer la recherche de champ d’état

Suivez ces étapes pour définir quels codes de taxe génèrent quelles cases dans la section II « Calcul de la taxe ».

1. Sur la page **Paramètres spécifiques à l’application**, dans le raccourci **Recherches**, sélectionnez **Recherche de champ d’état**.
2. Dans le raccourci **Conditions**, associez les codes de taxe et les champs d’état.

   > [!NOTE]
   > Assurez-vous d’associer tous les codes de taxe aux résultats de recherche. Si des codes de taxe ne doivent pas générer de valeurs dans la section II, associez-les au résultat de recherche **Autre**.

   ![Page des paramètres spécifiques à l’application pour la recherche du champ État ; page des paramètres spécifiques à l’application pour la recherche du champ État](media/b440aab1d394fb9e98f12aed5d96582d.png)

#### <a name="set-up-other-cash-flow-lookup"></a>Configurer la recherche d’autres flux de trésorerie

Suivez ces étapes pour définir quels codes de taxe génèrent quelles cases dans la section III « Autres flux de trésorerie ».

1. Sur la page **Paramètres spécifiques à l’application**, dans le raccourci **Recherches**, sélectionnez **Recherche d’autres flux de trésorerie**.
2. Dans le raccourci **Conditions**, associez les codes de taxe et les autres éléments de flux de trésorerie.

   > [!NOTE]
   > Comme dernière ligne de la configuration, créez une ligne où vous associez la valeur **\*Non vide\*** du code de taxe au résultat de recherche **Autre**. Cette ligne indique que tous les autres codes de taxe de vente qui ne sont pas définis dans les lignes précédentes ne génèrent pas de montants dans la section III.

   ![Page de paramètres spécifiques à l’application pour la recherche d’autres flux de trésorerie](media/2ddd539a62e69bc03c346fb8c90e6299.png)

 3. Dans le champ **État**, changez la valeur sur **Terminé**.
 4. Dans le volet Actions, sélectionnez **Exporter** pour exporter les réglages des paramètres spécifiques à l’application.
 5. Sélectionnez la configuration **Déclaration de TVA Excel (CH)**, puis, dans le volet Actions, sélectionnez **Importer** pour importer les paramètres que vous avez configurés pour **Déclaration de TVA XML (CH)**.
 6. Dans le champ **État**, sélectionnez **Terminé**.

### <a name="set-up-the-vat-reporting-format-for-preview-amounts-in-excel"></a>Configurer le format de déclaration de TVA pour les montants d’aperçu dans Excel

1. Dans l’espace de travail **Gestion des fonctionnalités**, activez la fonctionnalité **États de format de déclaration de TVA**.
2. Accédez à **Comptabilité \> Paramétrage \> Paramètres de comptabilité**.
3. Sur l’onglet **Taxe de vente**, dans le raccourci **Options de taxe**, dans le champ **Mise en correspondance des formats de déclaration de TVA**, sélectionnez le format ER **Déclaration de TVA Excel (CH)**.

   Ce format sera imprimé lorsque vous exécuterez l’état **État de la taxe pour la période de règlement**. Il sera également imprimé lorsque vous sélectionnerez **Imprimer** sur la page **Paiements de la taxe**.

4. Sur la page **Autorités fiscales**, sélectionnez l’administration fiscale, puis, dans le champ **Présentation d’état**, sélectionnez **Par défaut**.

Si vous configurez la déclaration de TVA dans une entité juridique qui a [plusieurs immatriculations à la TVA](emea-reporting-for-multiple-vat-registrations.md), procédez comme suit.

1. Accédez à **Comptabilité** > **Paramétrage** > **Paramètres de comptabilité**.
2. Dans l’onglet **Taxe de vente**, dans le raccourci **Gestion des états électroniques pour les pays/régions**, sur la ligne **CHE**, sélectionnez le format ER **Déclaration de TVA Excel (CH)**.

## <a name="set-up-electronic-messages"></a>Paramétrer des messages électroniques

### <a name="download-and-import-the-data-package-that-has-example-settings-for-electronic-messages"></a>Télécharger et importer le package de données ayant un exemple de paramètres pour les messages électroniques

Le package de données contient des paramètres de message électronique utilisés pour générer la déclaration de TVA au format XML et la prévisualiser dans Excel. Vous pouvez développer ces paramètres ou créer les vôtres. Pour plus d’informations sur l’utilisation de la messagerie électronique et la création de vos propres paramètres, consultez [Messagerie électronique](../general-ledger/electronic-messaging.md).

1. Dans [LCS](https://lcs.dynamics.com/v2), dans la bibliothèque d’actifs partagés, sélectionnez **Package de données** comme type d’actif, puis téléchargez le package EM **Déclaration de TVA CH**. Le fichier téléchargé se nomme **CH VAT declaration EM package.zip**.
2. Dans Finance, dans l’espace de travail **Gestion des données**, sélectionnez **Importer**.
3. Dans le raccourci **Importer**, dans le champ **Nom de groupe**, entrez un nom pour la tâche.
4. Dans le raccourci **Entités sélectionnées**, sélectionnez **Ajouter un fichier**.
5. Dans la boîte de dialogue **Ajouter un fichier**, vérifiez que le champ **Format des données source** est défini sur **Package**, sélectionnez **Charger et ajouter**, puis sélectionnez le fichier .zip que vous avez précédemment téléchargé.
6. Sélectionnez **Fermer**.
7. Une fois les entités de données chargées, dans le volet Actions, sélectionnez **Importer**.
8. Accédez à **Taxe** > **Recherches et états** > **Messages électroniques** > **Messages électroniques**, puis validez le traitement des messages électroniques que vous avez importé (**Déclaration de TVA CH**).

### <a name="configure-electronic-messages"></a>Configurer les messages électroniques

1. Accédez à **Taxe** > **Paramétrage** > **Messages électroniques** > **Actions Renseignement des enregistrements**.
2. Sélectionnez la ligne **Remplir les enregistrement de retour TVA CH**, puis sélectionnez **Modifier la requête**.
3. Utilisez le filtre pour spécifier les périodes de règlement à inclure dans l’état.
4. Si vous devez déclarer les transactions fiscales d’autres périodes de règlement dans une déclaration différente, créez une action **Remplir les enregistrements** et sélectionnez les périodes de règlement appropriées.

## <a name="preview-the-vat-declaration-in-excel"></a>Aperçu de la déclaration de TVA dans Excel

### <a name="preview-the-vat-declaration-in-excel-from-the-report-sales-tax-for-settlement-period-periodic-task"></a> Prévisualisez la déclaration de TVA dans Excel à partir de la tâche périodique État de la taxe pour la période de règlement

1. Accédez à **Taxe** > **Tâches périodiques** > **Déclarations** > **Taxe de vente** > **État de la taxe pour la période de règlement**.
2. Définisse les champs suivants.

   | Champ                     | Description                                     |
   |---------------------------|------------------------------------------------|
   | Période de règlement         | Sélectionnez la période de règlement.                  |
   | Version de paiement de la taxe | Vous devez sélectionner l’une des valeurs suivantes : <br>- **Original** : permet de générer un état pour les transactions de taxe du paiement de taxe d’origine ou avant que le paiement de taxe ne soit généré. <br>- **Corrections** : permet de générer un état pour les transactions de taxe de tous les paiements de taxe ultérieurs pour la période. <br> - **Liste totale** : permet de générer un état pour toutes les transactions de taxe pour la période, y compris l’original et toutes les corrections.            |
   | Date de début                 | Permet de sélectionner la date de début de la période de reporting. |

3. Sélectionnez **OK** et passez en revue la déclaration Excel.

### <a name=""></a><a name="settle-and-post-sales-tax">Régler et valider la taxe</a>

1. Accédez à **Taxe** > **Tâches périodiques** > **Déclarations** > **Taxe de vente** > **Régler et valider la taxe**.
2. Définisse les champs suivants.

   | Champ                     | Description                                     |
   |---------------------------|------------------------------------------------|
   | Période de règlement         | Sélectionnez la période de règlement.                  |
   | Version de paiement de la taxe | Vous devez sélectionner l’une des valeurs suivantes : <br> - **Original** : permet de générer le paiement de la taxe d’origine pour la période de règlement. <br> - **Dernières corrections** : permet de générer un paiement de taxe rectificatif après la création du paiement de taxe d’origine pour la période de règlement.          |
   | Date de début                 | Permet de sélectionner la date de début de la période de reporting. |

3. Cliquez sur **OK**.

### <a name="preview-the-vat-declaration-in-excel-from-a-sales-tax-payment"></a>Aperçu de la déclaration de TVA dans Excel à partir du paiement de la taxe de vente

1. Accédez à **Taxe** > **Recherches et états** > **Taxe (recherches)** > **Paiements de la taxe**, puis sélectionnez une ligne de paiement de taxe.
2. Sélectionnez **Imprimer un état**.
3. Dans la boîte de dialogue **Paramètres d’état électronique**, définissez les champs comme expliqué précédemment dans cette rubrique. Vérifiez ensuite le fichier Excel généré pour la ligne de paiement de taxe sélectionnée.

   > [!NOTE]
   > L’état est généré uniquement pour la ligne sélectionnée du paiement de taxe. Si vous devez générer, par exemple, une déclaration rectificative contenant toutes les corrections pour la période, ou une déclaration de remplacement qui contient les données d’origine et toutes les corrections, utilisez la tâche périodique **État de la taxe pour la période de règlement**.

## <a name="generate-a-vat-declaration-from-electronic-messages"></a>Générer une déclaration de TVA à partir de messages électroniques

Lorsque vous utilisez des messages électroniques pour générer l’état, vous pouvez collecter les données fiscales auprès de plusieurs entités juridiques. Pour plus d’informations, consultez la section [Exécuter une déclaration de TVA pour plusieurs entités juridiques](#run-a-vat-declaration-for-multiple-legal-entities) plus loin dans cette rubrique.

La procédure suivante s’applique à l’exemple de traitement de message électronique que vous avez importé précédemment à partir de la bibliothèque d’actifs partagés LCS.

1. Accédez à **Taxe \> Recherches et états \> Messages électroniques \> Messages électroniques**.
2. Dans le volet de navigation à gauche, sélectionnez **Déclaration de TVA CH**.
3. Dans le raccourci **Messages**, sélectionnez **Nouveau**, puis, dans la boîte de dialogue **Exécuter le traitement**, cliquez sur **OK**.
4. Sélectionnez la ligne de message créée, saisissez une description, puis spécifiez les dates de début et de fin de la déclaration.

   > [!NOTE]
   >  Les étapes 5 à 7 sont facultatives.

5. Facultatif : Dans le raccourci **Messages**, sélectionnez **Collecter des données**, puis cliquez sur **OK**. Les paiements de taxe qui ont été générés précédemment sont ajoutés au message. Pour plus d’informations, voir la section [Régler et valider la taxe](#settle-and-post-sales-tax) plus haut dans cette rubrique. Si vous ignorez cette étape, vous pouvez toujours générer une déclaration de TVA en utilisant le champ **Version de la déclaration fiscale** dans la boîte de dialogue **Déclaration**.
6. Facultatif : Dans le raccourci **Éléments du message**, passez en revue les paiements de taxe qui sont transférés pour traitement. Par défaut, tous les paiements de taxe de la période sélectionnée qui n’étaient inclus dans aucun autre message du même traitement sont inclus.
7. Facultatif : Sélectionnez **Document d’origine** pour examiner les paiements de taxe, ou sélectionnez **Supprimer** pour exclure les paiements de taxe du traitement. Si vous ignorez cette étape, vous pouvez toujours générer une déclaration de TVA en utilisant le champ **Version de la déclaration fiscale** dans la boîte de dialogue **Déclaration**.
8. Dans le raccourci **Messages**, sélectionnez **Mettre à jour le statut**. Dans la boîte de dialogue **Mettre à jour le statut**, sélectionnez **Prêt à générer**, puis cliquez sur **OK**. Vérifiez que l’état du message est modifié en **Prêt à générer**.
9. Sélectionnez **Générer l’état**. Pour prévisualiser les montants de la déclaration de TVA, dans la boîte de dialogue **Exécuter le traitement**, sélectionnez **Aperçu de l’état**, puis cliquez sur **OK**.
10. Dans la boîte de dialogue **Paramètres de gestion des états électroniques**, définissez les champs suivants, puis cliquez sur **OK**.

      | **Champ**               | **Description**    |
      |-------------------------|---------------------|
      | Période de règlement       | Sélectionnez la période de règlement. Si vous avez sélectionné **Collecter des données** à l’étape 5, vous pouvez ignorer ce champ. L’état sera généré pour les transactions de taxe qui sont incluses dans les paiements de taxe collectés. |
      | Version de la déclaration de taxe | Vous devez sélectionner l’une des valeurs suivantes : <br>-**Original** : permet de générer un état pour les transactions de taxe du paiement de taxe d’origine ou avant que le paiement de taxe ne soit généré. <br>-**Corrections** : permet de générer un état pour les transactions de taxe de tous les paiements de taxe ultérieurs pour la période. <br>- **Liste totale** : permet de générer un état pour toutes les transactions de taxe pour la période, y compris Original et Toutes les corrections.               |
    
    Si vous avez sélectionné **Collecter des données** à l’étape 5, vous pouvez ignorer ce champ. L’état sera généré pour les transactions de taxe qui sont incluses dans les paiements de taxe collectés.

11. Cliquez sur le bouton **Pièces jointes** (le symbole du trombone) dans l’angle supérieur droit de la page, puis sélectionnez **Ouvrir** pour ouvrir le fichier. Vérifiez les montants dans le document Excel.
12. Sélectionnez **Générer l’état**.
13. Pour générer une déclaration de TVA au format XML, dans la boîte de dialogue **Exécuter le traitement**, sélectionnez **Générer l’état**, puis cliquez sur **OK**.
14. Dans la boîte de dialogue **Paramètres de gestion des états électroniques**, définissez les champs comme décrit précédemment dans cette procédure, puis cliquez sur **OK**.

## <a name=""></a><a name="run-a-vat-declaration-for-multiple-legal-entities">Exécuter une déclaration de TVA pour plusieurs entités juridiques</a>

Pour utiliser les formats pour générer un état sur la déclaration de TVA pour un groupe d’entités juridiques, vous devez d’abord configurer les paramètres spécifiques à l’application des formats ER pour les codes de taxe de toutes les entités juridiques requises.

### <a name="set-up-electronic-messages-to-collect-tax-data-from-several-legal-entities"></a>Configurer des messages électroniques pour collecter des données fiscales auprès de plusieurs entités juridiques

Suivez les étapes suivantes pour configurer des messages électroniques pour collecter des données fiscales auprès de plusieurs entités juridiques.

1. Accédez à **Espaces de travail** > **Gestion des fonctionnalités**.
2. Recherchez et sélectionnez la fonctionnalité **Requêtes inter-sociétés pour les actions de remplissage des enregistrements** dans la liste, puis sélectionnez **Activer maintenant**.
3. Accédez à **Taxe** > **Paramétrage** > **Messages électroniques** > **Actions Renseignement des enregistrements**.
4. Sur la page **Action Renseigner des enregistrements**, sélectionnez la ligne **Remplir les enregistrement de retour TVA CH**.

   Dans la grille **Configuration des sources de données**, un nouveau champ **Société** est disponible. Pour les enregistrements existants, ce champ affiche l’identificateur de l’entité juridique actuelle.

5. Dans la grille **Configuration des sources de données**, ajoutez une ligne pour chaque entité juridique supplémentaire qui doit être incluse dans la génération des états. Pour chaque nouvelle ligne, définissez les champs suivants.

   | Champ                  | Description                                                                                                                    |
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
