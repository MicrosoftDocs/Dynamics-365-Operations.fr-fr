---
title: FR-00004 Effets de commerce et billets à ordre français
description: L'état de remise de lettre de change française affiche les détails sur les lettres de change renvoyées.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymMode, CustVendPaymFormat
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: France
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 613e735808a21bd1b4e75050ea6939b94db33a2a
ms.sourcegitcommit: b92c3e1b3403d0455fc4e0bf9132d6bc0d7aba5e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3139012"
---
# <a name="fr-00004-french-bills-of-exchange-and-promissory-notes"></a><span data-ttu-id="2a5fa-103">FR-00004 Effets de commerce et billets à ordre français</span><span class="sxs-lookup"><span data-stu-id="2a5fa-103">FR-00004 French bills of exchange and promissory notes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2a5fa-104">L'état de remise de lettre de change française affiche les détails sur les lettres de change renvoyées.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-104">The French bill of exchange remittance report displays details about remitted bills of exchange.</span></span> <span data-ttu-id="2a5fa-105">L'état inclut des informations sur le compte bancaire, l'entité juridique et le type de remise.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-105">The report includes information about your bank account, legal entity, and remittance type.</span></span> <span data-ttu-id="2a5fa-106">Il fournit également la liste des transactions client qui sont affectées par la lettre de change.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-106">It also provides a list of customer transactions that are affected by the bill of exchange.</span></span> <span data-ttu-id="2a5fa-107">Cet état est utilisé par les commis à la comptabilité client et les commis à la comptabilité fournisseur pour mettre à jour des paiements client.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-107">This report is used by accounts receivable clerks and accounts payable clerks to maintain customer payments.</span></span> 



<span data-ttu-id="2a5fa-108">Cette procédure vous fait parcourir les étapes de la création du journal de remise de lettre de change et de la génération de l'état de remise de lettre de change.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-108">This procedure walks you through creating the bill of exchange remittance journal and generating the bill of exchange remittance report.</span></span>

<span data-ttu-id="2a5fa-109">Avant d'exécuter cette procédure, vous devez créer, approuver et valider la création du journal des lettres de change.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-109">Before you can complete this procedure, you must create, approve, and post draw the bill of exchange journal.</span></span>

<span data-ttu-id="2a5fa-110">Cette procédure a été créée à l'aide des données fictives de la société FRSI.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-110">This procedure was created using the demo data company FRSI.</span></span>

1. <span data-ttu-id="2a5fa-111">Accédez à Comptabilité client > Paiements > Lettre de change > Journal des remises.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-111">Go to Accounts receivable > Payments > Bill of exchange > Remittance journal.</span></span>
2. <span data-ttu-id="2a5fa-112">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-112">Click New.</span></span>
3. <span data-ttu-id="2a5fa-113">Saisissez ou sélectionnez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-113">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="2a5fa-114">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-114">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2a5fa-115">Entrez RemiseBque, par exemple.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-115">For example, enter 'RemiseBque'.</span></span>  
5. <span data-ttu-id="2a5fa-116">Cliquez sur l'onglet Lettre de change.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-116">Click the Bill of exchange tab.</span></span>
6. <span data-ttu-id="2a5fa-117">Dans le champ Compte en banque, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-117">In the Bank account field, enter or select a value.</span></span>
7. <span data-ttu-id="2a5fa-118">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-118">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="2a5fa-119">Sélectionnez FRN, par exemple.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-119">For example, select 'FRN'.</span></span>  
8. <span data-ttu-id="2a5fa-120">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-120">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="2a5fa-121">Cliquez sur l'onglet Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-121">Click the Setup tab.</span></span>
10. <span data-ttu-id="2a5fa-122">Sélectionnez Banque dans le champ Type de compte.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-122">In the Account type field, select 'Bank'.</span></span>
11. <span data-ttu-id="2a5fa-123">Spécifiez les valeurs souhaitées dans le champ Compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-123">In the Offset account field, specify the desired values.</span></span>
    * <span data-ttu-id="2a5fa-124">Sélectionnez FRSI OPER, par exemple.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-124">For example, select 'FRSI OPER'.</span></span>  
12. <span data-ttu-id="2a5fa-125">Cliquez sur Lignes.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-125">Click Lines.</span></span>
13. <span data-ttu-id="2a5fa-126">Dans le champ Compte, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-126">In the Account field, specify the desired values.</span></span>
    * <span data-ttu-id="2a5fa-127">Sélectionnez FR_SI_0020, par exemple.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-127">For example, select 'FR_SI_0020'.</span></span>  
14. <span data-ttu-id="2a5fa-128">Cliquez sur Régler les transactions.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-128">Click Settle transactions.</span></span>
    * <span data-ttu-id="2a5fa-129">Sélectionnez les lignes à inclure.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-129">Select the lines to include.</span></span>  
15. <span data-ttu-id="2a5fa-130">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-130">Click OK.</span></span>
16. <span data-ttu-id="2a5fa-131">Cliquez sur Générer une remise.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-131">Click Generate remittance.</span></span>
17. <span data-ttu-id="2a5fa-132">Entrez ou sélectionnez une valeur dans le champ Mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-132">In the Method of payment field, enter or select a value.</span></span>
18. <span data-ttu-id="2a5fa-133">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-133">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="2a5fa-134">Sélectionnez BOEPDF, par exemple.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-134">For example, select 'BOEPDF'.</span></span>  
19. <span data-ttu-id="2a5fa-135">Tapez une valeur dans le champ Nom du fichier.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-135">In the File name field, type a value.</span></span>
20. <span data-ttu-id="2a5fa-136">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-136">Click OK.</span></span>
    * <span data-ttu-id="2a5fa-137">Vous pouvez être invité à entrer une date de traitement.</span><span class="sxs-lookup"><span data-stu-id="2a5fa-137">You might be asked to enter a processing date.</span></span>  

