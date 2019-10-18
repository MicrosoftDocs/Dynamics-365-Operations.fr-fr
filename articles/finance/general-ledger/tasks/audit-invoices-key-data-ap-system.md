---
title: Auditer les factures et les données clé dans le système de comptabilité fournisseur
description: Lorsque vous recevez une facture d'un fournisseur pour des marchandises ou des services sur une commande fournisseur, il est possible que les processus entreprise demandent que les marchandises ou les services soient reçus avant que la facture ne soit approuvée pour paiement.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c6e8967fe4db67ff98fc7093792bdb82b73a33d9
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177668"
---
# <a name="audit-invoices-and-key-data-in-ap-system"></a>Auditer les factures et les données clé dans le système de comptabilité fournisseur

[!include [task guide banner](../../includes/task-guide-banner.md)]

Lorsque vous recevez une facture d'un fournisseur pour des marchandises ou des services sur une commande fournisseur, il est possible que les processus entreprise demandent que les marchandises ou les services soient reçus avant que la facture ne soit approuvée pour paiement. Avant de commencer, vérifiez que la clé de configuration Rapprochement de factures est sélectionnée. 

Dans la page Comptabilité fournisseur, vérifiez que l'option Activer le contrôle de rapprochement de factures est sélectionnée, que le champ Valider la facture avec les non-correspondances est bien défini sur Demander une approbation, et que le champ Stratégie de rapprochement des lignes est défini sur Rapprochement à trois facteurs.

La société fictive USMF sert d'exemple dans cette procédure. Les différentes étapes seront effectuées par le responsable comptabilité fournisseur ou le gestionnaire comptable.


## <a name="create-a-purchase-order"></a>Créer une commande fournisseur
1. Accédez à **Toutes les commandes fournisseur**.
2. Cliquez sur **Nouveau**.
3. Dans le champ **Compte fournisseur**, tapez une valeur.
4. Cliquez sur **OK**.
5. Cliquez sur **Ajouter une ligne**.
6. Dans le champ **Numéro d'article**, tapez une valeur.
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

