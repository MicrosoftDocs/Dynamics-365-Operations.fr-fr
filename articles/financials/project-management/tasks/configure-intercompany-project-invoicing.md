---
title: Configurer la facturation de projets intersociétés
description: Cette procédure décrit comment paramétrer la facturation d'un projet entre deux sociétés de votre organisation.
author: KimANelson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, InterCompanyTradingRelationSetupVendor, SysDataAreaSelectLookup, ProjParameters, ProjPosting, ProjTransferPrice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2fe06978d3a1c41a1133a568cca61df05b49d235
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1572417"
---
# <a name="configure-intercompany-project-invoicing"></a><span data-ttu-id="fb193-103">Configurer la facturation de projets intersociétés</span><span class="sxs-lookup"><span data-stu-id="fb193-103">Configure intercompany project invoicing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fb193-104">Cette procédure décrit comment paramétrer la facturation d'un projet entre deux sociétés de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fb193-104">This procedure shows how to set up project invoicing between two companies in your organization.</span></span> <span data-ttu-id="fb193-105">Cette tâche utilise l'ensemble de données USSI.</span><span class="sxs-lookup"><span data-stu-id="fb193-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="fb193-106">Accédez à Comptabilité fournisseur > Fournisseurs > Tous les fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="fb193-106">Go to Accounts payable > Vendors > All vendors.</span></span>
2. <span data-ttu-id="fb193-107">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="fb193-107">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="fb193-108">Dans le volet Actions, cliquez sur Général.</span><span class="sxs-lookup"><span data-stu-id="fb193-108">On the Action Pane, click General.</span></span>
4. <span data-ttu-id="fb193-109">Cliquez sur Intersociétés.</span><span class="sxs-lookup"><span data-stu-id="fb193-109">Click Intercompany.</span></span>
5. <span data-ttu-id="fb193-110">Activez Oui pour activer les relations commerciales intersociétés.</span><span class="sxs-lookup"><span data-stu-id="fb193-110">Set Active to Yes to enable intercompany trading.</span></span>
6. <span data-ttu-id="fb193-111">Dans le champ Société du client, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="fb193-111">In the Customer company field, enter or select a value.</span></span>
7. <span data-ttu-id="fb193-112">Dans le champ Mon compte, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="fb193-112">In the My account field, enter or select a value.</span></span>
8. <span data-ttu-id="fb193-113">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="fb193-113">Click Save.</span></span>
9. <span data-ttu-id="fb193-114">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fb193-114">Close the page.</span></span>
10. <span data-ttu-id="fb193-115">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fb193-115">Close the page.</span></span>
11. <span data-ttu-id="fb193-116">Accédez à Gestion de projets et comptabilité > Paramétrage > Paramètres de gestion de projets et de comptabilité.</span><span class="sxs-lookup"><span data-stu-id="fb193-116">Go to Project management and accounting > Setup > Project management and accounting parameters.</span></span>
12. <span data-ttu-id="fb193-117">Cliquez sur l'onglet Intersociétés.</span><span class="sxs-lookup"><span data-stu-id="fb193-117">Click the Intercompany tab.</span></span>
13. <span data-ttu-id="fb193-118">Déplacez le curseur sur Oui pour activer la planification et les feuilles de temps des ressources intersociétés.</span><span class="sxs-lookup"><span data-stu-id="fb193-118">Move the slider to Yes to enable intercompany resource scheduling and timesheets.</span></span>
14. <span data-ttu-id="fb193-119">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fb193-119">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="fb193-120">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="fb193-120">Click New.</span></span>
16. <span data-ttu-id="fb193-121">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fb193-121">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="fb193-122">Dans le champ Entité juridique emprunteuse, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="fb193-122">In the Borrowing legal entity field, enter or select a value.</span></span>
18. <span data-ttu-id="fb193-123">Activez la case à cocher Provisionner le produit.</span><span class="sxs-lookup"><span data-stu-id="fb193-123">Select the Accrue revenue check box.</span></span>
19. <span data-ttu-id="fb193-124">Dans le champ Catégorie de feuille de temps par défaut, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="fb193-124">In the Default timesheet category field, enter or select a value.</span></span>
20. <span data-ttu-id="fb193-125">Dans le champ Catégorie de dépense par défaut, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="fb193-125">In the Default expense category field, enter or select a value.</span></span>
21. <span data-ttu-id="fb193-126">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="fb193-126">Click Save.</span></span>
22. <span data-ttu-id="fb193-127">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fb193-127">Close the page.</span></span>
23. <span data-ttu-id="fb193-128">Accédez à Gestion de projets et comptabilité > Paramétrage > Validation > Paramétrage de la validation dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="fb193-128">Go to Project management and accounting > Setup > Posting > Ledger posting setup.</span></span>
24. <span data-ttu-id="fb193-129">Dans le champ Types de compte général, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="fb193-129">In the Ledger account types field, select an option.</span></span>
25. <span data-ttu-id="fb193-130">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="fb193-130">Click New.</span></span>
26. <span data-ttu-id="fb193-131">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fb193-131">In the list, mark the selected row.</span></span>
27. <span data-ttu-id="fb193-132">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fb193-132">In the list, mark the selected row.</span></span>
28. <span data-ttu-id="fb193-133">Dans le champ Compte principal, spécifiez les valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="fb193-133">In the Main account field, specify the desired values.</span></span>
29. <span data-ttu-id="fb193-134">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="fb193-134">Click Save.</span></span>
30. <span data-ttu-id="fb193-135">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fb193-135">Close the page.</span></span>
31. <span data-ttu-id="fb193-136">Accédez à Gestion de projets et comptabilité > Paramétrage > Prix > Prix de transfert.</span><span class="sxs-lookup"><span data-stu-id="fb193-136">Go to Project management and accounting > Setup > Prices > Transfer price.</span></span>
32. <span data-ttu-id="fb193-137">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="fb193-137">Click New.</span></span>
33. <span data-ttu-id="fb193-138">Entrez une date dans le champ Date d'effet.</span><span class="sxs-lookup"><span data-stu-id="fb193-138">In the Effective date field, enter a date.</span></span>
34. <span data-ttu-id="fb193-139">Dans le champ Entité juridique emprunteuse, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="fb193-139">In the Borrowing legal entity field, enter or select a value.</span></span>
35. <span data-ttu-id="fb193-140">Dans le champ Modèle de prix de transfert, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="fb193-140">In the Transfer price model field, select an option.</span></span>
36. <span data-ttu-id="fb193-141">Dans le champ Tarification, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="fb193-141">In the Pricing field, enter a number.</span></span>
37. <span data-ttu-id="fb193-142">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="fb193-142">Click Save.</span></span>

