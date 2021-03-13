---
title: Configurer l'espace de travail mobile Gestion des actifs
description: Cette rubrique décrit comment configurer Microsoft Dynamics 365 Supply Chain Management et l'application mobile Finance and Operations (Dynamics 365) pour exécuter un espace de travail mobile Gestion des actifs que les collaborateurs peuvent utiliser pour effectuer des tâches de gestion des actifs.
author: johanhoffmann
manager: tfehr
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-22
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 9c2410c50b5d289792e2cc364674e1e093653590
ms.sourcegitcommit: 995c678b4715be267f1f97148902a6b3dde3bcab
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/20/2021
ms.locfileid: "5033207"
---
# <a name="set-up-the-asset-management-mobile-workspace"></a><span data-ttu-id="1ded7-103">Configurer l'espace de travail mobile Gestion des actifs</span><span class="sxs-lookup"><span data-stu-id="1ded7-103">Set up the Asset management mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1ded7-104">Cette rubrique décrit comment configurer Microsoft Dynamics 365 Supply Chain Management et l'application mobile Finance and Operations (Dynamics 365) pour exécuter un espace de travail mobile **Gestion des actifs** que les collaborateurs peuvent utiliser pour effectuer des tâches de gestion des actifs.</span><span class="sxs-lookup"><span data-stu-id="1ded7-104">This topic describes how to set up Microsoft Dynamics 365 Supply Chain Management and the Finance and Operations (Dynamics 365) mobile app to run an **Asset management** mobile workspace that workers can use to perform asset management tasks.</span></span>

## <a name="set-up-maintenance-worker-users-in-supply-chain-management"></a><span data-ttu-id="1ded7-105">Configurer les utilisateurs des agents de maintenance dans Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="1ded7-105">Set up maintenance worker users in Supply Chain Management</span></span>

<span data-ttu-id="1ded7-106">Pour chaque utilisateur nécessitant un accès à l'espace de travail mobile **Gestion des actifs**, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="1ded7-106">For each user that requires access to the **Asset management** mobile workspace, follow these steps.</span></span>

1. <span data-ttu-id="1ded7-107">Dans Supply Chain Management, accédez à **Ressources humaines \> Collaborateurs** et assurez-vous qu'il existe un enregistrement de collaborateur pour l'utilisateur que vous souhaitez configurer.</span><span class="sxs-lookup"><span data-stu-id="1ded7-107">In Supply Chain Management, go to **Human resources \> Workers**, and make sure that a worker record exists for the user that you want to set up.</span></span> <span data-ttu-id="1ded7-108">Créez un enregistrement de collaborateur selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="1ded7-108">Create a new worker record as required.</span></span>
1. <span data-ttu-id="1ded7-109">Accédez à **Gestion des actifs \> Configuration \> Collaborateurs \> Collaborateurs** et assurez-vous que l'enregistrement de collaborateur que vous avez identifié (ou créé) à l'étape précédente est associé à un enregistrement d'agent de maintenance.</span><span class="sxs-lookup"><span data-stu-id="1ded7-109">Go to **Asset management \> Setup \> Workers \> Workers**, and make sure that the worker record that you identified (or created) in the previous step is mapped to a maintenance worker record.</span></span> <span data-ttu-id="1ded7-110">Créez un enregistrement d'agent de maintenance selon vos besoins et définissez le champ **Collaborateur** sur l'enregistrement de collaborateur de l'étape précédente.</span><span class="sxs-lookup"><span data-stu-id="1ded7-110">Create a new maintenance worker record as required, and set the **Worker** field to the worker record from the previous step.</span></span>
1. <span data-ttu-id="1ded7-111">Accédez à **Gestion des actifs \> Configuration \> Collaborateurs \> Groupes d'agents de maintenance** et assurez-vous que l'enregistrement d'agent de maintenance que vous avez identifié (ou créé) à l'étape précédente appartient à un groupe d'agents de maintenance.</span><span class="sxs-lookup"><span data-stu-id="1ded7-111">Go to **Asset management \> Setup \> Workers \> Maintenance worker groups**, and make sure that the maintenance worker record that you identified (or created) in the previous step belongs to a maintenance worker group.</span></span>
1. <span data-ttu-id="1ded7-112">Accédez à **Administration système \> Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="1ded7-112">Go to **System administration \> Users**.</span></span>
1. <span data-ttu-id="1ded7-113">Sélectionnez l'utilisateur pertinent dans la grille.</span><span class="sxs-lookup"><span data-stu-id="1ded7-113">Select the relevant user in the grid.</span></span>
1. <span data-ttu-id="1ded7-114">Dans le raccourci **Détails de l'utilisateur**, définissez le champ **Personne** sur le compte de collaborateur que vous souhaitez associer au compte d'utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="1ded7-114">On the **User Details** FastTab, set the **Person** field to the worker account that you want to associate with the current user account.</span></span> <span data-ttu-id="1ded7-115">Ce compte de collaborateur doit être l'enregistrement de collaborateur que vous avez identifié (ou créé) à l'étape 1 et associé à un enregistrement d'agent de maintenance à l'étape 2.</span><span class="sxs-lookup"><span data-stu-id="1ded7-115">This worker account should be the worker record that you identified (or created) in step 1 and mapped to a maintenance worker record in step 2.</span></span>

> [!NOTE]
> <span data-ttu-id="1ded7-116">Les autorisations et les rôles de sécurité de l'utilisateur s'appliquent aux fonctionnalités de l'espace de travail mobile **Gestion des actifs**, de la même manière qu'ils s'appliquent aux fonctionnalités de l'interface utilisateur de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="1ded7-116">User permissions and security roles apply to the features of the **Asset management** mobile workspace just as they apply to the features of the Supply Chain Management user interface.</span></span> <span data-ttu-id="1ded7-117">Par conséquent, chaque utilisateur que vous configurez pour accéder à l'espace de travail mobile **Gestion des actifs** doit avoir les rôles de sécurité nécessaires pour effectuer des opérations similaires directement dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="1ded7-117">Therefore, every user that you set up to access the **Asset management** mobile workspace must have the security roles that are required to perform similar operations directly in Supply Chain Management.</span></span>

## <a name="publish-the-asset-management-mobile-workspace"></a><span data-ttu-id="1ded7-118">Publier l'espace de travail mobile Gestion des actifs</span><span class="sxs-lookup"><span data-stu-id="1ded7-118">Publish the Asset management mobile workspace</span></span>

<span data-ttu-id="1ded7-119">Pour rendre les fonctionnalités de gestion des actifs disponibles dans l'application mobile Finance and Operations (Dynamics 365), vous devez publier l'espace de travail mobile **Gestion des actifs**.</span><span class="sxs-lookup"><span data-stu-id="1ded7-119">To make asset management features available in the Finance and Operations (Dynamics 365) mobile app, you must publish the **Asset management** mobile workspace.</span></span>

1. <span data-ttu-id="1ded7-120">Dans Supply Chain Management, sélectionnez le bouton **Paramètres** (le symbole d'engrenage dans le coin supérieur droit), puis sélectionnez **Application mobile** dans le menu.</span><span class="sxs-lookup"><span data-stu-id="1ded7-120">In Supply Chain Management, select the **Settings** button (the gear symbol in upper-right corner), and then select **Mobile app** on the menu.</span></span>
1. <span data-ttu-id="1ded7-121">Dans la boîte de dialogue **Gérer l'application mobile**, recherchez la vignette **Gestion des actifs**.</span><span class="sxs-lookup"><span data-stu-id="1ded7-121">In the **Manage mobile app** dialog box, find the **Asset Management** tile.</span></span> <span data-ttu-id="1ded7-122">Si elle contient le texte « Dans les métadonnées : non publiées », l'espace de travail n'a pas encore été publié.</span><span class="sxs-lookup"><span data-stu-id="1ded7-122">If it contains the text "In metadata - not published," the workspace hasn't yet been published.</span></span> <span data-ttu-id="1ded7-123">Si elle contient le texte « Dans les métadonnées : publiées », l'espace de travail a déjà été publié et vous pouvez ignorer le reste de cette procédure.</span><span class="sxs-lookup"><span data-stu-id="1ded7-123">If it contains the text "In metadata - published," the workspace has already been published, and you can skip the rest of this procedure.</span></span>

    <span data-ttu-id="1ded7-124">![Boîte de dialogue Gérer l'application mobile](media/mobile-workspaces.png "Boîte de dialogue Gérer l'application mobile")</span><span class="sxs-lookup"><span data-stu-id="1ded7-124">![Manage mobile app dialog box](media/mobile-workspaces.png "Manage mobile app dialog box")</span></span>

1. <span data-ttu-id="1ded7-125">Sélectionnez la vignette **Gestion des actifs**, puis sélectionnez **Publier** dans la barre d'outils.</span><span class="sxs-lookup"><span data-stu-id="1ded7-125">Select the **Asset Management** tile, and then select **Publish** on the toolbar.</span></span> <span data-ttu-id="1ded7-126">Après quelques secondes, vous devriez recevoir une notification indiquant que la publication de l'espace de travail a réussi.</span><span class="sxs-lookup"><span data-stu-id="1ded7-126">After a few seconds, you should receive a notification that states that the workspace has been successfully published.</span></span> <span data-ttu-id="1ded7-127">En outre, le texte de la vignette doit être modifié en « Dans les métadonnées : publiées ».</span><span class="sxs-lookup"><span data-stu-id="1ded7-127">Additionally, the text on the tile should change to "In metadata - published."</span></span>

## <a name="install-and-set-up-the-finance-and-operations-dynamics-365-mobile-app"></a><span data-ttu-id="1ded7-128">Installer et configurer l'application mobile Finance and Operations (Dynamics 365)</span><span class="sxs-lookup"><span data-stu-id="1ded7-128">Install and set up the Finance and Operations (Dynamics 365) mobile app</span></span>

1. <span data-ttu-id="1ded7-129">Accédez à l'un des magasins d'applications suivants pour installer l'application **Microsoft Finance and Operations (Dynamics 365)** sur votre appareil mobile :</span><span class="sxs-lookup"><span data-stu-id="1ded7-129">Go to one of the following app stores to install the **Microsoft Finance and Operations (Dynamics 365)** app on your mobile device:</span></span>

    - [<span data-ttu-id="1ded7-130">Pour les appareils Google Android</span><span class="sxs-lookup"><span data-stu-id="1ded7-130">For Google Android devices</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
    - [<span data-ttu-id="1ded7-131">Pour les appareils Apple iOS</span><span class="sxs-lookup"><span data-stu-id="1ded7-131">For Apple iOS devices</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

1. <span data-ttu-id="1ded7-132">Ouvrez l'application Finance and Operations (Dynamics 365).</span><span class="sxs-lookup"><span data-stu-id="1ded7-132">Open the Finance and Operations (Dynamics 365) app.</span></span> <span data-ttu-id="1ded7-133">La page de connexion doit apparaître.</span><span class="sxs-lookup"><span data-stu-id="1ded7-133">The sign-in page should appear.</span></span> <span data-ttu-id="1ded7-134">Dans le champ **Se connecter**, entrez l'URL de Supply Chain Management ou sélectionnez une URL récente dans la liste **Environnements récents**, puis appuyez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="1ded7-134">In the **Sign in** field, enter your Supply Chain Management URL, or select a recent URL in the **Recent environments** list, and then tap **Connect**.</span></span>

    <span data-ttu-id="1ded7-135">![Page de connexion](media/mobile-app-sign-in.png "Page de connexion")</span><span class="sxs-lookup"><span data-stu-id="1ded7-135">![Sign-in page](media/mobile-app-sign-in.png "Sign-in page")</span></span>

1. <span data-ttu-id="1ded7-136">Si vous êtes invité à confirmer la connexion, cochez la case **Je comprends**, puis appuyez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="1ded7-136">If you're prompted to confirm the connection, select the **I understand** check box, and then tap **Connect**.</span></span>
1. <span data-ttu-id="1ded7-137">Sur la page **Sélectionner un compte**, utilisez votre compte Microsoft pour vous connecter à l'application mobile.</span><span class="sxs-lookup"><span data-stu-id="1ded7-137">On the **Pick an account** page, use your Microsoft account to sign in to the mobile application.</span></span>

    <span data-ttu-id="1ded7-138">La page **Espaces de travail** apparaît.</span><span class="sxs-lookup"><span data-stu-id="1ded7-138">The **Workspaces** page appears.</span></span> <span data-ttu-id="1ded7-139">Elle répertorie tous les espaces de travail mobiles qui ont été publiés par votre instance de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="1ded7-139">It lists every mobile workspace that has been published by your Supply Chain Management instance.</span></span>

    <span data-ttu-id="1ded7-140">![Liste des espaces de travail](media/mobile-app-workspaces.png "Liste des espaces de travail")</span><span class="sxs-lookup"><span data-stu-id="1ded7-140">![List of workspaces](media/mobile-app-workspaces.png "List of workspaces")</span></span>

1. <span data-ttu-id="1ded7-141">Si vous devez changer l'entité juridique (société), appuyez sur le bouton Menu (parfois appelé hamburger ou bouton hamburger) dans le coin supérieur gauche, puis appuyez sur **Changer de société**.</span><span class="sxs-lookup"><span data-stu-id="1ded7-141">If you must change the legal entity (company), tap the Menu button (sometimes referred to as the hamburger or the hamburger button) in the upper-left corner, and then tap **Change company**.</span></span>

    <span data-ttu-id="1ded7-142">![Changement de l'entité juridique](media/mobile-app-change-comp.png "Changement de l'entité juridique")</span><span class="sxs-lookup"><span data-stu-id="1ded7-142">![Changing the legal entity](media/mobile-app-change-comp.png "Changing the legal entity")</span></span>

1. <span data-ttu-id="1ded7-143">Sur la page **Espaces de travail**, sélectionnez l'espace de travail que vous souhaitez utiliser pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="1ded7-143">On the **Workspaces** page, select the workspace that you want to work with to open it.</span></span>

    <span data-ttu-id="1ded7-144">![Espace de travail mobile pour la gestion des actifs](media/mobile-app-asset-workspace.png "Espace de travail mobile pour la gestion des actifs")</span><span class="sxs-lookup"><span data-stu-id="1ded7-144">![Asset management mobile workspace](media/mobile-app-asset-workspace.png "Asset management mobile workspace")</span></span>

## <a name="work-with-the-asset-management-mobile-workspace"></a><span data-ttu-id="1ded7-145">Utiliser l'espace de travail mobile Gestion des actifs</span><span class="sxs-lookup"><span data-stu-id="1ded7-145">Work with the Asset management mobile workspace</span></span>

<span data-ttu-id="1ded7-146">Pour plus d'informations sur l'utilisation de l'espace de travail mobile **Gestion des actifs**, voir [Utiliser l'espace de travail mobile Gestion des actifs](asset-management-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="1ded7-146">For more information about how to work with the **Asset management** mobile workspace, see [Use the Asset management mobile workspace](asset-management-mobile-workspace.md).</span></span>

<span data-ttu-id="1ded7-147">Pour plus d'informations sur l'application mobile Finance and Operations (Dynamics 365), voir la [Page d'accueil de l'application mobile](../../fin-ops-core/dev-itpro/mobile-apps/Mobile-app-home-page.md).</span><span class="sxs-lookup"><span data-stu-id="1ded7-147">For more information about the Finance and Operations (Dynamics 365) mobile app, see the [Mobile app home page](../../fin-ops-core/dev-itpro/mobile-apps/Mobile-app-home-page.md).</span></span>
