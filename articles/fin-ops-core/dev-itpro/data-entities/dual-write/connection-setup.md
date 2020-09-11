---
title: Scénarios pris en charge pour la configuration en double écriture
description: Cette rubrique décrit les scénarios pris en charge pour la configuration en double écriture.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 08/17/2020
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
ms.openlocfilehash: 275d24d8f32fd1d2d15356d14c5c6591e8503c65
ms.sourcegitcommit: ec4df354602c20f48f8581bfe5be0c04c66d2927
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/19/2020
ms.locfileid: "3706250"
---
# <a name="supported-scenarios-for-dual-write-setup"></a><span data-ttu-id="7ea7f-103">Scénarios pris en charge pour la configuration en double écriture</span><span class="sxs-lookup"><span data-stu-id="7ea7f-103">Supported scenarios for dual-write setup</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="7ea7f-104">Vous pouvez configurer une connexion en double écriture entre un environnement Finance and Operations et un environnement Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-104">You can set up a dual-write connection between a Finance and Operations environment and a Common Data Service environment.</span></span>

+ <span data-ttu-id="7ea7f-105">Un **environnement Finance and Operations** offre la plateforme sous-jacente pour les **applications Finance and Operations** (par exemple, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management et Dynamics 365 Retail).</span><span class="sxs-lookup"><span data-stu-id="7ea7f-105">A **Finance and Operations environment** provides the underlying platform for **Finance and Operations apps** (for example, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, and Dynamics 365 Retail).</span></span>
+ <span data-ttu-id="7ea7f-106">Un environnement **Common Data Service** offre à la plateforme sous-jacente les **applications pilotées par modèle dans Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing et Dynamics 365 Project Service Automation).</span><span class="sxs-lookup"><span data-stu-id="7ea7f-106">A **Common Data Service environment** provides the underlying platform for **model-driven apps in Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation).</span></span>

>[!IMPORTANT]
><span data-ttu-id="7ea7f-107">Human Resources dans Finance and Operations prend en charge les connexions en double écriture, mais l’application Dynamics 365 Human Resources, non.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-107">Human Resources in Finance and Operations supports dual-write connections, but the Dynamics 365 Human Resources app doesn't.</span></span>

<span data-ttu-id="7ea7f-108">Le mécanisme de configuration varie en fonction de votre abonnement et de l’environnement.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-108">The setup mechanism varies, depending on your subscription and the environment.</span></span>

+ <span data-ttu-id="7ea7f-109">Pour les nouvelles instances des applications Finance and Operations, la configuration d’une connexion en double écriture commence dans Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="7ea7f-109">For new instances of Finance and Operations apps, the setup of a dual-write connection begins in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="7ea7f-110">Si vous avez une licence pour Microsoft Power Platform, vous obtiendrez un nouvel environnement Common Data Service si votre client n’en a pas.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-110">If you have a license for Microsoft Power Platform, you will get a new Common Data Service environment if your tenant doesn't have one.</span></span>
+ <span data-ttu-id="7ea7f-111">Pour les applications Finance and Operations des instances existantes, la configuration d’une connexion en double écriture commence dans l’environnement Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-111">For existing instances Finance and Operations apps, the setup of a dual-write connection begins in the Finance and Operations environment.</span></span>

<span data-ttu-id="7ea7f-112">Les scénarios de configuration suivants sont pris en charge :</span><span class="sxs-lookup"><span data-stu-id="7ea7f-112">The following setup scenarios are supported:</span></span>

+ [<span data-ttu-id="7ea7f-113">Une nouvelle instance d’application Finance and Operations et une nouvelle instance d’application pilotée par modèle</span><span class="sxs-lookup"><span data-stu-id="7ea7f-113">A new Finance and Operations app instance and a new model-driven app instance</span></span>](#new-new)
+ [<span data-ttu-id="7ea7f-114">Une nouvelle instance d’application Finance and Operations et une instance d’application pilotée par modèle existante</span><span class="sxs-lookup"><span data-stu-id="7ea7f-114">A new Finance and Operations app instance and an existing model-driven app instance</span></span>](#new-existing)
+ [<span data-ttu-id="7ea7f-115">Une nouvelle instance d’application Finance and Operations qui a des données de démonstration et une nouvelle instance d’application pilotée par modèle</span><span class="sxs-lookup"><span data-stu-id="7ea7f-115">A new Finance and Operations app instance that has demo data and a new model-driven app instance</span></span>](#new-demo-new)
+ [<span data-ttu-id="7ea7f-116">Une nouvelle instance d’application Finance and Operations qui a des données de démonstration et une instance d’application pilotée par modèle existante</span><span class="sxs-lookup"><span data-stu-id="7ea7f-116">A new Finance and Operations app instance that has demo data and an existing model-driven app instance</span></span>](#new-demo-existing)
+ [<span data-ttu-id="7ea7f-117">Une instance d’application Finance and Operations existante et une instance d’application pilotée par modèle existante ou nouvelle</span><span class="sxs-lookup"><span data-stu-id="7ea7f-117">An existing Finance and Operations app instance and a new or existing model-driven app instance</span></span>](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-model-driven-app-instance"></a><a id="new-new"></a><span data-ttu-id="7ea7f-118">Une nouvelle instance d’application Finance and Operations et une nouvelle instance d’application pilotée par modèle</span><span class="sxs-lookup"><span data-stu-id="7ea7f-118">A new Finance and Operations app instance and a new model-driven app instance</span></span>

<span data-ttu-id="7ea7f-119">Pour configurer une connexion en double écriture entre une nouvelle instance d’une application Finance and Operations qui n’a pas de données et une nouvelle instance d’une application pilotée par modèle dans Dynamics 365, suivez les étapes de [Configuration en double écriture de Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="7ea7f-119">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and a new instance of a model-driven app in Dynamics 365, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="7ea7f-120">Une fois la configuration de la connexion terminée, les actions suivantes se produisent automatiquement :</span><span class="sxs-lookup"><span data-stu-id="7ea7f-120">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="7ea7f-121">Un nouvel environnement Finance and Operations vide est provisionné.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-121">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="7ea7f-122">Une nouvelle instance vide d’une application pilotée par modèle est provisionnée lorsque la solution CRM principale est installée.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-122">A new, empty instance of a model-driven app is provisioned, where the CRM prime solution is installed.</span></span>
- <span data-ttu-id="7ea7f-123">Une connexion en double écriture est établie pour les données de la société DAT.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-123">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="7ea7f-124">Les mappages d’entités sont activés pour la synchronisation en direct.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-124">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="7ea7f-125">Les deux environnements sont alors prêts pour la synchronisation des données en direct.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-125">Both environments are then ready for live data synchronization.</span></span>

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-model-driven-app-instance"></a><a id="new-existing"></a><span data-ttu-id="7ea7f-126">Une nouvelle instance d’application Finance and Operations et une instance d’application pilotée par modèle existante</span><span class="sxs-lookup"><span data-stu-id="7ea7f-126">A new Finance and Operations app instance and an existing model-driven app instance</span></span>

<span data-ttu-id="7ea7f-127">Pour configurer une connexion en double écriture entre une nouvelle instance d’une application Finance and Operations qui n’a pas de données et une instance existante d’une application pilotée par modèle dans Dynamics 365, suivez les étapes de [Configuration en double écriture de Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="7ea7f-127">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and an existing instance of a model-driven app in Dynamics 365, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="7ea7f-128">Une fois la configuration de la connexion terminée, les actions suivantes se produisent automatiquement :</span><span class="sxs-lookup"><span data-stu-id="7ea7f-128">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="7ea7f-129">Un nouvel environnement Finance and Operations vide est provisionné.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-129">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="7ea7f-130">Une connexion en double écriture est établie pour les données de la société DAT.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-130">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="7ea7f-131">Les mappages d’entités sont activés pour la synchronisation en direct.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-131">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="7ea7f-132">Les deux environnements sont alors prêts pour la synchronisation des données en direct.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-132">Both environments are then ready for live data synchronization.</span></span>

<span data-ttu-id="7ea7f-133">Pour synchroniser les données Common Data Service existantes à l’application Finance and Operations, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-133">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="7ea7f-134">Créez une entreprise dans l’application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-134">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="7ea7f-135">Ajoutez l’entreprise à la configuration de la connexion en double écriture.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-135">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="7ea7f-136">[Amorcez](bootstrap-company-data.md) les données Common Data Service à l’aide d’un code d’entreprise à trois lettres de l’Organisation internationale de normalisation (ISO).</span><span class="sxs-lookup"><span data-stu-id="7ea7f-136">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter International Organization for Standardization (ISO) company code.</span></span>

<span data-ttu-id="7ea7f-137">Étant donné que la double écriture est en mode Synchronisation en direct, la diffusion des données de Common Data Service commence automatiquement vers l’application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-137">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-a-new-model-driven-app-instance"></a><a id="new-demo-new"></a><span data-ttu-id="7ea7f-138">Une nouvelle instance d’application Finance and Operations qui a des données de démonstration et une nouvelle instance d’application pilotée par modèle</span><span class="sxs-lookup"><span data-stu-id="7ea7f-138">A new Finance and Operations app instance that has demo data and a new model-driven app instance</span></span>

<span data-ttu-id="7ea7f-139">Pour configurer une connexion en double écriture entre une nouvelle instance d’une application Finance and Operations contenant des données de démonstration et une nouvelle instance d’une application pilotée par modèle dans Dynamics 365, suivez les étapes dans la section [Une nouvelle instance d’application Finance and Operations et une nouvelle instance d’application pilotée par modèle ](#new-new) précédente dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-139">To set up a dual-write connection between a new instance of a Finance and Operations app that has demo data and a new instance of a model-driven app in Dynamics 365, follow the steps in the [A new Finance and Operations app instance and a new model-driven app instance](#new-new) section earlier in this topic.</span></span> <span data-ttu-id="7ea7f-140">Une fois la configuration de la connexion terminée, si vous souhaitez synchroniser les données de démonstration avec l’application pilotée par modèle, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-140">When the connection setup is completed, if you want to sync the demo data to the model-driven app, follow these steps.</span></span>

1. <span data-ttu-id="7ea7f-141">Ouvrez l’application Finance and Operations à partir de la page LCS, connectez-vous, puis accédez à **Gestion des données \> Double écriture**.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-141">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="7ea7f-142">Exécutez la fonctionnalité **Synchronisation initiale** pour les entités pour lesquelles vous souhaitez synchroniser les données.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-142">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-an-existing-model-driven-app-instance"></a><a id="new-demo-existing"></a><span data-ttu-id="7ea7f-143">Une nouvelle instance d’application Finance and Operations qui a des données de démonstration et une instance d’application pilotée par modèle existante</span><span class="sxs-lookup"><span data-stu-id="7ea7f-143">A new Finance and Operations app instance that has demo data and an existing model-driven app instance</span></span>

<span data-ttu-id="7ea7f-144">Pour configurer une connexion en double écriture entre une nouvelle instance d’une application Finance and Operations contenant des données de démonstration et une instance d’une application pilotée par modèle existante dans Dynamics 365, suivez les étapes dans la section [Une nouvelle instance d’application Finance and Operations et une instance d’application pilotée par modèle existante](#new-existing) précédente dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-144">To set up a dual-write connection between a new instance of a Finance and Operations app that has demo data and an existing instance of a model-driven app in Dynamics 365, follow the steps in the [A new Finance and Operations app instance and an existing model-driven app instance](#new-existing) section earlier in this topic.</span></span> <span data-ttu-id="7ea7f-145">Une fois la configuration de la connexion terminée, si vous souhaitez synchroniser les données de démonstration avec l’application pilotée par modèle, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-145">When the connection setup is completed, if you want to sync the demo data to the model-driven app, follow these steps.</span></span>

1. <span data-ttu-id="7ea7f-146">Ouvrez l’application Finance and Operations à partir de la page LCS, connectez-vous, puis accédez à **Gestion des données \> Double écriture**.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-146">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="7ea7f-147">Exécutez la fonctionnalité **Synchronisation initiale** pour les entités pour lesquelles vous souhaitez synchroniser les données.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-147">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="7ea7f-148">Pour synchroniser les données Common Data Service existantes à l’application Finance and Operations, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-148">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="7ea7f-149">Créez une entreprise dans l’application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-149">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="7ea7f-150">Ajoutez l’entreprise à la configuration de la connexion en double écriture.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-150">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="7ea7f-151">[Amorcez](bootstrap-company-data.md) les données Common Data Service à l’aide du code d’entreprise à trois lettres de l’Organisation internationale de normalisation (ISO).</span><span class="sxs-lookup"><span data-stu-id="7ea7f-151">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>

<span data-ttu-id="7ea7f-152">Étant donné que la double écriture est en mode Synchronisation en direct, la diffusion des données de Common Data Service commence automatiquement vers l’application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-152">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-or-existing-model-driven-app-instance"></a><a id="existing-existing"></a><span data-ttu-id="7ea7f-153">Une instance d’application Finance and Operations existante et une instance d’application pilotée par modèle existante ou nouvelle</span><span class="sxs-lookup"><span data-stu-id="7ea7f-153">An existing Finance and Operations app instance and a new or existing model-driven app instance</span></span>

<span data-ttu-id="7ea7f-154">La configuration d’une connexion en double écriture entre une instance existante d’une application Finance and Operations et une instance nouvelle ou existante d’une application pilotée par modèle dans Dynamics 365 se produit dans l’environnement Finance and Operation.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-154">The setup of a dual-write connection between an existing instance of a Finance and Operations app and a new or existing instance of a model-driven app in Dynamics 365 occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="7ea7f-155">Configurez la connexion à partir de l’application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-155">Set up the connection from the Finance and Operations app.</span></span>
2. <span data-ttu-id="7ea7f-156">Pour synchroniser les données Common Data Service existantes avec l’application Finance and Operations, [amorcez](bootstrap-company-data.md) les données Common Data Service à l’aide d’un code d’entreprise ISO à trois lettres.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-156">To sync the existing Common Data Service data to the Finance and Operations app, [bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>

<span data-ttu-id="7ea7f-157">Étant donné que la double écriture est en mode Synchronisation en direct, la diffusion des données de Common Data Service commence automatiquement vers l’application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7ea7f-157">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>
