---
title: Enregistrer la facture fournisseur et la mettre en correspondance avec la quantité reçue
description: Lorsque vous recevez une facture d’un fournisseur pour des marchandises ou des services sur une commande fournisseur, il est possible que les processus entreprise demandent que les marchandises ou les services soient reçus avant que la facture ne soit approuvée pour paiement.
author: ShivamPandey-msft
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 352e188dcd25b486a1284be6958f44a5543f222c358153557366f9bdcc209f05
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722909"
---
# <a name="record-vendor-invoice-and-match-against-received-quantity"></a>Enregistrer la facture fournisseur et la mettre en correspondance avec la quantité reçue

[!include [banner](../../includes/banner.md)]

Lorsque vous recevez une facture d’un fournisseur pour des marchandises ou des services sur une commande fournisseur, il est possible que les processus entreprise demandent que les marchandises ou les services soient reçus avant que la facture ne soit approuvée pour paiement. Avant de commencer, vérifiez que la clé de configuration Rapprochement de factures est sélectionnée. 

Dans la page Comptabilité fournisseur, vérifiez que l’option Activer le contrôle de rapprochement de factures est sélectionnée, que le champ Valider la facture avec les non-correspondances est bien défini sur Demander une approbation, et que le champ Stratégie de rapprochement des lignes est défini sur Rapprochement à trois facteurs.

La société fictive USMF sert d’exemple dans cette procédure. Les différentes étapes seront effectuées par le responsable comptabilité fournisseur ou le gestionnaire comptable.


## <a name="create-a-purchase-order"></a>Créer une commande fournisseur
1. Allez dans Toutes les commandes fournisseur.
2. Cliquez sur Nouveau.
3. Dans le champ Compte fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Tapez une valeur dans le champ Compte fournisseur.
5. Cliquez sur OK.
6. Cliquez sur Ajouter une ligne.
7. Tapez une valeur dans le champ Numéro d’article.
8. Cliquez sur Achats dans le volet Actions.
9. Cliquez sur Confirmer.

## <a name="post-a-product-receipt"></a>Valider un accusé de réception de marchandises
1. Dans le volet Actions, cliquez sur Recevoir.
2. Cliquez sur Accusé de réception de marchandises.
3. Dans la liste, marquez la ligne sélectionnée.
4. Tapez une valeur dans le champ Accusé de réception de marchandises.
5. Cliquez sur OK.

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a>Enregistrer et mettre en correspondance une facture fournisseur avec un accusé de réception de marchandises
1. Dans le volet Actions, cliquez sur Facture.
2. Cliquez sur Facture.
3. Tapez une valeur dans le champ Nombre.
4. Cliquez sur Valeur par défaut de : Quantité commandée pour ouvrir la boîte de dialogue.
5. Sélectionnez une option dans le champ Quantité par défaut pour les lignes.
6. Cliquez sur OK.
7. Cliquez sur Oui.
8. Cliquez sur Mettre en correspondance les accusés de réception de marchandises.
9. Cliquez sur OK.
10. Cliquez sur Revoir dans le volet Actions.
11. Cliquez sur Mise en correspondance des détails.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]