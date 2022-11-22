---
title: Lettre de crédit d’exportation
description: Cette procédure décrit le processus associé à une lettre de crédit d’exportation.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, DefaultDashboard, SalesTableListPage, SalesCreateOrder, SalesTable, BankLCExport, SalesEditLines,  LedgerJournalTable, LedgerJournalTransCustPaym, CustOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cf06a73bf7665059658c7884a0b9f973929d647c
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779552"
---
# <a name="export-letter-of-credit"></a>Lettre de crédit d’exportation

[!include [banner](../../includes/banner.md)]

Cette procédure décrit le processus associé à une lettre de crédit d’exportation.

Une lettre de crédit est un accord émis par une banque, dans lequel la banque accepte de garantir le paiement au nom de l’acheteur, si les conditions de l’accord entre l’acheteur et le vendeur sont satisfaites.



Exécutez la procédure **Configurer les établissements bancaires et les profils de validation** et la procédure **Lettre de crédit_Créer un accord d’établissement bancaire** avant cette procédure. Pour exécuter cette procédure correctement, vous devez sélectionner la société fictive USMF.


## <a name="create-sales-order-for-export-letter-of-credit"></a>Créer une commande client pour une lettre de crédit d’exportation
1. Accédez à **Comptabilité client > Commandes > Toutes les commandes client**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Compte client**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Développez ou réduisez la section **Général**.
7. Dans le champ **Site**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Sélectionnez le **Site** dans lequel l’article à sortir est stocké.  
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
9. Dans le champ **Entrepôt**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Sélectionner l’**Entrepôt** dans lequel l’article à sortir est stocké.  
10. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Remarque : le champ **Type de document bancaire** doit être sélectionné avec la **Lettre de crédit**.  
11. Dans le champ **Type de document bancaire**, sélectionnez **Lettre de crédit**.
12. Développez ou réduisez la section **Livraison**.
    * Sélectionnez **Vérification de la date de livraison** = **Aucun(e)**.  
13. Dans le champ **Date de réception demandée**, entrez une date.
14. Cliquez sur **OK**.
15. Dans le champ **Numéro d’article**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Sélectionnez l’article requis qui doit sortir/être vendu.  
16. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
17. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
18. Entrez un nombre dans le champ **Prix unitaire**.
19. Développez ou réduisez la section **Détails de ligne**.
20. Cliquez sur l’onglet **Livraison**.
21. Dans le champ **Date d’expédition demandée**, entrez une date.
22. Dans le champ **Date d’expédition confirmée**, entrez une date.
23. Dans le volet Actions, cliquez sur **Gérer**.
24. Cliquez sur **Lettre de crédit**.
25. Dans le champ **Numéro de document bancaire**, tapez une valeur.
26. Entrez une date et une heure dans le champ **Date d’expiration**.
27. Développez ou réduisez la section **Détails bancaires**.
28. Dans le champ **Banque émettrice**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
29. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
30. Dans le champ **Banque conseillère**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
31. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
32. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
33. Cliquez sur **Extraire les expéditions de la commande client**.
34. Cliquez sur **Émettre le document bancaire**.
35. Fermez la page.

## <a name="post-packing-slip"></a>Valider un bon de livraison
1. Dans le volet Actions, cliquez sur **Prélever et emballer**.
2. Cliquez sur **Valider le bon de livraison**.
3. Développez ou réduisez la section **Paramètres**.
4. Sélectionnez **Tout** dans le champ **Quantité**.
5. Développez ou réduisez la section **Paramétrage**.
6. Dans le champ **Date de bon de livraison**, entrez une date.
7. Sélectionnez le numéro d’expédition.
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
9. Cliquez sur **OK**.
10. Cliquez sur **OK**.

## <a name="post-sales-invoice"></a>Valider une facture client
1. Cliquez sur **Facture** dans le volet Actions.
2. Cliquez sur **Facture**.
3. Développez ou réduisez la section **Vue d’ensemble**.
4. Sélectionnez le **numéro d’expédition**.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Développez ou réduisez la section **Paramétrage**.
7. Entrez une date dans le champ **Date de facture**.
8. Cliquez sur **OK**.
9. Cliquez sur **OK**.

## <a name="shipment-document-submitted-status"></a>Statut du document d’expédition soumis
1. Dans le volet Actions, cliquez sur **Gérer**.
2. Cliquez sur **Lettre de crédit**.
3. Développez ou réduisez la section **Lignes**.
    * Remarque : le champ **Document soumis** doit être défini à **Oui**.  

## <a name="verify-export-letter-of-credit"></a>Vérifier la lettre de crédit d’exportation
1. Accédez à **Gestion de la trésorerie et de la banque > Lettres de crédit > Lettre de crédit d’exportation/relance d’importation**.
2. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Vérifiez que l’option **Lettre de crédit d’exportation** est définie sur le **statut d’expédition** **Facturée**.  

## <a name="customer-payment"></a>Client – Paiements
1. Accédez à **Comptabilité client > Paiements > Journal des paiements**.
2. Cliquez sur **Nouveau**.
3. Dans la liste, marquez la ligne sélectionnée.
4. Dans le champ **Nom**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Cliquez sur **Lignes**.
7. Entrez une date dans le champ **Date**.
8. Dans le champ **Compte**, spécifiez les valeurs souhaitées.
9. Cliquez sur **Règlement**.
10. Cochez la case dans l’en-tête de Totaux.
    * Remarque : définissez le champ **Afficher** sur **Lettre de crédit**.  
11. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
12. Cochez ou décochez la case **Marquer**.
13. Cliquez sur **OK**.
14. Cliquez sur l’onglet **Paiement**.
    * Vérifier le numéro de document bancaire et le numéro d’expédition  
15. Cliquez sur **Valider**.

## <a name="verify-export-letter-of-credit-after-payment"></a>Vérifier la lettre de crédit d’exportation après paiement
1. Accédez à **Gestion de la trésorerie et de la banque > Lettres de crédit > Lettre de crédit d’exportation/relance d’importation**.
2. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Vérifiez que **Statut de l’expédition** = **Paiement reçu** et que **Montant du solde** = **0,00**.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
