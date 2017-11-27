---
title: "Synchroniser les en-têtes et les lignes de commande client directement entre le module Finance and Operations et Sales"
description: "Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de commande client directement entre Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition et Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2017
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
ms.openlocfilehash: cc0be50552ae680ba5291e72b7c482ee67e1e70e
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="synchronize-sales-order-headers-and-lines-directly-from-finance-and-operations-to-sales"></a><span data-ttu-id="b24b0-103">Synchroniser les en-têtes et les lignes de commande client directement entre le module Finance and Operations et Sales</span><span class="sxs-lookup"><span data-stu-id="b24b0-103">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="b24b0-104">Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les en-têtes et les lignes de commande client directement entre Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition et Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="b24b0-104">This topic discusses the templates and underlying tasks that are used to synchronize sales order headers and lines directly from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, to Microsoft Dynamics 365 for Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="b24b0-105">Flux de données dans Prospect en disponibilités</span><span class="sxs-lookup"><span data-stu-id="b24b0-105">Data flow in Prospect to cash</span></span>

<span data-ttu-id="b24b0-106">La solution Prospect en disponibilités utilise la fonction d'intégration de données pour synchroniser les données entre plusieurs instances de Finance and Operations et Sales.</span><span class="sxs-lookup"><span data-stu-id="b24b0-106">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="b24b0-107">Les modèles de prospects en disponibilités disponibles avec la fonction d'intégration de données activent le flux de données relatifs aux comptes, contacts, produits, devis de vente, commandes client et factures client entre Finance and Operations et Sales.</span><span class="sxs-lookup"><span data-stu-id="b24b0-107">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="b24b0-108">L'illustration ci-dessous indique comment les données sont synchronisées entre Finance and Operations et Sales.</span><span class="sxs-lookup"><span data-stu-id="b24b0-108">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="b24b0-109">[![Flux de données dans Prospect en disponibilités](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="b24b0-109">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="b24b0-110">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="b24b0-110">Templates and tasks</span></span>

<span data-ttu-id="b24b0-111">Pour accéder à des modèles disponibles, ouvrir [Centre d'administrateur PowerApps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="b24b0-111">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="b24b0-112">Sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner les modèles publics.</span><span class="sxs-lookup"><span data-stu-id="b24b0-112">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="b24b0-113">Le modèle et les tâches sous-jacentes suivants sont utilisés pour synchroniser les en-têtes et lignes de commande client entre Finance and Operations et Sales :</span><span class="sxs-lookup"><span data-stu-id="b24b0-113">The following template and underlying tasks are used to synchronize sales order headers and lines from Finance and Operations to Sales:</span></span>

- <span data-ttu-id="b24b0-114">**Nom du modèle dans l'intégration des données :** Commandes client (entre Fin and Ops et Sales) - Direct</span><span class="sxs-lookup"><span data-stu-id="b24b0-114">**Name of the template in Data integration:** Sales Orders (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="b24b0-115">**Noms des tâches dans le projet d'intégration de données :**</span><span class="sxs-lookup"><span data-stu-id="b24b0-115">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="b24b0-116">OrderHeader</span><span class="sxs-lookup"><span data-stu-id="b24b0-116">OrderHeader</span></span>
    - <span data-ttu-id="b24b0-117">OrderLine</span><span class="sxs-lookup"><span data-stu-id="b24b0-117">OrderLine</span></span>

<span data-ttu-id="b24b0-118">Les tâches suivantes de synchronisation sont requises avant que la synchronisation des en-têtes et des lignes de factures client puisse avoir lieu :</span><span class="sxs-lookup"><span data-stu-id="b24b0-118">The following synchronization tasks are required before synchronization of sales invoice headers and lines can occur:</span></span>

- <span data-ttu-id="b24b0-119">Produits (entre Fin and Ops et Sales) - Direct</span><span class="sxs-lookup"><span data-stu-id="b24b0-119">Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="b24b0-120">Comptes (entre Sales et Fin and Ops) - Direct (en cas d'utilisation)</span><span class="sxs-lookup"><span data-stu-id="b24b0-120">Accounts (Sales to Fin and Ops) - Direct (if used)</span></span>
- <span data-ttu-id="b24b0-121">Contacts vers Clients (entre Sales et Fin and Ops) - Direct (en cas d'utilisation)</span><span class="sxs-lookup"><span data-stu-id="b24b0-121">Contacts to Customers (Sales to Fin and Ops) - Direct (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="b24b0-122">Ensemble d'entités</span><span class="sxs-lookup"><span data-stu-id="b24b0-122">Entity set</span></span>

| <span data-ttu-id="b24b0-123">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b24b0-123">Finance and Operations</span></span>  | <span data-ttu-id="b24b0-124">Vente</span><span class="sxs-lookup"><span data-stu-id="b24b0-124">Sales</span></span>             |
|-------------------------|-------------------|
| <span data-ttu-id="b24b0-125">En-têtes de commande client CDS</span><span class="sxs-lookup"><span data-stu-id="b24b0-125">CDS sales order headers</span></span> | <span data-ttu-id="b24b0-126">SalesOrders</span><span class="sxs-lookup"><span data-stu-id="b24b0-126">SalesOrders</span></span>       |
| <span data-ttu-id="b24b0-127">Lignes de commande client CDS</span><span class="sxs-lookup"><span data-stu-id="b24b0-127">CDS sales order lines</span></span>   | <span data-ttu-id="b24b0-128">SalesOrderDetails</span><span class="sxs-lookup"><span data-stu-id="b24b0-128">SalesOrderDetails</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="b24b0-129">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="b24b0-129">Entity flow</span></span>

<span data-ttu-id="b24b0-130">Les commandes client sont créées dans Finance and Operations et synchronisées avec Sales.</span><span class="sxs-lookup"><span data-stu-id="b24b0-130">Sales orders are created in Finance and Operations and synchronized to Sales.</span></span>

<span data-ttu-id="b24b0-131">Les filtres du modèle aident à garantir que seules les commandes client appropriées sont incluses dans la synchronisation :</span><span class="sxs-lookup"><span data-stu-id="b24b0-131">Filters in the template help guarantee that only relevant sales orders are included in the synchronization:</span></span>

- <span data-ttu-id="b24b0-132">Sur la commande client, la commande et la facturation client provenant de Sales sont incluses dans la synchronisation.</span><span class="sxs-lookup"><span data-stu-id="b24b0-132">On the sales order, both the ordering customer and the invoicing customer that originate from Sales will be included in the synchronization.</span></span> <span data-ttu-id="b24b0-133">Dans Finance and Operations, les champs **OrderingCustomerIsExternallyMaintained** et **InvoiceCustomerIsExternallyMaintained** permettent de suivre la synchronisation dans les entités de données.</span><span class="sxs-lookup"><span data-stu-id="b24b0-133">In Finance and Operations, the **OrderingCustomerIsExternallyMaintained** and **InvoiceCustomerIsExternallyMaintained** fields are used to track the synchronization in the data entities.</span></span>
- <span data-ttu-id="b24b0-134">La commande client dans Finance and Operations doit être confirmée.</span><span class="sxs-lookup"><span data-stu-id="b24b0-134">The sales order in Finance and Operations must be confirmed.</span></span> <span data-ttu-id="b24b0-135">Seules les commandes client confirmées ou les commandes client dont le statut de traitement le plus élevé, par exemple, **Livré** ou **Facturé**, sont synchronisées avec Sales.</span><span class="sxs-lookup"><span data-stu-id="b24b0-135">Only confirmed sales orders or sales orders that have a higher processing status, such as **Shipped** or **Invoiced**, are synchronized to Sales.</span></span>
- <span data-ttu-id="b24b0-136">Après avoir créé ou modifié une commande client, le traitement par lots **Calcule les totaux de vente** dans Finance and Operations doit être exécuté.</span><span class="sxs-lookup"><span data-stu-id="b24b0-136">After a sales order is created or modified, the **Calculate sales totals** batch job in Finance and Operations must be run.</span></span> <span data-ttu-id="b24b0-137">Seules les commandes client où les totaux de vente sont calculés seront synchronisées avec Sales.</span><span class="sxs-lookup"><span data-stu-id="b24b0-137">Only sales orders where sales totals are calculated will be synchronized to Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="b24b0-138">Actuellement, la taxe associée aux frais dans l'en-tête de commande client n'est pas incluse dans la synchronisation entre Finance and Operations et Sales.</span><span class="sxs-lookup"><span data-stu-id="b24b0-138">Currently, tax that is related to charges on the sales order header isn't included in the synchronization from Finance and Operations to Sales.</span></span> <span data-ttu-id="b24b0-139">Sales ne prend pas en charge les informations fiscales au niveau de l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="b24b0-139">Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="b24b0-140">Toutefois, la taxe associée aux frais au niveau de la ligne est incluse dans la synchronisation.</span><span class="sxs-lookup"><span data-stu-id="b24b0-140">However, tax that is related to charges at the line level is included in the synchronization.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="b24b0-141">Prospect pour une solution de disponibilités pour Sales</span><span class="sxs-lookup"><span data-stu-id="b24b0-141">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="b24b0-142">De nouveaux champs sont ajoutés à l'entité **Commande** et s'affichent sur la page :</span><span class="sxs-lookup"><span data-stu-id="b24b0-142">New fields have been added to the **Order** entity and appear on the page:</span></span>

- <span data-ttu-id="b24b0-143">**Est conservé en externe** - Définissez cette option sur **Oui** lorsque la commande provient de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b24b0-143">**Is Maintained Externally** – Set this option to **Yes** when the order is coming from Finance and Operations.</span></span>
- <span data-ttu-id="b24b0-144">**Statut de traitement** - Ce champ affiche le statut de traitement de la commande dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b24b0-144">**Processing status** – This field shows the processing status of the order in Finance and Operations.</span></span> <span data-ttu-id="b24b0-145">Les valeurs disponibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="b24b0-145">The following values are available:</span></span>

    - <span data-ttu-id="b24b0-146">Active</span><span class="sxs-lookup"><span data-stu-id="b24b0-146">Active</span></span>
    - <span data-ttu-id="b24b0-147">Confirmée</span><span class="sxs-lookup"><span data-stu-id="b24b0-147">Confirmed</span></span>
    - <span data-ttu-id="b24b0-148">Bon de livraison</span><span class="sxs-lookup"><span data-stu-id="b24b0-148">Packing Slip</span></span>
    - <span data-ttu-id="b24b0-149">Facturé</span><span class="sxs-lookup"><span data-stu-id="b24b0-149">Invoiced</span></span>
    - <span data-ttu-id="b24b0-150">Prélevé</span><span class="sxs-lookup"><span data-stu-id="b24b0-150">Picked</span></span>
    - <span data-ttu-id="b24b0-151">Partiellement prélevé</span><span class="sxs-lookup"><span data-stu-id="b24b0-151">Partially Picked</span></span>
    - <span data-ttu-id="b24b0-152">Partiellement emballé</span><span class="sxs-lookup"><span data-stu-id="b24b0-152">Partially Packed</span></span>
    - <span data-ttu-id="b24b0-153">Expédié</span><span class="sxs-lookup"><span data-stu-id="b24b0-153">Shipped</span></span>
    - <span data-ttu-id="b24b0-154">Partiellement expédié</span><span class="sxs-lookup"><span data-stu-id="b24b0-154">Partially Shipped</span></span>
    - <span data-ttu-id="b24b0-155">Partiellement facturé</span><span class="sxs-lookup"><span data-stu-id="b24b0-155">Partially Invoiced</span></span>
    - <span data-ttu-id="b24b0-156">Annulé</span><span class="sxs-lookup"><span data-stu-id="b24b0-156">Cancelled</span></span>

<span data-ttu-id="b24b0-157">Le paramètre **Le devis a des produits mis à jour uniquement en externe** est utilisé dans d'autres scénarios de commande client (synchronisation entre Sales et Finance and Operation, par exemple) pour gérer de façon cohérente si la commande client comprend entièrement les produits gérés en externe.</span><span class="sxs-lookup"><span data-stu-id="b24b0-157">The **Has Externally Maintained Products Only** setting is used in other sales order scenarios (for example, synchronization from Sales to Finance and Operation) to consistently track whether a sales order consists entirely of externally maintained products.</span></span> <span data-ttu-id="b24b0-158">Si une commande client se compose uniquement des produits gérés en externe, les produits sont mis à jour dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b24b0-158">If a sales order consists entirely of externally maintained products, the products are maintained in Finance and Operations.</span></span> <span data-ttu-id="b24b0-159">Ceci permet de garantir que vous ne tenterez pas de synchroniser les lignes de commande client ayant des produits qui sont inconnus de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b24b0-159">This setting helps guarantee that you don't try to synchronize sales order lines that have products that are unknown to Finance and Operations.</span></span>

<span data-ttu-id="b24b0-160">Les boutons **Créer une facture**, **Annuler la commande**, **Recalculer**, **Obtenir des produits** et **Adresse de recherche** sur la page **Commande client** sont masqués pour les commandes gérées en externe, car les factures sont créées dans Finance and Operations et synchronisées avec Sales.</span><span class="sxs-lookup"><span data-stu-id="b24b0-160">The **Create Invoice**, **Cancel Order**, **Recalculate**, **Get Products**, and **Lookup Address** buttons on the **Sales order** page are hidden for externally maintained orders, because invoices will be created in Finance and Operations and synchronized to Sales.</span></span> <span data-ttu-id="b24b0-161">La page de commande ne peut pas être modifiée car les informations de commande client sont synchronisées à partir de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b24b0-161">The order page can't be edited, because sales order information will be synchronized from Finance and Operations.</span></span>

<span data-ttu-id="b24b0-162">Le statut d'une commande client restera **Actif** pour garantir que les modifications effectuées dans Finance and Operations peuvent être répercutées dans la commande client avec Sales.</span><span class="sxs-lookup"><span data-stu-id="b24b0-162">The status of a sales order will remain **Active** to help guarantee that changes from Finance and Operations can flow to the sales order in Sales.</span></span> <span data-ttu-id="b24b0-163">Cette opération est contrôlée en définissant le paramètre par défaut **Statecode \[Statut\]** sur **Actif** dans le projet d'intégration de données.</span><span class="sxs-lookup"><span data-stu-id="b24b0-163">To control this behavior, set the default **Statecode \[Status\]** value to **Active** in the Data integration project.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="b24b0-164">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="b24b0-164">Preconditions and mapping setup</span></span>

<span data-ttu-id="b24b0-165">Avant de synchroniser les commandes client, il est important de mettre les systèmes à jour avec le paramètre suivant :</span><span class="sxs-lookup"><span data-stu-id="b24b0-165">Before you synchronize sales orders, it's important that you update the following settings in the systems.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="b24b0-166">Configuration dans Sales</span><span class="sxs-lookup"><span data-stu-id="b24b0-166">Setup in Sales</span></span>

- <span data-ttu-id="b24b0-167">Vérifiez que les autorisations sont bien définies pour l'équipe à laquelle l'utilisateur est affecté (à partir de votre connexion dans Sales).</span><span class="sxs-lookup"><span data-stu-id="b24b0-167">Make sure that permissions are set up for the team that the user from your Sales connection set is assigned to.</span></span> <span data-ttu-id="b24b0-168">Si vous utilisez des données de démonstration, généralement l'utilisateur dispose de l'accès Administrateur, mais pas l'équipe.</span><span class="sxs-lookup"><span data-stu-id="b24b0-168">If you're using demo data, the user usually has admin access, but the team doesn't have admin access.</span></span> <span data-ttu-id="b24b0-169">Si l'équipe n'a pas accès d'administrateur, lors de l'exécution du projet à partir de l'intégrateur de données, vous recevrez un message d'erreur indiquant que l'équipe principale est manquante.</span><span class="sxs-lookup"><span data-stu-id="b24b0-169">If the team doesn't also have admin access, when you run the project from Data integration, you will receive an error message that states that Principal team is missing.</span></span>

    <span data-ttu-id="b24b0-170">Allez dans **Paramètres** > **Sécurité** > **Équipes**, sélectionnez l'équipe appropriée, cliquez sur **Gestion des rôles**, puis sélectionnez un rôle avec les autorisations souhaitées, par exemple, celles d'**Administrateur système**.</span><span class="sxs-lookup"><span data-stu-id="b24b0-170">Go to **Settings** > **Security** > **Teams**, select the relevant team, select **Manage Roles**, and select a role that has the desired permissions, such as **System Administrator**.</span></span>

- <span data-ttu-id="b24b0-171">Allez dans **Paramètres** > **Administration** > **Paramètres système** > **Sales**, et assurez-vous que les paramètres suivants sont utilisés :</span><span class="sxs-lookup"><span data-stu-id="b24b0-171">Go to **Settings** > **Administration** > **System settings** > **Sales**, and makes sure that the following settings are used:</span></span>

    - <span data-ttu-id="b24b0-172">L'option **Utiliser le système de calcul du prix du système** est définie **Oui**.</span><span class="sxs-lookup"><span data-stu-id="b24b0-172">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
    - <span data-ttu-id="b24b0-173">Le champ **Mode de calcul de remise** est défini sur **Ligne article**.</span><span class="sxs-lookup"><span data-stu-id="b24b0-173">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-finance-and-operations"></a><span data-ttu-id="b24b0-174">Configuration dans Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b24b0-174">Setup in Finance and Operations</span></span>

<span data-ttu-id="b24b0-175">Allez dans **Ventes et marketing** > **Tâches périodiques** > **Calcule les totaux de vente**, et configurez la tâche pour qu'elle s'exécute comme un traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="b24b0-175">Go to **Sales and marketing** > **Periodic tasks** > **Calculate sales totals**, and set the job to run as a batch job.</span></span> <span data-ttu-id="b24b0-176">Définissez l'option **Calculer les totaux des commandes client** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="b24b0-176">Set the **Calculate totals for sales orders** option to **Yes**.</span></span> <span data-ttu-id="b24b0-177">Cette étape est importante, car seules les commandes client où les totaux de vente ont été calculés sont synchronisées avec Sales.</span><span class="sxs-lookup"><span data-stu-id="b24b0-177">This step is important, because only sales orders where sales totals are calculated will be synchronized to Sales.</span></span> <span data-ttu-id="b24b0-178">La fréquence du traitement par lots doit être alignée avec la fréquence de la synchronisation des commandes client.</span><span class="sxs-lookup"><span data-stu-id="b24b0-178">The frequency of the batch job should be aligned with the frequency of sales order synchronization.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="b24b0-179">Paramétrage du projet d'intégration des données</span><span class="sxs-lookup"><span data-stu-id="b24b0-179">Setup in the Data integration project</span></span>

#### <a name="salesheader-task"></a><span data-ttu-id="b24b0-180">Tâche SalesHeader</span><span class="sxs-lookup"><span data-stu-id="b24b0-180">SalesHeader task</span></span>

- <span data-ttu-id="b24b0-181">Assurez-vous que la mise en correspondance nécessaire existe pour **InvoiceCountryRegionId** et **BillingAddress\_Country** et pour **DeliveryCountryRegionId** et **DeliveryAddress\_Country**.</span><span class="sxs-lookup"><span data-stu-id="b24b0-181">Make sure that the required mapping exists for **InvoiceCountryRegionId** to **BillingAddress\_Country** and for **DeliveryCountryRegionId** to **DeliveryAddress\_Country**.</span></span>

    <span data-ttu-id="b24b0-182">La valeur du modèle est une mise en correspondance des valeurs où plusieurs pays ou régions sont mis en correspondance.</span><span class="sxs-lookup"><span data-stu-id="b24b0-182">The template value is a value map where several countries or regions are mapped.</span></span>

- <span data-ttu-id="b24b0-183">Un tarif est requis pour créer des commandes dans Sales.</span><span class="sxs-lookup"><span data-stu-id="b24b0-183">A price list is required in order to create orders in Sales.</span></span> <span data-ttu-id="b24b0-184">Mettez à jour la mise en correspondance de la valeur pour **pricelevelid.name \[Nom des tarifs\]** sur la liste des prix utilisée dans Sales par devise.</span><span class="sxs-lookup"><span data-stu-id="b24b0-184">Update the value map for **pricelevelid.name \[Price list name\]** to the price list that is used in Sales per currency.</span></span> <span data-ttu-id="b24b0-185">Vous pouvez utiliser le tarif par défaut pour une seule devise.</span><span class="sxs-lookup"><span data-stu-id="b24b0-185">You can use the default price list for a single currency.</span></span> <span data-ttu-id="b24b0-186">Sinon, si vous avez un tarif dans plusieurs devises, vous pouvez utiliser une mise en correspondance des valeurs.</span><span class="sxs-lookup"><span data-stu-id="b24b0-186">Alternatively, if you have price lists in multiple currencies, you can use a value map.</span></span>

    <span data-ttu-id="b24b0-187">La valeur de modèle par défaut pour **pricelevelid.name \[Nom des tarifs\]** est le **service CRM USA (exemple)**.</span><span class="sxs-lookup"><span data-stu-id="b24b0-187">The default template value for **pricelevelid.name \[Price list name\]** is **CRM Service USA (sample)**.</span></span>

#### <a name="salesline-task"></a><span data-ttu-id="b24b0-188">Tâche SalesLine</span><span class="sxs-lookup"><span data-stu-id="b24b0-188">SalesLine task</span></span>

- <span data-ttu-id="b24b0-189">Assurez-vous que la mise en correspondance nécessaire existe pour **DeliveryCountryRegionId** et **DeliveryAddress\_Country**.</span><span class="sxs-lookup"><span data-stu-id="b24b0-189">Make sure that the required mapping exists for **DeliveryCountryRegionId** to **DeliveryAddress\_Country**.</span></span>

    <span data-ttu-id="b24b0-190">La valeur du modèle est une mise en correspondance des valeurs où plusieurs pays ou régions sont mis en correspondance.</span><span class="sxs-lookup"><span data-stu-id="b24b0-190">The template value is a value map where several countries or regions are mapped.</span></span>

- <span data-ttu-id="b24b0-191">Assurez-vous que la mise en correspondance des valeurs requise pour **SalesUnitSymbol** dans Finance and Operations existe.</span><span class="sxs-lookup"><span data-stu-id="b24b0-191">Make sure that the required value map for **SalesUnitSymbol** in Finance and Operations exists.</span></span>

    <span data-ttu-id="b24b0-192">Une valeur de modèle ayant une mise en correspondance des valeurs est définie pour **SalesUnitSymbol** sur **Quantité\_UOM**.</span><span class="sxs-lookup"><span data-stu-id="b24b0-192">A template value that has a value map is defined for **SalesUnitSymbol** to **Quantity\_UOM**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="b24b0-193">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="b24b0-193">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="b24b0-194">Les champs **Conditions de paiement**, **Conditions de transport**, **Conditions de livraison**, **Méthode d'expédition** et **Mode de distribution** ne sont pas inclus dans les mises en correspondance par défaut.</span><span class="sxs-lookup"><span data-stu-id="b24b0-194">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="b24b0-195">Pour mettre en correspondance ces champs, vous devez paramétrer une mise en correspondance des valeurs spécifique aux données des organisations entre lesquelles l'entité est synchronisée.</span><span class="sxs-lookup"><span data-stu-id="b24b0-195">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="b24b0-196">Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l'intégration de données.</span><span class="sxs-lookup"><span data-stu-id="b24b0-196">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="b24b0-197">La mise en correspondance indique quelles informations du champ sont synchronisées entre Sales et Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b24b0-197">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

### <a name="orderheader"></a><span data-ttu-id="b24b0-198">OrderHeader</span><span class="sxs-lookup"><span data-stu-id="b24b0-198">OrderHeader</span></span>

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-order-direct-template-mapping-data-integrator-1.png)

### <a name="orderline"></a><span data-ttu-id="b24b0-200">OrderLine</span><span class="sxs-lookup"><span data-stu-id="b24b0-200">OrderLine</span></span>

![Mise en correspondance de modèles dans l'intégrateur de données](./media/sales-order-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a><span data-ttu-id="b24b0-202">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="b24b0-202">Related topics</span></span>

[<span data-ttu-id="b24b0-203">Prospect en disponibilités</span><span class="sxs-lookup"><span data-stu-id="b24b0-203">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="b24b0-204">Synchroniser directement les comptes provenant du module Sales sur les clients de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b24b0-204">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="b24b0-205">Synchroniser les produits directement de Finance and Operations sur les produits du module Sales</span><span class="sxs-lookup"><span data-stu-id="b24b0-205">Synchronize products directly from Finance and Operations to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="b24b0-206">Synchroniser directement les contacts de Sales avec les contacts ou clients de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b24b0-206">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="b24b0-207">Synchroniser les en-têtes et les lignes de facture client provenant directement du module Finance and Operations avec Sales</span><span class="sxs-lookup"><span data-stu-id="b24b0-207">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)




