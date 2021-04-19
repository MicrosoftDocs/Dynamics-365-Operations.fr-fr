---
title: Synchroniser directement les comptes provenant du module Sales sur les clients de Supply Chain Management
description: Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les comptes depuis Dynamics 365 Sales vers Supply Chain Management.
author: ChristianRytt
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 1bf0da5ba5274b61758bc0efdc2f2167327966ad
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831648"
---
# <a name="synchronize-accounts-directly-from-sales-to-customers-in-supply-chain-management"></a><span data-ttu-id="2ab91-103">Synchroniser directement les comptes provenant du module Sales sur les clients de Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="2ab91-103">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> <span data-ttu-id="2ab91-104">Avant d’utiliser le prospect pour une solution de disponibilités, vous devez bien connaître la rubrique [Intégrer des données dans Microsoft Dataverse pour applications](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="2ab91-104">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Microsoft Dataverse for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span></span>

<span data-ttu-id="2ab91-105">Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les comptes directement depuis Dynamics 365 Sales vers Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2ab91-105">This topic discusses the templates and underlying tasks that are used to synchronize accounts directly from Dynamics 365 Sales to Dynamics 365 Supply Chain Management.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="2ab91-106">Flux de données dans Prospect en disponibilités</span><span class="sxs-lookup"><span data-stu-id="2ab91-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="2ab91-107">La solution Prospect en disponibilités utilise la fonction d’intégration de données pour synchroniser les données entre plusieurs instances de Supply Chain Management et Sales.</span><span class="sxs-lookup"><span data-stu-id="2ab91-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span>  <span data-ttu-id="2ab91-108">Les modèles de prospects en disponibilités disponibles avec la fonction d’intégration de données activent le flux de données relatifs aux comptes, contacts, produits, devis de vente, commandes client et factures client entre Supply Chain Management et Sales.</span><span class="sxs-lookup"><span data-stu-id="2ab91-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="2ab91-109">L’illustration ci-dessous indique comment les données sont synchronisées entre Supply Chain Management et Sales.</span><span class="sxs-lookup"><span data-stu-id="2ab91-109">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="2ab91-110">[![Flux de données dans Prospect en disponibilités](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="2ab91-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="2ab91-111">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="2ab91-111">Templates and tasks</span></span>

<span data-ttu-id="2ab91-112">Pour accéder à des modèles disponibles, ouvrez [Centre d’administrateur Power Apps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="2ab91-112">To access the available templates, open [Power Apps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="2ab91-113">Sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner les modèles publics.</span><span class="sxs-lookup"><span data-stu-id="2ab91-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="2ab91-114">L’exemple et la tâche sous-jacente suivants sont utilisés pour synchroniser les comptes de Sales vers Supply Chain Management :</span><span class="sxs-lookup"><span data-stu-id="2ab91-114">The following template and underlying task are used to synchronize accounts from Sales to Supply Chain Management:</span></span>

- <span data-ttu-id="2ab91-115">Comptes **Nom du modèle dans l’intégration des données :** (Sales à Fin and Ops) - Direct</span><span class="sxs-lookup"><span data-stu-id="2ab91-115">**Name of the template in Data integration:** Accounts (Sales to Fin and Ops) - Direct</span></span>
- <span data-ttu-id="2ab91-116">**Nom de la tâche dans le projet :** Comptes - Clients</span><span class="sxs-lookup"><span data-stu-id="2ab91-116">**Name of the task in the project:** Accounts - Customers</span></span>

<span data-ttu-id="2ab91-117">Aucune tâche de synchronisation n’est nécessaire pour que la synchronisation Compte/Client puisse se produire.</span><span class="sxs-lookup"><span data-stu-id="2ab91-117">No synchronization tasks are required before Account/Customer synchronization can occur.</span></span>

## <a name="entity-set"></a><span data-ttu-id="2ab91-118">Ensemble d’entités</span><span class="sxs-lookup"><span data-stu-id="2ab91-118">Entity set</span></span>

| <span data-ttu-id="2ab91-119">Ventes</span><span class="sxs-lookup"><span data-stu-id="2ab91-119">Sales</span></span>    | <span data-ttu-id="2ab91-120">Gestion de la chaîne d’approvisionnement</span><span class="sxs-lookup"><span data-stu-id="2ab91-120">Supply Chain Management</span></span> |
|----------|------------------------|
| <span data-ttu-id="2ab91-121">Comptes</span><span class="sxs-lookup"><span data-stu-id="2ab91-121">Accounts</span></span> | <span data-ttu-id="2ab91-122">Clients V2</span><span class="sxs-lookup"><span data-stu-id="2ab91-122">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="2ab91-123">Flux d’entité</span><span class="sxs-lookup"><span data-stu-id="2ab91-123">Entity flow</span></span>

<span data-ttu-id="2ab91-124">Les comptes sont gérés dans Sales et synchronisés sur Supply Chain Management en tant que clients.</span><span class="sxs-lookup"><span data-stu-id="2ab91-124">Accounts are managed in Sales and synchronized to Supply Chain Management as customers.</span></span> <span data-ttu-id="2ab91-125">La propriété **Géré en externe** sur ces clients est définie sur **Oui** pour suivre les clients issus de Sales.</span><span class="sxs-lookup"><span data-stu-id="2ab91-125">The **Is Externally Maintained** property on these customers is set to **Yes** to track customers that originate from Sales.</span></span> <span data-ttu-id="2ab91-126">Lors de la facturation, ces informations sont utilisées pour filtrer les factures qui sont synchronisées sur Sales.</span><span class="sxs-lookup"><span data-stu-id="2ab91-126">During invoicing, this information is used to filter invoices that are synchronized to Sales.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="2ab91-127">Prospect pour une solution de disponibilités pour Sales</span><span class="sxs-lookup"><span data-stu-id="2ab91-127">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="2ab91-128">La colonne **Numéro de compte** est disponible sur la page **Compte**.</span><span class="sxs-lookup"><span data-stu-id="2ab91-128">The **Account Number** column is available on the **Account** page.</span></span> <span data-ttu-id="2ab91-129">Une clé naturelle et unique a été créée pour prendre en charge l’intégration.</span><span class="sxs-lookup"><span data-stu-id="2ab91-129">It has been made a natural and unique key in order to support the integration.</span></span> <span data-ttu-id="2ab91-130">La fonction de clé naturelle de la solution de gestion de la relation client (CRM) peut affecter les clients utilisant déjà la colonne **Numéro de compte**, mais qui n’utilisez pas des valeurs **Numéro de compte** uniques par compte.</span><span class="sxs-lookup"><span data-stu-id="2ab91-130">The natural key feature of the Customer Relationship Management (CRM) solution might affect customers who already use the **Account Number** column, but who don't use unique **Account Number** values per account.</span></span> <span data-ttu-id="2ab91-131">Actuellement, la solution d’intégration ne prend pas en charge ce cas.</span><span class="sxs-lookup"><span data-stu-id="2ab91-131">Currently, the integration solution doesn't support this case.</span></span>

<span data-ttu-id="2ab91-132">Lorsqu’un compte est créé, si une valeur **Numéro de compte** n’existe pas encore, elle est automatiquement générée à l’aide d’une souche de numéros.</span><span class="sxs-lookup"><span data-stu-id="2ab91-132">When a new account is created, if an **Account Number** value doesn't already exist, it's automatically generated by using a number sequence.</span></span> <span data-ttu-id="2ab91-133">La valeur est composée d’**ACC**, suivi d’une souche de numéros croissante et d’un suffixe de six caractères.</span><span class="sxs-lookup"><span data-stu-id="2ab91-133">The value consists of **ACC**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="2ab91-134">Voici un exemple : **ACC-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="2ab91-134">Here is an example: **ACC-01000-BVRCPS**</span></span>

<span data-ttu-id="2ab91-135">Lorsque la solution d’intégration pour Sales est appliquée, un script de mise à niveau définit la colonne **Numéro de compte** sur les comptes existants dans Sales.</span><span class="sxs-lookup"><span data-stu-id="2ab91-135">When the integration solution for Sales is applied, an upgrade script sets the **Account Number** column for existing accounts in Sales.</span></span> <span data-ttu-id="2ab91-136">S’il n’existe aucune valeur **Numéro de compte**, la souche de numéros qui a été mentionnée plus haut est utilisée.</span><span class="sxs-lookup"><span data-stu-id="2ab91-136">If there are no **Account Number** values, the number sequence that was mentioned earlier is used.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="2ab91-137">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="2ab91-137">Preconditions and mapping setup</span></span>

- <span data-ttu-id="2ab91-138">Le mappage **CustomerGroupId** doit être mis à jour avec une valeur valide dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2ab91-138">The **CustomerGroupId** mapping must be updated to a valid value in Supply Chain Management.</span></span> <span data-ttu-id="2ab91-139">Vous pouvez spécifier une valeur par défaut ou vous pouvez définir la valeur à l’aide d’une mise en correspondance des valeurs.</span><span class="sxs-lookup"><span data-stu-id="2ab91-139">You can specify a default value, or you can set the value by using a value map.</span></span>

    <span data-ttu-id="2ab91-140">Le modèle de valeur par défaut est **10**.</span><span class="sxs-lookup"><span data-stu-id="2ab91-140">The default template value is **10**.</span></span>

- <span data-ttu-id="2ab91-141">En ajoutant les mises en correspondance suivantes, vous pouvez réduire le nombre de mises à jour manuelles requises dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2ab91-141">By adding the following mappings, you can help reduce the number of manual updates that are required in Supply Chain Management.</span></span> <span data-ttu-id="2ab91-142">Vous pouvez utiliser une valeur par défaut ou une mise en correspondance des valeurs, par exemple, **Pays/région** ou **Ville**.</span><span class="sxs-lookup"><span data-stu-id="2ab91-142">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="2ab91-143">**SiteId** – Un site est requis pour générer des lignes de devis et de commande client dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2ab91-143">**SiteId** – A site is required in order to generate quotations and sales order lines in Supply Chain Management.</span></span> <span data-ttu-id="2ab91-144">Un site par défaut peut être extrait du produit, ou du client de l’en-tête de commande.</span><span class="sxs-lookup"><span data-stu-id="2ab91-144">A default site can be taken either from the product, or from the customer from the order header.</span></span>

        <span data-ttu-id="2ab91-145">Le modèle de valeur par défaut est **1**.</span><span class="sxs-lookup"><span data-stu-id="2ab91-145">The default template value is **1**.</span></span>

    - <span data-ttu-id="2ab91-146">**WarehouseId** – Un entrepôt est requis pour traiter des lignes de devis et de commande client dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2ab91-146">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Supply Chain Management.</span></span> <span data-ttu-id="2ab91-147">Un entrepôt par défaut peut être extrait du produit, ou du client de l’en-tête de commande dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2ab91-147">A default warehouse can be taken either from the product, or from the customer from the order header in Supply Chain Management.</span></span>

        <span data-ttu-id="2ab91-148">Le modèle de valeur par défaut est **13**.</span><span class="sxs-lookup"><span data-stu-id="2ab91-148">The default template value is **13**.</span></span>

    - <span data-ttu-id="2ab91-149">**LanguageId** – Un langage est requis pour générer des lignes de devis et de commande client dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2ab91-149">**LanguageId** – A language is required in order to generate quotations and sales orders in Supply Chain Management.</span></span> <span data-ttu-id="2ab91-150">Par défaut, la langue de l’en-tête de commande du client est utilisée.</span><span class="sxs-lookup"><span data-stu-id="2ab91-150">By default, the language from the order header from the customer is used.</span></span>

        <span data-ttu-id="2ab91-151">Le modèle de valeur par défaut est **en-us**.</span><span class="sxs-lookup"><span data-stu-id="2ab91-151">The default template value is **en-us**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="2ab91-152">Mise en correspondance de modèles dans l’intégration de données</span><span class="sxs-lookup"><span data-stu-id="2ab91-152">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="2ab91-153">Les colonnes **Conditions de paiement**, **Conditions de transport**, **Conditions de livraison**, **Méthode d’expédition** et **Mode de distribution** ne sont pas inclus dans les mises en correspondance par défaut.</span><span class="sxs-lookup"><span data-stu-id="2ab91-153">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** columns aren't included in the default mappings.</span></span> <span data-ttu-id="2ab91-154">Pour mettre en correspondance ces colonnes, vous devez paramétrer une mise en correspondance des valeurs spécifique aux données des organisations entre lesquelles la table est synchronisée.</span><span class="sxs-lookup"><span data-stu-id="2ab91-154">To map these columns, you must set up a value mapping that is specific to the data in the organizations that the table is synchronized between.</span></span>

<span data-ttu-id="2ab91-155">Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l’intégration de données.</span><span class="sxs-lookup"><span data-stu-id="2ab91-155">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="2ab91-156">La mise en correspondance indique quelles informations de la colonne sont synchronisées entre Sales et Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2ab91-156">The mapping shows which column information will be synchronized from Sales to Supply Chain Management.</span></span>

![Mise en correspondance de modèles dans l’intégration de données](./media/accounts-direct-template-mapping-data-integrator-1.png)

## <a name="related-topics"></a><span data-ttu-id="2ab91-158">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="2ab91-158">Related topics</span></span>


[<span data-ttu-id="2ab91-159">Prospect en disponibilités</span><span class="sxs-lookup"><span data-stu-id="2ab91-159">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="2ab91-160">Synchroniser directement les comptes provenant du module Sales sur les clients de Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="2ab91-160">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="2ab91-161">Synchroniser directement les contacts provenant du module Sales sur les contacts ou clients de Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="2ab91-161">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="2ab91-162">Synchronisation des commandes client directement entre Sales et Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="2ab91-162">Synchronization of sales orders directly between Sales and Supply Chain Management</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="2ab91-163">Synchroniser les en-têtes et les lignes de facture client directement entre le module Supply Chain Management et Sales</span><span class="sxs-lookup"><span data-stu-id="2ab91-163">Synchronize sales invoice headers and lines directly from Supply Chain Management to Sales</span></span>](sales-invoice-template-mapping-direct.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]