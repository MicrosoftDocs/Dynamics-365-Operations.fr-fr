---
title: Configurer les coûts standard pour le travail et les dépenses
description: Cette rubrique décrit comment paramétrer les coûts standard pour le travail et les dépenses d'un projet.
author: KimANelson
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCostPriceHour, ProjSalesPriceHour, ProjCostPriceExpense, ProjSalesPriceCost
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 60ab8eb94d4a8a0fb2c1e732ec7b25bfd5e7611e
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867724"
---
# <a name="configure-standard-costs-for-labor-and-expenses"></a><span data-ttu-id="f1168-103">Configurer les coûts standard pour le travail et les dépenses</span><span class="sxs-lookup"><span data-stu-id="f1168-103">Configure standard costs for labor and expenses</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f1168-104">Cette rubrique décrit comment paramétrer les coûts standard pour le travail et les dépenses d'un projet.</span><span class="sxs-lookup"><span data-stu-id="f1168-104">This topic explains how to set up standard costs for labor and expenses for a project.</span></span> <span data-ttu-id="f1168-105">Cette tâche utilise l'ensemble de données USSI.</span><span class="sxs-lookup"><span data-stu-id="f1168-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="f1168-106">Dans le volet de navigation, accédez à **Modules > Gestion et comptabilité du projet > Paramétrage > Prix > Prix de revient (heure)**.</span><span class="sxs-lookup"><span data-stu-id="f1168-106">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Cost price (hour)**.</span></span>
2. <span data-ttu-id="f1168-107">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="f1168-107">Select **New**.</span></span>
3. <span data-ttu-id="f1168-108">Entrez une date dans le champ **Date d'effet**.</span><span class="sxs-lookup"><span data-stu-id="f1168-108">In the **Effective date** field, enter a date.</span></span>
4. <span data-ttu-id="f1168-109">Entrez un nombre dans le champ **Prix de revient**.</span><span class="sxs-lookup"><span data-stu-id="f1168-109">In the **Cost price** field, enter a number.</span></span> <span data-ttu-id="f1168-110">Vous pouvez définir un prix de revient standard pour la catégorie de projet ou un prix de revient par matricule de collaborateur, numéro de projet, catégorie, date ou n'importe quelle combinaison de ces trois éléments.</span><span class="sxs-lookup"><span data-stu-id="f1168-110">You can set up a standard cost price for the project category, or you can set up a cost price by worker number, project number, category, date, or any combination of these.</span></span> <span data-ttu-id="f1168-111">Le prix de revient appliqué est celui dont le niveau de détail est le plus élevé.</span><span class="sxs-lookup"><span data-stu-id="f1168-111">The cost price that is applied is the cost price with the highest level of detail.</span></span>  
5. <span data-ttu-id="f1168-112">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f1168-112">Select **Save**.</span></span>
6. <span data-ttu-id="f1168-113">Dans le volet de navigation, accédez à **Modules > Gestion et comptabilité du projet > Paramétrage > Prix > Prix de vente (heure)**.</span><span class="sxs-lookup"><span data-stu-id="f1168-113">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Sales price (hour)**.</span></span>
7. <span data-ttu-id="f1168-114">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="f1168-114">Select **New**.</span></span>
8. <span data-ttu-id="f1168-115">Entrez une date dans le champ **Date d'effet**.</span><span class="sxs-lookup"><span data-stu-id="f1168-115">In the **Effective date** field, enter a date.</span></span>
9. <span data-ttu-id="f1168-116">Dans le champ **Valide pour**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="f1168-116">In the **Valid for** field, select an option.</span></span>
10. <span data-ttu-id="f1168-117">Dans le champ **Tarification**, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="f1168-117">In the **Pricing** field, enter a number.</span></span> <span data-ttu-id="f1168-118">Vous pouvez définir un prix de vente standard pour les transactions horaires ou pour une catégorie de projets.</span><span class="sxs-lookup"><span data-stu-id="f1168-118">You can set up a standard sales price for hour transactions or for a project category.</span></span> <span data-ttu-id="f1168-119">Vous pouvez également paramétrer des prix de vente par matricule de collaborateur, numéro de projet, catégorie, date de transaction ou n'importe quelle combinaison de ces éléments.</span><span class="sxs-lookup"><span data-stu-id="f1168-119">You can also set up sales prices by worker number, project number, category, transaction date, or any combination of these.</span></span> <span data-ttu-id="f1168-120">Le prix de vente réel appliqué lorsqu'un collaborateur entre une transaction dans le journal des heures correspond au prix de vente ayant le plus haut niveau de détail.</span><span class="sxs-lookup"><span data-stu-id="f1168-120">The actual sales price, which is applied when a worker enters a transaction in the Hour journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="f1168-121">Par exemple, si un prix de vente général et un prix de vente spécifique à un collaborateur ont été paramétrés, le prix de vente spécifique au collaborateur est utilisé.</span><span class="sxs-lookup"><span data-stu-id="f1168-121">For example, if both a general sales price and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
11. <span data-ttu-id="f1168-122">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f1168-122">Select **Save**.</span></span>
12. <span data-ttu-id="f1168-123">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="f1168-123">Close the page.</span></span>
13. <span data-ttu-id="f1168-124">Dans le volet de navigation, accédez à **Modules > Gestion et comptabilité du projet > Paramétrage > Prix > Prix de revient (dépense)**.</span><span class="sxs-lookup"><span data-stu-id="f1168-124">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Cost price (expense)**.</span></span>
14. <span data-ttu-id="f1168-125">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="f1168-125">Select **New**.</span></span>
15. <span data-ttu-id="f1168-126">Entrez une date dans le champ **Date d'effet**.</span><span class="sxs-lookup"><span data-stu-id="f1168-126">In the **Effective date** field, enter a date.</span></span>
16. <span data-ttu-id="f1168-127">Entrez un nombre dans le champ **Prix de revient**.</span><span class="sxs-lookup"><span data-stu-id="f1168-127">In the **Cost price** field, enter a number.</span></span> <span data-ttu-id="f1168-128">Plusieurs champs peuvent être renseignés, mais ces éléments constituent le minimum requis pour sauvegarder l'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="f1168-128">Multiple fields can be filled in, but this is the minimum needed to save the record.</span></span>  
17. <span data-ttu-id="f1168-129">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f1168-129">Select **Save**.</span></span>
18. <span data-ttu-id="f1168-130">Dans le volet de navigation, accédez à **Modules > Gestion et comptabilité du projet > Paramétrage > Prix > Prix de vente (dépense)**.</span><span class="sxs-lookup"><span data-stu-id="f1168-130">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Sales price (expense)**.</span></span>
19. <span data-ttu-id="f1168-131">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="f1168-131">Select **New**.</span></span>
20. <span data-ttu-id="f1168-132">Entrez une date dans le champ **Date d'effet**.</span><span class="sxs-lookup"><span data-stu-id="f1168-132">In the **Effective date** field, enter a date.</span></span>
21. <span data-ttu-id="f1168-133">Dans le champ **Valide pour**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="f1168-133">In the **Valid for** field, select an option.</span></span>
22. <span data-ttu-id="f1168-134">Dans le champ **Tarification**, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="f1168-134">In the **Pricing** field, enter a number.</span></span> <span data-ttu-id="f1168-135">Le prix de vente réel appliqué lorsqu'un collaborateur entre une transaction dans un journal de dépenses est le prix de vente ayant le plus haut niveau de détail.</span><span class="sxs-lookup"><span data-stu-id="f1168-135">The actual sales price, which is applied when a worker enters transactions in an expense journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="f1168-136">Par exemple, si un prix de vente général et un prix de vente spécifique à un collaborateur ont été paramétrés, le prix de vente spécifique au collaborateur est utilisé.</span><span class="sxs-lookup"><span data-stu-id="f1168-136">For example, if both a general and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
23. <span data-ttu-id="f1168-137">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f1168-137">Select **Save**.</span></span>

