--- 
title: "Lettres de change et billets à ordre français (France)"
description: "L'état de remise de lettre de change française affiche les détails sur les lettres de change renvoyées."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: France
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 2628483eda5ac0b8b25e88ed9cdd5e525b1a872d
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="french-bills-of-exchange-and-promissory-notes-france"></a><span data-ttu-id="605ad-103">Lettres de change et billets à ordre français (France)</span><span class="sxs-lookup"><span data-stu-id="605ad-103">French bills of exchange and promissory notes (France)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="605ad-104">L'état de remise de lettre de change française affiche les détails sur les lettres de change renvoyées.</span><span class="sxs-lookup"><span data-stu-id="605ad-104">The French bill of exchange remittance report displays details about remitted bills of exchange.</span></span> <span data-ttu-id="605ad-105">L'état inclut des informations sur le compte bancaire, l'entité juridique et le type de remise.</span><span class="sxs-lookup"><span data-stu-id="605ad-105">The report includes information about your bank account, legal entity, and remittance type.</span></span> <span data-ttu-id="605ad-106">Il fournit également la liste des transactions client qui sont affectées par la lettre de change.</span><span class="sxs-lookup"><span data-stu-id="605ad-106">It also provides a list of customer transactions that are affected by the bill of exchange.</span></span> <span data-ttu-id="605ad-107">Cet état est utilisé par les commis à la comptabilité client et les commis à la comptabilité fournisseur pour mettre à jour des paiements client.</span><span class="sxs-lookup"><span data-stu-id="605ad-107">This report is used by accounts receivable clerks and accounts payable clerks to maintain customer payments.</span></span> 



<span data-ttu-id="605ad-108">Cette procédure vous fait parcourir les étapes de la création du journal de remise de lettre de change et de la génération de l'état de remise de lettre de change.</span><span class="sxs-lookup"><span data-stu-id="605ad-108">This procedure walks you through creating the bill of exchange remittance journal and generating the bill of exchange remittance report.</span></span>

<span data-ttu-id="605ad-109">Avant d'exécuter cette procédure, vous devez créer, approuver et valider la création du journal des lettres de change.</span><span class="sxs-lookup"><span data-stu-id="605ad-109">Before you can complete this procedure, you must create, approve, and post draw the bill of exchange journal.</span></span>

<span data-ttu-id="605ad-110">Cette procédure a été créée à l'aide des données fictives de la société FRSI.</span><span class="sxs-lookup"><span data-stu-id="605ad-110">This procedure was created using the demo data company FRSI.</span></span>

1. <span data-ttu-id="605ad-111">Accédez à Comptabilité client > Paiements > Lettre de change > Journal des remises.</span><span class="sxs-lookup"><span data-stu-id="605ad-111">Go to Accounts receivable > Payments > Bill of exchange > Remittance journal.</span></span>
2. <span data-ttu-id="605ad-112">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="605ad-112">Click New.</span></span>
3. <span data-ttu-id="605ad-113">Saisissez ou sélectionnez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="605ad-113">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="605ad-114">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="605ad-114">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="605ad-115">Entrez RemiseBque, par exemple.</span><span class="sxs-lookup"><span data-stu-id="605ad-115">For example, enter 'RemiseBque'.</span></span>  
5. <span data-ttu-id="605ad-116">Cliquez sur l'onglet Lettre de change.</span><span class="sxs-lookup"><span data-stu-id="605ad-116">Click the Bill of exchange tab.</span></span>
6. <span data-ttu-id="605ad-117">Dans le champ Compte en banque, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="605ad-117">In the Bank account field, enter or select a value.</span></span>
7. <span data-ttu-id="605ad-118">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="605ad-118">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="605ad-119">Sélectionnez FRN, par exemple.</span><span class="sxs-lookup"><span data-stu-id="605ad-119">For example, select 'FRN'.</span></span>  
8. <span data-ttu-id="605ad-120">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="605ad-120">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="605ad-121">Cliquez sur l'onglet Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="605ad-121">Click the Setup tab.</span></span>
10. <span data-ttu-id="605ad-122">Sélectionnez Banque dans le champ Type de compte.</span><span class="sxs-lookup"><span data-stu-id="605ad-122">In the Account type field, select 'Bank'.</span></span>
11. <span data-ttu-id="605ad-123">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="605ad-123">In the Offset account field, specify the desired values.</span></span>
    * <span data-ttu-id="605ad-124">Sélectionnez FRSI OPER, par exemple.</span><span class="sxs-lookup"><span data-stu-id="605ad-124">For example, select 'FRSI OPER'.</span></span>  
12. <span data-ttu-id="605ad-125">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="605ad-125">Click Lines.</span></span>
13. <span data-ttu-id="605ad-126">Dans le champ Compte, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="605ad-126">In the Account field, specify the desired values.</span></span>
    * <span data-ttu-id="605ad-127">Sélectionnez FR_SI_0020, par exemple.</span><span class="sxs-lookup"><span data-stu-id="605ad-127">For example, select 'FR_SI_0020'.</span></span>  
14. <span data-ttu-id="605ad-128">Cliquez sur Régler les transactions.</span><span class="sxs-lookup"><span data-stu-id="605ad-128">Click Settle transactions.</span></span>
    * <span data-ttu-id="605ad-129">Sélectionnez les lignes à inclure.</span><span class="sxs-lookup"><span data-stu-id="605ad-129">Select the lines to include.</span></span>  
15. <span data-ttu-id="605ad-130">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="605ad-130">Click OK.</span></span>
16. <span data-ttu-id="605ad-131">Cliquez sur Générer une remise.</span><span class="sxs-lookup"><span data-stu-id="605ad-131">Click Generate remittance.</span></span>
17. <span data-ttu-id="605ad-132">Entrez ou sélectionnez une valeur dans le champ Mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="605ad-132">In the Method of payment field, enter or select a value.</span></span>
18. <span data-ttu-id="605ad-133">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="605ad-133">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="605ad-134">Sélectionnez BOEPDF, par exemple.</span><span class="sxs-lookup"><span data-stu-id="605ad-134">For example, select 'BOEPDF'.</span></span>  
19. <span data-ttu-id="605ad-135">Tapez une valeur dans le champ Nom du fichier.</span><span class="sxs-lookup"><span data-stu-id="605ad-135">In the File name field, type a value.</span></span>
20. <span data-ttu-id="605ad-136">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="605ad-136">Click OK.</span></span>
    * <span data-ttu-id="605ad-137">Vous pouvez être invité à entrer une date de traitement.</span><span class="sxs-lookup"><span data-stu-id="605ad-137">You might be asked to enter a processing date.</span></span>  


