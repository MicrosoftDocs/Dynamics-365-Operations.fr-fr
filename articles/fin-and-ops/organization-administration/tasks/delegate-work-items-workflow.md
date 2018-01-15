--- 
title: "Délégation d'éléments de travail dans un workflow"
description: "Si vous pensez vous absenter du bureau ou être dans l'incapacité d'agir sur des éléments de travail, vous pouvez déléguer ou réaffecter vos éléments de travail à d'autres utilisateurs."
author: jasongre
manager: AnnBe
ms.date: 02/21/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 4765fec0cdce0e2f8859c979ff97d20aa6b20bfa
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="delegate-work-items-in-a-workflow"></a><span data-ttu-id="7f3c4-103">Délégation d'éléments de travail dans un workflow</span><span class="sxs-lookup"><span data-stu-id="7f3c4-103">Delegate work items in a workflow</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7f3c4-104">Si vous pensez vous absenter du bureau ou être dans l'incapacité d'agir sur des éléments de travail, vous pouvez déléguer ou réaffecter vos éléments de travail à d'autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7f3c4-104">If you plan to be out of the office or otherwise unavailable to act on work items, you can delegate, or reassign, your work items to other users.</span></span> <span data-ttu-id="7f3c4-105">Cette procédure vous permet de configurer le système pour déléguer automatiquement vos éléments de travail à un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7f3c4-105">This procedure helps you configure the system to automatically delegate your work items to another user.</span></span>



<span data-ttu-id="7f3c4-106">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="7f3c4-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-automatic-delegation"></a><span data-ttu-id="7f3c4-107">Paramétrage de la délégation automatique</span><span class="sxs-lookup"><span data-stu-id="7f3c4-107">Set up automatic delegation</span></span>
1. <span data-ttu-id="7f3c4-108">Accédez à Commun > Paramétrage > Options utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7f3c4-108">Go to Common > Setup > User options.</span></span>
2. <span data-ttu-id="7f3c4-109">Cliquez sur l'onglet Workflow.</span><span class="sxs-lookup"><span data-stu-id="7f3c4-109">Click the Workflow tab.</span></span>
    * <span data-ttu-id="7f3c4-110">Assurez-vous que la section Délégation est développée.</span><span class="sxs-lookup"><span data-stu-id="7f3c4-110">Make sure the Delegation section is expanded.</span></span>    <span data-ttu-id="7f3c4-111">Pour configurer le système de sorte à déléguer vos éléments de travail automatiquement à d'autres utilisateurs, vous devez créer des règles de délégation lorsque certains types d'éléments de travail sont délégués.</span><span class="sxs-lookup"><span data-stu-id="7f3c4-111">To configure the system to automatically delegate your work items to other users, you must create delegation rules, which specify when certain types of work items are delegated.</span></span> <span data-ttu-id="7f3c4-112">Pour créer une règle de délégation, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="7f3c4-112">Follow these steps to create a delegation rule.</span></span>  
3. <span data-ttu-id="7f3c4-113">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="7f3c4-113">Click Add.</span></span>
4. <span data-ttu-id="7f3c4-114">Dans le champ Portée, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="7f3c4-114">In the Scope field, select an option.</span></span>
    * <span data-ttu-id="7f3c4-115">Tout – Permet de déléguer tous les éléments de travail qui vous sont attribués.</span><span class="sxs-lookup"><span data-stu-id="7f3c4-115">All – Delegate all work items that are assigned to you.</span></span>    <span data-ttu-id="7f3c4-116">Module – Permet de déléguer uniquement les éléments de travail associés à un type donné de workflow.</span><span class="sxs-lookup"><span data-stu-id="7f3c4-116">Module – Delegate only the work items that are related to a specific type of workflow.</span></span> <span data-ttu-id="7f3c4-117">Si cette option est sélectionnée, vous devez sélectionner le type de workflow dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="7f3c4-117">If you select this option, you must select the type of workflow in the Name field.</span></span>    <span data-ttu-id="7f3c4-118">Workflow – Permet de déléguer uniquement les éléments de travail associés à un workflow donné.</span><span class="sxs-lookup"><span data-stu-id="7f3c4-118">Workflow – Delegate only the work items that are related to a specific workflow.</span></span> <span data-ttu-id="7f3c4-119">Si cette option est sélectionnée, vous devez sélectionner le workflow dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="7f3c4-119">If you select this option, you must select the workflow in the Name field.</span></span>  
5. <span data-ttu-id="7f3c4-120">Dans le champ Déléguer, sélectionnez l'utilisateur auquel déléguer les éléments de travail.</span><span class="sxs-lookup"><span data-stu-id="7f3c4-120">In the Delegate field, select the user to delegate the work items to.</span></span>
    * <span data-ttu-id="7f3c4-121">Les champs Date/heure de début et Date/heure de fin permettent de spécifier à quel moment vous souhaitez que les éléments de travail soient automatiquement délégués.</span><span class="sxs-lookup"><span data-stu-id="7f3c4-121">Use the Start date/time and End date/time fields to specify when you want the work items to be automatically delegated.</span></span>  
6. <span data-ttu-id="7f3c4-122">Dans le champ Date/heure de début, entrez une date et une heure.</span><span class="sxs-lookup"><span data-stu-id="7f3c4-122">In the Start date/time field, enter a date and time.</span></span>
7. <span data-ttu-id="7f3c4-123">Dans le champ Date/heure de fin, entrez une date et une heure.</span><span class="sxs-lookup"><span data-stu-id="7f3c4-123">In the End date/time field, enter a date and time.</span></span>
8. <span data-ttu-id="7f3c4-124">Activez la case à cocher Activé pour activer la règle de délégation.</span><span class="sxs-lookup"><span data-stu-id="7f3c4-124">Select the Enabled check box to activate the delegation rule.</span></span>
    * <span data-ttu-id="7f3c4-125">Si vous avez sélectionné Module comme Portée, vous devez alors sélectionner le module dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="7f3c4-125">If you selected Module as the Scope, then you must select the module in the Name field.</span></span>    <span data-ttu-id="7f3c4-126">Si vous avez sélectionné Workflow comme Portée, vous devez alors sélectionner le workflow spécifique à déléguer dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="7f3c4-126">If you selected Workflow as the Scope, then you must select the specific workflow to delegate in the Name field.</span></span>  
9. <span data-ttu-id="7f3c4-127">Dans le champ Commentaire, entrez un commentaire expliquant le motif de la délégation des éléments de travail.</span><span class="sxs-lookup"><span data-stu-id="7f3c4-127">In the Comment field, enter a comment that explains why you are delegating the work items.</span></span>

