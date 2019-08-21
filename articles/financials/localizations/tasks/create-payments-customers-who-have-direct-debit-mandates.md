---
title: Créer des paiements pour les clients qui ont des mandats de débit direct
description: Cette procédure indique comment générer un fichier de paiement à débit direct ISO20022 pour un client dont le débit direct est configuré et qui a une facture à payer.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustFreeInvoice, CustTableLookup, CustPostInvoiceJob, LedgerJournalTable, LedgerJournalTransCustPaym, SysQueryForm, CustPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e1959904befc62c32a8da185729f13525db27d4b
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1848920"
---
# <a name="create-payments-for-a-customer-who-have-direct-debit-mandates"></a><span data-ttu-id="1a93c-103">Créer des paiements pour les clients qui ont des mandats de débit direct</span><span class="sxs-lookup"><span data-stu-id="1a93c-103">Create payments for a customer who have direct debit mandates</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1a93c-104">Cette procédure indique comment générer un fichier de paiement à débit direct ISO20022 pour un client dont le débit direct est configuré et qui a une facture à payer.</span><span class="sxs-lookup"><span data-stu-id="1a93c-104">This procedure shows how to generate an ISO20022 direct debit payment file for a customer who has direct debit configured and an invoice to be paid.</span></span> <span data-ttu-id="1a93c-105">La création et la validation d'une facture sont facultatives.</span><span class="sxs-lookup"><span data-stu-id="1a93c-105">Creating and posting an invoice is optional.</span></span> <span data-ttu-id="1a93c-106">Au lieu d'avoir une facture à payer, vous pouvez sélectionner un mandat dans un journal avant de générer un fichier de paiement, pour prendre en charge un scénario d'acompte client.</span><span class="sxs-lookup"><span data-stu-id="1a93c-106">Instead of having an invoice to be paid you can select a mandate in a journal prior to generating a payment file, to support a customer prepayment scenario.</span></span>



<span data-ttu-id="1a93c-107">La société fictive de démonstration utilisée pour créer cette procédure est DEMF.</span><span class="sxs-lookup"><span data-stu-id="1a93c-107">The demo data company used to create this procedure is DEMF.</span></span>



<span data-ttu-id="1a93c-108">Il s'agit de la cinquième des cinq procédures illustrant le processus de paiement client à l'aide des configurations de génération d'états électroniques.</span><span class="sxs-lookup"><span data-stu-id="1a93c-108">This is the fifth of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span> <span data-ttu-id="1a93c-109">Avant de pouvoir effectuer cette tâche, vous devez effectuer les tâches précédentes.</span><span class="sxs-lookup"><span data-stu-id="1a93c-109">Before you can complete this task, you must complete the earlier tasks.</span></span> <span data-ttu-id="1a93c-110">Vous devez d'abord importer les configurations de génération d'états électroniques de paiement client, configurer les modes de paiement et paramétrer les informations de votre société et du client.</span><span class="sxs-lookup"><span data-stu-id="1a93c-110">You must first import customer payment electronic reporting configurations, configure method of payments, and set up your company and customer information.</span></span> 


## <a name="post-a-free-text-invoice-with-direct-debit-information"></a><span data-ttu-id="1a93c-111">Valider une facture financière avec les informations de débit direct</span><span class="sxs-lookup"><span data-stu-id="1a93c-111">Post a free text invoice with direct debit information</span></span>
1. <span data-ttu-id="1a93c-112">Accédez à Comptabilité client > Factures > Toutes factures financières.</span><span class="sxs-lookup"><span data-stu-id="1a93c-112">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="1a93c-113">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="1a93c-113">Click New.</span></span>
3. <span data-ttu-id="1a93c-114">Entrez ou sélectionnez une valeur dans le champ Compte client.</span><span class="sxs-lookup"><span data-stu-id="1a93c-114">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="1a93c-115">Par exemple, sélectionnez DE-010.</span><span class="sxs-lookup"><span data-stu-id="1a93c-115">For example, select DE-010.</span></span>  
4. <span data-ttu-id="1a93c-116">Entrez ou sélectionnez une valeur dans le champ Mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="1a93c-116">In the Method of payment field, enter or select a value.</span></span>
    * <span data-ttu-id="1a93c-117">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="1a93c-117">For example.</span></span> <span data-ttu-id="1a93c-118">sélectionnez Électronique.</span><span class="sxs-lookup"><span data-stu-id="1a93c-118">select Electronic.</span></span>  
5. <span data-ttu-id="1a93c-119">Dans le champ ID mandat de débit direct, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1a93c-119">In the Direct debit mandate ID field, enter or select a value.</span></span>
6. <span data-ttu-id="1a93c-120">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="1a93c-120">Click Add line.</span></span>
7. <span data-ttu-id="1a93c-121">Tapez une valeur dans le champ Description.</span><span class="sxs-lookup"><span data-stu-id="1a93c-121">In the Description field, type a value.</span></span>
8. <span data-ttu-id="1a93c-122">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="1a93c-122">In the Main account field, specify the desired values.</span></span>
9. <span data-ttu-id="1a93c-123">Entrez un nombre dans le champ Prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="1a93c-123">In the Unit price field, enter a number.</span></span>
10. <span data-ttu-id="1a93c-124">Cliquez sur Valider.</span><span class="sxs-lookup"><span data-stu-id="1a93c-124">Click Post.</span></span>
11. <span data-ttu-id="1a93c-125">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1a93c-125">Click OK.</span></span>

## <a name="create-a-payment"></a><span data-ttu-id="1a93c-126">Créer un paiement</span><span class="sxs-lookup"><span data-stu-id="1a93c-126">Create a payment</span></span>
1. <span data-ttu-id="1a93c-127">Accédez à Comptabilité client > Paiements > Journal des paiements.</span><span class="sxs-lookup"><span data-stu-id="1a93c-127">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="1a93c-128">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="1a93c-128">Click New.</span></span>
3. <span data-ttu-id="1a93c-129">Saisissez ou sélectionnez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="1a93c-129">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="1a93c-130">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="1a93c-130">Click Lines.</span></span>
5. <span data-ttu-id="1a93c-131">Cliquez sur Proposition de paiement.</span><span class="sxs-lookup"><span data-stu-id="1a93c-131">Click Payment proposal.</span></span>
6. <span data-ttu-id="1a93c-132">Cliquez sur Créer une proposition de paiement.</span><span class="sxs-lookup"><span data-stu-id="1a93c-132">Click Create payment proposal.</span></span>
7. <span data-ttu-id="1a93c-133">Développez les enregistrements pour inclure la section.</span><span class="sxs-lookup"><span data-stu-id="1a93c-133">Expand the Records to include section.</span></span>
8. <span data-ttu-id="1a93c-134">Cliquez sur Filtre.</span><span class="sxs-lookup"><span data-stu-id="1a93c-134">Click Filter.</span></span>
9. <span data-ttu-id="1a93c-135">Dans la liste, sélectionnez la ligne de la table Transactions client et du champ Mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="1a93c-135">In the list, select the row for the Customer transactions table and the Method of payment field.</span></span>
    * <span data-ttu-id="1a93c-136">Vous pouvez appliquer les critères de sélection des transactions client à payer.</span><span class="sxs-lookup"><span data-stu-id="1a93c-136">You can apply any criteria for selecting customer transactions to pay.</span></span> <span data-ttu-id="1a93c-137">Pour cet exemple, utilisez Électronique comme mode de paiement pour filtrer les transactions.</span><span class="sxs-lookup"><span data-stu-id="1a93c-137">For this example, use Electronic as a method of payment to filter transactions.</span></span>  
10. <span data-ttu-id="1a93c-138">Dans le champ Critères, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1a93c-138">In the Criteria field, enter or select a value.</span></span>
11. <span data-ttu-id="1a93c-139">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1a93c-139">Click OK.</span></span>
12. <span data-ttu-id="1a93c-140">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1a93c-140">Click OK.</span></span>
13. <span data-ttu-id="1a93c-141">Cliquez sur Créer des paiements.</span><span class="sxs-lookup"><span data-stu-id="1a93c-141">Click Create payments.</span></span>

## <a name="generate-a-payment-file"></a><span data-ttu-id="1a93c-142">Générer un fichier de paiement</span><span class="sxs-lookup"><span data-stu-id="1a93c-142">Generate a payment file</span></span>

