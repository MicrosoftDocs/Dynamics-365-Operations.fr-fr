---
title: "Paramétrage du processus d&quot;importation du rapprochement bancaire avancé"
description: "La fonctionnalité de rapprochement bancaire avancée vous permet d&quot;importer des relevés bancaires électroniques et de les rapprocher automatiquement avec des transactions bancaires dans Microsoft Dynamics 365 for Operations. Cet article explique comment configurer la fonctionnalité d’importation de vos relevés bancaires."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 106853
ms.assetid: 45dae275-ea45-4c7e-b38f-89297c7b5352
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eab840b2974f4e9e8cf542c146482ba8e4239079
ms.openlocfilehash: acf7bacf6e95725024ff0a542a059349593d01a0
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-the-advanced-bank-reconciliation-import-process"></a>Paramétrage du processus d'importation du rapprochement bancaire avancé

[!include[banner](../includes/banner.md)]


La fonctionnalité de rapprochement bancaire avancée vous permet d'importer des relevés bancaires électroniques et de les rapprocher automatiquement avec des transactions bancaires dans Microsoft Dynamics 365 for Operations. Cet article explique comment configurer la fonctionnalité d’importation de vos relevés bancaires. 

Le paramétrage de l’importation de relevé bancaire varie selon le format de votre relevé bancaire électronique. Microsoft Dynamics 365 for Operations prend en charge trois formats de relevés bancaires prêts à l'emploi : ISO20022, MT940 et BAI2.

## <a name="sample-files"></a>Exemples de fichiers
Pour les trois formats, vous devez disposer de fichiers qui traduisent le relevé bancaire électronique de son format d’origine vers un format que Dynamics 365 for Operations peut utiliser. Vous pouvez trouver les fichiers de ressources requis sous le nœud **Ressources** dans l’Explorateur d’application dans Microsoft Visual Studio. Après avoir trouvé les fichiers, copiez-les à un emplacement unique, afin que de pouvoir les télécharger plus facilement au cours du processus d’installation.

| Nom de la ressource                                           | Nom de fichier                            |
|---------------------------------------------------------|--------------------------------------|
| BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt              | BAI2CSV-to-BAI2XML.xslt              |
| BankStmtImport\_BAI2XML\_to\_Reconciliation\_xslt       | BAI2XML-to-Reconciliation.xslt       |
| BankStmtImport\_BankReconciliation\_to\_Composite\_xslt | BankReconciliation-to-Composite.xslt |
| BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt   | ISO20022XML-to-Reconciliation.xslt   |
| BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt            | MT940TXT-to-MT940XML.xslt            |
| BankStmtImport\_MT940XML\_to\_Reconciliation\_xslt      | MT940XML-to-Reconciliation.xslt      |
| BankStmtImport\_SampleBankCompositeEntity\_xml          | SampleBankCompositeEntity.xml        |

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>Exemples de formats de relevé bancaire et de mises en page techniques
Voici des exemples de définitions techniques de mise en page du fichier d'importation avancé de rapprochement bancaire, ainsi que trois exemples de fichiers de relevé bancaire : https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts  

| Définition de mise en page technique                             | Fichier d'exemple de relevé bancaire          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | MT940StatementExample                |
| DynamicsAXISO20022Layout                                | ISO20022StatementExample             |
| DynamicsAXBAI2Layout                                    | BAI2StatementExample                 |

 

## <a name="set-up-the-import-of-iso20022-bank-statements"></a>Paramétrer l'importation des relevés bancaires ISO20022
Tout d’abord, vous devez définir le groupe de traitement du format du relevé bancaire pour les relevés bancaires ISO20022 à l’aide de l’infrastructure d’entité de données.

1.  Accédez à **Espaces de travail** &gt; **Gestion des données**.
2.  Cliquez sur **Importer**.
3.  Entrez un nom pour le format, comme **ISO20022**.
4.  Définissez le champ **Format des données sources** sur **XML-Element**.
5.  Définissez champ **Nom de l'entité** sur **Relevés bancaires**.
6.  Pour télécharger les fichiers d’importation, cliquez sur **Télécharger**, puis accédez au fichier **SampleBankCompositeEntity.xml** que vous avez enregistré précédemment.
7.  Une fois l’entité de relevés bancaires téléchargée et la mise en correspondance terminée, cliquez sur l'action **Afficher le mappage** pour l’entité.
8.  L’entité de relevés bancaires est une entité composite qui se compose de quatre entités distinctes. Dans la liste, sélectionnez **BankStatementDocumentEntity**, puis cliquez sur l'action **Afficher le mappage**.
9.  Sous l'onglet **Transformations**, cliquez sur **Nouveau**.
10. Pour le numéro de souche 1, cliquez sur **Télécharger le fichier** et sélectionnez le fichier** ISO20022XML-to-Reconciliation.xslt** que vous avez enregistré précédemment. **Remarque :** les fichiers de transformation Dynamics 365 for Operations sont générés pour le format standard. Dans la mesure où les banques ont souvent des formats différents, vous devrez peut-être mettre à jour le fichier de transformation pour le mettre en correspondance avec votre format de relevé bancaire. <!-- For details about the expected format for ISO20022, see [Dynamics AX ISO20022 Layout](./media/dynamicsaxiso20022layout1.xlsx).-->
11. Cliquez sur **Nouveau**.
12. Pour le numéro de souche 2, cliquez sur **Télécharger le fichier** et sélectionnez le fichier **BankReconciliation-to-Composite.xslt** que vous avez enregistré précédemment.
13. Cliquez sur **Appliquer les transformations**.

Une fois que le groupe de traitement du format est configuré, l’étape suivante consiste à définir les règles de format de relevé bancaire pour les relevés bancaires ISO20022.

1.  Accédez à **Gestion de la trésorerie et de la banque** &gt; **Paramétrage** &gt; **Configuration du rapprochement bancaire avancé** &gt; **Format de relevé bancaire**.
2.  Cliquez sur **Nouveau**.
3.  Spécifiez un format de relevé, tel que **ISO20022**.
4.  Entrez un nom pour le format.
5.  Définissez le champ **Groupe de traitement** sur le groupe que vous avez défini précédemment, tel que **ISO20022**.
6.  Activez la case à cocher **Fichier XML**.

La dernière étape consiste à activer le rapprochement bancaire avancé et à définir le format de relevé sur le compte bancaire.

1.  Accédez à **Gestion de la trésorerie et de la banque** &gt; **Comptes bancaires**.
2.  Sélectionnez le compte bancaire et ouvrez-le pour afficher les détails.
3.  Sur l'onglet **Rapprochement**, définissez l'option **Rapprochement bancaire avancé **sur **Oui**.
4.  Définissez le champ **Format de relevé **sur le format que vous avez créé précédemment, tel que **ISO20022**.

## <a name="set-up-the-import-of-mt940-bank-statements"></a>Paramétrer l'importation des relevés bancaires MT940
Tout d’abord, vous devez définir le groupe de traitement du format du relevé bancaire pour les relevés bancaires MT940 à l’aide de l’infrastructure d’entité de données.

1.  Accédez à **Espaces de travail** &gt; **Gestion des données**.
2.  Cliquez sur **Importer**.
3.  Entrez un nom pour le format, comme **MT940**.
4.  Définissez le champ **Format des données sources** sur **XML-Element**.
5.  Définissez champ **Nom de l'entité** sur **Relevés bancaires**.
6.  Pour télécharger les fichiers d’importation, cliquez sur **Télécharger**, puis accédez au fichier **SampleBankCompositeEntity.xml** que vous avez enregistré précédemment.
7.  Une fois l’entité de relevés bancaires téléchargée et la mise en correspondance terminée, cliquez sur l'action **Afficher le mappage** pour l’entité.
8.  L’entité de relevés bancaires est une entité composite qui se compose de quatre entités distinctes. Dans la liste, sélectionnez **BankStatementDocumentEntity**, puis cliquez sur l'action **Afficher le mappage**.
9.  Sous l'onglet **Transformations**, cliquez sur **Nouveau**.
10. Pour le numéro de souche 1, cliquez sur **Télécharger le fichier** et sélectionnez le fichier **MT940TXT-to-MT940XML.xslt** que vous avez enregistré précédemment.
11. Cliquez sur **Nouveau**.
12. Pour le numéro de souche 2, cliquez sur **Télécharger le fichier** et sélectionnez le fichier **MT940XML-to-Reconciliation.xslt** que vous avez enregistré précédemment. **Remarque :** les fichiers de transformation Dynamics 365 for Operations sont générés pour le format standard. Dans la mesure où les banques ont souvent des formats différents, vous devrez peut-être mettre à jour le fichier de transformation pour le mettre en correspondance avec votre format de relevé bancaire. <!--- For details about the expected format for MT940, see [Dynamics AX MT940 Layout](./media/dynamicsaxmt940layout1.xlsx)-->
13. Cliquez sur **Nouveau**.
14. Pour le numéro de souche 3, cliquez sur **Télécharger le fichier** et sélectionnez le fichier **BankReconciliation-to-Composite.xslt** que vous avez enregistré précédemment.
15. Cliquez sur **Appliquer les transformations**.

Une fois que le groupe de traitement du format est configuré, l’étape suivante consiste à définir les règles de format de relevé bancaire pour les relevés bancaires MT940.

1.  Accédez à **Gestion de la trésorerie et de la banque** &gt; **Paramétrage** &gt; **Configuration du rapprochement bancaire avancé** &gt; **Format de relevé bancaire**.
2.  Cliquez sur **Nouveau**.
3.  Spécifiez un format de relevé, tel que **MT940**.
4.  Entrez un nom pour le format.
5.  Définissez le champ **Groupe de traitement** sur le groupe que vous avez défini précédemment, tel que **MT940**.
6.  Définissez le champ **Type de fichier** sur **txt**.

La dernière étape consiste à activer le rapprochement bancaire avancé et à définir le format de relevé sur le compte bancaire.

1.  Accédez à **Gestion de la trésorerie et de la banque** &gt; **Comptes bancaires**.
2.  Sélectionnez le compte bancaire et ouvrez-le pour afficher les détails.
3.  Sur l'onglet **Rapprochement**, définissez l'option **Rapprochement bancaire avancé** sur **Oui**.
4.  Lorsque vous êtes invité à confirmer votre sélection et à activer le rapprochement bancaire avancé, cliquez sur **OK**.
5.  Définissez le champ **Format de relevé** sur le format que vous avez créé précédemment, tel que **MT940**.

## <a name="set-up-the-import-of-bai2-bank-statements"></a>Paramétrer l'importation des relevés bancaires BAI2
Tout d’abord, vous devez définir le groupe de traitement du format du relevé bancaire pour les relevés bancaires BAI2 à l’aide de l’infrastructure d’entité de données.

1.  Accédez à **Espaces de travail** &gt; **Gestion des données**.
2.  Cliquez sur **Importer**.
3.  Entrez un nom pour le format, comme **BAI2**.
4.  Définissez le champ **Format des données sources** sur **XML-Element**.
5.  Définissez champ **Nom de l'entité** sur **Relevés bancaires**.
6.  Pour télécharger les fichiers d’importation, cliquez sur **Télécharger**, puis accédez au fichier **SampleBankCompositeEntity.xml** que vous avez enregistré précédemment.
7.  Une fois l’entité de relevés bancaires téléchargée et la mise en correspondance terminée, cliquez sur l'action **Afficher le mappage** pour l’entité.
8.  L’entité de relevés bancaires est une entité composite qui se compose de quatre entités distinctes. Dans la liste, sélectionnez **BankStatementDocumentEntity**, puis cliquez sur l'action **Afficher le mappage**.
9.  Sous l'onglet **Transformations**, cliquez sur **Nouveau**.
10. Pour le numéro de souche 1, cliquez sur **Télécharger le fichier** et sélectionnez le fichier **BAI2CSV-to-BAI2XML.xslt** que vous avez enregistré précédemment.
11. Cliquez sur **Nouveau**.
12. Pour le numéro de souche 2, cliquez sur **Télécharger le fichier** et sélectionnez le fichier **BAI2XML-to-Reconciliation.xslt** que vous avez enregistré précédemment. **Remarque :** les fichiers de transformation Dynamics 365 for Operations sont générés pour le format standard. Dans la mesure où les banques ont souvent des formats différents, vous devrez peut-être mettre à jour le fichier de transformation pour le mettre en correspondance avec votre format de relevé bancaire. <!--- For details about the expected format for BAI2, see [Dynamics AX BAI2 Layout](./media/dynamicsaxbai2layout1.xlsx).-->
13. Cliquez sur **Nouveau**.
14. Pour le numéro de souche 3, cliquez sur **Télécharger le fichier** et sélectionnez le fichier **BankReconciliation-to-Composite.xslt** que vous avez enregistré précédemment.
15. Cliquez sur **Appliquer les transformations**.

Une fois que le groupe de traitement du format est configuré, l’étape suivante consiste à définir les règles de format de relevé bancaire pour les relevés bancaires BAI2.

1.  Accédez à **Gestion de la trésorerie et de la banque** &gt; **Paramétrage** &gt; **Configuration du rapprochement bancaire avancé** &gt; **Format de relevé bancaire**.
2.  Cliquez sur **Nouveau**.
3.  Spécifiez un format de relevé, tel que **BAI2**.
4.  Entrez un nom pour le format.
5.  Définissez le champ **Groupe de traitement** sur le groupe que vous avez défini précédemment, tel que **BAI2**.
6.  Définissez le champ **Type de fichier** sur **txt**.

La dernière étape consiste à activer le rapprochement bancaire avancé et à définir le format de relevé sur le compte bancaire.

1.  Accédez à **Gestion de la trésorerie et de la banque** &gt; **Comptes bancaires**.
2.  Sélectionnez le compte bancaire et ouvrez-le pour afficher les détails.
3.  Sur l'onglet **Rapprochement**, définissez l'option **Rapprochement bancaire avancé** sur **Oui**.
4.  Lorsque vous êtes invité à confirmer votre sélection et à activer le rapprochement bancaire avancé, cliquez sur **OK**.
5.  Définissez le champ **Format de relevé** sur le format que vous avez créé précédemment, tel que **BAI2**.

## <a name="test-the-bank-statement-import"></a>Tester l'importation des relevés bancaires
La dernière étape consiste à tester l'importation de votre relevé bancaire.

1.  Accédez à **Gestion de la trésorerie et de la banque** &gt; **Comptes bancaires**.
2.  Sélectionnez le compte bancaire pour lequel la fonctionnalité de rapprochement bancaire avancé est activée.
3.  Sur l'onglet **Rapprocher**, cliquez sur **Relevés bancaires**.
4.  Sur la page **Relevés bancaires**, cliquez sur **Importer le relevé**.
5.  Définissez le champ **Compte bancaire** sur le compte bancaire sélectionné. Le champ **Format du relevé** est défini automatiquement, en fonction du paramètre du compte bancaire.
6.  Cliquez sur **Parcourir**, puis sélectionnez votre fichier de relevé bancaire électronique.
7.  Cliquez sur **Charger**.
8.  Cliquez sur **OK**.

Si l’importation réussit, vous recevrez un message indiquant que votre relevé a été importé. Si l’importation n’était pas réussie, dans l'espace de travail **Gestion des données**, dans la section **Historique des travaux**, recherchez la tâche. Cliquez sur **Détails de l’exécution** de la tâche pour ouvrir la page **Résumé d’exécution**, puis cliquez sur **Afficher le journal d’exécution** pour afficher les erreurs d’importation.




