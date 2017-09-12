--- 
title: "Paramétrer la tarification par attribut pour les produits configurables"
description: "Cette procédure décrit comment paramétrer la tarification basée sur des attributs."
author: BibiSp
manager: AnnBe
ms.date: 10/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: b113fb639b5d7c50e519a0225b1e5d8315b7f3a9
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a><span data-ttu-id="259ec-103">Paramétrer la tarification par attribut pour les produits configurables</span><span class="sxs-lookup"><span data-stu-id="259ec-103">Set up attribute-based pricing for configurable products</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="259ec-104">Cette procédure décrit comment paramétrer la tarification basée sur des attributs.</span><span class="sxs-lookup"><span data-stu-id="259ec-104">This procedure shows how to set up attribute-based pricing.</span></span> <span data-ttu-id="259ec-105">Comme condition préalable, vous devez avoir un modèle de configuration de produit contenant un ou plusieurs composants et attributs.</span><span class="sxs-lookup"><span data-stu-id="259ec-105">As a prerequisite, you must have a product configuration model that has one or more components and attributes.</span></span> <span data-ttu-id="259ec-106">Cet exemple utilise le modèle de produit Haut-parleur haut de gamme dans les données de démonstration de la société fictive USMF.</span><span class="sxs-lookup"><span data-stu-id="259ec-106">This example uses the High End Speaker product model in the USMF demo data company.</span></span> <span data-ttu-id="259ec-107">Généralement, un responsable de produit utilise cette procédure.</span><span class="sxs-lookup"><span data-stu-id="259ec-107">Typically, a product manager uses this procedure.</span></span>


## <a name="create-a-new-price-model"></a><span data-ttu-id="259ec-108">Créer un modèle de prix</span><span class="sxs-lookup"><span data-stu-id="259ec-108">Create a new price model</span></span>
1. <span data-ttu-id="259ec-109">Cliquez sur Définition du modèle de variante de produit.</span><span class="sxs-lookup"><span data-stu-id="259ec-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="259ec-110">Cliquez sur Modèles de configuration de produit.</span><span class="sxs-lookup"><span data-stu-id="259ec-110">Click Product configuration models.</span></span>
3. <span data-ttu-id="259ec-111">Dans la liste, sélectionnez la ligne Haut-parleur haut de gamme, mais ne cliquez pas sur le lien du nom.</span><span class="sxs-lookup"><span data-stu-id="259ec-111">In the list, select the High End Speaker line, but don’t click the link for the name.</span></span>
4. <span data-ttu-id="259ec-112">Dans le volet Actions, cliquez sur Modèle.</span><span class="sxs-lookup"><span data-stu-id="259ec-112">On the Action Pane, click Model.</span></span>
5. <span data-ttu-id="259ec-113">Cliquez sur Modèles de prix.</span><span class="sxs-lookup"><span data-stu-id="259ec-113">Click Price models.</span></span>
6. <span data-ttu-id="259ec-114">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="259ec-114">Click New.</span></span>
7. <span data-ttu-id="259ec-115">Dans le champ Modèle de prix, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="259ec-115">In the Price model name field, type a value.</span></span>
    * <span data-ttu-id="259ec-116">Utilisez un nom qui permet d'identifier facilement le modèle.</span><span class="sxs-lookup"><span data-stu-id="259ec-116">Use a name that makes the model easy to identify.</span></span>  
8. <span data-ttu-id="259ec-117">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="259ec-117">In the Description field, type a value.</span></span>
9. <span data-ttu-id="259ec-118">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="259ec-118">Click Save.</span></span>

## <a name="add-price-elements"></a><span data-ttu-id="259ec-119">Ajouter des éléments de prix</span><span class="sxs-lookup"><span data-stu-id="259ec-119">Add price elements</span></span>
1. <span data-ttu-id="259ec-120">Cliquez sur Modifier.</span><span class="sxs-lookup"><span data-stu-id="259ec-120">Click Edit.</span></span>
    * <span data-ttu-id="259ec-121">Chaque composant d'un modèle de produit peut avoir un élément de prix de base et plusieurs règles d'expression de prix.</span><span class="sxs-lookup"><span data-stu-id="259ec-121">Each component in a product model can have a base price element and any number of price expression rules.</span></span> <span data-ttu-id="259ec-122">Vous pouvez également ajouter des prix dans différentes devises.</span><span class="sxs-lookup"><span data-stu-id="259ec-122">You can also add prices in different currencies.</span></span>  
2. <span data-ttu-id="259ec-123">Dans le champ Expression de prix de base, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="259ec-123">In the Base price expression field, type a value.</span></span>
    * <span data-ttu-id="259ec-124">Entrez 100, par exemple.</span><span class="sxs-lookup"><span data-stu-id="259ec-124">For example, type 100.</span></span>   <span data-ttu-id="259ec-125">Une expression de prix de base peut être une valeur numérique, ou elle peut consister en un calcul arithmétique qui implique un ou plusieurs attributs.</span><span class="sxs-lookup"><span data-stu-id="259ec-125">A base price expression can be a numerical value, or it can consist of an arithmetic calculation that involves one or more attributes.</span></span>  
3. <span data-ttu-id="259ec-126">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="259ec-126">Click Add.</span></span>
4. <span data-ttu-id="259ec-127">Dans le champ Nom, tapez « Bois de rose ».</span><span class="sxs-lookup"><span data-stu-id="259ec-127">In the Name field, type ‘Rosewood’.</span></span>
    * <span data-ttu-id="259ec-128">Le nom de l'expression de prix permet d'identifier ce que représente l'élément de prix.</span><span class="sxs-lookup"><span data-stu-id="259ec-128">The price expression name helps identify what the price element represents.</span></span> <span data-ttu-id="259ec-129">Dans cet exemple, nous créons un élément de prix pour l'option Finitions du meuble pour haut-parleur en bois de rose.</span><span class="sxs-lookup"><span data-stu-id="259ec-129">In this example, we are creating a price element for the Rosewood speaker cabinet finish option.</span></span>  
5. <span data-ttu-id="259ec-130">Cliquez sur Modifier la condition.</span><span class="sxs-lookup"><span data-stu-id="259ec-130">Click Edit condition.</span></span>
    * <span data-ttu-id="259ec-131">Une condition de prix permet de garantir qu'un élément d'expression de prix est inclus dans le prix de vente uniquement si une combinaison spécifique d'attributs est présente.</span><span class="sxs-lookup"><span data-stu-id="259ec-131">A price condition helps guarantee that a price expression element is included in the sales price only if a specific combination of attributes is present.</span></span>  
6. <span data-ttu-id="259ec-132">Dans le champ ConstraintBody, entrez « CabinetFinish=="Rosewood" ».</span><span class="sxs-lookup"><span data-stu-id="259ec-132">In the ConstraintBody field, enter 'CabinetFinish=="Rosewood"'.</span></span>
7. <span data-ttu-id="259ec-133">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="259ec-133">Click OK.</span></span>
8. <span data-ttu-id="259ec-134">Dans le champ Expression, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="259ec-134">In the Expression field, type a value.</span></span>
    * <span data-ttu-id="259ec-135">Entrez 50, par exemple.</span><span class="sxs-lookup"><span data-stu-id="259ec-135">For example, type 50.</span></span>  
9. <span data-ttu-id="259ec-136">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="259ec-136">Close the page.</span></span>
10. <span data-ttu-id="259ec-137">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="259ec-137">Close the page.</span></span>


