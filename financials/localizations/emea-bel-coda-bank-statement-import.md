---
title: "Relevé bancaire CODA"
description: "Cette rubrique fournit des informations sur le CODA, qui est un format d&quot;état utilisé dans le système bancaire électronique belge."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BankAccountTable, BankCodaAccountStatement, BankCodaAccountStatementLines, BankCodaParameters, BankCodaTrans, BankCodaTransCategory, BankCodaTransDefTable, BankCodaTransFamily
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 262534
ms.assetid: 38a1f540-1488-4b63-b850-04e270622296
ms.search.region: Belgium
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 187a17ac4c1fb7b30447f7586b57497d7460c694
ms.lasthandoff: 03/31/2017


---

# <a name="coda-bank-statement"></a>Relevé bancaire CODA

Cette rubrique fournit des informations sur le CODA, qui est un format d'état utilisé dans le système bancaire électronique belge. 

Pour les importations belges de relevé bancaire, vous allez utiliser le format de fichier CODA. Cette fonction permet de contrôler les soldes d'ouverture et de fin de compte bancaire, et rapproche des règles importées de rapprochement des transactions basée.

## <a name="import-transactions-from-a-bank-statement"></a>Transactions d'importation d'un relevé bancaire
Pour importer un fichier de relevé bancaire pour un compte bancaire, procédez comme suit. ** Note ** : Avant d'importer un fichier de relevé bancaire, vous devez avoir déjà terminé ce qui suit :

-   Importez les configurations CODA des Lifecycle Services (LCS). Pour plus d'informations, voir [des configurations électroniques de génération d'états de téléchargement de Lifecycle Services] (/dynamics365/operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs).
-   Sélectionnez la configuration importée CODA sur ** les paramètres CODA ** la page.

1.  Allez ** des comptes bancaires ** à la page.
2.  Cliquez sur ** rapprochez ** &gt; ** CODA **.
3.  Cliquez sur ** CODA ** &gt; ** importation à partir de fichier **, puis sélectionnez le chemin d'accès au fichier de relevé bancaire.

Après avoir importé des transactions, vous pouvez effectuer les actions suivantes sous ** relevé bancaire ** la page.

-   Vérifiez les soldes d'ouverture et de fin.
-   Permet d'afficher les transactions importées comme état du relevé bancaire que vous pouvez imprimer.
-   Permet d'afficher les transactions importées ayant des lignes supplémentaires, telles que les lignes dont le type est « aucune ». Cliquez sur ** détails &gt; CODA **.

## <a name="process-imported-bank-statement-transactions"></a>Transactions de relevé bancaire importées par processus
Procédez comme suit pour traiter les transactions de relevé bancaire.

1.  Traiter les lignes détail (** CODA ** &gt; ** lignes détaillées de processus **). Démarrez correspondre automatique sur ** des définitions CODA **. Ces règles détermine le compte général, client, ou le compte fournisseur doivent être utilisé pour cette transaction. La comparaison est basé sur le code du groupe de transactions, le code catégorie du code transaction, et de transaction sont spécifiés dans le fichier CODA pour chaque transaction.
2.  Les transactions avec un client et un type de compte fournisseur peuvent être mises en correspondance avec les factures. Le cas échéant, les transactions importées peuvent être modifiées manuellement à tout moment après qu'un traitement, avant de transférer dans la comptabilité.
3.  S'il existe des transactions comportant des erreurs (en général, s'il n'existe aucune règle paramétrée), ces derniers peuvent être mentionnés le compte général particulier, spécifié sous ** les paramètres CODA ** la page (** CODA ** &gt; ** erreurs précises **).
4.  Une fois toutes les transactions du relevé bancaire réglées, elles sont prêtes à être transférées au journal de comptabilité (** CODA ** &gt;** transfert vers la comptabilité **). Les paramètres de journal doivent être spécifiés pour le compte bancaire. Les journaux peuvent être ouverts sur ** des comptes bancaires ** la page pour l'enregistrement sélectionné en cliquant sur ** paramétrage ** &gt; ** le journal CODA **.

Après traitement des transactions de relevé bancaire sont terminés, un journal comptable est créé et prêt pour la validation.


