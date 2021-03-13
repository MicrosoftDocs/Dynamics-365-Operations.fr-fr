---
title: Promouvoir une variante et terminer une expérience
description: Cette rubrique décrit comment promouvoir une variante réussie et réaliser une expérience dans Dynamics 365 Commerce.
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
ms.openlocfilehash: 25cccbeae5c263a3032eeebf2fc5335e22c1415a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009923"
---
# <a name="promote-a-variation-and-complete-an-experiment"></a><span data-ttu-id="69d47-103">Promouvoir une variante et terminer une expérience</span><span class="sxs-lookup"><span data-stu-id="69d47-103">Promote a variation and complete an experiment</span></span>

<span data-ttu-id="69d47-104">Cette rubrique décrit comment promouvoir la variante qui a produit les meilleurs résultats dans votre expérience et comment terminer le test.</span><span class="sxs-lookup"><span data-stu-id="69d47-104">This topic describes how to promote the variation that produced the best results in your experiment, and how to complete the experiment.</span></span> <span data-ttu-id="69d47-105">Le diagramme suivant montre toutes les étapes impliquées dans la configuration et l'exécution d'une expérience sur un site web d'e-commerce dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="69d47-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="69d47-106">Les étapes supplémentaires sont traitées dans d'autres rubriques.</span><span class="sxs-lookup"><span data-stu-id="69d47-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="69d47-107">[ ![Expérimentation parcours utilisateur - Examiner et terminer](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="69d47-107">[ ![Experimentation user journey - Review & Complete](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)</span></span>

<span data-ttu-id="69d47-108">Après avoir [réalisé votre expérience](experimentation-run-monitor.md) et collecté suffisamment de données pour déterminer la variante que vous souhaitez utiliser sur votre site en ligne, vous allez promouvoir la variante et terminer l'expérience.</span><span class="sxs-lookup"><span data-stu-id="69d47-108">After you've [run your experiment](experimentation-run-monitor.md) and collected sufficient data to determine which variation you want to use on your live site, you'll promote the variation and end the experiment.</span></span>

## <a name="promote-a-variation"></a><span data-ttu-id="69d47-109">Promouvoir une variante</span><span class="sxs-lookup"><span data-stu-id="69d47-109">Promote a variation</span></span>
<span data-ttu-id="69d47-110">Utilisez les données et les analyses liées à l'expérience dans le service tiers pour décider quelle variante a produit les meilleurs résultats.</span><span class="sxs-lookup"><span data-stu-id="69d47-110">Use the data and analytics related to the experiment in the third-party service to decide which variation produced the best results.</span></span> <span data-ttu-id="69d47-111">Vous pouvez ensuite la promouvoir en remplaçant le contenu actuel sur le site en ligne par la variante la plus performante afin qu'elle soit disponible pour tous les utilisateurs de votre site web.</span><span class="sxs-lookup"><span data-stu-id="69d47-111">You can then promote it by replacing the current content on the live site with the winning variation so that it's available to all users of your website.</span></span>

<span data-ttu-id="69d47-112">Pour promouvoir la variante la plus performante, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="69d47-112">To promote the winning variation, follow these steps.</span></span> 

1. <span data-ttu-id="69d47-113">Dans le générateur de site Commerce, sélectionnez **Expériences** dans le volet de navigation de gauche, puis sélectionnez l'expérience.</span><span class="sxs-lookup"><span data-stu-id="69d47-113">In Commerce site builder, select **Experiments** in the left navigation pane, and then select the experiment.</span></span>
1. <span data-ttu-id="69d47-114">Dans la barre de commande, sélectionnez **Terminer l'expérience**.</span><span class="sxs-lookup"><span data-stu-id="69d47-114">On the command bar, select **Complete experiment**.</span></span>
1. <span data-ttu-id="69d47-115">Dans la boîte de dialogue **Terminer l'expérience**, sélectionnez **Examiner les données de l'expérience**.</span><span class="sxs-lookup"><span data-stu-id="69d47-115">In the **Complete the experiment** dialog box, select **Review the experiment data**.</span></span> <span data-ttu-id="69d47-116">Le service tiers s'ouvre et vous permet de valider les métriques et de déterminer la variante la plus performante.</span><span class="sxs-lookup"><span data-stu-id="69d47-116">The third-party service opens where you can validate the metrics and determine which variation performed the best.</span></span>
1. <span data-ttu-id="69d47-117">Dans la boîte de dialogue **Terminer l'expérience**, sélectionnez la variante la plus performante, puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="69d47-117">In the **Complete the experiment** dialog box, select the winning variation, and then select **Next**.</span></span>
1. <span data-ttu-id="69d47-118">Ouvrez le service tiers et arrêtez l'expérience.</span><span class="sxs-lookup"><span data-stu-id="69d47-118">Open the third-party service and stop the experiment.</span></span>
1. <span data-ttu-id="69d47-119">Dans le générateur de site, sélectionnez **Terminer** pour remplacer la page d'origine en ligne et publier la variante la plus performante afin qu'elle soit disponible pour tous les utilisateurs de votre site web.</span><span class="sxs-lookup"><span data-stu-id="69d47-119">In site builder, select **Complete** to overwrite the original live page and publish the winning variation so that it's available to all users of your website.</span></span> 

> [!NOTE]
> <span data-ttu-id="69d47-120">Si vous choisissez de conserver la page en ligne actuelle et de ne pas publier de variante, sélectionnez **Republier la page d'origine**.</span><span class="sxs-lookup"><span data-stu-id="69d47-120">If you choose to keep the current live page and not publish a variation, select **Republish the original page**.</span></span>

## <a name="delete-your-experiment"></a><span data-ttu-id="69d47-121">Supprimer votre expérience</span><span class="sxs-lookup"><span data-stu-id="69d47-121">Delete your experiment</span></span>
<span data-ttu-id="69d47-122">Bien qu'il ne soit pas nécessaire de supprimer une expérience terminée dans Commerce, vous pouvez choisir de la supprimer pour économiser de l'espace ou nettoyer votre espace de travail.</span><span class="sxs-lookup"><span data-stu-id="69d47-122">While it's not required that you delete a completed experiment in Commerce, you may choose to delete it to save space or clean up your workspace.</span></span> 

<span data-ttu-id="69d47-123">Pour supprimer une expérience dans le générateur de site Commerce, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="69d47-123">To delete an experiment in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="69d47-124">Sélectionnez **Expériences** dans le volet de navigation de gauche, puis sélectionnez l'expérience.</span><span class="sxs-lookup"><span data-stu-id="69d47-124">Select **Experiments** in the left navigation pane, and then select the experiment.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="69d47-125">Si l'expérience est toujours active, arrêtez-la dans le service tiers avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="69d47-125">If the experiment is still active, stop the experiment in the third-party service before proceeding.</span></span>
1. <span data-ttu-id="69d47-126">Dans la barre de commande, sélectionnez **Annuler la publication** pour supprimer le contenu de la variante du site en ligne.</span><span class="sxs-lookup"><span data-stu-id="69d47-126">On the command bar, select **Unpublish**  to remove the variation content from the live site.</span></span>
1. <span data-ttu-id="69d47-127">Sélectionnez **Supprimer** pour supprimer l'expérience.</span><span class="sxs-lookup"><span data-stu-id="69d47-127">Select **Delete** to delete the experiment.</span></span>

## <a name="previous-step"></a><span data-ttu-id="69d47-128">Étape précédente</span><span class="sxs-lookup"><span data-stu-id="69d47-128">Previous step</span></span>
[<span data-ttu-id="69d47-129">Exécuter et surveiller une expérience</span><span class="sxs-lookup"><span data-stu-id="69d47-129">Run and monitor an experiment</span></span>](experimentation-run-monitor.md)
