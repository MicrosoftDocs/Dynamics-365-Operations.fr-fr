---
title: Amortissement des immobilisations
description: Cette rubrique fournit une vue d'ensemble de l'amortissement des immobilisations.
author: ShylaThompson
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBonus, AssetBookTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3121
ms.assetid: 98ff891f-e0e2-4184-b618-28107a50851f
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: a82e14e12cbde29e5619518481d0c22f6fa1a37a
ms.contentlocale: fr-fr
ms.lasthandoff: 08/07/2018

---

# <a name="fixed-asset-depreciation"></a><span data-ttu-id="a4e1f-103">Amortissement des immobilisations</span><span class="sxs-lookup"><span data-stu-id="a4e1f-103">Fixed asset depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a4e1f-104">Cette rubrique fournit une vue d'ensemble de l'amortissement des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-104">This topic provides an overview of depreciation for fixed assets.</span></span>

<span data-ttu-id="a4e1f-105">L'amortissement est une transaction périodique qui réduit généralement la valeur des immobilisations dans le bilan et est facturé comme une dépense dans le compte de résultat.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-105">Depreciation is a periodic transaction that typically reduces the value of the fixed asset on the balance sheet, and is charged as an expenditure to a profit and loss account.</span></span> <span data-ttu-id="a4e1f-106">Par conséquent, un compte principal est généralement utilisé pour créditer l'amortissement périodique dans le bilan.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-106">Therefore, a main account is typically used to credit the periodic depreciation on the balance sheet.</span></span> <span data-ttu-id="a4e1f-107">Un compte de contrepartie est un compte dans la partie résultat du plan de comptes.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-107">An offset account is an account in the profit and loss part of the chart of accounts.</span></span>

## <a name="depreciation-adjustment"></a><span data-ttu-id="a4e1f-108">Ajustement de l'amortissement</span><span class="sxs-lookup"><span data-stu-id="a4e1f-108">Depreciation adjustment</span></span>
<span data-ttu-id="a4e1f-109">En règle générale, seule la correction d'une transaction d'amortissement déjà validée peut être validée en tant qu'ajustement d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-109">Usually, only a correction to a posted depreciation transaction is posted as a depreciation adjustment.</span></span> <span data-ttu-id="a4e1f-110">Par conséquent, le compte principal et le compte de contrepartie sont paramétrés de la même manière que les comptes d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-110">Therefore, both the main account and the offset account are set up just like the accounts for depreciation.</span></span> <span data-ttu-id="a4e1f-111">Un ajustement de l'amortissement peut correspondre à un montant positif ou négatif mais la fonctionnalité du compte principal (en tant que compte de bilan) et de la fonctionnalité du compte de contrepartie (généralement en tant que compte de résultat) reste la même.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-111">A depreciation adjustment can be either a positive amount or a negative amount, but the functionality of the main account (as a balance sheet account) and the functionality of the offset account (usually as a profit and loss account) remain the same.</span></span>

## <a name="extraordinary-depreciation"></a><span data-ttu-id="a4e1f-112">Amortissement exceptionnel</span><span class="sxs-lookup"><span data-stu-id="a4e1f-112">Extraordinary depreciation</span></span>
<span data-ttu-id="a4e1f-113">L'amortissement exceptionnel fonctionne comme un amortissement de base.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-113">Extraordinary depreciation works like basic depreciation.</span></span> <span data-ttu-id="a4e1f-114">Par conséquent, un compte principal est utilisé pour créditer le montant de l'amortissement sur le bilan et réduire la valeur de l'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-114">Therefore, a main account is used to credit the depreciation amount to the balance sheet and reduce the value of the fixed asset.</span></span> <span data-ttu-id="a4e1f-115">Un compte de contrepartie est un compte de résultat dans lequel l'amortissement calculé pour la période fiscale est facturé comme dépense.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-115">An offset account is a profit and loss account, where the depreciation that is calculated for the fiscal period is charged as an expenditure.</span></span> 

<span data-ttu-id="a4e1f-116">Un amortissement exceptionnel fonctionne indépendamment de l'amortissement de base.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-116">Extraordinary depreciation works independently of basic depreciation.</span></span> <span data-ttu-id="a4e1f-117">En définissant l'amortissement exceptionnel en tant que type de transaction distinct, vous pouvez valider et de déclarer l'amortissement exceptionnel indépendamment de l'amortissement ordinaire, de base.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-117">By having extraordinary depreciation as a separate transaction type, you can post and report the extraordinary depreciation separately from the basic depreciation.</span></span>

## <a name="special-depreciation-allowance"></a><span data-ttu-id="a4e1f-118">Provision spéciale pour amortissement</span><span class="sxs-lookup"><span data-stu-id="a4e1f-118">Special depreciation allowance</span></span>
<span data-ttu-id="a4e1f-119">Vous pouvez utiliser des provisions spéciales pour l'amortissement pour prendre des montants d'amortissement exceptionnels durant la première année de mise en service et d'amortissement d'une immobilisation.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-119">You can use special depreciation allowances to take extra depreciation amounts during the first year that an asset is put in service and depreciated.</span></span> <span data-ttu-id="a4e1f-120">Les provisions spéciales pour amortissement doivent être prises avant tout autre calcul d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-120">Special depreciation allowances must be taken before any other depreciation calculations.</span></span> <span data-ttu-id="a4e1f-121">Comme les provisions spéciales pour amortissement sont souvent inconnues jusqu'à ultérieurement dans la vie de l'immobilisation, il est recommandé d'utiliser ce type d'amortissement avec un registre qui ne valide pas dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-121">Because special depreciation allowances are often unknown until later in the service life of the fixed asset, it's best to use this type of depreciation with a book that doesn't post to the general ledger.</span></span> <span data-ttu-id="a4e1f-122">Vous pouvez utiliser la fonctionnalité périodique Supprimer les transactions non validées dans la comptabilité pour supprimer l'historique des transactions pour ces registres.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-122">You can use the Delete transactions not posted to general ledger periodic function to delete the transaction history for these books.</span></span> <span data-ttu-id="a4e1f-123">Vous pouvez ensuite supprimer l'historique d'amortissement pour le registre des immobilisations, valider la provision spéciale pour amortissement lorsqu'elle est connue, puis valider les transactions d'amortissement restantes pour l'année.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-123">You can then delete the depreciation history for the fixed asset book, post the special depreciation allowance when it's known, and then post the remaining depreciation transactions for the year.</span></span> 

<span data-ttu-id="a4e1f-124">Vous pouvez créer un nombre illimité d'enregistrements de provision spéciale pour amortissement.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-124">You can create an unlimited number of special depreciation allowance records.</span></span> <span data-ttu-id="a4e1f-125">Une fois que vous affectez ces enregistrements à un registre de groupe d'immobilisations, ils sont appliqués au registre des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-125">After you assign those records to an asset group book, they are applied to the asset book.</span></span> 

<span data-ttu-id="a4e1f-126">Une provision spéciale pour amortissement est entrée comme pourcentage ou montant fixe.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-126">A special depreciation allowance is entered as either a percentage or a fixed amount.</span></span> <span data-ttu-id="a4e1f-127">Lorsque vous validez des propositions d'amortissement, les transactions de provision spéciale pour amortissement sont validées dans le registre comme transactions distinctes des transactions d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-127">When you post depreciation proposals, special depreciation allowance transactions are posted to the book as transactions that are separate from the depreciation transactions.</span></span>

## <a name="depreciation-calendars"></a><span data-ttu-id="a4e1f-128">Calendriers d'amortissement</span><span class="sxs-lookup"><span data-stu-id="a4e1f-128">Depreciation calendars</span></span>
<span data-ttu-id="a4e1f-129">Chaque registre possède un calendrier utilisé lorsque vous amortissez des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-129">Each book has a calendar that is used when you depreciate fixed assets.</span></span> <span data-ttu-id="a4e1f-130">Par défaut, si vous n'indiquez pas le calendrier sur le registre, celui-ci utilise le calendrier fiscal.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-130">By default, if you don't indicate a calendar on the book, the book uses the ledger fiscal calendar.</span></span> <span data-ttu-id="a4e1f-131">Vous devez sélectionner un calendrier fiscal pour un registre lorsque le profil d'amortissement associé au registre utilise une année d'amortissement fiscal.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-131">You must select a fiscal calendar for a book when the depreciation profile that is associated with the book uses a fiscal depreciation year.</span></span> 

<span data-ttu-id="a4e1f-132">Vous pouvez créer des calendriers partagés à l'aide de la page **Calendriers fiscaux** dans Comptabilité.</span><span class="sxs-lookup"><span data-stu-id="a4e1f-132">You can create shared calendars by using the **Fiscal calendars** page in General ledger.</span></span>

<span data-ttu-id="a4e1f-133">Pour plus d'informations, voir [Méthodes et conventions d'amortissement](depreciation-methods-conventions.md).</span><span class="sxs-lookup"><span data-stu-id="a4e1f-133">For more information, see [Depreciation methods and conventions](depreciation-methods-conventions.md).</span></span>




