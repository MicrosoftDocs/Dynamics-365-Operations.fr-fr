---
title: Conseils sur la configuration de la double écriture
description: Cette rubrique décrit les scénarios pris en charge pour la configuration en double écriture.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 10/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 47c07dd0e2f311b61297340a48a5a31cb1de3903
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685663"
---
# <a name="guidance-for-dual-write-setup"></a><span data-ttu-id="3800e-103">Conseils sur la configuration de la double écriture</span><span class="sxs-lookup"><span data-stu-id="3800e-103">Guidance for dual-write setup</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="3800e-104">Vous pouvez configurer une connexion en double écriture entre un environnement Finance and Operations et un environnement Dataverse.</span><span class="sxs-lookup"><span data-stu-id="3800e-104">You can set up a dual-write connection between a Finance and Operations environment and a Dataverse environment.</span></span>

+ <span data-ttu-id="3800e-105">Un environnement **Finance and Operations** offre la plateforme sous-jacente pour les applications **Finance and Operations** (par exemple, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce et Dynamics 365 Human Resources).</span><span class="sxs-lookup"><span data-stu-id="3800e-105">A **Finance and Operations environment** provides the underlying platform for **Finance and Operations apps** (for example, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce, and Dynamics 365 Human Resources).</span></span>
+ <span data-ttu-id="3800e-106">Un **environnement Dataverse** offre à la plateforme sous-jacente les **applications Customer Engagement** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing et Dynamics 365 Project Service Automation).</span><span class="sxs-lookup"><span data-stu-id="3800e-106">A **Dataverse environment** provides the underlying platform for **customer engagement apps** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3800e-107">Le module Human Resources dans Dynamics 365 Finance prend en charge les connexions en double écriture, mais l’application Dynamics 365 Human Resources, non.</span><span class="sxs-lookup"><span data-stu-id="3800e-107">The Human Resources module in Dynamics 365 Finance supports dual-write connections, but the Dynamics 365 Human Resources app doesn't.</span></span>

<span data-ttu-id="3800e-108">Le mécanisme de configuration varie en fonction de votre abonnement et de l’environnement :</span><span class="sxs-lookup"><span data-stu-id="3800e-108">The setup mechanism varies, depending on your subscription and the environment:</span></span>

+ <span data-ttu-id="3800e-109">Pour les nouvelles instances des applications Finance and Operations, la configuration d’une connexion en double écriture commence dans Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="3800e-109">For new instances of Finance and Operations apps, the setup of a dual-write connection begins in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="3800e-110">Si vous avez une licence pour Microsoft Power Platform, vous obtiendrez un nouvel environnement Dataverse si votre client n’en a pas.</span><span class="sxs-lookup"><span data-stu-id="3800e-110">If you have a license for Microsoft Power Platform, you will get a new Dataverse environment if your tenant doesn't have one.</span></span>
+ <span data-ttu-id="3800e-111">Pour les applications Finance and Operations des instances existantes, la configuration d’une connexion en double écriture commence dans l’environnement Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3800e-111">For existing instances Finance and Operations apps, the setup of a dual-write connection begins in the Finance and Operations environment.</span></span>

<span data-ttu-id="3800e-112">Avant de commencer la double écriture sur une entité, vous pouvez exécuter une synchronisation initiale pour gérer les données existantes des deux côtés : des applications Finance and Operations et des applications d’engagement client.</span><span class="sxs-lookup"><span data-stu-id="3800e-112">Before you start dual-write on an entity, you can run an initial synchronization to handle existing data on both sides: Finance and Operations apps and customer engagement apps.</span></span> <span data-ttu-id="3800e-113">Vous pouvez ignorer la synchronisation initiale si vous ne devez pas synchroniser les données entre les deux environnements.</span><span class="sxs-lookup"><span data-stu-id="3800e-113">You can skip the initial synchronization if you don't have to sync data between the two environments.</span></span>

<span data-ttu-id="3800e-114">Une synchronisation initiale vous permet de copier les données existantes d’une application vers une autre de manière bidirectionnelle.</span><span class="sxs-lookup"><span data-stu-id="3800e-114">An initial synchronization lets you copy existing data from one app to another bidirectionally.</span></span> <span data-ttu-id="3800e-115">Il existe plusieurs scénarios de configuration en fonction des environnements dont vous disposez déjà et du type de données qu’ils contiennent.</span><span class="sxs-lookup"><span data-stu-id="3800e-115">There are several setup scenarios, depending on the environments that you already have and the type of data in them.</span></span>

<span data-ttu-id="3800e-116">Les scénarios de configuration suivants sont pris en charge :</span><span class="sxs-lookup"><span data-stu-id="3800e-116">The following setup scenarios are supported:</span></span>

+ [<span data-ttu-id="3800e-117">Une nouvelle instance d’application Finance and Operations et une nouvelle instance d’application Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="3800e-117">A new Finance and Operations app instance and a new customer engagement app instance</span></span>](#new-new)
+ [<span data-ttu-id="3800e-118">Une nouvelle instance d’application Finance and Operations et une instance d’application Customer Engagement existante</span><span class="sxs-lookup"><span data-stu-id="3800e-118">A new Finance and Operations app instance and an existing customer engagement app instance</span></span>](#new-existing)
+ [<span data-ttu-id="3800e-119">Une nouvelle instance d’application Finance and Operations qui a des données et une nouvelle instance d’application Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="3800e-119">A new Finance and Operations app instance that has data and a new customer engagement app instance</span></span>](#new-data-new)
+ [<span data-ttu-id="3800e-120">Une nouvelle instance d’application Finance and Operations qui a des données et une instance d’application Customer Engagement existante</span><span class="sxs-lookup"><span data-stu-id="3800e-120">A new Finance and Operations app instance that has data and an existing customer engagement app instance</span></span>](#new-data-existing)
+ [<span data-ttu-id="3800e-121">Une instance d’application Finance and Operations existante et une nouvelle instance d’application Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="3800e-121">An existing Finance and Operations app instance and a new customer engagement app instance</span></span>](#existing-new)
+ [<span data-ttu-id="3800e-122">Une instance d’application Finance and Operations existante et une instance d’application Customer Engagement existante</span><span class="sxs-lookup"><span data-stu-id="3800e-122">An existing Finance and Operations app instance and an existing customer engagement app instance</span></span>](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a><span data-ttu-id="3800e-123">Une nouvelle instance d’application Finance and Operations et une nouvelle instance d’application Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="3800e-123">A new Finance and Operations app instance and a new customer engagement app instance</span></span>

<span data-ttu-id="3800e-124">Pour configurer une connexion en double écriture entre une nouvelle instance d’une application Finance and Operations qui n’a pas de données et une nouvelle instance d’une application Customer Engagement, suivez les étapes de [Configuration en double écriture depuis Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="3800e-124">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and a new instance of a customer engagement app, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="3800e-125">Une fois la configuration de la connexion terminée, les actions suivantes se produisent automatiquement :</span><span class="sxs-lookup"><span data-stu-id="3800e-125">When the connection setup is completed, the following actions automatically occur:</span></span>

- <span data-ttu-id="3800e-126">Un nouvel environnement Finance and Operations vide est provisionné.</span><span class="sxs-lookup"><span data-stu-id="3800e-126">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="3800e-127">Une nouvelle instance vide d’une application Customer Engagement est provisionnée lorsque la solution CRM principale est installée.</span><span class="sxs-lookup"><span data-stu-id="3800e-127">A new, empty instance of a customer engagement app is provisioned, where the CRM prime solution is installed.</span></span>
- <span data-ttu-id="3800e-128">Une connexion en double écriture est établie pour les données de la société DAT.</span><span class="sxs-lookup"><span data-stu-id="3800e-128">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="3800e-129">Les mappages de tables sont activés pour la synchronisation en direct.</span><span class="sxs-lookup"><span data-stu-id="3800e-129">Table maps are enabled for live synchronization.</span></span>

<span data-ttu-id="3800e-130">Les deux environnements sont alors prêts pour la synchronisation des données en direct.</span><span class="sxs-lookup"><span data-stu-id="3800e-130">Both environments are then ready for live data synchronization.</span></span>

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a><span data-ttu-id="3800e-131">Une nouvelle instance d’application Finance and Operations et une instance d’application Customer Engagement existante</span><span class="sxs-lookup"><span data-stu-id="3800e-131">A new Finance and Operations app instance and an existing customer engagement app instance</span></span>

<span data-ttu-id="3800e-132">Pour configurer une connexion en double écriture entre une nouvelle instance d’une application Finance and Operations qui n’a pas de données et une instance existante d’une application Customer Engagement, suivez les étapes de [Configuration en double écriture depuis Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="3800e-132">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and an existing instance of a customer engagement app, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="3800e-133">Une fois la configuration de la connexion terminée, les actions suivantes se produisent automatiquement :</span><span class="sxs-lookup"><span data-stu-id="3800e-133">When the connection setup is completed, the following actions automatically occur:</span></span>

- <span data-ttu-id="3800e-134">Un nouvel environnement Finance and Operations vide est provisionné.</span><span class="sxs-lookup"><span data-stu-id="3800e-134">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="3800e-135">Une connexion en double écriture est établie pour les données de la société DAT.</span><span class="sxs-lookup"><span data-stu-id="3800e-135">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="3800e-136">Les mappages de tables sont activés pour la synchronisation en direct.</span><span class="sxs-lookup"><span data-stu-id="3800e-136">Table maps are enabled for live synchronization.</span></span>

<span data-ttu-id="3800e-137">Les deux environnements sont alors prêts pour la synchronisation des données en direct.</span><span class="sxs-lookup"><span data-stu-id="3800e-137">Both environments are then ready for live data synchronization.</span></span>

<span data-ttu-id="3800e-138">Pour synchroniser les données Dataverse existantes à l’application Finance and Operations, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3800e-138">To sync the existing Dataverse data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="3800e-139">Créez une entreprise dans l’application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3800e-139">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="3800e-140">Ajoutez l’entreprise à la configuration de la connexion en double écriture.</span><span class="sxs-lookup"><span data-stu-id="3800e-140">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="3800e-141">[Amorcez](bootstrap-company-data.md) les données Dataverse à l’aide d’un code d’entreprise à trois lettres de l’Organisation internationale de normalisation (ISO).</span><span class="sxs-lookup"><span data-stu-id="3800e-141">[Bootstrap](bootstrap-company-data.md) the Dataverse data by using a three-letter International Organization for Standardization (ISO) company code.</span></span>
4. <span data-ttu-id="3800e-142">Exécutez la fonctionnalité **Synchronisation initiale** pour les tables pour lesquelles vous souhaitez synchroniser les données.</span><span class="sxs-lookup"><span data-stu-id="3800e-142">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="3800e-143">Pour obtenir des liens vers un exemple et une autre approche, consultez la section [Exemple](#example) plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="3800e-143">For links to an example and an alternative approach, see the [Example](#example) section later in this topic.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a><span data-ttu-id="3800e-144">Une nouvelle instance d’application Finance and Operations qui a des données et une nouvelle instance d’application Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="3800e-144">A new Finance and Operations app instance that has data and a new customer engagement app instance</span></span>

<span data-ttu-id="3800e-145">Pour configurer une connexion en double écriture entre une nouvelle instance d’une application Finance and Operations contenant des données et une nouvelle instance d’une application Customer Engagement, suivez les étapes dans la section [Une nouvelle instance d’application Finance and Operations et une nouvelle instance d’application Customer Engagement](#new-new) plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="3800e-145">To set up a dual-write connection between a new instance of a Finance and Operations app that has data and a new instance of a customer engagement app, follow the steps in the [A new Finance and Operations app instance and a new customer engagement app instance](#new-new) section earlier in this topic.</span></span> <span data-ttu-id="3800e-146">Une fois la configuration de la connexion terminée, si vous souhaitez synchroniser les données avec l’application Customer Engagement, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3800e-146">When the connection setup is completed, if you want to sync the data to the customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="3800e-147">Ouvrez l’application Finance and Operations à partir de la page LCS, connectez-vous, puis accédez à **Gestion des données \> Double écriture**.</span><span class="sxs-lookup"><span data-stu-id="3800e-147">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="3800e-148">Exécutez la fonctionnalité **Synchronisation initiale** pour les tables pour lesquelles vous souhaitez synchroniser les données.</span><span class="sxs-lookup"><span data-stu-id="3800e-148">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="3800e-149">Pour obtenir des liens vers un exemple et une autre approche, consultez la section [Exemple](#example).</span><span class="sxs-lookup"><span data-stu-id="3800e-149">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a><span data-ttu-id="3800e-150">Une nouvelle instance d’application Finance and Operations qui a des données et une instance d’application Customer Engagement existante</span><span class="sxs-lookup"><span data-stu-id="3800e-150">A new Finance and Operations app instance that has data and an existing customer engagement app instance</span></span>

<span data-ttu-id="3800e-151">Pour configurer une connexion en double écriture entre une nouvelle instance d’une application Finance and Operations contenant des données et une instance existante d’une application Customer Engagement, suivez les étapes dans la section [Une nouvelle instance d’application Finance and Operations et une instance d’application Customer Engagement existante](#new-existing) plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="3800e-151">To set up a dual-write connection between a new instance of a Finance and Operations app that has data and an existing instance of a customer engagement app, follow the steps in the [A new Finance and Operations app instance and an existing customer engagement app instance](#new-existing) section earlier in this topic.</span></span> <span data-ttu-id="3800e-152">Une fois la configuration de la connexion terminée, si vous souhaitez synchroniser les données avec l’application Customer Engagement, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3800e-152">When the connection setup is completed, if you want to sync the data to the customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="3800e-153">Ouvrez l’application Finance and Operations à partir de la page LCS, connectez-vous, puis accédez à **Gestion des données \> Double écriture**.</span><span class="sxs-lookup"><span data-stu-id="3800e-153">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="3800e-154">Exécutez la fonctionnalité **Synchronisation initiale** pour les tables pour lesquelles vous souhaitez synchroniser les données.</span><span class="sxs-lookup"><span data-stu-id="3800e-154">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="3800e-155">Pour synchroniser les données Dataverse existantes à l’application Finance and Operations, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3800e-155">To sync the existing Dataverse data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="3800e-156">Créez une entreprise dans l’application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3800e-156">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="3800e-157">Ajoutez l’entreprise à la configuration de la connexion en double écriture.</span><span class="sxs-lookup"><span data-stu-id="3800e-157">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="3800e-158">[Amorcez](bootstrap-company-data.md) les données Dataverse à l’aide du code d’entreprise à trois lettres de l’Organisation internationale de normalisation (ISO).</span><span class="sxs-lookup"><span data-stu-id="3800e-158">[Bootstrap](bootstrap-company-data.md) the Dataverse data by using a three-letter ISO company code.</span></span>
4. <span data-ttu-id="3800e-159">Exécutez la fonctionnalité **Synchronisation initiale** pour les tables pour lesquelles vous souhaitez synchroniser les données.</span><span class="sxs-lookup"><span data-stu-id="3800e-159">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="3800e-160">Pour obtenir des liens vers un exemple et une autre approche, consultez la section [Exemple](#example).</span><span class="sxs-lookup"><span data-stu-id="3800e-160">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a><span data-ttu-id="3800e-161">Une instance d’application Finance and Operations existante et une nouvelle instance d’application Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="3800e-161">An existing Finance and Operations app instance and a new customer engagement app instance</span></span>

<span data-ttu-id="3800e-162">La configuration d’une connexion en double écriture entre une instance existante d’une application Finance and Operations et une nouvelle instance d’une application Customer Engagement se produit dans l’environnement Finance and Operation.</span><span class="sxs-lookup"><span data-stu-id="3800e-162">The setup of a dual-write connection between an existing instance of a Finance and Operations app and a new instance of a customer engagement app occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="3800e-163">[Configurez la connexion à partir de l’application Finance and Operations](enable-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="3800e-163">[Set up the connection from the Finance and Operations app](enable-dual-write.md).</span></span>
2. <span data-ttu-id="3800e-164">Exécutez la fonctionnalité **Synchronisation initiale** pour les tables pour lesquelles vous souhaitez synchroniser les données.</span><span class="sxs-lookup"><span data-stu-id="3800e-164">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="3800e-165">Pour obtenir des liens vers un exemple et une autre approche, consultez la section [Exemple](#example).</span><span class="sxs-lookup"><span data-stu-id="3800e-165">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a><span data-ttu-id="3800e-166">Une instance d’application Finance and Operations existante et une instance d’application Customer Engagement existante</span><span class="sxs-lookup"><span data-stu-id="3800e-166">An existing Finance and Operations app instance and an existing customer engagement app instance</span></span>

<span data-ttu-id="3800e-167">La configuration d’une connexion en double écriture entre une instance existante d’une application Finance and Operations et une instance existante d’une application d’engagement client se produit dans l’environnement Finance and Operation.</span><span class="sxs-lookup"><span data-stu-id="3800e-167">The setup of a dual-write connection between an existing instance of a Finance and Operations app and an existing instance of a customer engagement app occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="3800e-168">[Configurez la connexion à partir de l’application Finance and Operations](enable-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="3800e-168">[Set up the connection from the Finance and Operations app](enable-dual-write.md).</span></span>
2. <span data-ttu-id="3800e-169">Pour synchroniser les données Dataverse existantes avec l’application Finance and Operations, [amorcez](bootstrap-company-data.md) les données Dataverse à l’aide d’un code d’entreprise ISO à trois lettres.</span><span class="sxs-lookup"><span data-stu-id="3800e-169">To sync the existing Dataverse data to the Finance and Operations app, [bootstrap](bootstrap-company-data.md) the Dataverse data by using a three-letter ISO company code.</span></span>
3. <span data-ttu-id="3800e-170">Exécutez la fonctionnalité **Synchronisation initiale** pour les tables pour lesquelles vous souhaitez synchroniser les données.</span><span class="sxs-lookup"><span data-stu-id="3800e-170">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="3800e-171">Pour obtenir des liens vers un exemple et une autre approche, consultez la section [Exemple](#example).</span><span class="sxs-lookup"><span data-stu-id="3800e-171">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="example"></a><span data-ttu-id="3800e-172">Exemple</span><span class="sxs-lookup"><span data-stu-id="3800e-172">Example</span></span>

<span data-ttu-id="3800e-173">Pour un exemple, voir [Activation de la carte des tables Clients V3 – Contacts](enable-entity-map.md#enable-table-map)</span><span class="sxs-lookup"><span data-stu-id="3800e-173">For an example, see [Enabling the Customers V3—Contacts table map](enable-entity-map.md#enable-table-map)</span></span>

<span data-ttu-id="3800e-174">Pour une approche alternative basée sur les volumes de données dans chaque entité qui doivent exécuter une synchronisation initiale, voir [Considérations relatives à la synchronisation initiale](initial-sync-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="3800e-174">For an alternative approach that is based on data volumes in each entity that must run an initial synchronization, see [Considerations for initial synchronization](initial-sync-guidance.md).</span></span>
