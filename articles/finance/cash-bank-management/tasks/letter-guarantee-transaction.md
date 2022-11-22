---
title: Transaction de lettre de garantie
description: Cette procédure décrit le processus associé à une lettre de garantie.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Reasons, SalesTableListPage, SalesCreateOrder, SalesTable, BankLGRequestForm, BankLGRequestFormRequest, BankLGGuarantee, BankLGFormSubmitToBank, BankDocumentAgreementLineLookup, BankLGFormReceiveFromBank, LedgerJournalTable, LedgerJournalTransDaily, BankLGRequestFormGiveToBeneficiary, BankLGFormGiveToBeneficiary, BankLGRequestFormIncreaseValue, BankLGFormIncreaseValue, BankLGRequestFormLiquidate, BankLGFormLiquidate
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 30e21c11b067f6def127f3eab026d7255ab1ca29
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779932"
---
# <a name="letter-of-guarantee-transaction"></a>Transaction de lettre de garantie

[!include [banner](../../includes/banner.md)]

Cette procédure décrit le processus associé à une lettre de garantie.



Les tâches suivantes doivent être terminées avant d’effectuer cette procédure :

- Paramétrer les établissements et les profils de validation pour une lettre de garantie.

- Créer un accord d’établissement bancaire pour une lettre de garantie.



La société fictive USMF sert d’exemple dans cette procédure.


## <a name="create-sales-order-with-letter-of-guarantee"></a>Créer une commande client avec une lettre de garantie
1. Accédez à **Comptabilité client > Commandes > Toutes les commandes client**.
2. Cliquez sur **Nouveau**.
3. Entrez ou sélectionnez une valeur dans le champ **Compte client**.
4. Développez la section Général.
5. Entrez ou sélectionnez une valeur dans le champ **Site**.
6. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
7. Entrez ou sélectionnez une valeur dans le champ **Entrepôt**.
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
9. Dans le champ **Type de document bancaire**, sélectionnez **Lettre de garantie**.
10. Cliquez sur **OK**.
11. Entrez ou sélectionnez une valeur dans le champ **Numéro d’article**.
12. Entrez un nombre dans le champ **Prix unitaire**.
13. Développez la section Détails de ligne.
14. Cliquez sur l’onglet Livraison.
    * Remarque : Sélectionnez Vérification de la date de livraison = Aucun(e).  
15. Dans le champ **Date d’expédition demandée**, entrez une date.
16. Dans le champ **Date d’expédition confirmée**, entrez une date.

## <a name="process-letter-of-guarantee_request"></a>Traiter une demande de lettre de garantie
1. Dans le volet Actions, cliquez sur **Gérer**.
2. Cliquez sur **Lettre de garantie**.
3. Dans le volet Actions, cliquez sur **Lettre de garantie**.
4. Cliquer sur **Demande** pour ouvrir la boîte de dialogue.
5. Dans le champ **Type**, entrez ou sélectionnez une valeur.
6. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
7. Entrez un nombre dans le champ **Valeur**.
8. Entrez une date et une heure dans le champ **Date d’expiration**.
9. Cliquez sur **OK**.
10. Fermez la page.

## <a name="process-letter-of-guarantee_submit-to-bank"></a>Traiter la lettre de garantie_Remettre à la banque
1. Accédez à **Gestion de la trésorerie et de la banque > Lettres de garantie > Lettres de garantie**.
2. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
3. Cliquez sur **Remettre à la banque** pour ouvrir la boîte de dialogue.
4. Dans le champ **Compte en banque**, entrez ou sélectionnez une valeur.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Cliquez sur **OK**.

## <a name="process-letter-of-guarantee_receive-from-bank"></a>Traiter la lettre de garantie_Recevoir de la banque
1. Cliquez sur **Recevoir de la banque** pour ouvrir la boîte de dialogue.
2. Dans le champ **Numéro de banque**, tapez une valeur.
    * Vérifiez les valeurs dans les champs calculés **Marge** et **Dépense**.  
3. Cliquez sur **OK**.
4. Développez la section Actions.
    * Vérifiez l’enregistrement « Recevoir de la banque ».  
5. Cliquez pour suivre le lien dans le champ **Numéro de lot du journal**.
6. Cliquez sur **Lignes**.
    * Vérifiez la validation des écritures de journal.  
7. Fermez la page.

## <a name="process-letter-of-guarantee_give-to-beneficiary"></a>Traiter la lettre de garantie_Remettre au bénéficiaire
1. Accédez à **Comptabilité client > Commandes > Toutes les commandes client**.
2. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
3. Dans le volet Actions, cliquez sur **Gérer**.
4. Cliquez sur **Lettre de garantie**.
5. Dans le volet Actions, cliquez sur **Lettre de garantie**.
6. Cliquez sur **Remettre au bénéficiaire** pour ouvrir la boîte de dialogue.
7. Cliquez sur **OK**.
8. Accédez à **Gestion de la trésorerie et de la banque > Lettres de garantie > Lettres de garantie**.
9. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
10. Cliquez sur **Remettre au bénéficiaire** pour ouvrir la boîte de dialogue.
11. Cliquez sur **OK**.
12. Développez la section Actions.
    * Validez l’enregistrement « Remettre au bénéficiaire ».  

## <a name="process-letter-of-guarantee_increase-value"></a>Traiter la lettre de garantie_Augmenter la valeur
1. Accédez à **Comptabilité client > Commandes > Toutes les commandes client**.
2. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
3. Dans le volet Actions, cliquez sur **Gérer**.
4. Cliquez sur **Lettre de garantie**.
5. Dans le volet Actions, cliquez sur **Lettre de garantie**.
6. Cliquer sur **Augmenter la valeur** pour ouvrir la boîte de dialogue.
7. Dans le champ **Valeur à ajouter**, entrez un numéro.
8. Cliquez sur **OK**.
9. Accédez à **Gestion de la trésorerie et de la banque > Lettres de garantie > Lettres de garantie**.
10. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
11. Cliquer sur **Augmenter la valeur** pour ouvrir la boîte de dialogue.
12. Cliquez sur **OK**.
13. Développez la section Actions.
    * Vérifiez l’enregistrement « Augmenter la valeur ».  
14. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
15. Cliquez pour suivre le lien dans le champ **Numéro de lot du journal**.
16. Cliquez sur **Lignes**.
    * Vérifiez les écritures de journal validées.  

## <a name="process-letter-of-guarantee_liquidate"></a>Traiter la lettre de garantie_Liquider
1. Accédez à **Comptabilité client > Commandes > Toutes les commandes client**.
2. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
3. Dans le volet Actions, cliquez sur **Gérer**.
4. Cliquez sur **Lettre de garantie**.
5. Dans le volet Actions, cliquez sur **Lettre de garantie**.
6. Cliquer sur **Liquider** pour ouvrir la boîte de dialogue.
7. Cliquez sur **OK**.
8. Accédez à **Gestion de la trésorerie et de la banque > Lettres de garantie > Lettres de garantie**.
9. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
10. Cliquer sur **Liquider** pour ouvrir la boîte de dialogue.
11. Cliquez sur **OK**.
12. Développez la section Actions.
    * Vérifiez l’enregistrement « Liquider ».  
13. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
14. Cliquez pour suivre le lien dans le champ **Numéro de lot du journal**.
15. Cliquez sur **Lignes**.
    * Vérifiez les écritures de journal validées.  
16. Fermez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
