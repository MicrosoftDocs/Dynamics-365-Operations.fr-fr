---
title: Configurer des ressources Azure pour l’intelligence IoT
description: Cette rubrique explique comment créer et configurer les ressources Microsoft Azure dont vous avez besoin pour l’intelligence IoT.
author: ''
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: ''
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ea1083a65efb25699b9237c72c081f50e1fb476c
ms.sourcegitcommit: 5bb36b74935ffe140367fd6ecf956b4857ad12e5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/14/2020
ms.locfileid: "3802771"
---
# <a name="set-up-azure-resources-for-iot-intelligence"></a><span data-ttu-id="9d837-103">Configurer des ressources Azure pour l’intelligence IoT</span><span class="sxs-lookup"><span data-stu-id="9d837-103">Set up Azure resources for IoT Intelligence</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9d837-104">Cette rubrique explique comment créer et configurer les ressources Microsoft Azure dont vous avez besoin pour l’intelligence IoT.</span><span class="sxs-lookup"><span data-stu-id="9d837-104">This topic explains how to create and configure the Microsoft Azure resources that you require for IoT Intelligence.</span></span>

## <a name="create-azure-resources"></a><span data-ttu-id="9d837-105">Créer des ressources Azure</span><span class="sxs-lookup"><span data-stu-id="9d837-105">Create Azure resources</span></span>

<span data-ttu-id="9d837-106">Suivez ces étapes pour créer un hub IoT, un cache Redis et un coffre de clés accessibles par Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9d837-106">Follow these steps to create an IoT hub, a Redis cache, and a key vault that can be accessed by Microsoft Dynamics 365 Supply Chain Management.</span></span>

### <a name="verify-that-the-microsoft-dynamics-erp-microservices-first-party-app-id-is-in-your-tenant"></a><span data-ttu-id="9d837-107">Vérifiez que l’ID d’application pour l’application propriétaire Microservices ERP Microsoft Dynamics est dans votre client</span><span class="sxs-lookup"><span data-stu-id="9d837-107">Verify that the Microsoft Dynamics ERP Microservices first-party app ID is in your tenant</span></span>

<span data-ttu-id="9d837-108">Pour vérifier que l’ID d’application pour l’application propriétaire Microservices ERP Microsoft Dynamics est dans votre client, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="9d837-108">To verify that the app ID for the Microsoft Dynamics ERP Microservices first-party app is in your tenant, follow these steps.</span></span>

1. <span data-ttu-id="9d837-109">Connectez-vous au portail Azure à l’adresse suivante : <https://portal.azure.com>.</span><span class="sxs-lookup"><span data-stu-id="9d837-109">Sign in to the Azure portal at <https://portal.azure.com>.</span></span>
2. <span data-ttu-id="9d837-110">Atteindre **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="9d837-110">Go to **Azure Active Directory**.</span></span>
3. <span data-ttu-id="9d837-111">Accédez à **Applications d’entreprise**.</span><span class="sxs-lookup"><span data-stu-id="9d837-111">Go to **Enterprise applications**.</span></span>
4. <span data-ttu-id="9d837-112">Dans le champ **Type d’application**, sélectionnez **Applications Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="9d837-112">In the **Application type** field, select **Microsoft applications**.</span></span>
5. <span data-ttu-id="9d837-113">Dans le champ de recherche, entrez **Microservices ERP Microsoft Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="9d837-113">In the search field, enter **Microsoft Dynamics ERP Microservices**.</span></span>
6. <span data-ttu-id="9d837-114">Vérifiez que **Microservices ERP Microsoft Dynamics** est bien dans la liste.</span><span class="sxs-lookup"><span data-stu-id="9d837-114">Verify that **Microsoft Dynamics ERP Microservices** is in the list.</span></span> <span data-ttu-id="9d837-115">D’autres applications ont des noms similaires.</span><span class="sxs-lookup"><span data-stu-id="9d837-115">Other applications have similar names.</span></span> <span data-ttu-id="9d837-116">Par conséquent, veillez à disposer de l’application correcte.</span><span class="sxs-lookup"><span data-stu-id="9d837-116">Therefore, make sure that you find the correct application.</span></span> <span data-ttu-id="9d837-117">L’ID de l’application est **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="9d837-117">The app ID is **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span>

    <span data-ttu-id="9d837-118">Si l’application ne figure pas dans la liste, vous devez l’ajouter à votre client :</span><span class="sxs-lookup"><span data-stu-id="9d837-118">If the application isn't in the list, you must add it to your tenant:</span></span>

    1. <span data-ttu-id="9d837-119">Dans le portail Azure, dans la barre d’outils, sélectionnez le bouton pour ouvrir Azure Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="9d837-119">In the Azure portal, on the toolbar, select the button to open Azure Cloud Shell.</span></span>
    2. <span data-ttu-id="9d837-120">Exécutez la commande **Module d’installation AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="9d837-120">Run the command **Install-Module AzureAD**.</span></span> <span data-ttu-id="9d837-121">Entrer **O** pour installer le module.</span><span class="sxs-lookup"><span data-stu-id="9d837-121">Enter **Y** to install the module.</span></span>
    3. <span data-ttu-id="9d837-122">Exécutez la commande **Get-InstalledModule -Name "AzureAD"** pour vérifier que le module est installé.</span><span class="sxs-lookup"><span data-stu-id="9d837-122">Run the command **Get-InstalledModule -Name "AzureAD"** to verify that the module is installed.</span></span>
    4. <span data-ttu-id="9d837-123">Exécutez la commande **Connect-AzureAD -Confirm** pour exécuter l’authentification.</span><span class="sxs-lookup"><span data-stu-id="9d837-123">Run the command **Connect-AzureAD -Confirm** to run the authentication.</span></span>
    5. <span data-ttu-id="9d837-124">Exécutez la commande **New-AzureADServicePrincipal -AppId 0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="9d837-124">Run the command **New-AzureADServicePrincipal -AppId 0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span>

    <span data-ttu-id="9d837-125">Vous pouvez maintenant répéter les étapes 1 à 6 pour vérifier que l’ID d’application se trouve dans votre client.</span><span class="sxs-lookup"><span data-stu-id="9d837-125">You can now repeat steps 1 through 6 to verify that the app ID is in your tenant.</span></span>

### <a name="create-a-key-vault-resource"></a><span data-ttu-id="9d837-126">Créer une ressource de coffre de clés</span><span class="sxs-lookup"><span data-stu-id="9d837-126">Create a key vault resource</span></span>

<span data-ttu-id="9d837-127">Pour créer une ressource de coffre de clés, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="9d837-127">To create a key vault resource, follow these steps.</span></span>

1. <span data-ttu-id="9d837-128">Dans le portail Azure, créez ou accédez à un groupe de ressources.</span><span class="sxs-lookup"><span data-stu-id="9d837-128">In the Azure portal, create or go to a resource group.</span></span>
2. <span data-ttu-id="9d837-129">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="9d837-129">Select **Add**.</span></span>
3. <span data-ttu-id="9d837-130">Sur la page **Nouveau**, entrez **Coffre de clés** dans le champ de recherche.</span><span class="sxs-lookup"><span data-stu-id="9d837-130">On the **New** page, in the search field, enter **Key vault**.</span></span> <span data-ttu-id="9d837-131">Ensuite, sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="9d837-131">Then select **Create**.</span></span>
4. <span data-ttu-id="9d837-132">Sur la page **Créer un coffre de clés**, entrez un nom dans le champ **Nom du coffre de clés**.</span><span class="sxs-lookup"><span data-stu-id="9d837-132">On the **Create key vault** page, in the **Key vault name** field, enter a name.</span></span>
5. <span data-ttu-id="9d837-133">Vérifiez les valeurs par défaut, puis sélectionnez **Vérifier + créer**.</span><span class="sxs-lookup"><span data-stu-id="9d837-133">Review the default values, and then select **Review + create**.</span></span>
6. <span data-ttu-id="9d837-134">Sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="9d837-134">Select **Create**.</span></span>

<span data-ttu-id="9d837-135">Le coffre de clés est créé en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="9d837-135">The key vault is created in the background.</span></span>

### <a name="create-an-iot-hub-resource"></a><span data-ttu-id="9d837-136">Créer une ressource hub IoT</span><span class="sxs-lookup"><span data-stu-id="9d837-136">Create an IoT hub resource</span></span>

<span data-ttu-id="9d837-137">Pour créer une ressource hub IoT, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="9d837-137">To create an IoT hub resource, follow these steps.</span></span>

1. <span data-ttu-id="9d837-138">Créez ou accédez à un groupe de ressources.</span><span class="sxs-lookup"><span data-stu-id="9d837-138">Create or go to a resource group.</span></span>
2. <span data-ttu-id="9d837-139">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="9d837-139">Select **Add**.</span></span>
3. <span data-ttu-id="9d837-140">Sur la page **Nouveau**, entrez **Hub IoT** dans le champ de recherche.</span><span class="sxs-lookup"><span data-stu-id="9d837-140">On the **New** page, in the search field, enter **Iot Hub**.</span></span> <span data-ttu-id="9d837-141">Ensuite, sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="9d837-141">Then select **Create**.</span></span>
4. <span data-ttu-id="9d837-142">Entrez un nom dans le champ **Nom du hub IoT**.</span><span class="sxs-lookup"><span data-stu-id="9d837-142">In the **IoT hub name** field, enter a name.</span></span>
5. <span data-ttu-id="9d837-143">Vérifiez les valeurs par défaut, puis sélectionnez **Vérifier + créer**.</span><span class="sxs-lookup"><span data-stu-id="9d837-143">Review the default values, and then select **Review + create**.</span></span>
6. <span data-ttu-id="9d837-144">Sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="9d837-144">Select **Create**.</span></span>

<span data-ttu-id="9d837-145">Le hub IoT est créé en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="9d837-145">The IoT hub is created in the background.</span></span>

> [!NOTE]
> <span data-ttu-id="9d837-146">Nous vous recommandons de créer une seule ressource hub IoT par environnement.</span><span class="sxs-lookup"><span data-stu-id="9d837-146">We recommend that you create only one IoT hub resource per environment.</span></span>

### <a name="create-a-redis-cache-resource"></a><span data-ttu-id="9d837-147">Créer une ressource de cache Redis</span><span class="sxs-lookup"><span data-stu-id="9d837-147">Create a Redis cache resource</span></span>

<span data-ttu-id="9d837-148">Pour créer une ressource de cache Redis, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="9d837-148">To create a Redis cache resource, follow these steps.</span></span>

1. <span data-ttu-id="9d837-149">Créez ou accédez à un groupe de ressources.</span><span class="sxs-lookup"><span data-stu-id="9d837-149">Create or go to a resource group.</span></span>
2. <span data-ttu-id="9d837-150">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="9d837-150">Select **Add**.</span></span>
3. <span data-ttu-id="9d837-151">Sur la page **Nouveau**, entrez **Cache Azure pour Redis** dans le champ de recherche.</span><span class="sxs-lookup"><span data-stu-id="9d837-151">On the **New** page, in the search field, enter **Azure Cache for Redis**.</span></span> <span data-ttu-id="9d837-152">Ensuite, sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="9d837-152">Then select **Create**.</span></span>
4. <span data-ttu-id="9d837-153">Entrez un nom dans le champ **Nom DNS**.</span><span class="sxs-lookup"><span data-stu-id="9d837-153">In the **DNS name** field, enter a name.</span></span>
5. <span data-ttu-id="9d837-154">Vérifiez les valeurs par défaut, puis sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="9d837-154">Review the default values, and then select **Create**.</span></span>

<span data-ttu-id="9d837-155">Le cache Redis est créé en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="9d837-155">The Redis cache is created in the background.</span></span>

> [!NOTE]
> <span data-ttu-id="9d837-156">Nous vous recommandons de créer un seul cache Redis par environnement.</span><span class="sxs-lookup"><span data-stu-id="9d837-156">We recommend that you create only one Redis cache per environment.</span></span>

<span data-ttu-id="9d837-157">Toutes les ressources sont maintenant créées.</span><span class="sxs-lookup"><span data-stu-id="9d837-157">All the resources have now been created.</span></span>

## <a name="configure-the-azure-resources"></a><span data-ttu-id="9d837-158">Configurer les ressources Azure</span><span class="sxs-lookup"><span data-stu-id="9d837-158">Configure the Azure resources</span></span>

### <a name="configure-the-iot-hub"></a><span data-ttu-id="9d837-159">Configurer le hub IoT</span><span class="sxs-lookup"><span data-stu-id="9d837-159">Configure the IoT hub</span></span>

<span data-ttu-id="9d837-160">Procédez comme suit pour configurer le hub IoT.</span><span class="sxs-lookup"><span data-stu-id="9d837-160">To configure the IoT hub, follow these steps.</span></span>

1. <span data-ttu-id="9d837-161">Dans vos ressources, sélectionnez la ressource hub IoT.</span><span class="sxs-lookup"><span data-stu-id="9d837-161">In your resources, select the IoT hub resource.</span></span>
2. <span data-ttu-id="9d837-162">Dans le volet de navigation de gauche, sélectionnez **Points de terminaison intégrés**.</span><span class="sxs-lookup"><span data-stu-id="9d837-162">In the left navigation pane, select **Built-in endpoints**.</span></span>
3. <span data-ttu-id="9d837-163">Collez les groupes de consommateurs suivants sous **Groupes de consommateurs**.</span><span class="sxs-lookup"><span data-stu-id="9d837-163">Under **Consumer groups**, paste the following consumer groups.</span></span> <span data-ttu-id="9d837-164">Ces groupes de consommateurs correspondent aux scénarios prêts à l’emploi.</span><span class="sxs-lookup"><span data-stu-id="9d837-164">These consumer groups correspond to the out-of-box scenarios.</span></span>

    + <span data-ttu-id="9d837-165">microsoft.dynamics.iotintelligence-1</span><span class="sxs-lookup"><span data-stu-id="9d837-165">microsoft.dynamics.iotintelligence-1</span></span>
    + <span data-ttu-id="9d837-166">microsoft.dynamics.iotintelligence-2</span><span class="sxs-lookup"><span data-stu-id="9d837-166">microsoft.dynamics.iotintelligence-2</span></span>
    + <span data-ttu-id="9d837-167">microsoft.dynamics.iotintelligence-3</span><span class="sxs-lookup"><span data-stu-id="9d837-167">microsoft.dynamics.iotintelligence-3</span></span>

### <a name="configure-the-key-vault"></a><span data-ttu-id="9d837-168">Configurer le coffre de clés</span><span class="sxs-lookup"><span data-stu-id="9d837-168">Configure the key vault</span></span>

<span data-ttu-id="9d837-169">Procédez comme suit pour configurer le coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="9d837-169">To configure the key vault, follow these steps.</span></span>

1. <span data-ttu-id="9d837-170">Sélectionnez la ressource de coffre de clés parmi vos ressources.</span><span class="sxs-lookup"><span data-stu-id="9d837-170">In your resources, select the key vault resource.</span></span>
2. <span data-ttu-id="9d837-171">Sélectionnez **Stratégies d’accès** dans le volet de navigation de gauche.</span><span class="sxs-lookup"><span data-stu-id="9d837-171">In the left navigation pane, select **Access policies**.</span></span>
3. <span data-ttu-id="9d837-172">Sélectionnez **Ajouter une stratégie d’accès**.</span><span class="sxs-lookup"><span data-stu-id="9d837-172">Select **Add an access policy**.</span></span>
4. <span data-ttu-id="9d837-173">Sur la page **Ajouter une stratégie d’accès**, dans le champ **Autorisations secrètes**, sélectionnez **Obtenir** et **Liste**.</span><span class="sxs-lookup"><span data-stu-id="9d837-173">On the **Add access policy** page, in the **Secret permissions** field, select **Get** and **List**.</span></span>
5. <span data-ttu-id="9d837-174">Cliquez dans le **Sélectionner le principal**.</span><span class="sxs-lookup"><span data-stu-id="9d837-174">Click in the **Select principal**.</span></span>
6. <span data-ttu-id="9d837-175">Dans la boîte de dialogue **Principal**, recherchez et sélectionnez **Microservices ERP Microsoft Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="9d837-175">In the **Principal** dialog box, search for and select **Microsoft Dynamics ERP Microservices**.</span></span> <span data-ttu-id="9d837-176">Cliquez ensuite sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="9d837-176">Then select **Select**.</span></span>
7. <span data-ttu-id="9d837-177">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="9d837-177">Select **Add**.</span></span>
8. <span data-ttu-id="9d837-178">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9d837-178">Select **Save**.</span></span>

<span data-ttu-id="9d837-179">L’application a désormais accès aux secrets du coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="9d837-179">The app now has access to the secrets in the key vault.</span></span>

### <a name="save-the-iot-hub-connection-string-secret"></a><span data-ttu-id="9d837-180">Enregistrer le secret de la chaîne de connexion du hub IoT</span><span class="sxs-lookup"><span data-stu-id="9d837-180">Save the IoT hub connection string secret</span></span>

<span data-ttu-id="9d837-181">Pour enregistrer le secret de la chaîne de connexion du hub IoT, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="9d837-181">To save the secret for the IoT hub connection string, follow these steps.</span></span>

1. <span data-ttu-id="9d837-182">Dans vos ressources, sélectionnez la ressource hub IoT.</span><span class="sxs-lookup"><span data-stu-id="9d837-182">In your resources, select the IoT hub resource.</span></span>
2. <span data-ttu-id="9d837-183">Dans le volet de navigation de gauche, sélectionnez **Points de terminaison intégrés**.</span><span class="sxs-lookup"><span data-stu-id="9d837-183">In the left navigation pane, select **Built-in endpoints**.</span></span>
3. <span data-ttu-id="9d837-184">Copiez la valeur dans le champ **Point de terminaison compatible avec Event Hub**.</span><span class="sxs-lookup"><span data-stu-id="9d837-184">Copy the value in the **Event Hub-compatible endpoint** field.</span></span>
4. <span data-ttu-id="9d837-185">Accédez à la ressource de coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="9d837-185">Go to the key vault resource.</span></span>
5. <span data-ttu-id="9d837-186">Dans le volet de navigation de gauche, sélectionnez **Secrets**.</span><span class="sxs-lookup"><span data-stu-id="9d837-186">In the left navigation pane, select **Secrets**.</span></span>
6. <span data-ttu-id="9d837-187">Sélectionnez **Générer/Importer**.</span><span class="sxs-lookup"><span data-stu-id="9d837-187">Select **Generate/Import**.</span></span>
7. <span data-ttu-id="9d837-188">Dans le champ **Nom**, entrez un nom.</span><span class="sxs-lookup"><span data-stu-id="9d837-188">In the **Name** field, enter a name.</span></span>
8. <span data-ttu-id="9d837-189">Dans le champ **Valeur**, collez la valeur de point de terminaison que vous avez copiée précédemment.</span><span class="sxs-lookup"><span data-stu-id="9d837-189">In the **Value** field, paste the endpoint value that you copied earlier.</span></span>
9. <span data-ttu-id="9d837-190">Sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="9d837-190">Select **Create**.</span></span>

### <a name="save-the-redis-cache-connection-string-secret"></a><span data-ttu-id="9d837-191">Enregistrer le secret de la chaîne de connexion du cache Redis</span><span class="sxs-lookup"><span data-stu-id="9d837-191">Save the Redis cache connection string secret</span></span>

<span data-ttu-id="9d837-192">Pour enregistrer le secret de la chaîne de connexion du cache Redis, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="9d837-192">To save the secret for the Redis cache connection string, follow these steps.</span></span>

1. <span data-ttu-id="9d837-193">Sélectionnez la ressource de cache Redis parmi vos ressources.</span><span class="sxs-lookup"><span data-stu-id="9d837-193">In your resources, select the Redis cache resource.</span></span>
2. <span data-ttu-id="9d837-194">Sélectionnez **Clés d’accès**.</span><span class="sxs-lookup"><span data-stu-id="9d837-194">Select **Access keys**.</span></span>
3. <span data-ttu-id="9d837-195">Copiez la valeur dans le champ **Chaîne de connexion principale**.</span><span class="sxs-lookup"><span data-stu-id="9d837-195">Copy the value in the **Primary connection string** field.</span></span>
4. <span data-ttu-id="9d837-196">Accédez à la ressource de coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="9d837-196">Go to the key vault resource.</span></span>
5. <span data-ttu-id="9d837-197">Dans le volet de navigation de gauche, sélectionnez **Secrets**.</span><span class="sxs-lookup"><span data-stu-id="9d837-197">In the left navigation pane, select **Secrets**.</span></span>
6. <span data-ttu-id="9d837-198">Sélectionnez **Générer/Importer**.</span><span class="sxs-lookup"><span data-stu-id="9d837-198">Select **Generate/Import**.</span></span>
7. <span data-ttu-id="9d837-199">Dans le champ **Nom**, entrez un nom.</span><span class="sxs-lookup"><span data-stu-id="9d837-199">In the **Name** field, enter a name.</span></span>
8. <span data-ttu-id="9d837-200">Dans le champ **Valeur**, collez la chaîne de connexion que vous avez copiée précédemment.</span><span class="sxs-lookup"><span data-stu-id="9d837-200">In the **Value** field, paste the connection string that you copied earlier.</span></span>
9. <span data-ttu-id="9d837-201">Sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="9d837-201">Select **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="9d837-202">Chaque fois que vous mettez à jour l’une des chaînes de connexion, vous devez également mettre à jour les valeurs secrètes.</span><span class="sxs-lookup"><span data-stu-id="9d837-202">Whenever you update one of the connection strings, you must also update the secret values.</span></span>

<span data-ttu-id="9d837-203">Vous avez maintenant terminé de provisionner les ressources Azure requises.</span><span class="sxs-lookup"><span data-stu-id="9d837-203">You've now finished provisioning the required Azure resources.</span></span> <span data-ttu-id="9d837-204">La prochaine étape consiste à [installer le complément Intelligence IoT dans Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="9d837-204">The next step is to [install the IoT Intelligence add-in in Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).</span></span>
