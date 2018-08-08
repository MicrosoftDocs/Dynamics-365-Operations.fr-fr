--- 
title: "Établir le mode de paiement client"
description: "Créez un mode de paiement pour les paiements client."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/26/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: b7c4c0670dbb2acd3fea1973d8a6f4f38bc94d4c
ms.contentlocale: fr-fr
ms.lasthandoff: 08/07/2018

---
# <a name="establish-customer-method-of-payment"></a><span data-ttu-id="b5ecc-103">Établir le mode de paiement client</span><span class="sxs-lookup"><span data-stu-id="b5ecc-103">Establish customer method of payment</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b5ecc-104">Créez un mode de paiement pour les paiements client.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-104">Create a method of payment for customer payments.</span></span> <span data-ttu-id="b5ecc-105">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="b5ecc-106">Accédez à Comptabilité client > Paramétrage des paiements > Modes de paiement.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-106">Go to Accounts receivable > Payments setup > Methods of payment.</span></span>
2. <span data-ttu-id="b5ecc-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-107">Click New.</span></span>
3. <span data-ttu-id="b5ecc-108">Dans le champ Mode de paiement, entrez un ID pour le mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-108">In the Method of payment field, enter an ID for the method of payment.</span></span>
    * <span data-ttu-id="b5ecc-109">L'ID du mode de paiement est indiqué sur les factures et les règlements, rendez-le assez descriptif pour comprendre quel type de paiement est enregistré, et pour quel compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-109">The Method of payment ID is shown on invoices and payments, so make it descriptive enough to understand what type of payment is being recorded, and for what bank account.</span></span>  
4. <span data-ttu-id="b5ecc-110">Entrez une description dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-110">In the Description field, enter a description.</span></span>
5. <span data-ttu-id="b5ecc-111">Sélectionnez le statut de paiement requis pour valider les paiements.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-111">Select what payment status is required in order for payments to be posted.</span></span>
    * <span data-ttu-id="b5ecc-112">Lorsque vous créez un paiement client, il peut seulement être validé lorsque le statut de paiement correspond au statut de paiement que vous définissez ici.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-112">When creating a customer payment, it can only be posted when the payment status matches the payment status you define here.</span></span>  
6. <span data-ttu-id="b5ecc-113">Sélectionnez la manière dont les paiements de clients doivent être créés pour les factures.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-113">Select how customers payments should be created for invoices.</span></span>
    * <span data-ttu-id="b5ecc-114">Cette option est uniquement utilisée lors de l'exécution d'une proposition de paiement.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-114">This option is only used when running a payment proposal.</span></span> <span data-ttu-id="b5ecc-115">Une proposition de paiement peut être utilisée pour les paiements client lorsque vous effectuez des débits directs et extrayez les fonds des comptes bancaires des clients.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-115">A payment proposal could be used for customer payments when doing direct debits, and pulling the funds from the customers' bank accounts.</span></span>  
7. <span data-ttu-id="b5ecc-116">Sélectionnez le type de paiement.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-116">Select the type of payment.</span></span>
    * <span data-ttu-id="b5ecc-117">Le type de paiement aidera à déterminer si le paiement est validé ou non.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-117">The payment type will help determine whether some validation will occur or not on the payment.</span></span>  
8. <span data-ttu-id="b5ecc-118">Sélectionnez le type de compte dans lequel les paiements seront validés.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-118">Select what account type payments will post to.</span></span>
    * <span data-ttu-id="b5ecc-119">Généralement, Banque est sélectionné pour cette option.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-119">Typically, Bank would be selected for this option.</span></span>  
9. <span data-ttu-id="b5ecc-120">Sélectionnez le compte bancaire dans lequel ce paiement sera enregistré.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-120">Select the bank account into which this payment will be recorded.</span></span>
10. <span data-ttu-id="b5ecc-121">Entrez le type de transaction bancaire pour identifier le type de paiement utilisé par votre banque.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-121">Enter the Bank transaction type to identify the type of payment used by your bank.</span></span>
    * <span data-ttu-id="b5ecc-122">Le type de transaction bancaire est utilisé lors du processus de rapprochement bancaire, et peut faciliter le rapprochement.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-122">The bank transaction type is used during the bank reconciliation process, and can make reconciliation easier.</span></span>  
11. <span data-ttu-id="b5ecc-123">Indiquez si ce paiement sera temporairement validé dans un compte de transition.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-123">Select whether this payment will temporarily post to a bridging account.</span></span>
    * <span data-ttu-id="b5ecc-124">Si vous souhaitez essayer l'heure flottante pour un paiement pour rapprocher la banque, utilisez la fonctionnalité Transition.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-124">If you want to try the float time for a payment to clear the bank, use the Bridging functionality.</span></span> <span data-ttu-id="b5ecc-125">Le paiement sera temporairement validé dans un compte général jusqu'à ce qu'il soit compensé par la banque, le paiement sera alors déplacé dans un compte bancaire que vous avez défini ici.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-125">The payment will temporarily post to a Ledger account until it clears the bank, at which time the payment will move to the bank account you defined here.</span></span>  
12. <span data-ttu-id="b5ecc-126">Entrez le compte principal utilisé pour la validation d'attente.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-126">Enter the main account used for the bridging posting.</span></span>
    * <span data-ttu-id="b5ecc-127">Il s'agit du compte principal dans lequel le paiement est temporairement validé si vous utilisez la transition.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-127">This is the main account to which the payment will temporarily post if using bridging.</span></span>  
13. <span data-ttu-id="b5ecc-128">Utilisez l'onglet Format de fichier pour définir le paramètre pour les paiements électroniques.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-128">Use the File format tab to define setting for electronic payments.</span></span>
14. <span data-ttu-id="b5ecc-129">Utilisez l'onglet Contrôle des paiements pour définir les champs qui sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-129">Use the Payment control tab to define fields that are mandatory.</span></span>
    * <span data-ttu-id="b5ecc-130">Par exemple, si tous les paiements doivent être déposés avec ce mode de paiement, vous pouvez sélectionner cette option sous cet onglet.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-130">For example, if you require all payments with this method of payment to be deposited, you can choose that option on this tab.</span></span>  
15. <span data-ttu-id="b5ecc-131">Utilisez l'onglet Attributs de paiement pour indiquer les attributs de paiement que vous souhaitez utiliser pour ce mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-131">Use the Payment attributes tab to define which payment attributes you want to use for this method of payment.</span></span>
16. <span data-ttu-id="b5ecc-132">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="b5ecc-132">Click Save.</span></span>


