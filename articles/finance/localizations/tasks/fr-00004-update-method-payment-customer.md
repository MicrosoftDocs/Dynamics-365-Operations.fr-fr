---
title: FR-00004 Mettre à jour un mode de paiement pour le client
description: Cette procédure vous guide dans l’ajout d’un compte bancaire pour un enregistrement client en France et dans la mise à jour d’un mode de paiement pour le même client.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, LogisticsPostalAddress, LogisticsPostalAddressGrid, SysLookupMultiSelectGrid
audience: Application User
ms.reviewer: kfend
ms.search.region: France
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d63ce67b80bc7e5344b32824b9e9cf97898629b8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4997456"
---
# <a name="fr-00004-update-method-of-payment-on-customer"></a><span data-ttu-id="1d1c2-103">FR-00004 Mettre à jour un mode de paiement pour le client</span><span class="sxs-lookup"><span data-stu-id="1d1c2-103">FR-00004 Update method of payment on customer</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1d1c2-104">Cette procédure vous guide dans l’ajout d’un compte bancaire pour un enregistrement client en France et dans la mise à jour d’un mode de paiement pour le même client.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-104">This procedure walks you through adding a bank account to a customer record in France and updating a method of payment for the same customer.</span></span>



<span data-ttu-id="1d1c2-105">Avant d’exécuter cette procédure, vous devez importer les configurations de génération d’état électronique suivantes : payments.initial.version.xml et BillsOfExchangeRemittance_FR.xml.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-105">Before you can complete this procedure, you must import the following electronic reporting configurations: payments.initial.version.xml and BillsOfExchangeRemittance_FR.xml.</span></span>



<span data-ttu-id="1d1c2-106">Cette procédure a été créée à l’aide des données fictives de la société FRSI.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-106">This procedure was created using the demo data company FRSI.</span></span>

1. <span data-ttu-id="1d1c2-107">Accédez à Comptabilité client > Clients > Tous les clients.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-107">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="1d1c2-108">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="1d1c2-109">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="1d1c2-110">Cliquez sur Client dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-110">On the Action Pane, click Customer.</span></span>
5. <span data-ttu-id="1d1c2-111">Cliquez sur Comptes bancaires.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-111">Click Bank accounts.</span></span>
6. <span data-ttu-id="1d1c2-112">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-112">Click New.</span></span>
7. <span data-ttu-id="1d1c2-113">Tapez une valeur dans le champ Compte en banque.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-113">In the Bank account field, type a value.</span></span>
8. <span data-ttu-id="1d1c2-114">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-114">In the Name field, type a value.</span></span>
9. <span data-ttu-id="1d1c2-115">Tapez une valeur dans le champ Numéro de compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-115">In the Bank account number field, type a value.</span></span>
10. <span data-ttu-id="1d1c2-116">Dans le champ N° d’acheminement, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-116">In the Routing number field, type a value.</span></span>
11. <span data-ttu-id="1d1c2-117">Développez la section Adresse.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-117">Expand the Address section.</span></span>
12. <span data-ttu-id="1d1c2-118">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-118">Click New.</span></span>
13. <span data-ttu-id="1d1c2-119">Tapez une valeur dans le champ Nom ou description.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-119">In the Name or description field, type a value.</span></span>
14. <span data-ttu-id="1d1c2-120">Dans le champ Pays/Région, sélectionnez ou entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-120">In the Country/region field, enter or select a value.</span></span>
15. <span data-ttu-id="1d1c2-121">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-121">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="1d1c2-122">Sélectionner FRA</span><span class="sxs-lookup"><span data-stu-id="1d1c2-122">Select FRA</span></span>  
16. <span data-ttu-id="1d1c2-123">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-123">Click OK.</span></span>
17. <span data-ttu-id="1d1c2-124">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-124">Close the page.</span></span>
18. <span data-ttu-id="1d1c2-125">Développez la section Adresses.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-125">Expand the Addresses section.</span></span>
19. <span data-ttu-id="1d1c2-126">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-126">Click Edit.</span></span>
20. <span data-ttu-id="1d1c2-127">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-127">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="1d1c2-128">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-128">Click OK.</span></span>
22. <span data-ttu-id="1d1c2-129">Développez la section Valeurs par défaut du paiement.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-129">Expand the Payment defaults section.</span></span>
23. <span data-ttu-id="1d1c2-130">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-130">Click Edit.</span></span>
24. <span data-ttu-id="1d1c2-131">Entrez ou sélectionnez une valeur dans le champ Mode de paiement.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-131">In the Method of payment field, enter or select a value.</span></span>
25. <span data-ttu-id="1d1c2-132">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-132">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="1d1c2-133">Définir le mode de paiement = BOEPDF</span><span class="sxs-lookup"><span data-stu-id="1d1c2-133">Set Method of payment = BOEPDF</span></span>  
26. <span data-ttu-id="1d1c2-134">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-134">In the list, click the link in the selected row.</span></span>
27. <span data-ttu-id="1d1c2-135">Dans le champ Compte en banque, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-135">In the Bank account field, enter or select a value.</span></span>
28. <span data-ttu-id="1d1c2-136">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-136">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="1d1c2-137">Modifier le compte bancaire = 1</span><span class="sxs-lookup"><span data-stu-id="1d1c2-137">Change to Bank account = 1</span></span>  
29. <span data-ttu-id="1d1c2-138">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="1d1c2-138">Click Save.</span></span>

