--- 
title: "Paramétrage de l'amortissement de la prime"
description: "Cette procédure indique comment créer une provision spéciale pour amortissement et l'associer à un registre d'immobilisations."
author: saraschi2
manager: AnnBe
ms.date: 10/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7e6ebb13084626b477b6e0b24acdc09e2c0d3d6d
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-bonus-depreciation"></a><span data-ttu-id="3dc76-103">Paramétrage de l'amortissement de la prime</span><span class="sxs-lookup"><span data-stu-id="3dc76-103">Set up bonus depreciation</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3dc76-104">Cette procédure indique comment créer une provision spéciale pour amortissement et l'associer à un registre d'immobilisations.</span><span class="sxs-lookup"><span data-stu-id="3dc76-104">This procedure shows how to create a special depreciation allowance and associate it with a fixed asset book.</span></span> <span data-ttu-id="3dc76-105">Elle utilise le rôle de comptable et les données de démonstration de l'entité juridique USMF.</span><span class="sxs-lookup"><span data-stu-id="3dc76-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-special-depreciation-allowance"></a><span data-ttu-id="3dc76-106">Créer une provision spéciale pour amortissement</span><span class="sxs-lookup"><span data-stu-id="3dc76-106">Create a special depreciation allowance</span></span>
1. <span data-ttu-id="3dc76-107">Accédez à Immobilisations > Paramétrage > Provision spéciale pour amortissement.</span><span class="sxs-lookup"><span data-stu-id="3dc76-107">Go to Fixed assets > Setup > Special depreciation allowance.</span></span>
2. <span data-ttu-id="3dc76-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="3dc76-108">Click New.</span></span>
3. <span data-ttu-id="3dc76-109">Entrez une valeur dans le champ Provision spéciale pour amortissement.</span><span class="sxs-lookup"><span data-stu-id="3dc76-109">In the Special depreciation allowance field, type a value.</span></span>
4. <span data-ttu-id="3dc76-110">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="3dc76-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="3dc76-111">Entrez un nombre dans le champ Pourcentage.</span><span class="sxs-lookup"><span data-stu-id="3dc76-111">In the Percentage field, enter a number.</span></span>
    * <span data-ttu-id="3dc76-112">Si un pourcentage n'est pas affiché, définissez un montant.</span><span class="sxs-lookup"><span data-stu-id="3dc76-112">If a percentage was not indicated, set an amount.</span></span>  

## <a name="associate-a-special-depreciation-allowance-with-a-fixed-asset-group-book"></a><span data-ttu-id="3dc76-113">Associer une provision spéciale pour amortissement au registre d'un groupe d'immobilisations</span><span class="sxs-lookup"><span data-stu-id="3dc76-113">Associate a special depreciation allowance with a fixed asset group book</span></span>
1. <span data-ttu-id="3dc76-114">Accédez à Immobilisations > Paramétrage > Groupes d'immobilisations.</span><span class="sxs-lookup"><span data-stu-id="3dc76-114">Go to Fixed assets > Setup > Fixed asset groups.</span></span>
2. <span data-ttu-id="3dc76-115">Dans la liste, sélectionnez le groupe d'immobilisations à associer à la provision spéciale pour amortissement.</span><span class="sxs-lookup"><span data-stu-id="3dc76-115">In the list, select the fixed asset group associated with the special depreciation allowance.</span></span>
3. <span data-ttu-id="3dc76-116">Cliquez sur Registres.</span><span class="sxs-lookup"><span data-stu-id="3dc76-116">Click Books.</span></span>
4. <span data-ttu-id="3dc76-117">Dans la liste, sélectionnez le registre associé à la provision spéciale pour amortissement.</span><span class="sxs-lookup"><span data-stu-id="3dc76-117">In the list, select the book that is associated with the special depreciation allowance.</span></span>
5. <span data-ttu-id="3dc76-118">Cliquez sur Provision spéciale pour amortissement.</span><span class="sxs-lookup"><span data-stu-id="3dc76-118">Click Special depreciation allowance.</span></span>
6. <span data-ttu-id="3dc76-119">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="3dc76-119">Click New.</span></span>
7. <span data-ttu-id="3dc76-120">Dans le champ Provision spéciale pour amortissement, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="3dc76-120">In the Special depreciation allowance field, enter or select a value.</span></span>
    * <span data-ttu-id="3dc76-121">La valeur par défaut du pourcentage ou du montant provient du paramétrage de la provision spéciale pour amortissement.</span><span class="sxs-lookup"><span data-stu-id="3dc76-121">The default for Percentage or Amount comes from the special depreciation allowance setup.</span></span>  
8. <span data-ttu-id="3dc76-122">Dans le champ Priorité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="3dc76-122">In the Priority field, enter a number.</span></span>


