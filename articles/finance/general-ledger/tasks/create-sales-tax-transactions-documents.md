---
title: Créer des transactions de taxe sur les documents
description: La taxe sur les documents est calculée en indiquant un groupe de taxe et un groupe de taxe d’article sur les lignes du document.
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
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1a807ee2743f051528b6b96ddf1eaada65283933
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968652"
---
# <a name="create-sales-tax-transactions-on-documents"></a><span data-ttu-id="c34fe-103">Créer des transactions de taxe sur les documents</span><span class="sxs-lookup"><span data-stu-id="c34fe-103">Create sales tax transactions on documents</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c34fe-104">La taxe sur les documents est calculée en indiquant un groupe de taxe et un groupe de taxe d’article sur les lignes du document.</span><span class="sxs-lookup"><span data-stu-id="c34fe-104">Sales tax on documents is calculated by providing a Sales tax group and an Item sales tax group on document lines.</span></span> <span data-ttu-id="c34fe-105">Ces valeurs proviennent par défaut des données principales mais peuvent être modifiées manuellement le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="c34fe-105">These default from master data but can be changed manually if necessary.</span></span> <span data-ttu-id="c34fe-106">La taxe calculée peut être vérifiée sur une ligne et au niveau du document.</span><span class="sxs-lookup"><span data-stu-id="c34fe-106">The calculated sales tax can be checked on a line and document level.</span></span> <span data-ttu-id="c34fe-107">La société fictive USMF est citée en exemple dans cette tâche.</span><span class="sxs-lookup"><span data-stu-id="c34fe-107">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="c34fe-108">Accédez à Comptabilité client > Commandes > Toutes les commandes client.</span><span class="sxs-lookup"><span data-stu-id="c34fe-108">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="c34fe-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="c34fe-109">Click New.</span></span>
3. <span data-ttu-id="c34fe-110">Dans le champ Compte client, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="c34fe-110">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="c34fe-111">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c34fe-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="c34fe-112">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c34fe-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="c34fe-113">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c34fe-113">Click OK.</span></span>
7. <span data-ttu-id="c34fe-114">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c34fe-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="c34fe-115">Dans le champ Numéro d’article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="c34fe-115">In the Item number field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="c34fe-116">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c34fe-116">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="c34fe-117">Entrez un nombre dans le champ Prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="c34fe-117">In the Unit price field, enter a number.</span></span>
11. <span data-ttu-id="c34fe-118">Développez ou réduisez la section Détails de ligne.</span><span class="sxs-lookup"><span data-stu-id="c34fe-118">Expand or collapse the Line details section.</span></span>
12. <span data-ttu-id="c34fe-119">Cliquez sur l’onglet Paramétrage.</span><span class="sxs-lookup"><span data-stu-id="c34fe-119">Click the Setup tab.</span></span>
13. <span data-ttu-id="c34fe-120">Dans le champ Groupes de taxe d’article : cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="c34fe-120">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="c34fe-121">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c34fe-121">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="c34fe-122">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c34fe-122">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="c34fe-123">Cliquez sur Finances.</span><span class="sxs-lookup"><span data-stu-id="c34fe-123">Click Financials.</span></span>
17. <span data-ttu-id="c34fe-124">Cliquez sur Taxe.</span><span class="sxs-lookup"><span data-stu-id="c34fe-124">Click Sales tax.</span></span>
18. <span data-ttu-id="c34fe-125">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c34fe-125">Click OK.</span></span>
19. <span data-ttu-id="c34fe-126">Cliquez sur Ajouter une ligne.</span><span class="sxs-lookup"><span data-stu-id="c34fe-126">Click Add line.</span></span>
20. <span data-ttu-id="c34fe-127">Dans la liste, marquez la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c34fe-127">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="c34fe-128">Dans le champ Numéro d’article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="c34fe-128">In the Item number field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="c34fe-129">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c34fe-129">In the list, find and select the desired record.</span></span>
23. <span data-ttu-id="c34fe-130">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c34fe-130">In the list, click the link in the selected row.</span></span>
24. <span data-ttu-id="c34fe-131">Entrez un nombre dans le champ Prix unitaire.</span><span class="sxs-lookup"><span data-stu-id="c34fe-131">In the Unit price field, enter a number.</span></span>
25. <span data-ttu-id="c34fe-132">Dans le champ Groupes de taxe d’article : cliquez sur le bouton de liste déroulante pour ouvrir la recherche.</span><span class="sxs-lookup"><span data-stu-id="c34fe-132">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
26. <span data-ttu-id="c34fe-133">Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="c34fe-133">In the list, find and select the desired record.</span></span>
27. <span data-ttu-id="c34fe-134">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c34fe-134">In the list, click the link in the selected row.</span></span>
28. <span data-ttu-id="c34fe-135">Cliquez sur Vendre dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="c34fe-135">On the Action Pane, click Sell.</span></span>
29. <span data-ttu-id="c34fe-136">Cliquez sur Taxe.</span><span class="sxs-lookup"><span data-stu-id="c34fe-136">Click Sales tax.</span></span>
30. <span data-ttu-id="c34fe-137">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="c34fe-137">Click OK.</span></span>

