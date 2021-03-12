---
title: Définir les commissions de paiement fournisseur
description: Paramétrez les frais de paiement fournisseur.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPaymFee, VendPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 52321851a1aa588a0bbe238e366a28d503665988
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979336"
---
# <a name="define-vendor-payment-fees"></a><span data-ttu-id="bafed-103">Définir les commissions de paiement fournisseur</span><span class="sxs-lookup"><span data-stu-id="bafed-103">Define vendor payment fees</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bafed-104">Paramétrez les frais de paiement fournisseur.</span><span class="sxs-lookup"><span data-stu-id="bafed-104">Set up vendor payment fees.</span></span> <span data-ttu-id="bafed-105">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="bafed-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="bafed-106">Accédez à Comptabilité fournisseur > Paramétrage des paiements > Frais de paiement.</span><span class="sxs-lookup"><span data-stu-id="bafed-106">Go to Accounts payable > Payment setup > Payment fee.</span></span>
2. <span data-ttu-id="bafed-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="bafed-107">Click New.</span></span>
3. <span data-ttu-id="bafed-108">Tapez une valeur dans le champ ID frais.</span><span class="sxs-lookup"><span data-stu-id="bafed-108">In the Fee ID field, type a value.</span></span>
    * <span data-ttu-id="bafed-109">L’ID de frais doit décrire quand ces frais sont utilisés, par exemple « Frais_EFT ».</span><span class="sxs-lookup"><span data-stu-id="bafed-109">The Fee ID should describe when this fee will be used, such as "EFT_Fee".</span></span>  
4. <span data-ttu-id="bafed-110">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="bafed-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="bafed-111">Tapez une valeur dans le champ Description des frais.</span><span class="sxs-lookup"><span data-stu-id="bafed-111">In the Fee description field, type a value.</span></span>
    * <span data-ttu-id="bafed-112">Ajoutez une description pour décrire à quel moment les frais sont imputés.</span><span class="sxs-lookup"><span data-stu-id="bafed-112">Add a description to provide more detail on when the fee is assessed.</span></span>  
6. <span data-ttu-id="bafed-113">Sélectionnez Fournisseur ou Comptabilité dans le champ Frais.</span><span class="sxs-lookup"><span data-stu-id="bafed-113">In the Charge field, select either Vendor or Ledger.</span></span>
    * <span data-ttu-id="bafed-114">Le compte Comptabilité est utilisé lorsque les frais sont imputés à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="bafed-114">Ledger is used when the fee will be expensed to your organization.</span></span>  <span data-ttu-id="bafed-115">Le compte Fournisseur est utilisé lorsque les frais sont imputés au fournisseur.</span><span class="sxs-lookup"><span data-stu-id="bafed-115">Vendor is used when the fee will be assessed to the vendor.</span></span>  
7. <span data-ttu-id="bafed-116">Entrez un compte principal pour lequel les frais seront imputés.</span><span class="sxs-lookup"><span data-stu-id="bafed-116">Enter a main account for where the fee will be expensed.</span></span>
    * <span data-ttu-id="bafed-117">Cette option n’est disponible que si Comptabilité est sélectionné comme option de frais.</span><span class="sxs-lookup"><span data-stu-id="bafed-117">This option is only available when selecting Ledger as the Charge option.</span></span>  
8. <span data-ttu-id="bafed-118">Sélectionnez le journal dans lequel ces frais peuvent être utilisés.</span><span class="sxs-lookup"><span data-stu-id="bafed-118">Select the journal on which this fee can be used.</span></span> 
    * <span data-ttu-id="bafed-119">Pour les frais de paiement fournisseur, vous devez sélectionner le journal « Fournisseur - Paiements ».</span><span class="sxs-lookup"><span data-stu-id="bafed-119">For a vendor payment fee, you would select the journal 'Vendor disbursement.'</span></span>  
9. <span data-ttu-id="bafed-120">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="bafed-120">Click Save.</span></span>
10. <span data-ttu-id="bafed-121">Cliquez sur Paramétrage des frais de paiement.</span><span class="sxs-lookup"><span data-stu-id="bafed-121">Click Payment fee setup.</span></span>
    * <span data-ttu-id="bafed-122">Passez au paramétrage des frais de paiement pour définir à quel moment les frais doivent être définis par défaut dans le journal sélectionné.</span><span class="sxs-lookup"><span data-stu-id="bafed-122">Continue to the Payment fee setup to define when the fee should default onto the journal you selected.</span></span>  
11. <span data-ttu-id="bafed-123">Sélectionnez Tableau, Groupe ou Tous.</span><span class="sxs-lookup"><span data-stu-id="bafed-123">Select either Table, Group or All.</span></span>
    * <span data-ttu-id="bafed-124">Tableau permet de sélectionner un compte bancaire unique, Groupe permet de sélectionner un groupe de banques, et Tous permet d’appliquer le paramétrage des frais pour tous les comptes bancaires</span><span class="sxs-lookup"><span data-stu-id="bafed-124">Table is used to select a single bank account, Group is used to select a bank group, and All is to use this fee setup for all bank accounts</span></span>  
12. <span data-ttu-id="bafed-125">Sélectionnez un groupe de banques ou un compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="bafed-125">Select either a bank group or a bank account.</span></span>
    * <span data-ttu-id="bafed-126">La recherche affiche le groupe de banques si vous avez sélectionné Groupe, et indique les comptes bancaires si vous avez sélectionné Tableau.</span><span class="sxs-lookup"><span data-stu-id="bafed-126">The lookup will show bank group if you selected Group, and will show bank accounts if you selected Table.</span></span>  
13. <span data-ttu-id="bafed-127">Sélectionnez le mode de paiement pour lequel ces frais seront imputés.</span><span class="sxs-lookup"><span data-stu-id="bafed-127">Select the method of payment for when this fee will be assessed.</span></span>
14. <span data-ttu-id="bafed-128">Sélectionnez les spécifications de paiement pour le mode de paiement sélectionné.</span><span class="sxs-lookup"><span data-stu-id="bafed-128">Select the Payment specification for the selected method of payment.</span></span>
    * <span data-ttu-id="bafed-129">La spécification de paiement est utilisée avec des modes de paiement électroniques.</span><span class="sxs-lookup"><span data-stu-id="bafed-129">The Payment specification is used with electronic fund transfer methods of payment.</span></span>  
15. <span data-ttu-id="bafed-130">Sélectionnez si les frais sont un pourcentage, un montant ou un intervalle.</span><span class="sxs-lookup"><span data-stu-id="bafed-130">Select whether the fee is a percentage, amount or interval.</span></span>
16. <span data-ttu-id="bafed-131">Entrez le pourcentage ou le montant des frais.</span><span class="sxs-lookup"><span data-stu-id="bafed-131">Enter the percentage or amount of the fee.</span></span>
    * <span data-ttu-id="bafed-132">Si les frais sont un pourcentage, entrez le pourcentage.</span><span class="sxs-lookup"><span data-stu-id="bafed-132">If the Fee is a percentage, enter the percentage.</span></span> <span data-ttu-id="bafed-133">Si les frais sont un montant, entrez le montant des frais.</span><span class="sxs-lookup"><span data-stu-id="bafed-133">If the Fee is an amount, enter the amount of the fee.</span></span> <span data-ttu-id="bafed-134">Si les frais sont un intervalle, utilisez l’onglet Intervalle pour définir des frais progressifs.</span><span class="sxs-lookup"><span data-stu-id="bafed-134">If the Fee is an interval, use the Interval tab to defined the tiered fees.</span></span>  
17. <span data-ttu-id="bafed-135">Dans le champ Devise des frais, sélectionnez la devise dans laquelle les frais seront imputés.</span><span class="sxs-lookup"><span data-stu-id="bafed-135">In the Fee currency field, select the currency in which the fee will be assessed.</span></span>
    * <span data-ttu-id="bafed-136">Cette devise est pour les frais.</span><span class="sxs-lookup"><span data-stu-id="bafed-136">This currency is for the fee.</span></span> <span data-ttu-id="bafed-137">La devise de paiement est utilisée pour définir à quel moment la règle en matière de frais doit être évaluée selon la devise du paiement.</span><span class="sxs-lookup"><span data-stu-id="bafed-137">The payment currency is used to define when the fee rule should be assessed based on the payment's currency.</span></span> <span data-ttu-id="bafed-138">Par exemple, votre banque peut facturer des frais lorsqu’un paiement est effectué en EUR, mais des frais ne sont pas imputés à tous les autres paiements.</span><span class="sxs-lookup"><span data-stu-id="bafed-138">For example, your bank may charge a fee when a payment is made in EUR, but all other payments aren't assessed a fee.</span></span>  
18. <span data-ttu-id="bafed-139">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="bafed-139">Click Save.</span></span>

