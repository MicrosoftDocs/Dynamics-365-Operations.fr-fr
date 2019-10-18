---
title: Contrepasser la validation du journal
description: Cette rubrique décrit les fonctionnalités qui vous permettent de contrepasser les documents provenant de la liste de transaction de documents ou provenant des journaux financiers.
author: MikeFalkner
manager: AnnBe
ms.date: 08/01/2019
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
ms.openlocfilehash: 5a5456e60f1f3cee5f83ac7f725f7e01ba5bd7a1
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2248583"
---
# <a name="reverse-journal-posting"></a><span data-ttu-id="ef789-103">Contrepasser la validation du journal</span><span class="sxs-lookup"><span data-stu-id="ef789-103">Reverse journal posting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ef789-104">Cette rubrique décrit les fonctionnalités Microsoft Dynamics 365 Finance qui vous permettent de contrepasser un journal entier ou de contrepasser un ou plusieurs documents provenant de la liste de transactions de documents, peu importe leur origine.</span><span class="sxs-lookup"><span data-stu-id="ef789-104">This topic describes capabilities Microsoft Dynamics 365 Finance that allows you to reverse an entire journal or reverse one or more vouchers from the voucher transaction list regardless of their origin.</span></span> 

## <a name="reversing-journals"></a><span data-ttu-id="ef789-105">Contrepassation des journaux</span><span class="sxs-lookup"><span data-stu-id="ef789-105">Reversing journals</span></span>

<span data-ttu-id="ef789-106">Vous pouvez contrepasser des lignes de journal individuellement.</span><span class="sxs-lookup"><span data-stu-id="ef789-106">You can reverse journal lines individually.</span></span> <span data-ttu-id="ef789-107">Avec la contrepassation de la validation du journal, vous pouvez également contrepasser tout un journal financier.</span><span class="sxs-lookup"><span data-stu-id="ef789-107">With reverse journal posting, you can also reverse an entire financial journal.</span></span> <span data-ttu-id="ef789-108">Pour contrepasser un journal :</span><span class="sxs-lookup"><span data-stu-id="ef789-108">To reverse a journal:</span></span> 
- <span data-ttu-id="ef789-109">Ouvrez le journal financier et filtrez selon les journaux validés.</span><span class="sxs-lookup"><span data-stu-id="ef789-109">Open the financial journal and filter on posted journals</span></span>
- <span data-ttu-id="ef789-110">Cliquez sur le menu Contrepasser en haut de la page.</span><span class="sxs-lookup"><span data-stu-id="ef789-110">Click on the Reverse menu at the top of the page</span></span>
- <span data-ttu-id="ef789-111">Vous verrez le nombre total de documents et les lignes de documents ainsi que le volume total des lignes contrepassées.</span><span class="sxs-lookup"><span data-stu-id="ef789-111">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed</span></span>
- <span data-ttu-id="ef789-112">Sélectionnez Oui pour utiliser les dates de transaction existantes ou Non pour en saisir de nouvelles.</span><span class="sxs-lookup"><span data-stu-id="ef789-112">Select Yes to use the existing transaction dates or No to enter a new one.</span></span> <span data-ttu-id="ef789-113">Dans certains cas, la période de la transaction d'origine peut être clôturée et vous pouvez saisir une nouvelle date de transaction pour la contrepassation.</span><span class="sxs-lookup"><span data-stu-id="ef789-113">In some cases, the period of the original transaction may be closed and you want to enter a new transaction date for the reversal.</span></span>
- <span data-ttu-id="ef789-114">Si vous choisissez Non, entrez une date de transaction pour la contrepassation.</span><span class="sxs-lookup"><span data-stu-id="ef789-114">If you selected No, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="ef789-115">Saisissez un commentaire que vous souhaitez ajouter à la transaction de contrepassation.</span><span class="sxs-lookup"><span data-stu-id="ef789-115">Enter a comment that you want added to the reversal transaction</span></span>
- <span data-ttu-id="ef789-116">Cliquez sur le bouton Contrepasser.</span><span class="sxs-lookup"><span data-stu-id="ef789-116">Click the Reverse button</span></span>

<span data-ttu-id="ef789-117">Les transactions seront contrepassées.</span><span class="sxs-lookup"><span data-stu-id="ef789-117">The transactions will be reversed.</span></span> 

<span data-ttu-id="ef789-118">Si le nombre de lignes de documents dépasse la centaine, le processus de contrepassation sera exécuté avec le processus de traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="ef789-118">If the number of voucher lines exceeds 100 lines, the reversal process will be run using the batch process.</span></span> <span data-ttu-id="ef789-119">Vous pouvez examiner les résultats de la contrepassation en affichant les commentaires dans le traitement par lots qui a été exécuté.</span><span class="sxs-lookup"><span data-stu-id="ef789-119">You can review the results of the reversal by viewing the comments in the batch job that was run.</span></span> <span data-ttu-id="ef789-120">Tous les échecs sont mentionnés dans l'historique des traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="ef789-120">All failures will be noted in the batch job history.</span></span>

<span data-ttu-id="ef789-121">Si le nombre de lignes de documents est inférieur ou égal à cent, le processus de contrepassation s'exécute immédiatement.</span><span class="sxs-lookup"><span data-stu-id="ef789-121">If the number of voucher lines is 100 lines or less, the reversal process will run immediately.</span></span> <span data-ttu-id="ef789-122">Les résultats seront présentés dans une boîte de dialogue qui indique tout document qui n'a pas pu être contrepassé et la raison de cet échec.</span><span class="sxs-lookup"><span data-stu-id="ef789-122">The results will be presented in a dialog that shows any voucher that could not be reversed and the reason why it could not be reversed.</span></span> <span data-ttu-id="ef789-123">Cliquez sur OK pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="ef789-123">Click on Ok to close the dialog.</span></span>

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a><span data-ttu-id="ef789-124">Contrepassation des documents provenant de la liste de transaction de documents.</span><span class="sxs-lookup"><span data-stu-id="ef789-124">Reversing vouchers from the voucher transaction list.</span></span> 

<span data-ttu-id="ef789-125">Vous pouvez également contrepasser les documents provenant de la **Liste des transactions des documents** parmi toutes les comptabilités auxiliaires.</span><span class="sxs-lookup"><span data-stu-id="ef789-125">You can also reverse vouchers from the **Voucher transaction list** across all subledgers.</span></span> <span data-ttu-id="ef789-126">En outre, vous pouvez contrepasser plusieurs documents à la fois.</span><span class="sxs-lookup"><span data-stu-id="ef789-126">In addition, you can reverse more than one voucher at a time.</span></span> 

<span data-ttu-id="ef789-127">Pour ce faire, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="ef789-127">To reverse one or more vouchers:</span></span> 
- <span data-ttu-id="ef789-128">Cliquez sur le menu Contrepasser en haut de la page.</span><span class="sxs-lookup"><span data-stu-id="ef789-128">Click on the Reverse menu at the top of the page</span></span>
- <span data-ttu-id="ef789-129">Vous verrez le nombre total de documents et les lignes de documents ainsi que le volume total des lignes contrepassées.</span><span class="sxs-lookup"><span data-stu-id="ef789-129">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed</span></span>
- <span data-ttu-id="ef789-130">Sélectionnez Oui pour utiliser les dates de transaction existantes ou Non pour en saisir de nouvelles.</span><span class="sxs-lookup"><span data-stu-id="ef789-130">Select Yes to use the existing transaction dates or No to enter a new one.</span></span> <span data-ttu-id="ef789-131">Dans certains cas, la période de la transaction d'origine peut être clôturée et vous pouvez saisir une nouvelle date de transaction pour la contrepassation.</span><span class="sxs-lookup"><span data-stu-id="ef789-131">In some cases, the period of the original transaction may be closed and you want to enter a new transaction date for the reversal.</span></span>
- <span data-ttu-id="ef789-132">Si vous choisissez Non, entrez une date de transaction pour la contrepassation.</span><span class="sxs-lookup"><span data-stu-id="ef789-132">If you selected No, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="ef789-133">Saisissez un commentaire que vous souhaitez ajouter à la transaction de contrepassation.</span><span class="sxs-lookup"><span data-stu-id="ef789-133">Enter a comment that you want added to the reversal transaction</span></span>
- <span data-ttu-id="ef789-134">Cliquez sur le bouton Contrepasser.</span><span class="sxs-lookup"><span data-stu-id="ef789-134">Click the Reverse button</span></span>

<span data-ttu-id="ef789-135">Les transactions seront contrepassées.</span><span class="sxs-lookup"><span data-stu-id="ef789-135">The transactions will be reversed.</span></span> 

<span data-ttu-id="ef789-136">Si le nombre de lignes de documents dépasse la centaine, le processus de contrepassation sera exécuté avec le processus de traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="ef789-136">If the number of voucher lines exceeds 100 lines, the reversal process will be run using the batch process.</span></span> <span data-ttu-id="ef789-137">Vous pouvez examiner les résultats de la contrepassation en affichant les commentaires dans le traitement par lots qui a été exécuté.</span><span class="sxs-lookup"><span data-stu-id="ef789-137">You can review the results of the reversal by viewing the comments in the batch job that was run.</span></span> <span data-ttu-id="ef789-138">Tous les échecs sont mentionnés dans l'historique des traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="ef789-138">All failures will be noted in the batch job history.</span></span>

<span data-ttu-id="ef789-139">Si le nombre de lignes de documents est inférieur ou égal à cent, le processus de contrepassation s'exécute immédiatement.</span><span class="sxs-lookup"><span data-stu-id="ef789-139">If the number of voucher lines is 100 lines or less, the reversal process will run immediately.</span></span> <span data-ttu-id="ef789-140">Les résultats seront présentés dans une boîte de dialogue qui indique tout document qui n'a pas pu être contrepassé et la raison de cet échec.</span><span class="sxs-lookup"><span data-stu-id="ef789-140">The results will be presented in a dialog that shows any voucher that could not be reversed and the reason why it could not be reversed.</span></span> <span data-ttu-id="ef789-141">Cliquez sur OK pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="ef789-141">Click on Ok to close the dialog.</span></span>

