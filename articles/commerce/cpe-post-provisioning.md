---
title: Configurer un environnement d'évaluation Commerce
description: Cette rubrique explique comment configurer des un environnement d'aperçu Microsoft Dynamics 365 Commerce après sa mise en service.
author: psimolin
manager: annbe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f19d03f3f2f5a9f6f7ba08b682277e4e3b764d10
ms.sourcegitcommit: 610d5c3efadbaf11752b46f24680af619bcd70a6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2019
ms.locfileid: "2906137"
---
# <a name="configure-a-commerce-preview-environment"></a><span data-ttu-id="58b53-103">Configurer un environnement d'évaluation Commerce</span><span class="sxs-lookup"><span data-stu-id="58b53-103">Configure a Commerce preview environment</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="58b53-104">Cette rubrique explique comment configurer des un environnement d'aperçu Microsoft Dynamics 365 Commerce après sa mise en service.</span><span class="sxs-lookup"><span data-stu-id="58b53-104">This topic explains how to configure a Microsoft Dynamics 365 Commerce preview environment after it's provisioned.</span></span>

## <a name="overview"></a><span data-ttu-id="58b53-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="58b53-105">Overview</span></span>

<span data-ttu-id="58b53-106">Effectuez les procédures de cette rubrique uniquement une fois que votre environnement d'aperçu Commerce a été mis en service.</span><span class="sxs-lookup"><span data-stu-id="58b53-106">Complete the procedures in this topic only after your Commerce preview environment has been provisioned.</span></span> <span data-ttu-id="58b53-107">Pour plus d'informations sur la mise en service de votre environnement d'aperçu Commerce, consultez [Mise en service d'un environnement d'aperçu Commerce](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="58b53-107">For information about how to provision your Commerce preview environment, see [Provision a Commerce preview environment](provisioning-guide.md).</span></span>

<span data-ttu-id="58b53-108">Une fois que votre environnement d'aperçu Commerce a été mis en service de bout en bout, des étapes de configuration post-mise en service supplémentaires doivent être effectuées avant que vous puissiez commencer à évaluer l'environnement.</span><span class="sxs-lookup"><span data-stu-id="58b53-108">After your Commerce preview environment has been provisioned end to end, additional post-provisioning configuration steps must be completed before you can start to evaluate the environment.</span></span> <span data-ttu-id="58b53-109">Pour terminer ces étapes, vous devez utiliser Microsoft Dynamics Lifecycle Services (LCS), Dynamics 365 Commerce et Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="58b53-109">To complete these steps, you must use Microsoft Dynamics Lifecycle Services (LCS), Dynamics 365 Commerce, and Dynamics 365 Retail.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="58b53-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="58b53-110">Before you start</span></span>

1. <span data-ttu-id="58b53-111">Connectez-vous au [portail LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="58b53-111">Sign in to the [LCS portal](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="58b53-112">Accédez à votre projet.</span><span class="sxs-lookup"><span data-stu-id="58b53-112">Go to your project.</span></span>
1. <span data-ttu-id="58b53-113">Sur le menu principal, sélectionnez **Environnements hébergés dans le cloud**.</span><span class="sxs-lookup"><span data-stu-id="58b53-113">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="58b53-114">Sélectionnez votre environnement dans la liste.</span><span class="sxs-lookup"><span data-stu-id="58b53-114">Select your environment in the list.</span></span>
1. <span data-ttu-id="58b53-115">Dans les informations de l'environnement à droite, cliquez sur **Détails complets**.</span><span class="sxs-lookup"><span data-stu-id="58b53-115">In the environment information on the right, select **Full details**.</span></span>
1. <span data-ttu-id="58b53-116">Cliquez sur **Connexion** pour ouvrir un menu, puis sur **Se connecter à l'environnement**.</span><span class="sxs-lookup"><span data-stu-id="58b53-116">Select **Login** to open a menu, and then select **Log on to environment**.</span></span>
1. <span data-ttu-id="58b53-117">Assurez-vous que l'entité juridique **USRT** est sélectionnée dans l'angle supérieur droit.</span><span class="sxs-lookup"><span data-stu-id="58b53-117">Make sure that the **USRT** legal entity is selected in the upper-right corner.</span></span>

## <a name="configure-the-point-of-sale-in-lcs"></a><span data-ttu-id="58b53-118">Configurer le point de vente dans LCS</span><span class="sxs-lookup"><span data-stu-id="58b53-118">Configure the point of sale in LCS</span></span>

### <a name="associate-a-worker-with-your-identity"></a><span data-ttu-id="58b53-119">Associer un collaborateur à votre identité</span><span class="sxs-lookup"><span data-stu-id="58b53-119">Associate a worker with your identity</span></span>

<span data-ttu-id="58b53-120">Pour associer un collaborateur à votre identité dans LCS, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="58b53-120">To associate a worker with your identity in LCS, follow these steps.</span></span>

1. <span data-ttu-id="58b53-121">Utilisez le menu à gauche pour accéder à **Modules \> Vente au détail \> Employés \> Collaborateurs**.</span><span class="sxs-lookup"><span data-stu-id="58b53-121">Use the menu on the left to go to **Modules \> Retail \> Employees \> Workers**.</span></span>
1. <span data-ttu-id="58b53-122">Dans la liste, recherchez et sélectionnez l'enregistrement suivant : **000713 - Andrew Collette**.</span><span class="sxs-lookup"><span data-stu-id="58b53-122">In the list, find and select the following record: **000713 - Andrew Collette**.</span></span>
1. <span data-ttu-id="58b53-123">Dans le volet Actions, sélectionnez **Vente au détail**.</span><span class="sxs-lookup"><span data-stu-id="58b53-123">On the Action Pane, select **Retail**.</span></span>
1. <span data-ttu-id="58b53-124">Sélectionnez **Associer une identité existante**.</span><span class="sxs-lookup"><span data-stu-id="58b53-124">Select **Associate existing identity**.</span></span>
1. <span data-ttu-id="58b53-125">Dans le champ **E-mail** (à droite de **Rechercher à l'aide de l'e-mail**), entrez votre adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="58b53-125">In the **Email** field to the right of **Search using email**, enter your email address.</span></span>
1. <span data-ttu-id="58b53-126">Sélectionnez **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="58b53-126">Select **Search**.</span></span>
1. <span data-ttu-id="58b53-127">Sélectionnez l'enregistrement à votre nom.</span><span class="sxs-lookup"><span data-stu-id="58b53-127">Select the record that has your name.</span></span>
1. <span data-ttu-id="58b53-128">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="58b53-128">Select **OK**.</span></span>
1. <span data-ttu-id="58b53-129">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="58b53-129">Select **Save**.</span></span>

### <a name="activate-cloud-pos"></a><span data-ttu-id="58b53-130">Activer le PDV Cloud</span><span class="sxs-lookup"><span data-stu-id="58b53-130">Activate Cloud POS</span></span>

<span data-ttu-id="58b53-131">Pour activer Cloud POS dans LCS, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="58b53-131">To activate Cloud POS in LCS, follow these steps.</span></span>

1. <span data-ttu-id="58b53-132">Sur le menu principal, sélectionnez **Environnements hébergés dans le cloud**.</span><span class="sxs-lookup"><span data-stu-id="58b53-132">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="58b53-133">Sélectionnez votre environnement dans la liste.</span><span class="sxs-lookup"><span data-stu-id="58b53-133">Select your environment in the list.</span></span>
1. <span data-ttu-id="58b53-134">Dans les informations de l'environnement à droite, cliquez sur **Détails complets**.</span><span class="sxs-lookup"><span data-stu-id="58b53-134">In the environment information on the right, select **Full details**.</span></span>
1. <span data-ttu-id="58b53-135">Sélectionnez **Connexion** pour ouvrir un menu, puis sélectionnez **Se connecter à Cloud Point of Sale** pour ouvrir le point de vente (POS).</span><span class="sxs-lookup"><span data-stu-id="58b53-135">Select **Login** to open a menu, and then select **Log on to Cloud Point of Sale** to open the point of sale (POS).</span></span>
1. <span data-ttu-id="58b53-136">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="58b53-136">Select **Next**.</span></span>
1. <span data-ttu-id="58b53-137">Connectez-vous en utilisant votre compte Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="58b53-137">Sign in by using your Microsoft Azure Active Directory (Azure AD) account.</span></span>
1. <span data-ttu-id="58b53-138">Sous **Nom du magasin**, sélectionnez **Saint-Nazaire**.</span><span class="sxs-lookup"><span data-stu-id="58b53-138">Under **Store name**, select **San Francisco**.</span></span>
1. <span data-ttu-id="58b53-139">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="58b53-139">Select **Next**.</span></span>
1. <span data-ttu-id="58b53-140">Sous **Registre et périphérique**, sélectionnez **SAiNNAZ-1**.</span><span class="sxs-lookup"><span data-stu-id="58b53-140">Under **Register and device**, select **SANFRAN-1**.</span></span>
1. <span data-ttu-id="58b53-141">Sélectionnez **Activer**.</span><span class="sxs-lookup"><span data-stu-id="58b53-141">Select **Activate**.</span></span> <span data-ttu-id="58b53-142">Vous êtes déconnecté et dirigé vers la page de connexion au PDV.</span><span class="sxs-lookup"><span data-stu-id="58b53-142">You're signed out and taken to the POS sign-in page.</span></span>
1. <span data-ttu-id="58b53-143">Vous pouvez désormais vous connecter à l'expérience du PDV de cloud à l'aide de l'ID opérateur **000713** et le mot de passe **123**.</span><span class="sxs-lookup"><span data-stu-id="58b53-143">You can now sign in to the Cloud POS experience by using operator ID **000713** and password **123**.</span></span>

## <a name="set-up-your-site-in-commerce"></a><span data-ttu-id="58b53-144">Configurer votre site dans Commerce</span><span class="sxs-lookup"><span data-stu-id="58b53-144">Set up your site in Commerce</span></span>

<span data-ttu-id="58b53-145">Pour commencer à configurer votre site d'aperçu dans Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="58b53-145">To start to set up your preview site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="58b53-146">Connectez-vous à l'outil de gestion de site en utilisant l'URL que vous avez notée lorsque vous avez initialisé le commerce électronique lors de la mise en service (voir [Initialiser le commerce électronique](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="58b53-146">Sign in to the site management tool by using the URL that you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="58b53-147">Sélectionnez le site **Fabrikam** pour ouvrir la boîte de dialogue de paramétrage de site.</span><span class="sxs-lookup"><span data-stu-id="58b53-147">Select the **Fabrikam** site to open the site setup dialog box.</span></span>
1. <span data-ttu-id="58b53-148">Sélectionnez le domaine que vous avez entré lors de l'initialisation du commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="58b53-148">Select the domain that you entered when you initialized e-Commerce.</span></span>
1. <span data-ttu-id="58b53-149">Sélectionnez **Fabrikam a étendu le magasin en ligne** comme canal par défaut.</span><span class="sxs-lookup"><span data-stu-id="58b53-149">Select **Fabrikam extended online store** as the default channel.</span></span> <span data-ttu-id="58b53-150">(Vérifiez que vous sélectionnez le magasin en ligne **étendu**.)</span><span class="sxs-lookup"><span data-stu-id="58b53-150">(Make sure that you select the **extended** online store.)</span></span>
1. <span data-ttu-id="58b53-151">Sélectionnez **fr-fr** comme langue par défaut.</span><span class="sxs-lookup"><span data-stu-id="58b53-151">Select **en-us** as the default language.</span></span>
1. <span data-ttu-id="58b53-152">Laissez la valeur du champ **Chemin d'accès** telle quelle.</span><span class="sxs-lookup"><span data-stu-id="58b53-152">Leave the value of the **Path** field as it is.</span></span>
1. <span data-ttu-id="58b53-153">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="58b53-153">Select **OK**.</span></span> <span data-ttu-id="58b53-154">La liste des pages du site apparaît.</span><span class="sxs-lookup"><span data-stu-id="58b53-154">The list of pages on the site appears.</span></span>

## <a name="enable-jobs-in-retail"></a><span data-ttu-id="58b53-155">Activer les emplois dans la vente au détail</span><span class="sxs-lookup"><span data-stu-id="58b53-155">Enable jobs in Retail</span></span>

<span data-ttu-id="58b53-156">Pour activer les tâches dans la vente au détail, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="58b53-156">To enable jobs in Retail, follow these steps.</span></span>

1. <span data-ttu-id="58b53-157">Connectez-vous à l'environnement (Siège social).</span><span class="sxs-lookup"><span data-stu-id="58b53-157">Sign in to the environment (HQ).</span></span>
1. <span data-ttu-id="58b53-158">Utilisez le menu à gauche pour accéder à **Vente au détail \> Recherches et états \> Traitements par lots**.</span><span class="sxs-lookup"><span data-stu-id="58b53-158">Use the menu on the left to go to **Retail \> Inquiries and reports \> Batch jobs**.</span></span>

    <span data-ttu-id="58b53-159">Les étapes restantes de cette procédure doivent être exécutées pour chacun des travaux suivants :</span><span class="sxs-lookup"><span data-stu-id="58b53-159">The remaining steps of this procedure must be completed for each of the following jobs:</span></span>

    * <span data-ttu-id="58b53-160">Traiter la notification par e-mail des commandes de vente au détail</span><span class="sxs-lookup"><span data-stu-id="58b53-160">Process retail order email notification</span></span>
    * <span data-ttu-id="58b53-161">Disponibilité du produit</span><span class="sxs-lookup"><span data-stu-id="58b53-161">Product availability</span></span>
    * <span data-ttu-id="58b53-162">P-0001</span><span class="sxs-lookup"><span data-stu-id="58b53-162">P-0001</span></span>
    * <span data-ttu-id="58b53-163">Synchroniser la tâche des commandes</span><span class="sxs-lookup"><span data-stu-id="58b53-163">Synchronize orders job</span></span>

1. <span data-ttu-id="58b53-164">Utilisez le filtre rapide pour rechercher la tâche selon son nom.</span><span class="sxs-lookup"><span data-stu-id="58b53-164">Use the Quick Filter to search for the job by name.</span></span>
1. <span data-ttu-id="58b53-165">Si le statut de la tâche est **Retenir**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="58b53-165">If the status of the job is **Withhold**, follow these steps:</span></span>

    1. <span data-ttu-id="58b53-166">Sélectionner l'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="58b53-166">Select the record.</span></span>
    1. <span data-ttu-id="58b53-167">Dans le volet Actions, sous **Traitement par lots**, sélectionnez **Modifier le statut**.</span><span class="sxs-lookup"><span data-stu-id="58b53-167">On the Action Pane, on **Batch job** tab, select **Change status**.</span></span>
    1. <span data-ttu-id="58b53-168">Sélectionnez **En attente**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="58b53-168">Select **Waiting**, and then select **OK**.</span></span>

### <a name="run-full-data-synchronization-in-retail"></a><span data-ttu-id="58b53-169">Exécutez la synchronisation complète des données dans Retail</span><span class="sxs-lookup"><span data-stu-id="58b53-169">Run full data synchronization in Retail</span></span>

<span data-ttu-id="58b53-170">Pour exécuter la synchronisation complète des données dans Retail, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="58b53-170">To run full data synchronization in Retail, follow these steps.</span></span>

1. <span data-ttu-id="58b53-171">Utilisez le menu à gauche pour accéder à **Modules \> Vente au détail \> Paramétrage du Siège \> Retail Planification \> Base de données du canal**.</span><span class="sxs-lookup"><span data-stu-id="58b53-171">Use the menu on the left to go to **Modules \> Retail \> Headquarters setup \> Retail scheduler \> Channel database**.</span></span>
1. <span data-ttu-id="58b53-172">Dans la liste de gauche, le canal **Par défaut** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="58b53-172">In the list on the left, the **Default** channel is selected.</span></span> <span data-ttu-id="58b53-173">Sélectionnez l'autre canal disponible.</span><span class="sxs-lookup"><span data-stu-id="58b53-173">Select the other available channel.</span></span> <span data-ttu-id="58b53-174">Ce canal est nommé **scXXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="58b53-174">This channel is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="58b53-175">Sur le volet Action, sélectionnez **Synchronisation de données complète**.</span><span class="sxs-lookup"><span data-stu-id="58b53-175">On the Action Pane, select **Full data sync**.</span></span>
1. <span data-ttu-id="58b53-176">Entrez **9999** comme programme de distribution.</span><span class="sxs-lookup"><span data-stu-id="58b53-176">Enter **9999** as the distribution schedule.</span></span>
1. <span data-ttu-id="58b53-177">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="58b53-177">Select **OK**.</span></span>
1. <span data-ttu-id="58b53-178">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="58b53-178">Select **OK**.</span></span>

### <a name="test-credit-card-information-to-do-test-purchases"></a><span data-ttu-id="58b53-179">Tester les informations de carte de crédit pour effectuer des tests d'achats</span><span class="sxs-lookup"><span data-stu-id="58b53-179">Test credit card information to do test purchases</span></span>

<span data-ttu-id="58b53-180">Pour effectuer des tests de transactions sur le site, vous pouvez utiliser les informations de carte de crédit de test suivantes :</span><span class="sxs-lookup"><span data-stu-id="58b53-180">To perform test transactions on the site, you can use the following test credit card information:</span></span>

- <span data-ttu-id="58b53-181">**Numéro de carte :** 4111-1111-1111-1111</span><span class="sxs-lookup"><span data-stu-id="58b53-181">**Card number:** 4111-1111-1111-1111</span></span>
- <span data-ttu-id="58b53-182">**Date d'expiration :** 10/20</span><span class="sxs-lookup"><span data-stu-id="58b53-182">**Expiration date:** 10/20</span></span>
- <span data-ttu-id="58b53-183">**Code de valeur de la vérification de la carte (CVV) :** 737</span><span class="sxs-lookup"><span data-stu-id="58b53-183">**Card verification value (CVV) code:** 737</span></span>

> [!IMPORTANT]
> <span data-ttu-id="58b53-184">En aucun cas vous ne devez tenter d'utiliser des informations de carte de crédit réelle sur le site de test.</span><span class="sxs-lookup"><span data-stu-id="58b53-184">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

## <a name="next-steps"></a><span data-ttu-id="58b53-185">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="58b53-185">Next steps</span></span>

<span data-ttu-id="58b53-186">Une fois les étapes de mise en service et de configuration terminées, vous êtes prêt à évaluer votre environnement d'aperçu.</span><span class="sxs-lookup"><span data-stu-id="58b53-186">After the provisioning and configuration steps are completed, you're ready to evaluate your preview environment.</span></span> <span data-ttu-id="58b53-187">Utilisez l'URL de l'outil de gestion du site Commerce pour accéder à l'expérience de création.</span><span class="sxs-lookup"><span data-stu-id="58b53-187">Use the URL of the Commerce site management tool to go to the authoring experience.</span></span> <span data-ttu-id="58b53-188">Utilisez l'URL du site Commerce pour accéder à l'expérience du site client de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="58b53-188">Use the URL of the Commerce site to go to the retail customer site experience.</span></span>

<span data-ttu-id="58b53-189">Pour configurer des fonctionnalités facultatives de votre environnement d'aperçu Commerce, consultez [Configurer les fonctionnalités facultatives d'un environnement d'aperçu Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="58b53-189">To configure optional features for your Commerce preview environment, see [Configure optional features for a Commerce preview environment](cpe-optional-features.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="58b53-190">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="58b53-190">Additional resources</span></span>

[<span data-ttu-id="58b53-191">Vue d'ensemble d'un environnement d'évaluation Commerce</span><span class="sxs-lookup"><span data-stu-id="58b53-191">Commerce preview environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="58b53-192">Mettre en service un environnement d'évaluation Commerce</span><span class="sxs-lookup"><span data-stu-id="58b53-192">Provision a Commerce preview environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="58b53-193">Configurer des fonctionnalités facultatives pour un environnement d'évaluation Commerce</span><span class="sxs-lookup"><span data-stu-id="58b53-193">Configure optional features for a Commerce preview environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="58b53-194">FAQ relative à l'environnement d'évaluation Commerce</span><span class="sxs-lookup"><span data-stu-id="58b53-194">Commerce preview environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="58b53-195">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="58b53-195">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="58b53-196">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="58b53-196">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="58b53-197">Portail Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="58b53-197">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="58b53-198">Site web Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="58b53-198">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)

[<span data-ttu-id="58b53-199">Ressources d'aide pour Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="58b53-199">Help resources for Dynamics 365 Retail</span></span>](../retail/index.md)
