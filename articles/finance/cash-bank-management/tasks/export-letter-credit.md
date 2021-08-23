---
title: Lettre de crédit d’exportation
description: Cette procédure décrit le processus associé à une lettre de crédit d’exportation.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, DefaultDashboard, SalesTableListPage, SalesCreateOrder, SalesTable, BankLCExport, SalesEditLines,  LedgerJournalTable, LedgerJournalTransCustPaym, CustOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 87bcf161e385b66ad725fc0fd915368ed3120a1573d780bebfb48ff73cce7847
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6766311"
---
# <a name="export-letter-of-credit"></a>Lettre de crédit d’exportation

[!include [banner](../../includes/banner.md)]

Cette procédure décrit le processus associé à une lettre de crédit d’exportation.

Une lettre de crédit est un accord émis par une banque, dans lequel la banque accepte de garantir le paiement au nom de l’acheteur, si les conditions de l’accord entre l’acheteur et le vendeur sont satisfaites.



Préalablement à cette procédure, exécutez la procédure « Paramétrage des établissements bancaires et profils de validation » et la procédure « Lettre de crédit_Création d’un accord d’établissement bancaire ». Pour exécuter cette procédure correctement, vous devez sélectionner la société fictive USMF.




## <a name="create-sales-order-for-export-letter-of-credit"></a>Créer une commande client pour une lettre de crédit d’exportation
1. Accédez à Comptabilité client > Commandes > Toutes les commandes client.
2. Cliquez sur Nouveau.
3. Dans le champ Compte client, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Développez ou réduisez la section Général.
7. Dans le champ Site, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Sélectionner le site où l’article qui doit sortir est stocké.  
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
9. Dans le champ Entrepôt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Sélectionner l’entrepôt où l’article qui doit sortir est stocké.  
10. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Remarque : le champ « Type de document bancaire » doit être sélectionné et renseigné avec la valeur « Lettre de crédit ».  
11. Dans le champ Type de document bancaire, sélectionnez « Lettre de crédit ».
12. Développez ou réduisez la section Livraison.
    * Sélectionnez Vérification de la date de livraison = Aucun(e).  
13. Dans le champ Date de réception demandée, entrez une date.
14. Cliquez sur OK.
15. Dans le champ Numéro d’article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Sélectionnez l’article requis qui doit sortir/être vendu.  
16. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
17. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
18. Entrez un nombre dans le champ Prix unitaire.
19. Développez ou réduisez la section Détails de ligne.
20. Cliquez sur l’onglet Livraison.
21. Dans le champ Date d’expédition demandée, entrez une date.
22. Dans le champ Date d’expédition confirmée, entrez une date.
23. Dans le volet Actions, cliquez sur Gérer.
24. Cliquez sur Lettre de crédit.
25. Dans le champ Numéro de document bancaire, tapez une valeur.
26. Entrez une date et une heure dans le champ Date d’expiration.
27. Développez ou réduisez la section Détails bancaires.
28. Dans le champ Banque émettrice, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
29. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
30. Dans le champ Banque conseillère, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
31. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
32. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
33. Cliquez sur Extraire les expéditions de la commande client.
34. Cliquez sur Émettre le document bancaire.
35. Fermez la page.

## <a name="post-packing-slip"></a>Valider un bon de livraison
1. Cliquez sur Prélever et emballer dans le volet Actions.
2. Cliquez sur Validation du bon de livraison.
3. Développez ou réduisez la section Paramètres.
4. Sélectionnez Tout dans le champ Quantité.
5. Développez ou réduisez la section Paramétrage.
6. Dans le champ Date de bon de livraison, entrez une date.
7. Sélectionnez le numéro d’expédition.
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
9. Cliquez sur OK.
10. Cliquez sur OK.

## <a name="post-sales-invoice"></a>Valider une facture client
1. Dans le volet Actions, cliquez sur Facture.
2. Cliquez sur Facture.
3. Développez ou réduisez la section Vue d’ensemble.
4. Sélectionnez le numéro d’expédition.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Développez ou réduisez la section Paramétrage.
7. Entrez une date dans le champ Date de facture.
8. Cliquez sur OK.
9. Cliquez sur OK.

## <a name="shipment-document-submitted-status"></a>Statut du document d’expédition soumis
1. Dans le volet Actions, cliquez sur Gérer.
2. Cliquez sur Lettre de crédit.
3. Développez ou réduisez la section Lignes.
    * Remarque : le champ « Document soumis » doit être défini à « Oui ».  

## <a name="verify-export-letter-of-credit"></a>Vérifier la lettre de crédit d’exportation
1. Accédez à Gestion de la trésorerie et de la banque > Lettres de crédit > Lettre de crédit d’exportation/relance d’importation.
2. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Vérifiez que la lettre de crédit d’exportation est dotée du statut d’expédition « Facturée ».  

## <a name="customer-payment"></a>Client – Paiements
1. Accédez à Comptabilité client > Paiements > Journal des paiements.
2. Cliquez sur Nouveau.
3. Dans la liste, marquez la ligne sélectionnée.
4. Dans le champ Nom, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
6. Cliquez sur Lignes.
7. Entrez une date dans le champ Date.
8. Dans le champ Compte, spécifiez les valeurs souhaitées.
9. Cliquez sur Règlement.
10. Cochez la case dans l’en-tête de Totaux.
    * Remarque : définissez le champ Afficher à « Lettre de crédit ».  
11. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
12. Activez ou désactivez la case à cocher Marquer.
13. Cliquez sur OK.
14. Cliquez sur l’onglet Paiement.
    * Vérifier les détails de numéro de document bancaire et de numéro d’expédition  
15. Cliquez sur Valider.

## <a name="verify-export-letter-of-credit-after-payment"></a>Vérifier la lettre de crédit d’exportation après paiement
1. Accédez à Gestion de la trésorerie et de la banque > Lettres de crédit > Lettre de crédit d’exportation/relance d’importation.
2. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Vérifiez que Statut de l’expédition = Paiement reçu et que le montant du solde = 0,00.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]