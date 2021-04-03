---
title: Enregistrer les guides de tâches dans LCS et les rediffuser
description: Cet article explique comment enregistrer les guides de tâches dans Microsoft Dynamics Lifecycle Services (LCS) puis les relire.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7d6102bafc9b55f9eff05bfc4a63c177c6548694
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463260"
---
# <a name="save-task-guides-to-lcs-and-replay-them"></a><span data-ttu-id="34525-103">Enregistrer les guides de tâches dans LCS et les rediffuser</span><span class="sxs-lookup"><span data-stu-id="34525-103">Save task guides to LCS and replay them</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="34525-104">**Détails de l’environnement**</span><span class="sxs-lookup"><span data-stu-id="34525-104">**Environment details**</span></span> 

<span data-ttu-id="34525-105">Microsoft Dynamics 365 Human Resources, qui a été déployé via Microsoft Dynamics Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="34525-105">Microsoft Dynamics 365 Human Resources, which was deployed via Microsoft Dynamics Lifecycle Services (LCS)</span></span>

<span data-ttu-id="34525-106">**Problème**</span><span class="sxs-lookup"><span data-stu-id="34525-106">**Issue**</span></span>

<span data-ttu-id="34525-107">Le client souhaite enregistrer des enregistrements de tâches dans son projet LCS, puis relire les guides de tâche enregistrés.</span><span class="sxs-lookup"><span data-stu-id="34525-107">The customer wants to save new task recordings to his or her LCS project, and then replay the saved task guides.</span></span>

<span data-ttu-id="34525-108">**Résolution**</span><span class="sxs-lookup"><span data-stu-id="34525-108">**Resolution**</span></span>

<span data-ttu-id="34525-109">Pour enregistrer un enregistrement de tâche dans LCS, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="34525-109">Follow these steps to save a task recording to LCS.</span></span>

1. <span data-ttu-id="34525-110">Connectez-vous à LCS, puis sélectionnez le projet.</span><span class="sxs-lookup"><span data-stu-id="34525-110">Sign in to LCS, and select the project.</span></span>
2. <span data-ttu-id="34525-111">Sélectionnez la vignette **Concepteur de processus d’entreprise**.</span><span class="sxs-lookup"><span data-stu-id="34525-111">Select the **Business process modeler** tile.</span></span>
3. <span data-ttu-id="34525-112">Affichez la page dans « l’expérience BPM mise à jour ».</span><span class="sxs-lookup"><span data-stu-id="34525-112">View the page in the "Updated BPM experience."</span></span>
4. <span data-ttu-id="34525-113">Sélectionnez une bibliothèque, puis cliquez sur **Copier**.</span><span class="sxs-lookup"><span data-stu-id="34525-113">Select a library, and then select **Copy**.</span></span>
5. <span data-ttu-id="34525-114">Entrez un nom pour le modèle de Concepteur de processus d’entreprise (BPM).</span><span class="sxs-lookup"><span data-stu-id="34525-114">Enter a name for the Business process modeler (BPM) model.</span></span>
6. <span data-ttu-id="34525-115">Connectez-vous à Human Resources à partir de LCS.</span><span class="sxs-lookup"><span data-stu-id="34525-115">Sign in to Human Resources from LCS.</span></span>
7. <span data-ttu-id="34525-116">Dans le champ **Recherche**, entrer **aide**.</span><span class="sxs-lookup"><span data-stu-id="34525-116">In the **Search** field, enter **help**.</span></span> <span data-ttu-id="34525-117">L’aide Lifecycle Services s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="34525-117">Lifecycle Services Help is opened.</span></span>
8. <span data-ttu-id="34525-118">Sélectionnez le bouton **Actualiser** pour la configuration de l’aide Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="34525-118">Select the **Refresh** button for Lifecycle Services Help configuration.</span></span>

    <span data-ttu-id="34525-119">Votre nouvelle bibliothèque BPM doit s’afficher, et être active.</span><span class="sxs-lookup"><span data-stu-id="34525-119">Your new BPM library should appear, and it should be active.</span></span>

9. <span data-ttu-id="34525-120">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="34525-120">Close the page.</span></span>
10. <span data-ttu-id="34525-121">Créez un enregistrement de tâche.</span><span class="sxs-lookup"><span data-stu-id="34525-121">Create a task recording.</span></span>
11. <span data-ttu-id="34525-122">Lorsque vous avez terminé, sélectionnez **Enregistrer sur Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="34525-122">When you've finished, select **Save to Lifecycle Services**.</span></span>

    ![Enregistrer sur Lifecycle Services](media/task-guides.png)

12. <span data-ttu-id="34525-124">Sélectionnez la bibliothèque et le nœud BPM dans lesquels enregistrer l’enregistrement de tâche.</span><span class="sxs-lookup"><span data-stu-id="34525-124">Select the BPM library and node to save the task recording to.</span></span>

<span data-ttu-id="34525-125">Procédez comme suit pour relire le guide de tâche sur LCS.</span><span class="sxs-lookup"><span data-stu-id="34525-125">Follow these steps to replay a task guide from LCS.</span></span>

1. <span data-ttu-id="34525-126">Démarrez l’enregistreur de tâches.</span><span class="sxs-lookup"><span data-stu-id="34525-126">Start Task recorder.</span></span>
2. <span data-ttu-id="34525-127">Sélectionnez **Ouvrir depuis LCS**.</span><span class="sxs-lookup"><span data-stu-id="34525-127">Select **Open from LCS**.</span></span>
3. <span data-ttu-id="34525-128">Sélectionnez la bibliothèque et le nœud BPM dans lesquels se trouve le guide de tâche enregistré.</span><span class="sxs-lookup"><span data-stu-id="34525-128">Select the library and the BPM node that have the saved task guide.</span></span>
4. <span data-ttu-id="34525-129">Ouvrez le guide de tâche.</span><span class="sxs-lookup"><span data-stu-id="34525-129">Open the task guide.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]