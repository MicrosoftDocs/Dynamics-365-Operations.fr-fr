---
title: Déclaration de TVA (Danemark)
description: Cet article décrit comment configurer et générer une déclaration de taxe sur la valeur ajoutée (TVA) pour le Danemark.
author: anasyash
ms.date: 03/10/2022
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: ''
ms.openlocfilehash: 666dc96cb169ab28ac3938299a3f245e3b4511ab
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862997"
---
# <a name="vat-declaration-denmark"></a>Déclaration de TVA (Danemark)

[!include [banner](../includes/banner.md)]

Cet article décrit comment configurer la déclaration de taxe sur la valeur ajoutée (TVA) pour le Danemark et l’afficher dans Microsoft Excel.

Pour générer automatiquement l’état, vous devez d’abord créer suffisamment de codes de taxe afin de conserver une comptabilité TVA distincte pour chaque case de la déclaration de TVA à l’avance. De plus, dans les paramètres spécifiques à l’application du format de gestion des états électroniques (ER) pour la déclaration de TVA avancée, vous devez associer des codes de taxe avec le résultat des recherches des cases de déclaration de TVA.

Pour le Danemark, vous devez configurer **Recherche de champ d’état**. Pour plus d’informations sur la configuration des paramètres spécifiques à l’application, consultez la section [Configurer les paramètres spécifiques à l’application pour les champs de déclaration de TVA](#set-up-application-specific-parameters) plus loin dans cet article.

Dans les tableaux suivants, la colonne « Résultat de la recherche » affiche le résultat de la recherche préconfiguré pour une ligne de déclaration de TVA spécifique dans le format de déclaration de TVA. Utilisez ces informations pour associer correctement les codes de taxe avec le résultat de la recherche, puis avec la ligne de déclaration de TVA.

### <a name="vat-declaration-overview"></a>Aperçu de la déclaration de TVA

La déclaration de TVA au Danemark contient les informations suivantes.

**VAT payable**

| Description                                                  | Base/Montant de la taxe | Résultat de la recherche/Total                                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| TVA d’aval                                                   | Montant de taxe          | **OutputVAT**</br> **DomesticVATUseTax** (également reporté dans la case « TVA d’amont »)                                                                                                                                                                                                                                                                       |
| TVA sur les marchandises, etc. acheté à l’étranger                           | Montant de taxe          | **PurchaseGoodsAbroad**</br>**PurchaseGoodsAbroadUseTax** (également reporté dans la case « TVA d’amont »)</br>**PurchaseGoodsEU** (La base de taxe est déclarée dans la « Case A - acquisition de biens ».)</br>**PurchaseGoodsEUUseTax** (Le montant de la taxe est également reporté dans la case « TVA d’amont ». La base de taxe est déclarée dans la « Case A - acquisition de biens ».)                   |
| TVA sur les services achetés à l’étranger soumis à la taxe au preneur | Montant de taxe          | **PurchaseServicesAbroad**</br> **PurchaseServicesAbroadUseTax** (également reporté dans la case « TVA d’amont »)</br>**PurchaseServicesEU** (La base de taxe est déclarée dans la « Case A - acquisition de services ».)</br>**PurchaseServicesEUUseTax** (Le montant de la taxe est également reporté dans la case « TVA d’amont ». La base de taxe est déclarée dans la « Case A - acquisition de services ».) |
| Total à payer                                                | Montant de taxe          | Total des trois cases précédentes                                                                                                                                                                                                                                                                                                            |

**Déductions**

| Description                                                                               | Base/Montant de la taxe | Résultat de la recherche/Total                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-------------------------------------------------------------------------------------------|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| TVA d’amont                                                                                 | Montant de taxe          | **InputVAT**</br> **DomesticVATUseTax** (également reporté dans la case « TVA d’aval »)</br>**PurchaseGoodsAbroadUseTax** (également reporté dans la case « TVA sur les biens », etc. acheté à l’étranger »)</br>**PurchaseServicesAbroadUseTax** (également déclarée dans la case « TVA sur les services achetés à l’étranger soumis à taxe au preneur »)</br>**PurchaseGoodsEUUseTax** (également reporté dans la case « TVA sur les biens », etc. acheté à l’étranger »)</br> **PurchaseServicesEUUseTax** (également déclarée dans la case « TVA sur les services achetés à l’étranger soumis à taxe au preneur ») |
| Taxe sur le pétrole et le gaz en bouteille                                                                  | Montant de taxe          | **OilGasDuty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Taxe sur le gaz naturel et le gaz de ville                                                             | Montant de taxe          | **NaturalTownGasDuty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Taxe carbone                                                                               | Montant de taxe          | **CarbonDuty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| CO2Duty                                                                                   | Montant de taxe          | **CO2Duty**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Redevance sur l’eau                                                                              | Montant de taxe          | **WaterCharge**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Total des déductions                                                                          | Montant de taxe          | Total des six cases précédentes                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Montant total des droits (montant positif = effectuer un paiement, montant négatif = recevoir un remboursement) | Montant de taxe          | « Total à payer » – « Déductions totales »                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |

**Informations complémentaires**

| Description                                                                                                                                                                                                                                | Base/Montant de la taxe | Résultat de la recherche/Total                             |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|-------------------------------------------------|
| Case A - acquisition de biens. La valeur hors TVA de l’acquisition de biens au sein de l’Union.                                                                                                                                                   | Base de la taxe            | **PurchaseGoodsEU PurchaseGoodsEUUseTax**       |
| Case A - acquisition de services. La valeur hors TVA de l’acquisition de services au sein de l’Union.                                                                                                                                             | Base de la taxe            | **PurchaseServicesEU PurchaseServicesEUUseTax** |
| Case B - livraison de biens - à déclarer à « EU-sales without VAT »/DK VIES. La valeur hors TVA de la fourniture de biens au sein de l’Union                                                                                                           | Base de la taxe            | **SalesGoodsEU**                                |
| Case B - fournitures - à ne pas déclarer à « EU-sales without VAT »/DK VIES. La valeur hors TVA de certaines livraisons au sein de l’Union, par exemple l’installation, le montage, les ventes à distance et les nouveaux moyens de transport à des personnes non-soumises à taxe. | Base de la taxe            | **SalesInstallationAssemblyEtcEU**              |
| Case B - fourniture de services. La valeur hors TVA des prestations de services intra-Union pour lesquelles l’acheteur est redevable de la TVA au titre de taxe au preneur - doit également être déclarée à « EU-sales without VAT »/DK VIES.                          | Base de la taxe            | **SalesServicesEU**                             |
| Case C - autres fournitures. Valeur des livraisons d’autres biens et services qui sont fournis sans TVA sur le territoire du Danemark, à d’autres États membres de l’UE et à des pays tiers ou territoires tiers.                                     | Base de la taxe            | **OtherSuppliesWithoutVAT**                     |

#### <a name="purchase-reverse-charge-vat"></a>Taxe au preneur Achat

Si vous configurez des codes de taxe pour valider la taxe au preneur entrante en utilisant la taxe d’utilisation, associez vos codes de taxe avec le résultat de la recherche **Recherche de champ d’état** qui contient « UseTax » dans le nom.

Vous pouvez également configurer deux codes de taxe distincts : un pour la TVA due et un pour la déduction de la TVA. Associez ensuite chaque code avec l’état de recherche correspondant de la recherche **Champ d’état**.

Par exemple, pour les acquisitions intracommunautaires taxables au taux standard, vous devez configurer le code TVA **UT_S_EU** avec la taxe d’utilisation et l’associer au résultat de la recherche **PurchaseGoodsEUUseTax** du champ **Recherche de champ d’état**. Dans ce cas, les montants de taxe qui utilisent le code de taxe **UT_S_EU** sont reflétés dans les cases « TVA sur les biens etc. achetés à l’étranger » et « TVA d’amont ». Les bases de taxe sont reflétées dans la « Case A - acquisition de biens ».

Vous pouvez également configurer deux codes de taxe :

- **VAT_S_EU**, qui a une valeur de taux de taxe de -25 %
- **InVAT_S_EU**, qui a une valeur de taux de taxe de 25 %

Associez ensuite les codes avec les résultats de recherche du champ **Recherche de champ d’état** de la manière suivante :

- Associez **AT_S_EU** avec le résultat de la recherche **PurchaseGoodsEU**.
- Associez **InVAT_S_EU** avec le résultat de la recherche **InputVAT**.

Dans ce cas, les montants de taxe qui utilisent le code de taxe **VAT_S_EU** sont reflétés dans les cases « TVA sur les biens etc. achetés à l’étranger » et « Case A - acquisition de biens ». Les montants qui utilisent le code de taxe de vente **InVAT_S_EU** sont reflétés dans la case « TVA d’amont ».

Pour plus d’informations sur la configuration de la taxe au preneur, consultez [Taxes au preneur](emea-reverse-charge.md).

## <a name="configure-system-parameters"></a>Configuration des paramètres système

Pour générer une déclaration de TVA, vous devez configurer le numéro de TVA.

1. Accédez à **Administration d’organisation** > **Organisations** > **Entités juridiques**.
2. Sélectionnez l’entité juridique, puis sélectionnez **ID enregistrement**.
3. Sélectionnez ou créez l’adresse au Danemark, puis, sur le raccourci **ID d’enregistrement**, sélectionnez **Ajouter**.
4. Dans le champ **Type d’enregistrement**, sélectionnez le type d’enregistrement dédié au Danemark, et qui utilise la catégorie d’enregistrement **N° de TVA**.
5. Entrez le numéro de taxe dans le champ **Numéro d’enregistrement**.
6. Sur l’onglet **Général**, dans le champ **Date d’effet**, entrez la date à laquelle le numéro entre en vigueur.

Pour plus d’informations sur la configuration des catégories d’inscription et des types d’inscription, voir [Identifiants d’enregistrement](emea-registration-ids.md).

## <a name="set-up-a-vat-declaration-preview-for-denmark"></a>Paramétrer un aperçu de la déclaration de TVA pour le Danemark

### <a name="import-er-configurations"></a>Importer les configurations ER

Ouvrez l’espace de travail **Gestion des états électroniques** et importez le format ER **Déclaration de TVA Excel (DK)**.

Pour plus d’informations, voir [Télécharger les configurations des états électroniques (ER) à partir du référentiel global de Configuration Service](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

### <a name="set-up-application-specific-parameters-for-vat-declaration-fields"></a><a name="set-up-application-specific-parameters"></a>Configurer les paramètres spécifiques à l’application pour les champs de déclaration de TVA

> [!NOTE]
> Nous vous recommandons d’activer la fonctionnalité, **Utiliser les paramètres spécifiques à l’application des versions précédentes de formats de rapport électronique** dans l’espace de travail **Gestion des fonctionnalités**. Lorsque cette fonctionnalité est activée, les paramètres configurés pour la version antérieure d’un format ER deviennent automatiquement applicables pour la version ultérieure du même format. Si cette fonctionnalité n’est pas activée, vous devez configurer explicitement les paramètres spécifiques à l’application pour chaque version de format. La fonctionnalité, **Utiliser les paramètres spécifiques à l’application des versions précédentes de formats de rapport électronique** est disponible dans l’espace de travail **Gestion des fonctionnalités** à partir de la version Finance 10.0.23. Pour plus d’informations sur la configuration des paramètres d’un format ER pour chaque entité juridique, voir [Définir les paramètres d’un format de gestion des états électroniques par entité juridique](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-set-up.md).

Pour générer automatiquement une déclaration de TVA, associez les codes de taxe dans l’application aux résultats de recherche dans la configuration ER.

Suivez ces étapes pour définir quels codes de taxe génèrent quelles cases sur la déclaration de TVA.

1. Accédez à **Espaces de travail** > **Gestion des états électroniques** et sélectionnez **Configurations des états**.
2. Sélectionnez la configuration **Déclaration de TVA Excel (DK)**, puis sélectionnez **Configurations \> Configuration des paramètres spécifiques à l’application**.
3. Sur la page **Paramètres spécifiques à l’application**, dans le raccourci **Recherches**, sélectionnez **Recherche de champ d’état**.
4. Dans le raccourci **Conditions**, définissez les champs suivants pour associer les codes de taxe et les champs d’état.

    | Champ                  | Description                                                                                                                                                                                                                                                                                                          |
    |------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Résultat de la recherche          | Sélectionnez la valeur du champ d’état. Pour plus d’informations sur les valeurs et leur affectation aux lignes de déclaration de TVA, consultez la section [Vue d’ensemble de la déclaration de TVA](#vat-declaration-overview) plus haut dans cet article.                                                                                               |
    | Code de taxe               | Sélectionnez le code de taxe à associer au champ d’état. Les transactions de taxe validées qui utilisent le code de taxe sélectionné seront collectées dans la case de déclaration appropriée. Nous vous recommandons de séparer les codes de taxe de telle sorte qu’un code de taxe ne génère des montants que dans une seule case de déclaration. |
    | Classifieur de transactions | Si vous avez créé suffisamment de codes de taxe pour déterminer une case de déclaration, sélectionnez **\*Non vide\***. Si vous n’avez pas créé suffisamment de codes de taxe pour qu’un code de taxe ne génère des montants que dans une seule case de déclaration, configurez un classifieur de transaction. Les classifieurs de transactions suivants sont disponibles :</br>-   **Achat**</br>-   **PurchaseExempt** (achat exonéré de taxe)</br>-   **PurchaseReverseCharge** (taxe déductible provenant d’une taxe au preneur sur achat)</br>-   **Vente**</br>-   **SalesExempt** (vente exonérée de taxe)</br>-   **SalesReverseCharge** (taxe exigible provenant d’une taxe au preneur sur achat ou vente)</br>-   **Taxe d’utilisation**. </br>Pour chaque classifieur de transaction, un classifieur pour l’avoir est également disponible. Par exemple, l’un de ces classifieurs est **PurchaseCreditNote** (avoir sur achat).</br>Assurez-vous de créer deux lignes pour chaque code de taxe de vente : une avec la valeur du classificateur de transaction et une avec le classificateur de transaction pour la valeur de l’avoir. |


    > [!NOTE]
    > Associez tous les codes de taxe aux résultats de recherche. Si des codes de taxe ne doivent pas générer de valeurs dans la déclaration de TVA, associez-les au résultat de recherche **Autre**.

    ![Page Paramètres spécifiques à l’application.](media/7db74920fad66a0db7fad60758698cc0.png)


5. Dans le champ **État**, changez la valeur sur **Terminé**.

### <a name="set-up-the-vat-reporting-format-for-preview-amounts-in-excel"></a>Configurer le format de déclaration de TVA pour les montants d’aperçu dans Excel

1. Dans l’espace de travail **Gestion des fonctionnalités**, recherchez et sélectionnez la fonctionnalité **États de format de déclaration de TVA.** dans la liste, puis sélectionnez **Activer maintenant**.
2. Accédez à **Comptabilité** > **Paramétrage** > **Paramètres de comptabilité**.
3. Sur l’onglet **Taxe de vente**, dans le raccourci **Options de taxe**, dans le champ **Mappage des formats de déclaration de TVA**, sélectionnez le format ER **Déclaration de TVA Excel (DK)**.

   Ce format est imprimé lorsque vous exécutez l’état **État de la taxe pour la période de règlement**. Il sera également imprimé lorsque vous sélectionnerez **Imprimer** sur la page **Paiements de la taxe**.

4. Sur la page **Autorités fiscales**, sélectionnez l’administration fiscale, puis, dans le champ **Présentation d’état**, sélectionnez **Par défaut**.

Si vous configurez la déclaration de TVA dans une entité juridique qui a [plusieurs immatriculations à la TVA](emea-reporting-for-multiple-vat-registrations.md), procédez comme suit.

1. Accédez à **Comptabilité** \> **Paramétrage** \> **Paramètres de comptabilité**.
2. Dans l’onglet **Taxe de vente**, dans le raccourci **Gestion des états électroniques pour les pays/régions**, sur la ligne **DNK**, sélectionnez le format ER **Déclaration de TVA Excel (DK)**.

## <a name="set-up-electronic-messages"></a>Paramétrer des messages électroniques

### <a name="download-and-import-the-data-package-that-has-example-settings-for-electronic-messages"></a>Télécharger et importer le package de données ayant un exemple de paramètres pour les messages électroniques

Le package de données contient des paramètres de message électronique utilisés pour générer et prévisualiser la déclaration de TVA au format Excel. Vous pouvez développer ces paramètres ou créer les vôtres. Pour plus d’informations sur l’utilisation de la messagerie électronique et la création de vos propres paramètres, consultez [Messagerie électronique](../general-ledger/electronic-messaging.md).

1. Dans [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/v2), dans la bibliothèque d’actifs partagés, sélectionnez **Package de données** comme type d’actif, puis téléchargez le **Package EM Déclaration de TVA DK**. Le fichier téléchargé se nomme **DK VAT declaration package.zip**.
2. Dans Finance, dans l’espace de travail **Gestion des données**, sélectionnez **Importer**.
3. Dans le raccourci **Importer**, dans le champ **Nom de groupe**, entrez un nom pour la tâche.
4. Dans le raccourci **Entités sélectionnées**, sélectionnez **Ajouter un fichier**.
5. Dans la boîte de dialogue **Ajouter un fichier**, vérifiez que le champ **Format des données source** est défini sur **Package**, sélectionnez **Charger et ajouter**, puis sélectionnez le fichier .zip que vous avez précédemment téléchargé.
6. Sélectionnez **Fermer**.
7. Une fois les entités de données chargées, dans le volet Actions, sélectionnez **Importer**.
8. Accédez à **Taxe** > **Recherches et états** > **Messages électroniques** > **Messages électroniques**, puis validez le traitement des messages électroniques que vous avez importé (**Déclaration de TVA DK**).

### <a name="configure-electronic-messages"></a>Configurer les messages électroniques

1. Accédez à **Taxe** > **Paramétrage** > **Messages électroniques** > **Actions Renseignement des enregistrements**.
2. Sélectionnez la ligne **Remplir les enregistrement de retour TVA DK**, puis sélectionnez **Modifier la requête**.
3. Utilisez le filtre pour spécifier les périodes de règlement à inclure dans l’état.
4. Si vous devez déclarer les transactions fiscales d’autres périodes de règlement dans une déclaration différente, créez une action **Remplir les enregistrements** et sélectionnez les périodes de règlement appropriées.

## <a name="preview-the-vat-declaration-in-excel"></a>Aperçu de la déclaration de TVA dans Excel

### <a name="preview-the-vat-declaration-in-excel-from-the-report-sales-tax-for-settlement-period-periodic-task"></a><a name="preview-vat-excel"></a> Prévisualisez la déclaration de TVA dans Excel à partir de la tâche périodique État de la taxe pour la période de règlement

1. Accédez à **Taxe** > **Tâches périodiques** > **Déclarations** > **Taxe de vente** > **État de la taxe pour la période de règlement**.
2. Sélectionnez une valeur dans le champ **Période de règlement**.
3. Sélectionnez l’une des valeurs suivantes dans le champ **Version de paiement de la taxe** :

    - **Original** : permet de générer un état pour les transactions de taxe du paiement de taxe d’origine ou avant que le paiement de taxe ne soit généré.
    - **Corrections** : permet de générer un état pour les transactions de taxe de tous les paiements de taxe ultérieurs pour la période.
    - **Liste totale** : permet de générer un état pour toutes les transactions de taxe pour la période, y compris l’original et toutes les corrections.

4. Dans le champ **Date de début**, sélectionnez la date de début de la période de déclaration.
5. Sélectionnez **OK** et passez en revue la déclaration Excel.

### <a name="settle-and-post-sales-tax"></a>Régler et valider la taxe

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
> L’état est généré uniquement pour la ligne sélectionnée du paiement de taxe. Si vous devez générer, par exemple, une déclaration rectificative contenant toutes les corrections pour la période, ou une déclaration de remplacement qui contient les données d’origine et toutes les corrections, utilisez la tâche périodique **État de la taxe pour la période de règlement**.

## <a name="generate-a-vat-declaration-from-electronic-messages"></a>Générer une déclaration de TVA à partir de messages électroniques

Lorsque vous utilisez des messages électroniques pour générer l’état, vous pouvez collecter les données fiscales auprès de plusieurs entités juridiques. Pour plus d’informations, consultez la section [Exécuter une déclaration de TVA pour plusieurs entités juridiques](#run-vat-declaration) plus loin dans cet article.

La procédure suivante s’applique à l’exemple de traitement de message électronique que vous avez importé précédemment à partir de la bibliothèque d’actifs partagés LCS.

1. Accédez à **Taxe \> Recherches et états \> Messages électroniques \> Messages électroniques**.
2. Dans le volet de navigation à gauche, sélectionnez **Déclaration de TVA DK**.
3. Dans le raccourci **Messages**, sélectionnez **Nouveau**, puis, dans la boîte de dialogue **Exécuter le traitement**, cliquez sur **OK**.
4. Sélectionnez la ligne de message créée, saisissez une description, puis spécifiez les dates de début et de fin de la déclaration.

   > [!NOTE]
   > Les étapes 5 à 7 sont facultatives.

5. Facultatif : Dans le raccourci **Messages**, sélectionnez **Collecter des données**, puis cliquez sur **OK**. Les paiements de taxe qui ont été générés précédemment sont ajoutés au message. Pour plus d’informations, voir la section [Régler et valider la taxe](#settle-and-post-sales-tax) plus haut dans cet article. Si vous ignorez cette étape, vous pouvez toujours générer une déclaration de TVA en utilisant le champ **Version de la déclaration fiscale** dans la boîte de dialogue **Déclaration**.
6. Facultatif : Dans le raccourci **Éléments du message**, passez en revue les paiements de taxe qui sont transférés pour traitement. Par défaut, tous les paiements de taxe de la période sélectionnée qui n’étaient inclus dans aucun autre message du même traitement sont inclus.
7. Facultatif : Sélectionnez **Document d’origine** pour examiner les paiements de taxe, ou sélectionnez **Supprimer** pour exclure les paiements de taxe du traitement. Si vous ignorez cette étape, vous pouvez toujours générer une déclaration de TVA en utilisant le champ **Version de la déclaration fiscale** dans la boîte de dialogue **Déclaration**.
8. Dans le raccourci **Messages**, sélectionnez **Mettre à jour le statut**. Dans la boîte de dialogue **Mettre à jour le statut**, sélectionnez **Prêt à générer**, puis cliquez sur **OK**. Vérifiez que l’état du message est modifié en **Prêt à générer**.
9. Sélectionnez **Générer l’état**. Pour prévisualiser les montants de la déclaration de TVA, dans la boîte de dialogue **Exécuter le traitement**, sélectionnez **Aperçu de l’état**, puis cliquez sur **OK**.
10. Dans la boîte de dialogue **Paramètres de gestion des états électroniques**, définissez les champs comme décrit dans la section [Aperçu de la déclaration de TVA dans Excel à partir de la tâche périodique État de la taxe pour la période de règlement](#preview-vat-excel) plus haut dans cet article, puis sélectionnez **OK**.
11. Cliquez sur le bouton **Pièces jointes** (le symbole du trombone) dans l’angle supérieur droit de la page, puis sélectionnez **Ouvrir** pour ouvrir le fichier. Vérifiez les montants dans le document Excel.

## <a name="run-a-vat-declaration-for-multiple-legal-entities"></a><a name="run-vat-declaration"></a>Exécuter une déclaration de TVA pour plusieurs entités juridiques

Pour utiliser les formats pour générer un état sur la déclaration de TVA pour un groupe d’entités juridiques, vous devez d’abord configurer les paramètres spécifiques à l’application des formats ER pour les codes de taxe de toutes les entités juridiques requises.

### <a name="set-up-electronic-messages-to-collect-tax-data-from-several-legal-entities"></a>Configurer des messages électroniques pour collecter des données fiscales auprès de plusieurs entités juridiques

Suivez les étapes suivantes pour configurer des messages électroniques pour collecter des données fiscales auprès de plusieurs entités juridiques.

1. Accédez à **Espaces de travail** > **Gestion des fonctionnalités**.
2. Recherchez et sélectionnez la fonctionnalité **Requêtes inter-sociétés pour les actions de remplissage des enregistrements** dans la liste, puis sélectionnez **Activer maintenant**.
3. Accédez à **Taxe** > **Paramétrage** > **Messages électroniques** > **Actions Renseignement des enregistrements**.
4. Sur la page **Action Renseigner des enregistrements**, sélectionnez la ligne **Remplir les enregistrement de retour TVA DK**.

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
