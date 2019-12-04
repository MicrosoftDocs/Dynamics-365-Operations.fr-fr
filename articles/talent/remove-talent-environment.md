---
title: Supprimer des environnements Talent
description: Cette rubrique décrit le processus de suppression d'un pilote test ou d'un environnement de production pour Microsoft Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.openlocfilehash: bbc65a77b7c3df6545dfd7aa2109aba5c4e1b57b
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773032"
---
# <a name="remove-talent-environments"></a><span data-ttu-id="817a0-103">Supprimer des environnements Talent</span><span class="sxs-lookup"><span data-stu-id="817a0-103">Remove Talent environments</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="817a0-104">Cette rubrique décrit le processus de suppression d'un pilote test ou d'un environnement de production pour Microsoft Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="817a0-104">This topic walks you through the process of removing a test drive or production environment for Microsoft Dynamics 365 Talent.</span></span>

## <a name="removing-a-test-drive-environment"></a><span data-ttu-id="817a0-105">Suppression d'un environnement de test</span><span class="sxs-lookup"><span data-stu-id="817a0-105">Removing a test drive environment</span></span>

<span data-ttu-id="817a0-106">Les tests Talent sont provisionnés avec une stratégie d'expiration de 60 jours.</span><span class="sxs-lookup"><span data-stu-id="817a0-106">Talent test drives are provisioned with a 60-day expiration policy.</span></span> <span data-ttu-id="817a0-107">Toutefois, les propriétaires des environnements de test ont l'option de mettre fin à leur période d'essai en suivant les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="817a0-107">However, owners of test drive environments have the option to end their trial early by completing the following steps.</span></span> 

1. <span data-ttu-id="817a0-108">Accédez au [centre d'administration Power Apps](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="817a0-108">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="817a0-109">Sélectionner **Environnements**.</span><span class="sxs-lookup"><span data-stu-id="817a0-109">Select **Environments**.</span></span>
3. <span data-ttu-id="817a0-110">Sélectionnez l'environnement de test, avec un modèle de dénomination similaire à ceci : TestDrive - alias@domain</span><span class="sxs-lookup"><span data-stu-id="817a0-110">Select the test drive environment, which has a naming pattern similar to this: TestDrive - alias@domain</span></span>
4. <span data-ttu-id="817a0-111">Sélectionnez **Supprimer** et confirmez la décision.</span><span class="sxs-lookup"><span data-stu-id="817a0-111">Select **Delete** and confirm the decision.</span></span> 

<span data-ttu-id="817a0-112">L'environnement de test existant est supprimé.</span><span class="sxs-lookup"><span data-stu-id="817a0-112">The existing test drive environment will be removed.</span></span> <span data-ttu-id="817a0-113">Une fois supprimé, vous pouvez vous inscrire à un nouvel environnement de test.</span><span class="sxs-lookup"><span data-stu-id="817a0-113">When it is removed, you can sign up for a new test drive environment.</span></span> 

## <a name="removing-a-production-environment"></a><span data-ttu-id="817a0-114">Suppression d'un environnement de production</span><span class="sxs-lookup"><span data-stu-id="817a0-114">Removing a production environment</span></span>

<span data-ttu-id="817a0-115">Cette rubrique suppose que vous avez acheté Talent par l'intermédiaire d'un fournisseur de solutions Cloud (CSP) ou dans le cadre d'un contrat d'architecture d'entreprise (EA).</span><span class="sxs-lookup"><span data-stu-id="817a0-115">This topic assumes that you've purchased Talent through a Cloud Solution Provider (CSP) or an enterprise architecture (EA) agreement.</span></span> 

<span data-ttu-id="817a0-116">Comme un seul environnement Talent est « contenu » dans un seul environnement Power Apps, il existe deux options à prendre en compte.</span><span class="sxs-lookup"><span data-stu-id="817a0-116">Since a single Talent environment is “contained” within a single Power Apps environment, there are two options to consider.</span></span> <span data-ttu-id="817a0-117">La première option implique de supprimer l'ensemble de l'environnement Power Apps ; puis supprimer uniquement Talent.</span><span class="sxs-lookup"><span data-stu-id="817a0-117">The first option involves removing the entire Power Apps environment; the second option involves removing only Talent.</span></span> <span data-ttu-id="817a0-118">La première option est recommandée lorsque vous avez créé un environnement Power Apps expressément pour le provisionnement de Talent, et que vous venez de commencer l'implémentation, ou que vous n'avez pas établi d'intégration.</span><span class="sxs-lookup"><span data-stu-id="817a0-118">The first option is preferred when you have created a Power Apps environment expressly for the purpose of provisioning Talent, and you've just begun implementation, or you don’t have any established integrations.</span></span> <span data-ttu-id="817a0-119">La deuxième option est utile lorsque vous avez établi un environnement Power Apps rempli avec des données enrichies qui sont exploitées dans Power Apps et Power Automate.</span><span class="sxs-lookup"><span data-stu-id="817a0-119">The second option is appropriate when you have an established Power Apps environment populated with rich data that's leveraged in Power Apps and Power Automate.</span></span>

> [!Important]
> <span data-ttu-id="817a0-120">Avant de supprimer l'environnement Power Apps, vérifiez qu'il n'est pas utilisé pour des intégrations de données enrichies en dehors de la portée de Talent.</span><span class="sxs-lookup"><span data-stu-id="817a0-120">Before removing the Power Apps environment, ensure it is not being used for rich data integrations outside the scope of Talent.</span></span> <span data-ttu-id="817a0-121">Notez également que les environnements Power Apps par défaut ne peuvent pas être supprimés.</span><span class="sxs-lookup"><span data-stu-id="817a0-121">Also note that the default Power Apps environments cannot be removed.</span></span> 

<span data-ttu-id="817a0-122">Pour supprimer l'ensemble de l'environnement Power Apps, notamment Talent et les applications et flux associés :</span><span class="sxs-lookup"><span data-stu-id="817a0-122">To remove the entire Power Apps environment, including Talent and the associated apps and flows:</span></span>

1. <span data-ttu-id="817a0-123">Accédez au [centre d'administration Power Apps](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="817a0-123">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="817a0-124">Sélectionner **Environnements**.</span><span class="sxs-lookup"><span data-stu-id="817a0-124">Select **Environments**.</span></span>
3. <span data-ttu-id="817a0-125">Sélectionnez l'environnement à supprimer.</span><span class="sxs-lookup"><span data-stu-id="817a0-125">Select the environment to be removed.</span></span>
4. <span data-ttu-id="817a0-126">Sélectionnez **Supprimer** et confirmez la décision.</span><span class="sxs-lookup"><span data-stu-id="817a0-126">Select **Delete** and confirm the decision.</span></span> 
5. <span data-ttu-id="817a0-127">Attendez que la suppression soit terminée.</span><span class="sxs-lookup"><span data-stu-id="817a0-127">Wait until the deletion is complete.</span></span>
6. <span data-ttu-id="817a0-128">Connectez-vous à [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (CS) à l'aide du compte utilisé pour vous abonner à Talent.</span><span class="sxs-lookup"><span data-stu-id="817a0-128">Sign in to [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) using the account that you used to subscribe to Talent.</span></span> 
7. <span data-ttu-id="817a0-129">Sélectionnez le projet Talent qui contient l'environnement.</span><span class="sxs-lookup"><span data-stu-id="817a0-129">Select the Talent Project that contains the environment.</span></span> 
8. <span data-ttu-id="817a0-130">Dans votre projet LCS, sélectionnez la vignette **Gestion de l'application Talent**.</span><span class="sxs-lookup"><span data-stu-id="817a0-130">In your LCS project, select the **Talent App Management** tile.</span></span> 
9. <span data-ttu-id="817a0-131">Sélectionnez l'instance à supprimer.</span><span class="sxs-lookup"><span data-stu-id="817a0-131">Select the instance to remove.</span></span> 
10. <span data-ttu-id="817a0-132">Sélectionnez **Supprimer l'instance** et confirmez votre décision.</span><span class="sxs-lookup"><span data-stu-id="817a0-132">Select **Remove instance** and confirm your decision.</span></span>  

<span data-ttu-id="817a0-133">Pour supprimer un environnement Talent d'un environnement Power Apps existant, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="817a0-133">To remove a Talent environment from an existing Power Apps environment, complete the following steps.</span></span> <span data-ttu-id="817a0-134">Notez que la nécessité d'inclure le support et de contacter l'équipe DevOps de Talent est temporaire tant que cette fonction est activée directement dans LCS.</span><span class="sxs-lookup"><span data-stu-id="817a0-134">Note that the need to involve support and contact the Talent DevOps team is temporary until this feature is enabled directly in LCS.</span></span>

1. <span data-ttu-id="817a0-135">Contactez le support pour lancer une demande de suppression.</span><span class="sxs-lookup"><span data-stu-id="817a0-135">Contact Support to initiate a removal request.</span></span>
2. <span data-ttu-id="817a0-136">L'équipe de support initialisera une demande de suppression avec l'équipe DevOps de Talent.</span><span class="sxs-lookup"><span data-stu-id="817a0-136">The Support team will initiate a removal request with the Talent DevOps team.</span></span> 
3. <span data-ttu-id="817a0-137">Continuez après la réception du message indiquant que l'environnement a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="817a0-137">Continue after you receive word that the environment has been removed.</span></span>
4.  <span data-ttu-id="817a0-138">Connectez-vous à LCS à l'aide du compte utilisé pour vous abonner à Talent.</span><span class="sxs-lookup"><span data-stu-id="817a0-138">Sign in to LCS using the account that you used to subscribe to Talent.</span></span> 
5. <span data-ttu-id="817a0-139">Sélectionnez le projet Talent qui contient l'environnement.</span><span class="sxs-lookup"><span data-stu-id="817a0-139">Select the Talent project that contains the environment.</span></span> 
6. <span data-ttu-id="817a0-140">Dans votre projet LCS, sélectionnez la vignette **Gestion de l'application Talent**.</span><span class="sxs-lookup"><span data-stu-id="817a0-140">In your LCS project, select the **Talent App Management** tile.</span></span> 
7. <span data-ttu-id="817a0-141">Sélectionnez l'instance à supprimer, qui doit être marquée avec un statut de déploiement **Échec**.</span><span class="sxs-lookup"><span data-stu-id="817a0-141">Select the instance you would like to remove, which should be marked with a Deployment status of **Failed**.</span></span>
8. <span data-ttu-id="817a0-142">Sélectionnez **Supprimer l'instance** et confirmez votre décision.</span><span class="sxs-lookup"><span data-stu-id="817a0-142">Select **Remove instance** and confirm your decision.</span></span> 

