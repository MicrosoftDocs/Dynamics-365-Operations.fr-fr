---
title: Prise en main de l'administration du service du module complémentaire de facturation électronique
description: Cette rubrique explique comment démarrer avec le module complémentaire de facturation électronique.
author: gionoder
manager: AnnBe
ms.date: 03/12/2021
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
ms.openlocfilehash: 05b00380cec7511adad2467d3f252799a4aaee5c
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592524"
---
# <a name="get-started-with-electronic-invoicing-add-on-service-administration"></a><span data-ttu-id="76d73-103">Prise en main de l'administration du service du module complémentaire de facturation électronique</span><span class="sxs-lookup"><span data-stu-id="76d73-103">Get started with Electronic invoicing add-on service administration</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="76d73-104">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="76d73-104">Prerequisites</span></span>

<span data-ttu-id="76d73-105">Avant d’effectuer les étapes de cette rubrique, les conditions préalables suivantes doivent être remplies :</span><span class="sxs-lookup"><span data-stu-id="76d73-105">Before you complete the procedures in this topic, the following prerequisites must be in place:</span></span>

- <span data-ttu-id="76d73-106">Vous devez avoir accès à votre compte Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="76d73-106">You must have access to your Microsoft Dynamics Lifecycle Services (LCS) account.</span></span>
- <span data-ttu-id="76d73-107">Vous devez avoir un projet LCS qui inclut la version 10.0.17 ou ultérieure de Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="76d73-107">You must have an LCS project that includes version 10.0.17 or later of Microsoft Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="76d73-108">En outre, ces applications doivent être déployées dans l'une des zones géographiques Azure suivantes :</span><span class="sxs-lookup"><span data-stu-id="76d73-108">Additionally, these apps must be deployed in one of the following Azure geographies:</span></span>

    - <span data-ttu-id="76d73-109">Est des États-Unis</span><span class="sxs-lookup"><span data-stu-id="76d73-109">East US</span></span>
    - <span data-ttu-id="76d73-110">Ouest des États-Unis</span><span class="sxs-lookup"><span data-stu-id="76d73-110">West US</span></span>
    - <span data-ttu-id="76d73-111">Nord de l'UE</span><span class="sxs-lookup"><span data-stu-id="76d73-111">North EU</span></span>
    - <span data-ttu-id="76d73-112">Ouest de l'UE</span><span class="sxs-lookup"><span data-stu-id="76d73-112">West EU</span></span>

- <span data-ttu-id="76d73-113">Vous devez avoir accès à votre compte Dynamics 365 Regulatory Configuration Services (RCS).</span><span class="sxs-lookup"><span data-stu-id="76d73-113">You must have access to your Dynamics 365 Regulatory Configuration Services (RCS) account.</span></span>
- <span data-ttu-id="76d73-114">Vous devez activer la fonctionnalité de globalisation pour votre compte RCS via le module Gestion des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="76d73-114">You must activate the Globalization feature for your RCS account in Feature management.</span></span> <span data-ttu-id="76d73-115">Pour plus d’informations, voir [Regulatory Configuration Services (RCS) - Fonctionnalités de globalisation](rcs-globalization-feature.md).</span><span class="sxs-lookup"><span data-stu-id="76d73-115">For more information, see [Regulatory Configuration Services (RCS) - Globalization features](rcs-globalization-feature.md).</span></span>
- <span data-ttu-id="76d73-116">Vous devez créer un coffre de clés et d’un compte de stockage dans Azure.</span><span class="sxs-lookup"><span data-stu-id="76d73-116">You must create a key vault and a storage account in Azure.</span></span> <span data-ttu-id="76d73-117">Pour plus d’informations, voir [Créer un compte de stockage Azure et un coffre de clés](e-invoicing-create-azure-storage-account-key-vault.md).</span><span class="sxs-lookup"><span data-stu-id="76d73-117">For more information, see [Create an Azure storage account and a key vault](e-invoicing-create-azure-storage-account-key-vault.md).</span></span>

## <a name="install-the-add-on-for-microservices-in-lifecycle-services"></a><span data-ttu-id="76d73-118">Installer le module complémentaire pour les microservices dans Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="76d73-118">Install the add-on for microservices in Lifecycle Services</span></span>

1. <span data-ttu-id="76d73-119">Connectez-vous à votre compte LCS.</span><span class="sxs-lookup"><span data-stu-id="76d73-119">Sign in to your LCS account.</span></span>
2. <span data-ttu-id="76d73-120">Sélectionnez la vignette **Gestion des fonctionnalités d'aperçu**.</span><span class="sxs-lookup"><span data-stu-id="76d73-120">Select the **Preview feature management** tile.</span></span>
3. <span data-ttu-id="76d73-121">Dans la section **Fonctionnalités de version préliminaire**, sélectionnez **Service de facturation électronique**.</span><span class="sxs-lookup"><span data-stu-id="76d73-121">In the **Public Preview Features** section, select **e-Invoicing service**.</span></span>
4. <span data-ttu-id="76d73-122">Veillez à ce que l'option **Fonctionnalité de version préliminaire activée** soit définie sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="76d73-122">Make sure that the **Preview feature enabled** option is set to **Yes**.</span></span>
5. <span data-ttu-id="76d73-123">Sur votre tableau de bord LCS, sélectionnez votre projet de déploiement LCS.</span><span class="sxs-lookup"><span data-stu-id="76d73-123">On your LCS dashboard, select your LCS deployment project.</span></span> <span data-ttu-id="76d73-124">Le projet LCS doit être en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="76d73-124">The LCS project must be running.</span></span>
7. <span data-ttu-id="76d73-125">Dans l’onglet **Compléments d’environnement**, sélectionnez **Installer un nouveau complément**.</span><span class="sxs-lookup"><span data-stu-id="76d73-125">On the **Environment add-ins** tab, select **Install a new add-in**.</span></span>
8. <span data-ttu-id="76d73-126">Sélectionnez **Services de facturation électronique** et dans le champ **ID application AAD**, entrez **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span><span class="sxs-lookup"><span data-stu-id="76d73-126">Select **e-invoicing Services** and in the **AAD application ID** field, enter **091c98b0-a1c9-4b02-b62c-7753395ccabe**.</span></span> <span data-ttu-id="76d73-127">Cette valeur est une valeur fixe.</span><span class="sxs-lookup"><span data-stu-id="76d73-127">This is a fixed value.</span></span>
10. <span data-ttu-id="76d73-128">Dans le champ **ID client AAD**, entrez l’ID client de votre compte d’abonnement Azure.</span><span class="sxs-lookup"><span data-stu-id="76d73-128">In the **AAD tenant ID** field, enter the tenant ID of your Azure subscription account.</span></span>
11. <span data-ttu-id="76d73-129">Passez en revue les conditions générales, puis cochez la case.</span><span class="sxs-lookup"><span data-stu-id="76d73-129">Review the terms and conditions, and then select the check box.</span></span>
12. <span data-ttu-id="76d73-130">Sélectionnez **Installer**.</span><span class="sxs-lookup"><span data-stu-id="76d73-130">Select **Install**.</span></span>


## <a name="set-up-the-parameters-for-rcs-integration-with-the-electronic-invoicing-add-on"></a><span data-ttu-id="76d73-131">Définir les paramètres pour l’intégration RCS avec le module complémentaire de facturation électronique</span><span class="sxs-lookup"><span data-stu-id="76d73-131">Set up the parameters for RCS integration with the Electronic invoicing add-on</span></span>

1. <span data-ttu-id="76d73-132">Connectez-vous à votre compte RCS.</span><span class="sxs-lookup"><span data-stu-id="76d73-132">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="76d73-133">Dans l’espace de travail **Génération d’états électroniques**, dans la section **Liens connexes**, sélectionnez **Paramètres de la gestion des états électroniques**.</span><span class="sxs-lookup"><span data-stu-id="76d73-133">In the **Electronic reporting** workspace, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="76d73-134">Sur l'onglet **Service de facturation électronique**, dans le champ **URI du point de terminaison de service**, entrez le point de terminaison de service approprié pour la zone géographique Azure, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="76d73-134">On the **e-Invoicing service** tab, in the **Service endpoint URI** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="76d73-135">Zone géographique Azure Datacenter</span><span class="sxs-lookup"><span data-stu-id="76d73-135">Datacenter Azure geography</span></span> | <span data-ttu-id="76d73-136">URI du point de terminaison de service</span><span class="sxs-lookup"><span data-stu-id="76d73-136">Service endpoint URI</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="76d73-137">Est des États-Unis</span><span class="sxs-lookup"><span data-stu-id="76d73-137">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="76d73-138">Ouest des États-Unis</span><span class="sxs-lookup"><span data-stu-id="76d73-138">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="76d73-139">Nord de l'UE</span><span class="sxs-lookup"><span data-stu-id="76d73-139">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="76d73-140">Ouest de l'UE</span><span class="sxs-lookup"><span data-stu-id="76d73-140">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. <span data-ttu-id="76d73-141">Vérifiez que le champ **ID candidature** est bien défini sur **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="76d73-141">Verify that the **Application Id** field is set to **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span> <span data-ttu-id="76d73-142">Cette valeur est une valeur fixe.</span><span class="sxs-lookup"><span data-stu-id="76d73-142">This value is a fixed value.</span></span>
5. <span data-ttu-id="76d73-143">Dans le champ **ID environnement LCS**, entrez l’ID de votre compte d’abonnement LCS.</span><span class="sxs-lookup"><span data-stu-id="76d73-143">In the **LCS Environment Id** field, enter the ID of your LCS subscription account.</span></span>
6. <span data-ttu-id="76d73-144">Sélectionnez **Sauvegarder**, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="76d73-144">Select **Save**, and then close the page.</span></span>

## <a name="create-key-vault-secret"></a><span data-ttu-id="76d73-145">Créer un secret Key Vault</span><span class="sxs-lookup"><span data-stu-id="76d73-145">Create Key Vault secret</span></span>

1. <span data-ttu-id="76d73-146">Connectez-vous à votre compte RCS.</span><span class="sxs-lookup"><span data-stu-id="76d73-146">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="76d73-147">Dans l’espace de travail **Fonctionnalités de globalisation**, dans la section **Environnement**, sélectionnez la vignette **Module complémentaire de facturation électronique**.</span><span class="sxs-lookup"><span data-stu-id="76d73-147">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing add-on** tile.</span></span>
3. <span data-ttu-id="76d73-148">Sur la page **Configurations d'environnement**, dans le volet Actions, sélectionnez **Environnement de service**, puis sélectionnez **Paramètres Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="76d73-148">On the **Environment setups** page, on the action Pane, select **Service environment**, and then select **Key Vault parameters**.</span></span>
4. <span data-ttu-id="76d73-149">Sélectionnez **Nouveau** pour créer un secret de Key Vault.</span><span class="sxs-lookup"><span data-stu-id="76d73-149">Select **New** to create a key vault secret.</span></span>
5. <span data-ttu-id="76d73-150">Dans le champ **Nom**, entrez le nom du secret Key Vault.</span><span class="sxs-lookup"><span data-stu-id="76d73-150">In the **Name** field, enter the name of the key vault secret.</span></span> <span data-ttu-id="76d73-151">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="76d73-151">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="76d73-152">Dans le champ **URI Key Vault**, collez le secret à partir d'Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="76d73-152">In the **Key Vault URI** field, paste the secret from Azure Key Vault.</span></span>
7. <span data-ttu-id="76d73-153">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="76d73-153">Select **Save**.</span></span>

## <a name="create-storage-account-secret"></a><span data-ttu-id="76d73-154">Créer un secret de compte de stockage</span><span class="sxs-lookup"><span data-stu-id="76d73-154">Create Storage account secret</span></span>

1. <span data-ttu-id="76d73-155">Accédez à **Administration du système** > **Paramétrage** > **Paramètres du coffre de clés** et sélectionnez un secret pour le coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="76d73-155">Go to **System administration** > **Setup** > **Key Vault parameters**, and select a Key vault secret.</span></span>
2. <span data-ttu-id="76d73-156">Dans la section **Certificats**, sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="76d73-156">In the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="76d73-157">Dans le champ **Nom**, entrez le nom du secret du compte de stockage et dans le champ **Description**, entrez une description.</span><span class="sxs-lookup"><span data-stu-id="76d73-157">In the **Name** field, enter the name of the storage account secret and in the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="76d73-158">Dans le champ **Type**, sélectionnez **Certificat**.</span><span class="sxs-lookup"><span data-stu-id="76d73-158">In the **Type** field, select **Certificate**.</span></span>
5. <span data-ttu-id="76d73-159">Sélectionnez **Sauvegarder**, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="76d73-159">Select **Save**, and then close the page.</span></span>

## <a name="create-a-digital-certificate-secret"></a><span data-ttu-id="76d73-160">Créer un secret de certificat numérique</span><span class="sxs-lookup"><span data-stu-id="76d73-160">Create a digital certificate secret</span></span>

1. <span data-ttu-id="76d73-161">Accédez à **Administration du système** > **Paramétrage** > **Paramètres du coffre de clés** et sélectionnez un secret pour le coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="76d73-161">Go to **System administration** > **Setup** > **Key Vault parameters**, and select a Key vault secret.</span></span>
2. <span data-ttu-id="76d73-162">Dans la section **Certificats**, sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="76d73-162">In the **Certificates** section, select **Add**.</span></span>
3. <span data-ttu-id="76d73-163">Dans le champ **Nom**, entrez le nom du secret du certificat numérique et dans le champ **Description**, entrez une description.</span><span class="sxs-lookup"><span data-stu-id="76d73-163">In the **Name** field, enter the name of the digital certificate secret and in the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="76d73-164">Dans le champ **Type**, sélectionnez **Certificat**.</span><span class="sxs-lookup"><span data-stu-id="76d73-164">In the **Type** field, select **Certificate**.</span></span>
5. <span data-ttu-id="76d73-165">Sélectionnez **Sauvegarder**, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="76d73-165">Select **Save**, and then close the page.</span></span>

## <a name="create-an-electronic-invoicing-add-on-environment"></a><span data-ttu-id="76d73-166">Créer un environnement complémentaire de facturation électronique</span><span class="sxs-lookup"><span data-stu-id="76d73-166">Create an Electronic invoicing add-on environment</span></span>

1. <span data-ttu-id="76d73-167">Connectez-vous à votre compte RCS.</span><span class="sxs-lookup"><span data-stu-id="76d73-167">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="76d73-168">Dans l’espace de travail **Fonctionnalités de globalisation**, dans la section **Environnement**, sélectionnez la vignette **Module complémentaire de facturation électronique**.</span><span class="sxs-lookup"><span data-stu-id="76d73-168">In the **Globalization feature** workspace, in the **Environment** section, select the **Electronic invoicing add-on** tile.</span></span>

## <a name="create-a-service-environment"></a><span data-ttu-id="76d73-169">Créer un environnement de service</span><span class="sxs-lookup"><span data-stu-id="76d73-169">Create a service environment</span></span>

1. <span data-ttu-id="76d73-170">Sur la page **Configurations d’environnement**, dans le volet Actions, sélectionnez **Environnement de service**.</span><span class="sxs-lookup"><span data-stu-id="76d73-170">On the **Environment setups** page, on the Action Pane, select **Service environment**.</span></span>
2. <span data-ttu-id="76d73-171">Sélectionnez **Nouveau** pour créer un environnement de service.</span><span class="sxs-lookup"><span data-stu-id="76d73-171">Select **New** to create a new service environment.</span></span>
3. <span data-ttu-id="76d73-172">Dans le champ **Nom**, entrez le nom de l’environnement de facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="76d73-172">In the **Name** field, enter the name of the e-Invoicing environment.</span></span> <span data-ttu-id="76d73-173">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="76d73-173">In the **Description** field, enter a description.</span></span>
4. <span data-ttu-id="76d73-174">Dans le champ **Secret de jeton SAS de stockage**, sélectionnez le secret du compte de stockage qui doit être utilisé pour authentifier l’accès au compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="76d73-174">In the **Storage SAS token secret** field, select the name of the storage account secret that must be used to authenticate access to the storage account.</span></span>
5. <span data-ttu-id="76d73-175">Dans la section **Utilisateurs**, sélectionnez **Ajouter** pour ajouter un utilisateur autorisé à soumettre des factures électroniques via l'environnement et à se connecter également au compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="76d73-175">In the **Users** section, select **Add** to add a user who is allowed to submit electronic invoices through the environment and also connect to the storage account.</span></span>
6. <span data-ttu-id="76d73-176">Entrez l'alias de l'utilisateur dans le champ **Identifiant utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="76d73-176">In the **User ID** field, enter the alias of the user.</span></span> <span data-ttu-id="76d73-177">Entrez l'adresse e-mail de l'utilisateur dans le champ **E-mail**.</span><span class="sxs-lookup"><span data-stu-id="76d73-177">In the **Email** field, enter the user's email address.</span></span>
7. <span data-ttu-id="76d73-178">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="76d73-178">Select **Save**.</span></span>
8. <span data-ttu-id="76d73-179">Si les factures spécifiques à votre pays/région nécessitent une chaîne de certificats pour appliquer des signatures numériques, dans le volet Actions, sélectionnez **Paramètres Key Vault**, puis **Chaîne de certificats**, et suivez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="76d73-179">If your country/region-specific invoices require a chain of certificates to apply digital signatures, on the Action pane, select **Key Vault parameters**, then select **Chain of certificates**, and follow these steps:</span></span>

    1. <span data-ttu-id="76d73-180">Sélectionnez **Nouveau** pour créer une chaîne de certificats.</span><span class="sxs-lookup"><span data-stu-id="76d73-180">Select **New** to create a chain of certificates.</span></span>
    2. <span data-ttu-id="76d73-181">Dans le champ **Nom**, entrez le nom de l’environnement de la chaîne de certificats.</span><span class="sxs-lookup"><span data-stu-id="76d73-181">In the **Name** field, enter the name of the chain of certificate.</span></span> <span data-ttu-id="76d73-182">Entrez une description dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="76d73-182">In the **Description** field, enter a description.</span></span>
    3. <span data-ttu-id="76d73-183">Dans la section **Certificats**, sélectionnez **Ajouter** pour ajouter un certificat à la chaîne.</span><span class="sxs-lookup"><span data-stu-id="76d73-183">In the **Certificates** section, select **Add** to add a certificate to the chain.</span></span>
    4. <span data-ttu-id="76d73-184">Utilisez le bouton **Vers le haut** ou **Vers le bas** pour changer la position du certificat dans la chaîne.</span><span class="sxs-lookup"><span data-stu-id="76d73-184">Use the **Up** or **Down** button to change the position of the certificate in the chain.</span></span>
    5. <span data-ttu-id="76d73-185">Sélectionnez **Sauvegarder**, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="76d73-185">Select **Save**, and then close the page.</span></span>
    6. <span data-ttu-id="76d73-186">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="76d73-186">Close the page.</span></span>
9. <span data-ttu-id="76d73-187">Sur la page **Environnement de service**, dans le volet Actions, sélectionnez **Publier** pour publier l’environnement dans le Cloud.</span><span class="sxs-lookup"><span data-stu-id="76d73-187">On **Service environment** page, on the Action Pane, select **Publish** to publish the environment to the cloud.</span></span> <span data-ttu-id="76d73-188">La valeur du champ **Statut** est remplacée par **Publié**.</span><span class="sxs-lookup"><span data-stu-id="76d73-188">The value of the **Status** field is changed to **Published**.</span></span>

## <a name="create-a-connected-application"></a><span data-ttu-id="76d73-189">Créer une application connectée</span><span class="sxs-lookup"><span data-stu-id="76d73-189">Create a connected application</span></span>

1. <span data-ttu-id="76d73-190">Sur la page **Configurations d'environnement**, dans le volet Actions, sélectionnez **Applications connectées**.</span><span class="sxs-lookup"><span data-stu-id="76d73-190">On the **Environment setups** page, on the action Pane, select **Connected applications**.</span></span>
2. <span data-ttu-id="76d73-191">Sélectionnez **Nouveau** pour créer une application connectée.</span><span class="sxs-lookup"><span data-stu-id="76d73-191">Select **New** to create a connected application.</span></span>
3. <span data-ttu-id="76d73-192">Dans le champ **Nom**, entrez le nom de l’application à connecter.</span><span class="sxs-lookup"><span data-stu-id="76d73-192">In the **Name** field, enter the name of the application to connect.</span></span>
4. <span data-ttu-id="76d73-193">Dans le champ **Application**, entrez l'URL de l'environnement Finance et Supply Chain Management à connecter.</span><span class="sxs-lookup"><span data-stu-id="76d73-193">In the **Application** field, enter the URL of the Finance and Supply Chain Management environment to connect.</span></span>
4. <span data-ttu-id="76d73-194">Dans le champ **Client**, entrez le client de l'environnement Finance et Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="76d73-194">In the **Tenant** field, enter the tenant of the Finance and Supply Chain Management environment.</span></span>
5. <span data-ttu-id="76d73-195">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="76d73-195">Select **Save**.</span></span>
6. <span data-ttu-id="76d73-196">Dans le volet Actions, sélectionnez **Vérifier la connexion** pour tester la connexion avec l'environnement.</span><span class="sxs-lookup"><span data-stu-id="76d73-196">On the Action Pane, select **Check connection** to test the connection with the environment.</span></span> <span data-ttu-id="76d73-197">Fermez ensuite la page.</span><span class="sxs-lookup"><span data-stu-id="76d73-197">Then close the page.</span></span>

## <a name="link-connected-applications-to-environments"></a><span data-ttu-id="76d73-198">Lier les applications connectées aux environnements</span><span class="sxs-lookup"><span data-stu-id="76d73-198">Link connected applications to environments</span></span>

1. <span data-ttu-id="76d73-199">Sur la page **Configurations d'environnement**, sélectionnez **Nouveau** pour affecter une application connectée à un environnement.</span><span class="sxs-lookup"><span data-stu-id="76d73-199">On the **Environment setups** page, select **New** to assign a connected application to an environment.</span></span>
2. <span data-ttu-id="76d73-200">Sélectionnez une application connectée dans le champ **Application connectée**.</span><span class="sxs-lookup"><span data-stu-id="76d73-200">In the **Connected application** field, select a connected application.</span></span>
3. <span data-ttu-id="76d73-201">Sélectionnez un environnement de service dans le champ **Environnement de service**.</span><span class="sxs-lookup"><span data-stu-id="76d73-201">In the **Service environment** field, select a service environment.</span></span>
4. <span data-ttu-id="76d73-202">Sélectionnez **Sauvegarder**, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="76d73-202">Select **Save**, and then close the page.</span></span>

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance-and-supply-chain-management"></a><span data-ttu-id="76d73-203">Paramétrer l’intégration du module complémentaire de facturation électronique dans Finance et Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="76d73-203">Set up the Electronic invoicing add-on integration in Finance and Supply Chain Management</span></span>

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a><span data-ttu-id="76d73-204">Activer la fonctionnalité d’intégration du module complémentaire de facturation électronique</span><span class="sxs-lookup"><span data-stu-id="76d73-204">Turn on the Electronic invoicing add-on integration feature</span></span>

1. <span data-ttu-id="76d73-205">Connectez-vous à l'instance Finance ou Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="76d73-205">Sign in to your Finance or Supply Chain Management instance.</span></span>
2. <span data-ttu-id="76d73-206">Dans l’espace de travail **Gestion des fonctionnalités**, recherchez la fonctionnalité **Intégration du module complémentaire de facturation électronique**.</span><span class="sxs-lookup"><span data-stu-id="76d73-206">In the **Feature management** workspace, search for the **Electronic invoicing add-on integration** feature.</span></span> <span data-ttu-id="76d73-207">Si cette fonctionnalité n'apparaît pas sur la page, sélectionnez **Rechercher des mises à jour**.</span><span class="sxs-lookup"><span data-stu-id="76d73-207">If this feature doesn't appear on the page, select **Check for updates**.</span></span>
3. <span data-ttu-id="76d73-208">Sélectionnez la fonctionnalité, puis sélectionnez **Activer maintenant**.</span><span class="sxs-lookup"><span data-stu-id="76d73-208">Select the feature, and then select **Enable now**.</span></span>

### <a name="set-up-the-service-endpoint-url"></a><span data-ttu-id="76d73-209">Paramétrer l’URL du point de terminaison de service</span><span class="sxs-lookup"><span data-stu-id="76d73-209">Set up the service endpoint URL</span></span>

1. <span data-ttu-id="76d73-210">Allez dans **Administration de l’organisation \> Paramétrage \> Paramètres des documents électroniques**.</span><span class="sxs-lookup"><span data-stu-id="76d73-210">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="76d73-211">Sur l'onglet **Service d'envoi**, dans le champ **URL du point de terminaison de service**, entrez le point de terminaison de service approprié pour la zone géographique Azure, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="76d73-211">On the **Submission service** tab, in the **Service endpoint URL** field, enter the appropriate service endpoint for your Azure geography, as shown in the following table.</span></span>

    | <span data-ttu-id="76d73-212">Zone géographique Azure Datacenter</span><span class="sxs-lookup"><span data-stu-id="76d73-212">Datacenter Azure geography</span></span> | <span data-ttu-id="76d73-213">URL du point de terminaison de service</span><span class="sxs-lookup"><span data-stu-id="76d73-213">Service endpoint URL</span></span>                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | <span data-ttu-id="76d73-214">Est des États-Unis</span><span class="sxs-lookup"><span data-stu-id="76d73-214">East US</span></span>                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="76d73-215">Ouest des États-Unis</span><span class="sxs-lookup"><span data-stu-id="76d73-215">West US</span></span>                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="76d73-216">Nord de l'UE</span><span class="sxs-lookup"><span data-stu-id="76d73-216">North EU</span></span>                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | <span data-ttu-id="76d73-217">Ouest de l'UE</span><span class="sxs-lookup"><span data-stu-id="76d73-217">West EU</span></span>                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. <span data-ttu-id="76d73-218">Dans le champ **Environnement**, entrez le nom de l’environnement complémentaire de facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="76d73-218">In the **Environment** field, enter the name of the Electronic invoicing add-on environment.</span></span>
4. <span data-ttu-id="76d73-219">Sélectionnez **Sauvegarder**, puis fermez la page.</span><span class="sxs-lookup"><span data-stu-id="76d73-219">Select **Save**, and then close the page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
