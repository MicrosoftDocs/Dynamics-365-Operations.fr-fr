---
title: Scénarios pris en charge pour la configuration en double écriture
description: Cette rubrique décrit les scénarios pris en charge pour la configuration en double écriture.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/06/2020
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
ms.openlocfilehash: 1319f1228b635e207754f7c2516cb2b5353a9edd
ms.sourcegitcommit: 48c39c0c0949fe48b3536d9d2d0e451d561ff5c6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2020
ms.locfileid: "3112437"
---
# <a name="supported-scenarios-for-dual-write-setup"></a><span data-ttu-id="bc793-103">Scénarios pris en charge pour la configuration en double écriture</span><span class="sxs-lookup"><span data-stu-id="bc793-103">Supported scenarios for dual-write setup</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="bc793-104">Vous pouvez configurer une connexion en double écriture entre un environnement Finance and Operations et un environnement Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="bc793-104">You can set up a dual-write connection between a Finance and Operations environment and a Common Data Service environment.</span></span>

+ <span data-ttu-id="bc793-105">Un environnement **Finance and Operations** offre la plateforme sous-jacente pour les applications **Finance and Operations** (par exemple, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Retail et Dynamics 365 Human Resources).</span><span class="sxs-lookup"><span data-stu-id="bc793-105">A **Finance and Operations environment** provides the underlying platform for **Finance and Operations apps** (for example, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Retail, and Dynamics 365 Human Resources).</span></span>
+ <span data-ttu-id="bc793-106">Un environnement **Common Data Service** offre à la plateforme sous-jacente les **applications pilotées par modèle dans Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing et Dynamics 365 Project Service Automation).</span><span class="sxs-lookup"><span data-stu-id="bc793-106">A **Common Data Service environment** provides the underlying platform for **model-driven apps in Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation).</span></span>

<span data-ttu-id="bc793-107">Le mécanisme de configuration varie en fonction de votre abonnement et de l'environnement.</span><span class="sxs-lookup"><span data-stu-id="bc793-107">The setup mechanism varies, depending on your subscription and the environment.</span></span>

+ <span data-ttu-id="bc793-108">Pour les nouvelles instances des applications Finance and Operations, la configuration d'une connexion en double écriture commence dans Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="bc793-108">For new instances of Finance and Operations apps, the setup of a dual-write connection begins in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="bc793-109">Si vous avez une licence pour Microsoft Power Platform, vous obtiendrez un nouvel environnement Common Data Service si votre client n'en a pas.</span><span class="sxs-lookup"><span data-stu-id="bc793-109">If you have a license for Microsoft Power Platform, you will get a new Common Data Service environment if your tenant doesn't have one.</span></span>
+ <span data-ttu-id="bc793-110">Pour les applications Finance and Operations des instances existantes, la configuration d'une connexion en double écriture commence dans l'environnement Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bc793-110">For existing instances Finance and Operations apps, the setup of a dual-write connection begins in the Finance and Operations environment.</span></span>

<span data-ttu-id="bc793-111">Les scénarios de configuration suivants sont pris en charge :</span><span class="sxs-lookup"><span data-stu-id="bc793-111">The following setup scenarios are supported:</span></span>

+ [<span data-ttu-id="bc793-112">Une nouvelle instance d'application Finance and Operations et une nouvelle instance d'application pilotée par modèle</span><span class="sxs-lookup"><span data-stu-id="bc793-112">A new Finance and Operations app instance and a new model-driven app instance</span></span>](#new-new)
+ [<span data-ttu-id="bc793-113">Une nouvelle instance d'application Finance and Operations et une instance d'application pilotée par modèle existante</span><span class="sxs-lookup"><span data-stu-id="bc793-113">A new Finance and Operations app instance and an existing model-driven app instance</span></span>](#new-existing)
+ [<span data-ttu-id="bc793-114">Une nouvelle instance d'application Finance and Operations qui a des données de démonstration et une nouvelle instance d'application pilotée par modèle</span><span class="sxs-lookup"><span data-stu-id="bc793-114">A new Finance and Operations app instance that has demo data and a new model-driven app instance</span></span>](#new-demo-new)
+ [<span data-ttu-id="bc793-115">Une nouvelle instance d'application Finance and Operations qui a des données de démonstration et une instance d'application pilotée par modèle existante</span><span class="sxs-lookup"><span data-stu-id="bc793-115">A new Finance and Operations app instance that has demo data and an existing model-driven app instance</span></span>](#new-demo-existing)
+ [<span data-ttu-id="bc793-116">Une instance d'application Finance and Operations existante et une instance d'application pilotée par modèle existante ou nouvelle</span><span class="sxs-lookup"><span data-stu-id="bc793-116">An existing Finance and Operations app instance and a new or existing model-driven app instance</span></span>](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-model-driven-app-instance"></a><a id="new-new"></a><span data-ttu-id="bc793-117">Une nouvelle instance d'application Finance and Operations et une nouvelle instance d'application pilotée par modèle</span><span class="sxs-lookup"><span data-stu-id="bc793-117">A new Finance and Operations app instance and a new model-driven app instance</span></span>

<span data-ttu-id="bc793-118">Pour configurer une connexion en double écriture entre une nouvelle instance d'une application Finance and Operations qui n'a pas de données et une nouvelle instance d'une application pilotée par modèle dans Dynamics 365, suivez les étapes de [Configuration en double écriture de Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="bc793-118">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and a new instance of a model-driven app in Dynamics 365, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="bc793-119">Une fois la configuration de la connexion terminée, les actions suivantes se produisent automatiquement :</span><span class="sxs-lookup"><span data-stu-id="bc793-119">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="bc793-120">Un nouvel environnement Finance and Operations vide est provisionné.</span><span class="sxs-lookup"><span data-stu-id="bc793-120">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="bc793-121">Une nouvelle instance vide d'une application pilotée par modèle est provisionnée lorsque la solution CRM principale est installée.</span><span class="sxs-lookup"><span data-stu-id="bc793-121">A new, empty instance of a model-driven app is provisioned, where the CRM prime solution is installed.</span></span>
- <span data-ttu-id="bc793-122">Une connexion en double écriture est établie pour les données de la société DAT.</span><span class="sxs-lookup"><span data-stu-id="bc793-122">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="bc793-123">Les mappages d'entités sont activés pour la synchronisation en direct.</span><span class="sxs-lookup"><span data-stu-id="bc793-123">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="bc793-124">Les deux environnements sont alors prêts pour la synchronisation des données en direct.</span><span class="sxs-lookup"><span data-stu-id="bc793-124">Both environments are then ready for live data synchronization.</span></span>

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-model-driven-app-instance"></a><a id="new-existing"></a><span data-ttu-id="bc793-125">Une nouvelle instance d'application Finance and Operations et une instance d'application pilotée par modèle existante</span><span class="sxs-lookup"><span data-stu-id="bc793-125">A new Finance and Operations app instance and an existing model-driven app instance</span></span>

<span data-ttu-id="bc793-126">Pour configurer une connexion en double écriture entre une nouvelle instance d'une application Finance and Operations qui n'a pas de données et une instance existante d'une application pilotée par modèle dans Dynamics 365, suivez les étapes de [Configuration en double écriture de Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="bc793-126">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and an existing instance of a model-driven app in Dynamics 365, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="bc793-127">Une fois la configuration de la connexion terminée, les actions suivantes se produisent automatiquement :</span><span class="sxs-lookup"><span data-stu-id="bc793-127">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="bc793-128">Un nouvel environnement Finance and Operations vide est provisionné.</span><span class="sxs-lookup"><span data-stu-id="bc793-128">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="bc793-129">Une connexion en double écriture est établie pour les données de la société DAT.</span><span class="sxs-lookup"><span data-stu-id="bc793-129">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="bc793-130">Les mappages d'entités sont activés pour la synchronisation en direct.</span><span class="sxs-lookup"><span data-stu-id="bc793-130">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="bc793-131">Les deux environnements sont alors prêts pour la synchronisation des données en direct.</span><span class="sxs-lookup"><span data-stu-id="bc793-131">Both environments are then ready for live data synchronization.</span></span>

<span data-ttu-id="bc793-132">Pour synchroniser les données Common Data Service existantes à l'application Finance and Operations, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="bc793-132">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="bc793-133">Créez une entreprise dans l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bc793-133">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="bc793-134">Ajoutez l'entreprise à la configuration de la connexion en double écriture.</span><span class="sxs-lookup"><span data-stu-id="bc793-134">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="bc793-135">[Amorcez](bootstrap-company-data.md) les données Common Data Service à l'aide d'un code d'entreprise à trois lettres de l'Organisation internationale de normalisation (ISO).</span><span class="sxs-lookup"><span data-stu-id="bc793-135">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter International Organization for Standardization (ISO) company code.</span></span>

<span data-ttu-id="bc793-136">Étant donné que la double écriture est en mode Synchronisation en direct, la diffusion des données de Common Data Service commence automatiquement vers l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bc793-136">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-a-new-model-driven-app-instance"></a><a id="new-demo-new"></a><span data-ttu-id="bc793-137">Une nouvelle instance d'application Finance and Operations qui a des données de démonstration et une nouvelle instance d'application pilotée par modèle</span><span class="sxs-lookup"><span data-stu-id="bc793-137">A new Finance and Operations app instance that has demo data and a new model-driven app instance</span></span>

<span data-ttu-id="bc793-138">Pour configurer une connexion en double écriture entre une nouvelle instance d'une application Finance and Operations contenant des données de démonstration et une nouvelle instance d'une application pilotée par modèle dans Dynamics 365, suivez les étapes dans la section [Une nouvelle instance d'application Finance and Operations et une nouvelle instance d'application pilotée par modèle ](#new-new) précédente dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="bc793-138">To set up a dual-write connection between a new instance of a Finance and Operations app that has demo data and a new instance of a model-driven app in Dynamics 365, follow the steps in the [A new Finance and Operations app instance and a new model-driven app instance](#new-new) section earlier in this topic.</span></span> <span data-ttu-id="bc793-139">Une fois la configuration de la connexion terminée, si vous souhaitez synchroniser les données de démonstration avec l'application pilotée par modèle, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="bc793-139">When the connection setup is completed, if you want to sync the demo data to the model-driven app, follow these steps.</span></span>

1. <span data-ttu-id="bc793-140">Ouvrez l'application Finance and Operations à partir de la page LCS, connectez-vous, puis accédez à **Gestion des données \> Double écriture**.</span><span class="sxs-lookup"><span data-stu-id="bc793-140">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="bc793-141">Exécutez la fonctionnalité **Synchronisation initiale** pour les entités pour lesquelles vous souhaitez synchroniser les données.</span><span class="sxs-lookup"><span data-stu-id="bc793-141">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-an-existing-model-driven-app-instance"></a><a id="new-demo-existing"></a><span data-ttu-id="bc793-142">Une nouvelle instance d'application Finance and Operations qui a des données de démonstration et une instance d'application pilotée par modèle existante</span><span class="sxs-lookup"><span data-stu-id="bc793-142">A new Finance and Operations app instance that has demo data and an existing model-driven app instance</span></span>

<span data-ttu-id="bc793-143">Pour configurer une connexion en double écriture entre une nouvelle instance d'une application Finance and Operations contenant des données de démonstration et une instance d'une application pilotée par modèle existante dans Dynamics 365, suivez les étapes dans la section [Une nouvelle instance d'application Finance and Operations et une instance d'application pilotée par modèle existante](#new-existing) précédente dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="bc793-143">To set up a dual-write connection between a new instance of a Finance and Operations app that has demo data and an existing instance of a model-driven app in Dynamics 365, follow the steps in the [A new Finance and Operations app instance and an existing model-driven app instance](#new-existing) section earlier in this topic.</span></span> <span data-ttu-id="bc793-144">Une fois la configuration de la connexion terminée, si vous souhaitez synchroniser les données de démonstration avec l'application pilotée par modèle, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="bc793-144">When the connection setup is completed, if you want to sync the demo data to the model-driven app, follow these steps.</span></span>

1. <span data-ttu-id="bc793-145">Ouvrez l'application Finance and Operations à partir de la page LCS, connectez-vous, puis accédez à **Gestion des données \> Double écriture**.</span><span class="sxs-lookup"><span data-stu-id="bc793-145">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="bc793-146">Exécutez la fonctionnalité **Synchronisation initiale** pour les entités pour lesquelles vous souhaitez synchroniser les données.</span><span class="sxs-lookup"><span data-stu-id="bc793-146">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="bc793-147">Pour synchroniser les données Common Data Service existantes à l'application Finance and Operations, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="bc793-147">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="bc793-148">Créez une entreprise dans l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bc793-148">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="bc793-149">Ajoutez l'entreprise à la configuration de la connexion en double écriture.</span><span class="sxs-lookup"><span data-stu-id="bc793-149">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="bc793-150">[Amorcez](bootstrap-company-data.md) les données Common Data Service à l'aide du code d'entreprise à trois lettres de l'Organisation internationale de normalisation (ISO).</span><span class="sxs-lookup"><span data-stu-id="bc793-150">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>

<span data-ttu-id="bc793-151">Étant donné que la double écriture est en mode Synchronisation en direct, la diffusion des données de Common Data Service commence automatiquement vers l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bc793-151">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-or-existing-model-driven-app-instance"></a><a id="existing-existing"></a><span data-ttu-id="bc793-152">Une instance d'application Finance and Operations existante et une instance d'application pilotée par modèle existante ou nouvelle</span><span class="sxs-lookup"><span data-stu-id="bc793-152">An existing Finance and Operations app instance and a new or existing model-driven app instance</span></span>

<span data-ttu-id="bc793-153">La configuration d'une connexion en double écriture entre une instance existante d'une application Finance and Operations et une instance nouvelle ou existante d'une application pilotée par modèle dans Dynamics 365 se produit dans l'environnement Finance and Operation.</span><span class="sxs-lookup"><span data-stu-id="bc793-153">The setup of a dual-write connection between an existing instance of a Finance and Operations app and a new or existing instance of a model-driven app in Dynamics 365 occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="bc793-154">Configurez la connexion à partir de l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bc793-154">Set up the connection from the Finance and Operations app.</span></span>
2. <span data-ttu-id="bc793-155">Pour synchroniser les données Common Data Service existantes avec l'application Finance and Operations, [amorcez](bootstrap-company-data.md) les données Common Data Service à l'aide d'un code d'entreprise ISO à trois lettres.</span><span class="sxs-lookup"><span data-stu-id="bc793-155">To sync the existing Common Data Service data to the Finance and Operations app, [bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>

<span data-ttu-id="bc793-156">Étant donné que la double écriture est en mode Synchronisation en direct, la diffusion des données de Common Data Service commence automatiquement vers l'application Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bc793-156">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>
