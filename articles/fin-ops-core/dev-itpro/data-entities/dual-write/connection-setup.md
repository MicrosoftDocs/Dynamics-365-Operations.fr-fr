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
ms.openlocfilehash: 2d77a1458f3f4c79b231e6a6d7cc320b8ee1fad9
ms.sourcegitcommit: ee643d651d57560bccae2f99238faa39881f5c64
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/21/2020
ms.locfileid: "4088504"
---
# <a name="guidance-for-how-to-set-up-dual-write"></a><span data-ttu-id="86c58-103">Conseils sur la configuration de la double écriture</span><span class="sxs-lookup"><span data-stu-id="86c58-103">Guidance for how to set up dual-write</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="86c58-104">Vous pouvez configurer une connexion en double écriture entre un environnement Finance and Operations et un environnement Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="86c58-104">You can set up a dual-write connection between a Finance and Operations environment and a Common Data Service environment.</span></span>

+ <span data-ttu-id="86c58-105">Un **environnement Finance and Operations** offre la plateforme sous-jacente pour les **applications Finance and Operations** (par exemple, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management et Dynamics 365 Retail).</span><span class="sxs-lookup"><span data-stu-id="86c58-105">A **Finance and Operations environment** provides the underlying platform for **Finance and Operations apps** (for example, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, and Dynamics 365 Retail).</span></span>
+ <span data-ttu-id="86c58-106">Un **environnement Common Data Service** offre à la plateforme sous-jacente les **applications Customer Engagement** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing et Dynamics 365 Project Service Automation).</span><span class="sxs-lookup"><span data-stu-id="86c58-106">A **Common Data Service environment** provides the underlying platform for **customer engagement apps** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation).</span></span>

>[!IMPORTANT]
><span data-ttu-id="86c58-107">Human Resources dans Finance and Operations prend en charge les connexions en double écriture, mais l’application Dynamics 365 Human Resources, non.</span><span class="sxs-lookup"><span data-stu-id="86c58-107">Human Resources in Finance and Operations supports dual-write connections, but the Dynamics 365 Human Resources app doesn't.</span></span>

<span data-ttu-id="86c58-108">Le mécanisme de configuration varie en fonction de votre abonnement et de l’environnement.</span><span class="sxs-lookup"><span data-stu-id="86c58-108">The setup mechanism varies, depending on your subscription and the environment.</span></span>

+ <span data-ttu-id="86c58-109">Pour les nouvelles instances des applications Finance and Operations, la configuration d’une connexion en double écriture commence dans Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="86c58-109">For new instances of Finance and Operations apps, the setup of a dual-write connection begins in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="86c58-110">Si vous avez une licence pour Power Platform, vous obtiendrez un nouvel environnement Common Data Service si votre client n’en a pas.</span><span class="sxs-lookup"><span data-stu-id="86c58-110">If you have a license for Power Platform, you will get a new Common Data Service environment if your tenant doesn't have one.</span></span>
+ <span data-ttu-id="86c58-111">Pour les applications Finance and Operations des instances existantes, la configuration d’une connexion en double écriture commence dans l’environnement Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="86c58-111">For existing instances Finance and Operations apps, the setup of a dual-write connection begins in the Finance and Operations environment.</span></span>

<span data-ttu-id="86c58-112">Avant de commencer la double écriture sur une entité, vous pouvez exécuter une synchronisation initiale pour gérer les données existantes des deux côtés des applications Finance and Operations et des applications Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="86c58-112">Before you start dual-write on an entity, you can run an initial sync to handle existing data on both sides of Finance and Operations apps and customer engagement apps.</span></span> <span data-ttu-id="86c58-113">Vous pouvez ignorer la synchronisation initiale si vous n'avez pas besoin de synchroniser les données entre les deux environnements.</span><span class="sxs-lookup"><span data-stu-id="86c58-113">You can skip the initial sync if you don't need to synchronize data between the two environments.</span></span>

<span data-ttu-id="86c58-114">Une synchronisation initiale vous permet de copier les données existantes d'une application vers une autre de manière bidirectionnelle.</span><span class="sxs-lookup"><span data-stu-id="86c58-114">An initial sync lets you copy existing data from one app to another bidirectionally.</span></span> <span data-ttu-id="86c58-115">Il existe plusieurs scénarios de configuration différents en fonction des environnements dont vous disposez déjà et du type de données se trouvant dans les environnements.</span><span class="sxs-lookup"><span data-stu-id="86c58-115">There are several different setup scenarios depending on which environments you already have and what type of data is in the environments.</span></span>

<span data-ttu-id="86c58-116">Les scénarios de configuration suivants sont pris en charge :</span><span class="sxs-lookup"><span data-stu-id="86c58-116">The following setup scenarios are supported:</span></span>

+ [<span data-ttu-id="86c58-117">Une nouvelle instance d’application Finance and Operations et une nouvelle instance d’application Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="86c58-117">A new Finance and Operations app instance and a new customer engagement app instance</span></span>](#new-new)
+ [<span data-ttu-id="86c58-118">Une nouvelle instance d’application Finance and Operations et une instance d’application Customer Engagement existante</span><span class="sxs-lookup"><span data-stu-id="86c58-118">A new Finance and Operations app instance and an existing customer engagement app instance</span></span>](#new-existing)
+ [<span data-ttu-id="86c58-119">Une nouvelle instance d’application Finance and Operations qui a des données et une nouvelle instance d’application Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="86c58-119">A new Finance and Operations app instance that has data and a new customer engagement app instance</span></span>](#new-data-new)
+ [<span data-ttu-id="86c58-120">Une nouvelle instance d’application Finance and Operations qui a des données et une instance d’application Customer Engagement existante</span><span class="sxs-lookup"><span data-stu-id="86c58-120">A new Finance and Operations app instance that has data and an existing customer engagement app instance</span></span>](#new-data-existing)
+ [<span data-ttu-id="86c58-121">Une instance d’application Finance and Operations existante et une nouvelle instance d’application Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="86c58-121">An existing Finance and Operations app instance and a new customer engagement app instance</span></span>](#existing-new)
+ [<span data-ttu-id="86c58-122">Une instance d’application Finance and Operations existante et une instance d’application Customer Engagement existante</span><span class="sxs-lookup"><span data-stu-id="86c58-122">An existing Finance and Operations app instance and an existing customer engagement app instance</span></span>](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a><span data-ttu-id="86c58-123">Une nouvelle instance d’application Finance and Operations et une nouvelle instance d’application Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="86c58-123">A new Finance and Operations app instance and a new customer engagement app instance</span></span>

<span data-ttu-id="86c58-124">Pour configurer une connexion en double écriture entre une nouvelle instance d’une application Finance and Operations qui n’a pas de données et une nouvelle instance d’une application Customer Engagement, suivez les étapes de [Configuration en double écriture depuis Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="86c58-124">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and a new instance of a customer engagement app, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="86c58-125">Une fois la configuration de la connexion terminée, les actions suivantes se produisent automatiquement :</span><span class="sxs-lookup"><span data-stu-id="86c58-125">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="86c58-126">Un nouvel environnement Finance and Operations vide est provisionné.</span><span class="sxs-lookup"><span data-stu-id="86c58-126">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="86c58-127">Une nouvelle instance vide d’une application Customer Engagement est provisionnée lorsque la solution CRM principale est installée.</span><span class="sxs-lookup"><span data-stu-id="86c58-127">A new, empty instance of a customer engagement app is provisioned, where the CRM prime solution is installed.</span></span>
- <span data-ttu-id="86c58-128">Une connexion en double écriture est établie pour les données de la société DAT.</span><span class="sxs-lookup"><span data-stu-id="86c58-128">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="86c58-129">Les mappages d’entités sont activés pour la synchronisation en direct.</span><span class="sxs-lookup"><span data-stu-id="86c58-129">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="86c58-130">Les deux environnements sont alors prêts pour la synchronisation des données en direct.</span><span class="sxs-lookup"><span data-stu-id="86c58-130">Both environments are then ready for live data synchronization.</span></span>

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a><span data-ttu-id="86c58-131">Une nouvelle instance d’application Finance and Operations et une instance d’application Customer Engagement existante</span><span class="sxs-lookup"><span data-stu-id="86c58-131">A new Finance and Operations app instance and an existing customer engagement app instance</span></span>

<span data-ttu-id="86c58-132">Pour configurer une connexion en double écriture entre une nouvelle instance d’une application Finance and Operations qui n’a pas de données et une instance existante d’une application Customer Engagement, suivez les étapes de [Configuration en double écriture depuis Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="86c58-132">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and an existing instance of a customer engagement app, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="86c58-133">Une fois la configuration de la connexion terminée, les actions suivantes se produisent automatiquement :</span><span class="sxs-lookup"><span data-stu-id="86c58-133">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="86c58-134">Un nouvel environnement Finance and Operations vide est provisionné.</span><span class="sxs-lookup"><span data-stu-id="86c58-134">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="86c58-135">Une connexion en double écriture est établie pour les données de la société DAT.</span><span class="sxs-lookup"><span data-stu-id="86c58-135">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="86c58-136">Les mappages d’entités sont activés pour la synchronisation en direct.</span><span class="sxs-lookup"><span data-stu-id="86c58-136">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="86c58-137">Les deux environnements sont alors prêts pour la synchronisation des données en direct.</span><span class="sxs-lookup"><span data-stu-id="86c58-137">Both environments are then ready for live data synchronization.</span></span>

<span data-ttu-id="86c58-138">Pour synchroniser les données Common Data Service existantes à l’application Finance and Operations, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="86c58-138">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="86c58-139">Créez une entreprise dans l’application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="86c58-139">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="86c58-140">Ajoutez l’entreprise à la configuration de la connexion en double écriture.</span><span class="sxs-lookup"><span data-stu-id="86c58-140">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="86c58-141">[Amorcez](bootstrap-company-data.md) les données Common Data Service à l’aide d’un code d’entreprise à trois lettres de l’Organisation internationale de normalisation (ISO).</span><span class="sxs-lookup"><span data-stu-id="86c58-141">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter International Organization for Standardization (ISO) company code.</span></span>
4. <span data-ttu-id="86c58-142">Exécutez la fonctionnalité **Synchronisation initiale** pour les entités pour lesquelles vous souhaitez synchroniser les données.</span><span class="sxs-lookup"><span data-stu-id="86c58-142">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="86c58-143">Pour un exemple et une approche alternative, voir [Exemple](#example).</span><span class="sxs-lookup"><span data-stu-id="86c58-143">For an example and alternative approach, see [Example](#example).</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a><span data-ttu-id="86c58-144">Une nouvelle instance d’application Finance and Operations qui a des données et une nouvelle instance d’application Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="86c58-144">A new Finance and Operations app instance that has data and a new customer engagement app instance</span></span>

<span data-ttu-id="86c58-145">Pour configurer une connexion en double écriture entre une nouvelle instance d’une application Finance and Operations contenant des données et une nouvelle instance d’une application Customer Engagement, suivez les étapes dans la section [Une nouvelle instance d’application Finance and Operations et une nouvelle instance d’application Customer Engagement](#new-new) plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="86c58-145">To set up a dual-write connection between a new instance of a Finance and Operations app that has data and a new instance of a customer engagement app, follow the steps in the [A new Finance and Operations app instance and a new customer engagement app instance](#new-new) section earlier in this topic.</span></span> <span data-ttu-id="86c58-146">Une fois la configuration de la connexion terminée, si vous souhaitez synchroniser les données avec l’application Customer Engagement, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="86c58-146">When the connection setup is completed, if you want to sync the data to the customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="86c58-147">Ouvrez l’application Finance and Operations à partir de la page LCS, connectez-vous, puis accédez à **Gestion des données \> Double écriture**.</span><span class="sxs-lookup"><span data-stu-id="86c58-147">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="86c58-148">Exécutez la fonctionnalité **Synchronisation initiale** pour les entités pour lesquelles vous souhaitez synchroniser les données.</span><span class="sxs-lookup"><span data-stu-id="86c58-148">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="86c58-149">Pour un exemple et une approche alternative, voir [Exemple](#example).</span><span class="sxs-lookup"><span data-stu-id="86c58-149">For an example and alternative approach, see [Example](#example).</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a><span data-ttu-id="86c58-150">Une nouvelle instance d’application Finance and Operations qui a des données et une instance d’application Customer Engagement existante</span><span class="sxs-lookup"><span data-stu-id="86c58-150">A new Finance and Operations app instance that has data and an existing customer engagement app instance</span></span>

<span data-ttu-id="86c58-151">Pour configurer une connexion en double écriture entre une nouvelle instance d’une application Finance and Operations contenant des données et une instance existante d’une application Customer Engagement, suivez les étapes dans la section [Une nouvelle instance d’application Finance and Operations et une instance d’application Customer Engagement existante](#new-existing) plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="86c58-151">To set up a dual-write connection between a new instance of a Finance and Operations app that has data and an existing instance of a customer engagement app, follow the steps in the [A new Finance and Operations app instance and an existing customer engagement app instance](#new-existing) section earlier in this topic.</span></span> <span data-ttu-id="86c58-152">Une fois la configuration de la connexion terminée, si vous souhaitez synchroniser les données avec l’application Customer Engagement, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="86c58-152">When the connection setup is completed, if you want to sync the data to the customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="86c58-153">Ouvrez l’application Finance and Operations à partir de la page LCS, connectez-vous, puis accédez à **Gestion des données \> Double écriture**.</span><span class="sxs-lookup"><span data-stu-id="86c58-153">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="86c58-154">Exécutez la fonctionnalité **Synchronisation initiale** pour les entités pour lesquelles vous souhaitez synchroniser les données.</span><span class="sxs-lookup"><span data-stu-id="86c58-154">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="86c58-155">Pour synchroniser les données Common Data Service existantes à l’application Finance and Operations, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="86c58-155">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="86c58-156">Créez une entreprise dans l’application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="86c58-156">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="86c58-157">Ajoutez l’entreprise à la configuration de la connexion en double écriture.</span><span class="sxs-lookup"><span data-stu-id="86c58-157">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="86c58-158">[Amorcez](bootstrap-company-data.md) les données Common Data Service à l’aide du code d’entreprise à trois lettres de l’Organisation internationale de normalisation (ISO).</span><span class="sxs-lookup"><span data-stu-id="86c58-158">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>
4. <span data-ttu-id="86c58-159">Exécutez la fonctionnalité **Synchronisation initiale** pour les entités pour lesquelles vous souhaitez synchroniser les données.</span><span class="sxs-lookup"><span data-stu-id="86c58-159">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="86c58-160">Pour un exemple et une approche alternative, voir [Exemple](#example).</span><span class="sxs-lookup"><span data-stu-id="86c58-160">For an example and alternative approach, see [Example](#example).</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a><span data-ttu-id="86c58-161">Une instance d’application Finance and Operations existante et une nouvelle instance d’application Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="86c58-161">An existing Finance and Operations app instance and a new customer engagement app instance</span></span>

<span data-ttu-id="86c58-162">La configuration d’une connexion en double écriture entre une instance existante d’une application Finance and Operations et une nouvelle instance d’une application Customer Engagement se produit dans l’environnement Finance and Operation.</span><span class="sxs-lookup"><span data-stu-id="86c58-162">The setup of a dual-write connection between an existing instance of a Finance and Operations app and a new instance of a customer engagement app occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="86c58-163">[Configurez la connexion à partir de l’application Finance and Operations](enable-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="86c58-163">[Set up the connection from the Finance and Operations app](enable-dual-write.md).</span></span>
2. <span data-ttu-id="86c58-164">Exécutez la fonctionnalité **Synchronisation initiale** pour les entités pour lesquelles vous souhaitez synchroniser les données.</span><span class="sxs-lookup"><span data-stu-id="86c58-164">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="86c58-165">Pour un exemple et une approche alternative, voir [Exemple](#example).</span><span class="sxs-lookup"><span data-stu-id="86c58-165">For an example and alternative approach, see [Example](#example).</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a><span data-ttu-id="86c58-166">Une instance d’application Finance and Operations existante et une instance d’application Customer Engagement existante</span><span class="sxs-lookup"><span data-stu-id="86c58-166">An existing Finance and Operations app instance and an existing customer engagement app instance</span></span>

<span data-ttu-id="86c58-167">La configuration d’une connexion en double écriture entre une instance existante d’une application Finance and Operations et une instance existante d’une application Customer Engagement se produit dans l’environnement Finance and Operation.</span><span class="sxs-lookup"><span data-stu-id="86c58-167">The setup of a dual-write connection between an existing instance of a Finance and Operations app and an existing instance of a customer engagement app  occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="86c58-168">Configurez la connexion à partir de l’application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="86c58-168">Set up the connection from the Finance and Operations app.</span></span>
2. <span data-ttu-id="86c58-169">Pour synchroniser les données Common Data Service existantes avec l’application Finance and Operations, [amorcez](bootstrap-company-data.md) les données Common Data Service à l’aide d’un code d’entreprise ISO à trois lettres.</span><span class="sxs-lookup"><span data-stu-id="86c58-169">To sync the existing Common Data Service data to the Finance and Operations app, [bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>
3. <span data-ttu-id="86c58-170">Exécutez la fonctionnalité **Synchronisation initiale** pour les entités pour lesquelles vous souhaitez synchroniser les données.</span><span class="sxs-lookup"><span data-stu-id="86c58-170">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="86c58-171">Pour un exemple et une approche alternative, voir [Exemple](#example).</span><span class="sxs-lookup"><span data-stu-id="86c58-171">For an example and alternative approach, see [Example](#example).</span></span>

## <a name="example"></a><span data-ttu-id="86c58-172">Exemple</span><span class="sxs-lookup"><span data-stu-id="86c58-172">Example</span></span>

<span data-ttu-id="86c58-173">Pour un exemple, voir [Activation de la carte des entités Clients V3 - Contacts](enable-entity-map.md#example-enabling-the-customers-v3contacts-entity-map)</span><span class="sxs-lookup"><span data-stu-id="86c58-173">For an example, see [Enabling the Customers V3—Contacts entity map](enable-entity-map.md#example-enabling-the-customers-v3contacts-entity-map)</span></span>

<span data-ttu-id="86c58-174">Pour une approche alternative basée sur les volumes de données dans chaque entité qui doivent exécuter la synchronisation initiale, consultez [Considérations relatives à la synchronisation initiale](initial-sync-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="86c58-174">For an alternative approach based on data volumes in each entity that need to run initial sync, see [Considerations for initial synchronization](initial-sync-guidance.md).</span></span>
