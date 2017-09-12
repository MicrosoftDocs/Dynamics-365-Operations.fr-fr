--- 
title: "Configurer les coûts standard pour le travail et les dépenses"
description: "Cette procédure décrit comment paramétrer les coûts standard pour le travail et les dépenses d'un projet."
author: KimANelson
manager: AnnBe
ms.date: 02/13/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 432b5b195b29fb03786cb0560e277735b531b7d7
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="configure-standard-costs-for-labor-and-expenses"></a><span data-ttu-id="e3593-103">Configurer les coûts standard pour le travail et les dépenses</span><span class="sxs-lookup"><span data-stu-id="e3593-103">Configure standard costs for labor and expenses</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e3593-104">Cette procédure décrit comment paramétrer les coûts standard pour le travail et les dépenses d'un projet.</span><span class="sxs-lookup"><span data-stu-id="e3593-104">This procedure shows you how to set up standard costs for labor and expenses for a project.</span></span> <span data-ttu-id="e3593-105">Cette tâche utilise l'ensemble de données USSI.</span><span class="sxs-lookup"><span data-stu-id="e3593-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="e3593-106">Accédez à Gestion de projets et comptabilité > Paramétrage > Prix > Prix de revient (heure).</span><span class="sxs-lookup"><span data-stu-id="e3593-106">Go to Project management and accounting > Setup > Prices > Cost price (hour).</span></span>
2. <span data-ttu-id="e3593-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e3593-107">Click New.</span></span>
3. <span data-ttu-id="e3593-108">Entrez une date dans le champ Date d'effet.</span><span class="sxs-lookup"><span data-stu-id="e3593-108">In the Effective date field, enter a date.</span></span>
4. <span data-ttu-id="e3593-109">Dans le champ Prix de revient, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="e3593-109">In the Cost price field, enter a number.</span></span>
    * <span data-ttu-id="e3593-110">Vous pouvez définir un prix de revient standard pour la catégorie de projet ou un prix de revient par matricule de collaborateur, numéro de projet, catégorie, date ou n'importe quelle combinaison de ces trois éléments.</span><span class="sxs-lookup"><span data-stu-id="e3593-110">You can set up a standard cost price for the project category, or you can set up a cost price by worker number, project number, category, date, or any combination of these.</span></span> <span data-ttu-id="e3593-111">Le prix de revient appliqué est celui dont le niveau de détail est le plus élevé.</span><span class="sxs-lookup"><span data-stu-id="e3593-111">The cost price that is applied is the cost price with the highest level of detail.</span></span>  
5. <span data-ttu-id="e3593-112">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e3593-112">Click Save.</span></span>
6. <span data-ttu-id="e3593-113">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e3593-113">Close the page.</span></span>
7. <span data-ttu-id="e3593-114">Accédez à Gestion de projets et comptabilité > Paramétrage > Prix > Prix de vente (heure).</span><span class="sxs-lookup"><span data-stu-id="e3593-114">Go to Project management and accounting > Setup > Prices > Sales price (hour).</span></span>
8. <span data-ttu-id="e3593-115">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e3593-115">Click New.</span></span>
9. <span data-ttu-id="e3593-116">Entrez une date dans le champ Date d'effet.</span><span class="sxs-lookup"><span data-stu-id="e3593-116">In the Effective date field, enter a date.</span></span>
10. <span data-ttu-id="e3593-117">Dans le champ Valide pour, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="e3593-117">In the Valid for field, select an option.</span></span>
11. <span data-ttu-id="e3593-118">Dans le champ Tarification, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="e3593-118">In the Pricing field, enter a number.</span></span>
    * <span data-ttu-id="e3593-119">Vous pouvez définir un prix de vente standard pour les transactions horaires ou pour une catégorie de projets.</span><span class="sxs-lookup"><span data-stu-id="e3593-119">You can set up a standard sales price for hour transactions or for a project category.</span></span> <span data-ttu-id="e3593-120">Vous pouvez également paramétrer des prix de vente par matricule de collaborateur, numéro de projet, catégorie, date de transaction ou n'importe quelle combinaison de ces éléments.</span><span class="sxs-lookup"><span data-stu-id="e3593-120">You can also set up sales prices by worker number, project number, category, transaction date, or any combination of these.</span></span> <span data-ttu-id="e3593-121">Le prix de vente réel appliqué lorsqu'un collaborateur entre une transaction dans le journal des heures correspond au prix de vente ayant le plus haut niveau de détail.</span><span class="sxs-lookup"><span data-stu-id="e3593-121">The actual sales price, which is applied when a worker enters a transaction in the Hour journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="e3593-122">Par exemple, si un prix de vente général et un prix de vente spécifique à un collaborateur ont été paramétrés, le prix de vente spécifique au collaborateur est utilisé.</span><span class="sxs-lookup"><span data-stu-id="e3593-122">For example, if both a general sales price and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
12. <span data-ttu-id="e3593-123">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e3593-123">Click Save.</span></span>
13. <span data-ttu-id="e3593-124">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e3593-124">Close the page.</span></span>
14. <span data-ttu-id="e3593-125">Accédez à Gestion de projets et comptabilité > Paramétrage > Prix > Prix de revient (dépense).</span><span class="sxs-lookup"><span data-stu-id="e3593-125">Go to Project management and accounting > Setup > Prices > Cost price (expense).</span></span>
15. <span data-ttu-id="e3593-126">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e3593-126">Click New.</span></span>
16. <span data-ttu-id="e3593-127">Entrez une date dans le champ Date d'effet.</span><span class="sxs-lookup"><span data-stu-id="e3593-127">In the Effective date field, enter a date.</span></span>
17. <span data-ttu-id="e3593-128">Dans le champ Prix de revient, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="e3593-128">In the Cost price field, enter a number.</span></span>
    * <span data-ttu-id="e3593-129">Plusieurs champs peuvent être renseignés, mais ces éléments constituent le minimum requis pour sauvegarder l'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="e3593-129">Multiple fields can be filled in, but this is the minimum needed to save the record.</span></span>  
18. <span data-ttu-id="e3593-130">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e3593-130">Click Save.</span></span>
19. <span data-ttu-id="e3593-131">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e3593-131">Close the page.</span></span>
20. <span data-ttu-id="e3593-132">Accédez à Gestion de projets et comptabilité > Paramétrage > Prix > Prix de vente (dépense).</span><span class="sxs-lookup"><span data-stu-id="e3593-132">Go to Project management and accounting > Setup > Prices > Sales price (expense).</span></span>
21. <span data-ttu-id="e3593-133">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e3593-133">Click New.</span></span>
22. <span data-ttu-id="e3593-134">Entrez une date dans le champ Date d'effet.</span><span class="sxs-lookup"><span data-stu-id="e3593-134">In the Effective date field, enter a date.</span></span>
23. <span data-ttu-id="e3593-135">Dans le champ Valide pour, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="e3593-135">In the Valid for field, select an option.</span></span>
24. <span data-ttu-id="e3593-136">Dans le champ Tarification, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="e3593-136">In the Pricing field, enter a number.</span></span>
    * <span data-ttu-id="e3593-137">Le prix de vente réel appliqué lorsqu'un collaborateur entre une transaction dans un journal de dépenses est le prix de vente ayant le plus haut niveau de détail.</span><span class="sxs-lookup"><span data-stu-id="e3593-137">The actual sales price, which is applied when a worker enters transactions in an expense journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="e3593-138">Par exemple, si un prix de vente général et un prix de vente spécifique à un collaborateur ont été paramétrés, le prix de vente spécifique au collaborateur est utilisé.</span><span class="sxs-lookup"><span data-stu-id="e3593-138">For example, if both a general and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
25. <span data-ttu-id="e3593-139">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e3593-139">Click Save.</span></span>


