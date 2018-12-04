--- 
title: "Importer une lettre de crédit"
description: "Cette procédure décrit le processus d'importation d'une lettre de crédit."
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendTable, VendBankAccounts, PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, BankLCImport,  PurchEditLines, VendEditInvoice, SrsReportViewerForm, LedgerJournalTable, LedgerJournalTransVendPaym, VendOpenTrans, SysQueryForm, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: c1768494182a79d7a33044498c1e768e61d937d1
ms.contentlocale: fr-fr
ms.lasthandoff: 09/14/2018

---
# <a name="import-letter-of-credit"></a>Importer une lettre de crédit

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit le processus d'importation d'une lettre de crédit. Vous devez configurer les éléments suivants avant de terminer cette procédure : les établissements bancaires, les profils de validation, un accord d'établissement bancaire et les coordonnées bancaires du fournisseur.

La société fictive USMF sert d'exemple dans cette procédure.


## <a name="create-a-purchase-order-with-letter-of-credit"></a>Créer une commande fournisseur avec une lettre de crédit
1. Accédez à Comptabilité fournisseur > Commandes fournisseur > Toutes les commandes fournisseur.
2. Cliquez sur Nouveau.
3. Dans le champ Compte fournisseur, saisissez ou sélectionnez une valeur.
4. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Développez la section Général.
7. Saisissez ou sélectionnez une valeur dans le champ Site.
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
9. Dans le champ Entrepôt, saisissez ou sélectionnez une valeur.
10. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
11. Dans le champ Comptabilité, entrez une date.
12. Dans le champ Date de livraison, entrez une date.
    * Remarque : le champ « Type de document bancaire » doit être sélectionné et renseigné avec la valeur « Lettre de crédit ».  
13. Cliquez sur OK.
14. Entrez ou sélectionnez une valeur dans le champ Numéro d'article.
15. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
16. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
17. Développez la section Détails de ligne.
18. Cliquez sur l'onglet Livraison.
19. Dans le champ Date de livraison, entrez une date.
20. Dans le champ Date de livraison confirmée, entrez une date.
21. Entrez un nombre dans le champ Prix unitaire.
    * Définissez les détails de la lettre de crédit.  
22. Dans le volet Actions, cliquez sur Gérer.
23. Cliquez sur Lettre de crédit/relance d'importation.
24. Dans le champ Date de demande, entrez une date et une heure.
    * Vérifiez que le champ « Compte bancaire » contient le compte bancaire actif par défaut, qui est basé sur la date de demande.  
25. Dans le champ Numéro de document bancaire, tapez une valeur.
26. Dans le champ Date de réception, entrez une date et une heure.
27. Développez la section Document bancaire.
28. Entrez une date et une heure dans le champ Date d'expiration.
29. Développez la section Détails bancaires.
30. Dans le champ Banque conseillère, saisissez ou sélectionnez une valeur.
31. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
32. Cliquez sur Enregistrer.
33. Cliquez sur Extraire les expéditions de commandes fournisseur.
34. Fermez la page.
35. Cliquez sur Achats dans le volet Actions.
36. Cliquez sur Confirmer.
37. Dans le volet Actions, cliquez sur Gérer.
38. Cliquez sur Lettre de crédit/relance d'importation.
39. Cliquez sur Traiter.
40. Cliquez sur Confirmer.
    * Vérifiez que le solde de l'établissement réduit le montant de la commande fournisseur.  Dans cet exemple, Montant des achats = 500,00, Limite des services = 10000,00, par conséquent, Solde de l'établissement = 9500,00.  
41. Fermez la page.
42. Entrez un nombre dans le champ Prix unitaire.
43. Cliquez sur Enregistrer.
44. Cliquez sur Achats dans le volet Actions.
45. Cliquez sur Confirmer.
    * Modifiez la lettre de crédit, en fonction de la modification du prix unitaire.  
46. Dans le volet Actions, cliquez sur Gérer.
47. Cliquez sur Lettre de crédit/relance d'importation.
    * Modifiez la lettre de crédit, en fonction de la modification du prix unitaire d'achat.  
48. Cliquez sur Traiter.
49. Cliquez sur Amender.
50. Cliquez sur Supprimer.
51. Cliquez sur Oui.
52. Cliquez sur Extraire les expéditions de commandes fournisseur.
53. Cliquez sur Traiter.
54. Cliquez sur Confirmer.
    * Vérifiez que le solde de l'établissement réduit le montant de la commande fournisseur.  Dans cet exemple, Montant modifié des achats = 600,00, Limite des services = 10 000,00, par conséquent, Solde de l'établissement = 9 400,00.  
55. Fermez la page.

## <a name="post-packing-slip"></a>Valider un bon de livraison
1. Dans le volet Actions, cliquez sur Recevoir.
2. Cliquez sur Accusé de réception de marchandises.
3. Dans le champ PurchParmTable_Num, tapez une valeur.
    * Sélectionnez le numéro d'expédition créé en référence à la lettre de crédit.  
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Dans le champ Date de l'accusé de réception de marchandises, entrez une date.
6. Cliquez sur OK.
7. Fermez la page.
8. Fermez la page.

## <a name="verify-import-letter-of-credit-status"></a>Vérifier le statut d'une lettre de crédit d'importation
1. Accédez à Gestion de la trésorerie et de la banque > Lettres de crédit > Lettre de crédit d'importation/relance d'importation.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Vérifiez le statut de la lettre de crédit d'importation.    
    *   
4. Fermez la page.
5. Fermez la page.

## <a name="post-purchase-invoice"></a>Valider une facture d'achat
1. Accédez à Comptabilité fournisseur > Commandes fournisseur > Toutes les commandes fournisseur.
    * Sélectionnez la commande fournisseur créée avec la lettre de crédit.  
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Dans le volet Actions, cliquez sur Facture.
5. Cliquez sur Facture.
6. Tapez une valeur dans le champ Nombre.
7. Dans le champ Numéro d'expédition, entrez ou sélectionnez une valeur.
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
9. Entrez une date dans le champ Date de facture.
10. Cliquez sur Mettre à jour le statut de rapprochement.
11. Cliquez sur Valider.
12. Fermez la page.
13. Fermez la page.

## <a name="verify-import-letter-of-credit-status"></a>Vérifier le statut d'une lettre de crédit d'importation
1. Accédez à Gestion de la trésorerie et de la banque > Lettres de crédit > Lettre de crédit d'importation/relance d'importation.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Vérifiez la lettre de crédit d'importation 2.  
    * Validez : Statut de l'expédition = détails de l'établissement bancaire facturé  
4. Cliquez sur Afficher.
5. Cliquez sur Imprimer la demande.
6. Cliquez sur OK.
    * Vérifiez que la demande de lettre de crédit est imprimée.  
7. Fermez la page.
8. Fermez la page.
9. Fermez la page.

## <a name="post-vendor-payment-journal-for-the-created-purchase-invoice-with-letter-of-credit"></a>Valider le journal des paiements fournisseur pour la facture d'achat créée avec une lettre de crédit
1. Accédez à Comptabilité fournisseur > Paiements > Journal des paiements.
2. Cliquez sur Nouveau.
3. Saisissez ou sélectionnez une valeur dans le champ Nom.
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Cliquez sur Lignes.
6. Entrez une date dans le champ Date.
7. Dans le champ Compte, spécifiez les valeurs souhaitées.
8. Cliquez sur Régler les transactions.
9. Développez la section Totaux.
10. Dans le champ Afficher, sélectionnez une option.
    * Vérifiez que les champs Numéro de document bancaire et Numéro d'expédition ont été mis à jour.  
11. Cochez la case Marquer.
12. Cliquez sur OK.
13. Cliquez sur l'onglet Paiement.
    * Vérifiez que les champs Numéro de document bancaire et Numéro d'expédition ont été mis à jour.  
14. Cliquez sur Valider.
15. Fermez la page.
16. Fermez la page.

## <a name="verify-import-letter-of-credit-status-after-invoice-paid"></a>Vérifier le statut de la lettre de crédit d'importation une fois la facture payée
1. Accédez à Gestion de la trésorerie et de la banque > Lettres de crédit > Lettre de crédit d'importation/relance d'importation.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Vérifiez le statut de la lettre de crédit d'importation.   
4. Fermez la page.

## <a name="verify-the-bank-facility-limit-and-utilization-report"></a>Vérifier l'état de la limite des services de l'établissement bancaire et l'utilisation
1. Accédez à Gestion de la trésorerie et de la banque > Recherches et états > Lettres de crédit ou garantie > État des moyens bancaires et utilisation.
2. Développez les enregistrements pour inclure la section.
3. Cliquez sur Filtre.
    * Définissez le champ Critères avec le compte bancaire requis.  
4. Dans le champ Critères, saisissez ou sélectionnez une valeur.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Cliquez sur OK.
7. Cliquez sur OK.
    * Vérifiez l'état qui répertorie les transactions.  
    * Vérifiez que l'état répertorie les transactions avec le numéro de document bancaire, la limite des services, le montant utilisé et le montant du solde d'établissement.  
8. Fermez la page.


