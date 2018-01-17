---
title: "Synchroniser les en-têtes et les lignes de devis de vente provenant du module Sales sur Finance and Operations"
description: "La rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de devis entre Microsoft Dynamics 365 for Sales et Microsoft Dynamics 365 for Finance and Operations, édition Entreprise."
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
ms.openlocfilehash: d34c808bce5b61b528f50224e3a72590476d8e55
ms.contentlocale: fr-fr
ms.lasthandoff: 01/17/2018

---

# <a name="synchronize-sales-quotation-headers-and-lines-from-sales-to-finance-and-operations"></a><span data-ttu-id="ba4d5-103">Synchroniser les en-têtes et les lignes de devis de vente provenant du module Sales sur Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ba4d5-103">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="ba4d5-104">Avant d'utiliser le prospect pour une solution de disponibilités, vous devez connaître [Intégration de données Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="ba4d5-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="ba4d5-105">La rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de devis entre Microsoft Dynamics 365 for Sales (Sales) et Microsoft Dynamics 365 for Finance and Operations, édition Entreprise (Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="ba4d5-105">The topic discusses the templates and underlying tasks that are used to synchronize sales quotation headers and lines from Microsoft Dynamics 365 for Sales (Sales) to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span></span> 

## <a name="template-and-tasks"></a><span data-ttu-id="ba4d5-106">Modèle et tâches</span><span class="sxs-lookup"><span data-stu-id="ba4d5-106">Template and tasks</span></span>

<span data-ttu-id="ba4d5-107">Les modèles et tâches sous-jacentes suivants sont utilisés pour synchroniser les en-têtes et lignes de devis entre Sales et Finance and Operations :</span><span class="sxs-lookup"><span data-stu-id="ba4d5-107">The following templates and underlying tasks are used to synchronize sales quotation headers and lines from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="ba4d5-108">**Nom du modèle :** Devis de vente (Sales vers Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="ba4d5-108">**Name of the template:** Sales Quotes (Sales to Fin and Ops)</span></span>
- <span data-ttu-id="ba4d5-109">**Noms des tâches du projet :**</span><span class="sxs-lookup"><span data-stu-id="ba4d5-109">**Names of the tasks in the project:**</span></span>

    - <span data-ttu-id="ba4d5-110">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="ba4d5-110">QuoteHeader</span></span>
    - <span data-ttu-id="ba4d5-111">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="ba4d5-111">QuoteLine</span></span>

<span data-ttu-id="ba4d5-112">Les tâches suivantes de synchronisation sont requises avant que la synchronisation des en-têtes et des lignes de devis puisse être entreprise :</span><span class="sxs-lookup"><span data-stu-id="ba4d5-112">The following synchronization tasks are required before synchronization of sales quotation headers and lines can occur:</span></span>

- <span data-ttu-id="ba4d5-113">Produits (entre Fin and Ops et Sales)</span><span class="sxs-lookup"><span data-stu-id="ba4d5-113">Products (Fin and Ops to Sales)</span></span>
- <span data-ttu-id="ba4d5-114">Comptes (Entre Sales et Fin and Ops) (en cas d'utilisation)</span><span class="sxs-lookup"><span data-stu-id="ba4d5-114">Accounts (Sales to Fin and Ops) (if used)</span></span>
- <span data-ttu-id="ba4d5-115">Contacts vers Clients (Sales vers Fin and Ops) (en cas d'utilisation)</span><span class="sxs-lookup"><span data-stu-id="ba4d5-115">Contacts to Customers (Sales to Fin and Ops) (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="ba4d5-116">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="ba4d5-116">Entity set</span></span>

| <span data-ttu-id="ba4d5-117">Vente</span><span class="sxs-lookup"><span data-stu-id="ba4d5-117">Sales</span></span>        | <span data-ttu-id="ba4d5-118">CDS</span><span class="sxs-lookup"><span data-stu-id="ba4d5-118">CDS</span></span>           | <span data-ttu-id="ba4d5-119">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ba4d5-119">Finance and Operations</span></span>    |
|--------------|---------------|---------------------------|
| <span data-ttu-id="ba4d5-120">Citations</span><span class="sxs-lookup"><span data-stu-id="ba4d5-120">Quotes</span></span>       | <span data-ttu-id="ba4d5-121">Devis</span><span class="sxs-lookup"><span data-stu-id="ba4d5-121">Quotation</span></span>     | <span data-ttu-id="ba4d5-122">En-têtes de devis de vente</span><span class="sxs-lookup"><span data-stu-id="ba4d5-122">Sales quotation headers</span></span>   |
| <span data-ttu-id="ba4d5-123">QuoteDetails</span><span class="sxs-lookup"><span data-stu-id="ba4d5-123">QuoteDetails</span></span> | <span data-ttu-id="ba4d5-124">QuotationLine</span><span class="sxs-lookup"><span data-stu-id="ba4d5-124">QuotationLine</span></span> | <span data-ttu-id="ba4d5-125">Lignes de devis de vente CDS</span><span class="sxs-lookup"><span data-stu-id="ba4d5-125">CDS sales quotation lines</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="ba4d5-126">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="ba4d5-126">Entity flow</span></span>

<span data-ttu-id="ba4d5-127">Les devis sont créés dans Sales et synchronisés avec Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-127">Sales quotations are created in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="ba4d5-128">Les devis sont synchronisés uniquement dans Sales si les conditions suivantes sont réunies :</span><span class="sxs-lookup"><span data-stu-id="ba4d5-128">Sales quotations from Sales are synchronized only if the following conditions are met:</span></span>

- <span data-ttu-id="ba4d5-129">Tous les produits sur les lignes de devis sont mis à jour en externe.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-129">All products on the sales quotation lines are externally maintained.</span></span>
- <span data-ttu-id="ba4d5-130">Le devis est actif ou activé.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-130">The sales quotation is active or activated.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="ba4d5-131">Prospect pour une solution de disponibilités pour Sales</span><span class="sxs-lookup"><span data-stu-id="ba4d5-131">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="ba4d5-132">Le champ **A des produits mis à jour en externe uniquement** a été ajouté à l'entité de devis pour effectuer le suivi uniformément si le devis consiste entièrement en produits mis à jour en externe.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-132">The **Has Externally Maintained Products Only** field has been added to the Quote entity to consistently track whether the sales quotation consists entirely of externally maintained products.</span></span> <span data-ttu-id="ba4d5-133">Si un devis comporte uniquement des produits mis à jour en externe, les produits sont mis à jour dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-133">If a sales quotation has only externally maintained products, the products are maintained in Finance and Operations.</span></span> <span data-ttu-id="ba4d5-134">Ceci permet de garantir que vous ne tenterez pas de synchroniser les lignes de devis avec des produits qui sont inconnus de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-134">This behavior helps guarantee that you don't try to synchronize sales quotation lines with products that are unknown to Finance and Operations.</span></span>

<span data-ttu-id="ba4d5-135">Tous les produits et lignes du devis sont mis à jour avec les informations **A des produits mis à jour uniquement en externe** de l'en-tête du devis.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-135">All products and lines on the quotation are updated with the **Has Externally Maintained Products Only** information from the quotation header.</span></span> <span data-ttu-id="ba4d5-136">Ces informations figurent dans le champ **Le devis a des produits mis à jour uniquement en externe** sur l'entité ligne de devis.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-136">This information can be found in the **Quote Has Externally Maintained Products Only** field on the Quote line entity.</span></span>

<span data-ttu-id="ba4d5-137">Les champs **Remise**, **Frais** et **Taxe** sont contrôlés par un paramétrage complexe dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-137">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="ba4d5-138">Ce paramétrage ne prend pas en charge actuellement la mise en correspondance d'intégration.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-138">This setup doesn't currently support integration mapping.</span></span> <span data-ttu-id="ba4d5-139">Dans la conception actuelle, les champs **Prix**, **Remise**, **Charge**, et **Taxe** sont maîtrisé et gérés par Finances and Operations.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-139">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are mastered and handled by Finance and Operations.</span></span>

<span data-ttu-id="ba4d5-140">Dans Sales, la solution rend les champs suivants en lecture seule, car les valeurs ne sont pas synchronisées avec Finance and Operations :</span><span class="sxs-lookup"><span data-stu-id="ba4d5-140">In Sales, the solution makes the following fields read-only, because the values aren't synchronized to Finance and Operations:</span></span>

- <span data-ttu-id="ba4d5-141">**Champs en lecture seule sur l'en-tête de devis :** % de remise, Remise, volume de transport</span><span class="sxs-lookup"><span data-stu-id="ba4d5-141">**Read-only fields on the sales quotation header:** Discount %, Discount, Freight Amount</span></span>
- <span data-ttu-id="ba4d5-142">**Champs en lecture seule sur les lignes de devis :** Taxe</span><span class="sxs-lookup"><span data-stu-id="ba4d5-142">**Read-only fields on sales quotation lines:** Tax</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="ba4d5-143">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="ba4d5-143">Preconditions and mapping setup</span></span>

<span data-ttu-id="ba4d5-144">Avant de synchroniser les commandes client, il est important de mettre les systèmes à jour avec le paramètre suivant :</span><span class="sxs-lookup"><span data-stu-id="ba4d5-144">Before synchronizing sales orders, it is important to update the systems with the following setting:</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="ba4d5-145">Configuration dans Sales</span><span class="sxs-lookup"><span data-stu-id="ba4d5-145">Setup in Sales</span></span>

- <span data-ttu-id="ba4d5-146">Accédez à **Paramètres** &gt; **Administration** &gt; **Paramètres système** &gt; **Ventes** et vérifiez que le champ **Mode de calcul de remise** est défini sur **Par unité**.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-146">Go to **Settings** &gt; **Administration** &gt; **System settings** &gt; **Sales**, and make sure that the **Discount calculation method** field is set to **Per unit**.</span></span> <span data-ttu-id="ba4d5-147">Ce paramètre permet de garantir que la remise de l'article de ligne dans Sales correspond au paramètre de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-147">This setting helps guarantee that the line item discount from Sales matches the setting in Finance and Operations.</span></span> <span data-ttu-id="ba4d5-148">Sinon, la remise ne sera pas correcte dans Finance and Operations, car Finance and Operations lira la remise comme une remise par unité, même s'il s'agit d'une remise par ligne dans Sales.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-148">Otherwise, the discount won't be correct in Finance and Operations, because Finance and Operations will read the discount as a per-unit discount even if it was a per-line discount in Sales.</span></span>

### <a name="setup-in-finance-and-operations"></a><span data-ttu-id="ba4d5-149">Configuration dans Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ba4d5-149">Setup in Finance and Operations</span></span>

- <span data-ttu-id="ba4d5-150">Accédez à **Comptabilité client** &gt; **Configuration** &gt; **Paramètres de la comptabilité client**.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-150">Go to **Accounts receivable** &gt; **Setup** &gt; **Account receivable parameters**.</span></span> <span data-ttu-id="ba4d5-151">Dans l'onglet **Souche de numéros**, sélectionnez la souche de numéros pour les devis, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-151">On the **Number sequence** tab, select the number sequence for sales quotations, and then click **View details**.</span></span> <span data-ttu-id="ba4d5-152">Ensuite, sous **Paramétrage général**, définissez le champ **Manuel** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-152">Then, under **General Setup**, set the **Manual** field to **Yes**.</span></span>
- <span data-ttu-id="ba4d5-153">Accédez à **Comptabilité client** &gt; **Configuration** &gt; **Paramètres de la comptabilité client**.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-153">Go to **Accounts receivable** &gt; **Setup** &gt; **Accounts receivable parameters**.</span></span> <span data-ttu-id="ba4d5-154">Puis, dans l'onglet **Expéditions**, définissez le champ **Vérification de la date de livraison** sur **Aucun**.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-154">Then, on the **Shipments** tab, set the **Delivery date control** field to **None**.</span></span> <span data-ttu-id="ba4d5-155">Ce paramètre permet d'empêcher la synchronisation d'échouer pour les devis.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-155">This setting helps prevent synchronization from failing for sales quotations.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="ba4d5-156">Paramétrage du projet d'intégration des données</span><span class="sxs-lookup"><span data-stu-id="ba4d5-156">Setup in the Data integration project</span></span>

#### <a name="quoteheader"></a><span data-ttu-id="ba4d5-157">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="ba4d5-157">QuoteHeader</span></span>

- <span data-ttu-id="ba4d5-158">Le champ **Date de livraison demandée** est requis dans Finance and Operations, et la synchronisation échoue si le champ est laissé vide.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-158">The **Requested delivery date** field is required in Finance and Operations, and synchronization will fail if the field is left blank.</span></span> <span data-ttu-id="ba4d5-159">Pour éviter ce problème, si le champ est vide, une date par défaut est issue de **Source &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-159">To prevent this issue, if the field is blank, a default date is taken from **Source &gt; CDS**.</span></span> <span data-ttu-id="ba4d5-160">La date doit être mise à jour avec une valeur recommandée.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-160">The date should be updated to a preferred value.</span></span> <span data-ttu-id="ba4d5-161">Actuellement, vous ne pouvez pas entrer de valeur comme **Aujourd'hui** pour représenter la date du jour.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-161">Currently, you can't enter a value such as **Today** to represent today's date.</span></span> <span data-ttu-id="ba4d5-162">Vous devez entrer une date spécifique.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-162">You must enter a specific date.</span></span> <span data-ttu-id="ba4d5-163">Le modèle de valeur par défaut pour **Date de livraison demandée** est **1/1/2020**.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-163">The default template value for **Requested delivery date** is **1/1/2020**.</span></span>
- <span data-ttu-id="ba4d5-164">Le champ **Adresse Pays Région Code** est requis dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-164">The **Address Country region code** field is required in Finance and Operations.</span></span> <span data-ttu-id="ba4d5-165">Pour empêcher les erreurs de synchronisation, vous pouvez spécifier une valeur par défaut utilisée si le champ est laissé vide dans Sales.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-165">To help prevent synchronization errors, you can specify a default value that is used if the field is left blank in Sales.</span></span> <span data-ttu-id="ba4d5-166">Cette valeur par défaut est également utile, car vous ne devez pas entrer manuellement de valeur dans le champ **Pays/Région** pour les adresses locales.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-166">This default value is also useful, because you don't have to manually enter a value in the **Country region** field for local addresses.</span></span> <span data-ttu-id="ba4d5-167">Il n'existe aucun modèle de valeur par défaut pour **DeliveryAddressCountryRegionISOCode**.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-167">There is no default template value for **DeliveryAddressCountryRegionISOCode**.</span></span>
- <span data-ttu-id="ba4d5-168">Mettez la mise en correspondance à jour pour **ID organisation CDS** dans **Source &gt; CDS** afin qu'elle corresponde à **Organisation CDS** dans l'entité Organisation :</span><span class="sxs-lookup"><span data-stu-id="ba4d5-168">Update the mapping for **CDS Organization ID** in **Source &gt; CDS** so that it matches **CDS organization** in the Organization entity:</span></span>

    - <span data-ttu-id="ba4d5-169">Le modèle de valeur par défaut pour **Organization_OrganizationId** est **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-169">The default template value for **Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="ba4d5-170">Le modèle de valeur par défaut pour **Account_Organization_OrganizationId** est **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-170">The default template value for **Account_Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="ba4d5-171">Le modèle de valeur par défaut pour **InvoiceAccount_OrganizationId** est **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-171">The default template value for **InvoiceAccount_OrganizationId** is **ORG001**.</span></span>

#### <a name="quoteline"></a><span data-ttu-id="ba4d5-172">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="ba4d5-172">QuoteLine</span></span>

- <span data-ttu-id="ba4d5-173">Mettez la mise en correspondance à jour pour **ID organisation CDS** dans **Source &gt; CDS** afin qu'elle corresponde à **Organisation CDS** dans l'entité Organisation :</span><span class="sxs-lookup"><span data-stu-id="ba4d5-173">Update the mapping for **CDS Organization ID** in **Source &gt; CDS** so that it matches **CDS organization** in the Organization entity:</span></span>

    - <span data-ttu-id="ba4d5-174">Le modèle de valeur par défaut pour **Organization_OrganizationId** est **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-174">The default template value for **Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="ba4d5-175">La valeur par défaut du modèle pour **Product_Organization_Organization_OrganizationId** est **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-175">The default template value for **Product_Organization_Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="ba4d5-176">La valeur par défaut du modèle pour **Quotation_Organization_Organization_OrganizationId** est **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-176">The default template value for **Quotation_Organization_Organization_OrganizationId** is **ORG001**.</span></span>

- <span data-ttu-id="ba4d5-177">Le champ **Date de livraison demandée** est requis dans Finance and Operations, et la synchronisation échoue si le champ est laissé vide.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-177">The **Requested delivery date** field is required in Finance and Operations, and synchronization will fail if the field is left blank.</span></span> <span data-ttu-id="ba4d5-178">Pour éviter ce problème, si le champ est vide, une date par défaut est issue de **Source &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-178">To prevent this issue, if the field is blank, a default date is taken from **Source &gt; CDS**.</span></span> <span data-ttu-id="ba4d5-179">La date doit être mise à jour avec une valeur recommandée.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-179">The date should be updated to a preferred value.</span></span> <span data-ttu-id="ba4d5-180">Actuellement, vous ne pouvez pas entrer de valeur comme **Aujourd'hui** pour représenter la date du jour.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-180">Currently, you can't enter a value such as **Today** to represent today's date.</span></span> <span data-ttu-id="ba4d5-181">Vous devez entrer une date spécifique.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-181">You must enter a specific date.</span></span> <span data-ttu-id="ba4d5-182">Le modèle de valeur par défaut pour **Date de livraison demandée** est **1/1/2020**.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-182">The default template value for **Requested delivery date** is **1/1/2020**.</span></span>
- <span data-ttu-id="ba4d5-183">Vous pouvez ajouter les mises en correspondance suivantes de **CDS &gt; Destination** pour vérifier que les lignes de devis sont importées dans Finances and Operations s'il n'existe aucune information par défaut du client ou du produit :</span><span class="sxs-lookup"><span data-stu-id="ba4d5-183">You can add the following mappings from **CDS &gt; Destination** to help guarantee that quotation lines are imported into Finance and Operations if there is no default information from either the customer or the product:</span></span>

    - <span data-ttu-id="ba4d5-184">**SiteId** – Un site est requis pour générer des lignes de devis et de commande client dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-184">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="ba4d5-185">Il n'existe aucun modèle de valeur par défaut pour **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-185">There is no default template value for **SiteId**.</span></span>
    - <span data-ttu-id="ba4d5-186">**WarehouseId** – Un entrepôt est requis pour traiter des lignes de devis et de commande client dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-186">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="ba4d5-187">Il n'existe aucun modèle de valeur par défaut pour **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-187">There is no default template value for **WarehouseId**.</span></span>

- <span data-ttu-id="ba4d5-188">Assurez-vous que la mise en correspondance des valeurs requise pour l'unité de mesure de vente (UOM) dans Finance and Operations existe dans la mise en correspondance **CDS &gt; Destination** pour **Quantity_UOM** vers **SALESUNITSYMBOL**.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-188">Make sure that the required value map for the selling unit of measure (UOM) in Finance and Operations exists in the **CDS &gt; Destination** mapping for **Quantity_UOM** to **SALESUNITSYMBOL**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="ba4d5-189">Mise en correspondance de modèles dans l'intégrateur de données</span><span class="sxs-lookup"><span data-stu-id="ba4d5-189">Template mapping in data integrator</span></span>

> [!NOTE]
> - <span data-ttu-id="ba4d5-190">Les champs **Remise**, **Frais** et **Taxe** sont contrôlés par un paramétrage complexe dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-190">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="ba4d5-191">Ce paramétrage ne prend pas en charge actuellement la mise en correspondance d'intégration.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-191">This setup doesn't currently support integration mapping.</span></span> <span data-ttu-id="ba4d5-192">Dans la conception actuelle, les champs **Prix**, **Remise**, **Charge**, et **Taxe** sont gérés par Finances and Operations.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-192">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are handled by Finance and Operations.</span></span>
> - <span data-ttu-id="ba4d5-193">Les champs **Conditions de paiement**, **Conditions de transport**, **Conditions de livraison**, **Méthode d'expédition** et **Mode de distribution** ne font pas partie des mises en correspondance par défaut.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-193">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="ba4d5-194">Pour mettre en correspondance ces champs, vous devez paramétrer une mise en correspondance des valeurs spécifique aux données des organisations entre lesquelles l'entité est synchronisée.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-194">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="ba4d5-195">Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l'intégrateur de données.</span><span class="sxs-lookup"><span data-stu-id="ba4d5-195">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="ba4d5-196">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="ba4d5-196">QuoteHeader</span></span>

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-quotation-template-mapping-data-integrator-1.png)

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-quotation-template-mapping-data-integrator-2.png)

### <a name="quoteline"></a><span data-ttu-id="ba4d5-199">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="ba4d5-199">QuoteLine</span></span>

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-quotation-template-mapping-data-integrator-3.png)

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-quotation-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a><span data-ttu-id="ba4d5-202">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="ba4d5-202">Related topics</span></span>

[<span data-ttu-id="ba4d5-203">Synchronisez les produits de Finance and Operations sur les produits de Sales</span><span class="sxs-lookup"><span data-stu-id="ba4d5-203">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="ba4d5-204">Synchroniser les comptes provenant du module Sales sur les clients de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ba4d5-204">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="ba4d5-205">Synchronisez les Contacts de Sales sur les contacts ou clients de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ba4d5-205">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)



