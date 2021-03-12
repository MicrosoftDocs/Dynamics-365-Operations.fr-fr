---
title: Créer des configurations ER dans RCS et les télécharger dans le référentiel global
description: Cette rubrique explique comment créer une configuration d’état électronique (ER) dans Microsoft Regulatory Configuration Services (RCS) et comment la télécharger dans le référentiel global.
author: JaneA07
manager: AnnBe
ms.date: 09/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: ef12c911c8953b181db1c0eff0874a3d8cfcb3da
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005746"
---
# <a name="create-er-configurations-in-regulatory-configuration-services-rcs-and-upload-them-to-the-global-repository"></a><span data-ttu-id="72045-103">Créer des configurations ER dans Regulatory Configuration Services (RCS) et les télécharger dans le référentiel global</span><span class="sxs-lookup"><span data-stu-id="72045-103">Create ER configurations in Regulatory Configuration Services (RCS) and upload them to the Global repository</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="72045-104">Vous pouvez utiliser Microsoft Regulatory Configuration Services (RCS) pour concevoir des configurations d’états électroniques (ER) et les publier afin qu’elles puissent être utilisées dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="72045-104">You can use Microsoft Regulatory Configuration Services (RCS) to design Electronic reporting (ER) configurations and publish them so that they can be used in your organization.</span></span>

<span data-ttu-id="72045-105">Les procédures suivantes expliquent comment un utilisateur ayant un rôle d’administrateur système ou de développeur d’états électroniques peut créer une version dérivée d’une configuration ER qui a été configurée dans une instance RCS, puis la télécharger dans le référentiel global.</span><span class="sxs-lookup"><span data-stu-id="72045-105">The following procedures explain how a user in the System Administrator or Electronic Reporting Developer role can create a derived version of an ER configuration that has been configured in an RCS instance, and then upload the derived configuration to the Global repository.</span></span> 

<span data-ttu-id="72045-106">Avant d’exécuter cette procédure, vous devez d’abord effectuer ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="72045-106">Before you can complete those procedures, you must complete the following prerequisites:</span></span>

- <span data-ttu-id="72045-107">Accédez à une instance RCS.</span><span class="sxs-lookup"><span data-stu-id="72045-107">Access an RCS instance.</span></span>
- <span data-ttu-id="72045-108">Créez un fournisseur de configuration actif.</span><span class="sxs-lookup"><span data-stu-id="72045-108">Create an active configuration provider.</span></span> <span data-ttu-id="72045-109">Pour plus d’informations, voir la procédure [Créer des fournisseurs de configuration et les marquer comme actif](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="72045-109">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

<span data-ttu-id="72045-110">Vous devez également vous assurer qu’un environnement RCS est configuré pour votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="72045-110">You must also make sure that an RCS environment is provisioned for your company.</span></span>

1. <span data-ttu-id="72045-111">Dans une application Finance and Operations, allez dans **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="72045-111">In a Finance and Operations app, go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="72045-112">Si vous n’avez pas d’environnement RCS configuré dans votre société, sélectionnez **Regulatory services – Configuration externe** et suivez les instructions pour en mettre un en service.</span><span class="sxs-lookup"><span data-stu-id="72045-112">If no RCS environment is provisioned for your company, select **Regulatory services – Configuration external**, and then follow the instructions to provision one.</span></span>

<span data-ttu-id="72045-113">Si un environnement RCS a déjà été configuré pour votre entreprise, utilisez l’URL de la page pour y accéder en sélectionnant l’option de connexion.</span><span class="sxs-lookup"><span data-stu-id="72045-113">If an RCS environment has been already provisioned for your company, use the page URL to access it by selecting the sign-in option.</span></span>

## <a name="create-a-derived-version-of-a-configuration-in-rcs"></a><span data-ttu-id="72045-114">Créer une version dérivée d’une configuration dans RCS</span><span class="sxs-lookup"><span data-stu-id="72045-114">Create a derived version of a configuration in RCS</span></span>

1. <span data-ttu-id="72045-115">Dans l’espace de travail **États électroniques**, vérifiez que vous disposez d’un fournisseur de configuration actif pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="72045-115">In the **Electronic reporting** workspace, verify that you have an active configuration provider for your organization.</span></span> 
2. <span data-ttu-id="72045-116">Sélectionnez **Configurations des états**.</span><span class="sxs-lookup"><span data-stu-id="72045-116">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="72045-117">Sélectionnez la configuration dont vous souhaitez dériver une nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="72045-117">Select the configuration that you want to derive a new version from.</span></span> <span data-ttu-id="72045-118">Vous pouvez utiliser le champ de filtre au-dessus de l’arborescence pour affiner votre recherche.</span><span class="sxs-lookup"><span data-stu-id="72045-118">You can use the filter field above the tree to narrow your search.</span></span>
4. <span data-ttu-id="72045-119">Sélectionnez **Créer une configuration** \> **Provenant du nom**.</span><span class="sxs-lookup"><span data-stu-id="72045-119">Select **Create configuration** \> **Derive from Name**.</span></span>
5. <span data-ttu-id="72045-120">Saisissez un nom et une description, puis sélectionnez **Créer une configuration** pour créer une nouvelle version dérivée.</span><span class="sxs-lookup"><span data-stu-id="72045-120">Enter a name and description, and then select **Create configuration** to create a new derived version.</span></span>
6. <span data-ttu-id="72045-121">Sélectionnez la configuration nouvellement dérivée, ajoutez une description de la version, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="72045-121">Select the newly derived configuration, add a description of the version, and then select **OK**.</span></span> <span data-ttu-id="72045-122">Le statut de la configuration est remplacé par **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="72045-122">The status of the configuration to is changed to **Completed**.</span></span>

![Nouvelle version de la configuration dans RCS](media/RCS_CompleteConfig.JPG)

> [!NOTE]
> <span data-ttu-id="72045-124">Lorsque l’état de la configuration est modifié, vous pouvez recevoir un message d’erreur de validation lié aux applications connectées.</span><span class="sxs-lookup"><span data-stu-id="72045-124">When the configuration status is changed, you might receive a validation error message that is related to the connected applications.</span></span> <span data-ttu-id="72045-125">Pour désactiver la validation, dans le volet Actions de l’onglet **Configurations**, sélectionnez **Paramètres utilisateur**, puis définissez l’option **Ignorer la validation lors du changement d’état de la configuration et rebaser** sur **Oui**</span><span class="sxs-lookup"><span data-stu-id="72045-125">To turn off the validation, on the Action Pane on the **Configurations** tab, select **User parameters**, and then set the **Skip validation at configuration's status change and rebase** option to **Yes**</span></span> 

## <a name="upload-a-configuration-to-the-global-repository"></a><span data-ttu-id="72045-126">Télécharger une configuration dans le référentiel global</span><span class="sxs-lookup"><span data-stu-id="72045-126">Upload a configuration to the Global repository</span></span>

<span data-ttu-id="72045-127">Pour partager une configuration nouvelle ou dérivée avec votre organisation, vous pouvez la télécharger dans le référentiel global.</span><span class="sxs-lookup"><span data-stu-id="72045-127">To share a new or derived configuration with your organization, you can upload it to the Global repository.</span></span>

1. <span data-ttu-id="72045-128">Sélectionnez la version terminée de la configuration, puis sélectionnez **Télécharger dans le référentiel**.</span><span class="sxs-lookup"><span data-stu-id="72045-128">Select the completed version of the configuration, and then select **Upload into repository**.</span></span>
2. <span data-ttu-id="72045-129">Sélectionnez l’option **Global (Microsoft)**, puis sélectionnez **Télécharger**.</span><span class="sxs-lookup"><span data-stu-id="72045-129">Select the **Global (Microsoft)** option, and then select **Upload**.</span></span>

    ![Télécharger dans les options du référentiel](media/RCS_Upload_to_GlobalRepo_options.JPG)

3. <span data-ttu-id="72045-131">Dans la boîte de dialogue de confirmation, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="72045-131">In the confirmation message box, select **Yes**.</span></span> 
4. <span data-ttu-id="72045-132">Mettez à jour la description de la version selon vos besoins, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="72045-132">Update the description of the version as required, and then select **OK**.</span></span> 

<span data-ttu-id="72045-133">Le statut de la configuration est mis à jour sur **Partager** et la configuration est téléchargée dans le référentiel global.</span><span class="sxs-lookup"><span data-stu-id="72045-133">The status of the configuration is updated to **Share**, and the configuration is uploaded to the Global repository.</span></span> <span data-ttu-id="72045-134">Vous pouvez ensuite l’utiliser de plusieurs manières :</span><span class="sxs-lookup"><span data-stu-id="72045-134">From there, you can work with it in the following ways:</span></span>

- <span data-ttu-id="72045-135">Vous pouvez l’importer dans votre instance Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="72045-135">Import it into your Dynamics 365 instance.</span></span> <span data-ttu-id="72045-136">Pour plus d’informations, voir [(ER) Importer les configurations depuis RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).</span><span class="sxs-lookup"><span data-stu-id="72045-136">For more information, see [(ER) Import configurations from RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).</span></span>
- <span data-ttu-id="72045-137">Vous pouvez la partager avec un tiers ou une organisation externe, consultez [RCS Partager des configurations d’états électroniques (ER) avec des organisations externes](rcs-global-repo-share-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="72045-137">Share it with a third party or an external organization, see [RCS Share Electronic reporting (ER) configurations with external organizations](rcs-global-repo-share-configuration.md)</span></span>

    ![Version de configuration Intrastat Contoso dérivée dans le référentiel global](media/RCS_Config_upload_GlobalRepo.JPG)

## <a name="delete-a-configuration-from-the-global-repository"></a><span data-ttu-id="72045-139">Supprimer une configuration du référentiel Global</span><span class="sxs-lookup"><span data-stu-id="72045-139">Delete a configuration from the Global repository</span></span>
<span data-ttu-id="72045-140">Effectuez les étapes suivantes pour supprimer une configuration que votre organisation a créée.</span><span class="sxs-lookup"><span data-stu-id="72045-140">Complete the following steps to delete a configuration that your organization has created.</span></span>

1. <span data-ttu-id="72045-141">Dans l’espace de travail **États électroniques**, vérifiez que votre fournisseur de configuration est **Actif**.</span><span class="sxs-lookup"><span data-stu-id="72045-141">In the **Electronic reporting** workspace, verify that your configuration provider is **Active**.</span></span> <span data-ttu-id="72045-142">Pour plus d’informations, voir la procédure [Créer des fournisseurs de configuration et les marquer comme actif](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="72045-142">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
2. <span data-ttu-id="72045-143">Sur votre fournisseur de configuration actif, sélectionnez **Référentiel**.</span><span class="sxs-lookup"><span data-stu-id="72045-143">On your active configuration provider, select **repository**.</span></span>
3. <span data-ttu-id="72045-144">Sélectionnez le type de référentiel **Global** et sélectionnez **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="72045-144">Select the repository type **Global**, and select **Open**.</span></span>
4. <span data-ttu-id="72045-145">Sur le FastTab **Filtre**, recherchez la configuration que vous souhaitez supprimer en utilisant la fonctionnalité **Filtre**.</span><span class="sxs-lookup"><span data-stu-id="72045-145">On the **Filter** FastTab, find the configuration that you want to delete by using the **Filter** functionality.</span></span>
5. <span data-ttu-id="72045-146">Sur le FastTab **Version**, sélectionnez la version de la configuration que vous souhaitez supprimer, puis sélectionnez **Supprimer** :</span><span class="sxs-lookup"><span data-stu-id="72045-146">On the **Version** FastTab, select the version of the configuration that you want to delete, and then select **Delete**:</span></span>

    ![Supprimer une configuration du référentiel global](media/RCS_Delete_from_GlobalRepo.JPG)

6. <span data-ttu-id="72045-148">Dans la boîte de dialogue de confirmation, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="72045-148">In the confirmation message box, select **Yes**.</span></span>

    ![Supprimer le message de confirmation de la version de la configuration](media/RCS_Delete_from_GlobalRepo_Msg.JPG)
 
<span data-ttu-id="72045-150">La version de la configuration est supprimée et un message de confirmation s’affiche.</span><span class="sxs-lookup"><span data-stu-id="72045-150">The configuration version is deleted, and confirmation message is shown.</span></span> 

> [!NOTE]
> <span data-ttu-id="72045-151">Les configurations ne peuvent être supprimées que par le fournisseur de configuration qui les a créées.</span><span class="sxs-lookup"><span data-stu-id="72045-151">Configurations can only be deleted by the Configuration provider that created them.</span></span> <span data-ttu-id="72045-152">Si la configuration a été partagée avec une autre organisation, le partage de la configuration devra être annulé avant que vous ne la supprimiez.</span><span class="sxs-lookup"><span data-stu-id="72045-152">If the configuration has been shared with another organization, the configuration will need to be unshared before you delete it.</span></span>
 
