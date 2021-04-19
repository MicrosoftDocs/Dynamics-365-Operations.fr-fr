---
title: Configurer des branches parallèles dans un workflow
description: Pour configurer une branche parallèle, exécutez les procédures suivantes dans l’éditeur de workflow.
author: ChrisGarty
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 196043
ms.assetid: dfdae2b8-6a4f-4760-b339-b755c66f3f89
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7b5270660f0dbe4351f0088787468a563d2f36cf
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747805"
---
# <a name="configure-parallel-branches-in-a-workflow"></a><span data-ttu-id="80497-103">Configurer des branches parallèles dans un workflow</span><span class="sxs-lookup"><span data-stu-id="80497-103">Configure parallel branches in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="80497-104">Pour configurer une branche parallèle, exécutez les procédures suivantes dans l’éditeur de workflow.</span><span class="sxs-lookup"><span data-stu-id="80497-104">To configure a parallel branch, complete the following procedures in the workflow editor.</span></span>

<span data-ttu-id="80497-105">Une branche parallèle est principalement un workflow qui s’exécute dans le contexte d’un workflow parent.</span><span class="sxs-lookup"><span data-stu-id="80497-105">A parallel branch is essentially a workflow that runs in the context of a parent workflow.</span></span>

## <a name="name-a-branch"></a><span data-ttu-id="80497-106">Saisir un nom de branche</span><span class="sxs-lookup"><span data-stu-id="80497-106">Name a branch</span></span>

<span data-ttu-id="80497-107">Procédez comme suit pour entrer un nom pour une branche parallèle.</span><span class="sxs-lookup"><span data-stu-id="80497-107">Follow these steps to enter a name for a parallel branch.</span></span>

1. <span data-ttu-id="80497-108">Cliquez avec le bouton droit sur la branche parallèle, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="80497-108">Right-click the parallel branch, and then click **Properties**.</span></span> <span data-ttu-id="80497-109">L’écran **Propriétés** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="80497-109">The **Properties** form is displayed.</span></span>
2. <span data-ttu-id="80497-110">Dans le volet gauche, cliquez sur **Paramètres de base**.</span><span class="sxs-lookup"><span data-stu-id="80497-110">In the left pane, click **Basic Settings**.</span></span>
3. <span data-ttu-id="80497-111">Dans le champ **Nom**, entrez un nom unique pour la branche parallèle.</span><span class="sxs-lookup"><span data-stu-id="80497-111">In the **Name** field, enter a unique name for the parallel branch.</span></span>
4. <span data-ttu-id="80497-112">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="80497-112">Click **Close**.</span></span>

## <a name="design-and-configure-the-elements-of-a-branch"></a><span data-ttu-id="80497-113">Conception et configuration des éléments d’une branche</span><span class="sxs-lookup"><span data-stu-id="80497-113">Design and configure the elements of a branch</span></span>

<span data-ttu-id="80497-114">Pour concevoir et configurer les éléments d’une branche parallèle, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="80497-114">Follow these steps to design and configure the elements of a parallel branch.</span></span>

1. <span data-ttu-id="80497-115">Double-cliquez sur la branche parallèle.</span><span class="sxs-lookup"><span data-stu-id="80497-115">Double-click the parallel branch.</span></span>
2. <span data-ttu-id="80497-116">Faites glisser les éléments de workflow sur le canevas, puis configurez les éléments, comme pour créer un autre workflow.</span><span class="sxs-lookup"><span data-stu-id="80497-116">Drag workflow elements onto the canvas, and then configure the elements, just as you would to create any other workflow.</span></span> <span data-ttu-id="80497-117">Pour plus d’informations, voir [Vue d’ensemble de création de workflows](create-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="80497-117">For more information, see [Create workflows overview](create-workflow.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="80497-118">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="80497-118">Additional resources</span></span>

[<span data-ttu-id="80497-119">Vue d’ensemble de création des workflows</span><span class="sxs-lookup"><span data-stu-id="80497-119">Create workflows overview</span></span>](create-workflow.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]