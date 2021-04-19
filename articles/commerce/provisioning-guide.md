---
title: Mettre en service un environnement d’évaluation Dynamics 365 Commerce
description: Cette rubrique explique comment mettre en service un environnement d’évaluation Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 12/17/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 19cedf01d1b916de785454d55448f41d1f5db1df
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792289"
---
# <a name="provision-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="f36fc-103">Mettre en service un environnement d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f36fc-103">Provision a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f36fc-104">Cette rubrique explique comment mettre en service un environnement d’évaluation Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f36fc-104">This topic explains how to provision a Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

<span data-ttu-id="f36fc-105">Avant de commencer, nous vous conseillons de parcourir rapidement cette rubrique pour avoir une idée de ce que le processus nécessite.</span><span class="sxs-lookup"><span data-stu-id="f36fc-105">Before you begin, we recommend that you take a quick scan through this topic to get an idea of what the process requires.</span></span>

> [!NOTE]
> <span data-ttu-id="f36fc-106">Les environnements d’évaluation de Commerce ne sont pas en disponibilité générale et sont accordés aux partenaires et aux clients sur demande.</span><span class="sxs-lookup"><span data-stu-id="f36fc-106">Commerce evaluation environments aren't generally available, and are granted to partners and customers on a per-request basis.</span></span> <span data-ttu-id="f36fc-107">Pour plus d’informations, contactez votre partenaire Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f36fc-107">For more information, reach out to your Microsoft partner contact.</span></span>

<span data-ttu-id="f36fc-108">Pour configurer correctement votre environnement d’évaluation Commerce, vous devez créer un projet qui a un nom et un type de produit spécifiques.</span><span class="sxs-lookup"><span data-stu-id="f36fc-108">To successfully provision a Commerce evaluation environment, you must create a project that has a specific product name and type.</span></span> <span data-ttu-id="f36fc-109">L’environnement et Commerce Scale Unit (CSU) ont aussi des paramètres spécifiques que vous devez utiliser si vous envisagez de mettre en service le commerce électronique ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="f36fc-109">The environment and Commerce Scale Unit (CSU) also have some specific parameters that you must use when you expect to provision e-Commerce later.</span></span> <span data-ttu-id="f36fc-110">Les instructions de cette rubrique décrivent toutes les étapes requises pour terminer la mise en service et indiquent également les paramètres à utiliser.</span><span class="sxs-lookup"><span data-stu-id="f36fc-110">The instructions in this topic describe all the steps that are required to complete provisioning and the parameters that you must use.</span></span>

<span data-ttu-id="f36fc-111">Après une mise en service réussie de votre environnement d’évaluation Commerce, des étapes postérieures à la mise en service sont à effectuer pour l’utiliser.</span><span class="sxs-lookup"><span data-stu-id="f36fc-111">After you successfully provision your Commerce evaluation environment, you must complete a few post-provisioning steps to prepare it for use.</span></span> <span data-ttu-id="f36fc-112">Certaines étapes sont facultatives, selon les aspects du système que vous souhaitez évaluer.</span><span class="sxs-lookup"><span data-stu-id="f36fc-112">Some steps are optional, depending on the aspects of the system that you want to evaluate.</span></span> <span data-ttu-id="f36fc-113">Vous pouvez toujours effectuer les étapes facultatives ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="f36fc-113">You can always complete the optional steps later.</span></span>

<span data-ttu-id="f36fc-114">Pour plus d’informations sur la configuration de votre environnement d’évaluation Commerce après l’avoir mis en service, consultez [Configurer un environnement d’évaluation Commerce](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="f36fc-114">For information about how to configure your Commerce evaluation environment after you provision it, see [Configure a Commerce evaluation environment](cpe-post-provisioning.md).</span></span> <span data-ttu-id="f36fc-115">Pour plus d’informations sur la configuration des fonctionnalités facultatives de votre environnement d’évaluation Commerce, consultez [Configurer les fonctionnalités facultatives d’un environnement d’évaluation Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="f36fc-115">For information about how to configure optional features for your Commerce evaluation environment, see [Configure optional features for a Commerce evaluation environment](cpe-optional-features.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f36fc-116">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="f36fc-116">Prerequisites</span></span>

<span data-ttu-id="f36fc-117">Les conditions préalables suivantes doivent être en place avant de pouvoir mettre en service votre environnement d’évaluation Commerce :</span><span class="sxs-lookup"><span data-stu-id="f36fc-117">The following prerequisites must be in place before you can provision your Commerce evaluation environment:</span></span>

- <span data-ttu-id="f36fc-118">Vous avez été intégré au programme d’évaluation et vous avez obtenu la capacité d’un environnement d’évaluation.</span><span class="sxs-lookup"><span data-stu-id="f36fc-118">You have been onboarded into the evaluation program and granted capacity for an evaluation environment.</span></span>
- <span data-ttu-id="f36fc-119">Vous avez accès au Portail Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="f36fc-119">You have access to the Microsoft Dynamics Lifecycle Services (LCS) portal.</span></span>
- <span data-ttu-id="f36fc-120">Vous êtes un client ou un partenaire Microsoft Dynamics 365 existant et savez créer un projet Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f36fc-120">You are an existing Microsoft Dynamics 365 partner or customer and are able to create a Dynamics 365 Commerce project.</span></span>
- <span data-ttu-id="f36fc-121">Vous disposez d’un accès administrateur à votre abonnement Microsoft Azure, ou vous êtes en contact avec un administrateur d’abonnement qui peut vous aider si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="f36fc-121">You have administrator access to your Microsoft Azure subscription, or you're in contact with a subscription administrator who can assist you if required.</span></span>
- <span data-ttu-id="f36fc-122">Vous avez votre ID client Azure Active Directory (Azure AD) disponible.</span><span class="sxs-lookup"><span data-stu-id="f36fc-122">You have your Azure Active Directory (Azure AD) tenant ID available.</span></span>
- <span data-ttu-id="f36fc-123">Vous avez créé un groupe de sécurité Azure AD à utiliser comme groupe d’administrateurs système de commerce électronique et son ID est disponible.</span><span class="sxs-lookup"><span data-stu-id="f36fc-123">You've created an Azure AD security group that can be used as an e-Commerce system admin group, and you have its ID available.</span></span>
- <span data-ttu-id="f36fc-124">Vous avez créé un groupe de sécurité Azure AD à utiliser comme groupe de modération des classements et évaluations et son ID est disponible.</span><span class="sxs-lookup"><span data-stu-id="f36fc-124">You've created an Azure AD security group that can be used as a Ratings and Reviews moderator group, and you have its ID available.</span></span> <span data-ttu-id="f36fc-125">(Ce groupe de sécurité peut être le même que le groupe d’administration système de commerce électronique.)</span><span class="sxs-lookup"><span data-stu-id="f36fc-125">(This security group can be the same as the e-Commerce system admin group.)</span></span>

<span data-ttu-id="f36fc-126">Notez que cette liste n’est pas exhaustive.</span><span class="sxs-lookup"><span data-stu-id="f36fc-126">Note that this list isn't exhaustive.</span></span> <span data-ttu-id="f36fc-127">Si vous rencontrez des problèmes, contactez votre partenaire Microsoft pour obtenir de l’aide.</span><span class="sxs-lookup"><span data-stu-id="f36fc-127">If you experience any issues, reach out to your Microsoft partner contact for assistance.</span></span>

## <a name="provision-your-commerce-evaluation-environment"></a><span data-ttu-id="f36fc-128">Mise en service de votre environnement d’évaluation Commerce</span><span class="sxs-lookup"><span data-stu-id="f36fc-128">Provision your Commerce evaluation environment</span></span>

<span data-ttu-id="f36fc-129">Ces procédures expliquent comment mettre en service un environnement d’évaluation Commerce.</span><span class="sxs-lookup"><span data-stu-id="f36fc-129">These procedures explain how to provision a Commerce evaluation environment.</span></span> <span data-ttu-id="f36fc-130">Une fois que vous les aurez terminées avec succès, l’environnement d’évaluation de Commerce sera prêt pour la configuration.</span><span class="sxs-lookup"><span data-stu-id="f36fc-130">After you successfully complete them, the Commerce evaluation environment will be ready for configuration.</span></span> <span data-ttu-id="f36fc-131">Toutes les activités décrites ici ont lieu dans le portail LCS.</span><span class="sxs-lookup"><span data-stu-id="f36fc-131">All the activities that are described here occur in the LCS portal.</span></span>

### <a name="create-a-new-project"></a><span data-ttu-id="f36fc-132">Créer un nouveau projet</span><span class="sxs-lookup"><span data-stu-id="f36fc-132">Create a new project</span></span>

<span data-ttu-id="f36fc-133">Pour créer un projet dans LCS, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="f36fc-133">To create a new project in LCS, follow these steps.</span></span>

1. <span data-ttu-id="f36fc-134">Sur la page d’accueil LCS, sélectionnez le signe plus (**+**) pour créer un projet.</span><span class="sxs-lookup"><span data-stu-id="f36fc-134">On the LCS home page, select the plus sign (**+**) to create a project.</span></span>
1. <span data-ttu-id="f36fc-135">Dans le volet droit, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f36fc-135">In the right pane, follow one of these steps:</span></span>

    - <span data-ttu-id="f36fc-136">Si vous êtes un partenaire, cliquez sur **Migrer, créer des solutions et découvrir**.</span><span class="sxs-lookup"><span data-stu-id="f36fc-136">If you're a partner, select **Migrate, create solutions, and learn**.</span></span>
    - <span data-ttu-id="f36fc-137">Si vous êtes un client, cliquez sur **Préventes potentielles**.</span><span class="sxs-lookup"><span data-stu-id="f36fc-137">If you're a customer, select **Prospective presales**.</span></span>

1. <span data-ttu-id="f36fc-138">Entrer une nom, une description et un secteur d’activité.</span><span class="sxs-lookup"><span data-stu-id="f36fc-138">Enter a name, description, and industry.</span></span>
1. <span data-ttu-id="f36fc-139">Dans le champ **Nom du produit**, cliquez sur **Dynamics 365 Commerce**.</span><span class="sxs-lookup"><span data-stu-id="f36fc-139">In the **Product name** field, select **Dynamics 365 Commerce**.</span></span>
1. <span data-ttu-id="f36fc-140">Dans le champ **Version du produit**, cliquez sur **Dynamics 365 Commerce**.</span><span class="sxs-lookup"><span data-stu-id="f36fc-140">In the **Product version** field, select **Dynamics 365 Commerce**.</span></span>
1. <span data-ttu-id="f36fc-141">Dans le champ **Méthodologie**, sélectionnez **Méthodologie de mise en œuvre de Dynamics Retail**.</span><span class="sxs-lookup"><span data-stu-id="f36fc-141">In the **Methodology** field, select **Dynamics Retail implementation methodology**.</span></span>
1. <span data-ttu-id="f36fc-142">Facultatif : Vous pouvez importer les rôles et les utilisateurs d’un projet existant.</span><span class="sxs-lookup"><span data-stu-id="f36fc-142">Optional: You can import roles and users from an existing project.</span></span>
1. <span data-ttu-id="f36fc-143">Sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="f36fc-143">Select **Create**.</span></span> <span data-ttu-id="f36fc-144">La vue du projet s’affiche.</span><span class="sxs-lookup"><span data-stu-id="f36fc-144">The project view appears.</span></span>

### <a name="add-the-azure-connector"></a><span data-ttu-id="f36fc-145">Ajouter le connecteur Azure</span><span class="sxs-lookup"><span data-stu-id="f36fc-145">Add the Azure Connector</span></span>

<span data-ttu-id="f36fc-146">Pour ajouter le connecteur Azure à votre projet LCS, suivez les étapes de [Terminer l’intégration d’Azure Resource Manager (ARM)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/deployment/arm-onboarding).</span><span class="sxs-lookup"><span data-stu-id="f36fc-146">To add the Azure Connector to your LCS project, follow the steps in [Complete the Azure Resource Manager (ARM) onboarding process](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/deployment/arm-onboarding).</span></span>

### <a name="deploy-the-environment"></a><span data-ttu-id="f36fc-147">Déploiement de l’environnement</span><span class="sxs-lookup"><span data-stu-id="f36fc-147">Deploy the environment</span></span>

<span data-ttu-id="f36fc-148">Pour déployer l’environnement, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="f36fc-148">To deploy the environment, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="f36fc-149">Vous n’aurez peut-être pas à effectuer les étapes 6, 7 et/ou 8, car les pages comportant une seule option sont ignorées.</span><span class="sxs-lookup"><span data-stu-id="f36fc-149">You might not have to complete steps 6, 7, and/or 8, because pages that have a single option are skipped.</span></span> <span data-ttu-id="f36fc-150">Si vous affichez la vue **Paramètres environnementaux**, confirmez que le texte **Dynamics 365 Commerce - Démonstration (10.0.* x* avec mise à jour de la plateforme *xx*)\*\* apparaît directement au-dessus du champ **Nom de l’environnement**.</span><span class="sxs-lookup"><span data-stu-id="f36fc-150">When you're in the **Environment parameters** view, confirm that the text **Dynamics 365 Commerce - Demo (10.0.* x* with Platform update *xx*)\*\* appears directly above the **Environment name** field.</span></span> <span data-ttu-id="f36fc-151">Pour plus de détails, voir l’illustration qui apparaît après l’étape 8.</span><span class="sxs-lookup"><span data-stu-id="f36fc-151">For details, see the illustration that appears after step 8.</span></span>

1. <span data-ttu-id="f36fc-152">Sur le menu principal, sélectionnez **Environnements hébergés dans le cloud**.</span><span class="sxs-lookup"><span data-stu-id="f36fc-152">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="f36fc-153">Cliquez sur **Ajouter** pour ajouter un environnement.</span><span class="sxs-lookup"><span data-stu-id="f36fc-153">Select **Add** to add an environment.</span></span>
1. <span data-ttu-id="f36fc-154">Dans le champ **Version de l’application**, sélectionnez la version la plus récente.</span><span class="sxs-lookup"><span data-stu-id="f36fc-154">In the **Application version** field, select the most current version.</span></span> <span data-ttu-id="f36fc-155">Si vous devez absolument sélectionner une version d’application autre que la version la plus récente, ne sélectionnez pas de version antérieure à la version **10.0.14**.</span><span class="sxs-lookup"><span data-stu-id="f36fc-155">If you have a specific need to select an application version other than the most current version, do not select a version prior to **10.0.14**.</span></span>
1. <span data-ttu-id="f36fc-156">Dans le champ **Version de la plateforme**, utilisez la version de la plateforme automatiquement choisie pour la version de l’application sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f36fc-156">In the **Platform version** field, use the platform version that is automatically chosen for the application version you selected.</span></span> 

    ![Sélection des versions de l’application et de la plateforme](./media/project1.png)

1. <span data-ttu-id="f36fc-158">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f36fc-158">Select **Next**.</span></span>
1. <span data-ttu-id="f36fc-159">Sélectionner **Démonstration** comme topologie de l’environnement.</span><span class="sxs-lookup"><span data-stu-id="f36fc-159">Select **Demo** as the environment topology.</span></span>

    ![Sélection de la topologie de l’environment 1](./media/project2.png)

1. <span data-ttu-id="f36fc-161">Sur la page **Déployer l’environnement**, entrez un nom d’environnement.</span><span class="sxs-lookup"><span data-stu-id="f36fc-161">On the **Deploy environment** page, enter an environment name.</span></span> <span data-ttu-id="f36fc-162">Laissez les paramètres avancés inchangés.</span><span class="sxs-lookup"><span data-stu-id="f36fc-162">Leave the advanced settings as they are.</span></span>

    ![Page Déployer l’environnement](./media/project4.png)

1. <span data-ttu-id="f36fc-164">Ajustez la taille de la machine virtuelle selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="f36fc-164">Adjust the VM size as required.</span></span> <span data-ttu-id="f36fc-165">(Nous recommandons l’unité de gestion de stock de machine virtuelle \[SKU\] **D13 v2**.)</span><span class="sxs-lookup"><span data-stu-id="f36fc-165">(We recommend VM stock keeping unit \[SKU\] **D13 v2**.)</span></span>
1. <span data-ttu-id="f36fc-166">Passez en revue les conditions de prix et de licence, puis cochez la case pour indiquer que vous les acceptez.</span><span class="sxs-lookup"><span data-stu-id="f36fc-166">Review the pricing and licensing terms, and then select the check box to indicate that you agree to them.</span></span>
1. <span data-ttu-id="f36fc-167">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f36fc-167">Select **Next**.</span></span>
1. <span data-ttu-id="f36fc-168">Dans la page de confirmation du déploiement, après avoir vérifié les détails sont corrects, cliquez sur **Déployer**.</span><span class="sxs-lookup"><span data-stu-id="f36fc-168">On the deployment confirmation page, verify that the details are correct, and then select **Deploy**.</span></span> <span data-ttu-id="f36fc-169">Vous revenez à la vue **Environnements hébergés sur le cloud** et votre environnement doit apparaître dans la liste.</span><span class="sxs-lookup"><span data-stu-id="f36fc-169">You're returned to the **Cloud-hosted environments** view, and your environment should appear in the list.</span></span>

    <span data-ttu-id="f36fc-170">Votre environnement demandé s’affiche comme mis en file d’attente, puis en cours de déploiement.</span><span class="sxs-lookup"><span data-stu-id="f36fc-170">Your requested environment will appear as queued and then deploying.</span></span> <span data-ttu-id="f36fc-171">Les workflows d’environnement prendront un certain temps à se terminer.</span><span class="sxs-lookup"><span data-stu-id="f36fc-171">The environment workflows will take some time to be completed.</span></span> <span data-ttu-id="f36fc-172">Par conséquent, revenez après environ six à neuf heures.</span><span class="sxs-lookup"><span data-stu-id="f36fc-172">Therefore, check back after approximately six to nine hours.</span></span>

1. <span data-ttu-id="f36fc-173">Avant de continuer, vérifiez que le statut de votre environnement est **Déployé**.</span><span class="sxs-lookup"><span data-stu-id="f36fc-173">Before you continue, make sure that the status of your environment is **Deployed**.</span></span>

### <a name="initialize-the-commerce-scale-unit-cloud"></a><span data-ttu-id="f36fc-174">Initialiser Commerce Scale Unit (cloud)</span><span class="sxs-lookup"><span data-stu-id="f36fc-174">Initialize the Commerce Scale Unit (cloud)</span></span>

<span data-ttu-id="f36fc-175">Pour initialiser le CSU, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="f36fc-175">To initialize the CSU, follow these steps.</span></span>

1. <span data-ttu-id="f36fc-176">Dans la vue **Environnements hébergés dans le cloud**, sélectionnez votre environnement dans la liste.</span><span class="sxs-lookup"><span data-stu-id="f36fc-176">In the **Cloud-hosted environments** view, select your environment in the list.</span></span>
1. <span data-ttu-id="f36fc-177">Dans les informations de l’environnement à droite, cliquez sur **Détails complets**.</span><span class="sxs-lookup"><span data-stu-id="f36fc-177">In the environment view on the right, select **Full details**.</span></span> <span data-ttu-id="f36fc-178">La vue des détails d’environnement s’affiche.</span><span class="sxs-lookup"><span data-stu-id="f36fc-178">The environment details view appears.</span></span>
1. <span data-ttu-id="f36fc-179">Sous **Fonctions d’environnement**, cliquez sur **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="f36fc-179">Under **Environment features**, select **Manage**.</span></span>
1. <span data-ttu-id="f36fc-180">Dans l’onglet **Commerce**, cliquez sur **Initialiser**.</span><span class="sxs-lookup"><span data-stu-id="f36fc-180">On the **Commerce** tab, select **Initialize**.</span></span> <span data-ttu-id="f36fc-181">La vue des paramètres d’initialisation de CSU s’affiche.</span><span class="sxs-lookup"><span data-stu-id="f36fc-181">The CSU initialization parameters view appears.</span></span>
1. <span data-ttu-id="f36fc-182">Dans le champ **Région**, sélectionnez la région identique ou proche de la région dans laquelle vous avez déployé l’environnement.</span><span class="sxs-lookup"><span data-stu-id="f36fc-182">In the **Region** field, select the region that is the same or close to the region that you deployed the environment to.</span></span>
1. <span data-ttu-id="f36fc-183">Laissez le champ **Version** tel qu’il est.</span><span class="sxs-lookup"><span data-stu-id="f36fc-183">Leave the **Version** field as it is.</span></span>
1. <span data-ttu-id="f36fc-184">Sélectionnez **Initialiser**.</span><span class="sxs-lookup"><span data-stu-id="f36fc-184">Select **Initialize**.</span></span>
1. <span data-ttu-id="f36fc-185">Dans la page de confirmation du déploiement, après avoir vérifié les détails sont corrects, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="f36fc-185">On the deployment confirmation page, verify that the details are correct, and then select **Yes**.</span></span> <span data-ttu-id="f36fc-186">La vue **Gestion de commerce** s’affiche à nouveau et l’onglet **Commerce** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f36fc-186">The **Commerce management** view displays again, where the **Commerce** tab is selected.</span></span> <span data-ttu-id="f36fc-187">Votre CSU a été mis en file d’attente pour la mise en service.</span><span class="sxs-lookup"><span data-stu-id="f36fc-187">Your CSU has been queued for provisioning.</span></span>
1. <span data-ttu-id="f36fc-188">Avant de continuer, vérifiez que le statut de votre CSU est **Réussite**.</span><span class="sxs-lookup"><span data-stu-id="f36fc-188">Before you continue, make sure that the status of your CSU is **Success**.</span></span> <span data-ttu-id="f36fc-189">L’initialisation prend environ deux à cinq heures.</span><span class="sxs-lookup"><span data-stu-id="f36fc-189">Initialization takes approximately two to five hours.</span></span>

<span data-ttu-id="f36fc-190">Si vous ne trouvez pas le lien **Gérer** dans la vue des détails de l’environnement, contactez votre contact Microsoft pour obtenir de l’aide.</span><span class="sxs-lookup"><span data-stu-id="f36fc-190">If you can't find the **Manage** link in the environment details view, reach out to your Microsoft contact for assistance.</span></span>

<span data-ttu-id="f36fc-191">Vous pouvez recevoir le message d’erreur suivant pendant le processus de déploiement :</span><span class="sxs-lookup"><span data-stu-id="f36fc-191">During the deployment process, you might receive the following error message:</span></span>

> <span data-ttu-id="f36fc-192">Les environnements d’évaluation (démo/test) doivent enregistrer l’application de connecteur d’unité de mise à l’échelle \<application ID\> dans le siège.</span><span class="sxs-lookup"><span data-stu-id="f36fc-192">Evaluation (demo/test) environments need to register the scale unit connector application \<application ID\> in headquarters.</span></span>

<span data-ttu-id="f36fc-193">Si l’initialisation de CSU échoue et que vous recevez ce message d’erreur, notez l’ID d’application, qui est un identificateur global unique (GUID), puis suivez les étapes de la section suivante pour enregistrer l’application de déploiement CSU dans Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="f36fc-193">If the CSU initialization fails and you receive this error message, make a note of the application ID, which is a globally unique identifier (GUID), and then follow the steps in the next section to register the CSU deployment application in Commerce headquarters.</span></span>

### <a name="register-the-csu-deployment-application-in-commerce-headquarters-if-required"></a><span data-ttu-id="f36fc-194">Enregistrez l’application de déploiement CSU dans Commerce Headquarters (si nécessaire)</span><span class="sxs-lookup"><span data-stu-id="f36fc-194">Register the CSU deployment application in Commerce headquarters (if required)</span></span>

<span data-ttu-id="f36fc-195">Pour enregistrer l’application de déploiement CSU dans Commerce Headquarters, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f36fc-195">To register the CSU deployment application in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="f36fc-196">Dans Commerce Headquarters, accédez à **Administration du système \> Paramétrage \> Applications Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="f36fc-196">In Commerce headquarters, go to **System administration \> Setup \> Azure Active Directory applications**.</span></span>
1. <span data-ttu-id="f36fc-197">Dans la colonne **ID client**, entrez l’ID d’application du message d’erreur d’initialisation CSU que vous avez reçu.</span><span class="sxs-lookup"><span data-stu-id="f36fc-197">In the **Client Id** column, enter the application ID from the CSU initialization error message that you received.</span></span>
1. <span data-ttu-id="f36fc-198">Dans la colonne **Nom**, entrez un texte descriptif (par exemple, **Évaluation CSU**).</span><span class="sxs-lookup"><span data-stu-id="f36fc-198">In the **Name** column, enter any descriptive text (for example, **CSU Eval**).</span></span>
1. <span data-ttu-id="f36fc-199">Dans la colonne **ID d’utilisateur**, entrez **RetailServiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="f36fc-199">In the **User ID** column, enter **RetailServiceAccount**.</span></span>
1. <span data-ttu-id="f36fc-200">Réessayez l’initialisation et le déploiement de CSU à partir de LCS.</span><span class="sxs-lookup"><span data-stu-id="f36fc-200">Retry the CSU initialization and deployment from LCS.</span></span>

### <a name="initialize-e-commerce"></a><span data-ttu-id="f36fc-201">Initialiser e-Commerce</span><span class="sxs-lookup"><span data-stu-id="f36fc-201">Initialize e-Commerce</span></span>

<span data-ttu-id="f36fc-202">Pour initialiser du commerce électronique, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="f36fc-202">To initialize e-Commerce, follow these steps.</span></span>

1. <span data-ttu-id="f36fc-203">Dans l’onglet **Commerce électronique**, vérifiez le consentement de l’évaluation, puis sélectionnez **Configuration**.</span><span class="sxs-lookup"><span data-stu-id="f36fc-203">On the **e-Commerce** tab, review the evaluation consent, and then select **Setup**.</span></span>
1. <span data-ttu-id="f36fc-204">Dans le champ **Nom de l’environnement de commerce électronique**, entrez un nom.</span><span class="sxs-lookup"><span data-stu-id="f36fc-204">In the **e-Commerce environment name** field, enter a name.</span></span> <span data-ttu-id="f36fc-205">Notez que ce nom sera visible dans certaines URL pointant vers votre instance de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="f36fc-205">Be aware that this name will appear in some of the URLs that point to your e-Commerce instance.</span></span>
1. <span data-ttu-id="f36fc-206">Dans le champ **Nom Commerce Scale Unit**, sélectionnez votre CSU dans la liste.</span><span class="sxs-lookup"><span data-stu-id="f36fc-206">In the **Commerce Scale Unit name** field, select your CSU in the list.</span></span> <span data-ttu-id="f36fc-207">(La liste ne doit avoir qu’une seule option.)</span><span class="sxs-lookup"><span data-stu-id="f36fc-207">(The list should have only one option.)</span></span>

    <span data-ttu-id="f36fc-208">Le champ **Géographie du commerce électronique** est défini automatiquement.</span><span class="sxs-lookup"><span data-stu-id="f36fc-208">The **e-Commerce geography** field is set automatically.</span></span>

1. <span data-ttu-id="f36fc-209">Sélectionnez **Suivant** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="f36fc-209">Select **Next** to continue.</span></span>
1. <span data-ttu-id="f36fc-210">Dans le champ **Noms d’hôtes pris en charge**, entrez un domaine valide, tel que `www.fabrikam.com`.</span><span class="sxs-lookup"><span data-stu-id="f36fc-210">In the **Supported host names** field, enter any valid domain, such as `www.fabrikam.com`.</span></span>
1. <span data-ttu-id="f36fc-211">Dans le champ **Groupe de sécurité AAD pour l’administrateur système**, entrez les premières lettres du nom du groupe de sécurité que vous souhaitez utiliser, puis sélectionnez le symbole de la loupe pour afficher les résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="f36fc-211">In the **AAD security group for system admin** field, enter the first few letters of the name of the security group that you want to use, and then select the magnifying glass symbol to view the search results.</span></span> <span data-ttu-id="f36fc-212">Sélectionnez le groupe de sécurité correct dans la liste.</span><span class="sxs-lookup"><span data-stu-id="f36fc-212">Select the correct security group in the list.</span></span>
1.  <span data-ttu-id="f36fc-213">Dans le champ **Groupe de sécurité AAD pour les classements et le modérateur de révision**, entrez les premières lettres du nom du groupe de sécurité que vous souhaitez utiliser, puis sélectionnez le symbole de la loupe pour afficher les résultats de la recherche.</span><span class="sxs-lookup"><span data-stu-id="f36fc-213">In the **AAD security group for ratings and review moderator** field, enter the first few letters of the name of the security group that you want to use, and then select the magnifying glass symbol to view the search results.</span></span> <span data-ttu-id="f36fc-214">Sélectionnez le groupe de sécurité correct dans la liste.</span><span class="sxs-lookup"><span data-stu-id="f36fc-214">Select the correct security group in the list.</span></span>
1. <span data-ttu-id="f36fc-215">Laissez l’option **Activer le service de classements et évaluations** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="f36fc-215">Leave the **Enable ratings and review service** option set to **Yes**.</span></span>
1. <span data-ttu-id="f36fc-216">Sélectionnez **Initialiser**.</span><span class="sxs-lookup"><span data-stu-id="f36fc-216">Select **Initialize**.</span></span> <span data-ttu-id="f36fc-217">La vue **Gestion de commerce** s’affiche à nouveau et l’onglet **Commerce électronique** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f36fc-217">The **Commerce management** view displays again, where the **e-Commerce** tab is selected.</span></span> <span data-ttu-id="f36fc-218">L’initialisation du commerce électronique a commencé.</span><span class="sxs-lookup"><span data-stu-id="f36fc-218">E-Commerce initialization has started.</span></span>
1. <span data-ttu-id="f36fc-219">Avant de continuer, attendez que le statut de l’initialisation du commerce électronique soit **Initialisation réussie**.</span><span class="sxs-lookup"><span data-stu-id="f36fc-219">Before you continue, wait until the status of e-Commerce initialization is **Initialization successful**.</span></span>
1. <span data-ttu-id="f36fc-220">Sous **Liens** en bas à droite, notez les URL des liens suivants :</span><span class="sxs-lookup"><span data-stu-id="f36fc-220">Under **Links** in the lower right, make a note of the URLs for the following links:</span></span>

    * <span data-ttu-id="f36fc-221">**Site de commerce électronique** - Lien vers la racine de votre site de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="f36fc-221">**e-Commerce site** – The link to the root of your e-Commerce site.</span></span>
    * <span data-ttu-id="f36fc-222">**Générateur de site Commerce** - Lien vers l’outil de gestion du site.</span><span class="sxs-lookup"><span data-stu-id="f36fc-222">**Commerce site builder** – The link to the site management tool.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f36fc-223">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="f36fc-223">Next steps</span></span>

<span data-ttu-id="f36fc-224">Pour poursuivre le processus de mise en service et de configuration de votre environnement d’évaluation Commerce, consultez [Configurer un environnement d’évaluation Commerce](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="f36fc-224">To continue the process of provisioning and configuring your Commerce evaluation environment, see [Configure a Commerce evaluation environment](cpe-post-provisioning.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f36fc-225">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="f36fc-225">Additional resources</span></span>

[<span data-ttu-id="f36fc-226">Vue d’ensemble d’un environnement d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f36fc-226">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="f36fc-227">Configurer un environnement d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f36fc-227">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="f36fc-228">Configurer le BOPIS dans un environnement d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f36fc-228">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="f36fc-229">Configurer des fonctionnalités facultatives pour un environnement d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f36fc-229">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="f36fc-230">FAQ des environnements d’évaluation Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f36fc-230">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="f36fc-231">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="f36fc-231">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="f36fc-232">Commerce Scale Unit (cloud)</span><span class="sxs-lookup"><span data-stu-id="f36fc-232">Commerce Scale Unit (cloud)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="f36fc-233">Portail Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="f36fc-233">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="f36fc-234">Site web Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f36fc-234">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
