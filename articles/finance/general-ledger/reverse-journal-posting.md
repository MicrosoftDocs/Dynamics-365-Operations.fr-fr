---
title: Contrepasser la validation du journal
description: Cette rubrique décrit les fonctionnalités qui vous permettent de contrepasser les documents provenant de la liste de transaction de documents ou provenant des journaux financiers.
author: MikeFalkner
manager: AnnBe
ms.date: 10/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc2ff30ef5d08759af700d683c207b0f5ed65d5b
ms.sourcegitcommit: 574309903f15eeab7911091114885b5c7279d22a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2019
ms.locfileid: "2658973"
---
# <a name="reverse-journal-posting"></a><span data-ttu-id="9c5b2-103">Contrepasser la validation du journal</span><span class="sxs-lookup"><span data-stu-id="9c5b2-103">Reverse journal posting</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="9c5b2-104">Cette rubrique décrit les fonctionnalités Microsoft Dynamics 365 Finance qui vous permettent de contrepasser un journal entier, ou de contrepasser un ou plusieurs documents provenant de la liste de transactions de documents, peu importe leur origine.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-104">This topic describes capabilities Microsoft Dynamics 365 Finance that allows you to reverse an entire journal, or reverse one or more vouchers from the voucher transaction list, regardless of their origin.</span></span> 

## <a name="reversing-journals"></a><span data-ttu-id="9c5b2-105">Contrepassation des journaux</span><span class="sxs-lookup"><span data-stu-id="9c5b2-105">Reversing journals</span></span>

<span data-ttu-id="9c5b2-106">Vous pouvez contrepasser des lignes de journal individuellement.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-106">You can reverse journal lines individually.</span></span> <span data-ttu-id="9c5b2-107">Avec la contrepassation de la validation du journal, vous pouvez également contrepasser tout un journal financier.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-107">With reverse journal posting, you can also reverse an entire financial journal.</span></span> <span data-ttu-id="9c5b2-108">Pour contrepasser un journal :</span><span class="sxs-lookup"><span data-stu-id="9c5b2-108">To reverse a journal:</span></span> 

- <span data-ttu-id="9c5b2-109">Ouvrez le journal financier et filtrez selon les journaux validés.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-109">Open the financial journal and filter on posted journals.</span></span>
- <span data-ttu-id="9c5b2-110">Sélectionnez le menu **Contrepasser** en haut de la page.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-110">Select the **Reverse** menu at the top of the page.</span></span>
- <span data-ttu-id="9c5b2-111">Vous verrez le nombre total de documents et les lignes de documents ainsi que le volume total des lignes contrepassées.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-111">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed</span></span>
- <span data-ttu-id="9c5b2-112">Sélectionnez **Oui** pour utiliser les dates de transaction existantes ou **Non** pour en saisir de nouvelles.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-112">Select **Yes** to use the existing transaction dates or **No** to enter a new one.</span></span> <span data-ttu-id="9c5b2-113">Dans certains cas, la période de la transaction d'origine peut être clôturée et vous devez saisir une nouvelle date de transaction pour la contrepassation.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-113">In some cases, the period of the original transaction may be closed and you must enter a new transaction date for the reversal.</span></span>
- <span data-ttu-id="9c5b2-114">Si vous sélectionnez **Non**, entrez une date de transaction pour la contrepassation.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-114">If you select **No**, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="9c5b2-115">Saisissez un commentaire que vous souhaitez ajouter à la transaction de contrepassation.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-115">Enter a comment that you want added to the reversal transaction.</span></span>
- <span data-ttu-id="9c5b2-116">Sélectionnez le bouton **Contrepasser**.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-116">Select the **Reverse** button.</span></span>

<span data-ttu-id="9c5b2-117">Les transactions seront contrepassées.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-117">The transactions will be reversed.</span></span> 

<span data-ttu-id="9c5b2-118">Si le document contient plus de 100 lignes, le processus de contrepassation sera exécuté avec le processus de traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-118">If the voucher contains more than 100 lines, the reversal process will run using the batch process.</span></span> <span data-ttu-id="9c5b2-119">Vous pouvez examiner les résultats en affichant les commentaires dans le traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-119">You can review the results by viewing the comments in the batch job.</span></span> <span data-ttu-id="9c5b2-120">Toutes les transactions qui ne peuvent pas être contrepassées sont répertoriées dans l'historique du traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-120">Any transactions that couldn't be reversed will be listed in the batch job history.</span></span>

<span data-ttu-id="9c5b2-121">Si le document contient 100 lignes ou moins, le processus de contrepassation s'exécute immédiatement.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-121">If the voucher contains 100 lines or fewer, the reversal process will run immediately.</span></span> <span data-ttu-id="9c5b2-122">Les résultats seront présentés dans une boîte de dialogue qui indique tout document qui n'a pas pu être contrepassé et la raison de cet échec.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-122">The results will be presented in a dialog box that shows any voucher that could not be reversed, along with the reason why it could not be reversed.</span></span> <span data-ttu-id="9c5b2-123">Sélectionnez **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-123">Select **OK** to close the dialog box.</span></span>

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a><span data-ttu-id="9c5b2-124">Contrepassation des documents provenant de la liste de transaction de documents.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-124">Reversing vouchers from the voucher transaction list.</span></span> 

<span data-ttu-id="9c5b2-125">Vous pouvez également contrepasser les documents provenant de la **Liste des transactions des documents** parmi toutes les comptabilités auxiliaires.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-125">You can also reverse vouchers from the **Voucher transaction list** across all subledgers.</span></span> <span data-ttu-id="9c5b2-126">En outre, vous pouvez contrepasser plusieurs documents à la fois.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-126">In addition, you can reverse more than one voucher at a time.</span></span> 

<span data-ttu-id="9c5b2-127">Pour ce faire, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="9c5b2-127">To reverse one or more vouchers:</span></span> 

- <span data-ttu-id="9c5b2-128">Sélectionnez le menu **Contrepasser** en haut de la page</span><span class="sxs-lookup"><span data-stu-id="9c5b2-128">Select the **Reverse** menu at the top of the page</span></span>
- <span data-ttu-id="9c5b2-129">Vous verrez le nombre total de documents et les lignes de documents ainsi que le volume total des lignes contrepassées.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-129">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed.</span></span>
- <span data-ttu-id="9c5b2-130">Sélectionnez **Oui** pour utiliser les dates de transaction existantes ou **Non** pour en saisir de nouvelles.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-130">Select **Yes** to use the existing transaction dates or **No** to enter a new one.</span></span> <span data-ttu-id="9c5b2-131">Dans certains cas, la période de la transaction d'origine peut être clôturée et vous devez saisir une nouvelle date de transaction pour la contrepasser.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-131">In some cases, the period of the original transaction may be closed and you must enter a new transaction date to reverse it.</span></span>
- <span data-ttu-id="9c5b2-132">Si vous sélectionnez **Non**, entrez une date de transaction pour la contrepassation.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-132">If you select **No**, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="9c5b2-133">Entrez un commentaire décrivant la transaction de contrepassation.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-133">Enter a comment to describe the reversal transaction.</span></span>
- <span data-ttu-id="9c5b2-134">Sélectionnez le bouton **Contrepasser**.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-134">Select the **Reverse** button.</span></span>

<span data-ttu-id="9c5b2-135">Les transactions seront contrepassées.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-135">The transactions will be reversed.</span></span> 

<span data-ttu-id="9c5b2-136">Si le document contient plus de 100 lignes document, le processus de contrepassation sera exécuté avec le processus de traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-136">If there are more than 100 voucher lines, the reversal process will run using the batch process.</span></span> <span data-ttu-id="9c5b2-137">Vous pouvez examiner les résultats en affichant les commentaires dans le traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-137">You can review the results by viewing the comments in the batch job.</span></span> <span data-ttu-id="9c5b2-138">Toutes les transactions qui ne peuvent pas être contrepassées sont notées dans l'historique du traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-138">Any transactions that couldn't be reversed will be noted in the batch job history.</span></span>

<span data-ttu-id="9c5b2-139">Si le nombre de lignes de documents est inférieur ou égal à cent, le processus de contrepassation s'exécute immédiatement.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-139">If the number of voucher lines is 100 lines or fewer, the reversal process will run immediately.</span></span> <span data-ttu-id="9c5b2-140">Les résultats seront affichés dans une boîte de dialogue qui indique tout document qui n'a pas pu être contrepassé et la raison de cet échec.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-140">The results will display in a dialog box that shows any voucher that couldn't be reversed, along with the reason why.</span></span> <span data-ttu-id="9c5b2-141">Sélectionnez **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-141">Select **OK** to close the dialog box.</span></span>

<span data-ttu-id="9c5b2-142">Les transactions peuvent être contrepassées que si elles sont conformes aux règles métier pour les contrepasser.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-142">Transactions can be reversed only if they meet the business rules for reversing them.</span></span> <span data-ttu-id="9c5b2-143">Les paiements fournisseur ne peuvent pas être contrepassés en utilisant une capacité décrite dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="9c5b2-143">Vendor payments cannot be reversed using the capability described in this topic.</span></span> <span data-ttu-id="9c5b2-144">Les paiements fournisseur doivent être contrepassés en suivant les étapes indiquées dans [Contrepasser un paiement fournisseur](https://docs.microsoft.com/en-us/dynamics365/finance/accounts-payable/reverse-vendor-payment).</span><span class="sxs-lookup"><span data-stu-id="9c5b2-144">Vendor payments must be reversed by following the steps listed in [Reverse a vendor payment](https://docs.microsoft.com/en-us/dynamics365/finance/accounts-payable/reverse-vendor-payment).</span></span>

