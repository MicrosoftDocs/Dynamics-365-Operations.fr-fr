---
title: "Synchroniser les en-têtes et les lignes de devis de vente provenant du module Sales sur Finance and Operations"
description: "La rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de devis entre Microsoft Dynamics 365 for Sales et Microsoft Dynamics 365 for Finance and Operations, édition Entreprise."
author: ChristianRytt
manager: AnnBe
ms.date: 07/03/2017
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
ms.author: ChristianRytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 172a3da1b6d90a25ea9ebd14265e70e4a6f9bd70
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---

# <a name="synchronize-sales-quotation-headers-and-lines-from-sales-to-finance-and-operations"></a><span data-ttu-id="35bcf-103">Synchroniser les en-têtes et les lignes de devis de vente provenant du module Sales sur Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="35bcf-103">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="35bcf-104">Avant d'utiliser le prospect pour une solution de disponibilités, vous devez connaître [Intégration de données Dynamics 365](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="35bcf-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="35bcf-105">La rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de devis entre Microsoft Dynamics 365 for Sales (Sales) et Microsoft Dynamics 365 for Finance and Operations, édition Entreprise (Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="35bcf-105">The topic discusses the templates and underlying tasks that are used to synchronize sales quotation headers and lines from Microsoft Dynamics 365 for Sales (Sales) to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span></span> 

## <a name="template-and-tasks"></a><span data-ttu-id="35bcf-106">Modèle et tâches</span><span class="sxs-lookup"><span data-stu-id="35bcf-106">Template and tasks</span></span>

<span data-ttu-id="35bcf-107">Les modèles et tâches sous-jacentes suivants sont utilisés pour synchroniser les en-têtes et lignes de devis entre Sales et Finance and Operations :</span><span class="sxs-lookup"><span data-stu-id="35bcf-107">The following templates and underlying tasks are used to synchronize sales quotation headers and lines from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="35bcf-108">**Nom du modèle :** Devis de vente (Sales vers Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="35bcf-108">**Name of the template:** Sales Quotes (Sales to Fin and Ops)</span></span>
- <span data-ttu-id="35bcf-109">**Noms des tâches du projet :**</span><span class="sxs-lookup"><span data-stu-id="35bcf-109">**Names of the tasks in the project:**</span></span>

    - <span data-ttu-id="35bcf-110">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="35bcf-110">QuoteHeader</span></span>
    - <span data-ttu-id="35bcf-111">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="35bcf-111">QuoteLine</span></span>

<span data-ttu-id="35bcf-112">Les tâches suivantes de synchronisation sont requises avant que la synchronisation des en-têtes et des lignes de devis puisse être entreprise :</span><span class="sxs-lookup"><span data-stu-id="35bcf-112">The following synchronization tasks are required before synchronization of sales quotation headers and lines can occur:</span></span>

- <span data-ttu-id="35bcf-113">Produits</span><span class="sxs-lookup"><span data-stu-id="35bcf-113">Products</span></span>
- <span data-ttu-id="35bcf-114">Comptes (le cas échéant)</span><span class="sxs-lookup"><span data-stu-id="35bcf-114">Accounts (if used)</span></span>
- <span data-ttu-id="35bcf-115">Contacts (le cas échéant)</span><span class="sxs-lookup"><span data-stu-id="35bcf-115">Contacts (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="35bcf-116">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="35bcf-116">Entity set</span></span>

| <span data-ttu-id="35bcf-117">Vente</span><span class="sxs-lookup"><span data-stu-id="35bcf-117">Sales</span></span>        | <span data-ttu-id="35bcf-118">CDS</span><span class="sxs-lookup"><span data-stu-id="35bcf-118">CDS</span></span>           | <span data-ttu-id="35bcf-119">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="35bcf-119">Finance and Operations</span></span>    |
|--------------|---------------|---------------------------|
| <span data-ttu-id="35bcf-120">Citations</span><span class="sxs-lookup"><span data-stu-id="35bcf-120">Quotes</span></span>       | <span data-ttu-id="35bcf-121">Devis</span><span class="sxs-lookup"><span data-stu-id="35bcf-121">Quotation</span></span>     | <span data-ttu-id="35bcf-122">En-têtes de devis de vente</span><span class="sxs-lookup"><span data-stu-id="35bcf-122">Sales quotation headers</span></span>   |
| <span data-ttu-id="35bcf-123">QuoteDetails</span><span class="sxs-lookup"><span data-stu-id="35bcf-123">QuoteDetails</span></span> | <span data-ttu-id="35bcf-124">QuotationLine</span><span class="sxs-lookup"><span data-stu-id="35bcf-124">QuotationLine</span></span> | <span data-ttu-id="35bcf-125">Lignes de devis de vente CDS</span><span class="sxs-lookup"><span data-stu-id="35bcf-125">CDS sales quotation lines</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="35bcf-126">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="35bcf-126">Entity flow</span></span>

<span data-ttu-id="35bcf-127">Les devis sont créés dans Sales et synchronisés avec Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="35bcf-127">Sales quotations are created in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="35bcf-128">Les devis sont synchronisés uniquement dans Sales si les conditions suivantes sont réunies :</span><span class="sxs-lookup"><span data-stu-id="35bcf-128">Sales quotations from Sales are synchronized only if the following conditions are met:</span></span>

- <span data-ttu-id="35bcf-129">Tous les produits sur les lignes de devis sont mis à jour en externe.</span><span class="sxs-lookup"><span data-stu-id="35bcf-129">All products on the sales quotation lines are externally maintained.</span></span>
- <span data-ttu-id="35bcf-130">Le devis est actif ou activé.</span><span class="sxs-lookup"><span data-stu-id="35bcf-130">The sales quotation is active or activated.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="35bcf-131">Prospect pour une solution de disponibilités pour Sales</span><span class="sxs-lookup"><span data-stu-id="35bcf-131">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="35bcf-132">Le champ **A des produits mis à jour en externe uniquement** a été ajouté à l'entité de devis pour effectuer le suivi uniformément si le devis consiste entièrement en produits mis à jour en externe.</span><span class="sxs-lookup"><span data-stu-id="35bcf-132">The **Has Externally Maintained Products Only** field has been added to the Quote entity to consistently track whether the sales quotation consists entirely of externally maintained products.</span></span> <span data-ttu-id="35bcf-133">Si un devis comporte uniquement des produits mis à jour en externe, les produits sont mis à jour dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="35bcf-133">If a sales quotation has only externally maintained products, the products are maintained in Finance and Operations.</span></span> <span data-ttu-id="35bcf-134">Ceci permet de garantir que vous ne tenterez pas de synchroniser les lignes de devis avec des produits qui sont inconnus de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="35bcf-134">This behavior helps guarantee that you don't try to synchronize sales quotation lines with products that are unknown to Finance and Operations.</span></span>

<span data-ttu-id="35bcf-135">Tous les produits et lignes du devis sont mis à jour avec les informations **A des produits mis à jour uniquement en externe** de l'en-tête du devis.</span><span class="sxs-lookup"><span data-stu-id="35bcf-135">All products and lines on the quotation are updated with the **Has Externally Maintained Products Only** information from the quotation header.</span></span> <span data-ttu-id="35bcf-136">Ces informations figurent dans le champ **Le devis a des produits mis à jour uniquement en externe** sur l'entité ligne de devis.</span><span class="sxs-lookup"><span data-stu-id="35bcf-136">This information can be found in the **Quote Has Externally Maintained Products Only** field on the Quote line entity.</span></span>

<span data-ttu-id="35bcf-137">Les champs **Remise**, **Frais** et **Taxe** sont contrôlés par un paramétrage complexe dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="35bcf-137">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="35bcf-138">Ce paramétrage ne prend pas en charge actuellement la mise en correspondance d'intégration.</span><span class="sxs-lookup"><span data-stu-id="35bcf-138">This setup doesn't currently support integration mapping.</span></span> <span data-ttu-id="35bcf-139">Dans la conception actuelle, les champs **Prix**, **Remise**, **Charge**, et **Taxe** sont maîtrisé et gérés par Finances and Operations.</span><span class="sxs-lookup"><span data-stu-id="35bcf-139">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are mastered and handled by Finance and Operations.</span></span>

<span data-ttu-id="35bcf-140">Dans Sales, la solution rend les champs suivants en lecture seule, car les valeurs ne sont pas synchronisées avec Finance and Operations :</span><span class="sxs-lookup"><span data-stu-id="35bcf-140">In Sales, the solution makes the following fields read-only, because the values aren't synchronized to Finance and Operations:</span></span>

- <span data-ttu-id="35bcf-141">**Champs en lecture seule sur l'en-tête de devis :** % de remise, Remise, volume de transport</span><span class="sxs-lookup"><span data-stu-id="35bcf-141">**Read-only fields on the sales quotation header:** Discount %, Discount, Freight Amount</span></span>
- <span data-ttu-id="35bcf-142">**Champs en lecture seule sur les lignes de devis :** Taxe</span><span class="sxs-lookup"><span data-stu-id="35bcf-142">**Read-only fields on sales quotation lines:** Tax</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="35bcf-143">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="35bcf-143">Preconditions and mapping setup</span></span>

- <span data-ttu-id="35bcf-144">Avant de synchroniser les devis dans Sales, accédez à **Paramètres** &gt; **Administration** &gt; **Paramètres système** &gt; **Ventes**, puis vérifiez que le champ **Mode de calcul de remise** est défini sur **Par unité**.</span><span class="sxs-lookup"><span data-stu-id="35bcf-144">Before you synchronize sales quotations, in Sales, go to **Settings** &gt; **Administration** &gt; **System settings** &gt; **Sales**, and make sure that the **Discount calculation method** field is set to **Per unit**.</span></span> <span data-ttu-id="35bcf-145">Ce paramètre permet de garantir que la remise de l'article de ligne dans Sales correspond au paramètre de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="35bcf-145">This setting helps guarantee that the line item discount from Sales matches the setting in Finance and Operations.</span></span> <span data-ttu-id="35bcf-146">Sinon, la remise ne sera pas correcte dans Finance and Operations, car Finance and Operations lira la remise comme une remise par unité, même s'il s'agit d'une remise par ligne dans Sales.</span><span class="sxs-lookup"><span data-stu-id="35bcf-146">Otherwise, the discount won't be correct in Finance and Operations, because Finance and Operations will read the discount as a per-unit discount even if it was a per-line discount in Sales.</span></span>
- <span data-ttu-id="35bcf-147">Dans Finance and Operations, accédez à **Comptabilité client** &gt; **Paramétrage** &gt; **Paramètres de comptabilité client**.</span><span class="sxs-lookup"><span data-stu-id="35bcf-147">In Finance and Operations, go to **Accounts receivable** &gt; **Setup** &gt; **Account receivable parameters**.</span></span> <span data-ttu-id="35bcf-148">Dans l'onglet **Souche de numéros**, sélectionnez la souche de numéros pour les devis, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="35bcf-148">On the **Number sequence** tab, select the number sequence for sales quotations, and then click **View details**.</span></span> <span data-ttu-id="35bcf-149">Ensuite, sous **Paramétrage général**, définissez le champ **Manuel** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="35bcf-149">Then, under **General Setup**, set the **Manual** field to **Yes**.</span></span>
- <span data-ttu-id="35bcf-150">Dans Finance and Operations, accédez à **Comptabilité client** &gt; **Paramétrage** &gt; **Paramètres de comptabilité client**.</span><span class="sxs-lookup"><span data-stu-id="35bcf-150">In Finance and Operations, go to **Accounts receivable** &gt; **Setup** &gt; **Accounts receivable parameters**.</span></span> <span data-ttu-id="35bcf-151">Puis, dans l'onglet **Expéditions**, définissez le champ **Vérification de la date de livraison** sur **Aucun**.</span><span class="sxs-lookup"><span data-stu-id="35bcf-151">Then, on the **Shipments** tab, set the **Delivery date control** field to **None**.</span></span> <span data-ttu-id="35bcf-152">Ce paramètre permet d'empêcher la synchronisation d'échouer pour les devis.</span><span class="sxs-lookup"><span data-stu-id="35bcf-152">This setting helps prevent synchronization from failing for sales quotations.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="35bcf-153">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="35bcf-153">QuoteHeader</span></span>

- <span data-ttu-id="35bcf-154">Le champ **Date de livraison demandée** est requis dans Finance and Operations, et la synchronisation échoue si le champ est laissé vide.</span><span class="sxs-lookup"><span data-stu-id="35bcf-154">The **Requested delivery date** field is required in Finance and Operations, and synchronization will fail if the field is left blank.</span></span> <span data-ttu-id="35bcf-155">Pour éviter ce problème, si le champ est vide, une date par défaut est issue de **Source &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="35bcf-155">To prevent this issue, if the field is blank, a default date is taken from **Source &gt; CDS**.</span></span> <span data-ttu-id="35bcf-156">La date doit être mise à jour avec une valeur recommandée.</span><span class="sxs-lookup"><span data-stu-id="35bcf-156">The date should be updated to a preferred value.</span></span> <span data-ttu-id="35bcf-157">Actuellement, vous ne pouvez pas entrer de valeur comme **Aujourd'hui** pour représenter la date du jour.</span><span class="sxs-lookup"><span data-stu-id="35bcf-157">Currently, you can't enter a value such as **Today** to represent today's date.</span></span> <span data-ttu-id="35bcf-158">Vous devez entrer une date spécifique.</span><span class="sxs-lookup"><span data-stu-id="35bcf-158">You must enter a specific date.</span></span> <span data-ttu-id="35bcf-159">Le modèle de valeur par défaut pour **Date de livraison demandée** est **1/1/2020**.</span><span class="sxs-lookup"><span data-stu-id="35bcf-159">The default template value for **Requested delivery date** is **1/1/2020**.</span></span>
- <span data-ttu-id="35bcf-160">Le champ **Adresse Pays Région Code** est requis dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="35bcf-160">The **Address Country region code** field is required in Finance and Operations.</span></span> <span data-ttu-id="35bcf-161">Pour empêcher les erreurs de synchronisation, vous pouvez spécifier une valeur par défaut utilisée si le champ est laissé vide dans Sales.</span><span class="sxs-lookup"><span data-stu-id="35bcf-161">To help prevent synchronization errors, you can specify a default value that is used if the field is left blank in Sales.</span></span> <span data-ttu-id="35bcf-162">Cette valeur par défaut est également utile, car vous ne devez pas entrer manuellement de valeur dans le champ **Pays/Région** pour les adresses locales.</span><span class="sxs-lookup"><span data-stu-id="35bcf-162">This default value is also useful, because you don't have to manually enter a value in the **Country region** field for local addresses.</span></span> <span data-ttu-id="35bcf-163">Il n'existe aucun modèle de valeur par défaut pour **DeliveryAddressCountryRegionISOCode**.</span><span class="sxs-lookup"><span data-stu-id="35bcf-163">There is no default template value for **DeliveryAddressCountryRegionISOCode**.</span></span>
- <span data-ttu-id="35bcf-164">Mettez la mise en correspondance à jour pour **ID organisation CDS** dans **Source &gt; CDS** afin qu'elle corresponde à **Organisation CDS** dans l'entité Organisation :</span><span class="sxs-lookup"><span data-stu-id="35bcf-164">Update the mapping for **CDS Organization ID** in **Source &gt; CDS** so that it matches **CDS organization** in the Organization entity:</span></span>

    - <span data-ttu-id="35bcf-165">Le modèle de valeur par défaut pour **Organization_OrganizationId** est **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="35bcf-165">The default template value for **Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="35bcf-166">Le modèle de valeur par défaut pour **Account_Organization_OrganizationId** est **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="35bcf-166">The default template value for **Account_Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="35bcf-167">Le modèle de valeur par défaut pour **InvoiceAccount_OrganizationId** est **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="35bcf-167">The default template value for **InvoiceAccount_OrganizationId** is **ORG001**.</span></span>

### <a name="quoteline"></a><span data-ttu-id="35bcf-168">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="35bcf-168">QuoteLine</span></span>

- <span data-ttu-id="35bcf-169">Mettez la mise en correspondance à jour pour **ID organisation CDS** dans **Source &gt; CDS** afin qu'elle corresponde à **Organisation CDS** dans l'entité Organisation :</span><span class="sxs-lookup"><span data-stu-id="35bcf-169">Update the mapping for **CDS Organization ID** in **Source &gt; CDS** so that it matches **CDS organization** in the Organization entity:</span></span>

    - <span data-ttu-id="35bcf-170">Le modèle de valeur par défaut pour **Organization_OrganizationId** est **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="35bcf-170">The default template value for **Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="35bcf-171">La valeur par défaut du modèle pour **Product_Organization_Organization_OrganizationId** est **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="35bcf-171">The default template value for **Product_Organization_Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="35bcf-172">La valeur par défaut du modèle pour **Quotation_Organization_Organization_OrganizationId** est **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="35bcf-172">The default template value for **Quotation_Organization_Organization_OrganizationId** is **ORG001**.</span></span>

- <span data-ttu-id="35bcf-173">Le champ **Date de livraison demandée** est requis dans Finance and Operations, et la synchronisation échoue si le champ est laissé vide.</span><span class="sxs-lookup"><span data-stu-id="35bcf-173">The **Requested delivery date** field is required in Finance and Operations, and synchronization will fail if the field is left blank.</span></span> <span data-ttu-id="35bcf-174">Pour éviter ce problème, si le champ est vide, une date par défaut est issue de **Source &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="35bcf-174">To prevent this issue, if the field is blank, a default date is taken from **Source &gt; CDS**.</span></span> <span data-ttu-id="35bcf-175">La date doit être mise à jour avec une valeur recommandée.</span><span class="sxs-lookup"><span data-stu-id="35bcf-175">The date should be updated to a preferred value.</span></span> <span data-ttu-id="35bcf-176">Actuellement, vous ne pouvez pas entrer de valeur comme **Aujourd'hui** pour représenter la date du jour.</span><span class="sxs-lookup"><span data-stu-id="35bcf-176">Currently, you can't enter a value such as **Today** to represent today's date.</span></span> <span data-ttu-id="35bcf-177">Vous devez entrer une date spécifique.</span><span class="sxs-lookup"><span data-stu-id="35bcf-177">You must enter a specific date.</span></span> <span data-ttu-id="35bcf-178">Le modèle de valeur par défaut pour **Date de livraison demandée** est **1/1/2020**.</span><span class="sxs-lookup"><span data-stu-id="35bcf-178">The default template value for **Requested delivery date** is **1/1/2020**.</span></span>
- <span data-ttu-id="35bcf-179">Vous pouvez ajouter les mises en correspondance suivantes de **CDS &gt; Destination** pour vérifier que les lignes de devis sont importées dans Finances and Operations s'il n'existe aucune information par défaut du client ou du produit :</span><span class="sxs-lookup"><span data-stu-id="35bcf-179">You can add the following mappings from **CDS &gt; Destination** to help guarantee that quotation lines are imported into Finance and Operations if there is no default information from either the customer or the product:</span></span>

    - <span data-ttu-id="35bcf-180">**SiteId** – Un site est requis pour générer des lignes de devis et de commande client dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="35bcf-180">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="35bcf-181">Il n'existe aucun modèle de valeur par défaut pour **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="35bcf-181">There is no default template value for **SiteId**.</span></span>
    - <span data-ttu-id="35bcf-182">**WarehouseId** – Un entrepôt est requis pour traiter des lignes de devis et de commande client dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="35bcf-182">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="35bcf-183">Il n'existe aucun modèle de valeur par défaut pour **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="35bcf-183">There is no default template value for **WarehouseId**.</span></span>

- <span data-ttu-id="35bcf-184">Assurez-vous que la mise en correspondance des valeurs requise pour l'unité de mesure de vente (UOM) dans Finance and Operations existe dans la mise en correspondance **CDS &gt; Destination** pour **Quantity_UOM** vers **SALESUNITSYMBOL**.</span><span class="sxs-lookup"><span data-stu-id="35bcf-184">Make sure that the required value map for the selling unit of measure (UOM) in Finance and Operations exists in the **CDS &gt; Destination** mapping for **Quantity_UOM** to **SALESUNITSYMBOL**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="35bcf-185">Mise en correspondance de modèles dans l'intégrateur de données</span><span class="sxs-lookup"><span data-stu-id="35bcf-185">Template mapping in data integrator</span></span>

> [!NOTE]
> - <span data-ttu-id="35bcf-186">Les champs **Remise**, **Frais** et **Taxe** sont contrôlés par un paramétrage complexe dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="35bcf-186">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="35bcf-187">Ce paramétrage ne prend pas en charge actuellement la mise en correspondance d'intégration.</span><span class="sxs-lookup"><span data-stu-id="35bcf-187">This setup doesn't currently support integration mapping.</span></span> <span data-ttu-id="35bcf-188">Dans la conception actuelle, les champs **Prix**, **Remise**, **Charge**, et **Taxe** sont gérés par Finances and Operations.</span><span class="sxs-lookup"><span data-stu-id="35bcf-188">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are handled by Finance and Operations.</span></span>
> - <span data-ttu-id="35bcf-189">Les champs **Conditions de paiement**, **Conditions de transport**, **Conditions de livraison**, **Méthode d'expédition** et **Mode de distribution** ne font pas partie des mises en correspondance par défaut.</span><span class="sxs-lookup"><span data-stu-id="35bcf-189">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="35bcf-190">Pour mettre en correspondance ces champs, vous devez paramétrer une mise en correspondance des valeurs spécifique aux données des organisations entre lesquelles l'entité est synchronisée.</span><span class="sxs-lookup"><span data-stu-id="35bcf-190">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="35bcf-191">Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l'intégrateur de données.</span><span class="sxs-lookup"><span data-stu-id="35bcf-191">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="35bcf-192">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="35bcf-192">QuoteHeader</span></span>

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-quotation-template-mapping-data-integrator-1.png)

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-quotation-template-mapping-data-integrator-2.png)

### <a name="quoteline"></a><span data-ttu-id="35bcf-195">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="35bcf-195">QuoteLine</span></span>

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-quotation-template-mapping-data-integrator-3.png)

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-quotation-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a><span data-ttu-id="35bcf-198">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="35bcf-198">Related topics</span></span>

[<span data-ttu-id="35bcf-199">Synchronisez les produits de Finance and Operations sur les produits de Sales</span><span class="sxs-lookup"><span data-stu-id="35bcf-199">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="35bcf-200">Synchronisez les comptes des ventes aux clients de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="35bcf-200">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="35bcf-201">Synchronisez les Contacts de Sales sur les contacts ou clients de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="35bcf-201">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)



