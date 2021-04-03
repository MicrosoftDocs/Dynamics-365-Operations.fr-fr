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
ms.openlocfilehash: 4e588be2ac5aae395ca66e3c9a743a67d71db7c0
ms.sourcegitcommit: a3052f76ad71894dbef66566c07c6e2c31505870
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/10/2021
ms.locfileid: "5574220"
---
# <a name="inventory-visibility-add-in"></a><span data-ttu-id="bada2-103">Complément de visibilité de stock</span><span class="sxs-lookup"><span data-stu-id="bada2-103">Inventory Visibility Add-in</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

<span data-ttu-id="bada2-104">Le complément de visibilité de stock est un microservice indépendant et hautement évolutif qui permet un suivi des stocks en temps réel, offrant ainsi une vue globale de la visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="bada2-104">The Inventory Visibility Add-in is an independent and highly scalable microservice that enables real-time on-hand inventory tracking, thus providing a global view of inventory visibility.</span></span>

<span data-ttu-id="bada2-105">Toutes les informations relatives à l’inventaire disponible sont exportées vers le service en temps quasi réel via une intégration SQL de bas niveau.</span><span class="sxs-lookup"><span data-stu-id="bada2-105">All information that relates to on-hand inventory is exported to the service in near real-time through low-level SQL integration.</span></span> <span data-ttu-id="bada2-106">Les systèmes externes accèdent au service via des API RESTful pour interroger les informations disponibles sur des ensembles de dimensions donnés, récupérant ainsi une liste des positions disponibles.</span><span class="sxs-lookup"><span data-stu-id="bada2-106">External systems access the service through RESTful APIs to query on-hand information on given sets of dimensions, thus retrieving a list of available on-hand positions.</span></span>

<span data-ttu-id="bada2-107">La visibilité du stock est un microservice basé sur Microsoft Dataverse, ce qui signifie que vous pouvez l’étendre en créant des Power Apps et en appliquant Power BI pour fournir des fonctionnalités personnalisées pour répondre aux besoins de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="bada2-107">Inventory Visibility is a microservice built on Microsoft Dataverse, which means you can extend it by building Power Apps and applying Power BI to provide customized functionality to meet your business requirements.</span></span> <span data-ttu-id="bada2-108">Il est également possible de mettre à niveau l’index pour effectuer des requêtes d’inventaire.</span><span class="sxs-lookup"><span data-stu-id="bada2-108">It is also possible to upgrade the index to do inventory queries.</span></span>

<span data-ttu-id="bada2-109">La visibilité du stock fournit des options de configuration qui lui permettent de s’intégrer à plusieurs systèmes tiers.</span><span class="sxs-lookup"><span data-stu-id="bada2-109">Inventory Visibility provides configuration options that let it integrate with multiple third-party systems.</span></span> <span data-ttu-id="bada2-110">Il prend en charge la dimension de stock normalisée, l’extensibilité personnalisée et les quantités calculées normalisées et configurables.</span><span class="sxs-lookup"><span data-stu-id="bada2-110">It supports the standardized inventory dimension, customized extensibility, and standardized, configurable calculated quantities.</span></span>

<span data-ttu-id="bada2-111">Cette rubrique décrit comment installer et configurer le complément de visibilité de stock pour Dynamics 365 Supply Chain Management, et comment utiliser son interface de programmation d’application (API).</span><span class="sxs-lookup"><span data-stu-id="bada2-111">This topic describes how to install and configure the Inventory Visibility Add-in for Dynamics 365 Supply Chain Management, and how to use its application programming interface (API).</span></span>

## <a name="install-the-inventory-visibility-add-in"></a><span data-ttu-id="bada2-112">Installer le complément de visibilité de stock</span><span class="sxs-lookup"><span data-stu-id="bada2-112">Install the Inventory Visibility Add-in</span></span>

<span data-ttu-id="bada2-113">Vous devez installer le complément de visibilité de stock à l’aide de Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="bada2-113">You need to install the Inventory Visibility Add-in using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="bada2-114">LCS est un portail de collaboration qui fournit un environnement et un ensemble de services régulièrement mis à jour qui vous aident à gérer le cycle de vie des applications de vos applications Dynamics 365 Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bada2-114">LCS is a collaboration portal that provides an environment and a set of regularly updated services that help you manage the application lifecycle of your Dynamics 365 Finance and Operations apps.</span></span>

<span data-ttu-id="bada2-115">Pour plus d’informations, voir [Ressources Lifecycle Services](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span><span class="sxs-lookup"><span data-stu-id="bada2-115">For more information, see [Lifecycle Services resources](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span></span>

### <a name="prerequisites"></a><span data-ttu-id="bada2-116">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="bada2-116">Prerequisites</span></span>

<span data-ttu-id="bada2-117">Avant de pouvoir installer le complément Visibilité du stock, vous devez procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="bada2-117">Before you install the Inventory Visibility Add-in, you must do the following:</span></span>

- <span data-ttu-id="bada2-118">Obtenez un projet d’implémentation LCS avec au moins un environnement déployé.</span><span class="sxs-lookup"><span data-stu-id="bada2-118">Obtain an LCS implementation project with at least one environment deployed.</span></span>
- <span data-ttu-id="bada2-119">Assurez-vous que les conditions préalables à la configuration des compléments fournies dans la [Présentation des compléments](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) ont été remplies.</span><span class="sxs-lookup"><span data-stu-id="bada2-119">Make sure that the prerequisites for setting up add-ins provided in the [Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) have been completed.</span></span> <span data-ttu-id="bada2-120">La visibilité de l’inventaire ne nécessite pas de liaison en double écriture.</span><span class="sxs-lookup"><span data-stu-id="bada2-120">Inventory Visibility doesn't require dual-write linking.</span></span>
- <span data-ttu-id="bada2-121">Contactez l’équipe de visibilité de l’inventaire à [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) pour obtenir les trois fichiers requis suivants :</span><span class="sxs-lookup"><span data-stu-id="bada2-121">Contact the Inventory Visibility Team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the following three required files:</span></span>

    - `Inventory Visibility Dataverse Solution.zip`
    - `Inventory Visibility Configuration Trigger.zip`
    - <span data-ttu-id="bada2-122">`Inventory Visibility Integration.zip` (si la version de Supply Chain Management que vous exécutez est antérieure à la version 10.0.18)</span><span class="sxs-lookup"><span data-stu-id="bada2-122">`Inventory Visibility Integration.zip` (if the version of Supply Chain Management that you're running is earlier than version 10.0.18)</span></span>

> [!NOTE]
> <span data-ttu-id="bada2-123">Les régions actuellement pris en charge comprennent le Canada, les États-Unis et l’Union européenne (UE).</span><span class="sxs-lookup"><span data-stu-id="bada2-123">The currently supported countries and regions include Canada, the United States, and the European Union (EU).</span></span>

<span data-ttu-id="bada2-124">Si vous avez des questions sur ces conditions préalables, contactez l’équipe produit de visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="bada2-124">If you have any questions about these prerequisites, please contact the Inventory Visibility product team.</span></span>

### <a name="set-up-dataverse"></a><a name="setup-microsoft-dataverse"></a><span data-ttu-id="bada2-125">Paramétrer Dataverse</span><span class="sxs-lookup"><span data-stu-id="bada2-125">Set up Dataverse</span></span>

<span data-ttu-id="bada2-126">Pour configurer Dataverse, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="bada2-126">Follow these steps to set up Dataverse.</span></span>

1. <span data-ttu-id="bada2-127">Ajoutez un principe de service à votre locataire :</span><span class="sxs-lookup"><span data-stu-id="bada2-127">Add a service principle to your tenant:</span></span>

    1. <span data-ttu-id="bada2-128">Installer Azure AD PowerShell Module v2 comme décrit dans [Installer Azure Active Directory PowerShell pour Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="bada2-128">Install Azure AD PowerShell Module v2 as described in [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
    1. <span data-ttu-id="bada2-129">Exécutez la commande suivante PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bada2-129">Run the following PowerShell command.</span></span>

        ```powershell
        Connect-AzureAD # (open a sign in window and sign in as a tenant user)

        New-AzureADServicePrincipal -AppId "3022308a-b9bd-4a18-b8ac-2ddedb2075e1" -DisplayName "d365-scm-inventoryservice"
        ```

1. <span data-ttu-id="bada2-130">Créer un utilisateur d’application pour la visibilité de l’inventaire dans Dataverse :</span><span class="sxs-lookup"><span data-stu-id="bada2-130">Create an application user for Inventory Visibility in Dataverse:</span></span>

    1. <span data-ttu-id="bada2-131">Ouvrez l’URL de votre environnement Dataverse.</span><span class="sxs-lookup"><span data-stu-id="bada2-131">Open the URL of your Dataverse environment.</span></span>
    1. <span data-ttu-id="bada2-132">Aller à **Paramètre avancé \> Système \> Sécurité \> Utilisateurs** et créez un utilisateur d’application.</span><span class="sxs-lookup"><span data-stu-id="bada2-132">Go to **Advanced Setting \> System \> Security \> Users**, and create an application user.</span></span> <span data-ttu-id="bada2-133">Utilisez le menu de la vue pour changez la vue de la page sur **Utilisateurs de l’application**.</span><span class="sxs-lookup"><span data-stu-id="bada2-133">Use the view menu to change the page view to **Application Users**.</span></span>
    1. <span data-ttu-id="bada2-134">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="bada2-134">Select **New**.</span></span> <span data-ttu-id="bada2-135">Définissez l’ID application sur *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*.</span><span class="sxs-lookup"><span data-stu-id="bada2-135">Set the application ID to *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*.</span></span> <span data-ttu-id="bada2-136">(L’ID d’objet sera automatiquement chargé lorsque vous enregistrez vos modifications.) Vous pouvez personnaliser le nom.</span><span class="sxs-lookup"><span data-stu-id="bada2-136">(The object ID will automatically be loaded when you save your changes.) You can customize the name.</span></span> <span data-ttu-id="bada2-137">Par exemple, vous pouvez le changer en *Visibilité de l’inventaire*.</span><span class="sxs-lookup"><span data-stu-id="bada2-137">For example, you can change it to *Inventory Visibility*.</span></span> <span data-ttu-id="bada2-138">Lorsque vous avez terminé, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="bada2-138">When you've finished, select **Save**.</span></span>
    1. <span data-ttu-id="bada2-139">Sélectionner **Attribuer un rôle**, puis **Administrateur système**.</span><span class="sxs-lookup"><span data-stu-id="bada2-139">Select **Assign Role**, and then select **System Administrator**.</span></span> <span data-ttu-id="bada2-140">S’il y a un rôle nommé **Utilisateur Common Data Service**, sélectionnez-le aussi.</span><span class="sxs-lookup"><span data-stu-id="bada2-140">If there is a role that is named **Common Data Service User**, select it too.</span></span>

    <span data-ttu-id="bada2-141">Pour plus d’informations, voir [Créer un utilisateur d’application](https://docs.microsoft.com/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span><span class="sxs-lookup"><span data-stu-id="bada2-141">For more information, see [Create an application user](https://docs.microsoft.com/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span></span>

1. <span data-ttu-id="bada2-142">Importez le fichier `Inventory Visibility Dataverse Solution.zip`, qui comprend entités liées à la configuration Dataverse et Power Apps :</span><span class="sxs-lookup"><span data-stu-id="bada2-142">Import the `Inventory Visibility Dataverse Solution.zip` file, which includes Dataverse configuration related entities and Power Apps:</span></span>

    1. <span data-ttu-id="bada2-143">Allez sur la page **Solutions**.</span><span class="sxs-lookup"><span data-stu-id="bada2-143">Go to the **Solutions** page.</span></span>
    1. <span data-ttu-id="bada2-144">Sélectionnez **Importer**.</span><span class="sxs-lookup"><span data-stu-id="bada2-144">Select **Import**.</span></span>

1. <span data-ttu-id="bada2-145">Importez le flux de déclenchement de la mise à niveau de la configuration :</span><span class="sxs-lookup"><span data-stu-id="bada2-145">Import the configuration upgrade trigger flow:</span></span>

    1. <span data-ttu-id="bada2-146">Allez sur la page Microsoft Flow.</span><span class="sxs-lookup"><span data-stu-id="bada2-146">Go to the Microsoft Flow page.</span></span>
    1. <span data-ttu-id="bada2-147">Assurez-vous que la connexion nommée *Dataverse (héritée)* existe.</span><span class="sxs-lookup"><span data-stu-id="bada2-147">Make sure that the connection that is named *Dataverse (legacy)* exists.</span></span> <span data-ttu-id="bada2-148">(S’il n’existe pas, créez-le.)</span><span class="sxs-lookup"><span data-stu-id="bada2-148">(If it doesn't exist, create it.)</span></span>
    1. <span data-ttu-id="bada2-149">Importer le fichier `Inventory Visibility Configuration Trigger.zip`.</span><span class="sxs-lookup"><span data-stu-id="bada2-149">Import the `Inventory Visibility Configuration Trigger.zip` file.</span></span> <span data-ttu-id="bada2-150">Une fois importé, le déclencheur apparaîtra sous **Mes flux**.</span><span class="sxs-lookup"><span data-stu-id="bada2-150">After it's imported, the trigger will appear under **My flows**.</span></span>
    1. <span data-ttu-id="bada2-151">Initialisez les quatre variables suivantes, en fonction des informations d’environnement :</span><span class="sxs-lookup"><span data-stu-id="bada2-151">Initialize the following four variables, based on the environment information:</span></span>

        - <span data-ttu-id="bada2-152">ID de locataire Azure</span><span class="sxs-lookup"><span data-stu-id="bada2-152">Azure Tenant ID</span></span>
        - <span data-ttu-id="bada2-153">ID client application Azure</span><span class="sxs-lookup"><span data-stu-id="bada2-153">Azure Application Client ID</span></span>
        - <span data-ttu-id="bada2-154">Clé secrète client application Azure</span><span class="sxs-lookup"><span data-stu-id="bada2-154">Azure Application Client Secret</span></span>
        - <span data-ttu-id="bada2-155">Point de terminaison de la visibilité du stock</span><span class="sxs-lookup"><span data-stu-id="bada2-155">Inventory Visibility Endpoint</span></span>

            <span data-ttu-id="bada2-156">Pour plus d’informations sur cette variable, consultez la section [Configurer l’intégration de la visibilité de l’inventaire](#setup-inventory-visibility-integration) plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="bada2-156">For more information about this variable, see the [Set up Inventory Visibility integration](#setup-inventory-visibility-integration) section later in this topic.</span></span>

        <span data-ttu-id="bada2-157">![déclencheur de configuration](media/configuration-trigger.png "déclencheur de configuration")</span><span class="sxs-lookup"><span data-stu-id="bada2-157">![Configuration trigger](media/configuration-trigger.png "Configuration trigger")</span></span>

    1. <span data-ttu-id="bada2-158">Sélectionnez **Activer**.</span><span class="sxs-lookup"><span data-stu-id="bada2-158">Select **Turn on**.</span></span>

### <a name="install-the-add-in"></a><a name="install-add-in"></a><span data-ttu-id="bada2-159">Installer le complément</span><span class="sxs-lookup"><span data-stu-id="bada2-159">Install the add-in</span></span>

<span data-ttu-id="bada2-160">Pour pouvoir installer le complément Visibilité du stock, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="bada2-160">To install the Inventory Visibility Add-in, do the following:</span></span>

1. <span data-ttu-id="bada2-161">Connectez-vous au portail [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="bada2-161">Sign in to the [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portal.</span></span>
1. <span data-ttu-id="bada2-162">Sur la page d’accueil, sélectionnez le projet dans lequel votre environnement est déployé.</span><span class="sxs-lookup"><span data-stu-id="bada2-162">On the home page, select the project where your environment is deployed.</span></span>
1. <span data-ttu-id="bada2-163">Sur la page du projet, sélectionnez l’environnement dans lequel vous souhaitez installer le complément.</span><span class="sxs-lookup"><span data-stu-id="bada2-163">On the project page, select the environment where you want to install the add-in.</span></span>
1. <span data-ttu-id="bada2-164">Sur la page d’environnement, faites défiler vers le bas jusqu’à ce que vous voyiez la section **Compléments d’environnement** dans la section **Intégration Power Platform**, où vous pouvez trouver le nom de l’environnement Dataverse.</span><span class="sxs-lookup"><span data-stu-id="bada2-164">On the environment page, scroll down until you see the **Environment add-ins** section in the **Power Platform integration** section, where you can find the Dataverse environment name.</span></span>
1. <span data-ttu-id="bada2-165">Dans la section **Compléments de l’environnement**, sélectionnez **Installer un nouveau complément**.</span><span class="sxs-lookup"><span data-stu-id="bada2-165">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>

    <span data-ttu-id="bada2-166">![Page de l’environnement dans LCS](media/inventory-visibility-environment.png "Page de l’environnement dans LCS")</span><span class="sxs-lookup"><span data-stu-id="bada2-166">![The environment page in LCS](media/inventory-visibility-environment.png "The environment page in LCS")</span></span>

1. <span data-ttu-id="bada2-167">Sélectionnez le lien **Installer un nouveau complément**.</span><span class="sxs-lookup"><span data-stu-id="bada2-167">Select the **Install a new add-in** link.</span></span> <span data-ttu-id="bada2-168">Une liste des compléments disponibles s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="bada2-168">A list of available add-ins opens.</span></span>
1. <span data-ttu-id="bada2-169">Dans la liste, sélectionnez **visibilité de stock**.</span><span class="sxs-lookup"><span data-stu-id="bada2-169">Select **Inventory Visibility** in the list.</span></span>
1. <span data-ttu-id="bada2-170">Saisissez des valeurs pour les champs suivants pour votre environnement :</span><span class="sxs-lookup"><span data-stu-id="bada2-170">Enter values for the following fields for your environment:</span></span>

    - <span data-ttu-id="bada2-171">**ID application AAD (client)**</span><span class="sxs-lookup"><span data-stu-id="bada2-171">**AAD application (client) ID**</span></span>
    - <span data-ttu-id="bada2-172">**ID locataire AAD**</span><span class="sxs-lookup"><span data-stu-id="bada2-172">**AAD tenant ID**</span></span>

    <span data-ttu-id="bada2-173">![Ajouter dans la page de configuration](media/inventory-visibility-setup.png "Page de configuration de complément")</span><span class="sxs-lookup"><span data-stu-id="bada2-173">![Add in setup page](media/inventory-visibility-setup.png "Add-in setup page")</span></span>

1. <span data-ttu-id="bada2-174">Acceptez les termes et conditions en cochant la case **Termes et conditions**.</span><span class="sxs-lookup"><span data-stu-id="bada2-174">Agree to the terms and condition by selecting the **Terms and conditions** check box.</span></span>
1. <span data-ttu-id="bada2-175">Sélectionnez **Installer**.</span><span class="sxs-lookup"><span data-stu-id="bada2-175">Select **Install**.</span></span> <span data-ttu-id="bada2-176">Le statut du complément s’affichera comme **Installation en cours**.</span><span class="sxs-lookup"><span data-stu-id="bada2-176">The status of the add-in will show as **Installing**.</span></span> <span data-ttu-id="bada2-177">Une fois terminé, actualisez la page pour voir le statut changer en **Installé**.</span><span class="sxs-lookup"><span data-stu-id="bada2-177">When it's done, refresh the page to see the status change to **Installed**.</span></span>

### <a name="uninstall-the-add-in"></a><a name="uninstall-add-in"></a><span data-ttu-id="bada2-178">Désinstaller le complément</span><span class="sxs-lookup"><span data-stu-id="bada2-178">Uninstall the add-in</span></span>

<span data-ttu-id="bada2-179">Pour désinstaller le complément, sélectionnez **Désinstaller**.</span><span class="sxs-lookup"><span data-stu-id="bada2-179">To uninstall the add-in, select **Uninstall**.</span></span> <span data-ttu-id="bada2-180">Lorsque vous actualisez LCS et le complément de visibilité de stock seront supprimés.</span><span class="sxs-lookup"><span data-stu-id="bada2-180">When you refresh LCS, the Inventory Visibility Add-in will be removed.</span></span> <span data-ttu-id="bada2-181">Le processus de désinstallation supprime l’inscription du complément et lance également une tâche pour nettoyer toutes les données d’entreprise stockées dans le service.</span><span class="sxs-lookup"><span data-stu-id="bada2-181">The uninstall process removes the add-in registration and also starts a job to clean up all the business data that is stored in the service.</span></span>

## <a name="consume-on-hand-inventory-data-from-supply-chain-management"></a><span data-ttu-id="bada2-182">Consommez les données d’inventaire disponibles à partir de Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="bada2-182">Consume on-hand inventory data from Supply Chain Management</span></span>

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a><span data-ttu-id="bada2-183">Déployer le package d’intégration de la visibilité d’inventaire</span><span class="sxs-lookup"><span data-stu-id="bada2-183">Deploy the Inventory Visibility integration package</span></span>

<span data-ttu-id="bada2-184">Si vous exécutez la version 10.0.17 ou antérieure de Supply Chain Management, contactez l’équipe d’assistance intégrée de la visibilité d’inventaire à l’adresse [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) pour obtenir le fichier de package.</span><span class="sxs-lookup"><span data-stu-id="bada2-184">If you're running Supply Chain Management version 10.0.17 or earlier, contact the Inventory Visibility on-board support team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the package file.</span></span> <span data-ttu-id="bada2-185">Déployez ensuite le package dans LCS.</span><span class="sxs-lookup"><span data-stu-id="bada2-185">Then deploy the package in LCS.</span></span>

> [!NOTE]
> <span data-ttu-id="bada2-186">Si une erreur de non-concordance de version se produit pendant le déploiement, vous devez importer manuellement le projet X++ dans votre environnement de développement.</span><span class="sxs-lookup"><span data-stu-id="bada2-186">If a version mismatch error occurs during deployment, you must manually import the X++ project into your development environment.</span></span> <span data-ttu-id="bada2-187">Créez ensuite le package déployable dans votre environnement de développement et déployez-le dans votre environnement de production.</span><span class="sxs-lookup"><span data-stu-id="bada2-187">Then create the deployable package in your development environment, and deploy it in your production environment.</span></span>
> 
> <span data-ttu-id="bada2-188">Le code est inclus dans la version 10.0.18 de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bada2-188">The code is included with Supply Chain Management version 10.0.18.</span></span> <span data-ttu-id="bada2-189">Si vous exécutez cette version ou une version ultérieure, le déploiement n’est pas requis.</span><span class="sxs-lookup"><span data-stu-id="bada2-189">If you're running that version or later, deployment isn't required.</span></span>

<span data-ttu-id="bada2-190">Assurez-vous que les fonctionnalités suivantes sont activées dans votre environnement Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bada2-190">Make sure that the following features are turned on in your Supply Chain Management environment.</span></span> <span data-ttu-id="bada2-191">(Par défaut, ils sont identiques.)</span><span class="sxs-lookup"><span data-stu-id="bada2-191">(By default, they are turned on.)</span></span>

| <span data-ttu-id="bada2-192">Description de fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="bada2-192">Feature description</span></span> | <span data-ttu-id="bada2-193">Version du code</span><span class="sxs-lookup"><span data-stu-id="bada2-193">Code version</span></span> | <span data-ttu-id="bada2-194">Basculer la classe</span><span class="sxs-lookup"><span data-stu-id="bada2-194">Toggle class</span></span> |
|---|---|---|
| <span data-ttu-id="bada2-195">Activer ou désactiver l’utilisation des dimensions d’inventaire sur le tableau InventSum</span><span class="sxs-lookup"><span data-stu-id="bada2-195">Enable or disable using inventory dimensions on InventSum table</span></span> | <span data-ttu-id="bada2-196">10.0.11</span><span class="sxs-lookup"><span data-stu-id="bada2-196">10.0.11</span></span> | <span data-ttu-id="bada2-197">InventUseDimOfInventSumToggle</span><span class="sxs-lookup"><span data-stu-id="bada2-197">InventUseDimOfInventSumToggle</span></span> |
| <span data-ttu-id="bada2-198">Activer ou désactiver l’utilisation des dimensions d’inventaire sur le tableau InventSumDelta</span><span class="sxs-lookup"><span data-stu-id="bada2-198">Enable or disable using inventory dimensions on InventSumDelta table</span></span> | <span data-ttu-id="bada2-199">10.0.12</span><span class="sxs-lookup"><span data-stu-id="bada2-199">10.0.12</span></span> | <span data-ttu-id="bada2-200">InventUseDimOfInventSumDeltaToggle</span><span class="sxs-lookup"><span data-stu-id="bada2-200">InventUseDimOfInventSumDeltaToggle</span></span> |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a><span data-ttu-id="bada2-201">Configurer l’intégration de la visibilité du stock</span><span class="sxs-lookup"><span data-stu-id="bada2-201">Set up Inventory Visibility integration</span></span>

1. <span data-ttu-id="bada2-202">Dans Supply Chain Management, ouvrez l’espace de travail **[Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** et activez la fonctionnalité **Intégration de la visibilité de l’inventaire**.</span><span class="sxs-lookup"><span data-stu-id="bada2-202">In Supply Chain Management, open the **[Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** workspace, and turn on the **Inventory Visibility Integration** feature.</span></span>
1. <span data-ttu-id="bada2-203">Aller à **Gestion de l’inventaire \> Installation \> Paramètres d’intégration de la visibilité de l’inventaire** et entrez l’URL de l’environnement dans lequel vous exécutez la visibilité de l’inventaire.</span><span class="sxs-lookup"><span data-stu-id="bada2-203">Go to **Inventory Management \> Set up \> Inventory Visibility Integration parameters**, and enter the URL of the environment where you're running Inventory Visibility.</span></span>

    <span data-ttu-id="bada2-204">Recherchez la région Azure de votre environnement LCS, puis entrez l’URL.</span><span class="sxs-lookup"><span data-stu-id="bada2-204">Find your LCS environment's Azure region, and then enter the URL.</span></span> <span data-ttu-id="bada2-205">L’URL a le format suivant :</span><span class="sxs-lookup"><span data-stu-id="bada2-205">The URL has the following form:</span></span>

    `https://inventoryservice.<RegionShortName>-il301.gateway.prod.island.powerapps.com/`

    <span data-ttu-id="bada2-206">Par exemple, si vous êtes en Europe, votre environnement aura l’une des URL suivantes :</span><span class="sxs-lookup"><span data-stu-id="bada2-206">For example, if you're in Europe, your environment will have one of the following URLs:</span></span>

    - `https://inventoryservice.neu-il301.gateway.prod.island.powerapps.com/`
    - `https://inventoryservice.weu-il301.gateway.prod.island.powerapps.com/`

    <span data-ttu-id="bada2-207">Les régions suivantes sont disponibles actuellement.</span><span class="sxs-lookup"><span data-stu-id="bada2-207">The following regions are currently available.</span></span>

    | <span data-ttu-id="bada2-208">Région Azure</span><span class="sxs-lookup"><span data-stu-id="bada2-208">Azure region</span></span> | <span data-ttu-id="bada2-209">Nom abrégé de la région</span><span class="sxs-lookup"><span data-stu-id="bada2-209">Region short name</span></span> |
    |---|---|
    | <span data-ttu-id="bada2-210">Est de l’Australie</span><span class="sxs-lookup"><span data-stu-id="bada2-210">Australia east</span></span> | <span data-ttu-id="bada2-211">eau</span><span class="sxs-lookup"><span data-stu-id="bada2-211">eau</span></span> |
    | <span data-ttu-id="bada2-212">Sud-est de l’Australie</span><span class="sxs-lookup"><span data-stu-id="bada2-212">Australia southeast</span></span> | <span data-ttu-id="bada2-213">seau</span><span class="sxs-lookup"><span data-stu-id="bada2-213">seau</span></span> |
    | <span data-ttu-id="bada2-214">Centre du Canada</span><span class="sxs-lookup"><span data-stu-id="bada2-214">Canada central</span></span> | <span data-ttu-id="bada2-215">cca</span><span class="sxs-lookup"><span data-stu-id="bada2-215">cca</span></span> |
    | <span data-ttu-id="bada2-216">Canada Est</span><span class="sxs-lookup"><span data-stu-id="bada2-216">Canada east</span></span> | <span data-ttu-id="bada2-217">eca</span><span class="sxs-lookup"><span data-stu-id="bada2-217">eca</span></span> |
    | <span data-ttu-id="bada2-218">Nord de l’Europe</span><span class="sxs-lookup"><span data-stu-id="bada2-218">North Europe</span></span> | <span data-ttu-id="bada2-219">neu</span><span class="sxs-lookup"><span data-stu-id="bada2-219">neu</span></span> |
    | <span data-ttu-id="bada2-220">Ouest de l’Europe</span><span class="sxs-lookup"><span data-stu-id="bada2-220">West Europe</span></span> | <span data-ttu-id="bada2-221">weu</span><span class="sxs-lookup"><span data-stu-id="bada2-221">weu</span></span> |
    | <span data-ttu-id="bada2-222">Est des États-Unis</span><span class="sxs-lookup"><span data-stu-id="bada2-222">East US</span></span> | <span data-ttu-id="bada2-223">eus</span><span class="sxs-lookup"><span data-stu-id="bada2-223">eus</span></span> |
    | <span data-ttu-id="bada2-224">Ouest des États-Unis</span><span class="sxs-lookup"><span data-stu-id="bada2-224">West US</span></span> | <span data-ttu-id="bada2-225">wus</span><span class="sxs-lookup"><span data-stu-id="bada2-225">wus</span></span> |

1. <span data-ttu-id="bada2-226">Aller à **Gestion de l’inventaire \> Périodique \> Intégration de la visibilité de l’inventaire** et activez le travail.</span><span class="sxs-lookup"><span data-stu-id="bada2-226">Go to **Inventory Management \> Periodic \> Inventory Visibility Integration**, and enable the job.</span></span> <span data-ttu-id="bada2-227">Tous les événements de changement d’inventaire de Supply Chain Management seront désormais publiés dans la visibilité des stocks.</span><span class="sxs-lookup"><span data-stu-id="bada2-227">All inventory change events from Supply Chain Management will now be posted to Inventory Visibility.</span></span>

## <a name="the-inventory-visibility-add-in-public-api"></a><a name="inventory-visibility-public-api"></a><span data-ttu-id="bada2-228">L’API publique du complément de visibilité de stock</span><span class="sxs-lookup"><span data-stu-id="bada2-228">The Inventory Visibility Add-in public API</span></span>

<span data-ttu-id="bada2-229">L’API REST publique du complément de visibilité de stock présente plusieurs points de terminaison d’intégration spécifiques.</span><span class="sxs-lookup"><span data-stu-id="bada2-229">The public REST API of the Inventory Visibility Add-in presents several specific endpoints for integration.</span></span> <span data-ttu-id="bada2-230">Elle prend en charge trois types d’interactions principaux :</span><span class="sxs-lookup"><span data-stu-id="bada2-230">It supports three main interaction types:</span></span>

- <span data-ttu-id="bada2-231">Publication des modifications de stock disponibles du complément à partir d’un système externe</span><span class="sxs-lookup"><span data-stu-id="bada2-231">Posting on-hand inventory changes to the add-in from an external system</span></span>
- <span data-ttu-id="bada2-232">Interrogation des quantités en stock actuelles à partir d’un système externe</span><span class="sxs-lookup"><span data-stu-id="bada2-232">Querying current on-hand quantities from an external system</span></span>
- <span data-ttu-id="bada2-233">Synchronisation automatique avec le stock Supply Chain Management à portée de main</span><span class="sxs-lookup"><span data-stu-id="bada2-233">Automatic synchronization with Supply Chain Management on-hand inventory</span></span>

<span data-ttu-id="bada2-234">La synchronisation automatique ne fait pas partie de l’API publique.</span><span class="sxs-lookup"><span data-stu-id="bada2-234">Automatic synchronization isn't part of the public API.</span></span> <span data-ttu-id="bada2-235">Au lieu de cela, il est géré en arrière-plan pour les environnements dans lesquels le complément de visibilité d’inventaire est activé.</span><span class="sxs-lookup"><span data-stu-id="bada2-235">Instead, it's handled in the background for environments where the Inventory Visibility Add-in is enabled.</span></span>

### <a name="authentication"></a><a name="inventory-visibility-authentication"></a><span data-ttu-id="bada2-236">Authentification</span><span class="sxs-lookup"><span data-stu-id="bada2-236">Authentication</span></span>

<span data-ttu-id="bada2-237">Le jeton de sécurité de la plateforme est utilisé pour appeler le complément de visibilité d’inventaire.</span><span class="sxs-lookup"><span data-stu-id="bada2-237">The platform security token is used to call the Inventory Visibility Add-in.</span></span> <span data-ttu-id="bada2-238">Par conséquent, vous devez générer un jeton *Azure Active Directory (Azure AD)* en utilisant votre application Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bada2-238">Therefore, you must generate an *Azure Active Directory (Azure AD) token* by using your Azure AD application.</span></span> <span data-ttu-id="bada2-239">Vous devez ensuite utiliser le jeton Azure AD pour obtenir le *jeton d’accès* du service de sécurité.</span><span class="sxs-lookup"><span data-stu-id="bada2-239">You must then use the Azure AD token to get the *access token* from the security service.</span></span>

<span data-ttu-id="bada2-240">Obtenez un jeton de service de sécurité en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="bada2-240">Get a security service token by doing the following:</span></span>

1. <span data-ttu-id="bada2-241">Connectez-vous au portail Azure et utilisez-le pour trouver le `clientId` et le `clientSecret` de votre application Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bada2-241">Sign in to Azure portal and use it to find the `clientId` and `clientSecret` for your Supply Chain Management application.</span></span>
1. <span data-ttu-id="bada2-242">Récupérez un jeton Azure Active Directory (`aadToken`) en envoyant une requête HTTP avec les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="bada2-242">Fetch an Azure Active Directory token (`aadToken`) by submitting an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="bada2-243">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span><span class="sxs-lookup"><span data-stu-id="bada2-243">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span></span>
    - <span data-ttu-id="bada2-244">**Méthode** - `GET`</span><span class="sxs-lookup"><span data-stu-id="bada2-244">**Method** - `GET`</span></span>
    - <span data-ttu-id="bada2-245">**Contenu du corps (données du formulaire)**  :</span><span class="sxs-lookup"><span data-stu-id="bada2-245">**Body content (form data)**:</span></span>

        | <span data-ttu-id="bada2-246">clé</span><span class="sxs-lookup"><span data-stu-id="bada2-246">key</span></span> | <span data-ttu-id="bada2-247">valeur</span><span class="sxs-lookup"><span data-stu-id="bada2-247">value</span></span> |
        | --- | --- |
        | <span data-ttu-id="bada2-248">client_id</span><span class="sxs-lookup"><span data-stu-id="bada2-248">client_id</span></span> | <span data-ttu-id="bada2-249">${aadAppId}</span><span class="sxs-lookup"><span data-stu-id="bada2-249">${aadAppId}</span></span> |
        | <span data-ttu-id="bada2-250">client_secret</span><span class="sxs-lookup"><span data-stu-id="bada2-250">client_secret</span></span> | <span data-ttu-id="bada2-251">${aadAppSecret}</span><span class="sxs-lookup"><span data-stu-id="bada2-251">${aadAppSecret}</span></span> |
        | <span data-ttu-id="bada2-252">grant_type</span><span class="sxs-lookup"><span data-stu-id="bada2-252">grant_type</span></span> | <span data-ttu-id="bada2-253">client_credentials</span><span class="sxs-lookup"><span data-stu-id="bada2-253">client_credentials</span></span> |
        | <span data-ttu-id="bada2-254">resource</span><span class="sxs-lookup"><span data-stu-id="bada2-254">resource</span></span> | <span data-ttu-id="bada2-255">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="bada2-255">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
1. <span data-ttu-id="bada2-256">Vous devriez recevoir un `aadToken` en réponse, qui ressemble à l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="bada2-256">You should receive an `aadToken` in response, which resembles the following example.</span></span>

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

1. <span data-ttu-id="bada2-257">Formulez une requête JSON qui ressemble à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="bada2-257">Formulate a JSON request that resembles the following:</span></span>

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

    <span data-ttu-id="bada2-258">Où :</span><span class="sxs-lookup"><span data-stu-id="bada2-258">Where:</span></span>
    - <span data-ttu-id="bada2-259">La valeur `client_assertion` doit être le `aadToken` que vous avez reçu à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="bada2-259">The `client_assertion` value must be the `aadToken` you received in the previous step.</span></span>
    - <span data-ttu-id="bada2-260">La valeur `context` doit être l’ID d’environnement dans lequel vous souhaitez déployer le complément.</span><span class="sxs-lookup"><span data-stu-id="bada2-260">The `context` value must be the environment ID where you want to deploy the add-in.</span></span>
    - <span data-ttu-id="bada2-261">Définissez toutes les autres valeurs comme indiqué dans l’exemple.</span><span class="sxs-lookup"><span data-stu-id="bada2-261">Set all of other values as shown in the example.</span></span>

1. <span data-ttu-id="bada2-262">Envoyez une requête HTTP avec les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="bada2-262">Submit an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="bada2-263">**URL** - `https://securityservice.operations365.dynamics.com/token`</span><span class="sxs-lookup"><span data-stu-id="bada2-263">**URL** - `https://securityservice.operations365.dynamics.com/token`</span></span>
    - <span data-ttu-id="bada2-264">**Méthode** - `POST`</span><span class="sxs-lookup"><span data-stu-id="bada2-264">**Method** - `POST`</span></span>
    - <span data-ttu-id="bada2-265">**En-tête HTTP** : incluez la version de l’API (la clé est `Api-Version` et la valeur est `1.0`)</span><span class="sxs-lookup"><span data-stu-id="bada2-265">**HTTP header** - Include the API version (key is `Api-Version` and value is `1.0`)</span></span>
    - <span data-ttu-id="bada2-266">**Contenu du corps** : incluez la requête JSON que vous avez créée à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="bada2-266">**Body content** - Include the JSON request that you created in the previous step.</span></span>

1. <span data-ttu-id="bada2-267">Vous obtiendrez un `access_token` en réponse.</span><span class="sxs-lookup"><span data-stu-id="bada2-267">You will get an `access_token` in response.</span></span> <span data-ttu-id="bada2-268">C’est ce dont vous avez besoin en tant que jeton de support pour appeler l’API de visibilité de stock.</span><span class="sxs-lookup"><span data-stu-id="bada2-268">This is what you need as a bearer token to call the Inventory Visibility API.</span></span> <span data-ttu-id="bada2-269">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="bada2-269">Here is an example.</span></span>

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="configure-the-inventory-visibility-api"></a><a name="inventory-visibility-configuration"></a><span data-ttu-id="bada2-270">Configurer l’API de visibilité de stock</span><span class="sxs-lookup"><span data-stu-id="bada2-270">Configure the Inventory Visibility API</span></span>

<span data-ttu-id="bada2-271">Avant d’utiliser le service, vous devez effectuer les configurations décrites dans les sous-sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="bada2-271">Before using the service, you must complete the configurations described in the following subsections.</span></span> <span data-ttu-id="bada2-272">La configuration peut varier en fonction des détails de votre environnement.</span><span class="sxs-lookup"><span data-stu-id="bada2-272">The configuration may vary based on the details of your environment.</span></span> <span data-ttu-id="bada2-273">Il comprend principalement quatre parties :</span><span class="sxs-lookup"><span data-stu-id="bada2-273">It primarily includes four parts:</span></span>

- [<span data-ttu-id="bada2-274">Partitionnement</span><span class="sxs-lookup"><span data-stu-id="bada2-274">Partitioning</span></span>](#partitioning)
- [<span data-ttu-id="bada2-275">Configurations des dimensions</span><span class="sxs-lookup"><span data-stu-id="bada2-275">Dimension configurations</span></span>](#dimension-configurations)
- [<span data-ttu-id="bada2-276">Indexation</span><span class="sxs-lookup"><span data-stu-id="bada2-276">Indexing</span></span>](#indexing)
- [<span data-ttu-id="bada2-277">Mesure personnalisée</span><span class="sxs-lookup"><span data-stu-id="bada2-277">Custom measurement</span></span>](#custom-measurement)

#### <a name="partitioning"></a><span data-ttu-id="bada2-278">Partitionnement</span><span class="sxs-lookup"><span data-stu-id="bada2-278">Partitioning</span></span>

<span data-ttu-id="bada2-279">Le partitionnement peut influencer considérablement les performances de l’API de visibilité d’inventaire.</span><span class="sxs-lookup"><span data-stu-id="bada2-279">Partitioning can significantly influence the performance of the Inventory Visibility API.</span></span> <span data-ttu-id="bada2-280">C’est une bonne idée de définir un schéma qui permet de petits regroupements de données tout en permettant des requêtes de données significatives.</span><span class="sxs-lookup"><span data-stu-id="bada2-280">It's a good idea to define a scheme that allows for small groupings of data while still allowing for meaningful data queries.</span></span>

<span data-ttu-id="bada2-281">L’`organizationId` (`dataAreaId` dans Supply Chain Management) fera toujours partie du partitionnement et, par défaut, la visibilité du stock est définie pour partitionner par dimensions comme *Site + Localisation*.</span><span class="sxs-lookup"><span data-stu-id="bada2-281">The `organizationId` (`dataAreaId` in Supply Chain Management) will always be part of the partitioning, and by default Inventory Visibility is set to partition by dimensions as *Site + Location*.</span></span> <span data-ttu-id="bada2-282">Cela signifie que le service doit toujours être interrogé avec ces dimensions définies sur les filtres.</span><span class="sxs-lookup"><span data-stu-id="bada2-282">This means that the service must always be queried with these dimensions defined on the filters.</span></span>

> [!NOTE]
> <span data-ttu-id="bada2-283">*Site* et *Emplacement* sont deux dimensions générales par défaut dans la visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="bada2-283">*Site* and *Location* are two general default dimensions in Inventory Visibility.</span></span> <span data-ttu-id="bada2-284">Dans Supply Chain Management, ces dimensions sont appelées *Site* (`InventSiteId`) et *Entrepôt* (`InventLocationId`)</span><span class="sxs-lookup"><span data-stu-id="bada2-284">In Supply Chain Management, those dimensions are called *Site* (`InventSiteId`) and *Warehouse* (`InventLocationId`)</span></span>

### <a name="dimension-configurations"></a><span data-ttu-id="bada2-285">Configurations des dimensions</span><span class="sxs-lookup"><span data-stu-id="bada2-285">Dimension configurations</span></span>

<span data-ttu-id="bada2-286">La visibilité du stock fournira une liste de dimensions générales par défaut pour permettre l’intégration du système source multiple.</span><span class="sxs-lookup"><span data-stu-id="bada2-286">Inventory Visibility will provide a list of general default dimensions to enable the multiple source system integration.</span></span>

<span data-ttu-id="bada2-287">Le tableau suivant répertorie les dimensions d’inventaire qui seront les noms de dimension par défaut dans la visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="bada2-287">The following table lists the inventory dimensions that will be the default dimension names in Inventory Visibility.</span></span>

| <span data-ttu-id="bada2-288">Type de dimension</span><span class="sxs-lookup"><span data-stu-id="bada2-288">Dimension type</span></span> | <span data-ttu-id="bada2-289">Nom de dimension</span><span class="sxs-lookup"><span data-stu-id="bada2-289">Dimension name</span></span> |
|---|---|
| <span data-ttu-id="bada2-290">Produit</span><span class="sxs-lookup"><span data-stu-id="bada2-290">Product</span></span> | `ColorId` |
| <span data-ttu-id="bada2-291">Produit</span><span class="sxs-lookup"><span data-stu-id="bada2-291">Product</span></span> | `SizeId` |
| <span data-ttu-id="bada2-292">Produit</span><span class="sxs-lookup"><span data-stu-id="bada2-292">Product</span></span> | `StyleId` |
| <span data-ttu-id="bada2-293">Produit</span><span class="sxs-lookup"><span data-stu-id="bada2-293">Product</span></span> | `ConfigId` |
| <span data-ttu-id="bada2-294">Suivi</span><span class="sxs-lookup"><span data-stu-id="bada2-294">Tracking</span></span> | `BatchId` |
| <span data-ttu-id="bada2-295">Suivi</span><span class="sxs-lookup"><span data-stu-id="bada2-295">Tracking</span></span> | `SerialId` |
| <span data-ttu-id="bada2-296">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="bada2-296">Location</span></span> | `LocationId` |
| <span data-ttu-id="bada2-297">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="bada2-297">Location</span></span> | `SiteId` |
| <span data-ttu-id="bada2-298">Statut du stock</span><span class="sxs-lookup"><span data-stu-id="bada2-298">Inventory Status</span></span> | `StatusId` |
| <span data-ttu-id="bada2-299">Spécifique à l’entrepôt</span><span class="sxs-lookup"><span data-stu-id="bada2-299">Warehouse Specific</span></span> | `WMSLocationId` |
| <span data-ttu-id="bada2-300">Spécifique à l’entrepôt</span><span class="sxs-lookup"><span data-stu-id="bada2-300">Warehouse Specific</span></span> | `WMSPalletId` |
| <span data-ttu-id="bada2-301">Spécifique à l’entrepôt</span><span class="sxs-lookup"><span data-stu-id="bada2-301">Warehouse Specific</span></span> | `LicensePlateId` |

> [!NOTE]
> <span data-ttu-id="bada2-302">Le type de dimension répertorié dans le tableau précédent est à titre indicatif uniquement.</span><span class="sxs-lookup"><span data-stu-id="bada2-302">The dimension type listed in the previous table is for reference only.</span></span> <span data-ttu-id="bada2-303">Vous n’avez pas besoin de définir le type de dimension dans la visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="bada2-303">You don't need to define the dimension type in Inventory Visibility.</span></span>

<span data-ttu-id="bada2-304">Si une dimension personnalisée existe et doit passer à une valeur par défaut lorsqu’elle est utilisée par la visibilité du stock, vous pouvez configurer le nom **Dimension personnalisée** dans la visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="bada2-304">If a custom dimension exists and needs to flow to a default value when consumed by Inventory Visibility, you can configure the **Custom dimension** name in Inventory Visibility.</span></span>

<span data-ttu-id="bada2-305">Les systèmes externes accèdent à la visibilité du stock via des API RESTful qui permettent d’interroger des informations disponibles sur des ensembles de dimensions donnés.</span><span class="sxs-lookup"><span data-stu-id="bada2-305">External systems access Inventory Visibility through RESTful APIs that enable on-hand information on given sets of dimensions to be queried.</span></span> <span data-ttu-id="bada2-306">Pour l’intégration, la visibilité du stock vous permet de configurer la *source de données de canal externe* et la dimension source des *dimensions cibles* dans la visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="bada2-306">For the integration, Inventory Visibility enables you to configure the *external channel data source* and the source dimension to the *target dimensions* in Inventory Visibility.</span></span>

<span data-ttu-id="bada2-307">Les dimensions cibles doivent être l’une des suivantes :</span><span class="sxs-lookup"><span data-stu-id="bada2-307">The target dimensions should be one of the following:</span></span>

- <span data-ttu-id="bada2-308">Dimensions par défaut dans la visibilité du stock</span><span class="sxs-lookup"><span data-stu-id="bada2-308">Default dimensions in Inventory Visibility</span></span>
- <span data-ttu-id="bada2-309">Dimensions personnalisées</span><span class="sxs-lookup"><span data-stu-id="bada2-309">Custom dimensions</span></span>

<span data-ttu-id="bada2-310">Le but de la configuration des dimensions est de standardiser l’intégration multi-système pour la requête sur les dimensions et l’événement de publication avec les dimensions.</span><span class="sxs-lookup"><span data-stu-id="bada2-310">The purpose of dimension configuration is to standardize the multi-system integration for the query on dimensions and the posting event with dimensions.</span></span>

#### <a name="indexing"></a><span data-ttu-id="bada2-311">Indexation</span><span class="sxs-lookup"><span data-stu-id="bada2-311">Indexing</span></span>

<span data-ttu-id="bada2-312">La plupart du temps, la requête de stock disponible sera non seulement au niveau "total" le plus élevé, mais vous souhaiterez peut-être voir les résultats agrégés en fonction des dimensions de stock.</span><span class="sxs-lookup"><span data-stu-id="bada2-312">Most of the time, the inventory on-hand query will not only be on the highest "total" level, but you may want to see results aggregated based on the inventory dimensions.</span></span>

<span data-ttu-id="bada2-313">La visibilité du stock offre une certaine flexibilité en vous permettant de configurer les index, qui sont basés sur la dimension ou la combinaison des dimensions.</span><span class="sxs-lookup"><span data-stu-id="bada2-313">Inventory Visibility provides flexibility by allowing you to set up the indexes, which are based on the dimension or the combination of the dimensions.</span></span>

> [!NOTE]
> <span data-ttu-id="bada2-314">Actuellement, vous ne pouvez configurer les index que jusqu’à un maximum de cinq.</span><span class="sxs-lookup"><span data-stu-id="bada2-314">Currently, you can only configure indexes to a maximum of five.</span></span> <span data-ttu-id="bada2-315">Vous devez examiner attentivement la dimension ou la combinaison de dimensions que vous utiliserez avant la mise en œuvre pour vous assurer qu’elle répondra aux besoins de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="bada2-315">You need to carefully consider which dimension or dimension combination you will use before the implementation to ensure that it will meet your business needs.</span></span> <span data-ttu-id="bada2-316">Par exemple, si vous souhaitez interroger les produits comme suit :</span><span class="sxs-lookup"><span data-stu-id="bada2-316">For example, if you want to query products as follows:</span></span>

- <span data-ttu-id="bada2-317">Recherchez le produit agrégé disponible par les dimensions *Couleur* et *Taille*.</span><span class="sxs-lookup"><span data-stu-id="bada2-317">Query the aggregated product on-hand by the *Color* and *Size* dimensions.</span></span>
- <span data-ttu-id="bada2-318">Dans certains cas, vous souhaitez simplement interroger le produit au total.</span><span class="sxs-lookup"><span data-stu-id="bada2-318">In some cases, you just want to query on the product in total.</span></span>

<span data-ttu-id="bada2-319">Vous auriez deux index définis comme suit :</span><span class="sxs-lookup"><span data-stu-id="bada2-319">You would have two indexes defined as the following:</span></span>

- `["ColorId", "SizeId"]`
- `[]`

<span data-ttu-id="bada2-320">Le crochet vide sera agrégé en fonction de l’ID de produit dans la partition.</span><span class="sxs-lookup"><span data-stu-id="bada2-320">The empty bracket will aggregate based on the product ID within the partition.</span></span>

<span data-ttu-id="bada2-321">L’indexation définit comment vous pouvez regrouper vos résultats en fonction du paramètre de requête `groupBy`.</span><span class="sxs-lookup"><span data-stu-id="bada2-321">The indexing defines how you can group your results based on the `groupBy` query setting.</span></span> <span data-ttu-id="bada2-322">Dans ce cas, si vous ne définissez aucune valeur `groupBy`, vous obtiendrez les totaux par `productid`.</span><span class="sxs-lookup"><span data-stu-id="bada2-322">In this case if you don't define any `groupBy` values, you'll get totals by `productid`.</span></span> <span data-ttu-id="bada2-323">Sinon, si vous définissez `groupBy` comme `groupBy=ColorId&groupBy=SizeId`, vous obtiendrez plusieurs lignes renvoyées, en fonction des différentes combinaisons de couleurs et de tailles du système.</span><span class="sxs-lookup"><span data-stu-id="bada2-323">Otherwise, if you define `groupBy` as `groupBy=ColorId&groupBy=SizeId`, you'll get multiple lines returned, based on the different color and size combinations in the system.</span></span>

<span data-ttu-id="bada2-324">Vous pouvez mettre vos critères de requête dans le corps de la requête.</span><span class="sxs-lookup"><span data-stu-id="bada2-324">You can put your query criteria in the request body.</span></span>

<span data-ttu-id="bada2-325">Voici un exemple de requête sur le produit avec une combinaison de couleur et de taille.</span><span class="sxs-lookup"><span data-stu-id="bada2-325">Here is a sample query on the product with color and size combination.</span></span>

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

#### <a name="custom-measurement"></a><span data-ttu-id="bada2-326">Mesure personnalisée</span><span class="sxs-lookup"><span data-stu-id="bada2-326">Custom measurement</span></span>

<span data-ttu-id="bada2-327">Les quantités de mesure par défaut sont liées à Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="bada2-327">The default measurement quantities are linked to Supply Chain Management.</span></span> <span data-ttu-id="bada2-328">Cependant, vous souhaiterez peut-être avoir une quantité composée d’une combinaison des mesures par défaut.</span><span class="sxs-lookup"><span data-stu-id="bada2-328">However, you may want to have a quantity that is made up of a combination of the default measurements.</span></span> <span data-ttu-id="bada2-329">Pour ce faire, vous pouvez avoir une configuration de quantités personnalisées, qui seront ajoutées à la sortie des requêtes en main.</span><span class="sxs-lookup"><span data-stu-id="bada2-329">To do this, you can have a configuration of custom quantities, which will be added to the output of the on-hand queries.</span></span>

<span data-ttu-id="bada2-330">La fonctionnalité vous permet simplement de définir un ensemble de mesures qui seront ajoutées, et/ou un ensemble de mesures qui seront soustraites, afin de la mesure personnalisée.</span><span class="sxs-lookup"><span data-stu-id="bada2-330">The functionality simply allows you to define a set of measures that will be added, and/or a set of measures that will be subtracted, in order to form the custom measurement.</span></span>

<span data-ttu-id="bada2-331">Par exemple, avec la condition de requête suivante, vous configurerez la quantité de mesure personnalisée comme `MyCustomAvailableforReservation` à consommer par le système de consommation.</span><span class="sxs-lookup"><span data-stu-id="bada2-331">For example, with the following query condition, you will configure the custom measurement quantity as `MyCustomAvailableforReservation` to be consumed by the consumption system.</span></span>

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



| <span data-ttu-id="bada2-332">Système de consommation</span><span class="sxs-lookup"><span data-stu-id="bada2-332">Consumption system</span></span> | <span data-ttu-id="bada2-333">Mesures calculées</span><span class="sxs-lookup"><span data-stu-id="bada2-333">Calculated measurers</span></span> | <span data-ttu-id="bada2-334">Source de données</span><span class="sxs-lookup"><span data-stu-id="bada2-334">Data source</span></span> | <span data-ttu-id="bada2-335">Modificateur</span><span class="sxs-lookup"><span data-stu-id="bada2-335">Modifier</span></span> | <span data-ttu-id="bada2-336">Type de calcul du modificateur</span><span class="sxs-lookup"><span data-stu-id="bada2-336">Modifier calculation type</span></span> |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | <span data-ttu-id="bada2-337">Addition</span><span class="sxs-lookup"><span data-stu-id="bada2-337">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | <span data-ttu-id="bada2-338">Addition</span><span class="sxs-lookup"><span data-stu-id="bada2-338">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | <span data-ttu-id="bada2-339">Soustraction</span><span class="sxs-lookup"><span data-stu-id="bada2-339">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | <span data-ttu-id="bada2-340">Addition</span><span class="sxs-lookup"><span data-stu-id="bada2-340">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | <span data-ttu-id="bada2-341">Soustraction</span><span class="sxs-lookup"><span data-stu-id="bada2-341">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | <span data-ttu-id="bada2-342">Addition</span><span class="sxs-lookup"><span data-stu-id="bada2-342">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | <span data-ttu-id="bada2-343">Addition</span><span class="sxs-lookup"><span data-stu-id="bada2-343">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | <span data-ttu-id="bada2-344">Soustraction</span><span class="sxs-lookup"><span data-stu-id="bada2-344">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | <span data-ttu-id="bada2-345">Soustraction</span><span class="sxs-lookup"><span data-stu-id="bada2-345">Subtraction</span></span> |

<span data-ttu-id="bada2-346">Avec cela, la requête sur la quantité de mesure personnalisée renverra la sortie suivante.</span><span class="sxs-lookup"><span data-stu-id="bada2-346">With that, the query on the custom measurement quantity will return the following output.</span></span>

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

<span data-ttu-id="bada2-347">La sortie `MyCustomAvailableforReservation` est basée sur le paramètre de calcul dans les mesures personnalisées comme :</span><span class="sxs-lookup"><span data-stu-id="bada2-347">The `MyCustomAvailableforReservation` output is based on the calculation setting in the custom measurements as:</span></span>  
 <span data-ttu-id="bada2-348">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span><span class="sxs-lookup"><span data-stu-id="bada2-348">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span></span>

### <a name="posting-on-hand-changes"></a><span data-ttu-id="bada2-349">Publication des modifications en stock</span><span class="sxs-lookup"><span data-stu-id="bada2-349">Posting on-hand changes</span></span>

<span data-ttu-id="bada2-350">L’URL exacte sur laquelle l’événement sera publié dépendra de votre région géographique.</span><span class="sxs-lookup"><span data-stu-id="bada2-350">The exact URL that the event will be posted to will depend on your geographical region.</span></span> <span data-ttu-id="bada2-351">Il prendra la forme :</span><span class="sxs-lookup"><span data-stu-id="bada2-351">It will take the form:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand`

<span data-ttu-id="bada2-352">Une fois authentifiée, cette URL peut être utilisée avec la méthode HTTP `POST` pour envoyer des événements de modification en main au service.</span><span class="sxs-lookup"><span data-stu-id="bada2-352">When authenticated, this URL can be used along with the HTTP `POST` method to send on-hand change events to the service.</span></span>

<span data-ttu-id="bada2-353">Un en-tête spécial est utilisé pour communiquer avec les services Dynamics 365 via des requêtes HTTP, indiquant l’ID d’environnement de l’instance Supply Chain Management à laquelle les données sont liées.</span><span class="sxs-lookup"><span data-stu-id="bada2-353">A special header is used for communicating with Dynamics 365 services through HTTP requests, denoting the environment ID of the Supply Chain Management instance the data is linked to.</span></span> <span data-ttu-id="bada2-354">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="bada2-354">For example:</span></span>

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a><span data-ttu-id="bada2-355">Exemple de requête de publication de modifications en main 1</span><span class="sxs-lookup"><span data-stu-id="bada2-355">Posting on-hand changes query example 1</span></span>

<span data-ttu-id="bada2-356">Cet exemple montre un scénario dans lequel vous allez configurer la configuration de dimension dans Power Apps.</span><span class="sxs-lookup"><span data-stu-id="bada2-356">This example shows a scenario where you will set up the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="bada2-357">Utilisez la requête suivante pour configurer le mappage de dimension dans Power Apps :</span><span class="sxs-lookup"><span data-stu-id="bada2-357">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="bada2-358">Vous pouvez maintenant spécifier la `dimensionDataSource` et utilisez des dimensions personnalisées dans vos requêtes.</span><span class="sxs-lookup"><span data-stu-id="bada2-358">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="bada2-359">Le système convertira automatiquement les dimensions personnalisées en dimensions de base.</span><span class="sxs-lookup"><span data-stu-id="bada2-359">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="posting-on-hand-changes-query-example-2"></a><span data-ttu-id="bada2-360">Exemple de requête de publication de modifications en main 2</span><span class="sxs-lookup"><span data-stu-id="bada2-360">Posting on-hand changes query example 2</span></span>

<span data-ttu-id="bada2-361">Cet exemple montre un scénario dans lequel aucun mappage n’est configuré pour la configuration de dimension dans Power Apps, donc la publication doit également utiliser les dimensions de base.</span><span class="sxs-lookup"><span data-stu-id="bada2-361">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="bada2-362">Toutes les dimensions doivent être des dimensions de base lorsque le champ `dimensionDataSource` est nul, vide ou espace.</span><span class="sxs-lookup"><span data-stu-id="bada2-362">All dimensions must be base dimensions when the `dimensionDataSource` field is null, empty, or whitespace.</span></span>

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

#### <a name="json-document-field-properties"></a><span data-ttu-id="bada2-363">Propriétés du champs de documents JSON</span><span class="sxs-lookup"><span data-stu-id="bada2-363">JSON document field properties</span></span>

<span data-ttu-id="bada2-364">Les champs des exemples de requête JSON fournis précédemment ont les propriétés répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="bada2-364">The fields from the JSON query examples provided previously have the properties listed in the following table.</span></span>

| <span data-ttu-id="bada2-365">ID champ</span><span class="sxs-lookup"><span data-stu-id="bada2-365">Field ID</span></span> | <span data-ttu-id="bada2-366">Description</span><span class="sxs-lookup"><span data-stu-id="bada2-366">Description</span></span> |
|---|---|
| `id` | <span data-ttu-id="bada2-367">Un ID unique pour l’événement de modification spécifique.</span><span class="sxs-lookup"><span data-stu-id="bada2-367">A unique ID for the specific change event.</span></span> <span data-ttu-id="bada2-368">Cet ID est utilisé pour garantir qu’en cas d’échec de la communication avec le service pendant la comptabilisation, la soumission à nouveau de l’événement n’entraînerait pas le comptage du même événement deux fois dans le système.</span><span class="sxs-lookup"><span data-stu-id="bada2-368">This ID is used to ensure that if communication with the service fails during posting, resubmitting the event would not result in the same event being counted twice in the system.</span></span> |
| `organizationId` | <span data-ttu-id="bada2-369">L’identificateur de l’organisation liée à l’événement.</span><span class="sxs-lookup"><span data-stu-id="bada2-369">The identifier of the organization linked to the event.</span></span> <span data-ttu-id="bada2-370">Cela correspond aux organisations de gestion de Supply Chain Management ou aux ID de zone de données.</span><span class="sxs-lookup"><span data-stu-id="bada2-370">This maps to Supply Chain Management organizations or data area IDs.</span></span> |
| `productId` | <span data-ttu-id="bada2-371">Identificateur du produit en question.</span><span class="sxs-lookup"><span data-stu-id="bada2-371">The identifier of the product in question.</span></span> |
| `quantity` | <span data-ttu-id="bada2-372">La quantité dont le stock doit être changé.</span><span class="sxs-lookup"><span data-stu-id="bada2-372">The quantity by which the on-hand needs to be changed.</span></span> <span data-ttu-id="bada2-373">Si, par exemple, 10 nouveaux bagels étaient ajoutés à une étagère, cette valeur serait de 10.</span><span class="sxs-lookup"><span data-stu-id="bada2-373">If, for instance, 10 new bagels were added to a shelf, this value would be 10.</span></span> <span data-ttu-id="bada2-374">Si 3 bagels étaient ensuite retirés de l’étagère ou vendus, cette valeur serait de -3.</span><span class="sxs-lookup"><span data-stu-id="bada2-374">If 3 bagels were then removed from the shelf or sold, this value would be -3.</span></span> |
| `dimensionDataSource` | <span data-ttu-id="bada2-375">Source de données des dimensions utilisées dans l’événement et la requête de modification de publication.</span><span class="sxs-lookup"><span data-stu-id="bada2-375">The data source of the dimensions used in the posting change event and query.</span></span> <span data-ttu-id="bada2-376">Si vous spécifiez la source de données, vous pouvez utiliser les dimensions personnalisées de la source de données spécifiée.</span><span class="sxs-lookup"><span data-stu-id="bada2-376">If you specify the data source, you can use the custom dimensions from the specified data source.</span></span> <span data-ttu-id="bada2-377">Avec la configuration des dimensions, la visibilité du stock peut mapper les dimensions personnalisées aux dimensions générales par défaut.</span><span class="sxs-lookup"><span data-stu-id="bada2-377">With the dimension configuration, Inventory Visibility can map the custom dimensions to the general default dimensions.</span></span> <span data-ttu-id="bada2-378">Si la `dimensionDataSource` n’est pas spécifié, vous ne pouvez utiliser que les dimensions générales par défaut dans vos requêtes.</span><span class="sxs-lookup"><span data-stu-id="bada2-378">If the `dimensionDataSource` is not specified, you can only use the general default dimensions in your queries.</span></span>   |
| `dimensions` | <span data-ttu-id="bada2-379">Un sac dynamique de paires clé/valeur.</span><span class="sxs-lookup"><span data-stu-id="bada2-379">A dynamic bag of key/value pairs.</span></span> <span data-ttu-id="bada2-380">Celles-ci correspondront à certaines des dimensions de Supply Chain Management, mais vous pouvez également ajouter des dimensions personnalisées (comme *Source*) qui peut indiquer si l’événement provenait de Supply Chain Management ou d’un système externe.</span><span class="sxs-lookup"><span data-stu-id="bada2-380">These will map to some of the dimensions in Supply Chain Management, but you could also add custom dimensions (like *Source*) that may denote if the event was coming from Supply Chain Management or an external system.</span></span> |

### <a name="querying-current-on-hand"></a><span data-ttu-id="bada2-381">Interrogation actuellement disponible</span><span class="sxs-lookup"><span data-stu-id="bada2-381">Querying current on-hand</span></span>

<span data-ttu-id="bada2-382">Le point de terminaison pour interroger le stock actuel aura une URL similaire :</span><span class="sxs-lookup"><span data-stu-id="bada2-382">The endpoint for querying the current on-hand will have a similar URL:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

<span data-ttu-id="bada2-383">Il sera interrogé avec la méthode HTTP `POST`.</span><span class="sxs-lookup"><span data-stu-id="bada2-383">It will be queried with the HTTP `POST` method.</span></span>

#### <a name="current-on-hand-query-example-1"></a><span data-ttu-id="bada2-384">Exemple de requête en main actuel 1</span><span class="sxs-lookup"><span data-stu-id="bada2-384">Current on-hand query example 1</span></span>

<span data-ttu-id="bada2-385">Cet exemple montre un scénario dans lequel vous disposez déjà d’une configuration de dimension terminée dans Power Apps.</span><span class="sxs-lookup"><span data-stu-id="bada2-385">This example shows a scenario where you have already completed the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="bada2-386">Utilisez la requête suivante pour configurer le mappage de dimension dans Power Apps :</span><span class="sxs-lookup"><span data-stu-id="bada2-386">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="bada2-387">Vous pouvez maintenant spécifier la `dimensionDataSource` et utilisez des dimensions personnalisées dans vos requêtes.</span><span class="sxs-lookup"><span data-stu-id="bada2-387">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="bada2-388">Le système convertira automatiquement les dimensions personnalisées en dimensions de base.</span><span class="sxs-lookup"><span data-stu-id="bada2-388">The system will automatically convert custom dimensions to base dimensions.</span></span> <span data-ttu-id="bada2-389">Vous pouvez spécifier la `DimensionDataSource` dans `filters` et spécifiez des dimensions personnalisées dans `filters` et `groupByValues`.</span><span class="sxs-lookup"><span data-stu-id="bada2-389">You can specify the `DimensionDataSource` in `filters` and specify custom dimensions in both `filters` and `groupByValues`.</span></span> <span data-ttu-id="bada2-390">Le système convertira automatiquement les dimensions personnalisées en dimensions de base.</span><span class="sxs-lookup"><span data-stu-id="bada2-390">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="current-on-hand-query-example-2"></a><span data-ttu-id="bada2-391">Exemple de requête en main actuel 2</span><span class="sxs-lookup"><span data-stu-id="bada2-391">Current on-hand query example 2</span></span>

<span data-ttu-id="bada2-392">Cet exemple montre un scénario dans lequel aucun mappage n’est configuré pour la configuration de dimension dans Power Apps, donc la publication doit également utiliser les dimensions de base.</span><span class="sxs-lookup"><span data-stu-id="bada2-392">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="bada2-393">Toutes les dimensions doivent être des dimensions de base lorsque le champ `dimensionDataSource`, sous `filters`, est nul, vide ou espace.</span><span class="sxs-lookup"><span data-stu-id="bada2-393">All dimensions must be base dimensions when the `dimensionDataSource` field, under `filters` is null, empty, or whitespace.</span></span>

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

#### <a name="example-return-result"></a><span data-ttu-id="bada2-394">Exemple de résultat de retour</span><span class="sxs-lookup"><span data-stu-id="bada2-394">Example return result</span></span>

<span data-ttu-id="bada2-395">Les requêtes présentées dans les exemples précédents peuvent renvoyer un résultat comme celui-ci.</span><span class="sxs-lookup"><span data-stu-id="bada2-395">The queries shown in the previous examples could return a result like this.</span></span>

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

<span data-ttu-id="bada2-396">Notez que les champs de quantités sont structurés comme un dictionnaire de mesures et de leurs valeurs associées.</span><span class="sxs-lookup"><span data-stu-id="bada2-396">Note that the quantities fields are structured as a dictionary of measures and their associated values.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
