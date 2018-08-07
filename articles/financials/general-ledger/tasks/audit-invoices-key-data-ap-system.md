--- 
title: "Auditer les factures et les données clés dans la comptabilité fournisseur"
description: "Lorsque vous recevez une facture d'un fournisseur pour des marchandises ou des services sur une commande fournisseur, il est possible que les processus entreprise demandent que les marchandises ou les services soient reçus avant que la facture ne soit approuvée pour paiement."
author: saraschi2
manager: AnnBe
ms.date: 02/16/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 5cd9448c95b7ec0c4a82aca3d21d961259dfb109
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="audit-invoices-and-key-data-in-accounts-payable"></a>Auditer les factures et les données clés dans la comptabilité fournisseur

[!include [task guide banner](../../includes/task-guide-banner.md)]

Lorsque vous recevez une facture d'un fournisseur pour des marchandises ou des services sur une commande fournisseur, il est possible que les processus entreprise demandent que les marchandises ou les services soient reçus avant que la facture ne soit approuvée pour paiement. Avant de commencer, vérifiez que la clé de configuration Rapprochement de factures est sélectionnée. 

Dans la page Comptabilité fournisseur, vérifiez que l'option Activer le contrôle de rapprochement de factures est sélectionnée, que le champ Valider la facture avec les non-correspondances est bien défini sur Demander une approbation, et que le champ Stratégie de rapprochement des lignes est défini sur Rapprochement à trois facteurs.

La société fictive USMF sert d'exemple dans cette procédure. Les différentes étapes seront effectuées par le responsable comptabilité fournisseur ou le gestionnaire comptable.


## <a name="create-a-purchase-order"></a>Créer une commande fournisseur
1. Allez dans Toutes les commandes fournisseur.
2. Cliquez sur Nouveau.
3. Dans le champ Compte fournisseur, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Tapez une valeur dans le champ Compte fournisseur.
5. Cliquez sur OK.
6. Cliquez sur Ajouter une ligne.
7. Tapez une valeur dans le champ Numéro d'article.
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


