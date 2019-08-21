---
title: Lettres de garantie
description: Cet article fournit des informations sur les lettres de garantie. Dans une lettre de garantie, une banque s'engage à payer une somme d'argent spécifique à une personne si l'un des clients de la banque ne règle pas un paiement ou une obligation au bénéficiaire.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankLGGuarantee
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 18291
ms.assetid: 5c0b5e37-d51d-4a01-bb37-1882173abb9f
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7e7ab2e66c378388d002d2f2090f89bf6c96dac2
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1842327"
---
# <a name="letters-of-guarantee"></a><span data-ttu-id="8f071-104">Lettres de garantie</span><span class="sxs-lookup"><span data-stu-id="8f071-104">Letters of guarantee</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8f071-105">Cet article fournit des informations sur les lettres de garantie.</span><span class="sxs-lookup"><span data-stu-id="8f071-105">This article provides information about letters of guarantee.</span></span> <span data-ttu-id="8f071-106">Dans une lettre de garantie, une banque s'engage à payer une somme d'argent spécifique à une personne si l'un des clients de la banque ne règle pas un paiement ou une obligation au bénéficiaire.</span><span class="sxs-lookup"><span data-stu-id="8f071-106">In a letter of guarantee, a bank agrees to pay a specific amount of money to a person if one of the bank's customers defaults on a payment or obligation to that person.</span></span> 

<span data-ttu-id="8f071-107">Une lettre de garantie représente l'accord d'une banque (le garant) de payer une somme d'argent définie à une autre personne (le bénéficiaire) si un client de la banque (le donneur d'ordre) ne règle pas un paiement ou une obligation au bénéficiaire.</span><span class="sxs-lookup"><span data-stu-id="8f071-107">A letter of guarantee is an agreement by a bank (the guarantor) to pay a set amount of money to some person (the beneficiary) if a bank customer (the principal) defaults on a payment or an obligation to the beneficiary.</span></span> <span data-ttu-id="8f071-108">Les lettres de garantie ne sont pas cessibles.</span><span class="sxs-lookup"><span data-stu-id="8f071-108">Letters of guarantee aren't transferable.</span></span> <span data-ttu-id="8f071-109">Elles ne s'appliquent qu'au bénéficiaire nommé dans l'accord.</span><span class="sxs-lookup"><span data-stu-id="8f071-109">They apply only to the beneficiary who is named in the agreement.</span></span> <span data-ttu-id="8f071-110">Le donneur d'ordre peut demander l'augmentation ou la diminution de la valeur d'une lettre de garantie, sous réserve des conditions stipulées dans l'accord.</span><span class="sxs-lookup"><span data-stu-id="8f071-110">The principal can request an increase or decrease in the value of a letter of guarantee, subject to the terms of the agreement.</span></span> 

<span data-ttu-id="8f071-111">Pour liquider une lettre de garantie, le bénéficiaire doit soumettre la lettre de garantie originale et informer la banque du défaut de paiement de la part du donneur d'ordre avant la date d'expiration.</span><span class="sxs-lookup"><span data-stu-id="8f071-111">To liquidate a letter of guarantee, the beneficiary must submit the original letter of guarantee and inform the bank of the principal’s default before the expiration date.</span></span> <span data-ttu-id="8f071-112">La banque paie ensuite la somme due sur le compte du bénéficiaire, comme convenu dans les conditions de la lettre de garantie.</span><span class="sxs-lookup"><span data-stu-id="8f071-112">The bank then pays the amount that is due to the beneficiary's account, according to the terms in the letter of guarantee.</span></span> <span data-ttu-id="8f071-113">En guise de marge, elle se réserve un pourcentage du paiement.</span><span class="sxs-lookup"><span data-stu-id="8f071-113">The bank reserves a percentage of the payment as a margin.</span></span> <span data-ttu-id="8f071-114">Le pourcentage est déterminé et spécifié dans les termes de l'accord.</span><span class="sxs-lookup"><span data-stu-id="8f071-114">The percentage is agreed upon and specified in the terms of the agreement.</span></span> 

<span data-ttu-id="8f071-115">Vous pouvez créer un code pour effectuer le suivi de l'objet d'une lettre de garantie.</span><span class="sxs-lookup"><span data-stu-id="8f071-115">You can create a code to track the purpose of a letter of guarantee.</span></span> <span data-ttu-id="8f071-116">Vous pouvez également mentionner les motifs qui peuvent être associés à une lettre de garantie lors de l'annulation de cette dernière.</span><span class="sxs-lookup"><span data-stu-id="8f071-116">You can also specify the reasons that can be associated with a letter of guarantee when the letter is canceled.</span></span> <span data-ttu-id="8f071-117">Vous pouvez afficher les codes objet et les motifs de banque sur la page **Codes objet de paiement** et **Motifs de banque**.</span><span class="sxs-lookup"><span data-stu-id="8f071-117">You can view the purpose codes and bank reasons on the **Payment purpose codes** and **Bank reasons** pages.</span></span> 

<span data-ttu-id="8f071-118">Vous pouvez utiliser la page **Lettre de garantie** pour effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="8f071-118">You can use the **Letter of guarantee** page to complete these tasks:</span></span>

-   <span data-ttu-id="8f071-119">créer des écritures comptables correctes et éliminer les entrées manuelles ;</span><span class="sxs-lookup"><span data-stu-id="8f071-119">Create correct ledger entries, and eliminate manual entry.</span></span>
-   <span data-ttu-id="8f071-120">enregistrer toutes les transactions monétaires et non monétaires et effectuer le suivi des soldes de la lettre de garantie ;</span><span class="sxs-lookup"><span data-stu-id="8f071-120">Record all monetary and nonmonetary transactions, and track balances of letters of guarantee.</span></span>
-   <span data-ttu-id="8f071-121">enregistrer et effectuer le suivi du statut et de l'expiration des lettres de garantie ;</span><span class="sxs-lookup"><span data-stu-id="8f071-121">Record and track the status and expiration of letters of guarantee.</span></span>
-   <span data-ttu-id="8f071-122">générer un état qui répertorie les banques détentrices de lettres de garantie.</span><span class="sxs-lookup"><span data-stu-id="8f071-122">Generate a report that lists the banks that are holding letters of guarantee.</span></span>

<span data-ttu-id="8f071-123">Le tableau suivant décrit les actions que vous pouvez effectuer sur une mettre de garantie.</span><span class="sxs-lookup"><span data-stu-id="8f071-123">The following table describes the actions that you can perform on a letter of guarantee.</span></span>

| <span data-ttu-id="8f071-124">Action</span><span class="sxs-lookup"><span data-stu-id="8f071-124">Action</span></span>              | <span data-ttu-id="8f071-125">Objectif</span><span class="sxs-lookup"><span data-stu-id="8f071-125">Purpose</span></span>                                                                                                                   |
|---------------------|---------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="8f071-126">Remettre à la banque</span><span class="sxs-lookup"><span data-stu-id="8f071-126">Submit to bank</span></span>      | <span data-ttu-id="8f071-127">Cette action permet de soumettre la demande de lettre de garantie à la banque.</span><span class="sxs-lookup"><span data-stu-id="8f071-127">Submit the letter of guarantee request to the bank.</span></span>                                                                       |
| <span data-ttu-id="8f071-128">Recevoir de la banque</span><span class="sxs-lookup"><span data-stu-id="8f071-128">Receive from bank</span></span>   | <span data-ttu-id="8f071-129">Dès que la banque a approuvé la demande soumise, cette action permet de récupérer la lettre de garantie auprès de la banque.</span><span class="sxs-lookup"><span data-stu-id="8f071-129">After the bank agrees to the submitted request, collect the letter of guarantee from the bank.</span></span>                            |
| <span data-ttu-id="8f071-130">Remettre au bénéficiaire</span><span class="sxs-lookup"><span data-stu-id="8f071-130">Give to beneficiary</span></span> | <span data-ttu-id="8f071-131">Après avoir reçu la lettre de garantie de la banque, cette action permet de la remettre au bénéficiaire.</span><span class="sxs-lookup"><span data-stu-id="8f071-131">After you receive the letter of guarantee from the bank, provide the letter of guarantee to the beneficiary.</span></span>              |
| <span data-ttu-id="8f071-132">Augmenter la valeur</span><span class="sxs-lookup"><span data-stu-id="8f071-132">Increase value</span></span>      | <span data-ttu-id="8f071-133">Si le bénéficiaire ainsi que le donneur d'ordre approuvent, cette action permet d'augmenter la valeur monétaire.</span><span class="sxs-lookup"><span data-stu-id="8f071-133">If the beneficiary and the principal agree, increase the monetary value.</span></span>                                                  |
| <span data-ttu-id="8f071-134">Diminuer la valeur</span><span class="sxs-lookup"><span data-stu-id="8f071-134">Decrease value</span></span>      | <span data-ttu-id="8f071-135">Si le bénéficiaire ainsi que le donneur d'ordre approuvent, cette action permet de diminuer la valeur monétaire.</span><span class="sxs-lookup"><span data-stu-id="8f071-135">If the beneficiary and the principal agree, decrease the monetary value.</span></span>                                                  |
| <span data-ttu-id="8f071-136">Étendre</span><span class="sxs-lookup"><span data-stu-id="8f071-136">Extend</span></span>              | <span data-ttu-id="8f071-137">Après avoir remis la lettre de garantie au bénéficiaire, cette action permet d'étendre la période de validité si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="8f071-137">After you provide the letter of guarantee to the beneficiary, extend the period of validity, if an extension is required.</span></span> |
| <span data-ttu-id="8f071-138">Annuler</span><span class="sxs-lookup"><span data-stu-id="8f071-138">Cancel</span></span>              | <span data-ttu-id="8f071-139">Lorsque l'objet pour lequel la lettre de garantie a été demandée ne s'applique plus, cette action permet d'annuler l'accord.</span><span class="sxs-lookup"><span data-stu-id="8f071-139">When the purpose that the letter of guarantee was requested for no longer applies, cancel the agreement.</span></span>                  |
| <span data-ttu-id="8f071-140">Liquider</span><span class="sxs-lookup"><span data-stu-id="8f071-140">Liquidate</span></span>           | <span data-ttu-id="8f071-141">Lorsque le bénéficiaire présente la lettre de garantie à la banque, cette action permet d'effectuer le décaissement de la lettre.</span><span class="sxs-lookup"><span data-stu-id="8f071-141">When the beneficiary presents the letter of guarantee to the bank, cash out the letter of guarantee.</span></span>                      |


<span data-ttu-id="8f071-142">Pour plus d'informations, voir les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="8f071-142">For more information, see the following topics:</span></span>

[<span data-ttu-id="8f071-143">Transaction de lettre de garantie</span><span class="sxs-lookup"><span data-stu-id="8f071-143">Letter of guarantee transaction</span></span>](tasks/letter-guarantee-transaction.md)

[<span data-ttu-id="8f071-144">Paramétrer les établissements bancaires et les profils de validation pour les lettres de garantie</span><span class="sxs-lookup"><span data-stu-id="8f071-144">Set up bank facilities and posting profiles for letters of guarantee</span></span>](tasks/set-up-bank-facilities-posting-profiles.md)


