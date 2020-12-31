---
title: Partager les configurations ER dans RCS/le référentiel global avec des organisations externes
description: Cette rubrique explique comment partager des configurations d’états électroniques (ER) dans Microsoft Regulatory Configuration Services (RCS)/le référentiel global directement avec des organisations externes.
author: JaneA07
manager: AnnBe
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 04c46824123906eccbfff18a03974c8043729e0a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443232"
---
# <a name="share-electronic-reporting-er-configurations-in-regulatory-configuration-services-rcs-global-repository-with-external-organizations"></a><span data-ttu-id="719ee-103">Partager des configurations d’états électroniques (ER) dans Regulatory Configuration Services (RCS)/le référentiel global avec des organisations externes.</span><span class="sxs-lookup"><span data-stu-id="719ee-103">Share Electronic reporting (ER) configurations in Regulatory Configuration Services (RCS) Global repository with external organizations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="719ee-104">Vous pouvez utiliser Microsoft Regulatory Configuration Services (RCS) pour partager des configurations d’états électroniques (ER) et les publier dans des organisations externes.</span><span class="sxs-lookup"><span data-stu-id="719ee-104">You can use Microsoft Regulatory Configuration Services (RCS) to share Electronic reporting (ER) configurations and then publish them to external organizations.</span></span>

<span data-ttu-id="719ee-105">Les procédures suivantes expliquent comment un utilisateur RCS peut partager une version d’une configuration ER qui a été configurée dans une instance RCS avec une organisation externe.</span><span class="sxs-lookup"><span data-stu-id="719ee-105">The following procedures explain how an RCS user can share a version of an ER configuration that has been configured in an RCS instance with an external organization.</span></span> <span data-ttu-id="719ee-106">Avant d’exécuter cette procédure, vous devez d’abord effectuer ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="719ee-106">Before you can complete those procedures, you must complete the following prerequisites:</span></span>

- <span data-ttu-id="719ee-107">Accédez à une instance RCS.</span><span class="sxs-lookup"><span data-stu-id="719ee-107">Access an RCS instance.</span></span>
- <span data-ttu-id="719ee-108">Créez un fournisseur de configuration actif.</span><span class="sxs-lookup"><span data-stu-id="719ee-108">Create an active configuration provider.</span></span> <span data-ttu-id="719ee-109">Pour plus d’informations, voir la procédure [Créer des fournisseurs de configuration et les marquer comme actif](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="719ee-109">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
- <span data-ttu-id="719ee-110">Créez et téléchargez une nouvelle version de configuration ER.</span><span class="sxs-lookup"><span data-stu-id="719ee-110">Create and upload a new version of an ER configuration.</span></span> <span data-ttu-id="719ee-111">Pour plus d’informations, voir [Créer et télécharger une nouvelle version d’une configuration d’état électronique (ER)](rcs-global-repo-upload.md).</span><span class="sxs-lookup"><span data-stu-id="719ee-111">For more information, see [Create and upload a new version of an Electronic reporting (ER) configuration](rcs-global-repo-upload.md).</span></span>

<span data-ttu-id="719ee-112">Vous devez également vous assurer qu’un environnement RCS est configuré pour votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="719ee-112">You must also make sure that an RCS environment is provisioned for your company.</span></span>

1. <span data-ttu-id="719ee-113">Dans une application Finance and Operations, allez dans **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.</span><span class="sxs-lookup"><span data-stu-id="719ee-113">In a Finance and Operations app, go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="719ee-114">Si vous n’avez pas d’environnement RCS configuré dans votre société, sélectionnez **Regulatory services – Configuration externe** et suivez les instructions pour en mettre un en service.</span><span class="sxs-lookup"><span data-stu-id="719ee-114">If no RCS environment is provisioned for your company, select **Regulatory services – Configuration external**, and then follow the instructions to provision one.</span></span>

<span data-ttu-id="719ee-115">Si un environnement RCS a déjà été configuré pour votre entreprise, utilisez l’URL de la page pour y accéder en sélectionnant l’option de connexion.</span><span class="sxs-lookup"><span data-stu-id="719ee-115">If an RCS environment has been already provisioned for your company, use the page URL to access it by selecting the sign-in option.</span></span>

## <a name="verify-the-configuration-that-you-want-to-share"></a><span data-ttu-id="719ee-116">Vérifier la configuration à partager</span><span class="sxs-lookup"><span data-stu-id="719ee-116">Verify the configuration that you want to share</span></span>

<span data-ttu-id="719ee-117">Suivez ces étapes pour vérifier que la configuration que vous souhaitez partager a déjà été téléchargée dans le référentiel global.</span><span class="sxs-lookup"><span data-stu-id="719ee-117">Follow these steps to verify that the configuration that you want to share has already been uploaded to the Global repository.</span></span>

1. <span data-ttu-id="719ee-118">Dans l’espace de travail **États électroniques**, sélectionnez **Référentiels** comme fournisseur de configuration.</span><span class="sxs-lookup"><span data-stu-id="719ee-118">In the **Electronic reporting** workspace, select **Repositories** for your configuration provider.</span></span>

    ![Fournisseurs de configuration](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/1_RCS_Repo_for_config_provider.JPG)

2. <span data-ttu-id="719ee-120">Select **Référentiel global** \> **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="719ee-120">Select **Global repository** \> **Open**.</span></span>
3. <span data-ttu-id="719ee-121">Recherchez la configuration à partager.</span><span class="sxs-lookup"><span data-stu-id="719ee-121">Search for the configuration that you want to share.</span></span> <span data-ttu-id="719ee-122">Vous pouvez utiliser le champ de filtre pour affiner votre recherche.</span><span class="sxs-lookup"><span data-stu-id="719ee-122">You can use the filter field to narrow your search.</span></span> <span data-ttu-id="719ee-123">Si vous ne trouvez pas la configuration dans le référentiel global, suivez les étapes indiquées dans [Créer et télécharger une nouvelle version d’une configuration d’état électronique (ER)](rcs-global-repo-upload.md).</span><span class="sxs-lookup"><span data-stu-id="719ee-123">If you can't find the configuration in the Global repository, follow the steps in [Create and upload a new version of an Electronic reporting (ER) configuration](rcs-global-repo-upload.md).</span></span>

## <a name="share-er-configurations-with-external-organizations"></a><span data-ttu-id="719ee-124">Partager des configurations ER avec des organisations externes</span><span class="sxs-lookup"><span data-stu-id="719ee-124">Share ER configurations with external organizations</span></span>

<span data-ttu-id="719ee-125">Une fois qu’une configuration a été créée sous votre fournisseur de configuration, vous pouvez la partager directement avec des organisations externes en utilisant le raccourci **Partagé avec** de la page **Référentiel de configuration globale**.</span><span class="sxs-lookup"><span data-stu-id="719ee-125">After a configuration has been created under your configuration provider, you can share it directly with external organizations by using the **Shared with** FastTab on the **Global configuration repository** page.</span></span>

1. <span data-ttu-id="719ee-126">Dans l’espace de travail **États électroniques**, sélectionnez **Référentiels** comme fournisseur de configuration.</span><span class="sxs-lookup"><span data-stu-id="719ee-126">In the **Electronic reporting** workspace, select **Repositories** for your configuration provider.</span></span>
2. <span data-ttu-id="719ee-127">Select **Référentiel global** \> **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="719ee-127">Select **Global repository** \> **Open**.</span></span> 
3. <span data-ttu-id="719ee-128">Sélectionnez la configuration à partager.</span><span class="sxs-lookup"><span data-stu-id="719ee-128">Select the configuration that you want to share.</span></span>
4. <span data-ttu-id="719ee-129">Dans le raccourci **Partagé avec**, sélectionnez **Organisation**.</span><span class="sxs-lookup"><span data-stu-id="719ee-129">On the **Shared with** FastTab, select **Organization**.</span></span>

    ![Raccourci Partagé avec](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/1_RCS_Repo_for_Share_with_org.JPG)

5. <span data-ttu-id="719ee-131">Dans la boîte de dialogue, entrez le nom de domaine de l’organisation externe, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="719ee-131">In the dialog box, enter the domain name for the external organization, and then select **OK**.</span></span>

    ![Boîte de dialogue Partager la version de la configuration avec l’organisation externe](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/1_RCS_Repo_for_Share_with_form.JPG)

<span data-ttu-id="719ee-133">La configuration est partagée avec l’organisation externe et est disponible pour cette organisation dans le référentiel global.</span><span class="sxs-lookup"><span data-stu-id="719ee-133">The configuration is shared with the external organization and is available to that organization in the Global repository.</span></span> <span data-ttu-id="719ee-134">De là, elle peut être importée dans l’instance de RCS de l’organisation ou dans ses instances des applications Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="719ee-134">From there, it can be imported into the organization's instance of RCS or into its instances of Finance and Operations apps.</span></span>

![Configuration partagée avec une organisation externe](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/1_RCS_Repo_for_Share_with_test.com)

6. <span data-ttu-id="719ee-136">Pour annuler le partage d’une configuration qui a été précédemment partagée avec une organisation externe, sélectionnez la configuration et cliquez sur **Annuler le partage**, puis cliquez sur **OK**</span><span class="sxs-lookup"><span data-stu-id="719ee-136">To unshare a configuration that has been previously shared with an external organization, select the configuration and click **Unshare**, and then select **OK**</span></span>
