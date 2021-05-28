---
title: Soldes d’ouverture manquants à la clôture de fin d’exercice
description: Cette rubrique explique pourquoi les soldes d’ouverture peuvent être manquants lorsque vous clôturez un exercice et comment les reconstituer, le cas échéant.
author: kweekley
ms.date: 05/12/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 045d0bf11b11c9a353858ce3ca82c698dbceea7c
ms.sourcegitcommit: 817716c2e96f24af0ef1d7d5323afdeccdc602f3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2021
ms.locfileid: "6028563"
---
# <a name="year-end-close-missing-opening-balances"></a><span data-ttu-id="27b52-103">Soldes d’ouverture manquants à la clôture de fin d’exercice</span><span class="sxs-lookup"><span data-stu-id="27b52-103">Year-end close missing opening balances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="27b52-104">Cette rubrique explique pourquoi les soldes d’ouverture peuvent être manquants lorsque vous clôturez un exercice et comment les reconstituer, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="27b52-104">This topic explains why opening balances might be missing when you close a year, and how to rebuild those balances if they are missing.</span></span>

### <a name="symptom"></a><span data-ttu-id="27b52-105">Problème</span><span class="sxs-lookup"><span data-stu-id="27b52-105">Symptom</span></span>

<span data-ttu-id="27b52-106">Pourquoi n’y a-t-il pas de solde d’ouverture après l’exécution de la clôture de fin d’exercice de comptabilité ?</span><span class="sxs-lookup"><span data-stu-id="27b52-106">Why are there no beginning balances after running the General ledger year-end close?</span></span> 

### <a name="resolution"></a><span data-ttu-id="27b52-107">Résolution</span><span class="sxs-lookup"><span data-stu-id="27b52-107">Resolution</span></span>

<span data-ttu-id="27b52-108">Voici des éléments à vérifier si vous avez clôturé un exercice en comptabilité, puis généré une balance comptable qui n’affiche pas les soldes d’ouverture pour l’exercice suivant.</span><span class="sxs-lookup"><span data-stu-id="27b52-108">Here are things to check if you've closed a year in General ledger, and then generated a trial balance that doesn't display opening balances for the next fiscal year.</span></span>

<span data-ttu-id="27b52-109">Si le champ **Annuler la clôture précédente** est défini sur **Oui**, la clôture de fin d’exercice pour le même exercice est annulée.</span><span class="sxs-lookup"><span data-stu-id="27b52-109">If the **Undo previous close** field is set to **Yes**, the previous year-end close for the same fiscal year is being reversed.</span></span> <span data-ttu-id="27b52-110">Lors de la contrepassation de la clôture de fin d’exercice, toutes les écritures de solde de clôture et de solde d’ouverture sont supprimées, comme si l’exercice n’avait jamais été clôturé.</span><span class="sxs-lookup"><span data-stu-id="27b52-110">When running a process to reverse the year-end close, all entries for both closing and opening balances will be deleted, as if the year had never been closed.</span></span> <span data-ttu-id="27b52-111">Les justificatifs sont également supprimés.</span><span class="sxs-lookup"><span data-stu-id="27b52-111">The vouchers are also deleted.</span></span> <span data-ttu-id="27b52-112">Le processus de clôture de fin d’exercice ne s’exécutera pas à nouveau automatiquement.</span><span class="sxs-lookup"><span data-stu-id="27b52-112">The year-end close process will not run again automatically.</span></span> <span data-ttu-id="27b52-113">Vous devez recommencer le processus, cette fois en définissant l’option **Annuler la clôture précédente** sur **Non**.</span><span class="sxs-lookup"><span data-stu-id="27b52-113">You must start the process again, this time updating the **Undo previous close** option to **No**.</span></span>

<span data-ttu-id="27b52-114">Ce scénario est traité dans la rubrique FAQ sur la clôture de fin d’exercice.</span><span class="sxs-lookup"><span data-stu-id="27b52-114">This scenario is covered in the year-end close FAQ topic.</span></span> <span data-ttu-id="27b52-115">Pour plus d’informations, voir [FAQ sur les activités de fin d’exercice](faq-year-end-activities.md).</span><span class="sxs-lookup"><span data-stu-id="27b52-115">For more information, see [Year-end activities FAQ](faq-year-end-activities.md).</span></span>

### <a name="symptom"></a><span data-ttu-id="27b52-116">Problème</span><span class="sxs-lookup"><span data-stu-id="27b52-116">Symptom</span></span>

<span data-ttu-id="27b52-117">J’ai exécuté la clôture de fin d’exercice avec l’option **Annuler la clôture précédente** définie sur **Non**, et je n’ai toujours pas de soldes d’ouverture pour mon exercice.</span><span class="sxs-lookup"><span data-stu-id="27b52-117">I ran year-end close with the **Undo previous close** option set to **No**, and I still do not have opening balances for my fiscal year.</span></span>

### <a name="resolution"></a><span data-ttu-id="27b52-118">Résolution</span><span class="sxs-lookup"><span data-stu-id="27b52-118">Resolution</span></span>

<span data-ttu-id="27b52-119">Commencez par vérifier le statut du traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="27b52-119">First check the status of the batch job.</span></span> <span data-ttu-id="27b52-120">La clôture d’un exercice comprend un certain nombre de tâches distinctes, mais l’étape la plus critique est la tâche de traitement par lots avec la description de la tâche **Étape 5.0.0**.</span><span class="sxs-lookup"><span data-stu-id="27b52-120">Closing a year includes a number of separate tasks, but the most critical step is the batch task with the task description **Step 5.0.0**.</span></span> <span data-ttu-id="27b52-121">L’enregistrement des transactions d’ouverture, et éventuellement des transactions de clôture en Comptabilité a lieu au cours de cette étape.</span><span class="sxs-lookup"><span data-stu-id="27b52-121">Posting the opening transactions, and optionally the closing transactions, to General ledger takes place during this step.</span></span> 

<span data-ttu-id="27b52-122">[![Liste de l’historique des lots](./media/yec-mssng-open-blnces-01.png)](./media/yec-mssng-open-blnces-01.png)</span><span class="sxs-lookup"><span data-stu-id="27b52-122">[![Batch history list](./media/yec-mssng-open-blnces-01.png)](./media/yec-mssng-open-blnces-01.png)</span></span>

<span data-ttu-id="27b52-123">Si cette étape s’est terminée avec succès, mais que vous ne voyez pas les soldes d’ouverture sur la page **Demande de balance comptable** (**Comptabilité > Recherches et rapports > Balance comptable**), examinez les résultats du traitement par lots de la clôture de fin d’exercice pour voir si l’étape Reconstruire les soldes s’est terminée avec succès.</span><span class="sxs-lookup"><span data-stu-id="27b52-123">If this step ended successfully but you don’t see opening balances on the **Trial balance inquiry** page (**General ledger > Inquires and reports > Trial balance**), review the results of the year-end close batch job to see if the Rebuild balances step completed successfully.</span></span>

<span data-ttu-id="27b52-124">[![Résultats du traitement par lots de la clôture de fin d’exercice](./media/yec-mssng-open-blnces-02.png)](./media/yec-mssng-open-blnces-02.png)</span><span class="sxs-lookup"><span data-stu-id="27b52-124">[![Results of year-end close batch job](./media/yec-mssng-open-blnces-02.png)](./media/yec-mssng-open-blnces-02.png)</span></span>

<span data-ttu-id="27b52-125">Si cette étape a échoué pour une raison quelconque, les transactions d’ouverture (et éventuellement de clôture) ont probablement été validées avec succès.</span><span class="sxs-lookup"><span data-stu-id="27b52-125">If this step has failed for any reason, the opening (and optionally closing) transactions were likely posted successfully.</span></span> <span data-ttu-id="27b52-126">Vous pouvez vérifier que les transactions comptables ont été validées avec succès à l’aide de la page **Demande de justificatif de transaction** en spécifiant le numéro et la date du justificatif figurant dans la boîte de dialogue de clôture de fin d’exercice pour l’exercice que vous clôturez, (**Comptabilité > Recherches et états > Justificatif de transaction**).</span><span class="sxs-lookup"><span data-stu-id="27b52-126">You can verify that the General ledger transactions were posted successfully using the **Voucher transactions inquiry** page by specifying the voucher number and date provided on the year-end close dialog for the year that you closed, (**General Ledger > Inquiries and reports > Voucher transactions**).</span></span>

<span data-ttu-id="27b52-127">[![Demande de justificatif de transaction](./media/yec-mssng-open-blnces-03.png)](./media/yec-mssng-open-blnces-03.png)</span><span class="sxs-lookup"><span data-stu-id="27b52-127">[![Voucher transactions inquiry](./media/yec-mssng-open-blnces-03.png)](./media/yec-mssng-open-blnces-03.png)</span></span>

<span data-ttu-id="27b52-128">Si les justificatifs d’ouverture (et éventuellement de clôture) sont présents, vous n’avez pas besoin d’exécuter à nouveau la clôture de fin d’exercice.</span><span class="sxs-lookup"><span data-stu-id="27b52-128">If the opening (and optionally closing) vouchers are present, you don’t need to run the year-end close again.</span></span> <span data-ttu-id="27b52-129">Reportez-vous plutôt à la section suivante pour savoir comment poursuivre.</span><span class="sxs-lookup"><span data-stu-id="27b52-129">Instead refer to the next section for information about how to move forward.</span></span>

### <a name="symptom"></a><span data-ttu-id="27b52-130">Problème</span><span class="sxs-lookup"><span data-stu-id="27b52-130">Symptom</span></span>

<span data-ttu-id="27b52-131">L’étape « Reconstruire les soldes » de la clôture de fin d’exercice a échoué. Dois-je relancer tout le processus de clôture de fin d’exercice ?</span><span class="sxs-lookup"><span data-stu-id="27b52-131">The “Rebuild balances” step in the year-end close failed, do I need to re-run the entire year-end close process?</span></span>

### <a name="resolution"></a><span data-ttu-id="27b52-132">Résolution</span><span class="sxs-lookup"><span data-stu-id="27b52-132">Resolution</span></span>

<span data-ttu-id="27b52-133">L’étape Reconstruire les soldes met à jour les soldes de la comptabilité qui sont utilisés lors de la génération de la demande de balance comptable.</span><span class="sxs-lookup"><span data-stu-id="27b52-133">The Rebuild balances step updates the General ledger balances that are used when the Trial balance inquiry is generated.</span></span>  <span data-ttu-id="27b52-134">Il s’agit de la dernière étape du processus de clôture de fin d’exercice.</span><span class="sxs-lookup"><span data-stu-id="27b52-134">It is the final step in the year-end close process.</span></span>  <span data-ttu-id="27b52-135">Si cette étape est la seule qui a échoué, les transactions comptables ont été validées avec succès.</span><span class="sxs-lookup"><span data-stu-id="27b52-135">If this step is the only step that failed, the General ledger transactions have posted successfully.</span></span>  <span data-ttu-id="27b52-136">Vous n’avez pas à exécuter à nouveau la clôture de fin d’exercice.</span><span class="sxs-lookup"><span data-stu-id="27b52-136">You do not need to run the year-end close again.</span></span> <span data-ttu-id="27b52-137">Vous pouvez exécuter le processus pour reconstruire les soldes manuellement à l’aide de la page **Ensembles de dimensions financières** (**Comptabilité> Plan comptable > Dimensions > Ensembles de dimensions financières**).</span><span class="sxs-lookup"><span data-stu-id="27b52-137">You can run the process to rebuild the balances manually using the **Financial dimension sets** page (**General ledger > Chart of accounts > Dimensions > Financial dimension sets**).</span></span>

<span data-ttu-id="27b52-138">[![Bouton Reconstruire les soldes sur la page Ensembles de dimensions financières](./media/yec-mssng-open-blnces-04.png)](./media/yec-mssng-open-blnces-04.png)</span><span class="sxs-lookup"><span data-stu-id="27b52-138">[![Rebuild balances button on Financial dimension sets page](./media/yec-mssng-open-blnces-04.png)](./media/yec-mssng-open-blnces-04.png)</span></span>

<span data-ttu-id="27b52-139">Si le traitement de cette étape prend du temps, nous vous recommandons de passer en revue les meilleures pratiques pour les ensembles de dimensions financières, comme décrit dans [Bonnes pratiques pour la mise à jour des ensembles de dimensions financières](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/best-practices-for-updating-financial-dimension-set-dimension-sets).</span><span class="sxs-lookup"><span data-stu-id="27b52-139">If this step takes a long time to process, we recommend reviewing the best practices for financial dimension sets as described in [Best practices for updating Financial dimension sets](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/best-practices-for-updating-financial-dimension-set-dimension-sets).</span></span> 

