---
title: Synchronisez les Contacts de Sales sur les contacts ou clients de Finance and Operations
description: "Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les Contacts (Contacts) et Contacts (Clients) de Microsoft Dynamics 365 for Sales à Microsoft Dynamics 365 for Finance and Operations, édition Entreprise."
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
ms.openlocfilehash: c838fef502f643c764fade9cd79ae770ffc36974
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---

# <a name="synchronize-contacts-from-sales-to-contacts-or-customers-in-finance-and-operations"></a><span data-ttu-id="6f02a-103">Synchronisez les Contacts de Sales sur les contacts ou clients de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="6f02a-103">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="6f02a-104">Avant d'utiliser le prospect pour une solution de disponibilités, vous devez connaître [Intégration de données Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="6f02a-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="6f02a-105">Cette rubrique présente les modèles et les tâches sous-jacentes utilisés pour synchroniser les entités Contact (Contacts) et Contact (Clients) de Microsoft Dynamics 365 for Sales (Sales) à Microsoft Dynamics 365 for Finance and Operations, édition Entreprise (Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="6f02a-105">This topic discusses the templates and underlying tasks that are used to synchronize Contact (Contacts) entities and Contact (Customers) from Microsoft Dynamics 365 for Sales (Sales) to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="6f02a-106">Modèles et tâches</span><span class="sxs-lookup"><span data-stu-id="6f02a-106">Templates and tasks</span></span>

<span data-ttu-id="6f02a-107">Les modèles et tâches sous-jacentes suivants sont utilisés pour synchroniser les Contacts (Contacts) de Sales avec les Contacts (Clients) de Finance and Operations :</span><span class="sxs-lookup"><span data-stu-id="6f02a-107">The following templates and underlying tasks are used to synchronize Contact (Contacts) in Sales to Contact (Customers) in Finance and Operations:</span></span>

- <span data-ttu-id="6f02a-108">**Nom des modèles :**</span><span class="sxs-lookup"><span data-stu-id="6f02a-108">**Names of the templates:**</span></span>

    - <span data-ttu-id="6f02a-109">Contacts (Entre Sales et Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="6f02a-109">Contacts (Sales to Fin and Ops)</span></span>
    - <span data-ttu-id="6f02a-110">Contacts vers Client (Sales vers Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="6f02a-110">Contacts to Customer (Sales to Fin and Ops)</span></span>

- <span data-ttu-id="6f02a-111">**Noms des tâches du projet :**</span><span class="sxs-lookup"><span data-stu-id="6f02a-111">**Names of the tasks in the project:**</span></span>

    - <span data-ttu-id="6f02a-112">Contacts</span><span class="sxs-lookup"><span data-stu-id="6f02a-112">Contacts</span></span>
    - <span data-ttu-id="6f02a-113">ContactToCustomer</span><span class="sxs-lookup"><span data-stu-id="6f02a-113">ContactToCustomer</span></span>

<span data-ttu-id="6f02a-114">La tâche suivante de synchronisation est requise avant la synchronisation de Contact : Comptes (Sales vers Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="6f02a-114">The following synchronization task is required before Contact synchronization: Accounts (Sales to Fin and Ops)</span></span>

## <a name="entity-sets"></a><span data-ttu-id="6f02a-115">Ensembles d'entités</span><span class="sxs-lookup"><span data-stu-id="6f02a-115">Entity sets</span></span>

| <span data-ttu-id="6f02a-116">Vente</span><span class="sxs-lookup"><span data-stu-id="6f02a-116">Sales</span></span>    | <span data-ttu-id="6f02a-117">CDS</span><span class="sxs-lookup"><span data-stu-id="6f02a-117">CDS</span></span>     | <span data-ttu-id="6f02a-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="6f02a-118">Finance and Operations</span></span> |
|----------|---------|------------------------|
| <span data-ttu-id="6f02a-119">Contacts</span><span class="sxs-lookup"><span data-stu-id="6f02a-119">Contacts</span></span> | <span data-ttu-id="6f02a-120">Contact</span><span class="sxs-lookup"><span data-stu-id="6f02a-120">Contact</span></span> | <span data-ttu-id="6f02a-121">Contacts CDS</span><span class="sxs-lookup"><span data-stu-id="6f02a-121">CDS Contacts</span></span>           |
| <span data-ttu-id="6f02a-122">Contacts</span><span class="sxs-lookup"><span data-stu-id="6f02a-122">Contacts</span></span> | <span data-ttu-id="6f02a-123">Compte</span><span class="sxs-lookup"><span data-stu-id="6f02a-123">Account</span></span> | <span data-ttu-id="6f02a-124">Clients V2</span><span class="sxs-lookup"><span data-stu-id="6f02a-124">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="6f02a-125">Flux d'entité</span><span class="sxs-lookup"><span data-stu-id="6f02a-125">Entity flow</span></span>

<span data-ttu-id="6f02a-126">Les contacts sont gérés dans Sales, et sont synchronisés avec Common Data Service (CDS) et Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6f02a-126">Contacts are managed in Sales, and are synchronized to Common Data Service (CDS) and Finance and Operations.</span></span>

<span data-ttu-id="6f02a-127">Un contact dans Sales peut devenir un contact dans CDS et Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6f02a-127">A Contact in Sales can become a Contact in CDS and Finance and Operations.</span></span> <span data-ttu-id="6f02a-128">Sinon, il peut devenir un compte dans CDS et un client dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6f02a-128">Alternatively, it can become an Account in CDS and a Customer in Finance and Operations.</span></span> <span data-ttu-id="6f02a-129">Pour déterminer si un contact doit être collecté rapidement de Sales pour la synchronisation avec CDS et Finance and Operations (par exemple, Contacts dans Sales &gt; Contact dans CDS &gt; Contacts dans Finance and Operations), les système recherche les propriétés suivantes sur le contact dans Sales :</span><span class="sxs-lookup"><span data-stu-id="6f02a-129">To determine whether a contact should be picked up in Sales for synchronization to CDS and Finance and Operations (for example, Contacts in Sales &gt; Contact in CDS &gt; Contacts in Finance and Operations), the system looks at the following properties on Contact in Sales:</span></span>

- <span data-ttu-id="6f02a-130">**Synchronisation avec Compte dans CDS et Client dans Finance and Operations :** Contacts là où **Client actif** est défini sur **Oui**</span><span class="sxs-lookup"><span data-stu-id="6f02a-130">**Sync to Account in CDS and Customer in Finance and Operations:** Contacts where **Is Active Customer** is set to **Yes**</span></span>
- <span data-ttu-id="6f02a-131">**Synchronisation avec Contact dans CDS et Contact dans Finance and Operations :** Contacts là où **Client actif** est défini sur **Non** et **Société** (Compte parent/Contact) pointe vers un Compte (pas un Contact)</span><span class="sxs-lookup"><span data-stu-id="6f02a-131">**Sync to Contact in CDS and Contact in Finance and Operations:** Contacts where **Is Active Customer** is set to **No** and **Company** (Parent Account/Contact) points to an Account (not a Contact)</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="6f02a-132">Prospect pour une solution de disponibilités pour Sales</span><span class="sxs-lookup"><span data-stu-id="6f02a-132">Prospect to cash solution for Sales</span></span> 

<span data-ttu-id="6f02a-133">Un nouveau champ **Client actif** a été ajouté au Contact.</span><span class="sxs-lookup"><span data-stu-id="6f02a-133">A new **Is Active Customer** field has been added to the Contact.</span></span> <span data-ttu-id="6f02a-134">Ce champ permet de différencier les contacts qui disposent d'activités commerciales et les contacts qui n'ont pas d'activités commerciales.</span><span class="sxs-lookup"><span data-stu-id="6f02a-134">This field is used to differentiate Contacts that have sales activity and Contacts that don't have sales activity.</span></span> <span data-ttu-id="6f02a-135">**Client actif** est défini sur **Oui** uniquement pour les Contacts qui associés à des devis, des commandes, ou des factures.</span><span class="sxs-lookup"><span data-stu-id="6f02a-135">**Is Active Customer** is set to **Yes** only for Contacts that have related quotations, orders, or invoices.</span></span> <span data-ttu-id="6f02a-136">Seuls ces contacts sont synchronisés avec Finance and Operations comme clients.</span><span class="sxs-lookup"><span data-stu-id="6f02a-136">Only those Contacts are synchronized to Finance and Operations as Customers.</span></span>

<span data-ttu-id="6f02a-137">Un nouveau champ **IsCompanyAnAccount** a été ajouté au Contact.</span><span class="sxs-lookup"><span data-stu-id="6f02a-137">A new **IsCompanyAnAccount** field has been added to the Contact.</span></span> <span data-ttu-id="6f02a-138">Ce champ permet d'indiquer si le contact est lié à une société parent (Compte parent/Contact) du type **Compte**.</span><span class="sxs-lookup"><span data-stu-id="6f02a-138">This field is used to indicate whether a Contact is linked to a Company (Parent Account/Contact) of the **Account** type.</span></span> <span data-ttu-id="6f02a-139">Ces informations servent à identifier les contacts qui doivent être synchronisés avec Finance and Operations comme contacts.</span><span class="sxs-lookup"><span data-stu-id="6f02a-139">This information is used to identify Contacts that should be synchronized to Finance and Operations as Contacts.</span></span>

<span data-ttu-id="6f02a-140">Un nouveau champ **Numéro de contact** a été ajouté au contact pour garantir une clé naturelle et unique pour l'intégration.</span><span class="sxs-lookup"><span data-stu-id="6f02a-140">A new **Contact Number** field has been added to the Contact to help guarantee a natural and unique key for the integration.</span></span> <span data-ttu-id="6f02a-141">Lorsqu'un nouveau contact est créé, une valeur **Numéro de contact** est automatiquement générée à l'aide d'une souche de numéros.</span><span class="sxs-lookup"><span data-stu-id="6f02a-141">When a new Contact is created, a **Contact Number** value is automatically generated by using a number sequence.</span></span> <span data-ttu-id="6f02a-142">La valeur est composée de **CON**, suivi d'une souche de numéros croissante et d'un suffixe de six caractères.</span><span class="sxs-lookup"><span data-stu-id="6f02a-142">The value consists of **CON**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="6f02a-143">Voici un exemple : **CON-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="6f02a-143">Here is an example: **CON-01000-BVRCPS**</span></span>

<span data-ttu-id="6f02a-144">Lorsque la solution d'intégration pour Sales est ajoutée à Sales, le script de mise à niveau définit le champ **Numéro de contact** pour des contact existants à l'aide de la souche de numéros qui a été précédemment évoquées.</span><span class="sxs-lookup"><span data-stu-id="6f02a-144">When the integration solution for Sales is added to Sales, an upgrade script sets the **Contact Number** field for existing Contacts by using the number sequence that was discussed earlier.</span></span> <span data-ttu-id="6f02a-145">Le script de mise à niveau définit également le champ **Client actif** sur **Oui** pour tous les contacts qui disposent d'activités commerciales.</span><span class="sxs-lookup"><span data-stu-id="6f02a-145">The upgrade script also sets the **Is Active Customer** field to **Yes** for any Contacts that have sales activity.</span></span>

## <a name="in-finance-and-operations"></a><span data-ttu-id="6f02a-146">Dans Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="6f02a-146">In Finance and Operations</span></span> 

<span data-ttu-id="6f02a-147">Les contacts sont étiquetés à l'aide de la propriété **IsContactPersonExternallyMaintained**.</span><span class="sxs-lookup"><span data-stu-id="6f02a-147">Contacts are tagged by using the **IsContactPersonExternallyMaintained** property.</span></span> <span data-ttu-id="6f02a-148">Cette propriété indique qu'un contact donné est conservé en externe.</span><span class="sxs-lookup"><span data-stu-id="6f02a-148">This property indicates that a given Contact is maintained externally.</span></span> <span data-ttu-id="6f02a-149">Dans ce cas, les contacts tenus à jour en externe sont tenus à jour dans Sales.</span><span class="sxs-lookup"><span data-stu-id="6f02a-149">In this case, externally maintained Contacts are maintained in Sales.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="6f02a-150">Conditions préalables et paramétrage de mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="6f02a-150">Preconditions and mapping setup</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="6f02a-151">Contact vers Contact</span><span class="sxs-lookup"><span data-stu-id="6f02a-151">Contact to Contact</span></span>

- <span data-ttu-id="6f02a-152">Mettez à jour **ID organisation CDS** dans la mise en correspondance **Source &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="6f02a-152">Update **CDS Organization ID** in the **Source &gt; CDS** mapping.</span></span>

    - <span data-ttu-id="6f02a-153">La valeur par défaut du modèle pour **Organization_OrganizationId [ID organisation]** est **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="6f02a-153">The default template value for **Organization_OrganizationId [Organization ID]** is **ORG001**.</span></span>
    - <span data-ttu-id="6f02a-154">La valeur par défaut du modèle pour **PrimaryAccount_Organization_OrganizationId [Organization ID]** est **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="6f02a-154">The default template value for **PrimaryAccount_Organization_OrganizationId [Organization ID]** is **ORG001**.</span></span>

- <span data-ttu-id="6f02a-155">**Adresse Pays Région Code** est requis dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6f02a-155">**Address Country region code** is required in Finance and Operations.</span></span> <span data-ttu-id="6f02a-156">Pour éviter toute erreur de synchronisation, vous pouvez spécifier une valeur par défaut dans la mise en correspondance **CDS &gt; Operations**.</span><span class="sxs-lookup"><span data-stu-id="6f02a-156">To avoid synchronization errors, you can specify a default value in the **CDS &gt; Operations** mapping.</span></span> <span data-ttu-id="6f02a-157">Cette valeur par défaut est alors utilisée si le champ est laissé vide dans Sales.</span><span class="sxs-lookup"><span data-stu-id="6f02a-157">That default value is then used if the field is left blank in Sales.</span></span> <span data-ttu-id="6f02a-158">Le modèle de valeur par défaut pour **PrimaryAddressCountryRegionISOCode** est **USA**.</span><span class="sxs-lookup"><span data-stu-id="6f02a-158">The default template value for **PrimaryAddressCountryRegionISOCode** is **USA**.</span></span>
- <span data-ttu-id="6f02a-159">Assurez-vous qu'une valeur pour le champ suivant existe dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6f02a-159">Make sure that a value for the following field exists in Finance and Operations.</span></span> <span data-ttu-id="6f02a-160">Si ces informations ne sont pas obligatoires dans Finance and Operations, vous pouvez supprimer la mise en correspondance de la mise en correspondance **CDS &gt; Destination**.</span><span class="sxs-lookup"><span data-stu-id="6f02a-160">If the information isn't required in Finance and Operations, you can remove the mapping from the **CDS &gt; Destination** mapping.</span></span>

    - <span data-ttu-id="6f02a-161">**Nom de champ dans Finance and Operations :** Décision</span><span class="sxs-lookup"><span data-stu-id="6f02a-161">**Field name in Finance and Operations:** Decision</span></span>
    - <span data-ttu-id="6f02a-162">**Mise en correspondance :** PrimaryAccountRole = DecisionMakingRole</span><span class="sxs-lookup"><span data-stu-id="6f02a-162">**Mapping:** PrimaryAccountRole = DecisionMakingRole</span></span>

### <a name="contact-to-customer"></a><span data-ttu-id="6f02a-163">Contact vers Client</span><span class="sxs-lookup"><span data-stu-id="6f02a-163">Contact to Customer</span></span>

- <span data-ttu-id="6f02a-164">Mettez à jour **ID organisation CDS** dans la mise en correspondance **Source &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="6f02a-164">Update **CDS Organization ID** in the **Source &gt; CDS** mapping.</span></span> <span data-ttu-id="6f02a-165">La valeur par défaut du modèle pour **Organization_OrganizationId [ID organisation]** est **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="6f02a-165">The default template value for **Organization_OrganizationId [Organization ID]** is **ORG001**.</span></span>
- <span data-ttu-id="6f02a-166">**Adresse Pays Région Code** est requis dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6f02a-166">**Address Country region code** is required in Finance and Operations.</span></span> <span data-ttu-id="6f02a-167">Pour éviter toute erreur de synchronisation, vous pouvez spécifier une valeur par défaut dans la mise en correspondance **CDS &gt; Destination**.</span><span class="sxs-lookup"><span data-stu-id="6f02a-167">To avoid synchronization errors, you can specify a default value in the **CDS &gt; Destination** mapping.</span></span> <span data-ttu-id="6f02a-168">Cette valeur par défaut est alors utilisée si le champ est laissé vide dans Sales.</span><span class="sxs-lookup"><span data-stu-id="6f02a-168">That default value is then used if the field is left blank in Sales.</span></span> <span data-ttu-id="6f02a-169">Le modèle de valeur par défaut pour **PrimaryAddressCountryRegionISOCode** est **USA**.</span><span class="sxs-lookup"><span data-stu-id="6f02a-169">The default template value for **PrimaryAddressCountryRegionISOCode** is **USA**.</span></span>
- <span data-ttu-id="6f02a-170">**CustomerGroup** est requis dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6f02a-170">**CustomerGroup** is required in Finance and Operations.</span></span> <span data-ttu-id="6f02a-171">Pour éviter toute erreur de synchronisation, vous pouvez spécifier une valeur par défaut dans la mise en correspondance **CDS &gt; Destination**.</span><span class="sxs-lookup"><span data-stu-id="6f02a-171">To avoid synchronization errors, you can specify a default value in the **CDS &gt; Destination** mapping.</span></span> <span data-ttu-id="6f02a-172">Cette valeur par défaut est alors utilisée si le champ est laissé vide dans Sales.</span><span class="sxs-lookup"><span data-stu-id="6f02a-172">That default value is then used if the field is left blank in Sales.</span></span> <span data-ttu-id="6f02a-173">Le modèle de valeur par défaut pour **CustomerGroupId** est **10**.</span><span class="sxs-lookup"><span data-stu-id="6f02a-173">The default template value for **CustomerGroupId** is **10**.</span></span>
- <span data-ttu-id="6f02a-174">En ajoutant les mises en correspondance suivantes de **CDS &gt; Destination**, vous pouvez réduire le nombre de mises à jour manuelles dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6f02a-174">By adding the following mappings from **CDS &gt; Destination**, you can help reduce the number of manual updates that are in Finance and Operations.</span></span> <span data-ttu-id="6f02a-175">Vous pouvez utiliser une valeur par défaut ou une mise en correspondance des valeurs, par exemple, **Pays/région** ou **Ville**.</span><span class="sxs-lookup"><span data-stu-id="6f02a-175">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="6f02a-176">**SiteId** : Site par défaut qui peut également être défini dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6f02a-176">**SiteId** - A default site can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="6f02a-177">Un site est requis pour générer des lignes de devis et de commandes client dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6f02a-177">A site is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="6f02a-178">Aucun modèle de valeur pour **SiteId** n'est défini.</span><span class="sxs-lookup"><span data-stu-id="6f02a-178">A template value for **SiteId** isn't defined.</span></span>
    - <span data-ttu-id="6f02a-179">**WarehouseId** : Entrepôt par défaut qui peut également être défini dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6f02a-179">**WarehouseId** - A default warehouse can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="6f02a-180">Un entrepôt est requis pour générer des lignes de devis et de commandes client dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6f02a-180">A warehouse is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="6f02a-181">Aucun modèle de valeur pour **WarehouseId** n'est défini.</span><span class="sxs-lookup"><span data-stu-id="6f02a-181">A template value for **WarehouseId** isn't defined.</span></span>
    - <span data-ttu-id="6f02a-182">**LanguageId** : Une langue est requise pour générer des devis et des commandes client dans Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6f02a-182">**LanguageId** - A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="6f02a-183">Le modèle de valeur par défaut pour **LanguageId** est **en-us**.</span><span class="sxs-lookup"><span data-stu-id="6f02a-183">The default template value for **LanguageId** is **en-us**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="6f02a-184">Mise en correspondance de modèles dans l'intégrateur de données</span><span class="sxs-lookup"><span data-stu-id="6f02a-184">Template mapping in data integrator</span></span>

<span data-ttu-id="6f02a-185">Les illustrations suivantes présentent un exemple de modèle de mise en correspondance dans l'intégrateur de données.</span><span class="sxs-lookup"><span data-stu-id="6f02a-185">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="6f02a-186">Contact vers Contact</span><span class="sxs-lookup"><span data-stu-id="6f02a-186">Contact to Contact</span></span>

![Mise en correspondance de modèles dans l'intégrateur de données](./media/contacts-template-mapping-data-integrator-1.png)

![Modèle de mise en correspondance pour les contacts dans l'intégrateur de données](./media/contacts-template-mapping-data-integrator-2.png)

### <a name="contact-to-customer"></a><span data-ttu-id="6f02a-189">Contact vers Client</span><span class="sxs-lookup"><span data-stu-id="6f02a-189">Contact to Customer</span></span>

![Mise en correspondance de modèles dans l'intégrateur de données](./media/contacts-template-mapping-data-integrator-3.png)

![Modèle de mise en correspondance pour les contacts dans l'intégrateur de données](./media/contacts-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a><span data-ttu-id="6f02a-192">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="6f02a-192">Related topics</span></span>

[<span data-ttu-id="6f02a-193">Synchronisez les produits de Finance and Operations sur les produits de Sales</span><span class="sxs-lookup"><span data-stu-id="6f02a-193">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="6f02a-194">Synchronisez les comptes des ventes aux clients de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="6f02a-194">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="6f02a-195">Synchroniser les en-têtes et les lignes de devis de vente provenant du module Sales sur Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="6f02a-195">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="6f02a-196">Synchroniser les en-têtes et les lignes de commande client provenant du module Finance and Operations sur Sales</span><span class="sxs-lookup"><span data-stu-id="6f02a-196">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>](sales-order-template-mapping.md)

[<span data-ttu-id="6f02a-197">Synchroniser les en-têtes et les lignes de facture client provenant du module Finance and Operations sur Sales</span><span class="sxs-lookup"><span data-stu-id="6f02a-197">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping.md)

