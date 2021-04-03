---
title: Supprimer une instance
description: Cet article décrit le processus de suppression d’un pilote test ou d’un environnement de production pour Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 08/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1e6d1eff32b6f925541760f0c0408238f3c4d947
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466854"
---
# <a name="remove-an-instance"></a><span data-ttu-id="04b12-103">Supprimer une instance</span><span class="sxs-lookup"><span data-stu-id="04b12-103">Remove an instance</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="04b12-104">Cet article décrit le processus de suppression d’un pilote test ou d’un environnement de production pour Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="04b12-104">This article walks you through the process of removing a test drive or production environment for Microsoft Dynamics 365 Human Resources.</span></span>

## <a name="remove-a-test-drive-environment"></a><span data-ttu-id="04b12-105">Suppression d’un environnement de test</span><span class="sxs-lookup"><span data-stu-id="04b12-105">Remove a test drive environment</span></span>

<span data-ttu-id="04b12-106">Les tests Human Resources sont provisionnés avec une stratégie d’expiration de 60 jours.</span><span class="sxs-lookup"><span data-stu-id="04b12-106">Human Resources test drives are provisioned with a 60-day expiration policy.</span></span> <span data-ttu-id="04b12-107">Toutefois, les propriétaires des environnements de test ont l’option de mettre fin à leur période d’essai en suivant les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="04b12-107">However, owners of test drive environments have the option to end their trial early by completing the following steps.</span></span> 

1. <span data-ttu-id="04b12-108">Accédez au [centre d’administration Power Apps](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="04b12-108">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="04b12-109">Sélectionner **Environnements**.</span><span class="sxs-lookup"><span data-stu-id="04b12-109">Select **Environments**.</span></span>
3. <span data-ttu-id="04b12-110">Sélectionnez l’environnement de test, avec un modèle de dénomination similaire à ceci : TestDrive - alias@domain</span><span class="sxs-lookup"><span data-stu-id="04b12-110">Select the test drive environment, which has a naming pattern similar to this: TestDrive - alias@domain</span></span>
4. <span data-ttu-id="04b12-111">Sélectionnez **Supprimer** et confirmez la décision.</span><span class="sxs-lookup"><span data-stu-id="04b12-111">Select **Delete** and confirm the decision.</span></span> 

<span data-ttu-id="04b12-112">L’environnement de test existant est supprimé.</span><span class="sxs-lookup"><span data-stu-id="04b12-112">The existing test drive environment will be removed.</span></span> <span data-ttu-id="04b12-113">Une fois supprimé, vous pouvez vous inscrire à un nouvel environnement de test.</span><span class="sxs-lookup"><span data-stu-id="04b12-113">When it is removed, you can sign up for a new test drive environment.</span></span> 

## <a name="remove-a-production-environment"></a><span data-ttu-id="04b12-114">Suppression d’un environnement de production</span><span class="sxs-lookup"><span data-stu-id="04b12-114">Remove a production environment</span></span>

<span data-ttu-id="04b12-115">Cet article suppose que vous avez acheté Human Resources par l’intermédiaire d’un fournisseur de solutions Cloud (CSP) ou dans le cadre d’un contrat d’architecture d’entreprise (EA).</span><span class="sxs-lookup"><span data-stu-id="04b12-115">This article assumes that you've purchased Human Resources through a Cloud Solution Provider (CSP) or an enterprise architecture (EA) agreement.</span></span> 

<span data-ttu-id="04b12-116">Comme un seul environnement Human Resources est « contenu » dans un seul environnement Power Apps, il existe deux options à prendre en compte.</span><span class="sxs-lookup"><span data-stu-id="04b12-116">Since a single Human Resources environment is contained within a single Power Apps environment, there are two options to consider.</span></span> <span data-ttu-id="04b12-117">La première option implique de supprimer l’ensemble de l’environnement Power Apps ; puis supprimer uniquement Human Resources.</span><span class="sxs-lookup"><span data-stu-id="04b12-117">The first option involves removing the entire Power Apps environment; the second option involves removing only Human Resources.</span></span> <span data-ttu-id="04b12-118">La première option est recommandée lorsque vous avez créé un environnement Power Apps expressément pour le provisionnement de Human Resources, et que vous venez de commencer l’implémentation, ou que vous n’avez pas établi d’intégration.</span><span class="sxs-lookup"><span data-stu-id="04b12-118">The first option is preferred when you have created a Power Apps environment expressly for the purpose of provisioning Human Resources, and you've just begun implementation, or you don’t have any established integrations.</span></span> <span data-ttu-id="04b12-119">La deuxième option est utile lorsque vous avez établi un environnement Power Apps rempli avec des données enrichies qui sont exploitées dans Power Apps et Power Automate.</span><span class="sxs-lookup"><span data-stu-id="04b12-119">The second option is appropriate when you have an established Power Apps environment populated with rich data that's leveraged in Power Apps and Power Automate.</span></span>

> [!Important]
> <span data-ttu-id="04b12-120">Avant de supprimer l’environnement Power Apps, vérifiez qu’il n’est pas utilisé pour des intégrations de données enrichies en dehors de la portée de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="04b12-120">Before removing the Power Apps environment, ensure it is not being used for rich data integrations outside the scope of Human Resources.</span></span> <span data-ttu-id="04b12-121">Notez également que les environnements Power Apps par défaut ne peuvent pas être supprimés.</span><span class="sxs-lookup"><span data-stu-id="04b12-121">Also note that the default Power Apps environments cannot be removed.</span></span> 

<span data-ttu-id="04b12-122">Pour supprimer l’ensemble de l’environnement Power Apps, notamment Human Resources et les applications et flux associés :</span><span class="sxs-lookup"><span data-stu-id="04b12-122">To remove the entire Power Apps environment, including Human Resources and the associated apps and flows:</span></span>

1. <span data-ttu-id="04b12-123">Accédez au [centre d’administration Power Apps](https://admin.businessplatform.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="04b12-123">Navigate to the [Power Apps Admin center](https://admin.businessplatform.microsoft.com/).</span></span>
2. <span data-ttu-id="04b12-124">Sélectionner **Environnements**.</span><span class="sxs-lookup"><span data-stu-id="04b12-124">Select **Environments**.</span></span>
3. <span data-ttu-id="04b12-125">Sélectionnez l’environnement à supprimer.</span><span class="sxs-lookup"><span data-stu-id="04b12-125">Select the environment to be removed.</span></span>
4. <span data-ttu-id="04b12-126">Sélectionnez **Supprimer** et confirmez la décision.</span><span class="sxs-lookup"><span data-stu-id="04b12-126">Select **Delete** and confirm the decision.</span></span> 
5. <span data-ttu-id="04b12-127">Attendez que la suppression soit terminée.</span><span class="sxs-lookup"><span data-stu-id="04b12-127">Wait until the deletion is complete.</span></span>
6. <span data-ttu-id="04b12-128">Connectez-vous à [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (CS) à l’aide du compte utilisé pour vous abonner à Human Resources.</span><span class="sxs-lookup"><span data-stu-id="04b12-128">Sign in to [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) using the account that you used to subscribe to Human Resources.</span></span> 
7. <span data-ttu-id="04b12-129">Sélectionnez le projet Human Resources qui contient l’environnement.</span><span class="sxs-lookup"><span data-stu-id="04b12-129">Select the Human Resources Project that contains the environment.</span></span> 
8. <span data-ttu-id="04b12-130">Dans votre projet LCS, sélectionnez la vignette **Gestion de l’application Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="04b12-130">In your LCS project, select the **Human Resources App Management** tile.</span></span> 
9. <span data-ttu-id="04b12-131">Sélectionnez l’instance à supprimer.</span><span class="sxs-lookup"><span data-stu-id="04b12-131">Select the instance to remove.</span></span> 
10. <span data-ttu-id="04b12-132">Sélectionnez **Supprimer l’instance** et confirmez votre décision.</span><span class="sxs-lookup"><span data-stu-id="04b12-132">Select **Remove instance** and confirm your decision.</span></span>  

<span data-ttu-id="04b12-133">Pour supprimer un environnement Human Resources d’un environnement Power Apps existant, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="04b12-133">To remove a Human Resources environment from an existing Power Apps environment, complete the following steps.</span></span> <span data-ttu-id="04b12-134">Notez que la nécessité d’inclure le support et de contacter l’équipe DevOps de Human Resources est temporaire tant que cette fonction est activée directement dans LCS.</span><span class="sxs-lookup"><span data-stu-id="04b12-134">Note that the need to involve support and contact the Human Resources DevOps team is temporary until this feature is enabled directly in LCS.</span></span>

1. <span data-ttu-id="04b12-135">Contactez le support pour lancer une demande de suppression.</span><span class="sxs-lookup"><span data-stu-id="04b12-135">Contact Support to initiate a removal request.</span></span>
2. <span data-ttu-id="04b12-136">L’équipe de support initialisera une demande de suppression avec l’équipe DevOps de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="04b12-136">The Support team will initiate a removal request with the Human Resources DevOps team.</span></span> 
3. <span data-ttu-id="04b12-137">Continuez après la réception du message indiquant que l’environnement a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="04b12-137">Continue after you receive word that the environment has been removed.</span></span>
4. <span data-ttu-id="04b12-138">Connectez-vous à LCS à l’aide du compte utilisé pour vous abonner à Human Resources.</span><span class="sxs-lookup"><span data-stu-id="04b12-138">Sign in to LCS using the account that you used to subscribe to Human Resources.</span></span> 
5. <span data-ttu-id="04b12-139">Sélectionnez le projet Human Resources qui contient l’environnement.</span><span class="sxs-lookup"><span data-stu-id="04b12-139">Select the Human Resources project that contains the environment.</span></span> 
6. <span data-ttu-id="04b12-140">Dans votre projet LCS, sélectionnez la vignette **Gestion de l’application Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="04b12-140">In your LCS project, select the **Human Resources App Management** tile.</span></span> 
7. <span data-ttu-id="04b12-141">Sélectionnez l’instance à supprimer, qui doit être marquée avec un statut de déploiement **Supprimé**.</span><span class="sxs-lookup"><span data-stu-id="04b12-141">Select the instance you would like to remove, which should be marked with a Deployment status of **Deleted**.</span></span>
8. <span data-ttu-id="04b12-142">Sélectionnez **Supprimer l’instance** et confirmez votre décision.</span><span class="sxs-lookup"><span data-stu-id="04b12-142">Select **Remove instance** and confirm your decision.</span></span> 

## <a name="recover-a-soft-deleted-environment"></a><span data-ttu-id="04b12-143">Récupérer un environnement supprimé de manière temporaire</span><span class="sxs-lookup"><span data-stu-id="04b12-143">Recover a soft-deleted environment</span></span>

<span data-ttu-id="04b12-144">Si vous supprimez l’environnement Power Apps auquel votre environnement Human Resources est connecté, le statut de l’environnement Human Resources dans Lifecycle Services est **Suppression temporaire**.</span><span class="sxs-lookup"><span data-stu-id="04b12-144">If you delete the Power Apps environment that your Human Resources environment is connected to, the status of the Human Resources environment in Lifecycle Services will be **Soft deleted**.</span></span> <span data-ttu-id="04b12-145">Dans ce cas, les utilisateurs ne peuvent pas se connecter à Human Resources.</span><span class="sxs-lookup"><span data-stu-id="04b12-145">In this case, users can't connect to Human Resources.</span></span>

<span data-ttu-id="04b12-146">Pour restaurer l’environnement :</span><span class="sxs-lookup"><span data-stu-id="04b12-146">To restore the environment:</span></span>

1. <span data-ttu-id="04b12-147">Suivez les instructions dans [Récupérer l’environnement Power Apps](/power-platform/admin/recover-environment.md).</span><span class="sxs-lookup"><span data-stu-id="04b12-147">Follow the instructions in [Recover the Power Apps environment](/power-platform/admin/recover-environment.md).</span></span>

2. <span data-ttu-id="04b12-148">Contactez le support pour restaurer l’environnement Human Resources.</span><span class="sxs-lookup"><span data-stu-id="04b12-148">Contact Support to restore the Human Resources environment.</span></span> <span data-ttu-id="04b12-149">Pour plus d’informations, voir [Obtenir de l’aide](hr-admin-troubleshooting-support.md).</span><span class="sxs-lookup"><span data-stu-id="04b12-149">For more information, see [Get support](hr-admin-troubleshooting-support.md).</span></span>

> [!Warning]
> <span data-ttu-id="04b12-150">Les environnements Power Apps ne sont enregistrés que pendant sept jours après la suppression.</span><span class="sxs-lookup"><span data-stu-id="04b12-150">Power Apps environments are only saved for seven days after deletion.</span></span> <span data-ttu-id="04b12-151">Vous devez récupérer l’environnement dans le délai de sept jours.</span><span class="sxs-lookup"><span data-stu-id="04b12-151">You must recover the environment within the seven day period.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]