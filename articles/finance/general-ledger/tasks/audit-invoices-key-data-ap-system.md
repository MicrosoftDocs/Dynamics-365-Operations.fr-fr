---
title: Auditer les factures et indexer les données dans la comptabilité fournisseur
description: Cet article montre comment auditer les factures et les données clés de la comptabilité fournisseur.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4525534f906322c7fe4c232f0f6da5b308829087
ms.sourcegitcommit: 9740f9b41a7dcf1821c6baccb2e05b9865ac2966
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2022
ms.locfileid: "9775213"
---
# <a name="audit-invoices-and-key-data-in-accounts-payable"></a>Auditer les factures et indexer les données dans la comptabilité fournisseur

[!include [banner](../../includes/banner.md)]

Lorsque vous recevez une facture d’un fournisseur pour des marchandises ou des services sur une commande fournisseur, il est possible que les processus entreprise demandent que les marchandises ou les services soient reçus avant que la facture ne soit approuvée pour paiement. Avant de commencer, vérifiez que la clé de configuration Rapprochement de factures est sélectionnée. 

Dans la page **Comptabilité fournisseur**, vérifiez que l’option **Activer le contrôle de rapprochement de factures** est sélectionnée, que le champ **Valider la facture avec les non-correspondances** est bien défini sur **Demander une approbation**, et que le champ **Stratégie de rapprochement des lignes** est défini sur **Rapprochement à trois facteurs**.

La société fictive USMF sert d’exemple dans cette procédure. Les différentes étapes seront effectuées par le responsable comptabilité fournisseur ou le gestionnaire comptable.


## <a name="create-a-purchase-order"></a>Créer une commande fournisseur
1. Accédez à **Toutes les commandes fournisseur**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Compte fournisseur**, tapez une valeur.
4. Cliquez sur **OK**.
5. Cliquez sur **Ajouter une ligne**.
6. Dans le champ **Numéro d’article**, tapez une valeur.
7. Dans le volet Actions, cliquez sur **Achat**.
8. Cliquez sur **Confirmer**.

## <a name="post-a-product-receipt"></a>Valider un accusé de réception de marchandises
1. Dans le volet Action, cliquez sur **Recevoir**.
2. Cliquez sur **Accusé de réception de marchandises**.
3. Dans le champ **Accusé de réception de marchandises**, tapez une valeur.
4. Cliquez sur **OK**.

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a>Enregistrer et mettre en correspondance une facture fournisseur avec un accusé de réception de marchandises
1. Dans le volet Actions, cliquez sur **Facture > Facture**.
2. Dans le champ **Nombre**, tapez une valeur.
3. Cliquez sur **Valeur par défaut de : Quantité commandée** pour ouvrir la boîte de dialogue.
4. Dans le champ **Quantité par défaut pour les lignes**, sélectionnez une option.
5. Cliquez sur **OK**.
6. Cliquez sur **Oui**.
7. Cliquez sur **Mettre en correspondance les accusés de réception de marchandises**.
8. Cliquez sur **OK**.
9. Cliquez sur **Revoir** dans le volet Actions.
10. Cliquez sur **Mise en correspondance des détails**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
