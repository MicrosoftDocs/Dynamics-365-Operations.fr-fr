---
title: amortissement de la prime
description: "Cet article offre une vue d'ensemble de la fonctionnalité d'amortissement de la prime."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBonus
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3621
ms.assetid: 835ec594-744e-461c-a676-1b9abc094173
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 5e05c0c195ddb948547ae008d050686bbcdc6ed3
ms.contentlocale: fr-fr
ms.lasthandoff: 08/07/2018

---

# <a name="bonus-depreciation"></a><span data-ttu-id="73b3b-103">amortissement de la prime</span><span class="sxs-lookup"><span data-stu-id="73b3b-103">Bonus depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="73b3b-104">Cet article offre une vue d'ensemble de la fonctionnalité d'amortissement de la prime.</span><span class="sxs-lookup"><span data-stu-id="73b3b-104">This article provides an overview of the bonus depreciation functionality.</span></span>

<span data-ttu-id="73b3b-105">Pour l'amortissement de la prime, vous pouvez prendre des montants d'amortissement exceptionnel ou de la prime au cours de la première année de mise en service et d'amortissement de l'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="73b3b-105">For bonus depreciation, you can take extra or bonus depreciation amounts during the first year that the asset is put in service and depreciated.</span></span> <span data-ttu-id="73b3b-106">L'amortissement de la prime doit être pris avant tout autre calcul d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="73b3b-106">Bonus depreciation must be taken before any other depreciation calculations.</span></span> <span data-ttu-id="73b3b-107">Par conséquent, il est recommandé d'utiliser l'amortissement de la prime avec des registres pour lesquels la fonctionnalité Valider dans la comptabilité est désactivée.</span><span class="sxs-lookup"><span data-stu-id="73b3b-107">Therefore, it's best to use bonus depreciation with books where the Post to general ledger functionality is disabled.</span></span> <span data-ttu-id="73b3b-108">Vous pouvez utiliser l'option **Supprimer les transactions non validées dans la comptabilité** pour supprimer les transactions historiques des registres qui ne sont pas validés dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="73b3b-108">You can use the **Delete transactions not posted to general ledger** option to delete historical transactions for books that don't post to the general ledger.</span></span> <span data-ttu-id="73b3b-109">Vous pouvez ensuite utiliser l'amortissement de la prime plus tard au cours du cycle de vie de l'immobilisation en supprimant les transactions d'amortissement précédemment validées.</span><span class="sxs-lookup"><span data-stu-id="73b3b-109">You can then accommodate bonus depreciation later in the asset life cycle by deleting depreciation transactions that were previously posted.</span></span> 

<span data-ttu-id="73b3b-110">Vous pouvez calculer un amortissement de la prime à l'aide du processus de proposition, ou créer des transactions manuelles d'amortissement de la prime.</span><span class="sxs-lookup"><span data-stu-id="73b3b-110">You can calculate bonus depreciation by using the proposal process, or you can create manual bonus depreciation transactions.</span></span> <span data-ttu-id="73b3b-111">Vous ne pouvez pas créer de transaction d'amortissement de la prime si des transactions d'amortissement ou d'ajustement de l'amortissement existent pour ce registre d'actifs.</span><span class="sxs-lookup"><span data-stu-id="73b3b-111">You can't create bonus depreciation transactions if depreciation transactions or depreciation adjustment transactions exist for that asset book.</span></span>

<span data-ttu-id="73b3b-112">Si vous utilisez le processus de proposition pour calculer un amortissement de prime, toutes les transactions de prime existantes sont incluses dans le calcul de la base.</span><span class="sxs-lookup"><span data-stu-id="73b3b-112">When you use the proposal process to calculate bonus depreciation, all existing bonus transactions are included in the calculation of the basis.</span></span> <span data-ttu-id="73b3b-113">Le calcul inclut également tout amortissement de prime précédent entré manuellement pour l'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="73b3b-113">The calculation also includes any previous bonus depreciations that you manually entered for the asset.</span></span> 

<span data-ttu-id="73b3b-114">Si plusieurs amortissements de prime doivent être pris pour une immobilisation, la priorité est prise en considération.</span><span class="sxs-lookup"><span data-stu-id="73b3b-114">If more than one bonus depreciation will be taken for an asset, the priority is considered.</span></span> <span data-ttu-id="73b3b-115">Chaque prime réduit la base des actifs pour la prime suivante.</span><span class="sxs-lookup"><span data-stu-id="73b3b-115">Each bonus reduces the asset basis for the next bonus.</span></span> <span data-ttu-id="73b3b-116">La valeur résiduelle n'est pas prise en compte dans la base des actifs pour les calculs d'amortissement de la prime, et la convention d'amortissement ne s'applique pas pour l'amortissement de la prime.</span><span class="sxs-lookup"><span data-stu-id="73b3b-116">Salvage value isn't considered in the asset basis for bonus depreciation calculations, and the depreciation convention doesn't apply for bonus depreciation.</span></span> 

<span data-ttu-id="73b3b-117">Actuellement, aux États-Unis, certaines propriétés sont qualifiées comme propriétés de la section 179.</span><span class="sxs-lookup"><span data-stu-id="73b3b-117">Currently, in the United States, some property qualifies as Section 179 property.</span></span> <span data-ttu-id="73b3b-118">La déduction au titre de la section 179 vous permet de récupérer tout ou partie du coût de certaines propriétés, dans une certaine limite.</span><span class="sxs-lookup"><span data-stu-id="73b3b-118">By using the Section 179 deduction, you can recover all or part of the cost of some property, up to a limit.</span></span> <span data-ttu-id="73b3b-119">Vous pouvez récupérer le coût en le déduisant au cours de l'année pendant laquelle la propriété a été mise en service.</span><span class="sxs-lookup"><span data-stu-id="73b3b-119">You can recover the cost by deducting it in the year when you put the property in service.</span></span>

## <a name="example"></a><span data-ttu-id="73b3b-120">Exemple</span><span class="sxs-lookup"><span data-stu-id="73b3b-120">Example</span></span>
<span data-ttu-id="73b3b-121">Les amortissements de prime suivants sont associés à un registre des immobilisations :</span><span class="sxs-lookup"><span data-stu-id="73b3b-121">The following bonus depreciations are associated with an asset book:</span></span>

-   <span data-ttu-id="73b3b-122">**Section 179 :** 1 000,00, Priorité 1</span><span class="sxs-lookup"><span data-stu-id="73b3b-122">**Section 179:** 1,000.00, Priority 1</span></span>
-   <span data-ttu-id="73b3b-123">**Zone de Liberty :** 30 %, Priorité 2</span><span class="sxs-lookup"><span data-stu-id="73b3b-123">**Liberty Zone:** 30 percent, Priority 2</span></span>

<span data-ttu-id="73b3b-124">Le coût d'acquisition d'immobilisation est de 5 000,00 USD.</span><span class="sxs-lookup"><span data-stu-id="73b3b-124">The asset acquisition cost is 5,000.00.</span></span> <span data-ttu-id="73b3b-125">Lors du calcul de l'amortissement de la prime, le premier montant d'amortissement est de 1 000,00 pour l'amortissement au titre de la section 179.</span><span class="sxs-lookup"><span data-stu-id="73b3b-125">When bonus depreciation is calculated, the first bonus depreciation amount is 1,000.00 for the Section 179 depreciation.</span></span> 

<span data-ttu-id="73b3b-126">Le montant d'amortissement de la prime suivant (pour l'amortissement dans la zone de Liberty) est calculé comme suit :</span><span class="sxs-lookup"><span data-stu-id="73b3b-126">The next bonus depreciation amount, for the Liberty Zone depreciation, is calculated as follows:</span></span> 

<span data-ttu-id="73b3b-127">Coût d'acquisition – 1 000 (amortissement au titre de la section 179) x 30 % = 1 200</span><span class="sxs-lookup"><span data-stu-id="73b3b-127">Acquisition cost – 1,000 (Section 179 depreciation) × 30 percent = 1,200</span></span> 

<span data-ttu-id="73b3b-128">Si le montant d'amortissement de la prime est supérieur au coût d'acquisition restant, le montant d'amortissement de la prime est le plus bas des montants suivants : calcul d'amortissement de la prime ou coût d'acquisition restant.</span><span class="sxs-lookup"><span data-stu-id="73b3b-128">If the bonus depreciation amount is more than the remaining acquisition cost, the bonus depreciation amount is either the result of the bonus depreciation calculation or the remaining acquisition cost, whichever amount is less.</span></span> 

<span data-ttu-id="73b3b-129">Si le coût d'acquisition restant est égal ou inférieur à 0 (zéro), aucune transaction d'amortissement de prime n'est générée.</span><span class="sxs-lookup"><span data-stu-id="73b3b-129">If the remaining acquisition cost is 0 (zero) or less, bonus depreciation transactions isn't generated.</span></span> 

<span data-ttu-id="73b3b-130">En cas de calcul de l'amortissement de la prime à l'aide du processus de proposition, une transaction d'amortissement de prime est créée pour tous les enregistrements d'amortissement de la prime applicables associés au registre des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="73b3b-130">When bonus depreciation is calculated by using the proposal process, a bonus depreciation transaction is created for all applicable bonus depreciation records that are associated with the asset book.</span></span> 

<span data-ttu-id="73b3b-131">Vous pouvez créer un nombre illimité d'enregistrements d'amortissement de la prime.</span><span class="sxs-lookup"><span data-stu-id="73b3b-131">You can create an unlimited number of bonus depreciation records.</span></span> <span data-ttu-id="73b3b-132">Une fois que vous affectez ces enregistrements à un registre de groupe d'immobilisations, ils sont appliqués au registre des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="73b3b-132">After you assign those records to the asset group book, they are applied to the asset book.</span></span> 

<span data-ttu-id="73b3b-133">L'amortissement de la prime est entré comme pourcentage ou montant fixe.</span><span class="sxs-lookup"><span data-stu-id="73b3b-133">Bonus depreciation is entered as either a percentage or a fixed amount.</span></span> <span data-ttu-id="73b3b-134">Lorsque vous validez des propositions d'amortissement, les transactions d'amortissement de la prime sont validées dans le registre comme transactions distinctes des transactions d'amortissement.</span><span class="sxs-lookup"><span data-stu-id="73b3b-134">When you post depreciation proposals, bonus depreciation transactions are posted to the book as separate transactions from the depreciation transactions.</span></span>




