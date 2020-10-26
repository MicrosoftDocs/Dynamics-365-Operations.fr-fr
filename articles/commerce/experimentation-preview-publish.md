---
title: Afficher un aperçu et publier une expérience
description: Cette rubrique décrit comment afficher un aperçu et publier une expérience à partir de Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 91e2e4840a2d53f195d881279050b6415d48b070
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930197"
---
# <a name="preview-and-publish-an-experiment"></a><span data-ttu-id="e4b40-103">Afficher un aperçu et publier une expérience</span><span class="sxs-lookup"><span data-stu-id="e4b40-103">Preview and publish an experiment</span></span>

<span data-ttu-id="e4b40-104">Cette rubrique décrit comment afficher un aperçu et publier votre expérience dans Dynamics 365 Commerce après avoir [connecté votre expérience et modifié vos variantes](experimentation-connect-edit.md).</span><span class="sxs-lookup"><span data-stu-id="e4b40-104">This topic describes how to preview and publish your experiment in Dynamics 365 Commerce after you've [connected your experiment and edited your variations](experimentation-connect-edit.md).</span></span> <span data-ttu-id="e4b40-105">Le diagramme suivant montre toutes les étapes impliquées dans la configuration et l'exécution d'une expérience sur un site web d'e-commerce dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e4b40-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="e4b40-106">Les étapes supplémentaires sont traitées dans d'autres rubriques.</span><span class="sxs-lookup"><span data-stu-id="e4b40-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="e4b40-107">[ ![Expérimentation parcours utilisateur - Afficher un aperçu et publier](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="e4b40-107">[ ![Experimentation user journey - Preview & Publish](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)</span></span>

## <a name="preview-your-experiment-variations"></a><span data-ttu-id="e4b40-108">Afficher un aperçu de vos variantes d'expérience</span><span class="sxs-lookup"><span data-stu-id="e4b40-108">Preview your experiment variations</span></span>
<span data-ttu-id="e4b40-109">Vous pouvez afficher un aperçu de vos variantes et continuer à les modifier jusqu'à ce qu'elles correspondent à ce que vous souhaitez.</span><span class="sxs-lookup"><span data-stu-id="e4b40-109">You can preview your variations and continue editing them until they look the way you want them to.</span></span>

1. <span data-ttu-id="e4b40-110">Dans le générateur de site, utilisez le menu déroulant des variantes sous la barre de commandes pour sélectionner le contenu dont vous souhaitez afficher un aperçu.</span><span class="sxs-lookup"><span data-stu-id="e4b40-110">In site builder, use the variations drop-down menu below the command bar to select the content you want to preview.</span></span> 
1. <span data-ttu-id="e4b40-111">Sélectionner **Afficher un aperçu** dans la barre du haut.</span><span class="sxs-lookup"><span data-stu-id="e4b40-111">Select **Preview** in the top bar.</span></span> <span data-ttu-id="e4b40-112">Un aperçu de la forme que prendra le contenu une fois publié s'affiche.</span><span class="sxs-lookup"><span data-stu-id="e4b40-112">A preview of what the content will look like when it's published is displayed.</span></span>
1. <span data-ttu-id="e4b40-113">Pour afficher un aperçu d'une autre variante, sélectionnez-la dans la liste déroulante des variantes et sélectionnez à nouveau **Afficher un aperçu**.</span><span class="sxs-lookup"><span data-stu-id="e4b40-113">To preview a different variation, select it from the variation drop-down and select **Preview** again.</span></span>

## <a name="publish-your-experiment"></a><span data-ttu-id="e4b40-114">Publier votre expérience</span><span class="sxs-lookup"><span data-stu-id="e4b40-114">Publish your experiment</span></span>
<span data-ttu-id="e4b40-115">Si vous n'utilisez pas de groupe de publication pour planifier la mise en ligne de votre expérience et que vous souhaitez publier immédiatement, sélectionnez **Publier** dans la barre de commandes.</span><span class="sxs-lookup"><span data-stu-id="e4b40-115">If you aren't using a publish group to schedule when your experiment goes live and you want to publish immediately, select **Publish** in the command bar.</span></span> <span data-ttu-id="e4b40-116">Toutes les variantes appartenant à l'expérience seront publiées.</span><span class="sxs-lookup"><span data-stu-id="e4b40-116">All variations that belong to the experiment will be published.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="e4b40-117">Si la page a une URL non publiée, vous devez d'abord publier l'URL, sinon les utilisateurs de votre site web ne pourront pas la voir.</span><span class="sxs-lookup"><span data-stu-id="e4b40-117">If the page has an unpublished URL, you must first publish the URL or it won't be visible to your website users.</span></span> <span data-ttu-id="e4b40-118">Pour plus de détails, consultez [Enregistrer, afficher un aperçu et publier une page](save-preview-publish-page.md).</span><span class="sxs-lookup"><span data-stu-id="e4b40-118">For details, see [Save, preview, and publish a page](save-preview-publish-page.md).</span></span>
    
### <a name="use-publish-groups-to-schedule-when-your-experiment-goes-live"></a><span data-ttu-id="e4b40-119">Utiliser des groupes de publication pour planifier la mise en ligne de votre expérience</span><span class="sxs-lookup"><span data-stu-id="e4b40-119">Use publish groups to schedule when your experiment goes live</span></span>
<span data-ttu-id="e4b40-120">Les variantes créées dans le générateur de site peuvent être planifiées afin d'être publiées à l'aide d'un groupe de publication.</span><span class="sxs-lookup"><span data-stu-id="e4b40-120">Variations created in site builder can be scheduled for publishing by using a publish group.</span></span> <span data-ttu-id="e4b40-121">Dans un groupe de publication, vous pouvez connecter une page ou un fragment à votre expérience en accédant à l'onglet **Expériences** ou à l'onglet **Pages** ou **Fragments**. Pour plus d'informations, consultez la rubrique [Connecter une expérience et modifier les variantes](experimentation-connect-edit.md).</span><span class="sxs-lookup"><span data-stu-id="e4b40-121">Within a publish group, you can connect a page or fragment to your experiment by going to the **Experiments** tab or the **Pages** or **Fragments** tab. For more information, see [Connect an experiment and edit variations](experimentation-connect-edit.md) topic.</span></span> <span data-ttu-id="e4b40-122">Pour plus d'informations sur les groupes de publication, consultez [Utiliser des groupes de publication](publish-groups.md).</span><span class="sxs-lookup"><span data-stu-id="e4b40-122">For information about publish groups, see [Work with publish groups](publish-groups.md).</span></span>

<span data-ttu-id="e4b40-123">Lorsque vous utilisez des groupes de publication avec des expériences, vous devez prendre en compte certaines considérations importantes.</span><span class="sxs-lookup"><span data-stu-id="e4b40-123">When using publish groups with experiments, there are some important considerations to be aware of.</span></span>
- <span data-ttu-id="e4b40-124">Lorsque vous ajoutez à un groupe de publication une page ou un fragment sur lequel une expérience est en cours, l'expérience est supprimée de la page ou du fragment dans le groupe de publication.</span><span class="sxs-lookup"><span data-stu-id="e4b40-124">When you add a page or fragment that has an experiment running on it to a publish group, the experiment will be removed from the page or fragment in the publish group.</span></span>
- <span data-ttu-id="e4b40-125">Les expériences connectées aux pages d'un site en ligne ne sont pas disponibles pour les pages des groupes de publication, et inversement.</span><span class="sxs-lookup"><span data-stu-id="e4b40-125">Experiments that are connected to pages in a live site aren't available to pages within publish groups and vice-versa.</span></span> <span data-ttu-id="e4b40-126">De même, les pages sur lesquelles des expériences sont exécutées dans un site en ligne ne sont pas disponibles pour d'autres expériences dans des groupes de publication, et inversement.</span><span class="sxs-lookup"><span data-stu-id="e4b40-126">Similarly, pages that have experiments running on them in a live site aren't available to other experiments in publish groups and vice versa.</span></span>
- <span data-ttu-id="e4b40-127">Lorsque vous publiez ou planifiez un groupe de publication, tout le contenu du groupe de publication est publié, qu'il existe ou non une expérience associée au groupe de publication.</span><span class="sxs-lookup"><span data-stu-id="e4b40-127">When you publish or schedule a publish group, all content in the publish group is published, regardless of whether there's an experiment associated with the publish group.</span></span>
- <span data-ttu-id="e4b40-128">Étant donné qu'un groupe de publication persiste après sa publication sur un site en ligne, les expériences du groupe de publication persistent également.</span><span class="sxs-lookup"><span data-stu-id="e4b40-128">Because a publish group continues to persist after it's been published to a live site, experiments in the publish group will also persist.</span></span> <span data-ttu-id="e4b40-129">Par conséquent, vous ne pourrez pas associer d'autres expériences à la même page ou au même fragment.</span><span class="sxs-lookup"><span data-stu-id="e4b40-129">Therefore, you won't be able to associate other experiments with the same page or fragment.</span></span> <span data-ttu-id="e4b40-130">Pour éviter cette limitation, supprimez tous les groupes de publication avec des expériences persistantes.</span><span class="sxs-lookup"><span data-stu-id="e4b40-130">To avoid this limitation, delete any publish groups with persisting experiments.</span></span> <span data-ttu-id="e4b40-131">De même, si vous souhaitez supprimer une expérience dans un site en ligne qui existe également dans un groupe de publication, supprimez-la d'abord du groupe de publication.</span><span class="sxs-lookup"><span data-stu-id="e4b40-131">Similarly, if you want to delete an experiment in a live site that also exists in a publish group, delete it from the publish group first.</span></span>

## <a name="previous-step"></a><span data-ttu-id="e4b40-132">Étape précédente</span><span class="sxs-lookup"><span data-stu-id="e4b40-132">Previous step</span></span>
[<span data-ttu-id="e4b40-133">Connecter et modifier une expérience</span><span class="sxs-lookup"><span data-stu-id="e4b40-133">Connect and edit an experiment</span></span>](experimentation-connect-edit.md)

## <a name="next-step"></a><span data-ttu-id="e4b40-134">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="e4b40-134">Next step</span></span>
[<span data-ttu-id="e4b40-135">Exécuter et surveiller une expérience</span><span class="sxs-lookup"><span data-stu-id="e4b40-135">Run and monitor an experiment</span></span>](experimentation-run-monitor.md)
