---
title: Création et facturation d’une commande fournisseur intersociétés pour un usage interne
description: Cette rubrique explique comment créer et facturer une commande fournisseur intersociétés pour un usage interne
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchLineOpenOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 88a14ff962c5cf0cd1cff24b16cc7a62e9e1c8ce
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548262"
---
# <a name="create-and-invoice-an-intercompany-purchase-order-for-internal-use"></a>Création et facturation d’une commande fournisseur intersociétés pour un usage interne

[!include [banner](../../includes/banner.md)]

Vous pouvez créer une commande fournisseur intersociétés pour un fournisseur intersociétés. Cela crée automatiquement une commande client intersociétés pour le fournisseur intersociétés.

![Processus d'achat interne intersociétés](media/intercompanypurchaseprocess.png)

## <a name="create-an-intercompany-purchase-order-and-a-corresponding-intercompany-sales-order"></a>Création d'une commande fournisseur intersociétés et d'une commande client intersociétés correspondante

Procédez comme suit dans l'entité juridique AAA, comme le montre l'illustration.

1. Sélectionnez **Comptabilité fournisseur** \> **Commandes fournisseur** \> **Toutes les commandes fournisseur**.
1. Dans la page de liste **Toutes les commandes fournisseur**, créez une commande fournisseur pour un fournisseur intersociétés. Les valeurs des champs sont copiées du compte fournisseur vers la commande fournisseur.

    Étant donné que vous utilisez un fournisseur intersociétés, une commande client intersociétés est créée dans l'entité juridique correspondant au fournisseur. Le numéro de la commande client intersociétés peut être identique au numéro de la commande fournisseur intersociétés, et peut inclure l'ID de l'entité juridique. La structure de numérotation utilisée dépend de la sélection effectuée dans le champ **Numérotation des commandes client** sur la page **Intersociétés**. Par exemple, si vous créez la commande fournisseur 00029\_064 dans l'entité juridique AAA, le numéro de commande client dans l'entité juridique BBB est AAA00029\_64.

    Un message d'information indique qu'une commande fournisseur intersociétés et une commande client intersociétés ont été créées. Le message inclut le numéro de commande client intersociétés, pour votre information.

1. Ajoutez des articles de ligne à la commande fournisseur. Les articles de ligne correspondants sont automatiquement ajoutés à la commande client intersociétés. Si un article n'existe pas dans l'autre entité juridique, un message s'affiche et vous ne pouvez pas ajouter l'article à la commande fournisseur. Pour résoudre ce problème, basculez vers l'autre entité juridique et lancez le produit dans cette entité juridique. L'article sera disponible pour être ajouté aux commandes client dans cette entité juridique. Ensuite, rebasculez vers l'entité juridique de la commande fournisseur et continuez d'ajouter des articles de ligne.
1. Lorsque vous avez terminé d'entrer les informations de la commande fournisseur, confirmez-la.

## <a name="process-the-intercompany-packing-slip-and-customer-invoice"></a>Traitement du bon de livraison intersociétés et de la facture client intersociétés

Procédez comme suit dans l'entité juridique BBB, comme le montre l'illustration.

1. Accédez à **Comptabilité client \> Commandes client \> Toutes les commandes client**.
1. Dans la page de liste **Toutes les commandes client**, sélectionnez une commande client intersociétés.
1. Dans le volet Actions, sélectionnez l'onglet **Choisir et emballer**, puis sélectionnez **Bon de livraison**.
1. Cochez la case **Validation**.
1. Cliquez sur **OK**. Le bon de livraison est validé dans l'entité juridique BBB.
1. Dans la page de liste **Toutes les commandes client**, sélectionnez une commande client intersociétés.
1. Dans le volet Actions, sélectionnez l'onglet **Facture**, puis sélectionnez à nouveau **Facture**.
1. Cochez la case **Validation**.
1. Cliquez sur **OK**.

    La facture client pour la commande client intersociétés est validée dans l'entité juridique BBB.

## <a name="process-the-intercompany-product-receipt-and-vendor-invoice"></a>Traitement de l'accusé de réception de marchandises intersociétés et de la facture fournisseur intersociétés

Procédez comme suit dans l'entité juridique AAA, comme le montre l'illustration.

1. Accédez à **Comptabilité fournisseur \> Commandes fournisseur \> Toutes les commandes fournisseur**.
1. Dans la page de liste **Toutes les commandes fournisseur**, sélectionnez une commande fournisseur intersociétés.
1. Dans le volet Actions, sélectionnez **Recevoir**, puis sélectionnez **Réception des produits**. L'accusé de réception de marchandises est créé. Le numéro de l'accusé de réception de marchandises est identique à celui du bon de livraison intersociétés.
1. Cochez la case **Validation**.
1. Cliquez sur **OK**.
1. Dans la page de liste **Toutes les commandes fournisseur**, sélectionnez une commande fournisseur intersociétés.
1. Dans le volet Actions, sélectionnez **Facture**, puis sélectionnez à nouveau **Facture**. La facture fournisseur est créée. Le numéro de facture fournisseur est identique à celui de la facture client intersociétés.
1. Finissez d'entrer la facture fournisseur, puis validez-la.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
