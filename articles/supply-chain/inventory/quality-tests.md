---
title: Tests de gestion de la qualité
description: Cette rubrique décrit comment créer des tests pour les utiliser avec des ordres de qualité dans Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b88011f486b6582db4727b85d021868899c6abe1
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956653"
---
# <a name="quality-management-tests"></a><span data-ttu-id="e80e2-103">Tests de gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="e80e2-103">Quality management tests</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e80e2-104">Cette rubrique décrit comment créer des tests pour les utiliser avec des ordres de qualité dans Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e80e2-104">This topic describes how to create tests that can be used for quality orders in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="e80e2-105">La page **Tests** permet de définir et d’afficher les tests individuels qui déterminent si vos produits correspondent aux spécifications de qualité.</span><span class="sxs-lookup"><span data-stu-id="e80e2-105">You use the **Tests** page to define and view the individual tests that determine whether your products meet quality specifications.</span></span> <span data-ttu-id="e80e2-106">Vous pouvez affecter un ou plusieurs tests à un groupe de tests.</span><span class="sxs-lookup"><span data-stu-id="e80e2-106">You can assign one or more individual tests to a test group.</span></span> <span data-ttu-id="e80e2-107">Dans ce cas, vous pouvez également spécifier des informations spécifiques aux tests, telles que les valeurs de mesures acceptables.</span><span class="sxs-lookup"><span data-stu-id="e80e2-107">In this case, you also specify test-specific information, such as the acceptable measurement values.</span></span> <span data-ttu-id="e80e2-108">Des valeurs de mesure sont utilisées pour les tests quantitatifs.</span><span class="sxs-lookup"><span data-stu-id="e80e2-108">Measurement values are used for quantitative tests.</span></span> <span data-ttu-id="e80e2-109">Pour les tests qualitatifs, des variables de test sont utilisées.</span><span class="sxs-lookup"><span data-stu-id="e80e2-109">For qualitative tests, test variables are used.</span></span>

- <span data-ttu-id="e80e2-110">Pour les tests quantitatifs, le champ **Type** est défini sur *Fraction* ou *Entier*.</span><span class="sxs-lookup"><span data-stu-id="e80e2-110">For quantitative tests, the **Type** field is set to *Integer* or *Fraction*.</span></span> <span data-ttu-id="e80e2-111">Une unité de mesure est également spécifiée.</span><span class="sxs-lookup"><span data-stu-id="e80e2-111">A unit of measure is also specified.</span></span> <span data-ttu-id="e80e2-112">Les spécifications de qualité et les résultats des tests peuvent être exprimés sous forme de nombres.</span><span class="sxs-lookup"><span data-stu-id="e80e2-112">Quality specifications and test results are expressed as numbers.</span></span>
- <span data-ttu-id="e80e2-113">Pour les tests qualitatifs, le champ **Type** de la page Tests est défini sur *Option*.</span><span class="sxs-lookup"><span data-stu-id="e80e2-113">For qualitative tests, the **Type** field is set to *Option*.</span></span> <span data-ttu-id="e80e2-114">Les tests qualitatifs exigent des informations supplémentaires sur la variable de test mesurée et la liste de ses options.</span><span class="sxs-lookup"><span data-stu-id="e80e2-114">Qualitative tests require additional information about the test variable that is being measured and its enumerated options.</span></span> <span data-ttu-id="e80e2-115">Les spécifications de qualité et les résultats des tests peuvent être exprimés sous forme de résultat.</span><span class="sxs-lookup"><span data-stu-id="e80e2-115">Quality specifications and test results are expressed according to an outcome.</span></span>

<span data-ttu-id="e80e2-116">Vous pouvez affecter un instrument de test à un test si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="e80e2-116">You can optionally assign a test instrument to a test.</span></span> <span data-ttu-id="e80e2-117">Cependant, les instruments de test ne sont pas nécessaires pour créer et utiliser des tests avec des ordres de qualité.</span><span class="sxs-lookup"><span data-stu-id="e80e2-117">However, test instruments aren't required to create and use tests with quality orders.</span></span> <span data-ttu-id="e80e2-118">Pour plus d'informations, consultez [Instruments de test de gestion de la qualité](quality-test-instruments.md).</span><span class="sxs-lookup"><span data-stu-id="e80e2-118">For more information, see [Quality management test instruments](quality-test-instruments.md).</span></span>

<span data-ttu-id="e80e2-119">Vous pouvez également spécifier une unité pour un test, pour indiquer l'unité de mesure dans laquelle les résultats du test sont enregistrés.</span><span class="sxs-lookup"><span data-stu-id="e80e2-119">You can also optionally specify a unit for a test, to indicate the unit of measure that test results are recorded in.</span></span> <span data-ttu-id="e80e2-120">Par exemple, un test de température peut inclure une unité de degrés Fahrenheit ou Celsius.</span><span class="sxs-lookup"><span data-stu-id="e80e2-120">For example, a test for temperature might include a unit of either degrees Fahrenheit or degrees Celsius.</span></span>

## <a name="example-of-a-test"></a><span data-ttu-id="e80e2-121">Exemple de test</span><span class="sxs-lookup"><span data-stu-id="e80e2-121">Example of a test</span></span>

<span data-ttu-id="e80e2-122">Une société de fabrication réalise deux tests sur du matériel acheté : un test quantitatif concernant la qualité du matériel et un test qualitatif concernant la solidité de l’emballage.</span><span class="sxs-lookup"><span data-stu-id="e80e2-122">A manufacturing company performs two tests on purchased material: a quantitative test for material quality and a qualitative test for packaging damage.</span></span> <span data-ttu-id="e80e2-123">Elle spécifie des informations supplémentaires concernant le test qualitatif afin de définir la variable de test (par exemple, solidité de l’emballage) et ses résultats.</span><span class="sxs-lookup"><span data-stu-id="e80e2-123">The company specifies additional information about the qualitative test to define the test variable (for example, damaged packaging) and its outcomes.</span></span> <span data-ttu-id="e80e2-124">Elle utilise la page **Groupes de test** pour affecter les deux tests à un groupe de test et spécifier les informations spécifiques aux tests.</span><span class="sxs-lookup"><span data-stu-id="e80e2-124">The company uses the **Test groups** page to assign the two tests to a test group and to specify the test-specific information.</span></span> <span data-ttu-id="e80e2-125">Le groupe de tests est affecté à un ordre de qualité, de sorte que la société puisse générer un état à partir des résultats des deux tests.</span><span class="sxs-lookup"><span data-stu-id="e80e2-125">The test group is assigned to a quality order so that the company can report test results for the two tests.</span></span>

## <a name="create-a-test"></a><span data-ttu-id="e80e2-126">Créer un test</span><span class="sxs-lookup"><span data-stu-id="e80e2-126">Create a test</span></span>

<span data-ttu-id="e80e2-127">Pour créer un test, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e80e2-127">Follow these steps to create a test.</span></span>

1. <span data-ttu-id="e80e2-128">Allez dans **Gestion des stocks \> Paramétrage \> Contrôle de la qualité \> Tests**.</span><span class="sxs-lookup"><span data-stu-id="e80e2-128">Go to **Inventory management \> Setup \> Quality control \> Tests**.</span></span>
1. <span data-ttu-id="e80e2-129">Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille.</span><span class="sxs-lookup"><span data-stu-id="e80e2-129">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="e80e2-130">Définissez ensuite les champs suivants pour la nouvelle ligne :</span><span class="sxs-lookup"><span data-stu-id="e80e2-130">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="e80e2-131">**Test** - Saisissez un identifiant ou un nom unique pour le test.</span><span class="sxs-lookup"><span data-stu-id="e80e2-131">**Test** – Enter a unique ID or name for the test.</span></span>
    - <span data-ttu-id="e80e2-132">**Description** - Entrez une description détaillée du test.</span><span class="sxs-lookup"><span data-stu-id="e80e2-132">**Description** – Enter a detailed description of the test.</span></span>
    - <span data-ttu-id="e80e2-133">**Type** - Sélectionnez le type de résultats produit par le test.</span><span class="sxs-lookup"><span data-stu-id="e80e2-133">**Type** – Select the type of results that the test produces.</span></span> <span data-ttu-id="e80e2-134">Pour les tests quantitatifs, sélectionnez *Fraction* ou *Entier*.</span><span class="sxs-lookup"><span data-stu-id="e80e2-134">For quantitative tests, select *Fraction* or *Integer*.</span></span> <span data-ttu-id="e80e2-135">Pour les tests qualitatifs, sélectionnez *Option*.</span><span class="sxs-lookup"><span data-stu-id="e80e2-135">For qualitative tests, select *Option*.</span></span>
    - <span data-ttu-id="e80e2-136">**Instrument de test** – Sélectionnez un [instrument de test](quality-test-instruments.md) à utiliser pour le test.</span><span class="sxs-lookup"><span data-stu-id="e80e2-136">**Test instrument** – Select a [test instrument](quality-test-instruments.md) that should be used for the test.</span></span>
    - <span data-ttu-id="e80e2-137">**Unité** - Si vous avez sélectionné *Fraction* ou alors *Entier* dans le champ **Type** (c'est-à-dire, si le test est un test quantitatif), sélectionnez l'unité de mesure dans laquelle les résultats du test doivent être enregistrés.</span><span class="sxs-lookup"><span data-stu-id="e80e2-137">**Unit** – If you selected *Fraction* or *Integer* in the **Type** field (that is, if the test is a quantitative test), select the unit of measure that test results should be recorded in.</span></span>

1. <span data-ttu-id="e80e2-138">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="e80e2-138">Close the page.</span></span>

> [!NOTE]
> <span data-ttu-id="e80e2-139">Après avoir enregistré un test, vous ne pouvez plus modifier le champ **Type** dans la grille.</span><span class="sxs-lookup"><span data-stu-id="e80e2-139">After you save a test, you can no longer edit the **Type** field in the grid.</span></span> <span data-ttu-id="e80e2-140">Si vous devez changer le type de résultats de test qui seront enregistrés pour un test, sélectionnez **Modifier le type de test de qualité** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="e80e2-140">If you must change the type of test results that will be recorded for a test, select **Change quality test type** on the Action Pane.</span></span> <span data-ttu-id="e80e2-141">Dans la boîte de dialogue **Modifier le type de test de qualité**, définissez le champ **Nouveau type** du type souhaité, puis cliquez sur **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e80e2-141">In the **Change quality test type** dialog box, set the **New type** field to the desired type, and then select **OK** to close the dialog box.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e80e2-142">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e80e2-142">Additional resources</span></span>

- [<span data-ttu-id="e80e2-143">Instruments de test de gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="e80e2-143">Quality management test instruments</span></span>](quality-test-instruments.md)
- [<span data-ttu-id="e80e2-144">Groupes de tests de gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="e80e2-144">Quality management test groups</span></span>](quality-test-groups.md)
- [<span data-ttu-id="e80e2-145">Variables de test de gestion de la qualité</span><span class="sxs-lookup"><span data-stu-id="e80e2-145">Quality management test variables</span></span>](quality-test-variables.md)
- [<span data-ttu-id="e80e2-146">Associations de qualité</span><span class="sxs-lookup"><span data-stu-id="e80e2-146">Quality associations</span></span>](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
