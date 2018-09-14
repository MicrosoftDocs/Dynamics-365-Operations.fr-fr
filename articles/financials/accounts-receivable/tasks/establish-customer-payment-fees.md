--- 
title: "Établir les commissions de paiement client"
description: "Créez des frais de paiement pour les paiements client."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustPaymFee, CustPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 5acb202d46ef39376a01ca592f60926786d11186
ms.contentlocale: fr-fr
ms.lasthandoff: 09/14/2018

---
# <a name="establish-customer-payment-fees"></a><span data-ttu-id="3fc95-103">Établir les commissions de paiement client</span><span class="sxs-lookup"><span data-stu-id="3fc95-103">Establish customer payment fees</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3fc95-104">Créez des frais de paiement pour les paiements client.</span><span class="sxs-lookup"><span data-stu-id="3fc95-104">Create payment fees for customer payments.</span></span>

<span data-ttu-id="3fc95-105">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="3fc95-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="3fc95-106">Accédez à Comptabilité client > Paramétrage des paiements > Frais de paiement.</span><span class="sxs-lookup"><span data-stu-id="3fc95-106">Go to Accounts receivable > Payments setup > Payment fee.</span></span>
2. <span data-ttu-id="3fc95-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="3fc95-107">Click New.</span></span>
3. <span data-ttu-id="3fc95-108">Entrez un ID frais dans le champ ID frais.</span><span class="sxs-lookup"><span data-stu-id="3fc95-108">In the Fee ID field, enter a Fee ID.</span></span>
    * <span data-ttu-id="3fc95-109">ID frais s'affiche sur les journaux des paiements, vous devez donc le rendre descriptif pour comprendre les frais qui sont imputés.</span><span class="sxs-lookup"><span data-stu-id="3fc95-109">The Fee ID displays on payment journals, so make it descriptive to understand what fee is being assessed.</span></span>  
4. <span data-ttu-id="3fc95-110">Entrez un nom de frais dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="3fc95-110">In the Name field, enter a fee Name.</span></span>
5. <span data-ttu-id="3fc95-111">Entrez une description des frais dans le champ Description des frais.</span><span class="sxs-lookup"><span data-stu-id="3fc95-111">In the Fee description field, enter a description for the fee.</span></span>
6. <span data-ttu-id="3fc95-112">Sélectionnez si les frais seront facturés au client ou un compte général.</span><span class="sxs-lookup"><span data-stu-id="3fc95-112">Select whether the fee will be charged to the Customer or a Ledger account.</span></span>
    * <span data-ttu-id="3fc95-113">Si les frais sont imputés au client, sélectionnez Client.</span><span class="sxs-lookup"><span data-stu-id="3fc95-113">If the customer is assessed the fee, select Customer.</span></span> <span data-ttu-id="3fc95-114">Si les frais seront imputés à votre organisation en tant que dépense, sélectionnez Comptabilité.</span><span class="sxs-lookup"><span data-stu-id="3fc95-114">If the fee will be assess to your organization as an expense, select Ledger.</span></span> <span data-ttu-id="3fc95-115">Pour cette tâche, sélectionnez Client.</span><span class="sxs-lookup"><span data-stu-id="3fc95-115">For this task, select Customer.</span></span>  
7. <span data-ttu-id="3fc95-116">Sélectionnez le type de journal qui peut utiliser ces frais de paiement.</span><span class="sxs-lookup"><span data-stu-id="3fc95-116">Select the type of  journal that can use this payment fee.</span></span>
    * <span data-ttu-id="3fc95-117">Si ces frais sont utilisés pour les paiements client, le type de journal sera certainement Client - Paiements.</span><span class="sxs-lookup"><span data-stu-id="3fc95-117">If these fees are used for customer payments, the journal type will likely be Customer payment.</span></span>  
8. <span data-ttu-id="3fc95-118">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="3fc95-118">Click Save.</span></span>
9. <span data-ttu-id="3fc95-119">Cliquez sur Paramétrage des frais de paiement.</span><span class="sxs-lookup"><span data-stu-id="3fc95-119">Click Payment fee setup.</span></span>
    * <span data-ttu-id="3fc95-120">Le paramétrage des frais de paiement permet de définir les critères pour l'évaluation des frais de paiement.</span><span class="sxs-lookup"><span data-stu-id="3fc95-120">The Payment fee setup is used to define the criteria for when the payment fee will be assessed.</span></span>  <span data-ttu-id="3fc95-121">Par exemple, vous pouvez indiquer que les frais seront calculés si le compte bancaire est USMF OPER, et le mode de paiement est le chèque.</span><span class="sxs-lookup"><span data-stu-id="3fc95-121">For example, you can define that the fee will be calculated if the bank account is USMF OPER, and the method of payment is check.</span></span>  
10. <span data-ttu-id="3fc95-122">Sélectionnez Tableau, Groupe ou Tout pour définir sur quels comptes bancaires ces frais seront imputés.</span><span class="sxs-lookup"><span data-stu-id="3fc95-122">Select either Table, Group or All to define which bank accounts will be assessed this fee.</span></span>
    * <span data-ttu-id="3fc95-123">Si vous sélectionnez Tous, ces frais pourraient être imputés sur tous les comptes bancaires.</span><span class="sxs-lookup"><span data-stu-id="3fc95-123">If you select All, all bank accounts could be assessed this fee.</span></span>  <span data-ttu-id="3fc95-124">Si vous sélectionnez Tableau, ces frais seront imputés sur le compte bancaire sélectionné uniquement.</span><span class="sxs-lookup"><span data-stu-id="3fc95-124">If you select Table, only the bank account you select could be assessed this fee.</span></span> <span data-ttu-id="3fc95-125">Si vous sélectionnez Groupe, ces frais peuvent uniquement être imputés aux comptes bancaires du groupe de banques sélectionné.</span><span class="sxs-lookup"><span data-stu-id="3fc95-125">If you select Group, only the bank accounts in the selected bank group could be assessed this fee.</span></span>  
11. <span data-ttu-id="3fc95-126">Sélectionnez un groupe de banques ou un compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="3fc95-126">Select either a bank group or a bank account.</span></span>
    * <span data-ttu-id="3fc95-127">Si vous avez sélectionné Tableau, la recherche affiche les comptes bancaires.</span><span class="sxs-lookup"><span data-stu-id="3fc95-127">If you selected Table, the lookup will display bank accounts.</span></span> <span data-ttu-id="3fc95-128">Si vous avez sélectionné Groupe, la recherche affiche les groupes de banques.</span><span class="sxs-lookup"><span data-stu-id="3fc95-128">If you selected Group, the lookup will display bank groups.</span></span>  
12. <span data-ttu-id="3fc95-129">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3fc95-129">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="3fc95-130">Sélectionnez le mode de paiement pour lequel ces frais seront imputés.</span><span class="sxs-lookup"><span data-stu-id="3fc95-130">Select the Method of payment for which this fee will be assessed.</span></span>
    * <span data-ttu-id="3fc95-131">Par exemple, vous pouvez imputer des frais à vos clients s'ils effectuent des paiements par chèque et non par paiement électronique.</span><span class="sxs-lookup"><span data-stu-id="3fc95-131">For example, you may assess a fee to your customers if they send payments as a check, rather than as an electronic payment.</span></span>  
14. <span data-ttu-id="3fc95-132">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="3fc95-132">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="3fc95-133">Le cas échéant, entrez une devise de paiement.</span><span class="sxs-lookup"><span data-stu-id="3fc95-133">If relevant, enter a payment currency.</span></span>
    * <span data-ttu-id="3fc95-134">La devise de paiement est utilisée comme un critère supplémentaire si les frais sont imputés.</span><span class="sxs-lookup"><span data-stu-id="3fc95-134">The payment currency is used as an additional criteria for whether the fee will be assessed.</span></span>  <span data-ttu-id="3fc95-135">Par exemple, votre banque peut facturer des frais supplémentaires pour les paiements reçus en USD, si elle traite normalement uniquement les transaction en EUR.</span><span class="sxs-lookup"><span data-stu-id="3fc95-135">For example, your bank may charge an extra fee for payments received in USD currency, since they normally only transact in EUR currency.</span></span>  
16. <span data-ttu-id="3fc95-136">Sélectionnez si les frais seront un pourcentage, un montant ou un intervalle.</span><span class="sxs-lookup"><span data-stu-id="3fc95-136">Select whether the fee will be a percent, amount or interval.</span></span>
17. <span data-ttu-id="3fc95-137">Entrez soit le pourcentage ou le montant des frais.</span><span class="sxs-lookup"><span data-stu-id="3fc95-137">Enter either percentage or amount of the fee.</span></span>
    * <span data-ttu-id="3fc95-138">Si le champ Pourcentage/montant est Pourcentage, la valeur entrée ici sera un pourcentage.</span><span class="sxs-lookup"><span data-stu-id="3fc95-138">If the Percentage/Amount field is Percent, then the value enter here will be a percentage.</span></span> <span data-ttu-id="3fc95-139">Si le champ Pourcentage/montant est Montant, la valeur entrée ici sera un montant.</span><span class="sxs-lookup"><span data-stu-id="3fc95-139">If the Percentage/Amount field is Amount, then the value you enter here will be an amount.</span></span> <span data-ttu-id="3fc95-140">Si le champ Pourcentage/montant est Intervalle, utilisez l'onglet Intervalle pour définir les niveaux.</span><span class="sxs-lookup"><span data-stu-id="3fc95-140">If the Percentage/Amount field is Interval, use the Interval tab to define the tiers.</span></span>  
18. <span data-ttu-id="3fc95-141">Sélectionnez la devise des frais dans le champ Devise des frais.</span><span class="sxs-lookup"><span data-stu-id="3fc95-141">In the Fee currency field, select the currency of the fee.</span></span>
    * <span data-ttu-id="3fc95-142">Il s'agit de la devise dans laquelle les frais seront créés.</span><span class="sxs-lookup"><span data-stu-id="3fc95-142">This is the currency in which the fee will be created.</span></span>  
19. <span data-ttu-id="3fc95-143">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="3fc95-143">Click Save.</span></span>


