---
title: Déclaration de TVA (Allemagne)
description: Cette rubrique décrit comment configurer et générer une déclaration de taxe sur la valeur ajoutée (TVA) pour l’Allemagne au format XML officiel.
author: anasyash
ms.date: 11/22/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: ''
ms.openlocfilehash: 29c04e1034c05b4672f3657ce0b7bc9d5f6d7c9c
ms.sourcegitcommit: 8c17717b800c2649af573851ab640368af299981
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/23/2021
ms.locfileid: "7860880"
---
# <a name="vat-declaration-germany"></a>Déclaration de TVA (Allemagne)

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment configurer et générer une déclaration de taxe sur la valeur ajoutée (TVA) pour l’Allemagne au format XML officiel. Elle explique également comment prévisualiser la déclaration de TVA dans Microsoft Excel.

Pour générer automatiquement le rapport, vous devez créer suffisamment de codes de taxe afin de conserver une comptabilité TVA distincte pour chaque case de la déclaration de TVA avancée. De plus, dans les paramètres spécifiques à l’application du format de gestion des états électroniques (ER) pour la déclaration de TVA avancée, vous devez associer des codes de taxe avec le résultat des recherches des cases de déclaration de TVA.

Pour l’Allemagne, vous devez configurer **Recherche de champ d’état**. Pour plus d’informations sur la configuration des paramètres spécifiques à l’application, consultez la section [Configurer les paramètres spécifiques à l’application pour les champs de déclaration de TVA](#set-up-application-specific-parameters-for-vat-declaration-fields) plus loin dans cette rubrique.

Dans les tableaux suivants, la colonne « Résultat de la recherche » affiche le résultat de la recherche préconfiguré pour une ligne de déclaration de TVA spécifique dans le format de déclaration de TVA. Utilisez ces informations pour associer correctement les codes de taxe avec le résultat de la recherche, puis avec la ligne de déclaration de TVA.

### <a name="vat-declaration-overview"></a><a name="vat-declaration-overview"></a>Aperçu de la déclaration de TVA

La déclaration de TVA avancée en Allemagne contient les informations suivantes.

**SECTION – LIVRAISONS ET AUTRES SERVICES**

**Ventes soumises à taxe**

| Ligne | Case – Base de taxe | Case - Montant de la taxe | Description                                                                                                                                      | Résultat de la recherche                                                                             |
|-----|----------------|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| 20  | 81             | Sans code     | Ventes taxables à un taux d’imposition de 19 %.                                                                                                       | 20-TaxableSalesStandard</br>73-BadDebtsWriteOffStandard (81/50) – avec signe moins             |
| 21  | 86             | Sans code     | Ventes taxables à un taux d’imposition de 7 %.                                                                                                        | 21-TaxableSalesReduced</br>73-BadDebtsWriteOffReduced (86/50) – avec signe moins               |
| 22  | 35             | 36               | Ventes taxables à d’autres taux d’imposition.                                                                                                                | 22-TaxableSalesOtherRates</br>73-BadDebtsWriteOffOtherRates (35/36/50) – avec signe moins      |
| 23  | 77             | *Aucun montant de taxe*  | Livraisons provenant d’entreprises agricoles et forestières conformément à l’article 24 de la loi allemande sur la TVA (UStG) à des clients disposant d’un numéro d’identification TVA. | 23-EUSalesAverageRate24</br>73-BadDebtsWriteOffEUSalesAverageRate24 (77/50) – avec signe moins |
| 24  | 76             | 80               | Ventes pour lesquelles une taxe doit être payée, conformément à l’article 24 de l’UStG (produits de scierie, boissons et liquides alcoolisés).                                | 24-SalesAverageRate24</br>73-BadDebtsWriteOffSalesAverageRate24 (76/80/50)                    |

**Ventes exonérées de taxe avec déduction de taxe sur les intrants**

| Ligne | Case – Base de taxe | Case - Montant de la taxe | Description                                                                       | Résultat de la recherche                       |
|-----|----------------|------------------|-----------------------------------------------------------------------------------|-------------------------------------|
| 26  | 41             | *Aucun montant de taxe*  | Livraisons intracommunautaires aux clients disposant d’un numéro de TVA.                       | 26-EUSales                          |
| 27  | 44             | *Aucun montant de taxe*  | Livraisons intracommunautaires de véhicules neufs à des acheteurs n’ayant pas de numéro de TVA.    | 27-EUSalesNewVehicles               |
| 28  | 49             | *Aucun montant de taxe*  | Livraisons intracommunautaires de véhicules neufs hors entreprise.                     | 28-EUSalesNewVehiclesOutsideCompany |
| 29  | 43             | *Aucun montant de taxe*  | Autres ventes hors taxes qui bénéficient d’une déduction de la taxe sur les intrants, telles que les livraisons à l’exportation. | 29-ExportOtherTaxFreeSales          |

**Ventes exonérées de taxe sans déduction de taxe sur les intrants**

| Ligne | Case – Base de taxe | Case - Montant de la taxe | Description                                            | Résultat de la recherche                           |
|-----|----------------|------------------|--------------------------------------------------------|-----------------------------------------|
| 30  | 48             | *Aucun montant de taxe*  | Ventes hors taxes qui n’ont pas de déduction de la taxe sur les intrants. | 30-TaxFreeSalesWithoutInputTaxDeduction |

**Acquisitions intracommunautaires**

| Ligne | Case – Base de taxe | Case - Montant de la taxe | Description                                                                                                                   | Résultat de la recherche                                                    |
|-----|----------------|------------------|-------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------|
| 33  | 91             | *Aucun montant de taxe*  | Acquisitions intracommunautaires hors taxes de certains objets et d’or d’investissement.                                                    | 33-TaxFreeEUPurchase                                             |
| 34  | 89             | Sans code     | Acquisitions intracommunautaires imposables à un taux d’imposition de 19 %.                                                             | 34-EUPurchaseStandard</br>34-UseTaxEUPurchaseStandard (89/61)        |
| 35  | 93             | Sans code     | Acquisitions intracommunautaires imposables à un taux d’imposition de 7 %.                                                              | 35-EUPurchaseReduced</br>35-UseTaxEUPurchaseReduced (93/61)          |
| 36  | 95             | 98               | Acquisitions intracommunautaires imposables à d’autres taux d’imposition.                                                                      | 36-EUPurchaseOtherRates</br>36-UseTaxEUPurchaseOtherRates (95/98/61) |
| 37  | 94             | 96               | Acquisitions intracommunautaires imposables de véhicules neufs auprès de fournisseurs n’ayant pas de numéro d’identification TVA, au taux d’imposition général. | 37-EUPurchaseVehicles</br>37-UseTaxEUPurchaseVehicles (94/96/61)     |

**SECTION – BÉNÉFICIAIRE EN TANT QUE DÉBITEUR FISCAL**

| Ligne | Case – Base de taxe | Case - Montant de la taxe | Description                                                                        | Résultat de la recherche                                                                                        |
|-----|----------------|------------------|------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
| 40  | 46             | 47               | Autres services d’un entrepreneur, basés sur le reste de la zone communautaire.        | 40-BeneficiaryTaxDebtor</br>40-UseTaxBeneficiaryTaxDebtor (46/47/66)                                                                              |
| 41  | 73             | 74               | Les ventes qui relèvent de l’article 13b (2) no. 3 de l’UStG.                               | 41-BeneficiaryTaxDebtorRealEstateTransfer</br>41-UseTaxBeneficiaryTaxDebtorRealEstateTransfer (73/74/67) |
| 42  | 84             | 85               | Autres services qui relèvent de l’article 13b (2) no. 1, 2 et 4 à 12 de l’UStG. | 42-BeneficiaryTaxDebtorOther</br>42-UseTaxBeneficiaryTaxDebtorOther (84/85/67)                           |

**SECTION – INFORMATIONS COMPLÉMENTAIRES SUR LES VENTES**

| Ligne | Case – Base de taxe  | Case - Montant de la taxe | Description                                                                                                | Résultat de la recherche                                                                                    |
|-----|-----------------|------------------|------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|
| 48  | 42              | *Aucun montant de taxe*  | Livraisons par le premier client dans le cas de transactions triangulaires intracommunautaires.                   | 48-DeliveriesFirstCustomerEUTriangular                                                           |
| 49  | 60              | *Aucun montant de taxe*  | Ventes imposables de l’entrepreneur pour lesquelles le destinataire de la prestation est redevable de la taxe. | 49-SalesServicesReverseCharge                                                                    |
| 50  | 21              | *Aucun montant de taxe*  | Autres services non imposables.                                                                                | 50-OtherServicesNonTaxable                                                                       |
| 51  | 45              | *Aucun montant de taxe*  | Autres ventes non imposables lorsque le lieu d’exécution n’est pas en Allemagne.                                    | 51-OtherSalesNonTaxable                                                                          |
| 52  | *Aucun montant de taxe* | *Aucun montant de taxe*  | TVA.                                                                                                       | Ligne 20 + Ligne 21 + Ligne 22 + Ligne 2 4 + Ligne 34 + Ligne 35 + Ligne 36 + Ligne 37 + Ligne 40 + Ligne 41 + Ligne 42 |

**SECTION – TAXE SUR LES INTRANTS DÉDUCTIBLE**

| Ligne | Case - Montant de la taxe | Description                                                                                                | Résultat de la recherche                                                                                                                                                                |
|-----|------------------|------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 55  | 66               | Saisissez les montants de taxes des factures d’autres sociétés, services et transactions triangulaires intracommunautaires.     | 55-InputTax 40-UseTaxBeneficiaryTaxDebtor (46/47/66)</br>74-BadDebtsWriteOffInputTax (66/37) – avec signe moins                                                                   |
| 56  | 61               | Montants des taxes sur les intrants provenant de l’acquisition intracommunautaire de marchandises.                                           | 56-InputTaxEUPurchase 34-UseTaxEUPurchaseStandard (89/61)</br>35-UseTaxEUPurchaseReduced (93/61)</br>36-UseTaxEUPurchaseOtherRates (95/98/61)</br>37-UseTaxEUPurchaseVehicles (94/96/61) |
| 57  | 62               | Taxe de vente à l’importation encourue.                                                                                 | 57-InputTaxImport                                                                                                                                                            |
| 58  | 67               | Montants des taxes sur les intrants provenant des services conformément à l’article 13b de l’UStG.                                        | 58-InputTaxServices</br>41-UseTaxBeneficiaryTaxDebtorRealEstateTransfer (73/74/67)</br>42-UseTaxBeneficiaryTaxDebtorOther (84/85/67)                                                 |
| 59  | 63               | Montants des taxes sur les intrants calculées selon les taux moyens généraux.                                  | 59-InputTaxAverageRates</br>74-BadDebtsWriteOffInputTaxAverageRates (63/37) – avec signe moins                                                                                    |
| 60  | 59               | Déduction des taxes sur les intrants pour les livraisons intracommunautaires de véhicules neufs hors entreprise et PME. | 60-InputTaxEUPurchaseNewVehicles</br>74-BadDebtsWriteOffInputTaxEUPurchaseNewVehicles (59/37) – avec signe moins                                                                  |
| 61  | 64               | Correction de la déduction de la taxe sur les intrants.                                                                     | 61-InputTaxCorrection                                                                                                                                                        |
| 62  | \-               | Montant restant.                                                                                      | Ligne 52 – Ligne 55 – Ligne 56 – Ligne 57 – Ligne 58 – Ligne 50 – Ligne 60 – Ligne 61                                                                                                        |

**SECTION – AUTRES MONTANTS DE TAXES**

| Ligne | Case - Montant de la taxe | Description                                                                                                                                                                                                                                                         | Résultat de la recherche                                 |
|-----|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| 64  | 65               | Impôt en raison d’un changement de forme d’imposition et impôt supplémentaire sur les acomptes taxés en raison d’un changement de taux d’imposition.                                                                                                                                        | 64-AdditionalTaxDueChangeTaxRate              |
| 65  | 69               | Les montants de taxes incorrects ou injustifiés qui sont indiqués sur les factures et les montants de taxes qui sont dus conformément à l’article 6a (4) phrase 2, article 17 (1) phrase 7 ou l’article 25b (2) de l’UStG, ou qui sont dus par une entreprise de sous-traitance ou une société d’entreposage. | 65-TaxDecreaseCorrection                      |
| 67  | 39               | Déduction de l’acompte spécial forfaitaire pour prolongation définitive. Cette ligne n’est généralement remplie qu’avec la dernière notification préalable de la période fiscale.                                                                                                  | Paramètre d’entrée utilisateur dans la boîte de dialogue d’état |
| 68  | 83               | Le paiement anticipé de la taxe de vente restant et l’excédent restant. Inclure un signe moins devant le montant.                                                                                                                                                          | Ligne 62 + Ligne 64 – Ligne 65 – Ligne 66             |

**SECTION – INFORMATIONS COMPLÉMENTAIRES SUR LES RÉDUCTIONS**

| Ligne | Case – Base de taxe | Case - Montant de la taxe | Description                                                            | Résultat de la recherche                                                                                                                                                                                                    |
|-----|----------------|------------------|------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 73  | 50             | \-               | Réduction de l’assiette fiscale sur les lignes 20 à 24.                      | 73-BadDebtsWriteOffStandard (81/50)</br>73-BadDebtsWriteOffReduced (86/50)</br>73-BadDebtsWriteOffOtherRates (35/36/50)</br>73-BadDebtsWriteOffEUSalesAverageRate24 (77/50)</br>73-BadDebtsWriteOffSalesAverageRate24 (76/80/50) |
| 74  | \-             | 37               | Réduction des montants de taxe sur les intrants déductible aux lignes 55, 59 et 60. | 74-BadDebtsWriteOffInputTax (66/37)</br>74-BadDebtsWriteOffInputTaxAverageRates (63/37)</br>74-BadDebtsWriteOffInputTaxEUPurchaseNewVehicles (59/37)                                                                     |

#### <a name="purchase-reverse-charge-vat"></a>Taxe au preneur Achat

Si vous configurez des codes de taxe pour valider la taxe au preneur entrante en utilisant la taxe d’utilisation, associez vos codes de taxe avec le résultat de la recherche **Recherche de champ d’état** qui contient « UseTax » dans le nom.

Vous pouvez également configurer deux codes de taxe distincts : un pour la TVA due et un pour la déduction de la TVA. Associez ensuite chaque code avec l’état de recherche correspondant de la recherche **Champ d’état**.

Par exemple, pour les acquisitions intracommunautaires taxables au taux standard, vous devez configurer le code TVA **UT_S_EU** avec la taxe d’utilisation et l’associer au résultat de la recherche **34-UseTaxEUPurchaseStandard** du champ **Recherche de champ d’état**. Dans ce cas, les montants qui utilisent le code de taxe **UT_S_EU** sont reflétés dans les cases 089 et 061 (lignes 34 et 56).

Vous pouvez également configurer deux codes de taxe :

  - **VAT_S_EU**, qui a une valeur de taux de taxe de -19 %
  - **InVAT_S_EU**, qui a une valeur de taux de taxe de 19 %

Associez ensuite les codes avec les résultats de recherche du champ **Recherche de champ d’état** de la manière suivante :

  - Associez **AT_S_EU** avec le résultat de la recherche **34-EUPurchaseStandard**.
  - Associez **InVAT_S_EU** avec le résultat de la recherche **56-InputTaxEUPurchase**.

Dans ce cas, les montants qui utilisent le code de taxe de vente **VAT_S_EU** sont reflétés dans la case 089 (ligne 34). Les montants qui utilisent le code de taxe de vente **InVAT_S_EU** sont reflétés dans la case 061 (ligne 56).

Pour plus d’informations sur la configuration de la taxe au preneur, consultez [Taxes au preneur](emea-reverse-charge.md).

## <a name="configure-system-parameters"></a>Configuration des paramètres système

Pour générer une déclaration de TVA, vous devez configurer le numéro fiscal (Steuernummer) de votre organisation.

1. Accédez à **Administration d’organisation** > **Organisations** > **Entités juridiques**.
2. Sélectionnez l’entité juridique, puis sélectionnez **ID enregistrement**.
3. Sélectionnez ou créez l’adresse en Allemagne, puis, sur le raccourci **ID d’enregistrement**, sélectionnez **Ajouter**.
4. Dans le champ **Type d’enregistrement**, sélectionnez le type d’enregistrement dédié à l’Allemagne, et qui utilise la catégorie d’enregistrement **ID entreprise (COID)**.
5. Entrez le numéro de taxe dans le champ **Numéro d’enregistrement**.
6. Sur l’onglet **Général**, dans le champ **Date d’effet**, entrez la date à laquelle le numéro entre en vigueur.

Pour plus d’informations sur la configuration des catégories d’inscription et des types d’inscription, voir [Identifiants d’enregistrement](emea-registration-ids.md).

## <a name="set-up-a-vat-declaration-for-germany"></a>Paramétrer un aperçu de la déclaration de TVA pour l’Allemagne

### <a name="import-er-configurations"></a>Importer les configurations ER

Ouvrez l’espace de travail **Déclaration électronique** et importez les versions suivantes ou ultérieures de ces formats ER :

   - Déclaration de TVA Excel (DE).version.101.16.12.xml
   - Déclaration de TVA XML (DE).version.101.16.xml

### <a name="set-up-application-specific-parameters-for-vat-declaration-fields"></a><a name="set-up-application-specific-parameters-for-vat-declaration-fields"></a>Configurer les paramètres spécifiques à l’application pour les champs de déclaration de TVA

Pour générer automatiquement une déclaration de TVA, associez les codes de taxe dans l’application aux résultats de recherche dans la configuration ER.

Suivez ces étapes pour définir quels codes de taxe génèrent quelles cases sur la déclaration de TVA.

1. Accédez à **Espaces de travail** > **Gestion des états électroniques** et sélectionnez **Configurations des états**.
2. Sélectionnez la configuration **Déclaration de TVA XML (DE)**, puis sélectionnez **Configurations \> Configuration des paramètres spécifiques à l’application**.
3. Sur la page **Paramètres spécifiques à l’application**, dans le raccourci **Recherches**, sélectionnez **Recherche de champ d’état**.
4. Dans le raccourci **Conditions**, définissez les champs suivants pour associer les codes de taxe et les champs d’état.

    | Champ                  | Description                                                                                                                                                                                                                                                                                                          |
    |------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Résultat de la recherche          | Sélectionnez la valeur du champ d’état. Pour plus d’informations sur les valeurs et leur affectation aux lignes de déclaration de TVA, consultez la section [Vue d’ensemble de la déclaration de TVA](#vat-declaration-overview) plus haut dans cette rubrique.                                                                                               |
    | Code taxe               | Sélectionnez le code de taxe à associer au champ d’état. Les transactions de taxe validées qui utilisent le code de taxe sélectionné seront collectées dans la case de déclaration appropriée. Nous vous recommandons de séparer les codes de taxe de telle sorte qu’un code de taxe ne génère des montants que dans une seule case de déclaration. |
    | Classifieur de transactions | Si vous avez créé suffisamment de codes de taxe pour déterminer une case de déclaration, sélectionnez **\*Non vide\***. Si vous n’avez pas créé suffisamment de codes de taxe pour qu’un code de taxe ne génère des montants que dans une seule case de déclaration, configurez un classifieur de transaction. Les classifieurs de transactions suivants sont disponibles :</br>-   **Achat**</br>-   **PurchaseExempt** (achat exonéré de taxe)</br>-   **PurchaseReverseCharge** (taxe déductible provenant d’une taxe au preneur sur achat)</br>-   **Vente**</br>-   **SalesExempt** (vente exonérée de taxe)</br>-   **SalesReverseCharge** (taxe exigible provenant d’une taxe au preneur sur achat ou vente)</br>-   **Taxe d’utilisation**. </br>Pour chaque classifieur de transaction, un classifieur pour l’avoir est également disponible. Par exemple, l’un de ces classifieurs est **PurchaseCreditNote** (avoir sur achat).</br>Assurez-vous de créer deux lignes pour chaque code de taxe de vente : une avec la valeur du classificateur de transaction et une avec le classificateur de transaction pour la valeur de l’avoir. |

    > [!NOTE]
    > Associez tous les codes de taxe aux résultats de recherche. Si des codes de taxe ne doivent pas générer de valeurs dans la déclaration de TVA, associez-les au résultat de recherche **Autre**.

    ![Page Paramètres spécifiques à l’application](media/69ecb881f12819259ca166b9b98b8303.jpg)

5. Dans le champ **État**, changez la valeur sur **Terminé**.
6. Dans le volet Actions, sélectionnez **Exporter** pour exporter les réglages des paramètres spécifiques à l’application.
7. Sélectionnez la configuration **Déclaration de TVA Excel (DE)**, puis, dans le volet Actions, sélectionnez **Importer** pour importer les paramètres que vous avez configurés pour **Déclaration de TVA XML (DE)**.
8. Dans le champ **État**, sélectionnez **Terminé**.

### <a name="set-up-the-vat-reporting-format-for-preview-amounts-in-excel"></a>Configurer le format de déclaration de TVA pour les montants d’aperçu dans Excel

1. Dans l’espace de travail **Gestion des fonctionnalités**, recherchez et activez la fonctionnalité **États de format de déclaration de TVA**.
2. Accédez à **Comptabilité** > **Paramétrage** > **Paramètres de comptabilité**.
3. Sur l’onglet **Taxe de vente**, dans le raccourci  **Options de taxe**, dans le champ **Mise en correspondance des formats de déclaration de TVA**, sélectionnez **Déclaration de TVA Excel (DE)**.

   Ce format est imprimé lorsque vous exécutez l’état **État de la taxe pour la période de règlement**. Il sera également imprimé lorsque vous sélectionnerez **Imprimer** sur la page **Paiements de la taxe**.

4. Sur la page **Autorités fiscales**, sélectionnez l’administration fiscale, puis, dans le champ **Présentation d’état**, sélectionnez **Par défaut**.

Si vous configurez la déclaration de TVA dans une entité juridique qui a [plusieurs immatriculations à la TVA](emea-reporting-for-multiple-vat-registrations.md), procédez comme suit :

1. Accédez à **Comptabilité** > **Paramétrage** > **Paramètres de comptabilité**.
2. Dans l’onglet **Taxe de vente**, dans le raccourci **Gestion des états électroniques pour les pays/régions**, sur la ligne **CHE**, sélectionnez le format ER **Déclaration de TVA Excel (DE)**.

## <a name="set-up-electronic-messages"></a>Paramétrer des messages électroniques

### <a name="download-and-import-the-data-package-that-has-example-settings-for-electronic-messages"></a>Télécharger et importer le package de données ayant un exemple de paramètres pour les messages électroniques

Le package de données contient des paramètres de message électronique utilisés pour générer la déclaration de TVA au format XML et la prévisualiser dans Excel. Vous pouvez développer ces paramètres ou créer les vôtres. Pour plus d’informations sur l’utilisation de la messagerie électronique et la création de vos propres paramètres, consultez [Messagerie électronique](../general-ledger/electronic-messaging.md).

1. Dans [Microsoft Dynamics Lifecycle Services(LCS)](https://lcs.dynamics.com/v2), dans la bibliothèque d’actifs partagés, sélectionnez **Package de données** comme type d’actif, puis téléchargez le **package EM Déclaration de TVA DE**. Le fichier téléchargé s’appelle **package EM Déclaration de TVA DE.zip**.
2. Dans Dynamics 365 Finance, dans l’espace de travail **Gestion des données**, sélectionnez **Importer**.
3. Dans le raccourci **Importer**, dans le champ **Nom de groupe**, entrez un nom pour la tâche.
4. Dans le raccourci **Entités sélectionnées**, sélectionnez **Ajouter un fichier**.
5. Dans la boîte de dialogue **Ajouter un fichier**, vérifiez que le champ **Format des données source** est défini sur **Package**, sélectionnez **Charger et ajouter**, puis sélectionnez le fichier .zip que vous avez précédemment téléchargé.
6. Sélectionnez **Fermer**.
7. Une fois les entités de données chargées, dans le volet Actions, sélectionnez **Importer**.
8. Accédez à **Taxe** > **Recherches et états** > **Messages électroniques** > **Messages électroniques**, puis validez le traitement des messages électroniques que vous avez importé.

### <a name="configure-electronic-messages"></a>Configurer les messages électroniques

1. Accédez à **Taxe** > **Paramétrage** > **Messages électroniques** > **Actions Renseignement des enregistrements**.
2. Sélectionnez la ligne **Remplir les enregistrement de retour TVA DE**, puis sélectionnez **Modifier la requête**.
3. Utilisez le filtre pour spécifier les périodes de règlement à inclure dans l’état.
4. Si vous devez déclarer les transactions fiscales d’autres périodes de règlement dans une déclaration différente, créez une action **Remplir les enregistrements** et sélectionnez les périodes de règlement appropriées.

## <a name="preview-the-vat-declaration-in-excel"></a>Aperçu de la déclaration de TVA dans Excel

### <a name="preview-the-vat-declaration-in-excel-from-the-report-sales-tax-for-settlement-period-periodic-task"></a> Prévisualisez la déclaration de TVA dans Excel à partir de la tâche périodique État de la taxe pour la période de règlement

1. Accédez à **Taxe** > **Tâches périodiques** > **Déclarations** > **Taxe de vente** > **État de la taxe pour la période de règlement**.
2. Sélectionnez une valeur dans le champ **Période de règlement**.
3. Sélectionnez l’une des valeurs suivantes dans le champ **Version de paiement de la taxe** :

    - **Original** : permet de générer un état pour les transactions de taxe du paiement de taxe d’origine ou avant que le paiement de taxe ne soit généré.
    - **Corrections** : permet de générer un état pour les transactions de taxe de tous les paiements de taxe ultérieurs pour la période.
    - **Liste totale** : permet de générer un état pour toutes les transactions de taxe pour la période, y compris l’original et toutes les corrections.

4. Dans le champ **Date de début**, sélectionnez la date de début de la période de déclaration.
5. Sélectionnez **OK** et passez en revue la déclaration Excel.

### <a name="settle-and-post-sales-tax"></a><a name="settle-and-post-sales-tax"></a>Régler et valider la taxe

1. Accédez à **Taxe** > **Tâches périodiques** > **Déclarations** > **Taxe de vente** > **Régler et valider la taxe**.
2. Sélectionnez une valeur dans le champ **Période de règlement**.
3. Sélectionnez l’une des valeurs suivantes dans le champ **Version de paiement de la taxe** :

    - **Original** : permet de générer le paiement de la taxe d’origine pour la période de règlement.
    - **Dernières corrections** : permet de générer un paiement de taxe rectificatif après la création du paiement de taxe d’origine pour la période de règlement.

4. Dans le champ **Date de début**, sélectionnez la date de début de la période de déclaration.
5. Cliquez sur **OK**.

### <a name="preview-the-vat-declaration-in-excel-from-a-sales-tax-payment"></a>Aperçu de la déclaration de TVA dans Excel à partir du paiement de la taxe de vente

1. Accédez à **Taxe** > **Recherches et états** > **Taxe (recherches)** > **Paiements de la taxe**, puis sélectionnez une ligne de paiement de taxe.
2. Sélectionnez **Imprimer un état**, puis **OK**.
3. Examinez ensuite le fichier Excel généré pour la ligne de paiement de taxe sélectionnée.

    > [!NOTE]
    > L’état est généré uniquement pour la ligne sélectionnée du paiement de taxe. Pour générer, par exemple, une déclaration rectificative contenant toutes les corrections pour la période, ou une déclaration de remplacement qui contient les données d’origine et toutes les corrections, utilisez la tâche périodique **État de la taxe pour la période de règlement**.

## <a name="generate-a-vat-declaration-from-electronic-messages"></a>Générer une déclaration de TVA à partir de messages électroniques

Lorsque vous utilisez des messages électroniques pour générer l’état, vous pouvez collecter les données fiscales auprès de plusieurs entités juridiques. Pour plus d’informations, consultez la section [Exécuter une déclaration de TVA pour plusieurs entités juridiques](#run-a-vat-declaration-for-multiple-legal-entities) plus loin dans cette rubrique.

La procédure suivante s’applique à l’exemple de traitement de message électronique que vous avez importé à partir de la bibliothèque d’actifs partagés LCS.

1. Accédez à **Taxe** > **Recherches et états** > **Messages électroniques** > **Messages électroniques**.
2. Dans le volet de navigation à gauche, sélectionnez **Déclaration de TVA DE**.
3. Dans le raccourci **Messages**, sélectionnez **Nouveau**, puis, dans la boîte de dialogue **Exécuter le traitement**, cliquez sur **OK**.
4. Sélectionnez la ligne de message créée, saisissez une description, puis spécifiez les dates de début et de fin de la déclaration.

    > [!NOTE]
    > Les étapes 5 à 7 sont facultatives.

5. Facultatif : Dans le raccourci **Messages**, sélectionnez **Collecter des données**, puis cliquez sur **OK**. Les paiements de taxe qui ont été générés précédemment sont ajoutés au message. Pour plus d’informations, voir la section [Régler et valider la taxe](#settle-and-post-sales-tax) plus haut dans cette rubrique. Si vous ignorez cette étape, vous pouvez toujours générer une déclaration de TVA en utilisant le champ **Version de la déclaration fiscale** dans la boîte de dialogue **Déclaration**.
6. Facultatif : Dans le raccourci **Éléments du message**, passez en revue les paiements de taxe qui sont transférés pour traitement. Par défaut, tous les paiements de taxe de la période sélectionnée qui n’étaient inclus dans aucun autre message du même traitement sont inclus.
7. Facultatif : Sélectionnez **Document d’origine** pour examiner les paiements de taxe, ou sélectionnez **Supprimer** pour exclure les paiements de taxe du traitement. Si vous ignorez cette étape, vous pouvez toujours générer une déclaration de TVA en utilisant le champ **Version de la déclaration fiscale** dans la boîte de dialogue **Déclaration**.
8. Dans le raccourci **Messages**, sélectionnez **Mettre à jour le statut**. Dans la boîte de dialogue **Mettre à jour le statut**, sélectionnez **Prêt à générer**, puis cliquez sur **OK**. Vérifiez que l’état du message est modifié en **Prêt à générer**.
9. Sélectionnez **Générer l’état**. Pour prévisualiser les montants de la déclaration de TVA, dans la boîte de dialogue **Exécuter le traitement**, sélectionnez **Aperçu de l’état**, puis cliquez sur **OK**.
10. Dans la boîte de dialogue **Paramètres de gestion des états électroniques**, définissez les champs suivants, puis cliquez sur **OK**.

    | **Champ**                                   | **Description**                                                                                                                                                                                                              |
    |---------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Période de règlement                           | Sélectionnez la période de règlement. Si vous avez sélectionné **Collecter des données** à l’étape 5, vous pouvez laisser ce champ vide. L’état sera généré pour les transactions de taxe qui sont incluses dans les paiements de taxe collectés. |
    | Version de la déclaration de taxe                     | Vous devez sélectionner l’une des valeurs suivantes :</br>-   **Original** : permet de générer un état pour les transactions de taxe du paiement de taxe d’origine ou avant que le paiement de taxe ne soit généré.</br>-   **Corrections** : permet de générer un état pour les transactions de taxe de tous les paiements de taxe ultérieurs pour la période.</br>-   **Liste totale** : permet de générer un état pour toutes les transactions de taxe pour la période, y compris l’original et toutes les corrections.|
    | Représentant fiscal | Sélectionnez la partie qui est un représentant fiscal pour la déclaration de TVA, le cas échéant. Les informations sur la partie sélectionnée sont exportées vers l’élément XML **DatenLieferant**. |
    | Personne à contacter | Sélectionnez une personne dans l’organisation qui est un fournisseur de données. Les informations sur la personne sélectionnée sont exportées vers l’élément XML **DatenLieferant**. |
    | Retour correctif | Sélectionnez **Oui** s’il s’agit d’une déclaration TVA rectificative. Dans ce cas, l’élément XML KZ10 aura une valeur de **1**.|
    | Documents justificatifs | Sélectionnez **Oui** si vous envoyez également des pièces justificatives. Dans ce cas, l’élément XML KZ22 aura une valeur de **1**.|
    | Le mandat SEPA de prélèvement automatique sera révoqué comme exception| Sélectionnez **Oui** si le mandat de prélèvement SEPA sera révoqué à titre exceptionnel pour cette période de pré-enregistrement. Par exemple, en raison de demandes de compensation. Tout solde restant doit être payé séparément. Dans ce cas, l’élément XML KZ26 aura une valeur de **1**. |
    | Compensation du montant du remboursement souhaité | Sélectionnez **Oui** si la compensation du montant du remboursement souhaitée ou si le montant du remboursement a été affecté. Dans ce cas, l’élément XML KZ29 aura une valeur de **1**. |
    | Prolongation définitive de l’acompte spécial | Entrez le montant de déduction de l’acompte spécial forfaitaire pour prolongation définitive. Ce montant n’est généralement renseigné que lors du dernier préenregistrement de la période fiscale. Le montant est exporté dans la ligne 67 (case 39) et l’élément XML KZ39 de la déclaration de TVA. |

11. Sélectionnez **Pièces jointes** dans le coin supérieur droit de la page, puis sélectionnez **Ouvrir**.
12. Vérifiez les montants dans le document Excel, puis sélectionnez **Générer un rapport**.
13. Pour générer une déclaration de TVA au format XML, dans la boîte de dialogue **Exécuter le traitement**, sélectionnez **Générer l’état**, puis cliquez sur **OK**.
14. Dans la boîte de dialogue **Paramètres de la gestion des états électroniques**, définissez les champs suivants tel que décrit à l’étape 10.
15. Sélectionnez **Pièces jointes** dans le coin supérieur droit de la page, téléchargez le fichier et utilisez-le pour votre soumission à l’administration fiscale.

## <a name="run-a-vat-declaration-for-multiple-legal-entities"></a><a name="run-a-vat-declaration-for-multiple-legal-entities"></a>Exécuter une déclaration de TVA pour plusieurs entités juridiques

Pour utiliser les formats pour générer un état sur la déclaration de TVA pour un groupe d’entités juridiques, vous devez d’abord configurer les paramètres spécifiques à l’application des formats ER pour les codes de taxe de toutes les entités juridiques requises.

### <a name="set-up-electronic-messages-to-collect-tax-data-from-several-legal-entities"></a>Configurer des messages électroniques pour collecter des données fiscales auprès de plusieurs entités juridiques

Suivez les étapes suivantes pour configurer des messages électroniques qui vont collecter des données fiscales auprès de plusieurs entités juridiques.

1. Accédez à **Espaces de travail** > **Gestion des fonctionnalités**.
2. Recherchez et sélectionnez la fonctionnalité **Requêtes inter-sociétés pour les actions de remplissage des enregistrements** dans la liste, puis sélectionnez **Activer maintenant**.
3. Accédez à **Taxe** > **Paramétrage** > **Messages électroniques \> Actions Renseignement des enregistrements**.
4. Sur la page **Action Renseigner des enregistrements**, sélectionnez la ligne **Remplir les enregistrement de retour TVA DE**.

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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
