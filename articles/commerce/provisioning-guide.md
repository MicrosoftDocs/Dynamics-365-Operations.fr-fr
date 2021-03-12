---
title: Mettre en service un environnement d'évaluation Dynamics 365 Commerce
description: Cette rubrique explique comment mettre en service un environnement d'évaluation Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 12/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8cda79a6be1aca7ad3826b9409e110524e6560e3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969899"
---
# <a name="provision-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="124b6-103">Mettre en service un environnement d'évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="124b6-103">Provision a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="124b6-104">Cette rubrique explique comment mettre en service un environnement d'évaluation Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="124b6-104">This topic explains how to provision a Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

<span data-ttu-id="124b6-105">Avant de commencer, nous vous conseillons de parcourir rapidement cette rubrique pour avoir une idée de ce que le processus nécessite.</span><span class="sxs-lookup"><span data-stu-id="124b6-105">Before you begin, we recommend that you take a quick scan through this topic to get an idea of what the process requires.</span></span>

> [!NOTE]
> <span data-ttu-id="124b6-106">Les environnements d'évaluation de Commerce ne sont pas en disponibilité générale et sont accordés aux partenaires et aux clients sur demande.</span><span class="sxs-lookup"><span data-stu-id="124b6-106">Commerce evaluation environments aren't generally available, and are granted to partners and customers on a per-request basis.</span></span> <span data-ttu-id="124b6-107">Pour plus d'informations, contactez votre partenaire Microsoft.</span><span class="sxs-lookup"><span data-stu-id="124b6-107">For more information, reach out to your Microsoft partner contact.</span></span>

## <a name="overview"></a><span data-ttu-id="124b6-108">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="124b6-108">Overview</span></span>

<span data-ttu-id="124b6-109">Pour configurer correctement votre environnement d'évaluation Commerce, vous devez créer un projet qui a un nom et un type de produit spécifiques.</span><span class="sxs-lookup"><span data-stu-id="124b6-109">To successfully provision a Commerce evaluation environment, you must create a project that has a specific product name and type.</span></span> <span data-ttu-id="124b6-110">L'environnement et Commerce Scale Unit (CSU) ont aussi des paramètres spécifiques que vous devez utiliser si vous envisagez de mettre en service le commerce électronique ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="124b6-110">The environment and Commerce Scale Unit (CSU) also have some specific parameters that you must use when you expect to provision e-Commerce later.</span></span> <span data-ttu-id="124b6-111">Les instructions de cette rubrique décrivent toutes les étapes requises pour terminer la mise en service et indiquent également les paramètres à utiliser.</span><span class="sxs-lookup"><span data-stu-id="124b6-111">The instructions in this topic describe all the steps that are required to complete provisioning and the parameters that you must use.</span></span>

<span data-ttu-id="124b6-112">Après une mise en service réussie de votre environnement d'évaluation Commerce, des étapes postérieures à la mise en service sont à effectuer pour l'utiliser.</span><span class="sxs-lookup"><span data-stu-id="124b6-112">After you successfully provision your Commerce evaluation environment, you must complete a few post-provisioning steps to prepare it for use.</span></span> <span data-ttu-id="124b6-113">Certaines étapes sont facultatives, selon les aspects du système que vous souhaitez évaluer.</span><span class="sxs-lookup"><span data-stu-id="124b6-113">Some steps are optional, depending on the aspects of the system that you want to evaluate.</span></span> <span data-ttu-id="124b6-114">Vous pouvez toujours effectuer les étapes facultatives ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="124b6-114">You can always complete the optional steps later.</span></span>

<span data-ttu-id="124b6-115">Pour plus d'informations sur la configuration de votre environnement d'évaluation Commerce après l'avoir mis en service, consultez [Configurer un environnement d'évaluation Commerce](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="124b6-115">For information about how to configure your Commerce evaluation environment after you provision it, see [Configure a Commerce evaluation environment](cpe-post-provisioning.md).</span></span> <span data-ttu-id="124b6-116">Pour plus d'informations sur la configuration des fonctionnalités facultatives de votre environnement d'évaluation Commerce, consultez [Configurer les fonctionnalités facultatives d'un environnement d'évaluation Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="124b6-116">For information about how to configure optional features for your Commerce evaluation environment, see [Configure optional features for a Commerce evaluation environment](cpe-optional-features.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="124b6-117">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="124b6-117">Prerequisites</span></span>

<span data-ttu-id="124b6-118">Les conditions préalables suivantes doivent être en place avant de pouvoir mettre en service votre environnement d'évaluation Commerce :</span><span class="sxs-lookup"><span data-stu-id="124b6-118">The following prerequisites must be in place before you can provision your Commerce evaluation environment:</span></span>

- <span data-ttu-id="124b6-119">Vous avez été intégré au programme d'évaluation et vous avez obtenu la capacité d'un environnement d'évaluation.</span><span class="sxs-lookup"><span data-stu-id="124b6-119">You have been onboarded into the evaluation program and granted capacity for an evaluation environment.</span></span>
- <span data-ttu-id="124b6-120">Vous avez accès au Portail Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="124b6-120">You have access to the Microsoft Dynamics Lifecycle Services (LCS) portal.</span></span>
- <span data-ttu-id="124b6-121">Vous êtes un client ou un partenaire Microsoft Dynamics 365 existant et savez créer un projet Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="124b6-121">You are an existing Microsoft Dynamics 365 partner or customer and are able to create a Dynamics 365 Commerce project.</span></span>
- <span data-ttu-id="124b6-122">Vous disposez d'un accès administrateur à votre abonnement Microsoft Azure, ou vous êtes en contact avec un administrateur d'abonnement qui peut vous aider si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="124b6-122">You have administrator access to your Microsoft Azure subscription, or you're in contact with a subscription administrator who can assist you if required.</span></span>
- <span data-ttu-id="124b6-123">Vous avez votre ID client Azure Active Directory (Azure AD) disponible.</span><span class="sxs-lookup"><span data-stu-id="124b6-123">You have your Azure Active Directory (Azure AD) tenant ID available.</span></span>
- <span data-ttu-id="124b6-124">Vous avez créé un groupe de sécurité Azure AD à utiliser comme groupe d'administrateurs système de commerce électronique et son ID est disponible.</span><span class="sxs-lookup"><span data-stu-id="124b6-124">You've created an Azure AD security group that can be used as an e-Commerce system admin group, and you have its ID available.</span></span>
- <span data-ttu-id="124b6-125">Vous avez créé un groupe de sécurité Azure AD à utiliser comme groupe de modération des classements et évaluations et son ID est disponible.</span><span class="sxs-lookup"><span data-stu-id="124b6-125">You've created an Azure AD security group that can be used as a Ratings and Reviews moderator group, and you have its ID available.</span></span> <span data-ttu-id="124b6-126">(Ce groupe de sécurité peut être le même que le groupe d'administration système de commerce électronique.)</span><span class="sxs-lookup"><span data-stu-id="124b6-126">(This security group can be the same as the e-Commerce system admin group.)</span></span>

<span data-ttu-id="124b6-127">Notez que cette liste n'est pas exhaustive.</span><span class="sxs-lookup"><span data-stu-id="124b6-127">Note that this list isn't exhaustive.</span></span> <span data-ttu-id="124b6-128">Si vous rencontrez des problèmes, contactez votre partenaire Microsoft pour obtenir de l'aide.</span><span class="sxs-lookup"><span data-stu-id="124b6-128">If you experience any issues, reach out to your Microsoft partner contact for assistance.</span></span>

## <a name="provision-your-commerce-evaluation-environment"></a><span data-ttu-id="124b6-129">Mise en service de votre environnement d'évaluation Commerce</span><span class="sxs-lookup"><span data-stu-id="124b6-129">Provision your Commerce evaluation environment</span></span>

<span data-ttu-id="124b6-130">Ces procédures expliquent comment mettre en service un environnement d'évaluation Commerce.</span><span class="sxs-lookup"><span data-stu-id="124b6-130">These procedures explain how to provision a Commerce evaluation environment.</span></span> <span data-ttu-id="124b6-131">Une fois que vous les aurez terminées avec succès, l'environnement d'évaluation de Commerce sera prêt pour la configuration.</span><span class="sxs-lookup"><span data-stu-id="124b6-131">After you successfully complete them, the Commerce evaluation environment will be ready for configuration.</span></span> <span data-ttu-id="124b6-132">Toutes les activités décrites ici ont lieu dans le portail LCS.</span><span class="sxs-lookup"><span data-stu-id="124b6-132">All the activities that are described here occur in the LCS portal.</span></span>

### <a name="create-a-new-project"></a><span data-ttu-id="124b6-133">Créer un nouveau projet</span><span class="sxs-lookup"><span data-stu-id="124b6-133">Create a new project</span></span>

<span data-ttu-id="124b6-134">Pour créer un projet dans LCS, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="124b6-134">To create a new project in LCS, follow these steps.</span></span>

1. <span data-ttu-id="124b6-135">Sur la page d'accueil LCS, sélectionnez le signe plus (**+**) pour créer un projet.</span><span class="sxs-lookup"><span data-stu-id="124b6-135">On the LCS home page, select the plus sign (**+**) to create a project.</span></span>
1. <span data-ttu-id="124b6-136">Dans le volet droit, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="124b6-136">In the right pane, follow one of these steps:</span></span>

    - <span data-ttu-id="124b6-137">Si vous êtes un partenaire, cliquez sur **Migrer, créer des solutions et découvrir**.</span><span class="sxs-lookup"><span data-stu-id="124b6-137">If you're a partner, select **Migrate, create solutions, and learn**.</span></span>
    - <span data-ttu-id="124b6-138">Si vous êtes un client, cliquez sur **Préventes potentielles**.</span><span class="sxs-lookup"><span data-stu-id="124b6-138">If you're a customer, select **Prospective presales**.</span></span>

1. <span data-ttu-id="124b6-139">Entrer une nom, une description et un secteur d'activité.</span><span class="sxs-lookup"><span data-stu-id="124b6-139">Enter a name, description, and industry.</span></span>
1. <span data-ttu-id="124b6-140">Dans le champ **Nom du produit**, cliquez sur **Dynamics 365 Commerce**.</span><span class="sxs-lookup"><span data-stu-id="124b6-140">In the **Product name** field, select **Dynamics 365 Commerce**.</span></span>
1. <span data-ttu-id="124b6-141">Dans le champ **Version du produit**, cliquez sur **Dynamics 365 Commerce**.</span><span class="sxs-lookup"><span data-stu-id="124b6-141">In the **Product version** field, select **Dynamics 365 Commerce**.</span></span>
1. <span data-ttu-id="124b6-142">Dans le champ **Méthodologie**, sélectionnez **Méthodologie de mise en œuvre de Dynamics Retail**.</span><span class="sxs-lookup"><span data-stu-id="124b6-142">In the **Methodology** field, select **Dynamics Retail implementation methodology**.</span></span>
1. <span data-ttu-id="124b6-143">Facultatif : Vous pouvez importer les rôles et les utilisateurs d'un projet existant.</span><span class="sxs-lookup"><span data-stu-id="124b6-143">Optional: You can import roles and users from an existing project.</span></span>
1. <span data-ttu-id="124b6-144">Sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="124b6-144">Select **Create**.</span></span> <span data-ttu-id="124b6-145">La vue du projet s'affiche.</span><span class="sxs-lookup"><span data-stu-id="124b6-145">The project view appears.</span></span>

### <a name="add-the-azure-connector"></a><span data-ttu-id="124b6-146">Ajouter le connecteur Azure</span><span class="sxs-lookup"><span data-stu-id="124b6-146">Add the Azure Connector</span></span>

<span data-ttu-id="124b6-147">Pour ajouter le connecteur Azure à votre projet LCS, suivez les étapes de [Terminer l'intégration d'Azure Resource Manager (ARM)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/deployment/arm-onboarding).</span><span class="sxs-lookup"><span data-stu-id="124b6-147">To add the Azure Connector to your LCS project, follow the steps in [Complete the Azure Resource Manager (ARM) onboarding process](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/deployment/arm-onboarding).</span></span>

### <a name="deploy-the-environment"></a><span data-ttu-id="124b6-148">Déploiement de l'environnement</span><span class="sxs-lookup"><span data-stu-id="124b6-148">Deploy the environment</span></span>

<span data-ttu-id="124b6-149">Pour déployer l'environnement, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="124b6-149">To deploy the environment, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="124b6-150">Vous n'aurez peut-être pas à effectuer les étapes 6, 7 et/ou 8, car les pages comportant une seule option sont ignorées.</span><span class="sxs-lookup"><span data-stu-id="124b6-150">You might not have to complete steps 6, 7, and/or 8, because pages that have a single option are skipped.</span></span> <span data-ttu-id="124b6-151">Si vous affichez la vue **Paramètres environnementaux**, confirmez que le texte **Dynamics 365 Commerce - Démonstration (10.0.* x* avec mise à jour de la plateforme *xx*)\*\* apparaît directement au-dessus du champ **Nom de l'environnement**.</span><span class="sxs-lookup"><span data-stu-id="124b6-151">When you're in the **Environment parameters** view, confirm that the text **Dynamics 365 Commerce - Demo (10.0.* x* with Platform update *xx*)\*\* appears directly above the **Environment name** field.</span></span> <span data-ttu-id="124b6-152">Pour plus de détails, voir l'illustration qui apparaît après l'étape 8.</span><span class="sxs-lookup"><span data-stu-id="124b6-152">For details, see the illustration that appears after step 8.</span></span>

1. <span data-ttu-id="124b6-153">Sur le menu principal, sélectionnez **Environnements hébergés dans le cloud**.</span><span class="sxs-lookup"><span data-stu-id="124b6-153">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="124b6-154">Cliquez sur **Ajouter** pour ajouter un environnement.</span><span class="sxs-lookup"><span data-stu-id="124b6-154">Select **Add** to add an environment.</span></span>
1. <span data-ttu-id="124b6-155">Dans le champ **Version de l'application**, sélectionnez la version la plus récente.</span><span class="sxs-lookup"><span data-stu-id="124b6-155">In the **Application version** field, select the most current version.</span></span> <span data-ttu-id="124b6-156">Si vous devez absolument sélectionner une version d'application autre que la version la plus récente, ne sélectionnez pas de version antérieure à la version **10.0.14**.</span><span class="sxs-lookup"><span data-stu-id="124b6-156">If you have a specific need to select an application version other than the most current version, do not select a version prior to **10.0.14**.</span></span>
1. <span data-ttu-id="124b6-157">Dans le champ **Version de la plateforme**, utilisez la version de la plateforme automatiquement choisie pour la version de l'application sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="124b6-157">In the **Platform version** field, use the platform version that is automatically chosen for the application version you selected.</span></span> 

    ![Sélection des versions de l'application et de la plateforme](./media/project1.png)

1. <span data-ttu-id="124b6-159">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="124b6-159">Select **Next**.</span></span>
1. <span data-ttu-id="124b6-160">Sélectionner **Démonstration** comme topologie de l'environnement.</span><span class="sxs-lookup"><span data-stu-id="124b6-160">Select **Demo** as the environment topology.</span></span>

    ![Sélection de la topologie de l'environment 1](./media/project2.png)

1. <span data-ttu-id="124b6-162">Sur la page **Déployer l'environnement**, entrez un nom d'environnement.</span><span class="sxs-lookup"><span data-stu-id="124b6-162">On the **Deploy environment** page, enter an environment name.</span></span> <span data-ttu-id="124b6-163">Laissez les paramètres avancés inchangés.</span><span class="sxs-lookup"><span data-stu-id="124b6-163">Leave the advanced settings as they are.</span></span>

    ![Page Déployer l'environnement](./media/project4.png)

1. <span data-ttu-id="124b6-165">Ajustez la taille de la machine virtuelle selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="124b6-165">Adjust the VM size as required.</span></span> <span data-ttu-id="124b6-166">(Nous recommandons l'unité de gestion de stock de machine virtuelle \[SKU\] **D13 v2**.)</span><span class="sxs-lookup"><span data-stu-id="124b6-166">(We recommend VM stock keeping unit \[SKU\] **D13 v2**.)</span></span>
1. <span data-ttu-id="124b6-167">Passez en revue les conditions de prix et de licence, puis cochez la case pour indiquer que vous les acceptez.</span><span class="sxs-lookup"><span data-stu-id="124b6-167">Review the pricing and licensing terms, and then select the check box to indicate that you agree to them.</span></span>
1. <span data-ttu-id="124b6-168">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="124b6-168">Select **Next**.</span></span>
1. <span data-ttu-id="124b6-169">Dans la page de confirmation du déploiement, après avoir vérifié les détails sont corrects, cliquez sur **Déployer**.</span><span class="sxs-lookup"><span data-stu-id="124b6-169">On the deployment confirmation page, verify that the details are correct, and then select **Deploy**.</span></span> <span data-ttu-id="124b6-170">Vous revenez à la vue **Environnements hébergés sur le cloud** et votre environnement doit apparaître dans la liste.</span><span class="sxs-lookup"><span data-stu-id="124b6-170">You're returned to the **Cloud-hosted environments** view, and your environment should appear in the list.</span></span>

    <span data-ttu-id="124b6-171">Votre environnement demandé s'affiche comme mis en file d'attente, puis en cours de déploiement.</span><span class="sxs-lookup"><span data-stu-id="124b6-171">Your requested environment will appear as queued and then deploying.</span></span> <span data-ttu-id="124b6-172">Les workflows d'environnement prendront un certain temps à se terminer.</span><span class="sxs-lookup"><span data-stu-id="124b6-172">The environment workflows will take some time to be completed.</span></span> <span data-ttu-id="124b6-173">Par conséquent, revenez après environ six à neuf heures.</span><span class="sxs-lookup"><span data-stu-id="124b6-173">Therefore, check back after approximately six to nine hours.</span></span>

1. <span data-ttu-id="124b6-174">Avant de continuer, vérifiez que le statut de votre environnement est **Déployé**.</span><span class="sxs-lookup"><span data-stu-id="124b6-174">Before you continue, make sure that the status of your environment is **Deployed**.</span></span>

### <a name="initialize-the-commerce-scale-unit-cloud"></a><span data-ttu-id="124b6-175">Initialiser Commerce Scale Unit (cloud)</span><span class="sxs-lookup"><span data-stu-id="124b6-175">Initialize the Commerce Scale Unit (cloud)</span></span>

<span data-ttu-id="124b6-176">Pour initialiser le CSU, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="124b6-176">To initialize the CSU, follow these steps.</span></span>

1. <span data-ttu-id="124b6-177">Dans la vue **Environnements hébergés dans le cloud**, sélectionnez votre environnement dans la liste.</span><span class="sxs-lookup"><span data-stu-id="124b6-177">In the **Cloud-hosted environments** view, select your environment in the list.</span></span>
1. <span data-ttu-id="124b6-178">Dans les informations de l'environnement à droite, cliquez sur **Détails complets**.</span><span class="sxs-lookup"><span data-stu-id="124b6-178">In the environment view on the right, select **Full details**.</span></span> <span data-ttu-id="124b6-179">La vue des détails d'environnement s'affiche.</span><span class="sxs-lookup"><span data-stu-id="124b6-179">The environment details view appears.</span></span>
1. <span data-ttu-id="124b6-180">Sous **Fonctions d'environnement**, cliquez sur **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="124b6-180">Under **Environment features**, select **Manage**.</span></span>
1. <span data-ttu-id="124b6-181">Dans l'onglet **Commerce**, cliquez sur **Initialiser**.</span><span class="sxs-lookup"><span data-stu-id="124b6-181">On the **Commerce** tab, select **Initialize**.</span></span> <span data-ttu-id="124b6-182">La vue des paramètres d'initialisation de CSU s'affiche.</span><span class="sxs-lookup"><span data-stu-id="124b6-182">The CSU initialization parameters view appears.</span></span>
1. <span data-ttu-id="124b6-183">Dans le champ **Région**, sélectionnez la région identique ou proche de la région dans laquelle vous avez déployé l'environnement.</span><span class="sxs-lookup"><span data-stu-id="124b6-183">In the **Region** field, select the region that is the same or close to the region that you deployed the environment to.</span></span>
1. <span data-ttu-id="124b6-184">Laissez le champ **Version** tel qu'il est.</span><span class="sxs-lookup"><span data-stu-id="124b6-184">Leave the **Version** field as it is.</span></span>
1. <span data-ttu-id="124b6-185">Sélectionnez **Initialiser**.</span><span class="sxs-lookup"><span data-stu-id="124b6-185">Select **Initialize**.</span></span>
1. <span data-ttu-id="124b6-186">Dans la page de confirmation du déploiement, après avoir vérifié les détails sont corrects, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="124b6-186">On the deployment confirmation page, verify that the details are correct, and then select **Yes**.</span></span> <span data-ttu-id="124b6-187">La vue **Gestion de commerce** s'affiche à nouveau et l'onglet **Commerce** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="124b6-187">The **Commerce management** view displays again, where the **Commerce** tab is selected.</span></span> <span data-ttu-id="124b6-188">Votre CSU a été mis en file d'attente pour la mise en service.</span><span class="sxs-lookup"><span data-stu-id="124b6-188">Your CSU has been queued for provisioning.</span></span>
1. <span data-ttu-id="124b6-189">Avant de continuer, vérifiez que le statut de votre CSU est **Réussite**.</span><span class="sxs-lookup"><span data-stu-id="124b6-189">Before you continue, make sure that the status of your CSU is **Success**.</span></span> <span data-ttu-id="124b6-190">L'initialisation prend environ deux à cinq heures.</span><span class="sxs-lookup"><span data-stu-id="124b6-190">Initialization takes approximately two to five hours.</span></span>

<span data-ttu-id="124b6-191">Si vous ne trouvez pas le lien **Gérer** dans la vue des détails de l'environnement, contactez votre contact Microsoft pour obtenir de l'aide.</span><span class="sxs-lookup"><span data-stu-id="124b6-191">If you can't find the **Manage** link in the environment details view, reach out to your Microsoft contact for assistance.</span></span>

<span data-ttu-id="124b6-192">Vous pouvez recevoir le message d’erreur suivant pendant le processus de déploiement :</span><span class="sxs-lookup"><span data-stu-id="124b6-192">During the deployment process, you might receive the following error message:</span></span>

> <span data-ttu-id="124b6-193">Les environnements d'évaluation (démo/test) doivent enregistrer l'application de connecteur d'unité de mise à l'échelle \<application ID\> dans le siège.</span><span class="sxs-lookup"><span data-stu-id="124b6-193">Evaluation (demo/test) environments need to register the scale unit connector application \<application ID\> in headquarters.</span></span>

<span data-ttu-id="124b6-194">Si l'initialisation de CSU échoue et que vous recevez ce message d'erreur, notez l'ID d'application, qui est un identificateur global unique (GUID), puis suivez les étapes de la section suivante pour enregistrer l'application de déploiement CSU dans Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="124b6-194">If the CSU initialization fails and you receive this error message, make a note of the application ID, which is a globally unique identifier (GUID), and then follow the steps in the next section to register the CSU deployment application in Commerce headquarters.</span></span>

### <a name="register-the-csu-deployment-application-in-commerce-headquarters-if-required"></a><span data-ttu-id="124b6-195">Enregistrez l'application de déploiement CSU dans Commerce Headquarters (si nécessaire)</span><span class="sxs-lookup"><span data-stu-id="124b6-195">Register the CSU deployment application in Commerce headquarters (if required)</span></span>

<span data-ttu-id="124b6-196">Pour enregistrer l'application de déploiement CSU dans Commerce Headquarters, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="124b6-196">To register the CSU deployment application in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="124b6-197">Dans Commerce Headquarters, accédez à **Administration du système \> Paramétrage \> Applications Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="124b6-197">In Commerce headquarters, go to **System administration \> Setup \> Azure Active Directory applications**.</span></span>
1. <span data-ttu-id="124b6-198">Dans la colonne **ID client**, entrez l'ID d'application du message d'erreur d'initialisation CSU que vous avez reçu.</span><span class="sxs-lookup"><span data-stu-id="124b6-198">In the **Client Id** column, enter the application ID from the CSU initialization error message that you received.</span></span>
1. <span data-ttu-id="124b6-199">Dans la colonne **Nom**, entrez un texte descriptif (par exemple, **Évaluation CSU**).</span><span class="sxs-lookup"><span data-stu-id="124b6-199">In the **Name** column, enter any descriptive text (for example, **CSU Eval**).</span></span>
1. <span data-ttu-id="124b6-200">Dans la colonne **ID d’utilisateur**, entrez **RetailServiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="124b6-200">In the **User ID** column, enter **RetailServiceAccount**.</span></span>
1. <span data-ttu-id="124b6-201">Réessayez l'initialisation et le déploiement de CSU à partir de LCS.</span><span class="sxs-lookup"><span data-stu-id="124b6-201">Retry the CSU initialization and deployment from LCS.</span></span>

### <a name="initialize-e-commerce"></a><span data-ttu-id="124b6-202">Initialiser e-Commerce</span><span class="sxs-lookup"><span data-stu-id="124b6-202">Initialize e-Commerce</span></span>

<span data-ttu-id="124b6-203">Pour initialiser du commerce électronique, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="124b6-203">To initialize e-Commerce, follow these steps.</span></span>

1. <span data-ttu-id="124b6-204">Dans l'onglet **Commerce électronique**, vérifiez le consentement de l'évaluation, puis sélectionnez **Configuration**.</span><span class="sxs-lookup"><span data-stu-id="124b6-204">On the **e-Commerce** tab, review the evaluation consent, and then select **Setup**.</span></span>
1. <span data-ttu-id="124b6-205">Dans le champ **Nom de l'environnement de commerce électronique**, entrez un nom.</span><span class="sxs-lookup"><span data-stu-id="124b6-205">In the **e-Commerce environment name** field, enter a name.</span></span> <span data-ttu-id="124b6-206">Notez que ce nom sera visible dans certaines URL pointant vers votre instance de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="124b6-206">Be aware that this name will appear in some of the URLs that point to your e-Commerce instance.</span></span>
1. <span data-ttu-id="124b6-207">Dans le champ **Nom Commerce Scale Unit**, sélectionnez votre CSU dans la liste.</span><span class="sxs-lookup"><span data-stu-id="124b6-207">In the **Commerce Scale Unit name** field, select your CSU in the list.</span></span> <span data-ttu-id="124b6-208">(La liste ne doit avoir qu'une seule option.)</span><span class="sxs-lookup"><span data-stu-id="124b6-208">(The list should have only one option.)</span></span>

    <span data-ttu-id="124b6-209">Le champ **Géographie du commerce électronique** est défini automatiquement.</span><span class="sxs-lookup"><span data-stu-id="124b6-209">The **e-Commerce geography** field is set automatically.</span></span>

1. <span data-ttu-id="124b6-210">Sélectionnez **Suivant** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="124b6-210">Select **Next** to continue.</span></span>
1. <span data-ttu-id="124b6-211">Dans le champ **Noms d'hôtes pris en charge**, entrez un domaine valide, tel que `www.fabrikam.com`.</span><span class="sxs-lookup"><span data-stu-id="124b6-211">In the **Supported host names** field, enter any valid domain, such as `www.fabrikam.com`.</span></span>
1. <span data-ttu-id="124b6-212">Dans le champ **Groupe de sécurité AAD pour l'administrateur système**, entrez les premières lettres du nom du groupe de sécurité que vous souhaitez utiliser, puis sélectionnez le symbole de la loupe pour afficher les résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="124b6-212">In the **AAD security group for system admin** field, enter the first few letters of the name of the security group that you want to use, and then select the magnifying glass symbol to view the search results.</span></span> <span data-ttu-id="124b6-213">Sélectionnez le groupe de sécurité correct dans la liste.</span><span class="sxs-lookup"><span data-stu-id="124b6-213">Select the correct security group in the list.</span></span>
1.  <span data-ttu-id="124b6-214">Dans le champ **Groupe de sécurité AAD pour les classements et le modérateur de révision**, entrez les premières lettres du nom du groupe de sécurité que vous souhaitez utiliser, puis sélectionnez le symbole de la loupe pour afficher les résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="124b6-214">In the **AAD security group for ratings and review moderator** field, enter the first few letters of the name of the security group that you want to use, and then select the magnifying glass symbol to view the search results.</span></span> <span data-ttu-id="124b6-215">Sélectionnez le groupe de sécurité correct dans la liste.</span><span class="sxs-lookup"><span data-stu-id="124b6-215">Select the correct security group in the list.</span></span>
1. <span data-ttu-id="124b6-216">Laissez l'option **Activer le service de classements et évaluations** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="124b6-216">Leave the **Enable ratings and review service** option set to **Yes**.</span></span>
1. <span data-ttu-id="124b6-217">Sélectionnez **Initialiser**.</span><span class="sxs-lookup"><span data-stu-id="124b6-217">Select **Initialize**.</span></span> <span data-ttu-id="124b6-218">La vue **Gestion de commerce** s'affiche à nouveau et l'onglet **Commerce électronique** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="124b6-218">The **Commerce management** view displays again, where the **e-Commerce** tab is selected.</span></span> <span data-ttu-id="124b6-219">L'initialisation du commerce électronique a commencé.</span><span class="sxs-lookup"><span data-stu-id="124b6-219">E-Commerce initialization has started.</span></span>
1. <span data-ttu-id="124b6-220">Avant de continuer, attendez que le statut de l'initialisation du commerce électronique soit **Initialisation réussie**.</span><span class="sxs-lookup"><span data-stu-id="124b6-220">Before you continue, wait until the status of e-Commerce initialization is **Initialization successful**.</span></span>
1. <span data-ttu-id="124b6-221">Sous **Liens** en bas à droite, notez les URL des liens suivants :</span><span class="sxs-lookup"><span data-stu-id="124b6-221">Under **Links** in the lower right, make a note of the URLs for the following links:</span></span>

    * <span data-ttu-id="124b6-222">**Site de commerce électronique** - Lien vers la racine de votre site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="124b6-222">**e-Commerce site** – The link to the root of your e-Commerce site.</span></span>
    * <span data-ttu-id="124b6-223">**Générateur de site Commerce** - Lien vers l'outil de gestion du site.</span><span class="sxs-lookup"><span data-stu-id="124b6-223">**Commerce site builder** – The link to the site management tool.</span></span>

## <a name="next-steps"></a><span data-ttu-id="124b6-224">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="124b6-224">Next steps</span></span>

<span data-ttu-id="124b6-225">Pour poursuivre le processus de mise en service et de configuration de votre environnement d'évaluation Commerce, consultez [Configurer un environnement d'évaluation Commerce](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="124b6-225">To continue the process of provisioning and configuring your Commerce evaluation environment, see [Configure a Commerce evaluation environment](cpe-post-provisioning.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="124b6-226">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="124b6-226">Additional resources</span></span>

[<span data-ttu-id="124b6-227">Vue d'ensemble d'un environnement d'évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="124b6-227">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="124b6-228">Configurer un environnement d'évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="124b6-228">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="124b6-229">Configurer le BOPIS dans un environnement d'évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="124b6-229">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="124b6-230">Configurer des fonctionnalités facultatives pour un environnement d'évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="124b6-230">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="124b6-231">FAQ des environnements d'évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="124b6-231">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="124b6-232">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="124b6-232">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="124b6-233">Commerce Scale Unit (cloud)</span><span class="sxs-lookup"><span data-stu-id="124b6-233">Commerce Scale Unit (cloud)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="124b6-234">Portail Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="124b6-234">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="124b6-235">Site web Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="124b6-235">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)
