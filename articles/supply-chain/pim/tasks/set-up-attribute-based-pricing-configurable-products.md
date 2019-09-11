---
title: Paramétrer la tarification par attribut pour les produits configurables
description: Cette rubrique explique comment paramétrer la tarification basée sur des attributs.
author: ShylaThompson
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 534e9c9332c107afebd814cf2090ecbdf0ec6459
ms.sourcegitcommit: e10491a2ff04f65d9f306ef6e068ee123213b23b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/21/2019
ms.locfileid: "1914697"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a><span data-ttu-id="fdf64-103">Paramétrer la tarification par attribut pour les produits configurables</span><span class="sxs-lookup"><span data-stu-id="fdf64-103">Set up attribute-based pricing for configurable products</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fdf64-104">Cette rubrique explique comment paramétrer la tarification basée sur des attributs.</span><span class="sxs-lookup"><span data-stu-id="fdf64-104">This topic explains how to set up attribute-based pricing.</span></span> <span data-ttu-id="fdf64-105">Comme condition préalable, vous devez avoir un modèle de configuration de produit contenant un ou plusieurs composants et attributs.</span><span class="sxs-lookup"><span data-stu-id="fdf64-105">As a prerequisite, you must have a product configuration model that has one or more components and attributes.</span></span> <span data-ttu-id="fdf64-106">Cet exemple utilise le modèle de produit Haut-parleur haut de gamme dans les données de démonstration de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="fdf64-106">This example uses the High End Speaker product model in the USMF demo data company.</span></span> <span data-ttu-id="fdf64-107">Généralement, un responsable de produit utilise cette procédure.</span><span class="sxs-lookup"><span data-stu-id="fdf64-107">Typically, a product manager uses this procedure.</span></span>


## <a name="create-a-new-price-model"></a><span data-ttu-id="fdf64-108">Créer un modèle de prix</span><span class="sxs-lookup"><span data-stu-id="fdf64-108">Create a new price model</span></span>
1. <span data-ttu-id="fdf64-109">Sélectionnez **Définition du modèle de variante de produit** sur la page d'accueil.</span><span class="sxs-lookup"><span data-stu-id="fdf64-109">Select **Product variant model definition** on the home page.</span></span>
2. <span data-ttu-id="fdf64-110">Sélectionnez **Modèles de configuration du produit** dans la section **liens**.</span><span class="sxs-lookup"><span data-stu-id="fdf64-110">Select **Product configuration models** in the **links** section.</span></span>
3. <span data-ttu-id="fdf64-111">Dans la liste, sélectionnez la ligne **Haut-parleur haut de gamme**, mais ne cliquez pas sur le lien du nom.</span><span class="sxs-lookup"><span data-stu-id="fdf64-111">In the list, select the **High End Speaker** line, but don’t select the link for the name.</span></span>
4. <span data-ttu-id="fdf64-112">Dans le volet Actions, sélectionnez **Modèle**.</span><span class="sxs-lookup"><span data-stu-id="fdf64-112">On the Action Pane, select **Model**.</span></span>
5. <span data-ttu-id="fdf64-113">Sélectionnez **Modèles de prix**.</span><span class="sxs-lookup"><span data-stu-id="fdf64-113">Select **Price models**.</span></span>
6. <span data-ttu-id="fdf64-114">Sélectionnez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="fdf64-114">Select **New**.</span></span>
7. <span data-ttu-id="fdf64-115">Dans le champ **Nom du modèle de prix**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="fdf64-115">In the **Price model name** field, type a value.</span></span> <span data-ttu-id="fdf64-116">Utilisez un nom qui permet d'identifier facilement le modèle.</span><span class="sxs-lookup"><span data-stu-id="fdf64-116">Use a name that makes the model easy to identify.</span></span>  
8. <span data-ttu-id="fdf64-117">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="fdf64-117">In the **Description** field, type a value.</span></span>
9. <span data-ttu-id="fdf64-118">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="fdf64-118">Select **Save**.</span></span>

## <a name="add-price-elements"></a><span data-ttu-id="fdf64-119">Ajouter des éléments de prix</span><span class="sxs-lookup"><span data-stu-id="fdf64-119">Add price elements</span></span>
1. <span data-ttu-id="fdf64-120">Sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="fdf64-120">Select **Edit**.</span></span> <span data-ttu-id="fdf64-121">Chaque composant d'un modèle de produit peut avoir un élément de prix de base et plusieurs règles d'expression de prix.</span><span class="sxs-lookup"><span data-stu-id="fdf64-121">Each component in a product model can have a base price element and any number of price expression rules.</span></span> <span data-ttu-id="fdf64-122">Vous pouvez également ajouter des prix dans différentes devises.</span><span class="sxs-lookup"><span data-stu-id="fdf64-122">You can also add prices in different currencies.</span></span>  
2. <span data-ttu-id="fdf64-123">Dans le champ **Expression de prix de base**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="fdf64-123">In the **Base price expression** field, type a value.</span></span> <span data-ttu-id="fdf64-124">Entrez 100, par exemple.</span><span class="sxs-lookup"><span data-stu-id="fdf64-124">For example, type 100.</span></span> <span data-ttu-id="fdf64-125">Une expression de prix de base peut être une valeur numérique, ou elle peut consister en un calcul arithmétique qui implique un ou plusieurs attributs.</span><span class="sxs-lookup"><span data-stu-id="fdf64-125">A base price expression can be a numerical value, or it can consist of an arithmetic calculation that involves one or more attributes.</span></span>  
3. <span data-ttu-id="fdf64-126">Sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="fdf64-126">Select **Add**.</span></span>
4. <span data-ttu-id="fdf64-127">Dans le champ **Nom**, saisissez `Rosewood`.</span><span class="sxs-lookup"><span data-stu-id="fdf64-127">In the **Name** field, type `Rosewood`.</span></span> <span data-ttu-id="fdf64-128">Le nom de l'expression de prix permet d'identifier ce que représente l'élément de prix.</span><span class="sxs-lookup"><span data-stu-id="fdf64-128">The price expression name helps identify what the price element represents.</span></span> <span data-ttu-id="fdf64-129">Dans cet exemple, nous créons un élément de prix pour l'option Finitions du meuble pour haut-parleur en bois de rose.</span><span class="sxs-lookup"><span data-stu-id="fdf64-129">In this example, we are creating a price element for the Rosewood speaker cabinet finish option.</span></span>  
5. <span data-ttu-id="fdf64-130">Sélectionnez **Modifier la condition**.</span><span class="sxs-lookup"><span data-stu-id="fdf64-130">Select **Edit condition**.</span></span> <span data-ttu-id="fdf64-131">Une condition de prix permet de garantir qu'un élément d'expression de prix est inclus dans le prix de vente uniquement si une combinaison spécifique d'attributs est présente.</span><span class="sxs-lookup"><span data-stu-id="fdf64-131">A price condition helps guarantee that a price expression element is included in the sales price only if a specific combination of attributes is present.</span></span>  
6. <span data-ttu-id="fdf64-132">Dans le champ **ConstraintBody**, saisissez `CabinetFinish=="Rosewood"`.</span><span class="sxs-lookup"><span data-stu-id="fdf64-132">In the **ConstraintBody** field, enter `CabinetFinish=="Rosewood"`.</span></span>
7. <span data-ttu-id="fdf64-133">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fdf64-133">Select **OK**.</span></span>
8. <span data-ttu-id="fdf64-134">Dans le champ **Expression**, saisissez une valeur.</span><span class="sxs-lookup"><span data-stu-id="fdf64-134">In the **Expression** field, type a value.</span></span> <span data-ttu-id="fdf64-135">Par exemple, saisissez `50`.</span><span class="sxs-lookup"><span data-stu-id="fdf64-135">For example, type `50`.</span></span> 
9. <span data-ttu-id="fdf64-136">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="fdf64-136">Close the page.</span></span>

