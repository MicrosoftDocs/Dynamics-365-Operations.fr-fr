---
title: Délégation d'éléments de travail dans un workflow
description: Si vous pensez vous absenter du bureau ou être dans l'incapacité d'agir sur des éléments de travail, vous pouvez déléguer ou réaffecter vos éléments de travail à d'autres utilisateurs.
author: jasongre
manager: AnnBe
ms.date: 04/09/2019
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
ms.openlocfilehash: feace647d7acef6abf86b13fcb8019c622c55ff6
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1509450"
---
# <a name="delegate-work-items-in-a-workflow"></a><span data-ttu-id="0e3f9-103">Délégation d'éléments de travail dans un workflow</span><span class="sxs-lookup"><span data-stu-id="0e3f9-103">Delegate work items in a workflow</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

## <a name="manually-delegate-a-work-item"></a><span data-ttu-id="0e3f9-104">Délégation manuelle d'un élément de travail</span><span class="sxs-lookup"><span data-stu-id="0e3f9-104">Manually delegate a work item</span></span>

<span data-ttu-id="0e3f9-105">Pour déléguer un élément de travail individuel, sélectionnez l'option **Déléguer** dans le menu **Workflow** puis entrez l'utilisateur à qui déléguer l'élément de travail en y ajoutant un commentaire.</span><span class="sxs-lookup"><span data-stu-id="0e3f9-105">To delegate an individual work item, select the **Delegate** option in the **Workflow** menu and then enter the user to be delegated to along with a comment.</span></span> <span data-ttu-id="0e3f9-106">Cela réaffectera l'élément de travail à cet utilisateur afin qu'il puisse l'exécuter.</span><span class="sxs-lookup"><span data-stu-id="0e3f9-106">This will reassign the work item to that user so they can complete it.</span></span>

## <a name="automatically-delegate-work-items"></a><span data-ttu-id="0e3f9-107">Déléguer automatiquement des éléments de travail</span><span class="sxs-lookup"><span data-stu-id="0e3f9-107">Automatically delegate work items</span></span>

<span data-ttu-id="0e3f9-108">Si vous prévoyez de vous absenter du bureau ou être indisponible d'une manière quelconque pour agir sur des éléments de travail pendant une période donnée, vous pouvez automatiquement déléguer de nouveaux éléments de travail à d'autres utilisateurs à l'aide de la page **Options utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="0e3f9-108">If you plan to be out of the office or otherwise unavailable to act on work items for a period of time, you can automatically delegate new work items to other users using the **User options** page.</span></span>

### <a name="set-up-automatic-delegation"></a><span data-ttu-id="0e3f9-109">Paramétrage de la délégation automatique</span><span class="sxs-lookup"><span data-stu-id="0e3f9-109">Set up automatic delegation</span></span>
1. <span data-ttu-id="0e3f9-110">Accédez à Commun > Paramétrage > Options utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0e3f9-110">Go to Common > Setup > User options.</span></span>
2. <span data-ttu-id="0e3f9-111">Cliquez sur l'onglet Workflow.</span><span class="sxs-lookup"><span data-stu-id="0e3f9-111">Click the Workflow tab.</span></span>
    * <span data-ttu-id="0e3f9-112">Assurez-vous que la section Délégation est développée.</span><span class="sxs-lookup"><span data-stu-id="0e3f9-112">Make sure the Delegation section is expanded.</span></span>    <span data-ttu-id="0e3f9-113">Pour configurer le système de sorte à déléguer vos éléments de travail automatiquement à d'autres utilisateurs, vous devez créer des règles de délégation lorsque certains types d'éléments de travail sont délégués.</span><span class="sxs-lookup"><span data-stu-id="0e3f9-113">To configure the system to automatically delegate your work items to other users, you must create delegation rules, which specify when certain types of work items are delegated.</span></span> <span data-ttu-id="0e3f9-114">Pour créer une règle de délégation, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0e3f9-114">Follow these steps to create a delegation rule.</span></span>  
3. <span data-ttu-id="0e3f9-115">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="0e3f9-115">Click Add.</span></span>
4. <span data-ttu-id="0e3f9-116">Dans le champ Portée, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="0e3f9-116">In the Scope field, select an option.</span></span>
    * <span data-ttu-id="0e3f9-117">Tout – Permet de déléguer tous les éléments de travail qui vous sont attribués.</span><span class="sxs-lookup"><span data-stu-id="0e3f9-117">All – Delegate all work items that are assigned to you.</span></span>    <span data-ttu-id="0e3f9-118">Module – Permet de déléguer uniquement les éléments de travail associés à un type donné de workflow.</span><span class="sxs-lookup"><span data-stu-id="0e3f9-118">Module – Delegate only the work items that are related to a specific type of workflow.</span></span> <span data-ttu-id="0e3f9-119">Si cette option est sélectionnée, vous devez sélectionner le type de workflow dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="0e3f9-119">If you select this option, you must select the type of workflow in the Name field.</span></span>    <span data-ttu-id="0e3f9-120">Workflow – Permet de déléguer uniquement les éléments de travail associés à un workflow donné.</span><span class="sxs-lookup"><span data-stu-id="0e3f9-120">Workflow – Delegate only the work items that are related to a specific workflow.</span></span> <span data-ttu-id="0e3f9-121">Si cette option est sélectionnée, vous devez sélectionner le workflow dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="0e3f9-121">If you select this option, you must select the workflow in the Name field.</span></span>  
5. <span data-ttu-id="0e3f9-122">Dans le champ Déléguer, sélectionnez l'utilisateur auquel déléguer les éléments de travail.</span><span class="sxs-lookup"><span data-stu-id="0e3f9-122">In the Delegate field, select the user to delegate the work items to.</span></span>
    * <span data-ttu-id="0e3f9-123">Les champs Date/heure de début et Date/heure de fin permettent de spécifier à quel moment vous souhaitez que les éléments de travail soient automatiquement délégués.</span><span class="sxs-lookup"><span data-stu-id="0e3f9-123">Use the Start date/time and End date/time fields to specify when you want the work items to be automatically delegated.</span></span>  
6. <span data-ttu-id="0e3f9-124">Dans le champ Date/heure de début, entrez une date et une heure.</span><span class="sxs-lookup"><span data-stu-id="0e3f9-124">In the Start date/time field, enter a date and time.</span></span>
7. <span data-ttu-id="0e3f9-125">Dans le champ Date/heure de fin, entrez une date et une heure.</span><span class="sxs-lookup"><span data-stu-id="0e3f9-125">In the End date/time field, enter a date and time.</span></span>
8. <span data-ttu-id="0e3f9-126">Activez la case à cocher Activé pour activer la règle de délégation.</span><span class="sxs-lookup"><span data-stu-id="0e3f9-126">Select the Enabled check box to activate the delegation rule.</span></span>
    * <span data-ttu-id="0e3f9-127">Si vous avez sélectionné Module comme Portée, vous devez alors sélectionner le module dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="0e3f9-127">If you selected Module as the Scope, then you must select the module in the Name field.</span></span>    <span data-ttu-id="0e3f9-128">Si vous avez sélectionné Workflow comme Portée, vous devez alors sélectionner le workflow spécifique à déléguer dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="0e3f9-128">If you selected Workflow as the Scope, then you must select the specific workflow to delegate in the Name field.</span></span>  
9. <span data-ttu-id="0e3f9-129">Dans le champ Commentaire, entrez un commentaire expliquant le motif de la délégation des éléments de travail.</span><span class="sxs-lookup"><span data-stu-id="0e3f9-129">In the Comment field, enter a comment that explains why you are delegating the work items.</span></span>

