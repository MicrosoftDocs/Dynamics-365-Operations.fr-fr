---
title: Délégation d'éléments de travail dans un workflow
description: Si vous pensez vous absenter du bureau ou être dans l'incapacité d'agir sur des éléments de travail, vous pouvez déléguer ou réaffecter vos éléments de travail à d'autres utilisateurs.
author: jasongre
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 44dc747543e32b54729d12c89a401b0187e25a61
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189957"
---
# <a name="delegate-work-items-in-a-workflow"></a><span data-ttu-id="50a46-103">Délégation d'éléments de travail dans un workflow</span><span class="sxs-lookup"><span data-stu-id="50a46-103">Delegate work items in a workflow</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

## <a name="manually-delegate-a-work-item"></a><span data-ttu-id="50a46-104">Délégation manuelle d'un élément de travail</span><span class="sxs-lookup"><span data-stu-id="50a46-104">Manually delegate a work item</span></span>

<span data-ttu-id="50a46-105">Pour déléguer un élément de travail individuel, sélectionnez l'option **Déléguer** dans le menu **Workflow** puis entrez l'utilisateur à qui déléguer l'élément de travail en y ajoutant un commentaire.</span><span class="sxs-lookup"><span data-stu-id="50a46-105">To delegate an individual work item, select the **Delegate** option in the **Workflow** menu and then enter the user to be delegated to along with a comment.</span></span> <span data-ttu-id="50a46-106">Cela réaffectera l'élément de travail à cet utilisateur afin qu'il puisse l'exécuter.</span><span class="sxs-lookup"><span data-stu-id="50a46-106">This will reassign the work item to that user so they can complete it.</span></span>

## <a name="automatically-delegate-work-items"></a><span data-ttu-id="50a46-107">Déléguer automatiquement des éléments de travail</span><span class="sxs-lookup"><span data-stu-id="50a46-107">Automatically delegate work items</span></span>

<span data-ttu-id="50a46-108">Si vous prévoyez de vous absenter du bureau ou être indisponible d'une manière quelconque pour agir sur des éléments de travail pendant une période donnée, vous pouvez automatiquement déléguer de nouveaux éléments de travail à d'autres utilisateurs à l'aide de la page **Options utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="50a46-108">If you plan to be out of the office or otherwise unavailable to act on work items for a period of time, you can automatically delegate new work items to other users using the **User options** page.</span></span>

### <a name="set-up-automatic-delegation"></a><span data-ttu-id="50a46-109">Paramétrage de la délégation automatique</span><span class="sxs-lookup"><span data-stu-id="50a46-109">Set up automatic delegation</span></span>
1. <span data-ttu-id="50a46-110">Accédez à **Commun > Paramétrage > Options utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="50a46-110">Go to **Common > Setup > User options**.</span></span>
2. <span data-ttu-id="50a46-111">Cliquez sur **Workflow** et vérifiez que la section Délégation est développée.</span><span class="sxs-lookup"><span data-stu-id="50a46-111">Click the **Workflow** tab. Make sure the Delegation section is expanded.</span></span> <span data-ttu-id="50a46-112">Pour configurer le système de sorte à déléguer vos éléments de travail automatiquement à d'autres utilisateurs, vous devez créer des règles de délégation lorsque certains types d'éléments de travail sont délégués.</span><span class="sxs-lookup"><span data-stu-id="50a46-112">To configure the system to automatically delegate your work items to other users, you must create delegation rules, which specify when certain types of work items are delegated.</span></span> <span data-ttu-id="50a46-113">Pour créer une règle de délégation, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="50a46-113">Follow these steps to create a delegation rule.</span></span>  
3. <span data-ttu-id="50a46-114">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="50a46-114">Click **Add**.</span></span>
4. <span data-ttu-id="50a46-115">Sélectionnez une option dans le champ **Portée**.</span><span class="sxs-lookup"><span data-stu-id="50a46-115">In the **Scope** field, select an option.</span></span>
    - <span data-ttu-id="50a46-116">Tout – Permet de déléguer tous les éléments de travail qui vous sont attribués.</span><span class="sxs-lookup"><span data-stu-id="50a46-116">All – Delegate all work items that are assigned to you.</span></span>
    - <span data-ttu-id="50a46-117">Module – Permet de déléguer uniquement les éléments de travail associés à un type donné de workflow.</span><span class="sxs-lookup"><span data-stu-id="50a46-117">Module – Delegate only the work items that are related to a specific type of workflow.</span></span> <span data-ttu-id="50a46-118">Si cette option est sélectionnée, vous devez sélectionner le type de workflow dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="50a46-118">If you select this option, you must select the type of workflow in the Name field.</span></span>
    - <span data-ttu-id="50a46-119">Workflow – Permet de déléguer uniquement les éléments de travail associés à un workflow donné.</span><span class="sxs-lookup"><span data-stu-id="50a46-119">Workflow – Delegate only the work items that are related to a specific workflow.</span></span> <span data-ttu-id="50a46-120">Si cette option est sélectionnée, vous devez sélectionner le workflow dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="50a46-120">If you select this option, you must select the workflow in the Name field.</span></span>  
5. <span data-ttu-id="50a46-121">Dans le champ **Déléguer**, sélectionnez l'utilisateur auquel déléguer les éléments de travail.</span><span class="sxs-lookup"><span data-stu-id="50a46-121">In the **Delegate** field, select the user to delegate the work items to.</span></span> <span data-ttu-id="50a46-122">Les champs Date/heure de début et Date/heure de fin permettent de spécifier à quel moment vous souhaitez que les éléments de travail soient automatiquement délégués.</span><span class="sxs-lookup"><span data-stu-id="50a46-122">Use the Start date/time and End date/time fields to specify when you want the work items to be automatically delegated.</span></span>  
6. <span data-ttu-id="50a46-123">Dans le champ **Date/heure de début**, entrez une date et une heure.</span><span class="sxs-lookup"><span data-stu-id="50a46-123">In the **Start date/time** field, enter a date and time.</span></span>
7. <span data-ttu-id="50a46-124">Dans le champ **Date/heure de fin**, entrez une date et une heure.</span><span class="sxs-lookup"><span data-stu-id="50a46-124">In the **End date/time** field, enter a date and time.</span></span>
8. <span data-ttu-id="50a46-125">Activez la case à cocher **Activé** pour activer la règle de délégation.</span><span class="sxs-lookup"><span data-stu-id="50a46-125">Select the **Enabled** check box to activate the delegation rule.</span></span> <span data-ttu-id="50a46-126">Si vous avez sélectionné **Module** comme Portée, vous devez alors sélectionner le module dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="50a46-126">If you selected **Module** as the Scope, then you must select the module in the Name field.</span></span> <span data-ttu-id="50a46-127">Si vous avez sélectionné **Workflow** comme Portée, vous devez alors sélectionner le workflow spécifique à déléguer dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="50a46-127">If you selected **Workflow** as the Scope, then you must select the specific workflow to delegate in the Name field.</span></span>  
9. <span data-ttu-id="50a46-128">Dans le champ **Commentaire**, entrez un commentaire expliquant le motif de la délégation des éléments de travail.</span><span class="sxs-lookup"><span data-stu-id="50a46-128">In the **Comment** field, enter a comment that explains why you are delegating the work items.</span></span>

