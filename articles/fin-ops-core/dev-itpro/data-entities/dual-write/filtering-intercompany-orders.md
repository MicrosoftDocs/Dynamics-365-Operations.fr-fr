---
title: Filtrer les commandes intersociétés pour éviter de synchroniser les commandes et les lignes de commande
description: Cette rubrique explique comment filtrer les commandes intersociétés afin que les entités Orders et OrderLines ne soient pas synchronisées.
author: negudava
ms.date: 11/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: negudava
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 5e7b0188d5c2dc4ee7691266aa4c857fc189d0f0
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6347246"
---
# <a name="filter-intercompany-orders-to-avoid-syncing-orders-and-orderlines"></a>Filtrer les commandes intersociétés pour éviter de synchroniser les commandes et les lignes de commande

[!include [banner](../../includes/banner.md)]

Vous pouvez filtrer les commandes intersociétés pour éviter de synchroniser les tables **Orders** et **OrderLines**. Dans certains scénarios, les détails de la commande intersociétés ne sont pas nécessaires dans l’application d’engagement client.

Chacune des tables Dataverse standard est étendue avec des références à la colonne **IntercompanyOrder** et les mappages à double écriture sont modifiés pour faire référence aux colonnes supplémentaires dans les filtres. Par conséquent, les commandes intersociétés ne sont plus synchronisées. Ce processus évite les données inutiles dans l’application d’engagement client.

1. Développez la table **En-têtes de commande client CDS** en ajoutant une référence à la colonne **Commande intersociété**. Cette colonne est renseignée uniquement sur les commandes intersociétés. La colonne **IntercompanyOrder** est disponible dans la table **SalesTable**.

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Mapper la mise en lots à la page cible pour les en-têtes de commande client CDS.":::

2. Une fois **En-têtes de commande client CDS** étendu, la colonne **IntercompanyOrder** est disponible dans le mappage. Appliquez un filtre avec `INTERCOMPANYORDER == ""` comme chaîne de requête.

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="Modifier la boîte de dialogue pour les en-têtes de commande client CDS.":::

3. Développez la table **Lignes de commande client CDS** en ajoutant une référence à la colonne **IntercompanyInventTransId**. Cette colonne est renseignée uniquement sur les commandes intersociétés. La colonne **InterCompanyInventTransId** est disponible dans la table **SalesLine**.

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Mapper la mise en lots à la page cible pour les lignes de commande client CDS.":::

4. Une fois **Lignes de commande client CDS** étendu, la colonne **IntercompanyInventTransId** est disponible dans le mappage. Appliquez un filtre avec `INTERCOMPANYINVENTTRANSID == ""` comme chaîne de requête.

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="Modifier la boîte de dialogue pour les lignes de commande client CDS.":::

5. Répétez les étapes 1 et 2 pour développer la table **En-tête de facture de vente V2** et ajoutez une requête de filtre. Dans ce cas, utilisez `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")` comme chaîne de requête pour le filtre.

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Mapper la mise en lots à la page cible pour l’en-tête de facturation client V2.":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="Modifier la boîte de dialogue pour l’en-tête de commande client V2.":::

6. Répétez les étapes 3 et 4 pour développer la table **Lignes de facture de vente V2** et ajoutez une requête de filtre. Dans ce cas, utilisez `INTERCOMPANYINVENTTRANSID == ""` comme chaîne de requête pour le filtre.

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="Modifier la boîte de dialogue pour les lignes de commande client V2.":::

7. La table **Citations** n’a pas de relation intersociétés. Si quelqu’un crée un devis pour l’un de vos clients intersociétés, vous pouvez utiliser la colonne **CustGroup** pour placer tous ces clients dans un groupe de clients. Vous pouvez développer l’en-tête et les lignes en ajoutant la colonne **CustGroup**, puis filtrer de sorte que le groupe n’est pas inclus.

    :::image type="content" source="media/filter-cust-group.png" alt-text="Mapper la mise en lots à la page cible pour l’en-tête de devis client CDS.":::

8. Après avoir développé **Devis**, appliquez un filtre avec `CUSTGROUP != "<company>"` comme chaîne de requête.

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="Modifier la boîte de dialogue pour l’en-tête de devis client CDS.":::


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]