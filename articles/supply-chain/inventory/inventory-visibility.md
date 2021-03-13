---
title: Complément de visibilité de stock
description: Cette rubrique décrit comment installer et configurer le complément de visibilité de stock pour Dynamics 365 Supply Chain Management.
author: sherry-zheng
manager: tfehr
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 4e6f7e0a3978bbf7e520f8cbcfd27c4cfe507777
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114668"
---
# <a name="inventory-visibility-add-in"></a><span data-ttu-id="c1ca5-103">Complément de visibilité de stock</span><span class="sxs-lookup"><span data-stu-id="c1ca5-103">Inventory Visibility Add-in</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

<span data-ttu-id="c1ca5-104">Le complément de visibilité de stock est un microservice indépendant et hautement évolutif qui permet un suivi des stocks en temps réel, offrant ainsi une vue globale de la visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-104">The Inventory Visibility Add-in is an independent and highly scalable microservice that enables real-time on-hand inventory tracking, thus providing a global view of inventory visibility.</span></span>

<span data-ttu-id="c1ca5-105">Toutes les informations relatives à l'inventaire disponible sont exportées vers le service en temps quasi réel via une intégration SQL de bas niveau.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-105">All information that relates to on-hand inventory is exported to the service in near real-time through low-level SQL integration.</span></span> <span data-ttu-id="c1ca5-106">Les systèmes externes accèdent au service via des API RESTful pour interroger les informations disponibles sur des ensembles de dimensions donnés, récupérant ainsi une liste des positions disponibles.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-106">External systems access the service through RESTful APIs to query on-hand information on given sets of dimensions, thus retrieving a list of available on-hand positions.</span></span>

<span data-ttu-id="c1ca5-107">La visibilité du stock est un microservice basé sur Microsoft Dataverse, ce qui signifie que vous pouvez l'étendre en créant des Power Apps et en appliquant Power BI pour fournir des fonctionnalités personnalisées pour répondre aux besoins de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-107">Inventory Visibility is a microservice built on Microsoft Dataverse, which means you can extend it by building Power Apps and applying Power BI to provide customized functionality to meet your business requirements.</span></span> <span data-ttu-id="c1ca5-108">Il est également possible de mettre à niveau l'index pour effectuer des requêtes d'inventaire.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-108">It is also possible to upgrade the index to do inventory queries.</span></span>

<span data-ttu-id="c1ca5-109">La visibilité du stock fournit des options de configuration qui lui permettent de s'intégrer à plusieurs systèmes tiers.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-109">Inventory Visibility provides configuration options that let it integrate with multiple third-party systems.</span></span> <span data-ttu-id="c1ca5-110">Il prend en charge la dimension de stock normalisée, l'extensibilité personnalisée et les quantités calculées normalisées et configurables.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-110">It supports the standardized inventory dimension, customized extensibility, and standardized, configurable calculated quantities.</span></span>

<span data-ttu-id="c1ca5-111">Cette rubrique décrit comment installer et configurer le complément de visibilité de stock pour Dynamics 365 Supply Chain Management, et comment utiliser son interface de programmation d'application (API).</span><span class="sxs-lookup"><span data-stu-id="c1ca5-111">This topic describes how to install and configure the Inventory Visibility Add-in for Dynamics 365 Supply Chain Management, and how to use its application programming interface (API).</span></span>

## <a name="install-the-inventory-visibility-add-in"></a><span data-ttu-id="c1ca5-112">Installer le complément de visibilité de stock</span><span class="sxs-lookup"><span data-stu-id="c1ca5-112">Install the Inventory Visibility Add-in</span></span>

<span data-ttu-id="c1ca5-113">Vous devez installer le complément de visibilité de stock à l'aide de Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="c1ca5-113">You need to install the Inventory Visibility Add-in using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="c1ca5-114">LCS est un portail de collaboration qui fournit un environnement et un ensemble de services régulièrement mis à jour qui vous aident à gérer le cycle de vie des applications de vos applications Dynamics 365 Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-114">LCS is a collaboration portal that provides an environment and a set of regularly updated services that help you manage the application lifecycle of your Dynamics 365 Finance and Operations apps.</span></span>

<span data-ttu-id="c1ca5-115">Pour plus d'informations, voir [Ressources Lifecycle Services](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span><span class="sxs-lookup"><span data-stu-id="c1ca5-115">For more information, see [Lifecycle Services resources](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span></span>

### <a name="prerequisites"></a><span data-ttu-id="c1ca5-116">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="c1ca5-116">Prerequisites</span></span>

<span data-ttu-id="c1ca5-117">Avant de pouvoir installer le complément Visibilité du stock, vous devez procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="c1ca5-117">Before you install the Inventory Visibility Add-in, you must do the following:</span></span>

- <span data-ttu-id="c1ca5-118">Obtenez un projet d'implémentation LCS avec au moins un environnement déployé.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-118">Obtain an LCS implementation project with at least one environment deployed.</span></span>
- <span data-ttu-id="c1ca5-119">Générez les clés bêta de votre offre dans LCS.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-119">Generate the beta keys for your offering in LCS.</span></span>
- <span data-ttu-id="c1ca5-120">Activez les clés bêta de votre offre pour votre utilisateur dans LCS.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-120">Enable the beta keys for your offering for your user in LCS.</span></span>
- <span data-ttu-id="c1ca5-121">Contactez l'équipe produit de la visibilité du stock Microsoft et fournissez un ID d'environnement dans lequel vous souhaitez déployer le complément de visibilité de stock.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-121">Contact the Microsoft Inventory Visibility product team and provide an environment ID where you want to deploy the Inventory Visibility Add-in.</span></span>

<span data-ttu-id="c1ca5-122">Si vous avez des questions sur ces conditions préalables, contactez l'équipe produit de visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-122">If you have any questions about these prerequisites, please contact the Inventory Visibility product team.</span></span>

### <a name="install-the-add-in"></a><a name="install-add-in"></a><span data-ttu-id="c1ca5-123">Installer le complément</span><span class="sxs-lookup"><span data-stu-id="c1ca5-123">Install the add-in</span></span>

<span data-ttu-id="c1ca5-124">Pour pouvoir installer le complément Visibilité du stock, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c1ca5-124">To install the Inventory Visibility Add-in, do the following:</span></span>

1. <span data-ttu-id="c1ca5-125">Connectez-vous au portail [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="c1ca5-125">Sign in to the [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portal.</span></span>
1. <span data-ttu-id="c1ca5-126">Sur la page d'accueil, sélectionnez le projet dans lequel votre environnement est déployé.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-126">On the home page, select the project where your environment is deployed.</span></span>
1. <span data-ttu-id="c1ca5-127">Sur la page du projet, sélectionnez l'environnement dans lequel vous souhaitez installer le complément.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-127">On the project page, select the environment where you want to install the add-in.</span></span>
1. <span data-ttu-id="c1ca5-128">Sur la page d'environnement, faites défiler vers le bas jusqu'à ce que vous voyiez la section **Compléments d'environnement**.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-128">On the environment page, scroll down until you see the **Environment add-ins** section.</span></span> <span data-ttu-id="c1ca5-129">Si la section n'est pas visible, assurez-vous que les clés bêta prérequises ont été entièrement traitées.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-129">If the section isn't visible, make sure the prerequisite beta keys have been fully processed.</span></span>
1. <span data-ttu-id="c1ca5-130">Dans la section **Compléments de l'environnement**, sélectionnez **Installer un nouveau complément**.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-130">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
    <span data-ttu-id="c1ca5-131">![Page de l'environnement dans LCS](media/inventory-visibility-environment.png "Page de l'environnement dans LCS")</span><span class="sxs-lookup"><span data-stu-id="c1ca5-131">![The environment page in LCS](media/inventory-visibility-environment.png "The environment page in LCS")</span></span>
1. <span data-ttu-id="c1ca5-132">Sélectionnez le lien **Installer un nouveau complément**.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-132">Select the **Install a new add-in** link.</span></span> <span data-ttu-id="c1ca5-133">Une liste des compléments disponibles s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-133">A list of available add-ins opens.</span></span>
1. <span data-ttu-id="c1ca5-134">Sélectionnez **Service d'inventaire** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-134">Select **Inventory service** from the list.</span></span> <span data-ttu-id="c1ca5-135">(Notez que cela peut maintenant être répertorié comme **Complément de visibilité de stock pour Dynamics 365 Supply Chain Management**.)</span><span class="sxs-lookup"><span data-stu-id="c1ca5-135">(Note, this may now be listed as **Inventory Visibility Add-in for Dynamics 365 Supply Chain Management**.)</span></span>
1. <span data-ttu-id="c1ca5-136">Saisissez des valeurs pour les champs suivants pour votre environnement :</span><span class="sxs-lookup"><span data-stu-id="c1ca5-136">Enter values for the following fields for your environment:</span></span>

    - <span data-ttu-id="c1ca5-137">**ID application AAD**</span><span class="sxs-lookup"><span data-stu-id="c1ca5-137">**AAD application ID**</span></span>
    - <span data-ttu-id="c1ca5-138">**ID locataire AAD**</span><span class="sxs-lookup"><span data-stu-id="c1ca5-138">**AAD tenant ID**</span></span>

    <span data-ttu-id="c1ca5-139">![Ajouter dans la page de configuration](media/inventory-visibility-setup.png "Page de configuration de complément")</span><span class="sxs-lookup"><span data-stu-id="c1ca5-139">![Add in setup page](media/inventory-visibility-setup.png "Add-in setup page")</span></span>

1. <span data-ttu-id="c1ca5-140">Acceptez les termes et conditions en cochant la case **Termes et conditions**.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-140">Agree to the terms and condition by selecting the **Terms and conditions** check box.</span></span>
1. <span data-ttu-id="c1ca5-141">Sélectionnez **Installer**.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-141">Select **Install**.</span></span> <span data-ttu-id="c1ca5-142">Le statut du complément s'affichera comme **Installation en cours**.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-142">The status of the add-in will show as **Installing**.</span></span> <span data-ttu-id="c1ca5-143">Une fois terminé, actualisez la page pour voir le statut changer en **Installé**.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-143">When it's done, refresh the page to see the status change to **Installed**.</span></span>

### <a name="get-a-security-service-token"></a><span data-ttu-id="c1ca5-144">Obtenir un jeton de service de sécurité</span><span class="sxs-lookup"><span data-stu-id="c1ca5-144">Get a security service token</span></span>

<span data-ttu-id="c1ca5-145">Obtenez un jeton de service de sécurité en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="c1ca5-145">Get a security service token by doing the following:</span></span>

1. <span data-ttu-id="c1ca5-146">Connectez-vous au portail Azure et utilisez-le pour trouver le `clientId` et le `clientSecret` de votre application Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-146">Sign in to Azure Portal and use it to find the `clientId` and `clientSecret` for your Supply Chain Management application.</span></span>
1. <span data-ttu-id="c1ca5-147">Récupérez un jeton Azure Active Directory (`aadToken`) en envoyant une requête HTTP avec les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="c1ca5-147">Fetch an Azure Active Directory token (`aadToken`) by submitting an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="c1ca5-148">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span><span class="sxs-lookup"><span data-stu-id="c1ca5-148">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span></span>
    - <span data-ttu-id="c1ca5-149">**Méthode** - `GET`</span><span class="sxs-lookup"><span data-stu-id="c1ca5-149">**Method** - `GET`</span></span>
    - <span data-ttu-id="c1ca5-150">**Contenu du corps (données du formulaire)**  :</span><span class="sxs-lookup"><span data-stu-id="c1ca5-150">**Body content (form data)**:</span></span>

        | <span data-ttu-id="c1ca5-151">clé</span><span class="sxs-lookup"><span data-stu-id="c1ca5-151">key</span></span> | <span data-ttu-id="c1ca5-152">valeur</span><span class="sxs-lookup"><span data-stu-id="c1ca5-152">value</span></span> |
        | --- | --- |
        | <span data-ttu-id="c1ca5-153">client_id</span><span class="sxs-lookup"><span data-stu-id="c1ca5-153">client_id</span></span> | <span data-ttu-id="c1ca5-154">${aadAppId}</span><span class="sxs-lookup"><span data-stu-id="c1ca5-154">${aadAppId}</span></span> |
        | <span data-ttu-id="c1ca5-155">client_secret</span><span class="sxs-lookup"><span data-stu-id="c1ca5-155">client_secret</span></span> | <span data-ttu-id="c1ca5-156">${aadAppSecret}</span><span class="sxs-lookup"><span data-stu-id="c1ca5-156">${aadAppSecret}</span></span> |
        | <span data-ttu-id="c1ca5-157">grant_type</span><span class="sxs-lookup"><span data-stu-id="c1ca5-157">grant_type</span></span> | <span data-ttu-id="c1ca5-158">client_credentials</span><span class="sxs-lookup"><span data-stu-id="c1ca5-158">client_credentials</span></span> |
        | <span data-ttu-id="c1ca5-159">resource</span><span class="sxs-lookup"><span data-stu-id="c1ca5-159">resource</span></span> | <span data-ttu-id="c1ca5-160">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="c1ca5-160">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
1. <span data-ttu-id="c1ca5-161">Vous devriez recevoir un `aadToken` en réponse, qui ressemble à l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-161">You should receive an `aadToken` in response, which resembles the following example.</span></span>

    ```json
    {
    "token_type": "Bearer",
    "expires_in": "3599",
    "ext_expires_in": "3599",
    "expires_on": "1610466645",
    "not_before": "1610462745",
    "resource": "0cdb527f-a8d1-4bf8-9436-b352c68682b2",
    "access_token": "eyJ0eX...8WQ"
    }
    ```

1. <span data-ttu-id="c1ca5-162">Formulez une requête JSON qui ressemble à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="c1ca5-162">Formulate a JSON request that resembles the following:</span></span>

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{Your_AADToken}",
        "scope":"https://inventoryservice.operations365.dynamics.com/.default",
        "context": "5dbf6cc8-255e-4de2-8a25-2101cd5649b4",
        "context_type": "finops-env"
    }
    ```

    <span data-ttu-id="c1ca5-163">Où :</span><span class="sxs-lookup"><span data-stu-id="c1ca5-163">Where:</span></span>
    - <span data-ttu-id="c1ca5-164">La valeur `client_assertion` doit être le `aadToken` que vous avez reçu à l'étape précédente.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-164">The `client_assertion` value must be the `aadToken` you received in the previous step.</span></span>
    - <span data-ttu-id="c1ca5-165">La valeur `context` doit être l'ID d'environnement dans lequel vous souhaitez déployer le complément.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-165">The `context` value must be the environment ID where you want to deploy the add-in.</span></span>
    - <span data-ttu-id="c1ca5-166">Définissez toutes les autres valeurs comme indiqué dans l'exemple.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-166">Set all of other values as shown in the example.</span></span>

1. <span data-ttu-id="c1ca5-167">Envoyez une requête HTTP avec les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="c1ca5-167">Submit an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="c1ca5-168">**URL** - `https://securityservice.operations365.dynamics.com/token`</span><span class="sxs-lookup"><span data-stu-id="c1ca5-168">**URL** - `https://securityservice.operations365.dynamics.com/token`</span></span>
    - <span data-ttu-id="c1ca5-169">**Méthode** - `POST`</span><span class="sxs-lookup"><span data-stu-id="c1ca5-169">**Method** - `POST`</span></span>
    - <span data-ttu-id="c1ca5-170">**En-tête HTTP** : incluez la version de l'API (la clé est `Api-Version` et la valeur est `1.0`)</span><span class="sxs-lookup"><span data-stu-id="c1ca5-170">**HTTP header** - Include the API version (key is `Api-Version` and value is `1.0`)</span></span>
    - <span data-ttu-id="c1ca5-171">**Contenu du corps** : incluez la requête JSON que vous avez créée à l'étape précédente.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-171">**Body content** - Include the JSON request that you created in the previous step.</span></span>

1. <span data-ttu-id="c1ca5-172">Vous obtiendrez un `access_token` en réponse.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-172">You will get an `access_token` in response.</span></span> <span data-ttu-id="c1ca5-173">C'est ce dont vous avez besoin en tant que jeton de support pour appeler l'API de visibilité de stock.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-173">This is what you need as a bearer token to call the Inventory Visibility API.</span></span> <span data-ttu-id="c1ca5-174">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="c1ca5-174">Here is an example.</span></span>

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="uninstall-the-add-in"></a><span data-ttu-id="c1ca5-175">Désinstaller le complément</span><span class="sxs-lookup"><span data-stu-id="c1ca5-175">Uninstall the add-in</span></span>

<span data-ttu-id="c1ca5-176">Pour désinstaller le complément, sélectionnez **Désinstaller**.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-176">To uninstall the add-in, select **Uninstall**.</span></span> <span data-ttu-id="c1ca5-177">Actualiser LCS et le complément de visibilité de stock seront supprimés.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-177">Refresh LCS and the Inventory Visibility Add-in will be removed.</span></span> <span data-ttu-id="c1ca5-178">Le processus de désinstallation supprimera l'inscription du complément et lancera également une tâche pour nettoyer toutes les données d'entreprise stockées dans le service.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-178">The uninstall process will remove the add-in registration and also start a job to clean up all of the business data stored in the service.</span></span>

## <a name="inventory-visibility-add-in-public-api"></a><span data-ttu-id="c1ca5-179">API publique du complément de visibilité de stock</span><span class="sxs-lookup"><span data-stu-id="c1ca5-179">Inventory Visibility Add-in public API</span></span>

<span data-ttu-id="c1ca5-180">L'API REST publique du complément de visibilité de stock présente plusieurs points de terminaison d'intégration spécifiques.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-180">The public REST API of the of the Inventory Visibility Add-in presents several specific endpoints of integration.</span></span> <span data-ttu-id="c1ca5-181">Elle prend en charge trois types d'interactions principaux :</span><span class="sxs-lookup"><span data-stu-id="c1ca5-181">It supports three main interaction types:</span></span>

- <span data-ttu-id="c1ca5-182">Publication des modifications disponibles du complément à partir d'un système externe.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-182">Posting on-hand changes to the add-in from an external system.</span></span>
- <span data-ttu-id="c1ca5-183">Interrogation des quantités en stock actuelles à partir d'un système externe.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-183">Querying current on-hand quantities from an external system.</span></span>
- <span data-ttu-id="c1ca5-184">Synchronisation automatique avec Supply Chain Management à portée de main.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-184">Automatic synchronization with Supply Chain Management on-hand.</span></span>

<span data-ttu-id="c1ca5-185">La synchronisation automatique ne fait pas partie de l'API publique, mais est plutôt gérée en arrière-plan pour les environnements qui ont activé le complément de visibilité d'inventaire.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-185">The automatic synchronization isn't part of the public API but is instead handled in the background for environments that have enabled the Inventory Visibility Add-in.</span></span>

### <a name="authentication"></a><span data-ttu-id="c1ca5-186">Authentification</span><span class="sxs-lookup"><span data-stu-id="c1ca5-186">Authentication</span></span>

<span data-ttu-id="c1ca5-187">Le jeton de sécurité de la plateforme est utilisé pour appeler le complément de visibilité d'inventaire, vous devez donc générer un jeton Azure Active Directory en utilisant votre application Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-187">The platform security token is used to call the Inventory Visibility Add-in, so you must generate an Azure Active Directory token using your Azure Active Directory application.</span></span>

<span data-ttu-id="c1ca5-188">Pour plus d'informations sur la façon d'obtenir le jeton de sécurité, consultez [Installer le complément de visibilité de stock](#install-add-in).</span><span class="sxs-lookup"><span data-stu-id="c1ca5-188">For more information about how to get the security token, see [Install the Inventory Visibility Add-in](#install-add-in).</span></span>

### <a name="configure-the-inventory-visibility-api"></a><span data-ttu-id="c1ca5-189">Configurer l'API de visibilité de stock</span><span class="sxs-lookup"><span data-stu-id="c1ca5-189">Configure the Inventory Visibility API</span></span>

<span data-ttu-id="c1ca5-190">Avant d'utiliser le service, vous devez effectuer les configurations décrites dans les sous-sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-190">Before using the service, you must complete the configurations described in the following subsections.</span></span> <span data-ttu-id="c1ca5-191">La configuration peut varier en fonction des détails de votre environnement.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-191">The configuration may vary based on the details of your environment.</span></span> <span data-ttu-id="c1ca5-192">Il comprend principalement quatre parties :</span><span class="sxs-lookup"><span data-stu-id="c1ca5-192">It primarily includes four parts:</span></span>

- [<span data-ttu-id="c1ca5-193">Partitionnement</span><span class="sxs-lookup"><span data-stu-id="c1ca5-193">Partitioning</span></span>](#partitioning)
- [<span data-ttu-id="c1ca5-194">Configurations des dimensions</span><span class="sxs-lookup"><span data-stu-id="c1ca5-194">Dimension configurations</span></span>](#dimension-configurations)
- [<span data-ttu-id="c1ca5-195">Indexation</span><span class="sxs-lookup"><span data-stu-id="c1ca5-195">Indexing</span></span>](#indexing)
- [<span data-ttu-id="c1ca5-196">Mesure personnalisée</span><span class="sxs-lookup"><span data-stu-id="c1ca5-196">Custom measurement</span></span>](#custom-measurement)

#### <a name="partitioning"></a><span data-ttu-id="c1ca5-197">Partitionnement</span><span class="sxs-lookup"><span data-stu-id="c1ca5-197">Partitioning</span></span>

<span data-ttu-id="c1ca5-198">Le partitionnement peut influencer considérablement les performances de l'API de visibilité d'inventaire.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-198">Partitioning can significantly influence the performance of the Inventory Visibility API.</span></span> <span data-ttu-id="c1ca5-199">C'est une bonne idée de définir un schéma qui permet de petits regroupements de données tout en permettant des requêtes de données significatives.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-199">It's a good idea to define a scheme that allows for small groupings of data while still allowing for meaningful data queries.</span></span>

<span data-ttu-id="c1ca5-200">L'`organizationId` (`dataAreaId` dans Supply Chain Management) fera toujours partie du partitionnement et, par défaut, la visibilité du stock est définie pour partitionner par dimensions comme *Site + Localisation*.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-200">The `organizationId` (`dataAreaId` in Supply Chain Management) will always be part of the partitioning, and by default Inventory Visibility is set to partition by dimensions as *Site + Location*.</span></span> <span data-ttu-id="c1ca5-201">Cela signifie que le service doit toujours être interrogé avec ces dimensions définies sur les filtres.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-201">This means that the service must always be queried with these dimensions defined on the filters.</span></span>

> [!NOTE]
> <span data-ttu-id="c1ca5-202">*Site* et *Emplacement* sont deux dimensions générales par défaut dans la visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-202">*Site* and *Location* are two general default dimensions in Inventory Visibility.</span></span> <span data-ttu-id="c1ca5-203">Dans Supply Chain Management, ces dimensions sont appelées *Site* (`InventSiteId`) et *Entrepôt* (`InventLocationId`)</span><span class="sxs-lookup"><span data-stu-id="c1ca5-203">In Supply Chain Management, those dimensions are called *Site* (`InventSiteId`) and *Warehouse* (`InventLocationId`)</span></span>

### <a name="dimension-configurations"></a><span data-ttu-id="c1ca5-204">Configurations des dimensions</span><span class="sxs-lookup"><span data-stu-id="c1ca5-204">Dimension configurations</span></span>

<span data-ttu-id="c1ca5-205">La visibilité du stock fournira une liste de dimensions générales par défaut pour permettre l'intégration du système source multiple.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-205">Inventory Visibility will provide a list of general default dimensions to enable the multiple source system integration.</span></span>

<span data-ttu-id="c1ca5-206">Le tableau suivant répertorie les dimensions d'inventaire qui seront les noms de dimension par défaut dans la visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-206">The following table lists the inventory dimensions that will be the default dimension names in Inventory Visibility.</span></span>

| <span data-ttu-id="c1ca5-207">Type de dimension</span><span class="sxs-lookup"><span data-stu-id="c1ca5-207">Dimension type</span></span> | <span data-ttu-id="c1ca5-208">Nom de dimension</span><span class="sxs-lookup"><span data-stu-id="c1ca5-208">Dimension name</span></span> |
|---|---|
| <span data-ttu-id="c1ca5-209">Produit</span><span class="sxs-lookup"><span data-stu-id="c1ca5-209">Product</span></span> | `ColorId` |
| <span data-ttu-id="c1ca5-210">Produit</span><span class="sxs-lookup"><span data-stu-id="c1ca5-210">Product</span></span> | `SizeId` |
| <span data-ttu-id="c1ca5-211">Produit</span><span class="sxs-lookup"><span data-stu-id="c1ca5-211">Product</span></span> | `StyleId` |
| <span data-ttu-id="c1ca5-212">Produit</span><span class="sxs-lookup"><span data-stu-id="c1ca5-212">Product</span></span> | `ConfigId` |
| <span data-ttu-id="c1ca5-213">Suivi</span><span class="sxs-lookup"><span data-stu-id="c1ca5-213">Tracking</span></span> | `BatchId` |
| <span data-ttu-id="c1ca5-214">Suivi</span><span class="sxs-lookup"><span data-stu-id="c1ca5-214">Tracking</span></span> | `SerialId` |
| <span data-ttu-id="c1ca5-215">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="c1ca5-215">Location</span></span> | `LocationId` |
| <span data-ttu-id="c1ca5-216">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="c1ca5-216">Location</span></span> | `SiteId` |
| <span data-ttu-id="c1ca5-217">Statut du stock</span><span class="sxs-lookup"><span data-stu-id="c1ca5-217">Inventory Status</span></span> | `StatusId` |
| <span data-ttu-id="c1ca5-218">Spécifique à l'entrepôt</span><span class="sxs-lookup"><span data-stu-id="c1ca5-218">Warehouse Specific</span></span> | `WMSLocationId` |
| <span data-ttu-id="c1ca5-219">Spécifique à l'entrepôt</span><span class="sxs-lookup"><span data-stu-id="c1ca5-219">Warehouse Specific</span></span> | `WMSPalletId` |
| <span data-ttu-id="c1ca5-220">Spécifique à l'entrepôt</span><span class="sxs-lookup"><span data-stu-id="c1ca5-220">Warehouse Specific</span></span> | `LicensePlateId` |

> [!NOTE]
> <span data-ttu-id="c1ca5-221">Le type de dimension répertorié dans le tableau précédent est à titre indicatif uniquement.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-221">The dimension type listed in the previous table is for reference only.</span></span> <span data-ttu-id="c1ca5-222">Vous n'avez pas besoin de définir le type de dimension dans la visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-222">You don't need to define the dimension type in Inventory Visibility.</span></span>

<span data-ttu-id="c1ca5-223">Si une dimension personnalisée existe et doit passer à une valeur par défaut lorsqu'elle est utilisée par la visibilité du stock, vous pouvez configurer le nom **Dimension personnalisée** dans la visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-223">If a custom dimension exists and needs to flow to a default value when consumed by Inventory Visibility, you can configure the **Custom dimension** name in Inventory Visibility.</span></span>

<span data-ttu-id="c1ca5-224">Les systèmes externes accèdent à la visibilité du stock via des API RESTful qui permettent d'interroger des informations disponibles sur des ensembles de dimensions donnés.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-224">External systems access Inventory Visibility through RESTful APIs that enable on-hand information on given sets of dimensions to be queried.</span></span> <span data-ttu-id="c1ca5-225">Pour l'intégration, la visibilité du stock vous permet de configurer la *source de données de canal externe* et la dimension source des *dimensions cibles* dans la visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-225">For the integration, Inventory Visibility enables you to configure the *external channel data source* and the source dimension to the *target dimensions* in Inventory Visibility.</span></span>

<span data-ttu-id="c1ca5-226">Les dimensions cibles doivent être l'une des suivantes :</span><span class="sxs-lookup"><span data-stu-id="c1ca5-226">The target dimensions should be one of the following:</span></span>

- <span data-ttu-id="c1ca5-227">Dimensions par défaut dans la visibilité du stock</span><span class="sxs-lookup"><span data-stu-id="c1ca5-227">Default dimensions in Inventory Visibility</span></span>
- <span data-ttu-id="c1ca5-228">Dimensions personnalisées</span><span class="sxs-lookup"><span data-stu-id="c1ca5-228">Custom dimensions</span></span>

<span data-ttu-id="c1ca5-229">Le but de la configuration des dimensions est de standardiser l'intégration multi-système pour la requête sur les dimensions et l'événement de publication avec les dimensions.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-229">The purpose of dimension configuration is to standardize the multi-system integration for the query on dimensions and the posting event with dimensions.</span></span>

#### <a name="indexing"></a><span data-ttu-id="c1ca5-230">Indexation</span><span class="sxs-lookup"><span data-stu-id="c1ca5-230">Indexing</span></span>

<span data-ttu-id="c1ca5-231">La plupart du temps, la requête de stock disponible sera non seulement au niveau "total" le plus élevé, mais vous souhaiterez peut-être voir les résultats agrégés en fonction des dimensions de stock.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-231">Most of the time, the inventory on-hand query will not only be on the highest "total" level, but you may want to see results aggregated based on the inventory dimensions.</span></span>

<span data-ttu-id="c1ca5-232">La visibilité du stock offre une certaine flexibilité en vous permettant de configurer les index, qui sont basés sur la dimension ou la combinaison des dimensions.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-232">Inventory Visibility provides flexibility by allowing you to set up the indexes, which are based on the dimension or the combination of the dimensions.</span></span>

> [!NOTE]
> <span data-ttu-id="c1ca5-233">Actuellement, vous ne pouvez configurer les index que jusqu'à un maximum de cinq.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-233">Currently, you can only configure indexes to a maximum of five.</span></span> <span data-ttu-id="c1ca5-234">Vous devez examiner attentivement la dimension ou la combinaison de dimensions que vous utiliserez avant la mise en œuvre pour vous assurer qu'elle répondra aux besoins de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-234">You need to carefully consider which dimension or dimension combination you will use before the implementation to ensure that it will meet your business needs.</span></span> <span data-ttu-id="c1ca5-235">Par exemple, si vous souhaitez interroger les produits comme suit :</span><span class="sxs-lookup"><span data-stu-id="c1ca5-235">For example, if you want to query products as follows:</span></span>

- <span data-ttu-id="c1ca5-236">Recherchez le produit agrégé disponible par les dimensions *Couleur* et *Taille*.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-236">Query the aggregated product on-hand by the *Color* and *Size* dimensions.</span></span>
- <span data-ttu-id="c1ca5-237">Dans certains cas, vous souhaitez simplement interroger le produit au total.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-237">In some cases, you just want to query on the product in total.</span></span>

<span data-ttu-id="c1ca5-238">Vous auriez deux index définis comme suit :</span><span class="sxs-lookup"><span data-stu-id="c1ca5-238">You would have two indexes defined as the following:</span></span>

- `["ColorId", "SizeId"]`
- `[]`

<span data-ttu-id="c1ca5-239">Le crochet vide sera agrégé en fonction de l'ID de produit dans la partition.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-239">The empty bracket will aggregate based on the product ID within the partition.</span></span>

<span data-ttu-id="c1ca5-240">L'indexation définit comment vous pouvez regrouper vos résultats en fonction du paramètre de requête `groupBy`.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-240">The indexing defines how you can group your results based on the `groupBy` query setting.</span></span> <span data-ttu-id="c1ca5-241">Dans ce cas, si vous ne définissez aucune valeur `groupBy`, vous obtiendrez les totaux par `productid`.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-241">In this case if you don't define any `groupBy` values, you'll get totals by `productid`.</span></span> <span data-ttu-id="c1ca5-242">Sinon si vous définissez `groupBy` comme `groupBy=ColorId&groupBy=SizeId`, vous obtiendrez plusieurs lignes renvoyées, en fonction des différentes combinaisons de couleurs et de tailles du système.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-242">Otherwise if you define `groupBy` as `groupBy=ColorId&groupBy=SizeId`, you'll get multiple lines returned, based on the different color and size combinations in the system.</span></span>

<span data-ttu-id="c1ca5-243">Vous pouvez mettre vos critères de requête dans le corps de la requête.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-243">You can put your query criteria in the request body.</span></span>

<span data-ttu-id="c1ca5-244">Voici un exemple de requête sur le produit avec une combinaison de couleur et de taille.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-244">Here is a sample query on the product with color and size combination.</span></span>

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

#### <a name="custom-measurement"></a><span data-ttu-id="c1ca5-245">Mesure personnalisée</span><span class="sxs-lookup"><span data-stu-id="c1ca5-245">Custom measurement</span></span>

<span data-ttu-id="c1ca5-246">Les quantités de mesure par défaut sont liées à Supply Chain Management, mais vous souhaiterez peut-être avoir une quantité composée d'une combinaison des mesures par défaut.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-246">The default measurement quantities are linked to Supply Chain Management, however you may want to have a quantity that is made up of a combination of the default measurements.</span></span> <span data-ttu-id="c1ca5-247">Pour ce faire, vous pouvez avoir une configuration de quantités personnalisées, qui seront ajoutées à la sortie des requêtes en main.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-247">To do this, you can have a configuration of custom quantities, which will be added to the output of the on-hand queries.</span></span>

<span data-ttu-id="c1ca5-248">La fonctionnalité vous permet simplement de définir un ensemble de mesures qui seront ajoutées, et/ou un ensemble de mesures qui seront soustraites, afin de la mesure personnalisée.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-248">The functionality simply allows you to define a set of measures that will be added, and/or a set of measures that will be subtracted, in order to form the custom measurement.</span></span>

<span data-ttu-id="c1ca5-249">Par exemple, avec la condition de requête suivante, vous configurerez la quantité de mesure personnalisée comme `MyCustomAvailableforReservation` à consommer par le système de consommation.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-249">For example, with the following query condition, you will configure the custom measurement quantity as `MyCustomAvailableforReservation` to be consumed by the consumption system.</span></span>

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



| <span data-ttu-id="c1ca5-250">Système de consommation</span><span class="sxs-lookup"><span data-stu-id="c1ca5-250">Consumption system</span></span> | <span data-ttu-id="c1ca5-251">Mesures calculées</span><span class="sxs-lookup"><span data-stu-id="c1ca5-251">Calculated measurers</span></span> | <span data-ttu-id="c1ca5-252">Source de données</span><span class="sxs-lookup"><span data-stu-id="c1ca5-252">Data source</span></span> | <span data-ttu-id="c1ca5-253">Modificateur</span><span class="sxs-lookup"><span data-stu-id="c1ca5-253">Modifier</span></span> | <span data-ttu-id="c1ca5-254">Type de calcul du modificateur</span><span class="sxs-lookup"><span data-stu-id="c1ca5-254">Modifier calculation type</span></span> |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | <span data-ttu-id="c1ca5-255">Addition</span><span class="sxs-lookup"><span data-stu-id="c1ca5-255">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | <span data-ttu-id="c1ca5-256">Addition</span><span class="sxs-lookup"><span data-stu-id="c1ca5-256">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | <span data-ttu-id="c1ca5-257">Soustraction</span><span class="sxs-lookup"><span data-stu-id="c1ca5-257">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | <span data-ttu-id="c1ca5-258">Addition</span><span class="sxs-lookup"><span data-stu-id="c1ca5-258">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | <span data-ttu-id="c1ca5-259">Soustraction</span><span class="sxs-lookup"><span data-stu-id="c1ca5-259">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | <span data-ttu-id="c1ca5-260">Addition</span><span class="sxs-lookup"><span data-stu-id="c1ca5-260">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | <span data-ttu-id="c1ca5-261">Addition</span><span class="sxs-lookup"><span data-stu-id="c1ca5-261">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | <span data-ttu-id="c1ca5-262">Soustraction</span><span class="sxs-lookup"><span data-stu-id="c1ca5-262">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | <span data-ttu-id="c1ca5-263">Soustraction</span><span class="sxs-lookup"><span data-stu-id="c1ca5-263">Subtraction</span></span> |

<span data-ttu-id="c1ca5-264">Avec cela, la requête sur la quantité de mesure personnalisée renverra la sortie suivante.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-264">With that, the query on the custom measurement quantity will return the following output.</span></span>

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

<span data-ttu-id="c1ca5-265">La sortie `MyCustomAvailableforReservation` est basée sur le paramètre de calcul dans les mesures personnalisées comme :</span><span class="sxs-lookup"><span data-stu-id="c1ca5-265">The `MyCustomAvailableforReservation` output is based on the calculation setting in the custom measurements as:</span></span>  
 <span data-ttu-id="c1ca5-266">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span><span class="sxs-lookup"><span data-stu-id="c1ca5-266">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span></span>

### <a name="posting-on-hand-changes"></a><span data-ttu-id="c1ca5-267">Publication des modifications en stock</span><span class="sxs-lookup"><span data-stu-id="c1ca5-267">Posting on-hand changes</span></span>

<span data-ttu-id="c1ca5-268">L'URL exacte sur laquelle l'événement sera publié dépendra de votre région géographique.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-268">The exact URL that the event will be posted to will depend on your geographical region.</span></span> <span data-ttu-id="c1ca5-269">Il prendra la forme :</span><span class="sxs-lookup"><span data-stu-id="c1ca5-269">It will take the form:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand`

<span data-ttu-id="c1ca5-270">Une fois authentifiée, cette URL peut être utilisée avec la méthode HTTP `POST` pour envoyer des événements de modification en main au service.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-270">When authenticated, this URL can be used along with the HTTP `POST` method to send on-hand change events to the service.</span></span>

<span data-ttu-id="c1ca5-271">Un en-tête spécial est utilisé pour communiquer avec les services Dynamics 365 via des requêtes HTTP, indiquant l'ID d'environnement de l'instance Supply Chain Management à laquelle les données sont liées.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-271">A special header is used for communicating with Dynamics 365 services through HTTP requests, denoting the environment ID of the Supply Chain Management instance the data is linked to.</span></span> <span data-ttu-id="c1ca5-272">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="c1ca5-272">For example:</span></span>

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a><span data-ttu-id="c1ca5-273">Exemple de requête de publication de modifications en main 1</span><span class="sxs-lookup"><span data-stu-id="c1ca5-273">Posting on-hand changes query example 1</span></span>

<span data-ttu-id="c1ca5-274">Cet exemple montre un scénario dans lequel vous allez configurer la configuration de dimension dans Power Apps.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-274">This example shows a scenario where you will set up the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="c1ca5-275">Utilisez la requête suivante pour configurer le mappage de dimension dans Power Apps :</span><span class="sxs-lookup"><span data-stu-id="c1ca5-275">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="c1ca5-276">Vous pouvez maintenant spécifier la `dimensionDataSource` et utilisez des dimensions personnalisées dans vos requêtes.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-276">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="c1ca5-277">Le système convertira automatiquement les dimensions personnalisées en dimensions de base.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-277">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="posting-on-hand-changes-query-example-2"></a><span data-ttu-id="c1ca5-278">Exemple de requête de publication de modifications en main 2</span><span class="sxs-lookup"><span data-stu-id="c1ca5-278">Posting on-hand changes query example 2</span></span>

<span data-ttu-id="c1ca5-279">Cet exemple montre un scénario dans lequel aucun mappage n'est configuré pour la configuration de dimension dans Power Apps, donc la publication doit également utiliser les dimensions de base.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-279">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="c1ca5-280">Toutes les dimensions doivent être des dimensions de base lorsque le champ `dimensionDataSource` est nul, vide ou espace.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-280">All dimensions must be base dimensions when the `dimensionDataSource` field is null, empty, or whitespace.</span></span>

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

#### <a name="json-document-field-properties"></a><span data-ttu-id="c1ca5-281">Propriétés du champs de documents JSON</span><span class="sxs-lookup"><span data-stu-id="c1ca5-281">JSON document field properties</span></span>

<span data-ttu-id="c1ca5-282">Les champs des exemples de requête JSON fournis précédemment ont les propriétés répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-282">The fields from the JSON query examples provided previously have the properties listed in the following table.</span></span>

| <span data-ttu-id="c1ca5-283">ID champ</span><span class="sxs-lookup"><span data-stu-id="c1ca5-283">Field ID</span></span> | <span data-ttu-id="c1ca5-284">Description</span><span class="sxs-lookup"><span data-stu-id="c1ca5-284">Description</span></span> |
|---|---|
| `id` | <span data-ttu-id="c1ca5-285">Un ID unique pour l'événement de modification spécifique.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-285">A unique ID for the specific change event.</span></span> <span data-ttu-id="c1ca5-286">Cet ID est utilisé pour garantir qu'en cas d'échec de la communication avec le service pendant la comptabilisation, la soumission à nouveau de l'événement n'entraînerait pas le comptage du même événement deux fois dans le système.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-286">This ID is used to ensure that if communication with the service fails during posting, resubmitting the event would not result in the same event being counted twice in the system.</span></span> |
| `organizationId` | <span data-ttu-id="c1ca5-287">L'identificateur de l'organisation liée à l'événement.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-287">The identifier of the organization linked to the event.</span></span> <span data-ttu-id="c1ca5-288">Cela correspond aux organisations de gestion de Supply Chain Management ou aux ID de zone de données.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-288">This maps to Supply Chain Management organizations or data area IDs.</span></span> |
| `productId` | <span data-ttu-id="c1ca5-289">Identificateur du produit en question.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-289">The identifier of the product in question.</span></span> |
| `quantity` | <span data-ttu-id="c1ca5-290">La quantité dont le stock doit être changé.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-290">The quantity by which the on-hand needs to be changed.</span></span> <span data-ttu-id="c1ca5-291">Si, par exemple, 10 nouveaux bagels étaient ajoutés à une étagère, cette valeur serait de 10.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-291">If, for instance, 10 new bagels were added to a shelf, this value would be 10.</span></span> <span data-ttu-id="c1ca5-292">Si 3 bagels étaient ensuite retirés de l'étagère ou vendus, cette valeur serait de -3.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-292">If 3 bagels were then removed from the shelf or sold, this value would be -3.</span></span> |
| `dimensionDataSource` | <span data-ttu-id="c1ca5-293">Source de données des dimensions utilisées dans l'événement et la requête de modification de publication.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-293">The data source of the dimensions used in the posting change event and query.</span></span> <span data-ttu-id="c1ca5-294">Si vous spécifiez la source de données, vous pouvez utiliser les dimensions personnalisées de la source de données spécifiée.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-294">If you specify the data source, you can use the custom dimensions from the specified data source.</span></span> <span data-ttu-id="c1ca5-295">Avec la configuration des dimensions, la visibilité du stock peut mapper les dimensions personnalisées aux dimensions générales par défaut.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-295">With the dimension configuration, Inventory Visibility can map the custom dimensions to the general default dimensions.</span></span> <span data-ttu-id="c1ca5-296">Si la `dimensionDataSource` n'est pas spécifié, vous ne pouvez utiliser que les dimensions générales par défaut dans vos requêtes.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-296">If the `dimensionDataSource` is not specified, you can only use the general default dimensions in your queries.</span></span>   |
| `dimensions` | <span data-ttu-id="c1ca5-297">Un sac dynamique de paires clé/valeur.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-297">A dynamic bag of key/value pairs.</span></span> <span data-ttu-id="c1ca5-298">Celles-ci correspondront à certaines des dimensions de Supply Chain Management, mais vous pouvez également ajouter des dimensions personnalisées (comme *Source*) qui peut indiquer si l'événement provenait de Supply Chain Management ou d'un système externe.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-298">These will map to some of the dimensions in Supply Chain Management, but you could also add custom dimensions (like *Source*) that may denote if the event was coming from Supply Chain Management or an external system.</span></span> |

### <a name="querying-current-on-hand"></a><span data-ttu-id="c1ca5-299">Interrogation actuellement disponible</span><span class="sxs-lookup"><span data-stu-id="c1ca5-299">Querying current on-hand</span></span>

<span data-ttu-id="c1ca5-300">Le point de terminaison pour interroger le stock actuel aura une URL similaire :</span><span class="sxs-lookup"><span data-stu-id="c1ca5-300">The endpoint for querying the current on-hand will have a similar URL:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

<span data-ttu-id="c1ca5-301">Il sera interrogé avec la méthode HTTP `POST`.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-301">It will be queried with the HTTP `POST` method.</span></span>

#### <a name="current-on-hand-query-example-1"></a><span data-ttu-id="c1ca5-302">Exemple de requête en main actuel 1</span><span class="sxs-lookup"><span data-stu-id="c1ca5-302">Current on-hand query example 1</span></span>

<span data-ttu-id="c1ca5-303">Cet exemple montre un scénario dans lequel vous disposez déjà d'une configuration de dimension terminée dans Power Apps.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-303">This example shows a scenario where you have already completed the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="c1ca5-304">Utilisez la requête suivante pour configurer le mappage de dimension dans Power Apps :</span><span class="sxs-lookup"><span data-stu-id="c1ca5-304">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="c1ca5-305">Vous pouvez maintenant spécifier la `dimensionDataSource` et utilisez des dimensions personnalisées dans vos requêtes.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-305">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="c1ca5-306">Le système convertira automatiquement les dimensions personnalisées en dimensions de base.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-306">The system will automatically convert custom dimensions to base dimensions.</span></span> <span data-ttu-id="c1ca5-307">Vous pouvez spécifier la `DimensionDataSource` dans `filters` et spécifiez des dimensions personnalisées dans `filters` et `groupByValues`.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-307">You can specify the `DimensionDataSource` in `filters` and specify custom dimensions in both `filters` and `groupByValues`.</span></span> <span data-ttu-id="c1ca5-308">Le système convertira automatiquement les dimensions personnalisées en dimensions de base.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-308">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="current-on-hand-query-example-2"></a><span data-ttu-id="c1ca5-309">Exemple de requête en main actuel 2</span><span class="sxs-lookup"><span data-stu-id="c1ca5-309">Current on-hand query example 2</span></span>

<span data-ttu-id="c1ca5-310">Cet exemple montre un scénario dans lequel aucun mappage n'est configuré pour la configuration de dimension dans Power Apps, donc la publication doit également utiliser les dimensions de base.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-310">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="c1ca5-311">Toutes les dimensions doivent être des dimensions de base lorsque le champ `dimensionDataSource`, sous `filters`, est nul, vide ou espace.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-311">All dimensions must be base dimensions when the `dimensionDataSource` field, under `filters` is null, empty, or whitespace.</span></span>

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

#### <a name="example-return-result"></a><span data-ttu-id="c1ca5-312">Exemple de résultat de retour</span><span class="sxs-lookup"><span data-stu-id="c1ca5-312">Example return result</span></span>

<span data-ttu-id="c1ca5-313">Les requêtes présentées dans les exemples précédents peuvent renvoyer un résultat comme celui-ci.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-313">The queries shown in the previous examples could return a result like this.</span></span>

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

<span data-ttu-id="c1ca5-314">Notez que les champs de quantités sont structurés comme un dictionnaire de mesures et de leurs valeurs associées.</span><span class="sxs-lookup"><span data-stu-id="c1ca5-314">Note that the quantities fields are structured as a dictionary of measures and their associated values.</span></span>
