---
title: Synchronisez les comptes des ventes aux clients de Finance and Operations
description: "La rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les comptes Microsoft Dynamics 365 for Sales à Microsoft Dynamics 365 for Finance and Operations, édition Entreprise."
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
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 1fdbeaaba53cd439d9872be78b1cf67cbc5a57b9
ms.contentlocale: fr-fr
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-accounts-from-sales-to-customers-in-finance-and-operations"></a><span data-ttu-id="ecc0f-103">Synchronisez les comptes des ventes aux clients de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ecc0f-103">Synchronize accounts from Sales to customers in Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="ecc0f-104">Avant d'utiliser le prospect pour une solution de disponibilités, vous devez connaître [Intégration de données Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="ecc0f-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="ecc0f-105">La rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les comptes Microsoft Dynamics 365 for Sales (Sales) à Microsoft Dynamics 365 for Finance and Operations, édition Entreprise (Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="ecc0f-105">The topic discusses the templates and underlying tasks that are used to synchronize accounts from Microsoft Dynamics 365 for Sales (Sales) to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span></span>

## <a name="template-and-task"></a><span data-ttu-id="ecc0f-106">Modèle et tâche</span><span class="sxs-lookup"><span data-stu-id="ecc0f-106">Template and task</span></span>

<span data-ttu-id="ecc0f-107">Les modèles et tâches sous-jacentes suivants sont utilisés pour synchroniser les comptes de Sales vers Finance and Operations :</span><span class="sxs-lookup"><span data-stu-id="ecc0f-107">The following templates and underlying tasks are used to synchronize accounts from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="ecc0f-108">**Nom du modèle :** Comptes (Sales vers Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="ecc0f-108">**Name of the template:** Accounts (Sales to Fin and Ops)</span></span>
- <span data-ttu-id="ecc0f-109">**Nom de la tâche dans le projet :** Comptes - compte - clients</span><span class="sxs-lookup"><span data-stu-id="ecc0f-109">**Name of the task in the project:** Accounts - Account - Customers</span></span>

<span data-ttu-id="ecc0f-110">Tâches de synchronisation requises avant la synchronisation Compte/client : aucune</span><span class="sxs-lookup"><span data-stu-id="ecc0f-110">Sync tasks required prior to Account / Customer sync: None</span></span>

## <a name="entity-set"></a><span data-ttu-id="ecc0f-111">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="ecc0f-111">Entity set</span></span>

| <span data-ttu-id="ecc0f-112">Vente</span><span class="sxs-lookup"><span data-stu-id="ecc0f-112">Sales</span></span>    | <span data-ttu-id="ecc0f-113">CDS</span><span class="sxs-lookup"><span data-stu-id="ecc0f-113">CDS</span></span>     | <span data-ttu-id="ecc0f-114">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ecc0f-114">Finance and Operations</span></span> |
|----------|---------|------------------------|
| <span data-ttu-id="ecc0f-115">Comptes</span><span class="sxs-lookup"><span data-stu-id="ecc0f-115">Accounts</span></span> | <span data-ttu-id="ecc0f-116">Compte</span><span class="sxs-lookup"><span data-stu-id="ecc0f-116">Account</span></span> | <span data-ttu-id="ecc0f-117">Clients</span><span class="sxs-lookup"><span data-stu-id="ecc0f-117">Customers</span></span>              |

## <a name="entity-flow"></a><span data-ttu-id="ecc0f-118">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="ecc0f-118">Entity flow</span></span>

<span data-ttu-id="ecc0f-119">Les comptes sont gérés dans Sales et synchronisés sur Finance and Operations en tant que clients.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-119">Accounts are managed in Sales and synchronized to Finance and Operations as Customers.</span></span> <span data-ttu-id="ecc0f-120">La propriété **Géré en externe** sur ces clients est définie sur **Activé** pour suivre les clients issus de Sales.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-120">The **Is Externally Maintained** property on these Customers is set to **Yes** to track Customers that originate from Sales.</span></span> <span data-ttu-id="ecc0f-121">Lors de la facturation, ces informations sont utilisées pour filtrer les factures qui sont synchronisées sur Sales.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-121">During invoicing, this information is used to filter invoices that are synchronized to Sales.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="ecc0f-122">Prospect pour une solution de disponibilités pour Sales</span><span class="sxs-lookup"><span data-stu-id="ecc0f-122">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="ecc0f-123">Le champ **Numéro de compte** est disponible sur la page **Compte**.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-123">The **Account Number** field is available on the **Account** page.</span></span> <span data-ttu-id="ecc0f-124">Une clé naturelle et unique a été créée pour prendre en charge l'intégration.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-124">It has been made a natural and unique key to support the integration.</span></span> <span data-ttu-id="ecc0f-125">La fonction de clé naturelle de la solution de gestion de la relation client (CRM) peut affecter les clients utilisant déjà le champ **Numéro de compte**, mais qui n'utilisez pas des valeurs **Numéro de compte** uniques par compte.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-125">The natural key feature of the Customer Relationship Management (CRM) solution might affect customers who already use the **Account Number** field, but who don't use unique **Account Number** values per account.</span></span> <span data-ttu-id="ecc0f-126">Actuellement, la solution d'intégration ne prend pas en charge ce cas.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-126">Currently, the integration solution doesn't support this case.</span></span>

<span data-ttu-id="ecc0f-127">Lorsqu'un compte est créé, si une valeur **Numéro de compte** n'existe pas encore, elle est automatiquement générée à l'aide d'une souche de numéros.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-127">When a new account is created, if an **Account Number** value doesn't already exist, it's automatically generated by using a number sequence.</span></span> <span data-ttu-id="ecc0f-128">La valeur est composée d'**ACC**, suivi d'une souche de numéros croissante et d'un suffixe de six caractères.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-128">The value consists of **ACC**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="ecc0f-129">Voici un exemple : **ACC-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="ecc0f-129">Here is an example: **ACC-01000-BVRCPS**</span></span>

<span data-ttu-id="ecc0f-130">Lorsque la solution d'intégration pour Sales est appliquée, un script de mise à niveau définit le champ **Numéro de compte** sur les comptes existants dans Sales.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-130">When the integration solution for Sales is applied, an upgrade script sets the **Account Number** field for existing accounts in Sales.</span></span> <span data-ttu-id="ecc0f-131">S'il n'existe aucune valeur **Numéro de compte**, la souche de numéros qui a été décrite plus haut est utilisée.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-131">If there are no **Account Number** values, the number sequence that was described earlier is used.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="ecc0f-132">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="ecc0f-132">Preconditions and mapping setup</span></span>

- <span data-ttu-id="ecc0f-133">La mise en correspondance **CustomerGroupId** à partir de **CDS &gt; Destination** doit être mise à jour avec une valeur valide dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-133">**CustomerGroupId** mapping from **CDS &gt; Destination** must be updated to a valid value in Finance and Operations.</span></span> <span data-ttu-id="ecc0f-134">Vous pouvez spécifier une valeur par défaut ou vous pouvez définir la valeur à l'aide d'une mise en correspondance des valeurs.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-134">You can specify a default value, or you can set the value by using a value map.</span></span> <span data-ttu-id="ecc0f-135">Le modèle de valeur par défaut est **10**.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-135">The default template value is **10**.</span></span>
- <span data-ttu-id="ecc0f-136">**Adresse Pays Région Code** est requis dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-136">**Address country region code** is required in Finance and Operations.</span></span> <span data-ttu-id="ecc0f-137">Pour éviter toute erreur de synchronisation, vous pouvez spécifier une valeur par défaut dans la mise en correspondance à partir de **CDS &gt; Destination**.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-137">To avoid synchronization errors, you can specify a default value in the mapping from **CDS &gt; Destination**.</span></span> <span data-ttu-id="ecc0f-138">Cette valeur par défaut est alors utilisée si le champ est laissé vide dans Sales.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-138">That default value is then used if the field is left blank in Sales.</span></span>

    - <span data-ttu-id="ecc0f-139">Le modèle de valeur par défaut pour **AddressCountryRegionISOCode** est **USA**.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-139">The default template value for **AddressCountryRegionISOCode** is **USA**.</span></span>
    - <span data-ttu-id="ecc0f-140">Le modèle de valeur par défaut pour **DeliveryAddressCountryRegionISOCode** est **USA**.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-140">The default template value for **DeliveryAddressCountryRegionISOCode** is **USA**.</span></span>

- <span data-ttu-id="ecc0f-141">En ajoutant les mises en correspondance suivantes de **CDS &gt; Destination**, vous pouvez réduire le nombre de mises à jour manuelles requises dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-141">By adding the following mappings from **CDS &gt; Destination**, you can help reduce the number of manual updates that are required in Finance and Operations.</span></span> <span data-ttu-id="ecc0f-142">Vous pouvez utiliser une valeur par défaut ou une mise en correspondance des valeurs, par exemple, **Pays/région** ou **Ville**.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-142">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="ecc0f-143">**SiteId** – Un site est requis pour générer des lignes de devis et de commande client dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-143">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="ecc0f-144">Un site par défaut peut être extrait du produit, ou du client de l'en-tête de commande.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-144">A default site can be taken either from the product, or from the customer from the order header.</span></span> <span data-ttu-id="ecc0f-145">Le modèle de valeur par défaut pour **SiteId** est **1**.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-145">The default template value for **SiteId** is **1**.</span></span>
    - <span data-ttu-id="ecc0f-146">**WarehouseId** – Un entrepôt est requis pour traiter des lignes de devis et de commande client dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-146">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="ecc0f-147">Un entrepôt par défaut peut être extrait du produit, ou du client de l'en-tête de commande dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-147">A default warehouse can be taken either from the product, or from the customer from the order header in Finance and Operations.</span></span> <span data-ttu-id="ecc0f-148">Le modèle de valeur par défaut pour **WarehouseId** est **13**.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-148">The default template value for **WarehouseId** is **13**.</span></span>
    - <span data-ttu-id="ecc0f-149">**LanguageId** – Une langue est requise pour générer des devis et des commandes client dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-149">**LanguageId** – A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="ecc0f-150">Par défaut, la langue de l'en-tête de commande du client est utilisée.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-150">By default, the language from the order header from the customer is used.</span></span> <span data-ttu-id="ecc0f-151">Le modèle de valeur par défaut pour **LanguageId** est **en-us**.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-151">The default template value for **LanguageId** is **en-us**.</span></span>

- <span data-ttu-id="ecc0f-152">Mettez à jour l'ID d'organisation CDS (**Organization_OrganizationId**) dans la mise en correspondance **Source &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-152">Update the CDS organization ID (**Organization_OrganizationId**) in the **Source &gt; CDS** mapping.</span></span> <span data-ttu-id="ecc0f-153">Le modèle de valeur par défaut est **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-153">The default template value is **ORG001**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="ecc0f-154">Mise en correspondance de modèles dans l'intégrateur de données</span><span class="sxs-lookup"><span data-stu-id="ecc0f-154">Template mapping in data integrator</span></span>

> [!NOTE]
> <span data-ttu-id="ecc0f-155">Les champs **Conditions de paiement**, **Conditions de transport**, **Conditions de livraison**, **Méthode d'expédition** et **Mode de distribution** ne sont pas inclus dans les mises en correspondance par défaut.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-155">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="ecc0f-156">Pour mettre ces champs en correspondance, vous devez paramétrer une mise en correspondance de valeurs.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-156">To map these fields, you must set up a value mapping.</span></span> <span data-ttu-id="ecc0f-157">Les mises en correspondance de valeurs sont spécifiques aux données des organisations entre lesquelles l'entité est synchronisée.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-157">Value mappings are specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="ecc0f-158">Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l'intégrateur de données.</span><span class="sxs-lookup"><span data-stu-id="ecc0f-158">The following illustrations show an example of a template mapping in data integrator.</span></span>

![Mise en correspondance de modèles dans l'intégrateur de données](./media/accounts-template-mapping-data-integrator-1.png)

![Modèle de mise en correspondance pour les comptes dans l'intégrateur de données](./media/accounts-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="ecc0f-161">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="ecc0f-161">Related topics</span></span>

[<span data-ttu-id="ecc0f-162">Synchronisez les produits de Finance and Operations sur les produits de Sales</span><span class="sxs-lookup"><span data-stu-id="ecc0f-162">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="ecc0f-163">Synchronisez les Contacts de Sales sur les contacts ou clients de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ecc0f-163">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="ecc0f-164">Synchroniser les en-têtes et les lignes de devis de vente provenant du module Sales sur Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ecc0f-164">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="ecc0f-165">Synchroniser les en-têtes et les lignes de commande client provenant du module Finance and Operations sur Sales</span><span class="sxs-lookup"><span data-stu-id="ecc0f-165">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>](sales-order-template-mapping.md)

[<span data-ttu-id="ecc0f-166">Synchroniser les en-têtes et les lignes de facture client provenant du module Finance and Operations sur Sales</span><span class="sxs-lookup"><span data-stu-id="ecc0f-166">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping.md)




