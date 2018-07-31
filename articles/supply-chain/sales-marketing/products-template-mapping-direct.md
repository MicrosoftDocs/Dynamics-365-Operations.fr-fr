---
title: Synchroniser les produits directement de Finance and Operations sur les produits du module Sales
description: "Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les produits entre Microsoft Dynamics 365 for Finance and Operations et Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 06/25/2018
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
ms.sourcegitcommit: 03bab1d03be71c0e23a6ea93f542d6a52a212a1f
ms.openlocfilehash: 66506953790fd77c2105591d3211c76991eced08
ms.contentlocale: fr-fr
ms.lasthandoff: 06/25/2018

---

# <a name="synchronize-products-directly-from-finance-and-operations-to-products-in-sales"></a><span data-ttu-id="460d9-103">Synchroniser directement les produits provenant de Finance and Operations sur les produits du module Sales</span><span class="sxs-lookup"><span data-stu-id="460d9-103">Synchronize products directly from Finance and Operations to products in Sales</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="460d9-104">Avant d'utiliser le prospect pour une solution de disponibilités, vous devez connaître l'[intégration de données Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="460d9-104">Before you can use the Prospect to cash solution, you should be familiar with [Dynamics 365 Data integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span>

<span data-ttu-id="460d9-105">Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser directement les produits entre Microsoft Dynamics 365 for Finance and Operations et Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="460d9-105">This topic discusses the templates and underlying tasks that are used to synchronize products directly from Microsoft Dynamics 365 for Finance and Operations, to Microsoft Dynamics 365 for Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="460d9-106">Flux de données dans Prospect en disponibilités</span><span class="sxs-lookup"><span data-stu-id="460d9-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="460d9-107">La solution Prospect en disponibilités utilise la fonction d'intégration de données pour synchroniser les données entre plusieurs instances de Finance and Operations et Sales.</span><span class="sxs-lookup"><span data-stu-id="460d9-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="460d9-108">Les modèles de prospects en disponibilités disponibles avec la fonction d'intégration de données activent le flux de données relatifs aux comptes, contacts, produits, devis de vente, commandes client et factures client entre Finance and Operations et Sales.</span><span class="sxs-lookup"><span data-stu-id="460d9-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="460d9-109">L'illustration ci-dessous indique comment les données sont synchronisées entre Finance and Operations et Sales.</span><span class="sxs-lookup"><span data-stu-id="460d9-109">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="460d9-110">[![Flux de données dans Prospect en disponibilités](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="460d9-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="460d9-111">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="460d9-111">Templates and tasks</span></span>

<span data-ttu-id="460d9-112">Pour accéder à des modèles disponibles, ouvrir [Centre d'administrateur PowerApps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="460d9-112">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="460d9-113">Sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner les modèles publics.</span><span class="sxs-lookup"><span data-stu-id="460d9-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="460d9-114">Le modèle et tâches sous-jacentes suivants sont utilisés pour synchroniser les produits de Finance and Operations vers Sales.</span><span class="sxs-lookup"><span data-stu-id="460d9-114">The following template and underlying tasks are used to synchronize products from Finance and Operations to Sales.</span></span>

- <span data-ttu-id="460d9-115">Produits **Nom du modèle dans l'intégration des données :** (Fin and Ops to Sales) - Direct</span><span class="sxs-lookup"><span data-stu-id="460d9-115">**Name of the template in Data integration:** Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="460d9-116">**Nom de la tâche dans le projet d'intégration de données :** Produits</span><span class="sxs-lookup"><span data-stu-id="460d9-116">**Name of the task in the Data integration project:** Products</span></span>

<span data-ttu-id="460d9-117">Aucune tâche de synchronisation n'est nécessaire pour que la synchronisation des produits puisse se produire.</span><span class="sxs-lookup"><span data-stu-id="460d9-117">No synchronization tasks are required before product synchronization can occur.</span></span>

## <a name="entity-set"></a><span data-ttu-id="460d9-118">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="460d9-118">Entity set</span></span>

| <span data-ttu-id="460d9-119">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="460d9-119">Finance and Operations</span></span>     | <span data-ttu-id="460d9-120">Vente</span><span class="sxs-lookup"><span data-stu-id="460d9-120">Sales</span></span>    |
|----------------------------|----------|
| <span data-ttu-id="460d9-121">Produits lancés vendables</span><span class="sxs-lookup"><span data-stu-id="460d9-121">Sellable released products</span></span> | <span data-ttu-id="460d9-122">Produits</span><span class="sxs-lookup"><span data-stu-id="460d9-122">Products</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="460d9-123">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="460d9-123">Entity flow</span></span>

<span data-ttu-id="460d9-124">Les produits sont gérés dans Finance and Operations et synchronisés avec Sales.</span><span class="sxs-lookup"><span data-stu-id="460d9-124">Products are managed in Finance and Operations and synchronized to Sales.</span></span> <span data-ttu-id="460d9-125">L'entité de données **Produits lancés vendables** dans Finance and Operations exporte uniquement les produits qui sont *vendables*.</span><span class="sxs-lookup"><span data-stu-id="460d9-125">The **Sellable released products** data entity in Finance and Operations exports only products that are *sellable*.</span></span> <span data-ttu-id="460d9-126">Les produits vendables sont des produits ayant toutes les informations requises pour être utilisés dans une commande client.</span><span class="sxs-lookup"><span data-stu-id="460d9-126">Sellable products are products that have the information that they require in order to be used on a sales order.</span></span> <span data-ttu-id="460d9-127">Les mêmes règles s'appliquent lorsqu'un produit est validé avec la fonction **Valider** sur la page **Produit lancé**.</span><span class="sxs-lookup"><span data-stu-id="460d9-127">The same rules apply when a product is validated by using the **Validate** function on the **Released product** page.</span></span>

<span data-ttu-id="460d9-128">Le numéro de produit est utilisé comme clé.</span><span class="sxs-lookup"><span data-stu-id="460d9-128">The product number is used as a key.</span></span> <span data-ttu-id="460d9-129">Par conséquent, lorsque des variantes de produit sont synchronisées avec Sales, chaque variante de produit a un ID de produit individuel.</span><span class="sxs-lookup"><span data-stu-id="460d9-129">Therefore, when product variants are synchronized to Sales, each product variant has an individual product ID.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="460d9-130">Prospect pour une solution de disponibilités pour Sales</span><span class="sxs-lookup"><span data-stu-id="460d9-130">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="460d9-131">Dans Sales, un nouveau champ **Géré en externe** est ajouté sur les produits pour indiquer qu'un produit donné est conservé en externe.</span><span class="sxs-lookup"><span data-stu-id="460d9-131">In Sales, a new **Is Externally Maintained** field has been added on products to indicate that a given product is maintained externally.</span></span> <span data-ttu-id="460d9-132">Par défaut, la valeur est définie sur **Oui** lors de l'importation dans Sales.</span><span class="sxs-lookup"><span data-stu-id="460d9-132">By default, the value is set to **Yes** during an import to Sales.</span></span> <span data-ttu-id="460d9-133">Les valeurs disponibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="460d9-133">The following values are available:</span></span>

- <span data-ttu-id="460d9-134">**Oui** – Le produit provient de Finance and Operations et n'est pas modifiable dans Sales.</span><span class="sxs-lookup"><span data-stu-id="460d9-134">**Yes** – The product originated from Finance and Operations and won't be editable in Sales.</span></span>
- <span data-ttu-id="460d9-135">**Non** – Le produit est entré directement dans Sales.</span><span class="sxs-lookup"><span data-stu-id="460d9-135">**No** – The product was entered directly in Sales.</span></span>
- <span data-ttu-id="460d9-136">**(Vide)** – Le produit existe dans Sales avant d'activer la solution de prospect en disponibilités.</span><span class="sxs-lookup"><span data-stu-id="460d9-136">**(Blank)** – The product existed in Sales before the Prospect to cash solution was enabled.</span></span>

<span data-ttu-id="460d9-137">Le champ **Géré en externe** aide à garantir que seuls les devis et les commandes client ayant des produits gérés en externes seront synchronisés avec Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="460d9-137">The **Is Externally Maintained** field helps guarantee that only quotations and sales orders that have externally maintained products will be synchronized to Finance and Operations.</span></span>

<span data-ttu-id="460d9-138">Les produits mis à jour en externe sont automatiquement ajoutés au premier tarif valide avec la même devise.</span><span class="sxs-lookup"><span data-stu-id="460d9-138">Externally maintained products are automatically added to the first valid price list that has the same currency.</span></span> <span data-ttu-id="460d9-139">Les tarifs sont organisés alphabétiquement par nom.</span><span class="sxs-lookup"><span data-stu-id="460d9-139">Price lists are organized alphabetically by name.</span></span> <span data-ttu-id="460d9-140">Le prix de vente du produit de Finance and Operations est utilisé comme prix sur le tarif.</span><span class="sxs-lookup"><span data-stu-id="460d9-140">The product sales price from Finance and Operations is used as the price on the price list.</span></span> <span data-ttu-id="460d9-141">Par conséquent, un tarif doit figurer dans Sales pour chaque devise de vente de produit dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="460d9-141">Therefore, there must be a price list in Sales for every product sales currency in Finance and Operations.</span></span> <span data-ttu-id="460d9-142">La devise des produits vendables lancés est définie sur la devise comptable de l'entité juridique, depuis laquelle le produit est exporté.</span><span class="sxs-lookup"><span data-stu-id="460d9-142">The currency on the released sellable products is set to the accounting currency in the legal entity that the product is exported from.</span></span>

> [!NOTE]
> - <span data-ttu-id="460d9-143">La synchronisation des produits ne réussit pas si une liste de prix n'a pas de devise correspondante.</span><span class="sxs-lookup"><span data-stu-id="460d9-143">Product synchronization will not succeed unless there is a price list that has a matching currency.</span></span>
> - <span data-ttu-id="460d9-144">Vous pouvez contrôler la liste de prix utilisée avec l'intégration en mettant en correspondance le pricelevelid.name [Liste de prix par défaut (nom)] dans le projet d'intégration de données.</span><span class="sxs-lookup"><span data-stu-id="460d9-144">You can control the used price list with the integration by mapping the pricelevelid.name [Default Price List (Name)] in the Data Integration project.</span></span> <span data-ttu-id="460d9-145">La saisie doit être effectuée en lettres minuscules.</span><span class="sxs-lookup"><span data-stu-id="460d9-145">The input has to be in all lowercase letters.</span></span> <span data-ttu-id="460d9-146">Par exemple, la valeur par défaut pour une liste de prix dans Sales nommée « Standard » est : Champ de destination : pricelevelid.name [Liste de prix par défaut (nom)] et Type de carte : [ { "transformType": "Default", "defaultValue": "standard" } ].</span><span class="sxs-lookup"><span data-stu-id="460d9-146">For example, the default for a price list in Sales named ‘Standard’ would be: Destination field: pricelevelid.name [Default Price List (Name)] and Map type: [ { "transformType": "Default", "defaultValue": "standard" } ].</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="460d9-147">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="460d9-147">Preconditions and mapping setup</span></span>

- <span data-ttu-id="460d9-148">Avant d'exécuter la toute première synchronisation, vous devez renseigner la Table des produits distincts pour les produits existants dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="460d9-148">Before you run the synchronization for the first time, you must fill the Distinct product table for existing products in Finance and Operations.</span></span> <span data-ttu-id="460d9-149">Les produits existants ne seront pas synchronisés tant que cette tâche ne sera pas terminée.</span><span class="sxs-lookup"><span data-stu-id="460d9-149">Existing products won't be synchronized until this job is completed.</span></span>

    1. <span data-ttu-id="460d9-150">Dans Finance and Operations, utilisez la fonction de recherche pour **Compléter la table des produits distincts**.</span><span class="sxs-lookup"><span data-stu-id="460d9-150">In Finance and Operations, use Search to search for **Populate distinct product table**.</span></span>
    2. <span data-ttu-id="460d9-151">Cliquez sur **Compléter la table des produits distincts** pour exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="460d9-151">Select **Populate distinct product table** to run the job.</span></span> <span data-ttu-id="460d9-152">Cette tâche ne doit être exécutée qu'une seule fois.</span><span class="sxs-lookup"><span data-stu-id="460d9-152">This job must be run only one time.</span></span>

- <span data-ttu-id="460d9-153">Assurez-vous que la mise en correspondance des valeurs requise pour l'unité de mesure de vente (UOM) entre Finance and Operations et Sales existe bien dans la mise en correspondance **SalesUnitSymbol** vers **DefaultUnit (Name)**.</span><span class="sxs-lookup"><span data-stu-id="460d9-153">Make sure that the required value map for the selling unit of measure (UOM) between Finance and Operations and Sales exists in the mapping of **SalesUnitSymbol** to **DefaultUnit (Name)**.</span></span>
- <span data-ttu-id="460d9-154">Mettez à jour la mise en correspondance de la valeur pour **Groupe d'unités** (**defaultuomscheduleid.name**) pour qu'il corresponde au  **Groupes d'unité** dans Sales.</span><span class="sxs-lookup"><span data-stu-id="460d9-154">Update the value map for **Unit group** (**defaultuomscheduleid.name**) so that it matches **Unit groups** in Sales.</span></span>

    <span data-ttu-id="460d9-155">Le modèle de valeur par défaut est **Unité par défaut**.</span><span class="sxs-lookup"><span data-stu-id="460d9-155">The default template value is **Default unit**.</span></span>

- <span data-ttu-id="460d9-156">Assurez-vous que les UM de vente pour tous les produits de Finance and Operations existent dans Sales.</span><span class="sxs-lookup"><span data-stu-id="460d9-156">Make sure that the selling UOMs for all products from Finance and Operations exist in Sales.</span></span>
- <span data-ttu-id="460d9-157">Assurez-vous que les tarifs figurent dans Sales pour chaque devise de vente de produit dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="460d9-157">Make sure that price lists exist in Sales for every product sales currency in Finance and Operations.</span></span>
- <span data-ttu-id="460d9-158">Lorsque les produits sont créés dans Sales, ils peuvent avoir un statut **Brouillon** ou **Actif**.</span><span class="sxs-lookup"><span data-stu-id="460d9-158">When products are created in Sales, they can have a status of **Draft** or **Active**.</span></span> <span data-ttu-id="460d9-159">Le comportement est contrôlé dans **Paramètres** > **Administration** > **Paramètres système** > **Ventes** dans Sales.</span><span class="sxs-lookup"><span data-stu-id="460d9-159">The behavior is controlled at **Settings** > **Administration** > **System settings** > **Sales** in Sales.</span></span>

    <span data-ttu-id="460d9-160">Les produits qui ont l'état **Brouillon** lors de leur création doivent être activés pour pouvoir être ajoutés aux devis ou aux commandes client.</span><span class="sxs-lookup"><span data-stu-id="460d9-160">Products that have **Draft** status when they are created must be activated before they can be added to quotations or sales orders.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="460d9-161">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="460d9-161">Template mapping in Data integration</span></span>

<span data-ttu-id="460d9-162">L'illustration suivante présente un exemple de modèle de mise en correspondance dans l'intégration des données.</span><span class="sxs-lookup"><span data-stu-id="460d9-162">The following illustration shows an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="460d9-163">La mise en correspondance indique quelles informations du champ sont synchronisées entre Sales et Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="460d9-163">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

![Mise en correspondance de modèles dans l'intégrateur de données](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a><span data-ttu-id="460d9-165">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="460d9-165">Related topics</span></span>

[<span data-ttu-id="460d9-166">Prospect en disponibilités</span><span class="sxs-lookup"><span data-stu-id="460d9-166">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="460d9-167">Synchroniser directement les comptes provenant du module Sales sur les clients de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="460d9-167">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="460d9-168">Synchroniser directement les contacts de Sales avec les contacts ou clients de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="460d9-168">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="460d9-169">Synchroniser directement les en-têtes et les lignes de commande client provenant du module Finance and Operations sur Sales</span><span class="sxs-lookup"><span data-stu-id="460d9-169">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="460d9-170">Synchroniser les en-têtes et les lignes de facture client provenant directement du module Finance and Operations avec Sales</span><span class="sxs-lookup"><span data-stu-id="460d9-170">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)




