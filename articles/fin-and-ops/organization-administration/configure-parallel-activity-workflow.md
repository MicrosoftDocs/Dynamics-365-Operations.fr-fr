---
title: Configurer des activités parallèles dans un workflow
description: Pour configurer une activité parallèle, exécutez les procédures suivantes dans l'éditeur de workflow.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 01c1fa876dd66ba6f0e1cdcecff56f424e117bd9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "308435"
---
# <a name="configure-parallel-activities-in-a-workflow"></a><span data-ttu-id="7d251-103">Configurer des activités parallèles dans un workflow</span><span class="sxs-lookup"><span data-stu-id="7d251-103">Configure parallel activities in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7d251-104">Pour configurer une activité parallèle, exécutez les procédures suivantes dans l'éditeur de workflow.</span><span class="sxs-lookup"><span data-stu-id="7d251-104">To configure a parallel activity, complete the following procedures in the workflow editor.</span></span>

<span data-ttu-id="7d251-105">Une activité parallèle comprend des branches de workflow qui s'exécutent simultanément.</span><span class="sxs-lookup"><span data-stu-id="7d251-105">A parallel activity consists of workflow branches that run at the same time.</span></span>

## <a name="name-a-parallel-activity"></a><span data-ttu-id="7d251-106">Saisie d'un nom pour une activité parallèle</span><span class="sxs-lookup"><span data-stu-id="7d251-106">Name a parallel activity</span></span>

<span data-ttu-id="7d251-107">Procédez comme suit pour entrer un nom pour une activité parallèle.</span><span class="sxs-lookup"><span data-stu-id="7d251-107">Follow these steps to enter a name for a parallel activity.</span></span>

1. <span data-ttu-id="7d251-108">Cliquez avec le bouton droit sur l'activité parallèle, puis cliquez sur **Propriétés** pour ouvrir l'écran **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="7d251-108">Right-click the parallel activity, and then click **Properties** to open the **Properties** form.</span></span>
2. <span data-ttu-id="7d251-109">Dans le volet gauche, cliquez sur **Paramètres de base**.</span><span class="sxs-lookup"><span data-stu-id="7d251-109">In the left pane, click **Basic Settings**.</span></span>
3. <span data-ttu-id="7d251-110">Dans le champ **Nom**, entrez un nom unique pour l'activité parallèle.</span><span class="sxs-lookup"><span data-stu-id="7d251-110">In the **Name** field, enter a unique name for the parallel activity.</span></span>
4. <span data-ttu-id="7d251-111">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="7d251-111">Click **Close**.</span></span>

## <a name="configure-the-branches-of-a-parallel-activity"></a><span data-ttu-id="7d251-112">Configuration des branches d'une activité parallèle</span><span class="sxs-lookup"><span data-stu-id="7d251-112">Configure the branches of a parallel activity</span></span>

<span data-ttu-id="7d251-113">Pour ajouter et configurer les branches de cette activité parallèle, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="7d251-113">Follow these steps to add and configure the branches of this parallel activity.</span></span>

1. <span data-ttu-id="7d251-114">Double-cliquez sur l'activité parallèle pour afficher les branches de l'activité parallèle.</span><span class="sxs-lookup"><span data-stu-id="7d251-114">Double-click the parallel activity to display the branches of the parallel activity.</span></span>
2. <span data-ttu-id="7d251-115">Pour ajouter une branche, faites glisser l'élément **Branche** de la zone **Élément de workflow** vers un point d'insertion sur le canevas.</span><span class="sxs-lookup"><span data-stu-id="7d251-115">To add a branch, drag the **Branch** element from the **Workflow elements** area to an insertion point on the canvas.</span></span> <span data-ttu-id="7d251-116">La figure suivante présente un point d'insertion.</span><span class="sxs-lookup"><span data-stu-id="7d251-116">The following figure shows an insertion point.</span></span>

    ![Point d'insertion](./media/workflow_insertionpoint.gif)

    > [!NOTE]
    > <span data-ttu-id="7d251-118">L'ordre des branches est sans importance, car toutes les branches d'une activité parallèle s'exécutent simultanément.</span><span class="sxs-lookup"><span data-stu-id="7d251-118">The order of the branches is not important because all the branches of a parallel activity run at the same time.</span></span>

3. <span data-ttu-id="7d251-119">Pour configurer chaque branche, voir [Configuration d'une branche parallèle](configure-parallel-branch-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="7d251-119">To configure each branch, see [Configure a parallel branch](configure-parallel-branch-workflow.md).</span></span>
