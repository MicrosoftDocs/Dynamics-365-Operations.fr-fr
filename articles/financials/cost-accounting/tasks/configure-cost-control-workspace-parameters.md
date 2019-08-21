---
title: Configurer les paramètres de l'espace de travail de contrôle des coûts
description: Cette procédure permet de configurer l'espace de travail Contrôle des coûts afin que les gestionnaires à différents niveaux d'une organisation puissent obtenir des informations sur leurs objets de coût, tels que les centres de coût et les groupes de produits.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 867bfd2f2d1ff486e683cb11c38906dd0efe8c14
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841415"
---
# <a name="configure-cost-control-workspace-parameters"></a><span data-ttu-id="bbc36-103">Configurer les paramètres de l'espace de travail de contrôle des coûts</span><span class="sxs-lookup"><span data-stu-id="bbc36-103">Configure cost control workspace parameters</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bbc36-104">Cette procédure permet de configurer l'espace de travail Contrôle des coûts afin que les gestionnaires à différents niveaux d'une organisation puissent obtenir des informations sur leurs objets de coût, tels que les centres de coût et les groupes de produits.</span><span class="sxs-lookup"><span data-stu-id="bbc36-104">Use this procedure to configure the Cost control workspace so that managers at various levels in an organization can gain insight into their cost objects, such as cost centers and product groups.</span></span> <span data-ttu-id="bbc36-105">La société fictive USP2 a été utilisée pour créer cet enregistrement.</span><span class="sxs-lookup"><span data-stu-id="bbc36-105">The USP2 demo company was used to create this recording.</span></span>

1. <span data-ttu-id="bbc36-106">Accédez à Contrôle de gestion > Paramétrage > Configuration de l'espace de travail de contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="bbc36-106">Go to Cost accounting > Setup > Cost control workspace configuration.</span></span>
2. <span data-ttu-id="bbc36-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="bbc36-107">Click New.</span></span>
3. <span data-ttu-id="bbc36-108">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="bbc36-108">In the Name field, type a value.</span></span>
4. <span data-ttu-id="bbc36-109">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bbc36-109">In the Description field, type a value.</span></span>
5. <span data-ttu-id="bbc36-110">Sélectionnez Oui dans le champ Publié.</span><span class="sxs-lookup"><span data-stu-id="bbc36-110">Select Yes in the Published field.</span></span>
    * <span data-ttu-id="bbc36-111">Si vous définissez cette option sur Oui, les utilisateurs affectés à l'un des rôles suivants peuvent afficher l'état dans l'espace de travail Contrôle des coûts : gestionnaire de contrôle de gestion, comptable, commis contrôleur de gestion ou contrôleur d'objet de coût.</span><span class="sxs-lookup"><span data-stu-id="bbc36-111">If you set this option to Yes, users who are assigned one of these roles can see the report in the Cost control workspace: cost accounting manager, cost accountant, cost accountant clerk, or cost object controller.</span></span> <span data-ttu-id="bbc36-112">Si vous définissez cette option sur Non, seuls les utilisateurs affectés à l'un des rôles suivants peuvent afficher l'état dans l'espace de travail Contrôle des coûts : gestionnaire de contrôle de gestion, comptable ou commis contrôleur de gestion.</span><span class="sxs-lookup"><span data-stu-id="bbc36-112">If you set this option to No, only users who are assigned one of these roles can see the report in the Cost control workspace: cost accounting manager, cost accountant, or cost accountant clerk.</span></span>  
6. <span data-ttu-id="bbc36-113">Développez la section Filtrage des données.</span><span class="sxs-lookup"><span data-stu-id="bbc36-113">Expand the Data filtering section.</span></span>
7. <span data-ttu-id="bbc36-114">Dans le champ Unité de contrôle des coûts, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bbc36-114">In the Cost control unit field, enter or select a value.</span></span>
8. <span data-ttu-id="bbc36-115">Dans le champ Version originale du budget, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bbc36-115">In the Budget original version field, enter or select a value.</span></span>
9. <span data-ttu-id="bbc36-116">Dans le champ Hiérarchie des dimensions d'élément de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bbc36-116">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
10. <span data-ttu-id="bbc36-117">Dans le champ Hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bbc36-117">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
11. <span data-ttu-id="bbc36-118">Développez la section Affecter les enregistrements de calcul.</span><span class="sxs-lookup"><span data-stu-id="bbc36-118">Expand the Assign calculation records section.</span></span>
12. <span data-ttu-id="bbc36-119">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="bbc36-119">Click New.</span></span>
13. <span data-ttu-id="bbc36-120">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="bbc36-120">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="bbc36-121">Dans le champ Période de calendrier fiscal, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bbc36-121">In the Fiscal calendar period field, enter or select a value.</span></span>
15. <span data-ttu-id="bbc36-122">Dans le champ Version réelle, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bbc36-122">In the Actual version field, enter or select a value.</span></span>
16. <span data-ttu-id="bbc36-123">Développez la section Périodes fiscales par colonne.</span><span class="sxs-lookup"><span data-stu-id="bbc36-123">Expand the Fiscal periods per column section.</span></span>
17. <span data-ttu-id="bbc36-124">Sélectionnez Oui dans le champ Période actuelle.</span><span class="sxs-lookup"><span data-stu-id="bbc36-124">Select Yes in the Current period field.</span></span>
18. <span data-ttu-id="bbc36-125">Développez la section Colonnes à afficher pour les coûts.</span><span class="sxs-lookup"><span data-stu-id="bbc36-125">Expand the Columns to display for costs section.</span></span>
19. <span data-ttu-id="bbc36-126">Sélectionnez Oui dans le champ Coût fixe.</span><span class="sxs-lookup"><span data-stu-id="bbc36-126">Select Yes in the Fixed cost field.</span></span>
20. <span data-ttu-id="bbc36-127">Sélectionnez Oui dans le champ Coût variable.</span><span class="sxs-lookup"><span data-stu-id="bbc36-127">Select Yes in the Variable cost field.</span></span>
21. <span data-ttu-id="bbc36-128">Sélectionnez Oui dans le champ Coût total.</span><span class="sxs-lookup"><span data-stu-id="bbc36-128">Select Yes in the Total cost field.</span></span>
22. <span data-ttu-id="bbc36-129">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="bbc36-129">Click Save.</span></span>
23. <span data-ttu-id="bbc36-130">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="bbc36-130">Close the page.</span></span>
24. <span data-ttu-id="bbc36-131">Accédez à Contrôle de gestion > Espaces de travail > Contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="bbc36-131">Go to Cost accounting > Workspaces > Cost control.</span></span>
25. <span data-ttu-id="bbc36-132">Sélectionnez un relevé pour afficher les coûts fixes, variables, totaux et non classés pour les périodes fiscales sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="bbc36-132">Select a statement to see fixed, variable, total, and unclassified costs for the selected fiscal periods.</span></span>
26. <span data-ttu-id="bbc36-133">Dans le champ Période de calendrier fiscal, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bbc36-133">In the Fiscal calendar period field, enter or select a value.</span></span>
27. <span data-ttu-id="bbc36-134">Dans le champ Nœud de hiérarchie des dimensions d'objet de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="bbc36-134">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="bbc36-135">Après avoir sélectionné une hiérarchie Dimension d'objet de coût, développez la hiérarchie Dimension d'élément de coût pour afficher les valeurs de coût souhaitées.</span><span class="sxs-lookup"><span data-stu-id="bbc36-135">After you've selected a Cost object dimension hierarchy, expand the Cost element dimension hierarchy to see the desired cost values.</span></span> <span data-ttu-id="bbc36-136">Par exemple, vous pouvez développer la hiérarchie des frais généraux de fabrication pour afficher la valeur.</span><span class="sxs-lookup"><span data-stu-id="bbc36-136">For example, you can expand the hierarchy to Manufacturing overhead to see the value.</span></span>  

