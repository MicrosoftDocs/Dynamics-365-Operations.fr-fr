---
title: Synchroniser les en-têtes et les lignes de facture client provenant directement du module Finance and Operations avec Sales
description: Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de factures commerciales directement depuis Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Sales.
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 70fc842463254b02d812447f93970a9da676057d
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "319498"
---
# <a name="synchronize-sales-invoice-headers-and-lines-directly-from-finance-and-operations-to-sales"></a><span data-ttu-id="58d9c-103">Synchroniser directement les en-têtes et les lignes de facture client entre Finance and Operations et Sales</span><span class="sxs-lookup"><span data-stu-id="58d9c-103">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="58d9c-104">Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de factures commerciales directement depuis Microsoft Dynamics 365 for Finance and Operations vers Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="58d9c-104">This topic discusses the templates and underlying tasks that are used to synchronize sales invoice headers and lines directly from Microsoft Dynamics 365 for Finance and Operations, to Microsoft Dynamics 365 for Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="58d9c-105">Flux de données dans Prospect en disponibilités</span><span class="sxs-lookup"><span data-stu-id="58d9c-105">Data flow in Prospect to cash</span></span>

<span data-ttu-id="58d9c-106">La solution Prospect en disponibilités utilise la fonction d'intégration de données pour synchroniser les données entre plusieurs instances de Finance and Operations et Sales.</span><span class="sxs-lookup"><span data-stu-id="58d9c-106">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="58d9c-107">Les modèles de prospects en disponibilités disponibles avec la fonction d'intégration de données activent le flux de données relatifs aux comptes, contacts, produits, devis de vente, commandes client et factures client entre Finance and Operations et Sales.</span><span class="sxs-lookup"><span data-stu-id="58d9c-107">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="58d9c-108">L'illustration ci-dessous indique comment les données sont synchronisées entre Finance and Operations et Sales.</span><span class="sxs-lookup"><span data-stu-id="58d9c-108">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="58d9c-109">[![Flux de données dans Prospect en disponibilités](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="58d9c-109">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="58d9c-110">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="58d9c-110">Templates and tasks</span></span>

<span data-ttu-id="58d9c-111">Pour accéder à des modèles disponibles, ouvrir [Centre d'administrateur PowerApps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="58d9c-111">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="58d9c-112">Sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner les modèles publics.</span><span class="sxs-lookup"><span data-stu-id="58d9c-112">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="58d9c-113">Les modèles et tâches sous-jacentes suivants sont utilisés pour synchroniser les en-têtes et lignes de facture client entre Finance and Operations et Sales :</span><span class="sxs-lookup"><span data-stu-id="58d9c-113">The following template and underlying tasks are used to synchronize sales invoice headers and lines from Finance and Operations to Sales:</span></span>

- <span data-ttu-id="58d9c-114">**Nom du modèle dans l'intégration des données :** Factures client (entre Fin and Ops et Sales) - Direct</span><span class="sxs-lookup"><span data-stu-id="58d9c-114">**Name of the template in Data integration:** Sales Invoices (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="58d9c-115">**Noms des tâches dans le projet d'intégration de données :**</span><span class="sxs-lookup"><span data-stu-id="58d9c-115">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="58d9c-116">SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="58d9c-116">SalesInvoiceHeader</span></span>
    - <span data-ttu-id="58d9c-117">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="58d9c-117">SalesInvoiceLine</span></span>

<span data-ttu-id="58d9c-118">Les tâches suivantes de synchronisation sont requises avant que la synchronisation des en-têtes et des lignes de factures client puisse avoir lieu :</span><span class="sxs-lookup"><span data-stu-id="58d9c-118">The following synchronization tasks are required before synchronization of sales invoice headers and lines can occur:</span></span>

- <span data-ttu-id="58d9c-119">Produits (entre Fin and Ops et Sales) - Direct</span><span class="sxs-lookup"><span data-stu-id="58d9c-119">Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="58d9c-120">Comptes (entre Sales et Fin and Ops) - Direct (en cas d'utilisation)</span><span class="sxs-lookup"><span data-stu-id="58d9c-120">Accounts (Sales to Fin and Ops) - Direct (if used)</span></span>
- <span data-ttu-id="58d9c-121">Contacts (entre Sales et Fin and Ops) - Direct (en cas d'utilisation)</span><span class="sxs-lookup"><span data-stu-id="58d9c-121">Contacts (Sales to Fin and Ops) - Direct (if used)</span></span>
- <span data-ttu-id="58d9c-122">En-tête et lignes de commande client (entre Fin and Ops et Sales) - Direct</span><span class="sxs-lookup"><span data-stu-id="58d9c-122">Sales order header and lines (Fin and Ops to Sales) - Direct</span></span>

## <a name="entity-set"></a><span data-ttu-id="58d9c-123">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="58d9c-123">Entity set</span></span>

| <span data-ttu-id="58d9c-124">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="58d9c-124">Finance and Operations</span></span>                               | <span data-ttu-id="58d9c-125">Vente</span><span class="sxs-lookup"><span data-stu-id="58d9c-125">Sales</span></span>          |
|------------------------------------------------------|----------------|
| <span data-ttu-id="58d9c-126">En-têtes de facture de vente client gérée en externe</span><span class="sxs-lookup"><span data-stu-id="58d9c-126">Externally maintained customer sales invoice headers</span></span> | <span data-ttu-id="58d9c-127">Factures</span><span class="sxs-lookup"><span data-stu-id="58d9c-127">Invoices</span></span>       |
| <span data-ttu-id="58d9c-128">Lignes de facture de vente client gérée en externe</span><span class="sxs-lookup"><span data-stu-id="58d9c-128">Externally maintained customer sales invoice lines</span></span>   | <span data-ttu-id="58d9c-129">InvoiceDetails</span><span class="sxs-lookup"><span data-stu-id="58d9c-129">InvoiceDetails</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="58d9c-130">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="58d9c-130">Entity flow</span></span>

<span data-ttu-id="58d9c-131">Les factures client sont créées dans Finance and Operations et synchronisées avec Sales.</span><span class="sxs-lookup"><span data-stu-id="58d9c-131">Sales invoices are created in Finance and Operations and synchronized to Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="58d9c-132">Actuellement, la taxe associée aux frais dans l'en-tête de facture client n'est pas incluse dans la synchronisation entre Finance and Operations et Sales.</span><span class="sxs-lookup"><span data-stu-id="58d9c-132">Currently, tax that is related to charges on the sales invoice header isn't included in the synchronization from Finance and Operations to Sales.</span></span> <span data-ttu-id="58d9c-133">Sales ne prend pas en charge les informations fiscales au niveau de l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="58d9c-133">Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="58d9c-134">Toutefois, la taxe associée aux frais au niveau de la ligne est incluse dans la synchronisation.</span><span class="sxs-lookup"><span data-stu-id="58d9c-134">However, tax that is related to charges at the line level is included in the synchronization.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="58d9c-135">Prospect pour une solution de disponibilités pour Sales</span><span class="sxs-lookup"><span data-stu-id="58d9c-135">Prospect to cash solution for Sales</span></span>

- <span data-ttu-id="58d9c-136">Un champ **Numéro de facture** a été ajouté à l'entité **Facture** et apparaît sur la page.</span><span class="sxs-lookup"><span data-stu-id="58d9c-136">An **Invoice number** field has been added to the **Invoice** entity and appears on the page.</span></span>
- <span data-ttu-id="58d9c-137">Le bouton **Créer une facture** sur la page **Commande client** est masqué car les factures sont créées dans Finance and Operations et synchronisées avec Sales.</span><span class="sxs-lookup"><span data-stu-id="58d9c-137">The **Create invoice** button on the **Sales order** page is hidden, because invoices will be created in Finance and Operations and synchronized to Sales.</span></span> <span data-ttu-id="58d9c-138">La page **Facture** ne peut pas être modifiée car les factures sont synchronisées à partir de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="58d9c-138">The **Invoice** page can't be edited, because invoices will be synchronized from Finance and Operations.</span></span>
- <span data-ttu-id="58d9c-139">La valeur **Statut de la commande client** passe automatiquement à **Facturé** lorsque la facture concernée dans Finance and Operations a été synchronisée avec Sales.</span><span class="sxs-lookup"><span data-stu-id="58d9c-139">The **Sales order status** value is automatically changed to **Invoiced** when the related invoice from Finance and Operations has been synchronized to Sales.</span></span> <span data-ttu-id="58d9c-140">En outre, le propriétaire de la commande client pour laquelle la facture a été créée est désigné propriétaire de la facture.</span><span class="sxs-lookup"><span data-stu-id="58d9c-140">Additionally, the owner of the sales order that the invoice was created from is assigned as the owner of the invoice.</span></span> <span data-ttu-id="58d9c-141">Par conséquent, le propriétaire de la commande client peut afficher la facture.</span><span class="sxs-lookup"><span data-stu-id="58d9c-141">Therefore, the owner of the sales order can view the invoice.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="58d9c-142">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="58d9c-142">Preconditions and mapping setup</span></span>

<span data-ttu-id="58d9c-143">Avant de synchroniser les factures client, il est important de mettre les systèmes à jour avec le paramètre suivant :</span><span class="sxs-lookup"><span data-stu-id="58d9c-143">Before you synchronize sales invoices, it's important that you update the following settings in the systems.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="58d9c-144">Configuration dans Sales</span><span class="sxs-lookup"><span data-stu-id="58d9c-144">Setup in Sales</span></span>

<span data-ttu-id="58d9c-145">Allez dans **Paramètres** > **Administration** > **Paramètres système** > **Sales**, et assurez-vous que les paramètres suivants sont utilisés :</span><span class="sxs-lookup"><span data-stu-id="58d9c-145">Go to **Settings** > **Administration** > **System settings** > **Sales**, and make sure that the following settings are used:</span></span>

- <span data-ttu-id="58d9c-146">L'option **Utiliser le système de calcul du prix du système** est définie **Oui**.</span><span class="sxs-lookup"><span data-stu-id="58d9c-146">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
- <span data-ttu-id="58d9c-147">Le champ **Mode de calcul de remise** est défini sur **Ligne article**.</span><span class="sxs-lookup"><span data-stu-id="58d9c-147">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="58d9c-148">Paramétrage du projet d'intégration des données</span><span class="sxs-lookup"><span data-stu-id="58d9c-148">Setup in the Data integration project</span></span>

#### <a name="salesinvoiceheader-task"></a><span data-ttu-id="58d9c-149">Tâche SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="58d9c-149">SalesInvoiceHeader task</span></span>

- <span data-ttu-id="58d9c-150">Assurez-vous que la mise en correspondance nécessaire existe pour **InvoiceCountryRegionId** dans **BillingAddress\_Country**.</span><span class="sxs-lookup"><span data-stu-id="58d9c-150">Make sure that the required mapping exists for **InvoiceCountryRegionId** to **BillingAddress\_Country**.</span></span>

    <span data-ttu-id="58d9c-151">La valeur du modèle est une mise en correspondance des valeurs où plusieurs pays ou régions sont mis en correspondance.</span><span class="sxs-lookup"><span data-stu-id="58d9c-151">The template value is a value map where several countries or regions are mapped.</span></span>

- <span data-ttu-id="58d9c-152">Un tarif est requis pour créer des factures dans Sales.</span><span class="sxs-lookup"><span data-stu-id="58d9c-152">A price list is required in order to create invoices in Sales.</span></span> <span data-ttu-id="58d9c-153">Mettez à jour la mise en correspondance de la valeur pour **pricelevelid.name \[Nom des tarifs\]** sur la liste des prix utilisée dans Sales par devise.</span><span class="sxs-lookup"><span data-stu-id="58d9c-153">Update the value map for **pricelevelid.name \[Price list name\]** to the price list that is used in Sales per currency.</span></span> <span data-ttu-id="58d9c-154">Vous pouvez utiliser le tarif par défaut pour une seule devise.</span><span class="sxs-lookup"><span data-stu-id="58d9c-154">You can use the default price list for a single currency.</span></span> <span data-ttu-id="58d9c-155">Sinon, si vous avez un tarif dans plusieurs devises, vous pouvez utiliser une mise en correspondance des valeurs.</span><span class="sxs-lookup"><span data-stu-id="58d9c-155">Alternatively, if you have price lists in multiple currencies, you can use a value map.</span></span>

    <span data-ttu-id="58d9c-156">La valeur de modèle pour **pricelevelid.name \[Nom des tarifs\]** est une mise en correspondance des valeurs basée sur la devise avec USD = CRM Service USA (exemple).</span><span class="sxs-lookup"><span data-stu-id="58d9c-156">The template value for **pricelevelid.name \[Price list name\]** is a value map that is based on currency with USD = CRM Service USA (sample).</span></span>  
    
#### <a name="salesinvoiceline-task"></a><span data-ttu-id="58d9c-157">Tâche SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="58d9c-157">SalesInvoiceLine task</span></span>

- <span data-ttu-id="58d9c-158">Assurez-vous que la mise en correspondance nécessaire existe pour **Unité de mesure**.</span><span class="sxs-lookup"><span data-stu-id="58d9c-158">Make sure that the required mapping exists for **Unit of measure**.</span></span>
- <span data-ttu-id="58d9c-159">Assurez-vous que la mise en correspondance des valeurs requise pour **SalesUnitSymbol** dans Finance and Operations existe.</span><span class="sxs-lookup"><span data-stu-id="58d9c-159">Make sure that the required value map for **SalesUnitSymbol** in Finance and Operations exists.</span></span>

    <span data-ttu-id="58d9c-160">Une valeur de modèle ayant une mise en correspondance des valeurs est définie pour **SalesUnitSymbol** sur **Quantité\_UOM**.</span><span class="sxs-lookup"><span data-stu-id="58d9c-160">A template value that has a value map is defined for **SalesUnitSymbol** to **Quantity\_UOM**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="58d9c-161">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="58d9c-161">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="58d9c-162">Les champs **Conditions de paiement**, **Conditions de transport**, **Conditions de livraison**, **Méthode d'expédition** et **Mode de distribution** ne sont pas inclus dans les mises en correspondance par défaut.</span><span class="sxs-lookup"><span data-stu-id="58d9c-162">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="58d9c-163">Pour mettre en correspondance ces champs, vous devez paramétrer une mise en correspondance des valeurs spécifique aux données des organisations entre lesquelles l'entité est synchronisée.</span><span class="sxs-lookup"><span data-stu-id="58d9c-163">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="58d9c-164">Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l'intégration de données.</span><span class="sxs-lookup"><span data-stu-id="58d9c-164">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="58d9c-165">La mise en correspondance indique quelles informations du champ sont synchronisées entre Sales et Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="58d9c-165">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

### <a name="salesinvoiceheader"></a><span data-ttu-id="58d9c-166">SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="58d9c-166">SalesInvoiceHeader</span></span>

![Mise en correspondance de modèles dans l'intégration de données](./media/sales-invoice-direct-template-mapping-data-integrator-1.png)

### <a name="salesinvoiceline"></a><span data-ttu-id="58d9c-168">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="58d9c-168">SalesInvoiceLine</span></span>

![Mise en correspondance de modèles dans l'intégration de données](./media/sales-invoice-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a><span data-ttu-id="58d9c-170">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="58d9c-170">Related topics</span></span>

[<span data-ttu-id="58d9c-171">Prospect en disponibilités</span><span class="sxs-lookup"><span data-stu-id="58d9c-171">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="58d9c-172">Synchroniser directement les comptes provenant du module Sales sur les clients de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="58d9c-172">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="58d9c-173">Synchroniser directement les produits provenant de Finance and Operations sur les produits du module Sales</span><span class="sxs-lookup"><span data-stu-id="58d9c-173">Synchronize products directly from Finance and Operations to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="58d9c-174">Synchroniser directement les contacts provenant du module Sales sur les contacts ou clients de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="58d9c-174">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="58d9c-175">Synchroniser les en-têtes et les lignes de commande client directement entre le module Finance and Operations et Sales</span><span class="sxs-lookup"><span data-stu-id="58d9c-175">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct-two-ways.md)






