---
title: Configurations de paiements pour les relevés de vente au détail
description: Cette procédure illustre les configurations de modes de paiement des magasins de commerce qui affectent la création et la validation des relevés de vente au détail.
author: jashanno
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: edd4a73523934e1fd70995c9275c564a50809957
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796704"
---
# <a name="payment-configurations-for-retail-statements"></a><span data-ttu-id="7edfd-103">Configurations de paiements pour les relevés de vente au détail</span><span class="sxs-lookup"><span data-stu-id="7edfd-103">Payment configurations for Retail statements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7edfd-104">Cette procédure illustre les configurations de modes de paiement des magasins de commerce qui affectent la création et la validation des relevés de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="7edfd-104">This procedure demonstrates configurations for Commerce store payment methods, which affect how statements get created and posted.</span></span>

<span data-ttu-id="7edfd-105">La société fictive USRT sert d’exemple dans cet enregistrement.</span><span class="sxs-lookup"><span data-stu-id="7edfd-105">This recording uses the USRT demo company.</span></span>

1. <span data-ttu-id="7edfd-106">Accédez à Retail et Commerce > Canaux > Magasins > Tous les magasins.</span><span class="sxs-lookup"><span data-stu-id="7edfd-106">Go to Retail and Commerce > Channels > Stores > All stores.</span></span>
2. <span data-ttu-id="7edfd-107">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="7edfd-107">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="7edfd-108">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7edfd-108">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="7edfd-109">Dans le volet Actions, cliquez sur Paramétrer.</span><span class="sxs-lookup"><span data-stu-id="7edfd-109">On the Action Pane, click Set up.</span></span>
5. <span data-ttu-id="7edfd-110">Cliquez sur Modes de paiement.</span><span class="sxs-lookup"><span data-stu-id="7edfd-110">Click Payment methods.</span></span>
6. <span data-ttu-id="7edfd-111">Développez ou réduisez la section Validation.</span><span class="sxs-lookup"><span data-stu-id="7edfd-111">Expand or collapse the Posting section.</span></span>
7. <span data-ttu-id="7edfd-112">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="7edfd-112">Click Edit.</span></span>
    * <span data-ttu-id="7edfd-113">Sélectionnez si les montants reçus pour ce mode de paiement doivent être validés dans un compte général ou sur un compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="7edfd-113">Select whether the amounts received for this payment method should be posted to a ledger account or bank account.</span></span>  
    * <span data-ttu-id="7edfd-114">Sélectionnez le compte dans lequel valider les montants reçus par le biais de ce mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="7edfd-114">Select the account that amounts received for this payment method should be posted to.</span></span>  
    * <span data-ttu-id="7edfd-115">Sélectionnez un compte pour valider les différences possibles entre le montant total de la transaction reçu et le montant compté pour ce mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="7edfd-115">Select an account to post possible differences between the total transaction amount received and the amount counted for this payment method.</span></span>  
    * <span data-ttu-id="7edfd-116">Ce champ vous permet de spécifier un montant à contrôler lorsque le montant de la différence doit être validé dans un autre compte de différence.</span><span class="sxs-lookup"><span data-stu-id="7edfd-116">In this field you can enter an amount to control when the difference amount should be posted to another difference account.</span></span> <span data-ttu-id="7edfd-117">Vous pouvez utiliser cette option pour effectuer le suivi des grandes différences.</span><span class="sxs-lookup"><span data-stu-id="7edfd-117">You can use this to track big differences.</span></span>  
    * <span data-ttu-id="7edfd-118">Sélectionnez un compte pour la validation des différences possibles entre le montant total de la transaction reçu et le montant compté, lorsqu’il dépasse la valeur définie dans le champ « Montant de différence maximale ».</span><span class="sxs-lookup"><span data-stu-id="7edfd-118">Select an account to post possible differences between the total transaction amount received and the amount counted, when it exceeds the value that is defined in the "Maximum difference amount" field.</span></span>  
    * <span data-ttu-id="7edfd-119">Sélectionnez « Oui » pour valider les montants de remise en banque dans un compte distinct.</span><span class="sxs-lookup"><span data-stu-id="7edfd-119">Select "Yes" to post bank drop amounts to a separate account.</span></span>  
    * <span data-ttu-id="7edfd-120">Ce champ vous permet de sélectionner si les montants de remise en banque doivent être validés dans un compte général ou sur un compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="7edfd-120">In this field you can select whether bank drop amounts should be posted to a ledger account or a bank account.</span></span>  
    * <span data-ttu-id="7edfd-121">Sélectionnez le compte sur lequel valider les montants de remise en banque.</span><span class="sxs-lookup"><span data-stu-id="7edfd-121">Select the account to post bank drop amounts into.</span></span>  
    * <span data-ttu-id="7edfd-122">Sélectionnez le type de transaction bancaire à utiliser lors de la validation de montants de remise en banque sur le compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="7edfd-122">Select the bank transaction type to use when posting bank drop amounts to the bank account.</span></span>  
    * <span data-ttu-id="7edfd-123">Sélectionnez « Oui » pour valider les montants de mise en coffre-fort sur un compte distinct.</span><span class="sxs-lookup"><span data-stu-id="7edfd-123">Select "Yes" to post safe drop amounts to a separate account.</span></span>  
    * <span data-ttu-id="7edfd-124">Sélectionnez si les montants de mise en coffre-fort doivent être validés sur le compte général ou le compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="7edfd-124">Select whether safe drop amounts should be posted to the ledger account or the bank account.</span></span>  
    * <span data-ttu-id="7edfd-125">Sélectionnez le compte sur lequel valider les montants de mise en coffre-fort.</span><span class="sxs-lookup"><span data-stu-id="7edfd-125">Select the account to post safe drop amounts into.</span></span>  
8. <span data-ttu-id="7edfd-126">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="7edfd-126">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]