--- 
title: "Gérer l'unité de mesure"
description: "Cette procédure décrit comment définir une unité de mesure, fournir des traductions pour l'unité et sa description, et définir des règles de conversion pour les unités associées."
author: sorenva
manager: AnnBe
ms.date: 02/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 6bb7a5133e9412f4ed6fb74f0d3ee595c07a0c4b
ms.contentlocale: fr-fr
ms.lasthandoff: 08/29/2017

---
# <a name="manage-unit-of-measure"></a><span data-ttu-id="e3976-103">Gérer l'unité de mesure</span><span class="sxs-lookup"><span data-stu-id="e3976-103">Manage unit of measure</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e3976-104">Cette procédure décrit comment définir une unité de mesure, fournir des traductions pour l'unité et sa description, et définir des règles de conversion pour les unités associées.</span><span class="sxs-lookup"><span data-stu-id="e3976-104">This procedure shows how to define a unit of measure, provide translations for the unit and it's description, and define conversion rules for related units.</span></span> <span data-ttu-id="e3976-105">Vous pouvez découvrir cette procédure à l'aide de la société fictive de démonstration USMF ou de vos propres données.</span><span class="sxs-lookup"><span data-stu-id="e3976-105">You can walk through this procedure using demo data, or using your own data.</span></span>

1. <span data-ttu-id="e3976-106">Accédez à la maintenance des produits lancés.</span><span class="sxs-lookup"><span data-stu-id="e3976-106">Go to Released product maintenance.</span></span>
2. <span data-ttu-id="e3976-107">Cliquez sur Unités.</span><span class="sxs-lookup"><span data-stu-id="e3976-107">Click Units.</span></span>

## <a name="create-a-unit-of-measure"></a><span data-ttu-id="e3976-108">Créer une unité de mesure</span><span class="sxs-lookup"><span data-stu-id="e3976-108">Create a unit of measure</span></span>
1. <span data-ttu-id="e3976-109">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e3976-109">Click New.</span></span>
2. <span data-ttu-id="e3976-110">Dans le champ Unité, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e3976-110">In the Unit field, type a value.</span></span>
    * <span data-ttu-id="e3976-111">Entrez l'ID ou le symbole à utiliser en se rapportant à l'unité de mesure.</span><span class="sxs-lookup"><span data-stu-id="e3976-111">Enter the ID or symbol to use when referring to the unit of measure.</span></span>  
3. <span data-ttu-id="e3976-112">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e3976-112">In the Description field, type a value.</span></span>
    * <span data-ttu-id="e3976-113">Entrez un nom descriptif pour l'unité de mesure dans la langue du système.</span><span class="sxs-lookup"><span data-stu-id="e3976-113">Enter a descriptive name for the unit of measure in the system language.</span></span>  
4. <span data-ttu-id="e3976-114">Dans le champ Classe d'unités, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="e3976-114">In the Unit class field, select an option.</span></span>
    * <span data-ttu-id="e3976-115">Une classe d'unités définit le regroupement logique, tel que la superficie, la masse ou la quantité, dont l'unité de mesure fait partie.</span><span class="sxs-lookup"><span data-stu-id="e3976-115">The unit class defines what logical grouping, such as area, mass, or quantity, the unit of measure is part of.</span></span>  
5. <span data-ttu-id="e3976-116">Dans le champ Précision décimale, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="e3976-116">In the Decimal precision field, enter a number.</span></span>
    * <span data-ttu-id="e3976-117">Indiquez le nombre de décimales auxquelles l'unité de mesure convertie doit être arrondie lorsqu'un calcul est réalisé pour l'unité de mesure.</span><span class="sxs-lookup"><span data-stu-id="e3976-117">Specify the number of decimals that the converted unit of measure must be rounded to when a calculation is completed for the unit of measure.</span></span>  
6. <span data-ttu-id="e3976-118">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e3976-118">Click Save.</span></span>

## <a name="define-unit-translations"></a><span data-ttu-id="e3976-119">Définir des traductions d'unité</span><span class="sxs-lookup"><span data-stu-id="e3976-119">Define unit translations</span></span>
1. <span data-ttu-id="e3976-120">Cliquez sur Textes d'unités.</span><span class="sxs-lookup"><span data-stu-id="e3976-120">Click Unit texts.</span></span>
2. <span data-ttu-id="e3976-121">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e3976-121">Click New.</span></span>
    * <span data-ttu-id="e3976-122">Utilisez le texte d'unité pour créer une traduction de l'ID ou d'un symbole représentant l'unité de mesure à utiliser sur des documents externes dans les langues du client ou spécifiques au fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e3976-122">Use unit text to create a translation of the ID or a symbol representing the unit of measure for use on external documents in customer- or vendor-specific languages.</span></span>  
3. <span data-ttu-id="e3976-123">Dans le champ Langue, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e3976-123">In the Language field, enter or select a value.</span></span>
4. <span data-ttu-id="e3976-124">Tapez une valeur dans le champ Texte.</span><span class="sxs-lookup"><span data-stu-id="e3976-124">In the Text field, type a value.</span></span>
5. <span data-ttu-id="e3976-125">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e3976-125">Click Save.</span></span>
6. <span data-ttu-id="e3976-126">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e3976-126">Close the page.</span></span>
7. <span data-ttu-id="e3976-127">Cliquez sur Descriptions de l'unité traduite.</span><span class="sxs-lookup"><span data-stu-id="e3976-127">Click Translated unit descriptions.</span></span>
8. <span data-ttu-id="e3976-128">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="e3976-128">Click New.</span></span>
    * <span data-ttu-id="e3976-129">Définissez des descriptions spécifiques à une langue pour l'unité de mesure.</span><span class="sxs-lookup"><span data-stu-id="e3976-129">Define language-specific descriptions for the unit of measure.</span></span>  
9. <span data-ttu-id="e3976-130">Dans le champ Langue, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e3976-130">In the Language field, enter or select a value.</span></span>
10. <span data-ttu-id="e3976-131">Dans le champ Description, entrez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e3976-131">In the Description field, type a value.</span></span>
11. <span data-ttu-id="e3976-132">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="e3976-132">Click Save.</span></span>
12. <span data-ttu-id="e3976-133">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e3976-133">Close the page.</span></span>

## <a name="define-unit-conversion-rules"></a><span data-ttu-id="e3976-134">Définir des règles de conversion d'unités</span><span class="sxs-lookup"><span data-stu-id="e3976-134">Define unit conversion rules</span></span>
1. <span data-ttu-id="e3976-135">Cliquez sur Conversions d'unités.</span><span class="sxs-lookup"><span data-stu-id="e3976-135">Click Unit conversions.</span></span>
    * <span data-ttu-id="e3976-136">Définissez les règles pour convertir l'unité de mesure vers et depuis d'autres unités de mesure appartenant à la classe d'unités sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e3976-136">Define rules for converting the unit of measure to and from other units of measure in the selected unit class.</span></span>  
2. <span data-ttu-id="e3976-137">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e3976-137">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="e3976-138">Dans le champ Facteur, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="e3976-138">In the Factor field, enter a number.</span></span>
    * <span data-ttu-id="e3976-139">Facteur de conversion entre l'Unité d'origine et l'Unité de destination.</span><span class="sxs-lookup"><span data-stu-id="e3976-139">Conversion factor between the From unit and the To unit.</span></span> <span data-ttu-id="e3976-140">Par exemple, le facteur de conversion du centimètre vers le mètre est 100, car il y a 100 centimètres dans 1 mètre.</span><span class="sxs-lookup"><span data-stu-id="e3976-140">For example, the conversion factor from centimeter to meter is 100 because there are 100 centimeters in one meter.</span></span>  
4. <span data-ttu-id="e3976-141">Dans le champ Unité de destination, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="e3976-141">In the To unit field, enter or select a value.</span></span>
5. <span data-ttu-id="e3976-142">Dans le champ Arrondi, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="e3976-142">In the Rounding field, select an option.</span></span>
    * <span data-ttu-id="e3976-143">Définissez l'arrondi de la valeur convertie.</span><span class="sxs-lookup"><span data-stu-id="e3976-143">Define how the converted value should be rounded.</span></span>  
6. <span data-ttu-id="e3976-144">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="e3976-144">Click OK.</span></span>
7. <span data-ttu-id="e3976-145">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e3976-145">Close the page.</span></span>


