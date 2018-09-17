---
title: Supprimer des environnements Talent
description: "Cette rubrique décrit le processus de suppression d'un environnement de test ou de production pour Microsoft Dynamics 365 for Talent."
author: rschloma
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 965826f5fddc2f53f33157434929eb265979376e
ms.openlocfilehash: e0422a5b7ac227ad03ccafb4e34e614dc770a363
ms.contentlocale: fr-fr
ms.lasthandoff: 09/17/2018

---
# <a name="remove-talent-environments"></a><span data-ttu-id="1a16f-103">Supprimer des environnements Talent</span><span class="sxs-lookup"><span data-stu-id="1a16f-103">Remove Talent environments</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1a16f-104">Cette rubrique décrit le processus de suppression d'un environnement de test ou de production pour Microsoft Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="1a16f-104">This topic walks you through the process of removing a test drive or production environment for Microsoft Dynamics 365 for Talent.</span></span>

## <a name="removing-a-test-drive-environment"></a><span data-ttu-id="1a16f-105">Suppression d'un environnement de test</span><span class="sxs-lookup"><span data-stu-id="1a16f-105">Removing a test drive environment</span></span>

<span data-ttu-id="1a16f-106">Les tests Talent sont provisionnés avec une stratégie d'expiration de 60 jours.</span><span class="sxs-lookup"><span data-stu-id="1a16f-106">Talent test drives are provisioned with a 60-day expiration policy.</span></span> <span data-ttu-id="1a16f-107">Toutefois, les propriétaires des environnements de test ont l'option de mettre fin à leur période d'essai en suivant les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="1a16f-107">However, owners of test drive environments have the option to end their trial early by completing the following steps.</span></span> 

1. <span data-ttu-id="1a16f-108">Accédez au [Centre d'administration PowerApps](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="1a16f-108">Navigate to the [PowerApps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="1a16f-109">Sélectionner **Environnements**.</span><span class="sxs-lookup"><span data-stu-id="1a16f-109">Select **Environments**.</span></span>
3. <span data-ttu-id="1a16f-110">Sélectionnez l'environnement de test, avec un modèle de dénomination similaire à ceci : TestDrive - alias@domain</span><span class="sxs-lookup"><span data-stu-id="1a16f-110">Select the test drive environment, which has a naming pattern similar to this: TestDrive - alias@domain</span></span>
4. <span data-ttu-id="1a16f-111">Sélectionnez **Supprimer** et confirmez la décision.</span><span class="sxs-lookup"><span data-stu-id="1a16f-111">Select **Delete** and confirm the decision.</span></span> 

<span data-ttu-id="1a16f-112">L'environnement de test existant est supprimé.</span><span class="sxs-lookup"><span data-stu-id="1a16f-112">The existing test drive environment will be removed.</span></span> <span data-ttu-id="1a16f-113">Une fois supprimé, vous pouvez vous inscrire à un nouvel environnement de test.</span><span class="sxs-lookup"><span data-stu-id="1a16f-113">When it is removed, you can sign up for a new test drive environment.</span></span> 

## <a name="removing-a-production-environment"></a><span data-ttu-id="1a16f-114">Suppression d'un environnement de production</span><span class="sxs-lookup"><span data-stu-id="1a16f-114">Removing a production environment</span></span>

<span data-ttu-id="1a16f-115">Cette rubrique suppose que vous avez acheté Talent par l'intermédiaire d'un fournisseur de solutions Cloud (CSP) ou dans le cadre d'un contrat d'architecture d'entreprise (EA).</span><span class="sxs-lookup"><span data-stu-id="1a16f-115">This topic assumes that you've purchased Talent through a Cloud Solution Provider (CSP) or an enterprise architecture (EA) agreement.</span></span> 

<span data-ttu-id="1a16f-116">Comme un seul environnement Talent est « contenu » dans un seul environnement PowerApps, il existe deux options à prendre en compte.</span><span class="sxs-lookup"><span data-stu-id="1a16f-116">Since a single Talent environment is “contained” within a single PowerApps environment, there are two options to consider.</span></span> <span data-ttu-id="1a16f-117">La première option implique de supprimer l'ensemble de l'environnement PowerApps ; puis supprimer uniquement Talent.</span><span class="sxs-lookup"><span data-stu-id="1a16f-117">The first option involves removing the entire PowerApps environment; the second option involves removing only Talent.</span></span> <span data-ttu-id="1a16f-118">La première option est recommandée lorsque vous avez créé un environnement PowerApps expressément pour le provisionnement de Talent, et que vous venez de commencer l'implémentation, ou que vous n'avez pas établi d'intégration.</span><span class="sxs-lookup"><span data-stu-id="1a16f-118">The first option is preferred when you have created a PowerApps environment expressly for the purpose of provisioning Talent, and you've just begun implementation, or you don’t have any established integrations.</span></span> <span data-ttu-id="1a16f-119">La deuxième option est utile lorsque vous avez établi un environnement PowerApps rempli avec des données enrichies qui sont exploitées dans PowerApps et Flow.</span><span class="sxs-lookup"><span data-stu-id="1a16f-119">The second option is appropriate when you have an established PowerApps environment populated with rich data that's leveraged in PowerApps and Flows.</span></span>

> [!Important]
> <span data-ttu-id="1a16f-120">Avant de supprimer l'environnement PowerApps, vérifiez qu'il n'est pas utilisé pour des intégrations de données enrichies en dehors de la portée de Talent.</span><span class="sxs-lookup"><span data-stu-id="1a16f-120">Before removing the PowerApps environment, ensure it is not being used for rich data integrations outside the scope of Talent.</span></span> <span data-ttu-id="1a16f-121">Notez également que les environnements PowerApps par défaut ne peuvent pas être supprimés.</span><span class="sxs-lookup"><span data-stu-id="1a16f-121">Also note that the default PowerApps environments cannot be removed.</span></span> 

<span data-ttu-id="1a16f-122">Pour supprimer l'ensemble de l'environnement PowerApps, notamment Talent et les applications et flux associés :</span><span class="sxs-lookup"><span data-stu-id="1a16f-122">To remove the entire PowerApps environment, including Talent and the associated Apps and Flows:</span></span>

1. <span data-ttu-id="1a16f-123">Accédez au [Centre d'administration PowerApps](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="1a16f-123">Navigate to the [PowerApps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="1a16f-124">Sélectionner **Environnements**.</span><span class="sxs-lookup"><span data-stu-id="1a16f-124">Select **Environments**.</span></span>
3. <span data-ttu-id="1a16f-125">Sélectionnez l'environnement à supprimer.</span><span class="sxs-lookup"><span data-stu-id="1a16f-125">Select the environment to be removed.</span></span>
4. <span data-ttu-id="1a16f-126">Sélectionnez **Supprimer** et confirmez la décision.</span><span class="sxs-lookup"><span data-stu-id="1a16f-126">Select **Delete** and confirm the decision.</span></span> 
5. <span data-ttu-id="1a16f-127">Attendez que la suppression soit terminée.</span><span class="sxs-lookup"><span data-stu-id="1a16f-127">Wait until the deletion is complete.</span></span>
6. <span data-ttu-id="1a16f-128">Connectez-vous à [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (CS) à l'aide du compte utilisé pour vous abonner à Talent.</span><span class="sxs-lookup"><span data-stu-id="1a16f-128">Sign in to [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) using the account that you used to subscribe to Talent.</span></span> 
7. <span data-ttu-id="1a16f-129">Sélectionnez le projet Talent qui contient l'environnement.</span><span class="sxs-lookup"><span data-stu-id="1a16f-129">Select the Talent Project that contains the environment.</span></span> 
8. <span data-ttu-id="1a16f-130">Dans votre projet LCS, sélectionnez la vignette **Gestion de l'application Talent**.</span><span class="sxs-lookup"><span data-stu-id="1a16f-130">In your LCS project, select the **Talent App Management** tile.</span></span> 
9. <span data-ttu-id="1a16f-131">Sélectionnez l'instance à supprimer.</span><span class="sxs-lookup"><span data-stu-id="1a16f-131">Select the instance to remove.</span></span> 
10. <span data-ttu-id="1a16f-132">Sélectionnez **Supprimer l'instance** et confirmez votre décision.</span><span class="sxs-lookup"><span data-stu-id="1a16f-132">Select **Remove instance** and confirm your decision.</span></span>  

<span data-ttu-id="1a16f-133">Pour supprimer un environnement Talent d'un environnement PowerApps existant, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="1a16f-133">To remove a Talent environment from an existing PowerApps environment, complete the following steps.</span></span> <span data-ttu-id="1a16f-134">Notez que la nécessité d'inclure le support et de contacter l'équipe DevOps de Talent est temporaire tant que cette fonction est activée directement dans LCS.</span><span class="sxs-lookup"><span data-stu-id="1a16f-134">Note that the need to involve support and contact the Talent DevOps team is temporary until this feature is enabled directly in LCS.</span></span>

1. <span data-ttu-id="1a16f-135">Contactez le support pour lancer une demande de suppression.</span><span class="sxs-lookup"><span data-stu-id="1a16f-135">Contact Support to initiate a removal request.</span></span>
2. <span data-ttu-id="1a16f-136">L'équipe de support initialisera une demande de suppression avec l'équipe DevOps de Talent.</span><span class="sxs-lookup"><span data-stu-id="1a16f-136">The Support team will initiate a removal request with the Talent DevOps team.</span></span> 
3. <span data-ttu-id="1a16f-137">Continuez après la réception du message indiquant que l'environnement a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="1a16f-137">Continue after you receive word that the environment has been removed.</span></span>
4.  <span data-ttu-id="1a16f-138">Connectez-vous à LCS à l'aide du compte utilisé pour vous abonner à Talent.</span><span class="sxs-lookup"><span data-stu-id="1a16f-138">Sign in to LCS using the account that you used to subscribe to Talent.</span></span> 
5. <span data-ttu-id="1a16f-139">Sélectionnez le projet Talent qui contient l'environnement.</span><span class="sxs-lookup"><span data-stu-id="1a16f-139">Select the Talent project that contains the environment.</span></span> 
6. <span data-ttu-id="1a16f-140">Dans votre projet LCS, sélectionnez la vignette **Gestion de l'application Talent**.</span><span class="sxs-lookup"><span data-stu-id="1a16f-140">In your LCS project, select the **Talent App Management** tile.</span></span> 
7. <span data-ttu-id="1a16f-141">Sélectionnez l'instance à supprimer, qui doit être marquée avec un statut de déploiement **Échec**.</span><span class="sxs-lookup"><span data-stu-id="1a16f-141">Select the instance you would like to remove, which should be marked with a Deployment status of **Failed**.</span></span>
8. <span data-ttu-id="1a16f-142">Sélectionnez **Supprimer l'instance** et confirmez votre décision.</span><span class="sxs-lookup"><span data-stu-id="1a16f-142">Select **Remove instance** and confirm your decision.</span></span> 


