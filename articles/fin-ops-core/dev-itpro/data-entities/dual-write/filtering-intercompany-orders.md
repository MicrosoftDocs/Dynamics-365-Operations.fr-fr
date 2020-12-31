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
# <a name="filter-intercompany-orders-to-avoid-synchronizing-orders-and-orderlines"></a><span data-ttu-id="7b06e-103">Filtrer les commandes intersociétés pour éviter de synchroniser les commandes et les lignes de commande</span><span class="sxs-lookup"><span data-stu-id="7b06e-103">Filter intercompany orders to avoid synchronizing Orders and OrderLines</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7b06e-104">Vous pouvez filtrer les commandes intersociétés pour éviter de synchroniser les entités **Orders** et **OrderLines**.</span><span class="sxs-lookup"><span data-stu-id="7b06e-104">You can filter intercompany orders to avoid synchronizing the **Orders** and **OrderLines** entities.</span></span> <span data-ttu-id="7b06e-105">Dans certains scénarios, les détails de la commande intersociétés ne sont pas nécessaires dans l’application d’engagement client.</span><span class="sxs-lookup"><span data-stu-id="7b06e-105">In some scenarios, the intercompany order details are not necessary in customer engagement app.</span></span>

<span data-ttu-id="7b06e-106">Chacune des entités Common Data Service standard est étendue avec des références au champ **IntercompanyOrder** et les mappages à double écriture sont modifiés pour faire référence aux champs supplémentaires dans les filtres.</span><span class="sxs-lookup"><span data-stu-id="7b06e-106">Each of the standard Common Data Service entities is extended with references to the **IntercompanyOrder** field, and the dual-write maps are modified to refer to the additional fields in the filters.</span></span> <span data-ttu-id="7b06e-107">Le résultat est que les commandes intersociétés ne sont plus synchronisées.</span><span class="sxs-lookup"><span data-stu-id="7b06e-107">The result is that the intercompany orders are no longer synchronized.</span></span> <span data-ttu-id="7b06e-108">Ce processus évite les données inutiles dans l’application d’engagement client.</span><span class="sxs-lookup"><span data-stu-id="7b06e-108">This process avoids unnecessary data in the customer engagement app.</span></span>

1. <span data-ttu-id="7b06e-109">Ajouter une référence à **IntercompanyOrder** à **En-têtes de commande client CDS**.</span><span class="sxs-lookup"><span data-stu-id="7b06e-109">Add a reference to **IntercompanyOrder** to **CDS Sales Order Headers**.</span></span> <span data-ttu-id="7b06e-110">Il est renseigné uniquement sur les commandes intersociétés.</span><span class="sxs-lookup"><span data-stu-id="7b06e-110">It is populated on only intercompany orders.</span></span> <span data-ttu-id="7b06e-111">Le champ **IntercompanyOrder** est disponible dans **SalesTable**.</span><span class="sxs-lookup"><span data-stu-id="7b06e-111">The field **IntercompanyOrder** is available in **SalesTable**.</span></span>

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Mapper la mise en lots à la cible, SalesOrderHeader":::
    
2. <span data-ttu-id="7b06e-113">Une fois **En-têtes de commande client CDS** étendu, le champ **IntercompanyOrder** est disponible dans le mappage.</span><span class="sxs-lookup"><span data-stu-id="7b06e-113">After **CDS Sales Order Headers** is extended, the **IntercompanyOrder** field is available in the mapping.</span></span> <span data-ttu-id="7b06e-114">Appliquez un filtre avec `INTERCOMPANYORDER == ""` comme chaîne de requête.</span><span class="sxs-lookup"><span data-stu-id="7b06e-114">Apply a filter with `INTERCOMPANYORDER == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="En-têtes de commandes client, modifier la requête":::

3. <span data-ttu-id="7b06e-116">Ajouter une référence à **IntercompanyInventTransId** à **Lignes de commande client CDS**.</span><span class="sxs-lookup"><span data-stu-id="7b06e-116">Add a reference to **IntercompanyInventTransId** to **CDS Sales Order Lines**.</span></span>  <span data-ttu-id="7b06e-117">Il est renseigné uniquement sur les commandes intersociétés.</span><span class="sxs-lookup"><span data-stu-id="7b06e-117">It is populated on only intercompany orders.</span></span> <span data-ttu-id="7b06e-118">Le champ **InterCompanyInventTransID** est disponible dans **SalesLine**.</span><span class="sxs-lookup"><span data-stu-id="7b06e-118">The field **InterCompanyInventTransID** is available in **SalesLine**.</span></span>

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Mapper la mise en lots à la cible, SalesOrderLine":::

4. <span data-ttu-id="7b06e-120">Une fois **Lignes de commande client CDS** étendu, le champ **IntercompanyInventTransId** est disponible dans le mappage.</span><span class="sxs-lookup"><span data-stu-id="7b06e-120">After **CDS Sales Order Lines** is extended, the **IntercompanyInventTransId** field is available in the mapping.</span></span> <span data-ttu-id="7b06e-121">Appliquez un filtre avec `INTERCOMPANYINVENTTRANSID == ""` comme chaîne de requête.</span><span class="sxs-lookup"><span data-stu-id="7b06e-121">Apply a filter with `INTERCOMPANYINVENTTRANSID == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="Lignes de commande client, modifier la requête":::

5. <span data-ttu-id="7b06e-123">Étendre **En-tête de facture de vente V2** et **Lignes de facture de vente V2** de la même manière que vous avez prolongé les entités Common Data Service aux étapes 1 et 2.</span><span class="sxs-lookup"><span data-stu-id="7b06e-123">Extend **Sales Invoice Header V2** and **Sales Invoice Lines V2** in the same way you extended the Common Data Service entities in steps 1 and 2.</span></span> <span data-ttu-id="7b06e-124">Ajoutez ensuite les requêtes de filtre.</span><span class="sxs-lookup"><span data-stu-id="7b06e-124">Then add the filter queries.</span></span> <span data-ttu-id="7b06e-125">La chaîne de filtre pour **En-tête de facture de vente V2** est `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")`.</span><span class="sxs-lookup"><span data-stu-id="7b06e-125">The filter string for **Sales Invoice Header V2** is `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")`.</span></span> <span data-ttu-id="7b06e-126">La chaîne de filtre pour **Lignes de facture de vente V2** est `INTERCOMPANYINVENTTRANSID == ""`.</span><span class="sxs-lookup"><span data-stu-id="7b06e-126">The filter string for **Sales Invoice Lines V2** is `INTERCOMPANYINVENTTRANSID == ""`.</span></span>

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Mapper la mise en lots à la cible, En-têtes de factures client":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="En-têtes de factures client, modifier la requête":::

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="Lignes de factures client, modifier la requête":::

6. <span data-ttu-id="7b06e-130">L’entité **Citations** n’a pas de relation intersociétés.</span><span class="sxs-lookup"><span data-stu-id="7b06e-130">The **Quotations** entity doesn't have an intercompany relationship.</span></span> <span data-ttu-id="7b06e-131">Si quelqu’un crée un devis pour l’un de vos clients intersociétés, vous pouvez placer tous ces clients dans un groupe de clients en utilisant le champ **CustGroup**.</span><span class="sxs-lookup"><span data-stu-id="7b06e-131">If someone creates a quote for one of your intercompany customers, you can put all of these customers in one customer group by using the **CustGroup** field.</span></span>  <span data-ttu-id="7b06e-132">L’en-tête et les lignes peuvent être étendus pour ajouter le champ **CustGroup** puis filtrez pour ne pas inclure ce groupe.</span><span class="sxs-lookup"><span data-stu-id="7b06e-132">Header and lines can be extended to add the **CustGroup** field and then filter to not include this group.</span></span>

    :::image type="content" source="media/filter-cust-group.png" alt-text="Mapper la mise en lots à la cible, En-têtes de devis de vente":::

7. <span data-ttu-id="7b06e-134">Après avoir étendu entité **Devis**, appliquez un filtre avec `CUSTGROUP !=  "<company>"` comme chaîne de requête.</span><span class="sxs-lookup"><span data-stu-id="7b06e-134">After you extent the **Quotations** entity, apply a filter with `CUSTGROUP !=  "<company>"` as the query string.</span></span>

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="En-tête de devis de vente, modifier la requête":::
