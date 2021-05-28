---
title: Paramétrage de chèques postdatés
description: Cette rubrique explique comment indiquer s’il faut valider les écritures de journal pour les chèques postdatés et quels journaux de validation utiliser pour les écritures de compensation et les paiements fournisseur.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankParameters, VendPaymMode, CustPaymMode
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d0d4afd74f9a0f9018629fa92ab6595bfa94f973
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026203"
---
# <a name="set-up-postdated-checks"></a><span data-ttu-id="1822f-103">Paramétrage de chèques postdatés</span><span class="sxs-lookup"><span data-stu-id="1822f-103">Set up postdated checks</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1822f-104">Cette rubrique explique comment indiquer s’il faut valider les écritures de journal pour les chèques postdatés et quels journaux de validation utiliser pour les écritures de compensation et les paiements fournisseur.</span><span class="sxs-lookup"><span data-stu-id="1822f-104">This topic explains how to specify whether to post journal entries for postdated checks and which posting journals to use for clearing entries and vendor payments.</span></span> <span data-ttu-id="1822f-105">Vous pouvez également spécifier les comptes de compensation pour les chèques émis, les chèques reçus et la retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="1822f-105">You can also specify clearing accounts for issued checks, received checks, and withholding tax.</span></span> <span data-ttu-id="1822f-106">Les chèques postdatés sont émis à des fins d’émission ou de réception de paiements à une date future.</span><span class="sxs-lookup"><span data-stu-id="1822f-106">Postdated checks that are issued to make and receive payments on a future date.</span></span> <span data-ttu-id="1822f-107">Vous pouvez indiquer si le chèque doit être pris en compte dans les registres comptables avant sa date d’échéance.</span><span class="sxs-lookup"><span data-stu-id="1822f-107">You can specify whether the check must be reflected in the accounting books before its maturity date.</span></span>



<span data-ttu-id="1822f-108">Le rôle de cette procédure Trésorier.</span><span class="sxs-lookup"><span data-stu-id="1822f-108">The role of this procedure is Treasurer.</span></span> <span data-ttu-id="1822f-109">La société fictive USMF sert d’exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="1822f-109">This procedure uses the USMF demo company.</span></span>


## <a name="set-up-postdated-checks"></a><span data-ttu-id="1822f-110">Paramétrage de chèques postdatés</span><span class="sxs-lookup"><span data-stu-id="1822f-110">Set up postdated checks</span></span>
1. <span data-ttu-id="1822f-111">Accédez à Gestion de la trésorerie et de la banque > Paramétrage > Paramètres de gestion de la trésorerie et de la banque.</span><span class="sxs-lookup"><span data-stu-id="1822f-111">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="1822f-112">Cliquez sur l’onglet Chèques postdatés.</span><span class="sxs-lookup"><span data-stu-id="1822f-112">Click the Postdated checks tab.</span></span>
3. <span data-ttu-id="1822f-113">Activez ou désactivez la case à cocher Activer les chèques postdatés.</span><span class="sxs-lookup"><span data-stu-id="1822f-113">Select or clear the Enable postdated checks check box.</span></span>
4. <span data-ttu-id="1822f-114">Activez ou désactivez les écritures de journal de validation pour la case à cocher des chèques postdatés.</span><span class="sxs-lookup"><span data-stu-id="1822f-114">Select or clear the Post journal entries for postdated checks check box.</span></span>
5. <span data-ttu-id="1822f-115">Dans le champ Compensation du compte pour des émissions de chèques, indiquez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="1822f-115">In the Clearing account for issued checks field, specify the desired values.</span></span>
6. <span data-ttu-id="1822f-116">Dans le champ Compensation du compte pour des réceptions de chèques, indiquez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="1822f-116">In the Clearing account for received checks field, specify the desired values.</span></span>
7. <span data-ttu-id="1822f-117">Dans le champ Journal des opérations diverses pour les entrées de compensation, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1822f-117">In the General journal for clearing entries field, type a value.</span></span>
8. <span data-ttu-id="1822f-118">Dans le champ Transférer les chèques postdatés vers ce journal des paiements fournisseur, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1822f-118">In the Transfer postdated checks to this vendor payment journal field, type a value.</span></span>
9. <span data-ttu-id="1822f-119">Dans le champ Montant de compensation de retenue à la source, indiquez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="1822f-119">In the Withholding tax clearing account field, specify the desired values.</span></span>
10. <span data-ttu-id="1822f-120">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="1822f-120">Click Save.</span></span>
11. <span data-ttu-id="1822f-121">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1822f-121">Close the page.</span></span>
12. <span data-ttu-id="1822f-122">Accédez à Comptabilité fournisseur > Paramétrage des paiements > Modes de paiement.</span><span class="sxs-lookup"><span data-stu-id="1822f-122">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
13. <span data-ttu-id="1822f-123">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="1822f-123">Click New.</span></span>
14. <span data-ttu-id="1822f-124">Tapez une valeur dans le champ Mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="1822f-124">In the Method of payment field, type a value.</span></span>
15. <span data-ttu-id="1822f-125">Sélectionnez l’option Validation de la compensation des chèques postdatés pour indiquer que le montant du chèque est validé dans un compte de compensation.</span><span class="sxs-lookup"><span data-stu-id="1822f-125">Select the Postdated check clearing posting option to indicate that the check amount is posted to a clearing account.</span></span>
16. <span data-ttu-id="1822f-126">Sélectionnez Banque dans le champ Type de compte.</span><span class="sxs-lookup"><span data-stu-id="1822f-126">In the Account type field, select 'Bank'.</span></span>
    * <span data-ttu-id="1822f-127">Le compte de contrepartie du mode de paiement est une banque.</span><span class="sxs-lookup"><span data-stu-id="1822f-127">The offset account of the payment method will be a bank.</span></span>  
17. <span data-ttu-id="1822f-128">Dans le champ Compte de paiement, indiquez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="1822f-128">In the Payment account field, specify the desired values.</span></span>
    * <span data-ttu-id="1822f-129">Sélectionnez le compte bancaire utilisé pour déduire le montant de la facture.</span><span class="sxs-lookup"><span data-stu-id="1822f-129">Select the bank account that is used to deduct the invoice amount.</span></span>  
18. <span data-ttu-id="1822f-130">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="1822f-130">Click Save.</span></span>
19. <span data-ttu-id="1822f-131">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1822f-131">Close the page.</span></span>
> [!NOTE]
> <span data-ttu-id="1822f-132">Pour pouvoir valider un chèque postdaté sur un compte bancaire lorsque la date de session est supérieure ou égale à la date d'échéance, vous devez activer la fonction **Validation de la date d'échéance de l'enregistrement du journal des paiements avec chèques postdatés sur le compte bancaire**.</span><span class="sxs-lookup"><span data-stu-id="1822f-132">To be able to post a postdated check to a bank account when the session date is greater than or equal to the maturity date, you must enable the feature **Maturity date validation of posting payment journal with postdated checks to bank account**.</span></span> <span data-ttu-id="1822f-133">Cette fonction vous permet de valider les journaux de paiement pour les fournisseurs ou les clients avec des chèques postdatés, lorsque la date de session est supérieure ou égale à la date d'échéance.</span><span class="sxs-lookup"><span data-stu-id="1822f-133">This feature allows you to post payment journals for vendors or customers with postdated checks, when the session date is greater than or equal to the maturity date.</span></span>
> 
> <span data-ttu-id="1822f-134">Lors de la configuration du **Mode de paiement** (**Comptabilité fournisseur > Configuration des paiements > Modes de paiement**), ne remplissez pas **Compte de transition**.</span><span class="sxs-lookup"><span data-stu-id="1822f-134">When setting the **Method of payment** (**Accounts payable > Payment setup > Methods of payment**), do not fill in **Bridging account**.</span></span> <span data-ttu-id="1822f-135">Dans ce cas, le compte de contrepartie est renseigné avec le compte bancaire, qui est configuré dans le **Mode de paiement**.</span><span class="sxs-lookup"><span data-stu-id="1822f-135">In this case, the offset account is filled in with the bank account, which is set up in the **Method of payment**.</span></span>
>  
> <span data-ttu-id="1822f-136">Lorsque la fonctionnalité est activée et que la date de session est inférieure à la date d'échéance, le message d'erreur suivant s'affiche lors de la validation d'un journal des paiements, "La date d'échéance doit être inférieure ou égale à la date de session si le type de compte de contrepartie est Banque".</span><span class="sxs-lookup"><span data-stu-id="1822f-136">When the feature is enabled and the session date is less than the maturity date, the following error message is displayed when posting a payment journal, "Maturity date must be less or equal to the session date if offset account type is Bank".</span></span> <span data-ttu-id="1822f-137">Si la fonction n'est pas activée, vous pouvez valider un journal des paiements avec un chèque postdaté lorsque la date de session est inférieure à la date d'échéance.</span><span class="sxs-lookup"><span data-stu-id="1822f-137">If the feature is not enabled, you can post a payment journal with a postdated check when the session date is less than the maturity date.</span></span>    

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
