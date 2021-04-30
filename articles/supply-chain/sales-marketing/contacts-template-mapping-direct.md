---
title: Synchroniser directement les contacts provenant du module Sales sur les contacts ou clients de Supply Chain Management
description: Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les entités Contact (Contacts) et Contact (Clients) directement depuis Dynamics 365 Sales vers Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 7bc4b48260907788eb90a19c5dc0b5c8f1d9d3b5
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908106"
---
# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-supply-chain-management"></a><span data-ttu-id="bd8f0-103">Synchroniser directement les contacts provenant du module Sales sur les contacts ou clients de Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="bd8f0-103">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> <span data-ttu-id="bd8f0-104">Avant d’utiliser le prospect pour une solution de disponibilités, vous devez bien connaître la rubrique [Intégrer des données dans Microsoft Dataverse pour applications](/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="bd8f0-104">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Microsoft Dataverse for Apps](/powerapps/administrator/data-integrator).</span></span>

<span data-ttu-id="bd8f0-105">Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les tables Contact (Contacts) et Contact (Clients) directement depuis Dynamics 365 Sales vers Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-105">This topic discusses the templates and underlying tasks that are used to synchronize Contact (Contacts) and Contact (Customers) tables directly from Dynamics 365 Sales to Dynamics 365 Supply Chain Management.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="bd8f0-106">Flux de données dans Prospect en disponibilités</span><span class="sxs-lookup"><span data-stu-id="bd8f0-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="bd8f0-107">La solution Prospect en disponibilités utilise la fonction d’intégration de données pour synchroniser les données entre plusieurs instances de Supply Chain Management et Sales.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span> <span data-ttu-id="bd8f0-108">Les modèles de prospects en disponibilités disponibles avec la fonction d’intégration de données activent le flux de données relatifs aux comptes, contacts, produits, devis de vente, commandes client et factures client entre Supply Chain Management et Sales.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="bd8f0-109">L’illustration ci-dessous indique comment les données sont synchronisées entre Supply Chain Management et Sales.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-109">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="bd8f0-110">[![Flux de données dans Prospect en disponibilités](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="bd8f0-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="bd8f0-111">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="bd8f0-111">Templates and tasks</span></span>

<span data-ttu-id="bd8f0-112">Pour accéder à des modèles disponibles, ouvrez [Centre d’administrateur PowerApps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="bd8f0-112">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="bd8f0-113">Sélectionnez **Projets**, puis, dans le coin supérieur droit, sélectionnez **Nouveau projet** pour sélectionner les modèles publics.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="bd8f0-114">Les modèles et tâches sous-jacentes suivants sont utilisés pour synchroniser les tables Contacts (Contacts) de Sales avec les tables Contacts (Clients) de Supply Chain Management :</span><span class="sxs-lookup"><span data-stu-id="bd8f0-114">The following templates and underlying tasks are used to synchronize Contact (Contacts) tables in Sales to Contact (Customers) tables in Supply Chain Management.</span></span>

- <span data-ttu-id="bd8f0-115">**Noms des modèles dans l’intégration des données**</span><span class="sxs-lookup"><span data-stu-id="bd8f0-115">**Names of the templates in Data integration**</span></span>

    - <span data-ttu-id="bd8f0-116">Contacts (Sales vers Supply Chain Management) - Direct</span><span class="sxs-lookup"><span data-stu-id="bd8f0-116">Contacts (Sales to Supply Chain Management) - Direct</span></span>
    - <span data-ttu-id="bd8f0-117">Contacts vers Customer (Sales vers Supply Chain Management) - Direct</span><span class="sxs-lookup"><span data-stu-id="bd8f0-117">Contacts to Customer (Sales to Supply Chain Management) - Direct</span></span>

- <span data-ttu-id="bd8f0-118">**Noms des tâches dans le projet d’intégration de données**</span><span class="sxs-lookup"><span data-stu-id="bd8f0-118">**Names of the tasks in the Data integration project**</span></span>

    - <span data-ttu-id="bd8f0-119">Contacts</span><span class="sxs-lookup"><span data-stu-id="bd8f0-119">Contacts</span></span>
    - <span data-ttu-id="bd8f0-120">ContactToCustomer</span><span class="sxs-lookup"><span data-stu-id="bd8f0-120">ContactToCustomer</span></span>

<span data-ttu-id="bd8f0-121">La tâche suivante de synchronisation est requise avant que la synchronisation du contact puisse avoir lieu : Comptes (Sales vers Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="bd8f0-121">The following synchronization task is required before contact synchronization can occur: Accounts (Sales to Supply Chain Management)</span></span>

## <a name="entity-sets"></a><span data-ttu-id="bd8f0-122">Ensembles d’entités</span><span class="sxs-lookup"><span data-stu-id="bd8f0-122">Entity sets</span></span>

| <span data-ttu-id="bd8f0-123">Vente</span><span class="sxs-lookup"><span data-stu-id="bd8f0-123">Sales</span></span>    | <span data-ttu-id="bd8f0-124">Gestion de la chaîne d’approvisionnement</span><span class="sxs-lookup"><span data-stu-id="bd8f0-124">Supply Chain Management</span></span> |
|----------|------------------------|
| <span data-ttu-id="bd8f0-125">Contacts</span><span class="sxs-lookup"><span data-stu-id="bd8f0-125">Contacts</span></span> | <span data-ttu-id="bd8f0-126">Contacts Dataverse</span><span class="sxs-lookup"><span data-stu-id="bd8f0-126">Dataverse Contacts</span></span>           |
| <span data-ttu-id="bd8f0-127">Contacts</span><span class="sxs-lookup"><span data-stu-id="bd8f0-127">Contacts</span></span> | <span data-ttu-id="bd8f0-128">Clients V2</span><span class="sxs-lookup"><span data-stu-id="bd8f0-128">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="bd8f0-129">Flux d’entité</span><span class="sxs-lookup"><span data-stu-id="bd8f0-129">Entity flow</span></span>

<span data-ttu-id="bd8f0-130">Les contacts sont gérés dans Sales et synchronisés sur Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-130">Contacts are managed in Sales and synchronized to Supply Chain Management.</span></span>

<span data-ttu-id="bd8f0-131">Un contact dans Sales peut devenir un contact ou un client dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-131">A contact in Sales can become either a contact or a customer in Supply Chain Management.</span></span> <span data-ttu-id="bd8f0-132">Pour déterminer si un contact dans Sales doit être synchronisé avec Supply Chain Management en tant que contact ou client, le système recherche les propriétés suivantes sur le contact dans Sales :</span><span class="sxs-lookup"><span data-stu-id="bd8f0-132">To determine whether a contact in Sales should be synchronized to Supply Chain Management as a contact or a customer, the system looks at the following properties on the contact in Sales:</span></span>

- <span data-ttu-id="bd8f0-133">**Synchronisation avec un client dans Supply Chain Management :** Contacts là où **Client actif** est défini sur **Oui**</span><span class="sxs-lookup"><span data-stu-id="bd8f0-133">**Synchronization to a customer in Supply Chain Management:** Contacts where **Is Active Customer** is set to **Yes**</span></span>
- <span data-ttu-id="bd8f0-134">**Synchronisation avec un contact dans Supply Chain Management :** Contacts là où **Client actif** est défini sur **Non** et **Société** (compte parent/contact) pointe vers un compte (pas un contact)</span><span class="sxs-lookup"><span data-stu-id="bd8f0-134">**Synchronization to a contact in Supply Chain Management:** Contacts where **Is Active Customer** is set to **No** and **Company** (parent account/contact) points to an account (not a contact)</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="bd8f0-135">Prospect pour une solution de disponibilités pour Sales</span><span class="sxs-lookup"><span data-stu-id="bd8f0-135">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="bd8f0-136">Une nouvelle colonne **Client actif** a été ajoutée au contact.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-136">A new **Is Active Customer** column has been added to the contact.</span></span> <span data-ttu-id="bd8f0-137">Cette colonne permet de différencier les contacts qui disposent d’activités commerciales et les contacts qui n’ont pas d’activités commerciales.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-137">This column is used to differentiate contacts that have sales activity and contacts that don't have sales activity.</span></span> <span data-ttu-id="bd8f0-138">**Client actif** est défini sur **Oui** uniquement pour les contacts qui associés à des devis, des commandes, ou des factures.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-138">**Is Active Customer** is set to **Yes** only for contacts that have related quotations, orders, or invoices.</span></span> <span data-ttu-id="bd8f0-139">Seuls ces contacts sont synchronisés avec Supply Chain Management comme clients.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-139">Only those contacts are synchronized to Supply Chain Management as customers.</span></span>

<span data-ttu-id="bd8f0-140">Une nouvelle colonne **IsCompanyAnAccount** a été ajoutée au contact.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-140">A new **IsCompanyAnAccount** column has been added to the contact.</span></span> <span data-ttu-id="bd8f0-141">Cette colonne indique si un contact est lié à une société (compte parent/contact) du type **Compte**.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-141">This column indicates whether a contact is linked to a company (parent account/contact) of the **Account** type.</span></span> <span data-ttu-id="bd8f0-142">Ces informations servent à identifier les contacts qui doivent être synchronisés avec Supply Chain Management comme contacts.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-142">This information is used to identify contacts that should be synchronized to Supply Chain Management as contacts.</span></span>

<span data-ttu-id="bd8f0-143">Une nouvelle colonne **Numéro de contact** a été ajoutée au contact pour garantir une clé naturelle et unique pour l’intégration.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-143">A new **Contact Number** column has been added to the contact to help guarantee a natural and unique key for the integration.</span></span> <span data-ttu-id="bd8f0-144">Lorsqu’un nouveau contact est créé, une valeur **Numéro de contact** est automatiquement générée à l’aide d’une souche de numéros.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-144">When a new contact is created, a **Contact Number** value is automatically generated by using a number sequence.</span></span> <span data-ttu-id="bd8f0-145">La valeur est composée de **CON**, suivi d’une souche de numéros croissante et d’un suffixe de six caractères.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-145">The value consists of **CON**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="bd8f0-146">Voici un exemple : **CON-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="bd8f0-146">Here is an example: **CON-01000-BVRCPS**</span></span>

<span data-ttu-id="bd8f0-147">Lorsque la solution d’intégration pour Sales est appliquée, un script de mise à niveau définit la colonne **Numéro de contact** pour des contact existants à l’aide de la souche de numéros qui a été précédemment mentionnée.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-147">When the integration solution for Sales is applied, an upgrade script sets the **Contact Number** column for existing contacts by using the number sequence that was mentioned earlier.</span></span> <span data-ttu-id="bd8f0-148">Le script de mise à niveau définit également la colonne **Client actif** sur **Oui** pour tous les contacts qui disposent d’activités commerciales.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-148">The upgrade script also sets the **Is Active Customer** column to **Yes** for any contacts that have sales activity.</span></span>

## <a name="in-supply-chain-management"></a><span data-ttu-id="bd8f0-149">Dans Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="bd8f0-149">In Supply Chain Management</span></span>

<span data-ttu-id="bd8f0-150">Les contacts sont étiquetés à l’aide de la propriété **IsContactPersonExternallyMaintained**.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-150">Contacts are tagged by using the **IsContactPersonExternallyMaintained** property.</span></span> <span data-ttu-id="bd8f0-151">Cette propriété indique qu’un contact donné est conservé en externe.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-151">This property indicates that a given contact is maintained externally.</span></span> <span data-ttu-id="bd8f0-152">Dans ce cas, les contacts tenus à jour en externe sont tenus à jour dans Sales.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-152">In this case, externally maintained contacts are maintained in Sales.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="bd8f0-153">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="bd8f0-153">Preconditions and mapping setup</span></span>

### <a name="contact-to-customer"></a><span data-ttu-id="bd8f0-154">Contact vers client</span><span class="sxs-lookup"><span data-stu-id="bd8f0-154">Contact to customer</span></span>

- <span data-ttu-id="bd8f0-155">**CustomerGroup** est obligatoire dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-155">**CustomerGroup** is required in Supply Chain Management.</span></span> <span data-ttu-id="bd8f0-156">Pour éviter toute erreur de synchronisation, vous pouvez spécifier une valeur par défaut dans la mise en correspondance.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-156">To help prevent synchronization errors, you can specify a default value in the mapping.</span></span> <span data-ttu-id="bd8f0-157">Cette valeur par défaut est alors utilisée si la colonne est laissée vide dans Sales.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-157">That default value is then used if the column is left blank in Sales.</span></span>

    <span data-ttu-id="bd8f0-158">Le modèle de valeur par défaut est **10**.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-158">The default template value is **10**.</span></span>

- <span data-ttu-id="bd8f0-159">En ajoutant les mises en correspondance suivantes, vous pouvez réduire le nombre de mises à jour manuelles requises dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-159">By adding the following mappings, you can help reduce the number of manual updates that are required in Supply Chain Management.</span></span> <span data-ttu-id="bd8f0-160">Vous pouvez utiliser une valeur par défaut ou une mise en correspondance des valeurs, par exemple, **Pays/région** ou **Ville**.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-160">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="bd8f0-161">**SiteId** – Site par défaut qui peut également être défini dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-161">**SiteId** – A default site can also be defined on products in Supply Chain Management.</span></span> <span data-ttu-id="bd8f0-162">Un site est requis pour générer des lignes de devis et de commandes client dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-162">A site is required in order to generate quotations and sales orders in Supply Chain Management.</span></span>

        <span data-ttu-id="bd8f0-163">Aucun modèle de valeur pour **SiteId** n’est défini.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-163">A template value for **SiteId** isn't defined.</span></span>

    - <span data-ttu-id="bd8f0-164">**WarehouseId** – Entrepôt par défaut qui peut également être défini dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-164">**WarehouseId** – A default warehouse can also be defined on products in Supply Chain Management.</span></span> <span data-ttu-id="bd8f0-165">Un entrepôt est requis pour générer des lignes de devis et de commandes client dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-165">A warehouse is required in order to generate quotations and sales orders in Supply Chain Management.</span></span>

        <span data-ttu-id="bd8f0-166">Aucun modèle de valeur pour **WarehouseId** n’est défini.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-166">A template value for **WarehouseId** isn't defined.</span></span>

    - <span data-ttu-id="bd8f0-167">**LanguageId** – Un langage est requis pour générer des lignes de devis et de commande client dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-167">**LanguageId** – A language is required in order to generate quotations and sales orders in Supply Chain Management.</span></span>
    
        <span data-ttu-id="bd8f0-168">Le modèle de valeur par défaut **en-us**.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-168">The default template value for is **en-us**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="bd8f0-169">Mise en correspondance de modèles dans l’intégration de données</span><span class="sxs-lookup"><span data-stu-id="bd8f0-169">Template mapping in Data integration</span></span>

<span data-ttu-id="bd8f0-170">Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l’intégration de données.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-170">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="bd8f0-171">La mise en correspondance indique quelles informations de la colonne sont synchronisées entre Sales et Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bd8f0-171">The mapping shows which column information will be synchronized from Sales to Supply Chain Management.</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="bd8f0-172">Contact vers contact</span><span class="sxs-lookup"><span data-stu-id="bd8f0-172">Contact to contact</span></span>

![Mise en correspondance de modèles dans l’intégrateur de données](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer"></a><span data-ttu-id="bd8f0-174">Contact vers client</span><span class="sxs-lookup"><span data-stu-id="bd8f0-174">Contact to customer</span></span>

![Mise en correspondance de modèles dans l’intégrateur de données](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a><span data-ttu-id="bd8f0-176">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="bd8f0-176">Related topics</span></span>

[<span data-ttu-id="bd8f0-177">Prospect en disponibilités</span><span class="sxs-lookup"><span data-stu-id="bd8f0-177">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="bd8f0-178">Synchroniser directement les comptes provenant du module Sales sur les clients de Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="bd8f0-178">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="bd8f0-179">Synchroniser directement les produits provenant du module Supply Chain Management sur les produits dans Sales</span><span class="sxs-lookup"><span data-stu-id="bd8f0-179">Synchronize products directly from Supply Chain Management to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="bd8f0-180">Synchronisation des commandes client directement entre Sales et Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="bd8f0-180">Synchronization of sales orders directly between Sales and Supply Chain Management</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="bd8f0-181">Synchroniser les en-têtes et les lignes de facture client directement entre le module Supply Chain Management et Sales</span><span class="sxs-lookup"><span data-stu-id="bd8f0-181">Synchronize sales invoice headers and lines directly from Supply Chain Management to Sales</span></span>](sales-invoice-template-mapping-direct.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]