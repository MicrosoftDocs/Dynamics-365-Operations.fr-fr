---
title: Synchroniser les produits provenant de Finance and Operations sur les produits du module Sales
description: "Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les produits entre Microsoft Dynamics 365 for Finance and Operations, édition Entreprise et Microsoft Dynamics 365 for Sales."
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
ms.openlocfilehash: 2f14b06b57930256f9211f2085512aa589df083e
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---

# <a name="synchronize-products-from-finance-and-operations-to-products-in-sales"></a><span data-ttu-id="2897f-103">Synchroniser les produits provenant de Finance and Operations sur les produits du module Sales</span><span class="sxs-lookup"><span data-stu-id="2897f-103">Synchronize products from Finance and Operations to products in Sales</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="2897f-104">Avant d'utiliser le prospect pour une solution de disponibilités, vous devez connaître [Intégration de données Dynamics 365](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="2897f-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="2897f-105">Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les produits entre Microsoft Dynamics 365 for Finance and Operations, édition Entreprise et Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="2897f-105">This topic discusses the templates and underlying tasks that are used to synchronize products from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition to Microsoft Dynamics 365 for Sales.</span></span>

## <a name="template-and-task"></a><span data-ttu-id="2897f-106">Modèle et tâche</span><span class="sxs-lookup"><span data-stu-id="2897f-106">Template and task</span></span>

<span data-ttu-id="2897f-107">Les modèles et les tâches sous-jacentes suivants sont utilisés pour synchroniser les produits entre Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations) et Microsoft Dynamics 365 for Sales (Sales).</span><span class="sxs-lookup"><span data-stu-id="2897f-107">The following templates and underlying tasks are used to synchronize products from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations) to Microsoft Dynamics 365 for Sales (Sales).</span></span>

-   <span data-ttu-id="2897f-108">Nom du modèle : Produits (Fin and Ops vers Sales)</span><span class="sxs-lookup"><span data-stu-id="2897f-108">Name of template: Products (Fin and Ops to Sales)</span></span>

-   <span data-ttu-id="2897f-109">Nom de la tâche dans le projet : Produits</span><span class="sxs-lookup"><span data-stu-id="2897f-109">Name of task in project: Products</span></span>

<span data-ttu-id="2897f-110">Tâches de synchronisation requises avant la synchronisation Produit/client : aucune</span><span class="sxs-lookup"><span data-stu-id="2897f-110">Sync tasks required prior to Product sync: None</span></span>

## <a name="entity-set"></a><span data-ttu-id="2897f-111">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="2897f-111">Entity set</span></span>

| <span data-ttu-id="2897f-112">**Finance and Operations**</span><span class="sxs-lookup"><span data-stu-id="2897f-112">**Finance and Operations**</span></span> | <span data-ttu-id="2897f-113">**CDS**</span><span class="sxs-lookup"><span data-stu-id="2897f-113">**CDS**</span></span> | <span data-ttu-id="2897f-114">**Ventes**</span><span class="sxs-lookup"><span data-stu-id="2897f-114">**Sales**</span></span>  |
|----------------------------|---------|------------|
| <span data-ttu-id="2897f-115">Produits lancés vendables</span><span class="sxs-lookup"><span data-stu-id="2897f-115">Sellable released products</span></span> | <span data-ttu-id="2897f-116">Produit</span><span class="sxs-lookup"><span data-stu-id="2897f-116">Product</span></span> | <span data-ttu-id="2897f-117">Produits</span><span class="sxs-lookup"><span data-stu-id="2897f-117">Products</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="2897f-118">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="2897f-118">Entity flow</span></span>

<span data-ttu-id="2897f-119">Les produits sont gérés dans Finance and Operations et synchronisés avec Sales.</span><span class="sxs-lookup"><span data-stu-id="2897f-119">Products are managed in Finance and Operations and synchronized to Sales.</span></span> <span data-ttu-id="2897f-120">L'entité de données **Produits lancés vendables** dans Finance and Operations exporte uniquement les produits vendables, ce qui signifie que les produits ont les informations obligatoires pour être utilisés sur une commande client.</span><span class="sxs-lookup"><span data-stu-id="2897f-120">The data entity **Sellable released products** in Finance and Operations only exports products that are sellable, which means that products have the information required to be used on a sales order.</span></span> <span data-ttu-id="2897f-121">Les mêmes règles s'appliquent lorsqu'un produit est validé avec la fonction **Valider** sur la page **Produit lancé**.</span><span class="sxs-lookup"><span data-stu-id="2897f-121">The same rules apply when a product is validated with the **Validate** function on the **Released product** page.</span></span>

<span data-ttu-id="2897f-122">Le **Numéro de produit** est utilisé comme clé, ce qui signifie que les variantes de produit sont synchronisées sur CDS et Sales avec des **ID produits** individuels par **Variante de produit**.</span><span class="sxs-lookup"><span data-stu-id="2897f-122">The **Product number** is used as key, meaning that product variants are synchronized to CDS and Sales with individual **Product IDs** per **Product variant**.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="2897f-123">Prospect pour une solution de disponibilités pour Sales</span><span class="sxs-lookup"><span data-stu-id="2897f-123">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="2897f-124">Dans Sales, un nouveau champ sur les produits, **Géré en externe**, est ajouté pour indiquer qu'un produit donné est conservé en externe.</span><span class="sxs-lookup"><span data-stu-id="2897f-124">In Sales, a new field on the products **Is Externally Maintained** is added to indicate that a given product is maintained externally.</span></span> <span data-ttu-id="2897f-125">La valeur est définie sur **Oui** par défaut lors de l'importation dans Sales.</span><span class="sxs-lookup"><span data-stu-id="2897f-125">The value is set to **Yes** by default during import to Sales.</span></span>

-   <span data-ttu-id="2897f-126">**Géré en externe = Oui** : Le produit provient de Finance and Operations et n'est pas modifiable dans Sales.</span><span class="sxs-lookup"><span data-stu-id="2897f-126">**Is Externally Maintained = Yes**: Product originates from Finance and Operations and will not be editable in Sales.</span></span>

-   <span data-ttu-id="2897f-127">**Géré en externe = Non** : Le produit est entré directement dans Sales.</span><span class="sxs-lookup"><span data-stu-id="2897f-127">**Is Externally Maintained = No**: Product is entered directly in Sales.</span></span>

-   <span data-ttu-id="2897f-128">**Géré en externe = Vide** : Le produit existe dans Sales avant d'activer la solution de prospect en disponibilités.</span><span class="sxs-lookup"><span data-stu-id="2897f-128">**Is Externally Maintained = Blank**: Product exists in Sales prior to enabling the Prospect to cash solution.</span></span>

<span data-ttu-id="2897f-129">L'information **Géré en externe** est utilisée pour vous assurer que seuls **Devis** et **Commandes client** avec **Produits mis à jour en externe** se synchroniseront avec Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2897f-129">The **Is Externally Maintained** information is used to ensure that only **Quotes** and **Sales orders** with **Externally maintained products** will sync to Finance and Operations.</span></span>

<span data-ttu-id="2897f-130">Les **Produits mis à jour en externe** sont automatiquement ajoutés à la première **Liste des prix** valide avec la même devise.</span><span class="sxs-lookup"><span data-stu-id="2897f-130">**Externally maintained products** are automatically added to the first valid **Price list** with the same currency.</span></span> <span data-ttu-id="2897f-131">Notez que la liste est organisée alphabétiquement par **Nom**.</span><span class="sxs-lookup"><span data-stu-id="2897f-131">Note that the list is organized alphabetically by **Name**.</span></span> <span data-ttu-id="2897f-132">Le prix de vente du produit de Finance and Operations est utilisé comme prix sur **Liste des prix**.</span><span class="sxs-lookup"><span data-stu-id="2897f-132">The product sales price from Finance and Operations is used as price on the **Price list**.</span></span> <span data-ttu-id="2897f-133">Cela signifie qu'il doit y avoir une **Liste des prix** dans Sales pour chaque **Devise de vente de produit** dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2897f-133">This means that it is required to have a **Price list** in Sales for each **Product sales currency** in Finance and Operations.</span></span> <span data-ttu-id="2897f-134">La devise des produits vendables lancés est définie sur la devise comptable de l'entité juridique, depuis laquelle le produit est exporté.</span><span class="sxs-lookup"><span data-stu-id="2897f-134">Currency on the released sellable products is set to the accounting currency in the legal entity, from which the product is exported.</span></span>

> [!NOTE]
> <span data-ttu-id="2897f-135">La synchronisation de produit ne réussira pas sans **Liste des prix** dans la devise correspondante.</span><span class="sxs-lookup"><span data-stu-id="2897f-135">Product sync will not succeed without a **Price list** with the matching currency.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="2897f-136">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="2897f-136">Preconditions and mapping setup</span></span>

-   <span data-ttu-id="2897f-137">Avant d'exécuter la toute première synchronisation, vous devez renseigner la **Table des produits distincts** pour les produits existants dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2897f-137">Before you run the very first sync, you must populate the **Distinct product table** for existing products in Finance and Operations.</span></span> <span data-ttu-id="2897f-138">Les produits existants ne seront pas synchronisés tant que cette tâche ne sera pas terminée.</span><span class="sxs-lookup"><span data-stu-id="2897f-138">Existing products will not be synchronized until this job is completed.</span></span>

    -   <span data-ttu-id="2897f-139">Dans Finance and Operations, utilisez la fonction de recherche pour **Compléter la table des produits distincts**.</span><span class="sxs-lookup"><span data-stu-id="2897f-139">In Finance and Operations, use Search to search for **Populate distinct product table**.</span></span>

    -   <span data-ttu-id="2897f-140">Cliquez sur **Compléter la table des produits distincts** pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="2897f-140">Click the **Populate distinct product table** to run the job.</span></span> <span data-ttu-id="2897f-141">Cette tâche doit être exécutée une seule fois.</span><span class="sxs-lookup"><span data-stu-id="2897f-141">This job only needs to be run once.</span></span>

-   <span data-ttu-id="2897f-142">Assurez-vous que la **ValueMap** nécessaire pour la vente d'**Unité de mesure** (UM) dans Finance and Operations existe dans **Source -\> Mise en correspondance CDS SalesUnitSymbol / DefaultSellingUnitOfMeasure**.</span><span class="sxs-lookup"><span data-stu-id="2897f-142">Ensure that the needed **ValueMap** for selling **Unit of measure** (UOM) in Finance and Operations exists in the **Source -\> CDS mapping SalesUnitSymbol / DefaultSellingUnitOfMeasure**.</span></span>

-   <span data-ttu-id="2897f-143">Assurez-vous que les **Décimales prises en charge** pour l'UM correspondent à vos besoins dans **CDS -\> Destination**.</span><span class="sxs-lookup"><span data-stu-id="2897f-143">Ensure that **Decimals supported** for UOM match your requirements in **CDS -\> Destination**.</span></span> <span data-ttu-id="2897f-144">Si vous avez besoin de différentes valeurs par UM, vous pouvez le faire avec **ValueMap** dans Unité, par exemple, [Chaque : 0] et [Livre : 2].</span><span class="sxs-lookup"><span data-stu-id="2897f-144">If you require different values per UOM, this can be done with **ValueMap** from Unit, for example, [Each : 0] & [Pound : 2].</span></span>

    -   <span data-ttu-id="2897f-145">Le modèle de valeur par défaut est 0.</span><span class="sxs-lookup"><span data-stu-id="2897f-145">Template value is defaulted to 0.</span></span>

-   <span data-ttu-id="2897f-146">Mettez à jour l'**ID d'organisation CDS Organization_OrganizationId** dans **Source -\> CDS**.</span><span class="sxs-lookup"><span data-stu-id="2897f-146">Update the **CDS Organization ID Organization_OrganizationId** in **Source -\> CDS**.</span></span>

    -   <span data-ttu-id="2897f-147">Le modèle de valeur par défaut est ORG001.</span><span class="sxs-lookup"><span data-stu-id="2897f-147">Template value is defaulted to ORG001.</span></span>

-   <span data-ttu-id="2897f-148">Mettez à jour **ValueMap** pour **Groupe d'unités** (**defaultuomscheduleid.name**) dans **CDS -\> Destination** pour correspondre au **Groupes d'unités** de Sales.</span><span class="sxs-lookup"><span data-stu-id="2897f-148">Update **ValueMap** for **Unit group** (**defaultuomscheduleid.name**) in **CDS -\> Destination** to match the **Unit groups** in Sales.</span></span>

    -   <span data-ttu-id="2897f-149">Le modèle de valeur par défaut est **Unité par défaut**.</span><span class="sxs-lookup"><span data-stu-id="2897f-149">Template value is defaulted to **Default unit**.</span></span>

-   <span data-ttu-id="2897f-150">Assurez-vous que les UM de vente de produits de Finance and Operations existent dans Sales avec la valeur **Listes de prélèvements CDS**.</span><span class="sxs-lookup"><span data-stu-id="2897f-150">Ensure that all products selling UOMs from Finance and Operations exist in Sales with the **CDS picklists** value.</span></span>

-   <span data-ttu-id="2897f-151">Assurez-vous que **Liste des prix** figurent dans Sales pour chaque devise de vente de produit dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2897f-151">Ensure that **Price lists** exist in Sales for each product sales currency in Finance and Operations.</span></span>

-   <span data-ttu-id="2897f-152">Les produits peuvent être créés dans Sales avec le statut **Brouillon** ou **Actif**.</span><span class="sxs-lookup"><span data-stu-id="2897f-152">Products can be created in Sales with status **Draft** or **Active**.</span></span> <span data-ttu-id="2897f-153">Cette opération est contrôlée dans **Paramètres système** sous **Sales** dans Sales.</span><span class="sxs-lookup"><span data-stu-id="2897f-153">This is controlled in **System settings** under **Sales** in Sales.</span></span>

    -   <span data-ttu-id="2897f-154">Les produits créés avec le statut de brouillon doivent être activés avant de pouvoir être ajoutés à **Devis** ou **Commande client**.</span><span class="sxs-lookup"><span data-stu-id="2897f-154">Products created with draft status need to be activated before they can be added to **Quote** or **Sales order**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="2897f-155">Mise en correspondance de modèles dans l'intégrateur de données</span><span class="sxs-lookup"><span data-stu-id="2897f-155">Template mapping in data integrator</span></span>

<span data-ttu-id="2897f-156">Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l'intégrateur de données.</span><span class="sxs-lookup"><span data-stu-id="2897f-156">The following illustrations show an example of a template mapping in data integrator.</span></span>

![modèle de mise en correspondance dans l'intégrateur de données](./media/products-template-mapping-data-integrator-1.png)

![modèle de mise en correspondance pour les produits dans l'intégrateur de données](./media/products-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="2897f-159">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="2897f-159">Related topics</span></span>

[<span data-ttu-id="2897f-160">Synchronisez les comptes des ventes aux clients de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="2897f-160">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="2897f-161">Synchronisez les Contacts de Sales sur les contacts ou clients de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="2897f-161">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="2897f-162">Synchronisez les en-têtes de vis de vente et les lignes entre Sales et Finances and Operations</span><span class="sxs-lookup"><span data-stu-id="2897f-162">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)


