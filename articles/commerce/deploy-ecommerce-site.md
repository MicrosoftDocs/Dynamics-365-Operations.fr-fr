---
title: Déployer un nouveau client e-commerce
description: Cette rubrique décrit la procédure de déploiement d'un nouveau site d'e-commerce Dynamics 365 Commerce à l'aide de Microsoft Dynamics Lifecycle Services (LCS).
author: psimolin
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 157dc8225e5bbf9338a1b5a79a2880e8a8c4bf10
ms.sourcegitcommit: 4bf5ae2f2f144a28e431ed574c7e8438dc5935de
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2020
ms.locfileid: "4517280"
---
# <a name="deploy-a-new-e-commerce-tenant"></a><span data-ttu-id="609ea-103">Déployer un nouveau client e-commerce</span><span class="sxs-lookup"><span data-stu-id="609ea-103">Deploy a new e-commerce tenant</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="609ea-104">Cette rubrique décrit la procédure de déploiement d'un nouveau site d'e-commerce Dynamics 365 Commerce à l'aide de Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="609ea-104">This topic describes how to deploy a new Dynamics 365 Commerce e-commerce site by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="overview"></a><span data-ttu-id="609ea-105">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="609ea-105">Overview</span></span>

<span data-ttu-id="609ea-106">Microsoft Dynamics Lifecycle Services (LCS) est un espace de travail de collaboration basé sur le cloud que les partenaires et les clients peuvent utiliser pour gérer leurs projets et environnements, afficher les dernières informations sur les produits et les fonctionnalités Microsoft Dynamics, et créer, effectuer le suivi, et consulter les incidents de support.</span><span class="sxs-lookup"><span data-stu-id="609ea-106">Microsoft Dynamics Lifecycle Services (LCS) is a cloud-based collaborative workspace that partners and customers can use to manage their projects and environments, view the latest information about Microsoft Dynamics products and features, and create, track, and browse support incidents.</span></span> <span data-ttu-id="609ea-107">Les fonctionnalités de gestion d'e-commerce sont intégrées à LCS.</span><span class="sxs-lookup"><span data-stu-id="609ea-107">E-commerce management features are integrated into LCS.</span></span>

<span data-ttu-id="609ea-108">Pour en savoir plus sur LCS, voir [Guide de l'utilisateur de Lifecycle Services](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span><span class="sxs-lookup"><span data-stu-id="609ea-108">To learn more about LCS, see the [Lifecycle Services User Guide](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span></span>
    
## <a name="get-started"></a><span data-ttu-id="609ea-109">Mise en route</span><span class="sxs-lookup"><span data-stu-id="609ea-109">Get started</span></span>

<span data-ttu-id="609ea-110">Avant d'initialiser l'e-commerce, vous devez initialiser un projet, un environnement, et une Retail Cloud Scale Unit (RCSU).</span><span class="sxs-lookup"><span data-stu-id="609ea-110">Before you can initialize e-commerce, you must initialize a project, an environment, and a Retail Cloud Scale Unit (RCSU).</span></span> <span data-ttu-id="609ea-111">Pour effectuer l'initialisation dans LCS, vous devez disposer des autorisations du rôle de Propriétaire du projet ou de Gestionnaire de l'environnement.</span><span class="sxs-lookup"><span data-stu-id="609ea-111">To do the initialization in LCS, you must have permissions for either the Project Owner or Environment manager role.</span></span> <span data-ttu-id="609ea-112">Les topologies d'environnement de production et bac à sable sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="609ea-112">The production and sandbox environment topologies are supported.</span></span>

<span data-ttu-id="609ea-113">Pour plus d'informations sur les environnements, voir [Planification de l'environnement](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span><span class="sxs-lookup"><span data-stu-id="609ea-113">For more information about environments, see [Environment planning](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span></span> <span data-ttu-id="609ea-114">Pour plus d'informations sur la conformité RCSU, voir [Initialiser Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="609ea-114">For more information about RCSU, see [Initialize Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span></span>

## <a name="initialize-e-commerce"></a><span data-ttu-id="609ea-115">Initialiser l'e-commerce</span><span class="sxs-lookup"><span data-stu-id="609ea-115">Initialize e-commerce</span></span>

<span data-ttu-id="609ea-116">Cette procédure permet d'initialiser la fonctionnalité d'e-commerce dans un environnement existant.</span><span class="sxs-lookup"><span data-stu-id="609ea-116">Use this procedure to initialize the e-commerce feature in an existing environment.</span></span>

<span data-ttu-id="609ea-117">Avant de commencer, vérifiez que vous avez les informations requises suivantes :</span><span class="sxs-lookup"><span data-stu-id="609ea-117">Before you begin, make sure that you have the following required information:</span></span>

- <span data-ttu-id="609ea-118">La RCSU qui sera utilisée.</span><span class="sxs-lookup"><span data-stu-id="609ea-118">The RCSU that will be used.</span></span>
- <span data-ttu-id="609ea-119">Le groupe de sécurité Microsoft Azure Active Directory qui sera utilisé pour les administrateurs système d'e-commerce.</span><span class="sxs-lookup"><span data-stu-id="609ea-119">The Microsoft Azure Active Directory security group that will be used for e-commerce system admins.</span></span>
- <span data-ttu-id="609ea-120">Le groupe de sécurité Microsoft Azure Active Directory qui sera utilisé pour les modérateurs des classements et évaluations.</span><span class="sxs-lookup"><span data-stu-id="609ea-120">The Microsoft Azure Active Directory security group that will be used for ratings and reviews moderators.</span></span>
- <span data-ttu-id="609ea-121">Les domaines qui seront associés à l'environnement.</span><span class="sxs-lookup"><span data-stu-id="609ea-121">The domains that will be associated with the environment.</span></span>

<span data-ttu-id="609ea-122">En outre, vous pouvez collecter les informations facultatives suivantes :</span><span class="sxs-lookup"><span data-stu-id="609ea-122">In addition, you can collect the following optional information:</span></span>

- <span data-ttu-id="609ea-123">Informations entreprise-client (B2C) Azure AD :</span><span class="sxs-lookup"><span data-stu-id="609ea-123">Azure AD business-to-consumer (B2C) information:</span></span>

    - <span data-ttu-id="609ea-124">Nom du client.</span><span class="sxs-lookup"><span data-stu-id="609ea-124">Tenant Name.</span></span>
    - <span data-ttu-id="609ea-125">ID client.</span><span class="sxs-lookup"><span data-stu-id="609ea-125">Client ID.</span></span>
    - <span data-ttu-id="609ea-126">Domaine personnalisé de connexion.</span><span class="sxs-lookup"><span data-stu-id="609ea-126">Login Custom Domain.</span></span>
    - <span data-ttu-id="609ea-127">URL de réponse.</span><span class="sxs-lookup"><span data-stu-id="609ea-127">Reply URL.</span></span>
    - <span data-ttu-id="609ea-128">ID stratégie Inscription Connexion.</span><span class="sxs-lookup"><span data-stu-id="609ea-128">SignUp SignIn Policy ID.</span></span>
    - <span data-ttu-id="609ea-129">ID stratégie de réinitialisation du mot de passe.</span><span class="sxs-lookup"><span data-stu-id="609ea-129">Reset password Policy ID.</span></span>
    - <span data-ttu-id="609ea-130">Modifiez l'ID stratégie de profil.</span><span class="sxs-lookup"><span data-stu-id="609ea-130">Edit Profile Policy ID.</span></span>

> [!NOTE]
> <span data-ttu-id="609ea-131">Ces informations peuvent être ajoutées ultérieurement, via une demande de service.</span><span class="sxs-lookup"><span data-stu-id="609ea-131">This information can be added later, through a service request.</span></span>

<span data-ttu-id="609ea-132">Après avoir collecté les informations requises, procédez comme suit pour initialiser l'e-commerce.</span><span class="sxs-lookup"><span data-stu-id="609ea-132">After you've collected the required information, follow these steps to initialize e-commerce.</span></span>

1. <span data-ttu-id="609ea-133">Connectez-vous à [LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="609ea-133">Sign in to [LCS](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="609ea-134">Ouvrir le projet contenant l'environnement dans lequel vous souhaitez initialiser l'e-commerce.</span><span class="sxs-lookup"><span data-stu-id="609ea-134">Open the project that contains the environment where you want to initialize e-commerce.</span></span>
1. <span data-ttu-id="609ea-135">Dans la section **Environnements**, sélectionnez l'environnement.</span><span class="sxs-lookup"><span data-stu-id="609ea-135">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="609ea-136">Sous **Fonctionnalités de l'environnement**, sélectionnez le lien **Gestion de la vente au détail**.</span><span class="sxs-lookup"><span data-stu-id="609ea-136">Under **Environment features**, select the **Retail manage** link.</span></span>
1. <span data-ttu-id="609ea-137">Dans l'onglet **commerce électronique**, sélectionnez **Paramétrage**.</span><span class="sxs-lookup"><span data-stu-id="609ea-137">On the **e-Commerce** tab, select **Setup**.</span></span> <span data-ttu-id="609ea-138">Une boîte de dialogue s'affiche, dans laquelle vous devez entrer les informations requises pour la mise en service.</span><span class="sxs-lookup"><span data-stu-id="609ea-138">A dialog box appears, where you must enter the information that is required for provisioning.</span></span>
1. <span data-ttu-id="609ea-139">Entrez les informations requises, puis passez à la page suivante.</span><span class="sxs-lookup"><span data-stu-id="609ea-139">Fill in the required information, and then go to the next page.</span></span>
1. <span data-ttu-id="609ea-140">Sur la page suivante, entrez les informations requises, puis envoyez le formulaire.</span><span class="sxs-lookup"><span data-stu-id="609ea-140">On the next page, fill in the required information, and then submit the form.</span></span> <span data-ttu-id="609ea-141">Vous êtes redirigé vers l'onglet **Commerce électronique**, sous lequel vous devez vérifier que l'initialisation a commencé.</span><span class="sxs-lookup"><span data-stu-id="609ea-141">You're returned to the **e-Commerce** tab, where you should see that initialization has been started.</span></span>
1. <span data-ttu-id="609ea-142">Pour afficher le statut de l'initialisation, **Actualisez** ou revenez à l'onglet **commerce électronique** ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="609ea-142">To view the initialization status, either **Refresh** or return to the **e-Commerce** tab later.</span></span>
    
<span data-ttu-id="609ea-143">Lorsque l'e-commerce est initialisé par LCS, le système met en service plusieurs composants requis pour l'e-commerce et les associe à l'environnement.</span><span class="sxs-lookup"><span data-stu-id="609ea-143">When e-commerce is initialized from LCS, the system provisions several components that are required for e-commerce and associates them with the environment.</span></span> <span data-ttu-id="609ea-144">Après la mise en service, l'onglet **Commerce électronique** sur la page **Gestion de la vente au détail** est mis à jour pour refléter la mise en service.</span><span class="sxs-lookup"><span data-stu-id="609ea-144">After provisioning is complete, the **e-Commerce** tab on the **Retail management** page is updated to reflect the provisioning.</span></span> <span data-ttu-id="609ea-145">La page présente les derniers déploiements de personnalisation et le statut de tout autre déploiements en cours.</span><span class="sxs-lookup"><span data-stu-id="609ea-145">The page shows the latest customization deployments and the status of any other ongoing deployments.</span></span> <span data-ttu-id="609ea-146">Elle contient également des liens vers le site d'e-commerce et le générateur de site d'e-commerce où les sites sont créés.</span><span class="sxs-lookup"><span data-stu-id="609ea-146">It also includes links to the e-commerce site and the Commerce site builder where sites are authored.</span></span>

## <a name="access-commerce-site-builder"></a><span data-ttu-id="609ea-147">Accéder au générateur de site Commerce</span><span class="sxs-lookup"><span data-stu-id="609ea-147">Access Commerce site builder</span></span>

<span data-ttu-id="609ea-148">Pour accéder au générateur de site Commerce, accédez à l'onglet **e-Commerce** dans la page **Gestion de vente au détail** dans LCS et sélectionnez le lien **Outil de gestion de site d'e-commerce**.</span><span class="sxs-lookup"><span data-stu-id="609ea-148">To access Commerce site builder, go to the **e-Commerce** tab on the **Retail management** page in LCS and select the **e-Commerce site management tool** link.</span></span> <span data-ttu-id="609ea-149">La page de destination du générateur de site affiche une vue au niveau du client.</span><span class="sxs-lookup"><span data-stu-id="609ea-149">The site builder landing page displays a tenant-level view.</span></span> <span data-ttu-id="609ea-150">Depuis cette page, vous pouvez effectuer les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="609ea-150">From this page, you can:</span></span>

- <span data-ttu-id="609ea-151">Modifier les paramètres au niveau du client.</span><span class="sxs-lookup"><span data-stu-id="609ea-151">Modify tenant-level settings.</span></span>
- <span data-ttu-id="609ea-152">Accéder à n'importe quel site que vous avez créé et avoir la permission de l'afficher.</span><span class="sxs-lookup"><span data-stu-id="609ea-152">Navigate to any site you have created, and have permission to view.</span></span> 
- <span data-ttu-id="609ea-153">Accéder aux fonctionnalités d'évaluation telles que la modération et le compte-rendu.</span><span class="sxs-lookup"><span data-stu-id="609ea-153">Access Reviews features such as moderation and reporting.</span></span>
- <span data-ttu-id="609ea-154">Créer un site.</span><span class="sxs-lookup"><span data-stu-id="609ea-154">Create a new site.</span></span> <span data-ttu-id="609ea-155">Pour plus d'informations sur la création d'un site, voir [Création d'un site d'e-commerce](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="609ea-155">For more information about how to create a new site, see [Create an e-commerce site](create-ecommerce-site.md) .</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="609ea-156">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="609ea-156">Additional resources</span></span>

[<span data-ttu-id="609ea-157">Configuration du nom de domaine</span><span class="sxs-lookup"><span data-stu-id="609ea-157">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="609ea-158">Créer un site d’e-commerce</span><span class="sxs-lookup"><span data-stu-id="609ea-158">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="609ea-159">Associer un site Dynamics 365 Commerce avec un canal en ligne</span><span class="sxs-lookup"><span data-stu-id="609ea-159">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="609ea-160">Gérer les fichiers robots.txt</span><span class="sxs-lookup"><span data-stu-id="609ea-160">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="609ea-161">Importer des redirections d’URL en bloc</span><span class="sxs-lookup"><span data-stu-id="609ea-161">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="609ea-162">Configurer un client B2C dans Commerce</span><span class="sxs-lookup"><span data-stu-id="609ea-162">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="609ea-163">Paramétrer des pages personnalisées pour les ouvertures de session utilisateur</span><span class="sxs-lookup"><span data-stu-id="609ea-163">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="609ea-164">Configurer plusieurs locataires B2C dans un environnement Commerce</span><span class="sxs-lookup"><span data-stu-id="609ea-164">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="609ea-165">Ajouter la prise en charge d’un réseau de diffusion de contenu (CDN)</span><span class="sxs-lookup"><span data-stu-id="609ea-165">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="609ea-166">Activation de la détection du magasin selon l’emplacement</span><span class="sxs-lookup"><span data-stu-id="609ea-166">Enable location-based store detection</span></span>](enable-store-detection.md)
