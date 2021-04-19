---
title: Mise en route de l’administration du service de Facturation électronique
description: Cette rubrique explique comment démarrer avec la Facturation électronique.
author: gionoder
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: ec431cb4a3620459d905f64a80fd820a2113290f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840146"
---
# <a name="get-started-with-electronic-invoicing-service-administration"></a><span data-ttu-id="21f1d-103">Mise en route de l’administration du service de Facturation électronique</span><span class="sxs-lookup"><span data-stu-id="21f1d-103">Get started with Electronic invoicing service administration</span></span>

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="21f1d-104">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="21f1d-104">Prerequisites</span></span>

<span data-ttu-id="21f1d-105">Avant d’effectuer les étapes de cette rubrique, les conditions préalables suivantes doivent être remplies :</span><span class="sxs-lookup"><span data-stu-id="21f1d-105">Before you complete the procedures in this topic, the following prerequisites must be in place:</span></span>

- <span data-ttu-id="21f1d-106">Vous devez avoir accès à votre compte Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="21f1d-106">You must have access to your Microsoft Dynamics Lifecycle Services (LCS) account.</span></span>
- <span data-ttu-id="21f1d-107">Vous devez avoir un projet LCS qui inclut la version 10.0.17 ou ultérieure de Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="21f1d-107">You must have an LCS project that includes version 10.0.17 or later of Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="21f1d-108">En outre, ces applications doivent être déployées dans l’une des zones géographiques Azure suivantes :</span><span class="sxs-lookup"><span data-stu-id="21f1d-108">Additionally, these apps must be deployed in one of the following Azure geographies:</span></span>

    - <span data-ttu-id="21f1d-109">Est des États-Unis</span><span class="sxs-lookup"><span data-stu-id="21f1d-109">East US</span></span>
    - <span data-ttu-id="21f1d-110">Ouest des États-Unis</span><span class="sxs-lookup"><span data-stu-id="21f1d-110">West US</span></span>
    - <span data-ttu-id="21f1d-111">Nord de l’UE</span><span class="sxs-lookup"><span data-stu-id="21f1d-111">North EU</span></span>
    - <span data-ttu-id="21f1d-112">Ouest de l’UE</span><span class="sxs-lookup"><span data-stu-id="21f1d-112">West EU</span></span>

- <span data-ttu-id="21f1d-113">Vous devez avoir accès à votre compte Dynamics 365 Regulatory Configuration Services (RCS).</span><span class="sxs-lookup"><span data-stu-id="21f1d-113">You must have access to your Dynamics 365 Regulatory Configuration Services (RCS) account.</span></span>
- <span data-ttu-id="21f1d-114">Vous devez activer la fonctionnalité de globalisation pour votre compte RCS via le module Gestion des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="21f1d-114">You must activate the Globalization feature for your RCS account in Feature management.</span></span> <span data-ttu-id="21f1d-115">Pour plus d’informations, voir [Regulatory Configuration Services (RCS) – Fonctionnalités de globalisation](rcs-globalization-feature.md).</span><span class="sxs-lookup"><span data-stu-id="21f1d-115">For more information, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md).</span></span>
- <span data-ttu-id="21f1d-116">Vous devez créer un coffre de clés et d’un compte de stockage dans Azure.</span><span class="sxs-lookup"><span data-stu-id="21f1d-116">You must create a key vault and a storage account in Azure.</span></span> <span data-ttu-id="21f1d-117">Pour plus d’informations, voir [Créer un compte de stockage Azure et un coffre de clés](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="21f1d-117">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

## <a name="install-the-add-in-for-microservices-in-lifecycle-services"></a><span data-ttu-id="21f1d-118">Installer le module complémentaire pour les microservices dans Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="21f1d-118">Install the add-in for microservices in Lifecycle Services</span></span>

1. <span data-ttu-id="21f1d-119">Connectez-vous à votre compte LCS.</span><span class="sxs-lookup"><span data-stu-id="21f1d-119">Sign in to your LCS account.</span></span>
2. <span data-ttu-id="21f1d-120">Sélectionnez la vignette **Gestion des fonctionnalités d’aperçu**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-120">Select the **Preview feature management** tile.</span></span>
3. <span data-ttu-id="21f1d-121">Dans la section **Fonctionnalités de version préliminaire**, sélectionnez **Service de facturation électronique**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-121">In the **Public Preview Features** section, select **e-Invoicing service**.</span></span>
4. <span data-ttu-id="21f1d-122">Veillez à ce que l’option **Fonctionnalité de version préliminaire activée** soit définie sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-122">Make sure that the **Preview feature enabled** option is set to **Yes**.</span></span>
5. <span data-ttu-id="21f1d-123">Sur votre tableau de bord LCS, sélectionnez votre projet de déploiement LCS.</span><span class="sxs-lookup"><span data-stu-id="21f1d-123">On your LCS dashboard, select your LCS deployment project.</span></span> <span data-ttu-id="21f1d-124">Le projet LCS doit être en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="21f1d-124">The LCS project must be running.</span></span>
7. <span data-ttu-id="21f1d-125">Dans l’onglet **Compléments d’environnement**, sélectionnez **Installer un nouveau complément**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-125">On the **Environment add-ins** tab, select **Install a new add-in**.</span></span>
8. <span data-ttu-id="21f1d-126">Sélectionnez **Services de facturation électronique**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-126">Select **e-invoicing Services**.</span></span>
9. <span data-ttu-id="21f1d-127">Dans le champ **ID d’application AAD**, entrez **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-127">In the **AAD application ID** field, enter **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span></span> <span data-ttu-id="21f1d-128">Cette valeur est une valeur fixe.</span><span class="sxs-lookup"><span data-stu-id="21f1d-128">This is a fixed value.</span></span>
10. <span data-ttu-id="21f1d-129">Dans le champ **ID client AAD**, entrez l’ID client de votre compte d’abonnement Azure.</span><span class="sxs-lookup"><span data-stu-id="21f1d-129">In the **AAD tenant ID** field, enter the tenant ID of your Azure subscription account.</span></span>
11. <span data-ttu-id="21f1d-130">Passez en revue les conditions générales, puis cochez la case.</span><span class="sxs-lookup"><span data-stu-id="21f1d-130">Review the terms and conditions, and then select the check box.</span></span>
12. <span data-ttu-id="21f1d-131">Sélectionnez **Installer**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-131">Select **Install**.</span></span>


## <a name="set-up-the-parameters-for-rcs-integration-with-electronic-invoicing"></a><span data-ttu-id="21f1d-132">Définir les paramètres pour l’intégration RCS avec la Facturation électronique</span><span class="sxs-lookup"><span data-stu-id="21f1d-132">Set up the parameters for RCS integration with Electronic invoicing</span></span>

1. <span data-ttu-id="21f1d-133">Connectez-vous à votre compte RCS.</span><span class="sxs-lookup"><span data-stu-id="21f1d-133">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="21f1d-134">Dans l’espace de travail **Génération d’états électroniques**, dans la section **Liens connexes**, sélectionnez **Paramètres de la gestion des états électroniques**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-134">In the **Electronic reporting** workspace, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="21f1d-135">Sur l’onglet **Service de facturation électronique**, dans le champ **URI du point de terminaison de service**, entrez le point de terminaison de service approprié pour la zone géographique Azure, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="21f1d-135">On the **e-Invoicing service** tab, in the **Service endpoint URI** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="21f1d-136">Zone géographique Azure Datacenter</span><span class="sxs-lookup"><span data-stu-id="21f1d-136">Datacenter Azure geography</span></span> | <span data-ttu-id="21f1d-137">URI du point de terminaison de service</span><span class="sxs-lookup"><span data-stu-id="21f1d-137">Service endpoint URI</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="21f1d-138">Est des États-Unis</span><span class="sxs-lookup"><span data-stu-id="21f1d-138">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="21f1d-139">Ouest des États-Unis</span><span class="sxs-lookup"><span data-stu-id="21f1d-139">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="21f1d-140">Nord de l’UE</span><span class="sxs-lookup"><span data-stu-id="21f1d-140">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="21f1d-141">Ouest de l’UE</span><span class="sxs-lookup"><span data-stu-id="21f1d-141">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. <span data-ttu-id="21f1d-142">Vérifiez que le champ **ID candidature** est bien défini sur **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-142">Verify that the **Application Id** field is set to **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span> <span data-ttu-id="21f1d-143">Cette valeur est une valeur fixe.</span><span class="sxs-lookup"><span data-stu-id="21f1d-143">This value is a fixed value.</span></span>
5. <span data-ttu-id="21f1d-144">Dans le champ **ID environnement LCS**, entrez l’ID de votre environnement LCS.</span><span class="sxs-lookup"><span data-stu-id="21f1d-144">In the **LCS Environment Id** field, enter the ID of your LCS environment.</span></span>
6. <span data-ttu-id="21f1d-145">Sélectionnez **Sauvegarder**, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="21f1d-145">Select **Save**, and then close the page.</span></span>

## <a name="create-key-vault-references"></a><span data-ttu-id="21f1d-146">Créer des références Key Vault</span><span class="sxs-lookup"><span data-stu-id="21f1d-146">Create Key Vault references</span></span>

1. <span data-ttu-id="21f1d-147">Connectez-vous à votre compte RCS.</span><span class="sxs-lookup"><span data-stu-id="21f1d-147">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="21f1d-148">Dans l’espace de travail **Fonctionnalités de globalisation**, dans la section **Environnement**, sélectionnez la vignette **Facturation électronique**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-148">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing** tile.</span></span>
3. <span data-ttu-id="21f1d-149">Sur la page **Configurations d’environnement**, dans le volet Actions, sélectionnez **Environnement de service**, puis sélectionnez **Paramètres Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-149">On the **Environment setups** page, on the action Pane, select **Service environment**, and then select **Key Vault parameters**.</span></span>
4. <span data-ttu-id="21f1d-150">Sélectionnez **Nouveau** pour créer une référence Key Vault.</span><span class="sxs-lookup"><span data-stu-id="21f1d-150">Select **New** to create a key vault reference.</span></span>
5. <span data-ttu-id="21f1d-151">Dans le champ **Nom**, entrez le nom de la référence Key Vault.</span><span class="sxs-lookup"><span data-stu-id="21f1d-151">In the **Name** field, enter the name of the key vault reference.</span></span> <span data-ttu-id="21f1d-152">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-152">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="21f1d-153">Dans le champ **URI Key Vault**, collez le secret du coffre de clés à partir d’Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="21f1d-153">In the **Key Vault URI** field, paste the key vault secret from Azure Key Vault.</span></span> <span data-ttu-id="21f1d-154">Pour plus d’informations, voir [Créer un compte de stockage Azure et un coffre de clés](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="21f1d-154">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>
7. <span data-ttu-id="21f1d-155">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-155">Select **Save**.</span></span>

## <a name="create-storage-account-secret"></a><span data-ttu-id="21f1d-156">Créer un secret de compte de stockage</span><span class="sxs-lookup"><span data-stu-id="21f1d-156">Create Storage account secret</span></span>

1. <span data-ttu-id="21f1d-157">Sur la page **Configurations d’environnement**, dans le volet Actions, sélectionnez **Environnement de service** > **Paramètres Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-157">On the **Environment setups** page, on the Action Pane, select **Service environment** > **Key Vault parameters**.</span></span>
2. <span data-ttu-id="21f1d-158">Sélectionnez une **Référence Key Vault** et, dans la section **Certificats**, sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-158">Select a **Key Vault reference** and in the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="21f1d-159">Dans le champ **Nom**, entrez le nom du secret du compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="21f1d-159">In the **Name** field, enter the name of the storage account secret.</span></span> <span data-ttu-id="21f1d-160">Pour plus d’informations, voir [Créer un compte de stockage Azure et un coffre de clés](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="21f1d-160">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>
4. <span data-ttu-id="21f1d-161">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-161">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="21f1d-162">Dans le champ **Type**, sélectionnez **Secret**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-162">In the **Type** field, select **Secret**.</span></span>
6. <span data-ttu-id="21f1d-163">Sélectionnez **Sauvegarder**, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="21f1d-163">Select **Save**, and then close the page.</span></span>

## <a name="create-a-digital-certificate-secret"></a><span data-ttu-id="21f1d-164">Créer un secret de certificat numérique</span><span class="sxs-lookup"><span data-stu-id="21f1d-164">Create a digital certificate secret</span></span>

1. <span data-ttu-id="21f1d-165">Sur la page **Configurations d’environnement**, dans le volet Actions, sélectionnez **Environnement de service**, puis sélectionnez **Paramètres Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-165">On the **Environment setups** page, on the action Pane, select **Service environment** and then select **Key Vault parameters**.</span></span>
2. <span data-ttu-id="21f1d-166">Sélectionnez une **Référence Key Vault** puis, dans la section **Certificats**, sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-166">Select a **Key Vault reference** and then in the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="21f1d-167">Dans le champ **Nom**, entrez le nom du secret de certificat numérique.</span><span class="sxs-lookup"><span data-stu-id="21f1d-167">In the **Name** field, enter the name of the digital certificate secret.</span></span> <span data-ttu-id="21f1d-168">Pour plus d’informations, voir [Créer un compte de stockage Azure et un coffre de clés](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="21f1d-168">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>
4. <span data-ttu-id="21f1d-169">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-169">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="21f1d-170">Dans le champ **Type**, sélectionnez **Certificat**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-170">In the **Type** field, select **Certificate**.</span></span>
6. <span data-ttu-id="21f1d-171">Sélectionnez **Sauvegarder**, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="21f1d-171">Select **Save**, and then close the page.</span></span>

## <a name="create-a-service-environment"></a><span data-ttu-id="21f1d-172">Créer un environnement de service</span><span class="sxs-lookup"><span data-stu-id="21f1d-172">Create a service environment</span></span>

1. <span data-ttu-id="21f1d-173">Connectez-vous à votre compte RCS.</span><span class="sxs-lookup"><span data-stu-id="21f1d-173">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="21f1d-174">Dans l’espace de travail **Fonctionnalités de globalisation**, dans la section **Environnement**, sélectionnez la vignette **Facturation électronique**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-174">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing** tile.</span></span>
3. <span data-ttu-id="21f1d-175">Sur la page **Configurations d’environnement**, dans le volet Actions, sélectionnez **Environnement de service**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-175">On the **Environment setups** page, on the Action Pane, select **Service environment**.</span></span>
4. <span data-ttu-id="21f1d-176">Sélectionnez **Nouveau** pour créer un environnement de service.</span><span class="sxs-lookup"><span data-stu-id="21f1d-176">Select **New** to create a new service environment.</span></span>
5. <span data-ttu-id="21f1d-177">Dans le champ **Nom**, entrez le nom de l’environnement de facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="21f1d-177">In the **Name** field, enter the name of the e-Invoicing environment.</span></span> <span data-ttu-id="21f1d-178">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-178">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="21f1d-179">Dans le champ **Secret de jeton SAS de stockage**, sélectionnez le secret du compte de stockage qui doit être utilisé pour authentifier l’accès au compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="21f1d-179">In the **Storage SAS token secret** field, select the name of the storage account secret that must be used to authenticate access to the storage account.</span></span>
7. <span data-ttu-id="21f1d-180">Dans la section **Utilisateurs**, sélectionnez **Ajouter** pour ajouter un utilisateur autorisé à soumettre des factures électroniques via l’environnement et à se connecter également au compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="21f1d-180">In the **Users** section, select **Add** to add a user who is allowed to submit electronic invoices through the environment and also connect to the storage account.</span></span>
8. <span data-ttu-id="21f1d-181">Entrez l’alias de l’utilisateur dans le champ **Identifiant utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-181">In the **User ID** field, enter the alias of the user.</span></span> <span data-ttu-id="21f1d-182">Entrez l’adresse e-mail de l’utilisateur dans le champ **E-mail**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-182">In the **Email** field, enter the user's email address.</span></span>
9. <span data-ttu-id="21f1d-183">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-183">Select **Save**.</span></span>
10. <span data-ttu-id="21f1d-184">Si les factures spécifiques à votre pays/région nécessitent une chaîne de certificats pour appliquer des signatures numériques, dans le volet Actions, sélectionnez **Paramètres Key Vault**, puis **Chaîne de certificats**, et suivez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="21f1d-184">If your country/region-specific invoices require a chain of certificates to apply digital signatures, on the Action pane, select **Key Vault parameters**, then select **Chain of certificates**, and follow these steps:</span></span>
    1. <span data-ttu-id="21f1d-185">Sélectionnez **Nouveau** pour créer une chaîne de certificats.</span><span class="sxs-lookup"><span data-stu-id="21f1d-185">Select **New** to create a chain of certificates.</span></span>
    2. <span data-ttu-id="21f1d-186">Dans le champ **Nom**, entrez le nom de l’environnement de la chaîne de certificats.</span><span class="sxs-lookup"><span data-stu-id="21f1d-186">In the **Name** field, enter the name of the chain of certificate.</span></span> <span data-ttu-id="21f1d-187">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-187">In the **Description** field, enter a description.</span></span>
    3. <span data-ttu-id="21f1d-188">Dans la section **Certificats**, sélectionnez **Ajouter** pour ajouter un certificat à la chaîne.</span><span class="sxs-lookup"><span data-stu-id="21f1d-188">In the **Certificates** section, select **Add** to add a certificate to the chain.</span></span>
    4. <span data-ttu-id="21f1d-189">Utilisez le bouton **Vers le haut** ou **Vers le bas** pour changer la position du certificat dans la chaîne.</span><span class="sxs-lookup"><span data-stu-id="21f1d-189">Use the **Up** or **Down** button to change the position of the certificate in the chain.</span></span>
    5. <span data-ttu-id="21f1d-190">Sélectionnez **Sauvegarder**, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="21f1d-190">Select **Save**, and then close the page.</span></span>
    6. <span data-ttu-id="21f1d-191">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="21f1d-191">Close the page.</span></span>
11. <span data-ttu-id="21f1d-192">Sur la page **Environnement de service**, dans le volet Actions, sélectionnez **Publier** pour publier l’environnement dans le Cloud.</span><span class="sxs-lookup"><span data-stu-id="21f1d-192">On **Service environment** page, on the Action Pane, select **Publish** to publish the environment to the cloud.</span></span> <span data-ttu-id="21f1d-193">La valeur du champ **Statut** est remplacée par **Publié**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-193">The value of the **Status** field is changed to **Published**.</span></span>

## <a name="create-a-connected-application"></a><span data-ttu-id="21f1d-194">Créer une application connectée</span><span class="sxs-lookup"><span data-stu-id="21f1d-194">Create a connected application</span></span>

1. <span data-ttu-id="21f1d-195">Sur la page **Configurations d’environnement**, dans le volet Actions, sélectionnez **Applications connectées**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-195">On the **Environment setups** page, on the action Pane, select **Connected applications**.</span></span>
2. <span data-ttu-id="21f1d-196">Sélectionnez **Nouveau** pour créer une application connectée.</span><span class="sxs-lookup"><span data-stu-id="21f1d-196">Select **New** to create a connected application.</span></span>
3. <span data-ttu-id="21f1d-197">Dans le champ **Nom**, entrez le nom de l’application à connecter.</span><span class="sxs-lookup"><span data-stu-id="21f1d-197">In the **Name** field, enter the name of the application to connect.</span></span>
4. <span data-ttu-id="21f1d-198">Dans le champ **Application**, entrez l’URL de l’environnement Finance et Supply Chain Management à connecter.</span><span class="sxs-lookup"><span data-stu-id="21f1d-198">In the **Application** field, enter the URL of the Finance and Supply Chain Management environment to connect.</span></span>
4. <span data-ttu-id="21f1d-199">Dans le champ **Client**, entrez le client de l’environnement Finance et Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="21f1d-199">In the **Tenant** field, enter the tenant of the Finance and Supply Chain Management environment.</span></span>
5. <span data-ttu-id="21f1d-200">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-200">Select **Save**.</span></span>
6. <span data-ttu-id="21f1d-201">Dans le volet Actions, sélectionnez **Vérifier la connexion** pour tester la connexion avec l’environnement.</span><span class="sxs-lookup"><span data-stu-id="21f1d-201">On the Action Pane, select **Check connection** to test the connection with the environment.</span></span> <span data-ttu-id="21f1d-202">Fermez ensuite la page.</span><span class="sxs-lookup"><span data-stu-id="21f1d-202">Then close the page.</span></span>

## <a name="link-connected-applications-to-environments"></a><span data-ttu-id="21f1d-203">Lier les applications connectées aux environnements</span><span class="sxs-lookup"><span data-stu-id="21f1d-203">Link connected applications to environments</span></span>

1. <span data-ttu-id="21f1d-204">Sur la page **Configurations d’environnement**, sélectionnez **Nouveau** pour affecter une application connectée à un environnement.</span><span class="sxs-lookup"><span data-stu-id="21f1d-204">On the **Environment setups** page, select **New** to assign a connected application to an environment.</span></span>
2. <span data-ttu-id="21f1d-205">Sélectionnez une application connectée dans le champ **Application connectée**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-205">In the **Connected application** field, select a connected application.</span></span>
3. <span data-ttu-id="21f1d-206">Sélectionnez un environnement de service dans le champ **Environnement de service**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-206">In the **Service environment** field, select a service environment.</span></span>
4. <span data-ttu-id="21f1d-207">Sélectionnez **Sauvegarder**, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="21f1d-207">Select **Save**, and then close the page.</span></span>

## <a name="set-up-electronic-invoicing-integration-in-finance-and-supply-chain-management"></a><span data-ttu-id="21f1d-208">Paramétrer l’intégration de la Facturation électronique dans Finance et Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="21f1d-208">Set up Electronic invoicing integration in Finance and Supply Chain Management</span></span>

### <a name="turn-on-the-electronic-invoicing-integration-feature"></a><span data-ttu-id="21f1d-209">Activer la fonctionnalité d’intégration de la Facturation électronique</span><span class="sxs-lookup"><span data-stu-id="21f1d-209">Turn on the Electronic invoicing integration feature</span></span>

1. <span data-ttu-id="21f1d-210">Connectez-vous à l’instance Finance ou Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="21f1d-210">Sign in to your Finance or Supply Chain Management instance.</span></span>
2. <span data-ttu-id="21f1d-211">Dans l’espace de travail **Gestion des fonctionnalités**, recherchez la fonctionnalité **Intégration de la Facturation électronique**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-211">In the **Feature management** workspace, search for the **Electronic invoicing integration** feature.</span></span> <span data-ttu-id="21f1d-212">Si cette fonctionnalité n’apparaît pas sur la page, sélectionnez **Rechercher des mises à jour**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-212">If this feature doesn't appear on the page, select **Check for updates**.</span></span>
3. <span data-ttu-id="21f1d-213">Sélectionnez la fonctionnalité, puis sélectionnez **Activer maintenant**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-213">Select the feature, and then select **Enable now**.</span></span>

### <a name="set-up-the-service-endpoint-url"></a><span data-ttu-id="21f1d-214">Paramétrer l’URL du point de terminaison de service</span><span class="sxs-lookup"><span data-stu-id="21f1d-214">Set up the service endpoint URL</span></span>

1. <span data-ttu-id="21f1d-215">Allez dans **Administration de l’organisation \> Paramétrage \> Paramètres des documents électroniques**.</span><span class="sxs-lookup"><span data-stu-id="21f1d-215">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="21f1d-216">Sur l’onglet **Service d’envoi**, dans le champ **URL du point de terminaison de service**, entrez le point de terminaison de service approprié pour la zone géographique Azure, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="21f1d-216">On the **Submission service** tab, in the **Service endpoint URL** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="21f1d-217">Zone géographique Azure Datacenter</span><span class="sxs-lookup"><span data-stu-id="21f1d-217">Datacenter Azure geography</span></span> | <span data-ttu-id="21f1d-218">URL du point de terminaison de service</span><span class="sxs-lookup"><span data-stu-id="21f1d-218">Service endpoint URL</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="21f1d-219">Est des États-Unis</span><span class="sxs-lookup"><span data-stu-id="21f1d-219">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="21f1d-220">Ouest des États-Unis</span><span class="sxs-lookup"><span data-stu-id="21f1d-220">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="21f1d-221">Nord de l’UE</span><span class="sxs-lookup"><span data-stu-id="21f1d-221">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="21f1d-222">Ouest de l’UE</span><span class="sxs-lookup"><span data-stu-id="21f1d-222">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. <span data-ttu-id="21f1d-223">Dans le champ **Environnement**, entrez le nom de l’environnement de service publié dans la Facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="21f1d-223">In the **Environment** field, enter the name of the service environment published in Electronic invoicing.</span></span>
4. <span data-ttu-id="21f1d-224">Sélectionnez **Sauvegarder**, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="21f1d-224">Select **Save**, and then close the page.</span></span>

### <a name="enable-flighting-keys"></a><span data-ttu-id="21f1d-225">Activer les clés de distribution de version d’évaluation</span><span class="sxs-lookup"><span data-stu-id="21f1d-225">Enable Flighting keys</span></span>

<span data-ttu-id="21f1d-226">Activez les clés de distribution de version d’évaluation pour Microsoft Dynamics 365 Finance ou Microsoft Dynamics 365 Supply Chain Management, versions 10.0.17 ou antérieures.</span><span class="sxs-lookup"><span data-stu-id="21f1d-226">Enable Flight keys for  Microsoft Dynamics 365 Finance or  Microsoft Dynamics 365 Supply Chain Management versions 10.0.17 or earlier.</span></span> 
1. <span data-ttu-id="21f1d-227">Exécutez la commande SQL suivante :</span><span class="sxs-lookup"><span data-stu-id="21f1d-227">Execute the following SQL command:</span></span>

    <span data-ttu-id="21f1d-228">INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES (’BusinessDocumentSubmissionServiceEnabled’, 1)</span><span class="sxs-lookup"><span data-stu-id="21f1d-228">INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BusinessDocumentSubmissionServiceEnabled', 1)</span></span>
    
    <span data-ttu-id="21f1d-229">INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES (’ElectronicInvoicingServiceIntegrationFeature’, 1)</span><span class="sxs-lookup"><span data-stu-id="21f1d-229">INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('ElectronicInvoicingServiceIntegrationFeature', 1)</span></span>

2. <span data-ttu-id="21f1d-230">Exécutez une commande IISreset pour tous les AOS.</span><span class="sxs-lookup"><span data-stu-id="21f1d-230">Perform an IISreset command for all AOS's.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
