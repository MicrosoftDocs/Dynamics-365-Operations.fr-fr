--- 
title: "Paramétrer des stratégies pour les hiérarchies de catégories d'approvisionnement"
description: "Cette procédure permet de définir des règles pour commander des produits dans une catégorie."
author: mkirknel
manager: AnnBe
ms.date: 08/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: a8f21599aec191c0358d919b501834677cda30ac
ms.contentlocale: fr-fr
ms.lasthandoff: 08/07/2018

---
# <a name="set-up-policies-for-procurement-category-hierarchies"></a><span data-ttu-id="6ec3b-103">Paramétrer des stratégies pour les hiérarchies de catégories d'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="6ec3b-103">Set up policies for procurement category hierarchies</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6ec3b-104">Cette procédure permet de définir des règles pour commander des produits dans une catégorie.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-104">Use this procedure to set up rules for ordering products in a category.</span></span> <span data-ttu-id="6ec3b-105">Les règles sont définies pour une politique d'achat spécifique.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-105">The rules are defined for a specific purchasing policy.</span></span> <span data-ttu-id="6ec3b-106">La règle d'accès à la catégorie détermine à quelles catégories d'approvisionnement les utilisateurs ont accès lorsqu'ils créent une demande.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-106">The category access rule controls which procurement categories employees have access to when they create a requisition.</span></span> <span data-ttu-id="6ec3b-107">Lorsqu'une demande est créée, la règle d'accès aux catégories et la politique d'achat à appliquer est déterminée en fonction de l'entité juridique et l'unité opérationnelle auxquelles l'employé appartient.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-107">When a requisition is being created, the purchasing policy and category access rule that should be applied are determined by the legal entity and the operational unit that the employee belongs to.</span></span> <span data-ttu-id="6ec3b-108">Vous pouvez utiliser cette procédure dans les données fictives de la société USMF.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-108">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="6ec3b-109">Cette tâche est généralement effectuée par un responsable des achats.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-109">This task would typically be carried out by a purchasing manager.</span></span>


## <a name="find-the-procurement-policy"></a><span data-ttu-id="6ec3b-110">Rechercher la stratégie d'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="6ec3b-110">Find the procurement policy</span></span>
1. <span data-ttu-id="6ec3b-111">Allez dans Approvisionnements > Paramétrage > Stratégies > Politiques d'achat.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-111">Go to Procurement and sourcing > Setup > Policies > Purchasing policies.</span></span>
2. <span data-ttu-id="6ec3b-112">Cliquez sur le lien de la stratégie d'approvisionnement USMF.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-112">Click the link on the Procurement Policy USMF policy.</span></span>
    * <span data-ttu-id="6ec3b-113">Il s'agit de la stratégie à laquelle vous devez ajouter la règle.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-113">This is the policy that you’ll add a rule to.</span></span> <span data-ttu-id="6ec3b-114">Il doit s'agir d'une stratégie Active.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-114">It must be an Active policy.</span></span>  

## <a name="create-a-category-access-rule"></a><span data-ttu-id="6ec3b-115">Création d'une règle d'accès à la catégorie</span><span class="sxs-lookup"><span data-stu-id="6ec3b-115">Create a category access rule</span></span>
1. <span data-ttu-id="6ec3b-116">Sélectionnez la règle de stratégie d'accès à la catégorie.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-116">Select the Category access policy rule.</span></span>
    * <span data-ttu-id="6ec3b-117">Le bouton Créer une règle de stratégie est estompé parce qu'il y a déjà une règle de stratégie active pour l'accès à la catégorie.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-117">If the Create policy rule button is dimmed, it’s because there’s already an active policy rule for Category access.</span></span> <span data-ttu-id="6ec3b-118">Vérifiez les champs Date d'effet et Date d'expiration pour déterminer de quelle règle il s'agit, puis sélectionnez-la et cliquez sur Supprimer la règle de stratégie.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-118">Check the Effective and Expiration date fields to determine which it is, then select it, and click Retire policy rule.</span></span> <span data-ttu-id="6ec3b-119">Si le bouton Créer une règle de stratégie est disponible, vous n'avez rien à faire.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-119">If the Create policy rule button is available, you don’t need to do anything.</span></span>  
2. <span data-ttu-id="6ec3b-120">Cliquez sur Créer une règle de stratégie.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-120">Click Create policy rule.</span></span>
3. <span data-ttu-id="6ec3b-121">Entrez une date et une heure dans le champ Date d'effet.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-121">In the Effective date field, enter a date and time.</span></span>
    * <span data-ttu-id="6ec3b-122">La durée ne doit pas chevaucher une autre règle qui est déjà active.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-122">The time must not overlap with another rule that’s already active.</span></span>  
    * <span data-ttu-id="6ec3b-123">Choisissez une catégorie à la laquelle la règle s'appliquera.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-123">Select a category that the rule will apply to.</span></span> <span data-ttu-id="6ec3b-124">Notez la catégorie dont il s'agit, vous en aurez besoin plus tard.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-124">Make a note of which category this is – you’ll need it later.</span></span> <span data-ttu-id="6ec3b-125">Lorsque vous sélectionnez une catégorie, sa ou ses catégories parentes sont également ajoutées à la liste Catégories sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-125">When you select a category, its parent category or categories will also be added to the Selected categories list.</span></span>  
    * <span data-ttu-id="6ec3b-126">Pour appliquer la règle à toutes les sous-catégories de la catégorie sélectionnée, cochez la case Inclure les sous-catégories.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-126">If you want the rule to apply to all subcategories of the selected category, select the Include subcategories check box.</span></span>  
4. <span data-ttu-id="6ec3b-127">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-127">Click Add.</span></span>
    * <span data-ttu-id="6ec3b-128">Si vous définissez l'option Inclure la règle parent sur Oui, la règle de stratégie que vous définissez pour une catégorie parente est également affectée à ses catégories enfants si aucune règle de stratégie n'a été définie pour les catégories enfants.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-128">If you set the Include parent rule option to Yes, the policy rule that you define for a parent category is also assigned to its child categories, if no policy rule has been defined for the child categories.</span></span>  
5. <span data-ttu-id="6ec3b-129">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-129">Click OK.</span></span>

## <a name="create-a-category-policy-rule"></a><span data-ttu-id="6ec3b-130">Création d'une règle de stratégie de catégorie.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-130">Create a category policy rule</span></span>
1. <span data-ttu-id="6ec3b-131">Sélectionner la règle de stratégie de catégorie</span><span class="sxs-lookup"><span data-stu-id="6ec3b-131">Select the Category policy rule</span></span>
    * <span data-ttu-id="6ec3b-132">Si le bouton Créer une règle de stratégie est estompé, choisissez la règle de stratégie active, puis cliquez sur Supprimer la règle de stratégie.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-132">If the Create policy rule button is dimmed, select the active policy rule, and then click Retire policy rule.</span></span>  
2. <span data-ttu-id="6ec3b-133">Cliquez sur Créer une règle de stratégie.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-133">Click Create policy rule.</span></span>
3. <span data-ttu-id="6ec3b-134">Entrez une date et une heure dans le champ Date d'effet.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-134">In the Effective date field, enter a date and time.</span></span>
4. <span data-ttu-id="6ec3b-135">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-135">Click Add.</span></span>
5. <span data-ttu-id="6ec3b-136">Choisissez la même catégorie que celle utilisée pour la règle d'accès à la catégorie.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-136">Select the same category that you used for the Category access rule.</span></span>
6. <span data-ttu-id="6ec3b-137">Dans le champ Sélection de fournisseur, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-137">In the Vendor selection field, select an option.</span></span>
    * <span data-ttu-id="6ec3b-138">Choisissez une règle pour contrôler le genre de fournisseur qui peut être choisi pour la catégorie quand des demandes sont créées.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-138">Select a rule to control which kind of vendors can be selected for the category when requisitions are created.</span></span>  
7. <span data-ttu-id="6ec3b-139">Cliquez sur Fermer.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-139">Click Close.</span></span>
    * <span data-ttu-id="6ec3b-140">Les règles de stratégie que vous avez définies concernaient des demandes de type Consommation.</span><span class="sxs-lookup"><span data-stu-id="6ec3b-140">The policy rules that you have defined have been for requisitions of type Consumption.</span></span> <span data-ttu-id="6ec3b-141">Pour définir des stratégies pour des demandes de type Réapprovisionnement, vous devez créer une règle pour le type de règle de stratégie appelé « Règle de stratégie d'accès à la catégorie de réapprovisionnement ».</span><span class="sxs-lookup"><span data-stu-id="6ec3b-141">If you wanted to define policies for requisitions of type Replenishment, you would create a rule for the Policy rule type called “Replenishment category access policy rule”.</span></span>  


