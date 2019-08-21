---
title: Synchroniser les en-têtes et les lignes de devis de vente directement entre Sales et Finance and Operations
description: La rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de devis de vente directement depuis Microsoft Dynamics 365 for Sales vers Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2018
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
ms.openlocfilehash: 0894f4728d3f1df21db130cd9e87d9881726e7fa
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2019
ms.locfileid: "1743369"
---
# <a name="synchronize-sales-quotation-headers-and-lines-directly-from-sales-to-finance-and-operations"></a><span data-ttu-id="06304-103">Synchroniser directement les en-têtes et les lignes de devis provenant du module Sales sur Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="06304-103">Synchronize sales quotation headers and lines directly from Sales to Finance and Operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="06304-104">La rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de devis de vente directement depuis Microsoft Dynamics 365 for Sales vers Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="06304-104">The topic discusses the templates and underlying tasks that are used to synchronize sales quotation headers and lines directly from Microsoft Dynamics 365 for Sales to Microsoft Dynamics 365 for Finance and Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="06304-105">Avant d'utiliser le prospect pour une solution de disponibilités, vous devez bien connaître la rubrique [Intégrer des données dans Common Data Service pour applications](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="06304-105">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Common Data Service for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="06304-106">Flux de données dans Prospect en disponibilités</span><span class="sxs-lookup"><span data-stu-id="06304-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="06304-107">La solution Prospect en disponibilités utilise la fonction d'intégration de données pour synchroniser les données entre plusieurs instances de Finance and Operations et Sales.</span><span class="sxs-lookup"><span data-stu-id="06304-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="06304-108">Les modèles Prospect en disponibilités disponibles avec la fonction d'intégration de données activent le flux de données pour les comptes, contacts, produits, devis de vente, commandes client et factures client entre Finance and Operations et Sales.</span><span class="sxs-lookup"><span data-stu-id="06304-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data for accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="06304-109">L'illustration ci-dessous indique comment les données sont synchronisées entre Finance and Operations et Sales.</span><span class="sxs-lookup"><span data-stu-id="06304-109">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="06304-110">[![Flux de données dans Prospect en disponibilités](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="06304-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="template-and-tasks"></a><span data-ttu-id="06304-111">Modèle et tâches</span><span class="sxs-lookup"><span data-stu-id="06304-111">Template and tasks</span></span>

<span data-ttu-id="06304-112">Le modèle et les tâches sous-jacentes suivants sont utilisés pour synchroniser les en-têtes et lignes de devis directement entre Sales et Finance and Operations :</span><span class="sxs-lookup"><span data-stu-id="06304-112">The following template and underlying tasks are used to synchronize sales quotation headers and lines directly from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="06304-113">**Nom du modèle dans l'intégration des données :** Devis de vente (entre Sales et Fin and Ops) - Direct</span><span class="sxs-lookup"><span data-stu-id="06304-113">**Name of the template in Data integration:** Sales Quotes (Sales to Fin and Ops) - Direct</span></span>
- <span data-ttu-id="06304-114">**Noms des tâches dans le projet d'intégration de données :**</span><span class="sxs-lookup"><span data-stu-id="06304-114">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="06304-115">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="06304-115">QuoteHeader</span></span>
    - <span data-ttu-id="06304-116">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="06304-116">QuoteLine</span></span>

<span data-ttu-id="06304-117">Les tâches suivantes de synchronisation sont requises avant que la synchronisation des en-têtes et des lignes de devis puisse être entreprise :</span><span class="sxs-lookup"><span data-stu-id="06304-117">The following synchronization tasks are required before synchronization of sales quotation headers and lines can occur:</span></span>

- <span data-ttu-id="06304-118">Produits (entre Fin and Ops et Sales) - Direct</span><span class="sxs-lookup"><span data-stu-id="06304-118">Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="06304-119">Comptes (entre Sales et Fin and Ops) - Direct (en cas d'utilisation)</span><span class="sxs-lookup"><span data-stu-id="06304-119">Accounts (Sales to Fin and Ops) - Direct (if used)</span></span>
- <span data-ttu-id="06304-120">Contacts vers Clients (entre Sales et Fin and Ops) - Direct (en cas d'utilisation)</span><span class="sxs-lookup"><span data-stu-id="06304-120">Contacts to Customers (Sales to Fin and Ops) - Direct (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="06304-121">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="06304-121">Entity set</span></span>

| <span data-ttu-id="06304-122">Vente</span><span class="sxs-lookup"><span data-stu-id="06304-122">Sales</span></span>        | <span data-ttu-id="06304-123">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="06304-123">Finance and Operations</span></span>     |
|--------------|----------------------------|
| <span data-ttu-id="06304-124">Citations</span><span class="sxs-lookup"><span data-stu-id="06304-124">Quotes</span></span>       | <span data-ttu-id="06304-125">En-tête de devis de vente CDS</span><span class="sxs-lookup"><span data-stu-id="06304-125">CDS sales quotation header</span></span> |
| <span data-ttu-id="06304-126">QuoteDetails</span><span class="sxs-lookup"><span data-stu-id="06304-126">QuoteDetails</span></span> | <span data-ttu-id="06304-127">Lignes de devis de vente CDS</span><span class="sxs-lookup"><span data-stu-id="06304-127">CDS sales quotation lines</span></span>  |

## <a name="entity-flow"></a><span data-ttu-id="06304-128">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="06304-128">Entity flow</span></span>

<span data-ttu-id="06304-129">Les devis sont créés dans Sales et synchronisés avec Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="06304-129">Sales quotations are created in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="06304-130">Les devis sont synchronisés uniquement dans Sales si les conditions suivantes sont réunies :</span><span class="sxs-lookup"><span data-stu-id="06304-130">Sales quotations from Sales are synchronized only if the following conditions are met:</span></span>

- <span data-ttu-id="06304-131">Tous les produits sur les devis de vente sont mis à jour en externe.</span><span class="sxs-lookup"><span data-stu-id="06304-131">All quote products on the sales quotation are externally maintained.</span></span>
- <span data-ttu-id="06304-132">Une fois que vous avez cliqué sur **Activer le devis**, le devis de vente est actif.</span><span class="sxs-lookup"><span data-stu-id="06304-132">After you click **Activate quote**, the sales quotation is active.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="06304-133">Prospect pour une solution de disponibilités pour Sales</span><span class="sxs-lookup"><span data-stu-id="06304-133">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="06304-134">Le champ **A des produits mis à jour en externe uniquement** a été ajouté à l'entité **Devis** pour effectuer le suivi uniformément si le devis consiste entièrement en produits mis à jour en externe.</span><span class="sxs-lookup"><span data-stu-id="06304-134">The **Has Externally Maintained Products Only** field has been added to the **Quote** entity to consistently track whether the sales quotation consists entirely of externally maintained products.</span></span> <span data-ttu-id="06304-135">Si un devis comporte uniquement des produits mis à jour en externe, les produits sont mis à jour dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="06304-135">If a sales quotation has only externally maintained products, the products are maintained in Finance and Operations.</span></span> <span data-ttu-id="06304-136">Ceci permet de garantir que vous ne tenterez pas de synchroniser les lignes de devis ayant des produits qui sont inconnus de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="06304-136">This behavior helps guarantee that you don't try to synchronize sales quotation lines that have products that are unknown to Finance and Operations.</span></span>

<span data-ttu-id="06304-137">Tous les produits du devis de vente sont mis à jour avec les informations **A des produits mis à jour uniquement en externe** de l'en-tête du devis de vente.</span><span class="sxs-lookup"><span data-stu-id="06304-137">All quote products on the sales quotation are updated with the **Has Externally Maintained Products Only** information from the sales quotation header.</span></span> <span data-ttu-id="06304-138">Ces informations figurent dans le champ **Le devis a des produits mis à jour uniquement en externe** sur l'entité **QuoteDetails** .</span><span class="sxs-lookup"><span data-stu-id="06304-138">This information is found in the **Quote Has Externally Maintained Products Only** field on the **QuoteDetails** entity.</span></span>

<span data-ttu-id="06304-139">Une remise peut être ajoutée au produit du devis et sera synchronisée avec Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="06304-139">A discount can be added to the quote product and will be synchronized to Finance and Operations.</span></span> <span data-ttu-id="06304-140">Les champs **Remise**, **Frais** et **Taxe** sont de l'en-tête sont contrôlés par un paramétrage complexe dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="06304-140">The **Discount**, **Charges**, and **Tax** fields on the header are controlled by a setup in Finance and Operations.</span></span> <span data-ttu-id="06304-141">Actuellement, ce paramétrage ne prend pas en charge la mise en correspondance d'intégration.</span><span class="sxs-lookup"><span data-stu-id="06304-141">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="06304-142">Dans la conception actuelle, les champs **Prix**, **Remise**, **Charge**, et **Taxe** sont mis à jour et gérés dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="06304-142">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are maintained and handled in Finance and Operations.</span></span>

<span data-ttu-id="06304-143">Dans Sales, la solution rend les champs suivants en lecture seule, car les valeurs ne sont pas synchronisées avec Finance and Operations :</span><span class="sxs-lookup"><span data-stu-id="06304-143">In Sales, the solution makes the following fields read-only, because the values aren't synchronized to Finance and Operations:</span></span>

- <span data-ttu-id="06304-144">Champs en lecture seule sur l'en-tête de devis : **% de remise**, **Remise** et **Volume de transport**</span><span class="sxs-lookup"><span data-stu-id="06304-144">Read-only fields on the sales quotation header: **Discount %**, **Discount**, and **Freight Amount**</span></span>
- <span data-ttu-id="06304-145">Champs en lecture seule sur les produits du devis : **Taxe**</span><span class="sxs-lookup"><span data-stu-id="06304-145">Read-only fields on quote products: **Tax**</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="06304-146">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="06304-146">Preconditions and mapping setup</span></span>

<span data-ttu-id="06304-147">Avant de synchroniser les devis de vente, il est important de mettre les systèmes à jour avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="06304-147">Before sales quotations are synchronized, it's important that you update the following settings.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="06304-148">Configuration dans Sales</span><span class="sxs-lookup"><span data-stu-id="06304-148">Setup in Sales</span></span>

- <span data-ttu-id="06304-149">Vérifiez que les autorisations sont bien définies pour l'équipe à laquelle l'utilisateur est affecté (à partir de votre connexion dans Sales).</span><span class="sxs-lookup"><span data-stu-id="06304-149">Make sure that permissions are set up for the team that the user from your connection set in Sales is assigned to.</span></span> <span data-ttu-id="06304-150">Si vous utilisez des données de démonstration, généralement l'utilisateur dispose de l'accès Administrateur, mais pas l'équipe.</span><span class="sxs-lookup"><span data-stu-id="06304-150">If you're using demo data, the user usually has admin access, but the team doesn't have admin access.</span></span> <span data-ttu-id="06304-151">Si l'équipe n'a pas accès d'administrateur lors de l'exécution du projet à partir de l'intégrateur de données, vous recevrez un message d'erreur indiquant que l'équipe principale est manquante.</span><span class="sxs-lookup"><span data-stu-id="06304-151">If the team doesn't have admin access when you run the project from Data integration, you will receive an error message that states that the Principal team is missing.</span></span>

    <span data-ttu-id="06304-152">Pour définir les autorisations pour l'équipe, allez dans &gt; **Paramètres** **Sécurité** &gt; **Équipes**, puis sélectionnez l'équipe appropriée.</span><span class="sxs-lookup"><span data-stu-id="06304-152">To set up permissions for the team, go to **Settings** &gt; **Security** &gt; **Teams**, and select the relevant team.</span></span> <span data-ttu-id="06304-153">Sélectionnez **Gestion des rôles**, puis sélectionnez un rôle qui a les autorisations souhaitées, tel que **Administrateur système**.</span><span class="sxs-lookup"><span data-stu-id="06304-153">Select **Manage Roles**, and then select a role that has the desired permissions, such as **System Administrator**.</span></span>

- <span data-ttu-id="06304-154">Allez dans **Paramètres** &gt; **Administration** &gt; **Paramètres système** &gt; **Sales**, et assurez-vous que les paramètres suivants sont utilisés :</span><span class="sxs-lookup"><span data-stu-id="06304-154">Go to **Settings** &gt; **Administration** &gt; **System settings** &gt; **Sales**, and make sure that the following settings are used:</span></span>

    - <span data-ttu-id="06304-155">L'option **Utiliser le système de calcul du prix du système** est définie **Oui**.</span><span class="sxs-lookup"><span data-stu-id="06304-155">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
    - <span data-ttu-id="06304-156">Le champ **Mode de calcul de remise** est défini sur **Ligne article**.</span><span class="sxs-lookup"><span data-stu-id="06304-156">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="06304-157">Paramétrage du projet d'intégration des données</span><span class="sxs-lookup"><span data-stu-id="06304-157">Setup in the Data integration project</span></span>

#### <a name="quoteheader"></a><span data-ttu-id="06304-158">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="06304-158">QuoteHeader</span></span>

- <span data-ttu-id="06304-159">Assurez-vous que la mise en correspondance nécessaire existe pour **Shipto\_country** avec **DeliveryAddressCountryRegionISOCode**.</span><span class="sxs-lookup"><span data-stu-id="06304-159">Make sure that the required mapping exists for **Shipto\_country** to **DeliveryAddressCountryRegionISOCode**.</span></span> <span data-ttu-id="06304-160">Dans la mise en correspondance des valeurs, vous pouvez définir une valeur par défaut qui est utilisée si la valeur reste vide.</span><span class="sxs-lookup"><span data-stu-id="06304-160">In the value map, you can define a default value that is used if the value is left blank.</span></span> <span data-ttu-id="06304-161">Laissez le côté gauche vide, puis définissez le côté droit sur le pays ou la région souhaité(e).</span><span class="sxs-lookup"><span data-stu-id="06304-161">Just leave the left side blank, and set the right side to the desired country or region.</span></span> <span data-ttu-id="06304-162">Ainsi, vous n'avez pas à entrer le pays ou la région pour des commandes nationales.</span><span class="sxs-lookup"><span data-stu-id="06304-162">In this way, you don't have to type the country or region for national orders.</span></span>

    <span data-ttu-id="06304-163">La valeur du modèle est une mise en correspondance des valeurs où plusieurs pays ou régions sont mis en correspondance et où une valeur nulle correspond à une valeur **US**.</span><span class="sxs-lookup"><span data-stu-id="06304-163">The template value is a value map where several countries or regions are mapped, and where a blank value equals a value of **US**.</span></span>

#### <a name="quoteline"></a><span data-ttu-id="06304-164">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="06304-164">QuoteLine</span></span>

- <span data-ttu-id="06304-165">Assurez-vous que la mise en correspondance des valeurs requise existe pour **SalesUnitSymbol** dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="06304-165">Make sure that the required value map exists for **SalesUnitSymbol** in Finance and Operations.</span></span>
- <span data-ttu-id="06304-166">Vérifiez que les unités nécessaires sont définies dans Sales.</span><span class="sxs-lookup"><span data-stu-id="06304-166">Make sure that the required units are defined in Sales.</span></span>

    <span data-ttu-id="06304-167">Une valeur de modèle ayant une mise en correspondance des valeurs est définie pour **oumid.name** sur **SalesUnitSymbol**.</span><span class="sxs-lookup"><span data-stu-id="06304-167">A template value that has a value map is defined for **oumid.name** to **SalesUnitSymbol**.</span></span>

- <span data-ttu-id="06304-168">Facultatif : Vous pouvez ajouter les mises en correspondance suivantes pour vérifier que les lignes de devis de vente sont importées dans Finance and Operations s'il n'existe aucune information par défaut du client ou du produit :</span><span class="sxs-lookup"><span data-stu-id="06304-168">Optional: You can add the following mappings to help guarantee that sales quotation lines are imported into Finance and Operations if there is no default information from either the customer or the product:</span></span>

    - <span data-ttu-id="06304-169">**SiteId** – Un site est requis pour générer des lignes de devis et de commande client dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="06304-169">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="06304-170">Il n'existe aucun modèle de valeur par défaut pour **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="06304-170">There is no default template value for **SiteId**.</span></span>
    - <span data-ttu-id="06304-171">**WarehouseId** – Un entrepôt est requis pour traiter des lignes de devis et de commande client dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="06304-171">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="06304-172">Il n'existe aucun modèle de valeur par défaut pour **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="06304-172">There is no default template value for **WarehouseId**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="06304-173">Mise en correspondance de modèles dans l'intégrateur de données</span><span class="sxs-lookup"><span data-stu-id="06304-173">Template mapping in data integrator</span></span>

> [!NOTE]
> - <span data-ttu-id="06304-174">Les champs **Remise**, **Frais** et **Taxe** sont contrôlés par un paramétrage complexe dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="06304-174">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="06304-175">Actuellement, ce paramétrage ne prend pas en charge la mise en correspondance d'intégration.</span><span class="sxs-lookup"><span data-stu-id="06304-175">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="06304-176">Dans la conception actuelle, les champs **Prix**, **Remise**, **Charge**, et **Taxe** sont gérés par Finances and Operations.</span><span class="sxs-lookup"><span data-stu-id="06304-176">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are handled by Finance and Operations.</span></span>
> - <span data-ttu-id="06304-177">Les champs **Conditions de paiement**, **Conditions de transport**, **Conditions de livraison**, **Méthode d'expédition** et **Mode de distribution** ne font pas partie des mises en correspondance par défaut.</span><span class="sxs-lookup"><span data-stu-id="06304-177">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="06304-178">Pour mettre en correspondance ces champs, vous devez paramétrer une mise en correspondance des valeurs spécifique aux données des organisations entre lesquelles l'entité est synchronisée.</span><span class="sxs-lookup"><span data-stu-id="06304-178">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="06304-179">Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l'intégrateur de données.</span><span class="sxs-lookup"><span data-stu-id="06304-179">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="06304-180">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="06304-180">QuoteHeader</span></span>

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-quotation-direct-template-mapping-data-integrator-1.png)

### <a name="quoteline"></a><span data-ttu-id="06304-182">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="06304-182">QuoteLine</span></span>

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-quotation-direct-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="06304-184">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="06304-184">Related topics</span></span>

[<span data-ttu-id="06304-185">Prospect en disponibilités</span><span class="sxs-lookup"><span data-stu-id="06304-185">Prospect to cash</span></span>](prospect-to-cash.md)

