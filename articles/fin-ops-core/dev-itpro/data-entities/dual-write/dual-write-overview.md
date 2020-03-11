---
title: Vue d'ensemble de la double écriture
description: Cette rubrique donne une vue d'ensemble de la double écriture. La double écriture est une infrastructure qui fournit une interaction en temps quasi réel entre les applications pilotées par modèle de Microsoft Dynamics 365 et les applications Finance and Operations.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 02/06/2020
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
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 12c6a39700a260c138fab67ed370f94b3aa04213
ms.sourcegitcommit: a688c864fc609e35072ad8fd2c01d71f6a5ee7b9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/20/2020
ms.locfileid: "3075983"
---
# <a name="dual-write-overview"></a><span data-ttu-id="1f50d-104">Vue d'ensemble de la double écriture</span><span class="sxs-lookup"><span data-stu-id="1f50d-104">Dual-write overview</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

## <a name="what-is-dual-write"></a><span data-ttu-id="1f50d-105">Qu'est-ce que la double écriture ?</span><span class="sxs-lookup"><span data-stu-id="1f50d-105">What is dual-write?</span></span>

<span data-ttu-id="1f50d-106">La double écriture est une infrastructure prête à l'emploi qui fournit une interaction en temps quasi réel entre les applications pilotées par modèle de Microsoft Dynamics 365 et les applications Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1f50d-106">Dual-write is an out-of-box infrastructure that provides near-real-time interaction between model-driven apps in Microsoft Dynamics 365 and Finance and Operations apps.</span></span> <span data-ttu-id="1f50d-107">Lorsque les données sur les clients, les produits, les personnes et les opérations vont au-delà des limites de l'application, tous les départements d'une organisation sont habilités.</span><span class="sxs-lookup"><span data-stu-id="1f50d-107">When data about customers, products, people, and operations flows beyond application boundaries, all departments in an organization are empowered.</span></span>

<span data-ttu-id="1f50d-108">La double écriture offre une intégration bidirectionnelle étroitement couplée entre les applications Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="1f50d-108">Dual-write provides tightly coupled, bidirectional integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="1f50d-109">Toute modification de données dans les applications Finance and Operations provoque des écritures dans Common Data Service et toute modification de données dans Common Data Service provoque des écritures dans les applications Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1f50d-109">Any data change in Finance and Operations apps causes writes to Common Data Service, and any data change in Common Data Service causes writes to Finance and Operations apps.</span></span> <span data-ttu-id="1f50d-110">Ce flux de données automatisé offre une expérience utilisateur intégrée dans les différentes applications.</span><span class="sxs-lookup"><span data-stu-id="1f50d-110">This automated data flow provides an integrated user experience across the apps.</span></span>

![Relation de données entre les applications](media/dual-write-overview.jpg)

<span data-ttu-id="1f50d-112">La double écriture a deux aspects : un aspect *infrastructure* et un aspect *application*.</span><span class="sxs-lookup"><span data-stu-id="1f50d-112">Dual-write has two aspects: an *infrastructure* aspect and an *application* aspect.</span></span>

### <a name="infrastructure"></a><span data-ttu-id="1f50d-113">Infrastructure</span><span class="sxs-lookup"><span data-stu-id="1f50d-113">Infrastructure</span></span>

<span data-ttu-id="1f50d-114">L'infrastructure de double écriture est extensible et fiable et comprend les fonctionnalités clés suivantes :</span><span class="sxs-lookup"><span data-stu-id="1f50d-114">The dual-write infrastructure is extensible and reliable, and includes the following key features:</span></span>

+ <span data-ttu-id="1f50d-115">Flux de données synchrone et bidirectionnel entre les applications</span><span class="sxs-lookup"><span data-stu-id="1f50d-115">Synchronous and bidirectional data flow between applications</span></span>
+ <span data-ttu-id="1f50d-116">Synchronisation avec les modes lecture, pause et rattrapage pour prendre en charge le système pendant les modes en ligne et hors connexion/asynchrone.</span><span class="sxs-lookup"><span data-stu-id="1f50d-116">Synchronization, together with play, pause, and catchup modes to support the system during online and offline/asynchronous modes.</span></span>
+ <span data-ttu-id="1f50d-117">Possibilité de synchroniser les données initiales entre les applications</span><span class="sxs-lookup"><span data-stu-id="1f50d-117">Ability to sync initial data between the applications</span></span>
+ <span data-ttu-id="1f50d-118">Vue consolidée des journaux d'activité et d'erreur pour les administrateurs de données</span><span class="sxs-lookup"><span data-stu-id="1f50d-118">Consolidated view of activity and error logs for data admins</span></span>
+ <span data-ttu-id="1f50d-119">Possibilité de configurer des alertes et des seuils personnalisés et de s'abonner aux notifications</span><span class="sxs-lookup"><span data-stu-id="1f50d-119">Ability to configure custom alerts and thresholds, and to subscribe to notifications</span></span>
+ <span data-ttu-id="1f50d-120">Interface utilisateur intuitive pour le filtrage et les transformations</span><span class="sxs-lookup"><span data-stu-id="1f50d-120">Intuitive user interface (UI) for filtering and transformations</span></span>
+ <span data-ttu-id="1f50d-121">Possibilité de définir et d'afficher les dépendances et les relations entre les entités</span><span class="sxs-lookup"><span data-stu-id="1f50d-121">Ability to set and view entity dependencies and relationships</span></span>
+ <span data-ttu-id="1f50d-122">Extensibilité pour les entités et les mappages standard et personnalisés</span><span class="sxs-lookup"><span data-stu-id="1f50d-122">Extensibility for both standard and custom entities and maps</span></span>
+ <span data-ttu-id="1f50d-123">Gestion fiable du cycle de vie des applications</span><span class="sxs-lookup"><span data-stu-id="1f50d-123">Reliable application lifecycle management</span></span>
+ <span data-ttu-id="1f50d-124">Expérience de configuration initiale pour les nouveaux clients</span><span class="sxs-lookup"><span data-stu-id="1f50d-124">Out-of-box setup experience for new customers</span></span>

### <a name="application"></a><span data-ttu-id="1f50d-125">Application</span><span class="sxs-lookup"><span data-stu-id="1f50d-125">Application</span></span>

<span data-ttu-id="1f50d-126">La double écriture crée un mappage entre les concepts des applications Finance and Operations et les concepts des applications pilotées par modèle de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="1f50d-126">Dual-write creates a mapping between concepts in Finance and Operations apps and concepts in model-driven apps in Dynamics 365.</span></span> <span data-ttu-id="1f50d-127">Cette intégration prend en charge les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="1f50d-127">This integration supports the following scenarios:</span></span>

+ <span data-ttu-id="1f50d-128">Données principales client intégrées</span><span class="sxs-lookup"><span data-stu-id="1f50d-128">Integrated customer master</span></span>
+ <span data-ttu-id="1f50d-129">Accès aux cartes de fidélité et aux points de récompense des clients</span><span class="sxs-lookup"><span data-stu-id="1f50d-129">Access to customer loyalty cards and reward points</span></span>
+ <span data-ttu-id="1f50d-130">Expérience de gestion des produits uniformisée</span><span class="sxs-lookup"><span data-stu-id="1f50d-130">Unified product mastering experience</span></span>
+ <span data-ttu-id="1f50d-131">Prise en charge de la hiérarchie d'organisation</span><span class="sxs-lookup"><span data-stu-id="1f50d-131">Awareness of organization hierarchy</span></span>
+ <span data-ttu-id="1f50d-132">Données principales fournisseur intégrées</span><span class="sxs-lookup"><span data-stu-id="1f50d-132">Integrated vendor master</span></span>
+ <span data-ttu-id="1f50d-133">Accès aux données de référence financières et fiscales</span><span class="sxs-lookup"><span data-stu-id="1f50d-133">Access to finance and tax reference data</span></span>
+ <span data-ttu-id="1f50d-134">Expérience du moteur de tarification à la demande</span><span class="sxs-lookup"><span data-stu-id="1f50d-134">On-demand price engine experience</span></span>
+ <span data-ttu-id="1f50d-135">Expérience Prospect en disponibilités intégrée</span><span class="sxs-lookup"><span data-stu-id="1f50d-135">Integrated prospect-to-cash experience</span></span>
+ <span data-ttu-id="1f50d-136">Possibilité de servir à la fois les actifs internes et les actifs client via des agents sur le terrain</span><span class="sxs-lookup"><span data-stu-id="1f50d-136">Ability to serve both in-house assets and customer assets through field agents</span></span>
+ <span data-ttu-id="1f50d-137">Expérience Approvisionnement au paiement intégrée</span><span class="sxs-lookup"><span data-stu-id="1f50d-137">Integrated procure-to-pay experience</span></span>
+ <span data-ttu-id="1f50d-138">Activités et notes intégrées pour les données et les documents du client</span><span class="sxs-lookup"><span data-stu-id="1f50d-138">Integrated activities and notes for customer data and documents</span></span>
+ <span data-ttu-id="1f50d-139">Possibilité de rechercher la disponibilité et les détails du stock disponible</span><span class="sxs-lookup"><span data-stu-id="1f50d-139">Ability to look up on-hand inventory availability and details</span></span>
+ <span data-ttu-id="1f50d-140">Expérience Projet en disponibilités</span><span class="sxs-lookup"><span data-stu-id="1f50d-140">Project-to-cash experience</span></span>
+ <span data-ttu-id="1f50d-141">Possibilité de gérer plusieurs adresses et rôles via le concept de partie</span><span class="sxs-lookup"><span data-stu-id="1f50d-141">Ability to handle multiple addresses and roles through the party concept</span></span>
+ <span data-ttu-id="1f50d-142">Gestion à source unique pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="1f50d-142">Single source management for users</span></span>
+ <span data-ttu-id="1f50d-143">Canaux intégrés pour la vente au détail et le marketing</span><span class="sxs-lookup"><span data-stu-id="1f50d-143">Integrated channels for retailing and marketing</span></span>
+ <span data-ttu-id="1f50d-144">Visibilité sur les promotions et les remises</span><span class="sxs-lookup"><span data-stu-id="1f50d-144">Visibility into promotions and discounts</span></span>
+ <span data-ttu-id="1f50d-145">Fonctions de demande de service</span><span class="sxs-lookup"><span data-stu-id="1f50d-145">Request-for-service functions</span></span>
+ <span data-ttu-id="1f50d-146">Opérations de service simplifiées</span><span class="sxs-lookup"><span data-stu-id="1f50d-146">Streamlined service operations</span></span>

## <a name="top-reasons-to-use-dual-write"></a><span data-ttu-id="1f50d-147">Principales raisons d'utiliser la double écriture</span><span class="sxs-lookup"><span data-stu-id="1f50d-147">Top reasons to use dual-write</span></span>

<span data-ttu-id="1f50d-148">La double écriture assure l'intégration des données entre les applications Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="1f50d-148">Dual-write provides data integration across Microsoft Dynamics 365 applications.</span></span> <span data-ttu-id="1f50d-149">Cette infrastructure robuste relie des environnements et permet à différentes applications métier de fonctionner ensemble.</span><span class="sxs-lookup"><span data-stu-id="1f50d-149">This robust framework links environments and enables different business applications to work together.</span></span> <span data-ttu-id="1f50d-150">Voici les principales raisons pour lesquelles vous devez utiliser la double écriture :</span><span class="sxs-lookup"><span data-stu-id="1f50d-150">Here are the top reasons why you should use dual-write:</span></span>

+ <span data-ttu-id="1f50d-151">La double écriture offre une intégration étroitement couplée, en temps quasi réel et bidirectionnelle entre les applications Finance and Operations et les applications pilotées par modèle de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="1f50d-151">Dual-write provides tightly coupled, near-real-time, and bidirectional integration between Finance and Operations apps and model-driven apps in Dynamics 365.</span></span> <span data-ttu-id="1f50d-152">Cette intégration fait de Microsoft Dynamics 365 un emplacement central pour toutes vos solutions d'entreprise.</span><span class="sxs-lookup"><span data-stu-id="1f50d-152">This integration makes Microsoft Dynamics 365 the one-stop shop for all your business solutions.</span></span> <span data-ttu-id="1f50d-153">Les clients qui utilisent Dynamics 365 Finance et Dynamics 365 Supply Chain Management, mais qui utilisent des solutions autres que Microsoft pour la gestion de la relation client, se tournent vers Dynamics 365 pour sa prise en charge de la double écriture.</span><span class="sxs-lookup"><span data-stu-id="1f50d-153">Customers who use Dynamics 365 Finance and Dynamics 365 Supply Chain Management, but who use non-Microsoft solutions for customer relationship management (CRM), are moving toward Dynamics 365 for its dual-write support.</span></span>
+ <span data-ttu-id="1f50d-154">Les données des clients, des produits, des opérations, des projets et de l'Internet des objets (IoT) sont automatiquement envoyées à Common Data Service via la double écriture.</span><span class="sxs-lookup"><span data-stu-id="1f50d-154">Data from customers, products, operations, projects, and the Internet of Things (IoT) automatically flows to Common Data Service through dual-write.</span></span> <span data-ttu-id="1f50d-155">Cette connexion est très utile pour les entreprises intéressées par les extensions Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="1f50d-155">This connection is very useful for businesses that are interested in Microsoft Power Platform expansions.</span></span>
+ <span data-ttu-id="1f50d-156">L'infrastructure de double écriture suit le principe no-code/low-code.</span><span class="sxs-lookup"><span data-stu-id="1f50d-156">The dual-write infrastructure follows the no-code/low-code principle.</span></span> <span data-ttu-id="1f50d-157">Un effort d'ingénierie minimal est nécessaire pour étendre les mappages entre tables standard et pour inclure des mappages personnalisés.</span><span class="sxs-lookup"><span data-stu-id="1f50d-157">Minimal engineering effort is required to extend the standard table-to-table maps and to include custom maps.</span></span>
+ <span data-ttu-id="1f50d-158">La double écriture prend en charge à la fois le mode en ligne et le mode hors connexion.</span><span class="sxs-lookup"><span data-stu-id="1f50d-158">Dual-write supports both online mode and offline mode.</span></span> <span data-ttu-id="1f50d-159">Microsoft est la seule société qui offre une prise en charge des modes en ligne et hors connexion.</span><span class="sxs-lookup"><span data-stu-id="1f50d-159">Microsoft is the only company that offers support for online and offline modes.</span></span>

## <a name="what-does-dual-write-mean-for-users-and-architects-of-crm-products"></a><span data-ttu-id="1f50d-160">Que signifie la double écriture pour les utilisateurs et les architectes des produits CRM ?</span><span class="sxs-lookup"><span data-stu-id="1f50d-160">What does dual-write mean for users and architects of CRM products?</span></span>

<span data-ttu-id="1f50d-161">La double écriture automatise le flux de données entre les applications Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="1f50d-161">Dual-write automates the data flow between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="1f50d-162">Dans les versions futures, les concepts des applications pilotées par modèle de Dynamics 365 (par exemple, client, contact, devis et commande) seront mis à l'échelle sur les clients milieu de gamme et haut de gamme.</span><span class="sxs-lookup"><span data-stu-id="1f50d-162">In future releases, concepts in model-driven apps in Dynamics 365 (for example, customer, contact, quotation, and order) will be scaled to mid-market and upper-mid-market customers.</span></span>

<span data-ttu-id="1f50d-163">Dans la première version, l'automatisation est gérée en grande partie par des solutions à double écriture.</span><span class="sxs-lookup"><span data-stu-id="1f50d-163">In the first release, most of the automation is handled by dual-write solutions.</span></span> <span data-ttu-id="1f50d-164">Dans les versions futures, ces solutions feront partie de Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="1f50d-164">In future releases, those solutions will become part of Common Data Service.</span></span> <span data-ttu-id="1f50d-165">En comprenant les modifications à venir dans Common Data Service, vous pouvez vous épargner des efforts à long terme.</span><span class="sxs-lookup"><span data-stu-id="1f50d-165">By understanding the upcoming changes to Common Data Service, you can save yourself effort in the long term.</span></span> <span data-ttu-id="1f50d-166">Voici quelques-une des modifications importantes :</span><span class="sxs-lookup"><span data-stu-id="1f50d-166">Here are some of the crucial changes:</span></span>

+ <span data-ttu-id="1f50d-167">Common Data Service aura de nouveaux concepts, comme la société et la partie.</span><span class="sxs-lookup"><span data-stu-id="1f50d-167">Common Data Service will have new concepts, such as company and party.</span></span> <span data-ttu-id="1f50d-168">Ces concepts affecteront toutes les applications reposant sur Common Data Service, comme Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service et Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="1f50d-168">These concepts will affect all apps that are built on Common Data Service, such as Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service, and Dynamics 365 Field Service.</span></span>
+ <span data-ttu-id="1f50d-169">Les activités et les notes sont unifiées et étendues pour prendre en charge à la fois les C1 (utilisateurs du système) et les C2 (clients du système).</span><span class="sxs-lookup"><span data-stu-id="1f50d-169">Activities and notes are unified and expanded to support both C1s (users of the system) and C2s (customers of the system).</span></span>
+ <span data-ttu-id="1f50d-170">Voici quelques-unes des modifications à venir dans Common Data Service :</span><span class="sxs-lookup"><span data-stu-id="1f50d-170">Here are some of the upcoming changes in Common Data Service:</span></span>

    - <span data-ttu-id="1f50d-171">Le type de données Décimal remplacera le type de données Devise.</span><span class="sxs-lookup"><span data-stu-id="1f50d-171">The decimal data type will replace the money data type.</span></span>
    - <span data-ttu-id="1f50d-172">Les dates de validité prendront en charge les données passées, présentes et futures au même emplacement.</span><span class="sxs-lookup"><span data-stu-id="1f50d-172">Date effectivity will support past, present, and future data in the same place.</span></span>
    - <span data-ttu-id="1f50d-173">Il y aura une plus grande prise en charge des devises et des taux de change, et l'API **Taux de change** sera révisée.</span><span class="sxs-lookup"><span data-stu-id="1f50d-173">There will be more support for currency and exchange rates, and the **Exchange Rate** application programming interface (API) will be revised.</span></span>
    - <span data-ttu-id="1f50d-174">Les conversions d'unités seront prises en charge.</span><span class="sxs-lookup"><span data-stu-id="1f50d-174">Unit conversions will be supported.</span></span>

<span data-ttu-id="1f50d-175">Pour plus d'informations sur les modifications à venir, voir [Données dans Common Data Service - phase 1 et 2](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/extensibility/extensibility-roadmap).</span><span class="sxs-lookup"><span data-stu-id="1f50d-175">For more information about upcoming changes, see [Data in Common Data Service – phase 1 & 2](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/extensibility/extensibility-roadmap).</span></span>
