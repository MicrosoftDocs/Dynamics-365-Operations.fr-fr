---
title: Les performances du calcul de la taxe affectent les transactions
description: Cette rubrique fournit des informations sur la résolution des problèmes liés aux performances du calcul de la taxe et à son effet sur les transactions.
author: shtao
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 6fce4e2cb8c5507769533a875e23ccc4531abf51
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020137"
---
# <a name="tax-calculation-performance-affects-transactions"></a><span data-ttu-id="2a9fb-103">Les performances du calcul de la taxe affectent les transactions</span><span class="sxs-lookup"><span data-stu-id="2a9fb-103">Tax calculation performance affects transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2a9fb-104">Parfois, une transaction est affectée par des problèmes de performance liés au calcul de la taxe.</span><span class="sxs-lookup"><span data-stu-id="2a9fb-104">Sometimes, a transaction is affected by performance issues that tax calculation is having.</span></span> <span data-ttu-id="2a9fb-105">Pour résoudre ce problème, suivez les étapes des sections suivantes selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="2a9fb-105">To troubleshoot this issue, follow the steps in the following sections as required.</span></span>

## <a name="review-the-transaction-line-count"></a><span data-ttu-id="2a9fb-106">Examiner le nombre de lignes de transaction</span><span class="sxs-lookup"><span data-stu-id="2a9fb-106">Review the transaction line count</span></span>

<span data-ttu-id="2a9fb-107">Déterminez si la transaction comporte un grand nombre de lignes (par exemple plusieurs centaines).</span><span class="sxs-lookup"><span data-stu-id="2a9fb-107">Determine whether the transaction has a large number of lines (for example, more than several hundred).</span></span> <span data-ttu-id="2a9fb-108">Si ce n'est pas le cas, passez à la section suivante.</span><span class="sxs-lookup"><span data-stu-id="2a9fb-108">If it doesn't, move on to the next section.</span></span> <span data-ttu-id="2a9fb-109">Si la transaction comporte plusieurs centaines de lignes, retardez le calcul de la taxe.</span><span class="sxs-lookup"><span data-stu-id="2a9fb-109">If the transaction does have several hundred lines, delay the tax calculation.</span></span> <span data-ttu-id="2a9fb-110">Pour plus d'informations, consultez [Activer un calcul de taxe différé sur les journaux](enable-delayed-tax-calculation.md).</span><span class="sxs-lookup"><span data-stu-id="2a9fb-110">For more information, see [Enable delayed tax calculation on journals](enable-delayed-tax-calculation.md).</span></span> 

<span data-ttu-id="2a9fb-111">Ensuite, vous pouvez déterminer si l'une des conditions suivantes est remplie :</span><span class="sxs-lookup"><span data-stu-id="2a9fb-111">Next, you can determine whether any of the following conditions are met:</span></span>

- <span data-ttu-id="2a9fb-112">Il existe des transactions d'importation à partir de fichiers volumineux.</span><span class="sxs-lookup"><span data-stu-id="2a9fb-112">There are import transactions from large files.</span></span>
- <span data-ttu-id="2a9fb-113">Plusieurs sessions traitent le même calcul de taxe sur des transactions en même temps.</span><span class="sxs-lookup"><span data-stu-id="2a9fb-113">Multiple sessions process the same transaction tax calculation at the same time.</span></span>
- <span data-ttu-id="2a9fb-114">La transaction comporte plusieurs lignes et les vues sont mises à jour en temps réel.</span><span class="sxs-lookup"><span data-stu-id="2a9fb-114">The transaction has multiple lines, and the views are updated in real time.</span></span> <span data-ttu-id="2a9fb-115">Par exemple, le champ **Montant de taxe calculé** sur la page **Journal des opérations diverses** est mis à jour en temps réel lorsque les champs d'une ligne sont modifiés.</span><span class="sxs-lookup"><span data-stu-id="2a9fb-115">For example, the **Calculated sales tax amount** field on the **General journal** page is updated in real time when a line's fields are changed.</span></span>

   <span data-ttu-id="2a9fb-116">[![Champ Montant de taxe calculé sur la page Justificatif de journal](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="2a9fb-116">[![Calculated sales tax amount field on the Jounal voucher page](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)</span></span>

<span data-ttu-id="2a9fb-117">Si l'une de ces conditions est remplie, retardez le calcul de la taxe.</span><span class="sxs-lookup"><span data-stu-id="2a9fb-117">If any of these conditions are met, delay the tax calculation.</span></span>

## <a name="review-the-call-stack"></a><span data-ttu-id="2a9fb-118">Examiner la pile d'appels</span><span class="sxs-lookup"><span data-stu-id="2a9fb-118">Review the call stack</span></span>

<span data-ttu-id="2a9fb-119">Examinez la pile d'appels pour déterminer si le calcul de la taxe est appelé plusieurs fois.</span><span class="sxs-lookup"><span data-stu-id="2a9fb-119">Review the call stack to determine whether tax calculation is called multiple times.</span></span> <span data-ttu-id="2a9fb-120">Si ce n'est pas le cas, passez à la section suivante.</span><span class="sxs-lookup"><span data-stu-id="2a9fb-120">If it isn't, move on to the next section.</span></span> <span data-ttu-id="2a9fb-121">Si la pile d'appels est appelée plusieurs fois, procédez comme suit pour réduire les temps de calcul de la taxe.</span><span class="sxs-lookup"><span data-stu-id="2a9fb-121">If the call stack is called multiple times, follow these steps to help reduce the tax calculation times.</span></span>

1. <span data-ttu-id="2a9fb-122">Si le journal a pris en compte la transaction, retardez le calcul de la taxe.</span><span class="sxs-lookup"><span data-stu-id="2a9fb-122">If the journal has considered the transaction, delay the tax calculation.</span></span> <span data-ttu-id="2a9fb-123">Pour plus d'informations, consultez [Activer un calcul de taxe différé sur les journaux](enable-delayed-tax-calculation.md).</span><span class="sxs-lookup"><span data-stu-id="2a9fb-123">For more information, see [Enable delayed tax calculation on journals](enable-delayed-tax-calculation.md).</span></span>
2. <span data-ttu-id="2a9fb-124">Si la transaction est un bon de commande et que la version de l'application est postérieure à 10.0.15, vous pouvez retarder le calcul de la taxe jusqu'au calcul final en activant le mode Flighting pour **PurchTableChangeMgmtDistributionUpdateOnToggle_KillSwitch**.</span><span class="sxs-lookup"><span data-stu-id="2a9fb-124">If the transaction is a purchase order, and the application version is later than 10.0.15, you can delay the tax calculation until the final calculation by enabling the flighting for **PurchTableChangeMgmtDistributionUpdateOnToggle_KillSwitch**.</span></span>

## <a name="review-the-call-stack-timeline"></a><span data-ttu-id="2a9fb-125">Examiner la chronologie de la pile d'appels</span><span class="sxs-lookup"><span data-stu-id="2a9fb-125">Review the call stack timeline</span></span>

<span data-ttu-id="2a9fb-126">Consultez la chronologie de la pile d'appels pour déterminer si les problèmes suivants existent.</span><span class="sxs-lookup"><span data-stu-id="2a9fb-126">Review the call stack timeline to determine whether the following issues exist.</span></span> <span data-ttu-id="2a9fb-127">Si tel est le cas, activez le mode Flighting pour **TaxUncommittedDoIsolateScopeFlighting** pour résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="2a9fb-127">If they do, enable the flighting for **TaxUncommittedDoIsolateScopeFlighting** to fix the issue.</span></span>

- <span data-ttu-id="2a9fb-128">La transaction fait que le système cesse de répondre jusqu'à ce que la session se termine.</span><span class="sxs-lookup"><span data-stu-id="2a9fb-128">The transaction causes the system to stop responding until the session ends.</span></span> <span data-ttu-id="2a9fb-129">Par conséquent, la transaction ne peut pas calculer le résultat fiscal.</span><span class="sxs-lookup"><span data-stu-id="2a9fb-129">Therefore, the transaction can't calculate the tax result.</span></span> <span data-ttu-id="2a9fb-130">L'illustration suivante montre la boîte de message « Session terminée » que vous recevez.</span><span class="sxs-lookup"><span data-stu-id="2a9fb-130">The following illustration shows the "Session ended" message box that you receive.</span></span>

    <span data-ttu-id="2a9fb-131">[![Message Session terminée](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="2a9fb-131">[![Session ended message](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)</span></span>

- <span data-ttu-id="2a9fb-132">Les méthodes **TaxUncommitted** prennent plus de temps que les autres.</span><span class="sxs-lookup"><span data-stu-id="2a9fb-132">The **TaxUncommitted** methods take more time than other methods.</span></span> <span data-ttu-id="2a9fb-133">Par exemple, dans l'illustration suivante, la méthode **TaxUncommitted::updateTaxUncommitted()** prend 43 347,42 secondes, mais les autres méthodes prennent 0,09 seconde.</span><span class="sxs-lookup"><span data-stu-id="2a9fb-133">For example, in the following illustration, the **TaxUncommitted::updateTaxUncommitted()** method takes 43,347.42 seconds, but other methods take 0.09 seconds.</span></span>

    <span data-ttu-id="2a9fb-134">[![Durée des méthodes](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)</span><span class="sxs-lookup"><span data-stu-id="2a9fb-134">[![Method durations](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)</span></span>

## <a name="customizing-and-calling-tax-calculation"></a><span data-ttu-id="2a9fb-135">Personnalisation et appel du calcul de la taxe</span><span class="sxs-lookup"><span data-stu-id="2a9fb-135">Customizing and calling tax calculation</span></span>

<span data-ttu-id="2a9fb-136">Lorsque vous personnalisez, n'appelez pas le calcul de la taxe pour la méthode **insérer()** ou **mettre à jour()** pour chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="2a9fb-136">When you customize, don't call tax calculation at the **insert()** or **update()** method for each line.</span></span> <span data-ttu-id="2a9fb-137">Le calcul de la taxe doit être appelé au niveau de la transaction.</span><span class="sxs-lookup"><span data-stu-id="2a9fb-137">Tax calculation should be called at the transaction level.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="2a9fb-138">Déterminer si la personnalisation existe</span><span class="sxs-lookup"><span data-stu-id="2a9fb-138">Determine whether customization exists</span></span>

<span data-ttu-id="2a9fb-139">Si vous avez terminé les étapes des sections précédentes mais que vous n'avez trouvé aucun problème, déterminez s'il existe une personnalisation.</span><span class="sxs-lookup"><span data-stu-id="2a9fb-139">If you've completed the steps in the previous sections but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="2a9fb-140">Si aucune personnalisation n'existe, créez une demande de service Microsoft pour une assistance supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="2a9fb-140">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
