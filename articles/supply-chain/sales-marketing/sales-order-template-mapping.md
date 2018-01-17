---
title: "Synchroniser les en-têtes et les lignes de commande client provenant du module Finance and Operations sur Sales"
description: "La rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de commande client entre Microsoft Dynamics 365 for Finance and Operations, Enterprise edition et Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: d7e4c435a3344f6a5d66e1889b633d80cda085eb
ms.contentlocale: fr-fr
ms.lasthandoff: 01/17/2018

---

# <a name="synchronize-sales-order-headers-and-lines-from-finance-and-operations-to-sales"></a><span data-ttu-id="30abb-103">Synchroniser les en-têtes et les lignes de commande client provenant du module Finance and Operations sur Sales</span><span class="sxs-lookup"><span data-stu-id="30abb-103">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="30abb-104">La rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de commande client entre Microsoft Dynamics 365 for Finance and Operations, Enterprise edition et Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="30abb-104">The topic discusses the templates and underlying tasks that are used to synchronize sales order headers and lines from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition to Microsoft Dynamics 365 for Sales.</span></span> 

## <a name="template-and-tasks"></a><span data-ttu-id="30abb-105">Modèle et tâches</span><span class="sxs-lookup"><span data-stu-id="30abb-105">Template and tasks</span></span>

<span data-ttu-id="30abb-106">Les modèles et tâches sous-jacentes suivants sont utilisés pour synchroniser les en-têtes et lignes de commande client entre Finance and Operations et Sales :</span><span class="sxs-lookup"><span data-stu-id="30abb-106">The following templates and underlying tasks are used to synchronize sales order headers and lines from Finance and Operations to Sales:</span></span>

- <span data-ttu-id="30abb-107">**Nom du modèle dans l'intégration des données**</span><span class="sxs-lookup"><span data-stu-id="30abb-107">**Name of template in Data integration**</span></span> 

    - <span data-ttu-id="30abb-108">Commandes client (entre Fin and Ops et Sales)</span><span class="sxs-lookup"><span data-stu-id="30abb-108">Sales Orders (Fin and Ops to Sales)</span></span>
    
- <span data-ttu-id="30abb-109">**Noms des tâches du projet d'intégration de données**</span><span class="sxs-lookup"><span data-stu-id="30abb-109">**Names of tasks in Data integration project**</span></span>

    - <span data-ttu-id="30abb-110">OrderHeader</span><span class="sxs-lookup"><span data-stu-id="30abb-110">OrderHeader</span></span>
    - <span data-ttu-id="30abb-111">OrderLine</span><span class="sxs-lookup"><span data-stu-id="30abb-111">OrderLine</span></span>

<span data-ttu-id="30abb-112">Tâches de synchronisation requises avant l'en-tête et les lignes synchronisation de facture client :</span><span class="sxs-lookup"><span data-stu-id="30abb-112">Sync tasks required prior to Sales invoice header and lines sync:</span></span>

- <span data-ttu-id="30abb-113">Produits (entre Fin and Ops et Sales)</span><span class="sxs-lookup"><span data-stu-id="30abb-113">Products (Fin and Ops to Sales)</span></span>
- <span data-ttu-id="30abb-114">Comptes (Entre Sales et Fin and Ops) (en cas d'utilisation)</span><span class="sxs-lookup"><span data-stu-id="30abb-114">Accounts (Sales to Fin and Ops) (if used)</span></span>
- <span data-ttu-id="30abb-115">Contacts vers Clients (Sales vers Fin and Ops) (en cas d'utilisation)</span><span class="sxs-lookup"><span data-stu-id="30abb-115">Contacts to Customers (Sales to Fin and Ops) (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="30abb-116">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="30abb-116">Entity set</span></span>

| <span data-ttu-id="30abb-117">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="30abb-117">Finance and Operations</span></span> |    <span data-ttu-id="30abb-118">Common Data Service (CDS)</span><span class="sxs-lookup"><span data-stu-id="30abb-118">Common Data Service (CDS)</span></span>         |     <span data-ttu-id="30abb-119">Vente</span><span class="sxs-lookup"><span data-stu-id="30abb-119">Sales</span></span>      |
|------------------------|----------------|----------------|
| <span data-ttu-id="30abb-120">En-têtes de commande client CDS</span><span class="sxs-lookup"><span data-stu-id="30abb-120">CDS sales order headers</span></span>| <span data-ttu-id="30abb-121">SalesOrder</span><span class="sxs-lookup"><span data-stu-id="30abb-121">SalesOrder</span></span>     | <span data-ttu-id="30abb-122">SalesOrders</span><span class="sxs-lookup"><span data-stu-id="30abb-122">SalesOrders</span></span> |
| <span data-ttu-id="30abb-123">Lignes de commande client CDS</span><span class="sxs-lookup"><span data-stu-id="30abb-123">CDS sales order lines</span></span>  | <span data-ttu-id="30abb-124">SalesOrderLine</span><span class="sxs-lookup"><span data-stu-id="30abb-124">SalesOrderLine</span></span> | <span data-ttu-id="30abb-125">SalesOrderDetails</span><span class="sxs-lookup"><span data-stu-id="30abb-125">SalesOrderDetails</span></span>|

## <a name="entity-flow"></a><span data-ttu-id="30abb-126">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="30abb-126">Entity flow</span></span>

<span data-ttu-id="30abb-127">Les commandes client sont créées dans Finance and Operations et synchronisées avec Sales.</span><span class="sxs-lookup"><span data-stu-id="30abb-127">Sales orders are created in Finance and Operations and synchronized to Sales.</span></span>

<span data-ttu-id="30abb-128">Les filtres dans le modèle garantissent que seules les commandes client appropriées sont incluses dans la synchronisation :</span><span class="sxs-lookup"><span data-stu-id="30abb-128">Filters in the template ensure that only relevant sales orders are included in the synchronization:</span></span>

- <span data-ttu-id="30abb-129">La commande et la facturation client sur la commande client provenant de Sales seront incluses dans la synchronisation.</span><span class="sxs-lookup"><span data-stu-id="30abb-129">Both ordering and invoicing customer on the sales order that originate from Sales will be included in the synchronization.</span></span> <span data-ttu-id="30abb-130">Dans Finance and Operations, les champs **OrderingCustomerIsExternallyMaintained** et **InvoiceCustomerIsExternallyMaintained** permettent de suivre la synchronisation dans les entités de données.</span><span class="sxs-lookup"><span data-stu-id="30abb-130">In Finance and Operations, the fields **OrderingCustomerIsExternallyMaintained** and **InvoiceCustomerIsExternallyMaintained** are used to track the synchronization in the data entities.</span></span>

- <span data-ttu-id="30abb-131">La **commande client** dans Finance and Operations doit être confirmée.</span><span class="sxs-lookup"><span data-stu-id="30abb-131">The **Sales order** in Finance and Operations must be confirmed.</span></span> <span data-ttu-id="30abb-132">Seules les commandes client confirmées ou les commandes client dont le statut de traitement le plus élevé, par exemple, Livré ou Facturé, sont synchronisées avec Sales.</span><span class="sxs-lookup"><span data-stu-id="30abb-132">Only the confirmed sales orders or sales orders with higher processing status, for example, Shipped or Invoiced status, are synchronized to Sales.</span></span>

- <span data-ttu-id="30abb-133">Après avoir créé ou modifié une commande client, le traitement par lots **Calcule les totaux de vente** dans Finance and Operations doit être exécuté.</span><span class="sxs-lookup"><span data-stu-id="30abb-133">After creating or modifying a sales order, the batch job **Calculate sales totals** in Finance and Operations must be executed.</span></span> <span data-ttu-id="30abb-134">Seules les commandes client avec des totaux de vente calculés seront synchronisés avec CDS et Sales.</span><span class="sxs-lookup"><span data-stu-id="30abb-134">Only the sales orders with sales totals calculated will be synced to CDS and Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="30abb-135">La taxe associée aux frais dans **En-tête de commande client** n'est actuellement pas incluse dans la synchronisation entre Finance and Operations et Sales.</span><span class="sxs-lookup"><span data-stu-id="30abb-135">Tax related to charges on the **Sales order header** is currently not included in synchronization from Finance and Operations to Sales.</span></span> <span data-ttu-id="30abb-136">En effet, Sales ne prend pas en charge les informations fiscales au niveau de l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="30abb-136">This is because Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="30abb-137">La taxe associée aux frais au niveau de la ligne est incluse.</span><span class="sxs-lookup"><span data-stu-id="30abb-137">Tax related to charges at the line level is included.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="30abb-138">Prospect pour une solution de disponibilités pour Sales</span><span class="sxs-lookup"><span data-stu-id="30abb-138">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="30abb-139">De nouveaux champs sont ajoutés à l'entité **Commande** et s'affichent sur la page :</span><span class="sxs-lookup"><span data-stu-id="30abb-139">New fields are added to the **Order** entity and displayed on the page:</span></span>

- <span data-ttu-id="30abb-140">**Est conservé en externe** - Défini sur **Oui** lorsque la commande provient de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="30abb-140">**Is Maintained Externally** - Set to **Yes** when the order is coming from Finance and Operations.</span></span>

- <span data-ttu-id="30abb-141">**Statut de traitement** - Utilisé pour afficher le statut de traitement de la commande dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="30abb-141">**Processing status** - Used to show the processing status of the order in Finance and Operations.</span></span> <span data-ttu-id="30abb-142">Les valeurs sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="30abb-142">Values are:</span></span>

    - <span data-ttu-id="30abb-143">Active</span><span class="sxs-lookup"><span data-stu-id="30abb-143">Active</span></span>
    - <span data-ttu-id="30abb-144">Confirmée</span><span class="sxs-lookup"><span data-stu-id="30abb-144">Confirmed</span></span>
    - <span data-ttu-id="30abb-145">Bon de livraison</span><span class="sxs-lookup"><span data-stu-id="30abb-145">Packing Slip</span></span>
    - <span data-ttu-id="30abb-146">Facturé</span><span class="sxs-lookup"><span data-stu-id="30abb-146">Invoiced</span></span>
    - <span data-ttu-id="30abb-147">Prélevé</span><span class="sxs-lookup"><span data-stu-id="30abb-147">Picked</span></span>
    - <span data-ttu-id="30abb-148">Partiellement prélevé</span><span class="sxs-lookup"><span data-stu-id="30abb-148">Partially Picked</span></span>
    - <span data-ttu-id="30abb-149">Partiellement emballé</span><span class="sxs-lookup"><span data-stu-id="30abb-149">Partially Packed</span></span>
    - <span data-ttu-id="30abb-150">Expédié</span><span class="sxs-lookup"><span data-stu-id="30abb-150">Shipped</span></span>
    - <span data-ttu-id="30abb-151">Partiellement expédié</span><span class="sxs-lookup"><span data-stu-id="30abb-151">Partially Shipped</span></span>
    - <span data-ttu-id="30abb-152">Partiellement facturé</span><span class="sxs-lookup"><span data-stu-id="30abb-152">Partially Invoiced</span></span>
    - <span data-ttu-id="30abb-153">Annulé</span><span class="sxs-lookup"><span data-stu-id="30abb-153">Cancelled</span></span>

<span data-ttu-id="30abb-154">Le paramètre **Le devis a des produits mis à jour uniquement en externe** est utilisé dans d'autres scénarios de commande client (synchronisation entre Sales et Finance and Operation) pour gérer de façon cohérente si la commande client comprend entièrement les **Produits mis à jour en externe**, dans le cas présent les produits sont gérés dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="30abb-154">The **Has Externally Maintained Products Only** setting is used in other sales order scenarios (from Sales to Finance and Operation sync) to consistently keep track of whether the sales order is made up entirely of **Externally Maintained Products**, in which case products are maintained in Finance and Operations.</span></span> <span data-ttu-id="30abb-155">Cela permet de garantir que vous ne tenterez pas de synchroniser les lignes de commande avec des produits qui sont inconnus de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="30abb-155">This ensures that you don't try to sync sales order lines with products that are unknown to Finance and Operations.</span></span>
 
<span data-ttu-id="30abb-156">Les boutons **Créer une facture**, **Annuler la commande**, **Recalculer**, **Obtenir des produits** et **Adresse de recherche** sur la page **Commande client** sont masqués pour les commandes gérées en externe car les factures sont créées dans Finance and Operations et synchronisées avec Sales.</span><span class="sxs-lookup"><span data-stu-id="30abb-156">The **Create Invoice**, **Cancel Order**, **Recalculate**, **Get Products** and **Lookup Address** buttons on the **Sales order** page are hidden for externally maintained orders because invoices will be created in Finance and Operations and synced to Sales.</span></span> <span data-ttu-id="30abb-157">La page de commande ne peut pas être modifiée car les informations de commande client sont synchronisées à partir de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="30abb-157">The order page is non-editable because sales order information will be synced from Finance and Operations.</span></span>
 
<span data-ttu-id="30abb-158">Le **Statut de la commande client** restera actif pour garantir que les modifications effectuées dans Finance and Operations peuvent être répercutées dans la **Commande client** avec Sales.</span><span class="sxs-lookup"><span data-stu-id="30abb-158">The **Sales order status** will remain active to ensure that changes from Finance and Operations can flow to the **Sales order** in Sales.</span></span> <span data-ttu-id="30abb-159">Cette opération est contrôlée en définissant le paramètre par défaut **Statecode [Statut]** sur **Actif** dans le projet d'intégration de données.</span><span class="sxs-lookup"><span data-stu-id="30abb-159">This is controlled by setting the default **Statecode [Status]** to **Active** in the Data integration project.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="30abb-160">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="30abb-160">Preconditions and mapping setup</span></span> 

<span data-ttu-id="30abb-161">Avant de synchroniser les commandes client, il est important de mettre les systèmes à jour avec le paramètre suivant :</span><span class="sxs-lookup"><span data-stu-id="30abb-161">Before synchronizing sales orders, it is important to update the systems with the following setting:</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="30abb-162">Configuration dans Sales</span><span class="sxs-lookup"><span data-stu-id="30abb-162">Setup in Sales</span></span>

- <span data-ttu-id="30abb-163">Vérifiez les autorisations de l'équipe à laquelle l'utilisateur est affecté (à partir des **paramètres de connexion** dans Sales).</span><span class="sxs-lookup"><span data-stu-id="30abb-163">Ensure permissions for the team that the user (from your Sales **Connection set**) is assigned to.</span></span> <span data-ttu-id="30abb-164">Si vous utilisez des données de démonstration, généralement l'utilisateur dispose de l'accès Administrateur, mais pas l'équipe.</span><span class="sxs-lookup"><span data-stu-id="30abb-164">If you are using demo data, usually the user has admin access, but not the team.</span></span> <span data-ttu-id="30abb-165">Sans cela vous obtiendrez une erreur disant que l'équipe principale est manquante lors de l'exécution du projet depuis l'intégrateur de données.</span><span class="sxs-lookup"><span data-stu-id="30abb-165">Without this you will get an error that Principal team is missing when running the project from Data integrator.</span></span> 

    - <span data-ttu-id="30abb-166">Sous **Paramètres** > **Sécurité** > **Équipes**, sélectionnez l'équipe appropriée, cliquez sur **Gestion des rôles**, puis sélectionnez un rôle avec les autorisations souhaitées, par exemple, celles d'administrateur système.</span><span class="sxs-lookup"><span data-stu-id="30abb-166">Under **Settings** > **Security** > **Teams**, select the relevant team, click **Manage Roles** and select a role with the desired permissions e.g. System Administrator.</span></span>

- <span data-ttu-id="30abb-167">Sous **Paramètres** > **Administration** > **Paramètres système** > **Ventes**, vérifiez que le paramètre **Utiliser le système de calcul du prix du système** est défini sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="30abb-167">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Use system prizing calculation system** is set to **Yes**.</span></span> 

- <span data-ttu-id="30abb-168">Sous **Paramètres** > **Administration** > **Paramètres système** > **Ventes**, vérifiez que **Mode de calcul de remise** est défini sur **Ligne**.</span><span class="sxs-lookup"><span data-stu-id="30abb-168">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Discount calculation method** is set to **Line item**.</span></span> 

### <a name="setup-in-finance-and-operations"></a><span data-ttu-id="30abb-169">Configuration dans Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="30abb-169">Setup in Finance and Operations</span></span>

<span data-ttu-id="30abb-170">Définissez **Ventes et marketing** > **Tâches périodiques** > **Calcule les totaux de vente** pour une exécution en tant que traitement par lots, avec **Calculer les totaux des commandes client** définie sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="30abb-170">Set **Sales and marketing** > **Periodic tasks** > **Calculate sales totals** to run as a batch job, with **Calculate totals for sales orders** set to **Yes**.</span></span> <span data-ttu-id="30abb-171">Cela est important car seules les commandes client avec des totaux de vente calculés seront synchronisés avec CDS et Sales.</span><span class="sxs-lookup"><span data-stu-id="30abb-171">This is important because only the sales orders with sales totals calculated will be synced to CDS and Sales.</span></span> <span data-ttu-id="30abb-172">La fréquence du traitement par lots doit être alignée avec la fréquence de la synchronisation des commandes client.</span><span class="sxs-lookup"><span data-stu-id="30abb-172">The frequency of the batch job should be alligned with the frequency of the sales order synchronization.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="30abb-173">Paramétrage du projet d'intégration des données</span><span class="sxs-lookup"><span data-stu-id="30abb-173">Setup in the Data integration project</span></span>

#### <a name="salesheader-task"></a><span data-ttu-id="30abb-174">Tâche SalesHeader</span><span class="sxs-lookup"><span data-stu-id="30abb-174">SalesHeader task</span></span>

- <span data-ttu-id="30abb-175">Mettez à jour la **Mise en correspondance pour l'ID organisation CDS dans Source** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="30abb-175">Update the mapping for **CDS Organization ID in Source** > **CDS**.</span></span>

    - <span data-ttu-id="30abb-176">Le modèle de valeur par défaut pour **Account_Organization_OrganizationId** est ORG001.</span><span class="sxs-lookup"><span data-stu-id="30abb-176">Default template value for **Account_Organization_OrganizationId** is ORG001.</span></span>
    - <span data-ttu-id="30abb-177">La valeur du modèle par défaut pour **InvoiceAccount_Organization_OrganizationId** est ORG001.</span><span class="sxs-lookup"><span data-stu-id="30abb-177">Default template value for **InvoiceAccount_Organization_OrganizationId** is ORG001.</span></span>
    - <span data-ttu-id="30abb-178">Le modèle de valeur par défaut pour **Organization_OrganizationId** est ORG001.</span><span class="sxs-lookup"><span data-stu-id="30abb-178">Default template value for **Organization_OrganizationId** is ORG001.</span></span>

- <span data-ttu-id="30abb-179">Assurez-vous que la mise en correspondance nécessaire existe dans **Source** > **CDS pour InvoiceCountryRegionId à BillingAddress_Country** et **DeliveryCountryRegionId à DeliveryAddress_Country**.</span><span class="sxs-lookup"><span data-stu-id="30abb-179">Ensure that the needed mapping exists in **Source** > **CDS for InvoiceCountryRegionId to BillingAddress_Country** and for **DeliveryCountryRegionId to DeliveryAddress_Country**.</span></span>

    - <span data-ttu-id="30abb-180">La valeur du modèle est **ValueMap** avec un numéro de pays mis en correspondance.</span><span class="sxs-lookup"><span data-stu-id="30abb-180">Template value is **ValueMap** with a number of countries mapped.</span></span>

- <span data-ttu-id="30abb-181">La **Liste des prix** est requise pour créer des commandes dans Sales.</span><span class="sxs-lookup"><span data-stu-id="30abb-181">**Price list** is required to create orders in Sales.</span></span> <span data-ttu-id="30abb-182">Mettez à jour **ValueMap** dans **CDS** > **Destination** pour **pricelevelid.name [Nom des tarifs]** dans la **Liste des prix** utilisée dans Sales par devise.</span><span class="sxs-lookup"><span data-stu-id="30abb-182">Update the **ValueMap** in **CDS** > **Destination** for **pricelevelid.name [Price List Name]** to the **Price list** used in Sales per currency.</span></span> <span data-ttu-id="30abb-183">Vous pouvez utiliser la **Liste des prix** par défaut pour une seule devise ou utiliser **ValueMap** si vous avez des **Listes de prix** dans plusieurs devises.</span><span class="sxs-lookup"><span data-stu-id="30abb-183">You can either used the default **Price list** for single currency or use **ValueMap** if you have **Price lists** in multiple currencies.</span></span>
    
    - <span data-ttu-id="30abb-184">La valeur de modèle par défaut pour **pricelevelid.name [Nom des tarifs]** est le service CRM USA (exemple).</span><span class="sxs-lookup"><span data-stu-id="30abb-184">Default template value for **pricelevelid.name [Price List Name]** is CRM Service USA (sample).</span></span> 

#### <a name="salesline-task"></a><span data-ttu-id="30abb-185">Tâche SalesLine</span><span class="sxs-lookup"><span data-stu-id="30abb-185">SalesLine task</span></span>

- <span data-ttu-id="30abb-186">Mettez à jour la **Mise en correspondance pour l'ID organisation CDS dans Source** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="30abb-186">Update the mapping for **CDS Organization ID in Source** > **CDS**.</span></span> 
    
    - <span data-ttu-id="30abb-187">La valeur du modèle par défaut pour **SalesOrder_Organization_OrganizationId** est ORG001.</span><span class="sxs-lookup"><span data-stu-id="30abb-187">Default template value for **SalesOrder_Organization_OrganizationId** is ORG001.</span></span>
    - <span data-ttu-id="30abb-188">Le modèle de valeur par défaut pour **Product_Organization_OrganizationId** est ORG001.</span><span class="sxs-lookup"><span data-stu-id="30abb-188">Default template value for **Product_Organization_OrganizationId** is ORG001.</span></span>

- <span data-ttu-id="30abb-189">Assurez-vous que la mise en correspondance nécessaire existe dans **Source** > **CDS** pour **DeliveryCountryRegionId** dans **DeliveryAddress_Country**.</span><span class="sxs-lookup"><span data-stu-id="30abb-189">Ensure that the needed mapping exists in **Source** > **CDS** for **DeliveryCountryRegionId** to **DeliveryAddress_Country**.</span></span>

    - <span data-ttu-id="30abb-190">La valeur du modèle est **ValueMap** avec un numéro de pays mis en correspondance.</span><span class="sxs-lookup"><span data-stu-id="30abb-190">Template value is **ValueMap** with a number of countries mapped.</span></span>
    
- <span data-ttu-id="30abb-191">Assurez-vous que **ValueMap** nécessaire pour **SalesUnitSymbol** dans Finance and Operations existe dans **Source** > **Mise en correspondance CDS**.</span><span class="sxs-lookup"><span data-stu-id="30abb-191">Ensure that the needed **ValueMap** for **SalesUnitSymbol** in Finance and Operations exists in the **Source** > **CDS mapping**.</span></span>

    - <span data-ttu-id="30abb-192">La valeur du modèle avec **ValueMap** est définie sur **SalesUnitSymbol à Quantity_UOM**.</span><span class="sxs-lookup"><span data-stu-id="30abb-192">Template value with **ValueMap** is defined for **SalesUnitSymbol to Quantity_UOM**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="30abb-193">Mise en correspondance de modèles dans l'intégrateur de données</span><span class="sxs-lookup"><span data-stu-id="30abb-193">Template mapping in data integrator</span></span>

> [!NOTE]
> <span data-ttu-id="30abb-194">Les champs **Conditions de paiement**, **Conditions de transport**, **Conditions de livraison**, **Méthode d'expédition** et **Mode de distribution** ne font pas partie des mises en correspondance par défaut.</span><span class="sxs-lookup"><span data-stu-id="30abb-194">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="30abb-195">Pour mettre en correspondance ces champs, vous devez paramétrer une mise en correspondance des valeurs spécifique aux données des organisations entre lesquelles l'entité est synchronisée.</span><span class="sxs-lookup"><span data-stu-id="30abb-195">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="30abb-196">Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l'intégrateur de données.</span><span class="sxs-lookup"><span data-stu-id="30abb-196">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="orderheader"></a><span data-ttu-id="30abb-197">OrderHeader</span><span class="sxs-lookup"><span data-stu-id="30abb-197">OrderHeader</span></span>

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-order-template-mapping-data-integrator-1.png)

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-order-template-mapping-data-integrator-2.png)

### <a name="orderline"></a><span data-ttu-id="30abb-200">OrderLine</span><span class="sxs-lookup"><span data-stu-id="30abb-200">OrderLine</span></span>

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-order-template-mapping-data-integrator-3.png)

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-order-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a><span data-ttu-id="30abb-203">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="30abb-203">Related topics</span></span>

[<span data-ttu-id="30abb-204">Synchronisez les produits de Finance and Operations sur les produits de Sales</span><span class="sxs-lookup"><span data-stu-id="30abb-204">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="30abb-205">Synchroniser les comptes provenant du module Sales sur les clients de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="30abb-205">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="30abb-206">Synchroniser les contacts provenant du module Sales sur les contacts ou clients de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="30abb-206">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="30abb-207">Synchroniser les en-têtes et les lignes de devis de vente provenant du module Sales sur Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="30abb-207">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="30abb-208">Synchroniser les en-têtes et les lignes de facture client provenant du module Finance and Operations sur Sales</span><span class="sxs-lookup"><span data-stu-id="30abb-208">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping.md)


