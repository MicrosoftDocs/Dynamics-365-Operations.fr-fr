---
title: Déploiement d'un nouveau client de commerce électronique
description: Cette rubrique décrit la procédure de déploiement d'un client de commerce électronique à l'aide de Microsoft Dynamics Lifecycle Services (LCS).
author: psimolin
manager: annbe
ms.date: 03/02/2020
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
ms.openlocfilehash: d5cf2804c44e81ad135a3248d38c228148b530cc
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096676"
---
# <a name="deploy-a-new-e-commerce-tenant"></a><span data-ttu-id="8c355-103">Déploiement d'un nouveau client de commerce électronique</span><span class="sxs-lookup"><span data-stu-id="8c355-103">Deploy a new e-Commerce tenant</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="8c355-104">Cette rubrique décrit la procédure de déploiement d'un site de commerce électronique à l'aide de Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="8c355-104">This topic describes how to deploy a new e-Commerce site by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="overview"></a><span data-ttu-id="8c355-105">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="8c355-105">Overview</span></span>

<span data-ttu-id="8c355-106">Microsoft Dynamics Lifecycle Services (LCS) est un espace de travail de collaboration basé sur le cloud que les partenaires et les clients peuvent utiliser pour gérer leurs projets et environnements, afficher les dernières informations sur les produits et les fonctionnalités Microsoft Dynamics, et créer, effectuer le suivi, et consulter les incidents de support.</span><span class="sxs-lookup"><span data-stu-id="8c355-106">Microsoft Dynamics Lifecycle Services (LCS) is a cloud-based collaborative workspace that partners and customers can use to manage their projects and environments, view the latest information about Microsoft Dynamics products and features, and create, track, and browse support incidents.</span></span> <span data-ttu-id="8c355-107">Les fonctionnalités de gestion de commerce électronique sont intégrées à LCS.</span><span class="sxs-lookup"><span data-stu-id="8c355-107">E-Commerce management features are integrated into LCS.</span></span>

<span data-ttu-id="8c355-108">Pour en savoir plus sur LCS, voir [Guide de l'utilisateur de Lifecycle Services](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span><span class="sxs-lookup"><span data-stu-id="8c355-108">To learn more about LCS, see the [Lifecycle Services User Guide](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span></span>
    
## <a name="get-started"></a><span data-ttu-id="8c355-109">Mise en route</span><span class="sxs-lookup"><span data-stu-id="8c355-109">Get started</span></span>

<span data-ttu-id="8c355-110">Avant d'initialiser le commerce électronique, vous devez initialiser un projet, un environnement, et une Retail Cloud Scale Unit (RCSU).</span><span class="sxs-lookup"><span data-stu-id="8c355-110">Before you can initialize e-Commerce, you must initialize a project, an environment, and a Retail Cloud Scale Unit (RCSU).</span></span> <span data-ttu-id="8c355-111">Pour effectuer l'initialisation dans LCS, vous devez disposer des autorisations du rôle de Propriétaire du projet ou de Gestionnaire de l'environnement.</span><span class="sxs-lookup"><span data-stu-id="8c355-111">To do the initialization in LCS, you must have permissions for either the Project Owner or Environment manager role.</span></span> <span data-ttu-id="8c355-112">Les topologies d'environnement de production et bac à sable sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="8c355-112">The production and sandbox environment topologies are supported.</span></span>

<span data-ttu-id="8c355-113">Pour plus d'informations sur les environnements, voir [Planification de l'environnement](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span><span class="sxs-lookup"><span data-stu-id="8c355-113">For more information about environments, see [Environment planning](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span></span> <span data-ttu-id="8c355-114">Pour plus d'informations sur la conformité RCSU, voir [Initialiser Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="8c355-114">For more information about RCSU, see [Initialize Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span></span>

## <a name="initialize-e-commerce"></a><span data-ttu-id="8c355-115">Initialiser e-Commerce</span><span class="sxs-lookup"><span data-stu-id="8c355-115">Initialize e-Commerce</span></span>

<span data-ttu-id="8c355-116">Cette procédure permet d'initialiser la fonctionnalité de commerce électronique dans un environnement existant.</span><span class="sxs-lookup"><span data-stu-id="8c355-116">Use this procedure to initialize the e-Commerce feature in an existing environment.</span></span>

<span data-ttu-id="8c355-117">Avant de commencer, vérifiez que vous avez les informations requises suivantes :</span><span class="sxs-lookup"><span data-stu-id="8c355-117">Before you begin, make sure that you have the following required information:</span></span>

- <span data-ttu-id="8c355-118">La RCSU qui sera utilisée.</span><span class="sxs-lookup"><span data-stu-id="8c355-118">The RCSU that will be used.</span></span>
- <span data-ttu-id="8c355-119">Le groupe de sécurité Microsoft Azure Active Directory qui sera utilisé pour les administrateurs système de commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="8c355-119">The Microsoft Azure Active Directory security group that will be used for e-Commerce system admins.</span></span>
- <span data-ttu-id="8c355-120">Le groupe de sécurité Microsoft Azure Active Directory qui sera utilisé pour les modérateurs des classements et évaluations.</span><span class="sxs-lookup"><span data-stu-id="8c355-120">The Microsoft Azure Active Directory security group that will be used for ratings and reviews moderators.</span></span>
- <span data-ttu-id="8c355-121">Les domaines qui seront associés à l'environnement.</span><span class="sxs-lookup"><span data-stu-id="8c355-121">The domains that will be associated with the environment.</span></span>

<span data-ttu-id="8c355-122">En outre, vous pouvez collecter les informations facultatives suivantes :</span><span class="sxs-lookup"><span data-stu-id="8c355-122">In addition, you can collect the following optional information:</span></span>

- <span data-ttu-id="8c355-123">Informations entreprise-client (B2C) Azure AD :</span><span class="sxs-lookup"><span data-stu-id="8c355-123">Azure AD business-to-consumer (B2C) information:</span></span>

    - <span data-ttu-id="8c355-124">Nom du client.</span><span class="sxs-lookup"><span data-stu-id="8c355-124">Tenant Name.</span></span>
    - <span data-ttu-id="8c355-125">ID client.</span><span class="sxs-lookup"><span data-stu-id="8c355-125">Client ID.</span></span>
    - <span data-ttu-id="8c355-126">Domaine personnalisé de connexion.</span><span class="sxs-lookup"><span data-stu-id="8c355-126">Login Custom Domain.</span></span>
    - <span data-ttu-id="8c355-127">URL de réponse.</span><span class="sxs-lookup"><span data-stu-id="8c355-127">Reply URL.</span></span>
    - <span data-ttu-id="8c355-128">ID stratégie Inscription Connexion.</span><span class="sxs-lookup"><span data-stu-id="8c355-128">SignUp SignIn Policy ID.</span></span>
    - <span data-ttu-id="8c355-129">ID stratégie de réinitialisation du mot de passe.</span><span class="sxs-lookup"><span data-stu-id="8c355-129">Reset password Policy ID.</span></span>
    - <span data-ttu-id="8c355-130">Modifiez l'ID stratégie de profil.</span><span class="sxs-lookup"><span data-stu-id="8c355-130">Edit Profile Policy ID.</span></span>

[!NOTE]
<span data-ttu-id="8c355-131">Ces informations peuvent être ajoutées ultérieurement, via une demande de service.</span><span class="sxs-lookup"><span data-stu-id="8c355-131">This information can be added later, through a service request.</span></span>

<span data-ttu-id="8c355-132">Après avoir collecté les informations requises, procédez comme suit pour initialiser le commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="8c355-132">After you've collected the required information, follow these steps to initialize e-Commerce.</span></span>

1. <span data-ttu-id="8c355-133">Connectez-vous à [LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="8c355-133">Sign in to [LCS](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="8c355-134">Ouvrir le projet contenant l'environnement dans lequel vous souhaitez initialiser le commerce électronique.</span><span class="sxs-lookup"><span data-stu-id="8c355-134">Open the project that contains the environment where you want to initialize e-Commerce.</span></span>
1. <span data-ttu-id="8c355-135">Dans la section **Environnements**, sélectionnez l'environnement.</span><span class="sxs-lookup"><span data-stu-id="8c355-135">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="8c355-136">Sous **Fonctionnalités de l'environnement**, sélectionnez le lien **Gestion de la vente au détail**.</span><span class="sxs-lookup"><span data-stu-id="8c355-136">Under **Environment features**, select the **Retail manage** link.</span></span>
1. <span data-ttu-id="8c355-137">Dans l'onglet **commerce électronique**, sélectionnez **Paramétrage**.</span><span class="sxs-lookup"><span data-stu-id="8c355-137">On the **e-Commerce** tab, select **Setup**.</span></span> <span data-ttu-id="8c355-138">Une boîte de dialogue s'affiche, dans laquelle vous devez entrer les informations requises pour la mise en service.</span><span class="sxs-lookup"><span data-stu-id="8c355-138">A dialog box appears, where you must enter the information that is required for provisioning.</span></span>
1. <span data-ttu-id="8c355-139">Entrez les informations requises, puis passez à la page suivante.</span><span class="sxs-lookup"><span data-stu-id="8c355-139">Fill in the required information, and then go to the next page.</span></span>
1. <span data-ttu-id="8c355-140">Sur la page suivante, entrez les informations requises, puis envoyez le formulaire.</span><span class="sxs-lookup"><span data-stu-id="8c355-140">On the next page, fill in the required information, and then submit the form.</span></span> <span data-ttu-id="8c355-141">Vous êtes redirigé vers l'onglet **Commerce électronique**, sous lequel vous devez vérifier que l'initialisation a commencé.</span><span class="sxs-lookup"><span data-stu-id="8c355-141">You're returned to the **e-Commerce** tab, where you should see that initialization has been started.</span></span>
1. <span data-ttu-id="8c355-142">Pour afficher le statut de l'initialisation, **Actualisez** ou revenez à l'onglet **commerce électronique** ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="8c355-142">To view the initialization status, either **Refresh** or return to the **e-Commerce** tab later.</span></span>
    
<span data-ttu-id="8c355-143">Lorsque le commerce électronique est initialisé par LCS, le système met en service plusieurs composants requis pour le commerce électronique et les associe à l'environnement.</span><span class="sxs-lookup"><span data-stu-id="8c355-143">When e-Commerce is initialized from LCS, the system provisions several components that are required for e-Commerce and associates them with the environment.</span></span> <span data-ttu-id="8c355-144">Après la mise en service, l'onglet **Commerce électronique** sur la page **Gestion de la vente au détail** est mis à jour pour refléter la mise en service.</span><span class="sxs-lookup"><span data-stu-id="8c355-144">After provisioning is complete, the **e-Commerce** tab on the **Retail management** page is updated to reflect the provisioning.</span></span> <span data-ttu-id="8c355-145">La page présente les derniers déploiements de personnalisation et le statut de tout autre déploiements en cours.</span><span class="sxs-lookup"><span data-stu-id="8c355-145">The page shows the latest customization deployments and the status of any other ongoing deployments.</span></span> <span data-ttu-id="8c355-146">Elle contient également des liens vers le site de commerce électronique et le générateur de site de commerce électronique où les sites sont créés.</span><span class="sxs-lookup"><span data-stu-id="8c355-146">It also includes links to the e-Commerce site and the e-Commerce site builder where sites are authored.</span></span>

## <a name="access-site-builder"></a><span data-ttu-id="8c355-147">Accéder au générateur de site</span><span class="sxs-lookup"><span data-stu-id="8c355-147">Access site builder</span></span>

<span data-ttu-id="8c355-148">Pour accéder au générateur de site, accédez à l'onglet **Commerce électronique** dans la page **Gestion de vente au détail** dans LCS et sélectionnez le lien **Outil de gestion de site de commerce électronique**.</span><span class="sxs-lookup"><span data-stu-id="8c355-148">To access site builder, go to the **e-Commerce** tab on the **Retail management** page in LCS and select the **e-Commerce site management tool** link.</span></span> <span data-ttu-id="8c355-149">La page de destination du générateur de site affiche une vue au niveau du client.</span><span class="sxs-lookup"><span data-stu-id="8c355-149">The site builder landing page displays a tenant-level view.</span></span> <span data-ttu-id="8c355-150">Depuis cette page, vous pouvez effectuer les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="8c355-150">From this page, you can:</span></span>

- <span data-ttu-id="8c355-151">Modifier les paramètres au niveau du client.</span><span class="sxs-lookup"><span data-stu-id="8c355-151">Modify tenant-level settings.</span></span>
- <span data-ttu-id="8c355-152">Accéder à n'importe quel site que vous avez créé et avoir la permission de l'afficher.</span><span class="sxs-lookup"><span data-stu-id="8c355-152">Navigate to any site you have created, and have permission to view.</span></span> 
- <span data-ttu-id="8c355-153">Accéder aux fonctionnalités d'évaluation telles que la modération et le compte-rendu.</span><span class="sxs-lookup"><span data-stu-id="8c355-153">Access Reviews features such as moderation and reporting.</span></span>
- <span data-ttu-id="8c355-154">Créer un site.</span><span class="sxs-lookup"><span data-stu-id="8c355-154">Create a new site.</span></span> <span data-ttu-id="8c355-155">Pour plus d'informations sur la création d'un site, voir [Création d'un site de commerce électronique](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="8c355-155">For more information about how to create a new site, see [Create an e-Commerce site](create-ecommerce-site.md) .</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="8c355-156">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="8c355-156">Additional resources</span></span>

[<span data-ttu-id="8c355-157">Configuration du nom de domaine</span><span class="sxs-lookup"><span data-stu-id="8c355-157">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="8c355-158">Création d'un site de commerce électronique</span><span class="sxs-lookup"><span data-stu-id="8c355-158">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="8c355-159">Paramétrer un canal de magasin en ligne</span><span class="sxs-lookup"><span data-stu-id="8c355-159">Set up an online store channel</span></span>](online-stores.md)

[<span data-ttu-id="8c355-160">Association d'un site en ligne avec un canal</span><span class="sxs-lookup"><span data-stu-id="8c355-160">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="8c355-161">Gérer les fichiers robots.txt</span><span class="sxs-lookup"><span data-stu-id="8c355-161">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="8c355-162">Importer des redirections d'URL en bloc</span><span class="sxs-lookup"><span data-stu-id="8c355-162">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="8c355-163">Configurer un client B2C dans Commerce</span><span class="sxs-lookup"><span data-stu-id="8c355-163">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="8c355-164">Paramétrer des pages personnalisées pour les ouvertures de session utilisateur</span><span class="sxs-lookup"><span data-stu-id="8c355-164">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="8c355-165">Configurer plusieurs locataires B2C dans un environnement Commerce</span><span class="sxs-lookup"><span data-stu-id="8c355-165">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="8c355-166">Ajouter la prise en charge d'un réseau de diffusion de contenu (CDN)</span><span class="sxs-lookup"><span data-stu-id="8c355-166">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="8c355-167">Activation de la détection du magasin selon l’emplacement</span><span class="sxs-lookup"><span data-stu-id="8c355-167">Enable location-based store detection</span></span>](enable-store-detection.md)
