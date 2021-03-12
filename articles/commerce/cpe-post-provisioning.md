---
title: Configurer un environnement d'évaluation Dynamics 365 Commerce
description: Cette rubrique explique comment configurer un environnement d'évaluation Microsoft Dynamics 365 Commerce après sa mise en service.
author: psimolin
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: fa92a581a96de6bed26b4a0c6601ebd9d5088347
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993423"
---
# <a name="configure-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="e900d-103">Configurer un environnement d'évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="e900d-103">Configure a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e900d-104">Cette rubrique explique comment configurer un environnement d'évaluation Microsoft Dynamics 365 Commerce après sa mise en service.</span><span class="sxs-lookup"><span data-stu-id="e900d-104">This topic explains how to configure a Microsoft Dynamics 365 Commerce evaluation environment after it's provisioned.</span></span>

## <a name="overview"></a><span data-ttu-id="e900d-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="e900d-105">Overview</span></span>

<span data-ttu-id="e900d-106">Effectuez les procédures de cette rubrique uniquement une fois que votre environnement d'évaluation Commerce a été mis en service.</span><span class="sxs-lookup"><span data-stu-id="e900d-106">Complete the procedures in this topic only after your Commerce evaluation environment has been provisioned.</span></span> <span data-ttu-id="e900d-107">Pour plus d'informations sur la mise en service de votre environnement d'évaluation Commerce, consultez [Mise en service d'un environnement d'évaluation Commerce](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="e900d-107">For information about how to provision your Commerce evaluation environment, see [Provision a Commerce evaluation environment](provisioning-guide.md).</span></span>

<span data-ttu-id="e900d-108">Une fois que votre environnement d'évaluation Commerce a été mis en service de bout en bout, des étapes de configuration post-mise en service supplémentaires doivent être effectuées avant que vous puissiez commencer à évaluer l'environnement.</span><span class="sxs-lookup"><span data-stu-id="e900d-108">After your Commerce evaluation environment has been provisioned end to end, additional post-provisioning configuration steps must be completed before you can start to evaluate the environment.</span></span> <span data-ttu-id="e900d-109">Pour effectuer ces étapes, vous devez utiliser Microsoft Dynamics Lifecycle Services (LCS) et Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e900d-109">To complete these steps, you must use Microsoft Dynamics Lifecycle Services (LCS) and Dynamics 365 Commerce.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="e900d-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="e900d-110">Before you start</span></span>

1. <span data-ttu-id="e900d-111">Connectez-vous au [portail LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="e900d-111">Sign in to the [LCS portal](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="e900d-112">Accédez à votre projet.</span><span class="sxs-lookup"><span data-stu-id="e900d-112">Go to your project.</span></span>
1. <span data-ttu-id="e900d-113">Sur le menu principal, sélectionnez **Environnements hébergés dans le cloud**.</span><span class="sxs-lookup"><span data-stu-id="e900d-113">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="e900d-114">Sélectionnez votre environnement dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e900d-114">Select your environment in the list.</span></span>
1. <span data-ttu-id="e900d-115">Dans les informations de l'environnement à droite, cliquez sur **Se connecter à l'environnement**.</span><span class="sxs-lookup"><span data-stu-id="e900d-115">In the environment information on the right, select **Log on to environment**.</span></span> <span data-ttu-id="e900d-116">Vous êtes alors dirigé vers le siège de Commerce.</span><span class="sxs-lookup"><span data-stu-id="e900d-116">You will be sent to Commerce headquarters.</span></span>
1. <span data-ttu-id="e900d-117">Assurez-vous que l'entité juridique **USRT** est sélectionnée dans l'angle supérieur droit.</span><span class="sxs-lookup"><span data-stu-id="e900d-117">Make sure that the **USRT** legal entity is selected in the upper-right corner.</span></span>

<span data-ttu-id="e900d-118">Lors des activités post-mise en service au siège de Commerce, assurez-vous que l'entité juridique **USRT** est toujours sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e900d-118">During post-provisioning activities in Commerce headquarters, make sure that the **USRT** legal entity is always selected.</span></span>

## <a name="configure-the-point-of-sale"></a><span data-ttu-id="e900d-119">Configurer le point de vente</span><span class="sxs-lookup"><span data-stu-id="e900d-119">Configure the point of sale</span></span>

### <a name="associate-a-worker-with-your-identity"></a><span data-ttu-id="e900d-120">Associer un collaborateur à votre identité</span><span class="sxs-lookup"><span data-stu-id="e900d-120">Associate a worker with your identity</span></span>

<span data-ttu-id="e900d-121">Pour associer un collaborateur à votre identité, procédez comme suit dans le siège de Commerce.</span><span class="sxs-lookup"><span data-stu-id="e900d-121">To associate a worker with your identity, follow these steps in Commerce headquarters.</span></span>

1. <span data-ttu-id="e900d-122">Utilisez le menu à gauche pour accéder à **Modules \> Commerce et vente au détail \> Employés \> Collaborateurs**.</span><span class="sxs-lookup"><span data-stu-id="e900d-122">Use the menu on the left to go to **Modules \> Retail and commerce \> Employees \> Workers**.</span></span>
1. <span data-ttu-id="e900d-123">Dans la liste, recherchez et sélectionnez l'enregistrement suivant : **000713 - Andrew Collette**.</span><span class="sxs-lookup"><span data-stu-id="e900d-123">In the list, find and select the following record: **000713 - Andrew Collette**.</span></span>
1. <span data-ttu-id="e900d-124">Dans le volet Action, sélectionnez **Commerce**.</span><span class="sxs-lookup"><span data-stu-id="e900d-124">On the Action Pane, select **Commerce**.</span></span>
1. <span data-ttu-id="e900d-125">Sélectionnez **Associer une identité existante**.</span><span class="sxs-lookup"><span data-stu-id="e900d-125">Select **Associate existing identity**.</span></span>
1. <span data-ttu-id="e900d-126">Dans le champ **E-mail** (à droite de **Rechercher à l'aide de l'e-mail**), entrez votre adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="e900d-126">In the **Email** field to the right of **Search using email**, enter your email address.</span></span>
1. <span data-ttu-id="e900d-127">Sélectionnez **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="e900d-127">Select **Search**.</span></span>
1. <span data-ttu-id="e900d-128">Sélectionnez l'enregistrement à votre nom.</span><span class="sxs-lookup"><span data-stu-id="e900d-128">Select the record that has your name.</span></span>
1. <span data-ttu-id="e900d-129">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e900d-129">Select **OK**.</span></span>
1. <span data-ttu-id="e900d-130">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e900d-130">Select **Save**.</span></span>

### <a name="activate-cloud-pos"></a><span data-ttu-id="e900d-131">Activer le PDV Cloud</span><span class="sxs-lookup"><span data-stu-id="e900d-131">Activate Cloud POS</span></span>

<span data-ttu-id="e900d-132">Pour activer Cloud POS, procédez comme suit dans LCS.</span><span class="sxs-lookup"><span data-stu-id="e900d-132">To activate Cloud POS, follow these steps in LCS.</span></span>

1. <span data-ttu-id="e900d-133">Sur le menu principal, sélectionnez **Environnements hébergés dans le cloud**.</span><span class="sxs-lookup"><span data-stu-id="e900d-133">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="e900d-134">Sélectionnez votre environnement dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e900d-134">Select your environment in the list.</span></span>
1. <span data-ttu-id="e900d-135">Dans les informations de l'environnement à droite, cliquez sur **Connexion au point de vente du cloud**.</span><span class="sxs-lookup"><span data-stu-id="e900d-135">In the environment information on the right, select **Log on to Cloud Point of Sale**.</span></span>
1. <span data-ttu-id="e900d-136">Sélectionnez **Suivant** pour ouvrir la boîte de dialogue **Avant de commencer**.</span><span class="sxs-lookup"><span data-stu-id="e900d-136">Select **Next** to open the **Before you start** dialog box.</span></span>
1. <span data-ttu-id="e900d-137">Laissez le champ **URL Serveur** tel qu'il est.</span><span class="sxs-lookup"><span data-stu-id="e900d-137">Leave the **Server URL** field as it is.</span></span> <span data-ttu-id="e900d-138">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e900d-138">Select **Next**.</span></span>
1. <span data-ttu-id="e900d-139">Connectez-vous en utilisant votre compte Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="e900d-139">Sign in by using your Microsoft Azure Active Directory (Azure AD) account.</span></span>
1. <span data-ttu-id="e900d-140">Sous **Nom du magasin**, sélectionnez **San Francisco**, puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e900d-140">Under **Store name**, select **San Francisco**, and then select **Next**.</span></span>
1. <span data-ttu-id="e900d-141">Sous **Registre et périphérique**, sélectionnez **SAiNNAZ-1**.</span><span class="sxs-lookup"><span data-stu-id="e900d-141">Under **Register and device**, select **SANFRAN-1**.</span></span>
1. <span data-ttu-id="e900d-142">Sélectionnez **Activer**.</span><span class="sxs-lookup"><span data-stu-id="e900d-142">Select **Activate**.</span></span> <span data-ttu-id="e900d-143">Vous êtes déconnecté et dirigé vers la page de connexion au PDV.</span><span class="sxs-lookup"><span data-stu-id="e900d-143">You're signed out and taken to the POS sign-in page.</span></span>
1. <span data-ttu-id="e900d-144">Vous pouvez désormais vous connecter à l'expérience du PDV de cloud à l'aide de l'ID opérateur **000713** et le mot de passe **123**.</span><span class="sxs-lookup"><span data-stu-id="e900d-144">You can now sign in to the Cloud POS experience by using operator ID **000713** and password **123**.</span></span>

## <a name="set-up-your-site-in-commerce"></a><span data-ttu-id="e900d-145">Configurer votre site dans Commerce</span><span class="sxs-lookup"><span data-stu-id="e900d-145">Set up your site in Commerce</span></span>

<span data-ttu-id="e900d-146">Pour commencer à configurer votre site d'évaluation dans Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e900d-146">To start to set up your evaluation site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="e900d-147">Connectez-vous au générateur de site en utilisant l'URL que vous avez notée lorsque vous avez initialisé le commerce électronique lors de la mise en service (voir [Initialiser le commerce électronique](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="e900d-147">Sign in to site builder by using the URL that you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="e900d-148">Sélectionnez le site **Fabrikam** pour ouvrir la boîte de dialogue de paramétrage de site.</span><span class="sxs-lookup"><span data-stu-id="e900d-148">Select the **Fabrikam** site to open the site setup dialog box.</span></span>
1. <span data-ttu-id="e900d-149">Sélectionnez le domaine que vous avez entré lors de l'initialisation du commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="e900d-149">Select the domain that you entered when you initialized e-Commerce.</span></span>
1. <span data-ttu-id="e900d-150">Sélectionnez **Fabrikam a étendu le magasin en ligne** comme canal par défaut.</span><span class="sxs-lookup"><span data-stu-id="e900d-150">Select **Fabrikam extended online store** as the default channel.</span></span> <span data-ttu-id="e900d-151">(Vérifiez que vous sélectionnez le magasin en ligne **étendu**.)</span><span class="sxs-lookup"><span data-stu-id="e900d-151">(Make sure that you select the **extended** online store.)</span></span>
1. <span data-ttu-id="e900d-152">Sélectionnez **fr-fr** comme langue par défaut.</span><span class="sxs-lookup"><span data-stu-id="e900d-152">Select **en-us** as the default language.</span></span>
1. <span data-ttu-id="e900d-153">Laissez la valeur du champ **Chemin d'accès** telle quelle.</span><span class="sxs-lookup"><span data-stu-id="e900d-153">Leave the value of the **Path** field as it is.</span></span>
1. <span data-ttu-id="e900d-154">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e900d-154">Select **OK**.</span></span> <span data-ttu-id="e900d-155">La liste des pages du site apparaît.</span><span class="sxs-lookup"><span data-stu-id="e900d-155">The list of pages on the site appears.</span></span>

## <a name="enable-jobs"></a><span data-ttu-id="e900d-156">Activer les tâches</span><span class="sxs-lookup"><span data-stu-id="e900d-156">Enable jobs</span></span>

<span data-ttu-id="e900d-157">Pour activer les tâches dans Commerce, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e900d-157">To enable jobs in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="e900d-158">Connectez-vous à l'environnement (Siège social).</span><span class="sxs-lookup"><span data-stu-id="e900d-158">Sign in to the environment (HQ).</span></span>
1. <span data-ttu-id="e900d-159">Utilisez le menu à gauche pour accéder à **Retail et Commerce \> Recherches et états \> Traitements par lots**.</span><span class="sxs-lookup"><span data-stu-id="e900d-159">Use the menu on the left to go to **Retail and commerce \> Inquiries and reports \> Batch jobs**.</span></span>

    <span data-ttu-id="e900d-160">Les étapes restantes de cette procédure doivent être exécutées pour chacun des travaux suivants :</span><span class="sxs-lookup"><span data-stu-id="e900d-160">The remaining steps of this procedure must be completed for each of the following jobs:</span></span>

    * <span data-ttu-id="e900d-161">Traiter la notification par e-mail des commandes de vente au détail</span><span class="sxs-lookup"><span data-stu-id="e900d-161">Process retail order email notification</span></span>
    * <span data-ttu-id="e900d-162">Disponibilité du produit</span><span class="sxs-lookup"><span data-stu-id="e900d-162">Product availability</span></span>
    * <span data-ttu-id="e900d-163">P-0001</span><span class="sxs-lookup"><span data-stu-id="e900d-163">P-0001</span></span>
    * <span data-ttu-id="e900d-164">Synchroniser la tâche des commandes</span><span class="sxs-lookup"><span data-stu-id="e900d-164">Synchronize orders job</span></span>

1. <span data-ttu-id="e900d-165">Utilisez le filtre rapide pour rechercher la tâche selon son nom.</span><span class="sxs-lookup"><span data-stu-id="e900d-165">Use the Quick Filter to search for the job by name.</span></span>
1. <span data-ttu-id="e900d-166">Si le statut de la tâche est **En cours d'exécution**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e900d-166">If the status of the job is **Executing**, follow these steps:</span></span>

    1. <span data-ttu-id="e900d-167">Sélectionner l'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="e900d-167">Select the record.</span></span>
    1. <span data-ttu-id="e900d-168">Dans le volet Actions, sous **Traitement par lots**, sélectionnez **Modifier le statut**.</span><span class="sxs-lookup"><span data-stu-id="e900d-168">On the Action Pane, on **Batch job** tab, select **Change status**.</span></span>
    1. <span data-ttu-id="e900d-169">Sélectionnez **Annulation**, puis **OK**.</span><span class="sxs-lookup"><span data-stu-id="e900d-169">Select **Canceling**, and then select **OK**.</span></span>

<span data-ttu-id="e900d-170">Si vous le souhaitez, vous pouvez également définir l'intervalle de récurrence sur une (1) minute pour les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="e900d-170">Optionally, you can also set the recurrence interval to one (1) minute for the following jobs:</span></span>

* <span data-ttu-id="e900d-171">Traiter la tâche de notification par e-mail des commandes de vente au détail</span><span class="sxs-lookup"><span data-stu-id="e900d-171">Process retail order email notification job</span></span>
* <span data-ttu-id="e900d-172">Tâche P-0001</span><span class="sxs-lookup"><span data-stu-id="e900d-172">P-0001 job</span></span>
* <span data-ttu-id="e900d-173">Synchroniser la tâche des commandes</span><span class="sxs-lookup"><span data-stu-id="e900d-173">Synchronize orders job</span></span>

### <a name="run-full-data-synchronization"></a><span data-ttu-id="e900d-174">Exécuter la synchronisation complète des données</span><span class="sxs-lookup"><span data-stu-id="e900d-174">Run full data synchronization</span></span>

<span data-ttu-id="e900d-175">Pour exécuter la synchronisation complète des données dans Commerce, procédez comme suit dans le siège de Commerce.</span><span class="sxs-lookup"><span data-stu-id="e900d-175">To run full data synchronization in Commerce, follow these steps in Commerce headquarters.</span></span>

1. <span data-ttu-id="e900d-176">Utilisez le menu à gauche pour accéder à **Modules \> Retail et Commerce \> Paramétrage du Siège \> Planificateur Commerce \> Base de données du canal**.</span><span class="sxs-lookup"><span data-stu-id="e900d-176">Use the menu on the left to go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce scheduler \> Channel database**.</span></span>
1. <span data-ttu-id="e900d-177">Sélectionnez le canal nommé **scXXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="e900d-177">Select the channel that is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="e900d-178">Sur le volet Action, sélectionnez **Synchronisation de données complète**.</span><span class="sxs-lookup"><span data-stu-id="e900d-178">On the Action Pane, select **Full data sync**.</span></span>
1. <span data-ttu-id="e900d-179">Entrez **9999** comme programme de distribution.</span><span class="sxs-lookup"><span data-stu-id="e900d-179">Enter **9999** as the distribution schedule.</span></span>
1. <span data-ttu-id="e900d-180">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e900d-180">Select **OK**.</span></span>
1. <span data-ttu-id="e900d-181">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e900d-181">Select **OK**.</span></span>

### <a name="test-credit-card-information-to-do-test-purchases"></a><span data-ttu-id="e900d-182">Tester les informations de carte de crédit pour effectuer des tests d'achats</span><span class="sxs-lookup"><span data-stu-id="e900d-182">Test credit card information to do test purchases</span></span>

<span data-ttu-id="e900d-183">Pour effectuer des tests de transactions sur le site, vous pouvez utiliser les informations de carte de crédit de test suivantes :</span><span class="sxs-lookup"><span data-stu-id="e900d-183">To perform test transactions on the site, you can use the following test credit card information:</span></span>

- <span data-ttu-id="e900d-184">**Numéro de carte :** 4111-1111-1111-1111</span><span class="sxs-lookup"><span data-stu-id="e900d-184">**Card number:** 4111-1111-1111-1111</span></span>
- <span data-ttu-id="e900d-185">**Date d'expiration :** 10/20</span><span class="sxs-lookup"><span data-stu-id="e900d-185">**Expiration date:** 10/20</span></span>
- <span data-ttu-id="e900d-186">**Code de valeur de la vérification de la carte (CVV) :** 737</span><span class="sxs-lookup"><span data-stu-id="e900d-186">**Card verification value (CVV) code:** 737</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e900d-187">En aucun cas vous ne devez tenter d'utiliser des informations de carte de crédit réelle sur le site de test.</span><span class="sxs-lookup"><span data-stu-id="e900d-187">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e900d-188">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="e900d-188">Next steps</span></span>

<span data-ttu-id="e900d-189">Une fois les étapes de mise en service et de configuration terminées, vous pouvez commencer à évaluer votre environnement d'évaluation.</span><span class="sxs-lookup"><span data-stu-id="e900d-189">After the provisioning and configuration steps are completed, you can start to use your evaluation environment.</span></span> <span data-ttu-id="e900d-190">Utilisez l'URL du générateur de site Commerce pour accéder à l'expérience de création.</span><span class="sxs-lookup"><span data-stu-id="e900d-190">Use the Commerce site builder URL to go to the authoring experience.</span></span> <span data-ttu-id="e900d-191">Utilisez l'URL du site Commerce pour accéder à l'expérience du site du client de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="e900d-191">Use the Commerce site URL to go to the retail customer site experience.</span></span>

<span data-ttu-id="e900d-192">Pour configurer des fonctionnalités facultatives de votre environnement d'évaluation Commerce, consultez [Configurer les fonctionnalités facultatives d'un environnement d'évaluation Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="e900d-192">To configure optional features for your Commerce evaluation environment, see [Configure optional features for a Commerce evaluation environment](cpe-optional-features.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e900d-193">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e900d-193">Additional resources</span></span>

[<span data-ttu-id="e900d-194">Vue d'ensemble d'un environnement d'évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="e900d-194">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="e900d-195">Mettre en service un environnement d'évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="e900d-195">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="e900d-196">Configurer des fonctionnalités facultatives pour un environnement d'évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="e900d-196">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="e900d-197">Configurer le BOPIS dans un environnement d'évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="e900d-197">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="e900d-198">FAQ des environnements d'évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="e900d-198">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="e900d-199">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="e900d-199">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="e900d-200">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="e900d-200">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="e900d-201">Portail Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="e900d-201">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="e900d-202">Site web Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="e900d-202">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)
