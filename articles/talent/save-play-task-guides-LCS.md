---
title: Enregistrer les guides de tâches dans LCS et les rediffuser
description: Cette rubrique explique comment enregistrer les guides de tâches dans Microsoft Dynamics Lifecycle Services (LCS) puis les relire.
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 40b4c3154a04a557b8a670e1f1ae3722c71122fe
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "304386"
---
# <a name="save-task-guides-to-lcs-and-replay-them"></a><span data-ttu-id="c57d1-103">Enregistrer les guides de tâches dans LCS et les rediffuser</span><span class="sxs-lookup"><span data-stu-id="c57d1-103">Save task guides to LCS and replay them</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c57d1-104">**Détails de l'environnement**</span><span class="sxs-lookup"><span data-stu-id="c57d1-104">**Environment details**</span></span> 

<span data-ttu-id="c57d1-105">Microsoft Dynamics 365 for Talent, qui a été déployé via Microsoft Dynamics Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="c57d1-105">Microsoft Dynamics 365 for Talent, which was deployed via Microsoft Dynamics Lifecycle Services (LCS)</span></span>

<span data-ttu-id="c57d1-106">**Problème**</span><span class="sxs-lookup"><span data-stu-id="c57d1-106">**Issue**</span></span>

<span data-ttu-id="c57d1-107">Le client souhaite enregistrer des enregistrements de tâches dans son projet LCS, puis relire les guides de tâche enregistrés.</span><span class="sxs-lookup"><span data-stu-id="c57d1-107">The customer wants to save new task recordings to his or her LCS project, and then replay the saved task guides.</span></span>

<span data-ttu-id="c57d1-108">**Résolution**</span><span class="sxs-lookup"><span data-stu-id="c57d1-108">**Resolution**</span></span>

<span data-ttu-id="c57d1-109">Pour enregistrer un enregistrement de tâche dans LCS, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="c57d1-109">Follow these steps to save a task recording to LCS.</span></span>

1. <span data-ttu-id="c57d1-110">Connectez-vous à LCS, puis sélectionnez le projet.</span><span class="sxs-lookup"><span data-stu-id="c57d1-110">Sign in to LCS, and select the project.</span></span>
2. <span data-ttu-id="c57d1-111">Sélectionnez la vignette **Concepteur de processus d'entreprise**.</span><span class="sxs-lookup"><span data-stu-id="c57d1-111">Select the **Business process modeler** tile.</span></span>
3. <span data-ttu-id="c57d1-112">Affichez la page dans « l'expérience BPM mise à jour ».</span><span class="sxs-lookup"><span data-stu-id="c57d1-112">View the page in the "Updated BPM experience."</span></span>
4. <span data-ttu-id="c57d1-113">Sélectionnez une bibliothèque, puis cliquez sur **Copier**.</span><span class="sxs-lookup"><span data-stu-id="c57d1-113">Select a library, and then select **Copy**.</span></span>
5. <span data-ttu-id="c57d1-114">Entrez un nom pour le modèle de Concepteur de processus d'entreprise (BPM).</span><span class="sxs-lookup"><span data-stu-id="c57d1-114">Enter a name for the Business process modeler (BPM) model.</span></span>
6. <span data-ttu-id="c57d1-115">Connectez-vous à Talent depuis LCS.</span><span class="sxs-lookup"><span data-stu-id="c57d1-115">Sign in to Talent from LCS.</span></span>
7. <span data-ttu-id="c57d1-116">Dans le champ **Recherche**, entrer **aide**.</span><span class="sxs-lookup"><span data-stu-id="c57d1-116">In the **Search** field, enter **help**.</span></span> <span data-ttu-id="c57d1-117">L'aide Lifecycle Services s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="c57d1-117">Lifecycle Services Help is opened.</span></span>
8. <span data-ttu-id="c57d1-118">Sélectionnez le bouton **Actualiser** pour la configuration de l'aide Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="c57d1-118">Select the **Refresh** button for Lifecycle Services Help configuration.</span></span>

    <span data-ttu-id="c57d1-119">Votre nouvelle bibliothèque BPM doit s'afficher, et être active.</span><span class="sxs-lookup"><span data-stu-id="c57d1-119">Your new BPM library should appear, and it should be active.</span></span>

9. <span data-ttu-id="c57d1-120">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="c57d1-120">Close the page.</span></span>
10. <span data-ttu-id="c57d1-121">Créez un enregistrement de tâche.</span><span class="sxs-lookup"><span data-stu-id="c57d1-121">Create a task recording.</span></span>
11. <span data-ttu-id="c57d1-122">Lorsque vous avez terminé, sélectionnez **Enregistrer sur Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="c57d1-122">When you've finished, select **Save to Lifecycle Services**.</span></span>

    ![Enregistrer sur Lifecycle Services](media/task-guides.png)

12. <span data-ttu-id="c57d1-124">Sélectionnez la bibliothèque et le nœud BPM dans lesquels enregistrer l'enregistrement de tâche.</span><span class="sxs-lookup"><span data-stu-id="c57d1-124">Select the BPM library and node to save the task recording to.</span></span>

<span data-ttu-id="c57d1-125">Procédez comme suit pour relire le guide de tâche sur LCS.</span><span class="sxs-lookup"><span data-stu-id="c57d1-125">Follow these steps to replay a task guide from LCS.</span></span>

1. <span data-ttu-id="c57d1-126">Démarrez l'enregistreur de tâches.</span><span class="sxs-lookup"><span data-stu-id="c57d1-126">Start Task recorder.</span></span>
2. <span data-ttu-id="c57d1-127">Sélectionnez **Ouvrir depuis LCS**.</span><span class="sxs-lookup"><span data-stu-id="c57d1-127">Select **Open from LCS**.</span></span>
3. <span data-ttu-id="c57d1-128">Sélectionnez la bibliothèque et le nœud BPM dans lesquels se trouve le guide de tâche enregistré.</span><span class="sxs-lookup"><span data-stu-id="c57d1-128">Select the library and the BPM node that have the saved task guide.</span></span>
4. <span data-ttu-id="c57d1-129">Ouvrez le guide de tâche.</span><span class="sxs-lookup"><span data-stu-id="c57d1-129">Open the task guide.</span></span>
