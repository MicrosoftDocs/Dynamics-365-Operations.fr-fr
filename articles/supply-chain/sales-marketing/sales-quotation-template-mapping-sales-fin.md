---
title: "Synchroniser les en-têtes et les lignes de devis de vente directement entre Sales et Finance and Operations"
description: "Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de devis de vente directement entre Microsoft Dynamics 365 for Sales et Microsoft Dynamics 365 for Finance and Operations."
author: ChristianRytt
manager: AnnBe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 77b15a51073bf923f09a4a0e83ee5b2642eec4af
ms.contentlocale: fr-fr
ms.lasthandoff: 08/07/2018

---

# <a name="synchronize-sales-quotation-headers-and-lines-directly-from-sales-to-finance-and-operations"></a><span data-ttu-id="33344-103">Synchroniser les en-têtes et les lignes de devis de vente directement entre Sales et Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="33344-103">Synchronize sales quotation headers and lines directly from Sales to Finance and Operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="33344-104">Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de devis de vente directement entre Microsoft Dynamics 365 for Sales et Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="33344-104">The topic discusses the templates and underlying tasks that are used to synchronize sales quotation headers and lines directly from Microsoft Dynamics 365 for Sales to Microsoft Dynamics 365 for Finance and Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="33344-105">Avant d'utiliser le prospect pour une solution de disponibilités, vous devez connaître l'[intégration de données Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="33344-105">Before you can use the Prospect to cash solution, you should be familiar with [Dynamics 365 Data integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span>

## <a name="template-and-tasks"></a><span data-ttu-id="33344-106">Modèle et tâches</span><span class="sxs-lookup"><span data-stu-id="33344-106">Template and tasks</span></span>

<span data-ttu-id="33344-107">Le modèle et les tâches sous-jacentes suivants sont utilisés pour synchroniser les en-têtes et lignes de devis directement entre Sales et Finance and Operations :</span><span class="sxs-lookup"><span data-stu-id="33344-107">The following template and underlying tasks are used to synchronize sales quotation headers and lines directly from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="33344-108">**Nom du modèle dans l'intégration des données :** Devis de vente (entre Sales et Fin and Ops) - Direct</span><span class="sxs-lookup"><span data-stu-id="33344-108">**Name of the template in Data integration:** Sales Quotes (Sales to Fin and Ops) - Direct</span></span>
- <span data-ttu-id="33344-109">**Noms des tâches dans le projet d'intégration de données :**</span><span class="sxs-lookup"><span data-stu-id="33344-109">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="33344-110">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="33344-110">QuoteHeader</span></span>
    - <span data-ttu-id="33344-111">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="33344-111">QuoteLine</span></span>

<span data-ttu-id="33344-112">Les tâches suivantes de synchronisation sont requises avant que la synchronisation des en-têtes et des lignes de devis puisse être entreprise :</span><span class="sxs-lookup"><span data-stu-id="33344-112">The following synchronization tasks are required before synchronization of sales quotation headers and lines can occur:</span></span>

- <span data-ttu-id="33344-113">Produits (entre Fin and Ops et Sales) - Direct</span><span class="sxs-lookup"><span data-stu-id="33344-113">Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="33344-114">Comptes (entre Sales et Fin and Ops) - Direct (en cas d'utilisation)</span><span class="sxs-lookup"><span data-stu-id="33344-114">Accounts (Sales to Fin and Ops) - Direct (if used)</span></span>
- <span data-ttu-id="33344-115">Contacts vers Clients (entre Sales et Fin and Ops) - Direct (en cas d'utilisation)</span><span class="sxs-lookup"><span data-stu-id="33344-115">Contacts to Customers (Sales to Fin and Ops) - Direct (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="33344-116">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="33344-116">Entity set</span></span>

| <span data-ttu-id="33344-117">Vente</span><span class="sxs-lookup"><span data-stu-id="33344-117">Sales</span></span>        | <span data-ttu-id="33344-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="33344-118">Finance and Operations</span></span>     |
|--------------|----------------------------|
| <span data-ttu-id="33344-119">Citations</span><span class="sxs-lookup"><span data-stu-id="33344-119">Quotes</span></span>       | <span data-ttu-id="33344-120">En-tête de devis de vente CDS</span><span class="sxs-lookup"><span data-stu-id="33344-120">CDS sales quotation header</span></span> |
| <span data-ttu-id="33344-121">QuoteDetails</span><span class="sxs-lookup"><span data-stu-id="33344-121">QuoteDetails</span></span> | <span data-ttu-id="33344-122">Lignes de devis de vente CDS</span><span class="sxs-lookup"><span data-stu-id="33344-122">CDS sales quotation lines</span></span>  |

## <a name="entity-flow"></a><span data-ttu-id="33344-123">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="33344-123">Entity flow</span></span>

<span data-ttu-id="33344-124">Les devis sont créés dans Sales et synchronisés avec Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="33344-124">Sales quotations are created in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="33344-125">Les devis sont synchronisés uniquement dans Sales si les conditions suivantes sont réunies :</span><span class="sxs-lookup"><span data-stu-id="33344-125">Sales quotations from Sales are synchronized only if the following conditions are met:</span></span>

- <span data-ttu-id="33344-126">Tous les produits sur les devis de vente sont mis à jour en externe.</span><span class="sxs-lookup"><span data-stu-id="33344-126">All quote products on the sales quotation are externally maintained.</span></span>
- <span data-ttu-id="33344-127">Une fois que vous avez cliqué sur **Activer le devis**, le devis de vente est actif.</span><span class="sxs-lookup"><span data-stu-id="33344-127">After you click **Activate quote**, the sales quotation is active.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="33344-128">Prospect pour une solution de disponibilités pour Sales</span><span class="sxs-lookup"><span data-stu-id="33344-128">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="33344-129">Le champ **A des produits mis à jour en externe uniquement** a été ajouté à l'entité **Devis** pour effectuer le suivi uniformément si le devis consiste entièrement en produits mis à jour en externe.</span><span class="sxs-lookup"><span data-stu-id="33344-129">The **Has Externally Maintained Products Only** field has been added to the **Quote** entity to consistently track whether the sales quotation consists entirely of externally maintained products.</span></span> <span data-ttu-id="33344-130">Si un devis comporte uniquement des produits mis à jour en externe, les produits sont mis à jour dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="33344-130">If a sales quotation has only externally maintained products, the products are maintained in Finance and Operations.</span></span> <span data-ttu-id="33344-131">Ceci permet de garantir que vous ne tenterez pas de synchroniser les lignes de devis ayant des produits qui sont inconnus de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="33344-131">This behavior helps guarantee that you don't try to synchronize sales quotation lines that have products that are unknown to Finance and Operations.</span></span>

<span data-ttu-id="33344-132">Tous les produits du devis de vente sont mis à jour avec les informations **A des produits mis à jour uniquement en externe** de l'en-tête du devis de vente.</span><span class="sxs-lookup"><span data-stu-id="33344-132">All quote products on the sales quotation are updated with the **Has Externally Maintained Products Only** information from the sales quotation header.</span></span> <span data-ttu-id="33344-133">Ces informations figurent dans le champ **Le devis a des produits mis à jour uniquement en externe** sur l'entité **QuoteDetails** .</span><span class="sxs-lookup"><span data-stu-id="33344-133">This information is found in the **Quote Has Externally Maintained Products Only** field on the **QuoteDetails** entity.</span></span>

<span data-ttu-id="33344-134">Une remise peut être ajoutée au produit du devis et sera synchronisée avec Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="33344-134">A discount can be added to the quote product and will be synchronized to Finance and Operations.</span></span> <span data-ttu-id="33344-135">Les champs **Remise**, **Frais** et **Taxe** sont de l'en-tête sont contrôlés par un paramétrage complexe dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="33344-135">The **Discount**, **Charges**, and **Tax** fields on the header are controlled by a setup in Finance and Operations.</span></span> <span data-ttu-id="33344-136">Actuellement, ce paramétrage ne prend pas en charge la mise en correspondance d'intégration.</span><span class="sxs-lookup"><span data-stu-id="33344-136">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="33344-137">Dans la conception actuelle, les champs **Prix**, **Remise**, **Charge**, et **Taxe** sont mis à jour et gérés dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="33344-137">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are maintained and handled in Finance and Operations.</span></span>

<span data-ttu-id="33344-138">Dans Sales, la solution rend les champs suivants en lecture seule, car les valeurs ne sont pas synchronisées avec Finance and Operations :</span><span class="sxs-lookup"><span data-stu-id="33344-138">In Sales, the solution makes the following fields read-only, because the values aren't synchronized to Finance and Operations:</span></span>

- <span data-ttu-id="33344-139">Champs en lecture seule sur l'en-tête de devis : **% de remise**, **Remise** et **Volume de transport**</span><span class="sxs-lookup"><span data-stu-id="33344-139">Read-only fields on the sales quotation header: **Discount %**, **Discount**, and **Freight Amount**</span></span>
- <span data-ttu-id="33344-140">Champs en lecture seule sur les produits du devis : **Taxe**</span><span class="sxs-lookup"><span data-stu-id="33344-140">Read-only fields on quote products: **Tax**</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="33344-141">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="33344-141">Preconditions and mapping setup</span></span>

<span data-ttu-id="33344-142">Avant de synchroniser les devis de vente, il est important de mettre les systèmes à jour avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="33344-142">Before sales quotations are synchronized, it's important that you update the following settings.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="33344-143">Configuration dans Sales</span><span class="sxs-lookup"><span data-stu-id="33344-143">Setup in Sales</span></span>

- <span data-ttu-id="33344-144">Vérifiez que les autorisations sont bien définies pour l'équipe à laquelle l'utilisateur est affecté (à partir de votre connexion dans Sales).</span><span class="sxs-lookup"><span data-stu-id="33344-144">Make sure that permissions are set up for the team that the user from your connection set in Sales is assigned to.</span></span> <span data-ttu-id="33344-145">Si vous utilisez des données de démonstration, généralement l'utilisateur dispose de l'accès Administrateur, mais pas l'équipe.</span><span class="sxs-lookup"><span data-stu-id="33344-145">If you're using demo data, the user usually has admin access, but the team doesn't have admin access.</span></span> <span data-ttu-id="33344-146">Si l'équipe n'a pas accès d'administrateur lors de l'exécution du projet à partir de l'intégrateur de données, vous recevrez un message d'erreur indiquant que l'équipe principale est manquante.</span><span class="sxs-lookup"><span data-stu-id="33344-146">If the team doesn't have admin access when you run the project from Data integration, you will receive an error message that states that the Principal team is missing.</span></span>

    <span data-ttu-id="33344-147">Pour définir les autorisations pour l'équipe, allez dans &gt; **Paramètres** **Sécurité** &gt; **Équipes**, puis sélectionnez l'équipe appropriée.</span><span class="sxs-lookup"><span data-stu-id="33344-147">To set up permissions for the team, go to **Settings** &gt; **Security** &gt; **Teams**, and select the relevant team.</span></span> <span data-ttu-id="33344-148">Sélectionnez **Gestion des rôles**, puis sélectionnez un rôle qui a les autorisations souhaitées, tel que **Administrateur système**.</span><span class="sxs-lookup"><span data-stu-id="33344-148">Select **Manage Roles**, and then select a role that has the desired permissions, such as **System Administrator**.</span></span>

- <span data-ttu-id="33344-149">Allez dans **Paramètres** &gt; **Administration** &gt; **Paramètres système** &gt; **Sales**, et assurez-vous que les paramètres suivants sont utilisés :</span><span class="sxs-lookup"><span data-stu-id="33344-149">Go to **Settings** &gt; **Administration** &gt; **System settings** &gt; **Sales**, and make sure that the following settings are used:</span></span>

    - <span data-ttu-id="33344-150">L'option **Utiliser le système de calcul du prix du système** est définie **Oui**.</span><span class="sxs-lookup"><span data-stu-id="33344-150">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
    - <span data-ttu-id="33344-151">Le champ **Mode de calcul de remise** est défini sur **Ligne article**.</span><span class="sxs-lookup"><span data-stu-id="33344-151">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="33344-152">Paramétrage du projet d'intégration des données</span><span class="sxs-lookup"><span data-stu-id="33344-152">Setup in the Data integration project</span></span>

#### <a name="quoteheader"></a><span data-ttu-id="33344-153">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="33344-153">QuoteHeader</span></span>

- <span data-ttu-id="33344-154">Assurez-vous que la mise en correspondance nécessaire existe pour **Shipto\_country** avec **DeliveryAddressCountryRegionISOCode**.</span><span class="sxs-lookup"><span data-stu-id="33344-154">Make sure that the required mapping exists for **Shipto\_country** to **DeliveryAddressCountryRegionISOCode**.</span></span> <span data-ttu-id="33344-155">Dans la mise en correspondance des valeurs, vous pouvez définir une valeur par défaut qui est utilisée si la valeur reste vide.</span><span class="sxs-lookup"><span data-stu-id="33344-155">In the value map, you can define a default value that is used if the value is left blank.</span></span> <span data-ttu-id="33344-156">Laissez le côté gauche vide, puis définissez le côté droit sur le pays ou la région souhaité(e).</span><span class="sxs-lookup"><span data-stu-id="33344-156">Just leave the left side blank, and set the right side to the desired country or region.</span></span> <span data-ttu-id="33344-157">Ainsi, vous n'avez pas à entrer le pays ou la région pour des commandes nationales.</span><span class="sxs-lookup"><span data-stu-id="33344-157">In this way, you don't have to type the country or region for national orders.</span></span>

    <span data-ttu-id="33344-158">La valeur du modèle est une mise en correspondance des valeurs où plusieurs pays ou régions sont mis en correspondance et où une valeur nulle correspond à une valeur **US**.</span><span class="sxs-lookup"><span data-stu-id="33344-158">The template value is a value map where several countries or regions are mapped, and where a blank value equals a value of **US**.</span></span>

#### <a name="quoteline"></a><span data-ttu-id="33344-159">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="33344-159">QuoteLine</span></span>

- <span data-ttu-id="33344-160">Assurez-vous que la mise en correspondance des valeurs requise existe pour **SalesUnitSymbol** dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="33344-160">Make sure that the required value map exists for **SalesUnitSymbol** in Finance and Operations.</span></span>
- <span data-ttu-id="33344-161">Vérifiez que les unités nécessaires sont définies dans Sales.</span><span class="sxs-lookup"><span data-stu-id="33344-161">Make sure that the required units are defined in Sales.</span></span>

    <span data-ttu-id="33344-162">Une valeur de modèle ayant une mise en correspondance des valeurs est définie pour **oumid.name** sur **SalesUnitSymbol**.</span><span class="sxs-lookup"><span data-stu-id="33344-162">A template value that has a value map is defined for **oumid.name** to **SalesUnitSymbol**.</span></span>

- <span data-ttu-id="33344-163">Facultatif : Vous pouvez ajouter les mises en correspondance suivantes pour vérifier que les lignes de devis de vente sont importées dans Finance and Operations s'il n'existe aucune information par défaut du client ou du produit :</span><span class="sxs-lookup"><span data-stu-id="33344-163">Optional: You can add the following mappings to help guarantee that sales quotation lines are imported into Finance and Operations if there is no default information from either the customer or the product:</span></span>

    - <span data-ttu-id="33344-164">**SiteId** – Un site est requis pour générer des lignes de devis et de commande client dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="33344-164">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="33344-165">Il n'existe aucun modèle de valeur par défaut pour **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="33344-165">There is no default template value for **SiteId**.</span></span>
    - <span data-ttu-id="33344-166">**WarehouseId** – Un entrepôt est requis pour traiter des lignes de devis et de commande client dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="33344-166">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="33344-167">Il n'existe aucun modèle de valeur par défaut pour **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="33344-167">There is no default template value for **WarehouseId**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="33344-168">Mise en correspondance de modèles dans l'intégrateur de données</span><span class="sxs-lookup"><span data-stu-id="33344-168">Template mapping in data integrator</span></span>

> [!NOTE]
> - <span data-ttu-id="33344-169">Les champs **Remise**, **Frais** et **Taxe** sont contrôlés par un paramétrage complexe dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="33344-169">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="33344-170">Actuellement, ce paramétrage ne prend pas en charge la mise en correspondance d'intégration.</span><span class="sxs-lookup"><span data-stu-id="33344-170">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="33344-171">Dans la conception actuelle, les champs **Prix**, **Remise**, **Charge**, et **Taxe** sont gérés par Finances and Operations.</span><span class="sxs-lookup"><span data-stu-id="33344-171">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are handled by Finance and Operations.</span></span>
> - <span data-ttu-id="33344-172">Les champs **Conditions de paiement**, **Conditions de transport**, **Conditions de livraison**, **Méthode d'expédition** et **Mode de distribution** ne font pas partie des mises en correspondance par défaut.</span><span class="sxs-lookup"><span data-stu-id="33344-172">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="33344-173">Pour mettre en correspondance ces champs, vous devez paramétrer une mise en correspondance des valeurs spécifique aux données des organisations entre lesquelles l'entité est synchronisée.</span><span class="sxs-lookup"><span data-stu-id="33344-173">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="33344-174">Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l'intégrateur de données.</span><span class="sxs-lookup"><span data-stu-id="33344-174">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="33344-175">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="33344-175">QuoteHeader</span></span>

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-quotation-direct-template-mapping-data-integrator-1.png)

### <a name="quoteline"></a><span data-ttu-id="33344-177">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="33344-177">QuoteLine</span></span>

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-quotation-direct-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="33344-179">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="33344-179">Related topics</span></span>

[<span data-ttu-id="33344-180">Prospect en disponibilités</span><span class="sxs-lookup"><span data-stu-id="33344-180">Prospect to cash</span></span>](prospect-to-cash.md)


