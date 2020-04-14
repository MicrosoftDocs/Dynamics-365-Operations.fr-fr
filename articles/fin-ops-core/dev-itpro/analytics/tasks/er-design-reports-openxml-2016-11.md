---
title: ER Concevoir une configuration pour générer des états au format OPENXML (novembre 2016)
description: Cette rubrique explique comment un utilisateur dont le rôle est Administrateur système ou Développeur d'états électroniques peut créer une configuration de format pour la génération d'états électronique (ER) qui contient un modèle pour générer des documents électroniques au format OPENXML.
author: NickSelin
manager: AnnBe
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERDataSourceAddDropDialog, ERModelGroupByFunctionEditor, VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ea5b17873dea4508230f39ffb41a50e2f427584f
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142130"
---
# <a name="er-design-a-configuration-for-generating-reports-in-openxml-format-november-2016"></a>ER Concevoir une configuration pour générer des états au format OPENXML (novembre 2016)

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment un utilisateur dont le rôle est Administrateur système ou Développeur d'états électroniques peut créer une configuration de format pour la génération d'états électronique (ER) qui contient un modèle pour générer des documents électroniques au format OPENXML. Cette configuration sera utilisée pour traiter les paiements fournisseur.

Dans cet exemple, vous allez créer une configuration pour la société témoin, Litware, Inc. Ces étapes peuvent être effectuées dans la société GBSI.

Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ». Vous devez également avoir un fichier Excel qui sera importé lorsque vous créez le modèle. Ce fichier est accessible depuis le [Modèle d'état de paiement](https://go.microsoft.com/fwlink/?linkid=862266).


## <a name="upload-the-payments-data-model-configuration"></a>Téléchargez la configuration du modèle de données des paiements
1. Dans le volet de navigation, accédez à **Modules > Administration d'organisation > Espaces de travail > Gestion des états électroniques**.
2. Dans la liste, sélectionnez le fournisseur de configuration pour la société fictive Litware, Inc. Si vous ne voyez pas ce fournisseur de configuration, vous devez d'abord effectuer les étapes de la procédure dans [Créer des fournisseurs de configuration et les marquer comme actifs](er-configuration-provider-mark-it-active-2016-11.md).
3. Sélectionnez **Activer**.
4. Sélectionnez **Référentiels**. Sélectionnez un référentiel pour le type de ressources opérationnelles, si disponible. S'il n'est pas disponible, ignorez les étapes suivantes sur la création d'un référentiel.  
5. Sélectionnez **Ajouter** pour ouvrir la boîte de dialogue.
6. Dans le champ **Type du référentiel de configuration**, entrez `Operations resourcesdd`.
7. Sélectionnez **Créer un référentiel**.
8. Cliquez sur **OK**.
9. Cliquez sur **Ouvrir**.
10. Dans l'arborescence, sélectionnez **Modèle de paiement**.
11. Sélectionnez **Importer**. Importez ce modèle de données. Il est utilisé comme source de données dans une nouvelle configuration de format. Ignorez cette étape si cette configuration a déjà été importée.  
12. Cliquez sur **Oui**.
13. Fermez les pages jusqu'à ce que vous reveniez à la page de génération d'états électroniques.

## <a name="create-a-new-format-configuration"></a>Créer une configuration de format
1. Sélectionnez **Configurations des états**.
2. Dans l'arborescence, sélectionnez **Modèle de paiement**.
3. Cliquez sur **Créer la configuration** pour ouvrir la boîte de dialogue.
4. Dans le champ **Nouveau**, entrez `Format based on data model PaymentModel`. Créez un format basé sur le modèle de données PaymentModel.
5. Dans le champ **Nom**, saisissez `Sample worksheet report`. Exemple d'état sur les feuilles de calcul  
6. Dans le champ **Description**, saisissez `Sample worksheet report for vendors' payments`. Exemple d'état sur les feuilles de calcul pour les paiements fournisseurs.  
7. Dans le champ **Définition du modèle de données**, entrez ou sélectionnez une valeur. Sélectionnez la définition **CustomerCreditTransferInitiation**.  
8. Sélectionnez **Créer une configuration**.

## <a name="design-a-new-document-in-openxml-worksheet-format"></a>Créez un document dans le format de la feuille de calcul OPENXML
1. Dans l'arborescence, sélectionnez **Modèle de paiement\Exemple d'état sur les feuilles de calcul**.
2. Sélectionnez **Concepteur**.
3. Dans la volet Actions, sélectionnez **Importer**.
4. Sélectionnez **Importer depuis Excel**.
5. Sélectionnez **Pièces jointes**. Joignez le document Excel existant comme modèle.  
6. Sélectionnez **Nouveau**.
7. Sélectionnez **Fichier**. Pointez vers le fichier Excel existant.  
8. Fermez la page.
9. Dans le champ **Modèle**, entrez ou sélectionnez une valeur. Sélectionnez le fichier Excel à utiliser comme modèle.  
10. Cliquez sur **OK**. Notez que les composants de format ER ont été créés dans le format de conception basé sur la structure du document MS Excel de référence (plages nommées).  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a>Créer une nouvelle source de données pour calculer les totaux par codes devise
1. Sélectionnez l'onglet **Mise en correspondance**.
2. Cliquez sur **Ajouter racine** pour ouvrir la boîte de dialogue.
3. Dans l'arborescence, sélectionnez **Fonctions\Grouper par**.
4. Dans le champ **Nom**, saisissez `PaymentByCurrency`.
5. Cliquez sur **Modifier le groupe par**.
6. Dans l'arborescence, développez **modèle**, puis sélectionnez **modèle\Paiements**.
7. Sélectionnez **Ajouter le champ à**.
8. Cliquez sur **Éléments à grouper**.
9. Dans l'arborescence, développez **modèle\Paiements**, puis sélectionnez **modèle\Paiement\Devise**.
10. Sélectionnez **Ajouter le champ à**.
11. Sélectionnez **Champs groupés**.
12. Dans l'arborescence, sélectionnez **modèle\Paiements\Montant ordonné(InstructedAmount)**.
13. Sélectionnez **Ajouter le champ à**, puis sélectionnez **Champs d'agrégation**.
14. Sélectionnez une option dans le champ **Méthode**. Sélectionnez la fonction d'agrégation **SOMME**.  
15. Dans le champ **Nom**, saisissez `TotalInstructuredAmount`.
16. Sélectionnez **Enregistrer**.
17. Fermez la page.
18. Cliquez sur **OK**.

## <a name="map-format-components-to-data-sources"></a>Mettre en correspondance des composants de format vers des sources de données
1. Dans l'arborescence, sélectionnez **modèle\Paiements\Partie qui prend l'initiative\Nom** et **Excel\ReportHeader\CompanyName**.
2. Sélectionnez **Lier**.
3. Dans l'arborescence, sélectionnez **modèle\Paiements\Créancier\Identification\Source ID(SourceID)** et **Excel\PaymLines\VendAccountName**.
4. Sélectionnez **Lier**.
5. Dans l'arborescence, sélectionnez **modèle\Paiements\Créditeur\Nom** et **Excel\PaymLines\VendName**.
6. Sélectionnez **Lier**.
7. Dans l'arborescence, sélectionnez **modèle\Paiements\Créancier(CreditorAgent)\Nom** et **Excel\PaymLines\Banque**.
8. Sélectionnez **Lier**.
9. Dans l'arborescence, sélectionnez **modèle\Paiements\Créancier(CreditorAgent)\Numéro d'acheminement(RoutingNumber)** et **Excel\PaymLines\RoutingNumber**.
10. Sélectionnez **Lier**.
11. Dans l'arborescence, sélectionnez **modèle\Paiements\Créancier(CreditorAccount)\Identification\Numéro** et **Excel\PaymLines\AccountNumber**.
12. Sélectionnez **Lier**.
13. Dans l'arborescence, sélectionnez **modèle\Paiements\Montant ordonné(InstructedAmount)** et **Excel\PaymLines\Débit**.
14. Sélectionnez **Lier**.
15. Dans l'arborescence, sélectionnez **modèle\Paiements\Devise** et **Excel\PaymLines\Devise**.
16. Sélectionnez **Lier**.
17. Dans l'arborescence, sélectionnez **PaymentByCurrency\groupé\Devise** et **Excel\SummaryLines\SummaryCurrency**.
18. Sélectionnez **Lier**.
19. Dans l'arborescence, sélectionnez **PaymentByCurrency\agrégé\TotalInstructuredAmount** et **Excel\SummaryLines\SummaryAmount**.
20. Sélectionnez **Lier**.
21. Dans l'arborescence, sélectionnez **PaymentByCurrency** et **Excel\SummaryLines**.
22. Sélectionnez **Lier**.
23. Dans l'arborescence, sélectionnez **model\Payments** et **Excel\PaymLines**.
24. Sélectionnez **Lier**.
25. Sélectionnez **Sauvegarder**, puis fermez la page.

## <a name="use-the-created-configuration-for-payments-processing"></a>Utiliser la configuration créée pour le traitement des paiements
1. Sélectionnez **Modifier le statut**.
2. Sélectionnez **Terminer**.
3. Cliquez sur **OK**.
4. Dans le Volet de navigation, allez dans **Modules > Comptabilité fournisseur > Paramétrage des paiements > Modes de paiement**.
5. Utilisez le filtre rapide pour filtrer selon le champ **Mode de paiement** avec une valeur de **Électronique**.
6. Sélectionnez **Modifier**.
7. Développez la section **Formats de fichier**.
8. Sélectionnez **Oui** dans le champ **États électroniques génériques**.
9. Entrez ou sélectionnez une valeur dans le champ **Exporter la configuration du format**. Sélectionnez la configuration **Exemple d'état sur les feuilles de calcul**.  
10. Sélectionnez **Enregistrer**.
11. Fermez la page.

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a>Utiliser la configuration créée pour tester le traitement de journaux des paiements
1. Dans le volet de navigation, accédez à **Modules > Comptabilité fournisseur > Paiements > Journal des paiements**.
2. Sélectionnez **Nouveau** pour créer un journal des paiements.
3. Dans le champ **Nom**, tapez **VendPay**.
4. Sélectionnez **Lignes**.
5. Dans le champ **Compte**, spécifiez les valeurs `GB_SI_000001`.
6. Définissez **Débit** sur `1000`.
7. Sélectionnez **Nouveau**.
8. Dans le champ **Compte**, spécifiez les valeurs `GB_SI_000005`.
9. Définissez **Débit** sur `2000`.
10. Dans le champ **Devise**, saisissez `EUR`.
11. Dans le champ **Compte de contrepartie**, spécifiez les valeurs `GBSI OPER`.
12. Dans le champ **Mode de paiement**, saisissez `Electronic`.
13. Sélectionnez **Enregistrer**.
14. Sélectionnez **Générer des paiements**.
15. Dans le champ **Mode de paiement**, saisissez `Electronic`.
16. Dans le champ **Nom de fichier**, saisissez `Payments`.
17. Dans le champ **Compte bancaire**, saisissez `GBSI OPER`.
18. Sélectionnez **OK**, puis à nouveau **OK**. Examinez la feuille de calcul créée, notamment les détails des lignes de paiement ainsi que les totaux pour chaque code devise utilisé dans ce message de paiement.  

