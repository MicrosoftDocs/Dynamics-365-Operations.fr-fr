---
title: ER Concevoir une configuration pour générer des états au format OPENXML (novembre 2016)
description: Les étapes suivantes expliquent comment un utilisateur dont le rôle est Administrateur système ou Développeur d'états électroniques peut créer une configuration de format pour la génération d'états électronique (ER) qui contient un modèle pour générer des documents électroniques au format OPENXML.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: 3e6b6b16f202af051ccff02051eb438ea49ff6da
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1551552"
---
# <a name="er-design-a-configuration-for-generating-reports-in-openxml-format-november-2016"></a>ER Concevoir une configuration pour générer des états au format OPENXML (novembre 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Les étapes suivantes expliquent comment un utilisateur dont le rôle est Administrateur système ou Développeur d'états électroniques peut créer une configuration de format pour la génération d'états électronique (ER) qui contient un modèle pour générer des documents électroniques au format OPENXML. Cette configuration sera utilisée pour traiter les paiements fournisseur.



Dans cet exemple, vous allez créer une configuration pour la société témoin, Litware, Inc. Ces étapes peuvent être effectuées dans la société GBSI.



Pour effectuer ces étapes, vous devez commencer par effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ». Vous devez également avoir un fichier Excel qui sera importé lorsque vous créez le modèle. Ce fichier est accessible depuis le [Modèle d'état de paiement](https://go.microsoft.com/fwlink/?linkid=862266).


## <a name="upload-the-payments-data-model-configuration"></a>Téléchargez la configuration du modèle de données des paiements
1. Accédez à Administration d'organisation > Espaces de travail > États électroniques.
2. Dans la liste, marquez la ligne sélectionnée.
    * Sélectionnez le fournisseur de configuration pour la société fictive Litware, Inc. Si vous ne voyez pas ce fournisseur de configuration, vous devez d'abord effectuer les étapes de la procédure « Créer un fournisseur de configuration et le marquer comme actif ».  
3. Cliquez sur Activer.
4. Cliquez sur Référentiels.
    * Sélectionnez un référentiel pour le type de ressources opérationnelles, si disponible. S'il n'est pas disponible, ignorez les étapes suivantes sur la création d'un référentiel.  
5. Cliquez sur Ajouter pour ouvrir la boîte de dialogue.
6. Dans le champ Type du référentiel de configuration, entrez « Ressources opérationnelles ».
7. Cliquez sur Créer un référentiel.
8. Cliquez sur OK.
9. Cliquez sur Ouvrir.
10. Dans l'arborescence, sélectionnez « Modèle de paiement ».
11. Cliquez sur Importer.
    * Importez ce modèle de données. Il est utilisé comme source de données dans une nouvelle configuration de format. Ignorez cette étape si cette configuration a déjà été importée.  
12. Cliquez sur Oui.
13. Fermez la page.
14. Fermez la page.

## <a name="create-a-new-format-configuration"></a>Créer une configuration de format
1. Cliquez sur Configurations des états.
2. Dans l'arborescence, sélectionnez « Modèle de paiement ».
3. Cliquez sur Créer la configuration pour ouvrir la boîte de dialogue.
4. Dans le champ Nouveau, entrez « Format basé sur le PaymentModel du modèle du paiement ».
    * Créez un format basé sur le modèle de données PaymentModel.  
5. Tapez Exemple d'état sur les feuilles de calcul dans le champ Nom.
    * Exemple d'état sur les feuilles de calcul  
6. Entrez « Exemple d'état sur les feuilles de calcul pour les paiements fournisseurs » dans le champ Description.
    * Exemple d'état sur les feuilles de calcul pour les paiements fournisseurs.  
7. Dans le champ Définition du modèle de données, entrez ou sélectionnez une valeur.
    * Sélectionnez la définition « CustomerCreditTransferInitiation ».  
8. Cliquez sur Créer une configuration.

## <a name="design-a-new-document-in-openxml-worksheet-format"></a>Créez un document dans le format de la feuille de calcul OPENXML
1. Sélectionnez Modèle de paiement\Exemple d'état sur les feuilles de calcul dans l'arborescence.
2. Cliquez sur Concepteur.
3. Cliquez sur Importer dans le volet Actions.
4. Cliquez sur Importer depuis Excel.
5. Cliquez sur Documents joints.
    * Joignez le document Excel existant comme modèle.  
6. Cliquez sur Nouveau.
7. Cliquez sur Fichier.
    * Pointez vers le fichier Excel existant.  
8. Fermez la page.
9. Dans le champ Modèle, entrez ou sélectionnez une valeur.
    * Sélectionnez le fichier Excel à utiliser comme modèle.  
10. Cliquez sur OK.
    * Notez que les composants de format ER ont été créés dans le format de conception basé sur la structure du document MS Excel de référence (plages nommées).  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a>Créer une nouvelle source de données pour calculer les totaux par codes devise
1. Cliquez sur l'onglet Mise en relation.
2. Cliquez sur Ajouter racine pour ouvrir la boîte de dialogue.
3. Dans l'arborescence, sélectionnez Fonctions\Grouper par.
4. Entrez PaymentByCurrency dans le champ Nom.
    * PaymentByCurrency  
5. Cliquez sur Modifier le groupe par.
6. Dans l'arborescence , développez « model ».
7. Dans l'arborescence, sélectionnez model\Payments.
8. Cliquez sur Ajouter le champ à.
9. Cliquez sur Éléments à grouper.
10. Dans l'arborescence, développez model\Payments.
11. Dans l'arborescence, sélectionnez modèle\Paiements\Devise.
12. Cliquez sur Ajouter le champ à.
13. Cliquez sur Champs groupés.
14. Dans l'arborescence, sélectionnez modèle\Paiements\Montant ordonné.
15. Cliquez sur Ajouter le champ à.
16. Cliquez sur Champs d'agrégation.
17. Sélectionnez une option dans le champ Méthode.
    * Sélectionnez la fonction d'agrégation SOMME.  
18. Dans le champ Nom, tapez TotalInstructuredAmount.
    * TotalInstructuredAmount  
19. Cliquez sur Enregistrer.
20. Fermez la page.
21. Cliquez sur OK.

## <a name="map-format-components-to-data-sources"></a>Mettre en correspondance des composants de format vers des sources de données
1. Dans l'arborescence , développez « model ».
2. Dans l'arborescence, développez model\Payments.
3. Dans l'arborescence, développez modèle\Paiements\Partie qui prend l'initiative.
4. Dans l'arborescence, sélectionnez modèle\Paiements\Partie qui prend l'initiative\Nom.
5. Dans l'arborescence, développez ou réduisez « Excel\ReportHeader ».
6. Dans l'arborescence, sélectionnez « Excel\ReportHeader\CompanyName ».
7. Cliquez sur Lier.
8. Dans l'arborescence , développez « modèle\Paiements\Créditeur ».
9. Dans l'arborescence , développez modèle\Paiements\Créancier\Identification.
10. Dans l'arborescence, sélectionnez modèle\Paiements\Créancier\Identification\Source ID(SourceID).
11. Dans l'arborescence, développez « Excel\PaymLines ».
12. Dans l'arborescence, sélectionnez « Excel\PaymLines\VendAccountName ».
13. Cliquez sur Lier.
14. Dans l'arborescence, sélectionnez « modèle\Paiements\Créditeur\Nom ».
15. Dans l'arborescence, sélectionnez « Excel\PaymLines\VendName ».
16. Cliquez sur Lier.
17. Dans l'arborescence , développez modèle\Paiements\Créancier.
18. Dans l'arborescence, sélectionnez modèle\Paiements\Créancier\Nom.
19. Dans l'arborescence, sélectionnez « Excel\PaymLines\Banque ».
20. Cliquez sur Lier.
21. Dans l'arborescence, sélectionnez modèle\Paiements\Créancier\Numéro d'acheminement.
22. Dans l'arborescence, sélectionnez « Excel\PaymLines\RoutingNumber ».
23. Cliquez sur Lier.
24. Dans l'arborescence , développez « model\Payments\Creditor Account(CreditorAccount) ».
25. Dans l'arborescence , développez « model\Payments\Creditor Account(CreditorAccount)\Identification ».
26. Dans l'arborescence, sélectionnez modèle\Paiements\Créancier\Identification\Numéro.
27. Dans l'arborescence, sélectionnez « Excel\PaymLines\AccountNumber ».
28. Cliquez sur Lier.
29. Dans l'arborescence, sélectionnez modèle\Paiements\Montant ordonné.
30. Dans l'arborescence, sélectionnez « Excel\PaymLines\Débit ».
31. Cliquez sur Lier.
32. Dans l'arborescence , développez « modèle\Paiements\Créditeur ».
33. Dans l'arborescence , développez « model\Payments\Creditor Account(CreditorAccount) ».
34. Dans l'arborescence , développez modèle\Paiements\Créancier.
35. Dans l'arborescence, sélectionnez modèle\Paiements\Devise.
36. Dans l'arborescence, sélectionnez « Excel\PaymLines\Devise ».
37. Cliquez sur Lier.
38. Dans l'arborescence, développez PaymentByCurrency.
39. Dans l'arborescence, développez PaymentByCurrency\groupé.
40. Dans l'arborescence, sélectionnez PaymentByCurrency\groupé\Devise.
41. Dans l'arborescence, développez « Excel\SummaryLines ».
42. Dans l'arborescence, sélectionnez « Excel\SummaryLines\SummaryCurrency ».
43. Cliquez sur Lier.
44. Dans l'arborescence, développez PaymentByCurrency\agrégé.
45. Dans l'arborescence, sélectionnez PaymentByCurrency\agrégé\TotalInstructuredAmount.
46. Dans l'arborescence, sélectionnez « Excel\SummaryLines\SummaryAmount ».
47. Cliquez sur Lier.
48. Sélectionnez PaymentByCurrency.
49. Dans l'arborescence, sélectionnez « Excel\SummaryLines ».
50. Cliquez sur Lier.
51. Dans l'arborescence, sélectionnez model\Payments.
52. Dans l'arborescence, sélectionnez « Excel\PaymLines ».
53. Cliquez sur Lier.
54. Cliquez sur Enregistrer.
55. Fermez la page.

## <a name="use-the-created-configuration-for-payments-processing"></a>Utiliser la configuration créée pour le traitement des paiements
1. Cliquez sur Modifier le statut.
2. Cliquez sur Terminé.
3. Cliquez sur OK.
4. Fermez la page.
5. Fermez la page.
6. Accédez à Comptabilité fournisseur > Paramétrage des paiements > Modes de paiement.
7. Utilisez le filtre rapide pour filtrer selon le champ Mode de paiement avec une valeur de « Électronique ».
    * électronique  
8. Cliquez sur Modifier.
9. Développez la section Formats de fichier.
10. Sélectionnez Oui dans le champ États électroniques génériques.
11. Entrez ou sélectionnez une valeur dans le champ Exporter la configuration du format.
    * Sélectionnez la configuration « Exemple d'état sur les feuilles de calcul ».  
12. Cliquez sur Enregistrer.
13. Fermez la page.

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a>Utiliser la configuration créée pour tester le traitement de journaux des paiements
1. Accédez à Comptabilité fournisseur > Paiements > Journal des paiements.
2. Cliquez sur Nouveau.
    * Créez un journal des paiements.  
3. Dans le champ Nom, tapez « VendPay ».
    * VendPay  
4. Cliquez sur Lignes.
5. Dans le champ Compte, spécifiez les valeurs GB_SI_000001.
    * GB_SI_000001  
6. Définissez Débit sur 1000.
7. Cliquez sur Nouveau.
8. Dans le champ Compte, spécifiez les valeurs GB_SI_000005.
    * GB_SI_000005  
9. Définissez Débit sur 2000.
10. Dans le champ Devise, tapez EUR.
    * EUR  
11. Spécifiez les valeurs GBSI OPER dans le champ Compte de contrepartie.
    * GBSI OPER  
12. Tapez Électronique dans le champ Mode de paiement.
    * électronique  
13. Cliquez sur Enregistrer.
14. Cliquez sur Générer les paiements.
15. Tapez Électronique dans le champ Mode de paiement.
    * électronique  
16. Dans le champ Nom de fichier, tapez « Paiements ».
    * Par exemple, tapez Paiements.  
17. Tapez GBSI OPER dans le champ Compte bancaire.
    * GBSI OPER  
18. Cliquez sur OK.
19. Cliquez sur OK.
    * Examinez la feuille de calcul créée, notamment les détails des lignes de paiement ainsi que les totaux pour chaque code devise utilisé dans ce message de paiement.  

