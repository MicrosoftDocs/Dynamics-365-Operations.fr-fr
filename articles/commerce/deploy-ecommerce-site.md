---
title: Déployer un nouveau client e-commerce
description: Cette rubrique décrit la procédure de déploiement d’un nouveau site d’e-commerce Dynamics 365 Commerce à l’aide de Microsoft Dynamics Lifecycle Services (LCS).
author: psimolin
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0fff5d47d6eb3e08288d17853fcd94f9eab843c3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801947"
---
# <a name="deploy-a-new-e-commerce-tenant"></a><span data-ttu-id="07bb0-103">Déployer un nouveau client e-commerce</span><span class="sxs-lookup"><span data-stu-id="07bb0-103">Deploy a new e-commerce tenant</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="07bb0-104">Cette rubrique décrit la procédure de déploiement d’un nouveau site d’e-commerce Dynamics 365 Commerce à l’aide de Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="07bb0-104">This topic describes how to deploy a new Dynamics 365 Commerce e-commerce site by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="07bb0-105">Microsoft Dynamics Lifecycle Services (LCS) est un espace de travail de collaboration basé sur le cloud que les partenaires et les clients peuvent utiliser pour gérer leurs projets et environnements, afficher les dernières informations sur les produits et les fonctionnalités Microsoft Dynamics, et créer, effectuer le suivi, et consulter les incidents de support.</span><span class="sxs-lookup"><span data-stu-id="07bb0-105">Microsoft Dynamics Lifecycle Services (LCS) is a cloud-based collaborative workspace that partners and customers can use to manage their projects and environments, view the latest information about Microsoft Dynamics products and features, and create, track, and browse support incidents.</span></span> <span data-ttu-id="07bb0-106">Les fonctionnalités de gestion d’e-commerce sont intégrées à LCS.</span><span class="sxs-lookup"><span data-stu-id="07bb0-106">E-commerce management features are integrated into LCS.</span></span>

<span data-ttu-id="07bb0-107">Pour en savoir plus sur LCS, voir [Guide de l’utilisateur de Lifecycle Services](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span><span class="sxs-lookup"><span data-stu-id="07bb0-107">To learn more about LCS, see the [Lifecycle Services User Guide](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span></span>
    
## <a name="get-started"></a><span data-ttu-id="07bb0-108">Mise en route</span><span class="sxs-lookup"><span data-stu-id="07bb0-108">Get started</span></span>

<span data-ttu-id="07bb0-109">Avant d’initialiser l’e-commerce, vous devez initialiser un projet, un environnement, et une Retail Cloud Scale Unit (RCSU).</span><span class="sxs-lookup"><span data-stu-id="07bb0-109">Before you can initialize e-commerce, you must initialize a project, an environment, and a Retail Cloud Scale Unit (RCSU).</span></span> <span data-ttu-id="07bb0-110">Pour effectuer l’initialisation dans LCS, vous devez disposer des autorisations du rôle de Propriétaire du projet ou de Gestionnaire de l’environnement.</span><span class="sxs-lookup"><span data-stu-id="07bb0-110">To do the initialization in LCS, you must have permissions for either the Project Owner or Environment manager role.</span></span> <span data-ttu-id="07bb0-111">Les topologies d’environnement de production et bac à sable sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="07bb0-111">The production and sandbox environment topologies are supported.</span></span>

<span data-ttu-id="07bb0-112">Pour plus d’informations sur les environnements, voir [Planification de l’environnement](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span><span class="sxs-lookup"><span data-stu-id="07bb0-112">For more information about environments, see [Environment planning](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span></span> <span data-ttu-id="07bb0-113">Pour plus d’informations sur la conformité RCSU, voir [Initialiser Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="07bb0-113">For more information about RCSU, see [Initialize Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span></span>

## <a name="initialize-e-commerce"></a><span data-ttu-id="07bb0-114">Initialiser l’e-commerce</span><span class="sxs-lookup"><span data-stu-id="07bb0-114">Initialize e-commerce</span></span>

<span data-ttu-id="07bb0-115">Cette procédure permet d’initialiser la fonctionnalité d’e-commerce dans un environnement existant.</span><span class="sxs-lookup"><span data-stu-id="07bb0-115">Use this procedure to initialize the e-commerce feature in an existing environment.</span></span>

<span data-ttu-id="07bb0-116">Avant de commencer, vérifiez que vous avez les informations requises suivantes :</span><span class="sxs-lookup"><span data-stu-id="07bb0-116">Before you begin, make sure that you have the following required information:</span></span>

- <span data-ttu-id="07bb0-117">La RCSU qui sera utilisée.</span><span class="sxs-lookup"><span data-stu-id="07bb0-117">The RCSU that will be used.</span></span>
- <span data-ttu-id="07bb0-118">Le groupe de sécurité Microsoft Azure Active Directory qui sera utilisé pour les administrateurs système d’e-commerce.</span><span class="sxs-lookup"><span data-stu-id="07bb0-118">The Microsoft Azure Active Directory security group that will be used for e-commerce system admins.</span></span>
- <span data-ttu-id="07bb0-119">Le groupe de sécurité Microsoft Azure Active Directory qui sera utilisé pour les modérateurs des classements et évaluations.</span><span class="sxs-lookup"><span data-stu-id="07bb0-119">The Microsoft Azure Active Directory security group that will be used for ratings and reviews moderators.</span></span>
- <span data-ttu-id="07bb0-120">Les domaines qui seront associés à l’environnement.</span><span class="sxs-lookup"><span data-stu-id="07bb0-120">The domains that will be associated with the environment.</span></span>

<span data-ttu-id="07bb0-121">En outre, vous pouvez collecter les informations facultatives suivantes :</span><span class="sxs-lookup"><span data-stu-id="07bb0-121">In addition, you can collect the following optional information:</span></span>

- <span data-ttu-id="07bb0-122">Informations entreprise-client (B2C) Azure AD :</span><span class="sxs-lookup"><span data-stu-id="07bb0-122">Azure AD business-to-consumer (B2C) information:</span></span>

    - <span data-ttu-id="07bb0-123">Nom du client.</span><span class="sxs-lookup"><span data-stu-id="07bb0-123">Tenant Name.</span></span>
    - <span data-ttu-id="07bb0-124">ID client.</span><span class="sxs-lookup"><span data-stu-id="07bb0-124">Client ID.</span></span>
    - <span data-ttu-id="07bb0-125">Domaine personnalisé de connexion.</span><span class="sxs-lookup"><span data-stu-id="07bb0-125">Login Custom Domain.</span></span>
    - <span data-ttu-id="07bb0-126">URL de réponse.</span><span class="sxs-lookup"><span data-stu-id="07bb0-126">Reply URL.</span></span>
    - <span data-ttu-id="07bb0-127">ID stratégie Inscription Connexion.</span><span class="sxs-lookup"><span data-stu-id="07bb0-127">SignUp SignIn Policy ID.</span></span>
    - <span data-ttu-id="07bb0-128">ID stratégie de réinitialisation du mot de passe.</span><span class="sxs-lookup"><span data-stu-id="07bb0-128">Reset password Policy ID.</span></span>
    - <span data-ttu-id="07bb0-129">Modifiez l’ID stratégie de profil.</span><span class="sxs-lookup"><span data-stu-id="07bb0-129">Edit Profile Policy ID.</span></span>

> [!NOTE]
> <span data-ttu-id="07bb0-130">Ces informations peuvent être ajoutées ultérieurement, via une demande de service.</span><span class="sxs-lookup"><span data-stu-id="07bb0-130">This information can be added later, through a service request.</span></span>

<span data-ttu-id="07bb0-131">Après avoir collecté les informations requises, procédez comme suit pour initialiser l’e-commerce.</span><span class="sxs-lookup"><span data-stu-id="07bb0-131">After you've collected the required information, follow these steps to initialize e-commerce.</span></span>

1. <span data-ttu-id="07bb0-132">Connectez-vous à [LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="07bb0-132">Sign in to [LCS](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="07bb0-133">Ouvrir le projet contenant l’environnement dans lequel vous souhaitez initialiser l’e-commerce.</span><span class="sxs-lookup"><span data-stu-id="07bb0-133">Open the project that contains the environment where you want to initialize e-commerce.</span></span>
1. <span data-ttu-id="07bb0-134">Dans la section **Environnements**, sélectionnez l’environnement.</span><span class="sxs-lookup"><span data-stu-id="07bb0-134">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="07bb0-135">Sous **Fonctionnalités de l’environnement**, sélectionnez le lien **Gestion de la vente au détail**.</span><span class="sxs-lookup"><span data-stu-id="07bb0-135">Under **Environment features**, select the **Retail manage** link.</span></span>
1. <span data-ttu-id="07bb0-136">Dans l’onglet **commerce électronique**, sélectionnez **Paramétrage**.</span><span class="sxs-lookup"><span data-stu-id="07bb0-136">On the **e-Commerce** tab, select **Setup**.</span></span> <span data-ttu-id="07bb0-137">Une boîte de dialogue s’affiche, dans laquelle vous devez entrer les informations requises pour la mise en service.</span><span class="sxs-lookup"><span data-stu-id="07bb0-137">A dialog box appears, where you must enter the information that is required for provisioning.</span></span>
1. <span data-ttu-id="07bb0-138">Entrez les informations requises, puis passez à la page suivante.</span><span class="sxs-lookup"><span data-stu-id="07bb0-138">Fill in the required information, and then go to the next page.</span></span>
1. <span data-ttu-id="07bb0-139">Sur la page suivante, entrez les informations requises, puis envoyez le formulaire.</span><span class="sxs-lookup"><span data-stu-id="07bb0-139">On the next page, fill in the required information, and then submit the form.</span></span> <span data-ttu-id="07bb0-140">Vous êtes redirigé vers l’onglet **Commerce électronique**, sous lequel vous devez vérifier que l’initialisation a commencé.</span><span class="sxs-lookup"><span data-stu-id="07bb0-140">You're returned to the **e-Commerce** tab, where you should see that initialization has been started.</span></span>
1. <span data-ttu-id="07bb0-141">Pour afficher le statut de l’initialisation, **Actualisez** ou revenez à l’onglet **commerce électronique** ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="07bb0-141">To view the initialization status, either **Refresh** or return to the **e-Commerce** tab later.</span></span>
    
<span data-ttu-id="07bb0-142">Lorsque l’e-commerce est initialisé par LCS, le système met en service plusieurs composants requis pour l’e-commerce et les associe à l’environnement.</span><span class="sxs-lookup"><span data-stu-id="07bb0-142">When e-commerce is initialized from LCS, the system provisions several components that are required for e-commerce and associates them with the environment.</span></span> <span data-ttu-id="07bb0-143">Après la mise en service, l’onglet **Commerce électronique** sur la page **Gestion de la vente au détail** est mis à jour pour refléter la mise en service.</span><span class="sxs-lookup"><span data-stu-id="07bb0-143">After provisioning is complete, the **e-Commerce** tab on the **Retail management** page is updated to reflect the provisioning.</span></span> <span data-ttu-id="07bb0-144">La page présente les derniers déploiements de personnalisation et le statut de tout autre déploiements en cours.</span><span class="sxs-lookup"><span data-stu-id="07bb0-144">The page shows the latest customization deployments and the status of any other ongoing deployments.</span></span> <span data-ttu-id="07bb0-145">Elle contient également des liens vers le site d’e-commerce et le générateur de site d’e-commerce où les sites sont créés.</span><span class="sxs-lookup"><span data-stu-id="07bb0-145">It also includes links to the e-commerce site and the Commerce site builder where sites are authored.</span></span>

## <a name="access-commerce-site-builder"></a><span data-ttu-id="07bb0-146">Accéder au générateur de site Commerce</span><span class="sxs-lookup"><span data-stu-id="07bb0-146">Access Commerce site builder</span></span>

<span data-ttu-id="07bb0-147">Pour accéder au générateur de site Commerce, accédez à l’onglet **e-Commerce** dans la page **Gestion de vente au détail** dans LCS et sélectionnez le lien **Outil de gestion de site d’e-commerce**.</span><span class="sxs-lookup"><span data-stu-id="07bb0-147">To access Commerce site builder, go to the **e-Commerce** tab on the **Retail management** page in LCS and select the **e-Commerce site management tool** link.</span></span> <span data-ttu-id="07bb0-148">La page de destination du générateur de site affiche une vue au niveau du client.</span><span class="sxs-lookup"><span data-stu-id="07bb0-148">The site builder landing page displays a tenant-level view.</span></span> <span data-ttu-id="07bb0-149">Depuis cette page, vous pouvez effectuer les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="07bb0-149">From this page, you can:</span></span>

- <span data-ttu-id="07bb0-150">Modifier les paramètres au niveau du client.</span><span class="sxs-lookup"><span data-stu-id="07bb0-150">Modify tenant-level settings.</span></span>
- <span data-ttu-id="07bb0-151">Accéder à n’importe quel site que vous avez créé et avoir la permission de l’afficher.</span><span class="sxs-lookup"><span data-stu-id="07bb0-151">Navigate to any site you have created, and have permission to view.</span></span> 
- <span data-ttu-id="07bb0-152">Accéder aux fonctionnalités d’évaluation telles que la modération et le compte-rendu.</span><span class="sxs-lookup"><span data-stu-id="07bb0-152">Access Reviews features such as moderation and reporting.</span></span>
- <span data-ttu-id="07bb0-153">Créer un site.</span><span class="sxs-lookup"><span data-stu-id="07bb0-153">Create a new site.</span></span> <span data-ttu-id="07bb0-154">Pour plus d’informations sur la création d’un site, voir [Création d’un site d’e-commerce](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="07bb0-154">For more information about how to create a new site, see [Create an e-commerce site](create-ecommerce-site.md) .</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="07bb0-155">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="07bb0-155">Additional resources</span></span>

[<span data-ttu-id="07bb0-156">Configuration du nom de domaine</span><span class="sxs-lookup"><span data-stu-id="07bb0-156">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="07bb0-157">Créer un site d’e-commerce</span><span class="sxs-lookup"><span data-stu-id="07bb0-157">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="07bb0-158">Associer un site Dynamics 365 Commerce avec un canal en ligne</span><span class="sxs-lookup"><span data-stu-id="07bb0-158">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="07bb0-159">Gérer les fichiers robots.txt</span><span class="sxs-lookup"><span data-stu-id="07bb0-159">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="07bb0-160">Importer des redirections d’URL en bloc</span><span class="sxs-lookup"><span data-stu-id="07bb0-160">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="07bb0-161">Configurer un client B2C dans Commerce</span><span class="sxs-lookup"><span data-stu-id="07bb0-161">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="07bb0-162">Paramétrer des pages personnalisées pour les ouvertures de session utilisateur</span><span class="sxs-lookup"><span data-stu-id="07bb0-162">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="07bb0-163">Configurer plusieurs locataires B2C dans un environnement Commerce</span><span class="sxs-lookup"><span data-stu-id="07bb0-163">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="07bb0-164">Ajouter la prise en charge d’un réseau de diffusion de contenu (CDN)</span><span class="sxs-lookup"><span data-stu-id="07bb0-164">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="07bb0-165">Activation de la détection du magasin selon l’emplacement</span><span class="sxs-lookup"><span data-stu-id="07bb0-165">Enable location-based store detection</span></span>](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
