---
title: Exécuter et surveiller une expérience
description: Cette rubrique décrit comment exécuter et surveiller une expérience dans un service tiers. Elle décrit également comment apporter des modifications aux variantes après le début de l'expérience.
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
ms.openlocfilehash: ba6fb94033e227790e01676819308bb4f0cd6868
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965211"
---
# <a name="run-and-monitor-an-experiment"></a><span data-ttu-id="c4782-104">Exécuter et surveiller une expérience</span><span class="sxs-lookup"><span data-stu-id="c4782-104">Run and monitor an experiment</span></span>

<span data-ttu-id="c4782-105">Cette rubrique décrit comment exécuter et surveiller votre expérience dans une application tierce et modifier les variantes si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="c4782-105">This topic describes how to run and monitor your experiment in a third-party app, and change variations if needed.</span></span> <span data-ttu-id="c4782-106">Avant d'effectuer les étapes de cette rubrique, vous devez tout d'abord [publier](experimentation-preview-publish.md) votre expérience dans Commerce.</span><span class="sxs-lookup"><span data-stu-id="c4782-106">Before you complete the steps in this topic, you'll first need to [publish](experimentation-preview-publish.md) your experiment in Commerce.</span></span> 

<span data-ttu-id="c4782-107">Le diagramme suivant montre toutes les étapes impliquées dans la configuration et l'exécution d'une expérience sur un site web d'e-commerce dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c4782-107">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="c4782-108">Les étapes supplémentaires sont traitées dans d'autres rubriques.</span><span class="sxs-lookup"><span data-stu-id="c4782-108">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="c4782-109">[ ![Expérimentation parcours utilisateur - Exécuter et surveiller](./media/experimentation_run_monitor.svg) ](./media/experimentation_run_monitor.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="c4782-109">[ ![Experimentation user journey - Run & Monitor](./media/experimentation_run_monitor.svg) ](./media/experimentation_run_monitor.svg#lightbox)</span></span>

<span data-ttu-id="c4782-110">Une fois que vous avez publié vos variantes, toutes les étapes à suivre dans Commerce pour exécuter votre expérience sont terminées.</span><span class="sxs-lookup"><span data-stu-id="c4782-110">After you publish your variations, all of the steps you need to do in Commerce to run your experiment are complete.</span></span> <span data-ttu-id="c4782-111">L'étape suivante consiste à déterminer la variante à montrer à chaque utilisateur lorsqu'il demande une page.</span><span class="sxs-lookup"><span data-stu-id="c4782-111">The next step is determining which variation to show to each user when they request a page.</span></span> <span data-ttu-id="c4782-112">Le service tiers effectue cette détermination, mais vous devez d'abord activer l'expérience dans le service.</span><span class="sxs-lookup"><span data-stu-id="c4782-112">The third-party service makes that determination, but first you have to activate the experiment within the service.</span></span> <span data-ttu-id="c4782-113">Étant donné que les étapes d'activation d'une expérience varient d'un service à l'autre, vous devrez suivre les instructions fournies avec votre service ou fournisseur.</span><span class="sxs-lookup"><span data-stu-id="c4782-113">Since the steps for activating an experiment vary from service to service, you'll need to follow the instructions included with your service or provider.</span></span> <span data-ttu-id="c4782-114">Si l'expérience n'est pas activée, les utilisateurs ne verront que la version par défaut de la page (aucune variante ne sera affichée).</span><span class="sxs-lookup"><span data-stu-id="c4782-114">If the experiment is not activated, users will only see the default version of the page (no variations will be displayed).</span></span>

<span data-ttu-id="c4782-115">Vous devrez prolonger l'expérience suffisamment longtemps pour collecter des données et obtenir des résultats statistiquement valides.</span><span class="sxs-lookup"><span data-stu-id="c4782-115">You'll need to keep the experiment running long enough to gather data for statistically valid results.</span></span> <span data-ttu-id="c4782-116">Utilisez le service tiers pour surveiller les données et les analyses liées à l'expérience pendant l'exécution de l'expérience.</span><span class="sxs-lookup"><span data-stu-id="c4782-116">Use the third-party service to monitor the experiment-related data and analytics while the experiment is running.</span></span>

## <a name="adjust-your-variations"></a><span data-ttu-id="c4782-117">Ajuster vos variantes</span><span class="sxs-lookup"><span data-stu-id="c4782-117">Adjust your variations</span></span>
<span data-ttu-id="c4782-118">Si vous devez modifier vos variantes, suivez les étapes ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="c4782-118">If for any reason you need to modify your variations, follow the steps below.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c4782-119">Si vous apportez des modifications à une expérience en cours dans Commerce ou dans le service tiers, vos résultats peuvent être considérablement affectés.</span><span class="sxs-lookup"><span data-stu-id="c4782-119">If you make changes to a live experiment in Commerce or the third-party service, your results may be significantly impacted.</span></span> <span data-ttu-id="c4782-120">Envisagez de laisser l'expérience suivre son cours, puis de créer une nouvelle expérience pour les changements majeurs.</span><span class="sxs-lookup"><span data-stu-id="c4782-120">Consider letting the experiment run its course and then creating a new experiment for major changes.</span></span>

1. <span data-ttu-id="c4782-121">Dans le générateur de site Commerce, sélectionnez **Expériences** dans le volet de navigation de gauche, puis sélectionnez l'expérience.</span><span class="sxs-lookup"><span data-stu-id="c4782-121">In Commerce site builder, select **Experiments** in the left navigation pane, and then select the experiment.</span></span> 
1. <span data-ttu-id="c4782-122">Sélectionnez la variante que vous souhaitez mettre à jour dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="c4782-122">Select the variation you want to update from the drop-down menu.</span></span>
1. <span data-ttu-id="c4782-123">Apportez les modifications nécessaires, puis affichez un aperçu et publiez les variantes.</span><span class="sxs-lookup"><span data-stu-id="c4782-123">Make any needed changes, and then preview and publish the variations.</span></span> <span data-ttu-id="c4782-124">Pour plus d'informations, consultez [Afficher un aperçu et publier une expérience](experimentation-preview-publish.md).</span><span class="sxs-lookup"><span data-stu-id="c4782-124">For more information, see [Preview and publish an experiment](experimentation-preview-publish.md).</span></span>
1. <span data-ttu-id="c4782-125">Accédez au service tiers pour apporter des modifications liées à la configuration de l'expérience.</span><span class="sxs-lookup"><span data-stu-id="c4782-125">Go to the third-party service to make any experiment setup-related changes.</span></span>
    
## <a name="previous-step"></a><span data-ttu-id="c4782-126">Étape précédente</span><span class="sxs-lookup"><span data-stu-id="c4782-126">Previous step</span></span>
[<span data-ttu-id="c4782-127">Afficher un aperçu et publier une expérience</span><span class="sxs-lookup"><span data-stu-id="c4782-127">Preview and publish an experiment</span></span>](experimentation-preview-publish.md)

## <a name="next-step"></a><span data-ttu-id="c4782-128">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="c4782-128">Next step</span></span>
[<span data-ttu-id="c4782-129">Promouvoir une variante et terminer une expérience</span><span class="sxs-lookup"><span data-stu-id="c4782-129">Promote a variation and complete an experiment</span></span>](experimentation-review-complete.md)
