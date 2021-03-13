---
title: Prise en main de l'administration du service du module complémentaire de facturation électronique
description: Cette rubrique explique comment démarrer avec le module complémentaire de facturation électronique.
author: gionoder
manager: AnnBe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 111ec65aa826795125d4a9ce835f72e1a0f41b7b
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104378"
---
# <a name="get-started-with-electronic-invoicing-add-on-service-administration"></a><span data-ttu-id="97712-103">Prise en main de l'administration du service du module complémentaire de facturation électronique</span><span class="sxs-lookup"><span data-stu-id="97712-103">Get started with Electronic invoicing add-on service administration</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="97712-104">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="97712-104">Prerequisites</span></span>

<span data-ttu-id="97712-105">Avant d’effectuer les étapes de cette rubrique, les conditions préalables suivantes doivent être remplies :</span><span class="sxs-lookup"><span data-stu-id="97712-105">Before you complete the procedures in this topic, the following prerequisites must be in place:</span></span>

- <span data-ttu-id="97712-106">Vous devez avoir accès à votre compte Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="97712-106">You must have access to your Microsoft Dynamics Lifecycle Services (LCS) account.</span></span>
- <span data-ttu-id="97712-107">Vous devez avoir un projet LCS qui inclut la version 10.0.13 ou ultérieure de Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="97712-107">You must have an LCS project that includes version 10.0.13 or later of Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="97712-108">En outre, ces applications doivent être déployées dans l'une des zones géographiques Azure suivantes :</span><span class="sxs-lookup"><span data-stu-id="97712-108">Additionally, these apps must be deployed in one of the following Azure geographies:</span></span>

    - <span data-ttu-id="97712-109">Est des États-Unis</span><span class="sxs-lookup"><span data-stu-id="97712-109">East US</span></span>
    - <span data-ttu-id="97712-110">Ouest des États-Unis</span><span class="sxs-lookup"><span data-stu-id="97712-110">West US</span></span>
    - <span data-ttu-id="97712-111">Nord de l'UE</span><span class="sxs-lookup"><span data-stu-id="97712-111">North EU</span></span>
    - <span data-ttu-id="97712-112">Ouest de l'UE</span><span class="sxs-lookup"><span data-stu-id="97712-112">West EU</span></span>

- <span data-ttu-id="97712-113">Vous devez avoir accès à votre compte Dynamics 365 Regulatory Configuration Services (RCS).</span><span class="sxs-lookup"><span data-stu-id="97712-113">You must have access to your Dynamics 365 Regulatory Configuration Services (RCS) account.</span></span>
- <span data-ttu-id="97712-114">Vous devez activer la fonctionnalité de globalisation pour votre compte RCS via le module Gestion des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="97712-114">You must activate the Globalization feature for your RCS account in Feature management.</span></span> <span data-ttu-id="97712-115">Pour plus d’informations, voir [Regulatory Configuration Services (RCS) - Fonctionnalités de globalisation](rcs-globalization-feature.md).</span><span class="sxs-lookup"><span data-stu-id="97712-115">For more information, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md).</span></span>
- <span data-ttu-id="97712-116">Vous devez créer un coffre de clés et d’un compte de stockage dans Azure.</span><span class="sxs-lookup"><span data-stu-id="97712-116">You must create a key vault and a storage account in Azure.</span></span> <span data-ttu-id="97712-117">Pour plus d’informations, voir [Créer un compte de stockage Azure et un coffre de clés](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="97712-117">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

## <a name="install-the-add-on-for-microservices-in-lifecycle-services"></a><span data-ttu-id="97712-118">Installer le module complémentaire pour les microservices dans Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="97712-118">Install the add-on for microservices in Lifecycle Services</span></span>

1. <span data-ttu-id="97712-119">Connectez-vous à votre compte LCS.</span><span class="sxs-lookup"><span data-stu-id="97712-119">Sign in to your LCS account.</span></span>
2. <span data-ttu-id="97712-120">Sélectionnez la vignette **Gestion des fonctionnalités d'aperçu**.</span><span class="sxs-lookup"><span data-stu-id="97712-120">Select the **Preview feature management** tile.</span></span>
3. <span data-ttu-id="97712-121">Dans la section **Fonctionnalités de version préliminaire**, sélectionnez **Service de facturation électronique**.</span><span class="sxs-lookup"><span data-stu-id="97712-121">In the **Public Preview Features** section, select **e-Invoicing service**.</span></span>
4. <span data-ttu-id="97712-122">Veillez à ce que l'option **Fonctionnalité de version préliminaire activée** soit définie sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="97712-122">Make sure that the **Preview feature enabled** option is set to **Yes**.</span></span>

## <a name="set-up-the-parameters-for-rcs-integration-with-the-electronic-invoicing-add-on"></a><span data-ttu-id="97712-123">Définir les paramètres pour l’intégration RCS avec le module complémentaire de facturation électronique</span><span class="sxs-lookup"><span data-stu-id="97712-123">Set up the parameters for RCS integration with the Electronic invoicing add-on</span></span>

1. <span data-ttu-id="97712-124">Connectez-vous à votre compte RCS.</span><span class="sxs-lookup"><span data-stu-id="97712-124">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="97712-125">Dans l’espace de travail **Génération d’états électroniques**, dans la section **Liens connexes**, sélectionnez **Paramètres de la gestion des états électroniques**.</span><span class="sxs-lookup"><span data-stu-id="97712-125">In the **Electronic reporting** workspace, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="97712-126">Sur l'onglet **Service de facturation électronique**, dans le champ **URI du point de terminaison de service**, entrez le point de terminaison de service approprié pour la zone géographique Azure, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="97712-126">On the **e-Invoicing service** tab, in the **Service endpoint URI** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="97712-127">Zone géographique Azure Datacenter</span><span class="sxs-lookup"><span data-stu-id="97712-127">Datacenter Azure geography</span></span> | <span data-ttu-id="97712-128">URI du point de terminaison de service</span><span class="sxs-lookup"><span data-stu-id="97712-128">Service endpoint URI</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="97712-129">Est des États-Unis</span><span class="sxs-lookup"><span data-stu-id="97712-129">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="97712-130">Ouest des États-Unis</span><span class="sxs-lookup"><span data-stu-id="97712-130">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="97712-131">Nord de l'UE</span><span class="sxs-lookup"><span data-stu-id="97712-131">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="97712-132">Ouest de l'UE</span><span class="sxs-lookup"><span data-stu-id="97712-132">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. <span data-ttu-id="97712-133">Vérifiez que le champ **ID candidature** est bien défini sur **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="97712-133">Verify that the **Application Id** field is set to **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span> <span data-ttu-id="97712-134">Cette valeur est une valeur fixe.</span><span class="sxs-lookup"><span data-stu-id="97712-134">This value is a fixed value.</span></span>
5. <span data-ttu-id="97712-135">Dans le champ **ID environnement LCS**, entrez l’ID de votre compte d’abonnement LCS.</span><span class="sxs-lookup"><span data-stu-id="97712-135">In the **LCS Environment Id** field, enter the ID of your LCS subscription account.</span></span>
6. <span data-ttu-id="97712-136">Sélectionnez **Sauvegarder**, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="97712-136">Select **Save**, and then close the page.</span></span>

## <a name="create-key-vault-secret"></a><span data-ttu-id="97712-137">Créer un secret Key Vault</span><span class="sxs-lookup"><span data-stu-id="97712-137">Create Key Vault secret</span></span>

1. <span data-ttu-id="97712-138">Connectez-vous à votre compte RCS.</span><span class="sxs-lookup"><span data-stu-id="97712-138">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="97712-139">Dans l’espace de travail **Fonctionnalité de globalisation**, dans la section **Environnement**, sélectionnez la vignette **Facturation électronique**.</span><span class="sxs-lookup"><span data-stu-id="97712-139">In the **Globalization feature** workspace, in the **Environment** section, select the **e-Invoicing** tile.</span></span>
3. <span data-ttu-id="97712-140">Sur la page **Configurations d'environnement**, dans le volet Actions, sélectionnez **Environnement de service**, puis sélectionnez **Paramètres Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="97712-140">On the **Environment setups** page, on the action Pane, select **Service environment**, and then select **Key Vault parameters**.</span></span>
4. <span data-ttu-id="97712-141">Sélectionnez **Nouveau** pour créer un secret de Key Vault.</span><span class="sxs-lookup"><span data-stu-id="97712-141">Select **New** to create a key vault secret.</span></span>
5. <span data-ttu-id="97712-142">Dans le champ **Nom**, entrez le nom du secret Key Vault.</span><span class="sxs-lookup"><span data-stu-id="97712-142">In the **Name** field, enter the name of the key vault secret.</span></span> <span data-ttu-id="97712-143">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="97712-143">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="97712-144">Dans le champ **URI Key Vault**, collez le secret à partir d'Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="97712-144">In the **Key Vault URI** field, paste the secret from Azure Key Vault.</span></span>
7. <span data-ttu-id="97712-145">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="97712-145">Select **Save**.</span></span>

## <a name="create-storage-account-secret"></a><span data-ttu-id="97712-146">Créer un secret de compte de stockage</span><span class="sxs-lookup"><span data-stu-id="97712-146">Create Storage account secret</span></span>

1. <span data-ttu-id="97712-147">Sur la page **Paramètres du coffre de clés**, dans la section **Certificats**, sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="97712-147">On **Key vault parameters** page, in the **Certificates** section, select **Add**.</span></span>
2. <span data-ttu-id="97712-148">Dans le champ **Nom**, entrez le nom du secret du compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="97712-148">In the **Name** field, enter the same of the storage account secret.</span></span> <span data-ttu-id="97712-149">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="97712-149">In the **Description** field, enter a description.</span></span>
3. <span data-ttu-id="97712-150">Dans le champ **Type**, sélectionnez **Certificat**.</span><span class="sxs-lookup"><span data-stu-id="97712-150">In the **Type** field, select **Certificate**.</span></span>
4. <span data-ttu-id="97712-151">Sélectionnez **Sauvegarder**, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="97712-151">Select **Save**, and then close the page.</span></span>

## <a name="create-an-electronic-invoicing-add-on-environment"></a><span data-ttu-id="97712-152">Créer un environnement complémentaire de facturation électronique</span><span class="sxs-lookup"><span data-stu-id="97712-152">Create an Electronic invoicing add-on environment</span></span>

1. <span data-ttu-id="97712-153">Connectez-vous à votre compte RCS.</span><span class="sxs-lookup"><span data-stu-id="97712-153">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="97712-154">Dans l’espace de travail **Fonctionnalité de globalisation**, dans la section **Environnement**, sélectionnez la vignette **Facturation électronique**.</span><span class="sxs-lookup"><span data-stu-id="97712-154">In the **Globalization feature** workspace, in the **Environment** section, select the **e-Invoicing** tile.</span></span>

## <a name="create-a-service-environment"></a><span data-ttu-id="97712-155">Créer un environnement de service</span><span class="sxs-lookup"><span data-stu-id="97712-155">Create a service environment</span></span>

1. <span data-ttu-id="97712-156">Sur la page **Configurations d'environnement**, dans le volet Actions, sélectionnez **Environnement de service**.</span><span class="sxs-lookup"><span data-stu-id="97712-156">On the **Environment setups** page, on the action Pane, select **Service environment**.</span></span>
2. <span data-ttu-id="97712-157">Sélectionnez **Nouveau** pour créer un environnement de service.</span><span class="sxs-lookup"><span data-stu-id="97712-157">Select **New** to create a new service environment.</span></span>
3. <span data-ttu-id="97712-158">Dans le champ **Nom**, entrez le nom de l’environnement de facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="97712-158">In the **Name** field, enter the name of the e-Invoicing environment.</span></span> <span data-ttu-id="97712-159">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="97712-159">In the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="97712-160">Dans le champ **Secret de jeton SAS de stockage**, sélectionnez le nom du certificat qui doit être utilisé pour authentifier l'accès au compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="97712-160">In the **Storage SAS token secret** field, select the name of the certificate that must be used to authenticate access to the storage account.</span></span>
5. <span data-ttu-id="97712-161">Dans la section **Utilisateurs**, sélectionnez **Ajouter** pour ajouter un utilisateur autorisé à soumettre des factures électroniques via l'environnement et à se connecter également au compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="97712-161">In the **Users** section, select **Add** to add a user who is allowed to submit electronic invoices through the environment and also connect to the storage account.</span></span>
6. <span data-ttu-id="97712-162">Entrez l'alias de l'utilisateur dans le champ **Identifiant utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="97712-162">In the **User ID** field, enter the alias of the user.</span></span> <span data-ttu-id="97712-163">Entrez l'adresse e-mail de l'utilisateur dans le champ **E-mail**.</span><span class="sxs-lookup"><span data-stu-id="97712-163">In the **Email** field, enter the user's email address.</span></span>
7. <span data-ttu-id="97712-164">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="97712-164">Select **Save**.</span></span>
8. <span data-ttu-id="97712-165">Si les factures spécifiques à votre pays/région nécessitent une chaîne de certificats pour appliquer des signatures numériques, dans le volet Actions, sélectionnez **Paramètres Key Vault**, puis **Chaîne de certificats**, et suivez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="97712-165">If your country/region-specific invoices require a chain of certificates to apply digital signatures, on the Action pane, select **Key Vault parameters**, then select **Chain of certificates**, and follow these steps:</span></span>

    1. <span data-ttu-id="97712-166">Sélectionnez **Nouveau** pour créer une chaîne de certificats.</span><span class="sxs-lookup"><span data-stu-id="97712-166">Select **New** to create a chain of certificates.</span></span>
    2. <span data-ttu-id="97712-167">Dans le champ **Nom**, entrez le nom de l’environnement de la chaîne de certificats.</span><span class="sxs-lookup"><span data-stu-id="97712-167">In the **Name** field, enter the name of the chain of certificate.</span></span> <span data-ttu-id="97712-168">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="97712-168">In the **Description** field, enter a description.</span></span>
    3. <span data-ttu-id="97712-169">Dans la section **Certificats**, sélectionnez **Ajouter** pour ajouter un certificat à la chaîne.</span><span class="sxs-lookup"><span data-stu-id="97712-169">In the **Certificates** section, select **Add** to add a certificate to the chain.</span></span>
    4. <span data-ttu-id="97712-170">Utilisez le bouton **Vers le haut** ou **Vers le bas** pour changer la position du certificat dans la chaîne.</span><span class="sxs-lookup"><span data-stu-id="97712-170">Use the **Up** or **Down** button to change the position of the certificate in the chain.</span></span>
    5. <span data-ttu-id="97712-171">Sélectionnez **Sauvegarder**, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="97712-171">Select **Save**, and then close the page.</span></span>
    6. <span data-ttu-id="97712-172">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="97712-172">Close the page.</span></span>
9. <span data-ttu-id="97712-173">Sur la page **Environnement de service**, dans le volet Actions, sélectionnez **Publier** pour publier l’environnement dans le Cloud.</span><span class="sxs-lookup"><span data-stu-id="97712-173">On **Service environment** page, on the Action Pane, select **Publish** to publish the environment to the cloud.</span></span> <span data-ttu-id="97712-174">La valeur du champ **Statut** est remplacée par **Publié**.</span><span class="sxs-lookup"><span data-stu-id="97712-174">The value of the **Status** field is changed to **Published**.</span></span>

## <a name="create-a-connected-application"></a><span data-ttu-id="97712-175">Créer une application connectée</span><span class="sxs-lookup"><span data-stu-id="97712-175">Create a connected application</span></span>

1. <span data-ttu-id="97712-176">Sur la page **Configurations d'environnement**, dans le volet Actions, sélectionnez **Applications connectées**.</span><span class="sxs-lookup"><span data-stu-id="97712-176">On the **Environment setups** page, on the action Pane, select **Connected applications**.</span></span>
2. <span data-ttu-id="97712-177">Sélectionnez **Nouveau** pour créer une application connectée.</span><span class="sxs-lookup"><span data-stu-id="97712-177">Select **New** to create a connected application.</span></span>
3. <span data-ttu-id="97712-178">Dans le champ **Nom**, entrez le nom de l’application à connecter.</span><span class="sxs-lookup"><span data-stu-id="97712-178">In the **Name** field, enter the name of the application to connect.</span></span>
4. <span data-ttu-id="97712-179">Dans le champ **Application**, entrez l'URL de l'environnement Finance et Supply Chain Management à connecter.</span><span class="sxs-lookup"><span data-stu-id="97712-179">In the **Application** field, enter the URL of the Finance and Supply Chain Management environment to connect.</span></span>
4. <span data-ttu-id="97712-180">Dans le champ **Client**, entrez le client de l'environnement Finance et Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="97712-180">In the **Tenant** field, enter the tenant of the Finance and Supply Chain Management environment.</span></span>
5. <span data-ttu-id="97712-181">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="97712-181">Select **Save**.</span></span>
6. <span data-ttu-id="97712-182">Dans le volet Actions, sélectionnez **Vérifier la connexion** pour tester la connexion avec l'environnement.</span><span class="sxs-lookup"><span data-stu-id="97712-182">On the Action Pane, select **Check connection** to test the connection with the environment.</span></span> <span data-ttu-id="97712-183">Fermez ensuite la page.</span><span class="sxs-lookup"><span data-stu-id="97712-183">Then close the page.</span></span>

## <a name="link-connected-applications-to-environments"></a><span data-ttu-id="97712-184">Lier les applications connectées aux environnements</span><span class="sxs-lookup"><span data-stu-id="97712-184">Link connected applications to environments</span></span>

1. <span data-ttu-id="97712-185">Sur la page **Configurations d'environnement**, sélectionnez **Nouveau** pour affecter une application connectée à un environnement.</span><span class="sxs-lookup"><span data-stu-id="97712-185">On the **Environment setups** page, select **New** to assign a connected application to an environment.</span></span>
2. <span data-ttu-id="97712-186">Sélectionnez une application connectée dans le champ **Application connectée**.</span><span class="sxs-lookup"><span data-stu-id="97712-186">In the **Connected application** field, select a connected application.</span></span>
3. <span data-ttu-id="97712-187">Sélectionnez un environnement de service dans le champ **Environnement de service**.</span><span class="sxs-lookup"><span data-stu-id="97712-187">In the **Service environment** field, select a service environment.</span></span>
4. <span data-ttu-id="97712-188">Sélectionnez **Sauvegarder**, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="97712-188">Select **Save**, and then close the page.</span></span>

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance-and-supply-chain-management"></a><span data-ttu-id="97712-189">Paramétrer l’intégration du module complémentaire de facturation électronique dans Finance et Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="97712-189">Set up the Electronic invoicing add-on integration in Finance and Supply Chain Management</span></span>

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a><span data-ttu-id="97712-190">Activer la fonctionnalité d’intégration du module complémentaire de facturation électronique</span><span class="sxs-lookup"><span data-stu-id="97712-190">Turn on the Electronic invoicing add-on integration feature</span></span>

1. <span data-ttu-id="97712-191">Connectez-vous à l'instance Finance ou Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="97712-191">Sign in to your Finance or Supply Chain Management instance.</span></span>
2. <span data-ttu-id="97712-192">Dans l’espace de travail **Gestion des fonctionnalités**, recherchez la fonctionnalité **Intégration du module complémentaire de facturation électronique**.</span><span class="sxs-lookup"><span data-stu-id="97712-192">In the **Feature management** workspace, search for the **Electronic invoicing add-on integration** feature.</span></span> <span data-ttu-id="97712-193">Si cette fonctionnalité n'apparaît pas sur la page, sélectionnez **Rechercher des mises à jour**.</span><span class="sxs-lookup"><span data-stu-id="97712-193">If this feature doesn't appear on the page, select **Check for updates**.</span></span>
3. <span data-ttu-id="97712-194">Sélectionnez la fonctionnalité, puis sélectionnez **Activer maintenant**.</span><span class="sxs-lookup"><span data-stu-id="97712-194">Select the feature, and then select **Enable now**.</span></span>

### <a name="set-up-the-service-endpoint-url"></a><span data-ttu-id="97712-195">Paramétrer l’URL du point de terminaison de service</span><span class="sxs-lookup"><span data-stu-id="97712-195">Set up the service endpoint URL</span></span>

1. <span data-ttu-id="97712-196">Allez dans **Administration de l’organisation \> Paramétrage \> Paramètres des documents électroniques**.</span><span class="sxs-lookup"><span data-stu-id="97712-196">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="97712-197">Sur l'onglet **Service d'envoi**, dans le champ **URL du point de terminaison de service**, entrez le point de terminaison de service approprié pour la zone géographique Azure, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="97712-197">On the **Submission service** tab, in the **Service endpoint URL** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="97712-198">Zone géographique Azure Datacenter</span><span class="sxs-lookup"><span data-stu-id="97712-198">Datacenter Azure geography</span></span> | <span data-ttu-id="97712-199">URL du point de terminaison de service</span><span class="sxs-lookup"><span data-stu-id="97712-199">Service endpoint URL</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="97712-200">Est des États-Unis</span><span class="sxs-lookup"><span data-stu-id="97712-200">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="97712-201">Ouest des États-Unis</span><span class="sxs-lookup"><span data-stu-id="97712-201">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="97712-202">Nord de l'UE</span><span class="sxs-lookup"><span data-stu-id="97712-202">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="97712-203">Ouest de l'UE</span><span class="sxs-lookup"><span data-stu-id="97712-203">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. <span data-ttu-id="97712-204">Dans le champ **Environnement**, entrez le nom de l’environnement complémentaire de facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="97712-204">In the **Environment** field, enter the name of the Electronic invoicing add-on environment.</span></span>
4. <span data-ttu-id="97712-205">Sélectionnez **Sauvegarder**, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="97712-205">Select **Save**, and then close the page.</span></span>
