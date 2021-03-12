---
title: Paramétrage de l’amortissement de la prime
description: Cette procédure indique comment créer une provision spéciale pour amortissement et l’associer à un registre d’immobilisations.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBonus, AssetGroup, AssetGroupBookSetup, AssetGroupSetupBonus
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7fed9f09b4e37da00a5d78fa088e8814db48456b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968927"
---
# <a name="set-up-bonus-depreciation"></a><span data-ttu-id="7c1db-103">Paramétrage de l’amortissement de la prime</span><span class="sxs-lookup"><span data-stu-id="7c1db-103">Set up bonus depreciation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7c1db-104">Cette procédure indique comment créer une provision spéciale pour amortissement et l’associer à un registre d’immobilisations.</span><span class="sxs-lookup"><span data-stu-id="7c1db-104">This procedure shows how to create a special depreciation allowance and associate it with a fixed asset book.</span></span> <span data-ttu-id="7c1db-105">Elle utilise le rôle de comptable et les données de démonstration de l’entité juridique USMF.</span><span class="sxs-lookup"><span data-stu-id="7c1db-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-special-depreciation-allowance"></a><span data-ttu-id="7c1db-106">Créer une provision spéciale pour amortissement</span><span class="sxs-lookup"><span data-stu-id="7c1db-106">Create a special depreciation allowance</span></span>
1. <span data-ttu-id="7c1db-107">Accédez à Immobilisations > Paramétrage > Provision spéciale pour amortissement.</span><span class="sxs-lookup"><span data-stu-id="7c1db-107">Go to Fixed assets > Setup > Special depreciation allowance.</span></span>
2. <span data-ttu-id="7c1db-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="7c1db-108">Click New.</span></span>
3. <span data-ttu-id="7c1db-109">Entrez une valeur dans le champ Provision spéciale pour amortissement.</span><span class="sxs-lookup"><span data-stu-id="7c1db-109">In the Special depreciation allowance field, type a value.</span></span>
4. <span data-ttu-id="7c1db-110">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="7c1db-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="7c1db-111">Entrez un nombre dans le champ Pourcentage.</span><span class="sxs-lookup"><span data-stu-id="7c1db-111">In the Percentage field, enter a number.</span></span>
    * <span data-ttu-id="7c1db-112">Si un pourcentage n’est pas affiché, définissez un montant.</span><span class="sxs-lookup"><span data-stu-id="7c1db-112">If a percentage was not indicated, set an amount.</span></span>  

## <a name="associate-a-special-depreciation-allowance-with-a-fixed-asset-group-book"></a><span data-ttu-id="7c1db-113">Associer une provision spéciale pour amortissement au registre d’un groupe d’immobilisations</span><span class="sxs-lookup"><span data-stu-id="7c1db-113">Associate a special depreciation allowance with a fixed asset group book</span></span>
1. <span data-ttu-id="7c1db-114">Accédez à Immobilisations > Paramétrage > Groupes d’immobilisations.</span><span class="sxs-lookup"><span data-stu-id="7c1db-114">Go to Fixed assets > Setup > Fixed asset groups.</span></span>
2. <span data-ttu-id="7c1db-115">Dans la liste, sélectionnez le groupe d’immobilisations à associer à la provision spéciale pour amortissement.</span><span class="sxs-lookup"><span data-stu-id="7c1db-115">In the list, select the fixed asset group associated with the special depreciation allowance.</span></span>
3. <span data-ttu-id="7c1db-116">Cliquez sur Registres.</span><span class="sxs-lookup"><span data-stu-id="7c1db-116">Click Books.</span></span>
4. <span data-ttu-id="7c1db-117">Dans la liste, sélectionnez le registre associé à la provision spéciale pour amortissement.</span><span class="sxs-lookup"><span data-stu-id="7c1db-117">In the list, select the book that is associated with the special depreciation allowance.</span></span>
5. <span data-ttu-id="7c1db-118">Cliquez sur Provision spéciale pour amortissement.</span><span class="sxs-lookup"><span data-stu-id="7c1db-118">Click Special depreciation allowance.</span></span>
6. <span data-ttu-id="7c1db-119">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="7c1db-119">Click New.</span></span>
7. <span data-ttu-id="7c1db-120">Dans le champ Provision spéciale pour amortissement, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="7c1db-120">In the Special depreciation allowance field, enter or select a value.</span></span>
    * <span data-ttu-id="7c1db-121">La valeur par défaut du pourcentage ou du montant provient du paramétrage de la provision spéciale pour amortissement.</span><span class="sxs-lookup"><span data-stu-id="7c1db-121">The default for Percentage or Amount comes from the special depreciation allowance setup.</span></span>  
8. <span data-ttu-id="7c1db-122">Dans le champ Priorité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="7c1db-122">In the Priority field, enter a number.</span></span>

