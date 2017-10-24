---
title: "Synchroniser les en-têtes et les lignes de facture client provenant du module Finance and Operations sur Sales"
description: "La rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de facture client entre Microsoft Dynamics 365 for Finance and Operations, Enterprise edition et Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: fb5ba099911deda5308daf92d82cd6b3489995bf
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="synchronize-sales-invoice-headers-and-lines-from-finance-and-operations-to-sales"></a><span data-ttu-id="44d30-103">Synchroniser les en-têtes et les lignes de facture client provenant du module Finance and Operations sur Sales</span><span class="sxs-lookup"><span data-stu-id="44d30-103">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="44d30-104">La rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de facture client entre Microsoft Dynamics 365 for Finance and Operations, Enterprise edition et Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="44d30-104">The topic discusses the templates and underlying tasks that are used to synchronize sales invoice headers and lines from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition to Microsoft Dynamics 365 for Sales.</span></span> 

## <a name="templates-and-tasks"></a><span data-ttu-id="44d30-105">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="44d30-105">Templates and tasks</span></span>

<span data-ttu-id="44d30-106">Les modèles et tâches sous-jacentes suivants sont utilisés pour synchroniser les en-têtes et lignes de facture client entre Finance and Operations et Sales :</span><span class="sxs-lookup"><span data-stu-id="44d30-106">The following templates and underlying tasks are used to synchronize sales invoice headers and lines from Finance and Operations to Sales:</span></span>

- <span data-ttu-id="44d30-107">**Nom du modèle dans l'intégration des données**</span><span class="sxs-lookup"><span data-stu-id="44d30-107">**Name of the template in Data integration**</span></span> 

     - <span data-ttu-id="44d30-108">Factures client (entre Fin and Ops et Sales)</span><span class="sxs-lookup"><span data-stu-id="44d30-108">Sales Invoices (Fin and Ops to Sales)</span></span>

- <span data-ttu-id="44d30-109">**Noms des tâches dans le projet d'intégration de données**</span><span class="sxs-lookup"><span data-stu-id="44d30-109">**Names of the tasks in the Data integration project**</span></span>

    - <span data-ttu-id="44d30-110">SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="44d30-110">SalesInvoiceHeader</span></span>
    - <span data-ttu-id="44d30-111">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="44d30-111">SalesInvoiceLine</span></span>

<span data-ttu-id="44d30-112">Tâches de synchronisation requises avant l'en-tête et les lignes synchronisation de facture client :</span><span class="sxs-lookup"><span data-stu-id="44d30-112">Sync tasks required prior to Sales invoice header and lines synchronization:</span></span>
-   <span data-ttu-id="44d30-113">Produits (entre Fin and Ops et Sales)</span><span class="sxs-lookup"><span data-stu-id="44d30-113">Products (Fin and Ops to Sales)</span></span>
-   <span data-ttu-id="44d30-114">Comptes (Entre Sales et Fin and Ops) (en cas d'utilisation)</span><span class="sxs-lookup"><span data-stu-id="44d30-114">Accounts (Sales to Fin and Ops) (if used)</span></span>
-   <span data-ttu-id="44d30-115">Contacts (Entre Sales et Fin and Ops) (en cas d'utilisation)</span><span class="sxs-lookup"><span data-stu-id="44d30-115">Contacts (Sales to Fin and Ops) (if used)</span></span>
-   <span data-ttu-id="44d30-116">En-tête et lignes de commande client (Entre Fin and Ops et Sales)</span><span class="sxs-lookup"><span data-stu-id="44d30-116">Sales order header and lines (Fin and Ops to Sales)</span></span>

## <a name="entity-set"></a><span data-ttu-id="44d30-117">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="44d30-117">Entity set</span></span>

| <span data-ttu-id="44d30-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="44d30-118">Finance and Operations</span></span>                               | <span data-ttu-id="44d30-119">Common Data Service (CDS)</span><span class="sxs-lookup"><span data-stu-id="44d30-119">Common Data Service (CDS)</span></span>              | <span data-ttu-id="44d30-120">Vente</span><span class="sxs-lookup"><span data-stu-id="44d30-120">Sales</span></span>          |
|------------------------------------------------------|------------------|----------------|
| <span data-ttu-id="44d30-121">En-têtes de facture de vente client gérée en externe</span><span class="sxs-lookup"><span data-stu-id="44d30-121">Externally maintained customer sales invoice headers</span></span> | <span data-ttu-id="44d30-122">SalesInvoice</span><span class="sxs-lookup"><span data-stu-id="44d30-122">SalesInvoice</span></span>     | <span data-ttu-id="44d30-123">Factures</span><span class="sxs-lookup"><span data-stu-id="44d30-123">Invoices</span></span>       |
| <span data-ttu-id="44d30-124">Lignes de facture de vente client gérée en externe</span><span class="sxs-lookup"><span data-stu-id="44d30-124">Externally maintained customer sales invoice lines</span></span>   | <span data-ttu-id="44d30-125">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="44d30-125">SalesInvoiceLine</span></span> | <span data-ttu-id="44d30-126">InvoiceDetails</span><span class="sxs-lookup"><span data-stu-id="44d30-126">InvoiceDetails</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="44d30-127">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="44d30-127">Entity flow</span></span>

<span data-ttu-id="44d30-128">Les factures client sont créées dans Finance and Operations et synchronisées avec Sales.</span><span class="sxs-lookup"><span data-stu-id="44d30-128">Sales invoices are created in Finance and Operations and synchronized to Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="44d30-129">La taxe associée aux frais dans **En-têtes de facture client** n'est actuellement pas incluse dans la synchronisation entre Finance and Operations et Sales.</span><span class="sxs-lookup"><span data-stu-id="44d30-129">Tax related to charges on the **Sales invoice header** is currently not included in synchronization from Finance and Operations to Sales.</span></span> <span data-ttu-id="44d30-130">En effet, Sales ne prend pas en charge les informations fiscales au niveau de l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="44d30-130">This is because Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="44d30-131">La taxe associée aux frais au niveau de la ligne est incluse.</span><span class="sxs-lookup"><span data-stu-id="44d30-131">Tax related to charges at the line level is included.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="44d30-132">Prospect pour une solution de disponibilités pour Sales</span><span class="sxs-lookup"><span data-stu-id="44d30-132">Prospect to cash solution for Sales</span></span>

-  <span data-ttu-id="44d30-133">Un **Champ de numéro de facture** est ajouté à l'entité **Facture** et apparaît sur la page.</span><span class="sxs-lookup"><span data-stu-id="44d30-133">An **Invoice number field** is added to the **Invoice** entity and displayed on the page.</span></span>
 
-  <span data-ttu-id="44d30-134">Le bouton **Créer une facture** sur la page **Commande client** est masqué car les factures sont créées dans Finance and Operations et synchronisées avec Sales.</span><span class="sxs-lookup"><span data-stu-id="44d30-134">The **Create invoice** button on the **Sales order** page is hidden because invoices will be created in Finance and Operations and synced to Sales.</span></span> <span data-ttu-id="44d30-135">La page **Facture** ne peut pas être modifiée car les factures sont synchronisées à partir de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="44d30-135">The **Invoice** page is non-editable because invoices will be synced from Finance and Operations.</span></span>
 
-  <span data-ttu-id="44d30-136">Le **Statut de la commande client** passe automatiquement à **Facturé** lorsque la facture concernée dans Finance and Operations a été synchronisée avec Sales.</span><span class="sxs-lookup"><span data-stu-id="44d30-136">The **Sales order status** changes automatically to **Invoiced** when the related invoice from Finance and Operations has been  synchronized to Sales.</span></span> <span data-ttu-id="44d30-137">En outre, le propriétaire de la commande client pour laquelle la facture a été créée est désigné propriétaire de la facture.</span><span class="sxs-lookup"><span data-stu-id="44d30-137">Also, the owner of the sales order from which the invoice was created is assigned as the owner of the invoice.</span></span> <span data-ttu-id="44d30-138">Cela donne au propriétaire de la commande client la capacité d'afficher la facture.</span><span class="sxs-lookup"><span data-stu-id="44d30-138">This gives the owner of the sales order the ability to view the invoice.</span></span>
 
## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="44d30-139">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="44d30-139">Preconditions and mapping setup</span></span>

<span data-ttu-id="44d30-140">Avant de synchroniser les factures client, il est important de mettre les systèmes à jour avec le paramètre suivant :</span><span class="sxs-lookup"><span data-stu-id="44d30-140">Before synchronizing sales invoices, it is important to update the systems with the following setting:</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="44d30-141">Configuration dans Sales</span><span class="sxs-lookup"><span data-stu-id="44d30-141">Setup in Sales</span></span>

- <span data-ttu-id="44d30-142">Sous **Paramètres** > **Administration** > **Paramètres système** > **Ventes**, vérifiez que le paramètre **Utiliser le système de calcul du prix du système** est défini sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="44d30-142">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Use system prizing calculation system** is set to **Yes**.</span></span> 

- <span data-ttu-id="44d30-143">Sous **Paramètres** > **Administration** > **Paramètres système** > **Ventes**, vérifiez que **Mode de calcul de remise** est défini sur **Ligne**.</span><span class="sxs-lookup"><span data-stu-id="44d30-143">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Discount calculation method** is set to **Line item**.</span></span> 

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="44d30-144">Paramétrage du projet d'intégration des données</span><span class="sxs-lookup"><span data-stu-id="44d30-144">Setup in the Data integration project</span></span>

#### <a name="salesinvoiceheader-task"></a><span data-ttu-id="44d30-145">Tâche SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="44d30-145">SalesInvoiceHeader task</span></span>

- <span data-ttu-id="44d30-146">Mettez à jour la mise en correspondance pour **ID organisation CDS** dans **Source** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="44d30-146">Update the mapping for **CDS Organization ID** in **Source** > **CDS**.</span></span> 

    -  <span data-ttu-id="44d30-147">La valeur du modèle par défaut pour **SalesOrder_Organization_OrganizationId** est ORG001.</span><span class="sxs-lookup"><span data-stu-id="44d30-147">Default template value for **SalesOrder_Organization_OrganizationId** is ORG001.</span></span>
    -  <span data-ttu-id="44d30-148">Le modèle de valeur par défaut pour **Account_Organization_OrganizationId** est ORG001.</span><span class="sxs-lookup"><span data-stu-id="44d30-148">Default template value for **Account_Organization_OrganizationId** is ORG001.</span></span>
    -  <span data-ttu-id="44d30-149">Le modèle de valeur par défaut pour **Organization_OrganizationId** est ORG001.</span><span class="sxs-lookup"><span data-stu-id="44d30-149">Default template value for **Organization_OrganizationId** is ORG001.</span></span>

- <span data-ttu-id="44d30-150">Assurez-vous que la mise en correspondance nécessaire existe dans **Source** > **CDS pour InvoiceCountryRegionId** dans **BillingAddress_Country**.</span><span class="sxs-lookup"><span data-stu-id="44d30-150">Ensure that the needed mapping exists in **Source** > **CDS for InvoiceCountryRegionId** to **BillingAddress_Country**.</span></span>

    -  <span data-ttu-id="44d30-151">La valeur du modèle est **ValueMap** avec un numéro de pays mis en correspondance.</span><span class="sxs-lookup"><span data-stu-id="44d30-151">Template value is **ValueMap** with a number of countries mapped.</span></span>

- <span data-ttu-id="44d30-152">La **Liste des prix** est requise pour créer des factures dans Sales.</span><span class="sxs-lookup"><span data-stu-id="44d30-152">**Price list** is required to create invoices in Sales.</span></span> <span data-ttu-id="44d30-153">Mettez à jour **ValueMap** dans **CDS** > **Destination pour pricelevelid.name [Nom des tarifs]** dans la **Liste des prix** utilisée dans Sales par devise.</span><span class="sxs-lookup"><span data-stu-id="44d30-153">Update the **ValueMap** in **CDS** > **Destination for pricelevelid.name [Price List Name]** to the **Price list** used in Sales per currency.</span></span> <span data-ttu-id="44d30-154">Vous pouvez utiliser la **Liste des prix** par défaut pour une seule devise ou utiliser **ValueMap** si vous avez des **Listes de prix** dans plusieurs devises.</span><span class="sxs-lookup"><span data-stu-id="44d30-154">You can either use the default **Price list** for single currency or use **ValueMap** if you have **Price lists** in multiple currencies.</span></span>

    -  <span data-ttu-id="44d30-155">La valeur de modèle pour **pricelevelid.name [Nom des tarifs]** est **ValueMap** en fonction de la **Devise**.</span><span class="sxs-lookup"><span data-stu-id="44d30-155">Template value for **pricelevelid.name [Price List Name]** is **ValueMap** based on **Currency**.</span></span>
    -  <span data-ttu-id="44d30-156">usd: CRM Service USA (exemple).</span><span class="sxs-lookup"><span data-stu-id="44d30-156">usd: CRM Service USA (sample).</span></span> 

#### <a name="salesinvoiceline-task"></a><span data-ttu-id="44d30-157">Tâche SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="44d30-157">SalesInvoiceLine task</span></span>

- <span data-ttu-id="44d30-158">Assurez-vous que la mise en correspondance nécessaire existe dans **Source** > **CDS pour l'unité de mesure**.</span><span class="sxs-lookup"><span data-stu-id="44d30-158">Ensure that the needed mapping exists in **Source** > **CDS for Unit of measure**.</span></span>

- <span data-ttu-id="44d30-159">Assurez-vous que **ValueMap** nécessaire pour **SalesUnitSymbol** dans Finance and Operations existe dans **Source** > **Mise en correspondance CDS**.</span><span class="sxs-lookup"><span data-stu-id="44d30-159">Ensure that the needed **ValueMap** for **SalesUnitSymbol** in Finance and Operations exists in the **Source** > **CDS mapping**.</span></span> 
    
    - <span data-ttu-id="44d30-160">La valeur du modèle avec **ValueMap** est définie sur **SalesUnitSymbol à Quantity_UOM**.</span><span class="sxs-lookup"><span data-stu-id="44d30-160">Template value with **ValueMap** is defined for **SalesUnitSymbol to Quantity_UOM**.</span></span>
    
-  <span data-ttu-id="44d30-161">Mettez à jour la **Mise en correspondance pour l'ID organisation CDS dans Source** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="44d30-161">Update the mapping for **CDS Organization ID in Source** > **CDS**.</span></span> 

    -  <span data-ttu-id="44d30-162">La valeur du modèle par défaut pour **SalesInvoicer_Organization_OrganizationId** est ORG001.</span><span class="sxs-lookup"><span data-stu-id="44d30-162">Default template value for **SalesInvoicer_Organization_OrganizationId** is ORG001.</span></span>
    -  <span data-ttu-id="44d30-163">Le modèle de valeur par défaut pour **Product_Organization_OrganizationId** est ORG001.</span><span class="sxs-lookup"><span data-stu-id="44d30-163">Default template value for **Product_Organization_OrganizationId** is ORG001.</span></span>
 
## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="44d30-164">Mise en correspondance de modèles dans l'intégrateur de données</span><span class="sxs-lookup"><span data-stu-id="44d30-164">Template mapping in Data integrator</span></span>

> [!NOTE]
> <span data-ttu-id="44d30-165">Les champs **Conditions de paiement**, **Conditions de transport**, **Conditions de livraison**, **Méthode d'expédition** et **Mode de distribution** ne font pas partie des mises en correspondance par défaut.</span><span class="sxs-lookup"><span data-stu-id="44d30-165">**Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** are not part of the default mappings.</span></span> <span data-ttu-id="44d30-166">La mise en correspondance de ces champs nécessite la mise en place d'un mappage de valeurs, spécifique aux données des organisations entre lesquelles l'entité est synchronisée.</span><span class="sxs-lookup"><span data-stu-id="44d30-166">Mapping of these fields requires value mapping to be set up, which is specific to the data in the organizations between which the entity is synchronized.</span></span>

<span data-ttu-id="44d30-167">Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l'intégrateur de données.</span><span class="sxs-lookup"><span data-stu-id="44d30-167">The following illustrations show an example of a template mapping in data integrator.</span></span>

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-invoice-template-mapping-data-integrator-1.png)

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-invoice-template-mapping-data-integrator-2.png)

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-invoice-template-mapping-data-integrator-3.png)

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-invoice-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a><span data-ttu-id="44d30-172">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="44d30-172">Related topics</span></span>

[<span data-ttu-id="44d30-173">Synchronisez les produits de Finance and Operations sur les produits de Sales</span><span class="sxs-lookup"><span data-stu-id="44d30-173">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="44d30-174">Synchroniser les comptes provenant du module Sales sur les clients de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="44d30-174">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="44d30-175">Synchroniser les contacts provenant du module Sales sur les contacts ou clients de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="44d30-175">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="44d30-176">Synchroniser les en-têtes et les lignes de devis de vente provenant du module Sales sur Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="44d30-176">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="44d30-177">Synchroniser les en-têtes et les lignes de commande client provenant du module Finance and Operations sur Sales</span><span class="sxs-lookup"><span data-stu-id="44d30-177">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>](sales-order-template-mapping.md)


