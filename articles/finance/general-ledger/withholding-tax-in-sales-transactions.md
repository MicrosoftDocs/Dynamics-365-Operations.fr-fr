---
title: Retenue à la source dans les transactions de vente
description: Cet article répertorie les étapes permettant d’éviter le calcul de la retenue à la source pour les clients sélectionnés. Pour les clients qui spécifient une retenue à la source dans leurs paiements, vous pouvez affecter le groupe de retenue à la source par défaut.
author: kailiang
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 75a7fc62c1d493007f3aa88a723465828c557df7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8910082"
---
# <a name="withholding-tax-in-sales-transactions"></a>Retenue à la source dans les transactions de vente

Cet article répertorie les étapes permettant d’éviter le calcul de la retenue à la source pour les clients sélectionnés. Pour les clients qui spécifient une retenue à la source dans leurs paiements, vous pouvez affecter le **Groupe de retenue à la source** sur la page **Clients**. 

1. Allez dans **Volet de navigation > Modules > Comptabilité client > Clients > Tous les clients**.

2. Cliquez sur le compte client concerné, puis sur **Modifier**.

3. Dans l’onglet **Facturation et livraison**, définissez le champ **Calcul de la retenue à la source** sur **Oui**.

   > [!NOTE] 
   > La retenue à la source ne sera pas calculée si le champ **Calcul de la retenue à la source** n’est pas activé pour ce client dans les données principales.

4. Sélectionnez un groupe de retenue à la source dans le **Groupe de retenue à la source**.

5. Cliquez sur **Enregistrer**.

Pour les articles/services soumis à une retenue à la source, vous pouvez attribuer la valeur par défaut du **Groupe de retenue à la source d’articles** dans **Produits lancés**.

1. Accédez à **Volet de navigation > Modules > Gestion d’informations sur les produits > Produits > Produits lancés**.

2. Cliquez sur le numéro d’article concerné, puis sur **Modifier**.

3. Dans l’onglet **Vente**, cliquez sur **Calcul de la retenue à la source**.

   > [!NOTE] 
   > La retenue à la source ne sera pas calculée si le champ **Calcul de la retenue à la source** n’est pas défini sur **Oui** pour cet article dans l’onglet **Vente** sur la page **Produit lancé**.

4. Sélectionnez un groupe de retenue à la source d’articles dans la liste **Groupe de retenue à la source d’articles**.

5. Cliquez sur **Enregistrer**.

Les groupes de retenue à la source et les groupes de retenue à la source d’articles peuvent être attribués à l’aide de la page **Commande client**. 

Le groupe de retenue à la source par défaut et le groupe de retenue à la source d’articles seront utilisés comme entrées par défaut sur les lignes de commande client lorsque vous créez une nouvelle commande client.

La retenue à la source est calculée et comptabilisée avec le **Journal des paiements client**. Vous pouvez ajuster manuellement le code de retenue à la source applicable, ainsi que le montant réel de la retenue à la source dans l’onglet **Retenue à la source** sur la page **Régler des transactions**.

Le montant de la retenue à la source calculé sera déduit du paiement du client et imputé au compte **Compensation de la retenue à la source** dans un justificatif associé.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
