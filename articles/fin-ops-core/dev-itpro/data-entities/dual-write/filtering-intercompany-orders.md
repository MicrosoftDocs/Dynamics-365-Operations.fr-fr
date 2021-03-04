---
title: Filtrer les commandes intersociétés pour éviter de synchroniser les commandes et les lignes de commande
description: Cette rubrique décrit comment filtrer les commandes intersociétés pour éviter de synchroniser les commandes et les lignes de commande.
author: negudava
manager: tfehr
ms.date: 11/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: negudava
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 6c5e1e2467673badd20366d3bd8e1b93b8078b26
ms.sourcegitcommit: 0eb33909a419d526eb84b4e4b64d3595d01731ef
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2020
ms.locfileid: "4701031"
---
# <a name="filter-intercompany-orders-to-avoid-synchronizing-orders-and-orderlines"></a>Filtrer les commandes intersociétés pour éviter de synchroniser les commandes et les lignes de commande

[!include [banner](../../includes/banner.md)]

Vous pouvez filtrer les commandes intersociétés pour éviter de synchroniser les entités **Orders** et **OrderLines**. Dans certains scénarios, les détails de la commande intersociétés ne sont pas nécessaires dans l’application d’engagement client.

Chacune des entités Common Data Service standard est étendue avec des références au champ **IntercompanyOrder** et les mappages à double écriture sont modifiés pour faire référence aux champs supplémentaires dans les filtres. Le résultat est que les commandes intersociétés ne sont plus synchronisées. Ce processus évite les données inutiles dans l’application d’engagement client.

1. Ajouter une référence à **IntercompanyOrder** à **En-têtes de commande client CDS**. Il est renseigné uniquement sur les commandes intersociétés. Le champ **IntercompanyOrder** est disponible dans **SalesTable**.

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Mapper la mise en lots à la cible, SalesOrderHeader":::
    
2. Une fois **En-têtes de commande client CDS** étendu, le champ **IntercompanyOrder** est disponible dans le mappage. Appliquez un filtre avec `INTERCOMPANYORDER == ""` comme chaîne de requête.

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="En-têtes de commandes client, modifier la requête":::

3. Ajouter une référence à **IntercompanyInventTransId** à **Lignes de commande client CDS**.  Il est renseigné uniquement sur les commandes intersociétés. Le champ **InterCompanyInventTransID** est disponible dans **SalesLine**.

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Mapper la mise en lots à la cible, SalesOrderLine":::

4. Une fois **Lignes de commande client CDS** étendu, le champ **IntercompanyInventTransId** est disponible dans le mappage. Appliquez un filtre avec `INTERCOMPANYINVENTTRANSID == ""` comme chaîne de requête.

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="Lignes de commande client, modifier la requête":::

5. Étendre **En-tête de facture de vente V2** et **Lignes de facture de vente V2** de la même manière que vous avez prolongé les entités Common Data Service aux étapes 1 et 2. Ajoutez ensuite les requêtes de filtre. La chaîne de filtre pour **En-tête de facture de vente V2** est `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")`. La chaîne de filtre pour **Lignes de facture de vente V2** est `INTERCOMPANYINVENTTRANSID == ""`.

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Mapper la mise en lots à la cible, En-têtes de factures client":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="En-têtes de factures client, modifier la requête":::

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="Lignes de factures client, modifier la requête":::

6. L’entité **Citations** n’a pas de relation intersociétés. Si quelqu’un crée un devis pour l’un de vos clients intersociétés, vous pouvez placer tous ces clients dans un groupe de clients en utilisant le champ **CustGroup**.  L’en-tête et les lignes peuvent être étendus pour ajouter le champ **CustGroup** puis filtrez pour ne pas inclure ce groupe.

    :::image type="content" source="media/filter-cust-group.png" alt-text="Mapper la mise en lots à la cible, En-têtes de devis de vente":::

7. Après avoir étendu entité **Devis**, appliquez un filtre avec `CUSTGROUP !=  "<company>"` comme chaîne de requête.

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="En-tête de devis de vente, modifier la requête":::


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]