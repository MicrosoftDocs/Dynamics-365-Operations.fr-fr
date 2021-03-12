---
title: Configurer les paramètres de l’espace de travail de contrôle des coûts
description: Cette procédure permet de configurer l’espace de travail Contrôle des coûts afin que les gestionnaires à différents niveaux d’une organisation puissent obtenir des informations sur leurs objets de coût, tels que les centres de coût et les groupes de produits.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostControlWorkspaceConfigurationPerUser
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9861d6bc83d3f1d62091154a36436627eeccad4a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969351"
---
# <a name="configure-cost-control-workspace-parameters"></a><span data-ttu-id="5dec2-103">Configurer les paramètres de l’espace de travail de contrôle des coûts</span><span class="sxs-lookup"><span data-stu-id="5dec2-103">Configure cost control workspace parameters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5dec2-104">Cette procédure permet de configurer l’espace de travail Contrôle des coûts afin que les gestionnaires à différents niveaux d’une organisation puissent obtenir des informations sur leurs objets de coût, tels que les centres de coût et les groupes de produits.</span><span class="sxs-lookup"><span data-stu-id="5dec2-104">Use this procedure to configure the Cost control workspace so that managers at various levels in an organization can gain insight into their cost objects, such as cost centers and product groups.</span></span> <span data-ttu-id="5dec2-105">La société fictive USP2 a été utilisée pour créer cet enregistrement.</span><span class="sxs-lookup"><span data-stu-id="5dec2-105">The USP2 demo company was used to create this recording.</span></span>

1. <span data-ttu-id="5dec2-106">Accédez à Contrôle de gestion > Paramétrage > Configuration de l’espace de travail de contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="5dec2-106">Go to Cost accounting > Setup > Cost control workspace configuration.</span></span>
2. <span data-ttu-id="5dec2-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="5dec2-107">Click New.</span></span>
3. <span data-ttu-id="5dec2-108">Tapez une valeur dans le champ Nom.</span><span class="sxs-lookup"><span data-stu-id="5dec2-108">In the Name field, type a value.</span></span>
4. <span data-ttu-id="5dec2-109">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5dec2-109">In the Description field, type a value.</span></span>
5. <span data-ttu-id="5dec2-110">Sélectionnez Oui dans le champ Publié.</span><span class="sxs-lookup"><span data-stu-id="5dec2-110">Select Yes in the Published field.</span></span>
    * <span data-ttu-id="5dec2-111">Si vous définissez cette option sur Oui, les utilisateurs affectés à l’un des rôles suivants peuvent afficher l’état dans l’espace de travail Contrôle des coûts : gestionnaire de contrôle de gestion, comptable, commis contrôleur de gestion ou contrôleur d’objet de coût.</span><span class="sxs-lookup"><span data-stu-id="5dec2-111">If you set this option to Yes, users who are assigned one of these roles can see the report in the Cost control workspace: cost accounting manager, cost accountant, cost accountant clerk, or cost object controller.</span></span> <span data-ttu-id="5dec2-112">Si vous définissez cette option sur Non, seuls les utilisateurs affectés à l’un des rôles suivants peuvent afficher l’état dans l’espace de travail Contrôle des coûts : gestionnaire de contrôle de gestion, comptable ou commis contrôleur de gestion.</span><span class="sxs-lookup"><span data-stu-id="5dec2-112">If you set this option to No, only users who are assigned one of these roles can see the report in the Cost control workspace: cost accounting manager, cost accountant, or cost accountant clerk.</span></span>  
6. <span data-ttu-id="5dec2-113">Développez la section Filtrage des données.</span><span class="sxs-lookup"><span data-stu-id="5dec2-113">Expand the Data filtering section.</span></span>
7. <span data-ttu-id="5dec2-114">Dans le champ Unité de contrôle des coûts, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5dec2-114">In the Cost control unit field, enter or select a value.</span></span>
8. <span data-ttu-id="5dec2-115">Dans le champ Version originale du budget, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5dec2-115">In the Budget original version field, enter or select a value.</span></span>
9. <span data-ttu-id="5dec2-116">Dans le champ Hiérarchie des dimensions d’élément de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5dec2-116">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
10. <span data-ttu-id="5dec2-117">Dans le champ Hiérarchie des dimensions d’objet de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5dec2-117">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
11. <span data-ttu-id="5dec2-118">Développez la section Affecter les enregistrements de calcul.</span><span class="sxs-lookup"><span data-stu-id="5dec2-118">Expand the Assign calculation records section.</span></span>
12. <span data-ttu-id="5dec2-119">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="5dec2-119">Click New.</span></span>
13. <span data-ttu-id="5dec2-120">Dans la liste, marquer la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5dec2-120">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="5dec2-121">Dans le champ Période de calendrier fiscal, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5dec2-121">In the Fiscal calendar period field, enter or select a value.</span></span>
15. <span data-ttu-id="5dec2-122">Dans le champ Version réelle, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5dec2-122">In the Actual version field, enter or select a value.</span></span>
16. <span data-ttu-id="5dec2-123">Développez la section Périodes fiscales par colonne.</span><span class="sxs-lookup"><span data-stu-id="5dec2-123">Expand the Fiscal periods per column section.</span></span>
17. <span data-ttu-id="5dec2-124">Sélectionnez Oui dans le champ Période actuelle.</span><span class="sxs-lookup"><span data-stu-id="5dec2-124">Select Yes in the Current period field.</span></span>
18. <span data-ttu-id="5dec2-125">Développez la section Colonnes à afficher pour les coûts.</span><span class="sxs-lookup"><span data-stu-id="5dec2-125">Expand the Columns to display for costs section.</span></span>
19. <span data-ttu-id="5dec2-126">Sélectionnez Oui dans le champ Coût fixe.</span><span class="sxs-lookup"><span data-stu-id="5dec2-126">Select Yes in the Fixed cost field.</span></span>
20. <span data-ttu-id="5dec2-127">Sélectionnez Oui dans le champ Coût variable.</span><span class="sxs-lookup"><span data-stu-id="5dec2-127">Select Yes in the Variable cost field.</span></span>
21. <span data-ttu-id="5dec2-128">Sélectionnez Oui dans le champ Coût total.</span><span class="sxs-lookup"><span data-stu-id="5dec2-128">Select Yes in the Total cost field.</span></span>
22. <span data-ttu-id="5dec2-129">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="5dec2-129">Click Save.</span></span>
23. <span data-ttu-id="5dec2-130">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="5dec2-130">Close the page.</span></span>
24. <span data-ttu-id="5dec2-131">Accédez à Contrôle de gestion > Espaces de travail > Contrôle des coûts.</span><span class="sxs-lookup"><span data-stu-id="5dec2-131">Go to Cost accounting > Workspaces > Cost control.</span></span>
25. <span data-ttu-id="5dec2-132">Sélectionnez un relevé pour afficher les coûts fixes, variables, totaux et non classés pour les périodes fiscales sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="5dec2-132">Select a statement to see fixed, variable, total, and unclassified costs for the selected fiscal periods.</span></span>
26. <span data-ttu-id="5dec2-133">Dans le champ Période de calendrier fiscal, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5dec2-133">In the Fiscal calendar period field, enter or select a value.</span></span>
27. <span data-ttu-id="5dec2-134">Dans le champ Nœud de hiérarchie des dimensions d’objet de coût, entrez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="5dec2-134">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="5dec2-135">Après avoir sélectionné une hiérarchie Dimension d’objet de coût, développez la hiérarchie Dimension d’élément de coût pour afficher les valeurs de coût souhaitées.</span><span class="sxs-lookup"><span data-stu-id="5dec2-135">After you've selected a Cost object dimension hierarchy, expand the Cost element dimension hierarchy to see the desired cost values.</span></span> <span data-ttu-id="5dec2-136">Par exemple, vous pouvez développer la hiérarchie des frais généraux de fabrication pour afficher la valeur.</span><span class="sxs-lookup"><span data-stu-id="5dec2-136">For example, you can expand the hierarchy to Manufacturing overhead to see the value.</span></span>  

