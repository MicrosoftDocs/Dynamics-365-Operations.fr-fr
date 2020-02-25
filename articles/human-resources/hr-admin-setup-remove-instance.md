---
title: Supprimer une instance
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5c5f875ad9361c31af4fbe863488b881cdd97a6e
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008967"
---
# <a name="remove-an-instance"></a><span data-ttu-id="620e6-102">Supprimer une instance</span><span class="sxs-lookup"><span data-stu-id="620e6-102">Remove an instance</span></span>

<span data-ttu-id="620e6-103">Cet article décrit le processus de suppression d'un pilote test ou d'un environnement de production pour Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="620e6-103">This article walks you through the process of removing a test drive or production environment for Microsoft Dynamics 365 Human Resources.</span></span>

## <a name="remove-a-test-drive-environment"></a><span data-ttu-id="620e6-104">Suppression d'un environnement de test</span><span class="sxs-lookup"><span data-stu-id="620e6-104">Remove a test drive environment</span></span>

<span data-ttu-id="620e6-105">Les tests Human Resources sont provisionnés avec une stratégie d'expiration de 60 jours.</span><span class="sxs-lookup"><span data-stu-id="620e6-105">Human Resources test drives are provisioned with a 60-day expiration policy.</span></span> <span data-ttu-id="620e6-106">Toutefois, les propriétaires des environnements de test ont l'option de mettre fin à leur période d'essai en suivant les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="620e6-106">However, owners of test drive environments have the option to end their trial early by completing the following steps.</span></span> 

1. <span data-ttu-id="620e6-107">Accédez au [centre d'administration Power Apps](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="620e6-107">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="620e6-108">Sélectionner **Environnements**.</span><span class="sxs-lookup"><span data-stu-id="620e6-108">Select **Environments**.</span></span>
3. <span data-ttu-id="620e6-109">Sélectionnez l'environnement de test, avec un modèle de dénomination similaire à ceci : TestDrive - alias@domain</span><span class="sxs-lookup"><span data-stu-id="620e6-109">Select the test drive environment, which has a naming pattern similar to this: TestDrive - alias@domain</span></span>
4. <span data-ttu-id="620e6-110">Sélectionnez **Supprimer** et confirmez la décision.</span><span class="sxs-lookup"><span data-stu-id="620e6-110">Select **Delete** and confirm the decision.</span></span> 

<span data-ttu-id="620e6-111">L'environnement de test existant est supprimé.</span><span class="sxs-lookup"><span data-stu-id="620e6-111">The existing test drive environment will be removed.</span></span> <span data-ttu-id="620e6-112">Une fois supprimé, vous pouvez vous inscrire à un nouvel environnement de test.</span><span class="sxs-lookup"><span data-stu-id="620e6-112">When it is removed, you can sign up for a new test drive environment.</span></span> 

## <a name="remove-a-production-environment"></a><span data-ttu-id="620e6-113">Suppression d'un environnement de production</span><span class="sxs-lookup"><span data-stu-id="620e6-113">Remove a production environment</span></span>

<span data-ttu-id="620e6-114">Cet article suppose que vous avez acheté Human Resources par l'intermédiaire d'un fournisseur de solutions Cloud (CSP) ou dans le cadre d'un contrat d'architecture d'entreprise (EA).</span><span class="sxs-lookup"><span data-stu-id="620e6-114">This article assumes that you've purchased Human Resources through a Cloud Solution Provider (CSP) or an enterprise architecture (EA) agreement.</span></span> 

<span data-ttu-id="620e6-115">Comme un seul environnement Human Resources est « contenu » dans un seul environnement Power Apps, il existe deux options à prendre en compte.</span><span class="sxs-lookup"><span data-stu-id="620e6-115">Since a single Human Resources environment is contained within a single Power Apps environment, there are two options to consider.</span></span> <span data-ttu-id="620e6-116">La première option implique de supprimer l'ensemble de l'environnement Power Apps ; puis supprimer uniquement Human Resources.</span><span class="sxs-lookup"><span data-stu-id="620e6-116">The first option involves removing the entire Power Apps environment; the second option involves removing only Human Resources.</span></span> <span data-ttu-id="620e6-117">La première option est recommandée lorsque vous avez créé un environnement Power Apps expressément pour le provisionnement de Human Resources, et que vous venez de commencer l'implémentation, ou que vous n'avez pas établi d'intégration.</span><span class="sxs-lookup"><span data-stu-id="620e6-117">The first option is preferred when you have created a Power Apps environment expressly for the purpose of provisioning Human Resources, and you've just begun implementation, or you don’t have any established integrations.</span></span> <span data-ttu-id="620e6-118">La deuxième option est utile lorsque vous avez établi un environnement Power Apps rempli avec des données enrichies qui sont exploitées dans Power Apps et Power Automate.</span><span class="sxs-lookup"><span data-stu-id="620e6-118">The second option is appropriate when you have an established Power Apps environment populated with rich data that's leveraged in Power Apps and Power Automate.</span></span>

> [!Important]
> <span data-ttu-id="620e6-119">Avant de supprimer l'environnement Power Apps, vérifiez qu'il n'est pas utilisé pour des intégrations de données enrichies en dehors de la portée de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="620e6-119">Before removing the Power Apps environment, ensure it is not being used for rich data integrations outside the scope of Human Resources.</span></span> <span data-ttu-id="620e6-120">Notez également que les environnements Power Apps par défaut ne peuvent pas être supprimés.</span><span class="sxs-lookup"><span data-stu-id="620e6-120">Also note that the default Power Apps environments cannot be removed.</span></span> 

<span data-ttu-id="620e6-121">Pour supprimer l'ensemble de l'environnement Power Apps, notamment Human Resources et les applications et flux associés :</span><span class="sxs-lookup"><span data-stu-id="620e6-121">To remove the entire Power Apps environment, including Human Resources and the associated apps and flows:</span></span>

1. <span data-ttu-id="620e6-122">Accédez au [centre d'administration Power Apps](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="620e6-122">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="620e6-123">Sélectionner **Environnements**.</span><span class="sxs-lookup"><span data-stu-id="620e6-123">Select **Environments**.</span></span>
3. <span data-ttu-id="620e6-124">Sélectionnez l'environnement à supprimer.</span><span class="sxs-lookup"><span data-stu-id="620e6-124">Select the environment to be removed.</span></span>
4. <span data-ttu-id="620e6-125">Sélectionnez **Supprimer** et confirmez la décision.</span><span class="sxs-lookup"><span data-stu-id="620e6-125">Select **Delete** and confirm the decision.</span></span> 
5. <span data-ttu-id="620e6-126">Attendez que la suppression soit terminée.</span><span class="sxs-lookup"><span data-stu-id="620e6-126">Wait until the deletion is complete.</span></span>
6. <span data-ttu-id="620e6-127">Connectez-vous à [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (CS) à l'aide du compte utilisé pour vous abonner à Human Resources.</span><span class="sxs-lookup"><span data-stu-id="620e6-127">Sign in to [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) using the account that you used to subscribe to Human Resources.</span></span> 
7. <span data-ttu-id="620e6-128">Sélectionnez le projet Human Resources qui contient l'environnement.</span><span class="sxs-lookup"><span data-stu-id="620e6-128">Select the Human Resources Project that contains the environment.</span></span> 
8. <span data-ttu-id="620e6-129">Dans votre projet LCS, sélectionnez la vignette **Gestion de l'application Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="620e6-129">In your LCS project, select the **Human Resources App Management** tile.</span></span> 
9. <span data-ttu-id="620e6-130">Sélectionnez l'instance à supprimer.</span><span class="sxs-lookup"><span data-stu-id="620e6-130">Select the instance to remove.</span></span> 
10. <span data-ttu-id="620e6-131">Sélectionnez **Supprimer l'instance** et confirmez votre décision.</span><span class="sxs-lookup"><span data-stu-id="620e6-131">Select **Remove instance** and confirm your decision.</span></span>  

<span data-ttu-id="620e6-132">Pour supprimer un environnement Human Resources d'un environnement Power Apps existant, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="620e6-132">To remove a Human Resources environment from an existing Power Apps environment, complete the following steps.</span></span> <span data-ttu-id="620e6-133">Notez que la nécessité d'inclure le support et de contacter l'équipe DevOps de Human Resources est temporaire tant que cette fonction est activée directement dans LCS.</span><span class="sxs-lookup"><span data-stu-id="620e6-133">Note that the need to involve support and contact the Human Resources DevOps team is temporary until this feature is enabled directly in LCS.</span></span>

1. <span data-ttu-id="620e6-134">Contactez le support pour lancer une demande de suppression.</span><span class="sxs-lookup"><span data-stu-id="620e6-134">Contact Support to initiate a removal request.</span></span>
2. <span data-ttu-id="620e6-135">L'équipe de support initialisera une demande de suppression avec l'équipe DevOps de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="620e6-135">The Support team will initiate a removal request with the Human Resources DevOps team.</span></span> 
3. <span data-ttu-id="620e6-136">Continuez après la réception du message indiquant que l'environnement a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="620e6-136">Continue after you receive word that the environment has been removed.</span></span>
4.  <span data-ttu-id="620e6-137">Connectez-vous à LCS à l'aide du compte utilisé pour vous abonner à Human Resources.</span><span class="sxs-lookup"><span data-stu-id="620e6-137">Sign in to LCS using the account that you used to subscribe to Human Resources.</span></span> 
5. <span data-ttu-id="620e6-138">Sélectionnez le projet Human Resources qui contient l'environnement.</span><span class="sxs-lookup"><span data-stu-id="620e6-138">Select the Human Resources project that contains the environment.</span></span> 
6. <span data-ttu-id="620e6-139">Dans votre projet LCS, sélectionnez la vignette **Gestion de l'application Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="620e6-139">In your LCS project, select the **Human Resources App Management** tile.</span></span> 
7. <span data-ttu-id="620e6-140">Sélectionnez l'instance à supprimer, qui doit être marquée avec un statut de déploiement **Échec**.</span><span class="sxs-lookup"><span data-stu-id="620e6-140">Select the instance you would like to remove, which should be marked with a Deployment status of **Failed**.</span></span>
8. <span data-ttu-id="620e6-141">Sélectionnez **Supprimer l'instance** et confirmez votre décision.</span><span class="sxs-lookup"><span data-stu-id="620e6-141">Select **Remove instance** and confirm your decision.</span></span> 
