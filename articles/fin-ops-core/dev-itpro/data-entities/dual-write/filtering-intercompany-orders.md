---
title: Filtrer les commandes intersociétés pour éviter de synchroniser les commandes et les lignes de commande
description: Cette rubrique explique comment filtrer les commandes intersociétés afin que les entités Orders et OrderLines ne soient pas synchronisées.
author: negudava
manager: tfehr
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
ms.openlocfilehash: 9a736c8e93dfa7dbcd0739b52e2da987dcefdc0e
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568100"
---
# <a name="filter-intercompany-orders-to-avoid-syncing-orders-and-orderlines"></a><span data-ttu-id="b5739-103">Filtrer les commandes intersociétés pour éviter de synchroniser les commandes et les lignes de commande</span><span class="sxs-lookup"><span data-stu-id="b5739-103">Filter intercompany orders to avoid syncing Orders and OrderLines</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b5739-104">Vous pouvez filtrer les commandes intersociétés pour éviter de synchroniser les tables **Orders** et **OrderLines**.</span><span class="sxs-lookup"><span data-stu-id="b5739-104">You can filter intercompany orders so that the **Orders** and **OrderLines** tables aren't synced.</span></span> <span data-ttu-id="b5739-105">Dans certains scénarios, les détails de la commande intersociétés ne sont pas nécessaires dans l’application d’engagement client.</span><span class="sxs-lookup"><span data-stu-id="b5739-105">In some scenarios, the intercompany order details aren't required in a customer engagement app.</span></span>

<span data-ttu-id="b5739-106">Chacune des tables Dataverse standard est étendue avec des références à la colonne **IntercompanyOrder** et les mappages à double écriture sont modifiés pour faire référence aux colonnes supplémentaires dans les filtres.</span><span class="sxs-lookup"><span data-stu-id="b5739-106">Each standard Dataverse table is extended through references to the **IntercompanyOrder** column, and the dual-write maps are modified so that they refer to the additional columns in the filters.</span></span> <span data-ttu-id="b5739-107">Par conséquent, les commandes intersociétés ne sont plus synchronisées.</span><span class="sxs-lookup"><span data-stu-id="b5739-107">Therefore, the intercompany orders are no longer synced.</span></span> <span data-ttu-id="b5739-108">Ce processus évite les données inutiles dans l’application d’engagement client.</span><span class="sxs-lookup"><span data-stu-id="b5739-108">This process helps prevent unnecessary data in the customer engagement app.</span></span>

1. <span data-ttu-id="b5739-109">Développez la table **En-têtes de commande client CDS** en ajoutant une référence à la colonne **Commande intersociété**.</span><span class="sxs-lookup"><span data-stu-id="b5739-109">Extend the **CDS Sales Order Headers** table by adding a reference to the **IntercompanyOrder** column.</span></span> <span data-ttu-id="b5739-110">Cette colonne est renseignée uniquement sur les commandes intersociétés.</span><span class="sxs-lookup"><span data-stu-id="b5739-110">This column is filled in only on intercompany orders.</span></span> <span data-ttu-id="b5739-111">La colonne **IntercompanyOrder** est disponible dans la table **SalesTable**.</span><span class="sxs-lookup"><span data-stu-id="b5739-111">The **IntercompanyOrder** column is available in the **SalesTable** table.</span></span>

    :::image type="content" source="media/filter-sales-order-header-field-display.png" alt-text="Mapper la mise en lots à la page cible pour les en-têtes de commande client CDS":::

2. <span data-ttu-id="b5739-113">Une fois **En-têtes de commande client CDS** étendu, la colonne **IntercompanyOrder** est disponible dans le mappage.</span><span class="sxs-lookup"><span data-stu-id="b5739-113">After **CDS Sales Order Headers** is extended, the **IntercompanyOrder** column is available in the mapping.</span></span> <span data-ttu-id="b5739-114">Appliquez un filtre avec `INTERCOMPANYORDER == ""` comme chaîne de requête.</span><span class="sxs-lookup"><span data-stu-id="b5739-114">Apply a filter that has `INTERCOMPANYORDER == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-header.png" alt-text="Modifier la boîte de dialogue pour les en-têtes de commande client CDS":::

3. <span data-ttu-id="b5739-116">Développez la table **Lignes de commande client CDS** en ajoutant une référence à la colonne **IntercompanyInventTransId**.</span><span class="sxs-lookup"><span data-stu-id="b5739-116">Extend the **CDS Sales Order Lines** table by adding a reference to the **IntercompanyInventTransId** column.</span></span> <span data-ttu-id="b5739-117">Cette colonne est renseignée uniquement sur les commandes intersociétés.</span><span class="sxs-lookup"><span data-stu-id="b5739-117">This column is filled in only on intercompany orders.</span></span> <span data-ttu-id="b5739-118">La colonne **InterCompanyInventTransId** est disponible dans la table **SalesLine**.</span><span class="sxs-lookup"><span data-stu-id="b5739-118">The **InterCompanyInventTransId** column is available in the **SalesLine** table.</span></span>

    :::image type="content" source="media/filter-sales-order-line-field-display.png" alt-text="Mapper la mise en lots à la page cible pour les lignes de commande client CDS":::

4. <span data-ttu-id="b5739-120">Une fois **Lignes de commande client CDS** étendu, la colonne **IntercompanyInventTransId** est disponible dans le mappage.</span><span class="sxs-lookup"><span data-stu-id="b5739-120">After **CDS Sales Order Lines** is extended, the **IntercompanyInventTransId** column is available in the mapping.</span></span> <span data-ttu-id="b5739-121">Appliquez un filtre avec `INTERCOMPANYINVENTTRANSID == ""` comme chaîne de requête.</span><span class="sxs-lookup"><span data-stu-id="b5739-121">Apply a filter that has `INTERCOMPANYINVENTTRANSID == ""` as the query string.</span></span>

    :::image type="content" source="media/filter-sales-order-lines.png" alt-text="Modifier la boîte de dialogue pour les lignes de commande client CDS":::

5. <span data-ttu-id="b5739-123">Répétez les étapes 1 et 2 pour développer la table **En-tête de facture de vente V2** et ajoutez une requête de filtre.</span><span class="sxs-lookup"><span data-stu-id="b5739-123">Repeat steps 1 and 2 to extend the **Sales Invoice Header V2** table and add a filter query.</span></span> <span data-ttu-id="b5739-124">Dans ce cas, utilisez `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")` comme chaîne de requête pour le filtre.</span><span class="sxs-lookup"><span data-stu-id="b5739-124">In this case, use `(INTERCOMPANYORDER == "") && (SALESORDERNUMBER != "")` as the query string for the filter.</span></span>

    :::image type="content" source="media/filter-sales-invoice-header-field-display.png" alt-text="Mapper la mise en lots à la page cible pour l’en-tête de facturation client V2":::

    :::image type="content" source="media/filter-sales-invoice-header-filter.png" alt-text="Modifier la boîte de dialogue pour l’en-tête de commande client V2":::

6. <span data-ttu-id="b5739-127">Répétez les étapes 3 et 4 pour développer la table **Lignes de facture de vente V2** et ajoutez une requête de filtre.</span><span class="sxs-lookup"><span data-stu-id="b5739-127">Repeat steps 3 and 4 to extend the **Sales Invoice Lines V2** table and add a filter query.</span></span> <span data-ttu-id="b5739-128">Dans ce cas, utilisez `INTERCOMPANYINVENTTRANSID == ""` comme chaîne de requête pour le filtre.</span><span class="sxs-lookup"><span data-stu-id="b5739-128">In this case, use `INTERCOMPANYINVENTTRANSID == ""` as the query string for the filter.</span></span>

    :::image type="content" source="media/filter-sales-invoice-lines-filter.png" alt-text="Modifier la boîte de dialogue pour les lignes de commande client V2":::

7. <span data-ttu-id="b5739-130">La table **Citations** n’a pas de relation intersociétés.</span><span class="sxs-lookup"><span data-stu-id="b5739-130">The **Quotations** table doesn't have an intercompany relationship.</span></span> <span data-ttu-id="b5739-131">Si quelqu’un crée un devis pour l’un de vos clients intersociétés, vous pouvez utiliser la colonne **CustGroup** pour placer tous ces clients dans un groupe de clients.</span><span class="sxs-lookup"><span data-stu-id="b5739-131">If someone creates a quotation for one of your intercompany customers, you can use the **CustGroup** column to put all those customers into one customer group.</span></span> <span data-ttu-id="b5739-132">Vous pouvez développer l’en-tête et les lignes en ajoutant la colonne **CustGroup**, puis filtrer de sorte que le groupe n’est pas inclus.</span><span class="sxs-lookup"><span data-stu-id="b5739-132">You can extend the header and lines by adding the **CustGroup** column, and then filter so that the group isn't included.</span></span>

    :::image type="content" source="media/filter-cust-group.png" alt-text="Mapper la mise en lots à la page cible pour l’en-tête de devis client CDS":::

8. <span data-ttu-id="b5739-134">Après avoir développé **Devis**, appliquez un filtre avec `CUSTGROUP != "<company>"` comme chaîne de requête.</span><span class="sxs-lookup"><span data-stu-id="b5739-134">After **Quotations** is extended, apply a filter that has `CUSTGROUP != "<company>"` as the query string.</span></span>

    :::image type="content" source="media/filter-cust-group-edit.png" alt-text="Modifier la boîte de dialogue pour l’en-tête de devis client CDS":::


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]