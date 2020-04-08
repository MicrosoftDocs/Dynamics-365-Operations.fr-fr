---
title: Paramétrage de l'amortissement de la prime
description: Cette procédure indique comment créer une provision spéciale pour amortissement et l'associer à un registre d'immobilisations.
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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 91243a4cee44410a221902990d31a10f1805eb08
ms.sourcegitcommit: c69926b4285cb2ec2d9ce1ad72d1cb852024dd5e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3138251"
---
# <a name="set-up-bonus-depreciation"></a><span data-ttu-id="940a9-103">Paramétrage de l'amortissement de la prime</span><span class="sxs-lookup"><span data-stu-id="940a9-103">Set up bonus depreciation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="940a9-104">Cette procédure indique comment créer une provision spéciale pour amortissement et l'associer à un registre d'immobilisations.</span><span class="sxs-lookup"><span data-stu-id="940a9-104">This procedure shows how to create a special depreciation allowance and associate it with a fixed asset book.</span></span> <span data-ttu-id="940a9-105">Elle utilise le rôle de comptable et les données de démonstration de l'entité juridique USMF.</span><span class="sxs-lookup"><span data-stu-id="940a9-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>


## <a name="create-a-special-depreciation-allowance"></a><span data-ttu-id="940a9-106">Créer une provision spéciale pour amortissement</span><span class="sxs-lookup"><span data-stu-id="940a9-106">Create a special depreciation allowance</span></span>
1. <span data-ttu-id="940a9-107">Accédez à Immobilisations > Paramétrage > Provision spéciale pour amortissement.</span><span class="sxs-lookup"><span data-stu-id="940a9-107">Go to Fixed assets > Setup > Special depreciation allowance.</span></span>
2. <span data-ttu-id="940a9-108">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="940a9-108">Click New.</span></span>
3. <span data-ttu-id="940a9-109">Entrez une valeur dans le champ Provision spéciale pour amortissement.</span><span class="sxs-lookup"><span data-stu-id="940a9-109">In the Special depreciation allowance field, type a value.</span></span>
4. <span data-ttu-id="940a9-110">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="940a9-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="940a9-111">Entrez un nombre dans le champ Pourcentage.</span><span class="sxs-lookup"><span data-stu-id="940a9-111">In the Percentage field, enter a number.</span></span>
    * <span data-ttu-id="940a9-112">Si un pourcentage n'est pas affiché, définissez un montant.</span><span class="sxs-lookup"><span data-stu-id="940a9-112">If a percentage was not indicated, set an amount.</span></span>  

## <a name="associate-a-special-depreciation-allowance-with-a-fixed-asset-group-book"></a><span data-ttu-id="940a9-113">Associer une provision spéciale pour amortissement au registre d'un groupe d'immobilisations</span><span class="sxs-lookup"><span data-stu-id="940a9-113">Associate a special depreciation allowance with a fixed asset group book</span></span>
1. <span data-ttu-id="940a9-114">Accédez à Immobilisations > Paramétrage > Groupes d'immobilisations.</span><span class="sxs-lookup"><span data-stu-id="940a9-114">Go to Fixed assets > Setup > Fixed asset groups.</span></span>
2. <span data-ttu-id="940a9-115">Dans la liste, sélectionnez le groupe d'immobilisations à associer à la provision spéciale pour amortissement.</span><span class="sxs-lookup"><span data-stu-id="940a9-115">In the list, select the fixed asset group associated with the special depreciation allowance.</span></span>
3. <span data-ttu-id="940a9-116">Cliquez sur Registres.</span><span class="sxs-lookup"><span data-stu-id="940a9-116">Click Books.</span></span>
4. <span data-ttu-id="940a9-117">Dans la liste, sélectionnez le registre associé à la provision spéciale pour amortissement.</span><span class="sxs-lookup"><span data-stu-id="940a9-117">In the list, select the book that is associated with the special depreciation allowance.</span></span>
5. <span data-ttu-id="940a9-118">Cliquez sur Provision spéciale pour amortissement.</span><span class="sxs-lookup"><span data-stu-id="940a9-118">Click Special depreciation allowance.</span></span>
6. <span data-ttu-id="940a9-119">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="940a9-119">Click New.</span></span>
7. <span data-ttu-id="940a9-120">Dans le champ Provision spéciale pour amortissement, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="940a9-120">In the Special depreciation allowance field, enter or select a value.</span></span>
    * <span data-ttu-id="940a9-121">La valeur par défaut du pourcentage ou du montant provient du paramétrage de la provision spéciale pour amortissement.</span><span class="sxs-lookup"><span data-stu-id="940a9-121">The default for Percentage or Amount comes from the special depreciation allowance setup.</span></span>  
8. <span data-ttu-id="940a9-122">Dans le champ Priorité, entrer un numéro.</span><span class="sxs-lookup"><span data-stu-id="940a9-122">In the Priority field, enter a number.</span></span>

