---
title: Créer un compte de stockage Azure et un coffre de clés
description: Cette rubrique explique comment créer un compte de stockage Azure et un coffre de clés.
author: gionoder
ms.date: 02/12/2021
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
ms.openlocfilehash: b7df4933c1373893e00f48ea3a21bd5af40719a9
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840218"
---
# <a name="create-an-azure-storage-account-and-a-key-vault"></a><span data-ttu-id="834fc-103">Créer un compte de stockage Azure et un coffre de clés</span><span class="sxs-lookup"><span data-stu-id="834fc-103">Create an Azure storage account and a key vault</span></span>

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="834fc-104">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="834fc-104">Prerequisites</span></span>

<span data-ttu-id="834fc-105">Avant de pouvoir effectuer les étapes de cette rubrique, vous devez vérifier que les tâches suivantes ont été réalisées :</span><span class="sxs-lookup"><span data-stu-id="834fc-105">Before you can complete the steps in this topic, you must make sure that the following tasks have been completed:</span></span>

- <span data-ttu-id="834fc-106">Créer une ressource de coffre de clés dans Azure.</span><span class="sxs-lookup"><span data-stu-id="834fc-106">Create a key vault resource in Azure.</span></span> <span data-ttu-id="834fc-107">Pour plus d’informations, voir [À propos de Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/overview).</span><span class="sxs-lookup"><span data-stu-id="834fc-107">For more information, see [About Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/overview).</span></span>
- <span data-ttu-id="834fc-108">Créer un compte de stockage Azure (stockage Blob).</span><span class="sxs-lookup"><span data-stu-id="834fc-108">Create an Azure storage account (Blob storage).</span></span> <span data-ttu-id="834fc-109">Pour plus d’informations, voir [Gestion du compte de stockage Azure](https://docs.microsoft.com/azure/storage/blobs/).</span><span class="sxs-lookup"><span data-stu-id="834fc-109">For more information, see [Maintaining Azure Storage Account](https://docs.microsoft.com/azure/storage/blobs/).</span></span>

## <a name="overview"></a><span data-ttu-id="834fc-110">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="834fc-110">Overview</span></span>

<span data-ttu-id="834fc-111">Dans cette rubrique, vous effectuerez deux étapes principales :</span><span class="sxs-lookup"><span data-stu-id="834fc-111">In this topic, you will complete two main steps:</span></span>

- <span data-ttu-id="834fc-112">Configurer le compte de stockage Azure pour obtenir l’URI du compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="834fc-112">Set up the Azure storage account to get the storage account URI.</span></span>
- <span data-ttu-id="834fc-113">Configurer le coffre de clés pour stocker l’URI du compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="834fc-113">Set up the key vault to store the storage account URI.</span></span>

## <a name="set-up-the-azure-storage-account-to-get-the-storage-account-uri"></a><span data-ttu-id="834fc-114">Configurer le compte de stockage Azure pour obtenir l’URI du compte de stockage</span><span class="sxs-lookup"><span data-stu-id="834fc-114">Set up the Azure storage account to get the storage account URI</span></span>

1. <span data-ttu-id="834fc-115">Ouvrez le compte de stockage que vous prévoyez d’utiliser avec la Facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="834fc-115">Open the storage account that you plan to use with Electronic invoicing.</span></span>
2. <span data-ttu-id="834fc-116">Allez dans **Service Blob** \> **Conteneurs** et créez un nouveau conteneur.</span><span class="sxs-lookup"><span data-stu-id="834fc-116">Go to **Blob service** \> **Containers**, and create a new container.</span></span>
3. <span data-ttu-id="834fc-117">Entrez un nom pour le conteneur et définissez le champ **Niveau d’accès public** sur **Privé (pas d’accès anonyme)**.</span><span class="sxs-lookup"><span data-stu-id="834fc-117">Enter a name for the container, and set the **Public access level** field to **Private (no anonymous access)**.</span></span>
4. <span data-ttu-id="834fc-118">Ouvrez le conteneur et accédez à **Paramètres \> Stratégie d’accès**.</span><span class="sxs-lookup"><span data-stu-id="834fc-118">Open the container, and go to **Settings \> Access policy**.</span></span>
5. <span data-ttu-id="834fc-119">Sélectionnez **Ajouter une stratégie** pour ajouter une stratégie d’accès stockée.</span><span class="sxs-lookup"><span data-stu-id="834fc-119">Select **Add policy** to add a stored access policy.</span></span>
6. <span data-ttu-id="834fc-120">Définissez les champs **Identifiant** et **Autorisations** au besoin.</span><span class="sxs-lookup"><span data-stu-id="834fc-120">Set the **Identifier** and **Permissions** fields as appropriate.</span></span> <span data-ttu-id="834fc-121">Dans le champ **Autorisations**, vous devez sélectionner toutes les autorisations.</span><span class="sxs-lookup"><span data-stu-id="834fc-121">In the **Permissions** field, you should select all permissions.</span></span>

    ![Octroi de l’autorisation de stockage Blob](media/e-Invoicing-services-create-azure-resources-grant-blob-permissions.png)

7. <span data-ttu-id="834fc-123">Entrez les dates de début et d’expiration.</span><span class="sxs-lookup"><span data-stu-id="834fc-123">Enter the start and expiry dates.</span></span> <span data-ttu-id="834fc-124">La date d’expiration doit être dans le futur.</span><span class="sxs-lookup"><span data-stu-id="834fc-124">The expiry date should be in future.</span></span>
8. <span data-ttu-id="834fc-125">Cliquez sur **OK** pour enregistrer la stratégie, puis enregistrez vos modifications du conteneur.</span><span class="sxs-lookup"><span data-stu-id="834fc-125">Select **OK** to save the policy, and then save your changes to the container.</span></span>
9. <span data-ttu-id="834fc-126">Revenez au compte de stockage et ouvrez l’**Explorateur de stockage (version préliminaire)**.</span><span class="sxs-lookup"><span data-stu-id="834fc-126">Return to the storage account, and open **Storage Explorer (preview)**.</span></span>
10. <span data-ttu-id="834fc-127">Cliquez avec le bouton droit sur le conteneur, puis sélectionnez **Obtenir la signature d’accès partagé**.</span><span class="sxs-lookup"><span data-stu-id="834fc-127">Right-click the container, and then select **Get Shared Access Signature**.</span></span>
11. <span data-ttu-id="834fc-128">Dans la boîte de dialogue **Signature d’accès partagé**, copiez et stockez la valeur dans le champ **URI**.</span><span class="sxs-lookup"><span data-stu-id="834fc-128">In the **Shared Access Signature** dialog box, copy and store the value in the **URI** field.</span></span> <span data-ttu-id="834fc-129">Cette valeur sera utilisée dans la procédure suivante et sera appelée *URI de la signature d’accès partagé*.</span><span class="sxs-lookup"><span data-stu-id="834fc-129">This value will be used in the next procedure and will be referred to as the *shared access signature URI*.</span></span>

    ![Sélection et copie de la valeur de l’URI](media/e-Invoicing-services-create-azure-resources-select-and-copy-uri.png)

## <a name="set-up-the-key-vault-to-store-the-storage-account-uri"></a><span data-ttu-id="834fc-131">Configurer le coffre de clés pour stocker l’URI du compte de stockage</span><span class="sxs-lookup"><span data-stu-id="834fc-131">Set up the key vault to store the storage account URI</span></span>

1. <span data-ttu-id="834fc-132">Ouvrez le coffre de clés que vous souhaitez utiliser avec la Facturation électronique.</span><span class="sxs-lookup"><span data-stu-id="834fc-132">Open the key vault that you intend to use with Electronic invoicing.</span></span>
2. <span data-ttu-id="834fc-133">Allez dans **Paramètres** \> **Secrets**, puis sélectionnez **Générer/Importer** pour créer un nouveau secret.</span><span class="sxs-lookup"><span data-stu-id="834fc-133">Go to **Settings** \> **Secrets**, and then select **Generate/Import** to create a new secret.</span></span>
3. <span data-ttu-id="834fc-134">Sur la page **Créer un secret**, dans le champ **Options de téléchargement**, sélectionnez **Manuel**.</span><span class="sxs-lookup"><span data-stu-id="834fc-134">On the **Create a secret** page, in the **Upload options** field, select **Manual**.</span></span>
4. <span data-ttu-id="834fc-135">Entrez le nom du secret.</span><span class="sxs-lookup"><span data-stu-id="834fc-135">Enter the name of the secret.</span></span> <span data-ttu-id="834fc-136">Ce nom sera utilisé lors de la configuration du service dans Regulatory Configuration Service (RCS) et sera appelé *nom du secret du coffre de clés*.</span><span class="sxs-lookup"><span data-stu-id="834fc-136">This name will be used during setup of the service in Regulatory Configuration Service (RCS) and will be referred to as the *key vault secret name*.</span></span>
5. <span data-ttu-id="834fc-137">Dans le champ **Valeur**, sélectionnez **URI de la signature d’accès partagé**, puis sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="834fc-137">In the **Value** field, select **Shared Access Signature URI**, and then select **Create**.</span></span>
6. <span data-ttu-id="834fc-138">Configurez la stratégie d’accès pour accorder à la Facturation électronique le niveau correct d’accès sécurisé au secret que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="834fc-138">Set up the access policy to grant Electronic invoicing the correct level of secure access to the secret you created.</span></span> <span data-ttu-id="834fc-139">Allez dans **Paramètres \> Stratégie d’accès** et sélectionnez **Ajouter une stratégie d’accès**.</span><span class="sxs-lookup"><span data-stu-id="834fc-139">Go to **Settings \> Access policy**, and select **Add Access Policy**.</span></span>
7. <span data-ttu-id="834fc-140">Définissez les autorisations du secret pour les opérations **Obtenir** et **Lister**.</span><span class="sxs-lookup"><span data-stu-id="834fc-140">Set the secret permissions for the **Get** and **List** operations.</span></span>

    ![Autorisation de l’accès au service](media/e-Invoicing-services-create-azure-resources-grant-service-access.png)

8. <span data-ttu-id="834fc-142">Définissez les autorisations du certificat pour les opérations **Obtenir** et **Lister**.</span><span class="sxs-lookup"><span data-stu-id="834fc-142">Set the certificate permissions for **Get** and **List** operations.</span></span>

    ![Octroi de l’autorisation de certificat](media/e-Invoicing-services-create-azure-resources-grant-certificate-permission.png)

9. <span data-ttu-id="834fc-144">Dans le champ **Sélectionnez le principal**, sélectionnez **Aucune sélection**.</span><span class="sxs-lookup"><span data-stu-id="834fc-144">In the **Select principal** field, select **None selected**.</span></span>
10. <span data-ttu-id="834fc-145">Dans la boîte de dialogue **Principal**, sélectionnez le principal en ajoutant **Service de facturation électronique**.</span><span class="sxs-lookup"><span data-stu-id="834fc-145">In the **Principal** dialog box, select the principal by adding **e-Invoicing Service**.</span></span>
11. <span data-ttu-id="834fc-146">Sélectionnez **Ajouter**, puis sélectionnez **Enregistrer les modifications du coffre de clés**.</span><span class="sxs-lookup"><span data-stu-id="834fc-146">Select **Add**, and then select **Save Key Vault changes**.</span></span>
12. <span data-ttu-id="834fc-147">Sur la page **Vue d’ensemble**, copiez la valeur **Nom DNS** du coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="834fc-147">On the **Overview** page, copy the **DNS name** value for the key vault.</span></span> <span data-ttu-id="834fc-148">Cette valeur sera utilisée lors de la configuration du service dans RCS et sera désignée sous le nom *URI du coffre de clés*.</span><span class="sxs-lookup"><span data-stu-id="834fc-148">This value will be used during setup of the service in RCS and will be referred as the *key vault URI*.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]

