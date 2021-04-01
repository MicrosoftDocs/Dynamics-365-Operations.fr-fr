---
title: Gérer l’unité de mesure
description: Cette procédure décrit comment définir une unité de mesure, fournir des traductions pour l’unité et sa description, et définir des règles de conversion pour les unités associées.
author: sorenva
manager: tfehr
ms.date: 07/08/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup, UnitOfMeasureCalculator, UnitOfMeasureWizard, UnitOfMeasureLookupTest
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ea89c00bc201f721617fe4f904b660da29e97fc2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5260573"
---
# <a name="manage-unit-of-measure"></a><span data-ttu-id="51cb1-103">Gérer l’unité de mesure</span><span class="sxs-lookup"><span data-stu-id="51cb1-103">Manage unit of measure</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="51cb1-104">Cette procédure décrit comment définir une unité de mesure, fournir des traductions pour l’unité et sa description, et définir des règles de conversion pour les unités associées.</span><span class="sxs-lookup"><span data-stu-id="51cb1-104">This procedure shows how to define a unit of measure, provide translations for the unit and it's description, and define conversion rules for related units.</span></span> <span data-ttu-id="51cb1-105">Vous pouvez découvrir cette procédure à l’aide de la société fictive de démonstration USMF ou de vos propres données.</span><span class="sxs-lookup"><span data-stu-id="51cb1-105">You can walk through this procedure using demo data, or using your own data.</span></span>

1. <span data-ttu-id="51cb1-106">Accédez à **Volet de navigation > Modules > Gestion d’informations sur les produits > Gestion des produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="51cb1-106">Go to **Navigation pane > Modules > Product information management > Released product maintenance**.</span></span>
2. <span data-ttu-id="51cb1-107">Cliquez sur **Unités**.</span><span class="sxs-lookup"><span data-stu-id="51cb1-107">Click **Units**.</span></span>

## <a name="create-a-unit-of-measure"></a><span data-ttu-id="51cb1-108">Créer une unité de mesure</span><span class="sxs-lookup"><span data-stu-id="51cb1-108">Create a unit of measure</span></span>
1. <span data-ttu-id="51cb1-109">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="51cb1-109">Click **New**.</span></span>
2. <span data-ttu-id="51cb1-110">Dans le champ **Unité**, tapez une valeur.</span><span class="sxs-lookup"><span data-stu-id="51cb1-110">In the **Unit** field, type a value.</span></span> <span data-ttu-id="51cb1-111">Entrez l’ID ou le symbole à utiliser en se rapportant à l’unité de mesure.</span><span class="sxs-lookup"><span data-stu-id="51cb1-111">Enter the ID or symbol to use when referring to the unit of measure.</span></span>  
3. <span data-ttu-id="51cb1-112">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="51cb1-112">In the **Description** field, type a value.</span></span> <span data-ttu-id="51cb1-113">Entrez un nom descriptif pour l’unité de mesure dans la langue du système.</span><span class="sxs-lookup"><span data-stu-id="51cb1-113">Enter a descriptive name for the unit of measure in the system language.</span></span>  
4. <span data-ttu-id="51cb1-114">Dans le champ **Classe d’unités**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="51cb1-114">In the **Unit class** field, select an option.</span></span> <span data-ttu-id="51cb1-115">Une classe d’unités définit le regroupement logique, tel que la superficie, la masse ou la quantité, dont l’unité de mesure fait partie.</span><span class="sxs-lookup"><span data-stu-id="51cb1-115">The unit class defines what logical grouping, such as area, mass, or quantity, the unit of measure is part of.</span></span>  
5. <span data-ttu-id="51cb1-116">Dans le champ **Précision décimale**, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="51cb1-116">In the **Decimal precision** field, enter a number.</span></span> <span data-ttu-id="51cb1-117">Indiquez le nombre de décimales auxquelles l’unité de mesure convertie doit être arrondie lorsqu’un calcul est réalisé pour l’unité de mesure.</span><span class="sxs-lookup"><span data-stu-id="51cb1-117">Specify the number of decimals that the converted unit of measure must be rounded to when a calculation is completed for the unit of measure.</span></span>  
6. <span data-ttu-id="51cb1-118">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="51cb1-118">Click **Save**.</span></span>

## <a name="define-unit-translations"></a><span data-ttu-id="51cb1-119">Définir des traductions d’unité</span><span class="sxs-lookup"><span data-stu-id="51cb1-119">Define unit translations</span></span>
1. <span data-ttu-id="51cb1-120">Dans le volet **Actions**, cliquez sur **Textes d’unité**.</span><span class="sxs-lookup"><span data-stu-id="51cb1-120">On the **Action Pane**, click **Unit texts**.</span></span>
2. <span data-ttu-id="51cb1-121">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="51cb1-121">Click **New**.</span></span> <span data-ttu-id="51cb1-122">Utilisez le texte d’unité pour créer une traduction de l’ID ou d’un symbole représentant l’unité de mesure à utiliser sur des documents externes dans les langues du client ou spécifiques au fournisseur.</span><span class="sxs-lookup"><span data-stu-id="51cb1-122">Use unit text to create a translation of the ID or a symbol representing the unit of measure for use on external documents in customer- or vendor-specific languages.</span></span>  
3. <span data-ttu-id="51cb1-123">Dans le champ **Langue**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="51cb1-123">In the **Language** field, enter or select a value.</span></span>
4. <span data-ttu-id="51cb1-124">Tapez une valeur dans le champ **Texte**.</span><span class="sxs-lookup"><span data-stu-id="51cb1-124">In the **Text** field, type a value.</span></span>
5. <span data-ttu-id="51cb1-125">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="51cb1-125">Click **Save**.</span></span>
6. <span data-ttu-id="51cb1-126">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="51cb1-126">Close the page.</span></span>
7. <span data-ttu-id="51cb1-127">Dans le volet **Actions**, cliquez sur **Descriptions de l’unité traduite**.</span><span class="sxs-lookup"><span data-stu-id="51cb1-127">On the **Action Pane**, click **Translated unit descriptions**.</span></span>
8. <span data-ttu-id="51cb1-128">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="51cb1-128">Click **New**.</span></span> <span data-ttu-id="51cb1-129">Définissez des descriptions spécifiques à une langue pour l’unité de mesure.</span><span class="sxs-lookup"><span data-stu-id="51cb1-129">Define language-specific descriptions for the unit of measure.</span></span>  
9. <span data-ttu-id="51cb1-130">Dans le champ **Langue**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="51cb1-130">In the **Language** field, enter or select a value.</span></span>
10. <span data-ttu-id="51cb1-131">Tapez une valeur dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="51cb1-131">In the **Description** field, type a value.</span></span>
11. <span data-ttu-id="51cb1-132">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="51cb1-132">Click **Save**.</span></span>
12. <span data-ttu-id="51cb1-133">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="51cb1-133">Close the page.</span></span>

## <a name="define-unit-conversion-rules"></a><span data-ttu-id="51cb1-134">Définir des règles de conversion d’unités</span><span class="sxs-lookup"><span data-stu-id="51cb1-134">Define unit conversion rules</span></span>
1. <span data-ttu-id="51cb1-135">Dans le volet **Actions**, cliquez sur **Conversion d’unités**.</span><span class="sxs-lookup"><span data-stu-id="51cb1-135">On the **Action Pane**, click **Unit conversions**.</span></span> <span data-ttu-id="51cb1-136">Définissez les règles pour convertir l’unité de mesure vers et depuis d’autres unités de mesure appartenant à la classe d’unités sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="51cb1-136">Define rules for converting the unit of measure to and from other units of measure in the selected unit class.</span></span>  
2. <span data-ttu-id="51cb1-137">Cliquez sur **Nouveau** pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="51cb1-137">Click **New** to open the drop dialog.</span></span>
3. <span data-ttu-id="51cb1-138">Dans le champ **Facteur**, entrez un nombre.</span><span class="sxs-lookup"><span data-stu-id="51cb1-138">In the **Factor** field, enter a number.</span></span> <span data-ttu-id="51cb1-139">Facteur de conversion entre l’Unité d’origine et l’Unité de destination.</span><span class="sxs-lookup"><span data-stu-id="51cb1-139">Conversion factor between the From unit and the To unit.</span></span> <span data-ttu-id="51cb1-140">Par exemple, le facteur de conversion du centimètre vers le mètre est 100, car il y a 100 centimètres dans 1 mètre.</span><span class="sxs-lookup"><span data-stu-id="51cb1-140">For example, the conversion factor from centimeter to meter is 100 because there are 100 centimeters in one meter.</span></span>  
4. <span data-ttu-id="51cb1-141">Dans le champ **Unité de destination**, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="51cb1-141">In the **To unit** field, enter or select a value.</span></span>
5. <span data-ttu-id="51cb1-142">Dans le champ **Arrondi**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="51cb1-142">In the **Rounding** field, select an option.</span></span> <span data-ttu-id="51cb1-143">Définissez l’arrondi de la valeur convertie.</span><span class="sxs-lookup"><span data-stu-id="51cb1-143">Define how the converted value should be rounded.</span></span>  
6. <span data-ttu-id="51cb1-144">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="51cb1-144">Click **OK**.</span></span>
7. <span data-ttu-id="51cb1-145">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="51cb1-145">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]