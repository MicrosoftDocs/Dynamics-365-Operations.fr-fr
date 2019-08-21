---
title: Créer des transactions de taxe sur les documents
description: La taxe sur les documents est calculée en indiquant un groupe de taxe et un groupe de taxe d'article sur les lignes du document.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, TaxTmpWorkTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 653b93744f5b891655cade0cb669d34179fca9cd
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846533"
---
# <a name="create-sales-tax-transactions-on-documents"></a><span data-ttu-id="13e62-103">Créer des transactions de taxe sur les documents</span><span class="sxs-lookup"><span data-stu-id="13e62-103">Create sales tax transactions on documents</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="13e62-104">La taxe sur les documents est calculée en indiquant un groupe de taxe et un groupe de taxe d'article sur les lignes du document.</span><span class="sxs-lookup"><span data-stu-id="13e62-104">Sales tax on documents is calculated by providing a Sales tax group and an Item sales tax group on document lines.</span></span> <span data-ttu-id="13e62-105">Ces valeurs proviennent par défaut des données principales mais peuvent être modifiées manuellement le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="13e62-105">These default from master data but can be changed manually if necessary.</span></span> <span data-ttu-id="13e62-106">La taxe calculée peut être vérifiée sur une ligne et au niveau du document.</span><span class="sxs-lookup"><span data-stu-id="13e62-106">The calculated sales tax can be checked on a line and document level.</span></span> <span data-ttu-id="13e62-107">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="13e62-107">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="13e62-108">Accédez à Comptabilité client > Commandes > Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="13e62-108">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="13e62-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="13e62-109">Click New.</span></span>
3. <span data-ttu-id="13e62-110">Dans le champ Compte client, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="13e62-110">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="13e62-111">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="13e62-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="13e62-112">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="13e62-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="13e62-113">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="13e62-113">Click OK.</span></span>
7. <span data-ttu-id="13e62-114">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="13e62-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="13e62-115">Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="13e62-115">In the Item number field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="13e62-116">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="13e62-116">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="13e62-117">Entrez un nombre dans le champ Prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="13e62-117">In the Unit price field, enter a number.</span></span>
11. <span data-ttu-id="13e62-118">Développez ou réduisez la section Détails de ligne.</span><span class="sxs-lookup"><span data-stu-id="13e62-118">Expand or collapse the Line details section.</span></span>
12. <span data-ttu-id="13e62-119">Cliquez sur l'onglet Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="13e62-119">Click the Setup tab.</span></span>
13. <span data-ttu-id="13e62-120">Dans le champ Groupes de taxe d'article : cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="13e62-120">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="13e62-121">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="13e62-121">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="13e62-122">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="13e62-122">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="13e62-123">Cliquez sur Finances.</span><span class="sxs-lookup"><span data-stu-id="13e62-123">Click Financials.</span></span>
17. <span data-ttu-id="13e62-124">Cliquez sur Taxe.</span><span class="sxs-lookup"><span data-stu-id="13e62-124">Click Sales tax.</span></span>
18. <span data-ttu-id="13e62-125">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="13e62-125">Click OK.</span></span>
19. <span data-ttu-id="13e62-126">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="13e62-126">Click Add line.</span></span>
20. <span data-ttu-id="13e62-127">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="13e62-127">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="13e62-128">Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="13e62-128">In the Item number field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="13e62-129">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="13e62-129">In the list, find and select the desired record.</span></span>
23. <span data-ttu-id="13e62-130">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="13e62-130">In the list, click the link in the selected row.</span></span>
24. <span data-ttu-id="13e62-131">Entrez un nombre dans le champ Prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="13e62-131">In the Unit price field, enter a number.</span></span>
25. <span data-ttu-id="13e62-132">Dans le champ Groupes de taxe d'article : cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="13e62-132">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
26. <span data-ttu-id="13e62-133">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="13e62-133">In the list, find and select the desired record.</span></span>
27. <span data-ttu-id="13e62-134">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="13e62-134">In the list, click the link in the selected row.</span></span>
28. <span data-ttu-id="13e62-135">Cliquez sur Vendre dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="13e62-135">On the Action Pane, click Sell.</span></span>
29. <span data-ttu-id="13e62-136">Cliquez sur Taxe.</span><span class="sxs-lookup"><span data-stu-id="13e62-136">Click Sales tax.</span></span>
30. <span data-ttu-id="13e62-137">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="13e62-137">Click OK.</span></span>

