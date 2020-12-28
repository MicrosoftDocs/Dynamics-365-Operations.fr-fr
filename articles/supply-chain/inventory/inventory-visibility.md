---
title: Complément de visibilité de stock
description: Cette rubrique décrit comment installer et configurer le complément de visibilité de stock pour Dynamics 365 Supply Chain Management.
author: chuzheng
manager: tfehr
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 2976153a6a7e4b4130e8f7673ed128945aeabf65
ms.sourcegitcommit: 03c2e1717b31e4c17ee7bb9004d2ba8cf379a036
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/24/2020
ms.locfileid: "4625063"
---
# <a name="inventory-visibility-add-in"></a><span data-ttu-id="71e04-103">Complément de visibilité de stock</span><span class="sxs-lookup"><span data-stu-id="71e04-103">Inventory Visibility Add-in</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="71e04-104">Le complément de visibilité de stock est un microservice indépendant et hautement évolutif qui permet un suivi des stocks en temps réel, offrant ainsi une vue globale de la visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="71e04-104">The Inventory Visibility Add-in is an independent and highly scalable microservice that enables real-time on-hand inventory tracking, thus providing a global view of inventory visibility.</span></span>

<span data-ttu-id="71e04-105">Toutes les informations relatives à l'inventaire disponible sont exportées vers le service en temps quasi réel via une intégration SQL de bas niveau.</span><span class="sxs-lookup"><span data-stu-id="71e04-105">All information that relates to on-hand inventory is exported to the service in near real-time through low-level SQL integration.</span></span> <span data-ttu-id="71e04-106">Les systèmes externes accèdent au service via des API RESTful pour interroger les informations disponibles sur des ensembles de dimensions donnés, récupérant ainsi une liste des positions disponibles.</span><span class="sxs-lookup"><span data-stu-id="71e04-106">External systems access the service through RESTful APIs to query on-hand information on given sets of dimensions, thus retrieving a list of available on-hand positions.</span></span>

<span data-ttu-id="71e04-107">La visibilité du stock est un microservice basé sur Common Data Service, ce qui signifie que vous pouvez l'étendre en créant Power Apps et en appliquant Power BI pour fournir des fonctionnalités personnalisées pour répondre aux besoins de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="71e04-107">Inventory Visibility is a microservice built on the Common Data Service, which means you can extend it by building Power Apps and applying Power BI to provide customized functionality to meet your business requirements.</span></span> <span data-ttu-id="71e04-108">Il est également possible de mettre à niveau l'index pour effectuer des requêtes d'inventaire.</span><span class="sxs-lookup"><span data-stu-id="71e04-108">It is also possible to upgrade the index to do inventory queries.</span></span>

<span data-ttu-id="71e04-109">La visibilité du stock fournit des options de configuration qui lui permettent de s'intégrer à plusieurs systèmes tiers.</span><span class="sxs-lookup"><span data-stu-id="71e04-109">Inventory Visibility provides configuration options that let it integrate with multiple third-party systems.</span></span> <span data-ttu-id="71e04-110">Il prend en charge la dimension de stock normalisée, l'extensibilité personnalisée et les quantités calculées normalisées et configurables.</span><span class="sxs-lookup"><span data-stu-id="71e04-110">It supports the standardized inventory dimension, customized extensibility, and standardized, configurable calculated quantities.</span></span>

<span data-ttu-id="71e04-111">Cette rubrique décrit comment installer et configurer le complément de visibilité de stock pour Dynamics 365 Supply Chain Management, et comment utiliser son interface de programmation d'application (API).</span><span class="sxs-lookup"><span data-stu-id="71e04-111">This topic describes how to install and configure the Inventory Visibility Add-in for Dynamics 365 Supply Chain Management, and how to use its application programming interface (API).</span></span>

## <a name="install-the-inventory-visibility-add-in"></a><span data-ttu-id="71e04-112">Installer le complément de visibilité de stock</span><span class="sxs-lookup"><span data-stu-id="71e04-112">Install the Inventory Visibility Add-in</span></span>

<span data-ttu-id="71e04-113">Vous devez installer le complément de visibilité de stock à l'aide de Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="71e04-113">You need to install the Inventory Visibility Add-in using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="71e04-114">LCS est un portail de collaboration qui fournit un environnement et un ensemble de services régulièrement mis à jour qui vous aident à gérer le cycle de vie des applications de vos applications Dynamics 365 Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="71e04-114">LCS is a collaboration portal that provides an environment and a set of regularly updated services that help you manage the application lifecycle of your Dynamics 365 Finance and Operations apps.</span></span>

<span data-ttu-id="71e04-115">Pour plus d'informations, voir [Ressources Lifecycle Services](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span><span class="sxs-lookup"><span data-stu-id="71e04-115">For more information, see [Lifecycle Services resources](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span></span>

### <a name="prerequisites"></a><span data-ttu-id="71e04-116">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="71e04-116">Prerequisites</span></span>

<span data-ttu-id="71e04-117">Avant de pouvoir installer le complément Visibilité du stock, vous devez procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="71e04-117">Before you install the Inventory Visibility Add-in, you must do the following:</span></span>

- <span data-ttu-id="71e04-118">Obtenez un projet d'implémentation LCS avec au moins un environnement déployé.</span><span class="sxs-lookup"><span data-stu-id="71e04-118">Obtain an LCS implementation project with at least one environment deployed.</span></span>
- <span data-ttu-id="71e04-119">Générez les clés bêta de votre offre dans LCS.</span><span class="sxs-lookup"><span data-stu-id="71e04-119">Generate the beta keys for your offering in LCS.</span></span>
- <span data-ttu-id="71e04-120">Activez les clés bêta de votre offre pour votre utilisateur dans LCS.</span><span class="sxs-lookup"><span data-stu-id="71e04-120">Enable the beta keys for your offering for your user in LCS.</span></span>
- <span data-ttu-id="71e04-121">Contactez l'équipe produit de la visibilité du stock Microsoft et fournissez un ID d'environnement dans lequel vous souhaitez déployer le complément de visibilité de stock.</span><span class="sxs-lookup"><span data-stu-id="71e04-121">Contact the Microsoft Inventory Visibility product team and provide an environment ID where you want to deploy the Inventory Visibility Add-in.</span></span>

<span data-ttu-id="71e04-122">Si vous avez des questions sur ces conditions préalables, contactez l'équipe produit de visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="71e04-122">If you have any questions about these prerequisites, please contact the Inventory Visibility product team.</span></span>

### <a name="install-the-add-in"></a><a name="install-add-in"></a><span data-ttu-id="71e04-123">Installer le complément</span><span class="sxs-lookup"><span data-stu-id="71e04-123">Install the add-in</span></span>

<span data-ttu-id="71e04-124">Pour pouvoir installer le complément Visibilité du stock, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="71e04-124">To install the Inventory Visibility Add-in, do the following:</span></span>

1. <span data-ttu-id="71e04-125">Connectez-vous au portail [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="71e04-125">Sign in to the [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portal.</span></span>
1. <span data-ttu-id="71e04-126">Sur la page d'accueil, sélectionnez le projet dans lequel votre environnement est déployé.</span><span class="sxs-lookup"><span data-stu-id="71e04-126">On the home page, select the project where your environment is deployed.</span></span>
1. <span data-ttu-id="71e04-127">Sur la page du projet, sélectionnez l'environnement dans lequel vous souhaitez installer le complément.</span><span class="sxs-lookup"><span data-stu-id="71e04-127">On the project page, select the environment where you want to install the add-in.</span></span>
1. <span data-ttu-id="71e04-128">Sur la page d'environnement, faites défiler vers le bas jusqu'à ce que vous voyiez la section **Compléments d'environnement**.</span><span class="sxs-lookup"><span data-stu-id="71e04-128">On the environment page, scroll down until you see the **Environment add-ins** section.</span></span> <span data-ttu-id="71e04-129">Si la section n'est pas visible, assurez-vous que les clés bêta prérequises ont été entièrement traitées.</span><span class="sxs-lookup"><span data-stu-id="71e04-129">If the section isn't visible, make sure the prerequisite beta keys have been fully processed.</span></span>
1. <span data-ttu-id="71e04-130">Dans la section **Compléments de l'environnement**, sélectionnez **Installer un nouveau complément**.</span><span class="sxs-lookup"><span data-stu-id="71e04-130">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
    <span data-ttu-id="71e04-131">![Page de l'environnement dans LCS](media/inventory-visibility-environment.png "Page de l'environnement dans LCS")</span><span class="sxs-lookup"><span data-stu-id="71e04-131">![The environment page in LCS](media/inventory-visibility-environment.png "The environment page in LCS")</span></span>
1. <span data-ttu-id="71e04-132">Sélectionnez le lien **Installer un nouveau complément**.</span><span class="sxs-lookup"><span data-stu-id="71e04-132">Select the **Install a new add-in** link.</span></span> <span data-ttu-id="71e04-133">Une liste des compléments disponibles s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="71e04-133">A list of available add-ins opens.</span></span>
1. <span data-ttu-id="71e04-134">Sélectionnez **Service d'inventaire** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="71e04-134">Select **Inventory service** from the list.</span></span> <span data-ttu-id="71e04-135">(Notez que cela peut maintenant être répertorié comme **Complément de visibilité de stock pour Dynamics 365 Supply Chain Management**.)</span><span class="sxs-lookup"><span data-stu-id="71e04-135">(Note, this may now be listed as **Inventory Visibility Add-in for Dynamics 365 Supply Chain Management**.)</span></span>
1. <span data-ttu-id="71e04-136">Saisissez des valeurs pour les champs suivants pour votre environnement :</span><span class="sxs-lookup"><span data-stu-id="71e04-136">Enter values for the following fields for your environment:</span></span>

    - <span data-ttu-id="71e04-137">**ID application AAD**</span><span class="sxs-lookup"><span data-stu-id="71e04-137">**AAD application ID**</span></span>
    - <span data-ttu-id="71e04-138">**ID locataire AAD**</span><span class="sxs-lookup"><span data-stu-id="71e04-138">**AAD tenant ID**</span></span>

    <span data-ttu-id="71e04-139">![Ajouter dans la page de configuration](media/inventory-visibility-setup.png "Page de configuration de complément")</span><span class="sxs-lookup"><span data-stu-id="71e04-139">![Add in setup page](media/inventory-visibility-setup.png "Add-in setup page")</span></span>

1. <span data-ttu-id="71e04-140">Acceptez les termes et conditions en cochant la case **Termes et conditions**.</span><span class="sxs-lookup"><span data-stu-id="71e04-140">Agree to the terms and condition by selecting the **Terms and conditions** check box.</span></span>
1. <span data-ttu-id="71e04-141">Sélectionnez **Installer**.</span><span class="sxs-lookup"><span data-stu-id="71e04-141">Select **Install**.</span></span> <span data-ttu-id="71e04-142">Le statut du complément s'affichera comme **Installation en cours**.</span><span class="sxs-lookup"><span data-stu-id="71e04-142">The status of the add-in will show as **Installing**.</span></span> <span data-ttu-id="71e04-143">Une fois terminé, actualisez la page pour voir le statut changer en **Installé**.</span><span class="sxs-lookup"><span data-stu-id="71e04-143">When it's done, refresh the page to see the status change to **Installed**.</span></span>

### <a name="get-a-security-service-token"></a><span data-ttu-id="71e04-144">Obtenir un jeton de service de sécurité</span><span class="sxs-lookup"><span data-stu-id="71e04-144">Get a security service token</span></span>

<span data-ttu-id="71e04-145">Pour obtenir un jeton de service de sécurité, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="71e04-145">To get a security service token, do the following:</span></span>

1. <span data-ttu-id="71e04-146">Obtenir votre `aadToken` et appelez le point de terminaison : https://securityservice.operations365.dynamics.com/token.</span><span class="sxs-lookup"><span data-stu-id="71e04-146">Get your `aadToken` and call the endpoint: https://securityservice.operations365.dynamics.com/token.</span></span>
1. <span data-ttu-id="71e04-147">Remplacez le `client_assertion` dans le corps avec votre `aadToken`.</span><span class="sxs-lookup"><span data-stu-id="71e04-147">Replace the `client_assertion` in the body with your `aadToken`.</span></span>
1. <span data-ttu-id="71e04-148">Remplacez le contexte dans le corps par l'environnement dans lequel vous souhaitez déployer le complément.</span><span class="sxs-lookup"><span data-stu-id="71e04-148">Replace the context in the body with the environment where you want to deploy the add-in.</span></span>
1. <span data-ttu-id="71e04-149">Remplacez la portée dans le corps par ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="71e04-149">Replace the scope in the body with the following:</span></span>

    - <span data-ttu-id="71e04-150">Portée pour MCK – « https://inventoryservice.operations365.dynamics.cn/.default »</span><span class="sxs-lookup"><span data-stu-id="71e04-150">Scope for MCK - "https://inventoryservice.operations365.dynamics.cn/.default"</span></span>  
    <span data-ttu-id="71e04-151">(Vous pouvez trouver ID d'application et ID de locataire Azure Active Directory pour MCK dans `appsettings.mck.json`.)</span><span class="sxs-lookup"><span data-stu-id="71e04-151">(You can find the Azure Active Directory application ID and tenant ID for MCK in `appsettings.mck.json`.)</span></span>
    - <span data-ttu-id="71e04-152">Portée pour PROD – « https://inventoryservice.operations365.dynamics.com/.default »</span><span class="sxs-lookup"><span data-stu-id="71e04-152">Scope for PROD - "https://inventoryservice.operations365.dynamics.com/.default"</span></span>  
    <span data-ttu-id="71e04-153">(Vous pouvez trouver ID d'application et ID de locataire Azure Active Directory pour PROD dans `appsettings.prod.json`.)</span><span class="sxs-lookup"><span data-stu-id="71e04-153">(You can find the Azure Active Directory application ID and tenant ID for PROD in `appsettings.prod.json`.)</span></span>

    <span data-ttu-id="71e04-154">Le résultat doit ressembler à l’exemple ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="71e04-154">The result should resemble the following example.</span></span>

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{**Your_AADToken**}",
        "scope":"**https://inventoryservice.operations365.dynamics.com/.default**",
        "context": "**5dbf6cc8-255e-4de2-8a25-2101cd5649b4**",
        "context_type": "finops-env"
    }
    ```

1. <span data-ttu-id="71e04-155">Vous obtiendrez un `access_token` en réponse.</span><span class="sxs-lookup"><span data-stu-id="71e04-155">You will get an `access_token` in response.</span></span> <span data-ttu-id="71e04-156">C'est ce dont vous avez besoin en tant que jeton de support pour appeler l'API de visibilité de stock.</span><span class="sxs-lookup"><span data-stu-id="71e04-156">This is what you need as a bearer token to call the Inventory Visibility API.</span></span> <span data-ttu-id="71e04-157">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="71e04-157">Here is an example.</span></span>

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="uninstall-the-add-in"></a><span data-ttu-id="71e04-158">Désinstaller le complément</span><span class="sxs-lookup"><span data-stu-id="71e04-158">Uninstall the add-in</span></span>

<span data-ttu-id="71e04-159">Pour désinstaller le complément, sélectionnez **Désinstaller**.</span><span class="sxs-lookup"><span data-stu-id="71e04-159">To uninstall the add-in, select **Uninstall**.</span></span> <span data-ttu-id="71e04-160">Actualiser LCS et le complément de visibilité de stock seront supprimés.</span><span class="sxs-lookup"><span data-stu-id="71e04-160">Refresh LCS and the Inventory Visibility Add-in will be removed.</span></span> <span data-ttu-id="71e04-161">Le processus de désinstallation supprimera l'inscription du complément et lancera également une tâche pour nettoyer toutes les données d'entreprise stockées dans le service.</span><span class="sxs-lookup"><span data-stu-id="71e04-161">The uninstall process will remove the add-in registration and also start a job to clean up all of the business data stored in the service.</span></span>

## <a name="inventory-visibility-add-in-public-api"></a><span data-ttu-id="71e04-162">API publique du complément de visibilité de stock</span><span class="sxs-lookup"><span data-stu-id="71e04-162">Inventory Visibility Add-in public API</span></span>

<span data-ttu-id="71e04-163">L'API REST publique du complément de visibilité de stock présente plusieurs points de terminaison d'intégration spécifiques.</span><span class="sxs-lookup"><span data-stu-id="71e04-163">The public REST API of the of the Inventory Visibility Add-in presents several specific endpoints of integration.</span></span> <span data-ttu-id="71e04-164">Elle prend en charge trois types d'interactions principaux :</span><span class="sxs-lookup"><span data-stu-id="71e04-164">It supports three main interaction types:</span></span>

- <span data-ttu-id="71e04-165">Publication des modifications disponibles du complément à partir d'un système externe.</span><span class="sxs-lookup"><span data-stu-id="71e04-165">Posting on-hand changes to the add-in from an external system.</span></span>
- <span data-ttu-id="71e04-166">Interrogation des quantités en stock actuelles à partir d'un système externe.</span><span class="sxs-lookup"><span data-stu-id="71e04-166">Querying current on-hand quantities from an external system.</span></span>
- <span data-ttu-id="71e04-167">Synchronisation automatique avec Supply Chain Management à portée de main.</span><span class="sxs-lookup"><span data-stu-id="71e04-167">Automatic synchronization with Supply Chain Management on-hand.</span></span>

<span data-ttu-id="71e04-168">La synchronisation automatique ne fait pas partie de l'API publique, mais est plutôt gérée en arrière-plan pour les environnements qui ont activé le complément de visibilité d'inventaire.</span><span class="sxs-lookup"><span data-stu-id="71e04-168">The automatic synchronization isn't part of the public API but is instead handled in the background for environments that have enabled the Inventory Visibility Add-in.</span></span>

### <a name="authentication"></a><span data-ttu-id="71e04-169">Authentification</span><span class="sxs-lookup"><span data-stu-id="71e04-169">Authentication</span></span>

<span data-ttu-id="71e04-170">Le jeton de sécurité de la plateforme est utilisé pour appeler le complément de visibilité d'inventaire, vous devez donc générer un jeton Azure Active Directory en utilisant votre application Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="71e04-170">The platform security token is used to call the Inventory Visibility Add-in, so you must generate an Azure Active Directory token using your Azure Active Directory application.</span></span>

<span data-ttu-id="71e04-171">Pour plus d'informations sur la façon d'obtenir le jeton de sécurité, consultez [Installer le complément de visibilité de stock](#install-add-in).</span><span class="sxs-lookup"><span data-stu-id="71e04-171">For more information about how to get the security token, see [Install the Inventory Visibility Add-in](#install-add-in).</span></span>

### <a name="configure-the-inventory-visibility-api"></a><span data-ttu-id="71e04-172">Configurer l'API de visibilité de stock</span><span class="sxs-lookup"><span data-stu-id="71e04-172">Configure the Inventory Visibility API</span></span>

<span data-ttu-id="71e04-173">Avant d'utiliser le service, vous devez effectuer les configurations décrites dans les sous-sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="71e04-173">Before using the service, you must complete the configurations described in the following subsections.</span></span> <span data-ttu-id="71e04-174">La configuration peut varier en fonction des détails de votre environnement.</span><span class="sxs-lookup"><span data-stu-id="71e04-174">The configuration may vary based on the details of your environment.</span></span> <span data-ttu-id="71e04-175">Il comprend principalement quatre parties :</span><span class="sxs-lookup"><span data-stu-id="71e04-175">It primarily includes four parts:</span></span>

- [<span data-ttu-id="71e04-176">Partitionnement</span><span class="sxs-lookup"><span data-stu-id="71e04-176">Partitioning</span></span>](#partitioning)
- [<span data-ttu-id="71e04-177">Configurations des dimensions</span><span class="sxs-lookup"><span data-stu-id="71e04-177">Dimension configurations</span></span>](#dimension-configurations)
- [<span data-ttu-id="71e04-178">Indexation</span><span class="sxs-lookup"><span data-stu-id="71e04-178">Indexing</span></span>](#indexing)
- [<span data-ttu-id="71e04-179">Mesure personnalisée</span><span class="sxs-lookup"><span data-stu-id="71e04-179">Custom measurement</span></span>](#custom-measurement)

#### <a name="partitioning"></a><span data-ttu-id="71e04-180">Partitionnement</span><span class="sxs-lookup"><span data-stu-id="71e04-180">Partitioning</span></span>

<span data-ttu-id="71e04-181">Le partitionnement peut influencer considérablement les performances de l'API de visibilité d'inventaire.</span><span class="sxs-lookup"><span data-stu-id="71e04-181">Partitioning can significantly influence the performance of the Inventory Visibility API.</span></span> <span data-ttu-id="71e04-182">C'est une bonne idée de définir un schéma qui permet de petits regroupements de données tout en permettant des requêtes de données significatives.</span><span class="sxs-lookup"><span data-stu-id="71e04-182">It's a good idea to define a scheme that allows for small groupings of data while still allowing for meaningful data queries.</span></span>

<span data-ttu-id="71e04-183">L'`organizationId` (`dataAreaId` dans Supply Chain Management) fera toujours partie du partitionnement et, par défaut, la visibilité du stock est définie pour partitionner par dimensions comme *Site + Localisation*.</span><span class="sxs-lookup"><span data-stu-id="71e04-183">The `organizationId` (`dataAreaId` in Supply Chain Management) will always be part of the partitioning, and by default Inventory Visibility is set to partition by dimensions as *Site + Location*.</span></span> <span data-ttu-id="71e04-184">Cela signifie que le service doit toujours être interrogé avec ces dimensions définies sur les filtres.</span><span class="sxs-lookup"><span data-stu-id="71e04-184">This means that the service must always be queried with these dimensions defined on the filters.</span></span>

> [!NOTE]
> <span data-ttu-id="71e04-185">*Site* et *Emplacement* sont deux dimensions générales par défaut dans la visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="71e04-185">*Site* and *Location* are two general default dimensions in Inventory Visibility.</span></span> <span data-ttu-id="71e04-186">Dans Supply Chain Management, ces dimensions sont appelées *Site* (`InventSiteId`) et *Entrepôt* (`InventLocationId`)</span><span class="sxs-lookup"><span data-stu-id="71e04-186">In Supply Chain Management, those dimensions are called *Site* (`InventSiteId`) and *Warehouse* (`InventLocationId`)</span></span>

### <a name="dimension-configurations"></a><span data-ttu-id="71e04-187">Configurations des dimensions</span><span class="sxs-lookup"><span data-stu-id="71e04-187">Dimension configurations</span></span>

<span data-ttu-id="71e04-188">La visibilité du stock fournira une liste de dimensions générales par défaut pour permettre l'intégration du système source multiple.</span><span class="sxs-lookup"><span data-stu-id="71e04-188">Inventory Visibility will provide a list of general default dimensions to enable the multiple source system integration.</span></span>

<span data-ttu-id="71e04-189">Le tableau suivant répertorie les dimensions d'inventaire qui seront les noms de dimension par défaut dans la visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="71e04-189">The following table lists the inventory dimensions that will be the default dimension names in Inventory Visibility.</span></span>

| <span data-ttu-id="71e04-190">Type de dimension</span><span class="sxs-lookup"><span data-stu-id="71e04-190">Dimension type</span></span> | <span data-ttu-id="71e04-191">Nom de dimension</span><span class="sxs-lookup"><span data-stu-id="71e04-191">Dimension name</span></span> |
|---|---|
| <span data-ttu-id="71e04-192">Produit</span><span class="sxs-lookup"><span data-stu-id="71e04-192">Product</span></span> | `ColorId` |
| <span data-ttu-id="71e04-193">Produit</span><span class="sxs-lookup"><span data-stu-id="71e04-193">Product</span></span> | `SizeId` |
| <span data-ttu-id="71e04-194">Produit</span><span class="sxs-lookup"><span data-stu-id="71e04-194">Product</span></span> | `StyleId` |
| <span data-ttu-id="71e04-195">Produit</span><span class="sxs-lookup"><span data-stu-id="71e04-195">Product</span></span> | `ConfigId` |
| <span data-ttu-id="71e04-196">Suivi</span><span class="sxs-lookup"><span data-stu-id="71e04-196">Tracking</span></span> | `BatchId` |
| <span data-ttu-id="71e04-197">Suivi</span><span class="sxs-lookup"><span data-stu-id="71e04-197">Tracking</span></span> | `SerialId` |
| <span data-ttu-id="71e04-198">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="71e04-198">Location</span></span> | `LocationId` |
| <span data-ttu-id="71e04-199">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="71e04-199">Location</span></span> | `SiteId` |
| <span data-ttu-id="71e04-200">Statut du stock</span><span class="sxs-lookup"><span data-stu-id="71e04-200">Inventory Status</span></span> | `StatusId` |
| <span data-ttu-id="71e04-201">Spécifique à l'entrepôt</span><span class="sxs-lookup"><span data-stu-id="71e04-201">Warehouse Specific</span></span> | `WMSLocationId` |
| <span data-ttu-id="71e04-202">Spécifique à l'entrepôt</span><span class="sxs-lookup"><span data-stu-id="71e04-202">Warehouse Specific</span></span> | `WMSPalletId` |
| <span data-ttu-id="71e04-203">Spécifique à l'entrepôt</span><span class="sxs-lookup"><span data-stu-id="71e04-203">Warehouse Specific</span></span> | `LicensePlateId` |

> [!NOTE]
> <span data-ttu-id="71e04-204">Le type de dimension répertorié dans le tableau précédent est à titre indicatif uniquement.</span><span class="sxs-lookup"><span data-stu-id="71e04-204">The dimension type listed in the previous table is for reference only.</span></span> <span data-ttu-id="71e04-205">Vous n'avez pas besoin de définir le type de dimension dans la visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="71e04-205">You don't need to define the dimension type in Inventory Visibility.</span></span>

<span data-ttu-id="71e04-206">Si une dimension personnalisée existe et doit passer à une valeur par défaut lorsqu'elle est utilisée par la visibilité du stock, vous pouvez configurer le nom **Dimension personnalisée** dans la visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="71e04-206">If a custom dimension exists and needs to flow to a default value when consumed by Inventory Visibility, you can configure the **Custom dimension** name in Inventory Visibility.</span></span>

<span data-ttu-id="71e04-207">Les systèmes externes accèdent à la visibilité du stock via des API RESTful qui permettent d'interroger des informations disponibles sur des ensembles de dimensions donnés.</span><span class="sxs-lookup"><span data-stu-id="71e04-207">External systems access Inventory Visibility through RESTful APIs that enable on-hand information on given sets of dimensions to be queried.</span></span> <span data-ttu-id="71e04-208">Pour l'intégration, la visibilité du stock vous permet de configurer la *source de données de canal externe* et la dimension source des *dimensions cibles* dans la visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="71e04-208">For the integration, Inventory Visibility enables you to configure the *external channel data source* and the source dimension to the *target dimensions* in Inventory Visibility.</span></span>

<span data-ttu-id="71e04-209">Les dimensions cibles doivent être l'une des suivantes :</span><span class="sxs-lookup"><span data-stu-id="71e04-209">The target dimensions should be one of the following:</span></span>

- <span data-ttu-id="71e04-210">Dimensions par défaut dans la visibilité du stock</span><span class="sxs-lookup"><span data-stu-id="71e04-210">Default dimensions in Inventory Visibility</span></span>
- <span data-ttu-id="71e04-211">Dimensions personnalisées</span><span class="sxs-lookup"><span data-stu-id="71e04-211">Custom dimensions</span></span>

<span data-ttu-id="71e04-212">Le but de la configuration des dimensions est de standardiser l'intégration multi-système pour la requête sur les dimensions et l'événement de publication avec les dimensions.</span><span class="sxs-lookup"><span data-stu-id="71e04-212">The purpose of dimension configuration is to standardize the multi-system integration for the query on dimensions and the posting event with dimensions.</span></span>

#### <a name="indexing"></a><span data-ttu-id="71e04-213">Indexation</span><span class="sxs-lookup"><span data-stu-id="71e04-213">Indexing</span></span>

<span data-ttu-id="71e04-214">La plupart du temps, la requête de stock disponible sera non seulement au niveau "total" le plus élevé, mais vous souhaiterez peut-être voir les résultats agrégés en fonction des dimensions de stock.</span><span class="sxs-lookup"><span data-stu-id="71e04-214">Most of the time, the inventory on-hand query will not only be on the highest "total" level, but you may want to see results aggregated based on the inventory dimensions.</span></span>

<span data-ttu-id="71e04-215">La visibilité du stock offre une certaine flexibilité en vous permettant de configurer les index, qui sont basés sur la dimension ou la combinaison des dimensions.</span><span class="sxs-lookup"><span data-stu-id="71e04-215">Inventory Visibility provides flexibility by allowing you to set up the indexes, which are based on the dimension or the combination of the dimensions.</span></span>

> [!NOTE]
> <span data-ttu-id="71e04-216">Actuellement, vous ne pouvez configurer les index que jusqu'à un maximum de cinq.</span><span class="sxs-lookup"><span data-stu-id="71e04-216">Currently, you can only configure indexes to a maximum of five.</span></span> <span data-ttu-id="71e04-217">Vous devez examiner attentivement la dimension ou la combinaison de dimensions que vous utiliserez avant la mise en œuvre pour vous assurer qu'elle répondra aux besoins de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="71e04-217">You need to carefully consider which dimension or dimension combination you will use before the implementation to ensure that it will meet your business needs.</span></span> <span data-ttu-id="71e04-218">Par exemple, si vous souhaitez interroger les produits comme suit :</span><span class="sxs-lookup"><span data-stu-id="71e04-218">For example, if you want to query products as follows:</span></span>

- <span data-ttu-id="71e04-219">Recherchez le produit agrégé disponible par les dimensions *Couleur* et *Taille*.</span><span class="sxs-lookup"><span data-stu-id="71e04-219">Query the aggregated product on-hand by the *Color* and *Size* dimensions.</span></span>
- <span data-ttu-id="71e04-220">Dans certains cas, vous souhaitez simplement interroger le produit au total.</span><span class="sxs-lookup"><span data-stu-id="71e04-220">In some cases, you just want to query on the product in total.</span></span>

<span data-ttu-id="71e04-221">Vous auriez deux index définis comme suit :</span><span class="sxs-lookup"><span data-stu-id="71e04-221">You would have two indexes defined as the following:</span></span>

- `["ColorId", "SizeId"]`
- `[]`

<span data-ttu-id="71e04-222">Le crochet vide sera agrégé en fonction de l'ID de produit dans la partition.</span><span class="sxs-lookup"><span data-stu-id="71e04-222">The empty bracket will aggregate based on the product ID within the partition.</span></span>

<span data-ttu-id="71e04-223">L'indexation définit comment vous pouvez regrouper vos résultats en fonction du paramètre de requête `groupBy`.</span><span class="sxs-lookup"><span data-stu-id="71e04-223">The indexing defines how you can group your results based on the `groupBy` query setting.</span></span> <span data-ttu-id="71e04-224">Dans ce cas, si vous ne définissez aucune valeur `groupBy`, vous obtiendrez les totaux par `productid`.</span><span class="sxs-lookup"><span data-stu-id="71e04-224">In this case if you don't define any `groupBy` values, you'll get totals by `productid`.</span></span> <span data-ttu-id="71e04-225">Sinon si vous définissez `groupBy` comme `groupBy=ColorId&groupBy=SizeId`, vous obtiendrez plusieurs lignes renvoyées, en fonction des différentes combinaisons de couleurs et de tailles du système.</span><span class="sxs-lookup"><span data-stu-id="71e04-225">Otherwise if you define `groupBy` as `groupBy=ColorId&groupBy=SizeId`, you'll get multiple lines returned, based on the different color and size combinations in the system.</span></span>

<span data-ttu-id="71e04-226">Vous pouvez mettre vos critères de requête dans le corps de la requête.</span><span class="sxs-lookup"><span data-stu-id="71e04-226">You can put your query criteria in the request body.</span></span>

<span data-ttu-id="71e04-227">Voici un exemple de requête sur le produit avec une combinaison de couleur et de taille.</span><span class="sxs-lookup"><span data-stu-id="71e04-227">Here is a sample query on the product with color and size combination.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="custom-measurement"></a><span data-ttu-id="71e04-228">Mesure personnalisée</span><span class="sxs-lookup"><span data-stu-id="71e04-228">Custom measurement</span></span>

<span data-ttu-id="71e04-229">Les quantités de mesure par défaut sont liées à Supply Chain Management, mais vous souhaiterez peut-être avoir une quantité composée d'une combinaison des mesures par défaut.</span><span class="sxs-lookup"><span data-stu-id="71e04-229">The default measurement quantities are linked to Supply Chain Management, however you may want to have a quantity that is made up of a combination of the default measurements.</span></span> <span data-ttu-id="71e04-230">Pour ce faire, vous pouvez avoir une configuration de quantités personnalisées, qui seront ajoutées à la sortie des requêtes en main.</span><span class="sxs-lookup"><span data-stu-id="71e04-230">To do this, you can have a configuration of custom quantities, which will be added to the output of the on-hand queries.</span></span>

<span data-ttu-id="71e04-231">La fonctionnalité vous permet simplement de définir un ensemble de mesures qui seront ajoutées, et/ou un ensemble de mesures qui seront soustraites, afin de la mesure personnalisée.</span><span class="sxs-lookup"><span data-stu-id="71e04-231">The functionality simply allows you to define a set of measures that will be added, and/or a set of measures that will be subtracted, in order to form the custom measurement.</span></span>

<span data-ttu-id="71e04-232">Par exemple, avec la condition de requête suivante, vous configurerez la quantité de mesure personnalisée comme `MyCustomAvailableforReservation` à consommer par le système de consommation.</span><span class="sxs-lookup"><span data-stu-id="71e04-232">For example, with the following query condition, you will configure the custom measurement quantity as `MyCustomAvailableforReservation` to be consumed by the consumption system.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]

```



| <span data-ttu-id="71e04-233">Système de consommation</span><span class="sxs-lookup"><span data-stu-id="71e04-233">Consumption system</span></span> | <span data-ttu-id="71e04-234">Mesures calculées</span><span class="sxs-lookup"><span data-stu-id="71e04-234">Calculated measurers</span></span> | <span data-ttu-id="71e04-235">Source de données</span><span class="sxs-lookup"><span data-stu-id="71e04-235">Data source</span></span> | <span data-ttu-id="71e04-236">Modificateur</span><span class="sxs-lookup"><span data-stu-id="71e04-236">Modifier</span></span> | <span data-ttu-id="71e04-237">Type de calcul du modificateur</span><span class="sxs-lookup"><span data-stu-id="71e04-237">Modifier calculation type</span></span> |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | <span data-ttu-id="71e04-238">Addition</span><span class="sxs-lookup"><span data-stu-id="71e04-238">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | <span data-ttu-id="71e04-239">Addition</span><span class="sxs-lookup"><span data-stu-id="71e04-239">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | <span data-ttu-id="71e04-240">Soustraction</span><span class="sxs-lookup"><span data-stu-id="71e04-240">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | <span data-ttu-id="71e04-241">Addition</span><span class="sxs-lookup"><span data-stu-id="71e04-241">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | <span data-ttu-id="71e04-242">Soustraction</span><span class="sxs-lookup"><span data-stu-id="71e04-242">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | <span data-ttu-id="71e04-243">Addition</span><span class="sxs-lookup"><span data-stu-id="71e04-243">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | <span data-ttu-id="71e04-244">Addition</span><span class="sxs-lookup"><span data-stu-id="71e04-244">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | <span data-ttu-id="71e04-245">Soustraction</span><span class="sxs-lookup"><span data-stu-id="71e04-245">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | <span data-ttu-id="71e04-246">Soustraction</span><span class="sxs-lookup"><span data-stu-id="71e04-246">Subtraction</span></span> |

<span data-ttu-id="71e04-247">Avec cela, la requête sur la quantité de mesure personnalisée renverra la sortie suivante.</span><span class="sxs-lookup"><span data-stu-id="71e04-247">With that, the query on the custom measurement quantity will return the following output.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

<span data-ttu-id="71e04-248">La sortie `MyCustomAvailableforReservation` est basée sur le paramètre de calcul dans les mesures personnalisées comme :</span><span class="sxs-lookup"><span data-stu-id="71e04-248">The `MyCustomAvailableforReservation` output is based on the calculation setting in the custom measurements as:</span></span>  
 <span data-ttu-id="71e04-249">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span><span class="sxs-lookup"><span data-stu-id="71e04-249">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span></span>

### <a name="posting-on-hand-changes"></a><span data-ttu-id="71e04-250">Publication des modifications en stock</span><span class="sxs-lookup"><span data-stu-id="71e04-250">Posting on-hand changes</span></span>

<span data-ttu-id="71e04-251">L'URL exacte sur laquelle l'événement sera publié dépendra de votre région géographique.</span><span class="sxs-lookup"><span data-stu-id="71e04-251">The exact URL that the event will be posted to will depend on your geographical region.</span></span> <span data-ttu-id="71e04-252">Il prendra la forme :</span><span class="sxs-lookup"><span data-stu-id="71e04-252">It will take the form:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand`

<span data-ttu-id="71e04-253">Une fois authentifiée, cette URL peut être utilisée avec la méthode HTTP `POST` pour envoyer des événements de modification en main au service.</span><span class="sxs-lookup"><span data-stu-id="71e04-253">When authenticated, this URL can be used along with the HTTP `POST` method to send on-hand change events to the service.</span></span>

<span data-ttu-id="71e04-254">Un en-tête spécial est utilisé pour communiquer avec les services Dynamics 365 via des requêtes HTTP, indiquant l'ID d'environnement de l'instance Supply Chain Management à laquelle les données sont liées.</span><span class="sxs-lookup"><span data-stu-id="71e04-254">A special header is used for communicating with Dynamics 365 services through HTTP requests, denoting the environment ID of the Supply Chain Management instance the data is linked to.</span></span> <span data-ttu-id="71e04-255">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="71e04-255">For example:</span></span>

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a><span data-ttu-id="71e04-256">Exemple de requête de publication de modifications en main 1</span><span class="sxs-lookup"><span data-stu-id="71e04-256">Posting on-hand changes query example 1</span></span>

<span data-ttu-id="71e04-257">Cet exemple montre un scénario dans lequel vous allez configurer la configuration de dimension dans Power Apps.</span><span class="sxs-lookup"><span data-stu-id="71e04-257">This example shows a scenario where you will set up the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="71e04-258">Utilisez la requête suivante pour configurer le mappage de dimension dans Power Apps :</span><span class="sxs-lookup"><span data-stu-id="71e04-258">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="71e04-259">Vous pouvez maintenant spécifier la `dimensionDataSource` et utilisez des dimensions personnalisées dans vos requêtes.</span><span class="sxs-lookup"><span data-stu-id="71e04-259">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="71e04-260">Le système convertira automatiquement les dimensions personnalisées en dimensions de base.</span><span class="sxs-lookup"><span data-stu-id="71e04-260">The system will automatically convert custom dimensions to base dimensions.</span></span>

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensionDataSource": "pos",
    "dimensions": {
        "PosSizeId": "Large",
        "PosColorId": "Red",
        "PosSiteId": "2",
        "PosLocationId": "21"
    }
}
```

#### <a name="posting-on-hand-changes-query-example-2"></a><span data-ttu-id="71e04-261">Exemple de requête de publication de modifications en main 2</span><span class="sxs-lookup"><span data-stu-id="71e04-261">Posting on-hand changes query example 2</span></span>

<span data-ttu-id="71e04-262">Cet exemple montre un scénario dans lequel aucun mappage n'est configuré pour la configuration de dimension dans Power Apps, donc la publication doit également utiliser les dimensions de base.</span><span class="sxs-lookup"><span data-stu-id="71e04-262">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="71e04-263">Toutes les dimensions doivent être des dimensions de base lorsque le champ `dimensionDataSource` est nul, vide ou espace.</span><span class="sxs-lookup"><span data-stu-id="71e04-263">All dimensions must be base dimensions when the `dimensionDataSource` field is null, empty, or whitespace.</span></span>

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensions": {
        "SizeId": "Large",
        "ColorId": "Red",
        "SiteId": "2",
        "LocationId": "21"
    }
}
```

#### <a name="json-document-field-properties"></a><span data-ttu-id="71e04-264">Propriétés du champs de documents JSON</span><span class="sxs-lookup"><span data-stu-id="71e04-264">JSON document field properties</span></span>

<span data-ttu-id="71e04-265">Les champs des exemples de requête JSON fournis précédemment ont les propriétés répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="71e04-265">The fields from the JSON query examples provided previously have the properties listed in the following table.</span></span>

| <span data-ttu-id="71e04-266">ID champ</span><span class="sxs-lookup"><span data-stu-id="71e04-266">Field ID</span></span> | <span data-ttu-id="71e04-267">Description</span><span class="sxs-lookup"><span data-stu-id="71e04-267">Description</span></span> |
|---|---|
| `id` | <span data-ttu-id="71e04-268">Un ID unique pour l'événement de modification spécifique.</span><span class="sxs-lookup"><span data-stu-id="71e04-268">A unique ID for the specific change event.</span></span> <span data-ttu-id="71e04-269">Cet ID est utilisé pour garantir qu'en cas d'échec de la communication avec le service pendant la comptabilisation, la soumission à nouveau de l'événement n'entraînerait pas le comptage du même événement deux fois dans le système.</span><span class="sxs-lookup"><span data-stu-id="71e04-269">This ID is used to ensure that if communication with the service fails during posting, resubmitting the event would not result in the same event being counted twice in the system.</span></span> |
| `organizationId` | <span data-ttu-id="71e04-270">L'identificateur de l'organisation liée à l'événement.</span><span class="sxs-lookup"><span data-stu-id="71e04-270">The identifier of the organization linked to the event.</span></span> <span data-ttu-id="71e04-271">Cela correspond aux organisations de gestion de Supply Chain Management ou aux ID de zone de données.</span><span class="sxs-lookup"><span data-stu-id="71e04-271">This maps to Supply Chain Management organizations or data area IDs.</span></span> |
| `productId` | <span data-ttu-id="71e04-272">Identificateur du produit en question.</span><span class="sxs-lookup"><span data-stu-id="71e04-272">The identifier of the product in question.</span></span> |
| `quantity` | <span data-ttu-id="71e04-273">La quantité dont le stock doit être changé.</span><span class="sxs-lookup"><span data-stu-id="71e04-273">The quantity by which the on-hand needs to be changed.</span></span> <span data-ttu-id="71e04-274">Si, par exemple, 10 nouveaux bagels étaient ajoutés à une étagère, cette valeur serait de 10.</span><span class="sxs-lookup"><span data-stu-id="71e04-274">If, for instance, 10 new bagels were added to a shelf, this value would be 10.</span></span> <span data-ttu-id="71e04-275">Si 3 bagels étaient ensuite retirés de l'étagère ou vendus, cette valeur serait de -3.</span><span class="sxs-lookup"><span data-stu-id="71e04-275">If 3 bagels were then removed from the shelf or sold, this value would be -3.</span></span> |
| `dimensionDataSource` | <span data-ttu-id="71e04-276">Source de données des dimensions utilisées dans l'événement et la requête de modification de publication.</span><span class="sxs-lookup"><span data-stu-id="71e04-276">The data source of the dimensions used in the posting change event and query.</span></span> <span data-ttu-id="71e04-277">Si vous spécifiez la source de données, vous pouvez utiliser les dimensions personnalisées de la source de données spécifiée.</span><span class="sxs-lookup"><span data-stu-id="71e04-277">If you specify the data source, you can use the custom dimensions from the specified data source.</span></span> <span data-ttu-id="71e04-278">Avec la configuration des dimensions, la visibilité du stock peut mapper les dimensions personnalisées aux dimensions générales par défaut.</span><span class="sxs-lookup"><span data-stu-id="71e04-278">With the dimension configuration, Inventory Visibility can map the custom dimensions to the general default dimensions.</span></span> <span data-ttu-id="71e04-279">Si la `dimensionDataSource` n'est pas spécifié, vous ne pouvez utiliser que les dimensions générales par défaut dans vos requêtes.</span><span class="sxs-lookup"><span data-stu-id="71e04-279">If the `dimensionDataSource` is not specified, you can only use the general default dimensions in your queries.</span></span>   |
| `dimensions` | <span data-ttu-id="71e04-280">Un sac dynamique de paires clé/valeur.</span><span class="sxs-lookup"><span data-stu-id="71e04-280">A dynamic bag of key/value pairs.</span></span> <span data-ttu-id="71e04-281">Celles-ci correspondront à certaines des dimensions de Supply Chain Management, mais vous pouvez également ajouter des dimensions personnalisées (comme *Source*) qui peut indiquer si l'événement provenait de Supply Chain Management ou d'un système externe.</span><span class="sxs-lookup"><span data-stu-id="71e04-281">These will map to some of the dimensions in Supply Chain Management, but you could also add custom dimensions (like *Source*) that may denote if the event was coming from Supply Chain Management or an external system.</span></span> |

### <a name="querying-current-on-hand"></a><span data-ttu-id="71e04-282">Interrogation actuellement disponible</span><span class="sxs-lookup"><span data-stu-id="71e04-282">Querying current on-hand</span></span>

<span data-ttu-id="71e04-283">Le point de terminaison pour interroger le stock actuel aura une URL similaire :</span><span class="sxs-lookup"><span data-stu-id="71e04-283">The endpoint for querying the current on-hand will have a similar URL:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

<span data-ttu-id="71e04-284">Il sera interrogé avec la méthode HTTP `POST`.</span><span class="sxs-lookup"><span data-stu-id="71e04-284">It will be queried with the HTTP `POST` method.</span></span>

#### <a name="current-on-hand-query-example-1"></a><span data-ttu-id="71e04-285">Exemple de requête en main actuel 1</span><span class="sxs-lookup"><span data-stu-id="71e04-285">Current on-hand query example 1</span></span>

<span data-ttu-id="71e04-286">Cet exemple montre un scénario dans lequel vous disposez déjà d'une configuration de dimension terminée dans Power Apps.</span><span class="sxs-lookup"><span data-stu-id="71e04-286">This example shows a scenario where you have already completed the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="71e04-287">Utilisez la requête suivante pour configurer le mappage de dimension dans Power Apps :</span><span class="sxs-lookup"><span data-stu-id="71e04-287">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="71e04-288">Vous pouvez maintenant spécifier la `dimensionDataSource` et utilisez des dimensions personnalisées dans vos requêtes.</span><span class="sxs-lookup"><span data-stu-id="71e04-288">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="71e04-289">Le système convertira automatiquement les dimensions personnalisées en dimensions de base.</span><span class="sxs-lookup"><span data-stu-id="71e04-289">The system will automatically convert custom dimensions to base dimensions.</span></span> <span data-ttu-id="71e04-290">Vous pouvez spécifier la `DimensionDataSource` dans `filters` et spécifiez des dimensions personnalisées dans `filters` et `groupByValues`.</span><span class="sxs-lookup"><span data-stu-id="71e04-290">You can specify the `DimensionDataSource` in `filters` and specify custom dimensions in both `filters` and `groupByValues`.</span></span> <span data-ttu-id="71e04-291">Le système convertira automatiquement les dimensions personnalisées en dimensions de base.</span><span class="sxs-lookup"><span data-stu-id="71e04-291">The system will automatically convert custom dimensions to base dimensions.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "DimensionDataSource": ["Pos"],
        "PosLocationId": ["21"],
        "PosSiteId": ["2"],
        "PosColorId": ["Red"]
    },
    "groupByValues": [
        "PosSizeId",
        "PosColorId"
    ],
    "returnNegative": true
}
```

#### <a name="current-on-hand-query-example-2"></a><span data-ttu-id="71e04-292">Exemple de requête en main actuel 2</span><span class="sxs-lookup"><span data-stu-id="71e04-292">Current on-hand query example 2</span></span>

<span data-ttu-id="71e04-293">Cet exemple montre un scénario dans lequel aucun mappage n'est configuré pour la configuration de dimension dans Power Apps, donc la publication doit également utiliser les dimensions de base.</span><span class="sxs-lookup"><span data-stu-id="71e04-293">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="71e04-294">Toutes les dimensions doivent être des dimensions de base lorsque le champ `dimensionDataSource`, sous `filters`, est nul, vide ou espace.</span><span class="sxs-lookup"><span data-stu-id="71e04-294">All dimensions must be base dimensions when the `dimensionDataSource` field, under `filters` is null, empty, or whitespace.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="example-return-result"></a><span data-ttu-id="71e04-295">Exemple de résultat de retour</span><span class="sxs-lookup"><span data-stu-id="71e04-295">Example return result</span></span>

<span data-ttu-id="71e04-296">Les requêtes présentées dans les exemples précédents peuvent renvoyer un résultat comme celui-ci.</span><span class="sxs-lookup"><span data-stu-id="71e04-296">The queries shown in the previous examples could return a result like this.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

<span data-ttu-id="71e04-297">Notez que les champs de quantités sont structurés comme un dictionnaire de mesures et de leurs valeurs associées.</span><span class="sxs-lookup"><span data-stu-id="71e04-297">Note that the quantities fields are structured as a dictionary of measures and their associated values.</span></span>
