---
title: Configurer la facturation de projets intersociétés
description: Cette rubrique décrit comment paramétrer la facturation d'un projet entre deux sociétés de votre organisation.
author: KimANelson
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, InterCompanyTradingRelationSetupVendor, SysDataAreaSelectLookup, ProjParameters, ProjPosting, ProjTransferPrice
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c89b17c09a4f145b5a4ca9cdd127b4e635447d4b
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867317"
---
# <a name="configure-intercompany-project-invoicing"></a><span data-ttu-id="2d7e7-103">Configurer la facturation de projets intersociétés</span><span class="sxs-lookup"><span data-stu-id="2d7e7-103">Configure intercompany project invoicing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2d7e7-104">Cette rubrique décrit comment paramétrer la facturation d'un projet entre deux sociétés de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-104">This topic shows how to set up project invoicing between two companies in your organization.</span></span> <span data-ttu-id="2d7e7-105">Cette tâche utilise l'ensemble de données USSI.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="2d7e7-106">Dans le volet de navigation, accédez à **Modules > Comptabilité fournisseur > Fournisseurs > Tous les fournisseurs**.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-106">In the navigation pane, go to **Modules > Accounts payable > Vendors > All vendors**.</span></span>
2. <span data-ttu-id="2d7e7-107">Dans la liste **Tous les fournisseurs**, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-107">In the **All vendors** list, find and select the desired record.</span></span>
3. <span data-ttu-id="2d7e7-108">Dans le volet Actions, sélectionnez **Général**.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-108">On the Action Pane, select **General**.</span></span>
4. <span data-ttu-id="2d7e7-109">Sélectionnez **Intersociétés**.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-109">Select **Intercompany**.</span></span>
5. <span data-ttu-id="2d7e7-110">Activez **Oui** pour **activer** les relations commerciales intersociétés.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-110">Set **Active** to **Yes** to enable intercompany trading.</span></span>
6. <span data-ttu-id="2d7e7-111">Dans le champ **Société du client**, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-111">In the **Customer company** field, enter or select a value.</span></span>
7. <span data-ttu-id="2d7e7-112">Dans le champ **Mon compte**, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-112">In the **My account** field, enter or select a value.</span></span>
8. <span data-ttu-id="2d7e7-113">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-113">Select **Save**.</span></span>
9. <span data-ttu-id="2d7e7-114">Fermez les pages pour revenir à la page d'accueil.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-114">Close the pages to return to the home page.</span></span>
10. <span data-ttu-id="2d7e7-115">Dans le volet de navigation, accédez à **Modules > Gestion et comptabilité du projet > Paramétrage > Paramètres de gestion et comptabilité des projets**.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-115">In the navigation pane, go to **Modules > Project management and accounting > Setup > Project management and accounting parameters**.</span></span>
11. <span data-ttu-id="2d7e7-116">Sélectionnez l'onglet **Intersociétés**.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-116">Select the **Intercompany** tab.</span></span>
12. <span data-ttu-id="2d7e7-117">Déplacez le curseur sur **Oui** pour activer la planification et les feuilles de temps des ressources intersociétés.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-117">Move the slider to **Yes** to enable intercompany resource scheduling and timesheets.</span></span>
13. <span data-ttu-id="2d7e7-118">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-118">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="2d7e7-119">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-119">Select **New**.</span></span>
15. <span data-ttu-id="2d7e7-120">Dans le champ **Entité juridique emprunteuse**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-120">In the **Borrowing legal entity** field, enter or select a value.</span></span>
16. <span data-ttu-id="2d7e7-121">Activez la case à cocher **Provisionner le produit**.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-121">Select the **Accrue revenue** check box.</span></span>
17. <span data-ttu-id="2d7e7-122">Dans le champ **Catégorie de feuille de temps par défaut**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-122">In the **Default timesheet category** field, enter or select a value.</span></span>
18. <span data-ttu-id="2d7e7-123">Dans le champ **Catégorie de dépense par défaut**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-123">In the **Default expense category** field, enter or select a value.</span></span>
19. <span data-ttu-id="2d7e7-124">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-124">Select **Save**.</span></span>
20. <span data-ttu-id="2d7e7-125">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-125">Close the page.</span></span>
21. <span data-ttu-id="2d7e7-126">Dans le volet de navigation, accédez à **Modules > Gestion et comptabilité du projet > Paramétrage > Validation > Paramétrage de la validation dans la comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-126">In the navigation pane, go to **Modules > Project management and accounting > Setup > Posting > Ledger posting setup**.</span></span>
22. <span data-ttu-id="2d7e7-127">Dans le champ **Types de compte général**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-127">In the **Ledger account types** field, select an option.</span></span>
23. <span data-ttu-id="2d7e7-128">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-128">Select **New**.</span></span>
24. <span data-ttu-id="2d7e7-129">Spécifiez les valeurs souhaitées dans le champ **Compte principal** de la nouvelle ligne.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-129">In the **Main account** field of the new row, specify the desired values.</span></span>
25. <span data-ttu-id="2d7e7-130">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-130">Select **Save**.</span></span>
26. <span data-ttu-id="2d7e7-131">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-131">Close the page.</span></span>
27. <span data-ttu-id="2d7e7-132">Dans le volet de navigation, accédez à **Modules > Gestion et comptabilité du projet > Paramétrage > Prix > Prix de transfert**.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-132">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Transfer price**.</span></span>
28. <span data-ttu-id="2d7e7-133">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-133">Select **New**.</span></span>
29. <span data-ttu-id="2d7e7-134">Entrez une date dans le champ **Date d'effet**.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-134">In the **Effective date** field, enter a date.</span></span>
30. <span data-ttu-id="2d7e7-135">Dans le champ **Entité juridique emprunteuse**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-135">In the **Borrowing legal entity** field, enter or select a value.</span></span>
31. <span data-ttu-id="2d7e7-136">Sélectionnez une option dans le champ **Modèle de prix de transfert**.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-136">In the **Transfer price model** field, select an option.</span></span>
32. <span data-ttu-id="2d7e7-137">Dans le champ **Tarification**, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-137">In the **Pricing** field, enter a number.</span></span>
33. <span data-ttu-id="2d7e7-138">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2d7e7-138">Select **Save**.</span></span>

