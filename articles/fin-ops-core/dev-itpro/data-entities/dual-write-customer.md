---
title: Données principales client intégrées
description: Cette rubrique décrit l'intégration des données client entre Finance and Operations et Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 09d985e5c6816ec0c718aaf418f4e85fb828f1c6
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769681"
---
# <a name="integrated-customer-master"></a><span data-ttu-id="ecaf7-103">Données principales client intégrées</span><span class="sxs-lookup"><span data-stu-id="ecaf7-103">Integrated customer master</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ecaf7-104">Il est courant que des enregistrements client soient gérés dans plusieurs applications.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-104">It's typical for customer records to be mastered in more than one application.</span></span> <span data-ttu-id="ecaf7-105">Par exemple, l'activité de vente peut entraîner des enregistrements client commerciaux via une application Sales, et les ventes de commerce électronique ou au détail entraîner des enregistrements client via une application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-105">For example, sales activity can bring in commercial customer records through a Sales application, and e-Commerce or retail sales can bring in customer records through a Finance and Operations application.</span></span> <span data-ttu-id="ecaf7-106">Indépendamment de l'origine de l'enregistrement client, il est intégré en arrière-plan, au delà des limites de l'application et des différences de l'infrastructure.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-106">Regardless of where the customer record originates, it's integrated behind the scenes across application boundaries and infrastructure differences.</span></span> <span data-ttu-id="ecaf7-107">Les données principales client intégrées permettent de traiter des scénarios de multi-gestion et de fournir une vue d'ensemble du client à la suite d'applications Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-107">Integrated customer mastering helps handle multi-mastering scenarios and provides a comprehensive view of the customer to the Dynamics 365 application suite.</span></span>

## <a name="customer-data-flow"></a><span data-ttu-id="ecaf7-108">Flux de données client</span><span class="sxs-lookup"><span data-stu-id="ecaf7-108">Customer data flow</span></span>

<span data-ttu-id="ecaf7-109">*Client* est un concept bien défini dans les applications.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-109">*Customer* is a well-defined concept in applications.</span></span> <span data-ttu-id="ecaf7-110">Par conséquent, l'intégration des données client implique l'harmonisation du concept de client entre les deux applications.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-110">Therefore, the integration of customer data just involves harmonizing the customer concept between the two applications.</span></span> <span data-ttu-id="ecaf7-111">La relation des données est illustrée dans le flux de données client.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-111">The following illustration shows the customer data flow.</span></span>

![Flux de données client](media/dual-write-customer-data-flow.png)

<span data-ttu-id="ecaf7-113">Les clients peuvent être classés largement en deux types : les clients commerciaux/organisationnels et les consommateurs/utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-113">Customers can be broadly classified into two types: commercial/organizational customers and consumers/end users.</span></span> <span data-ttu-id="ecaf7-114">Ces deux types de clients sont stockés et gérés différemment dans Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-114">These two types of customers are stored and handled differently in Finance and Operations and Common Data Service.</span></span>

<span data-ttu-id="ecaf7-115">Dans Finance and Operations, des clients commerciaux/organisationnels et des consommateurs/utilisateurs finaux sont gérés dans une table unique nommée **CustTable** (CustomerCustomerV3Entity), et ils sont classés selon l'attribut **Type**.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-115">In Finance and Operations, both commercial/organizational customers and consumers/end users are mastered in a single table that is named **CustTable** (CustomerCustomerV3Entity), and they are classified based on the **Type** attribute.</span></span> <span data-ttu-id="ecaf7-116">(Si **Type** est défini sur **Organisation**, le client est commercial/organisationnel, et si **Type** est défini sur **Personne**, le client est client/utilisateur.) Les informations de principale personne à contacter sont traitées via l'entité de SMMContactPersonEntity.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-116">(If **Type** is set to **Organization**, the customer is a commercial/organizational customer, and if **Type** is set to **Person**, the customer is a consumer/end user.) The primary contact person information is handled through the SMMContactPersonEntity entity.</span></span>

<span data-ttu-id="ecaf7-117">Dans Common Data Service, les clients commerciaux/organisationnels sont gérés dans l'entité Compte et identifiés comme clients lorsque l'attribut **RelationshipType** est défini sur **Client**.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-117">In Common Data Service, commercial/organizational customers are mastered in the Account entity and are identified as customers when the **RelationshipType** attribute is set to **Customer**.</span></span> <span data-ttu-id="ecaf7-118">Les consommateurs/utilisateurs finaux et la personne à contacter sont représentés par l'entité Contact.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-118">Both consumers/end users and the contact person are represented by the Contact entity.</span></span> <span data-ttu-id="ecaf7-119">Pour fournir une séparation claire entre un consommateur/utilisateur final et une personne à contacter, l'entité **Contact** a un indicateur booléen nommé **Vendable**.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-119">To provide a clear separation between a consumer/end user and a contact person, the **Contact** entity has a Boolean flag that is named **Sellable**.</span></span> <span data-ttu-id="ecaf7-120">Lorsque **Vendable** est **True**, le contact est un consommateur/utilisateur final, et des devis et des commandes peuvent être créés pour ce contact.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-120">When **Sellable** is **True**, the contact is a consumer/end user, and quotations and orders can be created for that contact.</span></span> <span data-ttu-id="ecaf7-121">Lorsque **Vendable** est **False**, le contact est simplement une principale personne à contacter d'un client.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-121">When **Sellable** is **False**, the contact is just a primary contact person of a customer.</span></span>

<span data-ttu-id="ecaf7-122">Lorsqu'un contact non vendable participe à un processus de devis ou de commande, **Vendable** est défini sur **True** pour indiquer que le contact est un contact de vente.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-122">When a non-sellable contact participates in a quotation or order process, **Sellable** is set to **True** to flag the contact as a sellable contact.</span></span> <span data-ttu-id="ecaf7-123">Un contact qui devient un contact de vente reste un contact de vente.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-123">A contact that has become a sellable contact remains a sellable contact.</span></span>

## <a name="templates"></a><span data-ttu-id="ecaf7-124">Modèles</span><span class="sxs-lookup"><span data-stu-id="ecaf7-124">Templates</span></span>

<span data-ttu-id="ecaf7-125">Les données client incluent toutes les informations sur le client, telles que le groupe de clients, les adresses, les informations de contact, le profil de paiement, le profil de facture, et le statut de fidélité.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-125">Customer data includes all information about the customer, such as the customer group, addresses, contact information, payment profile, invoice profile, and loyalty status.</span></span> <span data-ttu-id="ecaf7-126">Un ensemble de mappages d'entités fonctionne ensemble pendant l'interaction des données client, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-126">A collection of entity maps works together during customer data interaction, as shown in the following table.</span></span>

<span data-ttu-id="ecaf7-127">Applications Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ecaf7-127">Finance and Operations apps</span></span> | <span data-ttu-id="ecaf7-128">Autres applications Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="ecaf7-128">Other Dynamics 365 apps</span></span>         | <span data-ttu-id="ecaf7-129">Description</span><span class="sxs-lookup"><span data-stu-id="ecaf7-129">Description</span></span>
----------------------------|---------------------------------|------------
<span data-ttu-id="ecaf7-130">Contacts CDS V2</span><span class="sxs-lookup"><span data-stu-id="ecaf7-130">CDS Contacts V2</span></span>             | <span data-ttu-id="ecaf7-131">contacts</span><span class="sxs-lookup"><span data-stu-id="ecaf7-131">contacts</span></span>                        | <span data-ttu-id="ecaf7-132">Ce modèle synchronise toutes les informations principales, secondaires et tertiaires de contact, à la fois pour les clients et les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-132">This template synchronizes all primary, secondary, and tertiary contact information, for both customers and vendors.</span></span>
<span data-ttu-id="ecaf7-133">Groupes de clients</span><span class="sxs-lookup"><span data-stu-id="ecaf7-133">Customer groups</span></span>             | <span data-ttu-id="ecaf7-134">msdyn_customergroups</span><span class="sxs-lookup"><span data-stu-id="ecaf7-134">msdyn_customergroups</span></span>            | <span data-ttu-id="ecaf7-135">Ce modèle synchronise les informations du groupe de clients.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-135">This template synchronizes customer group information.</span></span>
<span data-ttu-id="ecaf7-136">Modes de paiement des clients</span><span class="sxs-lookup"><span data-stu-id="ecaf7-136">Customer payment method</span></span>     | <span data-ttu-id="ecaf7-137">msdyn_customerpaymentmethods</span><span class="sxs-lookup"><span data-stu-id="ecaf7-137">msdyn_customerpaymentmethods</span></span>    | <span data-ttu-id="ecaf7-138">Ce modèle synchronise les informations de la méthode de paiement des clients.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-138">This template synchronizes customer payment method information.</span></span>
<span data-ttu-id="ecaf7-139">Clients V3</span><span class="sxs-lookup"><span data-stu-id="ecaf7-139">Customers V3</span></span>                | <span data-ttu-id="ecaf7-140">comptes</span><span class="sxs-lookup"><span data-stu-id="ecaf7-140">accounts</span></span>                        | <span data-ttu-id="ecaf7-141">Ce modèle synchronise les informations principales client pour les clients commerciaux et organisationnels.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-141">This template synchronizes customer master information for commercial and organizational customers.</span></span>
<span data-ttu-id="ecaf7-142">Clients V3</span><span class="sxs-lookup"><span data-stu-id="ecaf7-142">Customers V3</span></span>                | <span data-ttu-id="ecaf7-143">contacts</span><span class="sxs-lookup"><span data-stu-id="ecaf7-143">contacts</span></span>                        | <span data-ttu-id="ecaf7-144">Ce modèle synchronise les données principales de clients pour les clients et les utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-144">This template synchronizes customer master data for consumers and end users.</span></span>
<span data-ttu-id="ecaf7-145">Carte de fidélité</span><span class="sxs-lookup"><span data-stu-id="ecaf7-145">Loyalty card</span></span>                | <span data-ttu-id="ecaf7-146">msdyn_loyaltycards</span><span class="sxs-lookup"><span data-stu-id="ecaf7-146">msdyn_loyaltycards</span></span>              | <span data-ttu-id="ecaf7-147">Ce modèle synchronise les informations de carte de fidélité des clients.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-147">This template synchronizes customer loyalty card information.</span></span>
<span data-ttu-id="ecaf7-148">Affixes de nom</span><span class="sxs-lookup"><span data-stu-id="ecaf7-148">Name affixes</span></span>                | <span data-ttu-id="ecaf7-149">msdyn_nameaffixes</span><span class="sxs-lookup"><span data-stu-id="ecaf7-149">msdyn_nameaffixes</span></span>               | <span data-ttu-id="ecaf7-150">Ce modèle synchronise les données de référence des affixes de nom pour les clients et les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-150">This template synchronizes name affixes reference data, for both customers and vendors.</span></span>
<span data-ttu-id="ecaf7-151">Lignes de jour de paiement CDS V2</span><span class="sxs-lookup"><span data-stu-id="ecaf7-151">Payment day lines CDS V2</span></span>    | <span data-ttu-id="ecaf7-152">msdyn_paymentdaylines</span><span class="sxs-lookup"><span data-stu-id="ecaf7-152">msdyn_paymentdaylines</span></span>           | <span data-ttu-id="ecaf7-153">Ce modèle synchronise les données de référence des lignes du jour de paiement, pour les clients et les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-153">This template synchronizes payment day lines reference data, for both customers and vendors.</span></span>
<span data-ttu-id="ecaf7-154">Jours de paiement CDS</span><span class="sxs-lookup"><span data-stu-id="ecaf7-154">Payment days CDS</span></span>            | <span data-ttu-id="ecaf7-155">msdyn_paymentdays</span><span class="sxs-lookup"><span data-stu-id="ecaf7-155">msdyn_paymentdays</span></span>               | <span data-ttu-id="ecaf7-156">Ce modèle synchronise les données de référence des jours de paiement, pour les clients et les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-156">This template synchronizes payment days reference data, for both customers and vendors.</span></span>
<span data-ttu-id="ecaf7-157">Lignes d'échéancier de paiement</span><span class="sxs-lookup"><span data-stu-id="ecaf7-157">Payment schedule lines</span></span>      | <span data-ttu-id="ecaf7-158">msdyn_paymentschedulelines</span><span class="sxs-lookup"><span data-stu-id="ecaf7-158">msdyn_paymentschedulelines</span></span>      | <span data-ttu-id="ecaf7-159">Synchronise les références de données des lignes du programme de paiement, à la fois pour les clients et les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-159">Syncs payment schedule lines reference data, for both customers and vendors.</span></span>
<span data-ttu-id="ecaf7-160">Echéancier de paiement</span><span class="sxs-lookup"><span data-stu-id="ecaf7-160">Payment schedule</span></span>            | <span data-ttu-id="ecaf7-161">msdyn_paymentschedules</span><span class="sxs-lookup"><span data-stu-id="ecaf7-161">msdyn_paymentschedules</span></span>          | <span data-ttu-id="ecaf7-162">Ce modèle synchronise les données de référence du programme de paiement, pour les clients et les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-162">This template synchronizes payment schedule reference data, for both customers and vendors.</span></span>
<span data-ttu-id="ecaf7-163">Conditions de paiement</span><span class="sxs-lookup"><span data-stu-id="ecaf7-163">Terms of payment</span></span>            | <span data-ttu-id="ecaf7-164">msdyn_paymentterms</span><span class="sxs-lookup"><span data-stu-id="ecaf7-164">msdyn_paymentterms</span></span>              | <span data-ttu-id="ecaf7-165">Ce modèle synchronise les données de référence des conditions de paiement pour les clients et les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="ecaf7-165">This template synchronizes payment terms (terms of payment) reference data, for both customers and vendors.</span></span>

[!include [banner](../includes/dual-write-symbols.md)]

[!include [mapping contacts contacts](dual-write/CDSContactsV2-contacts.md)]

[!include [mapping customer group](dual-write/CustCustomerGroup-msdyn-customergroups.md)]

[!include [mapping customer payment method](dual-write/CustomerPaymentMethod-msdyn-customerpaymentmethods.md)]

[!include [mapping customer accounts](dual-write/CustomersV3-accounts.md)]

[!include [mapping customer contacts](dual-write/CustomersV3-contacts.md)]

[!include [mapping loyalty card](dual-write/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping name affixes](dual-write/NameAffixes-msdyn-nameaffixes.md)]

[!include [mapping payment day lines](dual-write/PaymentDayLinesCdsV2-msdyn-paymentdaylines.md)]

[!include [mapping payment days](dual-write/PaymentDaysCds-msdyn-paymentdays.md)]

[!include [mapping payment schedule lines](dual-write/PaymentScheduleLines-msdyn-paymentschedulelines.md)]

[!include [mapping payment schedules](dual-write/PaymentSchedules-msdyn-paymentschedules.md)]

[!include [mapping terms of payment](dual-write/TermsofPayment-msdyn-paymentterms.md)]
