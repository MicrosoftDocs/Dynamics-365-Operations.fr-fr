---
title: Configurer les coûts standard pour le travail et les dépenses
description: Cette procédure décrit comment paramétrer les coûts standard pour le travail et les dépenses d'un projet.
author: KimANelson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCostPriceHour, ProjSalesPriceHour, ProjCostPriceExpense, ProjSalesPriceCost
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f89590c87aec1a7200e95aeac6b2765fc64bb623
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1572394"
---
# <a name="configure-standard-costs-for-labor-and-expenses"></a><span data-ttu-id="3c8fd-103">Configurer les coûts standard pour le travail et les dépenses</span><span class="sxs-lookup"><span data-stu-id="3c8fd-103">Configure standard costs for labor and expenses</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3c8fd-104">Cette procédure décrit comment paramétrer les coûts standard pour le travail et les dépenses d'un projet.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-104">This procedure shows you how to set up standard costs for labor and expenses for a project.</span></span> <span data-ttu-id="3c8fd-105">Cette tâche utilise l'ensemble de données USSI.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="3c8fd-106">Accédez à Gestion de projets et comptabilité > Paramétrage > Prix > Prix de revient (heure).</span><span class="sxs-lookup"><span data-stu-id="3c8fd-106">Go to Project management and accounting > Setup > Prices > Cost price (hour).</span></span>
2. <span data-ttu-id="3c8fd-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-107">Click New.</span></span>
3. <span data-ttu-id="3c8fd-108">Entrez une date dans le champ Date d'effet.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-108">In the Effective date field, enter a date.</span></span>
4. <span data-ttu-id="3c8fd-109">Dans le champ Prix de revient, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-109">In the Cost price field, enter a number.</span></span>
    * <span data-ttu-id="3c8fd-110">Vous pouvez définir un prix de revient standard pour la catégorie de projet ou un prix de revient par matricule de collaborateur, numéro de projet, catégorie, date ou n'importe quelle combinaison de ces trois éléments.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-110">You can set up a standard cost price for the project category, or you can set up a cost price by worker number, project number, category, date, or any combination of these.</span></span> <span data-ttu-id="3c8fd-111">Le prix de revient appliqué est celui dont le niveau de détail est le plus élevé.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-111">The cost price that is applied is the cost price with the highest level of detail.</span></span>  
5. <span data-ttu-id="3c8fd-112">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-112">Click Save.</span></span>
6. <span data-ttu-id="3c8fd-113">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-113">Close the page.</span></span>
7. <span data-ttu-id="3c8fd-114">Accédez à Gestion de projets et comptabilité > Paramétrage > Prix > Prix de vente (heure).</span><span class="sxs-lookup"><span data-stu-id="3c8fd-114">Go to Project management and accounting > Setup > Prices > Sales price (hour).</span></span>
8. <span data-ttu-id="3c8fd-115">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-115">Click New.</span></span>
9. <span data-ttu-id="3c8fd-116">Entrez une date dans le champ Date d'effet.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-116">In the Effective date field, enter a date.</span></span>
10. <span data-ttu-id="3c8fd-117">Dans le champ Valide pour, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-117">In the Valid for field, select an option.</span></span>
11. <span data-ttu-id="3c8fd-118">Dans le champ Tarification, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-118">In the Pricing field, enter a number.</span></span>
    * <span data-ttu-id="3c8fd-119">Vous pouvez définir un prix de vente standard pour les transactions horaires ou pour une catégorie de projets.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-119">You can set up a standard sales price for hour transactions or for a project category.</span></span> <span data-ttu-id="3c8fd-120">Vous pouvez également paramétrer des prix de vente par matricule de collaborateur, numéro de projet, catégorie, date de transaction ou n'importe quelle combinaison de ces éléments.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-120">You can also set up sales prices by worker number, project number, category, transaction date, or any combination of these.</span></span> <span data-ttu-id="3c8fd-121">Le prix de vente réel appliqué lorsqu'un collaborateur entre une transaction dans le journal des heures correspond au prix de vente ayant le plus haut niveau de détail.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-121">The actual sales price, which is applied when a worker enters a transaction in the Hour journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="3c8fd-122">Par exemple, si un prix de vente général et un prix de vente spécifique à un collaborateur ont été paramétrés, le prix de vente spécifique au collaborateur est utilisé.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-122">For example, if both a general sales price and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
12. <span data-ttu-id="3c8fd-123">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-123">Click Save.</span></span>
13. <span data-ttu-id="3c8fd-124">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-124">Close the page.</span></span>
14. <span data-ttu-id="3c8fd-125">Accédez à Gestion de projets et comptabilité > Paramétrage > Prix > Prix de revient (dépense).</span><span class="sxs-lookup"><span data-stu-id="3c8fd-125">Go to Project management and accounting > Setup > Prices > Cost price (expense).</span></span>
15. <span data-ttu-id="3c8fd-126">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-126">Click New.</span></span>
16. <span data-ttu-id="3c8fd-127">Entrez une date dans le champ Date d'effet.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-127">In the Effective date field, enter a date.</span></span>
17. <span data-ttu-id="3c8fd-128">Dans le champ Prix de revient, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-128">In the Cost price field, enter a number.</span></span>
    * <span data-ttu-id="3c8fd-129">Plusieurs champs peuvent être renseignés, mais ces éléments constituent le minimum requis pour sauvegarder l'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-129">Multiple fields can be filled in, but this is the minimum needed to save the record.</span></span>  
18. <span data-ttu-id="3c8fd-130">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-130">Click Save.</span></span>
19. <span data-ttu-id="3c8fd-131">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-131">Close the page.</span></span>
20. <span data-ttu-id="3c8fd-132">Accédez à Gestion de projets et comptabilité > Paramétrage > Prix > Prix de vente (dépense).</span><span class="sxs-lookup"><span data-stu-id="3c8fd-132">Go to Project management and accounting > Setup > Prices > Sales price (expense).</span></span>
21. <span data-ttu-id="3c8fd-133">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-133">Click New.</span></span>
22. <span data-ttu-id="3c8fd-134">Entrez une date dans le champ Date d'effet.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-134">In the Effective date field, enter a date.</span></span>
23. <span data-ttu-id="3c8fd-135">Dans le champ Valide pour, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-135">In the Valid for field, select an option.</span></span>
24. <span data-ttu-id="3c8fd-136">Dans le champ Tarification, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-136">In the Pricing field, enter a number.</span></span>
    * <span data-ttu-id="3c8fd-137">Le prix de vente réel appliqué lorsqu'un collaborateur entre une transaction dans un journal de dépenses est le prix de vente ayant le plus haut niveau de détail.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-137">The actual sales price, which is applied when a worker enters transactions in an expense journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="3c8fd-138">Par exemple, si un prix de vente général et un prix de vente spécifique à un collaborateur ont été paramétrés, le prix de vente spécifique au collaborateur est utilisé.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-138">For example, if both a general and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
25. <span data-ttu-id="3c8fd-139">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="3c8fd-139">Click Save.</span></span>

