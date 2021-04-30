---
title: Relevé bancaire CODA
description: Cette rubrique contient des informations sur CODA, qui est un format d’état utilisé par le système d’opérations bancaires électroniques belge.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankAccountTable, BankCodaAccountStatement, BankCodaAccountStatementLines, BankCodaParameters, BankCodaTrans, BankCodaTransCategory, BankCodaTransDefTable, BankCodaTransFamily
audience: Application User
ms.reviewer: kfend
ms.custom: 262534
ms.search.region: Belgium
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 37076c59a326b6eddff5318271553fa82fb52d12
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5894863"
---
# <a name="coda-bank-statement"></a>Relevé bancaire CODA

[!include [banner](../includes/banner.md)]

Cette rubrique contient des informations sur CODA, qui est un format d’état utilisé par le système d’opérations bancaires électroniques belge. 

Pour les importations de relevés bancaires belges, vous utiliserez le format de fichier CODA. Cette fonctionnalité permet de vérifier les soldes d’ouverture et de clôture d’un compte bancaire de société, et de rapprocher des transactions importées basées sur des règles de rapprochement.

## <a name="import-transactions-from-a-bank-statement"></a>Importer des transactions à partir d’un relevé bancaire
Pour importer un fichier de relevé bancaire pour un compte bancaire, procédez comme suit. **Remarque** : avant d’importer un fichier de relevé bancaire, vous devez avoir déjà effectué les opérations suivantes :

-   Importer les configurations CODA à partir de Lifecycle Services (LCS). Pour plus d’informations, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)
-   Sélectionner la configuration CODA importée dans la page **Paramètres CODA**.

1.  Accédez à la page **Comptes bancaires**.
2.  Cliquez sur **Rapprocher** &gt; **CODA**.
3.  Cliquez sur **CODA** &gt; **Importer depuis le fichier**, puis sélectionnez le chemin d’accès au fichier de relevé bancaire.

Après avoir importé les transactions, vous pouvez effectuer les actions suivantes dans la page **Relevé bancaire**.

-   Vérifier les soldes d’ouverture et de clôture.
-   Afficher les transactions importées en tant qu’état de relevé bancaire que vous pouvez imprimer.
-   Afficher les transactions importées contenant des lignes supplémentaires, telles que les lignes dont le type de compte est « Aucun ». Cliquez sur **CODA &gt; Détails**.

## <a name="process-imported-bank-statement-transactions"></a>Traiter les transactions de relevé bancaire importées
Effectuez les étapes suivantes pour traiter les transactions de relevé bancaire.

1. Traitez les lignes de détail (**CODA** &gt; **Traiter les lignes de détails**). Démarrez la mise en correspondance automatique en fonction des **Définitions CODA**. Ces règles déterminent le compte général, client ou fournisseur qui doit être utilisé pour cette transaction. La comparaison est basée sur le code du groupe de transactions, le code de transaction et le code de catégorie de transaction spécifiés dans le fichier CODA pour chaque transaction.
2. Les transactions avec un type de compte client et fournisseur peuvent être mises en correspondance avec les factures. Si nécessaire, les transactions importées peuvent être modifiées manuellement à tout moment après le traitement, avant de les transférer vers la comptabilité.
3. Si des transactions comportent des erreurs (en général, si aucune règle n’est paramétrée), celles-ci peuvent être mentionnées dans le compte général spécial, spécifié sur la page <strong>Paramètres CODA **(</strong>CODA** &gt; <strong>Effacer les erreurs</strong>).
4. Une fois que toutes les transactions du relevé bancaire sont réglées, elles sont prêtes à être transférées vers le journal de comptabilité (<strong>CODA</strong> &gt;<strong>Transfert vers la comptabilité</strong>). Les paramètres du journal doivent être spécifiés pour le compte bancaire. Les journaux peuvent être ouverts sur la page <strong>Comptes bancaires** pour l’enregistrement sélectionné en cliquant sur **Paramétrage</strong> &gt; <strong>Journal CODA</strong>.

Une fois que le traitement des transactions de relevé bancaire est terminé, un journal de comptabilité est créé et prêt à être validé.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]