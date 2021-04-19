---
title: Configurer un environnement d’évaluation Dynamics 365 Commerce
description: Cette rubrique explique comment configurer un environnement d’évaluation Microsoft Dynamics 365 Commerce après sa mise en service.
author: psimolin
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 10e80830a1cb0864c7eef19857b91e36ad27cdef
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795857"
---
# <a name="configure-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="06f2e-103">Configurer un environnement d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="06f2e-103">Configure a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="06f2e-104">Cette rubrique explique comment configurer un environnement d’évaluation Microsoft Dynamics 365 Commerce après sa mise en service.</span><span class="sxs-lookup"><span data-stu-id="06f2e-104">This topic explains how to configure a Microsoft Dynamics 365 Commerce evaluation environment after it's provisioned.</span></span>

<span data-ttu-id="06f2e-105">Effectuez les procédures de cette rubrique uniquement une fois que votre environnement d’évaluation Commerce a été mis en service.</span><span class="sxs-lookup"><span data-stu-id="06f2e-105">Complete the procedures in this topic only after your Commerce evaluation environment has been provisioned.</span></span> <span data-ttu-id="06f2e-106">Pour plus d’informations sur la mise en service de votre environnement d’évaluation Commerce, consultez [Mise en service d’un environnement d’évaluation Commerce](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="06f2e-106">For information about how to provision your Commerce evaluation environment, see [Provision a Commerce evaluation environment](provisioning-guide.md).</span></span>

<span data-ttu-id="06f2e-107">Une fois que votre environnement d’évaluation Commerce a été mis en service de bout en bout, des étapes de configuration post-mise en service supplémentaires doivent être effectuées avant que vous puissiez commencer à évaluer l’environnement.</span><span class="sxs-lookup"><span data-stu-id="06f2e-107">After your Commerce evaluation environment has been provisioned end to end, additional post-provisioning configuration steps must be completed before you can start to evaluate the environment.</span></span> <span data-ttu-id="06f2e-108">Pour effectuer ces étapes, vous devez utiliser Microsoft Dynamics Lifecycle Services (LCS) et Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="06f2e-108">To complete these steps, you must use Microsoft Dynamics Lifecycle Services (LCS) and Dynamics 365 Commerce.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="06f2e-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="06f2e-109">Before you start</span></span>

1. <span data-ttu-id="06f2e-110">Connectez-vous au [portail LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="06f2e-110">Sign in to the [LCS portal](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="06f2e-111">Accédez à votre projet.</span><span class="sxs-lookup"><span data-stu-id="06f2e-111">Go to your project.</span></span>
1. <span data-ttu-id="06f2e-112">Sur le menu principal, sélectionnez **Environnements hébergés dans le cloud**.</span><span class="sxs-lookup"><span data-stu-id="06f2e-112">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="06f2e-113">Sélectionnez votre environnement dans la liste.</span><span class="sxs-lookup"><span data-stu-id="06f2e-113">Select your environment in the list.</span></span>
1. <span data-ttu-id="06f2e-114">Dans les informations de l’environnement à droite, cliquez sur **Se connecter à l’environnement**.</span><span class="sxs-lookup"><span data-stu-id="06f2e-114">In the environment information on the right, select **Log on to environment**.</span></span> <span data-ttu-id="06f2e-115">Vous êtes alors dirigé vers le siège de Commerce.</span><span class="sxs-lookup"><span data-stu-id="06f2e-115">You will be sent to Commerce headquarters.</span></span>
1. <span data-ttu-id="06f2e-116">Assurez-vous que l’entité juridique **USRT** est sélectionnée dans l’angle supérieur droit.</span><span class="sxs-lookup"><span data-stu-id="06f2e-116">Make sure that the **USRT** legal entity is selected in the upper-right corner.</span></span>

<span data-ttu-id="06f2e-117">Lors des activités post-mise en service au siège de Commerce, assurez-vous que l’entité juridique **USRT** est toujours sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="06f2e-117">During post-provisioning activities in Commerce headquarters, make sure that the **USRT** legal entity is always selected.</span></span>

## <a name="configure-the-point-of-sale"></a><span data-ttu-id="06f2e-118">Configurer le point de vente</span><span class="sxs-lookup"><span data-stu-id="06f2e-118">Configure the point of sale</span></span>

### <a name="associate-a-worker-with-your-identity"></a><span data-ttu-id="06f2e-119">Associer un collaborateur à votre identité</span><span class="sxs-lookup"><span data-stu-id="06f2e-119">Associate a worker with your identity</span></span>

<span data-ttu-id="06f2e-120">Pour associer un collaborateur à votre identité, procédez comme suit dans le siège de Commerce.</span><span class="sxs-lookup"><span data-stu-id="06f2e-120">To associate a worker with your identity, follow these steps in Commerce headquarters.</span></span>

1. <span data-ttu-id="06f2e-121">Utilisez le menu à gauche pour accéder à **Modules \> Commerce et vente au détail \> Employés \> Collaborateurs**.</span><span class="sxs-lookup"><span data-stu-id="06f2e-121">Use the menu on the left to go to **Modules \> Retail and commerce \> Employees \> Workers**.</span></span>
1. <span data-ttu-id="06f2e-122">Dans la liste, recherchez et sélectionnez l’enregistrement suivant : **000713 - Andrew Collette**.</span><span class="sxs-lookup"><span data-stu-id="06f2e-122">In the list, find and select the following record: **000713 - Andrew Collette**.</span></span>
1. <span data-ttu-id="06f2e-123">Dans le volet Action, sélectionnez **Commerce**.</span><span class="sxs-lookup"><span data-stu-id="06f2e-123">On the Action Pane, select **Commerce**.</span></span>
1. <span data-ttu-id="06f2e-124">Sélectionnez **Associer une identité existante**.</span><span class="sxs-lookup"><span data-stu-id="06f2e-124">Select **Associate existing identity**.</span></span>
1. <span data-ttu-id="06f2e-125">Dans le champ **E-mail** (à droite de **Rechercher à l’aide de l’e-mail**), entrez votre adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="06f2e-125">In the **Email** field to the right of **Search using email**, enter your email address.</span></span>
1. <span data-ttu-id="06f2e-126">Sélectionnez **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="06f2e-126">Select **Search**.</span></span>
1. <span data-ttu-id="06f2e-127">Sélectionnez l’enregistrement à votre nom.</span><span class="sxs-lookup"><span data-stu-id="06f2e-127">Select the record that has your name.</span></span>
1. <span data-ttu-id="06f2e-128">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="06f2e-128">Select **OK**.</span></span>
1. <span data-ttu-id="06f2e-129">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="06f2e-129">Select **Save**.</span></span>

### <a name="activate-cloud-pos"></a><span data-ttu-id="06f2e-130">Activer le PDV Cloud</span><span class="sxs-lookup"><span data-stu-id="06f2e-130">Activate Cloud POS</span></span>

<span data-ttu-id="06f2e-131">Pour activer Cloud POS, procédez comme suit dans LCS.</span><span class="sxs-lookup"><span data-stu-id="06f2e-131">To activate Cloud POS, follow these steps in LCS.</span></span>

1. <span data-ttu-id="06f2e-132">Sur le menu principal, sélectionnez **Environnements hébergés dans le cloud**.</span><span class="sxs-lookup"><span data-stu-id="06f2e-132">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="06f2e-133">Sélectionnez votre environnement dans la liste.</span><span class="sxs-lookup"><span data-stu-id="06f2e-133">Select your environment in the list.</span></span>
1. <span data-ttu-id="06f2e-134">Dans les informations de l’environnement à droite, cliquez sur **Connexion au point de vente du cloud**.</span><span class="sxs-lookup"><span data-stu-id="06f2e-134">In the environment information on the right, select **Log on to Cloud Point of Sale**.</span></span>
1. <span data-ttu-id="06f2e-135">Sélectionnez **Suivant** pour ouvrir la boîte de dialogue **Avant de commencer**.</span><span class="sxs-lookup"><span data-stu-id="06f2e-135">Select **Next** to open the **Before you start** dialog box.</span></span>
1. <span data-ttu-id="06f2e-136">Laissez le champ **URL Serveur** tel qu’il est.</span><span class="sxs-lookup"><span data-stu-id="06f2e-136">Leave the **Server URL** field as it is.</span></span> <span data-ttu-id="06f2e-137">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="06f2e-137">Select **Next**.</span></span>
1. <span data-ttu-id="06f2e-138">Connectez-vous en utilisant votre compte Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="06f2e-138">Sign in by using your Microsoft Azure Active Directory (Azure AD) account.</span></span>
1. <span data-ttu-id="06f2e-139">Sous **Nom du magasin**, sélectionnez **San Francisco**, puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="06f2e-139">Under **Store name**, select **San Francisco**, and then select **Next**.</span></span>
1. <span data-ttu-id="06f2e-140">Sous **Registre et périphérique**, sélectionnez **SAiNNAZ-1**.</span><span class="sxs-lookup"><span data-stu-id="06f2e-140">Under **Register and device**, select **SANFRAN-1**.</span></span>
1. <span data-ttu-id="06f2e-141">Sélectionnez **Activer**.</span><span class="sxs-lookup"><span data-stu-id="06f2e-141">Select **Activate**.</span></span> <span data-ttu-id="06f2e-142">Vous êtes déconnecté et dirigé vers la page de connexion au PDV.</span><span class="sxs-lookup"><span data-stu-id="06f2e-142">You're signed out and taken to the POS sign-in page.</span></span>
1. <span data-ttu-id="06f2e-143">Vous pouvez désormais vous connecter à l’expérience du PDV de cloud à l’aide de l’ID opérateur **000713** et le mot de passe **123**.</span><span class="sxs-lookup"><span data-stu-id="06f2e-143">You can now sign in to the Cloud POS experience by using operator ID **000713** and password **123**.</span></span>

## <a name="set-up-your-site-in-commerce"></a><span data-ttu-id="06f2e-144">Configurer votre site dans Commerce</span><span class="sxs-lookup"><span data-stu-id="06f2e-144">Set up your site in Commerce</span></span>

<span data-ttu-id="06f2e-145">Pour commencer à configurer votre site d’évaluation dans Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="06f2e-145">To start to set up your evaluation site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="06f2e-146">Connectez-vous au générateur de site en utilisant l’URL que vous avez notée lorsque vous avez initialisé le commerce électronique lors de la mise en service (voir [Initialiser le commerce électronique](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="06f2e-146">Sign in to site builder by using the URL that you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="06f2e-147">Sélectionnez le site **Fabrikam** pour ouvrir la boîte de dialogue de paramétrage de site.</span><span class="sxs-lookup"><span data-stu-id="06f2e-147">Select the **Fabrikam** site to open the site setup dialog box.</span></span>
1. <span data-ttu-id="06f2e-148">Sélectionnez le domaine que vous avez entré lors de l’initialisation du commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="06f2e-148">Select the domain that you entered when you initialized e-Commerce.</span></span>
1. <span data-ttu-id="06f2e-149">Sélectionnez **Fabrikam a étendu le magasin en ligne** comme canal par défaut.</span><span class="sxs-lookup"><span data-stu-id="06f2e-149">Select **Fabrikam extended online store** as the default channel.</span></span> <span data-ttu-id="06f2e-150">(Vérifiez que vous sélectionnez le magasin en ligne **étendu**.)</span><span class="sxs-lookup"><span data-stu-id="06f2e-150">(Make sure that you select the **extended** online store.)</span></span>
1. <span data-ttu-id="06f2e-151">Sélectionnez **fr-fr** comme langue par défaut.</span><span class="sxs-lookup"><span data-stu-id="06f2e-151">Select **en-us** as the default language.</span></span>
1. <span data-ttu-id="06f2e-152">Laissez la valeur du champ **Chemin d’accès** telle quelle.</span><span class="sxs-lookup"><span data-stu-id="06f2e-152">Leave the value of the **Path** field as it is.</span></span>
1. <span data-ttu-id="06f2e-153">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="06f2e-153">Select **OK**.</span></span> <span data-ttu-id="06f2e-154">La liste des pages du site apparaît.</span><span class="sxs-lookup"><span data-stu-id="06f2e-154">The list of pages on the site appears.</span></span>

## <a name="enable-jobs"></a><span data-ttu-id="06f2e-155">Activer les tâches</span><span class="sxs-lookup"><span data-stu-id="06f2e-155">Enable jobs</span></span>

<span data-ttu-id="06f2e-156">Pour activer les tâches dans Commerce, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="06f2e-156">To enable jobs in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="06f2e-157">Connectez-vous à l’environnement (Siège social).</span><span class="sxs-lookup"><span data-stu-id="06f2e-157">Sign in to the environment (HQ).</span></span>
1. <span data-ttu-id="06f2e-158">Utilisez le menu à gauche pour accéder à **Retail et Commerce \> Recherches et états \> Traitements par lots**.</span><span class="sxs-lookup"><span data-stu-id="06f2e-158">Use the menu on the left to go to **Retail and commerce \> Inquiries and reports \> Batch jobs**.</span></span>

    <span data-ttu-id="06f2e-159">Les étapes restantes de cette procédure doivent être exécutées pour chacun des travaux suivants :</span><span class="sxs-lookup"><span data-stu-id="06f2e-159">The remaining steps of this procedure must be completed for each of the following jobs:</span></span>

    * <span data-ttu-id="06f2e-160">Traiter la notification par e-mail des commandes de vente au détail</span><span class="sxs-lookup"><span data-stu-id="06f2e-160">Process retail order email notification</span></span>
    * <span data-ttu-id="06f2e-161">Disponibilité du produit</span><span class="sxs-lookup"><span data-stu-id="06f2e-161">Product availability</span></span>
    * <span data-ttu-id="06f2e-162">P-0001</span><span class="sxs-lookup"><span data-stu-id="06f2e-162">P-0001</span></span>
    * <span data-ttu-id="06f2e-163">Synchroniser la tâche des commandes</span><span class="sxs-lookup"><span data-stu-id="06f2e-163">Synchronize orders job</span></span>

1. <span data-ttu-id="06f2e-164">Utilisez le filtre rapide pour rechercher la tâche selon son nom.</span><span class="sxs-lookup"><span data-stu-id="06f2e-164">Use the Quick Filter to search for the job by name.</span></span>
1. <span data-ttu-id="06f2e-165">Si le statut de la tâche est **En cours d’exécution**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="06f2e-165">If the status of the job is **Executing**, follow these steps:</span></span>

    1. <span data-ttu-id="06f2e-166">Sélectionner l’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="06f2e-166">Select the record.</span></span>
    1. <span data-ttu-id="06f2e-167">Dans le volet Actions, sous **Traitement par lots**, sélectionnez **Modifier le statut**.</span><span class="sxs-lookup"><span data-stu-id="06f2e-167">On the Action Pane, on **Batch job** tab, select **Change status**.</span></span>
    1. <span data-ttu-id="06f2e-168">Sélectionnez **Annulation**, puis **OK**.</span><span class="sxs-lookup"><span data-stu-id="06f2e-168">Select **Canceling**, and then select **OK**.</span></span>

<span data-ttu-id="06f2e-169">Si vous le souhaitez, vous pouvez également définir l’intervalle de récurrence sur une (1) minute pour les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="06f2e-169">Optionally, you can also set the recurrence interval to one (1) minute for the following jobs:</span></span>

* <span data-ttu-id="06f2e-170">Traiter la tâche de notification par e-mail des commandes de vente au détail</span><span class="sxs-lookup"><span data-stu-id="06f2e-170">Process retail order email notification job</span></span>
* <span data-ttu-id="06f2e-171">Tâche P-0001</span><span class="sxs-lookup"><span data-stu-id="06f2e-171">P-0001 job</span></span>
* <span data-ttu-id="06f2e-172">Synchroniser la tâche des commandes</span><span class="sxs-lookup"><span data-stu-id="06f2e-172">Synchronize orders job</span></span>

### <a name="run-full-data-synchronization"></a><span data-ttu-id="06f2e-173">Exécuter la synchronisation complète des données</span><span class="sxs-lookup"><span data-stu-id="06f2e-173">Run full data synchronization</span></span>

<span data-ttu-id="06f2e-174">Pour exécuter la synchronisation complète des données dans Commerce, procédez comme suit dans le siège de Commerce.</span><span class="sxs-lookup"><span data-stu-id="06f2e-174">To run full data synchronization in Commerce, follow these steps in Commerce headquarters.</span></span>

1. <span data-ttu-id="06f2e-175">Utilisez le menu à gauche pour accéder à **Modules \> Retail et Commerce \> Paramétrage du Siège \> Planificateur Commerce \> Base de données du canal**.</span><span class="sxs-lookup"><span data-stu-id="06f2e-175">Use the menu on the left to go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce scheduler \> Channel database**.</span></span>
1. <span data-ttu-id="06f2e-176">Sélectionnez le canal nommé **scXXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="06f2e-176">Select the channel that is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="06f2e-177">Sur le volet Action, sélectionnez **Synchronisation de données complète**.</span><span class="sxs-lookup"><span data-stu-id="06f2e-177">On the Action Pane, select **Full data sync**.</span></span>
1. <span data-ttu-id="06f2e-178">Entrez **9999** comme programme de distribution.</span><span class="sxs-lookup"><span data-stu-id="06f2e-178">Enter **9999** as the distribution schedule.</span></span>
1. <span data-ttu-id="06f2e-179">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="06f2e-179">Select **OK**.</span></span>
1. <span data-ttu-id="06f2e-180">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="06f2e-180">Select **OK**.</span></span>

### <a name="test-credit-card-information-to-do-test-purchases"></a><span data-ttu-id="06f2e-181">Tester les informations de carte de crédit pour effectuer des tests d’achats</span><span class="sxs-lookup"><span data-stu-id="06f2e-181">Test credit card information to do test purchases</span></span>

<span data-ttu-id="06f2e-182">Pour effectuer des tests de transactions sur le site, vous pouvez utiliser les informations de carte de crédit de test suivantes :</span><span class="sxs-lookup"><span data-stu-id="06f2e-182">To perform test transactions on the site, you can use the following test credit card information:</span></span>

- <span data-ttu-id="06f2e-183">**Numéro de carte :** 4111-1111-1111-1111</span><span class="sxs-lookup"><span data-stu-id="06f2e-183">**Card number:** 4111-1111-1111-1111</span></span>
- <span data-ttu-id="06f2e-184">**Date d’expiration :** 10/20</span><span class="sxs-lookup"><span data-stu-id="06f2e-184">**Expiration date:** 10/20</span></span>
- <span data-ttu-id="06f2e-185">**Code de valeur de la vérification de la carte (CVV) :** 737</span><span class="sxs-lookup"><span data-stu-id="06f2e-185">**Card verification value (CVV) code:** 737</span></span>

> [!IMPORTANT]
> <span data-ttu-id="06f2e-186">En aucun cas vous ne devez tenter d’utiliser des informations de carte de crédit réelle sur le site de test.</span><span class="sxs-lookup"><span data-stu-id="06f2e-186">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

## <a name="next-steps"></a><span data-ttu-id="06f2e-187">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="06f2e-187">Next steps</span></span>

<span data-ttu-id="06f2e-188">Une fois les étapes de mise en service et de configuration terminées, vous pouvez commencer à évaluer votre environnement d’évaluation.</span><span class="sxs-lookup"><span data-stu-id="06f2e-188">After the provisioning and configuration steps are completed, you can start to use your evaluation environment.</span></span> <span data-ttu-id="06f2e-189">Utilisez l’URL du générateur de site Commerce pour accéder à l’expérience de création.</span><span class="sxs-lookup"><span data-stu-id="06f2e-189">Use the Commerce site builder URL to go to the authoring experience.</span></span> <span data-ttu-id="06f2e-190">Utilisez l’URL du site Commerce pour accéder à l’expérience du site du client de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="06f2e-190">Use the Commerce site URL to go to the retail customer site experience.</span></span>

<span data-ttu-id="06f2e-191">Pour configurer des fonctionnalités facultatives de votre environnement d’évaluation Commerce, consultez [Configurer les fonctionnalités facultatives d’un environnement d’évaluation Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="06f2e-191">To configure optional features for your Commerce evaluation environment, see [Configure optional features for a Commerce evaluation environment](cpe-optional-features.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="06f2e-192">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="06f2e-192">Additional resources</span></span>

[<span data-ttu-id="06f2e-193">Vue d’ensemble d’un environnement d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="06f2e-193">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="06f2e-194">Mettre en service un environnement d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="06f2e-194">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="06f2e-195">Configurer des fonctionnalités facultatives pour un environnement d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="06f2e-195">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="06f2e-196">Configurer le BOPIS dans un environnement d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="06f2e-196">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="06f2e-197">FAQ des environnements d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="06f2e-197">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="06f2e-198">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="06f2e-198">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="06f2e-199">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="06f2e-199">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="06f2e-200">Portail Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="06f2e-200">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="06f2e-201">Site web Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="06f2e-201">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
