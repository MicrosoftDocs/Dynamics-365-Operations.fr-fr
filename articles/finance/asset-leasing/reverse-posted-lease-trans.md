---
title: Contrepasser les transactions de bail validées
description: Cette rubrique explique comment Contrepasser une transaction de location validée. Toute transaction créée via la location d’actifs peut être annulée.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 22d8eee22221efaf5e7a715c8b95dff261bee62f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249723"
---
# <a name="reverse-posted-lease-transactions"></a><span data-ttu-id="613dd-104">Contrepasser les transactions de bail validées</span><span class="sxs-lookup"><span data-stu-id="613dd-104">Reverse posted lease transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="613dd-105">Toute transaction créée via la location d’actifs peut être annulée.</span><span class="sxs-lookup"><span data-stu-id="613dd-105">Any transaction that is created through Asset leasing can be reversed.</span></span> <span data-ttu-id="613dd-106">Les transactions annulées via la location d’actifs mettent à jour vos données de location.</span><span class="sxs-lookup"><span data-stu-id="613dd-106">Transactions that are reversed through Asset leasing update your lease data.</span></span> <span data-ttu-id="613dd-107">Par conséquent, elles mettent également à jour les valeurs comptables du passif locatif et du droit d’utilisation de l’actif.</span><span class="sxs-lookup"><span data-stu-id="613dd-107">Therefore, they also update the carrying values of the lease liability and right-of-use (ROU) asset.</span></span>

<span data-ttu-id="613dd-108">Pour créer une transaction de contrepassation pour une location, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="613dd-108">To create a reversing transaction for a lease, follow these steps.</span></span>

1. <span data-ttu-id="613dd-109">Sur la page **Transactions d’actifs** ou la page **Transactions de passif**, sélectionnez la transaction, puis sélectionnez **Contrepasser la transaction**.</span><span class="sxs-lookup"><span data-stu-id="613dd-109">On either the **Asset transactions** page or the **Liability transactions** page, select the transaction, and then select **Reverse transaction**.</span></span>
2. <span data-ttu-id="613dd-110">Dans la boîte de dialogue qui apparaît, vous pouvez modifier la date à laquelle l’écriture de contrepassation sera validée.</span><span class="sxs-lookup"><span data-stu-id="613dd-110">In the dialog box that appears, you can edit the date when the reversing entry will be posted.</span></span> <span data-ttu-id="613dd-111">Par défaut, le champ **Date** est défini sur la date comptable de la transaction que vous avez sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="613dd-111">By default, the **Date** field is set to the transaction posting date of the transaction that you selected.</span></span> <span data-ttu-id="613dd-112">L’écriture de contrepassation ne peut pas être validée avant la date comptable d’origine de la transaction sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="613dd-112">The reversing entry can't be posted earlier than the original posting date of the selected transaction.</span></span>
3. <span data-ttu-id="613dd-113">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="613dd-113">Select **OK**.</span></span> <span data-ttu-id="613dd-114">Une entrée de journal est validée qui annule l’écriture que vous avez sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="613dd-114">A journal entry is posted that reverses the entry that you selected.</span></span> <span data-ttu-id="613dd-115">La Contrepassation est indiquée sur la page **Transactions d’actifs** ou **Transactions de passif** et le total net du solde actuel affiché sur la page est mis à jour.</span><span class="sxs-lookup"><span data-stu-id="613dd-115">The reversal is shown on the **Asset transactions** or **Liability transactions** page, and the net total of the current balance that is shown on the page is updated.</span></span>

<span data-ttu-id="613dd-116">Lorsque vous sélectionnez **Suivi de la Contrepassation**, une boîte de dialogue apparaît et affiche à la fois les transactions d’origine et les transactions annulées, ainsi qu’un numéro lié appelé *Numéro de trace*.</span><span class="sxs-lookup"><span data-stu-id="613dd-116">When you select **Reverse tracing**, a dialog box appears that shows both the original transactions and the reversed transactions, together with a linked number that is known as a *trace number*.</span></span> <span data-ttu-id="613dd-117">Pour faciliter la compréhension des annulations et améliorer la visibilité, vous pouvez également suivre les annulations à l’aide des échéanciers de location.</span><span class="sxs-lookup"><span data-stu-id="613dd-117">To make the reversals easier to understand and to improve visibility, you can also track reversals by using the lease schedules.</span></span>

<span data-ttu-id="613dd-118">Le champ **Dernier numéro de journal** sur la page **Échéancier** affiche les numéros de journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="613dd-118">The **Latest journal number** field on the **Schedule** page shows the journal numbers of transactions.</span></span> <span data-ttu-id="613dd-119">Lorsqu’une transaction est annulée, ce champ est mis à jour avec le numéro de journal d’une transaction d’annulation.</span><span class="sxs-lookup"><span data-stu-id="613dd-119">When a transaction is reversed, this field is updated with the journal number of a reversing transaction.</span></span> <span data-ttu-id="613dd-120">De plus, la case **Contrepassé** est cochée pour indiquer que la transaction est annulée et le champ **Validé** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="613dd-120">Additionally, the **Reversed** check box is selected to indicate that the transaction is reversed, and the **Posted** field is selected.</span></span>

## <a name="revoke-a-reversed-transaction"></a><span data-ttu-id="613dd-121">Annuler une transaction contrepassée</span><span class="sxs-lookup"><span data-stu-id="613dd-121">Revoke a reversed transaction</span></span>

<span data-ttu-id="613dd-122">Pour révoquer une transaction Contrepassée, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="613dd-122">To revoke a reversed transaction, follow these steps.</span></span>

1. <span data-ttu-id="613dd-123">Sur la page **Échéancier** ou la page **Transactions**, sélectionnez la transaction d’origine.</span><span class="sxs-lookup"><span data-stu-id="613dd-123">On either the **Schedule** page or the **Transactions** page, select the original transaction.</span></span>
2. <span data-ttu-id="613dd-124">Utilisez l’une des procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="613dd-124">Follow one of these steps:</span></span>

    - <span data-ttu-id="613dd-125">Si vous avez sélectionné la transaction sur la page **Échéancier**, suivez les étapes de création d’un journal dans [Créer des entrées de journal mensuelles dans un lot](create-monthly-journals-batch.md).</span><span class="sxs-lookup"><span data-stu-id="613dd-125">If you selected the transaction on the **Schedule** page, follow the steps for creating a journal in [Create monthly journal entries in a batch](create-monthly-journals-batch.md).</span></span> <span data-ttu-id="613dd-126">Vous devez valider manuellement le journal.</span><span class="sxs-lookup"><span data-stu-id="613dd-126">You must manually post the journal.</span></span>
    - <span data-ttu-id="613dd-127">Si vous avez sélectionné la transaction sur la page **Transactions**, sélectionnez **Contrepasser la transaction**.</span><span class="sxs-lookup"><span data-stu-id="613dd-127">If you selected the transaction on the **Transactions** page, select **Reverse transaction**.</span></span> <span data-ttu-id="613dd-128">Vous recevez un message indiquant que cette révocation est une révocation d’une contrepassation antérieure et que vous pouvez modifier la date comptable de cette révocation.</span><span class="sxs-lookup"><span data-stu-id="613dd-128">You receive a message that states that this revocation is a revocation of an earlier reversal, and that you can edit the posting date for this revocation.</span></span> <span data-ttu-id="613dd-129">Cependant, les validations commerciales générales affectent les dates qui peuvent être saisies dans le champ **Date**.</span><span class="sxs-lookup"><span data-stu-id="613dd-129">However, general business validations affect the dates that can be entered in the **Date** field.</span></span> 

3. <span data-ttu-id="613dd-130">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="613dd-130">Select **OK**.</span></span> <span data-ttu-id="613dd-131">Une entrée de journal est validée qui annule l’écriture que vous avez sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="613dd-131">A journal entry is posted that reverses the entry that you selected.</span></span> <span data-ttu-id="613dd-132">La Contrepassation est indiquée sur la page **Transactions**, et le solde courant total net est rétabli à ce qu’il était avant la première Contrepassation.</span><span class="sxs-lookup"><span data-stu-id="613dd-132">The reversal is shown on the **Transactions** page, and the net total current balance is restored to what it was before the first reversal.</span></span> <span data-ttu-id="613dd-133">Par conséquent, l’impact de la contrepassation sur les soldes est annulé.</span><span class="sxs-lookup"><span data-stu-id="613dd-133">Therefore, the impact that the reversal had on the balances is negated.</span></span>

<span data-ttu-id="613dd-134">Lorsque vous sélectionnez **Suivi de la Contrepassation**, une boîte de dialogue apparaît et affiche à la fois les transactions d’origine et les transactions annulées, ainsi qu’un numéro de trace.</span><span class="sxs-lookup"><span data-stu-id="613dd-134">When you select **Reverse tracing**, a dialog box appears that shows both the original transactions and the reversed transactions, together with a linked trace number.</span></span>

<span data-ttu-id="613dd-135">Vous pouvez également suivre les révocations en utilisant la page **Échéanciers**.</span><span class="sxs-lookup"><span data-stu-id="613dd-135">You can also track revocations by using the appropriate **Schedules** page.</span></span> <span data-ttu-id="613dd-136">Le champ **Contrepasser** est effacé, alors que le champ **Journal validé** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="613dd-136">The **Reverse** field is cleared, whereas the **Journal posted** field is selected.</span></span> <span data-ttu-id="613dd-137">De plus, le champ **Dernier numéro de journal** est mis à jour avec le numéro de journal de la transaction de révocation et le champ **Numéro de journal** est mis à jour avec le numéro de journal de contrepassation.</span><span class="sxs-lookup"><span data-stu-id="613dd-137">Additionally, the **Latest journal number** field is updated with the journal number of the revocation transaction, and the **Journal number** field is updated with the reversal journal number.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]