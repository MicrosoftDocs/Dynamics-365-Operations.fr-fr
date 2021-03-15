---
title: Retenue à la source dans les transactions d'achat
description: Pour les fournisseurs qui sont soumis à une retenue à la source, vous pouvez attribuer le **Groupe de retenue à la source** sur la page **Tous les fournisseurs**.
author: roschlom
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 06997e2d6b47d867e014a7d493d91015c78a5e04
ms.sourcegitcommit: 630a0b3f800f36ced49b79156dd52132904fef75
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2021
ms.locfileid: "5060734"
---
# <a name="withholding-tax-in-purchase-transactions"></a>Retenue à la source dans les transactions d'achat

Pour les fournisseurs qui sont soumis à une retenue à la source, vous pouvez attribuer le **Groupe de retenue à la source** sur la page **Tous les fournisseurs**.

1. Allez dans **Volet de navigation > Modules > Comptabilité fournisseur > Fournisseur > Tous les fournisseurs**.

2. Cliquez sur le compte fournisseur concerné, puis sur **Modifier**.

3. Dans l'onglet **Facturation et livraison**, définissez le champ **Calcul de la retenue à la source** sur **Oui**.

   > [!NOTE] 
   > La retenue à la source ne sera pas calculée si le champ **Calcul de la retenue à la source** n'est pas activé pour ce fournisseur dans les données principales.

4. Sélectionnez un groupe de retenue à la source dans le **Groupe de retenue à la source**.

5. Cliquez sur **Enregistrer**.

Pour les articles/services soumis à une retenue à la source, vous pouvez attribuer la valeur par défaut du **Groupe de retenue à la source d'articles** dans **Produits lancés**.

1. Accédez à **Volet de navigation > Modules > Gestion d'informations sur les produits > Produits > Produits lancés**.

2. Cliquez sur le numéro d’article concerné, puis sur **Modifier**.

3. Dans l'onglet **Achat**, cliquez sur **Calcul de la retenue à la source**.

   > [!NOTE] 
   > La retenue à la source ne sera pas calculée si le champ **Calcul de la retenue à la source** n'est pas défini sur **Oui** pour cet article dans l'onglet **Achat** sur la page **Produit lancé**.

4. Sélectionnez un groupe de retenue à la source d'articles dans la liste **Groupe de retenue à la source d'articles**.

5. Cliquez sur **Enregistrer**.

Les groupes de retenue à la source et les groupes de retenue à la source d'articles peuvent être attribués dans les pages : 

- **Commande fournisseur**
- **Facture fournisseur**
- **Journal des factures**

Le groupe de retenue à la source et le groupe de retenue à la source d'articles par défaut seront reportés dans les lignes lors de la création des **Commandes fournisseur** et/ou des **Factures fournisseur en attente**. Pour le **Journal des factures fournisseur**, vous pouvez activer **Calcul de la retenue à la source** et sélectionner **Groupe de retenue à la source d'articles** dans l'onglet **Général** du journal.

Le montant temporaire de la retenue à la source est disponible dans le champ **Retenue à la source ajustée** de l'onglet **Totaux** sur la page **Bon de commande**.

![La retenue à la source est incluse dans le bon de commande](media/withholding-tax-adjusted.png)

La retenue à la source est calculée dans le **Journal des paiements fournisseur**. Vous pouvez ajuster manuellement les codes de retenue à la source applicables, ainsi que les montants réels de la retenue à la source dans l'onglet **Retenue à la source** sur la page **Régler des transactions**.

![La retenue peut être ajustée manuellement sur la page Règlement des transactions](media/withholding-tax-vendor-payment-tab.png)

Le montant de la retenue à la source dérivé sera déduit du paiement du fournisseur et imputé au compte **Compte de retenue à la source** dans un justificatif associé.

![Compte de retenue à la source montrant un justificatif associé](media/withholding-tax-adjusted.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]