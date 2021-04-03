---
title: Données principales client intégrées
description: Cette rubrique décrit l’intégration des données client entre Finance and Operations et Dataverse.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 402342b459c366d0e198e3d0e946deb1f9e81739
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568124"
---
# <a name="integrated-customer-master"></a><span data-ttu-id="d8987-103">Données principales client intégrées</span><span class="sxs-lookup"><span data-stu-id="d8987-103">Integrated customer master</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]


<span data-ttu-id="d8987-104">Les données client peuvent être gérées dans plusieurs applications Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d8987-104">Customer data can be mastered in more than one Dynamics 365 application.</span></span> <span data-ttu-id="d8987-105">Par exemple, une ligne client peut provenir d’une activité de vente dans Dynamics 365 Sales (une application basée sur un modèle dans Dynamics 365), ou une ligne peut provenir d’une activité de vente au détail dans Dynamics 365 Commerce (une application Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="d8987-105">For example, a customer row can originate though sales activity in Dynamics 365 Sales (a model-driven app in Dynamics 365), or a row can originate through retail activity in Dynamics 365 Commerce (a Finance and Operations app).</span></span> <span data-ttu-id="d8987-106">Peu importe d’où proviennent les données client, elles sont intégrées en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="d8987-106">No matter where where the customer data originates, it is integrated behind the scenes.</span></span> <span data-ttu-id="d8987-107">Le client principal intégré vous permet de gérer les données client dans n’importe quelle application Dynamics 365 et offre une vue complète du client dans la suite de l’application Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d8987-107">Integrated customer master gives you the flexibility to master customer data in any Dynamics 365 application and provides a comprehensive view of the customer across the Dynamics 365 application suite.</span></span>

## <a name="customer-data-flow"></a><span data-ttu-id="d8987-108">Flux de données client</span><span class="sxs-lookup"><span data-stu-id="d8987-108">Customer data flow</span></span>

<span data-ttu-id="d8987-109">*Client* est un concept bien défini dans les applications.</span><span class="sxs-lookup"><span data-stu-id="d8987-109">*Customer* is a well-defined concept in applications.</span></span> <span data-ttu-id="d8987-110">Par conséquent, l’intégration des données client implique l’harmonisation du concept de client entre les deux applications.</span><span class="sxs-lookup"><span data-stu-id="d8987-110">Therefore, the integration of customer data just involves harmonizing the customer concept between the two applications.</span></span> <span data-ttu-id="d8987-111">La relation des données est illustrée dans le flux de données client.</span><span class="sxs-lookup"><span data-stu-id="d8987-111">The following illustration shows the customer data flow.</span></span>

![Flux de données client](media/dual-write-customer-data-flow.png)

<span data-ttu-id="d8987-113">Les clients peuvent être classés largement en deux types : les clients commerciaux/organisationnels et les consommateurs/utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="d8987-113">Customers can be broadly classified into two types: commercial/organizational customers and consumers/end users.</span></span> <span data-ttu-id="d8987-114">Ces deux types de clients sont stockés et gérés différemment dans Finance and Operations et dans Dataverse.</span><span class="sxs-lookup"><span data-stu-id="d8987-114">These two types of customers are stored and handled differently in Finance and Operations and Dataverse.</span></span>

<span data-ttu-id="d8987-115">Dans Finance and Operations, des clients commerciaux/organisationnels et des consommateurs/utilisateurs finaux sont gérés dans une table unique nommée **CustTable** (CustCustomerV3Entity), et ils sont classés selon l’attribut **Type**.</span><span class="sxs-lookup"><span data-stu-id="d8987-115">In Finance and Operations, both commercial/organizational customers and consumers/end users are mastered in a single table that is named **CustTable** (CustCustomerV3Entity), and they are classified based on the **Type** attribute.</span></span> <span data-ttu-id="d8987-116">(Si **Type** est défini sur **Organisation**, le client est commercial/organisationnel, et si **Type** est défini sur **Personne**, le client est client/utilisateur.) Les informations de principale personne à contacter sont traitées via la table de SMMContactPersonEntity.</span><span class="sxs-lookup"><span data-stu-id="d8987-116">(If **Type** is set to **Organization**, the customer is a commercial/organizational customer, and if **Type** is set to **Person**, the customer is a consumer/end user.) The primary contact person information is handled through the SMMContactPersonEntity table.</span></span>

<span data-ttu-id="d8987-117">Dans Dataverse, les clients commerciaux/organisationnels sont gérés dans la table Compte et identifiés comme clients lorsque l’attribut **RelationshipType** est défini sur **Client**.</span><span class="sxs-lookup"><span data-stu-id="d8987-117">In Dataverse, commercial/organizational customers are mastered in the Account table and are identified as customers when the **RelationshipType** attribute is set to **Customer**.</span></span> <span data-ttu-id="d8987-118">Les consommateurs/utilisateurs finaux et la personne à contacter sont représentés par la table Contact.</span><span class="sxs-lookup"><span data-stu-id="d8987-118">Both consumers/end users and the contact person are represented by the Contact table.</span></span> <span data-ttu-id="d8987-119">Pour fournir une séparation claire entre un consommateur/utilisateur final et une personne à contacter, la table **Contact** a un indicateur booléen nommé **Vendable**.</span><span class="sxs-lookup"><span data-stu-id="d8987-119">To provide a clear separation between a consumer/end user and a contact person, the **Contact** table has a Boolean flag that is named **Sellable**.</span></span> <span data-ttu-id="d8987-120">Lorsque **Vendable** est **True**, le contact est un consommateur/utilisateur final, et des devis et des commandes peuvent être créés pour ce contact.</span><span class="sxs-lookup"><span data-stu-id="d8987-120">When **Sellable** is **True**, the contact is a consumer/end user, and quotations and orders can be created for that contact.</span></span> <span data-ttu-id="d8987-121">Lorsque **Vendable** est **False**, le contact est simplement une principale personne à contacter d’un client.</span><span class="sxs-lookup"><span data-stu-id="d8987-121">When **Sellable** is **False**, the contact is just a primary contact person of a customer.</span></span>

<span data-ttu-id="d8987-122">Lorsqu’un contact non vendable participe à un processus de devis ou de commande, **Vendable** est défini sur **True** pour indiquer que le contact est un contact de vente.</span><span class="sxs-lookup"><span data-stu-id="d8987-122">When a non-sellable contact participates in a quotation or order process, **Sellable** is set to **True** to flag the contact as a sellable contact.</span></span> <span data-ttu-id="d8987-123">Un contact qui devient un contact de vente reste un contact de vente.</span><span class="sxs-lookup"><span data-stu-id="d8987-123">A contact that has become a sellable contact remains a sellable contact.</span></span>

## <a name="templates"></a><span data-ttu-id="d8987-124">Modèles</span><span class="sxs-lookup"><span data-stu-id="d8987-124">Templates</span></span>

<span data-ttu-id="d8987-125">Les données client incluent toutes les informations sur le client, telles que le groupe de clients, les adresses, les informations de contact, le profil de paiement, le profil de facture, et le statut de fidélité.</span><span class="sxs-lookup"><span data-stu-id="d8987-125">Customer data includes all information about the customer, such as the customer group, addresses, contact information, payment profile, invoice profile, and loyalty status.</span></span> <span data-ttu-id="d8987-126">Un ensemble de mappages de tables fonctionne ensemble pendant l’interaction des données client, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="d8987-126">A collection of table maps works together during customer data interaction, as shown in the following table.</span></span>

<span data-ttu-id="d8987-127">Applications Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d8987-127">Finance and Operations apps</span></span> | <span data-ttu-id="d8987-128">Autres applications Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="d8987-128">Other Dynamics 365 apps</span></span>         | <span data-ttu-id="d8987-129">Description</span><span class="sxs-lookup"><span data-stu-id="d8987-129">Description</span></span>
----------------------------|---------------------------------|------------
<span data-ttu-id="d8987-130">Contacts CDS V2</span><span class="sxs-lookup"><span data-stu-id="d8987-130">CDS Contacts V2</span></span>             | <span data-ttu-id="d8987-131">contacts</span><span class="sxs-lookup"><span data-stu-id="d8987-131">contacts</span></span>                        | <span data-ttu-id="d8987-132">Ce modèle synchronise toutes les informations principales, secondaires et tertiaires de contact, à la fois pour les clients et les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="d8987-132">This template synchronizes all primary, secondary, and tertiary contact information, for both customers and vendors.</span></span>
<span data-ttu-id="d8987-133">Groupes de clients</span><span class="sxs-lookup"><span data-stu-id="d8987-133">Customer groups</span></span>             | <span data-ttu-id="d8987-134">msdyn_customergroups</span><span class="sxs-lookup"><span data-stu-id="d8987-134">msdyn_customergroups</span></span>            | <span data-ttu-id="d8987-135">Ce modèle synchronise les informations du groupe de clients.</span><span class="sxs-lookup"><span data-stu-id="d8987-135">This template synchronizes customer group information.</span></span>
<span data-ttu-id="d8987-136">Modes de paiement des clients</span><span class="sxs-lookup"><span data-stu-id="d8987-136">Customer payment method</span></span>     | <span data-ttu-id="d8987-137">msdyn_customerpaymentmethods</span><span class="sxs-lookup"><span data-stu-id="d8987-137">msdyn_customerpaymentmethods</span></span>    | <span data-ttu-id="d8987-138">Ce modèle synchronise les informations de la méthode de paiement des clients.</span><span class="sxs-lookup"><span data-stu-id="d8987-138">This template synchronizes customer payment method information.</span></span>
<span data-ttu-id="d8987-139">Clients V3</span><span class="sxs-lookup"><span data-stu-id="d8987-139">Customers V3</span></span>                | <span data-ttu-id="d8987-140">comptes</span><span class="sxs-lookup"><span data-stu-id="d8987-140">accounts</span></span>                        | <span data-ttu-id="d8987-141">Ce modèle synchronise les informations principales client pour les clients commerciaux et organisationnels.</span><span class="sxs-lookup"><span data-stu-id="d8987-141">This template synchronizes customer master information for commercial and organizational customers.</span></span>
<span data-ttu-id="d8987-142">Clients V3</span><span class="sxs-lookup"><span data-stu-id="d8987-142">Customers V3</span></span>                | <span data-ttu-id="d8987-143">contacts</span><span class="sxs-lookup"><span data-stu-id="d8987-143">contacts</span></span>                        | <span data-ttu-id="d8987-144">Ce modèle synchronise les données principales de clients pour les clients et les utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="d8987-144">This template synchronizes customer master data for consumers and end users.</span></span>
<span data-ttu-id="d8987-145">Affixes de nom</span><span class="sxs-lookup"><span data-stu-id="d8987-145">Name affixes</span></span>                | <span data-ttu-id="d8987-146">msdyn_nameaffixes</span><span class="sxs-lookup"><span data-stu-id="d8987-146">msdyn_nameaffixes</span></span>               | <span data-ttu-id="d8987-147">Ce modèle synchronise les données de référence des affixes de nom pour les clients et les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="d8987-147">This template synchronizes name affixes reference data, for both customers and vendors.</span></span>
<span data-ttu-id="d8987-148">Lignes de jour de paiement CDS V2</span><span class="sxs-lookup"><span data-stu-id="d8987-148">Payment day lines CDS V2</span></span>    | <span data-ttu-id="d8987-149">msdyn_paymentdaylines</span><span class="sxs-lookup"><span data-stu-id="d8987-149">msdyn_paymentdaylines</span></span>           | <span data-ttu-id="d8987-150">Ce modèle synchronise les données de référence des lignes du jour de paiement, pour les clients et les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="d8987-150">This template synchronizes payment day lines reference data, for both customers and vendors.</span></span>
<span data-ttu-id="d8987-151">Jours de paiement CDS</span><span class="sxs-lookup"><span data-stu-id="d8987-151">Payment days CDS</span></span>            | <span data-ttu-id="d8987-152">msdyn_paymentdays</span><span class="sxs-lookup"><span data-stu-id="d8987-152">msdyn_paymentdays</span></span>               | <span data-ttu-id="d8987-153">Ce modèle synchronise les données de référence des jours de paiement, pour les clients et les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="d8987-153">This template synchronizes payment days reference data, for both customers and vendors.</span></span>
<span data-ttu-id="d8987-154">Lignes d’échéancier de paiement</span><span class="sxs-lookup"><span data-stu-id="d8987-154">Payment schedule lines</span></span>      | <span data-ttu-id="d8987-155">msdyn_paymentschedulelines</span><span class="sxs-lookup"><span data-stu-id="d8987-155">msdyn_paymentschedulelines</span></span>      | <span data-ttu-id="d8987-156">Synchronise les références de données des lignes du programme de paiement, à la fois pour les clients et les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="d8987-156">Syncs payment schedule lines reference data, for both customers and vendors.</span></span>
<span data-ttu-id="d8987-157">Echéancier de paiement</span><span class="sxs-lookup"><span data-stu-id="d8987-157">Payment schedule</span></span>            | <span data-ttu-id="d8987-158">msdyn_paymentschedules</span><span class="sxs-lookup"><span data-stu-id="d8987-158">msdyn_paymentschedules</span></span>          | <span data-ttu-id="d8987-159">Ce modèle synchronise les données de référence du programme de paiement, pour les clients et les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="d8987-159">This template synchronizes payment schedule reference data, for both customers and vendors.</span></span>
<span data-ttu-id="d8987-160">Conditions de paiement</span><span class="sxs-lookup"><span data-stu-id="d8987-160">Terms of payment</span></span>            | <span data-ttu-id="d8987-161">msdyn_paymentterms</span><span class="sxs-lookup"><span data-stu-id="d8987-161">msdyn_paymentterms</span></span>              | <span data-ttu-id="d8987-162">Ce modèle synchronise les données de référence des conditions de paiement pour les clients et les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="d8987-162">This template synchronizes payment terms (terms of payment) reference data, for both customers and vendors.</span></span>

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping contacts contacts](includes/CDSContactsV2-contacts.md)]

[!include [mapping customer group](includes/CustCustomerGroup-msdyn-customergroups.md)]

[!include [mapping customer payment method](includes/CustomerPaymentMethod-msdyn-customerpaymentmethods.md)]

[!include [mapping customer accounts](includes/CustomersV3-accounts.md)]

[!include [mapping customer contacts](includes/CustomersV3-contacts.md)]

[!include [mapping name affixes](includes/NameAffixes-msdyn-nameaffixes.md)]

[!include [mapping payment day lines](includes/PaymentDayLinesCdsV2-msdyn-paymentdaylines.md)]

[!include [mapping payment days](includes/PaymentDaysCds-msdyn-paymentdays.md)]

[!include [mapping payment schedule lines](includes/PaymentScheduleLines-msdyn-paymentschedulelines.md)]

[!include [mapping payment schedules](includes/PaymentSchedules-msdyn-paymentschedules.md)]

[!include [mapping terms of payment](includes/TermsofPayment-msdyn-paymentterms.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]