---
title: Synchroniser directement les contacts de Sales avec les contacts ou clients de Finance and Operations
description: "Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les entités Contact (Contacts) et Contact (Clients) de Microsoft Dynamics 365 for Sales vers Microsoft Dynamics 365 for Finance and Operations."
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2017
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
ms.openlocfilehash: 95b7d5be86676a1442df1c71308cb978b854d2c8
ms.contentlocale: fr-fr
ms.lasthandoff: 08/07/2018

---

# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-finance-and-operations"></a><span data-ttu-id="8de0d-103">Synchroniser directement les contacts provenant du module Sales sur les contacts ou clients de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8de0d-103">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="8de0d-104">Avant d'utiliser le prospect pour une solution de disponibilités, vous devez connaître l'[intégration de données Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="8de0d-104">Before you can use the Prospect to cash solution, you should be familiar with [Dynamics 365 Data integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span>

<span data-ttu-id="8de0d-105">Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les entités Contact (Contacts) et Contact (Clients) directement de Microsoft Dynamics 365 for Sales vers Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8de0d-105">This topic discusses the templates and underlying tasks that are used to synchronize Contact (Contacts) and Contact (Customers) entities directly from Microsoft Dynamics 365 for Sales to Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="8de0d-106">Flux de données dans Prospect en disponibilités</span><span class="sxs-lookup"><span data-stu-id="8de0d-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="8de0d-107">La solution Prospect en disponibilités utilise la fonction d'intégration de données pour synchroniser les données entre plusieurs instances de Finance and Operations et Sales.</span><span class="sxs-lookup"><span data-stu-id="8de0d-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="8de0d-108">Les modèles de prospects en disponibilités disponibles avec la fonction d'intégration de données activent le flux de données relatifs aux comptes, contacts, produits, devis de vente, commandes client et factures client entre Finance and Operations et Sales.</span><span class="sxs-lookup"><span data-stu-id="8de0d-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="8de0d-109">L'illustration ci-dessous indique comment les données sont synchronisées entre Finance and Operations et Sales.</span><span class="sxs-lookup"><span data-stu-id="8de0d-109">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="8de0d-110">[![Flux de données dans Prospect en disponibilités](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="8de0d-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="8de0d-111">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="8de0d-111">Templates and tasks</span></span>

<span data-ttu-id="8de0d-112">Pour accéder à des modèles disponibles, ouvrir [Centre d'administrateur PowerApps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="8de0d-112">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="8de0d-113">Sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner les modèles publics.</span><span class="sxs-lookup"><span data-stu-id="8de0d-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="8de0d-114">Les modèles et tâches sous-jacentes suivants sont utilisés pour synchroniser les entités Contacts (Contacts) de Sales avec les entités Contacts (Clients) de Finance and Operations :</span><span class="sxs-lookup"><span data-stu-id="8de0d-114">The following templates and underlying tasks are used to synchronize Contact (Contacts) entities in Sales to Contact (Customers) entities in Finance and Operations:</span></span>

- <span data-ttu-id="8de0d-115">**Noms des modèles dans l'intégration des données :**</span><span class="sxs-lookup"><span data-stu-id="8de0d-115">**Names of the templates in Data integration:**</span></span>

    - <span data-ttu-id="8de0d-116">Contacts (Sales et Fin and Ops) - Direct</span><span class="sxs-lookup"><span data-stu-id="8de0d-116">Contacts (Sales to Fin and Ops) - Direct</span></span>
    - <span data-ttu-id="8de0d-117">Contacts vers Client (Sales vers Fin and Ops) - Direct</span><span class="sxs-lookup"><span data-stu-id="8de0d-117">Contacts to Customer (Sales to Fin and Ops) - Direct</span></span>

- <span data-ttu-id="8de0d-118">**Noms des tâches dans le projet d'intégration de données :**</span><span class="sxs-lookup"><span data-stu-id="8de0d-118">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="8de0d-119">Contacts</span><span class="sxs-lookup"><span data-stu-id="8de0d-119">Contacts</span></span>
    - <span data-ttu-id="8de0d-120">ContactToCustomer</span><span class="sxs-lookup"><span data-stu-id="8de0d-120">ContactToCustomer</span></span>

<span data-ttu-id="8de0d-121">La tâche suivante de synchronisation est requise avant que la synchronisation du contact puisse avoir lieu : Comptes (Sales vers Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="8de0d-121">The following synchronization task is required before contact synchronization can occur: Accounts (Sales to Fin and Ops)</span></span>

## <a name="entity-sets"></a><span data-ttu-id="8de0d-122">Ensembles d'entités</span><span class="sxs-lookup"><span data-stu-id="8de0d-122">Entity sets</span></span>

| <span data-ttu-id="8de0d-123">Vente</span><span class="sxs-lookup"><span data-stu-id="8de0d-123">Sales</span></span>    | <span data-ttu-id="8de0d-124">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8de0d-124">Finance and Operations</span></span> |
|----------|------------------------|
| <span data-ttu-id="8de0d-125">Contacts</span><span class="sxs-lookup"><span data-stu-id="8de0d-125">Contacts</span></span> | <span data-ttu-id="8de0d-126">Contacts CDS</span><span class="sxs-lookup"><span data-stu-id="8de0d-126">CDS Contacts</span></span>           |
| <span data-ttu-id="8de0d-127">Contacts</span><span class="sxs-lookup"><span data-stu-id="8de0d-127">Contacts</span></span> | <span data-ttu-id="8de0d-128">Clients V2</span><span class="sxs-lookup"><span data-stu-id="8de0d-128">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="8de0d-129">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="8de0d-129">Entity flow</span></span>

<span data-ttu-id="8de0d-130">Les contacts sont gérés dans Sales et synchronisés avec Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8de0d-130">Contacts are managed in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="8de0d-131">Un contact dans Sales peut devenir un contact ou un client dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8de0d-131">A contact in Sales can become either a contact or a customer in Finance and Operations.</span></span> <span data-ttu-id="8de0d-132">Pour déterminer si un contact dans Sales doit être synchronisé avec Finance and Operations en tant que contact ou client, le système recherche les propriétés suivantes sur le contact dans Sales :</span><span class="sxs-lookup"><span data-stu-id="8de0d-132">To determine whether a contact in Sales should be synchronized to Finance and Operations as a contact or a customer, the system looks at the following properties on the contact in Sales:</span></span>

- <span data-ttu-id="8de0d-133">**Synchronisation avec un client dans Finance and Operations :** Contacts là où **Client actif** est défini sur **Oui**</span><span class="sxs-lookup"><span data-stu-id="8de0d-133">**Synchronization to a customer in Finance and Operations:** Contacts where **Is Active Customer** is set to **Yes**</span></span>
- <span data-ttu-id="8de0d-134">**Synchronisation avec un contact dans Finance and Operations :** Contacts là où **Client actif** est défini sur **Non** et **Société** (compte parent/contact) pointe vers un compte (pas un contact)</span><span class="sxs-lookup"><span data-stu-id="8de0d-134">**Synchronization to a contact in Finance and Operations:** Contacts where **Is Active Customer** is set to **No** and **Company** (parent account/contact) points to an account (not a contact)</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="8de0d-135">Prospect pour une solution de disponibilités pour Sales</span><span class="sxs-lookup"><span data-stu-id="8de0d-135">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="8de0d-136">Un nouveau champ **Client actif** a été ajouté au contact.</span><span class="sxs-lookup"><span data-stu-id="8de0d-136">A new **Is Active Customer** field has been added to the contact.</span></span> <span data-ttu-id="8de0d-137">Ce champ permet de différencier les contacts qui disposent d'activités commerciales et les contacts qui n'ont pas d'activités commerciales.</span><span class="sxs-lookup"><span data-stu-id="8de0d-137">This field is used to differentiate contacts that have sales activity and contacts that don't have sales activity.</span></span> <span data-ttu-id="8de0d-138">**Client actif** est défini sur **Oui** uniquement pour les contacts qui associés à des devis, des commandes, ou des factures.</span><span class="sxs-lookup"><span data-stu-id="8de0d-138">**Is Active Customer** is set to **Yes** only for contacts that have related quotations, orders, or invoices.</span></span> <span data-ttu-id="8de0d-139">Seuls ces contacts sont synchronisés avec Finance and Operations comme clients.</span><span class="sxs-lookup"><span data-stu-id="8de0d-139">Only those contacts are synchronized to Finance and Operations as customers.</span></span>

<span data-ttu-id="8de0d-140">Un nouveau champ **IsCompanyAnAccount** a été ajouté au contact.</span><span class="sxs-lookup"><span data-stu-id="8de0d-140">A new **IsCompanyAnAccount** field has been added to the contact.</span></span> <span data-ttu-id="8de0d-141">Ce champ indique si un contact est lié à une société (compte parent/contact) du type **Compte**.</span><span class="sxs-lookup"><span data-stu-id="8de0d-141">This field indicates whether a contact is linked to a company (parent account/contact) of the **Account** type.</span></span> <span data-ttu-id="8de0d-142">Ces informations servent à identifier les contacts qui doivent être synchronisés avec Finance and Operations comme contacts.</span><span class="sxs-lookup"><span data-stu-id="8de0d-142">This information is used to identify contacts that should be synchronized to Finance and Operations as contacts.</span></span>

<span data-ttu-id="8de0d-143">Un nouveau champ **Numéro de contact** a été ajouté au contact pour garantir une clé naturelle et unique pour l'intégration.</span><span class="sxs-lookup"><span data-stu-id="8de0d-143">A new **Contact Number** field has been added to the contact to help guarantee a natural and unique key for the integration.</span></span> <span data-ttu-id="8de0d-144">Lorsqu'un nouveau contact est créé, une valeur **Numéro de contact** est automatiquement générée à l'aide d'une souche de numéros.</span><span class="sxs-lookup"><span data-stu-id="8de0d-144">When a new contact is created, a **Contact Number** value is automatically generated by using a number sequence.</span></span> <span data-ttu-id="8de0d-145">La valeur est composée de **CON**, suivi d'une souche de numéros croissante et d'un suffixe de six caractères.</span><span class="sxs-lookup"><span data-stu-id="8de0d-145">The value consists of **CON**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="8de0d-146">Voici un exemple : **CON-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="8de0d-146">Here is an example: **CON-01000-BVRCPS**</span></span>

<span data-ttu-id="8de0d-147">Lorsque la solution d'intégration pour Sales est appliquée, un script de mise à niveau définit le champ **Numéro de contact** pour des contact existants à l'aide de la souche de numéros qui a été précédemment mentionnée.</span><span class="sxs-lookup"><span data-stu-id="8de0d-147">When the integration solution for Sales is applied, an upgrade script sets the **Contact Number** field for existing contacts by using the number sequence that was mentioned earlier.</span></span> <span data-ttu-id="8de0d-148">Le script de mise à niveau définit également le champ **Client actif** sur **Oui** pour tous les contacts qui disposent d'activités commerciales.</span><span class="sxs-lookup"><span data-stu-id="8de0d-148">The upgrade script also sets the **Is Active Customer** field to **Yes** for any contacts that have sales activity.</span></span>

## <a name="in-finance-and-operations"></a><span data-ttu-id="8de0d-149">Dans Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8de0d-149">In Finance and Operations</span></span>

<span data-ttu-id="8de0d-150">Les contacts sont étiquetés à l'aide de la propriété **IsContactPersonExternallyMaintained**.</span><span class="sxs-lookup"><span data-stu-id="8de0d-150">Contacts are tagged by using the **IsContactPersonExternallyMaintained** property.</span></span> <span data-ttu-id="8de0d-151">Cette propriété indique qu'un contact donné est conservé en externe.</span><span class="sxs-lookup"><span data-stu-id="8de0d-151">This property indicates that a given contact is maintained externally.</span></span> <span data-ttu-id="8de0d-152">Dans ce cas, les contacts tenus à jour en externe sont tenus à jour dans Sales.</span><span class="sxs-lookup"><span data-stu-id="8de0d-152">In this case, externally maintained contacts are maintained in Sales.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="8de0d-153">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="8de0d-153">Preconditions and mapping setup</span></span>

### <a name="contact-to-customer"></a><span data-ttu-id="8de0d-154">Contact vers client</span><span class="sxs-lookup"><span data-stu-id="8de0d-154">Contact to customer</span></span>

- <span data-ttu-id="8de0d-155">**CustomerGroup** est requis dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8de0d-155">**CustomerGroup** is required in Finance and Operations.</span></span> <span data-ttu-id="8de0d-156">Pour éviter toute erreur de synchronisation, vous pouvez spécifier une valeur par défaut dans la mise en correspondance.</span><span class="sxs-lookup"><span data-stu-id="8de0d-156">To help prevent synchronization errors, you can specify a default value in the mapping.</span></span> <span data-ttu-id="8de0d-157">Cette valeur par défaut est alors utilisée si le champ est laissé vide dans Sales.</span><span class="sxs-lookup"><span data-stu-id="8de0d-157">That default value is then used if the field is left blank in Sales.</span></span>

    <span data-ttu-id="8de0d-158">Le modèle de valeur par défaut est **10**.</span><span class="sxs-lookup"><span data-stu-id="8de0d-158">The default template value is **10**.</span></span>

- <span data-ttu-id="8de0d-159">En ajoutant les mises en correspondance suivantes, vous pouvez réduire le nombre de mises à jour manuelles requises dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8de0d-159">By adding the following mappings, you can help reduce the number of manual updates that are required in Finance and Operations.</span></span> <span data-ttu-id="8de0d-160">Vous pouvez utiliser une valeur par défaut ou une mise en correspondance des valeurs, par exemple, **Pays/région** ou **Ville**.</span><span class="sxs-lookup"><span data-stu-id="8de0d-160">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="8de0d-161">**SiteId** – Site par défaut qui peut également être défini dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8de0d-161">**SiteId** – A default site can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="8de0d-162">Un site est requis pour générer des lignes de devis et de commandes client dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8de0d-162">A site is required in order to generate quotations and sales orders in Finance and Operations.</span></span>

        <span data-ttu-id="8de0d-163">Aucun modèle de valeur pour **SiteId** n'est défini.</span><span class="sxs-lookup"><span data-stu-id="8de0d-163">A template value for **SiteId** isn't defined.</span></span>

    - <span data-ttu-id="8de0d-164">**WarehouseId** – Entrepôt par défaut qui peut également être défini dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8de0d-164">**WarehouseId** – A default warehouse can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="8de0d-165">Un entrepôt est requis pour générer des lignes de devis et de commandes client dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8de0d-165">A warehouse is required in order to generate quotations and sales orders in Finance and Operations.</span></span>

        <span data-ttu-id="8de0d-166">Aucun modèle de valeur pour **WarehouseId** n'est défini.</span><span class="sxs-lookup"><span data-stu-id="8de0d-166">A template value for **WarehouseId** isn't defined.</span></span>

    - <span data-ttu-id="8de0d-167">**LanguageId** – Une langue est requise pour générer des devis et des commandes client dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8de0d-167">**LanguageId** – A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span>
    
        <span data-ttu-id="8de0d-168">Le modèle de valeur par défaut **en-us**.</span><span class="sxs-lookup"><span data-stu-id="8de0d-168">The default template value for is **en-us**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="8de0d-169">Mise en correspondance de modèles dans l'intégration de données</span><span class="sxs-lookup"><span data-stu-id="8de0d-169">Template mapping in Data integration</span></span>

<span data-ttu-id="8de0d-170">Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l'intégration de données.</span><span class="sxs-lookup"><span data-stu-id="8de0d-170">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="8de0d-171">La mise en correspondance indique quelles informations du champ sont synchronisées entre Sales et Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8de0d-171">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="8de0d-172">Contact vers contact</span><span class="sxs-lookup"><span data-stu-id="8de0d-172">Contact to contact</span></span>

![Mise en correspondance de modèles dans l'intégrateur de données](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer"></a><span data-ttu-id="8de0d-174">Contact vers client</span><span class="sxs-lookup"><span data-stu-id="8de0d-174">Contact to customer</span></span>

![Mise en correspondance de modèles dans l'intégrateur de données](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a><span data-ttu-id="8de0d-176">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="8de0d-176">Related topics</span></span>

[<span data-ttu-id="8de0d-177">Prospect en disponibilités</span><span class="sxs-lookup"><span data-stu-id="8de0d-177">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="8de0d-178">Synchroniser directement les comptes provenant du module Sales sur les clients de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8de0d-178">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="8de0d-179">Synchroniser les produits directement de Finance and Operations sur les produits du module Sales</span><span class="sxs-lookup"><span data-stu-id="8de0d-179">Synchronize products directly from Finance and Operations to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="8de0d-180">Synchroniser les en-têtes et les lignes de commande client directement entre le module Finance and Operations et Sales</span><span class="sxs-lookup"><span data-stu-id="8de0d-180">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="8de0d-181">Synchroniser les en-têtes et les lignes de facture client provenant directement du module Finance and Operations avec Sales</span><span class="sxs-lookup"><span data-stu-id="8de0d-181">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)



