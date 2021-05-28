---
title: Complément de visibilité de stock
description: Cette rubrique décrit comment installer et configurer le complément de visibilité de stock pour Dynamics 365 Supply Chain Management.
author: sherry-zheng
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 84f5e949f0c81f840c8a9086d05bbcfc576e42aa
ms.sourcegitcommit: b67665ed689c55df1a67d1a7840947c3977d600c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6017004"
---
# <a name="inventory-visibility-add-in"></a><span data-ttu-id="613e3-103">Complément de visibilité de stock</span><span class="sxs-lookup"><span data-stu-id="613e3-103">Inventory Visibility Add-in</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

<span data-ttu-id="613e3-104">Le complément de visibilité de stock est un microservice indépendant et hautement évolutif qui permet un suivi des stocks en temps réel, offrant ainsi une vue globale de la visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="613e3-104">The Inventory Visibility Add-in is an independent and highly scalable microservice that enables real-time on-hand inventory tracking, thus providing a global view of inventory visibility.</span></span>

<span data-ttu-id="613e3-105">Toutes les informations relatives à l’inventaire disponible sont exportées vers le service en temps quasi réel via une intégration SQL de bas niveau.</span><span class="sxs-lookup"><span data-stu-id="613e3-105">All information that relates to on-hand inventory is exported to the service in near real-time through low-level SQL integration.</span></span> <span data-ttu-id="613e3-106">Les systèmes externes accèdent au service via des API RESTful pour interroger les informations disponibles sur des ensembles de dimensions donnés, récupérant ainsi une liste des positions disponibles.</span><span class="sxs-lookup"><span data-stu-id="613e3-106">External systems access the service through RESTful APIs to query on-hand information on given sets of dimensions, thus retrieving a list of available on-hand positions.</span></span>

<span data-ttu-id="613e3-107">La visibilité du stock est un microservice basé sur Microsoft Dataverse, ce qui signifie que vous pouvez l’étendre en créant des Power Apps et en appliquant Power BI pour fournir des fonctionnalités personnalisées pour répondre aux besoins de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="613e3-107">Inventory Visibility is a microservice built on Microsoft Dataverse, which means you can extend it by building Power Apps and applying Power BI to provide customized functionality to meet your business requirements.</span></span> <span data-ttu-id="613e3-108">Il est également possible de mettre à niveau l’index pour effectuer des requêtes d’inventaire.</span><span class="sxs-lookup"><span data-stu-id="613e3-108">It is also possible to upgrade the index to do inventory queries.</span></span>

<span data-ttu-id="613e3-109">La visibilité du stock fournit des options de configuration qui lui permettent de s’intégrer à plusieurs systèmes tiers.</span><span class="sxs-lookup"><span data-stu-id="613e3-109">Inventory Visibility provides configuration options that let it integrate with multiple third-party systems.</span></span> <span data-ttu-id="613e3-110">Il prend en charge la dimension de stock normalisée, l’extensibilité personnalisée et les quantités calculées normalisées et configurables.</span><span class="sxs-lookup"><span data-stu-id="613e3-110">It supports the standardized inventory dimension, customized extensibility, and standardized, configurable calculated quantities.</span></span>

<span data-ttu-id="613e3-111">Cette rubrique décrit comment installer et configurer le complément de visibilité de stock pour Dynamics 365 Supply Chain Management, et comment utiliser son interface de programmation d’application (API).</span><span class="sxs-lookup"><span data-stu-id="613e3-111">This topic describes how to install and configure the Inventory Visibility Add-in for Dynamics 365 Supply Chain Management, and how to use its application programming interface (API).</span></span>

## <a name="install-the-inventory-visibility-add-in"></a><span data-ttu-id="613e3-112">Installer le complément de visibilité de stock</span><span class="sxs-lookup"><span data-stu-id="613e3-112">Install the Inventory Visibility Add-in</span></span>

<span data-ttu-id="613e3-113">Vous devez installer le complément de visibilité de stock à l’aide de Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="613e3-113">You need to install the Inventory Visibility Add-in using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="613e3-114">LCS est un portail de collaboration qui fournit un environnement et un ensemble de services régulièrement mis à jour qui vous aident à gérer le cycle de vie des applications de vos applications Dynamics 365 Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="613e3-114">LCS is a collaboration portal that provides an environment and a set of regularly updated services that help you manage the application lifecycle of your Dynamics 365 Finance and Operations apps.</span></span>

<span data-ttu-id="613e3-115">Pour plus d’informations, voir [Ressources Lifecycle Services](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).</span><span class="sxs-lookup"><span data-stu-id="613e3-115">For more information, see [Lifecycle Services resources](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).</span></span>

### <a name="inventory-visibility-add-in-prerequisites"></a><span data-ttu-id="613e3-116">Conditions préalables pour le complément de visibilité de stock</span><span class="sxs-lookup"><span data-stu-id="613e3-116">Inventory Visibility Add-in prerequisites</span></span>

<span data-ttu-id="613e3-117">Avant de pouvoir installer le complément Visibilité du stock, vous devez procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="613e3-117">Before you install the Inventory Visibility Add-in, you must do the following:</span></span>

- <span data-ttu-id="613e3-118">Obtenez un projet d’implémentation LCS avec au moins un environnement déployé.</span><span class="sxs-lookup"><span data-stu-id="613e3-118">Obtain an LCS implementation project with at least one environment deployed.</span></span>
- <span data-ttu-id="613e3-119">Assurez-vous que les conditions préalables à la configuration des compléments fournies dans la [Présentation des compléments](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) ont été remplies.</span><span class="sxs-lookup"><span data-stu-id="613e3-119">Make sure that the prerequisites for setting up add-ins provided in the [Add-ins overview](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) have been completed.</span></span> <span data-ttu-id="613e3-120">La visibilité de l’inventaire ne nécessite pas de liaison en double écriture.</span><span class="sxs-lookup"><span data-stu-id="613e3-120">Inventory Visibility doesn't require dual-write linking.</span></span>
- <span data-ttu-id="613e3-121">Contactez l’équipe de visibilité de l’inventaire à [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) pour obtenir les trois fichiers requis suivants :</span><span class="sxs-lookup"><span data-stu-id="613e3-121">Contact the Inventory Visibility Team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the following three required files:</span></span>
  - `Inventory Visibility Dataverse Solution.zip`
  - `Inventory Visibility Configuration Trigger.zip`
  - <span data-ttu-id="613e3-122">`Inventory Visibility Integration.zip` (si la version de Supply Chain Management que vous exécutez est antérieure à la version 10.0.18)</span><span class="sxs-lookup"><span data-stu-id="613e3-122">`Inventory Visibility Integration.zip` (if the version of Supply Chain Management that you're running is earlier than version 10.0.18)</span></span>
- <span data-ttu-id="613e3-123">Vous pouvez également contacter l’équipe de visibilité de l’inventaire à [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) pour obtenir les packages de Package Deployer.</span><span class="sxs-lookup"><span data-stu-id="613e3-123">Alternatively, contact the Inventory Visibility Team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the package deployer packages.</span></span> <span data-ttu-id="613e3-124">Ces packages peuvent être utilisés par un outil Package Deployer officiel.</span><span class="sxs-lookup"><span data-stu-id="613e3-124">These packages can be used by an official package deployer tool.</span></span>
  - `InventoryServiceBase.PackageDeployer.zip`
  - <span data-ttu-id="613e3-125">`InventoryServiceApplication.PackageDeployer.zip` (ce package contient toutes les modifications apportées au package `InventoryServiceBase`, ainsi que des composants d'application d'interface utilisateur supplémentaires)</span><span class="sxs-lookup"><span data-stu-id="613e3-125">`InventoryServiceApplication.PackageDeployer.zip` (this package contains all of the changes in the `InventoryServiceBase` package, plus additional UI application components)</span></span>
- <span data-ttu-id="613e3-126">Suivez les instructions données dans [Démarrage rapide : enregistrer une application avec la plateforme d'identité Microsoft](/azure/active-directory/develop/quickstart-register-app) pour inscrire une application et ajouter un secret client à AAD dans le cadre de votre abonnement Azure.</span><span class="sxs-lookup"><span data-stu-id="613e3-126">Follow the instructions given in [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app) to register an application and add a client secret to AAD under your azure subscription.</span></span>
  - [<span data-ttu-id="613e3-127">Inscrire une application</span><span class="sxs-lookup"><span data-stu-id="613e3-127">Register an application</span></span>](/azure/active-directory/develop/quickstart-register-app)
  - [<span data-ttu-id="613e3-128">Ajouter un secret client</span><span class="sxs-lookup"><span data-stu-id="613e3-128">Add a client secret</span></span>](/azure/active-directory/develop/quickstart-register-app#add-a-certificate)
  - <span data-ttu-id="613e3-129">Les valeurs **Identifiant de l'application (client)**, **Secret client** et **ID du locataire** seront utilisées dans les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="613e3-129">The **Application(Client) Id**, **Client Secret**, and **Tenant ID** will be used in the following steps.</span></span>

> [!NOTE]
> <span data-ttu-id="613e3-130">Les régions actuellement pris en charge comprennent le Canada, les États-Unis et l’Union européenne (UE).</span><span class="sxs-lookup"><span data-stu-id="613e3-130">The currently supported countries and regions include Canada, the United States, and the European Union (EU).</span></span>

<span data-ttu-id="613e3-131">Si vous avez des questions sur ces conditions préalables, contactez l’équipe produit de visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="613e3-131">If you have any questions about these prerequisites, please contact the Inventory Visibility product team.</span></span>

### <a name="set-up-dataverse"></a><a name="setup-microsoft-dataverse"></a><span data-ttu-id="613e3-132">Paramétrer Dataverse</span><span class="sxs-lookup"><span data-stu-id="613e3-132">Set up Dataverse</span></span>

<span data-ttu-id="613e3-133">Pour configurer Dataverse pour une utilisation avec la visibilité du stock, vous devez d'abord préparer les prérequis, puis décider si vous souhaitez configurer Dataverse à l'aide de l'outil Package Deployer ou en important manuellement les solutions (vous n'avez pas à faire les deux).</span><span class="sxs-lookup"><span data-stu-id="613e3-133">To set up Dataverse for use with Inventory Visibility, you must first prepare the prerequisites and then decide whether to set up Dataverse using either the package deployer tool or by manually importing the solutions (you don't have to do both).</span></span> <span data-ttu-id="613e3-134">Ensuite installez le complément de visibilité de stock.</span><span class="sxs-lookup"><span data-stu-id="613e3-134">Then install the Inventory Visibility Add-in.</span></span> <span data-ttu-id="613e3-135">Les sous-sections suivantes décrivent comment effectuer chacune de ces tâches.</span><span class="sxs-lookup"><span data-stu-id="613e3-135">The following subsections describe how to complete each of these tasks.</span></span>

#### <a name="prepare-dataverse-prerequisites"></a><span data-ttu-id="613e3-136">Préparer les conditions préalables Dataverse</span><span class="sxs-lookup"><span data-stu-id="613e3-136">Prepare Dataverse prerequisites</span></span>

<span data-ttu-id="613e3-137">Avant de commencer la configuration de Dataverse, ajoutez un principe de service à votre locataire en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="613e3-137">Before you start to set up Dataverse, add a service principle to your tenant by doing the following:</span></span>

1. <span data-ttu-id="613e3-138">Installer Azure AD PowerShell Module v2 comme décrit dans [Installer Azure Active Directory PowerShell pour Graph](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="613e3-138">Install Azure AD PowerShell Module v2 as described in [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>

1. <span data-ttu-id="613e3-139">Exécutez la commande suivante PowerShell :</span><span class="sxs-lookup"><span data-stu-id="613e3-139">Run the following PowerShell command:</span></span>

    ```powershell
    Connect-AzureAD # (open a sign in window and sign in as a tenant user)
    
    New-AzureADServicePrincipal -AppId "3022308a-b9bd-4a18-b8ac-2ddedb2075e1" -DisplayName "d365-scm-inventoryservice"
    ```

#### <a name="set-up-dataverse-using-the-package-deployer-tool"></a><span data-ttu-id="613e3-140">Configurer Dataverse à l'aide de l'outil Package Deployer</span><span class="sxs-lookup"><span data-stu-id="613e3-140">Set up Dataverse using the package deployer tool</span></span>

<span data-ttu-id="613e3-141">Une fois les conditions préalables en place, utilisez la procédure suivante si vous préférez configurer Dataverse à l'aide de l'outil Package Deployer.</span><span class="sxs-lookup"><span data-stu-id="613e3-141">After you have the prerequisites in place, use the following procedure if you prefer to set up Dataverse using the package deployer tool.</span></span> <span data-ttu-id="613e3-142">Consultez la section suivante pour plus de détails sur la façon d'importer les solutions manuellement (ne faites pas les deux).</span><span class="sxs-lookup"><span data-stu-id="613e3-142">See the next section for details about how to import the solutions manually instead (don't do both).</span></span>

1. <span data-ttu-id="613e3-143">Installez les outils de développement comme décrit dans [Télécharger les outils depuis NuGet](/dynamics365/customerengagement/on-premises/developer/download-tools-nuget).</span><span class="sxs-lookup"><span data-stu-id="613e3-143">Install developer tools as described in [Download tools from NuGet](/dynamics365/customerengagement/on-premises/developer/download-tools-nuget).</span></span>

1. <span data-ttu-id="613e3-144">En fonction des besoins de votre entreprise, choisissez le package `InventoryServiceBase` ou `InventoryServiceApplication`.</span><span class="sxs-lookup"><span data-stu-id="613e3-144">Based on your business requirements, choose the `InventoryServiceBase` or `InventoryServiceApplication` package.</span></span>

1. <span data-ttu-id="613e3-145">Importer les solutions :</span><span class="sxs-lookup"><span data-stu-id="613e3-145">Import the solutions:</span></span>
    1. <span data-ttu-id="613e3-146">Pour le package `InventoryServiceBase` :</span><span class="sxs-lookup"><span data-stu-id="613e3-146">For the `InventoryServiceBase` package:</span></span>
        - <span data-ttu-id="613e3-147">Décompressez `InventoryServiceBase.PackageDeployer.zip`</span><span class="sxs-lookup"><span data-stu-id="613e3-147">Unzip `InventoryServiceBase.PackageDeployer.zip`</span></span>
        - <span data-ttu-id="613e3-148">Recherchez le dossier `InventoryServiceBase`, le fichier `[Content_Types].xml`, le fichier `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll`, le fichier `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config` et le fichier `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config`.</span><span class="sxs-lookup"><span data-stu-id="613e3-148">Find folder `InventoryServiceBase`, file `[Content_Types].xml`, file `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll`, file `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config`, and file `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config`.</span></span> 
        - <span data-ttu-id="613e3-149">Copiez chacun de ces dossiers et fichiers dans le répertoire `.\Tools\PackageDeployment`, qui a été créé lorsque vous avez installé les outils de développement.</span><span class="sxs-lookup"><span data-stu-id="613e3-149">Copy each of these folders and files to the `.\Tools\PackageDeployment` directory, which was created when you installed the developer tools.</span></span>
    1. <span data-ttu-id="613e3-150">Pour le package `InventoryServiceApplication` :</span><span class="sxs-lookup"><span data-stu-id="613e3-150">For the `InventoryServiceApplication` package:</span></span>
        - <span data-ttu-id="613e3-151">Décompressez `InventoryServiceApplication.PackageDeployer.zip`</span><span class="sxs-lookup"><span data-stu-id="613e3-151">Unzip `InventoryServiceApplication.PackageDeployer.zip`</span></span>
        - <span data-ttu-id="613e3-152">Recherchez le dossier `InventoryServiceApplication`, le fichier `[Content_Types].xml`, le fichier `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll`, le fichier `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config` et le fichier `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config`.</span><span class="sxs-lookup"><span data-stu-id="613e3-152">Find folder `InventoryServiceApplication`, file `[Content_Types].xml`, file `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll`, file `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config`, and file `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config`.</span></span>
        - <span data-ttu-id="613e3-153">Copiez chacun de ces dossiers et fichiers dans le répertoire `.\Tools\PackageDeployment`, qui a été créé lorsque vous avez installé les outils de développement.</span><span class="sxs-lookup"><span data-stu-id="613e3-153">Copy each of these folders and files to the `.\Tools\PackageDeployment` directory, which was created when you installed the developer tools.</span></span>
    1. <span data-ttu-id="613e3-154">Exécutez `.\Tools\PackageDeployment\PackageDeployer.exe`.</span><span class="sxs-lookup"><span data-stu-id="613e3-154">Execute `.\Tools\PackageDeployment\PackageDeployer.exe`.</span></span> <span data-ttu-id="613e3-155">Suivez les instructions sur votre écran pour importer les solutions.</span><span class="sxs-lookup"><span data-stu-id="613e3-155">Follow the instructions on your screen to import the solutions.</span></span>

1. <span data-ttu-id="613e3-156">Attribuez les rôles de sécurité à l'utilisateur de l'application.</span><span class="sxs-lookup"><span data-stu-id="613e3-156">Assign security roles to the application user.</span></span>
    1. <span data-ttu-id="613e3-157">Ouvrez l’URL de votre environnement Dataverse.</span><span class="sxs-lookup"><span data-stu-id="613e3-157">Open the URL of your Dataverse environment.</span></span>
    1. <span data-ttu-id="613e3-158">Accédez à **Paramètres avancés \> Système \> Sécurité \> Utilisateurs**, et recherchez l'utilisateur nommé **# InventoryVisibility**.</span><span class="sxs-lookup"><span data-stu-id="613e3-158">Go to **Advanced Setting \> System \> Security \> Users**, and find user the named **# InventoryVisibility**.</span></span>
    1. <span data-ttu-id="613e3-159">Sélectionner **Attribuer un rôle**, puis **Administrateur système**.</span><span class="sxs-lookup"><span data-stu-id="613e3-159">Select **Assign Role**, and then select **System Administrator**.</span></span> <span data-ttu-id="613e3-160">S’il y a un rôle nommé **Utilisateur Common Data Service**, sélectionnez-le aussi.</span><span class="sxs-lookup"><span data-stu-id="613e3-160">If there is a role that is named **Common Data Service User**, select it as well.</span></span>

#### <a name="set-up-dataverse-manually-by-importing-solutions"></a><span data-ttu-id="613e3-161">Configurer Dataverse manuellement en important des solutions</span><span class="sxs-lookup"><span data-stu-id="613e3-161">Set up Dataverse manually by importing solutions</span></span>

<span data-ttu-id="613e3-162">Une fois les conditions préalables en place, utilisez la procédure suivante si vous préférez configurer Dataverse en important manuellement des solutions.</span><span class="sxs-lookup"><span data-stu-id="613e3-162">After you have the prerequisites in place, use the following procedure if you prefer to set up Dataverse by manually importing solutions.</span></span> <span data-ttu-id="613e3-163">Consultez la section précédente pour plus de détails sur l'utilisation de l'outil Package Deployer (ne faites pas les deux).</span><span class="sxs-lookup"><span data-stu-id="613e3-163">See the previous section for details about how to use the package deployer tool instead (don't do both).</span></span>

1. <span data-ttu-id="613e3-164">Créer un utilisateur d’application pour la visibilité de l’inventaire dans Dataverse :</span><span class="sxs-lookup"><span data-stu-id="613e3-164">Create an application user for Inventory Visibility in Dataverse:</span></span>

    1. <span data-ttu-id="613e3-165">Ouvrez l’URL de votre environnement Dataverse.</span><span class="sxs-lookup"><span data-stu-id="613e3-165">Open the URL of your Dataverse environment.</span></span>
    1. <span data-ttu-id="613e3-166">Aller à **Paramètre avancé \> Système \> Sécurité \> Utilisateurs** et créez un utilisateur d’application.</span><span class="sxs-lookup"><span data-stu-id="613e3-166">Go to **Advanced Setting \> System \> Security \> Users**, and create an application user.</span></span> <span data-ttu-id="613e3-167">Utilisez le menu de la vue pour changez la vue de la page sur **Utilisateurs de l’application**.</span><span class="sxs-lookup"><span data-stu-id="613e3-167">Use the view menu to change the page view to **Application Users**.</span></span>
    1. <span data-ttu-id="613e3-168">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="613e3-168">Select **New**.</span></span> <span data-ttu-id="613e3-169">Définissez l’ID application sur *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*.</span><span class="sxs-lookup"><span data-stu-id="613e3-169">Set the application ID to *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*.</span></span> <span data-ttu-id="613e3-170">(L’ID d’objet sera automatiquement chargé lorsque vous enregistrez vos modifications.) Vous pouvez personnaliser le nom.</span><span class="sxs-lookup"><span data-stu-id="613e3-170">(The object ID will automatically be loaded when you save your changes.) You can customize the name.</span></span> <span data-ttu-id="613e3-171">Par exemple, vous pouvez le changer en *Visibilité de l’inventaire*.</span><span class="sxs-lookup"><span data-stu-id="613e3-171">For example, you can change it to *Inventory Visibility*.</span></span> <span data-ttu-id="613e3-172">Lorsque vous avez terminé, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="613e3-172">When you've finished, select **Save**.</span></span>
    1. <span data-ttu-id="613e3-173">Sélectionner **Attribuer un rôle**, puis **Administrateur système**.</span><span class="sxs-lookup"><span data-stu-id="613e3-173">Select **Assign Role**, and then select **System Administrator**.</span></span> <span data-ttu-id="613e3-174">S’il y a un rôle nommé **Utilisateur Common Data Service**, sélectionnez-le aussi.</span><span class="sxs-lookup"><span data-stu-id="613e3-174">If there is a role that is named **Common Data Service User**, select it too.</span></span>

    <span data-ttu-id="613e3-175">Pour plus d’informations, voir [Créer un utilisateur d’application](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span><span class="sxs-lookup"><span data-stu-id="613e3-175">For more information, see [Create an application user](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span></span>

1. <span data-ttu-id="613e3-176">Si la langue par défaut de votre Dataverse n'est pas **l'Anglais** :</span><span class="sxs-lookup"><span data-stu-id="613e3-176">If the default language of your Dataverse is not **English**:</span></span>

    1. <span data-ttu-id="613e3-177">Accédez à **Paramètres avancés \> Administration \> Langues**,</span><span class="sxs-lookup"><span data-stu-id="613e3-177">Go to **Advanced Setting \> Administration \> Languages**,</span></span>
    1. <span data-ttu-id="613e3-178">Sélectionnez **Anglais (LanguageCode = 1033)** et sélectionnez **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="613e3-178">Select **English (LanguageCode=1033)** and select **Apply**.</span></span>

1. <span data-ttu-id="613e3-179">Importez le fichier `Inventory Visibility Dataverse Solution.zip`, qui comprend entités liées à la configuration Dataverse et Power Apps :</span><span class="sxs-lookup"><span data-stu-id="613e3-179">Import the `Inventory Visibility Dataverse Solution.zip` file, which includes Dataverse configuration related entities and Power Apps:</span></span>

    1. <span data-ttu-id="613e3-180">Allez sur la page **Solutions**.</span><span class="sxs-lookup"><span data-stu-id="613e3-180">Go to the **Solutions** page.</span></span>
    1. <span data-ttu-id="613e3-181">Sélectionnez **Importer**.</span><span class="sxs-lookup"><span data-stu-id="613e3-181">Select **Import**.</span></span>

1. <span data-ttu-id="613e3-182">Importez le flux de déclenchement de la mise à niveau de la configuration :</span><span class="sxs-lookup"><span data-stu-id="613e3-182">Import the configuration upgrade trigger flow:</span></span>

    1. <span data-ttu-id="613e3-183">Allez sur la page Microsoft Flow.</span><span class="sxs-lookup"><span data-stu-id="613e3-183">Go to the Microsoft Flow page.</span></span>
    1. <span data-ttu-id="613e3-184">Assurez-vous que la connexion nommée *Dataverse (héritée)* existe.</span><span class="sxs-lookup"><span data-stu-id="613e3-184">Make sure that the connection that is named *Dataverse (legacy)* exists.</span></span> <span data-ttu-id="613e3-185">(S’il n’existe pas, créez-le.)</span><span class="sxs-lookup"><span data-stu-id="613e3-185">(If it doesn't exist, create it.)</span></span>
    1. <span data-ttu-id="613e3-186">Importer le fichier `Inventory Visibility Configuration Trigger.zip`.</span><span class="sxs-lookup"><span data-stu-id="613e3-186">Import the `Inventory Visibility Configuration Trigger.zip` file.</span></span> <span data-ttu-id="613e3-187">Une fois importé, le déclencheur apparaîtra sous **Mes flux**.</span><span class="sxs-lookup"><span data-stu-id="613e3-187">After it's imported, the trigger will appear under **My flows**.</span></span>
    1. <span data-ttu-id="613e3-188">Initialisez les quatre variables suivantes, en fonction des informations d’environnement :</span><span class="sxs-lookup"><span data-stu-id="613e3-188">Initialize the following four variables, based on the environment information:</span></span>

        - <span data-ttu-id="613e3-189">ID de locataire Azure</span><span class="sxs-lookup"><span data-stu-id="613e3-189">Azure Tenant ID</span></span>
        - <span data-ttu-id="613e3-190">ID client application Azure</span><span class="sxs-lookup"><span data-stu-id="613e3-190">Azure Application Client ID</span></span>
        - <span data-ttu-id="613e3-191">Clé secrète client application Azure</span><span class="sxs-lookup"><span data-stu-id="613e3-191">Azure Application Client Secret</span></span>
        - <span data-ttu-id="613e3-192">Point de terminaison de la visibilité du stock</span><span class="sxs-lookup"><span data-stu-id="613e3-192">Inventory Visibility Endpoint</span></span>

            <span data-ttu-id="613e3-193">Pour plus d’informations sur cette variable, consultez la section [Configurer l’intégration de la visibilité de l’inventaire](#setup-inventory-visibility-integration) plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="613e3-193">For more information about this variable, see the [Set up Inventory Visibility integration](#setup-inventory-visibility-integration) section later in this topic.</span></span>

        <span data-ttu-id="613e3-194">![déclencheur de configuration](media/configuration-trigger.png "déclencheur de configuration")</span><span class="sxs-lookup"><span data-stu-id="613e3-194">![Configuration trigger](media/configuration-trigger.png "Configuration trigger")</span></span>

    1. <span data-ttu-id="613e3-195">Sélectionnez **Activer**.</span><span class="sxs-lookup"><span data-stu-id="613e3-195">Select **Turn on**.</span></span>

### <a name="install-the-add-in"></a><a name="install-add-in"></a><span data-ttu-id="613e3-196">Installer le complément</span><span class="sxs-lookup"><span data-stu-id="613e3-196">Install the add-in</span></span>

<span data-ttu-id="613e3-197">Pour pouvoir installer le complément Visibilité du stock, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="613e3-197">To install the Inventory Visibility Add-in, do the following:</span></span>

1. <span data-ttu-id="613e3-198">Connectez-vous au portail [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="613e3-198">Sign in to the [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portal.</span></span>
1. <span data-ttu-id="613e3-199">Sur la page d’accueil, sélectionnez le projet dans lequel votre environnement est déployé.</span><span class="sxs-lookup"><span data-stu-id="613e3-199">On the home page, select the project where your environment is deployed.</span></span>
1. <span data-ttu-id="613e3-200">Sur la page du projet, sélectionnez l’environnement dans lequel vous souhaitez installer le complément.</span><span class="sxs-lookup"><span data-stu-id="613e3-200">On the project page, select the environment where you want to install the add-in.</span></span>
1. <span data-ttu-id="613e3-201">Sur la page d’environnement, faites défiler vers le bas jusqu’à ce que vous voyiez la section **Compléments d’environnement** dans la section **Intégration Power Platform**, où vous pouvez trouver le nom de l’environnement Dataverse.</span><span class="sxs-lookup"><span data-stu-id="613e3-201">On the environment page, scroll down until you see the **Environment add-ins** section in the **Power Platform integration** section, where you can find the Dataverse environment name.</span></span>
1. <span data-ttu-id="613e3-202">Dans la section **Compléments de l’environnement**, sélectionnez **Installer un nouveau complément**.</span><span class="sxs-lookup"><span data-stu-id="613e3-202">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>

    <span data-ttu-id="613e3-203">![Page de l’environnement dans LCS](media/inventory-visibility-environment.png "Page de l’environnement dans LCS")</span><span class="sxs-lookup"><span data-stu-id="613e3-203">![The environment page in LCS](media/inventory-visibility-environment.png "The environment page in LCS")</span></span>

1. <span data-ttu-id="613e3-204">Sélectionnez le lien **Installer un nouveau complément**.</span><span class="sxs-lookup"><span data-stu-id="613e3-204">Select the **Install a new add-in** link.</span></span> <span data-ttu-id="613e3-205">Une liste des compléments disponibles s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="613e3-205">A list of available add-ins opens.</span></span>
1. <span data-ttu-id="613e3-206">Dans la liste, sélectionnez **visibilité de stock**.</span><span class="sxs-lookup"><span data-stu-id="613e3-206">Select **Inventory Visibility** in the list.</span></span>
1. <span data-ttu-id="613e3-207">Saisissez des valeurs pour les champs suivants pour votre environnement :</span><span class="sxs-lookup"><span data-stu-id="613e3-207">Enter values for the following fields for your environment:</span></span>

    - <span data-ttu-id="613e3-208">**ID application AAD (client)**</span><span class="sxs-lookup"><span data-stu-id="613e3-208">**AAD application (client) ID**</span></span>
    - <span data-ttu-id="613e3-209">**ID locataire AAD**</span><span class="sxs-lookup"><span data-stu-id="613e3-209">**AAD tenant ID**</span></span>

    <span data-ttu-id="613e3-210">![Ajouter dans la page de configuration](media/inventory-visibility-setup.png "Page de configuration de complément")</span><span class="sxs-lookup"><span data-stu-id="613e3-210">![Add in setup page](media/inventory-visibility-setup.png "Add-in setup page")</span></span>

1. <span data-ttu-id="613e3-211">Acceptez les termes et conditions en cochant la case **Termes et conditions**.</span><span class="sxs-lookup"><span data-stu-id="613e3-211">Agree to the terms and condition by selecting the **Terms and conditions** check box.</span></span>
1. <span data-ttu-id="613e3-212">Sélectionnez **Installer**.</span><span class="sxs-lookup"><span data-stu-id="613e3-212">Select **Install**.</span></span> <span data-ttu-id="613e3-213">Le statut du complément s’affichera comme **Installation en cours**.</span><span class="sxs-lookup"><span data-stu-id="613e3-213">The status of the add-in will show as **Installing**.</span></span> <span data-ttu-id="613e3-214">Une fois terminé, actualisez la page pour voir le statut changer en **Installé**.</span><span class="sxs-lookup"><span data-stu-id="613e3-214">When it's done, refresh the page to see the status change to **Installed**.</span></span>

### <a name="uninstall-the-add-in"></a><a name="uninstall-add-in"></a><span data-ttu-id="613e3-215">Désinstaller le complément</span><span class="sxs-lookup"><span data-stu-id="613e3-215">Uninstall the add-in</span></span>

<span data-ttu-id="613e3-216">Pour désinstaller le complément, sélectionnez **Désinstaller**.</span><span class="sxs-lookup"><span data-stu-id="613e3-216">To uninstall the add-in, select **Uninstall**.</span></span> <span data-ttu-id="613e3-217">Lorsque vous actualisez LCS et le complément de visibilité de stock seront supprimés.</span><span class="sxs-lookup"><span data-stu-id="613e3-217">When you refresh LCS, the Inventory Visibility Add-in will be removed.</span></span> <span data-ttu-id="613e3-218">Le processus de désinstallation supprime l’inscription du complément et lance également une tâche pour nettoyer toutes les données d’entreprise stockées dans le service.</span><span class="sxs-lookup"><span data-stu-id="613e3-218">The uninstall process removes the add-in registration and also starts a job to clean up all the business data that is stored in the service.</span></span>

## <a name="consume-on-hand-inventory-data-from-supply-chain-management"></a><span data-ttu-id="613e3-219">Consommez les données d’inventaire disponibles à partir de Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="613e3-219">Consume on-hand inventory data from Supply Chain Management</span></span>

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a><span data-ttu-id="613e3-220">Déployer le package d’intégration de la visibilité d’inventaire</span><span class="sxs-lookup"><span data-stu-id="613e3-220">Deploy the Inventory Visibility integration package</span></span>

<span data-ttu-id="613e3-221">Si vous exécutez la version 10.0.17 ou antérieure de Supply Chain Management, contactez l’équipe d’assistance intégrée de la visibilité d’inventaire à l’adresse [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) pour obtenir le fichier de package.</span><span class="sxs-lookup"><span data-stu-id="613e3-221">If you're running Supply Chain Management version 10.0.17 or earlier, contact the Inventory Visibility on-board support team at [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) to get the package file.</span></span> <span data-ttu-id="613e3-222">Déployez ensuite le package dans LCS.</span><span class="sxs-lookup"><span data-stu-id="613e3-222">Then deploy the package in LCS.</span></span>

> [!NOTE]
> <span data-ttu-id="613e3-223">Si une erreur de non-concordance de version se produit pendant le déploiement, vous devez importer manuellement le projet X++ dans votre environnement de développement.</span><span class="sxs-lookup"><span data-stu-id="613e3-223">If a version mismatch error occurs during deployment, you must manually import the X++ project into your development environment.</span></span> <span data-ttu-id="613e3-224">Créez ensuite le package déployable dans votre environnement de développement et déployez-le dans votre environnement de production.</span><span class="sxs-lookup"><span data-stu-id="613e3-224">Then create the deployable package in your development environment, and deploy it in your production environment.</span></span>
> 
> <span data-ttu-id="613e3-225">Le code est inclus dans la version 10.0.18 de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="613e3-225">The code is included with Supply Chain Management version 10.0.18.</span></span> <span data-ttu-id="613e3-226">Si vous exécutez cette version ou une version ultérieure, le déploiement n’est pas requis.</span><span class="sxs-lookup"><span data-stu-id="613e3-226">If you're running that version or later, deployment isn't required.</span></span>

<span data-ttu-id="613e3-227">Assurez-vous que les fonctionnalités suivantes sont activées dans votre environnement Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="613e3-227">Make sure that the following features are turned on in your Supply Chain Management environment.</span></span> <span data-ttu-id="613e3-228">(Par défaut, ils sont identiques.)</span><span class="sxs-lookup"><span data-stu-id="613e3-228">(By default, they are turned on.)</span></span>

| <span data-ttu-id="613e3-229">Description de fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="613e3-229">Feature description</span></span> | <span data-ttu-id="613e3-230">Version du code</span><span class="sxs-lookup"><span data-stu-id="613e3-230">Code version</span></span> | <span data-ttu-id="613e3-231">Basculer la classe</span><span class="sxs-lookup"><span data-stu-id="613e3-231">Toggle class</span></span> |
|---|---|---|
| <span data-ttu-id="613e3-232">Activer ou désactiver l’utilisation des dimensions d’inventaire sur le tableau InventSum</span><span class="sxs-lookup"><span data-stu-id="613e3-232">Enable or disable using inventory dimensions on InventSum table</span></span> | <span data-ttu-id="613e3-233">10.0.11</span><span class="sxs-lookup"><span data-stu-id="613e3-233">10.0.11</span></span> | <span data-ttu-id="613e3-234">InventUseDimOfInventSumToggle</span><span class="sxs-lookup"><span data-stu-id="613e3-234">InventUseDimOfInventSumToggle</span></span> |
| <span data-ttu-id="613e3-235">Activer ou désactiver l’utilisation des dimensions d’inventaire sur le tableau InventSumDelta</span><span class="sxs-lookup"><span data-stu-id="613e3-235">Enable or disable using inventory dimensions on InventSumDelta table</span></span> | <span data-ttu-id="613e3-236">10.0.12</span><span class="sxs-lookup"><span data-stu-id="613e3-236">10.0.12</span></span> | <span data-ttu-id="613e3-237">InventUseDimOfInventSumDeltaToggle</span><span class="sxs-lookup"><span data-stu-id="613e3-237">InventUseDimOfInventSumDeltaToggle</span></span> |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a><span data-ttu-id="613e3-238">Configurer l’intégration de la visibilité du stock</span><span class="sxs-lookup"><span data-stu-id="613e3-238">Set up Inventory Visibility integration</span></span>

1. <span data-ttu-id="613e3-239">Dans Supply Chain Management, ouvrez l’espace de travail **[Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** et activez la fonctionnalité **Intégration de la visibilité de l’inventaire**.</span><span class="sxs-lookup"><span data-stu-id="613e3-239">In Supply Chain Management, open the **[Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** workspace, and turn on the **Inventory Visibility Integration** feature.</span></span>
1. <span data-ttu-id="613e3-240">Aller à **Gestion de l’inventaire \> Installation \> Paramètres d’intégration de la visibilité de l’inventaire** et entrez l’URL de l’environnement dans lequel vous exécutez la visibilité de l’inventaire.</span><span class="sxs-lookup"><span data-stu-id="613e3-240">Go to **Inventory Management \> Set up \> Inventory Visibility Integration parameters**, and enter the URL of the environment where you're running Inventory Visibility.</span></span>

    <span data-ttu-id="613e3-241">Recherchez la région Azure de votre environnement LCS, puis entrez l’URL.</span><span class="sxs-lookup"><span data-stu-id="613e3-241">Find your LCS environment's Azure region, and then enter the URL.</span></span> <span data-ttu-id="613e3-242">L’URL a le format suivant :</span><span class="sxs-lookup"><span data-stu-id="613e3-242">The URL has the following form:</span></span>

    `https://inventoryservice.<RegionShortName>-il301.gateway.prod.island.powerapps.com`

    <span data-ttu-id="613e3-243">Par exemple, si vous êtes en Europe, votre environnement aura l’une des URL suivantes :</span><span class="sxs-lookup"><span data-stu-id="613e3-243">For example, if you're in Europe, your environment will have one of the following URLs:</span></span>

    - `https://inventoryservice.neu-il301.gateway.prod.island.powerapps.com`
    - `https://inventoryservice.weu-il301.gateway.prod.island.powerapps.com`

    <span data-ttu-id="613e3-244">Les régions suivantes sont disponibles actuellement.</span><span class="sxs-lookup"><span data-stu-id="613e3-244">The following regions are currently available.</span></span>

    | <span data-ttu-id="613e3-245">Région Azure</span><span class="sxs-lookup"><span data-stu-id="613e3-245">Azure region</span></span> | <span data-ttu-id="613e3-246">Nom abrégé de la région</span><span class="sxs-lookup"><span data-stu-id="613e3-246">Region short name</span></span> |
    |---|---|
    | <span data-ttu-id="613e3-247">Est de l’Australie</span><span class="sxs-lookup"><span data-stu-id="613e3-247">Australia east</span></span> | <span data-ttu-id="613e3-248">eau</span><span class="sxs-lookup"><span data-stu-id="613e3-248">eau</span></span> |
    | <span data-ttu-id="613e3-249">Sud-est de l’Australie</span><span class="sxs-lookup"><span data-stu-id="613e3-249">Australia southeast</span></span> | <span data-ttu-id="613e3-250">seau</span><span class="sxs-lookup"><span data-stu-id="613e3-250">seau</span></span> |
    | <span data-ttu-id="613e3-251">Centre du Canada</span><span class="sxs-lookup"><span data-stu-id="613e3-251">Canada central</span></span> | <span data-ttu-id="613e3-252">cca</span><span class="sxs-lookup"><span data-stu-id="613e3-252">cca</span></span> |
    | <span data-ttu-id="613e3-253">Canada Est</span><span class="sxs-lookup"><span data-stu-id="613e3-253">Canada east</span></span> | <span data-ttu-id="613e3-254">eca</span><span class="sxs-lookup"><span data-stu-id="613e3-254">eca</span></span> |
    | <span data-ttu-id="613e3-255">Nord de l’Europe</span><span class="sxs-lookup"><span data-stu-id="613e3-255">North Europe</span></span> | <span data-ttu-id="613e3-256">neu</span><span class="sxs-lookup"><span data-stu-id="613e3-256">neu</span></span> |
    | <span data-ttu-id="613e3-257">Ouest de l’Europe</span><span class="sxs-lookup"><span data-stu-id="613e3-257">West Europe</span></span> | <span data-ttu-id="613e3-258">weu</span><span class="sxs-lookup"><span data-stu-id="613e3-258">weu</span></span> |
    | <span data-ttu-id="613e3-259">Est des États-Unis</span><span class="sxs-lookup"><span data-stu-id="613e3-259">East US</span></span> | <span data-ttu-id="613e3-260">eus</span><span class="sxs-lookup"><span data-stu-id="613e3-260">eus</span></span> |
    | <span data-ttu-id="613e3-261">Ouest des États-Unis</span><span class="sxs-lookup"><span data-stu-id="613e3-261">West US</span></span> | <span data-ttu-id="613e3-262">wus</span><span class="sxs-lookup"><span data-stu-id="613e3-262">wus</span></span> |

1. <span data-ttu-id="613e3-263">Aller à **Gestion de l’inventaire \> Périodique \> Intégration de la visibilité de l’inventaire** et activez le travail.</span><span class="sxs-lookup"><span data-stu-id="613e3-263">Go to **Inventory Management \> Periodic \> Inventory Visibility Integration**, and enable the job.</span></span> <span data-ttu-id="613e3-264">Tous les événements de changement d’inventaire de Supply Chain Management seront désormais publiés dans la visibilité des stocks.</span><span class="sxs-lookup"><span data-stu-id="613e3-264">All inventory change events from Supply Chain Management will now be posted to Inventory Visibility.</span></span>

## <a name="the-inventory-visibility-add-in-public-api"></a><a name="inventory-visibility-public-api"></a><span data-ttu-id="613e3-265">L’API publique du complément de visibilité de stock</span><span class="sxs-lookup"><span data-stu-id="613e3-265">The Inventory Visibility Add-in public API</span></span>

<span data-ttu-id="613e3-266">L’API REST publique du complément de visibilité de stock présente plusieurs points de terminaison d’intégration spécifiques.</span><span class="sxs-lookup"><span data-stu-id="613e3-266">The public REST API of the Inventory Visibility Add-in presents several specific endpoints for integration.</span></span> <span data-ttu-id="613e3-267">Elle prend en charge trois types d’interactions principaux :</span><span class="sxs-lookup"><span data-stu-id="613e3-267">It supports three main interaction types:</span></span>

- <span data-ttu-id="613e3-268">Publication des modifications de stock disponibles du complément à partir d’un système externe</span><span class="sxs-lookup"><span data-stu-id="613e3-268">Posting on-hand inventory changes to the add-in from an external system</span></span>
- <span data-ttu-id="613e3-269">Interrogation des quantités en stock actuelles à partir d’un système externe</span><span class="sxs-lookup"><span data-stu-id="613e3-269">Querying current on-hand quantities from an external system</span></span>
- <span data-ttu-id="613e3-270">Synchronisation automatique avec le stock Supply Chain Management à portée de main</span><span class="sxs-lookup"><span data-stu-id="613e3-270">Automatic synchronization with Supply Chain Management on-hand inventory</span></span>

<span data-ttu-id="613e3-271">La synchronisation automatique ne fait pas partie de l’API publique.</span><span class="sxs-lookup"><span data-stu-id="613e3-271">Automatic synchronization isn't part of the public API.</span></span> <span data-ttu-id="613e3-272">Au lieu de cela, il est géré en arrière-plan pour les environnements dans lesquels le complément de visibilité d’inventaire est activé.</span><span class="sxs-lookup"><span data-stu-id="613e3-272">Instead, it's handled in the background for environments where the Inventory Visibility Add-in is enabled.</span></span>

### <a name="authentication"></a><a name="inventory-visibility-authentication"></a><span data-ttu-id="613e3-273">Authentification</span><span class="sxs-lookup"><span data-stu-id="613e3-273">Authentication</span></span>

<span data-ttu-id="613e3-274">Le jeton de sécurité de la plateforme est utilisé pour appeler le complément de visibilité d’inventaire.</span><span class="sxs-lookup"><span data-stu-id="613e3-274">The platform security token is used to call the Inventory Visibility Add-in.</span></span> <span data-ttu-id="613e3-275">Par conséquent, vous devez générer un jeton *Azure Active Directory (Azure AD)* en utilisant votre application Azure AD.</span><span class="sxs-lookup"><span data-stu-id="613e3-275">Therefore, you must generate an *Azure Active Directory (Azure AD) token* by using your Azure AD application.</span></span> <span data-ttu-id="613e3-276">Vous devez ensuite utiliser le jeton Azure AD pour obtenir le *jeton d’accès* du service de sécurité.</span><span class="sxs-lookup"><span data-stu-id="613e3-276">You must then use the Azure AD token to get the *access token* from the security service.</span></span>

<span data-ttu-id="613e3-277">Obtenez un jeton de service de sécurité en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="613e3-277">Get a security service token by doing the following:</span></span>

1. <span data-ttu-id="613e3-278">Connectez-vous au portail Azure et utilisez-le pour trouver le `clientId` et le `clientSecret` de votre application Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="613e3-278">Sign in to Azure portal and use it to find the `clientId` and `clientSecret` for your Supply Chain Management application.</span></span>
1. <span data-ttu-id="613e3-279">Récupérez un jeton Azure Active Directory (`aadToken`) en envoyant une requête HTTP avec les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="613e3-279">Fetch an Azure Active Directory token (`aadToken`) by submitting an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="613e3-280">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span><span class="sxs-lookup"><span data-stu-id="613e3-280">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span></span>
    - <span data-ttu-id="613e3-281">**Méthode** - `GET`</span><span class="sxs-lookup"><span data-stu-id="613e3-281">**Method** - `GET`</span></span>
    - <span data-ttu-id="613e3-282">**Contenu du corps (données du formulaire)**  :</span><span class="sxs-lookup"><span data-stu-id="613e3-282">**Body content (form data)**:</span></span>

        | <span data-ttu-id="613e3-283">clé</span><span class="sxs-lookup"><span data-stu-id="613e3-283">key</span></span> | <span data-ttu-id="613e3-284">valeur</span><span class="sxs-lookup"><span data-stu-id="613e3-284">value</span></span> |
        | --- | --- |
        | <span data-ttu-id="613e3-285">client_id</span><span class="sxs-lookup"><span data-stu-id="613e3-285">client_id</span></span> | <span data-ttu-id="613e3-286">${aadAppId}</span><span class="sxs-lookup"><span data-stu-id="613e3-286">${aadAppId}</span></span> |
        | <span data-ttu-id="613e3-287">client_secret</span><span class="sxs-lookup"><span data-stu-id="613e3-287">client_secret</span></span> | <span data-ttu-id="613e3-288">${aadAppSecret}</span><span class="sxs-lookup"><span data-stu-id="613e3-288">${aadAppSecret}</span></span> |
        | <span data-ttu-id="613e3-289">grant_type</span><span class="sxs-lookup"><span data-stu-id="613e3-289">grant_type</span></span> | <span data-ttu-id="613e3-290">client_credentials</span><span class="sxs-lookup"><span data-stu-id="613e3-290">client_credentials</span></span> |
        | <span data-ttu-id="613e3-291">resource</span><span class="sxs-lookup"><span data-stu-id="613e3-291">resource</span></span> | <span data-ttu-id="613e3-292">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="613e3-292">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
1. <span data-ttu-id="613e3-293">Vous devriez recevoir un `aadToken` en réponse, qui ressemble à l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="613e3-293">You should receive an `aadToken` in response, which resembles the following example.</span></span>

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

1. <span data-ttu-id="613e3-294">Formulez une requête JSON qui ressemble à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="613e3-294">Formulate a JSON request that resembles the following:</span></span>

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

    <span data-ttu-id="613e3-295">Où :</span><span class="sxs-lookup"><span data-stu-id="613e3-295">Where:</span></span>
    - <span data-ttu-id="613e3-296">La valeur `client_assertion` doit être le `aadToken` que vous avez reçu à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="613e3-296">The `client_assertion` value must be the `aadToken` you received in the previous step.</span></span>
    - <span data-ttu-id="613e3-297">La valeur `context` doit être l’ID d’environnement dans lequel vous souhaitez déployer le complément.</span><span class="sxs-lookup"><span data-stu-id="613e3-297">The `context` value must be the environment ID where you want to deploy the add-in.</span></span>
    - <span data-ttu-id="613e3-298">Définissez toutes les autres valeurs comme indiqué dans l’exemple.</span><span class="sxs-lookup"><span data-stu-id="613e3-298">Set all of other values as shown in the example.</span></span>

1. <span data-ttu-id="613e3-299">Envoyez une requête HTTP avec les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="613e3-299">Submit an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="613e3-300">**URL** - `https://securityservice.operations365.dynamics.com/token`</span><span class="sxs-lookup"><span data-stu-id="613e3-300">**URL** - `https://securityservice.operations365.dynamics.com/token`</span></span>
    - <span data-ttu-id="613e3-301">**Méthode** - `POST`</span><span class="sxs-lookup"><span data-stu-id="613e3-301">**Method** - `POST`</span></span>
    - <span data-ttu-id="613e3-302">**En-tête HTTP** : incluez la version de l’API (la clé est `Api-Version` et la valeur est `1.0`)</span><span class="sxs-lookup"><span data-stu-id="613e3-302">**HTTP header** - Include the API version (key is `Api-Version` and value is `1.0`)</span></span>
    - <span data-ttu-id="613e3-303">**Contenu du corps** : incluez la requête JSON que vous avez créée à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="613e3-303">**Body content** - Include the JSON request that you created in the previous step.</span></span>

1. <span data-ttu-id="613e3-304">Vous obtiendrez un `access_token` en réponse.</span><span class="sxs-lookup"><span data-stu-id="613e3-304">You will get an `access_token` in response.</span></span> <span data-ttu-id="613e3-305">C’est ce dont vous avez besoin en tant que jeton de support pour appeler l’API de visibilité de stock.</span><span class="sxs-lookup"><span data-stu-id="613e3-305">This is what you need as a bearer token to call the Inventory Visibility API.</span></span> <span data-ttu-id="613e3-306">Voici un exemple :</span><span class="sxs-lookup"><span data-stu-id="613e3-306">Here is an example.</span></span>

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="sample-request"></a><a name="inventory-visibility-sample-request"></a><span data-ttu-id="613e3-307">Exemple de requête</span><span class="sxs-lookup"><span data-stu-id="613e3-307">Sample Request</span></span>

<span data-ttu-id="613e3-308">Pour votre référence, voici un exemple de requête http ; vous pouvez utiliser n'importe quel outil ou langage de code pour envoyer cette requête, tel que ``Postman``.</span><span class="sxs-lookup"><span data-stu-id="613e3-308">For your reference, here is a sample http request, you can use any tools or coding language to send this request, such as  ``Postman``.</span></span>

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand

# Method
Post

# Header
# replace {access_token} with the one get from security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "quantities": {
        "pos": {
            "inbound": 5
        }  
    },
    "dimensions": {
        "SizeId": "Small",
        "ColorId": "Red",
        "SiteId": "1",
        "LocationId": "11"
    }
}
```

### <a name="configure-the-inventory-visibility-api"></a><a name="inventory-visibility-configuration"></a><span data-ttu-id="613e3-309">Configurer l’API de visibilité de stock</span><span class="sxs-lookup"><span data-stu-id="613e3-309">Configure the Inventory Visibility API</span></span>

<span data-ttu-id="613e3-310">Avant d’utiliser le service, vous devez effectuer les configurations décrites dans les sous-sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="613e3-310">Before using the service, you must complete the configurations described in the following subsections.</span></span> <span data-ttu-id="613e3-311">La configuration peut varier en fonction des détails de votre environnement.</span><span class="sxs-lookup"><span data-stu-id="613e3-311">The configuration may vary based on the details of your environment.</span></span> <span data-ttu-id="613e3-312">Il comprend principalement quatre parties :</span><span class="sxs-lookup"><span data-stu-id="613e3-312">It primarily includes four parts:</span></span>

- [<span data-ttu-id="613e3-313">Partitionnement</span><span class="sxs-lookup"><span data-stu-id="613e3-313">Partitioning</span></span>](#partitioning)
- [<span data-ttu-id="613e3-314">Configurations des dimensions</span><span class="sxs-lookup"><span data-stu-id="613e3-314">Dimension configurations</span></span>](#dimension-configurations)
- [<span data-ttu-id="613e3-315">Indexation</span><span class="sxs-lookup"><span data-stu-id="613e3-315">Indexing</span></span>](#indexing)
- [<span data-ttu-id="613e3-316">Mesure personnalisée</span><span class="sxs-lookup"><span data-stu-id="613e3-316">Custom measurement</span></span>](#custom-measurement)

#### <a name="partitioning"></a><span data-ttu-id="613e3-317">Partitionnement</span><span class="sxs-lookup"><span data-stu-id="613e3-317">Partitioning</span></span>

<span data-ttu-id="613e3-318">Le partitionnement peut influencer considérablement les performances de l’API de visibilité d’inventaire.</span><span class="sxs-lookup"><span data-stu-id="613e3-318">Partitioning can significantly influence the performance of the Inventory Visibility API.</span></span> <span data-ttu-id="613e3-319">C’est une bonne idée de définir un schéma qui permet de petits regroupements de données tout en permettant des requêtes de données significatives.</span><span class="sxs-lookup"><span data-stu-id="613e3-319">It's a good idea to define a scheme that allows for small groupings of data while still allowing for meaningful data queries.</span></span>

<span data-ttu-id="613e3-320">L’`organizationId` (`dataAreaId` dans Supply Chain Management) fera toujours partie du partitionnement et, par défaut, la visibilité du stock est définie pour partitionner par dimensions comme *Site + Localisation*.</span><span class="sxs-lookup"><span data-stu-id="613e3-320">The `organizationId` (`dataAreaId` in Supply Chain Management) will always be part of the partitioning, and by default Inventory Visibility is set to partition by dimensions as *Site + Location*.</span></span> <span data-ttu-id="613e3-321">Cela signifie que le service doit toujours être interrogé avec ces dimensions définies sur les filtres.</span><span class="sxs-lookup"><span data-stu-id="613e3-321">This means that the service must always be queried with these dimensions defined on the filters.</span></span>

> [!NOTE]
> <span data-ttu-id="613e3-322">*Site* et *Emplacement* sont deux dimensions générales par défaut dans la visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="613e3-322">*Site* and *Location* are two general default dimensions in Inventory Visibility.</span></span> <span data-ttu-id="613e3-323">Dans Supply Chain Management, ces dimensions sont appelées *Site* (`InventSiteId`) et *Entrepôt* (`InventLocationId`)</span><span class="sxs-lookup"><span data-stu-id="613e3-323">In Supply Chain Management, those dimensions are called *Site* (`InventSiteId`) and *Warehouse* (`InventLocationId`)</span></span>

### <a name="dimension-configurations"></a><span data-ttu-id="613e3-324">Configurations des dimensions</span><span class="sxs-lookup"><span data-stu-id="613e3-324">Dimension configurations</span></span>

<span data-ttu-id="613e3-325">La visibilité du stock fournira une liste de dimensions générales par défaut pour permettre l’intégration du système source multiple.</span><span class="sxs-lookup"><span data-stu-id="613e3-325">Inventory Visibility will provide a list of general default dimensions to enable the multiple source system integration.</span></span>

<span data-ttu-id="613e3-326">Le tableau suivant répertorie les dimensions d’inventaire qui seront les noms de dimension par défaut dans la visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="613e3-326">The following table lists the inventory dimensions that will be the default dimension names in Inventory Visibility.</span></span>

| <span data-ttu-id="613e3-327">Type de dimension</span><span class="sxs-lookup"><span data-stu-id="613e3-327">Dimension type</span></span> | <span data-ttu-id="613e3-328">Nom de dimension</span><span class="sxs-lookup"><span data-stu-id="613e3-328">Dimension name</span></span> |
|---|---|
| <span data-ttu-id="613e3-329">Produit</span><span class="sxs-lookup"><span data-stu-id="613e3-329">Product</span></span> | `ColorId` |
| <span data-ttu-id="613e3-330">Produit</span><span class="sxs-lookup"><span data-stu-id="613e3-330">Product</span></span> | `SizeId` |
| <span data-ttu-id="613e3-331">Produit</span><span class="sxs-lookup"><span data-stu-id="613e3-331">Product</span></span> | `StyleId` |
| <span data-ttu-id="613e3-332">Produit</span><span class="sxs-lookup"><span data-stu-id="613e3-332">Product</span></span> | `ConfigId` |
| <span data-ttu-id="613e3-333">Suivi</span><span class="sxs-lookup"><span data-stu-id="613e3-333">Tracking</span></span> | `BatchId` |
| <span data-ttu-id="613e3-334">Suivi</span><span class="sxs-lookup"><span data-stu-id="613e3-334">Tracking</span></span> | `SerialId` |
| <span data-ttu-id="613e3-335">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="613e3-335">Location</span></span> | `LocationId` |
| <span data-ttu-id="613e3-336">Entrepôt</span><span class="sxs-lookup"><span data-stu-id="613e3-336">Location</span></span> | `SiteId` |
| <span data-ttu-id="613e3-337">Statut du stock</span><span class="sxs-lookup"><span data-stu-id="613e3-337">Inventory Status</span></span> | `StatusId` |
| <span data-ttu-id="613e3-338">Spécifique à l’entrepôt</span><span class="sxs-lookup"><span data-stu-id="613e3-338">Warehouse Specific</span></span> | `WMSLocationId` |
| <span data-ttu-id="613e3-339">Spécifique à l’entrepôt</span><span class="sxs-lookup"><span data-stu-id="613e3-339">Warehouse Specific</span></span> | `WMSPalletId` |
| <span data-ttu-id="613e3-340">Spécifique à l’entrepôt</span><span class="sxs-lookup"><span data-stu-id="613e3-340">Warehouse Specific</span></span> | `LicensePlateId` |

> [!NOTE]
> <span data-ttu-id="613e3-341">Le type de dimension répertorié dans le tableau précédent est à titre indicatif uniquement.</span><span class="sxs-lookup"><span data-stu-id="613e3-341">The dimension type listed in the previous table is for reference only.</span></span> <span data-ttu-id="613e3-342">Vous n’avez pas besoin de définir le type de dimension dans la visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="613e3-342">You don't need to define the dimension type in Inventory Visibility.</span></span>

<span data-ttu-id="613e3-343">Si une dimension personnalisée existe et doit passer à une valeur par défaut lorsqu’elle est utilisée par la visibilité du stock, vous pouvez configurer le nom **Dimension personnalisée** dans la visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="613e3-343">If a custom dimension exists and needs to flow to a default value when consumed by Inventory Visibility, you can configure the **Custom dimension** name in Inventory Visibility.</span></span>

<span data-ttu-id="613e3-344">Les systèmes externes accèdent à la visibilité du stock via des API RESTful qui permettent d’interroger des informations disponibles sur des ensembles de dimensions donnés.</span><span class="sxs-lookup"><span data-stu-id="613e3-344">External systems access Inventory Visibility through RESTful APIs that enable on-hand information on given sets of dimensions to be queried.</span></span> <span data-ttu-id="613e3-345">Pour l’intégration, la visibilité du stock vous permet de configurer la *source de données de canal externe* et la dimension source des *dimensions cibles* dans la visibilité du stock.</span><span class="sxs-lookup"><span data-stu-id="613e3-345">For the integration, Inventory Visibility enables you to configure the *external channel data source* and the source dimension to the *target dimensions* in Inventory Visibility.</span></span>

<span data-ttu-id="613e3-346">Les dimensions cibles doivent être l’une des suivantes :</span><span class="sxs-lookup"><span data-stu-id="613e3-346">The target dimensions should be one of the following:</span></span>

- <span data-ttu-id="613e3-347">Dimensions par défaut dans la visibilité du stock</span><span class="sxs-lookup"><span data-stu-id="613e3-347">Default dimensions in Inventory Visibility</span></span>
- <span data-ttu-id="613e3-348">Dimensions personnalisées</span><span class="sxs-lookup"><span data-stu-id="613e3-348">Custom dimensions</span></span>

<span data-ttu-id="613e3-349">Le but de la configuration des dimensions est de standardiser l’intégration multi-système pour la requête sur les dimensions et l’événement de publication avec les dimensions.</span><span class="sxs-lookup"><span data-stu-id="613e3-349">The purpose of dimension configuration is to standardize the multi-system integration for the query on dimensions and the posting event with dimensions.</span></span>

#### <a name="indexing"></a><span data-ttu-id="613e3-350">Indexation</span><span class="sxs-lookup"><span data-stu-id="613e3-350">Indexing</span></span>

<span data-ttu-id="613e3-351">La plupart du temps, la requête de stock disponible sera non seulement au niveau "total" le plus élevé, mais vous souhaiterez peut-être voir les résultats agrégés en fonction des dimensions de stock.</span><span class="sxs-lookup"><span data-stu-id="613e3-351">Most of the time, the inventory on-hand query will not only be on the highest "total" level, but you may want to see results aggregated based on the inventory dimensions.</span></span>

<span data-ttu-id="613e3-352">La visibilité du stock offre une certaine flexibilité en vous permettant de configurer les index, qui sont basés sur la dimension ou la combinaison des dimensions.</span><span class="sxs-lookup"><span data-stu-id="613e3-352">Inventory Visibility provides flexibility by allowing you to set up the indexes, which are based on the dimension or the combination of the dimensions.</span></span>

> [!NOTE]
> <span data-ttu-id="613e3-353">Actuellement, vous ne pouvez configurer les index que jusqu’à un maximum de cinq.</span><span class="sxs-lookup"><span data-stu-id="613e3-353">Currently, you can only configure indexes to a maximum of five.</span></span> <span data-ttu-id="613e3-354">Vous devez examiner attentivement la dimension ou la combinaison de dimensions que vous utiliserez avant la mise en œuvre pour vous assurer qu’elle répondra aux besoins de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="613e3-354">You need to carefully consider which dimension or dimension combination you will use before the implementation to ensure that it will meet your business needs.</span></span> <span data-ttu-id="613e3-355">Par exemple, si vous souhaitez interroger les produits comme suit :</span><span class="sxs-lookup"><span data-stu-id="613e3-355">For example, if you want to query products as follows:</span></span>

- <span data-ttu-id="613e3-356">Recherchez le produit agrégé disponible par les dimensions *Couleur* et *Taille*.</span><span class="sxs-lookup"><span data-stu-id="613e3-356">Query the aggregated product on-hand by the *Color* and *Size* dimensions.</span></span>
- <span data-ttu-id="613e3-357">Dans certains cas, vous souhaitez simplement interroger le produit au total.</span><span class="sxs-lookup"><span data-stu-id="613e3-357">In some cases, you just want to query on the product in total.</span></span>

<span data-ttu-id="613e3-358">Vous auriez deux index définis comme suit :</span><span class="sxs-lookup"><span data-stu-id="613e3-358">You would have two indexes defined as the following:</span></span>

- `["ColorId", "SizeId"]`
- `[]`

<span data-ttu-id="613e3-359">Le crochet vide sera agrégé en fonction de l’ID de produit dans la partition.</span><span class="sxs-lookup"><span data-stu-id="613e3-359">The empty bracket will aggregate based on the product ID within the partition.</span></span>

<span data-ttu-id="613e3-360">L’indexation définit comment vous pouvez regrouper vos résultats en fonction du paramètre de requête `groupBy`.</span><span class="sxs-lookup"><span data-stu-id="613e3-360">The indexing defines how you can group your results based on the `groupBy` query setting.</span></span> <span data-ttu-id="613e3-361">Dans ce cas, si vous ne définissez aucune valeur `groupBy`, vous obtiendrez les totaux par `productid`.</span><span class="sxs-lookup"><span data-stu-id="613e3-361">In this case if you don't define any `groupBy` values, you'll get totals by `productid`.</span></span> <span data-ttu-id="613e3-362">Sinon, si vous définissez `groupBy` comme `groupBy=ColorId&groupBy=SizeId`, vous obtiendrez plusieurs lignes renvoyées, en fonction des différentes combinaisons de couleurs et de tailles du système.</span><span class="sxs-lookup"><span data-stu-id="613e3-362">Otherwise, if you define `groupBy` as `groupBy=ColorId&groupBy=SizeId`, you'll get multiple lines returned, based on the different color and size combinations in the system.</span></span>

<span data-ttu-id="613e3-363">Vous pouvez mettre vos critères de requête dans le corps de la requête.</span><span class="sxs-lookup"><span data-stu-id="613e3-363">You can put your query criteria in the request body.</span></span>

<span data-ttu-id="613e3-364">Voici un exemple de requête sur le produit avec une combinaison de couleur et de taille.</span><span class="sxs-lookup"><span data-stu-id="613e3-364">Here is a sample query on the product with color and size combination.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct1", "MyProduct2"],
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

<span data-ttu-id="613e3-365">Pour le champ `filters`, actuellement seul `ProductId` prend en charge plusieurs valeurs.</span><span class="sxs-lookup"><span data-stu-id="613e3-365">For the `filters` field, currently only `ProductId` supports multiple values.</span></span> <span data-ttu-id="613e3-366">Si `ProductId` est un tableau vide, tous les produits seront interrogés.</span><span class="sxs-lookup"><span data-stu-id="613e3-366">If the `ProductId` is an empty array, all products will be queried.</span></span>

#### <a name="custom-measurement"></a><span data-ttu-id="613e3-367">Mesure personnalisée</span><span class="sxs-lookup"><span data-stu-id="613e3-367">Custom measurement</span></span>

<span data-ttu-id="613e3-368">Les quantités de mesure par défaut sont liées à Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="613e3-368">The default measurement quantities are linked to Supply Chain Management.</span></span> <span data-ttu-id="613e3-369">Cependant, vous souhaiterez peut-être avoir une quantité composée d’une combinaison des mesures par défaut.</span><span class="sxs-lookup"><span data-stu-id="613e3-369">However, you may want to have a quantity that is made up of a combination of the default measurements.</span></span> <span data-ttu-id="613e3-370">Pour ce faire, vous pouvez avoir une configuration de quantités personnalisées, qui seront ajoutées à la sortie des requêtes en main.</span><span class="sxs-lookup"><span data-stu-id="613e3-370">To do this, you can have a configuration of custom quantities, which will be added to the output of the on-hand queries.</span></span>

<span data-ttu-id="613e3-371">La fonctionnalité vous permet simplement de définir un ensemble de mesures qui seront ajoutées, et/ou un ensemble de mesures qui seront soustraites, afin de la mesure personnalisée.</span><span class="sxs-lookup"><span data-stu-id="613e3-371">The functionality simply allows you to define a set of measures that will be added, and/or a set of measures that will be subtracted, in order to form the custom measurement.</span></span>

<span data-ttu-id="613e3-372">Par exemple, avec la condition de requête suivante, vous configurerez la quantité de mesure personnalisée comme `MyCustomAvailableforReservation` à consommer par le système de consommation.</span><span class="sxs-lookup"><span data-stu-id="613e3-372">For example, with the following query condition, you will configure the custom measurement quantity as `MyCustomAvailableforReservation` to be consumed by the consumption system.</span></span>

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



| <span data-ttu-id="613e3-373">Système de consommation</span><span class="sxs-lookup"><span data-stu-id="613e3-373">Consumption system</span></span> | <span data-ttu-id="613e3-374">Mesures calculées</span><span class="sxs-lookup"><span data-stu-id="613e3-374">Calculated measurers</span></span> | <span data-ttu-id="613e3-375">Source de données</span><span class="sxs-lookup"><span data-stu-id="613e3-375">Data source</span></span> | <span data-ttu-id="613e3-376">Modificateur</span><span class="sxs-lookup"><span data-stu-id="613e3-376">Modifier</span></span> | <span data-ttu-id="613e3-377">Type de calcul du modificateur</span><span class="sxs-lookup"><span data-stu-id="613e3-377">Modifier calculation type</span></span> |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | <span data-ttu-id="613e3-378">Addition</span><span class="sxs-lookup"><span data-stu-id="613e3-378">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | <span data-ttu-id="613e3-379">Addition</span><span class="sxs-lookup"><span data-stu-id="613e3-379">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | <span data-ttu-id="613e3-380">Soustraction</span><span class="sxs-lookup"><span data-stu-id="613e3-380">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | <span data-ttu-id="613e3-381">Addition</span><span class="sxs-lookup"><span data-stu-id="613e3-381">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | <span data-ttu-id="613e3-382">Soustraction</span><span class="sxs-lookup"><span data-stu-id="613e3-382">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | <span data-ttu-id="613e3-383">Addition</span><span class="sxs-lookup"><span data-stu-id="613e3-383">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | <span data-ttu-id="613e3-384">Addition</span><span class="sxs-lookup"><span data-stu-id="613e3-384">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | <span data-ttu-id="613e3-385">Soustraction</span><span class="sxs-lookup"><span data-stu-id="613e3-385">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | <span data-ttu-id="613e3-386">Soustraction</span><span class="sxs-lookup"><span data-stu-id="613e3-386">Subtraction</span></span> |

<span data-ttu-id="613e3-387">Avec cela, la requête sur la quantité de mesure personnalisée renverra la sortie suivante.</span><span class="sxs-lookup"><span data-stu-id="613e3-387">With that, the query on the custom measurement quantity will return the following output.</span></span>

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

<span data-ttu-id="613e3-388">La sortie `MyCustomAvailableforReservation` est basée sur le paramètre de calcul dans les mesures personnalisées comme :</span><span class="sxs-lookup"><span data-stu-id="613e3-388">The `MyCustomAvailableforReservation` output is based on the calculation setting in the custom measurements as:</span></span>  
 <span data-ttu-id="613e3-389">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span><span class="sxs-lookup"><span data-stu-id="613e3-389">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span></span>

### <a name="posting-on-hand-changes"></a><span data-ttu-id="613e3-390">Publication des modifications en stock</span><span class="sxs-lookup"><span data-stu-id="613e3-390">Posting on-hand changes</span></span>

<span data-ttu-id="613e3-391">L’URL exacte sur laquelle l’événement sera publié dépendra de votre région géographique.</span><span class="sxs-lookup"><span data-stu-id="613e3-391">The exact URL that the event will be posted to will depend on your geographical region.</span></span> <span data-ttu-id="613e3-392">Il prendra la forme :</span><span class="sxs-lookup"><span data-stu-id="613e3-392">It will take the form:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand`

<span data-ttu-id="613e3-393">Une fois authentifiée, cette URL peut être utilisée avec la méthode HTTP `POST` pour envoyer des événements de modification en main au service.</span><span class="sxs-lookup"><span data-stu-id="613e3-393">When authenticated, this URL can be used along with the HTTP `POST` method to send on-hand change events to the service.</span></span>

<span data-ttu-id="613e3-394">Un en-tête spécial est utilisé pour communiquer avec les services Dynamics 365 via des requêtes HTTP, indiquant l’ID d’environnement de l’instance Supply Chain Management à laquelle les données sont liées.</span><span class="sxs-lookup"><span data-stu-id="613e3-394">A special header is used for communicating with Dynamics 365 services through HTTP requests, denoting the environment ID of the Supply Chain Management instance the data is linked to.</span></span> <span data-ttu-id="613e3-395">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="613e3-395">For example:</span></span>

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a><span data-ttu-id="613e3-396">Exemple de requête de publication de modifications en main 1</span><span class="sxs-lookup"><span data-stu-id="613e3-396">Posting on-hand changes query example 1</span></span>

<span data-ttu-id="613e3-397">Cet exemple montre un scénario dans lequel vous allez configurer la configuration de dimension dans Power Apps.</span><span class="sxs-lookup"><span data-stu-id="613e3-397">This example shows a scenario where you will set up the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="613e3-398">Utilisez la requête suivante pour configurer le mappage de dimension dans Power Apps :</span><span class="sxs-lookup"><span data-stu-id="613e3-398">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="613e3-399">Vous pouvez maintenant spécifier la `dimensionDataSource` et utilisez des dimensions personnalisées dans vos requêtes.</span><span class="sxs-lookup"><span data-stu-id="613e3-399">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="613e3-400">Le système convertira automatiquement les dimensions personnalisées en dimensions de base.</span><span class="sxs-lookup"><span data-stu-id="613e3-400">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="posting-on-hand-changes-query-example-2"></a><span data-ttu-id="613e3-401">Exemple de requête de publication de modifications en main 2</span><span class="sxs-lookup"><span data-stu-id="613e3-401">Posting on-hand changes query example 2</span></span>

<span data-ttu-id="613e3-402">Cet exemple montre un scénario dans lequel aucun mappage n’est configuré pour la configuration de dimension dans Power Apps, donc la publication doit également utiliser les dimensions de base.</span><span class="sxs-lookup"><span data-stu-id="613e3-402">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="613e3-403">Toutes les dimensions doivent être des dimensions de base lorsque le champ `dimensionDataSource` est nul, vide ou espace.</span><span class="sxs-lookup"><span data-stu-id="613e3-403">All dimensions must be base dimensions when the `dimensionDataSource` field is null, empty, or whitespace.</span></span>

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

#### <a name="json-document-field-properties"></a><span data-ttu-id="613e3-404">Propriétés du champs de documents JSON</span><span class="sxs-lookup"><span data-stu-id="613e3-404">JSON document field properties</span></span>

<span data-ttu-id="613e3-405">Les champs des exemples de requête JSON fournis précédemment ont les propriétés répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="613e3-405">The fields from the JSON query examples provided previously have the properties listed in the following table.</span></span>

| <span data-ttu-id="613e3-406">ID champ</span><span class="sxs-lookup"><span data-stu-id="613e3-406">Field ID</span></span> | <span data-ttu-id="613e3-407">Description</span><span class="sxs-lookup"><span data-stu-id="613e3-407">Description</span></span> |
|---|---|
| `id` | <span data-ttu-id="613e3-408">Un ID unique pour l’événement de modification spécifique.</span><span class="sxs-lookup"><span data-stu-id="613e3-408">A unique ID for the specific change event.</span></span> <span data-ttu-id="613e3-409">Cet ID est utilisé pour garantir qu’en cas d’échec de la communication avec le service pendant la comptabilisation, la soumission à nouveau de l’événement n’entraînerait pas le comptage du même événement deux fois dans le système.</span><span class="sxs-lookup"><span data-stu-id="613e3-409">This ID is used to ensure that if communication with the service fails during posting, resubmitting the event would not result in the same event being counted twice in the system.</span></span> |
| `organizationId` | <span data-ttu-id="613e3-410">L’identificateur de l’organisation liée à l’événement.</span><span class="sxs-lookup"><span data-stu-id="613e3-410">The identifier of the organization linked to the event.</span></span> <span data-ttu-id="613e3-411">Cela correspond aux organisations de gestion de Supply Chain Management ou aux ID de zone de données.</span><span class="sxs-lookup"><span data-stu-id="613e3-411">This maps to Supply Chain Management organizations or data area IDs.</span></span> |
| `productId` | <span data-ttu-id="613e3-412">Identificateur du produit en question.</span><span class="sxs-lookup"><span data-stu-id="613e3-412">The identifier of the product in question.</span></span> |
| `quantity` | <span data-ttu-id="613e3-413">La quantité dont le stock doit être changé.</span><span class="sxs-lookup"><span data-stu-id="613e3-413">The quantity by which the on-hand needs to be changed.</span></span> <span data-ttu-id="613e3-414">Si, par exemple, 10 nouveaux bagels étaient ajoutés à une étagère, cette valeur serait de 10.</span><span class="sxs-lookup"><span data-stu-id="613e3-414">If, for instance, 10 new bagels were added to a shelf, this value would be 10.</span></span> <span data-ttu-id="613e3-415">Si 3 bagels étaient ensuite retirés de l’étagère ou vendus, cette valeur serait de -3.</span><span class="sxs-lookup"><span data-stu-id="613e3-415">If 3 bagels were then removed from the shelf or sold, this value would be -3.</span></span> |
| `dimensionDataSource` | <span data-ttu-id="613e3-416">Source de données des dimensions utilisées dans l’événement et la requête de modification de publication.</span><span class="sxs-lookup"><span data-stu-id="613e3-416">The data source of the dimensions used in the posting change event and query.</span></span> <span data-ttu-id="613e3-417">Si vous spécifiez la source de données, vous pouvez utiliser les dimensions personnalisées de la source de données spécifiée.</span><span class="sxs-lookup"><span data-stu-id="613e3-417">If you specify the data source, you can use the custom dimensions from the specified data source.</span></span> <span data-ttu-id="613e3-418">Avec la configuration des dimensions, la visibilité du stock peut mapper les dimensions personnalisées aux dimensions générales par défaut.</span><span class="sxs-lookup"><span data-stu-id="613e3-418">With the dimension configuration, Inventory Visibility can map the custom dimensions to the general default dimensions.</span></span> <span data-ttu-id="613e3-419">Si la `dimensionDataSource` n’est pas spécifié, vous ne pouvez utiliser que les dimensions générales par défaut dans vos requêtes.</span><span class="sxs-lookup"><span data-stu-id="613e3-419">If the `dimensionDataSource` is not specified, you can only use the general default dimensions in your queries.</span></span>   |
| `dimensions` | <span data-ttu-id="613e3-420">Un sac dynamique de paires clé/valeur.</span><span class="sxs-lookup"><span data-stu-id="613e3-420">A dynamic bag of key/value pairs.</span></span> <span data-ttu-id="613e3-421">Celles-ci correspondront à certaines des dimensions de Supply Chain Management, mais vous pouvez également ajouter des dimensions personnalisées (comme *Source*) qui peut indiquer si l’événement provenait de Supply Chain Management ou d’un système externe.</span><span class="sxs-lookup"><span data-stu-id="613e3-421">These will map to some of the dimensions in Supply Chain Management, but you could also add custom dimensions (like *Source*) that may denote if the event was coming from Supply Chain Management or an external system.</span></span> |

### <a name="querying-current-on-hand"></a><span data-ttu-id="613e3-422">Interrogation actuellement disponible</span><span class="sxs-lookup"><span data-stu-id="613e3-422">Querying current on-hand</span></span>

<span data-ttu-id="613e3-423">Le point de terminaison pour interroger le stock actuel aura une URL similaire :</span><span class="sxs-lookup"><span data-stu-id="613e3-423">The endpoint for querying the current on-hand will have a similar URL:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

<span data-ttu-id="613e3-424">Il sera interrogé avec la méthode HTTP `POST`.</span><span class="sxs-lookup"><span data-stu-id="613e3-424">It will be queried with the HTTP `POST` method.</span></span>

#### <a name="current-on-hand-query-example-1"></a><span data-ttu-id="613e3-425">Exemple de requête en main actuel 1</span><span class="sxs-lookup"><span data-stu-id="613e3-425">Current on-hand query example 1</span></span>

<span data-ttu-id="613e3-426">Cet exemple montre un scénario dans lequel vous disposez déjà d’une configuration de dimension terminée dans Power Apps.</span><span class="sxs-lookup"><span data-stu-id="613e3-426">This example shows a scenario where you have already completed the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="613e3-427">Utilisez la requête suivante pour configurer le mappage de dimension dans Power Apps :</span><span class="sxs-lookup"><span data-stu-id="613e3-427">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="613e3-428">Vous pouvez maintenant spécifier la `dimensionDataSource` et utilisez des dimensions personnalisées dans vos requêtes.</span><span class="sxs-lookup"><span data-stu-id="613e3-428">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="613e3-429">Le système convertira automatiquement les dimensions personnalisées en dimensions de base.</span><span class="sxs-lookup"><span data-stu-id="613e3-429">The system will automatically convert custom dimensions to base dimensions.</span></span> <span data-ttu-id="613e3-430">Vous pouvez spécifier la `DimensionDataSource` dans `filters` et spécifiez des dimensions personnalisées dans `filters` et `groupByValues`.</span><span class="sxs-lookup"><span data-stu-id="613e3-430">You can specify the `DimensionDataSource` in `filters` and specify custom dimensions in both `filters` and `groupByValues`.</span></span> <span data-ttu-id="613e3-431">Le système convertira automatiquement les dimensions personnalisées en dimensions de base.</span><span class="sxs-lookup"><span data-stu-id="613e3-431">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="current-on-hand-query-example-2"></a><span data-ttu-id="613e3-432">Exemple de requête en main actuel 2</span><span class="sxs-lookup"><span data-stu-id="613e3-432">Current on-hand query example 2</span></span>

<span data-ttu-id="613e3-433">Cet exemple montre un scénario dans lequel aucun mappage n’est configuré pour la configuration de dimension dans Power Apps, donc la publication doit également utiliser les dimensions de base.</span><span class="sxs-lookup"><span data-stu-id="613e3-433">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="613e3-434">Toutes les dimensions doivent être des dimensions de base lorsque le champ `dimensionDataSource`, sous `filters`, est nul, vide ou espace.</span><span class="sxs-lookup"><span data-stu-id="613e3-434">All dimensions must be base dimensions when the `dimensionDataSource` field, under `filters` is null, empty, or whitespace.</span></span>

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

#### <a name="example-return-result"></a><span data-ttu-id="613e3-435">Exemple de résultat de retour</span><span class="sxs-lookup"><span data-stu-id="613e3-435">Example return result</span></span>

<span data-ttu-id="613e3-436">Les requêtes présentées dans les exemples précédents peuvent renvoyer un résultat comme celui-ci.</span><span class="sxs-lookup"><span data-stu-id="613e3-436">The queries shown in the previous examples could return a result like this.</span></span>

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

<span data-ttu-id="613e3-437">Notez que les champs de quantités sont structurés comme un dictionnaire de mesures et de leurs valeurs associées.</span><span class="sxs-lookup"><span data-stu-id="613e3-437">Note that the quantities fields are structured as a dictionary of measures and their associated values.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
