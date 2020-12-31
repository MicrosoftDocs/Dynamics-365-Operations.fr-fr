---
title: Déposer les paiements client
description: Déposez des paiements client.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransCustPaym, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1d903f557fbaeb720dd4a34dc1c772be0dcb56eb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443165"
---
# <a name="deposit-customer-payments"></a><span data-ttu-id="247ab-103">Déposer les paiements client</span><span class="sxs-lookup"><span data-stu-id="247ab-103">Deposit customer payments</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="247ab-104">Déposez des paiements client.</span><span class="sxs-lookup"><span data-stu-id="247ab-104">Deposit customer payments.</span></span> <span data-ttu-id="247ab-105">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="247ab-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="247ab-106">Accédez à **Volet de navigation > Modules > Comptabilité client > Paiements > Journal des paiements**.</span><span class="sxs-lookup"><span data-stu-id="247ab-106">Go to **Navigation pane > Modules > Accounts receivable > Payments > Payment journal**.</span></span>
2. <span data-ttu-id="247ab-107">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="247ab-107">Select **New**.</span></span>
3. <span data-ttu-id="247ab-108">Dans le champ **Nom**, sélectionnez **CustPay** dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="247ab-108">In the **Name** field, select **CustPay** in the drop-down menu.</span></span>
4. <span data-ttu-id="247ab-109">Sélectionnez **Lignes**.</span><span class="sxs-lookup"><span data-stu-id="247ab-109">Select **Lines**.</span></span>
5. <span data-ttu-id="247ab-110">Dans le champ **Compte**, sélectionnez le client pour lequel vous enregistrez le paiement.</span><span class="sxs-lookup"><span data-stu-id="247ab-110">In the **Account** field, select the customer for whom you are recording the payment.</span></span>
6. <span data-ttu-id="247ab-111">Dans le champ **Crédit**, entrez le montant du paiement.</span><span class="sxs-lookup"><span data-stu-id="247ab-111">In the **Credit** field, enter the amount of the payment.</span></span> <span data-ttu-id="247ab-112">Vous pouvez choisir de laisser le montant de ce champ vide, et laisser le système le calculer en sélectionnant les factures qui ont été payées.</span><span class="sxs-lookup"><span data-stu-id="247ab-112">You can choose to leave the amount blank, and have the system calculate it by selecting the invoices which were paid.</span></span>  
7. <span data-ttu-id="247ab-113">Tapez une valeur dans le champ **Référence de paiement**.</span><span class="sxs-lookup"><span data-stu-id="247ab-113">In the **Payment reference** field, type a value.</span></span> <span data-ttu-id="247ab-114">La référence de paiement peut être le numéro de chèque pour le paiement que vous entrez.</span><span class="sxs-lookup"><span data-stu-id="247ab-114">The payment reference could be the check number for the payment you are entering.</span></span> <span data-ttu-id="247ab-115">La référence de paiement est requise pour inclure le paiement sur un bordereau de remise.</span><span class="sxs-lookup"><span data-stu-id="247ab-115">The payment reference is required in order to include the payment on a deposit slip.</span></span>  
8. <span data-ttu-id="247ab-116">Cochez la case Utiliser un bordereau de remise.</span><span class="sxs-lookup"><span data-stu-id="247ab-116">Mark the box Use a deposit slip.</span></span> <span data-ttu-id="247ab-117">Si le paiement doit être inclus dans le dépôt, définissez ce paramètre sur Oui.</span><span class="sxs-lookup"><span data-stu-id="247ab-117">If the payment should be included in the deposit, change this setting to Yes.</span></span>  
9. <span data-ttu-id="247ab-118">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="247ab-118">Select **New**.</span></span>
10. <span data-ttu-id="247ab-119">Dans le champ **Compte**, sélectionnez le client pour le paiement suivant.</span><span class="sxs-lookup"><span data-stu-id="247ab-119">In the **Account** field, select the customer for the next payment.</span></span>
11. <span data-ttu-id="247ab-120">Dans le champ **Crédit**, entrez le montant du paiement.</span><span class="sxs-lookup"><span data-stu-id="247ab-120">In the **Credit** field, enter the payment amount.</span></span>
12. <span data-ttu-id="247ab-121">Tapez une valeur dans le champ **Référence de paiement**.</span><span class="sxs-lookup"><span data-stu-id="247ab-121">In the **Payment reference** field, type a value.</span></span>
13. <span data-ttu-id="247ab-122">Cochez la case **Utiliser un bordereau de remise**.</span><span class="sxs-lookup"><span data-stu-id="247ab-122">Mark the box **Use a deposit slip**.</span></span>
14. <span data-ttu-id="247ab-123">Sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="247ab-123">Select **Post**.</span></span> <span data-ttu-id="247ab-124">Les paiements doivent être validés avant que le bordereau de remise puisse être généré.</span><span class="sxs-lookup"><span data-stu-id="247ab-124">Payments must be posted before the deposit slip can be generated.</span></span> <span data-ttu-id="247ab-125">Cela permet de garantir que les paiements ne changent pas une fois le bordereau de remise généré.</span><span class="sxs-lookup"><span data-stu-id="247ab-125">This is to ensure that the payments don't change after the deposit slip is generated.</span></span>  
15. <span data-ttu-id="247ab-126">Sélectionnez **Fonctions**.</span><span class="sxs-lookup"><span data-stu-id="247ab-126">Select **Functions**.</span></span>
16. <span data-ttu-id="247ab-127">Sélectionnez **Bordereau de remise**.</span><span class="sxs-lookup"><span data-stu-id="247ab-127">Select **Deposit slip**.</span></span>
17. <span data-ttu-id="247ab-128">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="247ab-128">Select **OK**.</span></span> <span data-ttu-id="247ab-129">La première page permet de créer le bordereau de remise.</span><span class="sxs-lookup"><span data-stu-id="247ab-129">The first page is used to create the deposit slip.</span></span>  
18. <span data-ttu-id="247ab-130">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="247ab-130">Select **OK**.</span></span> <span data-ttu-id="247ab-131">La deuxième étape consiste à imprimer le bordereau de remise, mais cette étape n’est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="247ab-131">The second step is to print the deposit slip, but this step is not required.</span></span>  

