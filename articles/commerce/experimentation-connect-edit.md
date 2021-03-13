---
title: Connecter une expérience et modifier les variantes
description: Cette rubrique décrit comment connecter une expérience dans un service tiers à Dynamics 365 Commerce et comment modifier les variantes de l'expérience.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 2a33897d01dd98d446c2fb49e417abd9db9f403a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010022"
---
# <a name="connect-an-experiment-and-edit-variations"></a><span data-ttu-id="6b433-103">Connecter une expérience et modifier les variantes</span><span class="sxs-lookup"><span data-stu-id="6b433-103">Connect an experiment and edit variations</span></span>

<span data-ttu-id="6b433-104">Cette rubrique décrit comment connecter votre expérience dans Commerce et apporter des modifications à vos variantes afin qu'elles correspondent à votre hypothèse.</span><span class="sxs-lookup"><span data-stu-id="6b433-104">This topic describes how to connect your experiment in Commerce and make changes to your variations so that they align with your hypothesis.</span></span> 

<span data-ttu-id="6b433-105">Le diagramme suivant montre toutes les étapes impliquées dans la configuration et l'exécution d'une expérience sur un site web d'e-commerce dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6b433-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="6b433-106">Les étapes supplémentaires sont traitées dans d'autres rubriques.</span><span class="sxs-lookup"><span data-stu-id="6b433-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="6b433-107">[ ![Expérimentation parcours utilisateur - Se connecter et modifier](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="6b433-107">[ ![Experimentation user journey - Connect & Edit](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)</span></span>

<span data-ttu-id="6b433-108">Après avoir [configuré votre expérience](experimentation-setup.md) dans un service tiers, vous connecterez l'expérience dans Dynamics 365 Commerce et modifierez les variantes de l'expérience.</span><span class="sxs-lookup"><span data-stu-id="6b433-108">After you've [set up your experiment](experimentation-setup.md) in a third-party service, you'll connect the experiment in Dynamics 365 Commerce and edit the experiment variations.</span></span>

## <a name="planning-considerations"></a><span data-ttu-id="6b433-109">Considérations relatives à la planification</span><span class="sxs-lookup"><span data-stu-id="6b433-109">Planning considerations</span></span>

<span data-ttu-id="6b433-110">Avant de connecter votre expérience dans Commerce, vous devez prendre des décisions qui ont un impact sur la façon dont Commerce gère votre contenu.</span><span class="sxs-lookup"><span data-stu-id="6b433-110">Before you connect your experiment in Commerce, you'll need to make some decisions that impact the way Commerce manages your content.</span></span>

### <a name="determine-the-scope-of-your-experiment"></a><span data-ttu-id="6b433-111">Déterminer la portée de votre expérience</span><span class="sxs-lookup"><span data-stu-id="6b433-111">Determine the scope of your experiment</span></span>
<span data-ttu-id="6b433-112">Lorsque vous connectez une expérience, vous êtes invité à définir la portée de l'expérience.</span><span class="sxs-lookup"><span data-stu-id="6b433-112">When you connect an experiment, you are prompted to define the scope of the experiment.</span></span> <span data-ttu-id="6b433-113">La portée des expériences est définie comme **partielle** ou **complète**.</span><span class="sxs-lookup"><span data-stu-id="6b433-113">Experiments are defined as **partial** scope or **entire** scope.</span></span>
- <span data-ttu-id="6b433-114">Choisissez **partielle** si vous souhaitez mener une expérience sur une partie spécifique d'une page.</span><span class="sxs-lookup"><span data-stu-id="6b433-114">Choose **partial** if you want to conduct an experiment on a specific portion of a page.</span></span> <span data-ttu-id="6b433-115">Si vous sélectionnez cette option, vous devez identifier les modules inclus dans l'expérience.</span><span class="sxs-lookup"><span data-stu-id="6b433-115">If you select this option, you must identify which modules are included in the experiment.</span></span> <span data-ttu-id="6b433-116">Les modifications apportées à des parties de la page ou du fragment par défaut qui ne sont pas liés à l'expérience sont automatiquement synchronisés entre les variantes.</span><span class="sxs-lookup"><span data-stu-id="6b433-116">Changes that are made to parts of the default page or fragment that aren't related to the experiment are automatically synchronized across variations.</span></span>
- <span data-ttu-id="6b433-117">Choisissez **complète** si vous souhaitez mener une expérience sur une page entière ou sur un fragment entier.</span><span class="sxs-lookup"><span data-stu-id="6b433-117">Choose **entire** if you want to conduct an experiment on an entire page or fragment.</span></span> <span data-ttu-id="6b433-118">Des copies distinctes de la page ou du fragment par défaut sont créées.</span><span class="sxs-lookup"><span data-stu-id="6b433-118">Separate copies of the default page or fragment are created.</span></span> <span data-ttu-id="6b433-119">Vous n'aurez pas à sélectionner les modules inclus dans l'expérience, car l'ensemble de la surface de modification peut être modifiée.</span><span class="sxs-lookup"><span data-stu-id="6b433-119">You won't have to select which modules are included in the experiment because the whole editing surface is available to change.</span></span> <span data-ttu-id="6b433-120">Vous pouvez ajouter, supprimer ou réorganiser les modules selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="6b433-120">You can add, delete, or re-order modules as needed.</span></span> <span data-ttu-id="6b433-121">Toutefois, si des modifications sont apportées à la page ou au fragment par défaut auquel l'expérience est associée, ces modifications doivent être synchronisées manuellement sur toutes les variantes.</span><span class="sxs-lookup"><span data-stu-id="6b433-121">However, if any changes are made to the default page or fragment that the experiment is associated with, those changes have to be manually synchronized across all variations.</span></span>

<!-- not to editors, we're adding an image here to illustrate the difference. it will help.) -->

> [!NOTE]
> <span data-ttu-id="6b433-122">Si vous associez votre expérience à une page qui utilise une disposition, vous pouvez uniquement définir l'expérience comme **complète**.</span><span class="sxs-lookup"><span data-stu-id="6b433-122">If you associate your experiment with a page that uses a layout, you can only scope the experiment as **entire**.</span></span>

### <a name="decide-if-you-want-to-schedule-when-your-experiment-is-published"></a><span data-ttu-id="6b433-123">Décidez si vous souhaitez planifier la publication de votre expérience</span><span class="sxs-lookup"><span data-stu-id="6b433-123">Decide if you want to schedule when your experiment is published</span></span>
<span data-ttu-id="6b433-124">Si vous souhaitez planifier la publication de votre expérience sur votre site en ligne, assurez-vous que le contenu que vous souhaitez associer à l'expérience est disponible dans un groupe de publication *avant* de connecter l'expérience.</span><span class="sxs-lookup"><span data-stu-id="6b433-124">If you want to schedule when your experiment is published to your live site, make sure the content you want to associate with the experiment is available in a publish group *before* you connect the experiment.</span></span> 

<span data-ttu-id="6b433-125">Pour plus d'informations sur les groupes de publication, voir [Utiliser des groupes de publication](publish-groups.md).</span><span class="sxs-lookup"><span data-stu-id="6b433-125">For more information about publish groups, refer to [Work with publish groups](publish-groups.md).</span></span>


## <a name="connect-your-experiment"></a><span data-ttu-id="6b433-126">Connecter votre expérience</span><span class="sxs-lookup"><span data-stu-id="6b433-126">Connect your experiment</span></span>
<span data-ttu-id="6b433-127">Pour connecter votre expérience, vous allez lancer l'assistant **Connecter l'expérience**.</span><span class="sxs-lookup"><span data-stu-id="6b433-127">To connect your experiment, you'll launch the **Connect experiment** wizard.</span></span> <span data-ttu-id="6b433-128">L'assistant vous fait parcourir les étapes requises pour connecter votre expérience.</span><span class="sxs-lookup"><span data-stu-id="6b433-128">The wizard walks you through the steps required to connect your experiment.</span></span> <span data-ttu-id="6b433-129">Lorsque vous avez terminé l'assistant, votre expérience est connectée et les variantes sont créées et prêtes à être modifiées.</span><span class="sxs-lookup"><span data-stu-id="6b433-129">When you complete the wizard, your experiment is connected and variations are created and ready to be edited.</span></span>

<span data-ttu-id="6b433-130">Pour démarrer la connexion de votre expérience dans le générateur de site Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="6b433-130">To get started connecting your experiment in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="6b433-131">Pour lancer l'assistant **Connecter l'expérience**, sélectionnez **Expériences** dans le volet de navigation de gauche, puis sélectionnez **Connecter**.</span><span class="sxs-lookup"><span data-stu-id="6b433-131">To launch the **Connect experiment** wizard, select **Experiments** in the left navigation pane, and then select **Connect**.</span></span> <span data-ttu-id="6b433-132">Vous pouvez également accéder à l'assistant à partir d'un éditeur de fragment ou de page en le modifiant et en sélectionnant **Connecter l'expérience** sur la barre de commandes.</span><span class="sxs-lookup"><span data-stu-id="6b433-132">Alternatively, you can access the wizard from a page or fragment editor by editing it and selecting **Connect experiment** on the command bar.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6b433-133">Une page peut être connectée à une seule expérience à la fois.</span><span class="sxs-lookup"><span data-stu-id="6b433-133">A page can only be connected to one experiment at a time.</span></span> <span data-ttu-id="6b433-134">Pour connecter une page à une autre expérience, supprimez d'abord l'expérience à laquelle la page est actuellement connectée.</span><span class="sxs-lookup"><span data-stu-id="6b433-134">To connect a page to a different experiment, first delete the experiment that the page is currently connected to.</span></span>

1. <span data-ttu-id="6b433-135">Choisissez la page ou le fragment sur lequel vous souhaitez exécuter votre expérience.</span><span class="sxs-lookup"><span data-stu-id="6b433-135">Choose the page or fragment you want to run your experiment on.</span></span>
1. <span data-ttu-id="6b433-136">Définissez la portée de l'expérimentation sur **partielle** ou **complète**, en fonction du choix que vous avez fait dans la section [Déterminer la portée de votre expérience](#determine-the-scope-of-your-experiment) ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="6b433-136">Set the experimentation scope to **partial** or **entire**, based on the choice you made in the [Determine the scope of your experiment](#determine-the-scope-of-your-experiment) section above.</span></span>
    > [!NOTE]
    > <span data-ttu-id="6b433-137">L'indicateur de la fonctionnalité **Expérimenter sur des pages ou des fragments** doit être activé si vous souhaitez expérimenter sur une page complète ou sur un fragment complet.</span><span class="sxs-lookup"><span data-stu-id="6b433-137">The **Experiment on pages or fragments** feature flag must be enabled if you want to experiment on a full page or fragment.</span></span> <span data-ttu-id="6b433-138">Reportez-vous à la rubrique [Expérimentation dans Dynamics 365 Commerce](experimentation-overview.md) pour plus d'informations.</span><span class="sxs-lookup"><span data-stu-id="6b433-138">Refer to the [Experimentation in Dynamics 365 Commerce](experimentation-overview.md) topic for more information.</span></span>
    
1. <span data-ttu-id="6b433-139">Dans la dernière étape de l'assistant, sélectionnez **Générer des variantes et quitter l'assistant**.</span><span class="sxs-lookup"><span data-stu-id="6b433-139">In the final step of the wizard, select **Generate variations and exit wizard**.</span></span> <span data-ttu-id="6b433-140">Des variantes sont créées pour l'expérience.</span><span class="sxs-lookup"><span data-stu-id="6b433-140">Variations are created for the experiment.</span></span> 

## <a name="edit-your-variations"></a><span data-ttu-id="6b433-141">Modifier vos variantes</span><span class="sxs-lookup"><span data-stu-id="6b433-141">Edit your variations</span></span>
<span data-ttu-id="6b433-142">Lorsque vous quittez l'assistant, des variantes sont créées pour vous.</span><span class="sxs-lookup"><span data-stu-id="6b433-142">When you exit the wizard, variations are created for you.</span></span> 

<span data-ttu-id="6b433-143">Vous allez ensuite modifier les variantes afin qu'elles reflètent les choix que vous devez vérifier dans l'hypothèse de l'expérience.</span><span class="sxs-lookup"><span data-stu-id="6b433-143">Next, you'll edit the variations so they reflect the choices that you need to verify in the experiment hypothesis.</span></span> <span data-ttu-id="6b433-144">Choisissez l'une des procédures suivantes qui correspond à la portée que vous avez choisie pour votre expérience dans la section [Déterminer la portée de votre expérience](#determine-the-scope-of-your-experiment) ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="6b433-144">Choose one of following procedures that corresponds to the scope you chose for your experiment in the [Determine the scope of your experiment](#determine-the-scope-of-your-experiment) section above.</span></span>

### <a name="edit-variations-for-experiments-with-partial-scope"></a><span data-ttu-id="6b433-145">Modifier les variantes des expériences avec une portée partielle</span><span class="sxs-lookup"><span data-stu-id="6b433-145">Edit variations for experiments with partial scope</span></span>
<span data-ttu-id="6b433-146">Suivez ces étapes si vous avez défini la portée de votre expérience comme **partielle** dans l'assistant **Connecter l'expérience**.</span><span class="sxs-lookup"><span data-stu-id="6b433-146">Follow these steps if you defined the scope of your experiment as **partial** in the **Connect experiment** wizard.</span></span>

1. <span data-ttu-id="6b433-147">Dans la vue d'éditeur, utilisez le menu déroulant des variantes sous la barre de commandes pour modifier chaque variante en fonction de votre hypothèse d'origine.</span><span class="sxs-lookup"><span data-stu-id="6b433-147">In editor view, use the variations drop-down menu below the command bar to edit each variation based on your original hypothesis.</span></span> <span data-ttu-id="6b433-148">Vous pouvez également établir une variante de contrôle ou de base en laissant l'une des variantes inchangée.</span><span class="sxs-lookup"><span data-stu-id="6b433-148">You may also want to establish a control or base variation by leaving one of the variations unchanged.</span></span>
1. <span data-ttu-id="6b433-149">Sélectionnez le module sur lequel expérimenter, sélectionnez les points de suspension (...), puis sélectionnez **Ajouter à l'expérience**.</span><span class="sxs-lookup"><span data-stu-id="6b433-149">Select the module to be experimented on, select the ellipsis (...), and then select **Add to experiment**.</span></span>

### <a name="edit-variations-for-experiments-with-entire-scope"></a><span data-ttu-id="6b433-150">Modifier les variantes des expériences avec une portée complète</span><span class="sxs-lookup"><span data-stu-id="6b433-150">Edit variations for experiments with entire scope</span></span>
<span data-ttu-id="6b433-151">Si vous avez défini la portée de votre expérience comme **complète** dans l'assistant **Connecter l'expérience**, utilisez le menu déroulant des variantes sous la barre de commandes dans la vue d'éditeur pour modifier chaque variante en fonction de votre hypothèse d'origine.</span><span class="sxs-lookup"><span data-stu-id="6b433-151">If you defined the scope of your experiment as **entire** in the **Connect experiment** wizard, while in editor view, use the variations drop-down menu below the command bar to edit each variation based on your original hypothesis.</span></span> 

> [!NOTE]
> <span data-ttu-id="6b433-152">Dans les deux cas, vous pouvez également établir une variante de contrôle ou de base en laissant l'une des variantes inchangée.</span><span class="sxs-lookup"><span data-stu-id="6b433-152">In either case, you may also want to establish a control or base variation by leaving one of the variations unchanged.</span></span>

## <a name="previous-step"></a><span data-ttu-id="6b433-153">Étape précédente</span><span class="sxs-lookup"><span data-stu-id="6b433-153">Previous step</span></span>
[<span data-ttu-id="6b433-154">Configurer une expérience</span><span class="sxs-lookup"><span data-stu-id="6b433-154">Set up an experiment</span></span>](experimentation-setup.md) 


## <a name="next-step"></a><span data-ttu-id="6b433-155">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="6b433-155">Next step</span></span>
[<span data-ttu-id="6b433-156">Afficher un aperçu et publier une expérience</span><span class="sxs-lookup"><span data-stu-id="6b433-156">Preview and publish an experiment</span></span>](experimentation-preview-publish.md)
